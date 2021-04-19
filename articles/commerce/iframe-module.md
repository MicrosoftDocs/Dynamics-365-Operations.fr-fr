---
title: Module iframe
description: Cette rubrique couvre le module iframe et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 7b397b91d1b8a45347ef2d05f42fb7c610ab3912
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797068"
---
# <a name="iframe-module"></a><span data-ttu-id="ed9da-103">Module iFrame</span><span class="sxs-lookup"><span data-stu-id="ed9da-103">Iframe module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ed9da-104">Cette rubrique couvre le module iframe et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ed9da-104">This topic covers the iframe module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="ed9da-105">Un module iframe fournit un iframe (cadre incorporé) qui héberge du contenu externe sur un site.</span><span class="sxs-lookup"><span data-stu-id="ed9da-105">An iframe module provides an iframe (inline frame) that hosts external content on a site.</span></span> <span data-ttu-id="ed9da-106">Par exemple, il peut être utilisé pour héberger une vidéo YouTube ou une visionneuse de fichiers PDF sur une page de site.</span><span class="sxs-lookup"><span data-stu-id="ed9da-106">For example, it can be used to host a YouTube video or a PDF file viewer on any site page.</span></span> 

<span data-ttu-id="ed9da-107">Un module iframe nécessite une URL cible.</span><span class="sxs-lookup"><span data-stu-id="ed9da-107">An iframe module requires a target URL.</span></span> <span data-ttu-id="ed9da-108">Il héberge ensuite le contenu de la page cible dans un élément **iframe** HTML.</span><span class="sxs-lookup"><span data-stu-id="ed9da-108">It then hosts the content of the target page inside an HTML **iframe** element.</span></span> <span data-ttu-id="ed9da-109">Les URL externes doivent figurer sur la liste d’autorisation conformément aux instructions de la stratégie de sécurité du contenu (CSP) du site.</span><span class="sxs-lookup"><span data-stu-id="ed9da-109">External URLs must be on the allow list per the site's content security policy (CSP) directives.</span></span> <span data-ttu-id="ed9da-110">Pour le contenu iframe, les URL doivent être autorisées à l’aide de l’instruction **frame-ancestor**.</span><span class="sxs-lookup"><span data-stu-id="ed9da-110">For iframe content, URLs should be allowed by using the **frame-ancestor** directive.</span></span> <span data-ttu-id="ed9da-111">Pour plus d’informations, voir [Gérer la stratégie de sécurité du contenu (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="ed9da-111">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ed9da-112">Le module iframe est disponible dans Dynamics 365 Commerce version 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="ed9da-112">The iframe module is available in the Dynamics 365 Commerce 10.0.13 release.</span></span>

<span data-ttu-id="ed9da-113">L’image suivante montre des exemples de modules iframe qui présentent des vidéos externes sur des pages de site.</span><span class="sxs-lookup"><span data-stu-id="ed9da-113">The following image shows examples of iframe modules that showcase external videos on site pages.</span></span>

![Exemple de modules iframe qui présentent des vidéos externes](./media/ecommerce-iframe.PNG)

## <a name="iframe-module-properties"></a><span data-ttu-id="ed9da-115">Propriétés du module iframe</span><span class="sxs-lookup"><span data-stu-id="ed9da-115">Iframe module properties</span></span>

