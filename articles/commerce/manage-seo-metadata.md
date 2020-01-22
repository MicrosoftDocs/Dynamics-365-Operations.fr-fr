---
title: Gestion des métadonnées SEO
description: Cette rubrique décrit la procédure de gestion des métadonnées d'optimisation de moteur de recherche (SEO) dans Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/01/2019
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3ea06713af69659c205686a971393892fa584072
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945718"
---
# <a name="manage-seo-metadata"></a>Gestion des métadonnées SEO

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique décrit la procédure de gestion des métadonnées d'optimisation de moteur de recherche (SEO) dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Les métadonnées SEO pour un site peuvent être gérées à l'aide des métadonnées de plans et de pages du site.
    
## <a name="site-maps"></a>Plans de site

Un plan de site est une liste lisible par une machine, au format XML, des pages sur votre site web. Il doit être consommé par des moteurs de recherche, afin de pouvoir fournir de meilleurs résultats de recherche pour votre site. Les plans de site peuvent être manuellement ingérés par les moteurs de recherche ou publiés dans un fichier robots.txt.

Dynamics 365 Commerce prend en charge la génération automatique des plans de site. Les plans de site sont automatiquement mis à jour lorsque les pages sont publiées et non publiées.

### <a name="turn-on-site-map-generation"></a>Activer la génération de plan de site

1. Connectez-vous à l'outil de création.
1. Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).
1. Dans le volet de navigation sur la gauche, sélectionnez **Gestion du site**.
1. Assurez-vous que l'option **Plans de site activés** est activée.

## <a name="page-metadata"></a>Métadonnées de la page

Dynamics 365 Commerce vous permet de gérer des métadonnées SEO pour diverses pages. Vous pouvez afficher et modifier ces informations dans la section **Propriétés SEO** d'un conteneur de page. Les propriétés de métadonnées SEO suivantes sont actuellement prises en charge :

- Titre
- Description
- Mots clés SEO
- Étiquettes Aria
- noindex
- nofollow
- noarchive
- nocache
- noOpenDirectoryProject
- nosnippet
- noImageIndex
- unavailableAfter

### <a name="modify-page-metadata"></a>Modification des métadonnées de page

Pour modifier les métadonnées de page, procédez comme suit.

1. Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).
1. Dans le volet de navigation sur la gauche, sélectionnez **Pages**.
1. Sélectionnez la page d'accueil pour l'ouvrir dans l'éditeur de page.
1. Dans le volet Actions, sélectionnez **Extraire**.
1. Dans le volet de propriétés de droite, Développez **Métabalises par défaut**.
1. Pour ajouter une nouvelle métabalise, sélectionnez **Ajouter**, puis entrez la balise dans le champ.

    Pour supprimer une métabalise existante, sélectionnez le symbole de corbeille à droite de celui-ci.

1. Sélectionnez **Enregistrer**, puis sélectionnez **Archiver**.
1. Dans le champ **Commentaires**, entrez **Métabalises mises à jour**, puis sélectionnez **OK**.
1. Sélectionnez **Aperçu** pour prévisualiser votre page avant impression. Lorsque vous avez terminé, fermez l'onglet d'aperçu pour revenir à l'outil d'édition.
1. Sélectionnez **Publier**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Modifier une page de site existante](modify-existing-page.md)

[Ajouter une nouvelle page de site](add-new-page.md)

[Sélectionner des dispositions de page](select-page-layouts.md)

[Enregistrer, afficher un aperçu et publier une page](save-preview-publish-page.md)

[Enrichir une page de produit](enrich-product-page.md)

[Enrichir une page d'arrivée de catégorie](enrich-category-page.md)

[Vérifier l'accessibilité du contenu de la page](verify-accessibility.md)
