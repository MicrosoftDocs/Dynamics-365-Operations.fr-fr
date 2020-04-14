---
title: Module d'en-tête
description: Cette rubrique couvre les modules d'en-tête et décrit comment créer des en-têtes de page dans Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: efadd19681bbb21ea5b2b469e55bc6f4b0535046
ms.sourcegitcommit: 34e543e807ac8790597f522fe3b4f0266cf4ee56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/24/2020
ms.locfileid: "3025656"
---
# <a name="header-module"></a>Module d'en-tête


[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules d'en-tête et décrit comment créer des en-têtes de page dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Dans Dynamics 365 Commerce, un en-tête de page comprend plusieurs modules, tels que les modules d'en-tête, de menu de navigation, de recherche, de bannière promotionnelle et de consentement aux cookies. 

Le module d'en-tête comprend un logo de site, des liens vers la hiérarchie de navigation, des liens vers d'autres pages du site, un symbole de panier, un symbole de liste de souhaits, des options de connexion et la barre de recherche. Un module d'en-tête est automatiquement optimisé pour l'appareil sur lequel le site est affiché (autrement dit, pour un périphérique de bureau ou un appareil mobile). Par exemple, sur un appareil mobile, la barre de navigation est réduite en un bouton **Menu** (qui est parfois appelé *menu hamburger*).

## <a name="properties-of-a-header-module"></a>Propriétés d'un module d'en-tête

Un module d'en-tête prend en charge les propriétés suivantes : **Image de logo**, **Lien vers le logo** et **Liens de mon compte**. 

Les propriétés **Image de logo** et **Lien vers le logo** sont utilisées pour définir un logo sur la page. Pour plus d'informations, voir [Ajouter un logo](add-logo.md). 

La propriété **Liens de mon compte** peut être utilisée pour définir les pages de compte pour lesquelles le propriétaire du site souhaite afficher des liens rapides dans l'en-tête.

## <a name="modules-that-are-available-in-a-header-module"></a>Modules disponibles dans le module d'en-tête

Les modules suivants peuvent être utilisés dans un module d'en-tête :

- **Menu de navigation** – Le menu de navigation représente la hiérarchie de navigation du canal et d'autres liens de navigation statiques. La hiérarchie de navigation du canal peut être configurée dans Dynamics 365 Commerce. Le menu de navigation a une propriété **Source de navigation** qui est utilisée pour spécifier les éléments de menu statique et les éléments de menu de navigation Serveur de vente au détail comme source. Si des éléments de menu statique sont spécifiés comme source, des liens relatifs vers d'autres pages du site peuvent être fournis. Les articles configurés s'affichent alors comme navigation d'en-tête. 
- **Rechercher** – Le module de recherche permet aux utilisateurs d'entrer des critères de recherche pour des produits. L'URL de la page de recherche par défaut et les paramètres de la requête de recherche doivent être fournis à l'adresse **Paramètres du site \> Extensions**. Le module de recherche possède des propriétés qui vous permettent de supprimer l'étiquette ou le bouton de recherche selon vos besoins. Le module de recherche prend également en charge les options de suggestion automatique, telles que les résultats de recherche de produits, de mots clés et de catégories.

## <a name="create-a-header-module-for-a-page"></a>Créer un module d'en-tête pour une page

Pour créer un module d'en-tête, procédez comme suit :

1. Créez un fragment nommé **fragment d'en-tête**, puis ajoutez un module de conteneur à celui-ci.
1. Dans le volet de propriétés du module conteneur, définissez la propriété **Largeur** sur **Remplir le conteneur**.
1. Ajoutez des modules de bannière promotionnelle et de consentement aux cookies au module de conteneur.
1. Ajoutez un autre module de conteneur au fragment puis définissez la propriété **Largeur** sur **Remplir le conteneur**.
1. Ajoutez un module d'en-tête au deuxième module de conteneur.
1. Dans l'emplacement **menu de navigation** du module d'en-tête, ajoutez un module de menu de navigation. 
1. Dans le volet de propriétés du module de menu de navigation, configurez les propriétés du module de menu de navigation.
1. Dans l'emplacement **Rechercher** du module d'en-tête, ajoutez un module de recherche. 
1. Dans le volet de propriétés du module de recherche, configurez les propriétés du module de recherche. 
1. Enregistrez le fragment de page, terminez de le modifier et publiez-le. 

Pour vous assurer qu'un en-tête apparaît sur chaque page, suivez ces étapes pour chaque modèle de page créé pour le site.

1. Dans l'emplacement **Principal** de la page par défaut, ajoutez le fragment de page d'en-tête qui contient le module d'en-tête à l'en-tête.
1. Enregistrez le modèle, terminez de le modifier et publiez-le.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Container](add-container-module.md)

[Module Zone d'achat](add-buy-box.md)

[Module Panier](add-cart-module.md)

[Module Paiement](add-checkout-module.md)

[Module Confirmation de commande](order-confirmation-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)
