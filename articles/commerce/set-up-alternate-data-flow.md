---
title: Configurer un autre flux de données pour les recommandations
description: Cet article explique comment configurer un environnement à l’aide d’un autre flux de données pour fournir des données au service de recommandations.
author: bebeale
ms.date: 09/08/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: b507b9bb57c68aca9424b53f8ccc009efea733bc
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460161"
---
# <a name="set-up-an-alternate-dataflow-for-recommendations"></a>Configurer un autre flux de données pour les recommandations

[!include [banner](includes/banner.md)]

Cet article explique comment configurer un environnement à l’aide d’un autre flux de données pour fournir des données au service de recommandations.

## <a name="comparison-of-out-of-the-box-dataflow-with-alternate-dataflow"></a>Comparaison du flux de données prêt à l’emploi avec un flux de données alternatif

L’illustration suivante décrit le flux de données prêt à l’emploi dans un environnement.

![Flux de données prêt à l’emploi dans un environnement](media/reco-out-of-the-box-dataflow-2.png)

L’illustration suivante représente un autre flux de données, dans lequel la tâche par lots de synchronisation du magasin d’entités est remplacée par d’autres étapes de flux de données.

![Flux de données alternatif dans un environnement](media/reco-alternate-dataflow-2.png)

## <a name="assumptions"></a>Hypothèses

- Cet article suppose que vous avez déjà activé le service de recommandations pour votre environnement. Pour plus d’informations, voir [Activer les recommandations de produit](enable-product-recommendations.md).
- Lorsque vous travaillez avec des fichiers et des dossiers dans le compte de stockage Microsoft Azure Data Lake :

    - Vous pouvez utiliser l’interface du portail web Azure ou l’application Azure Storage Explorer.
    - Les points de départ pour utiliser les fichiers et les dossiers se trouvent dans le conteneur **dynamique365-financeandoperations** situé sous le dossier dont le nom correspond à l’URL de votre environnement.
    - Si le nom de votre environnement sandbox est **MyUAT**, l’URL de base de l’environnement est `myuat.sandbox.operations.dynamics.com`.
    - Si plusieurs environnements sont connectés au même compte de stockage, chaque environnement a son propre dossier racine.

## <a name="prerequisites"></a>Logiciels requis

Avant de pouvoir implémenter l’autre approche du flux de données, la procédure suivante doit être suivie.

### <a name="set-up-microsoft-power-platform"></a>Paramétrer Microsoft Power Platform

Pour configurer Microsoft Power Platform, suivez les instructions dans [Activer l’intégration Microsoft Power Platform](../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md).

### <a name="install-the-export-to-data-lake-add-in"></a>Installer le complément Exporter vers Data Lake

