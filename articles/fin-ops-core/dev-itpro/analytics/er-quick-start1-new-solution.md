---
title: Concevoir une nouvelle solution de gestion des états électroniques pour imprimer un rapport personnalisé
description: Cette rubrique explique comment concevoir une solution de gestion des états électroniques (ER) pour imprimer un rapport personnalisé.
author: NickSelin
ms.date: 08/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom:
- "220314"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 35db2eb3e0da91207f08d16b8fb1bfa6a6bb8607
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6345958"
---
# <a name="design-a-new-er-solution-to-print-a-custom-report"></a>Concevoir une nouvelle solution de gestion des états électroniques pour imprimer un rapport personnalisé

[!include[banner](../includes/banner.md)]

Les étapes suivantes expliquent comment un utilisateur avec le rôle d’administrateur système, de développeur d’états électroniques ou de consultant technique de gestion des états électroniques peut configurer les paramètres de la structure de gestion des états électroniques, concevoir les configurations de gestion des états électroniques requises d’une nouvelle solution de gestion des états électroniques pour accéder aux données d’un domaine d’activité particulier, et générer un rapport personnalisé dans un format Microsoft Office. Ces étapes peuvent être effectuées dans la société **USMF**.

- [Configurer la structure de gestion des états électroniques](#ConfigureFramework)

    - [Configurer les paramètres de gestion des états électroniques](#ConfigureParameters)
    - [Activer un fournisseur de configuration de gestion des états électroniques](#ActivateProvider)

        - [Consulter la liste des fournisseurs de configuration de gestion des états électroniques](#ReviewProvidersList)
        - [Ajouter un nouveau fournisseur de configuration de gestion des états électroniques](#AddProvider)
        - [Activer un fournisseur de configuration de gestion des états électroniques](#ActivateAddedProvider)

- [Concevoir un modèle de données spécifique à un domaine](#DesignModel)

    - [Importer une nouvelle configuration de modèle de données](#ImportDataModel)
    - [Créer une configuration de modèle de données](#DesignDataModel)

        - [Nommer un modèle de données](#NameDataModel)
        - [Ajouter des champs de modèle de données](#FieldsEntry)
        - [Terminer la conception du modèle de données](#CompleteDataModel)

- [Concevoir une mise en correspondance de modèles pour le modèle de données configuré](#DesignMapping)

    - [Importer une nouvelle configuration de mise en correspondance de modèles](#ImportModelMapping)
    - [Créez une configuration de mise en correspondance de modèles](#CreateModelMapping)

        - [Concevoir un nouveau composant de mise en correspondance de modèles](#DesignMappingComponent)
        - [Ajouter des sources de données pour accéder aux tables d’application](#AddMmDataSource1)
        - [Ajouter des sources de données pour accéder aux énumérations d’application](#AddMmDataSource2)
        - [Ajouter des étiquettes ER pour générer un rapport dans une langue spécifiée](#AddMmLabels)
        - [Ajouter une source de données pour transformer les résultats de la comparaison des valeurs d’énumération en une valeur de texte](#AddMmDataSource3)
        - [Lier des sources de données aux champs d’un modèle de données](#AddMmBindings1)
        - [Terminer la conception de la mise en correspondance de modèles](#CompleteModelMapping)

- [Concevoir un modèle de rapport personnalisé](#DesignReportTemplate)
- [Concevoir un format](#DesignFormat)

    - [Importer une configuration de format conçu](#FormatImport)
    - [Créer une configuration de format](#FormatCreate)

        - [Importer un modèle d’état](#ImportReportTemplate)
        - [Configurer un format](#ConfigureFormat)
        - [Définir la liaison de données pour un titre de rapport](#DefineFormatBindings)
        - [Examiner la source de données du modèle](#ReviewModelDataSource)
        - [Associer les éléments de format aux champs d’une source de données](#BindFormatElements)

    - [Exécuter un format conçu à partir d’ER](#RunFormatFromER)

- [Ajuster un format conçu](#TuneFormat)

    - [Modifier un format pour changer le nom d’un document généré](#ModifyToChangeName)
    - [Modifier un format pour changer l’ordre des questions](#ModifyToOrder)
    - [Exécuter un format modifié à partir d’ER](#RunFormatFromER2)
    - [Terminer la conception du format](#CompleteFormat)

- [Développer des artefacts d’application pour appeler le rapport conçu](#DevelopCustomCode)

    - [Modifier le code source](#ModifySourceCode)

        - [Ajouter une classe de contrat de données](#DataContractClass)
        - [Ajouter une classe AI Builder](#UIBuilderClass)
        - [Ajouter une classe de fournisseur de données](#DataProviderClass)
        - [Ajouter un fichier d’étiquettes](#LabelsFile)
        - [Ajouter une classe de service de rapport](#ServiceClass)
        - [Ajouter une classe de contrôleur de rapport](#ControllerClass)
        - [Ajouter un élément de menu](#MenuItem)
        - [Ajouter un élément de menu à un menu](#Menu)
        - [Générer un projet Visual Studio](#BuildVSProject)

    - [Exécuter un format depuis l’application](#RunFormatFromApp)

- [Ajuster une solution de gestion des états électroniques conçue](#TuneSolution)

    - [Modifier une mise en correspondance de modèle](#ModifyModelMapping)

        - [Ajouter des sources de données pour accéder à un objet de contrat de données](#AddDataSource1)
        - [Ajouter une source de données pour accéder aux enregistrements de mise en correspondance des formats ER](#AddDataSource2)
        - [Ajouter une source de données pour accéder à un enregistrement de mise en correspondance de formats ER d’un format ER en cours d’exécution](#AddDataSource3)
        - [Entrez le nom du format ER en cours d’exécution dans le modèle de données](#AddBinding)
        - [Terminer la conception de la mise en correspondance de modèles](#CompleteModelMapping2)

    - [Modifier un format](#ModifyFormat)

        - [Ajouter un nouvel élément de format](#AddFormatElement)
        - [Lier l’élément de format ajouté](#BindAddedFormatElement)
        - [Terminer la conception du format](#CompleteFormat2)

    - [Exécuter un format depuis l’application](#RunFormatFromApp2)
    - [Exécuter un format à partir d’ER](#RunFormatFromER3)
    - [Configurer une destination de format pour l’aperçu à l’écran](#ConfigureDestination)
    - [Exécuter un format à partir de l’application pour le prévisualiser sous forme de document PDF](#RunFormatFromApp3)

- [Ressources supplémentaires](#References)

Dans cet exemple, vous allez créer une solution de gestion des états électroniques pour le module [Questionnaire](../../../human-resources/hr-learning-questionnaires.md). Cette nouvelle solution de gestion des états électroniques vous permet de concevoir un rapport en utilisant une feuille de calcul Microsoft Excel comme modèle. Vous pouvez ensuite générer le rapport **Questionnaire** au format Excel ou PDF, en plus de générer le rapport SQL Server Reporting Services (SSRS) existant. Vous pouvez également modifier le nouveau rapport ultérieurement, sur demande. Aucun codage n’est requis.

1. Pour exécuter le rapport existant, accédez à **Questionnaire** \> **Conception** \> **État sur les questionnaires**.

    ![Sélection de l’élément de menu État sur les questionnaires dans le module Questionnaire pour exécuter le rapport SSRS existant.](./media/er-quick-start1-application-menu-origin.png)

2. Dans la boîte de dialogue **État sur les questionnaires**, spécifiez les critères de sélection. Appliquez un filtre afin que le rapport n’inclue que le questionnaire **SBCCrsExam**.

    ![Spécification des critères de sélection dans la boîte de dialogue État sur les questionnaires.](./media/er-quick-start1-ssrs-report-dialog.png)

L’illustration suivante montre la version générée du rapport SSRS pour le questionnaire **SBCCrsExam**.

![Rapport SSRS généré.](./media/er-quick-start1-ssrs-report.png)

## <a name="configure-the-er-framework"></a><a name="ConfigureFramework"></a>Configurer la structure de gestion des états électroniques

En tant qu’utilisateur doté du rôle de développeur d’états électroniques, vous devez configurer l’ensemble minimal des paramètres de gestion des états électroniques avant de pouvoir commencer à utiliser la structure de gestion des états électroniques pour créer votre solution de gestion des états électroniques.

### <a name="configure-er-parameters"></a><a name="ConfigureParameters"></a>Configurer les paramètres de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans l’espace de travail **Génération des états électroniques**, sélectionnez **Paramètres de gestion des états électroniques**.
3. Sur la page **Paramètres de gestion des états électroniques**, sous l’onglet **Général**, définissez l’option **Activer le mode de configuration** sur **Oui**.
4. Dans l’onglet **Pièces jointes**, définissez les paramètres suivants :

    - Définissez le champ **Configurations** sur **Fichier** pour la société **USMF**.
    - Définissez les champs **Archive de tâche**, **Temporaire**, **Référence** et **Autres** sur **Fichier**.

Pour plus d’informations sur les paramètres de gestion des états électroniques, voir [Configurer la structure de gestion des états électroniques](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a name="ActivateProvider"></a>Activer un fournisseur de configuration de gestion des états électroniques

Chaque configuration de gestion des états électroniques est marquée comme appartenant à un fournisseur de configuration de gestion des états électroniques. Par conséquent, vous devez activer un fournisseur de configuration de gestion des états électroniques dans l’espace de travail **Gestion des états électroniques** avant de commencer à ajouter ou modifier des configurations de gestion des états électroniques.

> [!NOTE]
> Seul le propriétaire d’une configuration de gestion des états électroniques peut la modifier. Par conséquent, avant qu’une configuration de gestion des états électroniques puisse être modifiée, le fournisseur de configuration de gestion des états électroniques approprié doit être activé dans l’espace de travail **Gestion des états électroniques**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a name="ReviewProvidersList"></a>Consulter la liste des fournisseurs de configuration de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans l’espace de travail **Génération d’états électroniques**, dans la section **Liens connexes**, sélectionnez **Fournisseurs de configuration**.
3. Sur la page **Fournisseurs de configuration**, chaque enregistrement de fournisseur de configuration a un nom et une URL uniques. Passez en revue le contenu de cette page. S’il existe déjà un enregistrement pour **Litware, Inc.** (`https://www.litware.com`), ignorez la procédure suivante, [Ajouter un nouveau fournisseur de configuration de gestion des états électroniques](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a name="AddProvider"></a>Ajouter un nouveau fournisseur de configuration de gestion des états électroniques

1. Sur la page **Fournisseurs de configuration**, sélectionnez **Nouveau**.
2. Dans le champ **Nom**, entrez **Litware, Inc.**
3. Dans le champ **Adresse Internet**, entrez `https://www.litware.com`.
4. Sélectionnez **Enregistrer**.

#### <a name="activate-an-er-configuration-provider"></a><a name="ActivateAddedProvider"></a>Activer un fournisseur de configuration de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans l’espace de travail **États électroniques**, sélectionnez fournisseur de configuration **Litware, Inc.**.
3. Sélectionnez **Activer**.

Pour plus d’informations sur les fournisseurs de configuration de gestion des états électroniques, voir [Créer des fournisseurs de configuration et les marquer comme actifs](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="design-a-domain-specific-data-model"></a><a name="DesignModel"></a>Concevoir un modèle de données spécifique à un domaine

Vous devez créer une configuration de la gestion des états électroniques contenant un composant de [modèle de données](general-electronic-reporting.md#data-model-and-model-mapping-components) pour le domaine d’affaires **Questionnaire**. Ce modèle de données sera ultérieurement utilisé comme source de données lorsque vous concevez un format ER pour générer le rapport **Questionnaire**.

En suivant les étapes de la section [Importer une nouvelle configuration de modèle de données](#ImportDataModel), vous pouvez importer le modèle de données requis à partir du fichier XML fourni. Vous pouvez également suivre les étapes de la section [Créer un configuration de modèle de données](#DesignDataModel) pour concevoir ce modèle de données à partir de zéro.

### <a name="import-a-new-data-model-configuration"></a><a name="ImportDataModel"></a>Importer une nouvelle configuration de modèle de données

1. Téléchargez le fichier [Questionnaires model.version.1.xml](https://download.microsoft.com/download/b/6/3/b633bd34-d200-4422-96d9-8f62eb5218f8/Questionnaires_model.version.1.xml) et enregistrez-le sur votre ordinateur local.
2. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
3. Dans l’espace de travail **Génération des états électronique**, sélectionnez **Configurations des états**.
4. Sur le volet Action, sélectionnez **Exchange** \> **Charger depuis le fichier XML**.
5. Sélectionnez **Parcourir**, puis recherchez et sélectionnez le fichier **Questionnaires model.version.1.xml**.
6. Sélectionnez **OK** pour importer la configuration.

Pour continuer, ignorez la procédure suivante, [Créer une configuration de modèle de données](#DesignDataModel).

### <a name="create-a-new-data-model-configuration"></a><a name="DesignDataModel"></a>Créer une configuration de modèle de données

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans l’espace de travail **Génération des états électronique**, sélectionnez **Configurations des états**.
3. Sélectionnez **Créer une configuration**.
4. Dans la boîte de dialogue déroulante, dans le champ **Nom**, tapez **Modèle de questionnaire**.
5. Sélectionnez **Créer une configuration** pour une configuration.

#### <a name="name-the-data-model"></a><a name="NameDataModel"></a>Nommer un modèle de données

1. Dans la page **Configurations**, dans l’arborescence de configuration, sélectionnez **Modèle de questionnaire**.
2. Sélectionnez **Concepteur**.
3. Sur la page **Concepteur de modèles de données**, sur le raccourci **Général**, dans le champ **Nom**, entrez <a name="DataModeName"></a>**Questionnaires**.

#### <a name="add-new-data-model-fields"></a><a name="FieldsEntry"></a>Ajouter de nouveaux champs de modèle de données

1. Sur la page **Concepteur de modèles de données**, sélectionnez **Nouveau**.
2. Dans la boîte de dialogue déroulante pour ajouter un nœud de modèle de données, procédez comme suit :

    1. Sélectionnez **Racine du modèle** comme type du nouveau nœud.
    2. Dans le champ **Nom**, entrez <a name="RootDefinitionName"></a>**Racine**.
    3. Pour ajouter le nouveau rôle, sélectionnez **Ajouter**.

    Ce descripteur racine sera utilisé pour fournir des données pour le rapport **Questionnaire**. Un seul modèle de données peut avoir plusieurs descripteurs. Chaque descripteur peut être spécifié pour un format ER unique, afin d’identifier les données requises pour générer le rapport.

3. Sélectionnez à nouveau **Nouveau** dans la boîte de dialogue déroulante pour ajouter un nœud de modèle de données, procédez comme suit :

    1. Sélectionnez **Enfant d’un nœud actif** comme type du nouveau nœud.
    2. Dans le champ **Nom**, entrez **CompanyName**.
    3. Dans le champ **Type d’article**, sélectionnez **Chaîne**.
    4. Pour ajouter le nouveau champ, sélectionnez **Ajouter**.

    Ce champ est obligatoire pour transmettre le nom de la société actuelle à un rapport ER qui utilise ce modèle de données en tant que source de données.

4. Sélectionnez à nouveau **Nouveau** dans la boîte de dialogue déroulante pour ajouter un nœud de modèle de données, procédez comme suit :

    1. Sélectionnez **Enfant d’un nœud actif** comme type du nouveau nœud.
    2. Dans le champ **Nom**, entrez **Questionnaire**.
    3. Dans le champ **Type d’article**, sélectionnez **Liste d’enregistrements**.
    4. Pour ajouter le nouveau champ, sélectionnez **Ajouter**.

    Ce champ permettra de transmettre la liste des questionnaires à un rapport ER qui utilise ce modèle de données en tant que source de données.

5. Sélectionnez le nœud **Questionnaire**.
6. Continuez à ajouter les champs obligatoires du modèle de données modifiable de la même manière jusqu’à ce que vous ayez terminé la structure de modèle de données suivante.

    | Chemin du champ                                                    | Type de données   | Désignation du champ/valeur renvoyée |
    |---------------------------------------------------------------|-------------|----------------------------------|
    | Racine                                                          |             | Le point de référence pour demander des données du questionnaire. |
    | Racine\\CompanyName                                             | Chaîne      | Nom de la société actuelle. |
    | Racine\\ExecutionContext                                        | Enregistrer      | Détails de l’exécution du format. |
    | Racine\\ExecutionContext\\FormatName                            | Chaîne      | Nom du format ER qui est exécuté. |
    | Racine\\Questionnaire                                           | Liste d’enregistrements | La liste des questionnaires |
    | Racine\\Questionnaire\\Actif                                   | Chaîne      | Statut du questionnaire actuel. |
    | Racine\\Questionnaire\\Code                                     | Chaîne      | Code du questionnaire actuel. |
    | Racine\\Questionnaire\\Description                              | Chaîne      | Description du questionnaire actuel. |
    | Racine\\Questionnaire\\QuestionnaireType                        | Chaîne      | Type du questionnaire actuel. |
    | Racine\\Questionnaire\\QuestionOrder                            | Chaîne      | Ordre numérique du questionnaire actuel. |
    | Racine\\Questionnaire\\ResultsGroup                             | Enregistrer      | Paramètres de résultat du questionnaire actuel. |
    | Racine\\Questionnaire\\ResultsGroup\\Code                       | Chaîne      | Code d’identification du groupe de résultats actuel. |
    | Racine\\Questionnaire\\ResultsGroup\\Description                | Chaîne      | Description du groupe de résultats actuel. |
    | Racine\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints          | Réel        | Le nombre maximum de points pouvant être gagnés. |
    | Racine\\Questionnaire\\Question                                 | Liste d’enregistrements | Liste des questions pour le questionnaire actuel. |
    | Racine\\Questionnaire\\Question\\CollectionSequenceNumber       | Entier     | Numéro de séquence de la collection de réponses actuelle. |
    | Racine\\Questionnaire\\Question\\Id                             | Chaîne      | Code d’identification de la question actuelle. |
    | Racine\\Questionnaire\\Question\\MustBeCompleted                | Chaîne      | Indicateur qui indique s’il faut répondre à la question actuelle. |
    | Racine\\Questionnaire\\Question\\PrimaryQuestion                | Chaîne      | Indicateur qui indique si la question actuelle est la principale. |
    | Racine\\Questionnaire\\Question\\SequenceNumber                 | Entier     | Numéro de séquence de la question actuelle. |
    | Racine\\Questionnaire\\Question\\Text                           | Chaîne      | Texte de la question actuelle. |
    | Racine\\Questionnaire\\Question\\Answer                         | Liste d’enregistrements | Liste des réponses pour la question actuelle. |
    | Racine\\Questionnaire\\Question\\Answer\\CorrectAnswer          | Chaîne      | Indicateur qui indique si la réponse actuelle est correcte. |
    | Racine\\Questionnaire\\Question\\Answer\\Points                 | Réel        | Points gagnés lorsque la réponse actuelle est sélectionnée. |
    | Racine\\Questionnaire\\Question\\Answer\\SequenceNumber         | Entier     | Numéro de séquence de la réponse actuelle. |
    | Racine\\Questionnaire\\Question\\Answer\\Text                   | Chaîne      | Texte de la réponse actuelle. |

    L’illustration suivante montre le modèle de données modifiable terminé sur la page **Concepteur de modèles de données**.

    ![Modèle de données configuré dans le concepteur de modèle de données ER.](./media/er-quick-start1-model2.png)

7. Enregistrez vos modifications.
8. Fermez la page **Concepteur de modèle de données**.

#### <a name="complete-the-design-of-the-data-model"></a><a name="CompleteDataModel"></a>Terminer la conception du modèle de données

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Dans la page **Configurations**, dans l’arborescence de configuration, sélectionnez **Modèle de questionnaire**.
3. Dans le raccourci **Versions**, sélectionnez la version de la configuration ayant un statut **Brouillon**.
4. Sélectionnez **Modifier le statut** \> **Terminé**.

Le statut de la version 1 de cette configuration est modifié de **Brouillon** à **Terminé**. La version 1 ne peut plus être modifiée. Cette version contient le modèle de données configuré et peut être utilisée comme base pour d’autres configurations ER. La version 2 de cette configuration est créée et a un statut de **Brouillon**. Vous pouvez modifier cette version pour ajuster le modèle de données **Questionnaire**.

![Versions de la configuration modifiable sur la page Configurations.](./media/er-quick-start1-model-configuration.png)

Pour plus d’informations sur la gestion des versions pour les configurations ER, voir [Présentation des rapports électroniques (ER)](general-electronic-reporting.md#component-versioning).

> [!NOTE]
> Le modèle de données configuré est votre représentation abstraite du domaine d’affaires **Questionnaire** et ne contient aucune relation avec des artefacts spécifiques à Microsoft Dynamics 365 Finance.

## <a name="design-a-model-mapping-for-the-configured-data-model"></a><a name="DesignMapping"></a>Concevoir une mise en correspondance de modèles pour le modèle de données configuré

En tant qu’utilisateur avec le rôle de développeur d’états électroniques, vous devez créer une configuration de la gestion des états électroniques contenant un composant [mise en correspondance des modèles](general-electronic-reporting.md#data-model-and-model-mapping-components) pour le modèle de données **Questionnaire**. Étant donné que ce composant implémente le modèle de données configuré pour Finance, il est spécifique à Finance. Vous devez configurer le composant de mise en correspondance des modèles pour spécifier les objets d’application qui doivent être utilisés pour remplir le modèle de données configuré avec les données d’application au moment de l’exécution. Pour effectuer cette tâche, vous devez connaître les détails de mise en œuvre de la structure de données du domaine d’affaires **Questionnaire** dans Finance.

En suivant les étapes de la section [Importer une nouvelle configuration de mise en correspondance des modèles](#ImportModelMapping) qui suit, vous pouvez importer la configuration de la mise en correspondance des modèles requis à partir du fichier XML fourni. Vous pouvez également suivre les étapes de la section [Créer un configuration de la mise en correspondance des modèles](#CreateModelMapping) pour concevoir cette mise en correspondance des modèles à partir de zéro.

### <a name="import-a-new-model-mapping-configuration"></a><a name="ImportModelMapping"></a>Importer une nouvelle configuration de mise en correspondance de modèles

1. Téléchargez le fichier [Questionnaires mapping.version.1.1.xml](https://download.microsoft.com/download/7/b/2/7b258e4e-4bd5-46a4-8114-27419ae4acd8/Questionnaires_mapping.version.1.1.xml) et enregistrez-le sur votre ordinateur local.
2. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
3. Dans l’espace de travail **Génération des états électronique**, sélectionnez **Configurations des états**.
4. Sur le volet Action, sélectionnez **Exchange** \> **Charger depuis le fichier XML**.
5. Sélectionnez **Parcourir**, puis recherchez et sélectionnez le fichier **Questionnaires mapping.version.1.1.xml**.
6. Sélectionnez **OK** pour importer la configuration.

Pour continuer, ignorez la procédure suivante, [Créer une configuration de mise en correspondance de modèles](#CreateModelMapping).

### <a name="create-a-new-model-mapping-configuration"></a><a name="CreateModelMapping"></a>Créer une configuration de mise en correspondance de modèles

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Dans la page **Configurations**, dans l’arborescence de configuration, sélectionnez **Modèle de questionnaire**.
3. Sélectionnez **Créer une configuration**.
4. Dans la boîte de dialogue déroulante, procédez comme suit :

    1. Dans le champ **Nouveau**, sélectionnez **Mise en correspondance de modèles basée sur le modèle de données Questionnaires**.
    2. Dans le champ **Nom**, tapez **Mise en correspondance Questionnaire**.
    3. Dans le champ **Définition du modèle de données**, sélectionnez la définition **Racine**.
    4. Sélectionnez **Créer une configuration** pour une configuration.

#### <a name="design-a-new-model-mapping-component"></a><a name="DesignMappingComponent"></a>Concevoir un nouveau composant de mise en correspondance de modèles

1. Dans la page **Configurations**, dans l’arborescence de configuration, sélectionnez **Mise en correspondance Questionnaire**.
2. Sélectionnez **Concepteur** pour ouvrir la liste des mises en correspondance.
3. Sélectionner la mise en correspondance **Mise en correspondance Questionnaire** ajoutée automatiquement pour la définition **Racine**
4. Sélectionnez **Concepteur** pour commencer à configurer la mise en correspondance sélectionnée.

Une nouvelle mise en correspondance est automatiquement ajoutée pour la définition **Racine**. Cette mise en correspondance a la direction **Vers le modèle**. Par conséquent, cette mise en correspondance peut être utilisée pour remplir un modèle de données avec les données requises.

#### <a name="add-data-sources-to-access-application-tables"></a><a name="AddMmDataSource1"></a>Ajouter des sources de données pour accéder aux tables d’application

Vous devez configurer les sources de données pour accéder aux tables d’application qui contiennent les détails du questionnaire.

1. Sur la page **Concepteur de mise en correspondance de modèles**, dans le volet **Types de sources de données**, sélectionnez **Dynamics 365 for Operations\\Enregistrements de la table**.
2. Ajoutez une nouvelle source de données qui sera utilisée pour accéder à la table KMCollection, où chaque enregistrement représente un seul questionnaire :

    1. dans le volet **Sources de données**, sélectionnez **Ajouter une racine**.
    2. Dans la boîte de dialogue, dans le champ **Nom**, entrez **Questionnaire**.
    3. Dans le champ **Table**, entrez **KMCollection**.
    4. Définissez l’option **Demander une requête** sur **Oui**. Vous pourrez alors spécifier des options de [filtrage](../../fin-ops/get-started/advanced-filtering-query-options.md) pour cette table dans la boîte de dialogue de requête système lors de l’exécution.
    5. Sélectionner **OK** pour ajouter la nouvelle source de données.

3. Dans le volet **Types de sources de données**, sélectionnez **Dynamics 365 for Operations\\Enregistrements de la table**.
4. Ajoutez une nouvelle source de données qui sera utilisée pour accéder à la table KMQuestion, où chaque enregistrement représente une seule question dans un questionnaire :

    1. dans le volet **Sources de données**, sélectionnez **Ajouter une racine**.
    2. Dans la boîte de dialogue déroulante, dans le champ **Nom**, entrez **Question**.
    3. Dans le champ **Table**, entrez **KMQuestion**.
    4. Sélectionner **OK** pour ajouter la nouvelle source de données.

5. Dans le volet **Types de sources de données**, sélectionnez **Dynamics 365 for Operations\\Enregistrements de la table**.
6. Ajoutez une nouvelle source de données qui sera utilisée pour accéder à la table KMAnswer, où chaque enregistrement représente une seule réponse dans un questionnaire :

    1. dans le volet **Sources de données**, sélectionnez **Ajouter une racine**.
    2. Dans le champ **Nom**, entrez **Réponse**.
    3. Dans le champ **Table**, entrez **KMAnswer**.
    4. Sélectionner **OK** pour ajouter la nouvelle source de données.

7. Dans le volet **Types de sources de données**, sélectionnez **Fonctions\\Champs calculés**.
8. Ajoutez un nouveau champ calculé qui sera utilisé pour accéder à un enregistrement de la table KMQuestionResultGroup à partir de chaque enregistrement de la table KMCollection parent :

    1. Dans le volet **Sources de données**, sélectionnez **Questionnaire**.
    2. Sélectionnez **Ajouter**.
    3. Dans la boîte de dialogue déroulante, dans le champ **Nom**, entrez **\$ResultGroup**.
    4. Sélectionnez **Modifier la formule**.
    5. Dans l’[Éditeur de formule ER](general-electronic-reporting-formula-designer.md), dans le champ **Formule**, entrez **FIRSTORNULL(\@’.\<Relations’.KMQuestionResultGroup)** pour utiliser le [chemin d’accès](er-formula-language.md#Paths) de la relation un-à-plusieurs entre les tables KMCollection et KMQuestionResultGroup.
    6. Sélectionnez **Enregistrer**, puis fermez l’éditeur de formule.
    7. Sélectionnez **OK** pour ajouter le nouveau champ calculé.

9. Dans le volet **Types de sources de données**, sélectionnez **Fonctions\\Champs calculés**.
10. Ajoutez un nouveau champ calculé qui sera utilisé pour accéder aux enregistrement de questions de la table KMQuestion à partir de chaque enregistrement de la table KMCollectionQuestion parent :

    1. Dans le volet **Sources de données**, sélectionnez **Questionnaire**.
    2. Étendez le nœud **\<Relations** contenant les relations un-à-plusieurs de la table KMCollection.
    3. Sélectionnez la table **KMCollectionQuestion**, puis sélectionnez **Ajouter**.
    4. Dans la boîte de dialogue déroulante, dans le champ **Nom**, entrez **\$Question**.
    5. Sélectionnez **Modifier la formule**.
    6. Dans l’éditeur de formule, dans le champ **Formule**, entrez **FIRSTORNULL (FILTRE(Question, Question.kmQuestionId = \@.kmQuestionId))** pour renvoyer les enregistrements de questions appropriés à partir de la table KMQuestion.
    7. Sélectionnez **Enregistrer**, puis fermez l’éditeur de formule.
    8. Sélectionnez **OK** pour ajouter le nouveau champ calculé.

11. Dans le volet **Types de sources de données**, sélectionnez **Fonctions\\Champs calculés**.
12. Ajoutez un nouveau champ calculé qui sera utilisé pour accéder aux enregistrement de réponses de la table KMQuestion à partir de chaque enregistrement de la table KMQuestion parent :

    1. Dans le volet **Source d’information**, sélectionnez **Questionnaire.\<Relations.KMCollectionQuestion.\$Question**, puis sélectionnez **Ajouter**.
    2. Dans la boîte de dialogue déroulante, dans le champ **Nom**, entrez **\$Answer**.
    3. Sélectionnez **Modifier la formule**.
    4. Dans l’éditeur de formule, dans le champ **Formule**, entrez **FILTER (Answer, Answer.kmAnswerCollectionId = \@.kmAnswerCollectionId)** pour renvoyer les enregistrements de réponses appropriés à partir de la table kmAnswer.
    5. Sélectionnez **Enregistrer**, puis fermez l’éditeur de formule.
    6. Sélectionnez **OK** pour ajouter le nouveau champ calculé.

13. Dans le volet **Types de sources de données**, sélectionnez **Dynamics 365 for Operations\\Table**.
14. Ajoutez une nouvelle source de données qui sera utilisée pour accéder aux méthodes de la table CompanyInfo. Notez que la méthode **find()** de cette table renvoie un enregistrement qui représente une société de l’instance Finance actuelle dans le contexte de laquelle cette mise en correspondance est appelée.

    1. dans le volet **Sources de données**, sélectionnez **Ajouter une racine**.
    2. Dans la boîte de dialogue déroulante, dans le champ **Nom**, entrez **CompanyInfo**.
    3. Dans le champ **Table**, entrez **CompanyInfo**.
    4. Sélectionner **OK** pour ajouter la nouvelle source de données.

#### <a name="add-data-sources-to-access-application-enumerations"></a><a name="AddMmDataSource2"></a>Ajouter des sources de données pour accéder aux énumérations d’application

Vous devez configurer les sources de données pour accéder aux énumérations d’application et comparer leurs valeurs avec les valeurs des champs du type **Énumération** dans les tables d’application. Vous devez utiliser le résultat de la comparaison pour remplir les champs appropriés du modèle de données.

1. Sur la page **Concepteur de mise en correspondance de modèles**, dans le volet **Types de sources de données**, sélectionnez **Dynamics 365 for Operations\\Énumération**.
2. Ajoutez une nouvelle source de données qui sera utilisée pour accéder aux valeurs de l’énumération **EnumAppNoYes** :

    1. dans le volet **Sources de données**, sélectionnez **Ajouter une racine**.
    2. Dans la boîte de dialogue déroulante, dans le champ **Nom**, entrez **EnumAppNoYes**.
    3. Dans le champ **Énumération**, entrez **NoYes**.
    4. Sélectionner **OK** pour ajouter la nouvelle source de données.

3. Dans le volet **Types de sources de données**, sélectionnez **Dynamics 365 for Operations\\Enumeration**.
4. Ajoutez une nouvelle source de données qui sera utilisée pour accéder aux valeurs de l’énumération **KMCollectionQuestionMode** :

    1. dans le volet **Sources de données**, sélectionnez **Ajouter une racine**.
    2. Dans la boîte de dialogue, dans le champ **Nom**, entrez **EnumAppQuestionOrder**.
    3. Dans le champ **Énumération**, entrez **KMCollectionQuestionMode**.
    4. Sélectionner **OK** pour ajouter la nouvelle source de données.

#### <a name="add-er-labels-to-generate-a-report-in-a-specified-language"></a><a name="AddMmLabels"></a>Ajouter des étiquettes ER pour générer un rapport dans une langue spécifiée

Vous pouvez ajouter des étiquettes ER pour configurer certaines de vos sources de données pour renvoyer des valeurs qui dépendent de la langue définie dans le contexte de la mise en correspondance des modèles.

1. Sur la page **Concepteur de mise en correspondance de modèles**, dans le volet **Sources de données**, sélectionnez **Réponse**, puis **Sélectionner**.
2. Activez le champ **Libellé**.
3. Sélectionnez **Traduire**.
4. Dans la boîte de dialogue **Traduction de texte**, procédez comme suit :

    1. Dans le champ **ID de libellé**, entrez **PositiveAnswer**.
    2. Dans le champ **Texte de la langue par défaut**, entrez **Oui**.
    3. Sélectionnez **Traduire**.
    4. Dans le champ **ID de libellé**, entrez **NegativeAnswer**.
    5. Dans le champ **Texte de la langue par défaut**, entrez **Non**.
    6. Sélectionnez **Traduire**.

5. Fermez la boite de dialogue **Traduction de texte**.
6. Sélectionnez **Annuler**.

![Ajout d’étiquettes ER pour la mise en correspondance de modèles modifiable.](./media/er-quick-start1-adding-labels.png)

Vous avez entré des étiquettes ER uniquement pour la langue par défaut. Pour plus d’informations sur la traduction des étiquettes ER dans d’autres langues, voir [Concevoir des rapports multilingues](er-design-multilingual-reports.md).

#### <a name="add-a-data-source-to-transform-the-results-of-comparing-enumeration-values-to-a-text-value"></a><a name="AddMmDataSource3"></a>Ajouter une source de données pour transformer les résultats de la comparaison des valeurs d’énumération en une valeur de texte

Étant donné que vous devez transformer les résultats de la comparaison entre les valeurs d’énumération et les valeurs de texte plusieurs fois pour des sources de différence, il est judicieux de configurer cette logique en tant que source de données unique. Cependant, pour rendre cette source de données réutilisable, vous devez ensuite la configurer comme source de données paramétrée. Pour plus d’informations, voir [Prendre en charge les appels paramétrés des sources de données des états électroniques du type de champ Calculé](er-calculated-field-type.md).

1. Sur la page **Concepteur de mise en correspondance de modèles**, dans le volet **Types de sources de données**, sélectionnez **Général\\Conteneur vide**.
2. Ajouter une nouvelle source de données de conteneur :

    1. dans le volet **Sources de données**, sélectionnez **Ajouter une racine**.
    2. Dans la boîte de dialogue, dans le champ **Nom**, entrez **Assistance**.
    3. Sélectionner **OK** pour ajouter la nouvelle source de données de conteneur.

3. Dans le volet **Types de sources de données**, sélectionnez **Fonctions\\Champs calculés**.
4. Ajouter une nouvelle source de données :

    1. Dans le volet **Sources de données**, sélectionnez **Assistance**.
    2. Sélectionnez **Ajouter**.
    3. Dans la boîte de dialogue, dans le champ **Nom**, entrez **NoYesEnumToString**.
    4. Sélectionnez **Modifier la formule**.
    5. Dans l’éditeur de formule, sélectionnez **Paramètres**.
    6. Suivez ces étapes pour spécifier les paramètres de l’expression configurée :

        1. Sélectionnez **Nouveau**.
        2. Dans la boîte de dialogue déroulante, dans le champ **Nom**, entrez **Argument**.
        3. Dans le champ **Type**, sélectionnez le type de données **Booléen**.
        4. Cliquez sur **OK**.

    7. Dans le champ **Formule**, entrez **IF (Argument = true, \@"GER\_LABEL:PositiveAnswer", \@"GER\_LABEL:NegativeAnswer")** pour renvoyer le texte de l’étiquette ER appropriée, en fonction de la langue du contexte d’exécution et de la valeur du paramètre spécifié.
    8. Sélectionnez **Enregistrer**, puis fermez l’éditeur de formule.
    9. Sélectionner **OK** pour ajouter la nouvelle source de données.

![Mise en correspondance des modèles configurée dans le concepteur de mise en correspondance des modèles de gestion des états électroniques.](./media/er-quick-start1-added-data-sources.png)

#### <a name="bind-data-sources-to-data-model-fields"></a><a name="AddMmBindings1"></a>Lier des sources de données aux champs d’un modèle de données

Vous devez lier les sources de données configurées aux champs du modèle de données pour spécifier la manière dont le modèle de données sera rempli avec les données d’application au moment de l’exécution.

1. Sur la page **Concepteur de mise en correspondance de modèles**, dans le volet **Modèle de données**, sélectionnez **CompanyName**.
2. Dans le volet **Sources d’informations**, développez **CompanyInfo**, puis suivez ces étapes :

    1. Étendez le nœud **CompanyInfo.find()** qui représente la méthode **find()** de la table CompanyInfo.
    2. Sélectionnez **CompanyInfo.find().Name**.
    3. Sélectionnez **Lier** pour renseigner le nom de la société dans le contexte de laquelle la mise en correspondance des modèles configurée est appelée lors de l’exécution.

3. Dans le volet **Modèle de données**, sélectionnez **Questionnaire**.
4. Dans le volet **Source de données**, sélectionnez **Questionnaire**, puis **Lier** pour renseigner les enregistrements du questionnaire.
5. Dans le volet **Modèle de données**, développez **Questionnaire**, puis suivez ces étapes :

    1. Dans le volet **Modèle de données**, sélectionnez **Actif**.
    2. Dans le volet **Modèle de données**, sélectionnez **Modifier**.
    3. Dans le champ **Formule**, entrez **Helper.NoYesEnumToString (\@.Active = EnumAppNoYes.Yes)** pour remplir le résultat dépendant du texte et de la langue de la comparaison entre les valeurs d’énumération.

6. Continuez à lier les sources de données aux champs de modèle de données de la même manière jusqu’à ce que vous obteniez le résultat suivant.

    | Chemin du champ                                              | Type de données   | Action | Expression de liaison |
    |---------------------------------------------------------|-------------|--------|--------------------|
    | CompanyName                                             | Chaîne      | Lier   | CompanyInfo.’find()’.Name |
    | Questionnaire                                           | Liste d’enregistrements | Lier   | Questionnaire |
    | Questionnaire\\Actif                                   | Chaîne      | Modifier   | Helper.NoYesEnumToString(\@.active = EnumAppNoYes.Yes) |
    | Questionnaire\\Code                                     | Chaîne      | Lier   | \@.kmCollectionId |
    | Questionnaire\\Description                              | Chaîne      | Lier   | \@.Description |
    | Questionnaire\\QuestionnaireType                        | Chaîne      | Lier   | \@.’&gt;Relations’.kmCollectionTypeId.Description |
    | Questionnaire\\QuestionOrder                            | Chaîne      | Modifier   | CASE (\@.questionMode,<br>EnumAppQuestionOrder.Conditional, "Conditional",<br>EnumAppQuestionOrder.Random, "Random (percentage in questionnaire)",<br>EnumAppQuestionOrder.RandomGroup, "Random (percentage in result groups)",<br>EnumAppQuestionOrder.Sequence, "Sequential",<br>"") |
    | Questionnaire\\ResultsGroup                             | Enregistrer      |        | |
    | Questionnaire\\ResultsGroup\\Code                       | Chaîne      | Lier   | \@.’\$ResultGroup’.kmQuestionResultGroupId |
    | Questionnaire\\ResultsGroup\\Description                | Chaîne      | Lier   | \@.’\$ResultGroup’.description |
    | Questionnaire\\ResultsGroup\\MaxNumberOfPoints          | Réel        | Lier   | \@.’\$ResultGroup’.maxPoint |
    | Questionnaire\\Question                                 | Liste d’enregistrements | Lier   | \@.’&lt;Relations’.KMCollectionQuestion |
    | Questionnaire\\Question\\CollectionSequenceNumber       | Entier     | Lier   | \@.answerCollectionSequenceNumber |
    | Questionnaire\\Question\\Id                             | Chaîne      | Lier   | \@.kmQuestionId |
    | Questionnaire\\Question\\MustBeCompleted                | Chaîne      | Modifier   | Helper.NoYesEnumToString(\@.mandatory = EnumAppNoYes.Yes) |
    | Questionnaire\\Question\\PrimaryQuestion                | Chaîne      | Lier   | \@.parentQuestionId |
    | Questionnaire\\Question\\SequenceNumber                 | Entier     | Lier   | \@.SequenceNumber |
    | Questionnaire\\Question\\Text                           | Chaîne      | Lier   | \@.’\$Question’.text |
    | Questionnaire\\Question\\Answer                         | Liste d’enregistrements | Lier   | \@.’\$Question’.’\$Answer’ |
    | Questionnaire\\Question\\Answer\\CorrectAnswer          | Chaîne      | Modifier   | Helper.NoYesEnumToString(\@.correctAnswer = EnumAppNoYes.Yes) |
    | Questionnaire\\Question\\Answer\\Points                 | Réel        | Lier   | \@.point |
    | Questionnaire\\Question\\Answer\\SequenceNumber         | Entier     | Lier   | \@.sequenceNumber |
    | Questionnaire\\Question\\Answer\\Text                   | Chaîne      | Lier   | \@.text |

    L’illustration suivante montre l’état final de la mise en correspondance des modèles configurée sur la page **Concepteur de mise en correspondance des modèles**.

    ![Mise en correspondance des modèles entièrement configurée dans le concepteur de mise en correspondance des modèles de gestion des états électroniques.](./media/er-quick-start1-mapping2.png)

7. Enregistrez vos modifications.
8. Fermez la page **Concepteur de mise en correspondance des modèles**.

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping"></a>Terminer la conception de la mise en correspondance de modèles

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Dans la page **Configurations**, dans l’arborescence de configuration, sélectionnez **Mise en correspondance Questionnaire**.
3. Dans le raccourci **Versions**, sélectionnez la version de la configuration ayant un statut **Brouillon**.
4. Sélectionnez **Modifier le statut** \> **Terminé**.

Le statut de la version 1.1 de cette configuration est modifié de **Brouillon** à **Terminé**. La version 1.1 ne peut plus être modifiée. Cette version contient la mise en correspondance de données configurée et peut être utilisée comme base pour d’autres configurations ER. La version 1.2 de cette configuration est créée et a un statut de **Brouillon**. Vous pouvez modifier cette version pour ajuster la configuration **Mise en correspondance de questionnaires**.

![Versions de la configuration ER modifiable sur la page Configurations.](./media/er-quick-start1-mapping-configuration.png)

> [!NOTE]
> La mise en correspondance des modèles configurée est votre implémentation spécifique à Finance du modèle de données abstrait qui représente le domaine d’affaires **Questionnaire**.

## <a name="design-a-template-for-a-custom-report"></a><a name="DesignReportTemplate"></a>Concevoir un modèle de rapport personnalisé

La structure de gestion des états électroniques utilise des modèles prédéfinis pour générer des états dans des formats Microsoft Office (des classeurs Excel ou des documents Word). Tandis que la génération d’état est en cours de génération, un modèle est rempli avec les données requises en fonction du dataflow configuré. Par conséquent, vous devez d’abord concevoir un modèle pour votre rapport personnalisé. Ce modèle doit être conçu comme un classeur Excel, dont la structure représente la disposition d’un rapport personnalisé. Vous devez nommer chaque élément Excel que vous prévoyez de remplir avec les données requises.

1. Téléchargez le fichier [Questionnaires report template.xlsx](https://download.microsoft.com/download/3/8/2/382c3cf0-87bb-473f-b7bb-3015b4facb74/Questionnaires_report_template.xlsx) et enregistrez-le sur votre ordinateur local.
2. Ouvrez le fichier dans Excel et examinez la structure du classeur.

Comme le montre l’illustration suivante, le modèle téléchargé a été conçu pour imprimer des questionnaires spécifiques qui présentent les questions d’un questionnaire avec les réponses appropriées.

![Modèle Excel pour imprimer les questionnaires spécifiés.](./media/er-quick-start1-template-layout.png)

Des noms Excel ont été ajoutés à ce modèle pour remplir les détails du questionnaire. Vous pouvez utiliser le Gestionnaire de noms pour examiner les noms Excel.

![Utilisation du gestionnaire de noms pour examiner les noms Excel dans le modèle Excel fourni.](./media/er-quick-start1-template-names.png)

Les étiquettes de rapport ont été ajoutées sous forme de texte fixe en anglais. Vous pouvez remplacer les étiquettes de rapport par de nouveaux noms Excel qui remplissent les étiquettes avec du texte dépendant de la langue en utilisant des [étiquettes](#AddMmLabels) au format ER, comme vous l’avez fait pour les expressions dépendantes de la langue dans la mise en correspondance des modèles configurée. Dans ce cas, les étiquettes ER doivent être ajoutées au format ER modifiable.

Comme le montre l’illustration suivante, l’en-tête de rapport personnalisé a été spécifié pour permettre à Excel d’effectuer la pagination.

![En-tête de rapport personnalisé dans le modèle Excel fourni.](./media/er-quick-start1-template-header.png)

## <a name="design-a-format"></a><a name="DesignFormat"></a>Concevoir un format

En tant qu’utilisateur avec un rôle de Consultant fonctionnel de gestion des états électroniques, vous devez créer une configuration ER contenant un composant de [format](general-electronic-reporting.md#FormatComponentOutbound). Vous devez configurer le composant de format pour spécifier comment un modèle de rapport sera rempli avec les données requises au moment de l’exécution.

En suivant les étapes de la section [Importer un configuration de format conçue](#FormatImport), vous pouvez importer le format requis à partir du fichier XML fourni. Vous pouvez également suivre les étapes de la section [Créer une configuration de format](#FormatCreate) pour concevoir ce format à partir de zéro.

### <a name="import-a-designed-format-configuration"></a><a name="FormatImport"></a>Importer une configuration de format conçu

1. Téléchargez le fichier [Questionnaires format.version.1.1.xml](https://download.microsoft.com/download/1/b/a/1ba39ec2-257a-44d8-972f-25bf7d18fb41/Questionnaires_format.version.1.1.xml) et enregistrez-le sur votre ordinateur local.
2. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
3. Dans l’espace de travail **Génération des états électronique**, sélectionnez **Configurations des états**.
4. Sur le volet Action, sélectionnez **Exchange** \> **Charger depuis le fichier XML**.
5. Sélectionnez **Parcourir**, puis recherchez et sélectionnez le fichier **Questionnaires format.version.1.1.xml**.
6. Sélectionnez **OK** pour importer la configuration.

Pour continuer, ignorez la procédure suivante, [Créer une configuration de format](#FormatCreate).

### <a name="create-a-new-format-configuration"></a><a name="FormatCreate"></a>Créer une configuration de format
 
1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Dans la page **Configurations**, dans l’arborescence de configuration, sélectionnez **Modèle de questionnaire**.
3. Sélectionnez **Créer une configuration**.
4. Dans la boîte de dialogue déroulante, procédez comme suit :

    1. Dans le champ **Nouveau**, sélectionnez **Format basé sur le modèle de données Questionnaires**.
    2. Dans le champ **Nom**, tapez **État Questionnaire**.
    3. Dans le champ **Version du modèle de données**, sélectionnez **1**.

        > [!NOTE]
        > - Si vous sélectionnez une version spécifique du modèle de données de base, la structure de la version correspondante du modèle de données vous sera présentée comme la structure de la source de données **Modèle** au format créé.
        > - Vous pouvez laisser ce champ vide. Dans ce cas, la structure de la version **Brouillon** du modèle de données vous sera présentée comme la structure de la source de données **Modèle** au format créé. Vous pouvez ensuite ajuster votre modèle et voir immédiatement ces ajustements dans votre format. Cette approche peut améliorer l’efficacité de la conception de la solution ER lorsque vous configurez simultanément votre modèle de données, la mise en correspondance des modèles et le format.
        > - Si vous sélectionnez une version spécifique du modèle de données de base, vous pouvez passer à la version **Brouillon** ultérieurement, lorsque vous commencez à modifier un format.

    4. Dans le champ **Définition du modèle de données**, sélectionnez la définition **Racine**.

5. Sélectionnez **Créer une configuration** pour une configuration.

#### <a name="import-a-report-template"></a><a name="ImportReportTemplate"></a>Importer un modèle d’état

1. Dans la page **Configurations**, dans l’arborescence de configuration, sélectionnez **État questionnaire**.
2. Sélectionner **Concepteur** pour commencer à configurer un format personnalisé.
3. Sur la page **Concepteur de formats**, sur le volet Actions, sélectionnez **Importer** \> **Importer à partir d’Excel**.
4. Dans la boîte de dialogue, procédez comme suit :

    1. Sélectionnez **Ajouter un modèle**.
    2. Recherchez et sélectionnez le fichier enregistré localement **Questionnaires report template.xlsx**, puis **Ouvrir**.
    3. Sélectionnez **OK** pour importer le modèle.

    ![Importation d’un modèle d’état.](./media/er-quick-start1-template-import.png)

L’élément de format **Excel\\File** est automatiquement ajouté au format modifiable en tant qu’élément racine. De plus, l’élément de format **Excel\\Plage** ou l’élément de format **Excel\\Cellule** est automatiquement ajouté pour chaque nom Excel reconnu du modèle importé. Le format **Excel\\En-tête** qui a l’élément **Chaîne** imbriqué est automatiquement ajouté pour refléter les paramètres d’en-tête du modèle importé.

![Structure de format qui inclut des éléments ajoutés automatiquement dans le concepteur d’opérations ER.](./media/er-quick-start1-template-import2.png)

#### <a name="configure-a-format"></a><a name="ConfigureFormat"></a>Configurer un format

1. Sur la page **Concepteur de format**, dans l’arborescence des formats, sélectionnez l’élément racine **Excel**.
2. Sur l’onglet **Format** sur le côté droit de la page, dans le champ **Nom**, entrez <a name="AddFormatRootElement"></a>**Rapport**.
3. Dans le champ **Préférence de langue**, sélectionnez **Préférence de l’utilisateur** pour exécuter le rapport dans la langue préférée de l’utilisateur.
4. Dans le champ **Préférence de culture**, sélectionnez **Préférence de l’utilisateur** pour exécuter le rapport dans la culture préférée de l’utilisateur.

    Pour plus d’informations sur la manière de spécifier les contextes de langue et de culture pour un processus ER, voir [Concevoir des rapports multilingues](er-design-multilingual-reports.md).

    ![Configuration des paramètres de langue et de culture pour le rapport conçu dans le concepteur d’opérations ER.](./media/er-quick-start1-template-format-structure1.png)

5. Dans l’arborescence des formats, développez le nœud racine, puis sélectionnez **ResultsGroup**.
6. Sur l’onglet **Format**, dans le champ **Direction de réplication**, sélectionnez **Pas de réplication**, car vous ne vous attendez pas à avoir plusieurs groupes de résultats pour un même questionnaire.

    ![Définition de la direction de réplication pour les éléments de format Plage dans le concepteur d’opérations ER.](./media/er-quick-start1-template-format-structure2.png)

7. Sélectionnez **Enregistrer**.

#### <a name="define-the-data-binding-for-a-report-title"></a><a name="DefineFormatBindings"></a>Définir la liaison de données pour un titre de rapport

Vous devez spécifier une liaison de données pour un élément de format utilisé pour remplir le titre d’un rapport généré.

1. Sur la page **Concepteur de format**, dans l’onglet **Mise en correspondance** de droite, sélectionnez l’élément **Report\\ReportTitle**.
2. Sélectionnez **Modifier la formule**.
3. Dans l’éditeur de formule, sélectionnez **Traduire**.
4. Dans la boîte de dialogue **Traduction de texte**, procédez comme suit :

    1. Dans le champ **ID de libellé**, entrez **ReportTitle**.
    2. Dans le champ **Texte de la langue par défaut**, entrez **État questionnaire**.
    3. Sélectionnez **Traduire**, puis sélectionnez **Enregistrer**.
    4. Sélectionnez **Traduire** pour fermer la boite de dialogue **Traduction de texte**.

5. Fermez l’éditeur de formule.

    ![Configuration de la liaison pour remplir le titre d’un rapport généré.](./media/er-quick-start1-add-report-title-label.png)

Vous pouvez utiliser cette technique pour rendre toutes les autres étiquettes du modèle actuel dépendantes de la langue. Pour plus d’informations sur la façon dont les étiquettes ajoutées d’une seule configuration ER peuvent être traduites dans toutes les langues prises en charge, voir [Concevoir des rapports multilingues](er-design-multilingual-reports.md).

#### <a name="review-model-data-source"></a><a name="ReviewModelDataSource"></a>Examiner la source de données du modèle

1. Sur la page **Concepteur de format**, sur l’onglet **Mise en correspondance**, sélectionnez la source de données <a name="ModelDSName"></a>**modèle** qui représente le modèle de données de base de ce format ER.
2. Sélectionnez **Modifier**.
3. Passez en revue les informations dans la boite de dialogue **Propriétés de la source de données**. Cette source de données représente la version 1 du composant de modèle de données **Questionnaires** qui réside dans la configuration ER **Modèle de questionnaires**.

![Propriétés de la source de données du modèle dans le concepteur d’opérations de gestion des états électroniques.](./media/er-quick-start1-model-data-source.png)

#### <a name="bind-format-elements-to-data-source-fields"></a><a name="BindFormatElements"></a>Associer les éléments de format aux champs d’une source de données

Pour spécifier la façon dont un modèle est rempli lors de l’exécution, vous devez lier chaque élément de format associé à un nom Excel approprié à un champ unique de la source de données de ce format.

1. Sur la page **Concepteur de format**, dans l’arborescence des formats, sélectionnez l’élément de format **Report\\CompanyName**.
2. Sur l’onglet **Mise en correspondance**, sélectionnez le champ de source de données **model.CompanyName** de type **Chaîne**.
3. Sélectionnez **Lier** pour saisir un nom d’entreprise dans un modèle.
4. Dans l’arborescence des formats, sélectionnez l’élément **Report\\Questionnaire**.
5. Sur l’onglet **Mise en correspondance**, sélectionnez le champ de source de données **model.Questionnaire** de type **liste d’enregistrements**.
6. Sélectionnez **Lier**.
7. Sélectionnez **Afficher les détails** pour voir plus de détails sur les éléments de format.

    L’élément de format de plage **Questionnaire** est configuré comme répliqué verticalement. Lorsqu’il est lié à une source de données du type **Liste des enregistrements**, la plage **Questionnaire** appropriée du modèle Excel est répétée pour chaque enregistrement de la source de données liée.
 
    ![Liaison de l’élément de format de plage de questionnaire aux sources de données de liste d’enregistrements appropriées dans le concepteur d’opérations ER.](./media/er-quick-start1-bindings1.png)

    Du fait que la plage du **Questionnaire** du modèle Excel est définie entre les lignes 5 à 14, ces lignes sont répétées pour chaque questionnaire signalé.

    ![Lignes dans le modèle Excel qui seront répétées dans un rapport généré pour chaque enregistrement des sources de données de la liste d’enregistrements.](./media/er-quick-start1-template-questionnaire-range.png)

8. Configurez des liaisons similaires pour les éléments de format restants, comme décrit dans le tableau suivant.

    > [!NOTE]
    > Dans ce tableau, les informations de la colonne « Chemin d’accès de la source de données » supposent que la fonctionnalité ER du [chemin relatif](relative-path-data-bindings-er-models-format.md) est activée.

    | Chemin d’accès de l’élément de format                                      | Chemin d’accès de la source de données |
    |----------------------------------------------------------|------------------|
    | Excel\\ReportTitle                                       | **\@"GER\_LABEL:ReportTitle"** |
    | Excel\\CompanyName                                       | **model.CompanyName** |
    | Excel\\Questionnaire                                     | **model.Questionnaire** |
    | Excel\\Questionnaire\\Active                             | **\@.Active**, where **\@** is **model.Questionnaire** |
    | Excel\\Questionnaire\\Code                               | **\@.Code** |
    | Excel\\Questionnaire\\Description                        | **\@.Description** |
    | Excel\\Questionnaire\\QuestionnaireType                  | **\@.QuestionnaireType** |
    | Excel\\Questionnaire\\QuestionOrder                      | **\@.QuestionOrder** |
    | Excel\\Questionnaire\\ResultsGroup\\Code\_               | **\@.ResultsGroup.Code** |
    | Excel\\Questionnaire\\ResultsGroup\\Description\_        | **\@.ResultsGroup.Description** |
    | Excel\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints    | **\@.ResultsGroup.MaxNumberOfPoint** |
    | Excel\\Questionnaire\\Question                           | **\@.Question** |
    | Excel\\Questionnaire\\Question\\CollectionSequenceNumber | **\@.CollectionSequenceNumber**, where **\@** is **model.Questionnaire.Question** |
    | Excel\\Questionnaire\\Question\\Id                       | **\@.Id** |
    | Excel\\Questionnaire\\Question\\MustBeCompleted          | **\@.MustBeCompleted** |
    | Excel\\Questionnaire\\Question\\PrimaryQuestion          | **\@.PrimaryQuestion** |
    | Excel\\Questionnaire\\Question\\SequenceNumber           | **\@.SequenceNumber** |
    | Excel\\Questionnaire\\Question\\Text                     | **\@.Text** |
    | Excel\\Questionnaire\\Question\\Answer                   | **\@.Answer** |
    | Excel\\Questionnaire\\Question\\Answer\\CorrectAnswer    | **\@.CorrectAnswer**, where **\@** is **model.Questionnaire.Answer** |
    | Excel\\Questionnaire\\Question\\Answer\\Points           | **\@.Points** |
    | Excel\\Questionnaire\\Question\\Answer\\Text             | **\@.Text** |

9. Lorsque vous avez terminé, sélectionnez **Enregistrer**.

L’illustration suivante montre l’état final des liaisons de données configurées sur la page **Concepteur de format**.

![Liaisons de données configurées dans le concepteur d’opérations ER.](./media/er-quick-start1-bindings2.png)

> [!IMPORTANT]
> L’ensemble des sources de données et des liaisons spécifiées représente un composant de mise en correspondance de formats du format configuré. Cette mise en correspondance de formats est appelée lorsque vous exécutez le format configuré pour la génération d’états.

### <a name="run-a-designed-format-from-er"></a><a name="RunFormatFromER"></a>Exécuter un format conçu à partir d’ER

Vous pouvez maintenant exécuter un format conçu à des fins de test à partir de la page **Configurations**.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configuration**, dans l’arborescence de configuration, développez **Modèle de questionnaire**, puis **Rapport questionnaire**.
3. Sélectionnez **Concepteur** pour la version de format dont le statut est **Brouillon**.
4. Dans la page **Concepteur de format**, sélectionnez **Exécuter**.
5. Dans la boîte de dialogue **Paramètres de gestion des états électroniques**, sur le raccourci **Enregistrements à inclure**, configurez l’option de filtrage de sorte que seul le questionnaire **SBCCrsExam** soit inclus.
6. Sélectionnez **OK** pour confirmer l’option de filtrage.
7. Sélectionnez **OK** pour exécuter l’état.
8. Examinez l’état généré.

Par [défaut](electronic-reporting-destinations.md#default-behavior), un rapport généré est livré sous forme de fichier Excel que vous pouvez télécharger. Les illustrations suivantes montrent deux pages du rapport généré au format Excel.

![Exemple d’état généré au format Excel, page 1.](./media/er-quick-start1-report1a.png)

![Exemple d"’état généré au format Excel, page 2.](./media/er-quick-start1-report1b.png)

## <a name="tune-a-designed-format"></a><a name="TuneFormat"></a>Ajuster un format conçu

### <a name="modify-a-format-to-change-the-name-of-a-generated-document"></a><a name="ModifyToChangeName"></a>Modifier un format pour changer le nom d’un document généré

Par défaut, un document généré est nommé en utilisant l’alias de l’utilisateur actuel. En modifiant le format, vous pouvez modifier ce comportement afin qu’un document généré soit nommé en fonction de votre logique personnalisée. Par exemple, le nom d’un document généré peut être basé sur la date et l’heure de la session en cours et sur le titre du rapport.

1. Dans la page **Concepteur de formats**, sélectionnez l’élément racine **Rapport**.
2. Sur l’onglet **Mise en correspondance**, sélectionnez **Modifier le nom du fichier**.
3. Dans le champ **Formule**, entrez **CONCATENATE (\@"GER\_LABEL:ReportTitle", " – ", DATETIMEFORMAT(SESSIONNOW(), "yyyy-MM-dd hh-mm-ss"))**.
4. Sélectionnez **Enregistrer**, puis fermez l’éditeur de formule.
5. Sélectionnez **Enregistrer**.

### <a name="modify-a-format-to-change-the-order-of-questions"></a><a name="ModifyToOrder"></a>Modifier un format pour changer l’ordre des questions

Les questions ne sont pas correctement classées dans un rapport généré. Vous pouvez changer l’ordre en modifiant le format.

1. Dans la page **Concepteur de formats**, sélectionnez l’élément racine **Rapport**.
2. Sur l’onglet **Mise en correspondance**, dans l’arborescence des formats, développez **Report\\Questionnaire\\Question**.

    ![Élément de format de question du type Plage dans le concepteur d’opérations ER.](./media/er-quick-start1-bindings3.png)

3. Sur l’onglet **Mise en correspondance**, sélectionnez **model.Questionnaire**.
4. Sélectionnez **Ajouter** \> **Fonctions\\Champ calculé**, puis, dans le champ **Nom**, entrez **OrderedQuestions**.
5. Sélectionnez **Modifier la formule**.
6. Dans l’éditeur de formule, dans le champ **Formule**, entrez **ORDERBY (model.Questionnaire.Question, model.Questionnaire.Question.SequenceNumber)** pour classer la liste des questions du questionnaire courant par numéro d’ordre de séquence.
7. Sélectionnez **Enregistrer**, puis fermez l’éditeur de formule.
8. Sélectionnez **OK** pour terminer la saisie d’un nouveau champ calculé.
9. Sur l’onglet **Mise en correspondance**, sélectionnez **model.Questionnaire.OrderedQuestions**.
10. Dans l’arborescence du format, sélectionnez **Excel\\Questionnaire\\Question**.
11. Sélectionnez **Lier**, puis confirmez que le chemin d’accès **model.Questionnaire.Questions** courant est remplacé par le nouveau chemin d’accès **model.Questionnaire.OrderedQuestions** dans toutes les liaisons d’éléments imbriqués.
12. Sélectionnez **Enregistrer**.

![Liaison de l’élément de format Question avec la source de données OrderedQuestions configurée dans le concepteur d’opérations ER.](./media/er-quick-start1-bindings4.png)

### <a name="run-a-modified-format-from-er"></a><a name="RunFormatFromER2"></a>Exécuter un format modifié à partir d’ER

Vous pouvez maintenant exécuter un format modifié à des fins de test à partir de la structure de gestion des états électroniques.

1. Dans la page **Concepteur de format**, sélectionnez **Exécuter**.
2. Dans la boîte de dialogue **Paramètres de gestion des états électroniques**, sur le raccourci **Enregistrements à inclure**, configurez l’option de filtrage de sorte que seul le questionnaire **SBCCrsExam** soit inclus.
3. Sélectionnez **OK** pour confirmer l’option de filtrage.
4. Sélectionnez **OK** pour exécuter l’état.
5. Examinez l’état généré.

L’illustration suivante montre un rapport généré au format Excel dans lequel les questions sont correctement ordonnées.

![État généré au format Excel avec des questions correctement ordonnées.](./media/er-quick-start1-report2.png)

### <a name="complete-the-format-design"></a><a name="CompleteFormat"></a>Terminer la conception du format

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration, développez **Modèle de questionnaire**, puis **Rapport questionnaire**.
3. Dans le raccourci **Versions**, sélectionnez la version de la configuration ayant un statut **Brouillon**.
4. Sélectionnez **Modifier le statut** \> **Terminé**.

Le statut de la version 1.1 de cette configuration est modifié de **Brouillon** à **Terminé**. La version 1.1 ne peut plus être modifiée. Cette version contient le format configuré et peut être utilisée pour imprimer votre rapport personnalisé. La version 1.2 de cette configuration est créée et a un statut de **Brouillon**. Vous pouvez modifier cette version pour ajuster le format de votre état **Questionnaire**.

![Configuration ER modifiable sur la page Configurations.](./media/er-quick-start1-format-configuration.png)

> [!NOTE]
> Le format configuré est votre conception de l’état **Questionnaire** et ne contient aucune relation avec les artefacts spécifiques à Finance.

## <a name="develop-application-artefacts-to-call-the-designed-report"></a><a name="DevelopCustomCode"></a>Développer des artefacts d’application pour appeler le rapport conçu

En tant qu’utilisateur ayant le rôle d’administrateur système, vous devez développer une nouvelle logique afin que le format ER configuré puisse être appelé à partir de l’interface utilisateur (IU) de l’application pour générer votre rapport personnalisé. Actuellement, ER n’offre aucune capacité pour configurer ce type de logique. Par conséquent, certaines tâches d’ingénierie sont nécessaires. 

Pour développer la nouvelle logique, vous devez déployer une topologie prenant en charge la génération continue. Pour plus d’informations, voir [Déployer des topologies prenant en charge l’élaboration continue et l’automatisation des tests](../perf-test/continuous-build-test-automation.md). Vous devez également avoir accès à l’environnement de développement pour cette topologie. Pour plus d’informations sur l’API de gestion des états électroniques disponible, voir [API de la structure de gestion des états électroniques](er-apis-app73.md).

### <a name="modify-source-code"></a><a name="ModifySourceCode"></a>Modifier le code source

#### <a name="add-a-data-contract-class"></a><a name="DataContractClass"></a>Ajouter une classe de contrat de données

Ajoutez la nouvelle classe **QuestionnairesErReportContrat** à votre projet Microsoft Visual Studio et écrivez le code qui spécifie le contrat de données qui doit être utilisé pour exécuter le format ER configuré.

```xpp
/// <summary>
///     This class is the data contract class for the <c>QuestionnairesErReportDP</c> class.
/// </summary>
/// <remarks>
///    This is the data contract class for the Questionnaires ER report.
/// </remarks>
[
    DataContractAttribute,
    SysOperationContractProcessingAttribute(classStr(QuestionnairesErReportUIBuilder))
    ]
    public class QuestionnairesErReportContract extends ERFormatMappingRunBaseContract implements SysOperationValidatable
{
    ERFormatMappingId formatMapping;

    /// <summary>
    ///    Validates the report parameters.
    /// </summary>
    /// <returns>
    ///    true if no errors; otherwise, false.
    /// </returns>
    public boolean validate()
    {
        boolean ret = true;
        if (!formatMapping)
        {
            ret = checkFailed(strFmt("@SYS26332", new SysDictType(extendedTypeNum(ERFormatMappingId)).label()));
        }
        return ret;
    }
    [
        DataMemberAttribute('FormatMapping'),
        SysOperationLabelAttribute(literalstr("@ElectronicReporting:FormatMapping")),
        SysOperationHelpTextAttribute(literalstr("@ElectronicReporting:FormatMapping"))
    ]
    public ERFormatMappingId parmFormatMapping(ERFormatMappingId _formatMapping = formatMapping)
    {
        formatMapping = _formatMapping;
        return formatMapping;
    }
}
```

#### <a name="add-a-ui-builder-class"></a><a name="UIBuilderClass"></a>Ajouter une classe AI Builder

Ajoutez la nouvelle classe **QuestionnairesErReportUIBuilder** à votre projet Visual Studio et écrivez du code pour générer une boîte de dialogue d’exécution qui sera utilisée pour rechercher l’ID de mise en correspondance de formats du format ER qui doit être exécuté. Le code fourni recherche uniquement les formats ER contenant une source de données de type **Modèle de données** qui fait référence au modèle de données **[Questionnaires](#DataModeName)** en utilisant la définition **[Racine](#RootDefinitionName)**.

> [!NOTE]
> Vous pouvez également utiliser des points d’intégration ER pour filtrer les formats ER. Pour plus d’informations, consultez [API pour afficher une recherche de mise en correspondance de formats](er-apis-app10-0-11.md#api-to-show-a-format-mapping-lookup).

```xpp
/// <summary>
/// The UIBuilder class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportUIBuilder extends SysOperationAutomaticUIBuilder
{
    public const str ERQuestionnairesModel = 'Questionnaires';
    public const str ERQuestionnairesDataContainer = 'Root';

    /// <summary>
    /// Action after build of the dialog UI.
    /// </summary>
    public void postBuild()
    {
        DialogField formatMapping;
        super();
        formatMapping = this.bindInfo().getDialogField(this.dataContractObject(),
            methodStr(QuestionnairesErReportContract, parmFormatMapping));
        formatMapping.registerOverrideMethod(
            methodStr(FormReferenceControl, lookupReference),
            methodStr(QuestionnairesErReportUIBuilder, formatMappingLookup),
            this);
    }

    /// <summary>
    /// Performs the lookup form for format mapping.
    /// </summary>
    /// <param name="_referenceGroupControl">
    /// The control to perform lookup form.
    /// </param>
    public void formatMappingLookup(FormReferenceControl _referenceGroupControl)
    {
        ERObjectsFactory::createFormatMappingTableLookupForControlAndModel(
            _referenceGroupControl,
            ERQuestionnairesModel,
            ERQuestionnairesDataContainer).performFormLookup();
    }
}
```

#### <a name="add-a-data-provider-class"></a><a name="DataProviderClass"></a>Ajouter une classe de fournisseur de données

Ajoutez la nouvelle classe **QuestionnairesErReportDP** à votre projet Visual Studio et écrivez le code qui introduit le fournisseur de données qui doit être utilisé pour exécuter le format ER configuré. Le code fourni comprend uniquement le contrat de données pour ce fournisseur de données.

```xpp
/// <summary>
/// Data provider class for Questionnaires ER report.
/// </summary>
public class QuestionnairesErReportDP
{
    QuestionnairesErReportContract contract;
    public static QuestionnairesErReportDP construct()
    {
        QuestionnairesErReportDP  dataProvider;
        dataProvider = new QuestionnairesErReportDP();
        return dataProvider;
    }
}
```

#### <a name="add-a-labels-file"></a><a name="LabelsFile"></a>Ajouter un fichier d’étiquettes

Ajouter le nouveau fichier d’étiquettes **QuestionnairesErReportLabels\_en-US** dans votre projet Visual Studio et spécifiez les étiquettes suivantes pour les nouvelles ressources de l’interface utilisateur :

- L’étiquette **\@QuestionnairesRapport** pour un nouvel élément de menu contenant le texte suivant en anglais américain (en-US) : **Rapport de questionnaires (généré par ER)**
- L’étiquette **\@QuestionnairesRapportBatchJobDescription** pour un titre de traitement par lots si un format ER sélectionné est planifié pour être exécuté en tant que traitement par lots

#### <a name="add-a-report-service-class"></a><a name="ServiceClass"></a>Ajouter une classe de service de rapport

Ajoutez la nouvelle classe **QuestionnairesErReportService** à votre projet Visual Studio et écrivez un code qui appelle un format ER, l’identifie par un ID de mise en correspondance de formats et fournit un contrat de données en tant que paramètre.

```xpp
using Microsoft.Dynamics365.LocalizationFramework;
/// <summary>
/// The electronic reporting service class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportService extends SysOperationServiceBase
{
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'Questionnaires report';
    public const str ParametersDataSourceName = 'RunTimeParameters';

    /// <summary>
    /// Generates report by using Electronic reporting framework
    /// </summary>
    /// <param name = "_contract">The Questionnaires report contract</param>
    public void generateReportByGER(QuestionnairesErReportContract _contract)
    {
        ERFormatMappingId formatMappingId;
        QuestionnairesErReportDP  dataProvider;
        dataProvider = QuestionnairesErReportDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        if (formatMappingId)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, ParametersDataSourceName, _contract, true));

                // Call ER to generate the report.
                ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                if (formatMappingRun.parmShowPromptDialog(true))
                {
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());
                    formatMappingRun.run();
                }
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

Lorsque vous devez utiliser un format ER qui exécute les données d’application, vous devez configurer une source de données de type **Modèle de données** dans la mise en correspondance de formats. Cette source de données fait référence à une partie spécifique du modèle de données spécifié à l’aide d’une seule définition racine. Lorsque le format ER est exécuté, il appelle cette source de données pour accéder à la mise en correspondance de modèles ER appropriée configurée pour un modèle et une définition racine donnés.

Toutes les informations que vous pouvez préparer dans le code source et stocker dans le cadre du contrat de données peuvent être transmises au format ER en cours d’exécution à l’aide d’une mise en correspondance de modèles ER de ce type. Dans la mise en correspondance de modèles de gestion des états électroniques, vous devez configurer une source de données de type **Objet** qui fait référence à la classe **[QuestionnairesErReportContrat](#DataContractClass)**. Pour identifier une mise en correspondance de modèles, vous devez spécifier une source de données qui appelle cette mise en correspondance de modèles. Dans le code fourni, cette source de données est spécifiée par la constante **ERModelDataSourceName** qui a la valeur **[modèle](#ModelDSName)**. Pour identifier la source de données utilisée pour exposer le contrat de données dans la mise en correspondance de modèles, vous devez spécifier un nom de source de données. Dans le code fourni, ce nom est spécifié par la constante **ParametersDataSourceName** qui a la valeur <a name="DataContractDSName"></a>**RunTimeParameters**.

> [!NOTE]
> Dans un nouvel environnement, vous devrez peut-être actualiser les métadonnées ER afin que ce type de classe soit disponible dans le concepteur de mise en correspondance de modèles ER. Pour plus d’informations, voir [Configurer la structure ER](electronic-reporting-er-configure-parameters.md#frequently-asked-questions).

#### <a name="add-a-report-controller-class"></a><a name="ControllerClass"></a>Ajouter une classe de contrôleur de rapport

Ajoutez la nouvelle classe **QuestionnairesErReportController** à votre projet Visual Studio, et écrivez du code qui exécute un format ER en mode synchrone ou en mode batch, comme vous préférez, dans la boîte de dialogue qui est générée en fonction de la logique de la classe **QuestionnairesErReportUIBuilder**.

```xpp
/// <summary>
/// The controller for Questionnaires ER report
/// </summary>
class QuestionnairesErReportController extends ERFormatMappingRunBaseController
{
    /// <summary>
    /// The main entrance of the controller
    /// </summary>
    /// <param name = "args">The arguments</param>
    public static void main(Args args)
    {
        QuestionnairesErReportController operation;
        operation = new QuestionnairesErReportController(
            classStr(QuestionnairesErReportService),
            methodStr(QuestionnairesErReportService, generateReportByGER),
            SysOperationExecutionMode::Synchronous);
        operation.startOperation();
    }

    /// <summary>
    /// Gets caption of the dialog.
    /// </summary>
    /// <returns>Caption of the dialog</returns>
    public ClassDescription defaultCaption()
    {
        ClassDescription batchDescription;
        batchDescription = "Questionnaires report (powered by ER)";
        return batchDescription;
    }
}
```

#### <a name="add-a-menu-item"></a><a name="MenuItem"></a>Ajouter un élément de menu

Ajoutez le nouvel élément de menu **QuestionnairesErReport** à votre projet Visual Studio. Dans la propriété **Object**, cet élément de menu fait référence à la classe **QuestionnairesErReportController**, et il est utilisé pour spécifier une autorisation utilisateur pour sélectionner et exécuter un format ER. Dans la propriété **Label**, cet élément de menu fait référence à l’étiquette **\@QuestionnairesRapport** que vous avez créée précédemment, afin que le texte correct soit présenté dans l’interface utilisateur de l’application.

#### <a name="add-a-menu-item-to-a-menu"></a><a name="Menu"></a>Ajouter un élément de menu à un menu

Ajoutez le menu existant **KM** à votre projet Visual Studio. Vous devez ajouter un nouvel élément **QuestionnairesErReport** de type **Production** à ce menu. Cet élément doit faire référence à l’élément de menu **QuestionnairesErReport** décrit dans la section précédente.

#### <a name="build-a-visual-studio-project"></a><a name="BuildVSProject"></a>Générer un projet Visual Studio

Créez votre projet pour rendre un nouvel élément de menu accessible aux utilisateurs.

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp"></a>Exécuter un format depuis l’application

1. Allez à **Questionnaire** \> **Conception** \> **Rapport questionnaires (généré par ER)**.

    ![Sélection de l’élément de menu État sur les questionnaires (généré par ER) dans le module Questionnaire pour exécuter le format ER configuré.](./media/er-quick-start1-application-menu-modified.png)

2. Dans la boîte de dialogue, dans le champ **Mise en correspondance de formats**, sélectionnez **Rapport de questionnaires**.
3. Cliquez sur **OK**.
4. Dans la boîte de dialogue **Paramètres de génération d’états électroniques**, sur le raccourci **Enregistrements à inclure**, configurez l’option de filtrage de sorte que seul le questionnaire **SBCCrsExam** soit inclus.
5. Sélectionnez **OK** pour confirmer l’option de filtrage.
6. Sélectionnez **OK** pour exécuter l’état.

    ![Spécification des critères de sélection dans la boîte de dialogue État électronique.](./media/er-quick-start1-report-run-dialog-page.png)

7. Examinez l’état généré.

## <a name="tune-a-designed-er-solution"></a><a name="TuneSolution"></a>Ajuster une solution de gestion des états électroniques conçue

Vous pouvez modifier la solution ER configurée afin qu’elle utilise la classe de fournisseur de données que vous avez développée pour accéder aux détails du format ER en cours d’exécution, et pour qu’elle entre le nom de ce format ER dans un rapport généré.

### <a name="modify-a-model-mapping"></a><a name="ModifyModelMapping"></a>Modifier une mise en correspondance de modèles

#### <a name="add-data-sources-to-access-a-data-contract-object"></a><a name="AddDataSource1"></a>Ajouter des sources de données pour accéder à un objet de contrat de données

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration, développez **Modèle de questionnaire**, puis **Mise en correspondance de questionnaires**.
3. Sélectionnez **Concepteur** pour ouvrir la page **Mise en correspondance de modèles à la source de données**.
4. Sélectionnez **Concepteur** pour ouvrir la mise en correspondance sélectionnée dans le concepteur de mise en correspondance de modèles.
5. Sur la page **Concepteur de mise en correspondance de modèles**, dans le volet **Types de sources de données**, sélectionnez **Dynamics 365 for Operations\\Objet**.
6. dans le volet **Sources de données**, sélectionnez **Ajouter une racine**.
7. Dans la boîte de dialogue, dans le champ **Nom**, entrez **[RunTimeParameters](#DataContractDSName)**, tel que défini dans le code source de la classe **QuestionnairesErReportService**.
8. Dans le champ **Classe**, entrez **[QuestionnairesErReportContrat](#DataContractClass)**, qui a été codé plus tôt.
9. Cliquez sur **OK**.
10. Développez **RunTimeParameters**.

La source de données ajoutée fournit des informations sur l’ID d’enregistrement de la mise en correspondance de formats ER en cours d’exécution.

![Source de données ajoutée dans le concepteur de mise en correspondance de modèles ER.](./media/er-quick-start1-mapping3.png)

#### <a name="add-a-data-source-to-access-er-format-mapping-records"></a><a name="AddDataSource2"></a>Ajouter une source de données pour accéder aux enregistrements de mise en correspondance des formats ER

Continuez à modifier la mise en correspondance de modèles sélectionné en ajoutant une source de données pour accéder aux enregistrements de mise en correspondance de formats ER.

1. Sur la page **Concepteur de mise en correspondance de modèles**, dans le volet **Types de sources de données**, sélectionnez **Dynamics 365 for Operations\\Enregistrements de la table**.
2. dans le volet **Sources de données**, sélectionnez **Ajouter une racine**.
3. Dans la boîte de dialogue, dans le champ **Nom**, entrez **ER1**.
4. Dans le champ **Table**, entrez **ERFormatMappingTable**.
5. Cliquez sur **OK**.

#### <a name="add-a-data-source-to-access-a-format-mapping-record-of-a-running-er-format"></a><a name="AddDataSource3"></a>Ajouter une source de données pour accéder à un enregistrement de mise en correspondance de formats ER d’un format ER en cours d’exécution

Continuez à modifier la mise en correspondance de modèles sélectionné en ajoutant une source de données pour accéder à l’enregistrement de mise en correspondance de formats du format ER en cours d’exécution.

1. Sur la page **Concepteur de mise en correspondance de modèles**, dans le volet **Types de sources de données**, sélectionnez **Fonctions\\Champ calculé**.
2. dans le volet **Sources de données**, sélectionnez **Ajouter une racine**.
3. Dans la boîte de dialogue, dans le champ **Nom**, entrez **ER2**.
4. Sélectionnez **Modifier la formule**.
5. Dans l’éditeur de formule, dans le champ **Formule**, entrez **FIRSTORNULL (FILTER(ER1, ER1.RecId = RunTimeParameters.parmFormatMapping))**.
6. Sélectionnez **Enregistrer**, puis fermez l’éditeur de formule.
7. Cliquez sur **OK**.

#### <a name="enter-the-name-of-the-running-er-format-in-the-data-model"></a><a name="AddBinding"></a>Entrez le nom du format ER en cours d’exécution dans le modèle de données

Continuez à modifier la mise en correspondance de modèles sélectionnée afin que le nom du format ER en cours d’exécution soit entré dans le modèle de données.

1. Sur la page **Concepteur de mise en correspondance de modèles**, dans le volet **Modèle de données**, développez **ExecutionContext**, puis sélectionnez **ExecutionContext\\FormatName**.
2. Dans le volet **Modèle de données**, sélectionnez **Modifier** pour configurer une liaison de données pour le champ du modèle de données sélectionné.
3. Dans l’éditeur de formule, dans le champ **Formule**, entrez **FIRSTORNULL (ER2.’\>Relations’.Format).Name**.
4. Sélectionnez **Enregistrer**, puis fermez l’éditeur de formule.

Du fait que vous avez utilisé le champ **FormatName**, la mise en correspondance de modèles configurée expose maintenant le nom d’un format ER qui appelle cette mise en correspondance de modèles lors de l’exécution.

![Liaison du champ de modèle de données à la méthode de la source de données ajoutée dans le concepteur de mise en correspondance de modèles ER.](./media/er-quick-start1-mapping4.png)

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping2"></a>Terminer la conception de la mise en correspondance de modèles

1. Sur la page **Concepteur de mise en correspondance de modèles**, sélectionnez **Enregistrer**.
2. Fermez la page.
3. Fermez la page Mises en correspondance de modèles.
4. Sur la page **Configurations**, dans l’arborescence de configuration, assurez-vous que la configuration **Mise en correspondance de questionnaires** est toujours sélectionnée. Puis, dans le raccourci **Versions**, sélectionnez la version de la configuration ayant un statut **Brouillon**.
5. Sélectionnez **Modifier le statut** \> **Terminé**.

Le statut de la version 1.2 de cette configuration est modifié de **Brouillon** à **Terminé**. La version 1.2 ne peut plus être modifiée. Cette version contient la mise en correspondance de données configurée et peut être utilisée comme base pour d’autres configurations ER. La version 1.3 de cette configuration est créée et a un statut de **Brouillon**. Vous pouvez modifier cette version pour ajuster la mise en correspondance de modèles **Questionnaire**.

### <a name="modify-a-format"></a><a name="ModifyFormat"></a>Modifier un format

Vous pouvez modifier le format ER configuré pour que son nom apparaisse dans le pied de page d’un rapport généré lors de l’exécution du format ER.

#### <a name="add-a-new-format-element"></a><a name="AddFormatElement"></a>Ajouter un nouvel élément de format

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration, développez **Modèle de questionnaire**, puis **Rapport questionnaire**.
3. Sélectionnez **Concepteur**.
4. Dans la page **Concepteur de formats**, sélectionnez l’élément racine **Rapport**.
5. Sélectionnez **Ajouter** pour ajouter un nouvel élément de format imbriqué pour l’élément racine **Rapport** sélectionné.
6. Sélectionnez **Excel\\Bas de page**.
7. Dans le champ **Nom**, entrez **Pied de page**.
8. Sélectionnez **Rapport\Pied de page**, puis sélectionnez **Ajouter**.
9. Sélectionnez **Texte\\Chaîne**.

#### <a name="bind-the-added-format-element"></a><a name="BindAddedFormatElement"></a>Lier l’élément de format ajouté

1. Sur la page **Concepteur de format**, dans l’onglet **Mise en correspondance**, dans l’arborescence de format, sélectionnez **Modifier la formule** pour l’élément **Pied de page\\Chaîne**.
2. Dans l’éditeur de formule, dans le champ **Formule**, entrez **CONCATENATE ("\&C\&10", FORMAT("Generated by’\%1’ ER solution", model.ExecutionContext.FormatName))**.
3. Sélectionnez **Enregistrer**, puis fermez l’éditeur de formule.
4. Sélectionnez **Enregistrer**.

Le format configuré a maintenant été modifié pour que son nom soit inscrit dans le pied de page d’un rapport généré en utilisant le élément **Pied de page\\Chaîne**.

![Ajout de l’élément de format Pied de page au format configuré dans le concepteur d’opérations ER.](./media/er-quick-start1-template-format-structure3.png)

#### <a name="complete-the-format-design"></a><a name="CompleteFormat2"></a>Terminer la conception du format

1. Fermez la page **Concepteur de format**.
2. Sur la page **Configurations**, dans l’arborescence de configuration, assurez-vous que la configuration **Rapport questionnaire** est toujours sélectionnée. Puis, dans le raccourci **Versions**, sélectionnez la version de la configuration ayant un statut **Brouillon**.
3. Sélectionnez **Modifier le statut** \> **Terminé**.

Le statut de la version 1.2 de cette configuration est modifié de **Brouillon** à **Terminé**. La version 1.2 ne peut plus être modifiée. Cette version contient le format configuré et peut être utilisée comme base pour d’autres configurations ER. La version 1.3 de cette configuration est créée et a un statut de **Brouillon**. Vous pouvez modifier cette version pour ajuster le rapport **Questionnaire**.

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp2"></a>Exécuter un format depuis l’application

1. Allez à **Questionnaire** \> **Conception** \> **Rapport questionnaires (généré par ER)**.
2. Dans la boîte de dialogue, dans le champ **Mise en correspondance de formats**, sélectionnez **Rapport de questionnaires**.
3. Cliquez sur **OK**.
4. Dans la boîte de dialogue **Paramètres de gestion des états électroniques**, sur le raccourci **Enregistrements à inclure**, configurez l’option de filtrage de sorte que seul le questionnaire **SBCCrsExam** soit inclus.
5. Sélectionnez **OK** pour confirmer l’option de filtrage.
6. Sélectionnez **OK** pour exécuter l’état.
7. Examinez le fichier généré dans le format Excel.

Notez que le pied de page du rapport généré contient le nom du format ER qui a été utilisé pour le générer.

![État généré au format Excel.](./media/er-quick-start1-report4.png)

### <a name="run-a-format-from-er"></a><a name="RunFormatFromER3"></a>Exécuter un format à partir d’ER

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration, développez **Modèle de questionnaire**, puis **Rapport questionnaire**.
3. Dans le volet Actions, sélectionnez **Exécuter**.
4. Dans la boîte de dialogue **Paramètres de génération d’états électroniques**, sur le raccourci **Enregistrements à inclure**, configurez l’option de filtrage de sorte que seul le questionnaire **SBCCrsExam** soit inclus.
5. Sélectionnez **OK** pour confirmer l’option de filtrage.
6. Sélectionnez **OK** pour exécuter l’état.
7. Examinez le fichier généré dans le format Excel.

Notez que le pied de page du rapport généré ne contient pas le nom du format ER utilisé pour le générer, car l’objet de contrat de données n’a pas été transmis à la mise en correspondance de modèles en cours d’exécution lorsqu’il a été appelé par le format ER qui a été exécuté à partir de ER.

### <a name="configure-a-format-destination-for-on-screen-preview"></a><a name="ConfigureDestination"></a>Configurer une destination de format pour l’aperçu à l’écran

1. Allez dans **Administration d’organisation** \> **Génération d’états électroniques** \> **Destination des états électroniques**.
2. Sur la page **Destination des rapports électroniques**, ajoutez un enregistrement de destination pour le format ER **Rapport de questionnaire**.
3. Sur le raccourci **Destination du fichier**, configurez la [destination](er-destination-type-screen.md) **Écran** pour le composant de format **Rapport** qui a été [ajouté](#AddFormatRootElement) comme élément racine de format ER **Rapport questionnaire** de la configuration.
4. Sur le raccourci **Paramètres de conversion PDF**, configurez la destination pour convertir un rapport au [format PDF](electronic-reporting-destinations.md#OutputConversionToPDF) qui utilise l’orientation de page **Paysage**.

![Configuration de la destination d’écran personnalisée pour le format ER sur la page de destination des états électroniques.](./media/er-quick-start1-destination.png)

### <a name="run-a-format-from-the-application-to-preview-it-as-a-pdf-document"></a><a name="RunFormatFromApp3"></a>Exécuter un format à partir de l’application pour le prévisualiser sous forme de document PDF

1. Allez à **Questionnaire** \> **Conception** \> **Rapport questionnaires (généré par ER)**.
2. Dans la boîte de dialogue, dans le champ **Mise en correspondance de formats**, sélectionnez **Rapport de questionnaires**.
3. Cliquez sur **OK**.
4. Dans la boîte de dialogue **Paramètres de génération d’états électroniques**, sur le raccourci **Enregistrements à inclure**, configurez l’option de filtrage de sorte que seul le questionnaire **SBCCrsExam** soit inclus.
5. Sélectionnez **OK** pour confirmer l’option de filtrage.

    Sur le raccourci **Destinations**, notez que le champ **Production** est défini sur **Écran**. Si vous souhaitez modifier la destination configurée, sélectionnez **Modifier**.

    ![Boîte de dialogue d’exécution de l’état ER dans laquelle vous pouvez modifier la destination configurée.](./media/er-quick-start1-run-settings.png)

6. Sélectionnez **OK** pour exécuter l’état.
7. Examinez le fichier généré dans le format PDF.

    ![Aperçu à l’écran de l’état généré au format PDF.](./media/er-quick-start1-preview-PDF.png)

## <a name="additional-resources"></a><a name="References"></a>Ressources supplémentaires

- [Vue d’ensemble des États électroniques](general-electronic-reporting.md)
- [Langage de formule dans la gestion des états électroniques](er-formula-language.md)
- [Concevoir des états multilingues](er-design-multilingual-reports.md)
- [API de la structure de gestion des états électroniques](er-apis-app73.md)
- [Fonction CASE](er-functions-logical-case.md)
- [Fonction CONCATENATE](er-functions-text-concatenate.md)
- [Fonction DATETIMEFORMAT](er-functions-datetime-datetimeformat.md)
- [Fonction FILTER](er-functions-list-filter.md)
- [Fonction FIRSTORNULL](er-functions-list-firstornull.md)
- [Fonction FORMAT](er-functions-text-format.md)
- [Fonction IF](er-functions-logical-if.md)
- [Fonction ORDERBY](er-functions-list-orderby.md)
- [Fonction SESSIONNOW](er-functions-datetime-sessionnow.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
