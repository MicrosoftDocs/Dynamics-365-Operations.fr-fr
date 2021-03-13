---
title: Créer des pages d'e-commerce dynamiques basées sur des paramètres d'URL
description: Cette rubrique décrit comment configurer une page d'e-commerce Microsoft Dynamics 365 Commerce pouvant diffuser du contenu dynamique, en fonction des paramètres d'URL.
author: StuHarg
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: e72b738133b396848848d167cace80fe23694334
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2021
ms.locfileid: "5098625"
---
# <a name="create-dynamic-e-commerce-pages-based-on-url-parameters"></a><span data-ttu-id="af073-103">Créer des pages d'e-commerce dynamiques basées sur des paramètres d'URL</span><span class="sxs-lookup"><span data-stu-id="af073-103">Create dynamic e-commerce pages based on URL parameters</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="af073-104">Cette rubrique décrit comment configurer une page d'e-commerce Microsoft Dynamics 365 Commerce pouvant diffuser du contenu dynamique, en fonction des paramètres d'URL.</span><span class="sxs-lookup"><span data-stu-id="af073-104">This topic describes how to set up a Microsoft Dynamics 365 Commerce e-commerce page that can serve dynamic content, based on URL parameters.</span></span>

<span data-ttu-id="af073-105">Une page d'e-commerce peut être configurée pour diffuser un contenu différent, en fonction d'un segment dans le chemin de l'URL.</span><span class="sxs-lookup"><span data-stu-id="af073-105">An e-commerce page can be configured to serve different content, based on a segment in the URL path.</span></span> <span data-ttu-id="af073-106">Par conséquent, la page est appelée page dynamique.</span><span class="sxs-lookup"><span data-stu-id="af073-106">Therefore, the page is known as a dynamic page.</span></span> <span data-ttu-id="af073-107">Le segment est utilisé comme paramètre pour récupérer le contenu de la page.</span><span class="sxs-lookup"><span data-stu-id="af073-107">The segment is used as a parameter to retrieve the page content.</span></span> <span data-ttu-id="af073-108">Par exemple, une page nommée **blog\_observateur** est créée et associée à l'URL `https://fabrikam.com/blog`.</span><span class="sxs-lookup"><span data-stu-id="af073-108">For example, a page that is named **blog\_viewer** is created and associated with the URL `https://fabrikam.com/blog`.</span></span> <span data-ttu-id="af073-109">Cette page peut ensuite être utilisée pour afficher un contenu différent, en fonction du dernier segment du chemin de l'URL.</span><span class="sxs-lookup"><span data-stu-id="af073-109">This page can then be used to show different content, based on the last segment in the URL path.</span></span> <span data-ttu-id="af073-110">Par exemple, le dernier segment de l'URL `https://fabrikam.com/blog/article-1` est **article-1**.</span><span class="sxs-lookup"><span data-stu-id="af073-110">For example, the last segment in the URL `https://fabrikam.com/blog/article-1` is **article-1**.</span></span>

<span data-ttu-id="af073-111">Des pages personnalisées distinctes qui remplacent la page dynamique peuvent également être associées à des segments dans le chemin de l'URL.</span><span class="sxs-lookup"><span data-stu-id="af073-111">Separate custom pages that override the dynamic page can also be associated with segments in the URL path.</span></span> <span data-ttu-id="af073-112">Par exemple, une page nommée **blog\_résumé** est créée et associée à l'URL `https://fabrikam.com/blog/about-this-blog`.</span><span class="sxs-lookup"><span data-stu-id="af073-112">For example, a page that is named **blog\_summary** is created and associated with the URL `https://fabrikam.com/blog/about-this-blog`.</span></span> <span data-ttu-id="af073-113">Lorsque cette URL est demandée, la page **blog\_résumé** associée au paramètre **/about-this-blog** est renvoyée à la place de la page **blog\_observateur**.</span><span class="sxs-lookup"><span data-stu-id="af073-113">When this URL is requested, the **blog\_summary** page that is associated with the **/about-this-blog** parameter is returned instead of the **blog\_viewer** page.</span></span>

> [!NOTE]
> <span data-ttu-id="af073-114">La fonctionnalité d'hébergement, de récupération et d'affichage du contenu de page dynamique est implémentée à l'aide d'un module personnalisé.</span><span class="sxs-lookup"><span data-stu-id="af073-114">The functionality for hosting, retrieving, and showing dynamic page content is implemented by using a custom module.</span></span> <span data-ttu-id="af073-115">Pour plus d'informations, consultez [Extensibilité des canaux en ligne](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="af073-115">For more information, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

## <a name="set-up-a-dynamic-e-commerce-page"></a><span data-ttu-id="af073-116">Configurer une page d'e-commerce dynamique</span><span class="sxs-lookup"><span data-stu-id="af073-116">Set up a dynamic e-commerce page</span></span>