Pour installer le complément Exporter vers Data Lake, suivez les instructions de la section [Installer le complément Exporter vers Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

> [!NOTE]
> Notez les valeurs de configuration, car vous en aurez besoin pour certaines des étapes qui suivent.

### <a name="configure-tables-to-export-in-dynamics-365"></a>Configurer les tables à exporter dans Dynamics 365

La synchronisation des tables de Dynamics 365 vers Azure Data Lake Storage est gérée sur la page **Exporter vers Data Lake**. Étant donné que cette page n’a pas actuellement d’élément de menu, seuls les utilisateurs du rôle de sécurité **Administrateur système** peuvent l’ouvrir.

Pour configurer les tables à exporter dans Dynamics 365, procédez comme suit.

1. Pour ouvrir la page **Exporter vers Data Lake**, ajoutez la chaîne `?mi=DataFeedsDefinitionWorkspace` à l’URL de base de l’environnement, comme illustré dans l’exemple suivant :

    `https://<environment-URL>/?mi=DataFeedsDefinitionWorkspace`

1. Sur la page **Exporter vers Data Lake**, copiez les tableaux répertoriés dans la section [Liste des tables de cube RetailSales](#list-of-retailsales-cube-tables) de cet article.
1. Dans la colonne **Nom du système**, développez la liste des options de filtre.
1. Pour le type de filtre, sélectionnez **fait partie de**. Placez ensuite le curseur dans la zone de texte et collez la liste des tables que vous avez copiée à partir de la page **Exporter vers Data Lake**.
1. En bas de la liste des options de filtre, sélectionnez **Appliquer**.
1. Sélectionnez toutes les lignes de la grille, puis sélectionnez **Activer**.

> [!NOTE]
> Avant de passer à l’étape suivante, toutes les lignes doivent être mises à jour avec le statut **En cours d’exécution**. Résolvez les problèmes, le cas échéant.

### <a name="create-a-synapse-workspace"></a>Créer un espace de travail Synapse

Pour créer un espace de travail Synapse si vous n’en avez pas déjà un, suivez les instructions dans [Démarrage rapide : Créer un espace de travail Synapse](/azure/synapse-analytics/quickstart-create-workspace).

Pour que vos ressources Azure restent organisées, nous vous recommandons de regrouper le compte Data Lake Storage et l’espace de travail Synapse dans un groupe de ressources dans Azure. Vous pouvez réutiliser le compte de stockage que vous avez créé lors de l’installation du complément Exporter vers Data Lake.

## <a name="create-a-database-in-synapse-for-recommendation-data-processing"></a>Créer une base de données dans Synapse pour le traitement des données de recommandation

Utilisez l’application de console de l’utilitaire Common Data Model (CDMUtil_ConsoleApp) pour créer une base de données dans votre espace de travail Synapse et la remplir à partir des tables Common Data Model dans Data Lake Storage. Nous vous recommandons d’utiliser l’utilitaire Common Data Model avec votre base de données dans un environnement de développement, au cas où il y aurait des extensions.

> [!NOTE]
> Les étapes suivantes supposent qu’aucune donnée d’extension n’est ajoutée au cube RetailSales.

Pour créer une base de données dans Synapse, procédez comme suit.

1. Accédez à [Dynamics-365-FastTrack-Implementation-Assets GitHub](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Analytics/CDMUtilSolution#2-cdmutil-console-app), et suivez les étapes pour télécharger le fichier **CDMUtilConsoleApp.zip**.
1. Extrayez le fichier zip dans un dossier local.
1. Ouvrez le fichier **CDMUtil_ConsoleApp.dll.config** dans un éditeur de texte et mettez à jour les valeurs suivantes :

    1. Définissez la valeur **ID client** (ID client Azure).
    1. Définissez la valeur **Clé d’accès** (la clé d’accès pour le compte Data Lake Storage).

        1. Dans le portail Azure, ouvrez votre compte de stockage.
        1. Dans le menu à gauche de la page, sélectionnez **Clés d’accès**.
        1. En haut de la page, sélectionnez **Afficher les clés**.
        1. Sélectionnez le bouton Copier pour l’un des deux champs clés, puis collez la valeur entre guillemets doubles dans le fichier de configuration.

    1. Définissez la valeur **ManifestURL** sur l’URL de votre fichier **Tables.manifest.cdm.json** dans Azure Data Lake Storage. Pour obtenir l’URL, accédez au fichier dans le portail Azure, sélectionnez les points de suspension (**...**) sur le côté droit de la vue, puis sélectionnez **Propriétés**. L’URL est la première propriété qui s’affiche sur l’onglet **Aperçu**.
    1. Définissez la valeur **TargetDbConnectionString** sur la chaîne de connexion pour le pool SQL sans serveur intégré de votre espace de travail Synapse.

        1. Dans l’espace de travail Synapse, sélectionnez l’onglet **Gérer**.
        1. Dans le sous-menu, sélectionnez **Pools SQL**.
        1. Sélectionnez le nom **Intégré** pour voir les propriétés du pool.
        1. Dans la boîte de dialogue Propriétés, sélectionnez le type de connexion ADO.NET que vous souhaitez utiliser. Copiez ensuite la valeur de la chaîne de connexion et collez-la entre guillemets doubles dans le fichier de configuration.

        > [!NOTE]
        > Vous devez être autorisé à créer des bases de données. Pour plus de facilité d’utilisation, vous pouvez utiliser le compte administrateur **sqladminuser**.

    1. Décommentez le nœud **ProcessEntities** et définissez sa valeur sur **true** (par exemple`<add key="ProcessEntities" value ="true"/>`).

1. Enregistrez et fermez le fichier **CDMUtil_ConsoleApp.dll.config**.
1. Copiez le fichier **EntityList.json** vers le répertoire **/Manifest**.
1. Dans une fenêtre d’invite de commande, exécutez **cdmutil_consoleapp.exe**.

> [!NOTE]
> Lorsque vous examinez le résultat, il doit y avoir 35 entités/vues, au moins 75 tables et aucune erreur.

## <a name="prepare-the-data-lake-retailsales-aggregate-measurements-directory"></a>Préparer le répertoire Data Lake RetailSales Aggregate Measurements

### <a name="back-up-your-current-retailsales-cube-data-from-data-lake-storage"></a>Sauvegardez vos données de cube RetailSales actuelles à partir de Data Lake Storage

Le moyen le plus simple de sauvegarder les données actuelles de votre cube RetailSales consiste à renommer le répertoire **RetailSales** dans Data Lake Storage **RetailSales-backup** ou autre nom similaire. Cette méthode préserve les données existantes au cas où un dépannage serait nécessaire ultérieurement.

Le dossier du cube **/RetailSales** se trouve à l’emplacement suivant :

`<storage-account>/dynamics365-financeandoperations/<environment-url (for example, myuat.sandbox.operations.dynamics.com)>/AggregateMeasurements/RetailSales`

### <a name="create-a-new-retailsales-folder-and-upload-the-model-file"></a>Créer un dossier RetailSales et télécharger le fichier de modèle

Pour créer un nouveau répertoire **RetailSales** et télécharger le fichier **model.json** vers Data Lake Storage, procédez comme suit.

1. Créez un répertoire vide au même niveau que le répertoire précédent et nommez-le **RetailSales**.
1. Téléchargez le fichier **model.json** dans le nouveau répertoire.

## <a name="create-a-pipeline-to-copy-the-retailsales-cube-data"></a>Créer un pipeline pour copier les données du cube RetailSales

Le pipeline lira les vues du cube RetailSales et exportera les données vers des fichiers .csv dans Data Lake Storage.

Pour créer un pipeline pour copier les données du cube RetailSales, procédez comme suit.

1. Dans l’espace de travail Synapse, sélectionnez l’onglet **Intégrer**.
1. Sélectionnez le signe plus (**+**), puis sélectionnez **Importer à partir du modèle de pipeline**.
1. Téléchargez puis sélectionnez le [fichier ExportRetailSalesCubeViews.zip](https://aka.ms/reco-alternate-dataflow-files).
1. Sélectionnez votre service lié à la base de données SQL.
1. Sélectionnez le service lié à votre compte de stockage.
1. Ouvrez l’outil **Copier les données**, et changez la propriété **Chemin d’accès au dossier** sur **\<environment_name\>/...**.

### <a name="test-execution-of-the-pipeline"></a>Tester l’exécution du pipeline

Nous vous recommandons de tester le pipeline en utilisant une seule vue. La vue **RetailSales_RetailMediaTemplateView** fonctionne bien, car elle contient généralement moins de 10 lignes.

## <a name="schedule-the-pipeline-to-run-on-a-recurring-schedule"></a>Planifier le pipeline pour qu’il s’exécute selon une planification récurrente

Chaque fois que le pipeline s’exécute, une consommation Azure se produit. Nous vous recommandons de programmer les exécutions à des intervalles de 48 heures ou plus. Vous pouvez toujours exécuter le pipeline manuellement si vous devez synchroniser les données immédiatement. 
 
## <a name="table-list-for-synchronization-from-dynamics-365-to-data-lake-storage"></a>Liste des tableaux pour la synchronisation de Dynamics 365 vers Data Lake Storage

La liste de tables suivante est un sous-ensemble de toutes les tables requises pour l’ensemble du cube RetailSales. Seules 15 des vues du cube RetailSales sont utilisées par le service de recommandations, et la liste des tables requises a été filtrée en conséquence.

### <a name="list-of-retailsales-cube-tables"></a>Liste des tables de cube RetailSales

- BICalendarOffsets
- BIDateDimension
- BIDateDimensionValue
- Catalogue
- CatalogProduct
- CatalogProductCategory
- CustInvoiceJour
- CustInvoiceTrans
- CustTable
- DataArea
- DimensionAttributeValueCombination
- DimensionAttributeValueSet
- DirPartyTable
- EcoResCategory
- EcoResCategoryHierarchy
- EcoResCategoryHierarchyRole
- EcoResColor
- EcoResConfiguration
- EcoResProduct
- EcoResProductCategory
- EcoResProductTranslation
- EcoResSize
- EcoResStyle
- HcmWorker
- InventDim
- InventDimCombination
- InventItemGroup
- InventItemGroupItem
- InventItemSetupSupplyType
- InventTable
- InventTrans
- LogisticsAddressCountryRegion
- LogisticsAddressCountryRegionTranslation
- LogisticsLocation
- LogisticsPostalAddress
- OMHIERARCHYPURPOSE
- RetailAssortmentLookup
- RetailAssortmentLookupChannelGroup
- RetailChannelProfile
- RetailChannelProfileProperty
- RetailChannelTable
- RetailChannelTableExt
- RetailConnDatabaseProfile
- RetailCustInvoiceJourTable
- RetailCustTable
- RetailMediaTemplate
- RetailOfflineProfile
- RetailPeriodicDiscount
- RetailRecoListConfigurationParameters
- RetailSalesTaxOverrideGroup
- RetailSharedParameters
- RetailSpecialCategoryMember
- RetailTenderTypeCardTable
- RetailTenderTypeTable
- RetailTerminalTable
- RetailTmpProductMedia
- RetailTransactionDiscountTrans
- RetailTransactionPaymentTrans
- RetailTransactionPaymentTransExt
- RetailTransactionSalesTrans
- RetailTransactionSalesTransExt
- RetailTransactionTable
- SalesLine
- SalesTable
- SystemParameters
- RETAILCATALOGINTERNALORG
- RETAILGROUPMEMBERLINE
- RETAILINTERNALORGANIZATION
- RETAILSPECIALCATEGORYPRODUCT
- RETAILPRODUCTCATEGORY
- ECORESCONFIGURATION
- DIMENSIONATTRIBUTE
- DIMENSIONATTRIBUTEVALUESET
- DIMENSIONHIERARCHY
- DIMENSIONHIERARCHYINTEGRATION
- DIMENSIONHIERARCHYLEVEL
- DIMENSIONPARAMETER
- OMExplodedOrganizationSecurityGraph

### <a name="view-list-for-the-parameter-to-pass-to-the-synapse-pipeline"></a>Afficher la liste du paramètre à transmettre au pipeline Synapse

La liste suivante, séparée par des virgules, contient les vues de cube RetailSales sur lesquelles le pipeline effectuera une opération de « sélection ». Il copiera ensuite les résultats dans Data Lake Storage.

RetailSales_RetailAssortmentRulesView,RetailSales_RetailChannelNavigationHierarchiesView,RetailSales_RetailChannelNavigationHierarchyCatalogProductsView,RetailSales_RetailChannelNavigationHierarchyCategoryNodesView,RetailSales_RetailChannelNavigationHierarchyCategoryProductsView,RetailSales_RetailMediaBaseUrlChannelView,RetailSales_RetailMediaRelativeUrlProductView,RetailSales_RetailMediaTemplateView,RetailSales_RetailOptOutCustomersView,RetailSales_RetailProductCategory,RetailSales_RetailProductTransaction,RetailSales_RetailProductVariantDimensionsView,RetailSales_RetailRecoListConfigurationParametersView,RetailSales_RetailRecoListsSharedParametersView,RetailSales_RetailEcoResProductTranslation

> [!IMPORTANT]
> Le paramètre pipeline doit être une liste de noms de vue séparés par des virgules simples. Il ne doit pas y avoir d’espaces ni de sauts de ligne.

## <a name="environment-specific-fixes"></a>Correctifs spécifiques à l’environnement

### <a name="retailchannelview-fix"></a>Correctif RETAILCHANNELVIEW

La vue **RETAILCHANNELVIEW** contient un entier codé en dur qui représente une organisation de type « canal de vente au détail ». La valeur réelle du type peut changer d’un environnement à l’autre ou d’un client à l’autre.

```SQL
CREATE OR ALTER   VIEW [dbo].[RETAILCHANNELVIEW]
AS
SELECT T1.RECID AS RECID1,
       T1.STOREAREA AS STOREAREA,
       T1.OMOPERATINGUNITID AS OMOPERATINGUNITID,
       T1.DEFAULTCUSTACCOUNT AS DEFAULTCUSTOMER,
       T1.RETAILCHANNELID AS RETAILCHANNELID,
       T1.CHANNELTYPE AS CHANNELTYPE,
       T1.PARTITION AS PARTITION,
       T1.RECID AS RECID,
       T2.OMOPERATINGUNITNUMBER AS OMOPERATINGUNITNUMBER,
       T3.NAME AS NAME
FROM   dbo.RETAILCHANNELTABLE AS T1 CROSS JOIN dbo.DIRPARTYTABLE AS T2 CROSS JOIN dbo.DIRPARTYTABLE AS T3
WHERE  ((((T1.OMOPERATINGUNITID = T2.RECID)
          )
         AND ((T2.RECID = T3.RECID)
              ))
        AND T2.INSTANCERELATIONTYPE IN (8363));
```

Pour mettre à jour l’entier codé en dur, suivez ces étapes.

1. Dans Dynamics 365, recherchez la valeur **ChannelID** pour votre canal en ligne.
1. Dans une instance de SQL Server Management Studio (SSMS) qui est attachée à la base de données Synapse, exécutez la requête suivante.

    ```SQL
    select INSTANCERELATIONTYPE, NAME, NAMEALIAS, * from dbo.DIRPARTYTABLE where RECID IN (select OMOPERATINGUNITID from dbo.RETAILCHANNELTABLE where RETAILCHANNELID =     <channelID>)
    ```

1. Copiez la valeur de la première colonne (**INSTANCERELATIONTYPE**) et collez-le dans la définition de la vue.

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="pipeline-task-fails"></a>La tâche de pipeline échoue

Il devrait y avoir 15 exécutions de tâches de pipeline pour la tâche **CopyData**. Si une exécution échoue, vous devez valider que tous les objets SQL dépendants existent et que les requêtes s’exécutent. Le moyen le plus simple d’accéder à toutes les dépendances consiste à utiliser SSMS pour se connecter à la base de données. Vous pouvez ensuite sélectionner et maintenir (ou cliquer avec le bouton droit) une vue et sélectionner **Générer CRÉER dans une nouvelle fenêtre**.

Le message d’erreur peut inclure le texte suivant :

- Erreur : un échec s’est produit du côté « Source »
- Erreur lors de la gestion du fichier externe : « Nombre maximal d’erreurs ».
- /RetailSales/RetailSales_xxxxxx

#### <a name="example-scenario"></a>Exemple de scénario

Dans cet exemple, la tâche **RetailSales_RetailProductCategory** échoue et vous recevez une erreur « Nombre maximal d’erreurs ».

Pour résoudre l’erreur, procédez comme suit.

1. Ouvrez le fichier **EntityList.json** dans un éditeur de texte (par exemple, Visual Studio Code).
1. Recherchez la définition de vue pour **RetailSales_RetailProductCategory**.

    ```SQL
    CREATE  VIEW [dbo].[RetailSales_RetailProductCategory] AS SELECT 0 AS ROW_UNIQUEKEY ,CATEGORY AS CATEGORYID ,PRODUCT AS PRODUCTID ,PRODUCTNAME ,CATEGORYNAME     ,PARENTCATEGORY AS PARENTCATEGORYID ,PARTITION ,RECID FROM RetailProductCategoryView
    ```

1. Cette vue ne dépend que d’une seule autre vue : **RetailProductCategoryView** _. Recherchez la définition de vue pour _*RetailProductCategoryView**.

    ```SQL
    CREATE VIEW [DBO].[RETAILPRODUCTCATEGORYVIEW] AS SELECT T1.CATEGORY AS CATEGORY, T1.PRODUCT AS PRODUCT, T1.PARTITION AS PARTITION, T1.RECID AS RECID, T2.PRODUCTNAME AS PRODUCTNAME, T2.PARTITION AS PARTITION#2, T3.NAME AS CATEGORYNAME, T3.PARENTCATEGORY AS PARENTCATEGORY, T3.PARTITION AS PARTITION#3 FROM RETAILPRODUCTCATEGORY T1 CROSS JOIN ECORESPRODUCTTRANSLATIONS T2 CROSS JOIN RETAILCATEGORYEXPANDED T3 WHERE((( T1.PRODUCT = T2.PRODUCT) AND ( T1.PARTITION = T2.PARTITION)) AND (( T1.CATEGORY = T3.RECID) AND ( T1.PARTITION = T3.PARTITION)))
    ```

1. Cette vue dépend de trois autres vues : **RETAILPRODUCTCATEGORY**, **ECORESPRODUCTTRANSLATIONS** et **RETAILCATEGORYEXPANDED**. Trouvez la définition de chacune de ces vues et répertoriez ses dépendances. Continuez jusqu’à ce que vous trouviez toutes les vues dépendantes.

    Voici la liste complète dans l’ordre de l’arborescence des dépendances. Treize vues doivent être validées.

    - RetailSales_RetailProductCategory

        - RetailProductCategoryView

            - RETAILPRODUCTCATEGORY

                - ECORESPRODUCTCATEGORY
                - ECORESCATEGORYHIERARCHYROLE
                - RETAILSPECIALCATEGORYPRODUCT

                    - ECORESPRODUCT
                    - RETAILGROUPMEMBERLINE
                    - RETAILSPECIALCATEGORYMEMBER

            - ECORESPRODUCTTRANSLATIONS

                - ECORESPRODUCT
                - ECORESPRODUCTTRANSLATION
                - SYSTEMPARAMETERS

            - RETAILCATEGORYEXPANDED

                - ECORESCATEGORY
                - ECORESCATEGORYHIERARCHYROLE

1. Dans Excel, créez les 13 instructions suivantes **select count(\*) from \<view_name\>**. Exécutez ces instructions dans SSMS et envoyez les résultats au format texte. Faites ensuite défiler les résultats pour voir si l’une des vues a échoué. L’erreur initiale suggère qu’au moins une des vues échouera.

    ```SQL
    select count(*) from RetailProductCategoryView
    select count(*) from RETAILPRODUCTCATEGORY
    select count(*) from ECORESPRODUCTCATEGORY
    select count(*) from ECORESCATEGORYHIERARCHYROLE
    select count(*) from RETAILSPECIALCATEGORYPRODUCT
    select count(*) from ECORESPRODUCT
    select count(*) from RETAILGROUPMEMBERLINE
    select count(*) from RETAILSPECIALCATEGORYMEMBER
    select count(*) from ECORESPRODUCTTRANSLATIONS
    select count(*) from ECORESPRODUCTTRANSLATION
    select count(*) from SYSTEMPARAMETERS
    select count(*) from RETAILCATEGORYEXPANDED
    select count(*) from ECORESCATEGORY
    ```

1. Une façon de valider ce que vous regardez est de créer une vue dépendante de la racine pour générer la définition de la vue dans SSMS. Vérifiez ensuite qu’il existe une colonne de fichier Azure Data Lake nommée **r.filepath**. La présence de cette colonne indique que la vue que vous inspectez lit les données de Data Lake Storage.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des recommandations produit](product-recommendations.md)

[Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce](enable-adls-environment.md)

[Activer les recommandations personnalisées](personalized-recommendations.md)

[Activer les recommandations « acheter des aspects similaires »](shop-similar-looks.md)

[Désactiver les recommandations personnalisées](personalization-gdpr.md)

[Ajouter des recommandations produit sur PDV](product.md)

[Ajouter des recommandations à l’écran de transaction](add-recommendations-control-pos-screen.md)

[Ajuster des résultats des recommandations AI-ML](modify-product-recommendation-results.md)

[Créer manuellement des recommandations sélectionnées](create-editorial-recommendation-lists.md)

[Créer des recommandations avec des données de démonstration](product-recommendations-demo-data.md)

[FAQ sur les recommandations produit](faq-recommendations.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
