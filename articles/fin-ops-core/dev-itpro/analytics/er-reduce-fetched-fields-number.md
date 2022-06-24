---
title: Amélioration des performances des solutions ER en réduisant le nombre de champs de table extraits lors de l’exécution
description: Cet article explique comment vous pouvez améliorer les performances en réduisant le nombre de champs de table extraits lors de l’exécution.
author: NickSelin
ms.date: 05/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: eb76c415da87d421b8135a93b84f4e905f01e70d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847449"
---
# <a name="improve-performance-of-er-solutions-by-reducing-the-number-of-table-fields-that-are-fetched-at-runtime"></a>Amélioration des performances des solutions ER en réduisant le nombre de champs de table extraits lors de l’exécution

[!include[banner](../includes/banner.md)]

Vous pouvez créer des [formats](er-overview-components.md#format-components-for-outgoing-electronic-documents) de [gestion des états électroniques](general-electronic-reporting.md) (ER) qui génèrent des documents sortants dans différents formats. Lorsqu’un document est généré, un format ER appelle les sources de données configurées dans une [mise en correspondance des modèles](er-overview-components.md#model-mapping-component) ER correspondante. Pour configurer l’accès aux tables d’application, aux requêtes ou aux entités pour la récupération des enregistrements, vous pouvez utiliser les sources de données ER du type *Enregistrements de la table*. Par défaut, une source de données de type *Enregistrements de la table* récupère les valeurs de tous les champs dans les enregistrements demandés. Toutefois, vous pouvez configurer ce type de source de données afin qu’il récupère uniquement les valeurs de champ requises pour le format ER en cours d’exécution. Cette configuration permet de réduire la consommation de mémoire du serveur d’applications qui effectue la récupération des données et la mise en cache des enregistrements.

Pour en savoir plus sur la façon de limiter la liste des champs récupérés des sources de données du type *Enregistrements de table*, exécutez l’exemple décrit dans cet article.

## <a name="example-reduce-the-number-of-table-fields-that-are-fetched-at-runtime"></a>Exemple : Réduire le nombre de champs de table extraits lors de l’exécution

Les procédures suivantes montrent comment un utilisateur du rôle Administrateur système ou Développeur de gestion des états électroniques peut configurer une mise en correspondance des modèles ER afin de récupérer uniquement les champs requis pour exécuter le format ER, afin de réduire la consommation de mémoire du serveur d’applications.

Ces procédures peuvent être effectuées dans la société **USMF** dans Microsoft Dynamics 365 Finance. Aucun codage n’est requis.

Pour réaliser cet exemple, vous devez avoir accès à la société **USMF** pour l’un des rôles suivants :

- Consultant fonctionnel de gestion des états électroniques
- Administrateur système

Dans cet exemple, vous allez utiliser les [configurations](general-electronic-reporting.md#Configuration) ER fournies pour la société fictive, **Litware, Inc**. Veillez à ce que le fournisseur de configuration pour l’exemple de société **Litware, Inc.** (`http://www.litware.com`) soit répertorié pour la structure ER et qu’il soit marqué comme **actif**. Si ce fournisseur de configuration n’est pas répertorié ou s’il n’est pas marqué comme **actif**, suivez les étapes de la rubrique [Créer un fournisseur de configuration et le marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="configure-the-er-framework"></a>Configurer la structure de gestion des états électroniques

Procédez comme suit dans [Configurer la structure des états électroniques](er-quick-start2-customize-report.md#ConfigureFramework) pour configurer l’ensemble minimum de paramètres d’état électronique. Vous devez réaliser cette configuration avant de commencer à utiliser la structure de gestion des états électroniques pour modifier les sources de données de la solution ER.

### <a name="import-the-sample-er-configurations"></a>Importer l’exemple de configurations ER

Si vous n’avez pas encore réalisé l’exemple de l’article [Concevoir une nouvelle solution de gestion des états électroniques pour imprimer un état personnalisé](er-quick-start1-new-solution.md), téléchargez et stockez localement les fichiers XML pour les configurations suivantes de la solution ER fournie.

| Description du contenu            | Nom du fichier |
|--------------------------------|-----------|
| Configuration de modèle de données ER    | [Questionnaires model.version.1.xml](https://download.microsoft.com/download/b/6/3/b633bd34-d200-4422-96d9-8f62eb5218f8/Questionnaires_model.version.1.xml) |
| Configuration de mise en correspondance de modèle ER | [Questionnaires mapping.version.1.1.xml](https://download.microsoft.com/download/7/b/2/7b258e4e-4bd5-46a4-8114-27419ae4acd8/Questionnaires_mapping.version.1.1.xml) |
| Configuration de format ER        | [Questionnaires format.version.1.1.xml](https://download.microsoft.com/download/1/b/a/1ba39ec2-257a-44d8-972f-25bf7d18fb41/Questionnaires_format.version.1.1.xml) |

Suivez ensuite ces étapes pour télécharger les configurations de la solution ER fournie sur votre instance Finance.

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sélectionnez **Configurations des états**.
3. Sur la page **Configurations**, importez la configuration du modèle de données ER.

    1. Sélectionner **Échanger**, puis sélectionnez **Charger depuis le fichier XML**.
    2. Sélectionnez **Parcourir**, puis recherchez et sélectionnez le fichier **Questionnaires model.version.1.xml**, et cliquez sur **OK**.

4. Importez la configuration de mise en correspondance des modèles ER.

    1. Sélectionner **Échanger**, puis sélectionnez **Charger depuis le fichier XML**.
    2. Sélectionnez **Parcourir**, puis recherchez et sélectionnez le fichier **Questionnaires mapping.1.1.xml** et cliquez sur **OK**.

5. Importez la configuration de format ER.

    1. Sélectionner **Échanger**, puis sélectionnez **Charger depuis le fichier XML**.
    2. Sélectionnez **Parcourir**, puis recherchez et sélectionnez le fichier **Questionnaires format.1.1.xml** et cliquez sur **OK**.

6. Dans l’arborescence de configuration, développez **Questionnaires model**.
7. Consultez la liste des configurations ER importées dans l’arborescence de configuration.

    ![Vérification de la liste des configurations ER importées sur la page Configurations.](./media/er-reduce-fetched-fields-number-configurations.png)

### <a name="review-the-provided-er-model-mapping"></a>Vérifier la mise en correspondance des modèles ER fournis

1. Sur la page **Configurations**, sélectionnez **Questionnaires mapping**.
2. Dans le volet Actions, sélectionnez **Concepteur**.
3. Sur la page **Mise en correspondance entre le modèle et la source de données**, sélectionnez **Concepteur**.
4. Sur la page **Concepteur de la mise en correspondance des modèles**, dans le volet Actions, sélectionnez **Vue des groupes** pour activer la vue **Groupe**.
5. Dans le volet **Modèle de données**, développez **Questionnaire**.

    Notez que la source de données **Questionnaire** a été configurée pour accéder à la table d’application `KMCollection`.

6. Dans le volet **Sources de données**, développez **Enregistrements de la table** \> **Questionnaire** \> **Champs**.

    Notez combien de champs de la table d’application `KMCollection` sont exposés par la source de données **Questionnaire** du type *Enregistrements de la table*.

    ![Vérification de la mise en correspondance des modèles fournie sur la page Concepteur de la mise en correspondance des modèles lorsque Vue des groupes est activée.](./media/er-reduce-fetched-fields-number-mapping1.png)

7. Dans le volet Actions, sélectionnez **Vue des groupes** à nouveau pour désactiver la vue **Groupe**, puis sélectionnez **Afficher tout** \> **Afficher les éléments mappés uniquement**.

    Notez que quelques champs de la table d’application `KMCollection` sont utilisés pour remplir la liste des enregistrements **Questionnaire** dans le modèle de données ER :

    - `Active`
    - `Description`
    - `questionMode`
    - `kmCollectionId`

    ![Vérification de la mise en correspondance des modèles fourni sur la page Concepteur de la mise en correspondance des modèles lorsque Vue des groupes est désactivée.](./media/er-reduce-fetched-fields-number-mapping2.png)

### <a name="turn-on-the-er-performance-trace"></a>Activer les performances de suivi ER

Suivez les étapes de la rubrique [Activer les performances de suivi ER](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) pour définir les paramètres utilisateur ER qui permettent de suivre l’exécution des composants ER.

### <a name="run-the-provided-er-format-by-using-the-provided-model-mapping"></a>Exécuter le format ER fourni en utilisant la mise en correspondance des modèles fournie

Suivez les étapes de la rubrique [Exécuter un format conçu à partir d’ER](er-quick-start1-new-solution.md#RunFormatFromER) pour exécuter le format ER fourni pour un seul questionnaire à partir de la page **Configurations**.

### <a name="review-the-execution-trace-of-the-first-run"></a>Vérifier le suivi de l’exécution de la première exécution

1. Accédez à **Administration d’organisation** \> **Gestion des états électroniques \> Configurations**.
2. Sur la page **Configurations**, développez **Questionnaires model**, et sélectionnez **Questionnaires mapping**.

    > [!NOTE]
    > Les détails du raccourci **Versions** indiquent que vous avez sélectionné la version brouillon de la configuration **Questionnaires mapping**. Par conséquent, vous pouvez modifier le contenu de cette mise en correspondance des modèles.

3. Dans le volet Actions, sélectionnez **Concepteur**.
4. Sur la page **Mise en correspondance entre le modèle et la source de données**, sélectionnez **Concepteur**.
5. Sur la page **Concepteur de mise en correspondance des modèles**, sur le volet Actions, sélectionnez **Suivi des performances**.
6. Dans la boîte de dialogue **Paramètres de résultat du suivi des performances**, sélectionnez le suivi qui a été généré lors de la dernière exécution du format.

    ![Sélection du suivi dans la boîte de dialogue Paramètres de résultat du suivi des performances.](./media/er-reduce-fetched-fields-number-select-trace-1.png)

7. Cliquez sur **OK**. 
8. Sur le raccourci **Détails**, filtrez le chemin d’accès **Questionnaire** qui pointe vers la source de données **Questionnaire**.
9. Passez en revue les détails de la requête de base de données qui a été générée lorsque la source de données **Questionnaire** a été appelée.

    Notez que tous les champs de la table d’application `KMCollection` ont été extraits lors de l’exécution lorsque la source de données **Questionnaire** a été appelée.

    ![Vérification des détails de la requête de base de données sur la page Concepteur de la mise en correspondance des modèles.](./media/er-reduce-fetched-fields-number-query1.png)

### <a name="modify-the-provided-er-model-mapping"></a>Modifier la mise en correspondance des modèles ER fournis

1. Sur la page **Concepteur de mise en correspondance des modèles**, dans le volet **Sources de données**, sélectionnez la source de données **Questionnaire**.
2. Dans le volet **Sources de données**, sélectionnez **Modifier**.
3. Dans la boîte de dialogue **Propriétés de la source de données**, sélectionnez **Sélectionner des champs** pour spécifier la liste des champs de table d’application `KMCollection` référencée qui sera récupérée au moment de l’exécution lorsque la source de données **Questionnaire** modifiable sera appelée.

    ![Sélection de Sélectionner des champs dans la boîte de dialogue Propriétés de la source de données pour commencer à configurer la liste des champs qui sera récupérée de table d’application à l’aide de la source de données modifiable.](./media/er-reduce-fetched-fields-number-select-fields1.png)

4. Sur la page **Sélectionner des champs**, sélectionnez **Remplissage auto**.

    La liste **Sélectionner des champs** est automatiquement remplie, en fonction des artefacts préconfigurés de la mise en correspondance des modèles. Tous les champs et toutes les relations de la table référencée qui sont mentionnés dans une liaison, une formule ou une source de données de la mise en correspondance des modèles sont ajoutés à la liste.

    ![Configuration de la liste des champs qui seront extraits de la table d’application sur la page Sélectionner des champs.](./media/er-reduce-fetched-fields-number-select-fields2.png)

5. Sélectionnez **Enregistrer** et fermez la page **Sélectionner des champs**.
6. Cliquez sur **OK** pour stocker les modifications que vous avez apportées aux paramètres de la source de données.
7. Dans le volet Actions, sélectionnez **Afficher tout**.

    Notez que la source de données **Questionnaire** affiche maintenant le texte **\<Fields are filtered\>**. Ce texte indique que la source de données a été configurée pour extraire un nombre limité de champs de la table d’application référencée.

    ![Vérification de la mise en correspondance des modèles sur la page Concepteur de la mise en correspondance des modèles.](./media/er-reduce-fetched-fields-number-mapping3.png)

8. Cliquez sur **Enregistrer** pour stocker les modifications que vous avez apportées à la mise en correspondance des modèles modifiable.

    > [!NOTE]
    > Au moment de l’exécution, ER analyse les relations ajoutées et ajoute tous les champs qui y sont utilisés à la requête de base de données, même si ces champs n’ont pas été explicitement ajoutés à la liste des champs extraits au moment de la conception.

### <a name="run-the-provided-er-format-by-using-the-updated-model-mapping"></a>Exécuter le format ER fourni en utilisant la mise en correspondance des modèles mise à jour

Suivez les étapes de la rubrique [Exécuter un format conçu à partir d’ER](er-quick-start1-new-solution.md#RunFormatFromER) pour exécuter le format ER fourni pour un seul questionnaire à partir de la page **Configurations**.

### <a name="review-the-execution-trace-of-the-second-run"></a>Vérifier le suivi de l’exécution de la deuxième exécution

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, développez **Questionnaires model**, et sélectionnez **Questionnaires mapping**.
3. Dans le volet Actions, sélectionnez **Concepteur**.
4. Sur la page **Mise en correspondance entre le modèle et la source de données**, sélectionnez **Concepteur**.
5. Sur la page **Concepteur de mise en correspondance des modèles**, sur le volet Actions, sélectionnez **Suivi des performances**.
6. Dans la boîte de dialogue **Paramètres de résultat du suivi des performances**, sélectionnez le suivi qui a été généré lors de la dernière exécution du format.
7. Cliquez sur **OK**.
8. Sur le raccourci **Détails**, filtrez le chemin d’accès **Questionnaire** qui pointe vers la source de données **Questionnaire**.
9. Passez en revue les détails de la requête de base de données qui a été générée lorsque la source de données **Questionnaire** a été appelée.

    Notez que seuls les champs requis pour renseigner la source de données ont été récupérés lors de l’exécution à partir de la table d’application `KMCollection` lorsque la source de données **Questionnaire** a été appelée.

    > [!NOTE]
    > Certains champs, tels que les champs pour l’ID de partition, l’ID de zone de données et l’ID d’enregistrement, sont automatiquement ajoutés par la structure de gestion des données de l’application Finance.

    ![Vérification des détails de la requête de base de données pour la mise en correspondance des modèles mise à jour sur la page Concepteur de la mise en correspondance des modèles.](./media/er-reduce-fetched-fields-number-query2.png)

Vous pouvez utiliser cette technique pour réduire le nombre d’enregistrements extraits lorsque vous devez réduire la consommation de mémoire par la mise en correspondance des modèles ER et le format ER en cours d’exécution.

## <a name="limitations"></a>Limitations

Lorsque vous limitez le nombre de champs extraits pour une source de données de type *Enregistrements de la table*, vous ne pouvez pas utiliser les méthodes d’une table d’application à laquelle la source de données fait référence, car les métadonnées de l’application ne fournissent pas d’informations sur les champs de table requis pour appeler ces méthodes.

## <a name="usage-notes"></a>Notes d’utilisation

Bien que le **Remplissage automatique** ajoute automatiquement des champs, il ne supprime pas automatiquement les champs précédemment ajoutés, même s’ils ne sont plus utilisés dans les liaisons, les formules et les sources de données de la mise en correspondance des modèles modifiable.

Lorsque vous sélectionnez **Remplissage automatique**, ER analyse les liaisons, les formules et les sources de données dont disposait la mise en correspondance des modèles modifiable lorsque vous l’avez ouverte pour la modifier. Si vous modifiez les liaisons, les formules et les sources de données de la mise en correspondance des modèles modifiable et que vous souhaitez utiliser la commande **Remplissage automatique**, fermez le concepteur de mise en correspondance des modèles, puis rouvrez-le pour modifier votre mise en correspondance des modèles. 

## <a name="additional-resources"></a>Ressources supplémentaires

- [Suivre l’exécution des formats d’état électronique pour résoudre les problèmes de performances](trace-execution-er-troubleshoot-perf.md)
- [Résolution des problèmes de performances dans les configurations ER](er-troubleshoot-perf-issues-in-configurations.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