<span data-ttu-id="af073-117">Pour configurer une page d'e-commerce dynamique, vous devez créer la page dynamique, créer l'URL de base et configurer l'itinéraire vers la page dynamique.</span><span class="sxs-lookup"><span data-stu-id="af073-117">To set up a dynamic e-commerce page, you must create the dynamic page, create the base URL, and configure the route to the dynamic page.</span></span>

### <a name="create-the-page-that-will-serve-dynamic-content"></a><span data-ttu-id="af073-118">Créer la page qui diffusera du contenu dynamique</span><span class="sxs-lookup"><span data-stu-id="af073-118">Create the page that will serve dynamic content</span></span>

<span data-ttu-id="af073-119">Pour créer une page qui diffusera du contenu dynamique, suivez les étapes de la rubrique [Ajouter une nouvelle page de site](add-new-page.md).</span><span class="sxs-lookup"><span data-stu-id="af073-119">To create a page that will serve dynamic content, follow the steps in [Add a new site page](add-new-page.md).</span></span> <span data-ttu-id="af073-120">La page que vous créez nécessitera l'implémentation d'un module qui utilise le dernier segment du chemin d'URL pour récupérer le contenu d'une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="af073-120">The page that you create will require implementation of a module that uses the last segment in the URL path to retrieve content from an external data source.</span></span> <span data-ttu-id="af073-121">Pour plus d'informations sur le développement de modules personnalisés, consultez la rubrique [Extensibilité des canaux en ligne](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="af073-121">For more information about custom module development, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

### <a name="create-the-base-url-for-the-dynamic-page"></a><span data-ttu-id="af073-122">Créer l'URL de base pour la page dynamique</span><span class="sxs-lookup"><span data-stu-id="af073-122">Create the base URL for the dynamic page</span></span>

<span data-ttu-id="af073-123">Pour créer l'URL de base de la page dynamique dans le générateur de site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="af073-123">To create the base URL for the dynamic page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="af073-124">Accédez à **URL**, et sélectionnez **Nouveau \> Nouvelle URL**.</span><span class="sxs-lookup"><span data-stu-id="af073-124">Go to **URLs**, and select **New \> New URL**.</span></span>
1. <span data-ttu-id="af073-125">Dans la boîte de dialogue **Créer une nouvelle URL**, sélectionnez **Page interne**.</span><span class="sxs-lookup"><span data-stu-id="af073-125">In the **Create new URL** dialog box, select **Internal page**.</span></span> <span data-ttu-id="af073-126">Sous **Chemin de l'URL**, entrez le chemin qui servira de racine à la page dynamique (dans cet exemple, **/blog**).</span><span class="sxs-lookup"><span data-stu-id="af073-126">Under **URL path**, enter the path that will serve as the root for the dynamic page (in this example, **/blog**).</span></span> <span data-ttu-id="af073-127">Sélectionnez ensuite **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="af073-127">Then select **Next**.</span></span>
1. <span data-ttu-id="af073-128">Dans la boîte de dialogue **Sélectionner une page**, sélectionnez la page que vous avez créée pour servir de page dynamique, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="af073-128">In the **Select a page** dialog box, select the page that you created to serve as the dynamic page, and then select **Save**.</span></span>
1. <span data-ttu-id="af073-129">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="af073-129">Select **Publish**.</span></span>

### <a name="configure-the-route-to-the-dynamic-page"></a><span data-ttu-id="af073-130">Configurer l'itinéraire vers la page dynamique</span><span class="sxs-lookup"><span data-stu-id="af073-130">Configure the route to the dynamic page</span></span>

<span data-ttu-id="af073-131">Pour configurer l'itinéraire vers la page dynamique dans le générateur de site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="af073-131">To configure the route to the dynamic page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="af073-132">Accédez à **Paramètres du site \> Extensions**.</span><span class="sxs-lookup"><span data-stu-id="af073-132">Go to **Site Settings \> Extensions**.</span></span>
1. <span data-ttu-id="af073-133">Sous **Chemins d'URL paramétrés**, sélectionnez **Ajouter**, puis entrez le chemin de l'URL que vous avez entré lors de la création de l'URL (dans cet exemple, **/blog**).</span><span class="sxs-lookup"><span data-stu-id="af073-133">Under **Parameterized URL paths**, select **Add**, and then enter the URL path that you entered when you created the URL (in this example, **/blog**).</span></span>
1. <span data-ttu-id="af073-134">Sélectionnez **Enregistrer et publier**.</span><span class="sxs-lookup"><span data-stu-id="af073-134">Select **Save and publish**.</span></span>

