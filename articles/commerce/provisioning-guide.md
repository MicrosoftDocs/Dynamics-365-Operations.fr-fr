---
title: Configurer un environnement d'évaluation de commerce électronique
description: Ce guide fournit les instructions pas-à-pas sur la mise en service et configurer votre environnement de Microsoft Dynamics 365 Commerce en préversion.
author: v-chgri
manager: annbe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b0dce2796e69cd8dee87cba176a521c26c81eb1a
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771678"
---
# <a name="configure-an-e-commerce-evaluation-environment"></a>Configurer un environnement d'évaluation de commerce électronique

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ce guide fournit les instructions pas-à-pas sur la mise en service et configurer votre environnement de Microsoft Dynamics 365 Commerce en préversion. Avant de commencer, nous vous recommandons de parcourir rapidement au moins la documentation pour avoir une idée de ce que le processus requiert et de ce que le guide contient.

*Remarque : si vous n'avez pas reçu l'accès à Microsoft Dynamics 365 Commerce Préversion encore, vous pouvez demander l'accès à la préversion sur le [site web de Commerce](https://aka.ms/Dynamics365CommerceWebsite).*

## <a name="summary"></a>Synthèse
Pour mettre en service l'environnement avec succès, le projet doit être créé avec un nom et un type de produit spécifiques. L'environnement et Retail Cloud Scale Unit ont aussi des paramètres spécifiques que vous devez utiliser pour démarrer la mise en service du commerce électronique ultérieurement. Les instructions de ce guide contiennent toutes les étapes nécessaires à prendre et les paramètres à utiliser.

Après une mise en service réussie, il existe des étapes postérieures à la mise en service à effectuer pour préparer votre environnement en préversion. Certaines étapes sont facultatives, selon les aspects du système vous souhaitez évaluer. Si vous changez d'avis ultérieurement, vous pouvez toujours exécuter les étapes facultatives ultérieurement.

