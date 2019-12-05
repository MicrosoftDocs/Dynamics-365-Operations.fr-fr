---
title: Mettre en œuvre des champs personnalisés pour l'application mobile Microsoft Dynamics 365 Project Timesheet sur IOS et Android
description: Cette rubrique fournit des modèles courants pour l'utilisation des extensions pour mettre en œuvre des champs personnalisés.
author: KimANelson
manager: AnnBe
ms.date: 05/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: 10.0.3
ms.search.validFrom: 2019-05-29
ms.openlocfilehash: c0c578ca44919671b67daeea51a9ec7687f755c9
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773643"
---
# <a name="implement-custom-fields-for-the-microsoft-dynamics-365-project-timesheet-mobile-app-on-ios-and-android"></a>Mettre en œuvre des champs personnalisés pour l'application mobile Microsoft Dynamics 365 Project Timesheet sur IOS et Android

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des modèles courants pour l'utilisation des extensions pour mettre en œuvre des champs personnalisés. Les rubriques suivantes sont couvertes :

- Les différents types de données que la structure de champ personnalisé prend en charge
- Comment afficher des champs en lecture seule ou modifiables sur les entrées de feuille de temps, et sauvegarder les valeurs fournies par l'utilisateur dans la base de données
- Comment afficher des champs en lecture seule sous l'en-tête de feuille de temps
- Comment intégrer une autre logique métier personnalisée pour entrer des valeurs par défaut dans les champs et effectuer un contrôle supplémentaire

## <a name="audience"></a>Public

Cette rubrique est prévue pour les développeurs qui intègrent leurs champs personnalisés dans l'application mobile Microsoft Dynamics 365 Project Timesheet disponible pour Apple IOS et Google Android. Le présupposé est que des lecteurs sont au fait du développement X++ et de la fonctionnalité de feuille de temps de projet.

## <a name="data-contract--tstimesheetcustomfield-x-class"></a>Contrat de données – classe X++ TSTimesheetCustomField

La classe **TSTimesheetCustomField** est la classe de contrat de données X++ qui représente des informations sur un champ personnalisé pour la fonctionnalité de feuille de temps. Les listes des objets de champ personnalisés sont transmises au contrat de données TSTimesheetDetails et au contrat de données TSTimesheetEntry pour afficher les champs personnalisés dans l'application mobile.

- **TSTimesheetDetails** - Le contrat d'en-tête de feuille de temps.
- **TSTimesheetEntry** - Le contrat de transaction de feuille de temps. Les groupes de ces objets avec les mêmes informations de projet et la valeur **timesheetLineRecId** constituent une ligne.

### <a name="fieldbasetype-types"></a>fieldBaseType (types)

La propriété **FieldBaseType** sur l'objet **TsTimesheetCustom** détermine le type de champ qui apparaît dans l'application. Les valeurs **Types** suivantes qui sont prises en charge.

| Valeur de types | Type              | Notes |
|-------------|-------------------|-------|
| 0           | Chaîne (et énumération) | Le champ apparaît comme champ de texte. |
| 1           | Entier           | La valeur est affichée comme nombre sans décimales. |
| 2           | Réel              | La valeur est affichée comme nombre avec décimales.<p>Pour afficher la valeur réelle comme devise dans l'application, utilisez la propriété **fieldExtenededType**. Vous pouvez utiliser la propriété **numberOfDecimals** pour définir le nombre de décimales à afficher.</p> |
| 3           | Date              | Les formats de date sont déterminés par le paramètre **Date, périodes et format de numéro** de l'utilisateur qui est spécifié sous **Préférences de langue et paramètres locaux** dans **Options utilisateur**. |
| 4           | Booléen           | |
| 15          | GUID              | |
| 16          | Int64             | |

- Si la propriété **stringOptions** n'est pas fournie dans l'objet **TSTimesheetCustomField**, un champ de texte libre est fourni à l'utilisateur.

    La propriété **stringLength** peut être utilisée pour définir la longueur maximale de chaîne que les utilisateurs peuvent entrer.

