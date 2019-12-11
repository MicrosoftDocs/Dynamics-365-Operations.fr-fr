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
# <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="0a882-103">Choix d'utilisation des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="0a882-103">Opt in to use ratings and reviews</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="0a882-104">Cette rubrique explique comment adhérer à l'utilisation des classements et des évaluations de votre site Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0a882-104">This topic explains how to opt in to use ratings and reviews on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="0a882-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="0a882-105">Overview</span></span>

<span data-ttu-id="0a882-106">La solution de classement et évaluation est une solution omnicanale que vous pouvez rendre disponible dans Dynamics 365 Commerce en utilisant Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="0a882-106">The ratings and reviews solution is an omnichannel solution that you can make available in Dynamics 365 Commerce by using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="0a882-107">LCS est un portail d'administration que les détaillants utilisent pour gérer leurs environnements de la mise en service jusqu'à la mise hors service.</span><span class="sxs-lookup"><span data-stu-id="0a882-107">LCS is an administration portal that retailers use to manage their environments from provisioning to decommissioning.</span></span>

<span data-ttu-id="0a882-108">Si vous souhaitez utiliser la solution de classement et d'évaluation sur votre site web Commerce, vous devez d'abord adhérer.</span><span class="sxs-lookup"><span data-stu-id="0a882-108">If you want to use the ratings and reviews solution on your Commerce website, you must first opt in.</span></span>

## <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="0a882-109">Choix d'utilisation des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="0a882-109">Opt in to use ratings and reviews</span></span>

<span data-ttu-id="0a882-110">Pour adhérer à l'utilisation des classements et évaluations sur votre site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="0a882-110">To opt in to use ratings and reviews on your site, follow these steps.</span></span>

1. <span data-ttu-id="0a882-111">Suivez les étapes dans [Déployer un nouveau site de commerce électronique](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="0a882-111">Follow the steps in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span>
1. <span data-ttu-id="0a882-112">Lorsque vous êtes toujours dans LCS, accédez à **Paramétrage du déploiement de la vente au détail \> Autres paramètres**.</span><span class="sxs-lookup"><span data-stu-id="0a882-112">While you're still in LCS, go to **Retail deployment setup \> Other settings**.</span></span>
1. <span data-ttu-id="0a882-113">Définissez l'option **Activer le service de classements et évaluations** sur **Activé**.</span><span class="sxs-lookup"><span data-stu-id="0a882-113">Set the **Enable ratings and reviews service** option to **Yes**.</span></span>
1. <span data-ttu-id="0a882-114">Dans le champ **Groupe de sécurité AAD pour le modérateur de classements et d'évaluations (ID objet du groupe de sécurité)**, entrez l'ID du groupe de sécurité Microsoft Azure Active Directory (Azure AD) qui inclut les modérateurs des classements et évaluations.</span><span class="sxs-lookup"><span data-stu-id="0a882-114">In the **AAD security group for ratings and review moderator (security group object id)** field, enter the ID of the Microsoft Azure Active Directory (Azure AD) security group that includes the ratings and reviews moderators.</span></span>

    ![Choix d'utilisation des évaluations et avis](media/LCS_RnR_Preference.png)

1. <span data-ttu-id="0a882-116">Terminez le processus d'initialisation de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="0a882-116">Complete the e-Commerce initialization process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0a882-117">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0a882-117">Additional resources</span></span>

[<span data-ttu-id="0a882-118">Vue d'ensemble des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="0a882-118">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="0a882-119">Gestion des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="0a882-119">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="0a882-120">Configuration des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="0a882-120">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="0a882-121">Synchronisation des évaluations de produit dans Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="0a882-121">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
