---
title: Mise en service d'un environnement d'aperçu Commerce
description: Cette rubrique explique comment mettre en service un environnement d'aperçu dans Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 01/06/2020
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b77d2cbbc100aeae5dcd53ddbe69ff2e4435da13
ms.sourcegitcommit: 4d77d06a07ec9e7a3fcbd508afdffaa406fd3dd8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934746"
---
# <a name="provision-a-commerce-preview-environment"></a>Mise en service d'un environnement d'aperçu Commerce

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique explique comment mettre en service un environnement d'aperçu dans Microsoft Dynamics 365 Commerce.

Avant de commencer, nous vous recommandons de parcourir rapidement l'ensemble de cette rubrique pour avoir une idée de ce que le processus requiert et de ce que cette rubrique contient.

> [!NOTE]
> Si vous n'avez pas encore obtenu l'accès à l'aperçu de Dynamics 365 Commerce, vous pouvez demander l'accès à l'aperçu sur le [site web de Commerce](https://aka.ms/Dynamics365CommerceWebsite).

## <a name="overview"></a>Vue d'ensemble

Pour configurer correctement votre environnement d'aperçu Commerce, vous devez créer un projet qui a un nom et un type de produit spécifiques. L'environnement et Retail Cloud Scale Unit (RCSU) ont aussi des paramètres spécifiques que vous devez utiliser pour mettre en service du commerce électronique ultérieurement. Les instructions de cette rubrique décrivent toutes les étapes requises et les paramètres à utiliser.

Après une mise en service réussie de votre environnement d'aperçu Commerce, des étapes postérieures à la mise en service sont à effectuer pour le préparer. Certaines étapes sont facultatives, selon les aspects du système que vous souhaitez évaluer. Vous pouvez toujours effectuer les étapes facultatives ultérieurement.

Pour plus d'informations sur la configuration de votre environnement d'aperçu Commerce après l'avoir mis en service, consultez [Configurer un environnement d'aperçu Commerce](cpe-post-provisioning.md). Pour plus d'informations sur la configuration des fonctionnalités facultatives de votre environnement d'aperçu Commerce, consultez [Configurer les fonctionnalités facultatives d'un environnement d'aperçu Commerce](cpe-optional-features.md).

