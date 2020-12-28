---
title: Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie
description: Cette rubrique décrit comment ajouter un code du script côté client à vos pages du site pour prendre en charge la collection de télémétrie côté client.
author: bicyclingfool
manager: annbe
ms.date: 09/29/2020
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
ms.openlocfilehash: e15ba6a0d624bd97c25936aa6d3bfafb844b66c0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412211"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="19b1a-103">Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie</span><span class="sxs-lookup"><span data-stu-id="19b1a-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="19b1a-104">Cette rubrique décrit comment ajouter un code du script côté client à vos pages du site pour prendre en charge la collection de télémétrie côté client.</span><span class="sxs-lookup"><span data-stu-id="19b1a-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="19b1a-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="19b1a-105">Overview</span></span>

<span data-ttu-id="19b1a-106">Les analyses web sont un outil essentiel lorsque vous souhaitez inclure la manière dont vos clients peuvent interagir avec votre site et prendre des décisions qui aideront à optimiser l’expérience pour la conversion maximale.</span><span class="sxs-lookup"><span data-stu-id="19b1a-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="19b1a-107">De nombreux packages d’analyses web sont disponibles pour vous aider à atteindre ces objectifs, comme Google Analytics, Clicky, Moz Analytics, et KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="19b1a-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="19b1a-108">La plupart des packages d’analyses web nécessitent que vous ajoutiez un code du script côté client dans l’élément **\<head\>** du fichier HTML pour toutes les pages du site.</span><span class="sxs-lookup"><span data-stu-id="19b1a-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="19b1a-109">Les instructions de cette rubrique s’appliquent également à l’autre fonctionnalité côté client personnalisée que Microsoft Dynamics 365 Commerce n’offre pas en mode natif.</span><span class="sxs-lookup"><span data-stu-id="19b1a-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="19b1a-110">Créer un fragment réutilisable pour votre code de script</span><span class="sxs-lookup"><span data-stu-id="19b1a-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="19b1a-111">Un fragment vous permet de réutiliser un code de script externe ou en ligne sur toutes les pages de votre site, peu importe le modèle qu’elles utilisent.</span><span class="sxs-lookup"><span data-stu-id="19b1a-111">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="19b1a-112">Créer un fragment réutilisable pour votre code de script en ligne</span><span class="sxs-lookup"><span data-stu-id="19b1a-112">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="19b1a-113">Pour créer un fragment réutilisable pour votre code de script en ligne dans le générateur de site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="19b1a-113">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="19b1a-114">Accédez à **Fragments**, puis sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-114">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="19b1a-115">Dans la boîte de dialogue **Nouveau fragment**, sélectionnez **Script en ligne**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-115">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="19b1a-116">Sous **Nom du fragment**, entrez un nom pour le fragment, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-116">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="19b1a-117">Sous le fragment que vous avez créé, sélectionnez le module **Script en ligne par défaut**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-117">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="19b1a-118">Dans le volet des propriétés à droite, sous **Script en ligne**, entrez votre script côté client.</span><span class="sxs-lookup"><span data-stu-id="19b1a-118">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="19b1a-119">Puis configurez d’autres options selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="19b1a-119">Then configure other options as you require.</span></span>
1. <span data-ttu-id="19b1a-120">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-120">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="19b1a-121">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-121">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="19b1a-122">Créer un fragment réutilisable pour votre code de script externe</span><span class="sxs-lookup"><span data-stu-id="19b1a-122">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="19b1a-123">Pour créer un fragment réutilisable pour votre code de script externe dans le générateur de site, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="19b1a-123">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="19b1a-124">Accédez à **Fragments**, puis sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-124">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="19b1a-125">Dans la boîte de dialogue **Nouveau fragment**, sélectionnez **Script externe**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-125">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="19b1a-126">Sous **Nom du fragment**, entrez un nom pour le fragment, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-126">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="19b1a-127">Sous le fragment que vous avez créé, sélectionnez le module **Script externe par défaut**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-127">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="19b1a-128">Dans le volet des propriétés à droite, sous **Source du script**, ajoutez une URL externe ou relative pour la source de script externe.</span><span class="sxs-lookup"><span data-stu-id="19b1a-128">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="19b1a-129">Puis configurez d’autres options selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="19b1a-129">Then configure other options as you require.</span></span>
1. <span data-ttu-id="19b1a-130">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="19b1a-131">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-131">Select **Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="19b1a-132">Si la stratégie de stratégie de sécurité (CSP) est activée pour votre site, assurez-vous que toutes les URL externes sont ajoutées à l'instruction CSP **script-src** dans le générateur de site Commerce.</span><span class="sxs-lookup"><span data-stu-id="19b1a-132">If content security policy (CSP) is enabled for your site, ensure that all external URLs are added to the **script-src** CSP directive in Commerce site builder.</span></span> <span data-ttu-id="19b1a-133">Pour plus d’informations, voir [Gérer la stratégie de sécurité du contenu (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="19b1a-133">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="19b1a-134">Ajouter un fragment qui inclut le code de script à un modèle</span><span class="sxs-lookup"><span data-stu-id="19b1a-134">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="19b1a-135">Pour ajouter un fragment qui comprend un code de script à un modèle dans le générateur de site, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="19b1a-135">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="19b1a-136">Accédez à **Modèles**, puis ouvrez le modèle pour les pages dans lesquelles vous souhaitez ajouter votre code de script.</span><span class="sxs-lookup"><span data-stu-id="19b1a-136">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="19b1a-137">Dans le volet gauche, développez la hiérarchie de modèle pour afficher l’emplacement **En-tête HTML**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-137">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="19b1a-138">Dans l’emplacement **En-tête HTML**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un fragment**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-138">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="19b1a-139">Sélectionnez le fragment créé pour votre code de script.</span><span class="sxs-lookup"><span data-stu-id="19b1a-139">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="19b1a-140">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-140">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="19b1a-141">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-141">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="19b1a-142">Ajouter un script externe ou en ligne directement à un modèle</span><span class="sxs-lookup"><span data-stu-id="19b1a-142">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="19b1a-143">Si vous souhaitez insérer un script en ligne ou externe directement dans un ensemble de pages contrôlées par un seul modèle, vous n’avez pas à créer de fragment tout d’abord.</span><span class="sxs-lookup"><span data-stu-id="19b1a-143">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="19b1a-144">Ajouter un script en ligne directement à un modèle</span><span class="sxs-lookup"><span data-stu-id="19b1a-144">Add an inline script directly to a template</span></span>

