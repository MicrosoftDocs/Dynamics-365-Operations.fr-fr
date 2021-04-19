---
title: Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie
description: Cette rubrique décrit comment ajouter un code du script côté client à vos pages du site pour prendre en charge la collection de télémétrie côté client.
author: bicyclingfool
ms.date: 09/29/2020
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
ms.openlocfilehash: fb1773ab10b23a586eb6a8286f145181818585b9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797429"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="0c060-103">Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie</span><span class="sxs-lookup"><span data-stu-id="0c060-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0c060-104">Cette rubrique décrit comment ajouter un code du script côté client à vos pages du site pour prendre en charge la collection de télémétrie côté client.</span><span class="sxs-lookup"><span data-stu-id="0c060-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

<span data-ttu-id="0c060-105">Les analyses web sont un outil essentiel lorsque vous souhaitez inclure la manière dont vos clients peuvent interagir avec votre site et prendre des décisions qui aideront à optimiser l’expérience pour la conversion maximale.</span><span class="sxs-lookup"><span data-stu-id="0c060-105">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="0c060-106">De nombreux packages d’analyses web sont disponibles pour vous aider à atteindre ces objectifs, comme Google Analytics, Clicky, Moz Analytics, et KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="0c060-106">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="0c060-107">La plupart des packages d’analyses web nécessitent que vous ajoutiez un code du script côté client dans l’élément **\<head\>** du fichier HTML pour toutes les pages du site.</span><span class="sxs-lookup"><span data-stu-id="0c060-107">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="0c060-108">Les instructions de cette rubrique s’appliquent également à l’autre fonctionnalité côté client personnalisée que Microsoft Dynamics 365 Commerce n’offre pas en mode natif.</span><span class="sxs-lookup"><span data-stu-id="0c060-108">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="0c060-109">Créer un fragment réutilisable pour votre code de script</span><span class="sxs-lookup"><span data-stu-id="0c060-109">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="0c060-110">Un fragment vous permet de réutiliser un code de script externe ou en ligne sur toutes les pages de votre site, peu importe le modèle qu’elles utilisent.</span><span class="sxs-lookup"><span data-stu-id="0c060-110">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="0c060-111">Créer un fragment réutilisable pour votre code de script en ligne</span><span class="sxs-lookup"><span data-stu-id="0c060-111">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="0c060-112">Pour créer un fragment réutilisable pour votre code de script en ligne dans le générateur de site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="0c060-112">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="0c060-113">Accédez à **Fragments**, puis sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="0c060-113">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="0c060-114">Dans la boîte de dialogue **Nouveau fragment**, sélectionnez **Script en ligne**.</span><span class="sxs-lookup"><span data-stu-id="0c060-114">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="0c060-115">Sous **Nom du fragment**, entrez un nom pour le fragment, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c060-115">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="0c060-116">Sous le fragment que vous avez créé, sélectionnez le module **Script en ligne par défaut**.</span><span class="sxs-lookup"><span data-stu-id="0c060-116">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="0c060-117">Dans le volet des propriétés à droite, sous **Script en ligne**, entrez votre script côté client.</span><span class="sxs-lookup"><span data-stu-id="0c060-117">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="0c060-118">Puis configurez d’autres options selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="0c060-118">Then configure other options as you require.</span></span>
1. <span data-ttu-id="0c060-119">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="0c060-119">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="0c060-120">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="0c060-120">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="0c060-121">Créer un fragment réutilisable pour votre code de script externe</span><span class="sxs-lookup"><span data-stu-id="0c060-121">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="0c060-122">Pour créer un fragment réutilisable pour votre code de script externe dans le générateur de site, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0c060-122">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="0c060-123">Accédez à **Fragments**, puis sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="0c060-123">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="0c060-124">Dans la boîte de dialogue **Nouveau fragment**, sélectionnez **Script externe**.</span><span class="sxs-lookup"><span data-stu-id="0c060-124">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="0c060-125">Sous **Nom du fragment**, entrez un nom pour le fragment, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c060-125">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="0c060-126">Sous le fragment que vous avez créé, sélectionnez le module **Script externe par défaut**.</span><span class="sxs-lookup"><span data-stu-id="0c060-126">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="0c060-127">Dans le volet des propriétés à droite, sous **Source du script**, ajoutez une URL externe ou relative pour la source de script externe.</span><span class="sxs-lookup"><span data-stu-id="0c060-127">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="0c060-128">Puis configurez d’autres options selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="0c060-128">Then configure other options as you require.</span></span>
1. <span data-ttu-id="0c060-129">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="0c060-129">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="0c060-130">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="0c060-130">Select **Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="0c060-131">Si la stratégie de stratégie de sécurité (CSP) est activée pour votre site, assurez-vous que toutes les URL externes sont ajoutées à l’instruction CSP **script-src** dans le générateur de site Commerce.</span><span class="sxs-lookup"><span data-stu-id="0c060-131">If content security policy (CSP) is enabled for your site, ensure that all external URLs are added to the **script-src** CSP directive in Commerce site builder.</span></span> <span data-ttu-id="0c060-132">Pour plus d’informations, voir [Gérer la stratégie de sécurité du contenu (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="0c060-132">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="0c060-133">Ajouter un fragment qui inclut le code de script à un modèle</span><span class="sxs-lookup"><span data-stu-id="0c060-133">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="0c060-134">Pour ajouter un fragment qui comprend un code de script à un modèle dans le générateur de site, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0c060-134">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="0c060-135">Accédez à **Modèles**, puis ouvrez le modèle pour les pages dans lesquelles vous souhaitez ajouter votre code de script.</span><span class="sxs-lookup"><span data-stu-id="0c060-135">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="0c060-136">Dans le volet gauche, développez la hiérarchie de modèle pour afficher l’emplacement **En-tête HTML**.</span><span class="sxs-lookup"><span data-stu-id="0c060-136">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="0c060-137">Dans l’emplacement **En-tête HTML**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un fragment**.</span><span class="sxs-lookup"><span data-stu-id="0c060-137">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="0c060-138">Sélectionnez le fragment créé pour votre code de script.</span><span class="sxs-lookup"><span data-stu-id="0c060-138">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="0c060-139">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="0c060-139">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="0c060-140">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="0c060-140">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="0c060-141">Ajouter un script externe ou en ligne directement à un modèle</span><span class="sxs-lookup"><span data-stu-id="0c060-141">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="0c060-142">Si vous souhaitez insérer un script en ligne ou externe directement dans un ensemble de pages contrôlées par un seul modèle, vous n’avez pas à créer de fragment tout d’abord.</span><span class="sxs-lookup"><span data-stu-id="0c060-142">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="0c060-143">Ajouter un script en ligne directement à un modèle</span><span class="sxs-lookup"><span data-stu-id="0c060-143">Add an inline script directly to a template</span></span>

<span data-ttu-id="0c060-144">Pour ajouter un script en ligne directement à un modèle dans le générateur de site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="0c060-144">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="0c060-145">Accédez à **Modèles**, puis ouvrez le modèle pour les pages dans lesquelles vous souhaitez ajouter votre code de script.</span><span class="sxs-lookup"><span data-stu-id="0c060-145">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="0c060-146">Dans le volet gauche, développez la hiérarchie de modèle pour afficher l’emplacement **En-tête HTML**.</span><span class="sxs-lookup"><span data-stu-id="0c060-146">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="0c060-147">Dans l’emplacement **En-tête HTML**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="0c060-147">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="0c060-148">Dans la boîte de dialogue **Ajouter un module**, sélectionnez **Script en ligne**.</span><span class="sxs-lookup"><span data-stu-id="0c060-148">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="0c060-149">Dans le volet des propriétés à droite, sous **Script en ligne**, entrez votre script côté client.</span><span class="sxs-lookup"><span data-stu-id="0c060-149">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="0c060-150">Puis configurez d’autres options selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="0c060-150">Then configure other options as you require.</span></span>
1. <span data-ttu-id="0c060-151">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="0c060-151">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="0c060-152">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="0c060-152">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="0c060-153">Ajouter un script externe directement à un modèle</span><span class="sxs-lookup"><span data-stu-id="0c060-153">Add an external script directly to a template</span></span>

<span data-ttu-id="0c060-154">Pour ajouter un script externe à un modèle dans le générateur de site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="0c060-154">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="0c060-155">Accédez à **Modèles**, puis ouvrez le modèle pour les pages dans lesquelles vous souhaitez ajouter votre code de script.</span><span class="sxs-lookup"><span data-stu-id="0c060-155">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="0c060-156">Dans le volet gauche, développez la hiérarchie de modèle pour afficher l’emplacement **En-tête HTML**.</span><span class="sxs-lookup"><span data-stu-id="0c060-156">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="0c060-157">Dans l’emplacement **En-tête HTML**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="0c060-157">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="0c060-158">Dans la boîte de dialogue **Ajouter un module**, sélectionnez **Script externe**.</span><span class="sxs-lookup"><span data-stu-id="0c060-158">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="0c060-159">Dans le volet des propriétés à droite, sous **Source du script**, ajoutez une URL externe ou relative pour la source de script externe.</span><span class="sxs-lookup"><span data-stu-id="0c060-159">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="0c060-160">Puis configurez d’autres options selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="0c060-160">Then configure other options as you require.</span></span>
1. <span data-ttu-id="0c060-161">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="0c060-161">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="0c060-162">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="0c060-162">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0c060-163">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0c060-163">Additional resources</span></span>

[<span data-ttu-id="0c060-164">Ajouter un logo</span><span class="sxs-lookup"><span data-stu-id="0c060-164">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="0c060-165">Sélectionner un thème pour le site</span><span class="sxs-lookup"><span data-stu-id="0c060-165">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="0c060-166">Utilisation de fichiers de remplacement CSS</span><span class="sxs-lookup"><span data-stu-id="0c060-166">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="0c060-167">Ajouter une icône de favori</span><span class="sxs-lookup"><span data-stu-id="0c060-167">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="0c060-168">Ajouter un message de bienvenue</span><span class="sxs-lookup"><span data-stu-id="0c060-168">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="0c060-169">Ajouter un avis de droits d’auteur</span><span class="sxs-lookup"><span data-stu-id="0c060-169">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="0c060-170">Ajouter des langues à votre site</span><span class="sxs-lookup"><span data-stu-id="0c060-170">Add languages to your site</span></span>](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
