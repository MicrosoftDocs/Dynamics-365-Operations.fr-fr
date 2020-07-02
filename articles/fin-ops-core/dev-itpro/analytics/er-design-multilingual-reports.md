---
title: Concevoir des états multilingues dans les états électroniques
description: Cette rubrique explique comment utiliser les étiquettes d'états électroniques (ER) pour concevoir et générer des états multilingues.
author: NickSelin
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 65efb8dbec925b5238acaa5d6769f3085e9715b9
ms.sourcegitcommit: cf709f1421a0bf66ecea493088ecb4eb08004187
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/12/2020
ms.locfileid: "3444619"
---
# <a name="design-multilingual-reports-in-electronic-reporting"></a>Concevoir des états multilingues dans les états électroniques

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>Vue d’ensemble

En tant qu'utilisateur professionnel, vous pouvez utiliser la structure de [Gestion des états électroniques (ER)](general-electronic-reporting.md) pour configurer des formats pour les documents sortants conformément aux obligations légales de différents pays ou régions. Lorsque ces exigences requièrent que les documents sortants soient générés dans différentes langues pour différents pays ou régions, vous pouvez configurer un seul [format](general-electronic-reporting.md#FormatComponentOutbound) ER qui contient des ressources dépendantes de la langue. De cette façon, vous pouvez réutiliser le format pour générer des documents sortants pour différents pays ou régions. Vous pouvez également utiliser un format ER unique pour générer un document sortant dans différentes langues pour les clients, fournisseurs, filiales ou autres parties correspondants.

Vous pouvez configurer des modèles de données ER et des mappages de modèles en tant que sources de données des formats ER configurés pour définir le flux de données qui spécifie les données d'application qui sont placées dans les documents générés. En tant que [fournisseur](general-electronic-reporting.md#Provider) de configuration ER, vous pouvez [publier](tasks/er-upload-configuration-into-lifecycle-services.md#upload-configuration-into-lcs) des [modèles de données](general-electronic-reporting.md#data-model-and-model-mapping-components), [mises en correspondance de modèles](general-electronic-reporting.md#data-model-and-model-mapping-components), et [formats](general-electronic-reporting.md#FormatComponentOutbound) configurés sous la forme de composants d'une solution ER pour générer des documents sortants spécifiques. Vous pouvez également autoriser les clients à [charger](general-electronic-reporting-manage-configuration-lifecycle.md) la solution ER publiée afin qu'elle puisse être utilisée et personnalisée. Si vous vous attendez à ce que les clients parlent d'autres langues, vous pouvez configurer les composants ER afin qu'ils contiennent des ressources dépendantes de la langue. De cette façon, le contenu d'un composant ER modifiable peut être présenté dans la langue préférée par l'utilisateur au moment de la conception.

Vous pouvez configurer des ressources dépendantes de la langue comme étiquettes ER. Vous pouvez ensuite utiliser ces étiquettes pour configurer les composants ER aux fins suivantes :

- Au moment de la conception :

    - Présentez le contenu des composants ER configurés dans la langue préférée de l'utilisateur.

- Lors de l'exécution :

    - Générez du contenu dépendant de la langue pour les documents sortants.
    - Fournissez des messages d'avertissement et d'erreur dans la langue préférée de l'utilisateur.
    - Demandez les champs obligatoires dans la langue préférée de l'utilisateur.

