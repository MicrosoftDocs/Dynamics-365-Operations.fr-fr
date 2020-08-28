---
title: Ajouter un logo
description: Cette rubrique décrit comment ajouter un logo à votre site dans Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 62b8237fa0c30fa9d901d670de38416cf8615c8d
ms.sourcegitcommit: 81f162f2d50557d7afe292c8d326618ba0bc3259
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/11/2020
ms.locfileid: "3686644"
---
# <a name="add-a-logo"></a><span data-ttu-id="c8ab0-103">Ajouter un logo</span><span class="sxs-lookup"><span data-stu-id="c8ab0-103">Add a logo</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c8ab0-104">Cette rubrique décrit comment ajouter un logo à votre site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c8ab0-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c8ab0-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="c8ab0-105">Overview</span></span>

<span data-ttu-id="c8ab0-106">Lorsque vous créez votre site, l'une des premières choses que vous ferez probablement est d'ajouter le logo de votre entreprise ou de votre marque à l'en-tête du site.</span><span class="sxs-lookup"><span data-stu-id="c8ab0-106">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="c8ab0-107">Le kit de démarrage en ligne Dynamics 365 Commerce fournit un module qui facilite cette tâche.</span><span class="sxs-lookup"><span data-stu-id="c8ab0-107">The Dynamics 365 Commerce online starter kit provides a module that makes this task easy.</span></span>

<span data-ttu-id="c8ab0-108">Vous pouvez ajouter un logo directement à un modèle, une disposition ou une page.</span><span class="sxs-lookup"><span data-stu-id="c8ab0-108">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="c8ab0-109">De cette façon, vous pouvez facilement changer le logo qui apparaît sur des pages ou des groupes de pages spécifiques.</span><span class="sxs-lookup"><span data-stu-id="c8ab0-109">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="c8ab0-110">Cependant, cette rubrique couvre le scénario le plus fréquent, où vous ajoutez votre logo à un fragment d'en-tête qui peut être réutilisé sur toutes les pages de votre site.</span><span class="sxs-lookup"><span data-stu-id="c8ab0-110">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c8ab0-111">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="c8ab0-111">Prerequisites</span></span>

<span data-ttu-id="c8ab0-112">Avant de pouvoir ajouter un logo à toutes les pages de votre site, vous devez effectuer ces tâches.</span><span class="sxs-lookup"><span data-stu-id="c8ab0-112">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="c8ab0-113">Téléchargez votre logo dans la bibliothèque multimédia.</span><span class="sxs-lookup"><span data-stu-id="c8ab0-113">Upload your logo to the Media Library.</span></span>
1. <span data-ttu-id="c8ab0-114">Créez un fragment d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="c8ab0-114">Create a header fragment.</span></span> <span data-ttu-id="c8ab0-115">Pour plus d'informations sur la création et l'utilisation de fragments, consultez [Utilisation des fragments](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="c8ab0-115">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="c8ab0-116">Incluez le fragment d'en-tête dans le modèle que les pages de votre site utilisent pour leurs options de disposition et de module.</span><span class="sxs-lookup"><span data-stu-id="c8ab0-116">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="c8ab0-117">Pour plus d'informations sur les modèles, voir [Utilisation des modèles](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="c8ab0-117">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="c8ab0-118">Ajouter un logo à un fragment d'en-tête</span><span class="sxs-lookup"><span data-stu-id="c8ab0-118">Add a logo to a header fragment</span></span>

<span data-ttu-id="c8ab0-119">Pour ajouter un logo au fragment d'en-tête de votre site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c8ab0-119">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="c8ab0-120">Dans le volet de navigation sur la gauche, sélectionnez **Fragments**.</span><span class="sxs-lookup"><span data-stu-id="c8ab0-120">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="c8ab0-121">Sélectionnez le fragment d'en-tête créé précédemment, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="c8ab0-121">Select the header fragment that you created, and then select **Edit**.</span></span>
1. <span data-ttu-id="c8ab0-122">Développez le module d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="c8ab0-122">Expand the header module.</span></span>
1. <span data-ttu-id="c8ab0-123">Dans le volet des propriétés du module d'en-tête, fournissez une image et un lien pour le logo.</span><span class="sxs-lookup"><span data-stu-id="c8ab0-123">In the property pane for the header module, provide an image and link for the logo.</span></span> 
1. <span data-ttu-id="c8ab0-124">Enregistrez le fragment d'en-tête, terminez de le modifier et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="c8ab0-124">Save the header fragment, finish editing it, and publish it.</span></span>

<span data-ttu-id="c8ab0-125">Après avoir publié le fragment d'en-tête mis à jour, toutes les pages de site qui utilisent le modèle qui contient le fragment d'en-tête afficheront votre logo.</span><span class="sxs-lookup"><span data-stu-id="c8ab0-125">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c8ab0-126">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c8ab0-126">Additional resources</span></span>

[<span data-ttu-id="c8ab0-127">Sélectionner un thème pour le site</span><span class="sxs-lookup"><span data-stu-id="c8ab0-127">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="c8ab0-128">Utilisation de fichiers de remplacement CSS</span><span class="sxs-lookup"><span data-stu-id="c8ab0-128">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="c8ab0-129">Ajouter une icône de favori</span><span class="sxs-lookup"><span data-stu-id="c8ab0-129">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="c8ab0-130">Ajouter un message de bienvenue</span><span class="sxs-lookup"><span data-stu-id="c8ab0-130">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="c8ab0-131">Ajouter un avis de droits d’auteur</span><span class="sxs-lookup"><span data-stu-id="c8ab0-131">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="c8ab0-132">Ajouter des langues à votre site</span><span class="sxs-lookup"><span data-stu-id="c8ab0-132">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="c8ab0-133">Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie</span><span class="sxs-lookup"><span data-stu-id="c8ab0-133">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

