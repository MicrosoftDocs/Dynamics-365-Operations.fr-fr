---
title: Vérifier l’accessibilité du contenu de la page
description: Cette rubrique décrit comment vérifier l’accessibilité du contenu des pages dans Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 885696c13b0e5353e6dbd9dc21cf075d5e301786
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791629"
---
# <a name="verify-page-content-accessibility"></a><span data-ttu-id="7b970-103">Vérifier l’accessibilité du contenu de la page</span><span class="sxs-lookup"><span data-stu-id="7b970-103">Verify page content accessibility</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7b970-104">Cette rubrique décrit comment vérifier l’accessibilité du contenu des pages dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7b970-104">This topic describes how to verify the accessibility of page content in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="7b970-105">Lorsque vous avez terminé de modifier une page, vous devez vous assurer que le contenu est accessible à tous sur le web.</span><span class="sxs-lookup"><span data-stu-id="7b970-105">When you've finished changing a page, you should make sure that the content is accessible to everyone on the web.</span></span> <span data-ttu-id="7b970-106">Dans les outils de création de Commerce, vous pouvez facilement vérifier l’accessibilité du contenu de la page en utilisant le service [Informations sur l’accessibilité de Microsoft](https://accessibilityinsights.io/).</span><span class="sxs-lookup"><span data-stu-id="7b970-106">In the Commerce authoring tools, you can easily verify the accessibility of page content by using the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service.</span></span> <span data-ttu-id="7b970-107">Ce service vérifie le contenu de votre page par rapport aux dernières lignes directrices d’[accessibilité au World Wide Web Consortium (W3C)](https://www.w3.org/standards/webdesign/accessibility).</span><span class="sxs-lookup"><span data-stu-id="7b970-107">This service verifies your page content against the latest [World Wide Web Consortium (W3C) accessibility](https://www.w3.org/standards/webdesign/accessibility) guidelines.</span></span>

