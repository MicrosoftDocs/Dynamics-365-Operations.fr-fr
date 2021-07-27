---
title: Présentation du site d’e-commerce
description: Cette rubrique fournit une vue d’ensemble de la prise en charge des sites d’e-commerce dans Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 11/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b7050f954116213f700e4a2b3326547f4d070674
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6353010"
---
# <a name="e-commerce-site-overview"></a>Présentation du site d’e-commerce

[!include [banner](includes/banner.md)]

Cette rubrique fournit une vue d’ensemble de la prise en charge des sites d’e-commerce dans Microsoft Dynamics 365 Commerce. Il comprend des informations sur la façon dont les boutiques en ligne d’e-commerce sont initialisées et gérées dans Dynamics 365 Commerce. Elle fournit également des liens vers plus d’informations sur les magasins en ligne et des informations sur la paramétrage et de configuration d’un site d’e-commerce. Bien que ce sujet couvre la plupart des bases, il ne couvre pas tout ce qui est nécessaire pour configurer un site d’e-commerce de production. Des sujets plus avancés peuvent être trouvés dans la documentation Dynamics 365 Commerce.

## <a name="online-store-channel"></a>Canal de magasin en ligne

Avant de générer votre site, au moins un canal de magasin en ligne doit être créé dans Dynamics 365 Commerce. Pour plus d’informations, consultez [Paramétrer un canal en ligne](channel-setup-online.md). 

Dans Dynamics 365 Commerce, vous utilisez un canal de magasin en ligne pour établir les produits, les prix, les langues, les méthodes de paiement, les modes de livraison, les centres de traitement des commandes et d’autres aspects de l’expérience en ligne qui devraient être disponibles pour vos clients.

Un seul canal de magasin en ligne doit être créé avant de pouvoir commencer Dynamics 365 Commerce. Cependant, un seul site d’e-commerce peut offrir une expérience en ligne à plusieurs magasins en ligne. Par exemple, si plusieurs magasins en ligne sont configurés pour prendre en charge différentes zones géographiques, un seul ensemble de pages d’e-commerce peut être utilisé pour fournir les expériences uniques définies par chaque magasin. Pour plus d’informations sur la configuration d’un site pour prendre en charge plusieurs magasins en ligne, consultez [Association d’un site en ligne à un canal](associate-site-online-store.md).

Une fois le magasin en ligne créé, il peut être associé au site Dynamics 365 Commerce qui servira de vitrine en ligne. Pour plus d’informations sur les magasins en ligne et comment les configurer, consultez [Créer des magasins en ligne](/dynamics365/unified-operations/retail/online-stores).

## <a name="deploy-a-new-e-commerce-tenant"></a>Déployer un nouveau client e-commerce

Lors de l’initialisation d’un site d’e-commerce, vous êtes invité à entrer un nom de domaine. Pour plus d’informations sur les domaines dans Commerce, consultez [Configurer votre nom de domaine](configure-your-domain-name.md) et [Domaines dans Dynamics 365 Commerce](domains-commerce.md). Pour déployer un nouveau client e-commerce à l’aide de [Microsoft Dynamics Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide), suivez les étapes de [Déployer un nouveau locataire e-commerce](deploy-ecommerce-site.md). Une fois votre locataire d’e-commerce configuré dans LCS, un lien vers le constructeur de site Commerce sera fourni. Vous pouvez ensuite utiliser le générateur de site Commerce pour initialiser et configurer vos sites d’e-commerce.

## <a name="initialize-your-e-commerce-site"></a>Initialiser votre site d’e-commerce

Lorsque vous démarrez le générateur de site Commerce à partir de LCS, la page **Sites** apparaît. Cette page comprend deux sites préconfigurés, **par défaut** et **fabrikam**, comme indiqué dans l’exemple de l’illustration suivante.

![Page Sites dans le générateur de site Commerce.](media/e-commerce-site-01.png)

Lorsque vous sélectionnez l’un de ces sites, vous êtes invité à sélectionner un nom de domaine, un canal de magasin en ligne par défaut, une langue prise en charge pour le canal sélectionné et un chemin. Si un seul canal est utilisé, vous pouvez laisser le chemin vide. D’autres canaux ou langues de magasin en ligne peuvent être configurés ultérieurement dans le générateur de site Commerce. Chaque canal ou langue supplémentaire nécessitera un chemin unique. Par exemple, vous disposez de deux canaux en ligne associés à un seul site et le nom de domaine du site est `www.fabrikam.com`. Dans ce cas, le chemin pour un canal peut être la valeur par défaut qui n’a pas de chemin (`https://www.fabrikam.com`), et le deuxième canal peut être défini sur un nouveau chemin, tel que **site2**, qui aura l’URL `https://www.fabrikam.com/site2`. L’illustration suivante montre un exemple de boîte de dialogue d’initialisation de site dans le générateur de site Commerce.

![Boîte de dialogue d’initialisation du site dans le générateur de site Commerce.](media/e-commerce-site-02.png)

