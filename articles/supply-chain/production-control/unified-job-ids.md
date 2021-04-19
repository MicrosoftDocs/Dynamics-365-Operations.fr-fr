---
title: Souche de numéros unifiés pour les ID tâche
description: Cette fonction fournit une souche de numéros unique et unifiée qui génère des ID de tâche pour les modules Contrôle de la production, Exécution de la fabrication et Pointage.
author: johanhoffmann
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 00212803c46d898a39eafbc5c62016eb829535e2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824940"
---
# <a name="unified-number-sequence-for-job-ids"></a><span data-ttu-id="6c674-103">Souche de numéros unifiés pour les ID tâche</span><span class="sxs-lookup"><span data-stu-id="6c674-103">Unified number sequence for job IDs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6c674-104">Cette fonction fournit une souche de numéros unique et unifiée qui génère des ID de tâche pour les modules Contrôle de la production, Exécution de la fabrication et Pointage.</span><span class="sxs-lookup"><span data-stu-id="6c674-104">This feature provides a single, unified number sequence that generates job IDs for the Production control, Manufacturing execution, and Time and attendance modules.</span></span> <span data-ttu-id="6c674-105">Auparavant, vous pouviez choisir une souche de numéros différente pour chacun de ces modules, ce qui pouvait entraîner des conflits d’ID de tâche si deux ou plusieurs de ces souches utilisaient un format identique.</span><span class="sxs-lookup"><span data-stu-id="6c674-105">Previously, you were able to choose a different number sequence for each of these modules, which could result in conflicting job IDs if two or more of these sequences used an identical format.</span></span> <span data-ttu-id="6c674-106">Un tel conflit peut entraîner une corruption des données.</span><span class="sxs-lookup"><span data-stu-id="6c674-106">Such a conflict can cause data corruption.</span></span>

## <a name="turn-on-this-feature-for-your-system"></a><span data-ttu-id="6c674-107">Activez cette fonctionnalité pour votre système</span><span class="sxs-lookup"><span data-stu-id="6c674-107">Turn on this feature for your system</span></span>

<span data-ttu-id="6c674-108">Si votre système n’inclut pas déjà la fonctionnalité décrite dans cette rubrique, accédez à [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et activez la fonctionnalité *Souche de numéros unifiée pour les ID de tâche*.</span><span class="sxs-lookup"><span data-stu-id="6c674-108">If your system doesn't already include the feature described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the *Unified number sequence for job IDs* feature.</span></span>

## <a name="set-up-the-unified-number-sequence-for-job-ids"></a><span data-ttu-id="6c674-109">Paramétrer la souche de numéros unifiée pour les ID de tâche</span><span class="sxs-lookup"><span data-stu-id="6c674-109">Set up the unified number sequence for job IDs</span></span>

<span data-ttu-id="6c674-110">Après avoir activé cette fonctionnalité, les paramètres de souche de numéros **Identification de tâche** situés sur les pages de paramètres des modules Contrôle de production, Exécution de la fabrication et Pointage seront obsolètes et un nouveau champ **ID de tâche unifié** sera ajouté.</span><span class="sxs-lookup"><span data-stu-id="6c674-110">After enabling this feature, the existing **Job identification** number-sequence settings located on the parameters pages for the Production control, Manufacturing execution, and Time and attendance modules will be deprecated and a new **Unified job ID** field will be added.</span></span> <span data-ttu-id="6c674-111">La valeur **ID de tâche unifié** est partagée par les trois modules. Cela garantit que tous les modules font référence à la même souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="6c674-111">The **Unified job ID** value is shared by all three modules, thus ensuring that all modules reference the same number sequence.</span></span> <span data-ttu-id="6c674-112">Les ID de tâche seront donc uniques dans les trois modules et aucun conflit ne se produira jamais.</span><span class="sxs-lookup"><span data-stu-id="6c674-112">Job IDs will therefore be unique across all three modules and a conflict will never occur.</span></span>

<span data-ttu-id="6c674-113">Pour paramétrer la souche de numéros unifiée pour les ID de tâche :</span><span class="sxs-lookup"><span data-stu-id="6c674-113">To set up the unified number sequence for job IDs:</span></span>

1. <span data-ttu-id="6c674-114">Activez la fonction comme décrit dans la section précédente.</span><span class="sxs-lookup"><span data-stu-id="6c674-114">Turn on the feature as described in the previous section.</span></span>
1. <span data-ttu-id="6c674-115">Identifiez la souche de numéros que vous souhaitez utiliser pour vos ID de tâche unifiés ou créez-en une nouvelle.</span><span class="sxs-lookup"><span data-stu-id="6c674-115">Either identify the number sequence you want to use for your unified job IDs, or create a new one.</span></span> <span data-ttu-id="6c674-116">Pour plus d’informations, voir [Vue d’ensemble des souches de numéros](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6c674-116">For more information, see [Number sequences overview](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).</span></span>
1. <span data-ttu-id="6c674-117">Accédez à la page **Paramètres de contrôle de la production**, **Paramètres d’exécution de la fabrication**, ou **Paramètres de pointage**.</span><span class="sxs-lookup"><span data-stu-id="6c674-117">Go to the **Production control parameters**, **Manufacturing execution parameters**, or **Time and attendance parameters** page.</span></span> <span data-ttu-id="6c674-118">Peu importe celle que vous choisissez, car lorsque vous définissez ce paramètre sur l’une de ces pages, toutes les autres pages se mettront à jour automatiquement.</span><span class="sxs-lookup"><span data-stu-id="6c674-118">It doesn't matter which one you choose because when you make this setting on any of those pages, all of the other pages will update automatically.</span></span>
1. <span data-ttu-id="6c674-119">Ouvrez l’onglet **Souche de numéros** sur la page des paramètres sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6c674-119">Open the **Number sequences** tab on your selected parameters page.</span></span>
1. <span data-ttu-id="6c674-120">Attribuez le **Code de souche de numéros** que vous avez identifié précédemment dans la ligne de la grille **ID de tâche unifiés**.</span><span class="sxs-lookup"><span data-stu-id="6c674-120">Assign the **Number sequence code** that you identified previously to the **Unified job IDs** row of the grid.</span></span>