En cas de questions sur les étapes de mise en service ou si vous rencontrez des problèmes, contactez-nous sur le [groupe Yammer de Microsoft Dynamics 365 Commerce Préversion](https://aka.ms/Dynamics365CommercePreviewYammer). 

## <a name="prerequisites"></a>Conditions préalables
Voici les conditions préalables à appliquer pour mettre en service votre environnement de préversion de Dynamics 365 :
* Vous avez accès au **Portail Lifecycle Services (LCS)**
* Vous avez été **accepté dans le programme de préversion de Dynamics 365 Commerce**
* Vous avez les autorisations nécessaires pour créer un projet pour **Préventes potentielles** ou **Migrer, créer des solutions et découvrir**
* Vous êtes membre du rôle **Gestionnaire d'environnement** ou **Propriétaire du projet** dans le projet où vous mettrez l'environnement en service
* Vous avez un accès en tant qu'administrateur à votre abonnement Azure, ou contactez un administrateur d'abonnement qui peut effectuer les deux étapes qui nécessitent des autorisations d'administrateur en votre nom
* Vous avez votre **ID client AAD** disponible
* Vous avez créé un **groupe de sécurité AAD** à utiliser comme **groupe d'administrateurs système de commerce électronique** et son ID est disponible
* Vous avez créé un **groupe de sécurité AAD** à utiliser comme **groupe de modérateurs des évaluations et avis** et vous avez son ID disponible (peut être le même groupe de sécurité que le groupe d'administrateurs système ci-dessus)
## <a name="provisioning-preview-environment"></a>Mise en service de la préversion de l'environnement
Ces instructions couvrent la mise en service d'un environnement en préversion de Microsoft Dynamics 365 Commerce. Après avoir terminé la procédure, vous avez un environnement en préversion prêt à être configuré. Toutes les activités décrites ici ont lieu dans le portail LCS.

*Notez que l'accès en préversion est lié au compte et à l'organisation LCS spécifiés dans votre demande de préversion. Vous devez utiliser le même compte pour la mise en service. Si vous devez utiliser un autre compte ou client LCS pour l'environnement en préversion, vous devez nous fournir ces détails. Pour des informations de contact, voir « Ressources supplémentaires » ci-dessous.*
### <a name="before-starting"></a>Avant de démarrer
##### <a name="grant-access-to-e-commerce-applications"></a>Accorder l'accès aux applications de commerce électronique

*Remarque : **l'utilisateur ouvrant une session doit être administrateur de client AAD**. Sans exécuter correctement cette étape, le reste des étapes de mise en service échouera.*

1. Pour cette étape, vous avez besoin de votre **ID client AAD**. Vous devez autoriser les applications de commerce électronique à accéder à votre abonnement Azure. La manière la plus simple pour cela est d'assembler une URL comme ceci :

https://login.windows.net/{AAD_TENANT_ID}/oauth2/authorize?client_id=fbcbf727-cd18-4422-a723-f8274075331a&response_type=code&redirect_uri=https://sb.manage.commerce.dynamics.com/_commerce/Consent&response_mode=query&prompt=admin_consent&state=12345

2. **Ne cliquez pas sur l'URL directement**, à la place copiez-la et collez-la dans votre éditeur de texte ou navigateur et remplacez **\{AAD_TENANT_ID\}** par votre **ID client AAD**, avant d'accéder à l'URL.
3. Une boîte de dialogue de connexion à Microsoft AAD s'affichera dans laquelle vous confirmerez que vous souhaitez accorder l'accès de « Dynamics 365 Commerce (préversion) » à votre abonnement.
4. Vous serez dirigé vers une page qui confirme si l'opération a réussi.

##### <a name="log-in-to-the-lcs"></a>Connexion à LCS
1. Connexion au portail LCS : https://lcs.dynamics.com
1. Assurez-vous que vous êtes connecté avec le même compte LCS que celui utilisé pour demander l'accès à la préversion.
##### <a name="confirm-that-preview-features-are-available-and-enabled"></a>Confirmez que les fonctionnalités de préversion sont disponibles et activées
1. Sur la première page de LCS, faites défiler tout à droite et cliquez sur la vignette **Gestion des fonctionnalités d'aperçu**.
1. Faites défiler jusqu'à « FONCTIONNALITÉS D'APERÇU PRIVÉ » et assurez-vous que les fonctionnalités suivantes sont disponibles et activées :
    1. **Évaluation du commerce électronique**
    1. **Environnements du programme de préversion de Commerce**
1. Si vous ne voyez pas ces fonctionnalités dans la liste, contactez-nous avec votre e-mail professionnel, compte LCS, et détails concernant le client. Voir **Ressources supplémentaires** ci-dessous pour plus informations sur la manière dont nous contacter.

![Vignette Gestion des versions préliminaires](./media/preview1.png)

![Fonctionnalités d'aperçu](./media/preview2.png)
### <a name="create-project"></a>Créer un projet
##### <a name="creating-new-project"></a>Création d'un projet
1. Cliquez sur **+** pour créer un projet.
1. Si vous êtes un partenaire, choisissez **Migrer, créer des solutions et découvrir**.
1. Si vous êtes un client, choisissez **Préventes potentielles**.
1. Entrez un nom, une description et un secteur comme vous le souhaitez.
1. Pour **Nom du produit**, sélectionnez **Dynamics 365 Retail**.
1. Pour **Version du produit**, sélectionnez **Dynamics 365 Retail**.
1. Pour **Méthodologie**, sélectionnez **Méthodologie de mise en œuvre de Dynamics Retail**.
1. Vous pouvez importer des rôles et des utilisateurs d'un projet existant si vous le souhaitez.
1. Cliquez sur **Créer**.
1. Vous êtes dirigé vers la vue du projet.
##### <a name="add-azure-connector"></a>Ajouter un connecteur Azure
1. Si vous êtes un partenaire, cliquez sur **Paramètres du projet** dans les vignettes d'outils à l'extrême droite.
1. Si vous êtes un client, choisissez **Paramètres du projet** dans menu principal.
1. Sélectionnez **Connecteurs Azure**.
1. Cliquez sur **Ajouter** pour ajouter un connecteur Azure.
1. Entrez un nom.
1. Entrez votre **ID abonnement Azure**.
1. Activez **Configurer pour utiliser ARM (Azure Resource Manager)**.
1. Vérifiez que **Domaine du locataire AAD de l'abonnement Azure (ou ID)** est correct. Contactez l'administrateur d'abonnements Azure, si nécessaire.
1. Cliquez sur **Suivant**.
1. Suivez les instructions à l'écran pour accorder l'accès aux applications requises à votre abonnement. Contactez l'administrateur d'abonnements Azure, si nécessaire :
    1. Connexion au portail Azure : https://portal.azure.com/
    1. Vérifiez que vous avez sélectionné le bon répertoire.
    1. Cliquez sur **Abonnements** dans menu à gauche.
    1. Localisez l'abonnement approprié dans la liste et sélectionnez-le. Utilisez la recherche si nécessaire.
    1. Choisissez **Contrôle d'accès (IAM)** dans le menu.
    1. Cliquez sur **Ajouter** sous **Ajouter une affectation de rôle** à droite. Le volet **Ajouter une affectation de rôle** s'ouvre.
    1. Pour **Rôle**, sélectionnez **Contributeur**.
    1. Pour **Affecter l'accès**, laissez comme **Utilisateur, groupe ou principal de service Azure AD**.
    1. Sous **Sélectionner**, entrez **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.
    1. Sélectionnez **Services de déploiement Dynamics [activé pour WsFed]** de la liste.
    1. Cliquez sur **Enregistrer**.
1. Cliquez sur **Suivant**.
1. Suivez les instructions à l'écran pour accorder l'accès aux applications requises à votre abonnement. Contactez l'administrateur d'abonnements Azure, si nécessaire.
1. Cliquez sur **Suivant**.
1. Pour **Région Azure**, choisissez **Est des États-Unis**, **Est des États-Unis 2**, **Ouest des États-Unis** ou **Ouest des États-Unis 2**.
1. Cliquez sur **Connecter**.
1. Votre connecteur Azure doit apparaître dans la liste.
### <a name="import-extension"></a>Importation d'extension
1. Revenez à la première page de votre projet en cliquant sur le nom du projet en haut.
1. Si vous êtes un partenaire, cliquez sur **Bibliothèque d'actifs** dans les vignettes d'outils à l'extrême droite.
1. Si vous êtes un client, choisissez **Bibliothèque d'actifs** dans menu principal.
1. Sélectionnez **Module déployable de logiciel** dans la liste de gauche.
1. Cliquez sur **IMPORTER** dans le volet Actions.
1. Sélectionnez **Extension de de base de démonstration de version d'évaluation de Commerce** dans la liste des actifs sous **BIBLIOTHÈQUE D'ACTIFS PARTAGÉS**.
1. Cliquez sur **Choisir**.
1. Vous êtes renvoyé vers la Bibliothèque d'actifs et vous devez voir l'extension dans la liste.

![Création du projet - versions](./media/import.png)
### <a name="deploy-environment"></a>Déployer l'environnement

*Remarque : il est possible que les étapes 6, 7, et/ou 8 ne soient pas affichées, car les écrans avec une option unique sont ignorés. Lorsque vous êtes dans la vue **Paramètres d'environnement**, confirmez que vous avez le texte « Dynamics 365 Commerce (Préversion) - Démonstration (10.0.6 avec Platform Update 30) » directement au-dessus du champ **Nom de l'environnement**. Voir la capture d'écran ci-dessous.*

1. Dans le menu principal, sélectionnez **Environnements hébergés dans le cloud**.
1. Cliquez sur **+ Ajouter** pour ajouter un environnement.
1. Pour **Version de l'application**, sélectionnez **10.0.6**.
1. Pour **Version de la plateforme**, sélectionnez **Platform Update 30**.
1. Cliquez sur **Suivant**.
1. Pour la topologie de l'environnement, choisissez **DÉMONSTRATION**.
1. Pour la topologie de l'environnement, choisissez **Dynamics 365 Commerce (Préversion) - Démonstration**.
1. Si vous avez configuré un seul connecteur Azure plus tôt, utilisez-le pour l'environnement. Si vous avez configuré plusieurs connecteurs Azure, vous avez la possibilité de sélectionner le connecteur à utiliser : **Est des États-Unis**, **Est des États-Unis 2**, **Ouest des États-Unis** ou **Ouest des États-Unis 2** (recommandée pour les meilleures performances de bout en bout)
1. Entrez le **Nom de l'environnement**.
1. Ajustez la taille de la MV comme bon vous semble. (Nous vous recommandons le SKU de MV **D13 v2**.)
1. Laissez les **Paramètres avancés** inchangés.
1. Après avoir vérifié la tarification et les conditions d'attribution de licence à l'écran, activez la case à cocher pour indiquer votre accord.
1. Cliquez sur **Suivant**.
1. Dans l'écran de confirmation de déploiement, après avoir vérifié les détails sont corrects, cliquez sur **Déployer**.
1. Vous reviendrez à la vue **Environnements hébergés sur le cloud** et votre environnement doit apparaître dans la liste.
1. Votre environnement demandé s'affiche comme mis en file d'attente puis en cours de déploiement. Cela prendra un certain temps pour que tous les workflows d'environnement se terminent, revérifiez ultérieurement après quelques heures (environ 6 à 9 heures).
1. Avant de continuer, vérifiez que votre statut d'environnement est **Déployé**.

![Création du projet - versions](./media/project1.png)

![Création du projet - topologie 1](./media/project2.png)

![Création du projet - topologie 2](./media/project3.png)

![Création de projet - paramètres d'environnement](./media/project4.png)
### <a name="initialize-rcsu"></a>Initialiser RCSU
1. Dans la vue **Environnements hébergés dans le cloud**, sélectionnez votre environnement de la liste.
1. Dans la vue d'environnement à droite de l'écran, cliquez sur **Détails complets**. La vue des détails d'environnement s'affiche.
1. Sous **FONCTIONS D'ENVIRONNEMENT**, cliquez sur **Gérer**.
1. Sous l'onglet **Vente au détail**, cliquez sur **Initialiser**. La vue des paramètres d'initialisation de RCSU s'affiche.
1. Pour **RÉGION**, sélectionnez **Est des États-Unis**, **Est des États-Unis 2**, **Ouest des États-Unis** ou **Ouest des États-Unis 2**.
1. Pour **VERSION**, sélectionnez **Spécifier une version** d'abord dans la liste déroulante, puis spécifiez **9.16.19262.5** dans le champ texte qui apparaît ci-après. *Remarque : veillez à **spécifier la version précise** répertorié ici pour éviter de devoir mettre le RCSU à jour ultérieurement pour corriger la version.*
1. Activez **Appliquer l'extension**.
1. Dans la liste des extensions, choisissez **Numéro de base de démonstration de version d'évaluation de Commerce**.
1. Cliquez sur **Initialiser**.
1. Dans l'écran de confirmation de déploiement, après avoir vérifié les détails sont corrects, cliquez sur **Oui**.
1. Vous êtes renvoyé à la vue **Gestion de la vente au détail** avec l'onglet **Vente au détail** activé. Votre RCSU a été mis en file d'attente pour la mise en service.
1. Attendez que votre statut de RCSU soit **RÉUSSITE** avant de poursuivre (environ 2 à 5 heures).
### <a name="initialize-e-commerce"></a>Initialiser e-Commerce
1. Passez à l'onglet **Commerce électronique (préversion)**.
1. Après vérification du consentement pour la version d'évaluation, cliquez sur **Paramétrage**.
1. Entrez un nom pour le **nom du client de commerce électronique**. Toutefois, notez que ce sera visible dans certaines URL pointant vers votre instance de commerce électronique.
1. Pour **Nom Retail Cloud Scale Unit**, sélectionnez votre RCSU dans la liste (la liste doit contenir une option).
1. **Géographie de commerce électronique** est automatiquement rempli et ne peut pas être modifié.
1. Cliquez sur **Suivant** pour continuer.
1. Pour **Noms d'hôte pris en charge**, entrez tout domaine valide (par exemple www.fabrikam.com).
1. Pour **Groupe de sécurité AAD pour l'administrateur système**, entrez l'ID groupe de sécurité AAD que vous souhaitez utiliser comme groupe d'administrateur système de commerce électronique.
1. Pour **Groupe de sécurité du DAA pour les classements et le modérateur de révision**, entrez l'ID de SG du DAA que vous souhaitez à utiliser comme classements et vérifiez le groupe de modérateur.
1. Laissez les valeurs **B2C** vides (7 champs qui commencent par B2C.)
1. Laissez **Activer le service de classements et évaluations** activé.
1. Cliquez sur **Initialiser**.
1. Vous êtes renvoyé à la vue **Gestion de la vente au détail** avec l'onglet **Commerce électronique (aperçu)** activé. Votre initialisation de commerce électronique a commencé.
1. Avant de continuer, attendez que votre statut d'initialisation de commerce électronique soit **INITIALISATION RÉUSSIE**.
1. Sous **LIENS** en bas à droite.
    * Prenez une note du lien **site de commerce électronique**. Il s'agit du lien à la racine du site C2.
    * Prenez une note du lien **outil de gestion du site de commerce électronique**. Il s'agit du lien vers l'outil de gestion du site (outil de création C1).
## <a name="post-provisioning-steps"></a>Étapes postérieures à la mise en service
À ce stade, l'environnement a été mis en service de bout en bout, mais il reste des étapes de configuration à réaliser pris avant de commencer évaluer l'environnement.
### <a name="before-starting"></a>Avant de démarrer
1. Dans le menu principal, sélectionnez **Environnements hébergés dans le cloud**.
1. Sélectionnez votre environnement dans la liste.
1. Cliquez sur **Détails complets** dans les informations de l'environnement à droite.
1. Cliquez sur **Connexion** pour ouvrir un menu, choisissez **Se connecter à l'environnement**.

Assurez-vous que l'entité juridique **USRT** est sélectionnée (angle supérieur droit).

### <a name="configure-pos"></a>Configurer POS
##### <a name="associate-worker-with-your-identity"></a>Associer le collaborateur à votre identité
1. À l'aide du menu à gauche, accédez à **Modules > Vente au détail > Employés > Collaborateurs**.
1. Dans la liste, recherchez et sélectionnez l'enregistrement **000713 - Andrew Collette**.
1. Dans le volet Actions, cliquez sur **Vente au détail**.
1. Cliquez sur **Associer une identité existante**.
1. Dans le champ **E-mail** (à droite de **Rechercher à l'aide de l'e-mail**), entrez votre adresse e-mail.
1. Cliquez sur **Recherche**.
1. Sélectionnez l'enregistrement à votre nom.
1. Cliquez sur **OK**.
1. Cliquez sur **Enregistrer**.
##### <a name="activate-cloud-pos"></a>Activer le PDV Cloud
1. Connexion au portail LCS.
1. Accédez à votre projet.
1. Dans le menu principal, sélectionnez **Environnements hébergés dans le cloud**.
1. Sélectionnez votre environnement dans la liste.
1. Cliquez sur **Détails complets** dans les informations de l'environnement à droite.
1. Cliquez sur **Connexion** pour ouvrir un menu, choisissez **Connexion au point de vente du cloud**, le PDV doit se charger.
1. Cliquez sur **Suivant**.
1. Connexion avec votre compte AAD
1. Sous **Nom du magasin**, choisissez **Saint-Nazaire**.
1. Cliquez sur **Suivant**.
1. Sous **Registre et périphérique**, choisissez **SAiNNAZ-1**.
1. Cliquez sur **Activer**.
1. Vous devez être déconnecté et voir l'écran de connexion du PDV.
1. Vous pouvez désormais vous connecter à l'expérience du PDV de cloud à l'aide de l'ID opérateur **000713** et le mot de passe **123**.
### <a name="site-setup"></a>Paramétrage de site
1. Connexion à **outil de gestion de site** en utilisant l'URL que vous avez notée précédemment.
1. Cliquez sur le site **Fabrikam** pour ouvrir la boîte de dialogue de paramétrage de site.
1. Pour le domaine, sélectionnez le domaine entré précédemment lors de l'initialisation du commerce électronique.
1. Pour le canal par défaut, sélectionnez **Fabrikam a étendu le magasin en ligne**. *Remarque : vérifiez de sélectionner le magasin en ligne **étendu***
1. Pour la langue par défaut, sélectionnez **fr-fr**.
1. Laissez le **Chemin d'accès** comme il est.
1. Cliquez sur **OK**.
1. Vous êtes dirigé vers la liste des pages du site.
### <a name="enable-jobs"></a>Activer les tâches
1. Connectez-vous à l'environnement (Siège social).
1. Utilisation du menu à gauche, **Vente au détail > Recherches et états > Traitements par lots**.
1. Effectuez les tâches suivantes pour chacune des tâches dans la liste ci-dessous :
    * **Traiter la notification par e-mail des commandes de vente au détail**.
    * **Disponibilité du produit**.
    * **P-0001**.
    * **Synchroniser la tâche des commandes**.
1. Utilisez le filtre rapide pour rechercher la tâche en utilisant son nom (répertorié ci-dessus).
1. Si le statut de la tâche est **Retenir**, procédez comme suit :
    1. Sélectionner l'enregistrement.
    1. Dans le volet Actions, ouvrez le ruban **Traitement par lots** et cliquez sur **Modifier le statut**.
    1. Sélectionnez **En attente** et cliquez sur **OK**.
### <a name="run-full-data-sync"></a>Exécuter une synchronisation complète des données
1. Utilisation du menu à gauche, accédez à **Modules > Vente au détail > Paramétrage du Siège > Retail Planification > Base de données du canal**.
1. Le canal**Par défaut** est sélectionné dans la liste vers la gauche. *Sélectionnez l'autre canal disponible (nommé **scXXXXXXXXX**)*.
1. Cliquez sur **Synchronisation de données complète** du volet Actions.
1. Entrez **9999** comme programme de distribution.
1. Cliquez sur **OK**.
1. Cliquez sur **OK**.
### <a name="after-these-steps-you-are-ready-to-start-evaluating-your-preview-environment"></a>Une fois ces étapes vous sont prêt à commencer à évaluer votre environnement d'aperçu !
Utilisez l'URL **outil de gestion du site de commerce électronique** pour accéder au à l'expérience de création C1 et l'URL **site de commerce électronique** pour accéder à l'expérience du site C2.

## <a name="additional-resources"></a>Ressources supplémentaires
### <a name="how-to-find-your-aad-tenant-id"></a>Procédure de recherche de l'ID client AAD
L'ID client AAD est un GUID et ressemble à cet exemple : **72f988bf-86f1-41af-91ab-2d7cd011db47**
##### <a name="from-azure-portal"></a>À partir du portail Azure
1. Connexion au portail Azure : https://portal.azure.com/
1. Vérifiez que vous avez sélectionné le bon répertoire.
1. Cliquez sur **Azure Active Directory** dans menu à gauche.
1. Choisissez **Propriétés** sous **Gérer**.
1. L'ID client AAD s'affiche sous **ID répertoire**.
##### <a name="from-openid-connect-metadata"></a>Métadonnées de connexion à partir d'OpenID
Créez l'**URL OpenID** en remplaçant **\{VOTRE_DOMAINE\}** par votre domaine, par exemple microsoft.com : https://login.microsoftonline.com/{YOUR_DOMAIN}/.well-known/openid-configuration deviendrait https://login.microsoftonline.com/microsoft.com/.well-known/openid-configuration

1. Accédez à l'**URL OpenID** avec votre domaine dans celle-ci.
1. L'ID client AAD peut être vue dans plusieurs valeurs de propriété.
1. Localisez **authorization_endpoint** et extrayez le GUID juste après **login.microsoftonline.com/**.
### <a name="how-to-find-the-id-of-your-aad-security-group"></a>Procédure de recherche de l'ID de votre groupe de sécurité AAD
L'ID de groupe de sécurité AAD est un GUID et ressemble à cet exemple : **436ea7f5-ee6c-40c1-9f08-825c5811066a**

Cette étape suppose que l'utilisateur est membre du groupe dont il tente de rechercher l'ID.
1. Accédez à l'Explorateur graphique : https://developer.microsoft.com/en-us/graph/graph-explorer#
1. Cliquez sur **Connexion à Microsoft** et connectez-vous à l'aide de vos informations d'identification.
1. Après vous être connecté, cliquez sur **afficher d'autres exemples** à gauche.
1. Activez **Groupes** dans le volet droit.
1. Fermez le volet droit.
1. Cliquez sur **tous les groupes auxquels j'appartiens**.
1. Localisez le groupe avec la zone de texte **Aperçu de la réponse**.
1. L'ID du groupe de sécurité est notée sous la propriété **ID**.
### <a name="test-credit-card-information-to-perform-test-purchases"></a>Tester les informations de carte de crédit pour effectuer des tests d'achats
Pour effectuer des tests de transactions sur le site, vous pouvez utiliser ces informations de carte de crédit de test :

Numéro de carte : 4111-1111-1111-1111, expiration : 10/20, CVV : 737

*Remarque : vous ne devez tenter d'utiliser des informations de carte de crédit réelle sur le site de test sous aucune circonstance !*
### <a name="useful-links"></a>Liens utiles
* [LCS (Lifecycle services)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)
* [RCSU (Retail Cloud Scale Unit)](https://docs.microsoft.com/en-us/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)
* [Portail Microsoft Azure](https://azure.microsoft.com/en-us/features/azure-portal)
* [Site web Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)
* [Ressources d'aide pour Dynamics 365 Retail](../retail/index.md)
### <a name="microsoft-dynamics-365-commerce-preview-support"></a>Prise en charge de l'aperçu de Microsoft Dynamics 365 Commerce
Si vous rencontrez des problèmes lors de l'exécution des étapes de mise en service, visitez le [groupe Yammer de la version d'évaluation de Microsoft Dynamics 365 Commerce](https://aka.ms/Dynamics365CommercePreviewYammer) pour obtenir de l'aide. 

Si vous avez des problèmes pour accéder au groupe Yammer, vous pouvez également nous joindre par e-mail à l'adresse **Dynamics365Commerce@microsoft.com**. Cette adresse e-mail n'est pas activement surveillée, attendez-vous à un retard dans la réponse.
***
## <a name="prerequisites-for-optional-features"></a>Conditions préalables pour les fonctionnalités facultatives
Si vous souhaitez évaluer les fonctionnalités d'e-mail transactionnelles, les conditions requises suivantes doivent être remplies :
* Un serveur de messagerie disponible (serveur SMTP), qui peut être utilisé par l'abonnement Azure dans lequel vous mettez en service l'environnement d'aperçu.
* Le nom de domaine complet (FQDN) ou ID, le numéro de port SMTP, et les détails d'authentification disponibles.

Si vous souhaitez évaluer des fonctionnalités de gestion d'actifs numériques, notamment ingérer de nouvelles images omnicanales, les conditions requises suivantes doivent satisfaire :
* Vous devez disposer de votre **Nom de client CMS** disponible. Les instructions pour rechercher ce nom sont ci-dessous.
### <a name="configure-image-backend-optional"></a>Configurer le principal d'image (facultatif)
##### <a name="finding-your-media-base-url"></a>Recherche de votre URL de base multimédia
*Remarque : avant de pouvoir effectuer cette étape, vous devez effectuer le **Paramétrage du site**.*
1. Connexion à outil de gestion de site en utilisant l'URL que vous avez notée précédemment.
1. Ouvrez le site **Fabrikam**.
1. Choisissez **Actifs** dans menu à gauche.
1. Sélectionnez un actif d'image unique.
1. Localisez **URL publique** dans l'inspecteur de propriété à droite. Elle comporte une URL en son sein.
    * Exemple d'URL : https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC
1. Remplacez le dernier identificateur de l'URL (MA1nQC dans l'exemple d'URL ci-dessus) par la chaîne suivante : **search?fileName=**
    * Exemple d'URL après remplacement : https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=
    * Il s'agit de votre **URL de base multimédia** - prenez-en note.
##### <a name="updating-the-media-base-url"></a>Mise à jour de l'URL de base multimédia
1. Connectez-vous à l'environnement (Siège social).
1. Utilisation du menu à gauche, accédez à **Modules > Vente au détail > Paramétrage du canal > Profils du canal**.
1. Cliquez sur **Modifier**.
1. Dans **Propriétés du profil**, remplacez la valeur de propriété pour **URL de base du serveur multimédia** par **URL de base multimédia** créé précédemment.
1. Sélectionnez l'autre canal dans la liste à gauche, sous le canal **Par défaut**.
1. Sous **Propriétés du profil**, cliquez sur **+ Ajouter**.
1. Pour la propriété qui a été ajoutée, choisissez **URL de base du serveur multimédia** comme clé de propriété et pour la valeur de propriété, entrez **URL de base multimédia** créé précédemment.
1. Cliquez sur **Enregistrer**.

### <a name="configure-email-server-optional"></a>Configuration du serveur de messagerie (facultatif)
Notez que le serveur SMTP ou le service de messagerie que vous entrez ici doivent être accessibles à partir de l'abonnement Azure que vous utilisez pour l'environnement.
1. Connectez-vous à l'environnement (Siège social).
1. Utilisation du menu à gauche, accédez à **Modules > Vente au détail > Paramétrage du Siège > Paramètres > Paramètres de la messagerie**.
1. Cliquez sur l'onglet **Paramètres SMTP**.
1. Dans le **champ Serveur de messagerie sortante**, tapez le nom de domaine complet ou l'adresse IP du serveur SMTP ou du service de messagerie.
1. Dans le champ **Numéro de port SMTP**, entrez le numéro de port (la valeur par défaut est le 25 si pas d'authentification SSL).
1. Dans le champ **Nom d'utilisateur**, tapez une valeur (si l'authentification est obligatoire).
1. Dans le champ **Mot de passe**, tapez une valeur (si l'authentification est obligatoire).
1. Cliquez sur **Enregistrer**.
1. Cliquez sur **Actualiser**.
1. Cliquez sur l'onglet **Tester la messagerie**.
1. Dans le champ Fournisseur de messagerie, choisissez **SMTP**.
1. Dans le champ **Destinataire**, entrez l'adresse e-mail à laquelle vous souhaitez que l'e-mail de test soit remis.
1. Cliquez sur **Envoyer un e-mail de test**.
### <a name="configure-email-templates-optional"></a>Configuration des modèles de-mails (facultatif)
Le modèle d'e-mail pour chaque événement transactionnel pour lequel envoyer des e-mails doit être mis à jour avec une adresse e-mail d'expéditeur valide.
1. Utilisation du menu à gauche, accédez à **Modules > Administration de l'organisation > Paramétrage > Modèles d'e-mail de l'organisation**.
1. Cliquez sur **Afficher la liste**.
1. Pour chacun des modèles dans la liste :
    1. Dans le champ **Adresse e-mail de l'expéditeur**, tapez l'adresse e-mail de l'expéditeur pour ce modèle d'e-mail.
    1. (Facultatif) Dans le champ **Nom de l'expéditeur**, tapez un nom qui sera utilisé comme expéditeur pour ce modèle d'e-mail.
1. Cliquez sur **Enregistrer**.
### <a name="customizing-email-templates-optional"></a>Personnalisation des modèles de-mails (facultatif)
Vous pouvez personnaliser les modèles d'e-mail pour utiliser différentes images ou mettre à jour les liens dans le modèle à relier à votre environnement d'aperçu. Les étapes ci-dessous décrivent le téléchargement des modèles par défaut, leur personnalisation et la mise à jour des modèles à jour dans le système.
1. Utilisation d'un navigateur, téléchargez le [fichier .zip des modèles d'e-mails par défaut de Microsoft Dynamics 365 Commerce Aperçu](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) contenant les documents HTML suivants sur votre ordinateur local.
    1. Modèle de confirmation de commande
    1. Émettre un modèle de carte cadeau
    1. Nouveau modèle de commande
    1. Modèle de commande emballée
    1. Modèle de commande à prélever
1. Personnaliser les modèles à l'aide d'un texte ou un éditeur HTML. Voir la liste des jetons pris en charge ci-dessous.
1. Connectez-vous à l'environnement (Siège social).
1. Utilisation du menu à gauche, accédez à **Modules > Vente au détail > Paramétrage du Siège > Paramètres > Modèles d'e-mails d'organisation**.
1. Développez la liste à gauche pour afficher tous les modèles.
1. Pour chacun des modèles que vous souhaitez personnaliser, procédez comme suit :
    1. Sélectionnez le modèle dans la liste.
    1. Sous **Contenu de message électronique**, sélectionnez la version de langue appropriée dans la liste (**fr-fr** par défaut).
    1. Sous **Contenu du message électronique**, cliquez sur **Modifier**, vous devez voir le volet **Télécharger un modèle d'e-mail** s'ouvrir.
    1. Cliquez sur **Parcourir** et rechercher le fichier HTML avec le contenu personnalisé.
    1. Cliquez sur **Charger**, votre modèle est chargé vers le système et un aperçu s'affiche.
    1. Cliquez sur **OK**.
    1. (Facultatif) Personnalisez la propriété **Objet** du modèle.
    1. Cliquez sur **Enregistrer**.

#### <a name="supported-tokens-in-the-email-template"></a>Jetons pris en charge dans le modèle d'e-mail
Ces jetons seront remplacés au moment de l'affichage de l'e-mail par les valeurs réelles s'appliquant au client et à sa commande.

**Commande client** - Les jetons suivants s'appliquent à la commande client globale.

|Nom du jeton|Jeton|
|---|---|
|Numéro de la commande|%salesid%|
|Nom du client|%customername%|
|Adresse de livraison|%deliveryaddress%|
|Adresse de facturation|%customeraddress%|
|Date de commande|%shipdate%|
|Mode de distribution|%modeofdelivery%|
|Remise|%discount%|
|Taxe|%tax%|
|Total de la commande|%total%|

**Ligne de ventes** - Les jetons suivants sont remplis pour chaque produit de la commande.

*Remarque : placez les jetons **Liste de produit - Début** et **Liste de produit - Fin** au début et à la fin du bloc HTML qui se répète pour chaque produit.*

|Nom du jeton|Jeton|
|---|---|
|Liste de produits - début|\<!--%tablebegin.salesline% -->|
|Liste de produits - fin|\<!--%tableend.salesline%-->|
|Nom du produit|%lineproductname%|
|Description|%lineproductdescription%|
|Quantité|%linequantity%|
|Prix unitaire de la ligne|%lineprice% (vérifier)|
|nombre total d'articles de ligne|%linenetamount%|
|remise ligne|%linediscount%|
|Date d'expédition|%lineshipdate%|
|Méthode d'approvisionnement|%linedeliverymode%|
|adresse de livraison|%linedeliveryaddress%|
|Unité de vente de la ligne|%lineunit%|

