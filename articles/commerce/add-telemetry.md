---
title: Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie
description: Cette rubrique décrit comment ajouter un code du script côté client à vos pages du site pour prendre en charge la collection de télémétrie côté client.
author: bicyclingfool
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: a88f4f920154aafaa15a48af67365152e21111f7
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761247"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="17544-103">Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie</span><span class="sxs-lookup"><span data-stu-id="17544-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="17544-104">Cette rubrique décrit comment ajouter un code du script côté client à vos pages du site pour prendre en charge la collection de télémétrie côté client.</span><span class="sxs-lookup"><span data-stu-id="17544-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="17544-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="17544-105">Overview</span></span>

<span data-ttu-id="17544-106">Les analyses web sont un outil essentiel lorsque vous souhaitez inclure la manière dont vos clients peuvent interagir avec votre site et prendre des décisions qui aideront à optimiser l’expérience pour la conversion maximale.</span><span class="sxs-lookup"><span data-stu-id="17544-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="17544-107">De nombreux packages d’analyses web sont disponibles pour vous aider à atteindre ces objectifs, comme Google Analytics, Clicky, Moz Analytics, et KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="17544-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="17544-108">La plupart des packages d’analyses web nécessitent que vous ajoutiez un code du script côté client dans l’élément **\<head\>** du fichier HTML pour toutes les pages du site.</span><span class="sxs-lookup"><span data-stu-id="17544-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="17544-109">Les instructions de cette rubrique s’appliquent également à l’autre fonctionnalité côté client personnalisée que Microsoft Dynamics 365 Commerce n’offre pas en mode natif.</span><span class="sxs-lookup"><span data-stu-id="17544-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="17544-110">Créer un fragment réutilisable pour votre code de script</span><span class="sxs-lookup"><span data-stu-id="17544-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="17544-111">Un fragment vous permet de réutiliser un code de script externe ou en ligne sur toutes les pages de votre site, peu importe le modèle qu’elles utilisent.</span><span class="sxs-lookup"><span data-stu-id="17544-111">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="17544-112">Créer un fragment réutilisable pour votre code de script en ligne</span><span class="sxs-lookup"><span data-stu-id="17544-112">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="17544-113">Pour créer un fragment réutilisable pour votre code de script en ligne dans le générateur de site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="17544-113">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="17544-114">Accédez à **Fragments**, puis sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="17544-114">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="17544-115">Dans la boîte de dialogue **Nouveau fragment**, sélectionnez **Script en ligne**.</span><span class="sxs-lookup"><span data-stu-id="17544-115">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="17544-116">Sous **Nom du fragment**, entrez un nom pour le fragment, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="17544-116">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="17544-117">Sous le fragment que vous avez créé, sélectionnez le module **Script en ligne par défaut**.</span><span class="sxs-lookup"><span data-stu-id="17544-117">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="17544-118">Dans le volet des propriétés à droite, sous **Script en ligne**, entrez votre script côté client.</span><span class="sxs-lookup"><span data-stu-id="17544-118">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="17544-119">Puis configurez d’autres options selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="17544-119">Then configure other options as you require.</span></span>
1. <span data-ttu-id="17544-120">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="17544-120">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="17544-121">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="17544-121">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="17544-122">Créer un fragment réutilisable pour votre code de script externe</span><span class="sxs-lookup"><span data-stu-id="17544-122">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="17544-123">Pour créer un fragment réutilisable pour votre code de script externe dans le générateur de site, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="17544-123">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="17544-124">Accédez à **Fragments**, puis sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="17544-124">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="17544-125">Dans la boîte de dialogue **Nouveau fragment**, sélectionnez **Script externe**.</span><span class="sxs-lookup"><span data-stu-id="17544-125">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="17544-126">Sous **Nom du fragment**, entrez un nom pour le fragment, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="17544-126">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="17544-127">Sous le fragment que vous avez créé, sélectionnez le module **Script externe par défaut**.</span><span class="sxs-lookup"><span data-stu-id="17544-127">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="17544-128">Dans le volet des propriétés à droite, sous **Source du script**, ajoutez une URL externe ou relative pour la source de script externe.</span><span class="sxs-lookup"><span data-stu-id="17544-128">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="17544-129">Puis configurez d’autres options selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="17544-129">Then configure other options as you require.</span></span>
1. <span data-ttu-id="17544-130">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="17544-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="17544-131">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="17544-131">Select **Publish**.</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="17544-132">Ajouter un fragment qui inclut le code de script à un modèle</span><span class="sxs-lookup"><span data-stu-id="17544-132">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="17544-133">Pour ajouter un fragment qui comprend un code de script à un modèle dans le générateur de site, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="17544-133">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="17544-134">Accédez à **Modèles**, puis ouvrez le modèle pour les pages dans lesquelles vous souhaitez ajouter votre code de script.</span><span class="sxs-lookup"><span data-stu-id="17544-134">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="17544-135">Dans le volet gauche, développez la hiérarchie de modèle pour afficher l’emplacement **En-tête HTML**.</span><span class="sxs-lookup"><span data-stu-id="17544-135">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="17544-136">Dans l’emplacement **En-tête HTML**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un fragment**.</span><span class="sxs-lookup"><span data-stu-id="17544-136">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="17544-137">Sélectionnez le fragment créé pour votre code de script.</span><span class="sxs-lookup"><span data-stu-id="17544-137">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="17544-138">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="17544-138">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="17544-139">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="17544-139">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="17544-140">Ajouter un script externe ou en ligne directement à un modèle</span><span class="sxs-lookup"><span data-stu-id="17544-140">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="17544-141">Si vous souhaitez insérer un script en ligne ou externe directement dans un ensemble de pages contrôlées par un seul modèle, vous n’avez pas à créer de fragment tout d’abord.</span><span class="sxs-lookup"><span data-stu-id="17544-141">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="17544-142">Ajouter un script en ligne directement à un modèle</span><span class="sxs-lookup"><span data-stu-id="17544-142">Add an inline script directly to a template</span></span>

