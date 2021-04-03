---
title: Module Sélecteur de sites
description: Cette rubrique couvre le module de sélecteur de sites et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: e24590d4a8f172809704aab0d761f6db0fb0e11b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234339"
---
# <a name="site-selector-module"></a><span data-ttu-id="4ea1d-103">Module de sélection de site</span><span class="sxs-lookup"><span data-stu-id="4ea1d-103">Site selector module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4ea1d-104">Cette rubrique couvre le module de sélecteur de sites et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-104">This topic covers the site selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="4ea1d-105">Lorsqu'une entreprise possède différents sites sur des marchés, des régions et des paramètres régionaux, les utilisateurs des sites ont besoin d'un moyen simple de basculer entre les sites et de sélectionner leur site d'achat préféré.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-105">When a business has different sites across markets, regions, and locales, site users need an easy way to switch between sites and select their preferred shopping site.</span></span> <span data-ttu-id="4ea1d-106">Pour s'adapter à ce scénario, le module de sélecteur de sites permet aux utilisateurs de parcourir plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-106">To accommodate this scenario, the site selector module lets users browse across multiple sites.</span></span>

<span data-ttu-id="4ea1d-107">Le module de sélecteur de sites doit être configuré avec la liste des sites (marchés, régions ou paramètres régionaux) que les utilisateurs des sites peuvent parcourir.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-107">The site selector module must be configured with the list of sites (markets, regions, or locales) that site users can browse.</span></span>

> [!NOTE]
> <span data-ttu-id="4ea1d-108">Le module de sélecteur de sites est disponible dans la version 10.0.14 de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-108">The site selector module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="4ea1d-109">L'illustration suivante montre un exemple de module de sélecteur de sites qui figure dans l'en-tête d'une page de site.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-109">The following illustration shows an example of a site selector module that is featured in the header of a site page.</span></span>

![Exemple de module de sélecteur de sites dans l'en-tête d'une page de site](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a><span data-ttu-id="4ea1d-111">Propriétés du module de sélecteur de sites</span><span class="sxs-lookup"><span data-stu-id="4ea1d-111">Site selector module properties</span></span>

| <span data-ttu-id="4ea1d-112">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="4ea1d-112">Property name</span></span> | <span data-ttu-id="4ea1d-113">Valeur</span><span class="sxs-lookup"><span data-stu-id="4ea1d-113">Value</span></span>                 | <span data-ttu-id="4ea1d-114">Description</span><span class="sxs-lookup"><span data-stu-id="4ea1d-114">Description</span></span> |
|---------------|-----------------------|-------------|
| <span data-ttu-id="4ea1d-115">Titre</span><span class="sxs-lookup"><span data-stu-id="4ea1d-115">Heading</span></span>       | <span data-ttu-id="4ea1d-116">Détails</span><span class="sxs-lookup"><span data-stu-id="4ea1d-116">Text</span></span>                  | <span data-ttu-id="4ea1d-117">En-tête du module.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-117">The heading for the module.</span></span> |
| <span data-ttu-id="4ea1d-118">Options de site</span><span class="sxs-lookup"><span data-stu-id="4ea1d-118">Site options</span></span>  | <span data-ttu-id="4ea1d-119">Nom, image, URL</span><span class="sxs-lookup"><span data-stu-id="4ea1d-119">Name, Image, URL</span></span>      | <span data-ttu-id="4ea1d-120">Cette propriété spécifie un nom, un lien vers la page d'accueil du site et une image facultative à afficher pour chaque site inclus dans le module.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-120">This property specifies a name, a link to the site's home page, and an optional image to show for each site that is included in the module.</span></span> <span data-ttu-id="4ea1d-121">L'image peut être un drapeau ou une représentation d'un marché, d'une région ou d'un lieu.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-121">The image can be a flag, or some representation of a market, region, or locale.</span></span> |

## <a name="add-a-site-selector-module-to-a-page"></a><span data-ttu-id="4ea1d-122">Ajouter un module de sélecteur de sites à une page</span><span class="sxs-lookup"><span data-stu-id="4ea1d-122">Add a site selector module to a page</span></span>

<span data-ttu-id="4ea1d-123">Le module de sélecteur de sites peut être ajouté au [Module d'en-tête](author-header-module.md) sous l'emplacement du sélecteur de sites.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-123">The site selector module can be added to the [Header module](author-header-module.md) under the site selector slot.</span></span> <span data-ttu-id="4ea1d-124">Une fois ajouté, vous pouvez définir l'en-tête du module et les options du site.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-124">After it's added, you can define the module heading and site options.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4ea1d-125">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="4ea1d-125">Additional resources</span></span>

[<span data-ttu-id="4ea1d-126">Vue d’ensemble de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="4ea1d-126">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="4ea1d-127">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="4ea1d-127">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="4ea1d-128">Module de barre de navigation</span><span class="sxs-lookup"><span data-stu-id="4ea1d-128">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="4ea1d-129">Module du menu de navigation</span><span class="sxs-lookup"><span data-stu-id="4ea1d-129">Navigation menu module</span></span>](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]