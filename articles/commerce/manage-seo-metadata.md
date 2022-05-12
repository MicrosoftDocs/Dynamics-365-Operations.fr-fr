---
title: Gestion des métadonnées SEO
description: Cette rubrique décrit la procédure de gestion des métadonnées d’optimisation de moteur de recherche (SEO) dans Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3d6f56968e9adfe90142955cba8e6c7ecc50fc92
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644757"
---
# <a name="manage-seo-metadata"></a>Gestion des métadonnées SEO

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cette rubrique décrit la procédure de gestion des métadonnées d’optimisation de moteur de recherche (SEO) dans Microsoft Dynamics 365 Commerce.

Les métadonnées SEO pour un site peuvent être gérées à l’aide des métadonnées de plans et de pages du site.
    
## <a name="site-maps"></a>Plans de site

Un plan de site est une liste lisible par une machine, au format XML, des pages sur votre site web. Il doit être consommé par des moteurs de recherche, afin de pouvoir fournir de meilleurs résultats de recherche pour votre site. Les plans de site peuvent être manuellement ingérés par les moteurs de recherche ou publiés dans un fichier robots.txt.

Dynamics 365 Commerce prend en charge la génération automatique des plans de site. Les plans de site sont automatiquement mis à jour quand les pages sont publiées et non publiées.

### <a name="turn-on-site-map-generation"></a>Activer la génération de plan de site

1. Connectez-vous à l’outil de création.
1. Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).
1. Dans le volet de navigation sur la gauche, sélectionnez **Gestion du site**.
1. Assurez-vous que l’option **Plans de site activés** est activée.

## <a name="page-metadata"></a>Métadonnées de la page

Dynamics 365 Commerce vous permet de gérer des métadonnées SEO pour diverses pages. Vous pouvez afficher et modifier ces informations dans la section **Propriétés SEO** d’un conteneur de page. Les propriétés de métadonnées SEO suivantes sont actuellement prises en charge :

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
1. Sélectionnez la page d’accueil pour l’ouvrir dans l’éditeur de page.
1. Dans la barre de commande, sélectionnez **Modifier**.
1. Sous l’éditeur de pages, en haut du contrôle Plan de page à gauche, sélectionnez **l’option Mode Plan** (symbole d’engrenage), puis sélectionnez **Vue de plan avancée**.
1. Dans la vue de plan, développez les contrôles de l’arborescence pour afficher le contenu de l’emplacement **Tête HTML**.
1. Dans l’emplacement **Tête HTML**, sélectionnez le module SEO souhaité (par exemple, **Récapitulatif de page**, **Récapitulatif de la page produit**, **Récapitulatif de la page de catégorie** ou **Métabalises**).
1. Dans le volet des propriétés à droite, modifiez les données SEO souhaitées pour le module SEO sélectionné (par exemple, **Titre**, **Description** ou **Partage d’images**).
1. Sélectionnez **Enregistrer**, puis **Terminer la modification**.
1. Dans le champ **Commentaires**, entrez **Donées SEO mises à jour**, puis sélectionnez **OK**.
1. Sélectionnez **Aperçu** pour prévisualiser votre page avant impression. Quand vous avez terminé, fermez l’onglet d’aperçu pour revenir à l’outil d’édition.
1. Cliquez sur **Publier**.

> [!TIP]
> Les auteurs peuvent utiliser **l’option mode Plan** (symbole d’engrenage) en haut du contrôle de plan gauche dans l’éditeur de page pour basculer entre **Vue de plan de base** et **Vue de plan avancée**. **Vue de plan de base** est le paramètre par défaut et filtre le plan afin qu’il n’affiche que les modules de l’emplacement HTML **Corps** pour une page. **Vue de plan avancée** affiche le module de la page entière, y compris les emplacements **Tête HTML**, **Début du corps** et **Fin du corps**. Cette vue est utile quand les auteurs doivent modifier des paramètres de module SEO ou de script spécifiques pour une page.

## <a name="additional-resources"></a>Ressources supplémentaires

[Modifier une page de site existante](modify-existing-page.md)

[Ajouter une nouvelle page de site](add-new-page.md)

[Sélectionner des dispositions de page](select-page-layouts.md)

[Enregistrer, afficher un aperçu et publier une page](save-preview-publish-page.md)

[Enrichir une page de produit](enrich-product-page.md)

[Enrichir une page d’arrivée de catégorie](enrich-category-page.md)

[Vérifier l’accessibilité du contenu de la page](verify-accessibility.md)

[Créer des pages e-commerce dynamiques basées sur des paramètres d’URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
