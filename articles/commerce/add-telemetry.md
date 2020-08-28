---
title: Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie
description: Cette rubrique décrit comment ajouter un code du script côté client à vos pages du site pour prendre en charge la collection de télémétrie côté client.
author: bicyclingfool
manager: annbe
ms.date: 03/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4f26ed5b6674566f579e801f4b7be63c2d0dc38d
ms.sourcegitcommit: 81f162f2d50557d7afe292c8d326618ba0bc3259
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/11/2020
ms.locfileid: "3686812"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="1e4f2-103">Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie</span><span class="sxs-lookup"><span data-stu-id="1e4f2-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1e4f2-104">Cette rubrique décrit comment ajouter un code du script côté client à vos pages du site pour prendre en charge la collection de télémétrie côté client.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="1e4f2-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="1e4f2-105">Overview</span></span>

<span data-ttu-id="1e4f2-106">Les analyses web sont un outil essentiel lorsque vous souhaitez inclure la manière dont vos clients peuvent interagir avec votre site et prendre des décisions qui aideront à optimiser l’expérience pour la conversion maximale.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="1e4f2-107">De nombreux packages d’analyses web sont disponibles pour vous aider à atteindre ces objectifs, comme Google Analytics, Clicky, Moz Analytics, et KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="1e4f2-108">La plupart des packages d’analyses web nécessitent que vous ajoutiez un code du script côté client dans l’élément **\<head\>** du fichier HTML pour toutes les pages du site.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="1e4f2-109">Les instructions de cette rubrique s’appliquent également à l’autre fonctionnalité côté client personnalisée que Microsoft Dynamics 365 Commerce n’offre pas en mode natif.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-page-fragment-for-your-script-code"></a><span data-ttu-id="1e4f2-110">Créer un fragment de page réutilisable pour votre code de script</span><span class="sxs-lookup"><span data-stu-id="1e4f2-110">Create a reusable page fragment for your script code</span></span>

<span data-ttu-id="1e4f2-111">Un fragment de page vous permet de réutiliser un code de script externe ou en ligne sur toutes les pages de votre site, peu importe le modèle qu’elles utilisent.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-111">A page fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-page-fragment-for-your-inline-script-code"></a><span data-ttu-id="1e4f2-112">Créer un fragment de page réutilisable pour votre code de script en ligne</span><span class="sxs-lookup"><span data-stu-id="1e4f2-112">Create a reusable page fragment for your inline script code</span></span>

<span data-ttu-id="1e4f2-113">Pour créer un fragment de page réutilisable pour votre code de script en ligne dans le générateur de site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-113">To create a reusable page fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="1e4f2-114">Accédez à **Fragments**, puis sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-114">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="1e4f2-115">Dans la boîte de dialogue **Nouveau fragment de page**, sélectionnez **Script en ligne**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-115">In the **New page fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="1e4f2-116">Sous **Nom du fragment de page**, entrez un nom pour le fragment, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-116">Under **Page fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="1e4f2-117">Sous le fragment de page que vous avez créé, sélectionnez le module **Script en ligne par défaut**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-117">Under the page fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="1e4f2-118">Dans le volet des propriétés à droite, sous **Script en ligne**, entrez votre script côté client.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-118">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="1e4f2-119">Puis configurez d’autres options selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-119">Then configure other options as you require.</span></span>
1. <span data-ttu-id="1e4f2-120">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-120">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="1e4f2-121">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-121">Select **Publish**.</span></span>

### <a name="create-a-reusable-page-fragment-for-your-external-script-code"></a><span data-ttu-id="1e4f2-122">Créer un fragment de page réutilisable pour votre code de script externe</span><span class="sxs-lookup"><span data-stu-id="1e4f2-122">Create a reusable page fragment for your external script code</span></span>

<span data-ttu-id="1e4f2-123">Pour créer un fragment de page réutilisable pour votre code de script externe dans le générateur de site, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1e4f2-123">To create a reusable page fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="1e4f2-124">Accédez à **Fragments**, puis sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-124">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="1e4f2-125">Dans la boîte de dialogue **Nouveau fragment de page**, sélectionnez **Script externe**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-125">In the **New page fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="1e4f2-126">Sous **Nom du fragment de page**, entrez un nom pour le fragment, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-126">Under **Page fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="1e4f2-127">Sous le fragment de page que vous avez créé, sélectionnez le module **Script externe par défaut**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-127">Under the page fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="1e4f2-128">Dans le volet des propriétés à droite, sous **Source du script**, ajoutez une URL externe ou relative pour la source de script externe.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-128">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="1e4f2-129">Puis configurez d’autres options selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-129">Then configure other options as you require.</span></span>
1. <span data-ttu-id="1e4f2-130">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="1e4f2-131">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-131">Select **Publish**.</span></span>

