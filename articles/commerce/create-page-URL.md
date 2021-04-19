---
title: Créer une URL de page
description: Cette rubrique présente les concepts et les procédures fondamentaux pour créer une URL de page sur votre site.
author: bicyclingfool
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 98743d8948669f32d3c74e1915c7ed53db81141c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795689"
---
# <a name="create-a-page-url"></a><span data-ttu-id="41361-103">Créer une URL de page</span><span class="sxs-lookup"><span data-stu-id="41361-103">Create a page URL</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="41361-104">Cette rubrique présente les concepts et les procédures fondamentaux pour créer une URL de page sur votre site.</span><span class="sxs-lookup"><span data-stu-id="41361-104">This topic covers the basic concepts and procedures for creating a page URL on your site.</span></span>

<span data-ttu-id="41361-105">L’URL totale, ou absolue, qui désigne une page sur votre site est constituée de pièces distinctes.</span><span class="sxs-lookup"><span data-stu-id="41361-105">The full, or absolute, URL that points to a page on your site consists of distinct parts.</span></span> <span data-ttu-id="41361-106">Par exemple, l’URL `https://www.contoso.com/en-us/contactus` a les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="41361-106">For example, the URL `https://www.contoso.com/en-us/contactus` has the following parts:</span></span>

- <span data-ttu-id="41361-107">`https://www.contoso.com` – Le protocole HTTP et le domaine du site.</span><span class="sxs-lookup"><span data-stu-id="41361-107">`https://www.contoso.com` – The HTTP protocol and the site's domain.</span></span>
- <span data-ttu-id="41361-108">`/en-us` – Le chemin de la langue du site.</span><span class="sxs-lookup"><span data-stu-id="41361-108">`/en-us` – The site's language path.</span></span>
- <span data-ttu-id="41361-109">`/contactus` – L’URL relative de la page **Nous contacter**.</span><span class="sxs-lookup"><span data-stu-id="41361-109">`/contactus` – The relative URL for the **Contact Us** page.</span></span> <span data-ttu-id="41361-110">Une URL relative est également appelée *slug* URL.</span><span class="sxs-lookup"><span data-stu-id="41361-110">A relative URL is also known as a URL *slug*.</span></span>

<span data-ttu-id="41361-111">Vous établissez le domaine du site et le chemin d’accès facultatif de la langue lorsque vous paramétrez le site.</span><span class="sxs-lookup"><span data-stu-id="41361-111">You establish your site's domain and optional language path when you set up the site.</span></span> <span data-ttu-id="41361-112">Vous pouvez ajouter des chemins de domaines et de langue à votre site via la page de magasins en ligne dans les paramètres du site.</span><span class="sxs-lookup"><span data-stu-id="41361-112">You can add more domains and language paths to your site through the online stores page in the site's settings.</span></span>

<span data-ttu-id="41361-113">Le slug URL pour une page existe comme entité autonome dans le site de création de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="41361-113">The URL slug for a page exists as a standalone entity in the site authoring environment.</span></span> <span data-ttu-id="41361-114">Une URL de page est composé de deux parties : un nom qui représente le slug URL, et un pointeur vers une page sur votre site ou un site externe.</span><span class="sxs-lookup"><span data-stu-id="41361-114">A page URL consists of two parts: a name that represents the URL slug, and a pointer to a page on either your site or an external site.</span></span> <span data-ttu-id="41361-115">Une URL de page peut également être configurée pour servir de redirection vers une autre page sur votre site ou un site externe.</span><span class="sxs-lookup"><span data-stu-id="41361-115">A page URL can also be configured to act as a redirect to another page on either your site or an external site.</span></span>

## <a name="create-a-page-url"></a><span data-ttu-id="41361-116">Créer une URL de page</span><span class="sxs-lookup"><span data-stu-id="41361-116">Create a page URL</span></span>

<span data-ttu-id="41361-117">Il existe deux façons de créer des URL de la page :</span><span class="sxs-lookup"><span data-stu-id="41361-117">There are two ways to create page URLs:</span></span>

