---
title: Utilisation des sources de données JOIN dans des mises en correspondance de modèle ER pour obtenir des données de plusieurs tables d’application
description: Cette rubrique explique comment utiliser les sources de données de type JOIN dans la gestion des états électroniques (ER).
author: NickSelin
manager: AnnBe
ms.date: 05/04/2020
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
ms.search.validFrom: 2019-03-01
ms.dyn365.ops.version: Release 10.0.1
ms.openlocfilehash: e872ff38d2115273fe76f5a2f54197c55cc7a2e0
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565539"
---
# <a name="use-join-data-sources-to-get-data-from-multiple-application-tables-in-electronic-reporting-er-model-mappings"></a>Utilisation des sources de données JOIN pour obtenir des données de plusieurs tables d’application dans des mises en correspondance de modèle de gestion des états électroniques (ER)

[!include[banner](../includes/banner.md)]

Lors de la configuration des mises en correspondance ou des formats de modèle de gestion des états électroniques (ER), vous pouvez [ajouter](#review) les sources de données nécessaires de type **JOIN**. Au moment de la conception, une source de données **Joindre** est configurée comme ensemble de plusieurs sources de données dont chacune retourne une liste des enregistrements. Pour chaque source de données sauf la première, vous devez définir les conditions nécessaires pour joindre des enregistrements des sources de données actuelles et précédentes. À l’exécution, une source de données configurée de type **Joindre** [retourne](#executeERformat) une liste jointe simple des enregistrements contenant les champs des enregistrements des sources de données imbriquées.

Les types de jointures suivants sont actuellement pris en charge :

- Jointure externe (gauche) :
    - Joignez tous les enregistrements de la première source de données (extrême gauche) puis toute correspondance conforme aux enregistrements de conditions configurés de la deuxième source de données (extrême droite).
- Jointure interne (droite) :
    - Joignez uniquement les enregistrements de la première source de données (extrême gauche) et uniquement les enregistrements de la deuxième source de données (extrême droite) correspondant les uns aux autres conformément aux conditions configurées.

Dans la source de données **Jointure** configurée, lorsque toutes les sources de données sont de type **Enregistrements de table**, l’exécution de la source de données de jointure peut être [effectuée au niveau de base de données](#analyze) à l’aide d’une instruction SQL unique. Cette instruction réduit le nombre d’appels de la base de données, ce qui améliore les performances de mise en correspondance des modèles. Sinon, l’exécution de la source **Joindre les données** est réalisée dans la mémoire.

> [!NOTE]
> L’utilisation de la fonction **VALUEIN** dans des expressions ER qui indiquent les conditions pour joindre les enregistrements dans les sources de données de type Join n’est pas prise en charge encore. Visitez la page [Concepteur de formule dans la gestion des états électroniques](general-electronic-reporting-formula-designer.md) pour plus d’informations sur cette fonction.

Pour en savoir plus sur cette fonctionnalité, exécutez l’exemple décrit dans cette rubrique.

## <a name="example-use-join-data-sources-in-er-model-mappings"></a>Exemple : Utilisation de sources de données JOIN dans des mises en correspondance de modèle ER

La procédure suivante décrit comment l’administrateur système ou le développeur de gestion des états électroniques peut configurer une mise en correspondance de modèle de gestion d’états électroniques (ER) pour obtenir des données de plusieurs tables d’application simultanément à l’aide de sources de données de type **Join** pour améliorer les performances d’accès de données. Ces étapes peuvent être effectuées pour n’importe quelle société Dynamics 365 Finance ou Regulatory Configuration Service (RCS).

### <a name="prerequisites"></a>Conditions préalables

Pour terminer les exemples de cette rubrique, vous devez avoir accès à l’un des éléments suivants en fonction du service utilisé pour effectuer cette procédure :

**Accès à Finance pour un des rôles suivants :**

- Développeur d’états électroniques
- Consultant fonctionnel des états électroniques
- Administrateur système

**L’accès à RCS pour l’un des rôles suivants :**

- Développeur d’états électroniques
- Consultant fonctionnel des états électroniques
- Administrateur système

Vous devez également commencer par effectuer les étapes de la procédure [Créer un fournisseur de configuration et le marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md).

Au préalable, vous devez également télécharger sur le [Centre de téléchargement Microsoft](https://go.microsoft.com/fwlink/?linkid=000000) et localement enregistrer les exemples de fichiers de configuration ER suivants :

| **Description du contenu**  | **Nom de fichier**   |
|--------------------------|-----------------|
| Exemple de fichier de configuration **Modèle de données ER**, qui est utilisé comme source de données pour les exemples.| [Modèle pour apprendre les sources de données JOIN.version.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Exemple de fichier de configuration **Mise en correspondance de modèle ER**, qui met en service le modèle de données ER pour les exemples. | [Mise en correspondance pour apprendre les sources de données JOIN.version.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Exemple de configuration de **Format ER**. Ce fichier décrit les données pour remplir le composant de format ER pour les exemples. | [Mise en forme pour apprendre les sources de données JOIN.version.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

### <a name="activate-a-configurations-provider"></a>Activer un fournisseur de configurations

1. Accéder à Finance ou RCS dans la première session de votre navigateur web.
2. Allez dans **Administration d’organisation \> Espaces de travail \> États électroniques**.
3. Dans la page **Configurations de localisation**, dans la section **Fournisseurs de configuration**, vérifiez que le fournisseur de configuration pour l’exemple de société [Litware, Inc.](http://www.litware.com) est répertorié, et qu’il est marqué comme **actif**. Si ce fournisseur de configuration ne s’affiche pas, suivez les étapes de la procédure [Créer un fournisseur de configuration et le marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md).

    ![Espace de travail des états électroniques](./media/GER-JoinDS-ActiveProvider.PNG)

### <a name="import-sample-er-configuration-files"></a>Importer des exemples de fichiers de configuration ER

1. Sélectionnez **Configurations des états**.
2. Importez le fichier de configuration du modèle de données ER.
    1. Sélectionnez **Exchange**.
    2. Sélectionnez **Charger depuis le fichier XML**.
    3. Sélectionnez **Parcourir** pour rechercher le fichier **Modèle pour apprendre les sources de données JOIN.version.1.1.xml**.
    4. Cliquez sur **OK**.
3. Importez le fichier de configuration de mise en correspondance de modèle ER.
    1. Sélectionnez **Exchange**.
    2. Sélectionnez **Charger depuis le fichier XML**.
    3. Sélectionnez **Parcourir** pour rechercher le fichier **Mise en correspondance pour apprendre les sources de données JOIN.version.1.1.xml**.
    4. Cliquez sur **OK**.
4. Importer le fichier de configuration du format ER.
    1. Sélectionnez **Exchange**.
    2. Sélectionnez **Charger depuis le fichier XML**.
    3. Sélectionnez **Parcourir** pour rechercher le fichier **Mise en forme pour apprendre les sources de données JOIN.version.1.1.xml**.
    4. Cliquez sur **OK**.
5. Dans l’arborescence de configurations, développez l’élément **Modèle pour apprendre les sources de données JOIN** ainsi que d’autres éléments de modèle (le cas échéant).
6. Observez la liste des configurations ER dans l’arborescence, ainsi que les détails de la version sur l’organisateur **Versions** - ils seront utilisés comme source de données pour votre exemple d’état.

    ![Page des configurations de gestion des états électroniques](./media/GER-JoinDS-ConfigurationsTree.PNG)

### <a name="turn-on-execution-trace-options"></a>Activer l’exécution des options de suivi de l’exécution

1. Sélectionner **CONFIGURATIONS**.
2. Sélectionnez **Utiliser les paramètres**.
3. Définissez les paramètres de suivi de l’exécution comme indiqué dans la capture d’écran ci-dessous.

    ![Page Paramètres utilisateur de la gestion des états électroniques](./media/GER-JoinDS-Parameters.PNG)

    Avec ces paramètres activés, pour chaque exécution du fichier de format ER importé, le suivi de l’exécution sera généré. À l’aide des détails de suivi d’exécution générée, vous pouvez analyser l’exécution du format ER et des composants de mise en correspondance ER. Visitez la page [Suivi de l’exécution du format ER pour résoudre les problèmes de performances](trace-execution-er-troubleshoot-perf.md) pour plus d’informations sur la fonctionnalité de suivi l’exécution ER.

### <a name="review-er-model-mapping-part-1"></a>Vérifier la mise en correspondance de modèle ER (partie 1)

Examinez les paramètres du composant de mise en correspondance de modèle ER. Le composant est configuré pour accéder aux informations sur les versions des configurations ER, les détails des configurations et les fournisseurs de configuration sans utiliser les sources de données de type **Join**.

1. Sélectionnez la configuration **Mise en correspondance pour apprendre les sources de données JOIN**.
2. Sélectionnez **Concepteur** pour ouvrir la liste des mises en correspondance.
3. Sélectionnez **Concepteur** pour consulter les détails de mise en correspondance.
4. Sélectionnez **Afficher les détails**.
5. Dans l’arborescence de configurations, développez les éléments de modèle de données **Set1** et **Set1.Details** :

    1. La liaison **Details: Record list = Versions** indique que l’élément **Set1.Details** est lié à la source de données **Versions** retournant des enregistrements de la table **ERSolutionVersionTable**. Chaque enregistrement de cette table représente une version unique d’une configuration ER. Le contenu de cette table s’affiche dans l’organisateur **Versions** de la page **Configurations**.
    2. La liaison **ConfigurationVersion: String = @.PublicVersionNumber** signifie que la valeur de la version publique de la version de chaque configuration ER est extraite du champ **PublicVersionNumber** de la table **ERSolutionVersionTable** et placée dans l’élément **ConfigurationVersion**.
    3. La liaison **ConfigurationTitle: String = @.’>Relations’.Solution.Name** indique que le nom d’une configuration ER est extrait du champ **Nom** de l’évaluation de la table **ERSolutionTable** à l’aide de la relation plusieurs à un (**« >Relations »**) entre les tables **ERSolutionVersionTable** et **ERSolutionTable**. Les noms des configurations ER de l’instance actuelle d’application sont présentés dans l’arborescence de configurations sur la page **Configurations**.
    4. La liaison **@.’>Relations’.Solution.’>Relations’.SolutionVendor.Name** signifie que le nom du fournisseur de configuration propriétaire de la configuration actuelle est extrait du champ **Nom** de l’évaluation de la table **ERSolutionTable** à l’aide de la relation plusieurs à un entre les tables **ERSolutionVersionTable** et **ERVendorTable**. Les fournisseurs de configuration ER sont présentés dans l’arborescence de configurations sur la page **Configurations** de l’en-tête de page de chaque configuration. La liste entière de fournisseurs de configuration ER figure sur la page de table **Administration d’organisation \> Gestion des états électroniques \> Fournisseur de configuration**.

    ![Page du concepteur de mise en correspondance des modèles ER](./media/GER-JoinDS-Set1Review.PNG)

6. Dans l’arborescence de configurations, développez l’élément de modèle de données **Set1.Summary** :

    1. La liaison **VersionsNumber: Integer = VersionsSummary.aggregated.VersionsNumber** indique que l’élément **Set1.Summary.VersionsNumber** est lié au champ d’agrégation **VersionsNumber** de la source de données **VersionsSummary** du type **GroupBy** configurée pour retourner le nombre d’enregistrements de la table **ERSolutionVersionTable** via la source de données **Versions**.

    ![Page des paramètres de source de données GROUPBY](./media/GER-JoinDS-Set1GroupByReview.PNG)

7. Fermez la page.

### <a name="review-er-model-mapping-part-2"></a><a name="review"></a> Vérifier la mise en correspondance de modèle ER (partie 2)

Examinez les paramètres du composant de mise en correspondance de modèle ER. Le composant est configuré pour accéder aux informations sur les versions des configurations ER, les détails des configurations et les fournisseurs de configuration en utilisant une source de données de type **Join**.

1. Dans l’arborescence de configurations, développez les éléments de modèle de données **Set2** et **Set2.Details**. La liaison **Details: Record list = Details** indique que l’élément **Set2.Details** est lié à la source de données **Détails** configurée comme source de données de type **Join**.

    ![Page du concepteur de mise en correspondance des modèles ER](./media/GER-JoinDS-Set2Review.PNG)

    La source de données **Join** peut être ajoutée en sélectionnant la source de données **Functions\Join** :

    ![Page du concepteur de mise en correspondance des modèles ER](./media/GER-JoinDS-AddJoinDS.PNG)

2. Sélectionnez la source de données **Détails**.
3. Sélectionnez **Modifier** dans le volet **Sources de données**.
4. Sélectionnez **Modifier la jointure**.
5. Sélectionnez **Afficher les détails**.

    ![Page des paramètres de source de données JOIN](./media/GER-JoinDS-JoinDSEditor.PNG)

    Cette page permet de concevoir la source de données requise de **type Join**. À l’exécution, cette source de données crée une liste jointe simple des enregistrements des sources de données de la grille **Liste jointe**. La jointure des enregistrements commencera à partir de la source de données **ConfigurationProviders** située dans la grille en premier (la colonne **Type** est vide pour elle). Les enregistrements de chaque autre source de données sont joints par la suite aux enregistrements de la source de données parente selon son ordre dans cette grille. Chaque source de données de jointure doit être configurée comme source de données imbriquée sous une source de données cible (la source de données `1Versions` est imbriquée sous `1Configurations` une ; la source de données `1Configurations` est imbriquée sous **ConfigurationProviders** une). Chaque source de données de configuration doit contenir les conditions de la jointure. Dans la source de données de cette **Jointure** donnée, les jointures suivantes sont définies :

    - Chaque enregistrement de la source de données **ConfigurationProviders** (référencées la table **ERVendorTable**) est joint uniquement aux enregistrements **1Configurations** un (référencés dans la table **ERSolutionTable**) ayant la même valeur dans les champs **SolutionVendor** et **Recid**. Le type **Jointure interne** est utilisé pour cette jointure ainsi que les conditions suivantes pour mettre en correspondance les enregistrements :

    FILTER (Configurations, Configurations.SolutionVendor = ConfigurationProviders.RecId)

    - Chaque enregistrement de la source de données **1Configurations** (référencées la table **ERSolutionTable**) est joint uniquement aux enregistrements **1Versions** un (référencés dans la table **ERSolutionVersionTable**) ayant la même valeur dans les champs **Solution** et **Recid**. Le type **Jointure interne** est utilisé pour cette jointure ainsi que les conditions suivantes pour mettre en correspondance les enregistrements :

    FILTER (ConfigurationVersions, ConfigurationVersions.Solution = ConfigurationProviders.’1Configurations’.RecId)

    - L’option **Exécuter** est configurée comme **Requête** ce qui signifie que cette source de données de jointure est exécutée au moment de l’exécution au niveau de base de données comme appel SQL direct.

    Pour joindre des enregistrements des sources de données représentant des tables d’application, vous pouvez spécifier des conditions de jointure en utilisant des paires de champs autres que ceux qui décrivent des relations AOA existant entre ces tables. Ce type de jointure peut être configuré pour s’exécuter au niveau de base de données.

6. Fermez la page.
7. Sélectionnez **Annuler**.
8. Dans l’arborescence de configurations, développez l’élément de modèle de données **Set2.Summary** :

    - La liaison **VersionsNumber: Integer = DetailsSummary.aggregated.VersionsNumber** indique que l’élément **Set2.Summary.VersionsNumber** est lié au champ d’agrégation **VersionsNumber** de la source de données **DetailsSummary** du type **GroupBy** configurée pour retourner le nombre d’enregistrements joints de la source de données **Détails** de type **Join**.
    - L’option d’emplacement **Exécution** est configurée comme **Requête** ce qui signifie que cette source de données **GroupBy** est exécutée au moment de l’exécution comme appel SQL direct au niveau de base de données. Ce comportement possible car la source de données de base **Détails** du type **Join** est configurée comme exécutée au niveau de base de données.

    ![Page des paramètres de source de données GROUPBY](./media/GER-JoinDS-Set2GroupByReview.PNG)

9. Fermez la page.
10. Sélectionnez **Annuler**.

### <a name="execute-er-format"></a><a name="executeERformat"></a> Exécuter le format ER

1. Accédez à Finance ou RCS dans la deuxième session de votre navigateur web à l’aide des mêmes informations d’identification et société que dans la première session.
2. Accédez à **Administration d’organisation \> États électroniques \> Configurations**.
3. Développez la configuration **Modèle pour apprendre les sources de données JOIN**.
4. Sélectionnez la configuration **Mise en forme pour apprendre les sources de données JOIN**.
5. Sélectionnez **Concepteur**.
6. Sélectionnez **Afficher les détails**.
7. Sélectionnez **Mappage**.
8. Sélectionnez **Développer/Réduire**.

    Ce format est conçu pour remplir un fichier texte généré avec une nouvelle ligne pour chaque version d’une configuration ER (souche **Version** ). Chaque ligne générée contient le nom d’un fournisseur de configuration possédant la configuration actuelle, le nom de la configuration et la version de la configuration séparés par un point-virgule. La ligne finale du fichier généré contiendra le numéro de versions détecté de configurations ER (souche **Synthèse** ).

    ![Page Concepteur de formats ER](./media/GER-JoinDS-FormatReview.PNG)

    Les sources de données **Données** et **Synthèse** sont utilisées pour remplir les détails de la version de configuration dans le fichier généré :

    - Les informations du modèle de données **Set1** sont utilisées lorsque vous sélectionnez **Non** pour la source de données **Sélecteur** au moment de l’exécution dans la page de la boîte de dialogue utilisateur en exécutant le format ER.
    - Les informations du modèle de données **Set2** sont utilisées lorsque vous sélectionnez **Oui** pour la source de données **Sélecteur** au moment de l’exécution dans la page de la boîte de dialogue utilisateur.

    ![Page Concepteur de formats ER](./media/GER-JoinDS-FormatMappingReview.PNG)

9. Sélectionnez **Exécuter**.
10. Dans la page de dialogue, sélectionnez **Non** dans le champ **Utiliser la source de données JOIN**.
11. Cliquez sur **OK**.
12. Vérifiez les fichiers générés.

    ![Page de boîte de dialogue utilisateur pour ER](./media/GER-JoinDS-Set1Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a>Analyser le suivi de l’exécution du format ER

1. Dans la première session de Finance ou RCS, sélectionnez **Concepteur**.
2. sélectionnez **Suivi des performances**.
3. Dans la grille **Suivi des performances**, sélectionnez l’enregistrement le plus élevé du dernier de l’exécution d’un format ER ayant utilisé le composant de mise en correspondance du modèle actuel.
4. Cliquez sur **OK**.

    Les statistiques d’exécution vous informent sur les appels en double des tables d’application :

    - **ERSolutionTable** a été appelé autant de fois que vous avez d’enregistrements de version de configuration dans la table **ERSolutionVersionTable**, tandis que le nombre de ce type d’appels peut être réduit parfois pour l’amélioration des performances.
    - **ERVendorTable** a été appelé deux fois pour chaque enregistrement de version de configuration détecté dans la table **ERSolutionVersionTable**, tandis que le nombre de ce type d’appels peut être réduit également.

    ![Page du concepteur de mise en correspondance des modèles ER](./media/GER-JoinDS-Set1Run2.PNG)

5. Fermez la page.

### <a name="execute-er-format"></a>Exécuter le format ER

1. Passez à votre onglet du navigateur web avec la deuxième session de Finance ou RCS.
2. Sélectionnez **Exécuter**.
3. Dans la page de dialogue, sélectionnez **Oui** dans le champ **Utiliser la source de données JOIN**.
4. Cliquez sur **OK**.
5. Vérifiez les fichiers générés.

    ![Page de boîte de dialogue utilisateur pour ER](./media/GER-JoinDS-Set2Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a><a name="analyze"></a> Analyser le suivi de l’exécution du format ER

1. Dans la première session de Finance ou RCS, sélectionnez **Concepteur**.
2. Sélectionnez **Suivi des performances**.
3. Dans la grille **Suivi des performances**, sélectionnez l’enregistrement le plus élevé représentant l’exécution d’un format ER la plus récente ayant utilisé le composant de mise en correspondance du modèle actuel.
4. Cliquez sur **OK**.

    Les statistiques vous informent sur les éléments suivants :

    - La base de données d’application a été appelée une fois pour obtenir des enregistrements auprès des tables **ERVendorTable**, **ERSolutionTable** et **ERSolutionVersionTable** pour accéder aux champs obligatoires.

    ![Page du concepteur de mise en correspondance des modèles ER](./media/GER-JoinDS-Set2Run2.PNG)

    - La base de données d’application a été appelée une fois pour calculer le nombre de versions de configuration utilisant des jointures ayant été configurées dans la source de données **Détails**.

    ![Page du concepteur de mise en correspondance des modèles ER](./media/GER-JoinDS-Set2Run3.PNG)

## <a name="limitations"></a>Limitations

Comme vous pouvez le voir dans l’exemple de cette rubrique, la source de données **JOIN** peut être construite à partir de plusieurs sources de données qui décrivent les ensembles de données individuels des enregistrements qui doivent finalement être joints. Vous pouvez configurer ces sources de données à l’aide de la fonction de l’ER intégré [FILTER](er-functions-list-filter.md). Lorsque vous configurez la source de données afin qu’elle soit appelée au-delà de la source de données **JOIN**, vous pouvez utiliser des plages de sociétés dans le cadre de la condition de sélection des données. La mise en œuvre initiale de la source de données **JOIN** ne prend pas en charge les sources de données de ce type. Par exemple, lorsque vous appelez une source de données basée sur un [FILTRE](er-functions-list-filter.md) dans le cadre de l’exécution d’une source de données **JOIN**, si la source de données appelée contient des plages de sociétés dans le cadre de la condition de sélection des données, une exception se produit.

Dans Microsoft Dynamics 365 Finance version 10.0.12 (août 2020), vous pouvez utiliser des plages de sociétés dans le cadre de la condition de sélection des données dans les sources de données basées sur le [FILTRE](er-functions-list-filter.md) qui sont appelées dans le cadre de l’exécution d’une source de données **JOIN**. En raison des limites de l’application configuratrice [query](../dev-ref/xpp-library-objects.md#query-object-model), les gammes d’entreprise ne sont prises en charge que pour la première source de données **JOIN**.

### <a name="example"></a>Exemple

Par exemple, vous devez effectuer un appel unique à la base de données d’application pour obtenir la liste des transactions de commerce extérieur de plusieurs sociétés et les détails de l’article en stock auquel il est fait référence dans ces transactions.

Dans ce cas, vous configurez les artefacts suivants dans votre mise en correspondances de modèles ER :

- La source de données racine **Intrastat** qui représente la table **Intrastat**.
- La source de données racine **Articles** qui représente la table **InventTable**.
- La source de données racine **Entreprises** qui renvoie la liste des sociétés (**DEMF** et **GBSI** dans cet exemple) où les transactions doivent être accessibles. Le code d’entreprise est disponible dans le champ **Companies.Code**.
- La source de données racine **X1** qui a l’expression `FILTER (Intrastat, VALUEIN(Intrastat.dataAreaId, Companies, Companies.Code))`. Dans le cadre de la condition de sélection des données, cette expression contient la définition des plages d’entreprises `VALUEIN(Intrastat.dataAreaId, Companies, Companies.Code)`.
- La source de données **X2** en tant qu’élément imbriqué de la source de données **X1**. Elle comprend l’expression `FILTER (Items, Items.ItemId = X1.ItemId)`.

Enfin, vous pouvez configurer une source de données **JOIN** où **X1** est la première source de données et **X2** est la deuxième source de données. Vous pouvez spécifier **Requête** comme l’option **Exécuter** pour forcer ER à exécuter cette source de données au niveau de la base de données en tant qu’appel SQL direct.

Lorsque la source de données configurée est exécutée pendant que l’exécution ER est [tracé](trace-execution-er-troubleshoot-perf.md), l’instruction suivante est affichée dans le concepteur de mise en correspondance des modèles ER dans le cadre de la trace de performance ER.

`SELECT ... FROM INTRASTAT T1 CROSS JOIN INVENTTABLE T2 WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF',N'GBSI') )) AND ((T2.PARTITION=?) AND (T2.ITEMID=T1.ITEMID AND (T2.DATAAREAID = T1.DATAAREAID) AND (T2.PARTITION = T1.PARTITION))) ORDER BY T1.DISPATCHID,T1.SEQNUM`

> [!NOTE]
> Une erreur se produit si vous exécutez une source de données **JOIN** qui a été configurée de sorte qu’elle contienne des conditions de sélection de données qui ont des plages de société pour des sources de données supplémentaires de l’exécution de la source de données **JOIN**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Concepteur de formule dans la gestion des états électroniques](general-electronic-reporting-formula-designer.md)

[Suivez l’exécution du format d’ER pour résoudre les problèmes de performances](trace-execution-er-troubleshoot-perf.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]