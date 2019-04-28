---
title: Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (17 septembre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-09-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 213324f9074f88d9fdc8efdfa46bc3ed7817d1e8
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "856805"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-september-17-2018"></a><span data-ttu-id="285a8-103">Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (17 septembre 2018)</span><span class="sxs-lookup"><span data-stu-id="285a8-103">What's new or changed in Dynamics 365 for Talent Core HR (September 17, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="285a8-104">**Version 8.1.154.0**</span><span class="sxs-lookup"><span data-stu-id="285a8-104">**Build 8.1.154.0**</span></span>

<span data-ttu-id="285a8-105">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.</span><span class="sxs-lookup"><span data-stu-id="285a8-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="leave-and-absence--accrue-time-based-on-hours-worked"></a><span data-ttu-id="285a8-106">Congé et absence – Accorder des congés sur la base des heures travaillées</span><span class="sxs-lookup"><span data-stu-id="285a8-106">Leave and Absence – Accrue time based on hours worked</span></span>

<span data-ttu-id="285a8-107">Un nouveau type de régularisation a été ajouté aux plans de congés.</span><span class="sxs-lookup"><span data-stu-id="285a8-107">A new accrual type has been added to Leave plans.</span></span> <span data-ttu-id="285a8-108">Le programme de régularisation peut maintenant être basé sur les mois de service ou les heures travaillées.</span><span class="sxs-lookup"><span data-stu-id="285a8-108">The accrual schedule can now be based on months of service or hours worked.</span></span> <span data-ttu-id="285a8-109">Pour plus d'informations, voir [Accorder des congés sur la base des heures travaillées](leave-accrue-hours-worked.md).</span><span class="sxs-lookup"><span data-stu-id="285a8-109">For more information, see [Accrue time off based on hours worked](leave-accrue-hours-worked.md).</span></span>

## <a name="platform-update-18"></a><span data-ttu-id="285a8-110">Platform update 18</span><span class="sxs-lookup"><span data-stu-id="285a8-110">Platform update 18</span></span>

<span data-ttu-id="285a8-111">Platform update 18 fait maintenant partie de la version de Talent.</span><span class="sxs-lookup"><span data-stu-id="285a8-111">Platform update 18 is now part of the Talent release.</span></span> 

-   <span data-ttu-id="285a8-112">Les champs obligatoires et autres champs peuvent être masqués via la personnalisation.</span><span class="sxs-lookup"><span data-stu-id="285a8-112">Mandatory and other fields can be hidden via personalization.</span></span> <span data-ttu-id="285a8-113">Cela permet à un utilisateur de créer une expérience simplifiée lorsque des champs obligatoires définis par défaut par la logique métier ne sont pas affichés.</span><span class="sxs-lookup"><span data-stu-id="285a8-113">This allows a user to create a simplified experience where mandatory fields that are defaulted by business logic are not shown.</span></span> <span data-ttu-id="285a8-114">Les champs obligatoires masqués sont également temporairement visibles s'ils sont vides lorsque un enregistrement est effectué.</span><span class="sxs-lookup"><span data-stu-id="285a8-114">Hidden mandatory fields are also temporarily made visible if they are empty when a save is attempted.</span></span>

-   <span data-ttu-id="285a8-115">Dans Platform update 18, le client Web Talent aligne maintenant ses visuels sur Microsoft Fluent Design.</span><span class="sxs-lookup"><span data-stu-id="285a8-115">In Platform update 18, the Talent web client now aligns its visuals with Microsoft Fluent Design.</span></span>

    -   <span data-ttu-id="285a8-116">Lorsque les champs sont en « mode lecture », vous pouvez simplement sélectionner l'option de modification des champs pour basculer l'écran en mode édition.</span><span class="sxs-lookup"><span data-stu-id="285a8-116">When fields are in “read mode”, you can simply select the edit option in the fields to switch the form to edit.</span></span>

    -   <span data-ttu-id="285a8-117">Modifications de l'affichage des champs en mode lecture.</span><span class="sxs-lookup"><span data-stu-id="285a8-117">Changes in how fields display when in read mode.</span></span>

    -   <span data-ttu-id="285a8-118">Les en-têtes dans les espaces de travail et les pages sont en gras.</span><span class="sxs-lookup"><span data-stu-id="285a8-118">Headings in workspaces and pages are bold.</span></span>

-   <span data-ttu-id="285a8-119">Le comportement des recherches sans remplacement a été amélioré.</span><span class="sxs-lookup"><span data-stu-id="285a8-119">The behavior of non-replacing lookups has been improved.</span></span> <span data-ttu-id="285a8-120">Pour plus d'informations, voir [Comportement amélioré pour les recherches sans remplacement](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fbusiness-applications-release-notes%2FOctober18%2Fdynamics365-finance-operations%2Fnon-replacing-lookups&data=02%7C01%7C%7Ce0b3b3bee47b4424aaa208d619ce86f2%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636724772137980342&sdata=RN1qjtZSLtS010zgs0KlcwFrrB8Z7uWWGtFjdxdaamg%3D&reserved=0).</span><span class="sxs-lookup"><span data-stu-id="285a8-120">For more information, see [Improved behavior for non-replacing lookups](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fbusiness-applications-release-notes%2FOctober18%2Fdynamics365-finance-operations%2Fnon-replacing-lookups&data=02%7C01%7C%7Ce0b3b3bee47b4424aaa208d619ce86f2%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636724772137980342&sdata=RN1qjtZSLtS010zgs0KlcwFrrB8Z7uWWGtFjdxdaamg%3D&reserved=0).</span></span>

## <a name="bug-fixes"></a><span data-ttu-id="285a8-121">Correctifs de bogue</span><span class="sxs-lookup"><span data-stu-id="285a8-121">Bug fixes</span></span>

<span data-ttu-id="285a8-122">Cette version contient plusieurs correctifs de bogue supplémentaires, notamment des références à ACA, ADA et I9, qui ne seront activés que dans les sociétés américaines.</span><span class="sxs-lookup"><span data-stu-id="285a8-122">This release includes several additional bug fixes, including references to ACA, ADA, and I9 now will only be enabled in US companies.</span></span>