<span data-ttu-id="17544-143">Pour ajouter un script en ligne directement à un modèle dans le générateur de site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="17544-143">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="17544-144">Accédez à **Modèles**, puis ouvrez le modèle pour les pages dans lesquelles vous souhaitez ajouter votre code de script.</span><span class="sxs-lookup"><span data-stu-id="17544-144">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="17544-145">Dans le volet gauche, développez la hiérarchie de modèle pour afficher l’emplacement **En-tête HTML**.</span><span class="sxs-lookup"><span data-stu-id="17544-145">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="17544-146">Dans l’emplacement **En-tête HTML**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="17544-146">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="17544-147">Dans la boîte de dialogue **Ajouter un module**, sélectionnez **Script en ligne**.</span><span class="sxs-lookup"><span data-stu-id="17544-147">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="17544-148">Dans le volet des propriétés à droite, sous **Script en ligne**, entrez votre script côté client.</span><span class="sxs-lookup"><span data-stu-id="17544-148">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="17544-149">Puis configurez d’autres options selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="17544-149">Then configure other options as you require.</span></span>
1. <span data-ttu-id="17544-150">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="17544-150">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="17544-151">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="17544-151">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="17544-152">Ajouter un script externe directement à un modèle</span><span class="sxs-lookup"><span data-stu-id="17544-152">Add an external script directly to a template</span></span>

<span data-ttu-id="17544-153">Pour ajouter un script externe à un modèle dans le générateur de site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="17544-153">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="17544-154">Accédez à **Modèles**, puis ouvrez le modèle pour les pages dans lesquelles vous souhaitez ajouter votre code de script.</span><span class="sxs-lookup"><span data-stu-id="17544-154">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="17544-155">Dans le volet gauche, développez la hiérarchie de modèle pour afficher l’emplacement **En-tête HTML**.</span><span class="sxs-lookup"><span data-stu-id="17544-155">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="17544-156">Dans l’emplacement **En-tête HTML**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="17544-156">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="17544-157">Dans la boîte de dialogue **Ajouter un module**, sélectionnez **Script externe**.</span><span class="sxs-lookup"><span data-stu-id="17544-157">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="17544-158">Dans le volet des propriétés à droite, sous **Source du script**, ajoutez une URL externe ou relative pour la source de script externe.</span><span class="sxs-lookup"><span data-stu-id="17544-158">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="17544-159">Puis configurez d’autres options selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="17544-159">Then configure other options as you require.</span></span>
1. <span data-ttu-id="17544-160">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="17544-160">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="17544-161">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="17544-161">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="17544-162">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="17544-162">Additional resources</span></span>

[<span data-ttu-id="17544-163">Ajouter un logo</span><span class="sxs-lookup"><span data-stu-id="17544-163">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="17544-164">Sélectionner un thème pour le site</span><span class="sxs-lookup"><span data-stu-id="17544-164">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="17544-165">Utilisation de fichiers de remplacement CSS</span><span class="sxs-lookup"><span data-stu-id="17544-165">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="17544-166">Ajouter une icône de favori</span><span class="sxs-lookup"><span data-stu-id="17544-166">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="17544-167">Ajouter un message de bienvenue</span><span class="sxs-lookup"><span data-stu-id="17544-167">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="17544-168">Ajouter un avis de droits d’auteur</span><span class="sxs-lookup"><span data-stu-id="17544-168">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="17544-169">Ajouter des langues à votre site</span><span class="sxs-lookup"><span data-stu-id="17544-169">Add languages to your site</span></span>](add-languages-to-site.md)
