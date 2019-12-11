---
title: Module Alerte
description: Cette rubrique couvre les modules d'alerte et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 82138dd7f0934f732215f67a3726638eb87075d4
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785350"
---
# <a name="alert-module"></a><span data-ttu-id="ed147-103">Module Alerte</span><span class="sxs-lookup"><span data-stu-id="ed147-103">Alert module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="ed147-104">Cette rubrique couvre les modules d'alerte et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ed147-104">This topic covers alert modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ed147-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="ed147-105">Overview</span></span>

<span data-ttu-id="ed147-106">Un module d'alerte est utilisé pour afficher des messages d'information intégrés sur une page.</span><span class="sxs-lookup"><span data-stu-id="ed147-106">An alert module is used to show inline informational messages on a page.</span></span> <span data-ttu-id="ed147-107">Les modules d'alerte prennent en charge un texte et un lien.</span><span class="sxs-lookup"><span data-stu-id="ed147-107">Alert modules support a text message and a link.</span></span> <span data-ttu-id="ed147-108">Ils peuvent être utilisés pour afficher des promotions à l'échelle du site qui figurent sur toutes les pages d'un site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="ed147-108">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="ed147-109">Les modules d'alerte sont pilotés par les données du système de gestion de contenu (CMS) et peuvent être placés dans n'importe quelle page.</span><span class="sxs-lookup"><span data-stu-id="ed147-109">Alert modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="examples-of-alert-modules-in-e-commerce"></a><span data-ttu-id="ed147-110">Exemples de modules d'alerte dans le commerce électronique</span><span class="sxs-lookup"><span data-stu-id="ed147-110">Examples of alert modules in e-Commerce</span></span>

<span data-ttu-id="ed147-111">Les modules d'alerte peuvent être utilisés dans l'en-tête de site pour indiquer des promotions ou des messages à l'échelle du site.</span><span class="sxs-lookup"><span data-stu-id="ed147-111">Alert modules can be used in the site header to indicate site-wide promotions or messages.</span></span> <span data-ttu-id="ed147-112">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="ed147-112">Here are some examples:</span></span>

<span data-ttu-id="ed147-113">« Les soldes annuelles se terminent dans 10 jours »</span><span class="sxs-lookup"><span data-stu-id="ed147-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="ed147-114">« Réalisez des économisez avec les soldes de la rentrée.</span><span class="sxs-lookup"><span data-stu-id="ed147-114">"Save big with back to school sale.</span></span> <span data-ttu-id="ed147-115">Achetez dès maintenant. »</span><span class="sxs-lookup"><span data-stu-id="ed147-115">Shop Now."</span></span>

## <a name="alert-module-properties"></a><span data-ttu-id="ed147-116">Propriétés du module d'alerte</span><span class="sxs-lookup"><span data-stu-id="ed147-116">Alert module properties</span></span>

| <span data-ttu-id="ed147-117">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="ed147-117">Property name</span></span>  | <span data-ttu-id="ed147-118">Valeur</span><span class="sxs-lookup"><span data-stu-id="ed147-118">Value</span></span>                              | <span data-ttu-id="ed147-119">Description</span><span class="sxs-lookup"><span data-stu-id="ed147-119">Description</span></span> |
|----------------|------------------------------------|-------------|
| <span data-ttu-id="ed147-120">Détails</span><span class="sxs-lookup"><span data-stu-id="ed147-120">Text</span></span>           | <span data-ttu-id="ed147-121">Détails</span><span class="sxs-lookup"><span data-stu-id="ed147-121">Text</span></span>                               | <span data-ttu-id="ed147-122">Texte qui s'affiche dans le module d'alerte.</span><span class="sxs-lookup"><span data-stu-id="ed147-122">The text message that appears in the alert module.</span></span> |
| <span data-ttu-id="ed147-123">Alignement du texte</span><span class="sxs-lookup"><span data-stu-id="ed147-123">Text alignment</span></span> | <span data-ttu-id="ed147-124">**Droite**, **Gauche** ou **Centre**</span><span class="sxs-lookup"><span data-stu-id="ed147-124">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="ed147-125">Valeur qui définit la manière dont le texte est aligné dans le module d'alerte.</span><span class="sxs-lookup"><span data-stu-id="ed147-125">A value that defines how text is aligned in the alert module.</span></span> |
| <span data-ttu-id="ed147-126">Ignorer l'alerte</span><span class="sxs-lookup"><span data-stu-id="ed147-126">Dismiss alert</span></span>  | <span data-ttu-id="ed147-127">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="ed147-127">**True** or **False**</span></span>              | <span data-ttu-id="ed147-128">Si la valeur est définie sur **Vrai**, le client peut ignorer l'alerte.</span><span class="sxs-lookup"><span data-stu-id="ed147-128">If the value is set to **True**, the customer can dismiss the alert.</span></span> |
| <span data-ttu-id="ed147-129">Lien</span><span class="sxs-lookup"><span data-stu-id="ed147-129">Link</span></span>           | <span data-ttu-id="ed147-130">URL</span><span class="sxs-lookup"><span data-stu-id="ed147-130">URL</span></span>                                | <span data-ttu-id="ed147-131">URL pour un lien supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="ed147-131">The URL for an optional link.</span></span> |

