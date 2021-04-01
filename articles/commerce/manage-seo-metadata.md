---
title: Gestion des métadonnées SEO
description: Cette rubrique décrit la procédure de gestion des métadonnées d’optimisation de moteur de recherche (SEO) dans Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 00942befef9f9b6a878766bbbb5341426e31db2c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252604"
---
# <a name="manage-seo-metadata"></a><span data-ttu-id="51d55-103">Gestion des métadonnées SEO</span><span class="sxs-lookup"><span data-stu-id="51d55-103">Manage SEO metadata</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="51d55-104">Cette rubrique décrit la procédure de gestion des métadonnées d’optimisation de moteur de recherche (SEO) dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="51d55-104">This topic describes how to manage search engine optimization (SEO) metadata in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="51d55-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="51d55-105">Overview</span></span>

<span data-ttu-id="51d55-106">Les métadonnées SEO pour un site peuvent être gérées à l'aide des métadonnées de plans et de pages du site.</span><span class="sxs-lookup"><span data-stu-id="51d55-106">SEO metadata for a site can be managed by using site maps and page metadata.</span></span>
    
## <a name="site-maps"></a><span data-ttu-id="51d55-107">Plans de site</span><span class="sxs-lookup"><span data-stu-id="51d55-107">Site maps</span></span>

<span data-ttu-id="51d55-108">Un plan de site est une liste lisible par une machine, au format XML, des pages sur votre site web.</span><span class="sxs-lookup"><span data-stu-id="51d55-108">A site map is a machine-readable list, in XML format, of the pages on your website.</span></span> <span data-ttu-id="51d55-109">Il doit être consommé par des moteurs de recherche, afin de pouvoir fournir de meilleurs résultats de recherche pour votre site.</span><span class="sxs-lookup"><span data-stu-id="51d55-109">It's intended to be consumed by search engines, so that they can provide better search results from your site.</span></span> <span data-ttu-id="51d55-110">Les plans de site peuvent être manuellement ingérés par les moteurs de recherche ou publiés dans un fichier robots.txt.</span><span class="sxs-lookup"><span data-stu-id="51d55-110">Site maps can be manually ingested by search engines or published in a robots.txt file.</span></span>

<span data-ttu-id="51d55-111">Dynamics 365 Commerce prend en charge la génération automatique des plans de site.</span><span class="sxs-lookup"><span data-stu-id="51d55-111">Dynamics 365 Commerce supports automatic generation of site maps.</span></span> <span data-ttu-id="51d55-112">Les plans de site sont automatiquement mis à jour lorsque les pages sont publiées et non publiées.</span><span class="sxs-lookup"><span data-stu-id="51d55-112">Site maps are automatically updated when pages are published and unpublished.</span></span>

### <a name="turn-on-site-map-generation"></a><span data-ttu-id="51d55-113">Activer la génération de plan de site</span><span class="sxs-lookup"><span data-stu-id="51d55-113">Turn on site map generation</span></span>

1. <span data-ttu-id="51d55-114">Connectez-vous à l'outil de création.</span><span class="sxs-lookup"><span data-stu-id="51d55-114">Sign in to the authoring tool.</span></span>
1. <span data-ttu-id="51d55-115">Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).</span><span class="sxs-lookup"><span data-stu-id="51d55-115">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="51d55-116">Dans le volet de navigation sur la gauche, sélectionnez **Gestion du site**.</span><span class="sxs-lookup"><span data-stu-id="51d55-116">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="51d55-117">Assurez-vous que l'option **Plans de site activés** est activée.</span><span class="sxs-lookup"><span data-stu-id="51d55-117">Make sure that the **Site maps enabled** option is turned on.</span></span>

## <a name="page-metadata"></a><span data-ttu-id="51d55-118">Métadonnées de la page</span><span class="sxs-lookup"><span data-stu-id="51d55-118">Page metadata</span></span>

<span data-ttu-id="51d55-119">Dynamics 365 Commerce vous permet de gérer des métadonnées SEO pour diverses pages.</span><span class="sxs-lookup"><span data-stu-id="51d55-119">Dynamics 365 Commerce lets you manage SEO metadata for individual pages.</span></span> <span data-ttu-id="51d55-120">Vous pouvez afficher et modifier ces informations dans la section **Propriétés SEO** d'un conteneur de page.</span><span class="sxs-lookup"><span data-stu-id="51d55-120">You can view and modify this information in the **SEO Properties** section of a page container.</span></span> <span data-ttu-id="51d55-121">Les propriétés de métadonnées SEO suivantes sont actuellement prises en charge :</span><span class="sxs-lookup"><span data-stu-id="51d55-121">The following SEO metadata properties are supported:</span></span>