<span data-ttu-id="7b970-108">L’intégration des [Informations sur l’accessibilité de Microsoft](https://accessibilityinsights.io/) doit être activée au niveau du client ou du site avant de pouvoir l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="7b970-108">The [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration must be turned on at the tenant or site level before you can use it.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a><span data-ttu-id="7b970-109">Activer les Informations sur l’accessibilité de Microsoft pour tous les sites de votre client</span><span class="sxs-lookup"><span data-stu-id="7b970-109">Turn on Microsoft Accessibility Insights for all the sites in your tenant</span></span>

<span data-ttu-id="7b970-110">Pour activer l’intégration des [Informations sur l’accessibilité de Microsoft](https://accessibilityinsights.io/) pour tous les sites Commerce de votre client, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7b970-110">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for all the Commerce sites in your tenant, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="7b970-111">Pour accéder aux paramètres du client, vous devez être connecté à Commerce en tant qu’administrateur système.</span><span class="sxs-lookup"><span data-stu-id="7b970-111">To access tenant settings, you must be signed in to Commerce as a system admin.</span></span>

1. <span data-ttu-id="7b970-112">Connectez-vous à Commerce en tant qu’administrateur système.</span><span class="sxs-lookup"><span data-stu-id="7b970-112">Sign in to Commerce as a system admin.</span></span>
1. <span data-ttu-id="7b970-113">Dans le volet de navigation de gauche, sélectionnez **Paramètres du client** (à côté du symbole d’engrenage) pour l’agrandir.</span><span class="sxs-lookup"><span data-stu-id="7b970-113">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
1. <span data-ttu-id="7b970-114">Sous **Paramètres du client**, cliquez sur **Fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="7b970-114">Under **Tenant Settings**, select **Features**.</span></span>
1. <span data-ttu-id="7b970-115">Définissez l’option **Vérification de l’accessibilité** sur **Activé**.</span><span class="sxs-lookup"><span data-stu-id="7b970-115">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a><span data-ttu-id="7b970-116">Activer Informations sur l’accessibilité de Microsoft pour un seul site</span><span class="sxs-lookup"><span data-stu-id="7b970-116">Turn on Microsoft Accessibility Insights for a single site</span></span>

<span data-ttu-id="7b970-117">Pour activer l’intégration des [Informations sur l’accessibilité de Microsoft](https://accessibilityinsights.io/) pour un seul site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7b970-117">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for a single Commerce site, follow these steps.</span></span>

1. <span data-ttu-id="7b970-118">Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).</span><span class="sxs-lookup"><span data-stu-id="7b970-118">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="7b970-119">Dans le volet de navigation de gauche, cliquez sur **Paramètres du site** pour les étendre.</span><span class="sxs-lookup"><span data-stu-id="7b970-119">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="7b970-120">Sous **Paramètres du site**, cliquez sur **Fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="7b970-120">Under **Site Settings**, select **Features**.</span></span>
1. <span data-ttu-id="7b970-121">Définissez l’option **Vérification de l’accessibilité** sur **Activé**.</span><span class="sxs-lookup"><span data-stu-id="7b970-121">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a><span data-ttu-id="7b970-122">Vérifier l’accessibilité du contenu sur la page d’accueil</span><span class="sxs-lookup"><span data-stu-id="7b970-122">Verify the accessibility of the content on the home page</span></span>

<span data-ttu-id="7b970-123">Pour utiliser le service [Informations sur l’accessibilité de Microsoft](https://accessibilityinsights.io/) intégré pour analyser et vérifier le contenu de votre page d’accueil dans Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7b970-123">To use the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service to scan and verify the content of your home page in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="7b970-124">Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).</span><span class="sxs-lookup"><span data-stu-id="7b970-124">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="7b970-125">Dans le volet de navigation de gauche, sélectionnez **Pages**.</span><span class="sxs-lookup"><span data-stu-id="7b970-125">In the left navigation pane, select **Pages**.</span></span>
1. <span data-ttu-id="7b970-126">Recherchez et sélectionnez la page d’accueil pour l’ouvrir dans l’éditeur de page.</span><span class="sxs-lookup"><span data-stu-id="7b970-126">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="7b970-127">Dans la barre de commande, sélectionnez **Vérifier l’accessibilité**.</span><span class="sxs-lookup"><span data-stu-id="7b970-127">On the command bar, select **Check accessibility**.</span></span> <span data-ttu-id="7b970-128">La page **Vérifier l’accessibilité** apparaît.</span><span class="sxs-lookup"><span data-stu-id="7b970-128">The **Check Accessibility** page appears.</span></span>
1. <span data-ttu-id="7b970-129">Une fois l’analyse terminée, examinez le contenu du rapport.</span><span class="sxs-lookup"><span data-stu-id="7b970-129">After the scan is completed, review the contents of the report.</span></span>
1. <span data-ttu-id="7b970-130">Si des vérifications ont échoué, sélectionnez chaque élément de vérification ayant échoué pour le développer afin de pouvoir afficher plus de détails.</span><span class="sxs-lookup"><span data-stu-id="7b970-130">If any checks failed, select each failed check item to expand it so that you can view more details.</span></span>
1. <span data-ttu-id="7b970-131">Pour fermer le rapport après l’avoir examiné, faites défiler vers le bas de la page **Vérifier l’accessibilité** et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b970-131">To close the report after you've finished reviewing it, scroll to the bottom of the **Check Accessibility** page, and select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7b970-132">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="7b970-132">Additional resources</span></span>

[<span data-ttu-id="7b970-133">Modifier une page de site existante</span><span class="sxs-lookup"><span data-stu-id="7b970-133">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="7b970-134">Ajouter une nouvelle page de site</span><span class="sxs-lookup"><span data-stu-id="7b970-134">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="7b970-135">Sélectionner des dispositions de page</span><span class="sxs-lookup"><span data-stu-id="7b970-135">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="7b970-136">Gestion des métadonnées SEO</span><span class="sxs-lookup"><span data-stu-id="7b970-136">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="7b970-137">Enregistrer, afficher un aperçu et publier une page</span><span class="sxs-lookup"><span data-stu-id="7b970-137">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="7b970-138">Enrichir une page de produit</span><span class="sxs-lookup"><span data-stu-id="7b970-138">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="7b970-139">Enrichir une page d’arrivée de catégorie</span><span class="sxs-lookup"><span data-stu-id="7b970-139">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="7b970-140">Créer des pages e-commerce dynamiques basées sur des paramètres d’URL</span><span class="sxs-lookup"><span data-stu-id="7b970-140">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
