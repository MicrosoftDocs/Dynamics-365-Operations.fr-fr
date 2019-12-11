---
title: Module En-tête
description: Cette rubrique couvre les modules d'en-tête et décrit leur création dans Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: d393701dacb88ab03a4b56724d93c794da6bb5c8
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697273"
---
# <a name="header-module"></a>Module En-tête

[!include [banner](../includes/preview-banner.md)] [!include [banner](includes/banner.md)]

Cette rubrique couvre les modules d'en-tête et décrit leur création dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un module d'en-tête est un conteneur spécial utilisé pour héberger tous les modules qui s'affichent dans l'en-tête d'une page. Par exemple, il peut comprendre votre logo de site, des liens vers la hiérarchie de navigation, des liens vers d'autres pages du site, et la barre de recherche.

Un module d'en-tête est automatiquement optimisé pour l'appareil sur lequel le site est affiché (autrement dit, un périphérique de bureau ou un appareil mobile). Par exemple, sur un appareil mobile, la barre de navigation est réduite en un bouton **Menu** (qui est parfois appelé *menu hamburger*).

## <a name="properties-of-a-header"></a>Propriétés d'un en-tête

Comme les conteneurs génériques, un module d'en-tête prend en charge les propriétés pour l'**en-tête** et la **largeur**.

Un module d'en-tête a plusieurs emplacements. Par exemple, des emplacements pour un message d'information, un menu de navigation, le logo, une barre de recherche, une icône de panier, une icône de liste de souhaits, et des informations sur le compte. Chaque emplacement prend en charge un ensemble spécifique de modules.

## <a name="modules-that-are-available-in-a-header-module"></a>Modules disponibles dans le module d'en-tête

Les modules suivants peuvent être utilisés dans un module d'en-tête :

- **Menu de navigation** – Le menu de navigation représente la hiérarchie de navigation du canal et d'autres liens de navigation statiques. La hiérarchie de navigation du canal peut être configurée dans Dynamics 365 Retail. Les articles configurés s'affichent alors comme navigation d'en-tête. En outre, les liens de navigation statiques peuvent être configurés, et des liens associés à d'autres pages du site de commerce électronique peuvent être fournis. L'en-tête lui-même peut être aligné à gauche, droite, ou centre.
- **Icône de panier** – L'icône du panier est une icône spéciale qui représente le panier. Elle s'affiche dans l'en-tête et indique le nombre d'articles dans le panier. Un lien vers la page de panier doit accompagner l'icône du panier, de sorte que les clients puissent être redirigés vers la page de panier lorsqu'ils interagissent avec l'icône.
- **Icône de liste de souhaits** – L'icône de liste de souhaits s'affiche dans l'en-tête et indique le nombre d'articles ajoutés à la liste de souhaits du client. Un lien vers la page de liste de souhaits doit accompagner cette icône, de sorte que les clients puissent être redirigés vers la page de liste de souhaits lorsqu'ils interagissent avec l'icône.
- **Module de connexion** – Le module de connexion s'affiche dans l'en-tête. Il permet aux clients de se connecter à son compte ou de s'inscrire pour un compte. Si le client est déjà connecté, le module peut être configuré pour afficher des liens sur la page du compte, la page Historique des commandes, ou une autre page.
- **Module Logo** – Ce module affiche le logo qui représente le détaillant et la marque. Il s'agit d'une image avec un lien. Le lien est généralement configuré de sorte qu'il redirige vers la page d'accueil, afin que les clients puissent rapidement revenir à la page d'accueil des pages du site.
- **Alerte** – Une alerte s'affiche dans l'en-tête et est utilisée pour afficher un message intégré qui s'applique à toutes les pages du site. Par exemple, une alerte peut afficher un message, par exemple « Les soldes annuelles se terminent dans 2 jours ».
- **Barre de recherche** – La barre de recherche permet aux utilisateurs d'entrer des termes de recherche afin de rechercher des produits. Le module doit être configuré avec l'URL de la page de résultats de la recherche. Le paramètre de chaîne de requête peut être configuré (la valeur par défaut est **« q »**). La barre de recherche a un emplacement de suggestion automatique où le module de suggestion automatique doit être ajouté.
- **Suggestion automatique** – Le module de suggestion automatique affiche des résultats suggérés automatiquement. Ces résultats peuvent être des mots clés, des produits, ou des catégories si le terme de recherche est trouvé.

## <a name="create-a-header-module"></a>Créer un module d'en-tête

Pour créer un module d'en-tête, procédez comme suit :

1. Créez un fragment de page qui inclut un module d'en-tête.
1. Ajoutez les modules aux emplacements dans le module d'en-tête.
1. Mettez à jour les paramètres pour chaque module.
1. Enregistrez le fragment de page. 
1. Archivez la page, et publiez-la.

Pour vous assurer qu'un en-tête apparaît sur chaque page, suivez ces étapes pour chaque modèle de page créé pour le site.

1. Sur la page par défaut, ajoutez le fragment de page contenant le module d'en-tête à l'en-tête de l'emplacement principal.
1. Enregistrez le modèle. 
1. Archivez le modèle, et publiez-le.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Container](add-container-module.md)

[Module Zone d'achat](add-buy-box.md)

[Module Panier](add-cart-module.md)

[Module Paiement](add-checkout-module.md)

[Module Confirmation de commande](order-confirmation-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)