| <span data-ttu-id="ed9da-116">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="ed9da-116">Property name</span></span>             | <span data-ttu-id="ed9da-117">Valeur</span><span class="sxs-lookup"><span data-stu-id="ed9da-117">Value</span></span>                 | <span data-ttu-id="ed9da-118">Description</span><span class="sxs-lookup"><span data-stu-id="ed9da-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="ed9da-119">Titre</span><span class="sxs-lookup"><span data-stu-id="ed9da-119">Heading</span></span> | <span data-ttu-id="ed9da-120">Détails</span><span class="sxs-lookup"><span data-stu-id="ed9da-120">Text</span></span> | <span data-ttu-id="ed9da-121">En-tête du module.</span><span class="sxs-lookup"><span data-stu-id="ed9da-121">The heading for the module.</span></span> |
| <span data-ttu-id="ed9da-122">URL cible</span><span class="sxs-lookup"><span data-stu-id="ed9da-122">Target URL</span></span> | <span data-ttu-id="ed9da-123">URL</span><span class="sxs-lookup"><span data-stu-id="ed9da-123">URL</span></span> | <span data-ttu-id="ed9da-124">URL hébergée dans le module.</span><span class="sxs-lookup"><span data-stu-id="ed9da-124">The URL that is hosted in the module.</span></span> |
| <span data-ttu-id="ed9da-125">Hauteur</span><span class="sxs-lookup"><span data-stu-id="ed9da-125">Height</span></span> | <span data-ttu-id="ed9da-126">Nombre ou pourcentage</span><span class="sxs-lookup"><span data-stu-id="ed9da-126">Number or percentage</span></span> | <span data-ttu-id="ed9da-127">Hauteur du module, en pixels ou en pourcentage.</span><span class="sxs-lookup"><span data-stu-id="ed9da-127">The height of the module, in pixels or as a percentage.</span></span> <span data-ttu-id="ed9da-128">Par exemple, la valeur **100** est traitée comme un nombre de pixels et la valeur **100 %** est traitée comme un pourcentage.</span><span class="sxs-lookup"><span data-stu-id="ed9da-128">For example, the value **100** will be treated as a number of pixels, and the value **100%** will be treated as a percentage.</span></span> |
| <span data-ttu-id="ed9da-129">Aria-label</span><span class="sxs-lookup"><span data-stu-id="ed9da-129">Aria label</span></span> | <span data-ttu-id="ed9da-130">Détails</span><span class="sxs-lookup"><span data-stu-id="ed9da-130">Text</span></span> | <span data-ttu-id="ed9da-131">Une étiquette ARIA (Accessible Rich Internet Applications) peut être définie à des fins d’accessibilité.</span><span class="sxs-lookup"><span data-stu-id="ed9da-131">An Accessible Rich Internet Applications (ARIA) label can be defined for accessibility purposes.</span></span> |

## <a name="add-an-iframe-module-to-a-page"></a><span data-ttu-id="ed9da-132">Ajouter un module iframe à une page</span><span class="sxs-lookup"><span data-stu-id="ed9da-132">Add an iframe module to a page</span></span>

<span data-ttu-id="ed9da-133">Pour ajouter un module iframe à une page afin d’afficher une vidéo externe, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ed9da-133">To add an iframe module to a page to show an external video, follow these steps.</span></span>

1. <span data-ttu-id="ed9da-134">Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="ed9da-134">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="ed9da-135">Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle marketing**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed9da-135">In the **New Template** dialog box, under **Template name**, enter **Marketing template**, and then select **OK**.</span></span>
1. <span data-ttu-id="ed9da-136">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="ed9da-136">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="ed9da-137">Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.</span><span class="sxs-lookup"><span data-stu-id="ed9da-137">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="ed9da-138">Dans la boîte de dialogue **Choisir un modèle**, sélectionnez le modèle **Modèle marketing**.</span><span class="sxs-lookup"><span data-stu-id="ed9da-138">In the **Choose a template** dialog box, select the **Marketing template** template.</span></span> <span data-ttu-id="ed9da-139">Sous **Nom de la page**, entrez **Page marketing**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed9da-139">Under **Page name**, enter **Marketing page**, and then select **OK**.</span></span>
1. <span data-ttu-id="ed9da-140">Dans l’emplacement **Principal** de la nouvelle page, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="ed9da-140">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="ed9da-141">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed9da-141">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="ed9da-142">Dans le volet des propriétés du module, définissez la valeur **Largeur** sur **Remplir le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="ed9da-142">In the module's properties pane, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="ed9da-143">Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="ed9da-143">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="ed9da-144">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **iframe**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed9da-144">In the **Add Module** dialog box, select the **iframe** module, and then select **OK**.</span></span>
1. <span data-ttu-id="ed9da-145">Dans le volet des propriétés du module, définissez la valeur **URL cible** sur une URL externe pour une vidéo.</span><span class="sxs-lookup"><span data-stu-id="ed9da-145">In the module's properties pane, set the **Target URL** value to an external URL for a video.</span></span>
1. <span data-ttu-id="ed9da-146">Définissez d’autres propriétés, telles que **Titre** et **Hauteur**, selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="ed9da-146">Set other properties, such as **Heading** and **Height**, as you require.</span></span>
1. <span data-ttu-id="ed9da-147">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="ed9da-147">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="ed9da-148">Accédez à la page marketing de votre site.</span><span class="sxs-lookup"><span data-stu-id="ed9da-148">Go to the marketing page on your site.</span></span> <span data-ttu-id="ed9da-149">Vous devriez voir que la vidéo est affichée dans le module iframe.</span><span class="sxs-lookup"><span data-stu-id="ed9da-149">You should see that the video is rendered in the iframe module.</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="ed9da-150">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ed9da-150">Additional resources</span></span>

[<span data-ttu-id="ed9da-151">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="ed9da-151">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="ed9da-152">Gérer la stratégie de sécurité de contenu (CSP)</span><span class="sxs-lookup"><span data-stu-id="ed9da-152">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]