---
title: Module iframe
description: Cette rubrique couvre le module iframe et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 58446289c9a53af30d4d6d331a1a609ae0d2a0ad
ms.sourcegitcommit: 97ceb24f191161ca601e0889a539df665834ac3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2020
ms.locfileid: "3818196"
---
# <a name="iframe-module"></a><span data-ttu-id="7ad50-103">Module iframe</span><span class="sxs-lookup"><span data-stu-id="7ad50-103">Iframe module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7ad50-104">Cette rubrique couvre le module iframe et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7ad50-104">This topic covers the iframe module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="7ad50-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="7ad50-105">Overview</span></span>

<span data-ttu-id="7ad50-106">Un module iframe fournit un iframe (cadre incorporé) qui héberge du contenu externe sur un site.</span><span class="sxs-lookup"><span data-stu-id="7ad50-106">An iframe module provides an iframe (inline frame) that hosts external content on a site.</span></span> <span data-ttu-id="7ad50-107">Par exemple, il peut être utilisé pour héberger une vidéo YouTube ou une visionneuse de fichiers PDF sur une page de site.</span><span class="sxs-lookup"><span data-stu-id="7ad50-107">For example, it can be used to host a YouTube video or a PDF file viewer on any site page.</span></span> 

<span data-ttu-id="7ad50-108">Un module iframe nécessite une URL cible.</span><span class="sxs-lookup"><span data-stu-id="7ad50-108">An iframe module requires a target URL.</span></span> <span data-ttu-id="7ad50-109">Il héberge ensuite le contenu de la page cible dans un élément **iframe** HTML.</span><span class="sxs-lookup"><span data-stu-id="7ad50-109">It then hosts the content of the target page inside an HTML **iframe** element.</span></span> <span data-ttu-id="7ad50-110">Les URL externes doivent figurer sur la liste d’autorisation (également appelée « liste verte ») conformément aux instructions de la stratégie de sécurité du contenu (CSP) du site.</span><span class="sxs-lookup"><span data-stu-id="7ad50-110">External URLs must be on the allow list (also known as a "whitelist") per the site's content security policy (CSP) directives.</span></span> <span data-ttu-id="7ad50-111">Pour le contenu iframe, les URL doivent être autorisées à l’aide de l’instruction **frame-ancestor**.</span><span class="sxs-lookup"><span data-stu-id="7ad50-111">For iframe content, URLs should be allowed by using the **frame-ancestor** directive.</span></span> <span data-ttu-id="7ad50-112">Pour plus d’informations, voir [Gérer la stratégie de sécurité du contenu (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="7ad50-112">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7ad50-113">Le module iframe est disponible dans Dynamics 365 Commerce version 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="7ad50-113">The iframe module is available in the Dynamics 365 Commerce 10.0.13 release.</span></span>

<span data-ttu-id="7ad50-114">L’image suivante montre des exemples de modules iframe qui présentent des vidéos externes sur des pages de site.</span><span class="sxs-lookup"><span data-stu-id="7ad50-114">The following image shows examples of iframe modules that showcase external videos on site pages.</span></span>

![Exemple de modules iframe qui présentent des vidéos externes](./media/ecommerce-iframe.PNG)

## <a name="iframe-module-properties"></a><span data-ttu-id="7ad50-116">Propriétés du module iframe</span><span class="sxs-lookup"><span data-stu-id="7ad50-116">Iframe module properties</span></span>