La page **Sites** comprend également un bouton **Nouveau site**. La boîte de dialogue qui s’affiche lorsque vous sélectionnez ce bouton ressemble à la boîte de dialogue d’initialisation du site, mais elle est utilisée pour créer un site. Les nouveaux sites sont vides. Ils n’incluent pas les mêmes modèles, fragments, pages et images par défaut fournis avec les sites **Par défaut** et **fabrikam**. Cependant, selon vos besoins, vous pouvez ouvrir un ticket de support pour demander qu’une copie du contenu par défaut soit ajoutée à un nouveau site vierge. Pour plus d’informations, voir [Créer un site d’e-commerce](create-ecommerce-site.md).

Après l’initialisation d’un nouveau site, la page **Accueil** du générateur de site Commerce apparaît. Cette page comprend des liens vers des actions courantes et du contenu de guidage, comme indiqué dans l’exemple de l’illustration suivante.

![Liens sur la page d’accueil dans le générateur de site Commerce.](media/e-commerce-site-03.png)

## <a name="modify-online-store-channels-or-add-online-store-channels-to-an-e-commerce-site"></a>Modifier les canaux de magasin en ligne ou ajouter des canaux de magasin en ligne à un site d’e-commerce

Après la création d’un site d’e-commerce, vous pouvez modifier le canal auquel il est associé en suivant les étapes de [Associer un site d’e-commerce à un canal en ligne](associate-site-online-store.md). L’exemple de l’illustration suivante montre comment un numéro d’unité de commande de canal (NUC) peut être modifié sur la page **Canaux** (**Paramètres du site \> Canaux**). Après avoir effectué une modification, assurez-vous de sélectionner **Enregistrer et publier**. De cette manière, vous vous assurez que la modification est publiée.

![Page Canaux dans le générateur de site Commerce.](media/e-commerce-site-04.png)

Vous pouvez ajouter de nouveaux canaux en sélectionnant **Ajouter un canal**. Pour ajouter de nouvelles langues à un canal, sélectionnez le canal, puis sélectionnez **Ajouter un paramètre régional** dans la boîte de dialogue de canal qui apparaît. Pour que les paramètres régionaux puissent apparaître dans la boîte de dialogue, ils doivent être préconfigurés pour le canal du magasin en ligne au siège de Commerce.

![Boîte de dialogue Canal dans le générateur de site Commerce.](media/e-commerce-site-05.png)

## <a name="set-up-an-azure-b2c-tenant"></a>Configurer un locataire Azure B2C

Dynamics 365 Commerce fait appel à Azure Active Directory (Azure AD) entreprise-client (B2C) pour prendre en charge les flux d’informations d’identification et d’authentification des utilisateurs. Pour plus d’informations sur la configuration de votre locataire Azure B2C, voir [Configurer un locataire B2C dans Commerce](set-up-b2c-tenant.md), [Configurer des pages personnalisées pour les connexions des utilisateurs](custom-pages-user-logins.md), et [Configurer plusieurs locataires B2C dans un environnement Commerce](configure-multi-b2c-tenants.md).

## <a name="overview-of-the-default-site-pages"></a>Vue d’ensemble des pages du site par défaut

Les sites **Par défaut** et **fabrikam** incluent des modèles, des fragments et des pages préconfigurés pour vous aider à démarrer. Pour plus d’informations, voir les rubriques suivantes :

- [Vue d’ensemble de la page d’accueil](quick-tour-home-page.md)
- [Vue d’ensemble de la page détaillée du produit](quick-tour-pdp.md)
- [Vue d’ensemble des pages du panier et du paiement](quick-tour-cart-checkout.md)
- [Vue d’ensemble des pages de gestion de compte](quick-tour-account-management.md)

## <a name="manage-site-settings"></a>Gérer les paramètres de site

Pour plus d’informations sur la gestion des paramètres de votre site, voir les rubriques suivantes :

- [Gestion des utilisateurs et des rôles d’e-commerce](manage-ecommerce-users-roles.md)
- [Considérations relatives à l’optimisation du référencement d’un site auprès d’un moteur de recherche (SEO) pour le site](/search-engine-optimization-considerations.md)
- [Gérer la stratégie de sécurité de contenu (CSP)](manage-csp.md)
- [Sélectionner un thème pour le site](select-site-theme.md)

## <a name="manage-site-content"></a>Gérer le contenu du site

Pour plus d’informations sur la gestion d contenu du site, voir les rubriques suivantes :

- [Glossaire sur le modèle de page](page-elements-overview.md)
- [États et cycle de vie des documents](document-states-overview.md)
- [Modèles et disposition](templates-layouts-overview.md)
- [Utiliser des fragments](work-with-fragments.md)
- [Utiliser des modules](work-with-modules.md)
- [Vue d’ensemble de la gestion des actifs numériques](dam-overview.md)
- [Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

## <a name="additional-resources"></a>Ressources supplémentaires

[Créer un site d’e-commerce](create-ecommerce-site.md)

[Déploiement d’un nouveau site d’e-commerce](deploy-ecommerce-site.md)

[Association d’un site en ligne avec un canal](associate-site-online-store.md)

[Configuration du nom de domaine](configure-your-domain-name.md)

[Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)](add-cdn-support.md)

[Activation de la détection du magasin selon l’emplacement](enable-store-detection.md)

[Paramétrer des pages personnalisées pour les ouvertures de session utilisateur](custom-pages-user-logins.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]