---
title: Configuration des évaluations et avis
description: Cette rubrique décrit la procédure de configuration de votre site de commerce électronique pour afficher les classements et les évaluations des clients dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 130c80c1d68c7fb207a4fa073fe2b0476cbdd409
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220532"
---
# <a name="configure-ratings-and-reviews"></a><span data-ttu-id="55427-103">Configuration des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="55427-103">Configure ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="55427-104">Cette rubrique décrit la procédure de configuration de votre site de commerce électronique pour afficher les classements et les évaluations des clients dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="55427-104">This topic describes how to configure your e-Commerce site to show customer ratings and reviews in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="55427-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="55427-105">Overview</span></span>

<span data-ttu-id="55427-106">Les classements et les évaluations des sites web de commerce électronique permettent aux clients d'en savoir plus sur les produits avant de prendre une décision d'achat, en leur affichant ce que d'autres clients pensent de ces produits.</span><span class="sxs-lookup"><span data-stu-id="55427-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision by showing them what other customers think about those products.</span></span> <span data-ttu-id="55427-107">Pour les sites web de commerce électronique, les classements et les évaluations sont également un mécanisme de collecte des commentaires des clients sur les produits.</span><span class="sxs-lookup"><span data-stu-id="55427-107">For e-Commerce websites, ratings and reviews are also a mechanism for collecting customer feedback about products.</span></span> 

## <a name="configure-a-site-to-show-ratings-and-reviews"></a><span data-ttu-id="55427-108">Configuration d'un site pour afficher des classements et des évaluations</span><span class="sxs-lookup"><span data-stu-id="55427-108">Configure a site to show ratings and reviews</span></span>

<span data-ttu-id="55427-109">Les valeurs de configuration pour les classements et les évaluations, telles que l'ID client, vérifier la longueur du texte, et analyser la longueur du titre, sont configurées au niveau de le site.</span><span class="sxs-lookup"><span data-stu-id="55427-109">Configuration values for ratings and reviews, such as the tenant ID, review text length, and review title length, are configured at the site level.</span></span> 

<span data-ttu-id="55427-110">Pour configurer un site afin d'afficher des classements et des évaluations, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="55427-110">To configure a site to show ratings and reviews, follow these steps.</span></span> 

1. <span data-ttu-id="55427-111">Accédez à **Accueil \> Sites**.</span><span class="sxs-lookup"><span data-stu-id="55427-111">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="55427-112">Sélectionnez le nom de votre site.</span><span class="sxs-lookup"><span data-stu-id="55427-112">Select the name of your site.</span></span> 
1. <span data-ttu-id="55427-113">Accédez à **Paramètres du site \> Extensions**.</span><span class="sxs-lookup"><span data-stu-id="55427-113">Go to **Site settings \> Extensions**.</span></span> 
1. <span data-ttu-id="55427-114">Dans le champ **Vérifier la longueur maximale du texte**, entrez le nombre maximal de caractères que le texte d'évaluation peut comporter (par exemple, **1 000**).</span><span class="sxs-lookup"><span data-stu-id="55427-114">In the **Review text max length** field, enter the maximum number of characters that review text can have (for example, **1000**).</span></span> 
1. <span data-ttu-id="55427-115">Dans le champ **Vérifier la longueur maximale du titre**, entrez le nombre maximal de caractères que les titres d'évaluation peuvent comporter (par exemple, **55**).</span><span class="sxs-lookup"><span data-stu-id="55427-115">In the **Review title max length** field, enter the maximum number of characters that review titles can have (for example, **55**).</span></span> 
1. <span data-ttu-id="55427-116">Sélectionnez **Enregistrer et publier**.</span><span class="sxs-lookup"><span data-stu-id="55427-116">Select **Save and Publish**.</span></span> 