<span data-ttu-id="af073-135">Une fois l'itinéraire configuré, toutes les demandes adressées au chemin d'URL paramétré renverront la page associée à cette URL.</span><span class="sxs-lookup"><span data-stu-id="af073-135">After the route is configured, all requests to the parameterized URL path will return the page that is associated with that URL.</span></span> <span data-ttu-id="af073-136">Si des demandes contiennent un segment supplémentaire, la page associée sera renvoyée et le contenu de la page sera récupéré en utilisant le segment comme paramètre.</span><span class="sxs-lookup"><span data-stu-id="af073-136">If any requests contain an additional segment, the associated page will be returned, and the page content will be retrieved by using the segment as a parameter.</span></span> <span data-ttu-id="af073-137">Par exemple, `https://fabrikam.com/blog/article-1` retournera la page **blog\_résumé**, et le contenu de la page sera récupéré en utilisant le paramètre **/article-1**.</span><span class="sxs-lookup"><span data-stu-id="af073-137">For example, `https://fabrikam.com/blog/article-1` will return the **blog\_summary** page, and the page content will be retrieved by using the **/article-1** parameter.</span></span>

## <a name="override-a-parameterized-url-with-a-custom-page"></a><span data-ttu-id="af073-138">Remplacer une URL paramétrée par une page personnalisée</span><span class="sxs-lookup"><span data-stu-id="af073-138">Override a parameterized URL with a custom page</span></span>

<span data-ttu-id="af073-139">Pour remplacer une URL paramétrée par une page personnalisée dans le générateur de site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="af073-139">To override a parameterized URL with a custom page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="af073-140">Accédez à **URL**, et sélectionnez **Nouveau \> Nouvelle URL**.</span><span class="sxs-lookup"><span data-stu-id="af073-140">Go to **URLs**, and select **New \> New URL**.</span></span>
1. <span data-ttu-id="af073-141">Dans la boîte de dialogue **Créer une nouvelle URL**, sélectionnez **Page interne**.</span><span class="sxs-lookup"><span data-stu-id="af073-141">In the **Create new URL** dialog box, select **Internal page**.</span></span> <span data-ttu-id="af073-142">Sous **Chemin de l'URL**, entrez le chemin qui inclut le segment à remplacer (dans cet exemple, **/blog/about-this-blog**).</span><span class="sxs-lookup"><span data-stu-id="af073-142">Under **URL path**, enter the path that includes the segment to override (in this example, **/blog/about-this-blog**).</span></span> <span data-ttu-id="af073-143">Sélectionnez ensuite **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="af073-143">Then select **Next**.</span></span>
1. <span data-ttu-id="af073-144">Dans la boîte de dialogue **Sélectionner une page**, sélectionnez la page personnalisée, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="af073-144">In the **Select a page** dialog box, select the custom page, and then select **Save**.</span></span>
1. <span data-ttu-id="af073-145">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="af073-145">Select **Publish**.</span></span>
1. <span data-ttu-id="af073-146">Si la page personnalisée n'a pas encore été publiée, accédez à **Pages**, sélectionnez la page personnalisée, puis sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="af073-146">If the custom page hasn't yet been published, go to **Pages**, select the custom page, and then select **Publish**.</span></span>

<span data-ttu-id="af073-147">Une fois la page personnalisée publiée, elle sera diffusée à la place de la page dynamique dont le contenu est paramétré.</span><span class="sxs-lookup"><span data-stu-id="af073-147">After the custom page is published, it will be served instead of the dynamic page that has parameterized content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="af073-148">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="af073-148">Additional resources</span></span>

[<span data-ttu-id="af073-149">Modifier une page de site existante</span><span class="sxs-lookup"><span data-stu-id="af073-149">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="af073-150">Ajouter une nouvelle page de site</span><span class="sxs-lookup"><span data-stu-id="af073-150">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="af073-151">Sélectionner des dispositions de page</span><span class="sxs-lookup"><span data-stu-id="af073-151">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="af073-152">Gestion des métadonnées SEO</span><span class="sxs-lookup"><span data-stu-id="af073-152">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="af073-153">Enregistrer, afficher un aperçu et publier une page</span><span class="sxs-lookup"><span data-stu-id="af073-153">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="af073-154">Enrichir une page de produit</span><span class="sxs-lookup"><span data-stu-id="af073-154">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="af073-155">Enrichir une page d’arrivée de catégorie</span><span class="sxs-lookup"><span data-stu-id="af073-155">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="af073-156">Vérifier l’accessibilité du contenu de la page</span><span class="sxs-lookup"><span data-stu-id="af073-156">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="af073-157">Extensibilité des canaux en ligne</span><span class="sxs-lookup"><span data-stu-id="af073-157">Online channel extensibility</span></span>](e-commerce-extensibility/overview.md)