| <span data-ttu-id="7ad50-117">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="7ad50-117">Property name</span></span>             | <span data-ttu-id="7ad50-118">Valeur</span><span class="sxs-lookup"><span data-stu-id="7ad50-118">Value</span></span>                 | <span data-ttu-id="7ad50-119">Description</span><span class="sxs-lookup"><span data-stu-id="7ad50-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="7ad50-120">Titre</span><span class="sxs-lookup"><span data-stu-id="7ad50-120">Heading</span></span> | <span data-ttu-id="7ad50-121">Détails</span><span class="sxs-lookup"><span data-stu-id="7ad50-121">Text</span></span> | <span data-ttu-id="7ad50-122">En-tête du module.</span><span class="sxs-lookup"><span data-stu-id="7ad50-122">The heading for the module.</span></span> |
| <span data-ttu-id="7ad50-123">URL cible</span><span class="sxs-lookup"><span data-stu-id="7ad50-123">Target URL</span></span> | <span data-ttu-id="7ad50-124">URL</span><span class="sxs-lookup"><span data-stu-id="7ad50-124">URL</span></span> | <span data-ttu-id="7ad50-125">URL hébergée dans le module.</span><span class="sxs-lookup"><span data-stu-id="7ad50-125">The URL that is hosted in the module.</span></span> |
| <span data-ttu-id="7ad50-126">Hauteur</span><span class="sxs-lookup"><span data-stu-id="7ad50-126">Height</span></span> | <span data-ttu-id="7ad50-127">Nombre ou pourcentage</span><span class="sxs-lookup"><span data-stu-id="7ad50-127">Number or percentage</span></span> | <span data-ttu-id="7ad50-128">Hauteur du module, en pixels ou en pourcentage.</span><span class="sxs-lookup"><span data-stu-id="7ad50-128">The height of the module, in pixels or as a percentage.</span></span> <span data-ttu-id="7ad50-129">Par exemple, la valeur **100** est traitée comme un nombre de pixels et la valeur **100 %** est traitée comme un pourcentage.</span><span class="sxs-lookup"><span data-stu-id="7ad50-129">For example, the value **100** will be treated as a number of pixels, and the value **100%** will be treated as a percentage.</span></span> |
| <span data-ttu-id="7ad50-130">Aria-label</span><span class="sxs-lookup"><span data-stu-id="7ad50-130">Aria label</span></span> | <span data-ttu-id="7ad50-131">Détails</span><span class="sxs-lookup"><span data-stu-id="7ad50-131">Text</span></span> | <span data-ttu-id="7ad50-132">Une étiquette ARIA (Accessible Rich Internet Applications) peut être définie à des fins d’accessibilité.</span><span class="sxs-lookup"><span data-stu-id="7ad50-132">An Accessible Rich Internet Applications (ARIA) label can be defined for accessibility purposes.</span></span> |

## <a name="add-an-iframe-module-to-a-page"></a><span data-ttu-id="7ad50-133">Ajouter un module iframe à une page</span><span class="sxs-lookup"><span data-stu-id="7ad50-133">Add an iframe module to a page</span></span>

<span data-ttu-id="7ad50-134">Pour ajouter un module iframe à une page afin d’afficher une vidéo externe, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7ad50-134">To add an iframe module to a page to show an external video, follow these steps.</span></span>

1. <span data-ttu-id="7ad50-135">Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="7ad50-135">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="7ad50-136">Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle marketing**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7ad50-136">In the **New Template** dialog box, under **Template name**, enter **Marketing template**, and then select **OK**.</span></span>
1. <span data-ttu-id="7ad50-137">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="7ad50-137">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="7ad50-138">Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.</span><span class="sxs-lookup"><span data-stu-id="7ad50-138">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="7ad50-139">Dans la boîte de dialogue **Choisir un modèle**, sélectionnez le modèle **Modèle marketing**.</span><span class="sxs-lookup"><span data-stu-id="7ad50-139">In the **Choose a template** dialog box, select the **Marketing template** template.</span></span> <span data-ttu-id="7ad50-140">Sous **Nom de la page**, entrez **Page marketing**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7ad50-140">Under **Page name**, enter **Marketing page**, and then select **OK**.</span></span>
1. <span data-ttu-id="7ad50-141">Dans l’emplacement **Principal** de la nouvelle page, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="7ad50-141">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="7ad50-142">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="7ad50-142">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="7ad50-143">Dans le volet des propriétés du module, définissez la valeur **Largeur** sur **Remplir le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="7ad50-143">In the module's properties pane, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="7ad50-144">Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="7ad50-144">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="7ad50-145">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **iframe**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7ad50-145">In the **Add Module** dialog box, select the **iframe** module, and then select **OK**.</span></span>
1. <span data-ttu-id="7ad50-146">Dans le volet des propriétés du module, définissez la valeur **URL cible** sur une URL externe pour une vidéo.</span><span class="sxs-lookup"><span data-stu-id="7ad50-146">In the module's properties pane, set the **Target URL** value to an external URL for a video.</span></span>
1. <span data-ttu-id="7ad50-147">Définissez d’autres propriétés, telles que **Titre** et **Hauteur**, selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="7ad50-147">Set other properties, such as **Heading** and **Height**, as you require.</span></span>
1. <span data-ttu-id="7ad50-148">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="7ad50-148">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="7ad50-149">Accédez à la page marketing de votre site.</span><span class="sxs-lookup"><span data-stu-id="7ad50-149">Go to the marketing page on your site.</span></span> <span data-ttu-id="7ad50-150">Vous devriez voir que la vidéo est affichée dans le module iframe.</span><span class="sxs-lookup"><span data-stu-id="7ad50-150">You should see that the video is rendered in the iframe module.</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="7ad50-151">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="7ad50-151">Additional resources</span></span>

[<span data-ttu-id="7ad50-152">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="7ad50-152">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="7ad50-153">Gérer la stratégie de sécurité de contenu (CSP)</span><span class="sxs-lookup"><span data-stu-id="7ad50-153">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)