<span data-ttu-id="55427-117">L'illustration suivante présente à quoi cette configuration ressemble dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="55427-117">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Configuration d'un site pour afficher des classements et des évaluations](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a><span data-ttu-id="55427-119">Association d'un classement de produit à la section Évaluation d'une page de détails de produit</span><span class="sxs-lookup"><span data-stu-id="55427-119">Link a product rating to the Reviews section of a PDP</span></span>

<span data-ttu-id="55427-120">Un classement de produit apparaît sous le titre de produit en haut de la page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="55427-120">A product rating is shown below the product title at the top of PDP.</span></span> <span data-ttu-id="55427-121">Le classement de produit peut être configuré pour qu'il soit lié à la section **Évaluations** de la même page de détails du produit.</span><span class="sxs-lookup"><span data-stu-id="55427-121">The product rating can be configured so that it's linked to the **Reviews** section of the same PDP.</span></span> 

<span data-ttu-id="55427-122">Pour lier un classement de produit à la section **Évaluations** de la page de détails de produit, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="55427-122">To link a product rating to the **Reviews** section of the PDP, follow these steps.</span></span>

1. <span data-ttu-id="55427-123">Ouvrez le modèle de page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="55427-123">Open the PDP template.</span></span> 
1. <span data-ttu-id="55427-124">Accédez à **Paramètres du module de conteneur Zone d'achat**.</span><span class="sxs-lookup"><span data-stu-id="55427-124">Go to **Buy box container module settings**.</span></span>
1. <span data-ttu-id="55427-125">Sous **Zone d'achat**, sélectionnez **Classements de produit**, puis activez la case à cocher **Lier le clic au module complet d'évaluations**.</span><span class="sxs-lookup"><span data-stu-id="55427-125">Under **Buy box**, select **Product ratings**, and then select the **Link the click to full reviews module** check box.</span></span>

<span data-ttu-id="55427-126">L'illustration suivante présente à quoi cette configuration ressemble dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="55427-126">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Association d'un classement de produit à la section Évaluation d'une page de détails de produit](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a><span data-ttu-id="55427-128">Configurer le lien de la page de confidentialité et de politique</span><span class="sxs-lookup"><span data-stu-id="55427-128">Configure the link for the privacy and policy page</span></span>

<span data-ttu-id="55427-129">Pour configurer le lien de la page de confidentialité et de politique, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="55427-129">To configure the link for the privacy and policy page, follow these steps.</span></span>

1. <span data-ttu-id="55427-130">Accédez à **Accueil \> Sites**.</span><span class="sxs-lookup"><span data-stu-id="55427-130">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="55427-131">Sélectionnez le nom de votre site.</span><span class="sxs-lookup"><span data-stu-id="55427-131">Select the name of your site.</span></span> 
1. <span data-ttu-id="55427-132">Accédez à **Paramètres du site \> Extensions**.</span><span class="sxs-lookup"><span data-stu-id="55427-132">Go to **Site settings \> Extensions**.</span></span>
1. <span data-ttu-id="55427-133">Dans l'onglet **Acheminements**, sous **Confidentialité et politique RNR**, sélectionnez **Ajouter un lien**.</span><span class="sxs-lookup"><span data-stu-id="55427-133">On the **Routes** tab, under **RNR Privacy and Policy**, select **Add a link**.</span></span> <span data-ttu-id="55427-134">Si un lien est déjà entré, et si vous souhaitez le remplacer, sélectionnez le lien.</span><span class="sxs-lookup"><span data-stu-id="55427-134">If a link is already entered, and you want to replace it, select the link.</span></span> 
1. <span data-ttu-id="55427-135">Dans la boîte de dialogue **Ajouter un lien**, sélectionnez le lien de la page de confidentialité et de politique, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="55427-135">In the **Add a link** dialog box, select the link for the privacy and policy page, and then select **OK**.</span></span> 
1. <span data-ttu-id="55427-136">Sélectionnez **Enregistrer et publier**.</span><span class="sxs-lookup"><span data-stu-id="55427-136">Select **Save and Publish**.</span></span> 

<span data-ttu-id="55427-137">L'illustration suivante présente à quoi cette configuration ressemble dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="55427-137">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Configuration du lien de la page de confidentialité et de politique](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="configure-ratings-and-reviews-modules-on-product-details-pages"></a><span data-ttu-id="55427-139">Configurer les modules de classements et d'évaluations sur les pages de détails des produits</span><span class="sxs-lookup"><span data-stu-id="55427-139">Configure ratings and reviews modules on product details pages</span></span>

<span data-ttu-id="55427-140">Pour plus d'informations sur la configuration des modules de classements et d'évaluations sur les pages de détails des produits, voir [Modules de classements et d'évaluations](ratings-reviews-modules.md).</span><span class="sxs-lookup"><span data-stu-id="55427-140">For information on configuring ratings and reviews modules on product details pages, see [Ratings and reviews modules](ratings-reviews-modules.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="55427-141">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="55427-141">Additional resources</span></span>

[<span data-ttu-id="55427-142">Vue d'ensemble des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="55427-142">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="55427-143">Choix d'utilisation des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="55427-143">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="55427-144">Gestion des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="55427-144">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="55427-145">Configurer les modules de classements et d'évaluations sur les pages de détails des produits</span><span class="sxs-lookup"><span data-stu-id="55427-145">Configure ratings and reviews modules on product details pages</span></span>](ratings-reviews-modules.md)

[<span data-ttu-id="55427-146">Synchronisation des évaluations de produit dans Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="55427-146">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]