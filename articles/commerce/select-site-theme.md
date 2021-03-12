---
title: Sélectionner un thème pour le site
description: Cette rubrique décrit la procédure de définir ou de modifier le thème de votre site dans Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 66fcff9fa18d3c98e022ef91d15903fbba8b6b61
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982399"
---
# <a name="select-a-site-theme"></a><span data-ttu-id="5e5c3-103">Sélectionner un thème pour le site</span><span class="sxs-lookup"><span data-stu-id="5e5c3-103">Select a site theme</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5e5c3-104">Cette rubrique décrit la procédure de définir ou de modifier le thème de votre site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-104">This topic describes how to set or change your site's theme in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5e5c3-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="5e5c3-105">Overview</span></span>

<span data-ttu-id="5e5c3-106">La disposition et le style d'un site (par exemple, les polices, les tailles, les couleurs etc.) sont définis par le thème sélectionné et que vous appliquez au site.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-106">A site's layout and style (for example, fonts, sizes, and colors) are defined by the theme that you select and apply to the site.</span></span> <span data-ttu-id="5e5c3-107">Un thème est créé et déployé par un développeur de votre société.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-107">A theme is created and deployed by a developer at your company.</span></span> <span data-ttu-id="5e5c3-108">Pour obtenir une vue d'ensemble des thèmes, voir [Vue d'ensemble de la création de thème](e-commerce-extensibility/theming.md).</span><span class="sxs-lookup"><span data-stu-id="5e5c3-108">For an overview of themes, see [Theming overview](e-commerce-extensibility/theming.md).</span></span> <span data-ttu-id="5e5c3-109">Pour plus d'informations sur la création et le déploiement de thèmes, voir [Créer un thème](e-commerce-extensibility/create-theme.md).</span><span class="sxs-lookup"><span data-stu-id="5e5c3-109">For more information about how to create and deploy themes, see [Create a new theme](e-commerce-extensibility/create-theme.md).</span></span>

<span data-ttu-id="5e5c3-110">Par défaut, lorsque vous commencez par créer un site, il utilise un thème nommé **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-110">By default, when you first create a site, it uses a theme that is named **Fabrikam**.</span></span> <span data-ttu-id="5e5c3-111">Ce thème par défaut est disponible dans le cadre de la bibliothèque de modules Commerce.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-111">This default theme is provided as part of the Commerce module library.</span></span> <span data-ttu-id="5e5c3-112">Après avoir déployé des thèmes supplémentaires pour votre site, vous pouvez configurer le site afin qu'il utilise l'un d'entre eux à la place.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-112">After you've deployed additional themes for your site, you can configure the site so that it uses one of them instead.</span></span>

## <a name="select-the-site-theme"></a><span data-ttu-id="5e5c3-113">Sélectionner le thème du site</span><span class="sxs-lookup"><span data-stu-id="5e5c3-113">Select the site theme</span></span>

<span data-ttu-id="5e5c3-114">Pour sélectionner un thème appliqué à votre site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-114">To select the theme that is applied to your site, follow these steps.</span></span>

1. <span data-ttu-id="5e5c3-115">Dans l'environnement de création de site, accédez à votre site.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-115">In the site authoring environment, go to your site.</span></span>
1. <span data-ttu-id="5e5c3-116">Accédez à **Gestion du site** \> **Extensibilité**.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-116">Go to **Site Management** \> **Extensibility**.</span></span>
1. <span data-ttu-id="5e5c3-117">Sous **Thème**, sélectionnez un thème dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-117">Under **Theme**, select a theme on the drop-down menu.</span></span>
1. <span data-ttu-id="5e5c3-118">Pour appliquer le thème sélectionné à votre site, sélectionnez **Enregistrer et publier**.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-118">To apply the selected theme to your site, select **Save and publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="5e5c3-119">Le thème que vous sélectionnez est publié sur votre site dès que vous sélectionnerez **Enregistrer et publier** sur la page **Extensibilité**.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-119">The theme that you select is published to your site as soon as you select **Save and publish** on the **Extensibility** page.</span></span> <span data-ttu-id="5e5c3-120">Pour obtenir un aperçu du thème sur votre site avant de l'appliquer, vous pouvez utiliser votre environnement de développement ou bac à sable.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-120">To preview a theme on your site before you apply it, you can use your development or sandbox environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5e5c3-121">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="5e5c3-121">Additional resources</span></span>

[<span data-ttu-id="5e5c3-122">Ajouter un logo</span><span class="sxs-lookup"><span data-stu-id="5e5c3-122">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="5e5c3-123">Utilisation de fichiers de remplacement CSS</span><span class="sxs-lookup"><span data-stu-id="5e5c3-123">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="5e5c3-124">Ajouter une icône de favori</span><span class="sxs-lookup"><span data-stu-id="5e5c3-124">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="5e5c3-125">Ajouter un message de bienvenue</span><span class="sxs-lookup"><span data-stu-id="5e5c3-125">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="5e5c3-126">Ajouter un avis de droits d’auteur</span><span class="sxs-lookup"><span data-stu-id="5e5c3-126">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="5e5c3-127">Ajouter des langues à votre site</span><span class="sxs-lookup"><span data-stu-id="5e5c3-127">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="5e5c3-128">Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie</span><span class="sxs-lookup"><span data-stu-id="5e5c3-128">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="5e5c3-129">Vue d’ensemble de la création de thèmes</span><span class="sxs-lookup"><span data-stu-id="5e5c3-129">Theming overview</span></span>](e-commerce-extensibility/theming.md)

[<span data-ttu-id="5e5c3-130">Créer un thème</span><span class="sxs-lookup"><span data-stu-id="5e5c3-130">Create a new theme</span></span>](e-commerce-extensibility/create-theme.md)