## <a name="add-a-page-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="1e4f2-132">Ajouter un fragment de page qui inclut le code de script à un modèle</span><span class="sxs-lookup"><span data-stu-id="1e4f2-132">Add a page fragment that includes script code to a template</span></span>

<span data-ttu-id="1e4f2-133">Pour ajouter un fragment de page qui comprend un code de script à un modèle dans le générateur de site, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1e4f2-133">To add a page fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="1e4f2-134">Accédez à **Modèles**, puis ouvrez le modèle pour les pages dans lesquelles vous souhaitez ajouter votre code de script.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-134">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="1e4f2-135">Dans le volet gauche, développez la hiérarchie de modèle pour afficher l’emplacement **En-tête HTML**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-135">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="1e4f2-136">Dans l’emplacement **En-tête HTML**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un fragment de page**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-136">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Page Fragment**.</span></span>
1. <span data-ttu-id="1e4f2-137">Sélectionnez le fragment créé pour votre code de script.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-137">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="1e4f2-138">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-138">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="1e4f2-139">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-139">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="1e4f2-140">Ajouter un script externe ou en ligne directement à un modèle</span><span class="sxs-lookup"><span data-stu-id="1e4f2-140">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="1e4f2-141">Si vous souhaitez insérer un script en ligne ou externe directement dans un ensemble de pages contrôlées par un seul modèle, vous n’avez pas à créer de fragment de page tout d’abord.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-141">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a page fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="1e4f2-142">Ajouter un script en ligne directement à un modèle</span><span class="sxs-lookup"><span data-stu-id="1e4f2-142">Add an inline script directly to a template</span></span>

<span data-ttu-id="1e4f2-143">Pour ajouter un script en ligne directement à un modèle dans le générateur de site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-143">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="1e4f2-144">Accédez à **Modèles**, puis ouvrez le modèle pour les pages dans lesquelles vous souhaitez ajouter votre code de script.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-144">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="1e4f2-145">Dans le volet gauche, développez la hiérarchie de modèle pour afficher l’emplacement **En-tête HTML**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-145">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="1e4f2-146">Dans l’emplacement **En-tête HTML**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-146">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="1e4f2-147">Dans la boîte de dialogue **Ajouter un module**, sélectionnez **Script en ligne**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-147">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="1e4f2-148">Dans le volet des propriétés à droite, sous **Script en ligne**, entrez votre script côté client.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-148">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="1e4f2-149">Puis configurez d’autres options selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-149">Then configure other options as you require.</span></span>
1. <span data-ttu-id="1e4f2-150">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-150">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="1e4f2-151">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-151">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="1e4f2-152">Ajouter un script externe directement à un modèle</span><span class="sxs-lookup"><span data-stu-id="1e4f2-152">Add an external script directly to a template</span></span>

<span data-ttu-id="1e4f2-153">Pour ajouter un script externe à un modèle dans le générateur de site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-153">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="1e4f2-154">Accédez à **Modèles**, puis ouvrez le modèle pour les pages dans lesquelles vous souhaitez ajouter votre code de script.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-154">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="1e4f2-155">Dans le volet gauche, développez la hiérarchie de modèle pour afficher l’emplacement **En-tête HTML**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-155">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="1e4f2-156">Dans l’emplacement **En-tête HTML**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-156">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="1e4f2-157">Dans la boîte de dialogue **Ajouter un module**, sélectionnez **Script externe**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-157">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="1e4f2-158">Dans le volet des propriétés à droite, sous **Source du script**, ajoutez une URL externe ou relative pour la source de script externe.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-158">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="1e4f2-159">Puis configurez d’autres options selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-159">Then configure other options as you require.</span></span>
1. <span data-ttu-id="1e4f2-160">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-160">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="1e4f2-161">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="1e4f2-161">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1e4f2-162">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="1e4f2-162">Additional resources</span></span>

[<span data-ttu-id="1e4f2-163">Ajouter un logo</span><span class="sxs-lookup"><span data-stu-id="1e4f2-163">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="1e4f2-164">Sélectionner un thème pour le site</span><span class="sxs-lookup"><span data-stu-id="1e4f2-164">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="1e4f2-165">Utilisation de fichiers de remplacement CSS</span><span class="sxs-lookup"><span data-stu-id="1e4f2-165">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="1e4f2-166">Ajouter une icône de favori</span><span class="sxs-lookup"><span data-stu-id="1e4f2-166">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="1e4f2-167">Ajouter un message de bienvenue</span><span class="sxs-lookup"><span data-stu-id="1e4f2-167">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="1e4f2-168">Ajouter un avis de droits d’auteur</span><span class="sxs-lookup"><span data-stu-id="1e4f2-168">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="1e4f2-169">Ajouter des langues à votre site</span><span class="sxs-lookup"><span data-stu-id="1e4f2-169">Add languages to your site</span></span>](add-languages-to-site.md)
