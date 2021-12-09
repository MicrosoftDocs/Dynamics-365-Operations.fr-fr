---
title: Commerce Analytics (version préliminaire)
description: Cette rubrique explique comment installer et utiliser la fonction d’analyse dans Microsoft Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 11/23/2021
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2021-11-12
ms.openlocfilehash: 8cfe2af756315b5be3eb22d99376a96166fffc52
ms.sourcegitcommit: f9fca3d55b47e615e5ef64669dab184e057ec234
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/23/2021
ms.locfileid: "7862771"
---
# <a name="commerce-analytics-preview"></a>Commerce Analytics (version préliminaire)

[!include [banner](includes/banner.md)]

Cette rubrique explique comment installer la fonction d’analyse Commerce Analytics (version préliminaire) incluse dans Microsoft Dynamics 365 Commerce.

## <a name="commerce-analytics-preview-live-demo"></a>Démo en direct de Commerce Analytics (version préliminaire)

Vous pouvez effectuer une [démo en direct de Commerce Analytics (version préliminaire)](https://aka.ms/CommerceAnalyticsDemo).

![Commerce Analytics (version préliminaire) Résumé](media/CommerceAnalytics_Summary.png)
![Commerce Analytics (version préliminaire) Paiements](media/CommerceAnalytics_Payments.png)
![Commerce Analytics (version préliminaire) Activité Web](media/CommerceAnalytics_WebActivity.png)


## <a name="commerce-analytics-preview-system-architecture"></a>Commerce Analytics (version préliminaire) Architecture du système

### <a name="key-components"></a>Composants principaux

Commerce Analytics (version préliminaire) comprend les composants clés suivants :

- Rapports Power BI interactifs et prêts à l’emploi
- Vues SQL dans Azure Synapse Analytics
- Données d’entité et d’ontologie dans Azure Data Lake
- Données brutes dans Data Lake

![Composants clés de l’architecture du système Commerce Analytics](media/CommerceAnalyticsArchitecture_v2.png)

### <a name="data-flow"></a>Flux de données

#### <a name="step-1-data-generation"></a>Étape 1 : génération de données

Les données proviennent soit de données transactionnelles, soit de données comportementales provenant de l’une des sources suivantes :

- Un collaborateur du centre d’appels utilise le client Commerce HQ pour traiter les commandes client.
- Un caissier au point de vente (POS) traite les transactions de vente.
- Les ventes sont créées dans des applications personnalisées à l’aide du commerce headless (Commerce Scale Unit).
- Un acheteur e-commerce parcourt votre site Web de commerce électronique.
- Un client e-commerce passe une commande sur votre site Web e-commerce.
- Les données sont produites par d’autres systèmes, tels que Dynamics 365 Connected Spaces.

#### <a name="step-2-ingestion-and-pre-processing"></a>Étape 2 : Ingestion et pré-traitement

Les données transactionnelles sont transmises à Commerce HQ soit directement (dans le cas des commandes saisies directement dans le client Commerce HQ) soit via Commerce Scale Unit (dans le cas des commandes saisies au point de vente, dans le commerce électronique ou clients qui utilisent le commerce headless).

La fonctionnalité Exporter vers Data Lake est ensuite utilisée pour copier les données transactionnelles dans votre lac de données en tant que données brutes. Dans le lac de données, les données brutes sont stockées dans le dossier Tables.

Les données d’activité Web d’e-commerce sont envoyées directement au lac de données. Les données produites par d’autres systèmes, tels que Dynamics 365 Connected Spaces, sont envoyées directement au lac de données par ces systèmes.

#### <a name="step-3-transformation-and-aggregation"></a>Étape 3 : Transformation et agrégation

Une fois les données brutes dans votre lac de données, le service Commerce Analytics les lit, les transforme, les agrège et les réécrit dans le lac de données sous la forme d’entités logiques (dans le dossier Entités) et de métriques agrégées (dans le dossier Ontologies).

#### <a name="step-4-querying"></a>Étape 4 : Interrogation

Azure Synapse Analytics est utilisée pour interroger les données de votre lac de données via une interface Transact-SQL (T-SQL). Cette interface comprend des vues SQL. Les vues SQL permettent l’interrogation fédérée des données dans le lac de données, soit directement via un client T-SQL (pour l’analyse ad-hoc) soit via un outil de visualisation tel que Power BI.

#### <a name="step-5-modeling-and-serving"></a>Étape 5 : Modélisation et service

Les données interrogées par Azure Synapse Analytics passent dans le modèle sémantique de Power BI. Selon le type de données, elles sont soit importées périodiquement en mémoire dans Power BI ou directement interrogées au moment de l’exécution.

Enfin, les données sont rendues dans les visuels Power BI, afin que les utilisateurs puissent les voir et interagir avec elles.

## <a name="commerce-analytics-preview-functional-overview"></a>Présentation fonctionnelle de la fonction d’analyse dans Commerce (version préliminaire)

### <a name="summary"></a>Résumé

L’application modèle Commerce Analytics comprend les pages de rapport principales suivantes :

1. [Filtres de premier niveau](#TopLevelFilters)
2. [Produits](#ProductsPage)
3. [Clients](#CustomersPage)
4. [Canaux](#ChannelsPage)
5. [Ventes](#SalesPage)
6. [Marges](#MarginsPage)
7. [Retours](#ReturnsPage)
8. [Remises](#DiscountsPage)
9. [Paiements](#PaymentsPage)
10. [Clients](#CustomersPage)
11. [Comparaison](#ComparisonPage)
12. [Activité Web](#WebActivityPage)
13. [Activité Web - Filtre de premier niveau](#WebActivityTopLevelFilters)

####  <a name="top-level-filters"></a><a name="TopLevelFilters"></a> Filtres de premier niveau

- Paramètres de date

    - Année
    - Trimestre
    - Mois
    - Semaine
    - Jour

- Paramètres du canal

    - Entité juridique
    - Type de canal
    - Type de client
    - Type de vente
    - Canal
    - Hiérarchie d’organisation

- Paramètres du produit

    - Hiérarchie de catégories
    - Catégorie

####  <a name="products"></a><a name="ProductsPage"></a> Produits

- Vente
- Marge
- Retours

####  <a name="customers"></a><a name="CustomersPage"></a> Clients

- Vente
- Marge
- Retours

#### <a name="channels"></a><a name="ChannelsPage"></a> Canaux

- Vente
- Marge
- Retours

### <a name="sales"></a>Vente <a name="SalesPage"></a>

- Par emplacement de livraison
- Par canal/magasin/terminal
- Par employé
- Par date
- Par heure
- Par catégorie de produit

### <a name="margins"></a><a name="MarginsPage"></a> Marges

- Par emplacement de livraison
- Par produit
- Par date

### <a name="returns"></a><a name="ReturnsPage"></a> Retours

- Retour par montant

    - Par magasin
    - Par produit
    - Par date

- Retour par transaction

    - Par magasin
    - Par produit
    - Par date

### <a name="discounts"></a><a name="DiscountsPage"></a> Remises

- Par magasin
- Par produit
- Par date
- Décomposition

    - Entité juridique
    - Magasin
    - Type de remise
    - Nom de la remise
    - Produit

### <a name="payments"></a><a name="PaymentsPage"></a> Paiements

- Par canal/terminal
- Par type/mode de paiement
- Par date
- Décomposition

    - Entité juridique
    - Type de canal
    - Magasin
    - Terminal
    - Mode de règlement

### <a name="customers"></a><a name="CustomersPage"></a> Clients

- Lifetime Value (LTV)

    La LTV est calculée sur la base du montant total qu’un client dépense dans tous les canaux de vente Dynamics 365 Commerce (y compris les points de vente, le commerce électronique et le centre d’appels).

- Récence

    La récence est calculée en fonction du nombre de jours écoulés depuis le dernier engagement transactionnel d’un client auprès de l’organisation. Actuellement, la récence ne prend pas en compte les signaux d’engagement non transactionnels, tels que l’activité de navigation dans e-commerce.

- Fréquence

    La fréquence est calculée en fonction du dernier engagement transactionnel d’un client auprès de l’organisation. Actuellement, la fréquence ne prend pas en compte les signaux d’engagement non transactionnels, tels que l’activité de navigation dans e-commerce.

- Durée de la relation

    La durée de la relation est calculée en fonction du nombre de jours depuis la création de la fiche client dans le système.

- Nombre de transactions

### <a name="comparison"></a><a name="ComparisonPage"></a> Comparaison

- Comparaison des produits par période

    - Ventes et différence de ventes
    - Marge et différence de marge

- Client par période

    - Ventes et différence de ventes
    - Marge et différence de marge

### <a name="web-activity"></a><a name="WebActivityPage"></a> Activité Web

#### <a name="top-level-filters"></a><a name="WebActivityTopLevelFilters"></a> Filtres de premier niveau

- Plage de dates
- Type de canal
- Canal
- Hiérarchie de catégories

#### <a name="acquisitions"></a>Acquisitions

- Affichages des pages

    - Par pays ou région
    - Par produit
    - Par statut d’utilisateur connecté
    - Par date

- Commandes e-commerce
- Taux de conversion

    - Par date

- Entonnoir de conversion

    - Affichage de la page par type de page (page d’accueil, page de catégorie ou page de détails du produit)
    - Ajouter au panier
    - Paiement
    - Achat

#### <a name="sessions"></a>Sessions

Une session est un épisode de la visite d’un utilisateur sur votre site e-commerce. Une session est considérée comme terminée après 30 minutes d’inactivité ou 24 heures d’utilisation active.

- Par pays ou région
- Par origine (référent externe)
- Par statut d’utilisateur connecté
- Nombre de sessions

    - Par date
    - Par page consultée

- Commande par session

    - Par date

- Taux de rebond de session

    Un rebond de session est une session où un utilisateur quitte immédiatement après avoir visité votre site Web e-commerce. Pour plus d’informations, voir [Taux de rebond](https://en.wikipedia.org/wiki/Bounce_rate).

- Clics par session

#### <a name="visitors"></a>Visiteurs

Un visiteur anonyme sur votre site de commerce électronique est identifié de manière unique en fonction du navigateur spécifique et de l’appareil spécifique que l’utilisateur utilise. Commerce Analytics ne suit pas les visiteurs anonymes sur différents navigateurs ou appareils. Un visiteur anonyme qui utilise le même navigateur sur le même appareil est identifié de manière unique sur plusieurs sessions utilisateur, jusqu’à ce que les données mises en cache du navigateur soient effacées ou qu’une période (généralement 12 mois) s’écoule, selon la première éventualité.

Si les visiteurs parcourent votre site d’e-commerce alors qu’ils sont connectés, Commerce Analytics peut fournir des informations supplémentaires à leur sujet. Ces informations sont basées sur la relation existante que votre organisation entretient avec les visiteurs à la suite de leurs achats précédents dans tous les canaux de vente Dynamics 365 Commerce (y compris les points de vente, l’e-commerce et le centre d’appels). Les informations supplémentaires incluent la récence, la durée de la relation, la valeur vie client et les données de fréquence.

- Marge des visiteurs
- Commandes moyennes des visiteurs
- Ventes moyennes des visiteurs
- Nombre de visiteurs du commerce électronique

    - Par date
    - Par emplacement

        Actuellement, Commerce Analytics ne peut fournir qu’une granularité au niveau du pays/de la région pour les informations sur l’emplacement des visiteurs du commerce électronique.

    - Par récence

        La récence est calculée en fonction du nombre de jours écoulés depuis le dernier engagement transactionnel d’un client auprès de l’organisation. Actuellement, la récence ne prend pas en compte les signaux d’engagement non transactionnels, tels que l’activité de navigation dans e-commerce.

    - Par durée de la relation

        La durée de la relation est calculée en fonction du nombre de jours depuis la création de la fiche client dans le système.

    - Par Valeur Vie Client

        La LTV est calculée sur la base du montant total qu’un client dépense dans tous les canaux de vente Dynamics 365 Commerce (y compris les points de vente, le commerce électronique et le centre d’appels).

    - Par fréquence

        La fréquence est calculée en fonction du dernier engagement transactionnel d’un client auprès de l’organisation. Actuellement, la fréquence ne prend pas en compte les signaux d’engagement non transactionnels, tels que l’activité de navigation dans e-commerce.

#### <a name="impressions"></a>Impressions

Une impression est une vue unique d’un visuel de produit par un visiteur e-commerce. Par exemple, un visiteur e-commerce accède à la page d’accueil de votre site Web e-commerce et voit un tapis de yoga dans un module de liste **Meilleures ventes**. Le visiteur voit ensuite le même tapis de yoga dans un module de liste **Nos choix pour vous**. Dans ce cas, il y a deux impressions de produit. 

Actuellement, les impressions sont suivies dans les surfaces suivantes :

- Les listes (par exemple, **Recommandé**, **Meilleures ventes**, **Nos choix pour vous** et **Tendances**)
- Module Panier
- Conteneur de résultats de recherche
- Conteneur de résultats de recherche par catégorie

Actuellement, les produits affichés dans un module de carrousel ou dans des visuels personnalisés ne sont pas pris en compte dans les indicateurs liés aux impressions.

La page **Rapport d’impression** inclut les mesures suivantes :

- Nombre d’impressions

    - Par type de page et module

        Le type de page est le type de page générique qui est défini pour chaque page de votre site e-commerce. Le type de module est le type de module visuel e-commerce dans lequel le produit est affiché.

        Pour afficher les impressions par module, vous devrez peut-être explorer les visuels de la page et du module.

    - Par produit
    - Par statut d’utilisateur connecté
    - Par date

- Nombre de clics par impression

    Un clic d’impression se produit lorsqu’un visiteur du commerce électronique sélectionne un visuel de produit. En règle générale, le visiteur est ensuite dirigé vers la page de détails du produit pour le produit.

- Taux de clic par impression (CTR)

    Le CTR est calculé comme le nombre total de clics sur impression divisé par le nombre total d’impressions.

## <a name="commerce-analytics-preview-installation"></a>Installation de Commerce Analytics (version préliminaire)

> [!NOTE]
> Commerce Analytics (version préliminaire) est disponible en version préliminaire aux États-Unis, au Canada, au Royaume-Uni, en Europe, en Asie du Sud-Est, en Asie de l’Est, en Australie et au Japon. Si votre environnement Finance and Operations se trouve dans l’une de ces régions, vous pouvez activer cette fonctionnalité dans votre environnement en utilisant Microsoft Dynamics Lifecycle Services (LCS). Avant de pouvoir utiliser cette fonction, consultez [Configurer l’exportation vers Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

### <a name="enable-and-configure-commerce-analytics-preview"></a><a name="enableCommerceAnalytics"></a>Activer et configurer Commerce Analytics (version préliminaire)

Pour installer Commerce Analytics (version préliminaire), vous devez disposer des autorisations pour créer des ressources dans un abonnement Azure. Vous devez également disposer des autorisations pour installer des compléments dans LCS. Voici une présentation de ces étapes :

1. [Soumettre le formulaire d’admission Aperçu pour Commerce Analytics (version préliminaire)](#joinPreview).
2. [Activer et configurer Exporter vers Data Lake](#enableExportToDataLake).
3. [Activer et configurer le module complémentaire Commerce Analytics (version préliminaire)](#enableCommerceAnalyticsAddin).
4. [Générer un jeton de signature d’accès partagé (SAS) pour votre compte de stockage](#getSASToken).
5. [Téléchargez les scripts de déploiement pour les vues Azure Synapse](#downloadSynapseDeploymentScripts).
6. [Installer et configurer Azure Synapse workspace](#configureAzureSynapse).
7. [Installer l’application du modèle Power BI](#powerbi).

### <a name="submit-the-preview-intake-form-for-commerce-analytics-preview"></a><a name="joinPreview"></a>Soumettre le formulaire d’admission Aperçu pour Commerce Analytics (version préliminaire)

Soumettre le [formulaire d’admission Aperçu pour Commerce Analytics (version préliminaire)](https://forms.office.com/r/vW5VLJGXZ2). Prévoyez jusqu’à trois jours ouvrables pour que le formulaire soit traité. Après son traitement, un e-mail de confirmation sera envoyé à l’adresse e-mail que vous avez fournie dans le formulaire.

### <a name="enable-and-configure-export-to-data-lake"></a><a name="enableExportToDataLake"></a>Activer et configurer Exporter vers Data Lake

Commerce Analytics (version préliminaire) s’appuie sur la fonctionnalité Exporter vers Data Lake pour exporter les données Commerce HQ vers Data Lake et conserver les données à jour. Avant de configurer Commerce Analytics (version préliminaire), activez et configurez Exporter vers Data Lake en suivant les étapes décrites dans [Configurer l’exportation vers Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

Pendant que vous configurez Exporter vers Data Lake, notez les informations suivantes, car vous devrez les saisir ultérieurement :

- <a name="keyVault"></a>Le nom DNS (Domain Name System) du coffre de clés et les noms secrets où vous stockez l’ID d’application et le secret d’application. Pour plus d’informations, voir [Ajouter des secrets au coffre de clés](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#addsecrets).
- <a name="storageAccount"></a>Nom du compte de stockage pour l’instance Data Lake. Pour plus d’informations, voir [Créer un compte Data Lake Storage (Gen2) dans votre abonnement](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createsubscription).

### <a name="enable-and-configure-the-commerce-analytics-preview-add-in"></a><a name="enableCommerceAnalyticsAddin"></a>Activer et configurer le module complémentaire Commerce Analytics (version préliminaire)

Pour installer le module complémentaire Commerce Analytics (version préliminaire) dans LCS, vous devez être un administrateur d’environnement dans LCS pour l’environnement que vous prévoyez d’utiliser.

Pour installer et configurer le module complémentaire Commerce Analytics (version préliminaire), procédez comme suit.

1. Connectez-vous à [LCS](https://lcs.dynamics.com/), et accédez à votre environnement.
2. Sur la page **Environnement**, sur l’onglet **Compléments d’environnement**, sélectionnez **Installer un nouveau complément**.
3. Dans la boîte de dialogue, sélectionnez **Commerce Analytics (version préliminaire)**.

    Si **Commerce Analytics (version préliminaire)** n’est pas répertorié, assurez-vous d’avoir rejoint le programme Insider.

4. Entrez les informations suivantes dans la boîte de dialogue **Complément d’installation** :

    | Informations | Source | Exemple de valeur |
    |---|---|---|
    | ID locataire Azure AD pour votre environnement | Connectez-vous au [portail Azure](https://portal.azure.com/), et ouvrez le service **Azure Active Directory**. Ensuite, ouvrez la page **Propriétés** et copiez la valeur dans le champ **ID de répertoire**. | 72f988bf-0000-0000-00000-2d7cd011db47 |
    | Nom DNS de votre coffre de clés | Entrez le [nom DNS](#keyVault) de votre coffre de clés. Vous avez dû noter cette valeur dans la section précédente. | `https://contosod365datafeedpoc.vault.azure.net/` |
    | Secret qui contient l’ID d’application | Entrez le [nom secret qui stocke l’ID de l’application](#keyVault). Vous avez dû noter cette valeur dans la section précédente. | app-id |
    | Secret qui contient le secret d’application | Entrez le [nom secret qui stocke le secret de l’application](#keyVault). Vous avez dû noter cette valeur dans la section précédente. | app-secret |

5. Acceptez les termes de l’offre en cochant la case, puis sélectionnez **Installer**.

    Le système installe et configure le complément Commerce Analytics (version préliminaire) pour l’environnement. Ce processus peut prendre quelques minutes. Une fois terminé, **Commerce Analytics (version préliminaire)** doit être répertorié sur la page **Environnement**, et le statut doit être **Installé**.

### <a name="generate-a-sas-token-for-your-storage-account"></a><a name="getSASToken"></a>Générer un jeton SAS pour votre compte de stockage

Un jeton SAS permet à des entités externes d’accéder à votre compte de stockage et de disposer d’un ensemble spécifique de privilèges pour une durée limitée. Azure Synapse utilisera le jeton SAS pour accéder aux données sous-jacentes dans Data Lake.

> [!NOTE]
> En raison d’une limitation connue de Commerce Analytics (version préliminaire), l’instance Azure Synapse perdra l’accès au lac de données lorsque le jeton SAS expirera. Par conséquent, lorsque vous générez le jeton SAS, vous devez définir la date d’expiration maximale autorisée par les politiques de sécurité de votre organisation.

Pour générer un jeton SAS, procédez comme suit.

1. Dans le portail Azure, accédez au [compte de stockage](#storageAccount) que vous avez créé lors de la configuration de l’exportation vers Data Lake.
2. Dans le volet de gauche, sous le compte de stockage, sélectionnez **Signature d’accès partagé**.
3. Sur la page **Options SAS**, définissez les champs suivants :

    | Champ | Valeur  |
    |---|---|
    | Services autorisés | Sélectionnez **Blob**. |
    | Types de ressources autorisées | Sélectionnez **Service**, **Conteneur** et **Objet**. |
    | Autorisations autorisées | Sélectionnez **Lire**, **Écrire**, **Supprimer**, **Répertorier**, **Ajouter** et **Créer**. |
    | Autorisations de gestion des versions d’objets blob | Sélectionnez **Permet la suppression de versions**. |
    | Date/heure de début de la date d’expiration | Définissez une date et une heure de début et de fin pour le jeton SAS, le cas échéant. |
    | Adresses IP autorisées | Laissez ce champ vide. |
    | Protocoles autorisés | Sélectionnez **HTTPS uniquement**. |
    | Niveau d’acheminement préféré | Sélectionnez **De base (par défaut)**. |
    | Clé de signature | Sélectionnez **key1** ou **key2**, le cas échéant. |

4. Sélectionnez **Générer SAS et chaîne de connexion**.
5. Copiez la valeur dans le champ **Jeton SAS** et collez-le dans un éditeur de texte tel que le Bloc-notes.

### <a name="download-the-deployment-scripts-for-azure-synapse-views"></a><a name="downloadSynapseDeploymentScripts"></a>Télécharger les scripts de déploiement pour les vues Azure Synapse

Pour créer et publier les vues requises dans Azure Synapse workspace, vous devez exécuter un ensemble de scripts. Procédez comme suit pour télécharger les scripts :

1. Sur GitHub, allez dans le référentiel [microsoft/Dynamics365Commerce.Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions).
2. Téléchargez les scripts sur votre ordinateur local en clonant le référentiel ou en le téléchargeant sous forme de fichier zip.

### <a name="install-and-configure-an-azure-synapse-workspace"></a><a name="configureAzureSynapse"></a>Installer et configurer Azure Synapse workspace

Pour installer et configurer Azure Synapse workspace, procédez comme suit :

1. Installez Azure Synapse workspace dans votre abonnement Azure. Pour plus d’informations, voir [Démarrage rapide : créer un espace de travail Synapse](/azure/synapse-analytics/quickstart-create-workspace).
2. Dans le Bloc-notes ou un autre éditeur de texte, ouvrez le script **SetupSynapse.sql** à partir du dossier de votre ordinateur local dans lequel vous avez cloné ou téléchargé le référentiel Dynamics365Commerce.Solutions dans la section précédente. Le fichier de script se trouvera dans le dossier /Pipeline/CommerceAnalyticsSynapse/. Dans le script, remplacez le texte de l’espace réservé de données par des valeurs comme indiqué dans le tableau suivant.

    | Texte d’espace réservé | Valeur de remplacement |
    |---|---|
    | placeholder_storageaccount | Nom du [compte de stockage](#storageAccount) que vous avez créé lors de la configuration de l’exportation vers Data Lake. |
    | <a name="phContainer"></a>placeholder_container | Nom du conteneur de stockage qui a été créé dans votre instance Data Lake après avoir installé avec succès le complément Exporter vers Data Lake dans LCS. Pour obtenir le nom du conteneur, vous devez utiliser l’Explorateur Stockage dans le portail Azure pour parcourir votre compte de stockage. |
    | placeholder_sastoken | [Jeton SAS](#getSASToken) que vous avez généré. Assurez-vous de supprimer le point d’interrogation (**?**) du début de la valeur du jeton SAS. |
    | <a name="phUserPwd"></a>placeholder_password | Mot de passe fort de votre choix. Notez ce mot de passe. Il sera défini comme mot de passe pour le nouveau compte **reportreadonlyuser** créé par le script. N’entrez **pas** le mot de passe du compte **sqladminuser**. |

3. Copiez le contenu mis à jour du fichier de script.
4. Dans le portail Azure, accédez au nouvel Azure Synapse workspace. Sur la page **Vue d’ensemble**, sélectionnez **Ouvrir Synapse Studio**.
5. Dans Synapse Studio, sélectionnez **Nouveau \> Script SQL**, et collez le contenu du fichier de script dans l’éditeur de script SQL.
6. Veillez à ce que le champ **Utiliser la base de données** soit défini sur **principale**.
7. Sélectionnez **Exécuter**, et attendez la fin de l’exécution du script. L’exécution réussie du script créera la base de données pour Commerce Analytics, les informations d’identification pour accéder au lac de données et un compte d’utilisateur en lecture seule que Power BI utilisera pour se connecter à l’instance Azure Synapse.
8. Sur votre ordinateur local, ouvrez Windows PowerShell en mode administrateur et accédez au dossier /Pipeline/CommerceAnalyticsSynapse/ sous le dossier dans lequel vous avez cloné ou téléchargé le référentiel Dynamics365Commerce.Solutions.
9. Configurez la stratégie d’exécution de Windows PowerShell en exécutant la commande suivante.

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
    ```

10. Si le module SQL Server PowerShell n’est pas déjà installé, installez-le en exécutant la commande suivante.

    ```powershell
    Install-Module sqlserver
    ```

    > [!NOTE]
    > Lors de l’installation du module, vous serez peut-être invité à installer le fournisseur NuGet. Dans ce cas, sélectionnez **Oui** pour installer le fournisseur NuGet. Vous pouvez également être invité à confirmer que vous installez des modules à partir d’un référentiel non fiable. Dans ce cas, sélectionnez **Oui** pour continuer l’installation. Vous pouvez éventuellement exécuter le cmdlet **Set-PSRepository** pour faire confiance au référentiel **PSGallery**.

11. Publiez les vue Azure Synapse en exécutant la commande suivante.

    ```powershell
    .\PublishSynapseViews.ps1 -serverName SERVER_NAME -password PASSWORD -storageAccount STORAGE_ACCOUNT -containerName CONTAINER_NAME -datarootpath DATA_ROOT_PATH
    ```

    Lorsque vous exécutez cette commande, remplacez les valeurs de l’espace réservé de données comme indiqué dans le tableau suivant.

    | Valeur de l’espace réservé | Valeur de remplacement |
    |---|---|
    | SERVER_NAME | Nom du point de terminaison Azure Synapse Serverless SQL. Vous pouvez obtenir cette valeur à partir de la page **Vue d’ensemble** d'Azure Synapse workspace dans le portail Azure. |
    | PASSWORD | Le mot de passe pour le compte **sqladminuser**. |
    | STORAGE_ACCOUNT | Nom du compte de stockage pour Data Lake. |
    | CONTAINER_NAME | Nom du conteneur qui a été créé par la fonctionnalité Exporter vers Data Lake. Ce conteneur est le même conteneur que celui spécifié comme valeur [placeholder_container](#phContainer) à l’étape 2. |
    | DATA_ROOT_PATH | Le nom du dossier sous le conteneur qui contient toutes les données. |

    > [!NOTE]
    > Vous pouvez trouver le nom du compte de stockage, le nom du conteneur et le chemin d’accès à la racine des données à l’aide du navigateur Azure Storage et de votre compte de stockage Data Lake dans le portail Azure.

12. Attendez la fin de l’exécution du script. Une exécution réussie du script créera des vues SQL dans l’instance Azure Synapse Serverless SQL.

### <a name="install-the-power-bi-template-app"></a><a name="powerbi"></a>Installer l’application du modèle Power BI

Pour installer l’application du modèle Power BI pour Commerce Analytics (version préliminaire), procédez comme suit.

1. Connectez-vous au [portail Power BI](https://powerbi.microsoft.com/) en utilisant l’ID de votre organisation.
2. Installez l’application du modèle Commerce Analytics (version préliminaire) Power BI en allant sur [https://aka.ms/cdireport-installapp](https://aka.ms/cdireport-installapp). Vous recevrez peut-être un avertissement indiquant que l’application n’est pas répertoriée sur AppSource. Sélectionnez **Installer**.
3. Si vous installez l’application pour la première fois, passez à l’étape 5. Si vous avez déjà installé cette application, les options suivantes pour la mise à jour de l’application s’affichent :

    - **Mettre à jour l’espace de travail et l’application** – Mettez à jour l’application modèle existante et écrasez vos paramètres d’application existants, tels que le nom de l’instance d’application et les configurations d’autorisation.
    - **Mettre à jour uniquement le contenu de l’espace de travail sans mettre à jour l’application** – Mettez à jour l’application modèle existante, mais conservez vos paramètres d’application existants. *Cette option est recommandée pour les mises à jour d’applications.*
    - **Installer une autre copie de l’application dans un nouvel espace de travail** – Créez un nouvel espace de travail, puis créez une copie du modèle d’application existant dans celui-ci. L’espace de travail existant sera laissé intact.

4. Sélectionnez l’une des options de mise à jour, puis sélectionnez **Installer**.
5. Ouvrez l’application installée en sélectionnant **Applications** dans le volet de gauche, puis en sélectionnant l’application.
6. Connectez l’application à votre source de données en sélectionnant **Connecter**. Si vous avez déjà installé l’application, cliquez sur le lien **Connecter vos données** dans la barre de message jaune.
7. Définisse les champs suivants.

    | Champ | Valeur |
    |---|---|
    | Serveur | Entrez le nom du point de terminaison Azure Synapse Serverless SQL que vous avez créé dans la section précédente. Vous pouvez obtenir cette valeur à partir de la page **Vue d’ensemble** d'Azure Synapse workspace dans le portail Azure. |
    | Base de données | Entrez **CommerceAnalytics**. |
    | Langue | Sélectionnez une valeur dans la liste. Ce champ est utilisé pour les noms de produits et de catégories localisés. Cette valeur respecte la casse. |
    | Plage de dates | Sélectionnez une valeur dans la liste. Les données pour le nombre de mois sélectionné seront importées dans le jeu de données Power BI. La valeur que vous sélectionnez affecte la taille de l’ensemble de données et le temps requis pour la synchronisation. |

8. Cliquez sur **Suivant**. Vous êtes invité à saisir les informations d’identification pour vous connecter à la base de données SQL Azure Synapse. Définissez les champs comme décrit dans le tableau suivant.

    | Champ | Valeur |
    |---|---|
    | Méthode d’authentification | Sélectionnez **De base**. |
    | Nom d’utilisateur | Entrez **reportreadonlyuser**. |
    | Mot de passe | Entrez la valeur avec laquelle vous avez remplacée l’espace réservé [placeholder_password](#phUserPwd) dans le script SetupSynapse.sql. Ce mot de passe est celui du compte **reportreadonlyuser**. |

9. Sélectionnez **Se connecter**.
10. Attendez que l’ensemble de données soit mis à jour avec succès. Cliquez ensuite sur le bouton **Modifier l’application** pour ouvrir l’espace de travail de l’application, où vous pouvez afficher l’état de mise à jour du jeu de données. Dans l’espace de travail de l’application, vous pouvez également configurer des planifications de mise à jour automatiques pour votre jeu de données, gérer les autorisations et renommer l’instance de l’application.

### <a name="privacy"></a><a name="privacy"></a>Confidentialité

La protection de votre vie privée est importante pour nous. Pour en savoir plus, lisez notre [Déclaration de confidentialité](https://go.microsoft.com/fwlink/?LinkId=521839).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