<span data-ttu-id="19b1a-145">Pour ajouter un script en ligne directement à un modèle dans le générateur de site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="19b1a-145">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="19b1a-146">Accédez à **Modèles**, puis ouvrez le modèle pour les pages dans lesquelles vous souhaitez ajouter votre code de script.</span><span class="sxs-lookup"><span data-stu-id="19b1a-146">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="19b1a-147">Dans le volet gauche, développez la hiérarchie de modèle pour afficher l’emplacement **En-tête HTML**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-147">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="19b1a-148">Dans l’emplacement **En-tête HTML**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-148">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="19b1a-149">Dans la boîte de dialogue **Ajouter un module**, sélectionnez **Script en ligne**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-149">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="19b1a-150">Dans le volet des propriétés à droite, sous **Script en ligne**, entrez votre script côté client.</span><span class="sxs-lookup"><span data-stu-id="19b1a-150">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="19b1a-151">Puis configurez d’autres options selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="19b1a-151">Then configure other options as you require.</span></span>
1. <span data-ttu-id="19b1a-152">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-152">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="19b1a-153">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-153">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="19b1a-154">Ajouter un script externe directement à un modèle</span><span class="sxs-lookup"><span data-stu-id="19b1a-154">Add an external script directly to a template</span></span>

<span data-ttu-id="19b1a-155">Pour ajouter un script externe à un modèle dans le générateur de site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="19b1a-155">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="19b1a-156">Accédez à **Modèles**, puis ouvrez le modèle pour les pages dans lesquelles vous souhaitez ajouter votre code de script.</span><span class="sxs-lookup"><span data-stu-id="19b1a-156">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="19b1a-157">Dans le volet gauche, développez la hiérarchie de modèle pour afficher l’emplacement **En-tête HTML**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-157">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="19b1a-158">Dans l’emplacement **En-tête HTML**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-158">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="19b1a-159">Dans la boîte de dialogue **Ajouter un module**, sélectionnez **Script externe**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-159">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="19b1a-160">Dans le volet des propriétés à droite, sous **Source du script**, ajoutez une URL externe ou relative pour la source de script externe.</span><span class="sxs-lookup"><span data-stu-id="19b1a-160">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="19b1a-161">Puis configurez d’autres options selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="19b1a-161">Then configure other options as you require.</span></span>
1. <span data-ttu-id="19b1a-162">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-162">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="19b1a-163">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="19b1a-163">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="19b1a-164">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="19b1a-164">Additional resources</span></span>

[<span data-ttu-id="19b1a-165">Ajouter un logo</span><span class="sxs-lookup"><span data-stu-id="19b1a-165">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="19b1a-166">Sélectionner un thème pour le site</span><span class="sxs-lookup"><span data-stu-id="19b1a-166">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="19b1a-167">Utilisation de fichiers de remplacement CSS</span><span class="sxs-lookup"><span data-stu-id="19b1a-167">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="19b1a-168">Ajouter une icône de favori</span><span class="sxs-lookup"><span data-stu-id="19b1a-168">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="19b1a-169">Ajouter un message de bienvenue</span><span class="sxs-lookup"><span data-stu-id="19b1a-169">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="19b1a-170">Ajouter un avis de droits d’auteur</span><span class="sxs-lookup"><span data-stu-id="19b1a-170">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="19b1a-171">Ajouter des langues à votre site</span><span class="sxs-lookup"><span data-stu-id="19b1a-171">Add languages to your site</span></span>](add-languages-to-site.md)