Les étiquettes ER peuvent être configurées dans chaque [configuration](general-electronic-reporting.md#Configuration) ER qui contient différents composants. Les étiquettes peuvent être gérées indépendamment de la logique configurée des modèles de données ER, des mappages de modèles ER et des composants de format ER.

Chaque étiquette ER est identifiée par un ID unique dans la portée de la configuration ER contenant cette étiquette. Chaque étiquette peut contenir du texte d'étiquette pour chaque langue prise en charge dans l'instance actuelle de Microsoft Dynamics 365 Finance. Ces langues prises en charge incluent les langues des personnalisations déployées.

## <a name="entry"></a>Saisie

Lorsque vous concevez un modèle de données ER, un mappage de modèle ER ou un format ER, l'option **Traduire** est affichée chaque fois que vous sélectionnez un champ pouvant contenir le contexte traduisible. Lorsque vous sélectionnez cette option, vous pouvez lier le champ sélectionné à une étiquette ER dans le <a name="TextTranslationPane">volet</a> **Traduction de texte**. Vous pouvez sélectionner une étiquette ER existante, ou vous pouvez ajouter une nouvelle étiquette ER si elle n'est pas encore disponible. Lorsque vous sélectionnez ou ajoutez une étiquette ER, vous pouvez ajouter du texte associé pour chaque langue prise en charge dans l'instance Finance actuelle.

L'illustration suivante montre comment cette traduction est effectuée dans un modèle de données ER modifiable. Dans cet exemple, l'attribut **Description** du champ **Bon de commande** pour le **Modèle de facture** modifiable est traduit en allemand autrichien (DE-AT) et en japonais (JA).

![Fournir la traduction d'une étiquette ER dans le concepteur de modèles de données ER](./media/er-multilingual-labels-refer.png)

Seul le texte d'étiquette pour les étiquettes qui résident dans un composant ER modifiable peut être traduit. Par exemple, si vous sélectionnez **Traduire** pour l'attribut d'étiquette d'une source de données de mise en correspondance de modèles ER, puis vous sélectionnez une étiquette ER qui réside dans le modèle de données ER parent, vous verrez le contenu de l'étiquette, mais vous ne pourrez pas le modifier. Dans ces cas, le champ **Texte traduit** n'est pas disponible, comme indiqué dans l'illustration suivante.

![Examen de la traduction fournie d'une étiquette ER dans le concepteur de mise en correspondance des modèles ER](./media/er-multilingual-labels-refer-mapping.png)

> [!NOTE]
> Vous ne pouvez pas utiliser les concepteurs pour supprimer l'étiquette entrée dans un composant ER modifiable.

## <a name="scope"></a>Portée

Les étiquettes ER peuvent être référencées dans plusieurs attributs traduisibles des composants ER.

### <a name="data-model-component"></a>Composant Modèle de données

Lorsque vous configurez un modèle de données ER, vous pouvez lui ajouter des étiquettes ER. Les attributs **Étiquette** et **Description** de l'élément de modèle, chaque champ de modèle et chaque valeur d'énumération du modèle <a id="LinkModelEnum"></a> peut être liée à une étiquette ER qui est ajoutée au modèle de données ER.

![Fournir la traduction de l'attribut Description dans le concepteur de modèle de données ER](./media/er-multilingual-labels-refer.png)

Lorsqu'un modèle de données ER est configuré de cette manière, son contenu sera présenté aux utilisateurs du concepteur de modèles de données ER dans la langue préférée de chaque utilisateur. Par conséquent, la maintenance des modèles est simplifiée. Les illustrations suivantes montrent comment cette fonctionnalité fonctionne pour les utilisateurs qui ont défini DE-AT et JA comme langues préférées.

![Disposition du concepteur de modèle de données ER pour un utilisateur ayant défini DE-AT comme langue préférée](./media/er-multilingual-labels-refer-de.png)

![Disposition du concepteur de modèle de données ER pour un utilisateur ayant défini JA comme langue préférée](./media/er-multilingual-labels-refer-ja.png)

### <a name="model-mapping-component"></a>Composant de mise en correspondance de modèles

Étant donné que le mappage de modèles ER est basé sur un modèle de données ER, les étiquettes des éléments de modèle de données auxquels il est fait référence sont affichées dans la langue préférée de l'utilisateur dans le concepteur de mise en correspondance de modèles. L'illustration suivante montre comment la signification de **Bon de commande** est expliquée dans la mise en correspondance de modèles modifiables à l'aide de l'étiquette de l'attribut **Description** ayant été ajouté au modèle de données configuré. Notez que cette étiquette est présentée dans la langue préférée de l'utilisateur (DE-AT dans cet exemple).

![Disposition du concepteur de mise en correspondance de modèles pour un utilisateur ayant défini DE-AT comme langue préférée](./media/er-multilingual-labels-show-mapping.png)

Quand l'attribut **Étiquette** de la source de données **Paramètre d'entrée utilisateur** est configuré comme liée à une étiquette ER, le champ de paramètre qui correspond à cette source de données est présenté dans la boîte de dialogue utilisateur au moment de l'exécution aux utilisateurs dans leur langue préférée.

### <a name="format-component"></a>Composant des formats

Lorsque vous configurez un format ER, vous pouvez lui ajouter des étiquettes ER. Les attributs **Étiquette** et **Texte d'aide** de chaque source de données configurée peuvent être liés à une étiquette ER ajoutée au format ER. Les attributs **Étiquette** et **Description** de chaque valeur d'énumération de format <a id="LinkFormatEnum"></a> peuvent également être liés à une étiquette ER accessible à partir du format ER modifiable.

> [!NOTE]
> Vous pouvez également lier ces attributs à une étiquette ER du modèle de données ER parent qui réutilise les étiquettes du modèle dans chaque format ER configuré pour ce modèle de données ER.

Lorsqu'un format ER est configuré de cette manière, le contenu du format sera présenté aux utilisateurs du concepteur de modèles de données ER dans la langue préférée de chaque utilisateur. Par conséquent, la maintenance des formats et l'analyse de la logique configurée sont simplifiées.

Étant donné qu'un format ER est basé sur un modèle de données ER, les étiquettes dont il est fait référence dans les éléments de modèle de données sont présentés dans le concepteur de mise en correspondance de modèles dans la langue préférée de l'utilisateur.

Lorsque l'attribut **Étiquette** de la source de données **Paramètre d'entrée utilisateur** est lié à une étiquette ER, le champ qui correspond au paramètre dans la boîte de dialogue utilisateur au moment de l'exécution est présenté à l'utilisateur sous la forme d'une invite. Les illustrations suivantes montrent comment lier l'attribut **Étiquette** de la source de données **Paramètre d'entrée utilisateur** au moment de la conception vers une étiquette ER, afin que les utilisateurs soient invités à entrer le paramètre dans différentes langues préférées par l'utilisateur (affichées pour les langues anglais États-Unis (EN-US) et DE-AT) au moment de l'exécution.

![Fournir la traduction des attributs d'un paramètre d'entrée utilisateur dans le concepteur d'opérations ER](./media/er-multilingual-labels-refer-format.png)

![Traitement des paiements par le fournisseur ER au moment de l'exécution pour la langue préférée des utilisateurs EN-US](./media/er-multilingual-labels-show-runtime-en.png)

![Traitement des paiements par le fournisseur ER au moment de l'exécution pour la langue préférée des utilisateurs DE-AT](./media/er-multilingual-labels-show-runtime-de.png)

### <a name="expressions"></a>Expressions

Pour utiliser une étiquette dans une [expression](er-formula-language.md) ER, vous devez utiliser la syntaxe **@"GER\_LABEL:X"**, où le préfixe **@** indique que l'opérande fait référence à une étiquette, **GER\_LABEL** indique qu'une étiquette ER est impliquée, et **X** est l'ID d'étiquette ER.

![Configuration d'une expression ER contenant une référence à une étiquette ER dans le concepteur de formule ER](./media/er-multilingual-labels-expression1.png)

Pour faire référence à une étiquette système (application), utilisez la syntaxe **@"X"**, où le préfixe **@** indique que l'opérande fait référence à une étiquette, et **X** est l'ID d'étiquette du système.

![Configuration d'une expression ER contenant une référence à une application dans le concepteur de formules ER](./media/er-multilingual-labels-expression2.png)

#### <a name="model-mapping"></a>Mise en correspondance des modèles

Une expression d'une mise en correspondance de modèles ER peut être configurée à l'aide d'une étiquette. Lorsque cette mise en correspondance est appelée par un format ER exécuté pour générer un document sortant, le contexte de l'exécution inclut un code de langue. Une étiquette d'expression configurée sera remplie avec le texte de l'étiquette qui a été configuré pour la langue de ce contexte.

Si une étiquette référencée n'a pas de traduction pour la langue du contexte d'exécution de format qui appelle le mappage de modèle, le texte de l'étiquette dans la langue EN-US est utilisé à la place.

#### <a name="format"></a>Format

Une expression ER d'un format ER peut être configurée à l'aide d'étiquettes. Lorsque ce format est exécuté pour générer un document sortant, le contexte de l'exécution inclut un code de langue. Une étiquette d'expression configurée sera remplie avec le texte de l'étiquette qui a été configuré pour la langue de ce contexte.

![Fournir la traduction d'une étiquette ER de l'expression ER modifiable dans le concepteur de formules ER](./media/er-multilingual-labels-refer-in-expression.png)

![Exemple de liaison de données faisant référence à une étiquette ER dans le concepteur d'opération ER](./media/er-multilingual-labels-refer-in-binding.png)

Vous pouvez configurer le composant **FILE** d'un format ER pour générer l'état dans la langue préférée de l'utilisateur.

![Configurer le composant FILE dans le concepteur d'opérations ER pour générer l'état dans la langue préférée de l'utilisateur](./media/er-multilingual-labels-language-context-user.png)

Si vous configurez un format ER de cette manière, l'état est généré à l'aide du texte correspondant des étiquettes ER. Les illustrations suivantes montrent des exemples d'états pour les langues utilisateur EN-US et DE-AT.

![Aperçu de l'état généré dans la langue préférée de l'utilisateur EN-US](./media/er-multilingual-labels-report-preview-en.png)

![Aperçu de l'état généré dans la langue préférée de l'utilisateur DE-AT](./media/er-multilingual-labels-report-preview-de.png)

Si une étiquette référencée n'a pas de traduction pour la langue du contexte d'exécution de format, le texte de l'étiquette dans la langue EN-US est utilisé à la place.

## <a name="language"></a>Langue

ER prend en charge différentes façons de spécifier une langue pour un état généré. Dans le champ **Préférences linguistiques** sur l'onglet **Format**, vous pouvez sélectionner les valeurs suivantes :

- **Préférence de l'entreprise** - Générez un état dans une langue spécifiée par l'entreprise.

    ![Spécifier dans le concepteur d'opérations ER la langue préférée de l'entreprise comme langue d'un état généré](./media/er-multilingual-labels-language-context-company.png)

- **Préférence utilisateur** - Générez un état dans la langue préférée de l'utilisateur.
- **Défini explicitement** - Générez un état dans une langue spécifiée au moment de la conception.

    ![Spécifier dans le concepteur d'opérations ER la langue définie au moment de la conception comme langue d'un état généré](./media/er-multilingual-labels-language-context-fixed.png)

- **Défini lors de l'exécution** - Générez un état dans une langue spécifiée au moment de l'exécution. Si vous sélectionnez cette valeur, dans le champ **Langue**, configurez une expression ER qui renvoie le code de langue pour la langue, comme la langue du client correspondant.

    ![Spécifier dans le concepteur d'opérations ER la langue définie au moment de l'exécution comme langue d'un état généré](./media/er-multilingual-labels-language-context-runtime.png)

## <a name="translation"></a>Traduction

Vous pouvez ajouter des étiquettes ER requises à un composant ER modifiable. Lorsqu'une étiquette ER est ajoutée, elle peut être traduite de deux manières : manuellement et automatiquement.

### <a name="manual-translation"></a>Traduction manuelle

Lorsque vous ajoutez une étiquette ER dans le [volet](#TextTranslationPane) **Traduction de texte**, vous pouvez le traduire manuellement dans toutes les langues prises en charge dans l'instance Finance actuelle. Vous pouvez sélectionner la langue préférée dans le champ **Langue** dans la section **Langue du système** ou **Langue utilisateur**, saisissez le texte approprié dans le champ correspondant **Texte traduit**, puis sélectionnez **Traduire**. Ce processus doit être répété pour chaque langue requise et pour chaque étiquette que vous ajoutez.

### <a name="automatic-translation"></a>Traduction automatique

La configuration d'un composant ER se fait dans la version préliminaire de la configuration ER dans laquelle réside le composant ER modifiable.

![Page Configurations ER permettant d'accéder à la version de la configuration à l'état Brouillon](./media/er-multilingual-labels-configurations.png)

Comme décrit précédemment dans cette rubrique, vous pouvez ajouter des étiquettes ER requises à un composant ER modifiable. De cette façon, vous pouvez spécifier le texte des étiquettes ER dans la langue EN-US. Vous pouvez ensuite exporter les étiquettes du composant ER à l'aide de la fonction ER intégrée. Sélectionnez la version provisoire d'une configuration ER contenant le composant ER modifiable, puis sélectionnez **Échange \> Exporter des étiquettes**.

![Page Configurations ER permettant d'exporter des étiquettes ER depuis la version de configuration sélectionnée](./media/er-multilingual-labels-export.png)

Vous pouvez exporter toutes les étiquettes ou les étiquettes pour une seule langue que vous spécifiez au début de l'exportation. Les étiquettes sont exportées sous forme de fichier zip contenant des fichiers XML. Chaque fichier XML contient des étiquettes pour une seule langue.

![Exemple de fichier exporté contenant des étiquettes ER pour la langue DE-AT](./media/er-multilingual-labels-in-xml.png)

Ce format est utilisé pour la traduction automatique des étiquettes par des services de traduction externes tels que [Dynamics 365 Translation Service](../lifecycle-services/translation-service-overview.md). Lorsque vous recevez les étiquettes traduites, vous pouvez les réimporter dans la version préliminaire d'une configuration ER qui contient les composants ER qui possèdent ces étiquettes. Sélectionnez la version provisoire d'une configuration ER contenant le composant ER modifiable, puis sélectionnez **Échanger \> Charger des étiquettes**.

![Page Configurations ER permettant d'importer des étiquettes ER vers la version de configuration sélectionnée](./media/er-multilingual-labels-load.png)

Les étiquettes traduites seront importées dans la configuration ER sélectionnée. Les étiquettes traduites qui existent dans cette configuration ER sont remplacées. Si une étiquette traduite est manquante dans la configuration ER, elle est ajoutée.

## <a name="lifecycle"></a>Cycle de vie

Les étiquettes d'un composant ER qui peuvent être modifiées sont conservées, ainsi que tout autre contenu pour le composant, dans la version appropriée d'une configuration ER.

Les étiquettes d'un composant ER de base peuvent être référencées dans une version dérivée du composant ER que vous créez pour introduire vos modifications.

Le contrôle de version ER contrôle l'attribution d'étiquette à n'importe quel attribut d'un composant ER. Les modifications apportées à l'affectation d'étiquette sont enregistrées dans la liste des modifications (delta) d'un composant ER modifiable qui a été créé en tant que version dérivée du composant ER fourni. Ces modifications seront validées lorsqu'une version dérivée est rebasée vers une nouvelle version de base.

## <a name="functions"></a>Fonctions

La fonction ER [LISTOFFIELDS](er-functions-list-listoffields.md) intégré peut accéder aux étiquettes ER qui ont été configurées pour certains éléments des composants ER.

Comme décrit précédemment dans cette rubrique, les attributs **Étiquette** et **Description** de la valeur d'énumération ER de chaque [modèle](#LinkModelEnum) ou [format](#LinkFormatEnum) peuvent être liés à une étiquette ER accessible dans le composant ER approprié. Vous pouvez configurer une expression ER où vous appelez la fonction **LISTOFFIELDS** en utilisant l'énumération ER comme argument. Cette expression renvoie une liste qui contient un enregistrement pour chaque valeur d'une énumération ER définie comme argument de cette fonction. Chaque enregistrement contient la valeur d'une étiquette ER liée à une valeur d'énumération ER :

- La valeur d'une étiquette ER liée aux attributs **Étiquette** est stockée dans le champ **Étiquette** de l'enregistrement renvoyé.
- La valeur d'une étiquette ER liée aux attributs **Description** est stockée dans le champ **Description** de l'enregistrement renvoyé.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d'ensemble des États électroniques](general-electronic-reporting.md)
- [Fonctions de génération d'états électroniques](er-formula-language.md#functions)
