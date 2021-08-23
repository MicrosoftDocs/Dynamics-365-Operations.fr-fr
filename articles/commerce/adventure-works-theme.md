---
title: Présentation du thème Adventure Works
description: Cette rubrique donne un aperçu du thème Adventure Works et décrit comment l'appliquer aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 5bade39b1b327a0784272669ce074d9762a318c2cad6d4105f0d186c91d2593f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733226"
---
# <a name="adventure-works-theme-overview"></a>Présentation du thème Adventure Works

[!include [banner](includes/banner.md)]

Cette rubrique donne un aperçu du thème Adventure Works et décrit comment l'appliquer aux pages du site dans Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce a un thème pour le e-commerce nommé Adventure Works. Le thème Adventure Works présente des produits sportifs et récréatifs et est optimisé pour une expérience de narration enrichie et améliorée. Il offre une apparence moderne, de nouvelles mises en page et des effets d'animation pour créer une expérience d'achat en ligne immersive et engageante pour les clients de l'e-commerce.

## <a name="trial-environments-in-commerce"></a>Environnements d'essai dans Commerce

Pour voir à quoi ressemble le thème Adventure Works lorsqu'il est déployé pour les sites B2C et B2B, visitez les sites d'essai suivants :

- [Site Adventure Works B2C](https://www.adventure-works.com/)
- [Site Adventure Works B2B](https://www.adventure-works.com/business)

## <a name="theme-capabilities"></a>Fonctionnalités du thème

Le thème Adventure Works propose les nouvelles fonctionnalités suivantes :

- Le module de lecteur vidéo prend désormais en charge les fonctionnalités de titre, de paragraphe et de liens pour une narration supplémentaire.
- Les transitions de contenu sont améliorées grâce à l'animation.
- L'action « Ajouter au panier » appelle le mini panier au lieu de fournir une notification.
- Le module d'affichage rapide est un volet qui se glisse dans les fenêtres de PC de bureau et de mobiles.
- Il offre de nouvelles dispositions pour les pages du site. 
- Le contenu marketing peut être configuré pour le panier et le mini panier lorsqu'ils sont vides.
- Le mini panier peut afficher des messages promotionnels, tels que « Livraison gratuite pour les commandes de plus de 50 USD ».
- Les fiches descriptives sont affichées sur les pages de recherche et de catégorie.

Le thème Adventure Works comprend désormais les modules de narration suivants dans la bibliothèque de modules Commerce :

- [Module de liste de vignettes](tile-list-module.md)
- [Module de fonctionnalités interactives](interactive-feature-module.md)
- [Module Image actif](active-image-module.md)
- [Module d’abonnement](subscribe-module.md)
- [Module de liste d’images](image-list-module.md)

Le thème Adventure Works est entièrement réactif et offre une expérience optimisée pour les fenêtres de PC de bureau, de mobiles et de tablettes.

> [!IMPORTANT]
> Le thème Adventure Works et les nouveaux modules sont disponibles à partir de la version 10.0.20 de Dynamics 365 Commerce.

L'illustration suivante montre un exemple de page d'accueil qui utilise le thème Adventure Works.

![Exemple de page d'accueil utilisant le thème Adventure Works](./media/aw_b2c.PNG)

L'illustration suivante montre un exemple de page de liste qui utilise le thème Adventure Works.

![Exemple de page de liste utilisant le thème Adventure Works](./media/Aw_list.PNG)

L'illustration suivante montre un exemple de page de détails des produits qui utilise le thème Adventure Works.

![Exemple de page de détails des produits utilisant le thème Adventure Works](./media/aw_pdp.PNG)

## <a name="use-the-adventure-works-theme-for-b2b-sites"></a>Utilisez le thème Adventure Works pour les sites B2B

Le thème Adventure Works est également un thème de référence pour les sites business-to-business (B2B). Tous les modules et workflows B2B sont présentés dans le thème Adventure Works. Pour plus d’informations sur la configuration d’un site B2B, voir [Configuration d'un site B2B](./b2b/set-up-b2b-site.md).

L'illustration suivante montre un exemple de page d'accueil B2B qui utilise le thème Adventure Works.

![Exemple de page d'accueil B2B utilisant le thème Adventure Works](./media/aw_b2b.PNG)

## <a name="theme-extensions"></a>Extensions de thème

Le thème Adventure Works comprend plusieurs extensions de thème, telles que les extensions **Afficher les extensions** et **Définition des modules**. Le thème Adventure Works peut être utilisé comme thème de référence pour créer des extensions similaires. Par exemple, la page de liste du thème Adventure Works est implémentée en tant qu'extension de vue dotée d'un affinement horizontal. (En revanche, un affinement du volet de gauche est utilisé dans le thème Fabrikam.)

De même, d'autres modules incluent des extensions de définition de module. Par exemple, le [module d'icône de panier](cart-icon-module.md) comprend deux autres emplacements **Panier vide** et **Contenu promotionnel** qui sont implémentés à l'aide d'extensions de définition de module. De plus, une nouvelle propriété **Logo mobile** a été ajoutée au module d'en-tête pour prendre en charge un logo sur les fenêtres mobiles. Cette propriété est implémentée en tant qu'extension de définition de module d'en-tête.

Pour plus d'informations sur les extensions de thème, consultez [Extensions de thème](e-commerce-extensibility/theme-module-extensions.md).

## <a name="install-the-adventure-works-theme"></a>Installer le thème Adventure Works

Pour plus d'informations sur l'installation du thème Adventure Works, consultez [Installer le thème Adventure Works](install-adventure-works.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Module de liste de vignettes](tile-list-module.md)

[Module de fonctionnalité interactive](interactive-feature-module.md)

[Module Image active](active-image-module.md)

[Module d'abonnement](subscribe-module.md)

[Module de liste d'images](image-list-module.md)

[Extensions de thème](e-commerce-extensibility/theme-module-extensions.md)

[Module Icône de panier](cart-icon-module.md)

[Mettre en place un site e-commerce B2B](./b2b/set-up-b2b-site.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
