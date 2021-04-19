---
title: Ajouter un logo
description: Cette rubrique décrit comment ajouter un logo à votre site dans Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d9e1cba6bd07e0c3d9ed7d741d87e10837d8021c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797597"
---
# <a name="add-a-logo"></a><span data-ttu-id="5af51-103">Ajouter un logo</span><span class="sxs-lookup"><span data-stu-id="5af51-103">Add a logo</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5af51-104">Cette rubrique décrit comment ajouter un logo à votre site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5af51-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="5af51-105">Lorsque vous créez votre site, l’une des premières choses que vous ferez probablement est d’ajouter le logo de votre entreprise ou de votre marque à l’en-tête du site.</span><span class="sxs-lookup"><span data-stu-id="5af51-105">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="5af51-106">La bibliothèque de modules en ligne Dynamics 365 Commerce fournit un module qui facilite cette tâche.</span><span class="sxs-lookup"><span data-stu-id="5af51-106">The Dynamics 365 Commerce online module library provides a module that makes this task easy.</span></span>

<span data-ttu-id="5af51-107">Vous pouvez ajouter un logo directement à un modèle, une disposition ou une page.</span><span class="sxs-lookup"><span data-stu-id="5af51-107">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="5af51-108">De cette façon, vous pouvez facilement changer le logo qui apparaît sur des pages ou des groupes de pages spécifiques.</span><span class="sxs-lookup"><span data-stu-id="5af51-108">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="5af51-109">Cependant, cette rubrique couvre le scénario le plus fréquent, où vous ajoutez votre logo à un fragment d’en-tête qui peut être réutilisé sur toutes les pages de votre site.</span><span class="sxs-lookup"><span data-stu-id="5af51-109">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5af51-110">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="5af51-110">Prerequisites</span></span>

<span data-ttu-id="5af51-111">Avant de pouvoir ajouter un logo à toutes les pages de votre site, vous devez effectuer ces tâches.</span><span class="sxs-lookup"><span data-stu-id="5af51-111">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="5af51-112">Téléchargez votre logo dans la bibliothèque multimédia.</span><span class="sxs-lookup"><span data-stu-id="5af51-112">Upload your logo to the Media Library.</span></span>
1. <span data-ttu-id="5af51-113">Créez un fragment d’en-tête.</span><span class="sxs-lookup"><span data-stu-id="5af51-113">Create a header fragment.</span></span> <span data-ttu-id="5af51-114">Pour plus d’informations sur la création et l’utilisation de fragments, consultez [Utilisation des fragments](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="5af51-114">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="5af51-115">Incluez le fragment d’en-tête dans le modèle que les pages de votre site utilisent pour leurs options de disposition et de module.</span><span class="sxs-lookup"><span data-stu-id="5af51-115">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="5af51-116">Pour plus d’informations sur les modèles, voir [Utilisation des modèles](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="5af51-116">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="5af51-117">Ajouter un logo à un fragment d’en-tête</span><span class="sxs-lookup"><span data-stu-id="5af51-117">Add a logo to a header fragment</span></span>

<span data-ttu-id="5af51-118">Pour ajouter un logo au fragment d’en-tête de votre site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="5af51-118">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="5af51-119">Dans le volet de navigation sur la gauche, sélectionnez **Fragments**.</span><span class="sxs-lookup"><span data-stu-id="5af51-119">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="5af51-120">Sélectionnez le fragment d’en-tête créé précédemment, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="5af51-120">Select the header fragment that you created, and then select **Edit**.</span></span>
1. <span data-ttu-id="5af51-121">Développez le module d’en-tête.</span><span class="sxs-lookup"><span data-stu-id="5af51-121">Expand the header module.</span></span>
1. <span data-ttu-id="5af51-122">Dans le volet des propriétés du module d’en-tête, fournissez une image et un lien pour le logo.</span><span class="sxs-lookup"><span data-stu-id="5af51-122">In the property pane for the header module, provide an image and link for the logo.</span></span> 
1. <span data-ttu-id="5af51-123">Enregistrez le fragment d’en-tête, terminez de le modifier et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="5af51-123">Save the header fragment, finish editing it, and publish it.</span></span>

<span data-ttu-id="5af51-124">Après avoir publié le fragment d’en-tête mis à jour, toutes les pages de site qui utilisent le modèle qui contient le fragment d’en-tête afficheront votre logo.</span><span class="sxs-lookup"><span data-stu-id="5af51-124">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5af51-125">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="5af51-125">Additional resources</span></span>

[<span data-ttu-id="5af51-126">Sélectionner un thème pour le site</span><span class="sxs-lookup"><span data-stu-id="5af51-126">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="5af51-127">Utilisation de fichiers de remplacement CSS</span><span class="sxs-lookup"><span data-stu-id="5af51-127">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="5af51-128">Ajouter une icône de favori</span><span class="sxs-lookup"><span data-stu-id="5af51-128">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="5af51-129">Ajouter un message de bienvenue</span><span class="sxs-lookup"><span data-stu-id="5af51-129">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="5af51-130">Ajouter un avis de droits d’auteur</span><span class="sxs-lookup"><span data-stu-id="5af51-130">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="5af51-131">Ajouter des langues à votre site</span><span class="sxs-lookup"><span data-stu-id="5af51-131">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="5af51-132">Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie</span><span class="sxs-lookup"><span data-stu-id="5af51-132">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
