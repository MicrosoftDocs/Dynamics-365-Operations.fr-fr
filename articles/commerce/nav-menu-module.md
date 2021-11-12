---
title: Module Menu de navigation
description: Cette rubrique couvre les modules de menu de navigation et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 5379aa4496c1c448d147bb260689ebe38aaf903f
ms.sourcegitcommit: 6bf9e18989e6d77497a9dda1c362f324b3c2fbf2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2021
ms.locfileid: "7713850"
---
# <a name="navigation-menu-module"></a>Module du menu de navigation

[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de menu de navigation et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

L’objectif principal des modules de menu de navigation est de permettre aux utilisateurs du site de parcourir les produits et les pages du site en fonction de la hiérarchie de navigation des canaux définie dans le siège Dynamics 365 Commerce. Les éléments configurés dans un module de menu de navigation apparaissent en tant que navigation dans l’en-tête du site. Les modules de menu de navigation prennent également en charge les éléments de menu statiques qui renvoient à d’autres pages d’un site d’e-commerce.

Le module de menu de navigation peut être ajouté au module d’en-tête d’une page. Dans le thème Fabrikam, le menu de navigation affiche deux niveaux par défaut. Dans le thème Starter, le menu de navigation affiche trois niveaux par défaut. Pour modifier le nombre de niveaux, une extension de vue est requise sur le thème.

L’illustration suivante montre un exemple de menu de navigation pour le site Fabrikam avec deux niveaux de hiérarchie de catégories et des éléments de menu statiques.
![Exemple de module de menu de navigation.](./media/ecommerce-header.png)

## <a name="navigation-menu-module-properties"></a>Propriétés du module Menu de navigation

| Nom de la propriété             | Valeur                  | Description  |
|---------------------------|-----------------------|-------------|
| Source                  | **Vente au détail**, **Création manuelle**, **Vente au détail et création manuelle** | La valeur **Vente au détail** permet d’afficher la hiérarchie de navigation des canaux depuis le siège Commerce dans le menu de navigation. La valeur **Création manuelle** permet aux éléments de menu statiques d’être organisés. La valeur **Vente au détail et création manuelle** permet un mélange des deux. |
| Afficher les images des catégories | **Vrai** ou **Faux**    | Lorsqu’elle est activée, cette propriété affiche les images de catégorie dans le menu de navigation, telles que définies dans le siège Commerce pour chaque catégorie. Ajouté dans la version 10.0.14 de Commerce. |
| Afficher les images promotionnelles | **Vrai** ou **Faux** | Lorsque cette propriété est activée, les promotions peuvent être configurées à l’aide d’images, de liens et de texte. Cette propriété a été ajoutée dans la version 10.0.17 de Commerce. |
|Ajouter le contenu promotionnel de la catégorie | Texte, image ou lien | Quand la propriété **Afficher les images promotionnelles** est activée, vous pouvez ajouter du texte, une image ou un lien comme contenu promotionnel dans le menu de navigation. |
| Activer le menu de navigation à plusieurs niveaux | **Vrai** ou **Faux** | Lorsque cette propriété est activée, le menu de navigation peut afficher plusieurs niveaux de la hiérarchie de navigation. Cette fonctionnalité est disponible dans la version 10.0.15 et ultérieure de Commerce. |
| Nombre de niveaux | entier | Cette propriété définit le nombre de niveaux à afficher si la propriété **Activer le menu de navigation à plusieurs niveaux** est définie sur **True**. |
| Élément de menu statique| Tableau de valeurs| Éléments de menu statiques qui associent un nom d’élément de menu à un lien vers une page de site statique. Vous pouvez créer des éléments de menu sous d’autres éléments de menu. Par défaut, les menus statiques apparaissent au niveau racine et seront ajoutés à la hiérarchie de navigation des canaux si elle existe. |
| Afficher le menu racine | **Vrai** ou **Faux** | Lorsque cette propriété est activée, le menu de navigation peut être défini sous une racine personnalisée (par exemple, **Acheter maintenant**). Cette fonction est disponible dans Dynamics 365 Commerce version 10.0.15. |
| Menu racine | chaîne | Cette propriété peut être utilisée pour définir le texte d’une racine personnalisée si la propriété **Afficher le menu racine** est définie sur **True**. |

L’illustration suivante montre un exemple d’image de catégorie affichée dans le menu de navigation du site Fabrikam.
![Exemple de module de navigation avec images de catégories.](./media/ecommerce-categoryimages.PNG)

## <a name="add-a-navigation-menu-module-to-a-header-module"></a>Ajouter un module de menu de navigation à un module d’en-tête

Pour plus d’informations sur l’ajout d’un module de menu de navigation à un module d’en-tête, voir [Module d’en-tête](author-header-module.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Module de barre de navigation](add-breadcrumb.md)

[Module Sélecteur de site](site-selector.md)

[Module Zone d’achat](add-buy-box.md)

[Conformité des cookies](cookie-compliance.md)

[Module En-tête](author-header-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
