---
title: Vérifier l'accessibilité du contenu de la page
description: Cette rubrique décrit comment vérifier l'accessibilité du contenu des pages dans Microsoft Dynamics 365 Commerce.
author: josaw1
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: fc3dca673510e1636f497bb7d5c295bebe025677
ms.sourcegitcommit: 092ef6a45f515b38be2a4481abdbe7518a636f85
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4412394"
---
# <a name="verify-page-content-accessibility"></a><span data-ttu-id="f4f07-103">Vérifier l'accessibilité du contenu de la page</span><span class="sxs-lookup"><span data-stu-id="f4f07-103">Verify page content accessibility</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f4f07-104">Cette rubrique décrit comment vérifier l'accessibilité du contenu des pages dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f4f07-104">This topic describes how to verify the accessibility of page content in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f4f07-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="f4f07-105">Overview</span></span>

<span data-ttu-id="f4f07-106">Lorsque vous avez terminé de modifier une page, vous devez vous assurer que le contenu est accessible à tous sur le web.</span><span class="sxs-lookup"><span data-stu-id="f4f07-106">When you've finished changing a page, you should make sure that the content is accessible to everyone on the web.</span></span> <span data-ttu-id="f4f07-107">Dans les outils de création de Commerce, vous pouvez facilement vérifier l'accessibilité du contenu de la page en utilisant le service [Informations sur l'accessibilité de Microsoft](https://accessibilityinsights.io/).</span><span class="sxs-lookup"><span data-stu-id="f4f07-107">In the Commerce authoring tools, you can easily verify the accessibility of page content by using the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service.</span></span> <span data-ttu-id="f4f07-108">Ce service vérifie le contenu de votre page par rapport aux dernières lignes directrices d'[accessibilité au World Wide Web Consortium (W3C)](https://www.w3.org/standards/webdesign/accessibility).</span><span class="sxs-lookup"><span data-stu-id="f4f07-108">This service verifies your page content against the latest [World Wide Web Consortium (W3C) accessibility](https://www.w3.org/standards/webdesign/accessibility) guidelines.</span></span>

<span data-ttu-id="f4f07-109">L'intégration des [Informations sur l'accessibilité de Microsoft](https://accessibilityinsights.io/) doit être activée au niveau du client ou du site avant de pouvoir l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="f4f07-109">The [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration must be turned on at the tenant or site level before you can use it.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a><span data-ttu-id="f4f07-110">Activer les Informations sur l'accessibilité de Microsoft pour tous les sites de votre client</span><span class="sxs-lookup"><span data-stu-id="f4f07-110">Turn on Microsoft Accessibility Insights for all the sites in your tenant</span></span>

<span data-ttu-id="f4f07-111">Pour activer l'intégration des [Informations sur l'accessibilité de Microsoft](https://accessibilityinsights.io/) pour tous les sites Commerce de votre client, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f4f07-111">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for all the Commerce sites in your tenant, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="f4f07-112">Pour accéder aux paramètres du client, vous devez être connecté à Commerce en tant qu'administrateur système.</span><span class="sxs-lookup"><span data-stu-id="f4f07-112">To access tenant settings, you must be signed in to Commerce as a system admin.</span></span>

1. <span data-ttu-id="f4f07-113">Connectez-vous à Commerce en tant qu'administrateur système.</span><span class="sxs-lookup"><span data-stu-id="f4f07-113">Sign in to Commerce as a system admin.</span></span>
1. <span data-ttu-id="f4f07-114">Dans le volet de navigation de gauche, sélectionnez **Paramètres du client** (à côté du symbole d'engrenage) pour l'agrandir.</span><span class="sxs-lookup"><span data-stu-id="f4f07-114">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
1. <span data-ttu-id="f4f07-115">Sous **Paramètres du client**, cliquez sur **Fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="f4f07-115">Under **Tenant Settings**, select **Features**.</span></span>
1. <span data-ttu-id="f4f07-116">Définissez l'option **Vérification de l'accessibilité** sur **Activé**.</span><span class="sxs-lookup"><span data-stu-id="f4f07-116">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a><span data-ttu-id="f4f07-117">Activer Informations sur l'accessibilité de Microsoft pour un seul site</span><span class="sxs-lookup"><span data-stu-id="f4f07-117">Turn on Microsoft Accessibility Insights for a single site</span></span>

<span data-ttu-id="f4f07-118">Pour activer l'intégration des [Informations sur l'accessibilité de Microsoft](https://accessibilityinsights.io/) pour un seul site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f4f07-118">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for a single Commerce site, follow these steps.</span></span>

1. <span data-ttu-id="f4f07-119">Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).</span><span class="sxs-lookup"><span data-stu-id="f4f07-119">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="f4f07-120">Dans le volet de navigation de gauche, cliquez sur **Paramètres du site** pour les étendre.</span><span class="sxs-lookup"><span data-stu-id="f4f07-120">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="f4f07-121">Sous **Paramètres du site**, cliquez sur **Fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="f4f07-121">Under **Site Settings**, select **Features**.</span></span>
1. <span data-ttu-id="f4f07-122">Définissez l'option **Vérification de l'accessibilité** sur **Activé**.</span><span class="sxs-lookup"><span data-stu-id="f4f07-122">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a><span data-ttu-id="f4f07-123">Vérifier l'accessibilité du contenu sur la page d'accueil</span><span class="sxs-lookup"><span data-stu-id="f4f07-123">Verify the accessibility of the content on the home page</span></span>

<span data-ttu-id="f4f07-124">Pour utiliser le service [Informations sur l'accessibilité de Microsoft](https://accessibilityinsights.io/) intégré pour analyser et vérifier le contenu de votre page d'accueil dans Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f4f07-124">To use the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service to scan and verify the content of your home page in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="f4f07-125">Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).</span><span class="sxs-lookup"><span data-stu-id="f4f07-125">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="f4f07-126">Dans le volet de navigation de gauche, sélectionnez **Pages**.</span><span class="sxs-lookup"><span data-stu-id="f4f07-126">In the left navigation pane, select **Pages**.</span></span>
1. <span data-ttu-id="f4f07-127">Recherchez et sélectionnez la page d'accueil pour l'ouvrir dans l'éditeur de page.</span><span class="sxs-lookup"><span data-stu-id="f4f07-127">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="f4f07-128">Dans la barre de commande, sélectionnez **Vérifier l'accessibilité**.</span><span class="sxs-lookup"><span data-stu-id="f4f07-128">On the command bar, select **Check accessibility**.</span></span> <span data-ttu-id="f4f07-129">La page **Vérifier l'accessibilité** apparaît.</span><span class="sxs-lookup"><span data-stu-id="f4f07-129">The **Check Accessibility** page appears.</span></span>
1. <span data-ttu-id="f4f07-130">Une fois l'analyse terminée, examinez le contenu du rapport.</span><span class="sxs-lookup"><span data-stu-id="f4f07-130">After the scan is completed, review the contents of the report.</span></span>
1. <span data-ttu-id="f4f07-131">Si des vérifications ont échoué, sélectionnez chaque élément de vérification ayant échoué pour le développer afin de pouvoir afficher plus de détails.</span><span class="sxs-lookup"><span data-stu-id="f4f07-131">If any checks failed, select each failed check item to expand it so that you can view more details.</span></span>
1. <span data-ttu-id="f4f07-132">Pour fermer le rapport après l'avoir examiné, faites défiler vers le bas de la page **Vérifier l'accessibilité** et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4f07-132">To close the report after you've finished reviewing it, scroll to the bottom of the **Check Accessibility** page, and select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f4f07-133">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f4f07-133">Additional resources</span></span>

[<span data-ttu-id="f4f07-134">Modifier une page de site existante</span><span class="sxs-lookup"><span data-stu-id="f4f07-134">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="f4f07-135">Ajouter une nouvelle page de site</span><span class="sxs-lookup"><span data-stu-id="f4f07-135">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="f4f07-136">Sélectionner des dispositions de page</span><span class="sxs-lookup"><span data-stu-id="f4f07-136">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="f4f07-137">Gestion des métadonnées SEO</span><span class="sxs-lookup"><span data-stu-id="f4f07-137">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="f4f07-138">Enregistrer, afficher un aperçu et publier une page</span><span class="sxs-lookup"><span data-stu-id="f4f07-138">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="f4f07-139">Enrichir une page de produit</span><span class="sxs-lookup"><span data-stu-id="f4f07-139">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="f4f07-140">Enrichir une page d'arrivée de catégorie</span><span class="sxs-lookup"><span data-stu-id="f4f07-140">Enrich a category landing page</span></span>](enrich-category-page.md)