- Si la propriété **stringOptions** est indiquée dans l'objet **TSTimesheetCustomField**, ces éléments de liste sont les seules valeurs que les utilisateurs peuvent sélectionner à l'aide des boutons d'option (cases d'options).

    Dans ce cas, le champ de chaîne peut agir de valeur d'énumération destinée à l'entrée utilisateur. Pour enregistrer la valeur dans la base de données comme énumération, mettez en correspondance manuellement la valeur de chaîne avec la valeur d'énumération avant d'enregistrer dans la base de données à l'aide de la chaîne de la commande (voir la section « Utiliser la chaîne de commande sur la classe TSTimesheetEntryService pour enregistrer une entrée de feuille de temps de l'application dans la base de données » plus loin dans cette rubrique pour obtenir un exemple).

### <a name="fieldextendedtype-tscustomfieldextendedtype"></a>fieldExtendedType (TSCustomFieldExtendedType)

Vous pouvez utiliser cette propriété pour mettre en forme des valeurs réelles comme devises. Cette approche s'applique uniquement lorsque la valeur **fieldBaseType** est **Réel**.

- **TSCustomFieldExtendedType:None** – Aucune mise en forme n'est appliquée.
- **TSCustomFieldExtendedType::Currency** – Mise en forme de la valeur comme devise.

    Lorsque la mise en forme comme devises est active, le champ **stringValue** peut être utilisée pour transmettre le code devise qui doit être affiché dans l'application. La valeur est une valeur en lecture seule.

    Le champ **realValue** contient la somme d'argent qui doit être enregistrée dans la base de données.

### <a name="fieldsection-tscustomfieldsection"></a>fieldSection (TSCustomFieldSection)

Vous pouvez utiliser cette propriété pour spécifier à quel emplacement le champ personnalisé doit apparaître dans l'application.

- **TSCustomFieldSection::Header** – Le champ apparaît dans la section **Afficher plus de détails** de l'application. Ces champs sont toujours en lecture seule.
- **TSCustomFieldSection::Line** – Le champ apparaît après tous les champs de ligne prédéfinis sur les entrées de feuille de temps. Ces champs peuvent être modifiables ou en lecture seule.

### <a name="fieldname-fieldnameshort"></a>fieldName (FieldNameShort)

Cette propriété identifie le champ lorsque des valeurs que l'application fournit sont enregistrées dans la base de données.

### <a name="tablename-tablenameshort"></a>tableName (TableNameShort)

Cette propriété identifie le champ lorsque des valeurs que l'application fournit sont enregistrées dans la base de données.

### <a name="iseditable-noyes"></a>isEditable (NoYes)

Définissez cette propriété sur **Oui** pour spécifier que le champ de la section d'entrée de feuille de temps doit être modifié par les utilisateurs. Définissez la propriété sur **Non** pour rendre le champ en lecture seule.

### <a name="ismandatory-noyes"></a>isMandatory (NoYes)

Définissez cette propriété sur **Oui** pour spécifier que le champ de la section d'entrée de feuille de temps doit être obligatoire.

### <a name="label-str"></a>label (str)

Cette propriété spécifie l'étiquette qui s'affiche en regard du champ de l'application.

### <a name="stringoptions-list-of-strings"></a>stringOptions (liste des chaînes)

