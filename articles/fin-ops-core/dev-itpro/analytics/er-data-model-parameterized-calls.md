---
title: Prendre en charge les appels paramétrés des modèles de données ER
description: Cette rubrique explique comment implémenter des appels paramétrés de modèles de données de gestion des états électroniques (ER).
author: NickSelin
ms.date: 03/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula, ERDataModelDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-10-01
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 968b0769607e9fdbed57c25b727ed44988a92913
ms.sourcegitcommit: 399d0d3f8e2ebb81b6b9d640365ebe182690bab2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2022
ms.locfileid: "8419469"
---
# <a name="support-parameterized-calls-of-er-data-models"></a>Prendre en charge les appels paramétrés des modèles de données ER

[!include [banner](../includes/banner.md)]

Pour générer des documents commerciaux, vous configurez une solution de [gestion des états électroniques (ER)](general-electronic-reporting.md) qui contient les composants ER suivants :

- **[Format](er-overview-components.md#format-component)** – Ce composant spécifie la structure d’un document commercial.
- **Mappage des formats** – Ce composant contrôle la manière dont un document commercial est rempli au moment de l’exécution.
- **[Mappage de modèles](er-overview-components.md#model-mapping-component)** – Ce composant spécifie ce que les données extraient de l’application dans un mappage de format.
- **[Modèle de données](er-overview-components.md#data-model-component)** – Ce composant transmet des informations entre les composants individuels.

Lorsque vous exécutez un format ER, chaque élément de format est exécuté, à partir de l’élément de format racine. Chaque fois qu’un élément de format exécuté contient une liaison vers une [source de données](general-electronic-reporting.md#configuring-data-model-mappings-for-outgoing-documents), la source de données est exécutée pour fournir les données attendues et les utiliser pour remplir l’élément de format. Lorsqu’une source de données de type *Modèle* est appelée, le mappage de modèles approprié est appelé pour extraire les données de l’application, en fonction des paramètres de mappage de modèles.

Auparavant, ces appels de mappage de modèles ne pouvaient pas être paramétrés pour les rendre dépendants de la logique du format exécuté. Seul le flux de données suivant était pris en charge.

<table>
<tbody>
<tr align="center">
<td>
<b>Format</b><br>
Élément&nbsp;Format<br>
&nbsp;
</td>
<td>
<i>Liaison</i><br>
&gt;&nbsp;demande&nbsp;&gt;<br>
&lt;&nbsp;valeur&nbsp;&lt;
</td>
<td><b>Mappage&nbsp;des formats</b><br>
Source de données<br>
&nbsp;
</td>
<td>
<i>Modèle&nbsp;de données</i><br>
&gt;&nbsp;demande&nbsp;&gt;<br>
&lt;&nbsp;valeur&nbsp;&lt;
</td>
<td>
<b>Mappage&nbsp;de modèles</b><br>
Source&nbsp;de données<br>
&nbsp;
</td>
<td>
<i>Liaison</i><br>
&gt;&nbsp;demande&nbsp;&gt;<br>
&lt;&nbsp;valeur&nbsp;&lt;
</td>
<td>
<b>Enregistrement</b><br>
Enregistrer<br>
Champ
</td>
</tr>
</tbody>
</table>

Cependant, dans la version 10.0.15 et les versions ultérieures, vous pouvez configurer des champs de modèle de données qui ne peuvent être appelés que lorsque les valeurs des paramètres configurés sont fournies. Lorsqu’un tel champ est configuré et appelé à partir d’un composant de format, les paramètres requis doivent être fournis dans une liaison de format en tant qu’arguments de l’appel. Dans ces cas, les valeurs des arguments peuvent être spécifiées en fonction de valeurs spécifiques au format. Par conséquent, vous pouvez utiliser la **paramétrisation d’exécution dynamique** pour les appels de modèle de données afin de prendre en charge le flux de données suivant.

<table>
<tbody>
<tr align="center">
<td>
<b>Format</b><br>
Élément&nbsp;Format&nbsp;1<br>
<br>
Élément&nbsp;Format&nbsp;2<br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Liaison</i><br>
&gt;&nbsp;demande&nbsp;1&nbsp;&gt;<br>
&lt;&nbsp;valeur&nbsp;1&nbsp;&lt;<br>
&gt;&nbsp;demande&nbsp;2&nbsp;&gt;<br>
&lt;&nbsp;valeur&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Mappage&nbsp;des formats</b><br>
Source&nbsp;de données&nbsp;1<br>
&nbsp;<br>
<b>value2=Func(value1)</b><br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Modèle&nbsp;de données</i><br>
&gt;&nbsp;field1&nbsp;&gt;<br>
&lt;&nbsp;valeur&nbsp;1&nbsp;&lt;<br>
<b>&gt;&nbsp;field2(value2)&nbsp;&gt;</b><br>
&lt;&nbsp;valeur&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Mappage&nbsp;de modèles</b><br>
Source&nbsp;de données&nbsp;1<br>
<br>
Source&nbsp;de données&nbsp;2<br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Liaison</i><br>
&gt;&nbsp;demande&nbsp;1&nbsp;&gt;<br>
&lt;&nbsp;valeur&nbsp;1&nbsp;&lt;<br>
&gt;&nbsp;demande&nbsp;2&nbsp;&gt;<br>
&lt;&nbsp;valeur&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Table&nbsp;1</b><br>
Enregistrement&nbsp;1<br>
Champ&nbsp;1<br>
<b>Table&nbsp;2</b><br>
Enregistrement&nbsp;2<br>
Champ&nbsp;2
</td>
</tr>
</tbody>
</table>

La nouvelle fonctionnalité vous permet de paramétriser l’appel vers n’importe quel champ de modèle de données de type [*Enregistrement*](er-formula-supported-data-types-composite.md#record) ou [*Liste d’enregistrement*](er-formula-supported-data-types-composite.md#record-list). Les types de données suivants sont pris en charge pour les paramètres d’un champ de modèle de données :

- [Booléen](er-formula-supported-data-types-primitive.md#boolean)
- [Conteneur](er-formula-supported-data-types-composite.md#container)
- [Date](er-formula-supported-data-types-primitive.md#date)
- [Date et heure](er-formula-supported-data-types-primitive.md#datetime)
- [GUID](er-formula-supported-data-types-primitive.md#guid)
- [Int64](er-formula-supported-data-types-primitive.md#int64)
- [Entier](er-formula-supported-data-types-primitive.md#integer)
- [Réel](er-formula-supported-data-types-primitive.md#real)
- [Chaîne](er-formula-supported-data-types-primitive.md#string)

Vous pouvez spécifier chaque paramètre d’un champ de modèle de données pour lequel l’argument peut être fourni comme une valeur unique du type de données défini et la [*liste*](er-formula-supported-data-types-composite.md#record-list) de telles valeurs.

> [!NOTE]
> La valeur par défaut du paramètre d’un champ de modèle de données n’est pas prise en charge. Si vous ajoutez un paramètre à un champ dans un modèle de données et que la version de ce modèle de données a déjà été lancée et publiée, vous devez [rebaser](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase) tous les mappages et formats de modèle correspondants à la nouvelle version de ce modèle, car cette modification du modèle de données n’est pas rétrocompatible.

Vous pouvez configurer des champs de modèle de données paramétrés pour rendre les appels de mappage de modèle spécifiques au format. Cette approche peut vous aider à réduire le nombre de mappages de modèles qui doivent être configurés pour de nombreux formats d’un modèle de données unique. Vous pouvez également utiliser cette approche pour améliorer les performances d’exécution de vos formats et réduire le temps nécessaire à la génération de documents commerciaux. Pour en savoir plus sur cette fonctionnalité, exécutez l’exemple décrit dans cette rubrique.

## <a name="example-use-parameterized-calls-of-er-data-models"></a>Exemple : Utiliser les appels paramétrés des modèles de données ER

Les étapes suivantes expliquent comment un utilisateur dans le rôle d’administrateur système ou de développeur de gestion des états électroniques peut concevoir une solution ER qui contient un modèle de données, un mappage de modèle et un composant ER de format qui sont configurés pour appeler un mappage de modèle à partir d’un format en fournissant un argument de l’appel dont la valeur a été calculée à l’exécution en utilisant la formule du format d’exécution. 

Ces étapes peuvent être effectuées dans la société **DEMF**. Aucune modification de code n’est requise. 

Dans cet exemple, vous créerez les [configurations](general-electronic-reporting.md#Configuration) ER requises pour la société fictive, **Litware, Inc**. Veillez à ce que le fournisseur de configuration pour l’exemple de société **Litware, Inc.** (`http://www.litware.com`) soit répertorié pour la structure ER et qu’il soit marqué comme **actif**. Si ce fournisseur de configuration n’est pas répertorié ou s’il n’est pas marqué comme **actif**, suivez les étapes de la rubrique [Créer un fournisseur de configuration et le marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="business-scenario"></a>Scénario d’entreprise

Vous disposez d’une solution ER qui inclut un format que vous pouvez exécuter pour générer un document électronique à des fins d’audit. Ce format contient les transactions de taxe liées aux commandes client et aux commandes fournisseurs, et qui contiennent les détails requis, tels que la date de transaction et la valeur de la taxe. À compter du nouvel exercice, la structure de ce document a changé. Vous devez maintenant soumettre un document étendu qui inclut des détails supplémentaires (noms) de toutes les parties (clients et fournisseurs) dont les transactions sont présentées sur les états générés. Vous devez donc modifier votre solution ER afin qu’elle génère des documents conformes à cette nouvelle exigence.

### <a name="configure-the-er-framework"></a>Configurer la structure de gestion des états électroniques

Procédez comme suit dans [Configurer la structure des états électroniques](er-quick-start2-customize-report.md#ConfigureFramework) pour configurer l’ensemble minimum de paramètres d’état électronique. Vous devez terminer cette configuration avant de commencer à utiliser la structure des états électroniques pour concevoir une nouvelle solution de gestion des états électroniques.

### <a name="design-a-domain-specific-data-model"></a>Concevoir un modèle de données spécifique à un domaine

Vous devez créer une configuration de la gestion des états électroniques contenant un composant de modèle de données requis. Ce modèle de données sera ultérieurement utilisé comme source de données lorsque vous concevez un format ER pour générer un rapport d’audit.

Suivez ces étapes pour importer le modèle de données requis à partir d’un fichier XML fourni par Microsoft.

1. Téléchargez le fichier [Sample audit model.version.1.xml](https://download.microsoft.com/download/7/1/9/719b0132-fed7-4c73-8afa-90cac29c2fee/Sample-audit-model.version.1.xml) et enregistrez-le sur votre ordinateur local.
2. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
3. Dans l’espace de travail **Génération des états électronique**, sélectionnez **Configurations des états**.
4. Sur la page **Configurations**, dans le volet Action, sélectionnez **Échanger** \> **Charger depuis le fichier XML**.
5. Sélectionnez **Parcourir**, puis recherchez et sélectionnez le fichier **Sample audit model.version.1.xml**.
6. Sélectionnez **OK** pour importer la configuration.

    ![Configuration du modèle de données ER importé sur la page Configurations.](./media/er-data-model-parameterized-calls-imported-model.png)

L’illustration suivante montre le modèle de données configuré de la version modifiable sur la page **Concepteur de modèles de données**.

![Structure du modèle de données ER sur la page Concepteur de modèle de données.](./media/er-data-model-parameterized-calls-model1.png)

Actuellement, le modèle est conçu pour exposer uniquement les transactions fiscales qui contiennent les détails requis.

### <a name="design-a-model-mapping-for-the-configured-data-model"></a>Concevoir une mise en correspondance de modèles pour le modèle de données configuré

En tant qu’utilisateur avec le rôle de développeur d’états électroniques, vous devez créer une configuration de la gestion des états électroniques contenant un composant de mappage de modèles pour le modèle de données Exemple d’audit. Ce composant implémente le modèle de données configuré pour Microsoft Dynamics 365 Finance, il est spécifique à cette application. Vous devez configurer le composant de mise en correspondance des modèles pour spécifier les objets d’application qui doivent être utilisés pour remplir le modèle de données configuré avec les données d’application au moment de l’exécution. Pour effectuer cette tâche, vous devez comprendre la mise en œuvre de la structure de données du domaine d’activités de taxe dans Finance.

Suivez ces étapes pour importer la mise en correspondance de modèle requise à partir d’un fichier XML fourni par Microsoft.

1. Téléchargez le fichier [Sample audit model mapping.version.1.1.xml](https://download.microsoft.com/download/c/0/3/c03a4673-b1b1-4ef8-96d0-bf96518be6e0/Sample-audit-model-mapping.version.1.1.xml) et enregistrez-le sur votre ordinateur local.
2. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
3. Dans l’espace de travail **Génération des états électronique**, sélectionnez **Configurations des états**.
4. Sur la page **Configurations**, dans le volet Action, sélectionnez **Échanger** \> **Charger depuis le fichier XML**.
5. Sélectionnez **Parcourir**, puis recherchez et sélectionnez le fichier **Sample audit model mapping.version.1.1.xml**.
6. Sélectionnez **OK** pour importer la configuration.

    ![Configuration de la mise en correspondance de modèle ER importé sur la page Configurations.](./media/er-data-model-parameterized-calls-imported-mapping.png)

L’illustration suivante montre la version modifiable du mappage de modèles configuré sur la page **Concepteur de mappage de modèles**.

![Structure de mise en correspondance de modèle ER sur la page Concepteur de mise en correspondance de modèle.](./media/er-data-model-parameterized-calls-mapping1.png)

Actuellement, le mappage de modèles est conçu pour exposer uniquement les transactions fiscales qui contiennent les détails requis. Il récupère ces informations à partir de la table d’application `TaxTrans` à l’aide des sources de données ER `TaxTrans` et `TaxTransFiltered` configurées.

### <a name="design-a-new-format"></a>Conception d’un nouveau format

En tant qu’utilisateur avec un rôle de Consultant fonctionnel de gestion des états électroniques, vous devez créer une configuration ER contenant un composant de format. Vous devez configurer le composant de format pour remplir les états générés avec les transactions fiscales qui contiennent tous les détails requis.

Suivez ces étapes pour importer le format requis à partir d’un fichier XML fourni par Microsoft.

1. Téléchargez le fichier [Sample audit format.version.1.1.xml](https://download.microsoft.com/download/e/b/7/eb7e126e-2bb3-4bbb-a735-ffd4c48920b1/Sample-audit-format.version.1.1.xml) et enregistrez-le sur votre ordinateur local.
2. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
3. Dans l’espace de travail **Génération des états électronique**, sélectionnez **Configurations des états**.
4. Sur la page **Configurations**, dans le volet Action, sélectionnez **Échanger** \> **Charger depuis le fichier XML**.
5. Sélectionnez **Parcourir**, puis recherchez et sélectionnez le fichier **Sample audit format.version.1.1.xml**.
6. Sélectionnez **OK** pour importer la configuration.

    ![Configuration du format ER importé sur la page Configurations.](./media/er-data-model-parameterized-calls-imported-format.png)

L’illustration suivante montre la version modifiable du format configuré sur la page **Concepteur de format**.

![Structure du format ER sur la page Concepteur de format.](./media/er-data-model-parameterized-calls-format1.png)

Le format ER est configuré pour générer un état sous forme de fichier texte au format CSV (valeurs séparées par des virgules).

### <a name="run-the-imported-format"></a>Exécuter le format ER importé

1. Sur la page **Configurations**, sélectionnez la configuration **Exemple de format d’audit**, puis, dans le volet Actions, sélectionnez **Exécuter**.
2. Dans la boîte de dialogue **Paramètres du rapport de gestion des états électroniques**, sur l’onglet **Enregistrements à inclure**, sélectionnez **Filtre**.
3. Spécifiez les conditions pour sélectionner les transactions fiscales des documents **PIV-110000004** et **INV-10000001**.
4. Cliquez sur **OK**.
5. Cliquez sur **OK**.
6. Vérifiez le document généré qui contient les transactions fiscales des documents sélectionnés.

    ![Aperçu du document généré avec les transactions fiscales.](./media/er-data-model-parameterized-calls-output1.png)

### <a name="adjust-the-imported-er-solution"></a>Ajuster la solution ER importée

Selon la nouvelle exigence, le document que vous devez soumettre doit contenir les noms des clients et des fournisseurs dont les transactions sont incluses. Vous devez donc modifier votre solution ER importée afin qu’elle génère un document conforme à cette nouvelle exigence.

Décidez comment vous souhaitez implémenter les modifications requises des composants ER importés.

L’approche évidente consiste à implémenter les modifications suivantes :

- Dans votre modèle de données, ajoutez le nouveau champ du modèle de données `Transaction.Party.Name` de type *Chaîne*.
- Dans votre mappage de modèles, configurez la liaison pour le nouveau champ de modèle de données en utilisant les relations de table disponibles pour accéder à l’enregistrement pertinent de la table d’application `DirPartyTable` et récupérez la valeur du champ `Name` de celui-ci.

Bien que cette approche fonctionne, elle peut entraîner des problèmes de performances dans la base de données SQL, car `TaxTrans` est la table des transactions et peut donc contenir un grand volume d’enregistrements. Dans ce cas, le nombre d’appels à `DirPartyTable` doit être égal au nombre d’enregistrements dans la table `TaxTrans` qui peut entraîner des problèmes de performances.

Vous pouvez également implémenter les modifications suivantes :

- Dans votre modèle de données, ajoutez la nouvelle racine `Party` et le nouveau champ `Party.Name`.
- Dans votre mappage de modèles, ajoutez une nouvelle source de données qui rejoindra tous les enregistrements de tables utilisés dans les relations de table pour accéder à l’enregistrement pertinent de la table d’application `DirPartyTable`, à partir de la table `TaxTrans`.

Bien que cette approche fonctionne, elle peut entraîner des problèmes de consommation de mémoire. Même lorsqu’une nouvelle source de données [JOIN](er-join-data-sources.md) est exécutée en tant que requête SQL unique à la base de données d’application pour éviter les problèmes de performances de la base de données, le résultat doit être récupéré dans la mémoire du serveur d’application. Étant donné que le nombre d’enregistrements et le nombre de champs dans ces enregistrements seront assez importants, cette approche peut entraîner une consommation de mémoire très importante. Une exception d’exécution de mémoire insuffisante peut même être levée.

Vous pouvez implémenter les modifications lorsqu’un format en cours d’exécution collecte, en mémoire, les codes d’identification uniques des clients et des fournisseurs pour toutes les transactions fiscales qui seront présentées sur un rapport généré. Étant donné que seuls les codes uniques doivent être conservés, l’ensemble final de codes ne sera pas assez grand pour affecter la consommation de mémoire. L’ensemble de codes sera ensuite passé au mappage du modèle comme argument d’un autre appel de la source de données du type *Modèle*. Sur la base de cet appel, le mappage du modèle exécutera une nouvelle source de données ER qui envoie une seule requête SQL à la base de données d’application pour extraire, à partir de la table `DirPartyTable`, enregistre uniquement les parties dont les codes sont présentés dans l’ensemble de codes fourni.

### <a name="adjust-the-imported-data-model"></a>Ajuster le modèle de données importé

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configurations du volet gauche, sélectionnez **Modèle d’exemple d’audit**.
3. Dans le raccourci **Versions**, sélectionnez la version **2** ayant un statut défini sur **[Brouillon](general-electronic-reporting.md#component-versioning)**.
4. Sélectionnez l’organisateur **Composants de configuration**.
5. Sélectionnez **Concepteur** pour ouvrir le modèle de données pour modification.
6. Sur la page **Modèle de données**, veillez à ce que le champ `Root` soit sélectionné, puis sélectionnez **Nouveau**.
7. Dans la boîte de dialogue déroulante, procédez comme suit :

    1. Dans le groupe de champs **Nouveau nœud en tant que**, sélectionnez l’option **Enfant d’un nœud actif**.
    2. Dans le champ **Nom**, entrez **Partie**.
    3. Dans le champ **Type d’article**, sélectionnez **Liste d’enregistrements**.
    4. Pour finir d’ajouter le nouveau champ, sélectionnez **Ajouter**.

8. Veillez à ce que le champ `Root.Party` soit sélectionné, puis sur l’onglet **Nœud**, sélectionnez **Paramètres**.
9. Dans la boîte de dialogue **Paramètres**, procédez comme suit :

    1. Dans l’onglet **Paramètres**, sélectionnez **Nouveau**.
    2. Dans le champ **Nom**, entrez **PartyRefRecId**.
    3. Dans le champ **Type**, sélectionnez **Int64**.
    4. Activez la case à cocher **Liste**.
    5. Sélectionnez **OK** pour terminer la saisie des paramètres.

    > [!NOTE]
    > Vous venez de configurer le champ du modèle de données `Root.Party` en tant que champ appelé lorsqu’une valeur est fournie dans le paramètre **PartyRefRecId**. Cette valeur doit être présente dans la liste des enregistrements contenant un champ `Value` du type de données *Int64*.

    ![Boîte de dialogue Paramètres.](./media/er-data-model-parameterized-calls-model2a.png)

10. Assurez-vous que le champ `Root.Party` est toujours sélectionné, puis sélectionnez **Nouveau**.
11. Dans la boîte de dialogue déroulante, procédez comme suit :

    1. Dans le groupe de champs **Nouveau nœud en tant que**, sélectionnez l’option **Enfant d’un nœud actif**.
    2. Dans le champ **Nom**, entrez **Nom**.
    3. Dans le champ **Type d’article**, sélectionnez **Chaîne**.
    4. Pour finir d’ajouter le nouveau champ, sélectionnez **Ajouter**.

12. Sélectionnez **Enregistrer**, puis fermez la page **Modèles de données**.

    ![Structure du modèle de données ER ajusté sur la page Concepteur de modèle de données.](./media/er-data-model-parameterized-calls-model2b.png)

13. Dans le raccourci **Versions**, pour la version **2**, sélectionnez **Modifier le statut** \> **Terminé**. Puis sélectionnez **OK**.

    > [!NOTE]
    > Les modifications de votre modèle de données sont stockées dans la deuxième révision du composant du modèle de données **Exemple de modèle d’audit** situé dans la deuxième version de la configuration ER **Exemple de modèle d’audit**.

![Configuration du modèle de données ER mise à jour sur la page Configurations.](./media/er-data-model-parameterized-calls-updated-model.png)

### <a name="adjust-the-imported-model-mapping"></a>Ajuster le mappage des modèles importés

1. Sur la page **Configurations**, dans l’arborescence de configurations du volet gauche, développez **Modèle d’exemple d’audit**.
2. Sélectionnez **Exemple de mappage de modèle d’audit**, puis, sur le raccourci **Versions**, sélectionnez la deuxième version de mappage basée sur la première version du modèle de données (version **1.2**), et dont le statut est défini sur **Brouillon**.
3. Sélectionnez **Redéfinir**.
4. Dans le champ **Version cible**, laissez la version **2** du modèle de base **Exemple de modèle d’audit**.
5. Sélectionnez **OK** pour rebaser et aligner votre mappage de modèles avec les modifications récentes du modèle de données.

    Notez que le numéro de version de votre mappage de modèles modifiable est passé de **1,2** à **2,2** pour indiquer que la deuxième version du modèle est actuellement utilisée comme base.

6. Sélectionnez **Concepteur**.
7. Sur la page **Mappage de modèles à une source de données**, sélectionnez **Concepteur** pour le mappage de modèle actuel.
8. Suivez ces étapes pour ajouter une nouvelle source de données afin d’accéder à la table d’application `DirPartyTable` :

    1. Dans le volet **Type de sources de données**, sélectionnez **Dynamics 365 for Operations \> Enregistrements de la table**.
    2. dans le volet **Sources de données**, sélectionnez **Ajouter une racine**.
    3. Dans le champ **Nom**, entrez **PartyTable**.
    4. Dans le champ **Table**, entrez **DirPartyTable**.
    5. Sélectionner **OK** pour finir d’ajouter la nouvelle source de données.

9. Suivez ces étapes pour ajouter une nouvelle source de données pour demander des enregistrements `DirPartyTable`, sur la base de la liste fournie des codes d’identification d’enregistrement :

    1. Dans le volet **Types de sources de données**, sélectionnez **Général \> Conteneur vide**.
    2. dans le volet **Sources de données**, sélectionnez **Ajouter une racine**.
    3. Dans le champ **Nom**, entrez **Données**.
    4. Sélectionner **OK** pour finir d’ajouter la nouvelle source de données.
    5. Dans le volet **Sources de données**, sélectionnez la source de données **Données**.
    6. Dans le volet **Type de sources de données**, sélectionnez **Fonctions \> Champs calculés**.
    7. Dans le volet **Sources de données**, sélectionnez **Ajouter**.
    8. Dans le champ **Nom**, entrez **DirParty**.
    9. Sélectionnez **Modifier la formule**.
    10. Sur la page **Concepteur de formule**, sélectionnez **Paramètres**.
    11. Dans la boîte de dialogue **Paramètres**, procédez comme suit :

        1. Dans l’onglet **Paramètres**, sélectionnez **Nouveau**.
        2. Dans le champ **Nom**, entrez **DirPartyId**.
        3. Dans le champ **Type**, sélectionnez **Int64**.
        4. Activez la case à cocher **Liste**.
        5. Cliquez sur **OK**.

        > [!NOTE]
        > Vous venez de configurer ce champ calculé afin qu’il accepte, lors de l’exécution, l’argument d’un seul paramètre configuré comme une liste d’enregistrements qui a un seul champ `Value` de type *Int64*.

    12. Dans le champ **Formule**, entrez l’expression suivantes :

        `FILTER(PartyTable, VALUEINLARGE(PartyTable.RecId, DirPartyId, DirPartyId.Value))`

        > [!NOTE]
        > Vous venez de configurer le champ calculé `DirParty` pour récupérer uniquement les enregistrements `DirPartyTable` où les codes d’identification d’enregistrement sont inclus dans la liste `DirPartyId` qui est fournie comme argument lorsque le champ `DirParty` est appelé.

        ![Formule pour récupérer les noms de partie à partir de la table d’application sur la page Concepteur de formule.](./media/er-data-model-parameterized-calls-formula1.png)

    13. Sélectionnez **Enregistrer** et fermez la page du **Concepteur de formule**.
    14. Sélectionnez **Enregistrer**, puis sélectionnez **OK** pour terminer l’ajout de la nouvelle source de données.

10. Suivez ces étapes pour lier la nouvelle source de données au nouveau champ de modèle de données, afin que le modèle de données soit utilisé pour exposer les noms des parties :

    1. Dans le volet **Modèle de données**, sélectionnez le champ de modèle de données `Root.Party`.
    2. Dans le volet **Modèle de données**, sélectionnez **Modifier**.
    3. Sur la page **Concepteur de formule**, dans le champ **Formule**, saisissez l’expression `Data.DirParty(PartyRefRecId)`.
    4. Sélectionnez **Enregistrer** et fermez la page du **Concepteur de formule**.

        > [!NOTE]
        > Vous venez de configurer la liaison pour appeler la source de données `Data.DirParty` et fournir la liste des codes d’identification d’enregistrement qui seront spécifiés dans le format lorsque le champ de modèle de données `Root.Party` est appelé.

    5. Dans le volet **Modèle de données**, sélectionnez le champ de modèle de données `Root.Party.Name`.
    6. Dans le volet **Modèle de données**, sélectionnez **Modifier**.
    7. Sur la page **Concepteur de formule**, dans le volet **Source de données**, développez **Données \> DirParty** et sélectionnez **Nom**.
    8. Sélectionnez **Ajouter une source de données**.
    9. Sélectionnez **Enregistrer** et fermez la page du **Concepteur de formule**.

    ![Structure de mappage de modèles ER ajustée sur la page Concepteur de mappage de modèles.](./media/er-data-model-parameterized-calls-mapping2.png)

11. Sélectionnez **Enregistrer**, et fermez la page du **Concepteur de mappage de modèles**.
12. Fermez la page **Mappage de modèles à la source de données**.
13. Dans le raccourci **Versions**, pour la version **2.2**, sélectionnez **Modifier le statut \> Terminé**. Puis sélectionnez **OK**.

### <a name="adjust-the-imported-format"></a>Ajuster le format importé

1. Dans la page **Configurations**, sélectionnez **Exemple de format d’audit**.
2. Dans le raccourci **Versions**, sélectionnez la version **1.2** ayant un statut défini sur **Brouillon**.
3. Sélectionnez **Redéfinir**.
4. Dans le champ **Version cible**, laissez la version **2** du modèle de base **Exemple de modèle d’audit**.
5. Sélectionnez **OK** pour rebaser et aligner votre format aux modifications récentes du modèle de données.
6. Sélectionnez **Concepteur**.
7. Sur la page **Concepteur de formats**, dans l’arborescence de la structure du format du volet gauche, sélectionnez **Agrandir/Réduire**.
8. Suivez ces étapes pour ajouter un nouvel élément de format afin de collecter les codes d’identification d’enregistrement des parties dont les transactions sont présentées sur les rapports générés.

    1. Dans l’arborescence de la structure des formats, sélectionnez l’élément de séquence **Report.Row.Trans**.
    2. Sélectionnez **Ajouter**.
    3. Dans la boîte de dialogue **Ajouter**, sélectionnez **Source de données \> Article**.
    4. Dans la boîte de dialogue **Propriétés du composant**, dans le champ **Nom**, tapez **Identifiant**.
    5. Dans le champ **Type de données**, sélectionnez **Int64**.
    6. Cliquez sur **OK**.

    > [!NOTE]
    > Un élément **Source de données \> Article** peut être utilisé pour effectuer des calculs internes et la transformation de données uniquement dans le cadre du format d’exécution. Par conséquent, en ajoutant cet élément de format, vous ne modifiez pas le contenu d’un document généré.

9. Suivez ces étapes pour ajouter de nouveaux éléments de format afin de saisir les noms des parties sur les rapports générés :

    1. Sélectionnez l’élément de séquence **Report.Row**.
    2. Sélectionnez **Ajouter**.
    3. Dans la boîte de dialogue **Ajouter**, sélectionnez **Texte \> Souche**.
    4. Dans la boîte de dialogue **Propriétés du composant**, dans le champ **Nom**, tapez **Partie**.
    5. Cliquez sur **OK**.
    6. Sélectionnez l’élément de séquence **Report.Row.Party**.
    7. Sélectionnez **Ajouter**.
    8. Dans la boîte de dialogue **Ajouter**, sélectionnez **Texte \> Chaîne**.
    9. Dans la boîte de dialogue **Propriétés du composant**, dans le champ **Nom**, tapez **Nom**.
    10. Cliquez sur **OK**.

10. Suivez ces étapes pour ajouter une nouvelle source de données afin de collecter les codes d’identification d’enregistrement des parties dont les transactions sont présentées sur les rapports générés :

    1. Dans l’onglet **Mappage**, sélectionnez **Ajouter une racine**.
    2. Dans la boîte de dialogue **Ajouter une source de données**, sélectionnez **Fonctions \> Collection de données**.
    3. Dans la boîte de dialogue **Propriétés de la source de données « Collection de données »**, dans le champ **Nom**, saisissez **PartyIds**.
    4. Dans le champ **Type d’article**, sélectionnez **Int64**.
    5. Cliquez sur **OK**.

11. Suivez ces étapes pour ajouter une nouvelle liaison afin de collecter les codes d’identification d’enregistrement des parties dont les transactions sont présentées sur les rapports générés :

    1. Dans l’arborescence de la structure des formats, sélectionnez l’élément d’article de données **Report.Row.Trans.Id**.
    2. Sélectionnez **Modifier la formule**.
    3. Sur la page **Concepteur de formule**, entrez l’expression `PartyIds.Collect(model.Transaction.Party.RecId)`.
    4. Sélectionnez **Enregistrer** et fermez la page du **Concepteur de formule**.

12. Suivez ces étapes pour ajouter de nouvelles liaisons afin de saisir les noms des parties sur les rapports générés :

    1. Dans l’arborescence de la structure des formats, sélectionnez l’élément de séquence **Report.Party**.
    2. Sélectionnez **Modifier la formule**.
    3. Sur la page **Concepteur de formule**, entrez l’expression `model.Party(PartyIds.Result)`.
    4. Sélectionnez **Enregistrer** et fermez la page du **Concepteur de formule**.
    5. Dans l’arborescence de la structure des formats, sélectionnez l’élément de séquence **Report.Party.Name**.
    6. Sur l’onglet **Mappage**, sélectionnez le champ de modèle de données `model.Party.Name`.
    7. Sélectionnez **Lier**.

    ![Structure du format ER ajusté sur la page Concepteur de format.](./media/er-data-model-parameterized-calls-format2.png)

13. Sélectionnez **Enregistrer** et fermez la page du **Concepteur de format**.
14. Fermez la page **Mappage de modèles à la source de données**.
15. Dans le raccourci **Versions**, pour la version **2.2**, sélectionnez **Modifier le statut** \> **Terminé**. Puis sélectionnez **OK**.

### <a name="run-the-adjusted-format"></a>Exécuter le format ajusté

1. Sur la page **Configurations**, sélectionnez **Exemple de format d’audit**, puis, dans le volet Actions, sélectionnez **Exécuter**.
2. Dans la boîte de dialogue **Paramètres du rapport de gestion des états électroniques**, sur l’onglet **Enregistrements à inclure**, sélectionnez **Filtre**.
3. Spécifiez les conditions pour sélectionner les transactions fiscales des documents **PIV-110000004** et **INV-10000001**.
4. Cliquez sur **OK**.
5. Cliquez sur **OK**.
6. Passez en revue le document généré qui contient les transactions fiscales des bons sélectionnés et les noms du client et du fournisseur correspondants.

    ![Aperçu du document généré avec les transactions fiscales et les noms de partie.](./media/er-data-model-parameterized-calls-output2.png)

7. Accédez à **Comptabilité fournisseur** \> **Fournisseurs** \> **Tous les fournisseurs**, et passez en revue les détails du justificatif **PIV-110000004** sélectionné, y compris le nom du fournisseur.

    ![Examiner les détails du justificatif d’achat sur les pages Tous les fournisseurs et Journal des factures.](./media/er-data-model-parameterized-calls-review1.gif)

8. Accédez à **Comptabilité client** \> **Clients** \> **Tous les clients**, et passez en revue les détails du justificatif **INV-10000001** sélectionné, y compris le nom du client.

    ![Examinez les détails du justificatif de vente sur les pages Tous les clients et Taxe validée.](./media/er-data-model-parameterized-calls-review2.gif)

Pour plus de détails sur cette exécution de la solution ER, utilisez l’analyseur de [suivi des performances](trace-execution-er-troubleshoot-perf.md) intégré ER.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Prise en charge des appels paramétrés des sources de données de gestion des états électroniques (ER) de type Champ calculé](er-calculated-field-type.md)
- [Suivre l’exécution des formats d’état électronique pour résoudre les problèmes de performances](trace-execution-er-troubleshoot-perf.md)
- [Utiliser les sources de données COLLECTION DE DONNÉES dans des formats de gestion d’états électroniques](er-data-collection-data-sources.md)
- [Fonction ER ValueInLarge](er-functions-logical-valueinlarge.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