En cas de questions sur les étapes de mise en service ou si vous rencontrez des problèmes, contactez Microsoft sur le [groupe Yammer de Microsoft Dynamics 365 Commerce Préversion](https://aka.ms/Dynamics365CommercePreviewYammer).

## <a name="prerequisites"></a>Conditions préalables

Les conditions préalables suivantes doivent être en place avant de pouvoir mettre en service votre environnement d'aperçu Commerce :

- Vous avez accès au Portail Microsoft Dynamics Lifecycle Services (LCS).
- Vous avez été accepté dans le programme de préversion de Dynamics 365 Commerce.
- Vous avez les autorisations nécessaires pour créer un projet pour **Préventes potentielles** ou **Migrer, créer des solutions et découvrir**.
- Vous êtes membre du rôle **Gestionnaire d'environnement** ou **Propriétaire du projet** dans le projet où vous mettrez l'environnement en service.
- Vous avez un accès en tant qu'administrateur à votre abonnement Microsoft Azure, ou contactez un administrateur d'abonnement qui peut effectuer les deux étapes qui nécessitent des autorisations d'administrateur en votre nom.
- Vous avez votre ID client Azure Active Directory (Azure AD) disponible.
- Vous avez créé un groupe de sécurité Azure AD à utiliser comme groupe d'administrateurs système de commerce électronique et son ID est disponible.
- Vous avez créé un groupe de sécurité Azure AD à utiliser comme groupe de modération des classements et évaluations et son ID est disponible. (Ce groupe de sécurité peut être le même que le groupe d'administration système de commerce électronique.)

### <a name="find-your-azure-ad-tenant-id"></a>Recherche de l'ID client Azure AD

Votre ID client Azure AD est un identificateur global unique (GUID) qui ressemble à cet exemple: **72f988bf-86f1-41af-91ab-2d7cd011db47**.

#### <a name="find-your-azure-ad-tenant-id-by-using-the-azure-portal"></a>Recherche de votre ID client Azure AD à l'aide du portail Azure

1. Connectez-vous au [portail Azure](https://portal.azure.com/).
1. Vérifiez que vous avez sélectionné le bon répertoire.
1. Dans le menu à gauche, sélectionnez **Azure Active Directory**.
1. Cliquez sur **Propriétés** sous **Gérer**. Votre ID client Azure AD apparaît sous **ID répertoire**.

#### <a name="find-your-azure-ad-tenant-id-by-using-openid-connect-metadata"></a>Recherche de votre ID client Azure AD à l'aide des métadonnées OpenID Connect

Créez une URL OpenID en remplaçant **\{VOTRE\_DOMAINE\}** par votre domaine, comme `microsoft.com`. Par exemple, `https://login.microsoftonline.com/{YOUR_DOMAIN}/.well-known/openid-configuration` va devenir `https://login.microsoftonline.com/microsoft.com/.well-known/openid-configuration`.

1. Accédez à l'URL OpenID qui contient votre domaine.

    Votre ID client Azure AD est dans plusieurs valeurs de propriété.

1. Recherchez **autorisation\_point de terminaison**et extrayez le GUID qui apparaît immédiatement après `login.microsoftonline.com/`.

### <a name="find-your-azure-ad-security-group-id"></a>Recherche de votre ID de groupe de sécurité Azure AD

L'ID de votre groupe de sécurité Azure AD est un GUID qui ressemble à cet exemple: **436ea7f5-ee6c-40c1-9f08-825c5811066a**.

Cette procédure suppose que vous soyez membre du groupe pour lequel vous essayez de trouver l'ID.

1. Ouvrez l'[Explorateur graphique](https://developer.microsoft.com/graph/graph-explorer#).
1. Cliquez sur **Connexion à Microsoft** et connectez-vous à l'aide de vos informations d'identification.
1. À gauche, sélectionnez **afficher plus d'exemples**.
1. Dans le volet droit, activez **Groupes**.
1. Fermez le volet droit.
1. Cliquez sur **tous les groupes auxquels j'appartiens**.
1. Dans le champ **Aperçu de la réponse**, recherchez votre groupe. L'ID du groupe de sécurité apparaît sous la propriété **id**.

## <a name="provision-your-commerce-preview-environment"></a>Mise en service de votre environnement d'aperçu Commerce

Ces procédures expliquent comment mettre en service un environnement d'aperçu Commerce. Une fois que vous les avez terminées avec succès, l'environnement d'aperçu de Commerce sera prêt pour la configuration. Toutes les activités décrites ici ont lieu dans le portail LCS.

> [!IMPORTANT]
> L'accès à l'aperçu est lié au compte LCS et à l'organisation que vous avez spécifiés dans votre application d'aperçu. Vous devez utiliser le même compte pour mettre en service l'environnement d'aperçu Commerce. Si vous devez utiliser un compte LCS ou un client différent pour l'environnement d'aperçu Commerce, vous devez fournir ces informations à Microsoft. Pour les coordonnées, voir le [support de l'environnement d'aperçu Commerce](#commerce-preview-environment-support) plus loin dans cette rubrique.

### <a name="grant-access-to-e-commerce-applications"></a>Accorder l'accès aux applications de commerce électronique

> [!IMPORTANT]
> La personne qui se connecte doit être un administrateur du client Azure AD avec l'ID client Azure AD. Si cette étape n'est pas terminée avec succès, les étapes de mise en service restantes échoueront.

Pour autoriser les applications de commerce électronique à accéder à votre abonnement Azure, procédez comme suit.

1. Assemblez une URL au format suivant :

    `https://login.windows.net/{AAD_TENANT_ID}/oauth2/authorize?client_id=fbcbf727-cd18-4422-a723-f8274075331a&response_type=code&redirect_uri=https://sb.manage.commerce.dynamics.com/_commerce/Consent&response_mode=query&prompt=admin_consent&state=12345`

1. Copiez et collez l'URL dans votre navigateur ou votre éditeur de texte et remplacez **\{ID\_CLIENT\_AAD\}** par votre ID client Azure AD. Ensuite, ouvrez l'URL.
1. Dans la boîte de dialogue de connexion à Azure AD, connectez-vous et confirmez que vous souhaitez accorder à **Dynamics 365 Commerce (Aperçu)** l'accès à votre abonnement. Vous êtes redirigé vers une page qui indique si l'opération a réussi.

### <a name="confirm-that-preview-features-are-available-and-turned-on-in-lcs"></a>Confirmation que les fonctionnalités de préversion sont disponibles et activées dans LCS

Pour confirmer que les fonctionnalités de préversion sont disponibles et activées dans LCS, procédez comme suit.

1. Connectez-vous au [Portail LCS](https://lcs.dynamics.com) en utilisant le même compte LCS que vous avez utilisé pour demander l'accès à l'aperçu.
1. Sur la page d'accueil de LCS, faites défiler tout à droite et cliquez sur la vignette **Gestion des fonctionnalités d'aperçu**.

    ![Vignette Gestion des versions préliminaires](./media/preview1.png)

1. Faites défiler jusqu'à **Fonctionnalités d'aperçu privé** et confirmez que les fonctionnalités suivantes sont disponibles et activées :

    - Évaluation du commerce électronique
    - Environnements du programme de préversion de Commerce

    ![Fonctionnalités d'aperçu privé](./media/preview2.png)

1. Si ces fonctionnalités n'apparaissent pas dans la liste, contactez Microsoft et fournissez votre adresse e-mail professionnelle, votre compte LCS et les détails du client. Pour les coordonnées, voir la section [support de l'environnement d'aperçu Commerce](#commerce-preview-environment-support).

### <a name="create-a-new-project"></a>Créer un nouveau projet

Pour créer un projet dans LCS, procédez comme suit.

1. Sur la page d'accueil LCS, sélectionnez le signe plus (**+**) pour créer un projet.
1. Dans le volet droit, procédez comme suit :

    - Si vous êtes un partenaire, cliquez sur **Migrer, créer des solutions et découvrir**.
    - Si vous êtes un client, cliquez sur **Préventes potentielles**.

1. Entrer une nom, une description et un secteur d'activité.
1. Dans le champ **Nom du produit**, cliquez sur **Dynamics 365 Retail**.
1. Dans le champ **Version du produit**, cliquez sur **Dynamics 365 Retail**.
1. Dans le champ **Méthodologie**, sélectionnez **Méthodologie de mise en œuvre de Dynamics Retail**.
1. Facultatif : Vous pouvez importer les rôles et les utilisateurs d'un projet existant.
1. Sélectionnez **Créer**. La vue du projet s'affiche.

### <a name="add-the-azure-connector"></a>Ajouter le connecteur Azure

Pour ajouter le connecteur Azure à votre projet LCS, procédez comme suit.

1. Utilisez l'une des procédures suivantes :

    - Si vous êtes partenaire, sélectionnez la vignette **Paramètres du projet** à l'extrême droite.
    - Si vous êtes un client, cliquez sur **Paramètres du projet** dans menu principal.

1. Sélectionnez **Connecteurs Azure**.
1. Cliquez sur **Ajouter** pour ajouter le connecteur Azure.
1. Entrez un nom.
1. Entrez votre ID d'abonnement Azure.
1. Activez l'option **Configurer pour utiliser ARM (Azure Resource Manager)**.
1. Vérifiez que la valeur du **Domaine du locataire AAD de l'abonnement Azure (ou ID)** est correcte. Contactez l'administrateur d'abonnements Azure, comme requis.
1. Sélectionnez **Suivant**.
1. Suivez les instructions sur la page pour accorder l'accès aux applications requises à votre abonnement. Contactez l'administrateur d'abonnements Azure, comme requis.

    1. Connectez-vous au [portail Azure](https://portal.azure.com/).
    1. Assurez-vous que le répertoire correct est sélectionné, puis, dans le menu de gauche, cliquez sur **Abonnements**.
    1. Recherchez l'abonnement approprié dans la liste et sélectionnez-le. Utilisez la fonctionnalité de recherche si nécessaire.
    1. Dans le menu, sélectionnez **Contrôle d'accès (IAM)**.
    1. À droite, cliquez sur **Ajouter** sous **Ajouter une affectation de rôle**. Le volet **Ajouter une affectation de rôle** s'affiche.
    1. Dans le champ **Rôle**, sélectionnez **Contributeur**.
    1. Dans le champ **Attribuer l'accès à**, laissez la valeur par défaut **Utilisateur, groupe ou principal de service Azure AD**.
    1. Sous **Sélectionner**, entrez **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.
    1. Sélectionnez **Services de déploiement Dynamics \[activé pour WsFed\]** dans la liste.
    1. Sélectionnez **Enregistrer**.

1. Sélectionnez **Suivant**.
1. Suivez les instructions sur la page pour accorder l'accès aux applications requises à votre abonnement. Contactez l'administrateur d'abonnements Azure, comme requis.
1. Sélectionnez **Suivant**.
1. Dans le champ **Région Azure**, choisissez **Est des États-Unis**, **Est des États-Unis 2**, **Ouest des États-Unis** ou **Ouest des États-Unis 2**.
1. Sélectionner **Connecter**. Votre connecteur Azure doit apparaître dans la liste.

### <a name="import-the-commerce-preview-demo-base-extension"></a>Importation de l'extension de base de démonstration de l'aperçu de Commerce

Pour importer l'extension de base de démonstration de l'aperçu de Commerce dans votre projet, procédez comme suit.

1. Ouvrez la page d'accueil de votre projet en sélectionnant le nom du projet en haut.
1. Utilisez l'une des procédures suivantes :

    - Si vous êtes partenaire, cliquez sur la vignette **Bibliothèque d'actifs** à l'extrême droite.
    - Si vous êtes un client, cliquez sur **Bibliothèque d'actifs** dans menu principal.

1. Dans la liste de gauche, cliquez sur **Module déployable par logiciel**.
1. Sélectionnez **Importer**.
1. Sous **Bibliothèque d'actifs partagés**, sélectionnez **Extension de base de démonstration d'aperçu de Commerce** dans la liste des actifs.
1. Cliquez sur **Prélever**. Vous êtes renvoyé vers la Bibliothèque d'actifs et vous devez voir l'extension dans la liste.

L'illustration suivante montre les actions à effectuer sur la page **Bibliothèque d'actifs** de LCS.

![Importation de l'extension de base de démonstration de l'aperçu de Commerce](./media/import.png)

### <a name="deploy-the-environment"></a>Déploiement de l'environnement

Pour déployer l'environnement, procédez comme suit.

> [!NOTE]
> Vous n'aurez peut-être pas à effectuer les étapes 6, 7 et/ou 8, car les pages comportant une seule option sont ignorées. Lorsque vous êtes dans la vue **Paramètres d'environnement**, confirmez que le texte **Dynamics 365 Commerce (Aperçu) - Démonstration (10.0.6 avec Platform Update 30)** apparaît directement au-dessus du champ **Nom de l'environnement**. Voir l'illustration qui apparaît après l'étape 8.

1. Sur le menu principal, sélectionnez **Environnements hébergés dans le cloud**.
1. Cliquez sur **Ajouter** pour ajouter un environnement.
1. Dans le champ **Version de l'application**, cliquez sur **10.0.6**.
1. Dans le champ **Version de la plateforme**, cliquez sur **Platform Update 30**.

    ![Sélection des versions d'application et de plateforme](./media/project1.png)

1. Sélectionnez **Suivant**.
1. Sélectionner **Démonstration** comme topologie de l'environnement.

    ![Sélection de la topologie de l'environment 1](./media/project2.png)

1. Sélectionnez **Dynamics 365 Commerce (Aperçu) - Démonstration** comme topologie de l'environnement. Si vous avez configuré un seul connecteur Azure plus tôt, utilisez-le pour l'environnement. Si vous avez configuré plusieurs connecteurs Azure, vous pouvez sélectionner le connecteur à utiliser : **Est des États-Unis**, **Est des États-Unis 2**, **Ouest des États-Unis**, ou **Ouest des États-Unis 2**. (Pour de meilleures performances de bout en bout, nous vous recommandons de sélectionner **Ouest des États-Unis 2**.)

    ![Sélection de la topologie de l'environment 2](./media/project3.png)

1. Sur la page **Déployer l'environnement**, entrez un nom d'environnement. Laissez les paramètres avancés inchangés.

    ![Page Déployer l'environnement](./media/project4.png)

1. Ajustez la taille de la machine virtuelle selon vos besoins. (Nous recommandons l'unité de gestion de stock de machine virtuelle \[SKU\] **D13 v2**.)
1. Passez en revue les conditions de prix et de licence, puis cochez la case pour indiquer que vous les acceptez.
1. Sélectionnez **Suivant**.
1. Dans la page de confirmation du déploiement, après avoir vérifié les détails sont corrects, cliquez sur **Déployer**. Vous revenez à la vue **Environnements hébergés sur le cloud** et votre environnement doit apparaître dans la liste.

    Votre environnement demandé s'affiche comme mis en file d'attente, puis en cours de déploiement. Les workflows d'environnement prendront un certain temps à se terminer. Par conséquent, revenez après environ six à neuf heures.

1. Avant de continuer, vérifiez que le statut de votre environnement est **Déployé**.

### <a name="initialize-rcsu"></a>Initialiser RCSU

Pour initialiser une RCSU, procédez comme suit.

1. Dans la vue **Environnements hébergés dans le cloud**, sélectionnez votre environnement dans la liste.
1. Dans les informations de l'environnement à droite, cliquez sur **Détails complets**. La vue des détails d'environnement s'affiche.
1. Sous **Fonctions d'environnement**, cliquez sur **Gérer**.
1. Sur l'onglet **Vente au détail**, cliquez sur **Initialiser**. La vue des paramètres d'initialisation de RCSU s'affiche.
1. Dans le champ **Région**, choisissez **Est des États-Unis**, **Est des États-Unis 2**, **Ouest des États-Unis** ou **Ouest des États-Unis 2**.
1. Dans le champ **Version**, sélectionnez **Spécifier une version** dans la liste, puis spécifiez **9.16.19262.5** dans le champ qui apparaît. Assurez-vous de spécifier la version exacte indiquée ici. Sinon, vous devrez mettre à jour l'URSC avec la bonne version plus tard.
1. Activez l'option **Appliquer l'extension**.
1. Dans la liste des extensions, sélectionnez **Numéro de base de démonstration de version d'évaluation de Commerce**.
1. Sélectionnez **Initialiser**.
1. Dans la page de confirmation du déploiement, après avoir vérifié les détails sont corrects, cliquez sur **Oui**. Vous êtes renvoyé à la vue **Gestion de la vente au détail** où l'onglet **Vente au détail** est activé. Votre RCSU a été mis en file d'attente pour la mise en service.
1. Avant de continuer, vérifiez que le statut de votre RCSU est **Réussite**. L'initialisation prend environ deux à cinq heures.

### <a name="initialize-e-commerce"></a>Initialiser e-Commerce

Pour initialiser du commerce électronique, procédez comme suit.

1. Sur l'onglet **Commerce électronique (préversion)**, vérifiez le consentement de l'aperçu, puis sélectionnez **Paramétrer**.
1. Dans le champ **Nom du client de commerce électronique**, entrez un nom. Toutefois, notez que ce nom sera visible dans certaines URL pointant vers votre instance de commerce électronique.
1. Dans le champ **Nom Retail Cloud Scale Unit**, sélectionnez votre RCSU dans la liste. (La liste ne doit avoir qu'une seule option.)

    Le champ **Géographie du commerce électronique** est défini automatiquement et sa valeur ne peut pas être modifiée.

1. Sélectionnez **Suivant** pour continuer.
1. Dans le champ **Noms d'hôtes pris en charge**, entrez un domaine valide, tel que `www.fabrikam.com`.
1.  Dans le champ **Groupe de sécurité AAD pour l'administrateur système**, entrez les premières lettres du nom du groupe de sécurité que vous souhaitez utiliser. Sélectionnez l'icône de loupe pour afficher les résultats de la recherche. Sélectionnez un groupe de sécurité dans la liste.
2.  Dans le champ **Groupe de sécurité AAD pour le modérateur de classements et d'évaluations**, entrez les premières lettres du nom du groupe de sécurité que vous souhaitez utiliser. Sélectionnez l'icône de loupe pour afficher les résultats de la recherche. Sélectionnez un groupe de sécurité dans la liste.
1. Laissez l'option **Activer le service de classements et évaluations** activée.
1. Si vous avez déjà terminé l'étape de consentement de Microsoft Azure Active Directory (Azure AD) comme décrit dans la section « Accorder l'accès aux applications de commerce électronique », cochez la case pour confirmer votre consentement. Si vous n'avez pas encore terminé cette étape, vous devez le faire avant de procéder à l'initialisation. Sélectionnez le lien dans le texte à côté de la case à cocher pour ouvrir la boîte de dialogue de consentement et terminer l'étape.
1. Sélectionnez **Initialiser**. Vous êtes renvoyé à la vue **Gestion de la vente au détail** où l'onglet **Commerce électronique (aperçu)** est activé. L'initialisation du commerce électronique a commencé.
1. Avant de continuer, attendez que le statut de l'initialisation du commerce électronique soit **Initialisation réussie**.
1. Sous **Liens** en bas à droite, notez les URL des liens suivants :

    * **Site de commerce électronique** - Lien vers la racine de votre site de commerce électronique.
    * **Outil de gestion de site de commerce électronique** - Lien vers l'outil de gestion du site.

## <a name="commerce-preview-environment-support"></a>Support d'un environnement d'aperçu Commerce

Si vous rencontrez des problèmes lors de l'exécution des étapes de mise en service, visitez le [groupe Yammer de la version d'évaluation de Microsoft Dynamics 365 Commerce](https://aka.ms/Dynamics365CommercePreviewYammer) pour obtenir de l'aide.

Si vous rencontrez des problèmes lorsque vous essayez d'accéder au groupe Yammer, vous pouvez contacter Microsoft par e-mail à l'adresse <Dynamics365Commerce@microsoft.com>. Cette adresse e-mail n'est pas activement surveillée. Par conséquent, attendez-vous à un retard dans la réponse.

## <a name="next-steps"></a>Étapes suivantes

Pour poursuivre le processus de mise en service et de configuration de votre environnement d'aperçu Commerce, consultez [Configurer un environnement d'aperçu Commerce](cpe-post-provisioning.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble d'un environnement d'évaluation Commerce](cpe-overview.md)

[Configurer un environnement d'évaluation Commerce](cpe-post-provisioning.md)

[Configurer des fonctionnalités facultatives pour un environnement d'évaluation Commerce](cpe-optional-features.md)

[FAQ relative à l'environnement d'évaluation Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portail Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Site web Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Ressources d'aide pour Dynamics 365 Retail](../retail/index.md)