- <span data-ttu-id="51d55-122">Titre</span><span class="sxs-lookup"><span data-stu-id="51d55-122">Title</span></span>
- <span data-ttu-id="51d55-123">Description</span><span class="sxs-lookup"><span data-stu-id="51d55-123">Description</span></span>
- <span data-ttu-id="51d55-124">Mots clés SEO</span><span class="sxs-lookup"><span data-stu-id="51d55-124">SEO keywords</span></span>
- <span data-ttu-id="51d55-125">Étiquettes Aria</span><span class="sxs-lookup"><span data-stu-id="51d55-125">Aria labels</span></span>
- <span data-ttu-id="51d55-126">noindex</span><span class="sxs-lookup"><span data-stu-id="51d55-126">noindex</span></span>
- <span data-ttu-id="51d55-127">nofollow</span><span class="sxs-lookup"><span data-stu-id="51d55-127">nofollow</span></span>
- <span data-ttu-id="51d55-128">noarchive</span><span class="sxs-lookup"><span data-stu-id="51d55-128">noarchive</span></span>
- <span data-ttu-id="51d55-129">nocache</span><span class="sxs-lookup"><span data-stu-id="51d55-129">nocache</span></span>
- <span data-ttu-id="51d55-130">noOpenDirectoryProject</span><span class="sxs-lookup"><span data-stu-id="51d55-130">noOpenDirectoryProject</span></span>
- <span data-ttu-id="51d55-131">nosnippet</span><span class="sxs-lookup"><span data-stu-id="51d55-131">nosnippet</span></span>
- <span data-ttu-id="51d55-132">noImageIndex</span><span class="sxs-lookup"><span data-stu-id="51d55-132">noImageIndex</span></span>
- <span data-ttu-id="51d55-133">unavailableAfter</span><span class="sxs-lookup"><span data-stu-id="51d55-133">unavailableAfter</span></span>

### <a name="modify-page-metadata"></a><span data-ttu-id="51d55-134">Modification des métadonnées de page</span><span class="sxs-lookup"><span data-stu-id="51d55-134">Modify page metadata</span></span>

<span data-ttu-id="51d55-135">Pour modifier les métadonnées de page, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="51d55-135">To modify page metadata, follow these steps.</span></span>

1. <span data-ttu-id="51d55-136">Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).</span><span class="sxs-lookup"><span data-stu-id="51d55-136">Under **Sites**, select the **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="51d55-137">Dans le volet de navigation sur la gauche, sélectionnez **Pages**.</span><span class="sxs-lookup"><span data-stu-id="51d55-137">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="51d55-138">Sélectionnez la page d'accueil pour l'ouvrir dans l'éditeur de page.</span><span class="sxs-lookup"><span data-stu-id="51d55-138">Select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="51d55-139">Dans la barre de commande, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="51d55-139">On the command bar, select **Edit**.</span></span>
1. <span data-ttu-id="51d55-140">Dans le volet de propriétés de droite, Développez **Métabalises par défaut**.</span><span class="sxs-lookup"><span data-stu-id="51d55-140">In the properties pane on the right, expand **Default metatags**.</span></span>
1. <span data-ttu-id="51d55-141">Pour ajouter une nouvelle métabalise, sélectionnez **Ajouter**, puis entrez la balise dans le champ.</span><span class="sxs-lookup"><span data-stu-id="51d55-141">To add a new metatag, select **Add**, and then enter the tag in the field.</span></span> <span data-ttu-id="51d55-142">Pour supprimer une métabalise existante, sélectionnez le symbole de corbeille à droite de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="51d55-142">To remove an existing metatag, select the trash can symbol to the right of it.</span></span>
1. <span data-ttu-id="51d55-143">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="51d55-143">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="51d55-144">Dans le champ **Commentaires**, entrez **Métabalises mises à jour**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="51d55-144">In the **Comments** field, enter **Updated metatags**, and then select **OK**.</span></span>
1. <span data-ttu-id="51d55-145">Sélectionnez **Aperçu** pour prévisualiser votre page avant impression.</span><span class="sxs-lookup"><span data-stu-id="51d55-145">Select **Preview** to preview your page.</span></span> <span data-ttu-id="51d55-146">Lorsque vous avez terminé, fermez l'onglet d'aperçu pour revenir à l'outil d'édition.</span><span class="sxs-lookup"><span data-stu-id="51d55-146">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="51d55-147">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="51d55-147">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="51d55-148">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="51d55-148">Additional resources</span></span>

[<span data-ttu-id="51d55-149">Modifier une page de site existante</span><span class="sxs-lookup"><span data-stu-id="51d55-149">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="51d55-150">Ajouter une nouvelle page de site</span><span class="sxs-lookup"><span data-stu-id="51d55-150">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="51d55-151">Sélectionner des dispositions de page</span><span class="sxs-lookup"><span data-stu-id="51d55-151">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="51d55-152">Enregistrer, afficher un aperçu et publier une page</span><span class="sxs-lookup"><span data-stu-id="51d55-152">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="51d55-153">Enrichir une page de produit</span><span class="sxs-lookup"><span data-stu-id="51d55-153">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="51d55-154">Enrichir une page d’arrivée de catégorie</span><span class="sxs-lookup"><span data-stu-id="51d55-154">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="51d55-155">Vérifier l’accessibilité du contenu de la page</span><span class="sxs-lookup"><span data-stu-id="51d55-155">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="51d55-156">Créer des pages e-commerce dynamiques basées sur des paramètres d'URL</span><span class="sxs-lookup"><span data-stu-id="51d55-156">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]