- <span data-ttu-id="41361-118">Automatiquement, lorsque vous créez une page</span><span class="sxs-lookup"><span data-stu-id="41361-118">Automatically, when you create a page</span></span>
- <span data-ttu-id="41361-119">Manuellement, dans la page **URL**</span><span class="sxs-lookup"><span data-stu-id="41361-119">Manually, from the **URLs** page</span></span>

### <a name="create-a-page-url-when-you-create-a-page"></a><span data-ttu-id="41361-120">Créer une URL de page lorsque vous créez une page</span><span class="sxs-lookup"><span data-stu-id="41361-120">Create a page URL when you create a page</span></span>

<span data-ttu-id="41361-121">Si vous fournissez un nom dans le champ **URL** lorsque vous créez une page, une URL de page qui indique cette page est automatiquement créée dans la page **URL**.</span><span class="sxs-lookup"><span data-stu-id="41361-121">If you provide a name in the **URL** field when you create a new page, a page URL that points to that page is automatically created on the **URLs** page.</span></span> <span data-ttu-id="41361-122">Une fois publié l’URL et la page vers laquelle elle pointe, les utilisateurs de sites (vos clients) peuvent accéder à la page associée à l’URL.</span><span class="sxs-lookup"><span data-stu-id="41361-122">After you publish the URL and the page that it points to, site users (your customers) can access the page that is associated with the URL.</span></span>

> [!NOTE]
> <span data-ttu-id="41361-123">Si vous publiez une URL sans publier la page vers laquelle elle pointe, les utilisateurs de site reçoivent une erreur 404 lorsqu’ils essayent d’accéder à la page.</span><span class="sxs-lookup"><span data-stu-id="41361-123">If you publish a URL without publishing the page that it points to, site users receive a 404 error when they try to access the page.</span></span> <span data-ttu-id="41361-124">Si vous publiez une page sans publier l’URL pour pointer vers celle-ci, la page ne peut pas accéder à l’aide d’une URL.</span><span class="sxs-lookup"><span data-stu-id="41361-124">If you publish a page without publishing the URL that points to it, the page can't be accessed by using a URL.</span></span>

### <a name="manually-create-a-page-url"></a><span data-ttu-id="41361-125">Créer manuellement une URL de page</span><span class="sxs-lookup"><span data-stu-id="41361-125">Manually create a page URL</span></span>

<span data-ttu-id="41361-126">Lorsque vous créez des pages, vous n’êtes pas obligé de spécifier une URL de la page.</span><span class="sxs-lookup"><span data-stu-id="41361-126">When you create new pages, you aren't required to specify a page URL.</span></span> <span data-ttu-id="41361-127">Si vous laissez le champ vide URL, la page est créée dans un état dissocié.</span><span class="sxs-lookup"><span data-stu-id="41361-127">If you leave the URL field blank, the page is created in an unlinked state.</span></span> <span data-ttu-id="41361-128">Dans ce cas, les clients ne peuvent pas accéder à la page, même si elle est publiée.</span><span class="sxs-lookup"><span data-stu-id="41361-128">In this case, customers won't be able to access the page, even if it's published.</span></span> <span data-ttu-id="41361-129">Pour rendre la page accessible, vous devez créer manuellement l’URL et la lier à la page.</span><span class="sxs-lookup"><span data-stu-id="41361-129">To make the page accessible, you must manually create the URL and link it to the page.</span></span>

<span data-ttu-id="41361-130">Pour créer manuellement l’URL de page pour une page, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="41361-130">To manually create the page URL for a page, follow these steps.</span></span>

1. <span data-ttu-id="41361-131">Dans la page **URL**, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="41361-131">On the **URLs** page, select **New**.</span></span>
1. <span data-ttu-id="41361-132">Sélectionnez la page du site à associer à l’URL.</span><span class="sxs-lookup"><span data-stu-id="41361-132">Select the site page to associate with the URL.</span></span>
1. <span data-ttu-id="41361-133">Entrez le slug URL, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="41361-133">Enter the URL slug, and then select **OK**.</span></span>