Cette propriété s'applique uniquement lorsque **fieldBaseType** est défini sur **Chaîne**. Si **stringOptions** est défini, les valeurs de chaîne disponibles pour la sélection à l'aide des boutons d'option (cases d'options) sont spécifiées par les chaînes dans la liste. Si aucune chaîne n'est fournie, l'entrée de texte libre est autorisée dans le champ de chaîne (voir la section « Utiliser la chaîne de commande sur la classe TSTimesheetEntryService pour enregistrer une entrée de feuille de temps de l'application dans la base de données » plus loin dans cette rubrique pour obtenir un exemple).

### <a name="stringlength-int"></a>stringLength (int)

Cette propriété spécifie la longueur maximale d'un champ de chaîne. Elle s'applique uniquement lorsque **fieldBaseType** est défini sur **Chaîne**.

### <a name="numberofdecimals-int"></a>numberOfDecimals (int)

Cette propriété spécifie le nombre de décimales à afficher pour un champ réel. Elle s'applique uniquement lorsque **fieldBaseType** est défini sur **Réel**.

### <a name="ordersequence-int"></a>orderSequence (int)

Cette propriété détermine l'ordre dans lequel les champs personnalisés sont affichés dans l'application lorsque plusieurs champs personnalisés sont spécifiés. Les champs qui ont des nombres plus petits sont affichés en premier.

### <a name="booleanvalue-boolean"></a>booleanValue (booléen)

Pour les champs de type **Booléen**, cette propriété transmet la valeur booléenne du champ entre le serveur et l'application.

### <a name="guidvalue-guid"></a>guidValue (guid)

Pour les champs de type **GUID**, cette propriété transmet la valeur de l'identificateur global unique (GUID) du champ entre le serveur et l'application.

### <a name="int64value-int64"></a>int64Value (int64)

Pour les champs de type **Int64**, cette propriété transmet la valeur int64 du champ entre le serveur et l'application.

### <a name="intvalue-int"></a>intValue (int)

Pour les champs de type **Int**, cette propriété transmet la valeur int du champ entre le serveur et l'application.

### <a name="realvalue-real"></a>realValue (real)

Pour les champs de type **Réel**, cette propriété transmet la valeur réelle du champ entre le serveur et l'application.

### <a name="stringvalue-str"></a>stringValue (str)

Pour les champs de type **Chaîne**, cette propriété transmet la valeur de chaîne du champ entre le serveur et l'application. Elle est également utilisée pour les champs de type **Réel** qui sont mis en forme comme devises. Pour ces champs, la propriété est utilisée pour transmettre un code devise à l'application.

### <a name="datevalue-date"></a>dateValue (date)

Pour les champs de type **Date**, cette propriété transmet la valeur de date du champ entre le serveur et l'application.

## <a name="show-and-save-a-custom-field-in-the-timesheet-entry-section"></a>Afficher et enregistrer un champ personnalisé dans la section des entrées de feuille de temps

Voici une capture d'écran de l'application mobile d'une création d'entrée de feuille de temps. Elle affiche les champs prédéfinis et un champ personnalisé dans la chaîne « Entrée de temps » appelée « Chaîne de test » avec une valeur d'énumération « Seconde option » déjà définie.

![Champ personnalisé de chaîne de test dans l'application](media/timesheet-entry.jpg)



Voici une capture d'écran de l'application mobile de l'utilisateur sélectionnant l'une des options d'énumération disponibles pour le champ personnalisé « Chaîne de test ».  Les deux options sont « Première option » et « Seconde option » affichées sous forme de cases d'options. La seconde option est sélectionnée actuellement.

![Boutons d'option (cases d'options) du champ personnalisé Chaîne de test](media/enum-option.jpg)



### <a name="extend-the-tstimesheetline-table-so-that-it-has-a-custom-field"></a>Étendre la table TSTimesheetLine afin qu'elle dispose d'un champ personnalisé

Dans les scénarios typiques, il est probable que les données d'un champ personnalisé dans la section des entrées de feuille de temps soient enregistrées dans la table TSTimesheetLine. Toutefois, d'autres tables peuvent être utilisées si les données peuvent être extraites selon un enregistrement TSTimesheetTrans qui est fourni, ou s'il n'y a pas de contexte spécifique d'enregistrement (par exemple, si le champ est défini en lecture seule dans les paramètres de projet).

Notez que les champs personnalisés ne doivent pas avoir d'enregistrements de base de données de sauvegarde. Ils peuvent être générés dynamiquement selon la logique X++. Cette approche peut être utile dans les scénarios en lecture seule (voir la section « Utiliser la chaîne de commande sur la classe TSTimesheetDetails, la méthode buildCustomFieldListForHeader pour renseigner les détails de la feuille de temps » pour obtenir un exemple de valeurs de champ personnalisé générées dynamiquement.)

Voici une capture d'écran Visual Studio de l'arbre d'objets d'application. Elle présente une extension de la table TSTimesheetLine avec le champ TestLineString ajouté comme champ personnalisé.

![Chaîne de ligne](media/b6756b4a3fc5298093327a088a7710fd.png)

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-timesheet-entry-section"></a>Section Utiliser la chaîne de commande sur la méthode buildCustomFieldList de la classe TSTimesheetSettings pour afficher un champ dans l'entrée de feuille de temps

Ce code contrôle les paramètres d'affichage du champ dans l'application. Par exemple, il contrôle le type de champ, l'étiquette, si le champ est obligatoire, et dans quelle section le champ apparaît.

L'exemple suivant montre un champ de chaîne sur les entrées de temps. Ce champ propose deux options, **Première option** et **Deuxième option**, disponibles via les boutons d'option (cases d'options). Le champ dans l'application est associé au champ **TestLineString** ajouté à la table TSTimesheetLine.

Notez l'utilisation de la méthode **TSTimesheetCustomField::newFromMetatdata()** pour simplifier l'initialisation des propriétés de champ personnalisées : **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength**, et **numberOfDecimals**. Vous pouvez également définir ces paramètres manuellement, comme vous le souhaitez.

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('Second option');
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforentry-method-of-the-tstimesheetentry-class-to-enter-values-in-a-timesheet-entry"></a>Utiliser la chaîne de commande sur la méthode buildCustomFieldListForEntry de la classe TSTimesheetEntry pour entrer des valeurs dans une entrée de feuille de temps

La méthode **buildCustomFieldListForEntry** est utilisée pour entrer des valeurs dans les lignes de feuille de temps enregistrées dans l'application mobile. Elle utilise un enregistrement TSTimesheetTrans comme paramètre. Les champs de cet enregistrement peuvent être utilisés pour renseigner la valeur du champ personnalisé dans l'application.

```
...
[ExtensionOf(classStr(TsTimesheetEntry))]
final class TsTimesheetEntry_Extension
{
    protected List buildCustomFieldListForEntry(TSTimesheetTrans _tsTimesheetTrans)
    {
        List customFieldList = next buildCustomFieldListForEntry(_tsTimesheetTrans);
        TSTimesheetLine tsTimesheetLine = _tsTimesheetTrans.timesheetLine();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        tsTimesheetCustomField.parmStringValue(tsTimesheetLine.TestLineString);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('second option;);
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-tstimesheetentryservice-class-to-save-a-timesheet-entry-from-the-app-back-to-the-database"></a>Utiliser la chaîne de commande sur la classe TSTimesheetEntryService pour enregistrer une entrée de feuille de temps depuis l'application dans la base de données

Pour enregistrer un champ personnalisé dans la base de données dans un usage classique, vous devez étendre plusieurs méthodes :

- La méthode **timesheetLineNeedsUpdating** est utilisée pour déterminer si l'enregistrement de ligne a été modifié par l'utilisateur de l'application et doit être enregistré dans la base de données. Si les performances ne sont pas un problème, cette méthode peut être simplifiée de sorte qu'elle renvoie toujours **true**.
- Les méthodes **populateTimesheetLineFromEntryDuringCreate** et **populateTimesheetLineFromEntryDuringUpdate** peuvent être étendues afin qu'elles entrent des valeurs dans l'enregistrement de base de données TSTimesheetLine de l'enregistrement de contrat de données TSTimesheetEntry qui est fourni. Dans l'exemple suivant, notez comment la mise en correspondance entre le champ de base de données et le champ d'entrée manuelle est effectuée via un code X++.
- La méthode **populateTimesheetWeekFromEntry** peut également être étendue si le champ personnalisé qui est mis en correspondance avec l'objet **TSTimesheetEntry** doit écrire dans la table de base de données TSTimesheetLineweek.

> [!NOTE]
> L'exemple suivant enregistre la valeur **firstOption** ou **secondOption** que l'utilisateur sélectionne dans la base de données comme valeur de la chaîne brute. Si le champ de base de données est un champ de type **Énumération**, ces valeurs peuvent être manuellement mises en correspondance avec une valeur d'énumération puis enregistrées dans un champ d'énumération de la table de base de données.

```
...
[ExtensionOf(classStr(TSTimesheetEntryService))]
final class TSTimesheetEntryService_Extension
{
    protected boolean timesheetLineNeedsUpdating(TSTimesheetLine _tsTimesheetLine,
    TsTimesheetEntry _tsTimesheetEntry)
    {
        boolean ret = next timesheetLineNeedsUpdating(_tsTimesheetLine,
        _tsTimesheetEntry);
        if (!ret)
        {
            */ Loop through custom fields to see if value needs updating*/
            ListEnumerator enumerator =  _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    */ If Custom field value for TestLineString field has changed, We need to update the timesheet line.*/
                    if (_tsTimesheetLine.TestLineString != customField.parmStringValue())
                    {
                        ret = true;
                    }
                }
            }
        }
        return ret;
    }
    protected void populateTimesheetLineFromEntryDuringCreate(TSTimesheetLine
    _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
    {
        next populateTimesheetLineFromEntryDuringCreate(_tsTimesheetLine,
        _tsTimesheetEntry);
        this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
        _tsTimesheetEntry);
        }
        protected void populateTimesheetLineFromEntryDuringUpdate(TSTimesheetLine
        \_tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            next populateTimesheetLineFromEntryDuringUpdate(_tsTimesheetLine,
            _tsTimesheetEntry);
            this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
            _tsTimesheetEntry);
        }
        private void populateTimesheetLineFromCustomFields(TSTimesheetLine
        _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            ListEnumerator enumerator =
            _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    _tsTimesheetLine.TestLineString = customField.parmStringValue();
                }
            }
        }
    }
