---
title: Choix d'utilisation des évaluations et avis
description: Cette rubrique explique comment adhérer à l'utilisation des classements et des évaluations de votre site Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
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
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 10e3c33af232fa46df09a103b2e73eae09a909eb
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697978"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a>Choix d'utilisation des évaluations et avis

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique explique comment adhérer à l'utilisation des classements et des évaluations de votre site Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

La solution de classement et évaluation est une solution omnicanale que vous pouvez rendre disponible dans Dynamics 365 Commerce en utilisant Microsoft Dynamics Lifecycle Services (LCS). LCS est un portail d'administration que les détaillants utilisent pour gérer leurs environnements de la mise en service jusqu'à la mise hors service.

Si vous souhaitez utiliser la solution de classement et d'évaluation sur votre site web Commerce, vous devez d'abord adhérer.

## <a name="opt-in-to-use-ratings-and-reviews"></a>Choix d'utilisation des évaluations et avis

Pour adhérer à l'utilisation des classements et évaluations sur votre site, procédez comme suit.

1. Suivez les étapes dans [Déployer un nouveau site de commerce électronique](deploy-ecommerce-site.md).
1. Lorsque vous êtes toujours dans LCS, accédez à **Paramétrage du déploiement de la vente au détail \> Autres paramètres**.
1. Définissez l'option **Activer le service de classements et évaluations** sur **Activé**.
1. Dans le champ **Groupe de sécurité AAD pour le modérateur de classements et d'évaluations (ID objet du groupe de sécurité)**, entrez l'ID du groupe de sécurité Microsoft Azure Active Directory (Azure AD) qui inclut les modérateurs des classements et évaluations.

    ![Choix d'utilisation des évaluations et avis](media/LCS_RnR_Preference.png)

1. Terminez le processus d'initialisation de commerce électronique.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des évaluations et avis](ratings-reviews-overview.md)

[Gestion des évaluations et avis](manage-reviews.md)

[Configuration des évaluations et avis](configure-ratings-reviews.md)

[Synchronisation des évaluations de produit dans Dynamics 365 Retail](sync-product-ratings.md)
