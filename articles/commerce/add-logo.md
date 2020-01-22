---
title: Ajouter un logo
description: Cette rubrique décrit comment ajouter un logo à votre site dans Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 12/12/2019
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
ms.openlocfilehash: 23bac9aae6beb59912bbc9e1f2c6958c007550b0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914618"
---
# <a name="add-a-logo"></a><span data-ttu-id="6b7c4-103">Ajouter un logo</span><span class="sxs-lookup"><span data-stu-id="6b7c4-103">Add a logo</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="6b7c4-104">Cette rubrique décrit comment ajouter un logo à votre site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6b7c4-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="6b7c4-105">Overview</span></span>

<span data-ttu-id="6b7c4-106">Lorsque vous créez votre site, l'une des premières choses que vous ferez probablement est d'ajouter le logo de votre entreprise ou de votre marque à l'en-tête du site.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-106">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="6b7c4-107">Le kit de démarrage en ligne Dynamics 365 Commerce fournit un module qui facilite cette tâche.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-107">The Dynamics 365 Commerce online starter kit provides a module that makes this task easy.</span></span>

<span data-ttu-id="6b7c4-108">Vous pouvez ajouter un logo directement à un modèle, une disposition ou une page.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-108">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="6b7c4-109">De cette façon, vous pouvez facilement changer le logo qui apparaît sur des pages ou des groupes de pages spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-109">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="6b7c4-110">Cependant, cette rubrique couvre le scénario le plus fréquent, où vous ajoutez votre logo à un fragment d'en-tête qui peut être réutilisé sur toutes les pages de votre site.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-110">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6b7c4-111">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="6b7c4-111">Prerequisites</span></span>

<span data-ttu-id="6b7c4-112">Avant de pouvoir ajouter un logo à toutes les pages de votre site, vous devez effectuer ces tâches.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-112">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="6b7c4-113">Chargez votre logo dans le gestionnaire des actifs numériques, auquel vous pouvez accéder depuis la page **Actifs**.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-113">Upload your logo to the digital assets manager, which you can access from the **Assets** page.</span></span>
1. <span data-ttu-id="6b7c4-114">Créez un fragment d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-114">Create a header fragment.</span></span> <span data-ttu-id="6b7c4-115">Pour plus d'informations sur la création et l'utilisation de fragments, consultez [Utilisation des fragments](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="6b7c4-115">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="6b7c4-116">Incluez le fragment d'en-tête dans le modèle que les pages de votre site utilisent pour leurs options de disposition et de module.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-116">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="6b7c4-117">Pour plus d'informations sur les modèles, voir [Utilisation des modèles](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="6b7c4-117">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="6b7c4-118">Ajouter un logo à un fragment d'en-tête</span><span class="sxs-lookup"><span data-stu-id="6b7c4-118">Add a logo to a header fragment</span></span>

<span data-ttu-id="6b7c4-119">Pour ajouter un logo au fragment d'en-tête de votre site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-119">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="6b7c4-120">Dans le volet de navigation de gauche, sélectionnez **Fragments**, puis sélectionnez le fragment d'en-tête que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-120">In the navigation pane on the left, select **Fragments**, and then select the header fragment that you created.</span></span>
2. <span data-ttu-id="6b7c4-121">Sélectionnez **Caisse**.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-121">Select **Check out**.</span></span>
3. <span data-ttu-id="6b7c4-122">Développez l'emplacement **En-tête** et l'emplacement **Logo**.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-122">Expand the **Header** slot and the **Logo** slot.</span></span>
4. <span data-ttu-id="6b7c4-123">Sélectionnez le bouton représentant des points de suspension (**...**) en regard de l'emplacement **Logo**, et sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-123">Select the ellipsis button (**...**) for the **Logo** slot, and then select **Add module**.</span></span>
5. <span data-ttu-id="6b7c4-124">Sélectionnez le module du logo.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-124">Select the logo module.</span></span>
6. <span data-ttu-id="6b7c4-125">Dans le volet des propriétés de droite, configurez le module de logo afin qu'il affiche votre logo.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-125">In the properties pane on the right, configure the logo module so that it shows your logo.</span></span>
7. <span data-ttu-id="6b7c4-126">Enregistrez le fragment d'en-tête, archivez-le, et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-126">Save the header fragment, check it in, and publish it.</span></span>

<span data-ttu-id="6b7c4-127">Après avoir publié le fragment d'en-tête mis à jour, toutes les pages de site qui utilisent le modèle qui contient le fragment d'en-tête afficheront votre logo.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-127">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6b7c4-128">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6b7c4-128">Additional resources</span></span>

[<span data-ttu-id="6b7c4-129">Sélectionner un thème pour le site</span><span class="sxs-lookup"><span data-stu-id="6b7c4-129">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="6b7c4-130">Utilisation de fichiers de remplacement CSS</span><span class="sxs-lookup"><span data-stu-id="6b7c4-130">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="6b7c4-131">Ajouter une icône de favori</span><span class="sxs-lookup"><span data-stu-id="6b7c4-131">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="6b7c4-132">Ajouter un message de bienvenue</span><span class="sxs-lookup"><span data-stu-id="6b7c4-132">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="6b7c4-133">Ajouter un avis de droits d'auteur</span><span class="sxs-lookup"><span data-stu-id="6b7c4-133">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="6b7c4-134">Ajouter des langues à votre site</span><span class="sxs-lookup"><span data-stu-id="6b7c4-134">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="6b7c4-135">Ajout d'un code de script aux pages de site pour prendre en charge la télémétrie</span><span class="sxs-lookup"><span data-stu-id="6b7c4-135">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