<span data-ttu-id="41361-134">À ce stade, l’URL est dans un état de brouillon.</span><span class="sxs-lookup"><span data-stu-id="41361-134">At this point, the URL is in a draft state.</span></span> <span data-ttu-id="41361-135">Elle doit être publiée avant que les utilisateurs de site puissent accéder à la page associée.</span><span class="sxs-lookup"><span data-stu-id="41361-135">It must be published before site users can access the associated page.</span></span>

## <a name="update-a-page-url"></a><span data-ttu-id="41361-136">Mettre à jour une URL de page</span><span class="sxs-lookup"><span data-stu-id="41361-136">Update a page URL</span></span>

<span data-ttu-id="41361-137">Pour mettre à jour la page cible d’une URL de page, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="41361-137">To update the target page of a page URL, follow these steps.</span></span>

1. <span data-ttu-id="41361-138">Dans la page **URL**, sélectionnez l’URL à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="41361-138">On the **URLs** page, select the URL to update.</span></span>
1. <span data-ttu-id="41361-139">Dans le volet de propriétés à droite, sélectionnez le bouton représentant des points de suspension (**...**) en regard de le champ cible de page.</span><span class="sxs-lookup"><span data-stu-id="41361-139">In the property pane on the right, select the ellipsis button (**...**) next to the target page field.</span></span>
1. <span data-ttu-id="41361-140">Dans la boîte de dialogue, sélectionnez une autre page, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="41361-140">In the dialog box, select a different page, and then select **OK**.</span></span>
1. <span data-ttu-id="41361-141">Enregistrez et publiez l’URL.</span><span class="sxs-lookup"><span data-stu-id="41361-141">Save and publish the URL.</span></span>

## <a name="redirect-a-page-url"></a><span data-ttu-id="41361-142">Rediriger une URL de page</span><span class="sxs-lookup"><span data-stu-id="41361-142">Redirect a page URL</span></span>

<span data-ttu-id="41361-143">Parfois, vous pouvez vouloir que vos clients affichent une autre page lorsqu’ils demandent une URL spécifique.</span><span class="sxs-lookup"><span data-stu-id="41361-143">Sometimes, you might want your customers to view a different page when they request a specific URL.</span></span> <span data-ttu-id="41361-144">Dans ces cas, la meilleure approche, et la plus simple, est souvent de modifier la page vers laquelle l’URL pointe.</span><span class="sxs-lookup"><span data-stu-id="41361-144">In these cases, the best and easiest approach is often to change the page that the page URL points to.</span></span> <span data-ttu-id="41361-145">Toutefois, vous pouvez avoir des motifs légitimes pour l’utilisation de redirections HTTP 301 ou 3023 pour rediriger les demandes d’URL vers une URL différent.</span><span class="sxs-lookup"><span data-stu-id="41361-145">However, you might have legitimate reasons for using HTTP 301 or 3023 redirects to redirect requests for a URL to a different URL.</span></span>

<span data-ttu-id="41361-146">Pour rediriger une URL vers une URL différent, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="41361-146">To redirect a URL to a different URL, follow these steps.</span></span>