...
```

## <a name="show-a-custom-field-in-the-timesheet-header-section"></a>Afficher un champ personnalisé dans la section d'en-tête de feuille de temps

Voici une capture d'écran de l'application mobile d'un utilisateur affichant une feuille de temps. Le bouton « Informations supplémentaires » a été sélectionné dans l'angle supérieur droit pour afficher l'option « Afficher plus de détails ».  

![Commande Afficher plus de détails](media/show-more.png)

Voici une capture d'écran de l'application mobile affichant la section « Plus » d'une feuille de temps. Un champ personnalisé appelé « Taux d'utilisation de cette feuille de temps (champ personnalisé calculé) » a été ajouté dans la section d'en-tête de feuille de temps. Une valeur en lecture seule de « 0,667 » est définie dans le champ personnalisé.

![Section Plus](media/more-section.jpg)

### <a name="extend-the-tstimesheettable-table-so-that-it-has-a-custom-field"></a>Étendre la table TSTimesheetTable afin qu'elle dispose d'un champ personnalisé

Dans les scénarios typiques, il est probable que les données d'un champ personnalisé dans la section d'en-tête soient extraites de la table TSTimesheetHeader. Toutefois, d'autres tables peuvent être utilisées si les données peuvent être extraites selon un enregistrement TSTimesheetTable qui est fourni, ou s'il n'y a pas de contexte spécifique d'enregistrement (par exemple, si le champ est défini en lecture seule dans les paramètres de projet).

Notez que les champs personnalisés ne doivent pas avoir d'enregistrements de base de données de sauvegarde. Ils peuvent être générés dynamiquement selon la logique X++. L'exemple suivant montre cette approche.

Les champs de la section d'en-tête sont toujours en lecture seule dans l'application.

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-header-section"></a>Section Utiliser la chaîne de commande sur la méthode buildCustomFieldList de la classe TSTimesheetSettings pour afficher un champ dans l'en-tête

Ce code contrôle les paramètres d'affichage du champ dans l'application. Par exemple, il contrôle le type de champ, l'étiquette, si le champ est obligatoire, et dans quelle section le champ apparaît.

L'exemple suivant montre une valeur calculée dans la section d'en-tête de l'application.

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforheader-method-of-the-tstimesheetdetails-class-to-fill-in-timesheet-details"></a>Utiliser la chaîne de commande sur la méthode buildCustomFieldListForHeader de la classe TSTimesheetDetails pour renseigner des informations dans une feuille de temps

La méthode **buildCustomFieldListForHeader** est utilisée pour renseigner des détails de l'en-tête de la feuille de temps dans l'application mobile. Elle utilise un enregistrement TSTimesheetTable comme paramètre. Les champs de cet enregistrement peuvent être utilisés pour renseigner la valeur du champ personnalisé dans l'application. L'exemple suivant ne lit aucune valeur de la base de données. Au lieu de cela, il utilise la logique X++ pour générer une valeur calculée qui est ensuite affichée dans l'application.


```
...
[ExtensionOf(classStr(TSTimesheetDetails))]
final class TSTimesheetDetails_Extension
{
    protected List buildCustomFieldListForHeader(TSTimesheetTable
    _tsTimesheetTable)
    {
        List customFieldList = next buildCustomFieldListForHeader(_tsTimesheetTable);
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        real utilizationRate = 0;
        if (_tsTimesheetTable.totalHours() != 0)
        {
            utilizationRate = _tsTimesheetTable.totalHoursBillable() /
            _tsTimesheetTable.totalHours();
        }
        tsTimesheetCustomField.parmRealValue(utilizationRate);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

## <a name="other-configurabilityextensibility-opportunities"></a>Autres possibilités de configuration/extensibilité

### <a name="adding-additional-validation-for-the-app"></a>Ajout d'un contrôle supplémentaire pour l'application

La logique existante pour la fonctionnalité de feuille de temps au niveau de la base de données fonctionne toujours comme prévu. Pour interrompre l'exécution de l'enregistrement ou envoyer des opérations et afficher un message d'erreur spécifique, vous pouvez ajouter **throw error("message to user")** au code via une chaîne d'extension de commande. Voici trois exemples de méthodes extensibles utiles :

- Si **validateWrite** dans la table TSTimesheetLine renvoie **false** au cours d'une opération d'enregistrement pour une ligne de feuille de temps, un message d'erreur s'affiche dans l'application mobile.
- Si **validateSubmit** dans la table TSTimesheetTable renvoie **false** au cours de l'envoi d'une feuille de temps dans l'application, un message d'erreur s'affiche pour l'utilisateur.
- La logique qui renseigne les champs (par exemple, **Propriété de ligne**) lors de la méthode **insert** dans la table TSTimesheetLine s'exécute toujours.

### <a name="hiding-and-marking-out-of-box-fields-as-read-only-via-configuration"></a>Masquage et marquage des champs prédéfinis comme en lecture seule via la configuration

Dans les paramètres de projet, vous pouvez rendre les champs prédéfinis en lecture seule ou les masquer dans l'application mobile. Définissez les options de la section **Feuilles de temps mobiles** sur l'onglet **Feuille de temps** de la page **Paramètres de gestion et comptabilité des projets**.

![Paramètres de projet](media/5753b8ecccd1d8bb2b002dd538b3f762.png)

### <a name="changing-the-activities-that-are-available-for-selection-via-extensions"></a>Modification des activités disponibles pour la sélection via les extensions

Les activités disponibles pour la sélection d'un projet sont renseignées via les méthodes **getActivitiesForProject()** et **getActivityQuery()** dans la classe **TsTimesheetProjectService**. Vous pouvez utiliser une chaîne de commande pour modifier ce comportement en fonction de votre scénario métier pour les activités disponibles pour la sélection pour un projet spécifique.

### <a name="entering-a-default-project-category-on-timesheet-entries"></a>Entrée d'une catégorie de projet par défaut dans les entrées de feuille de temps

L'entrée d'une catégorie de projet par défaut dans les entrées de feuille de temps se produit à trois niveaux. Vous pouvez utiliser la chaîne de commande pour étendre le comportement à tout ou partie de ces niveaux pour obtenir le comportement souhaité. La hiérarchie utilisée est la suivante :

1. L'application essaie de mettre la catégorie par défaut de la ressource de projet. Cette catégorie par défaut est définie dans les méthodes **getCurrentUserResource** et **getDelegatedResourcesForCurrentUser** dans la classe **TSTimesheetSettingsService**.
2. Si la catégorie par défaut n'est pas fournie au niveau de ressources de projet, l'application essaie de l'extraire de l'activité de projet. Cette catégorie par défaut est définie dans la méthode **getActivitiesForProject** de la classe **TSTimesheetProjectService**.
3. Si la catégorie par défaut n'est pas fournie au niveau de l'activité de projet, la catégorie de projet est extraite des paramètres du projet. Cette catégorie par défaut est définie dans la méthode **getProjectDetailsbyRule** de la classe **TSTimesheetProjectService**.
