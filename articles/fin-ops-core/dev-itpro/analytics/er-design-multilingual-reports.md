---
title: Concevoir des états multilingues dans les états électroniques
description: Cet article explique comment utiliser les étiquettes d’états électroniques (ER) pour concevoir et générer des états multilingues.
author: kfend
ms.date: 05/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: ''
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
ms.openlocfilehash: 5575ba3154521e3855ce6b97c5b37d3c4868e3e9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285483"
---
# <a name="design-multilingual-reports-in-electronic-reporting"></a>Concevoir des états multilingues dans les états électroniques

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>Vue d’ensemble

En tant qu’utilisateur professionnel, vous pouvez utiliser la structure de [Gestion des états électroniques (ER)](general-electronic-reporting.md) pour configurer des formats pour les documents sortants conformément aux obligations légales de différents pays ou régions. Lorsque ces exigences requièrent que les documents sortants soient générés dans différentes langues pour différents pays ou régions, vous pouvez configurer un seul format ER qui contient des ressources dépendantes de la langue. De cette façon, vous pouvez réutiliser le format pour générer des documents sortants pour différents pays ou régions. Vous pouvez également utiliser un format ER unique pour générer un document sortant dans différentes langues pour les clients, fournisseurs, filiales ou autres parties correspondants.

Vous pouvez configurer des modèles de données ER et des mappages de modèles en tant que sources de données des formats ER configurés pour définir le flux de données qui spécifie les données d’application qui sont placées dans les documents générés. En tant que [fournisseur](general-electronic-reporting.md#Provider) de configuration ER, vous pouvez [publier](tasks/er-upload-configuration-into-lifecycle-services.md#upload-a-configuration-into-lcs) des modèles de données, mises en correspondance de modèles, et formats configurés sous la forme de composants d’une solution ER pour générer des documents sortants spécifiques. Vous pouvez également autoriser les clients à [charger](general-electronic-reporting-manage-configuration-lifecycle.md) la solution ER publiée afin qu’elle puisse être utilisée et personnalisée. Si vous vous attendez à ce que les clients parlent d’autres langues, vous pouvez configurer les composants ER afin qu’ils contiennent des ressources dépendantes de la langue. De cette façon, le contenu d’un composant ER modifiable peut être présenté dans la langue préférée par l’utilisateur au moment de la conception.

Vous pouvez configurer des ressources dépendantes de la langue comme étiquettes ER. Vous pouvez ensuite utiliser ces étiquettes pour configurer les composants ER aux fins suivantes :

- Au moment de la conception :

    - Présentez le contenu des composants ER configurés dans la langue préférée de l’utilisateur.

- Lors de l’exécution :

    - Générez du contenu dépendant de la langue pour les documents sortants.
    - Fournissez des messages d’avertissement et d’erreur dans la langue préférée de l’utilisateur.
    - Demandez les champs obligatoires dans la langue préférée de l’utilisateur.

Les étiquettes ER peuvent être configurées dans chaque [configuration](general-electronic-reporting.md#Configuration) ER qui contient différents composants. Les étiquettes peuvent être gérées indépendamment de la logique configurée des modèles de données ER, des mappages de modèles ER et des composants de format ER.

Chaque étiquette ER est identifiée par un ID unique dans la portée de la configuration ER contenant cette étiquette. Chaque étiquette peut contenir du texte d’étiquette pour chaque langue prise en charge dans l’instance actuelle de Microsoft Dynamics 365 Finance. Ces langues prises en charge incluent les langues des personnalisations déployées.

## <a name="entry"></a>Saisie

Lorsque vous concevez un modèle de données ER, un mappage de modèle ER ou un format ER, l’option **Traduire** est affichée chaque fois que vous sélectionnez un champ pouvant contenir le contexte traduisible. Lorsque vous sélectionnez cette option, vous pouvez lier le champ sélectionné à une étiquette ER dans le <a name="TextTranslationPane">volet</a> **Traduction de texte**. Vous pouvez sélectionner une étiquette ER existante, ou vous pouvez ajouter une nouvelle étiquette ER si elle n’est pas encore disponible. Lorsque vous sélectionnez ou ajoutez une étiquette ER, vous pouvez ajouter du texte associé pour chaque langue prise en charge dans l’instance Finance actuelle.

L’illustration suivante montre comment cette traduction est effectuée dans un modèle de données ER modifiable. Dans cet exemple, l’attribut **Description** du champ **Bon de commande** pour le **Modèle de facture** modifiable est traduit en allemand autrichien (DE-AT) et en japonais (JA).

![Fournir la traduction d’une étiquette ER dans le concepteur de modèles de données ER.](./media/er-multilingual-labels-refer.png)

Seul le texte d’étiquette pour les étiquettes qui résident dans un composant ER modifiable peut être traduit. Par exemple, si vous sélectionnez **Traduire** pour l’attribut d’étiquette d’une source de données de mise en correspondance de modèles ER, puis vous sélectionnez une étiquette ER qui réside dans le modèle de données ER parent, vous verrez le contenu de l’étiquette, mais vous ne pourrez pas le modifier. Dans ces cas, le champ **Texte traduit** n’est pas disponible, comme indiqué dans l’illustration suivante.

![Examen de la traduction fournie d’une étiquette ER dans le concepteur de mise en correspondance des modèles ER.](./media/er-multilingual-labels-refer-mapping.png)

> [!NOTE]
> Vous ne pouvez pas utiliser les concepteurs pour supprimer l’étiquette entrée dans un composant ER modifiable.

## <a name="scope"></a>Portée

Les étiquettes ER peuvent être référencées dans plusieurs attributs traduisibles des composants ER.

### <a name="data-model-component"></a>Composant Modèle de données

Lorsque vous configurez un modèle de données ER, vous pouvez lui ajouter des étiquettes ER. Les attributs **Étiquette** et **Description** de l’élément de modèle, chaque champ de modèle et chaque valeur d’énumération du modèle <a id="LinkModelEnum"></a> peut être liée à une étiquette ER qui est ajoutée au modèle de données ER.

![Fournir la traduction de l’attribut Description dans le concepteur de modèle de données ER.](./media/er-multilingual-labels-refer.png)

Lorsqu’un modèle de données ER est configuré de cette manière, son contenu sera présenté aux utilisateurs du concepteur de modèles de données ER dans la langue préférée de chaque utilisateur. Par conséquent, la maintenance des modèles est simplifiée. Les illustrations suivantes montrent comment cette fonctionnalité fonctionne pour les utilisateurs qui ont défini DE-AT et JA comme langues préférées.

![Disposition du concepteur de modèle de données ER pour un utilisateur ayant défini DE-AT comme langue préférée.](./media/er-multilingual-labels-refer-de.png)

![Disposition du concepteur de modèle de données ER pour un utilisateur ayant défini JA comme langue préférée.](./media/er-multilingual-labels-refer-ja.png)

### <a name="model-mapping-component"></a>Composant de mise en correspondance de modèles

Étant donné que la mise en correspondance des modèles ER est basée sur un modèle de données ER, les étiquettes des éléments de modèle de données auxquels il est fait référence apparaissent dans la langue préférée de l’utilisateur dans le concepteur de mise en correspondance des modèles. L’illustration suivante montre comment la signification de **Bon de commande** est expliquée dans la mise en correspondance de modèles modifiables à l’aide de l’étiquette de l’attribut **Description** ayant été ajouté au modèle de données configuré. Notez que cette étiquette est présentée dans la langue préférée de l’utilisateur (DE-AT dans cet exemple).

![Disposition du concepteur de mise en correspondance de modèles pour un utilisateur ayant défini DE-AT comme langue préférée.](./media/er-multilingual-labels-show-mapping.png)

Quand l’attribut **Étiquette** de la source de données **Paramètre d’entrée utilisateur** est configuré comme liée à une étiquette ER, le champ de paramètre qui correspond à cette source de données est présenté dans la boîte de dialogue utilisateur au moment de l’exécution aux utilisateurs dans leur langue préférée.

### <a name="format-component"></a>Composant des formats

Lorsque vous configurez un format ER, vous pouvez lui ajouter des étiquettes ER. Les attributs **Étiquette** et **Texte d’aide** de chaque source de données configurée peuvent être liés à une étiquette ER ajoutée au format ER. Les attributs **Étiquette** et **Description** de chaque valeur d’énumération de format <a id="LinkFormatEnum"></a> peuvent également être liés à une étiquette ER accessible à partir du format ER modifiable.

> [!NOTE]
> Vous pouvez également lier ces attributs à une étiquette ER du modèle de données ER parent qui réutilise les étiquettes du modèle dans chaque format ER configuré pour ce modèle de données ER.

Lorsqu’un format ER est configuré de cette manière, le contenu du format sera présenté aux utilisateurs du concepteur de modèles de données ER dans la langue préférée de chaque utilisateur. Par conséquent, la maintenance des formats et l’analyse de la logique configurée sont simplifiées.

Étant donné qu’un format ER est basé sur un modèle de données ER, les étiquettes dont il est fait référence dans les éléments de modèle de données sont présentés dans le concepteur de mise en correspondance de modèles dans la langue préférée de l’utilisateur.

Lorsque l’attribut **Étiquette** de la source de données **Paramètre d’entrée utilisateur** est lié à une étiquette ER, le champ qui correspond au paramètre dans la boîte de dialogue utilisateur au moment de l’exécution est présenté à l’utilisateur sous la forme d’une invite. Les illustrations suivantes montrent comment lier l’attribut **Étiquette** de la source de données **Paramètre d’entrée utilisateur** au moment de la conception vers une étiquette ER, afin que les utilisateurs soient invités à entrer le paramètre dans différentes langues préférées par l’utilisateur (affichées pour les langues anglais États-Unis (EN-US) et DE-AT) au moment de l’exécution.

![Fournir la traduction des attributs d’un paramètre d’entrée utilisateur dans le concepteur d’opérations ER.](./media/er-multilingual-labels-refer-format.png)

![Traitement des paiements par le fournisseur ER au moment de l’exécution pour la langue préférée des utilisateurs EN-US.](./media/er-multilingual-labels-show-runtime-en.png)

![Traitement des paiements par le fournisseur ER au moment de l’exécution pour la langue préférée des utilisateurs DE-AT.](./media/er-multilingual-labels-show-runtime-de.png)

### <a name="expressions"></a>Expressions

Pour utiliser une étiquette dans une [expression](er-formula-language.md) ER, vous devez utiliser la syntaxe **@"GER\_LABEL:X"**, où le préfixe **@** indique que l’opérande fait référence à une étiquette, **GER\_LABEL** indique qu’une étiquette ER est impliquée, et **X** est l’ID d’étiquette ER.

![Configuration d’une expression ER contenant une référence à une étiquette ER dans le concepteur de formule ER.](./media/er-multilingual-labels-expression1.png)

Pour faire référence à une étiquette système (application), utilisez la syntaxe **@"X"**, où le préfixe **@** indique que l’opérande fait référence à une étiquette, et **X** est l’ID d’étiquette du système.

![Configuration d’une expression ER contenant une référence à une application dans le concepteur de formules ER.](./media/er-multilingual-labels-expression2.png)

#### <a name="model-mapping"></a>Mappage de modèles

Une expression d’une mise en correspondance de modèles ER peut être configurée à l’aide d’une étiquette. Lorsque cette mise en correspondance est appelée par un format ER exécuté pour générer un document sortant, le contexte de l’exécution inclut un code de langue. Une étiquette d’expression configurée sera remplie avec le texte de l’étiquette qui a été configuré pour la langue de ce contexte.

Si une étiquette référencée n’a pas de traduction pour la langue du contexte d’exécution de format qui appelle le mappage de modèle, le texte de l’étiquette dans la langue EN-US est utilisé à la place.

#### <a name="format"></a>Format

Une expression ER d’un format ER peut être configurée à l’aide d’étiquettes. Lorsque ce format est exécuté pour générer un document sortant, le contexte de l’exécution inclut un code de langue. Une étiquette d’expression configurée sera remplie avec le texte de l’étiquette qui a été configuré pour la langue de ce contexte.

![Fournir la traduction d’une étiquette ER de l’expression ER modifiable dans le concepteur de formules ER.](./media/er-multilingual-labels-refer-in-expression.png)

![Exemple de liaison de données faisant référence à une étiquette ER dans le concepteur d’opération ER.](./media/er-multilingual-labels-refer-in-binding.png)

Vous pouvez configurer le composant **FILE** d’un format ER pour générer l’état dans la langue préférée de l’utilisateur.

![Configurer le composant FILE dans le concepteur d’opérations ER pour générer l’état dans la langue préférée de l’utilisateur.](./media/er-multilingual-labels-language-context-user.png)

Si vous configurez un format ER de cette manière, l’état est généré à l’aide du texte correspondant des étiquettes ER. Les illustrations suivantes montrent des exemples d’états pour les langues utilisateur EN-US et DE-AT.

![Aperçu de l’état généré dans la langue préférée de l’utilisateur EN-US.](./media/er-multilingual-labels-report-preview-en.png)

![Aperçu de l’état généré dans la langue préférée de l’utilisateur DE-AT.](./media/er-multilingual-labels-report-preview-de.png)

Si une étiquette référencée n’a pas de traduction pour la langue du contexte d’exécution de format, le texte de l’étiquette dans la langue EN-US est utilisé à la place.

> [!TIP]
> Vous pouvez utiliser les composants **DOSSIER** et des types distincts de composants **FICHIER** au format ER modifiable pour spécifier comment un fichier sortant est généré. Pour nommer un fichier généré, configurez l’[expression](er-formula-language.md) ER pour le paramètre **Nom de fichier** du composant. Vous pouvez utiliser des étiquettes dans l’expression configurée. Comme le paramètre **Nom de fichier** est indépendant de la langue par défaut, le texte de toutes les étiquettes auxquelles vous faites référence dans cette expression est affiché dans la langue EN-US par défaut lors de l’exécution. Cependant, dans la version 10.0.28 et ultérieure, vous pouvez activer la fonctionnalité **Appliquer le paramètre « Préférence de langue » à l’expression « Nom de fichier »**. L’expression **Nom de fichier** prend alors le paramètre **Préférences linguistiques** en compte lors de son calcul.

## <a name="language"></a>Langue

ER prend en charge différentes façons de spécifier une langue pour un état généré. Dans le champ **Préférences linguistiques** sur l’onglet **Format**, vous pouvez sélectionner les valeurs suivantes :

- **Préférence de l’entreprise** – Générez un état dans une langue spécifiée par l’entreprise.

    ![Spécifier dans le concepteur d’opérations ER la langue préférée de l’entreprise comme langue d’un état généré.](./media/er-multilingual-labels-language-context-company.png)

- **Préférence utilisateur** – Générez un état dans la langue préférée de l’utilisateur.
- **Défini explicitement** – Générez un état dans une langue spécifiée au moment de la conception.

    ![Spécifier dans le concepteur d’opérations ER la langue définie au moment de la conception comme langue d’un état généré.](./media/er-multilingual-labels-language-context-fixed.png)

- **Défini lors de l’exécution** – Générez un état dans une langue spécifiée au moment de l’exécution. Si vous sélectionnez cette valeur, dans le champ **Langue**, configurez une expression ER qui renvoie le code de langue pour la langue, comme la langue du client correspondant.

    ![Spécifier dans le concepteur d’opérations ER la langue définie au moment de l’exécution comme langue d’un état généré.](./media/er-multilingual-labels-language-context-runtime.png)

## <a name="culture-specific-formatting"></a>Mise en forme spécifique à la culture

ER prend en charge différentes façons de spécifier une culture pour un état généré. Par conséquent, la mise en forme spécifique à la culture peut être utilisée pour la date, l’heure et les valeurs numériques. Lorsque vous concevez un format ER, sur l’onglet **Format**, dans le champ **Préférences culturelles**, vous pouvez sélectionner l’une des valeurs suivantes pour chaque composant de format de type **Commun\\Fichier**, **Excel\\Fichier**, **PDF\\Fichier**, ou **PDF\\Fusionner** :

- **Préférence de l’utilisateur** – Formatez les valeurs en fonction de la culture de l’utilisateur. Cette culture est définie dans le champ **Format de la date, de l’heure et des chiffres** sur l’onglet **Préférences** de la page **Options utilisateur**.

    ![Définir la culture favorite de l’utilisateur comme culture de l’état généré dans le concepteur d’opérations ER.](./media/er-multilingual-labels-culture-context-user-preferred.png)

- **Définition explicite** – Mettez en forme les valeurs en fonction de la culture spécifiée au moment de la conception.

    ![Définir la culture définie au moment de la conception comme culture de l’état généré dans le concepteur d’opérations ER.](./media/er-multilingual-labels-culture-context-fixed.png)

- **Définition au moment de l’exécution** – Mettez en forme les valeurs en fonction de la culture spécifiée au moment de l’exécution. Si vous sélectionnez cette valeur, sur l’onglet **Mappage**, dans le champ **Format de la date, de l’heure et des chiffre**, configurez une expression ER qui renvoie le code de culture pour la culture, comme la culture du client correspondant.

    ![Définir la culture définie au moment de l’exécution comme culture de l’état généré dans le concepteur d’opérations ER.](./media/er-multilingual-labels-culture-context-runtime.png)

> [!NOTE]
> Un composant ER pour lequel vous définissez une culture spécifique peut contenir des composants ER enfants qui ont été configurés pour remplir une valeur de texte. Par défaut, la culture du composant parent est utilisée pour mettre en forme les valeurs de ces composants. Vous pouvez utiliser les fonctions ER intégrées suivantes pour configurer des liaisons pour ces composants et appliquer une culture alternative pour la mise en forme des valeurs :
>
> - [DATEFORMAT](er-functions-datetime-dateformat.md#syntax-2)
> - [DATETIMEFORMAT](er-functions-datetime-datetimeformat.md#syntax-2)
> - [NUMBERFORMAT](er-functions-text-numberformat.md#syntax-2)
>
> Dans les versions 10.0.20 et ultérieures, les paramètres régionaux des composants de format de type **Commun\\Fichier** et **Excel\\Fichier** sont utilisés pour formater les valeurs pendant la [Conversion PDF](electronic-reporting-destinations.md#OutputConversionToPDF) d’un document généré.

## <a name="translation"></a>Traduction

Vous pouvez ajouter des étiquettes ER requises à un composant ER modifiable. Lorsqu’une étiquette ER est ajoutée, elle peut être traduite de deux manières : manuellement et automatiquement.

### <a name="manual-translation"></a>Traduction manuelle

Lorsque vous ajoutez une étiquette ER dans le [volet](#TextTranslationPane) **Traduction de texte**, vous pouvez le traduire manuellement dans toutes les langues prises en charge dans l’instance Finance actuelle. Vous pouvez sélectionner la langue préférée dans le champ **Langue** dans la section **Langue du système** ou **Langue utilisateur**, saisissez le texte approprié dans le champ correspondant **Texte traduit**, puis sélectionnez **Traduire**. Ce processus doit être répété pour chaque langue requise et pour chaque étiquette que vous ajoutez.

### <a name="automatic-translation"></a>Traduction automatique

La configuration d’un composant ER se fait dans la version préliminaire de la configuration ER dans laquelle réside le composant ER modifiable.

![Page Configurations ER permettant d’accéder à la version de la configuration à l’état Brouillon.](./media/er-multilingual-labels-configurations.png)

Comme décrit précédemment dans cet article, vous pouvez ajouter des étiquettes ER requises à un composant ER modifiable. De cette façon, vous pouvez spécifier le texte des étiquettes ER dans la langue EN-US. Vous pouvez ensuite exporter les étiquettes du composant ER à l’aide de la fonction ER intégrée. Sélectionnez la version provisoire d’une configuration ER contenant le composant ER modifiable, puis sélectionnez **Échange \> Exporter des étiquettes**.

![Page Configurations ER permettant d’exporter des étiquettes ER depuis la version de configuration sélectionnée.](./media/er-multilingual-labels-export.png)

Vous pouvez exporter toutes les étiquettes ou les étiquettes pour une seule langue que vous spécifiez au début de l’exportation. Les étiquettes sont exportées sous forme de fichier zip contenant des fichiers XML. Chaque fichier XML contient des étiquettes pour une seule langue.

![Exemple de fichier exporté contenant des étiquettes ER pour la langue DE-AT.](./media/er-multilingual-labels-in-xml.png)

Ce format est utilisé pour la traduction automatique des étiquettes par des services de traduction externes tels que [Dynamics 365 Translation Service](../lifecycle-services/translation-service-overview.md). Lorsque vous recevez les étiquettes traduites, vous pouvez les réimporter dans la version préliminaire d’une configuration ER qui contient les composants ER qui possèdent ces étiquettes. Sélectionnez la version provisoire d’une configuration ER contenant le composant ER modifiable, puis sélectionnez **Échanger \> Charger des étiquettes**.

![Page Configurations ER permettant d’importer des étiquettes ER vers la version de configuration sélectionnée.](./media/er-multilingual-labels-load.png)

Les étiquettes traduites seront importées dans la configuration ER sélectionnée. Les étiquettes traduites qui existent dans cette configuration ER sont remplacées. Si une étiquette traduite est manquante dans la configuration ER, elle est ajoutée.

## <a name="lifecycle"></a>Cycle de vie

Les étiquettes d’un composant ER qui peuvent être modifiées sont conservées, ainsi que tout autre contenu pour le composant, dans la version appropriée d’une configuration ER.

Les étiquettes d’un composant ER de base peuvent être référencées dans une version dérivée du composant ER que vous créez pour introduire vos modifications.

> [!TIP]
> Lorsque vous concevez une solution ER, vous pouvez dériver votre propre composant [modèle de données](er-overview-components.md#data-model-component) ER à partir de celui qui est fourni. Dans ce modèle de données dérivé, vous pouvez introduire vos propres étiquettes ER et les utiliser dans tous les formats ER qui utiliseront le modèle de données comme source de données. Vous pouvez ensuite dériver votre propre composant de [format](er-overview-components.md#format-component) ER de celui qui est fourni en sélectionnant votre modèle de données ER dérivé au lieu de celui fourni. Dans la version 10.0.28 et ultérieures, vous pouvez activer la fonctionnalité **Accès amélioré aux étiquettes du modèle de données de rapport électronique croissant** pour accéder aux étiquettes d’un modèle de données ER croissant dans les composants de format ER dérivés, même si modèle de données ER sélectionné pour le composant ER dérivé diffère de celui utilisé dans le composant ER de base.
>
> Lorsque le même nom d’étiquette est utilisé dans votre composant dérivé et ses composants ascendants, votre traduction de cette étiquette est utilisée comme la plus pertinente.

Le contrôle de version ER contrôle l’attribution d’étiquette à n’importe quel attribut d’un composant ER. Les modifications apportées à l’affectation d’étiquette sont enregistrées dans la liste des modifications (delta) d’un composant ER modifiable qui a été créé en tant que version dérivée du composant ER fourni. Ces modifications seront validées lorsqu’une version dérivée est rebasée vers une nouvelle version de base.

## <a name="functions"></a>Fonctions

La fonction ER [LISTOFFIELDS](er-functions-list-listoffields.md) intégré peut accéder aux étiquettes ER qui ont été configurées pour certains éléments des composants ER.

Comme décrit précédemment dans cet article, les attributs **Étiquette** et **Description** de la valeur d’énumération ER de chaque [modèle](#LinkModelEnum) ou [format](#LinkFormatEnum) peuvent être liés à une étiquette ER accessible dans le composant ER approprié. Vous pouvez configurer une expression ER où vous appelez la fonction **LISTOFFIELDS** en utilisant l’énumération ER comme argument. Cette expression renvoie une liste qui contient un enregistrement pour chaque valeur d’une énumération ER définie comme argument de cette fonction. Chaque enregistrement contient la valeur d’une étiquette ER liée à une valeur d’énumération ER :

- La valeur d’une étiquette ER liée aux attributs **Étiquette** est stockée dans le champ **Étiquette** de l’enregistrement renvoyé.
- La valeur d’une étiquette ER liée aux attributs **Description** est stockée dans le champ **Description** de l’enregistrement renvoyé.

## <a name="performance"></a><a name=performance></a>Performance

Lorsque vous configurez un composant dans un format ER pour générer un état dans votre [langue](#language) préférée, ou pour importer un document entrant dont le contenu sera analysé dans votre langue préférée, nous vous recommandons d’activer la fonction **Mettre en cache la langue préférée de l’utilisateur actuel pour les exécutions ER** dans l’espace de travail [Gestion des fonctionnalités](../../fin-ops/get-started/feature-management/feature-management-overview.md). Cette fonctionnalité permet d’améliorer les performances, en particulier pour les composants au format ER qui contiennent plusieurs références à des étiquettes dans les formules et les liaisons ER et de nombreuses règles de [validation](general-electronic-reporting-formula-designer.md#TestFormula) pour générer les messages utilisateur dans votre langue préférée.

Lorsque vous changez le statut d’une version de configuration de la gestion des états électroniques de **Brouillon** sur **Terminé**, si la version de configuration contient des étiquettes de gestion des états électroniques, ces étiquettes sont stockées dans la base de données de l’application. Le schéma de stockage dépend de l’état de la fonctionnalité **Accélérer le stockage des étiquettes de gestion des états électroniques** :

- Si la fonctionnalité n’est pas activée, toutes les étiquettes sont stockées dans le champ **LABELXML** de la table **ERSOLUTIONVERSIONTABLE** sous la forme d’un extrait XML unique.
- Si la fonctionnalité est activée, un enregistrement distinct est créé pour chaque langue dans la table **ERSOLUTIONVERSIONLABELSTABLE**. Le champ **CONTENU** de cette table stocke les étiquettes par langue sous la forme d’un extrait de code XML compressé.

Nous vous recommandons d’activer la fonctionnalité **Accélérer le stockage des étiquettes de gestion des états électroniques** dans l’espace de travail **Gestion des fonctionnalités**. Cette fonctionnalité permet d’améliorer l’utilisation de la bande passante du réseau et les performances globales du système car, dans la plupart des cas, les étiquettes de gestion des états électroniques d’une seule langue sont utilisées lorsque vous travaillez avec une seule configuration de gestion des états électroniques.

Pour appliquer le schéma de stockage sélectionné afin de conserver les étiquettes de toutes les configurations ER dans l’instance Finance actuelle, procédez comme suit :

1. Accédez à **Administration de l’organisation** > **Périodique** > **Appliquer le schéma de stockage des étiquettes sélectionnées pour toutes les configurations de gestion des états électroniques**.
2. Cliquez sur **OK**.


## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble des États électroniques](general-electronic-reporting.md)
- [Fonctions de génération d’états électroniques](er-formula-language.md#Functions)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