## <a name="add-an-alert-module-to-a-page"></a><span data-ttu-id="ed147-132">Ajouter un module d'alerte à une page</span><span class="sxs-lookup"><span data-stu-id="ed147-132">Add an alert module to a page</span></span> 

<span data-ttu-id="ed147-133">Pour ajouter un module d'alerte à une page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ed147-133">To add an alert module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="ed147-134">Créez un modèle de page nommé **modèle d'alerte**.</span><span class="sxs-lookup"><span data-stu-id="ed147-134">Create a page template that is named **alert template**.</span></span>
1. <span data-ttu-id="ed147-135">À l'emplacement **Principal** de la page par défaut, ajoutez un module d'alerte.</span><span class="sxs-lookup"><span data-stu-id="ed147-135">In the **Main** slot of the default page, add an alert module.</span></span>
1. <span data-ttu-id="ed147-136">Archivez le modèle, et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="ed147-136">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="ed147-137">Utilisez le modèle d'alerte que vous venez de créer pour créer une page qui s'appelle **page d'alerte**.</span><span class="sxs-lookup"><span data-stu-id="ed147-137">Use the alert template that you just created to create a page that is named **alert page**.</span></span> 
1. <span data-ttu-id="ed147-138">À l'emplacement **Principal** de la nouvelle page, ajoutez un module d'alerte.</span><span class="sxs-lookup"><span data-stu-id="ed147-138">In the **Main** slot of the new page, add an alert module.</span></span>
1. <span data-ttu-id="ed147-139">Dans les paramètres du module d'alerte, entrez le texte d'alerte.</span><span class="sxs-lookup"><span data-stu-id="ed147-139">In the settings for the alert module, enter the alert text.</span></span> <span data-ttu-id="ed147-140">Vous pouvez modifier les autres propriétés si vous souhaitez personnaliser le module d'alerte davantage.</span><span class="sxs-lookup"><span data-stu-id="ed147-140">You can edit the other properties if you want to customize the alert module further.</span></span>
1. <span data-ttu-id="ed147-141">Enregistrez et affichez un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="ed147-141">Save and preview the page.</span></span> <span data-ttu-id="ed147-142">En haut de la page, vous devez voir une alerte avec le texte que vous avez ajouté.</span><span class="sxs-lookup"><span data-stu-id="ed147-142">At the top of the page, you should see an alert that has the text that you added.</span></span>
1. <span data-ttu-id="ed147-143">Archivez la page, et publiez-la.</span><span class="sxs-lookup"><span data-stu-id="ed147-143">Check in the page, and publish it.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="ed147-144">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ed147-144">Additional resources</span></span>

[<span data-ttu-id="ed147-145">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="ed147-145">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="ed147-146">Module Carrousel</span><span class="sxs-lookup"><span data-stu-id="ed147-146">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="ed147-147">Module de bloc de contenu riche</span><span class="sxs-lookup"><span data-stu-id="ed147-147">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="ed147-148">Module Placement de contenu</span><span class="sxs-lookup"><span data-stu-id="ed147-148">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="ed147-149">Module Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="ed147-149">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="ed147-150">Module Bannière</span><span class="sxs-lookup"><span data-stu-id="ed147-150">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="ed147-151">Module Lecteur vidéo</span><span class="sxs-lookup"><span data-stu-id="ed147-151">Video player module</span></span>](add-video-player.md)
