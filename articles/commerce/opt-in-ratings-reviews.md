---
title: Choix d'utilisation des évaluations et avis
description: Cette rubrique explique comment adhérer à l'utilisation des classements et des évaluations de votre site Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 01/30/2020
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
ms.openlocfilehash: cbdb69202ebec19f4442041cfb1f99857da36d2e
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057508"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="2b58b-103">Choix d'utilisation des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="2b58b-103">Opt in to use ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2b58b-104">Cette rubrique explique comment adhérer à l'utilisation des classements et des évaluations de votre site Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2b58b-104">This topic explains how to opt in to use ratings and reviews on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="2b58b-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="2b58b-105">Overview</span></span>

<span data-ttu-id="2b58b-106">La solution de classements et d'évaluations est une solution omnicanale que vous pouvez rendre disponible dans Dynamics 365 Commerce en utilisant Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="2b58b-106">The ratings and reviews solution is an omni-channel solution that you can make available in Dynamics 365 Commerce by using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="2b58b-107">LCS est un portail d'administration que les détaillants utilisent pour gérer leurs environnements de la mise en service jusqu'à la mise hors service.</span><span class="sxs-lookup"><span data-stu-id="2b58b-107">LCS is an administration portal that retailers use to manage their environments from provisioning to decommissioning.</span></span>

<span data-ttu-id="2b58b-108">Pour utiliser la solution de classements et d'évaluations sur votre site web Commerce, activez les classements et les évaluations lors du déploiement de votre site de commerce électronique sur Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2b58b-108">If you want to use the ratings and reviews solution on your Commerce website, you must opt in for ratings and reviews during deployment of your e-Commerce site on Dynamics 365 Commerce.</span></span>

## <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="2b58b-109">Choix d'utilisation des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="2b58b-109">Opt in to use ratings and reviews</span></span>

<span data-ttu-id="2b58b-110">Pour adhérer à l'utilisation des classements et évaluations sur votre site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="2b58b-110">To opt in to use ratings and reviews on your site, follow these steps.</span></span>

1. <span data-ttu-id="2b58b-111">Suivez les étapes dans [Déployer un nouveau site de commerce électronique](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="2b58b-111">Follow the steps in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span>
1. <span data-ttu-id="2b58b-112">Lorsque vous êtes toujours dans LCS, accédez à **Paramétrage du déploiement de la vente au détail \> Autres paramètres**.</span><span class="sxs-lookup"><span data-stu-id="2b58b-112">While you're still in LCS, go to **Retail deployment setup \> Other settings**.</span></span>
1. <span data-ttu-id="2b58b-113">Définissez l'option **Activer le service de classements et évaluations** sur **Activé**.</span><span class="sxs-lookup"><span data-stu-id="2b58b-113">Set the **Enable ratings and reviews service** option to **Yes**.</span></span>
1. <span data-ttu-id="2b58b-114">Dans le champ **Groupe de sécurité AAD pour le modérateur de classements et d'évaluations (ID objet du groupe de sécurité)**, entrez l'ID du groupe de sécurité Microsoft Azure Active Directory (Azure AD) qui inclut les modérateurs des classements et évaluations.</span><span class="sxs-lookup"><span data-stu-id="2b58b-114">In the **AAD security group for ratings and review moderator (security group object id)** field, enter the ID of the Microsoft Azure Active Directory (Azure AD) security group that includes the ratings and reviews moderators.</span></span>

    ![Choix d'utilisation des évaluations et avis](media/LCS_RnR_Preference.png)

1. <span data-ttu-id="2b58b-116">Terminez le processus d'initialisation de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="2b58b-116">Complete the e-Commerce initialization process.</span></span>

> [!NOTE] 
> <span data-ttu-id="2b58b-117">Si vous êtes un client Dynamics 365 Commerce existant, qui a déjà déployé un site de commerce électronique sans choisir les classements et les évaluations, mais que vous souhaitez maintenant les utiliser à partir du progiciel Dynamics 365 Commerce, veuillez envoyer une demande de service.</span><span class="sxs-lookup"><span data-stu-id="2b58b-117">If you are an existing Dynamics 365 Commerce customer who has already deployed an e-Commerce site without having opted in for ratings and reviews and now want to use ratings and reviews from the Dynamics 365 Commerce package, please submit a service request.</span></span> <span data-ttu-id="2b58b-118">Pour des informations sur l'envoi d'une demande de service, voir [Soumettre des demandes de service](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="2b58b-118">For information about how to submit a service request, see [Submit service requests process](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json).</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="2b58b-119">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="2b58b-119">Additional resources</span></span>

[<span data-ttu-id="2b58b-120">Vue d'ensemble des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="2b58b-120">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="2b58b-121">Gestion des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="2b58b-121">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="2b58b-122">Configuration des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="2b58b-122">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="2b58b-123">Synchronisation des évaluations de produit dans Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="2b58b-123">Sync product ratings in Dynamics 365 Commerce</span></span>](sync-product-ratings.md)


