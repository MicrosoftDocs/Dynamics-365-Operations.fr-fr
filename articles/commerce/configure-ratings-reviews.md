---
title: Configuration des évaluations et avis
description: Cette rubrique décrit la procédure de configuration de votre site de commerce électronique pour afficher les classements et les évaluations des clients dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e3f9ff4b0654ec5fa7548ac62e16ae64f44383e7
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968100"
---
# <a name="configure-ratings-and-reviews"></a>Configuration des évaluations et avis

[!include [banner](includes/banner.md)]

Cette rubrique décrit la procédure de configuration de votre site de commerce électronique pour afficher les classements et les évaluations des clients dans Microsoft Dynamics 365 Commerce.

Les classements et les évaluations des sites web de commerce électronique permettent aux clients d’en savoir plus sur les produits avant de prendre une décision d’achat, en leur affichant ce que d’autres clients pensent de ces produits. Pour les sites web de commerce électronique, les classements et les évaluations sont également un mécanisme de collecte des commentaires des clients sur les produits. 

## <a name="configure-a-site-to-show-ratings-and-reviews"></a>Configuration d’un site pour afficher des classements et des évaluations

Les valeurs de configuration pour les classements et les évaluations, telles que l’ID client, vérifier la longueur du texte, et analyser la longueur du titre, sont configurées au niveau de le site. 

Pour configurer un site afin d’afficher des classements et des évaluations, procédez comme suit. 

1. Accédez à **Accueil \> Sites**.
1. Sélectionnez le nom de votre site. 
1. Accédez à **Paramètres du site \> Extensions**. 
1. Dans le champ **Vérifier la longueur maximale du texte**, entrez le nombre maximal de caractères que le texte d’évaluation peut comporter (par exemple, **1 000**). 
1. Dans le champ **Vérifier la longueur maximale du titre**, entrez le nombre maximal de caractères que les titres d’évaluation peuvent comporter (par exemple, **55**). 
1. Sélectionnez **Enregistrer et publier**. 

L’illustration suivante présente à quoi cette configuration ressemble dans Dynamics 365 Commerce.

![Configuration d’un site pour afficher des classements et des évaluations.](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a>Association d’un classement de produit à la section Évaluation d’une page de détails de produit

Un classement de produit apparaît sous le titre de produit en haut de la page de détails de produit. Le classement de produit peut être configuré pour qu’il soit lié à la section **Évaluations** de la même page de détails du produit. 

Pour lier un classement de produit à la section **Évaluations** de la page de détails de produit, procédez comme suit.

1. Ouvrez le modèle de page de détails de produit. 
1. Accédez à **Paramètres du module de conteneur Zone d’achat**.
1. Sous **Zone d’achat**, sélectionnez **Classements de produit**, puis activez la case à cocher **Lier le clic au module complet d’évaluations**.

L’illustration suivante présente à quoi cette configuration ressemble dans Dynamics 365 Commerce.

![Association d’un classement de produit à la section Évaluation d’une page de détails de produit.](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a>Configurer le lien de la page de confidentialité et de politique

Pour configurer le lien de la page de confidentialité et de politique, procédez comme suit.

1. Accédez à **Accueil \> Sites**.
1. Sélectionnez le nom de votre site. 
1. Accédez à **Paramètres du site \> Extensions**.
1. Dans l’onglet **Acheminements**, sous **Confidentialité et politique RNR**, sélectionnez **Ajouter un lien**. Si un lien est déjà entré, et si vous souhaitez le remplacer, sélectionnez le lien. 
1. Dans la boîte de dialogue **Ajouter un lien**, sélectionnez le lien de la page de confidentialité et de politique, puis sélectionnez **OK**. 
1. Sélectionnez **Enregistrer et publier**. 

L’illustration suivante présente à quoi cette configuration ressemble dans Dynamics 365 Commerce.

![Configuration du lien de la page de confidentialité et de politique.](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="configure-ratings-and-reviews-modules-on-product-details-pages"></a>Configurer les modules de classements et d’évaluations sur les pages de détails des produits

Pour plus d’informations sur la configuration des modules de classements et d’évaluations sur les pages de détails des produits, voir [Modules de classements et d’évaluations](ratings-reviews-modules.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des évaluations et avis](ratings-reviews-overview.md)

[Choix d’utilisation des évaluations et avis](opt-in-ratings-reviews.md)

[Gestion des évaluations et avis](manage-reviews.md)

[Synchronisation des évaluations de produit dans Dynamics 365 Retail](sync-product-ratings.md)

[Activer la publication manuelle des évaluations et des avis par un modérateur](manual-publish-rating-reviews.md)

[Importation et exportation des évaluations et des avis](import-export-reviews.md)

[Configurer l’authentification service à service](service-to-service-auth.md)

[FAQ sur les évaluations et avis](ratings-reviews-faq.md)

[Modules de classements et d’évaluations](ratings-reviews-modules.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