1. <span data-ttu-id="41361-147">Dans la page **URL**, sélectionnez l’URL à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="41361-147">On the **URLs** page, select the URL to update.</span></span>
1. <span data-ttu-id="41361-148">Dans le volet de propriétés de droite, sélectionnez **Redirigez**.</span><span class="sxs-lookup"><span data-stu-id="41361-148">In the property pane on the right, select **Redirect**.</span></span>
1. <span data-ttu-id="41361-149">Sélectionnez une destination pour la redirection :</span><span class="sxs-lookup"><span data-stu-id="41361-149">Select a destination for the redirect:</span></span>

    - <span data-ttu-id="41361-150">Pour pointer vers une autre page sur votre site, sélectionnez **URL interne**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez l’URL pour rediriger sur.</span><span class="sxs-lookup"><span data-stu-id="41361-150">To point to another page on your site, select **Internal URL**, select the ellipsis button (**...**), and then select the URL to redirect to.</span></span>
    - <span data-ttu-id="41361-151">Pour pointer vers une page sur un site externe, sélectionnez **URL externe**, puis entrez l’URL complète de cette page.</span><span class="sxs-lookup"><span data-stu-id="41361-151">To point to a page on an external site, select **External URL**, and then enter the full URL for that page.</span></span> <span data-ttu-id="41361-152">Veillez à inclure le protocole.</span><span class="sxs-lookup"><span data-stu-id="41361-152">Be sure to include the protocol.</span></span> <span data-ttu-id="41361-153">Par exemple, entrez `https://domain.com/new/page`.</span><span class="sxs-lookup"><span data-stu-id="41361-153">For example, enter `https://domain.com/new/page`.</span></span> <span data-ttu-id="41361-154">Si l’URL redirige déjà vers une URL interne, vous devez sélectionner **Effacer la sélection** avant de pouvoir entrer une URL externe.</span><span class="sxs-lookup"><span data-stu-id="41361-154">If the URL already redirects to an internal URL, you must select **Clear selection** before you can enter an external URL.</span></span>

1. <span data-ttu-id="41361-155">Sélectionner un type de redirection :</span><span class="sxs-lookup"><span data-stu-id="41361-155">Select a redirect type:</span></span>

    - <span data-ttu-id="41361-156">**Redirection permanente (301)** – Sélectionnez cette option si vous savez que votre contenu se déplacera en permanence et ne rétablira pas son URL précédent.</span><span class="sxs-lookup"><span data-stu-id="41361-156">**Permanent redirect (301)** – Select this option when you know that your content is moving permanently and won't revert to its previous URL.</span></span> <span data-ttu-id="41361-157">Les moteurs de recherche affecteront la valeur de l’optimisation du moteur de recherche (SEO) de l’URL de redirection à l’URL vers laquelle elle est redirigée et mettront à jour leur enregistrement pour afficher la nouvelle URL.</span><span class="sxs-lookup"><span data-stu-id="41361-157">Search engines will assign the search engine optimization (SEO) value of the redirecting URL to the URL that is being redirected to and update their record to show the new URL.</span></span> 
    - <span data-ttu-id="41361-158">**Redirection provisoire (302)** – Sélectionnez cette option pour rediriger le trafic sans mettre à jour les moteurs de recherche.</span><span class="sxs-lookup"><span data-stu-id="41361-158">**Temporary redirect (302)** – Select this option to redirect traffic without updating search engines.</span></span> <span data-ttu-id="41361-159">Cette méthode est généralement utilisée si le contenu reviendra bientôt à son URL précédent.</span><span class="sxs-lookup"><span data-stu-id="41361-159">This approach is typically used if the content will soon revert to its previous URL.</span></span>

1. <span data-ttu-id="41361-160">Lorsque vous êtes prêt à implémenter la redirection, enregistrez et publiez l’URL.</span><span class="sxs-lookup"><span data-stu-id="41361-160">When you're ready to implement the redirect, save and publish the URL.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="41361-161">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="41361-161">Additional resources</span></span>

[<span data-ttu-id="41361-162">Personnaliser la navigation dans le site</span><span class="sxs-lookup"><span data-stu-id="41361-162">Customize site navigation</span></span>](customize-site-navigation.md)

[<span data-ttu-id="41361-163">Ajouter une nouvelle page de site</span><span class="sxs-lookup"><span data-stu-id="41361-163">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="41361-164">Configuration du nom de domaine</span><span class="sxs-lookup"><span data-stu-id="41361-164">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="41361-165">Ajouter des langues à votre site</span><span class="sxs-lookup"><span data-stu-id="41361-165">Add languages to your site</span></span>](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
