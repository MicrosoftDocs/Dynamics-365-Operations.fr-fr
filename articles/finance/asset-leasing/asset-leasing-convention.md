---
title: Conventions de location d’actifs
description: Cette rubrique décrit les conventions d’actifs loués.
author: moaamer
manager: Ann Beebe
ms.date: 1/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ea89d54f1ce3a1e971d41623bf44f909f7dfdf09
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5131283"
---
# <a name="asset-leasing-conventions"></a><span data-ttu-id="d632f-103">Conventions de location d’actifs</span><span class="sxs-lookup"><span data-stu-id="d632f-103">Asset leasing conventions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d632f-104">Cette rubrique décrit les conventions d’actifs loués.</span><span class="sxs-lookup"><span data-stu-id="d632f-104">This topic describes conventions for leased assets.</span></span> <span data-ttu-id="d632f-105">Les conventions de location sont utilisées pour déterminer la date de début d'un registre des baux.</span><span class="sxs-lookup"><span data-stu-id="d632f-105">Leasing conventions are used to determine the commencement date of a lease book.</span></span> <span data-ttu-id="d632f-106">Si la convention de location est définie sur **Aucun**, la date de début est la même que la date de début du bail (c'est-à-dire la valeur du champ **Date de début du bail**).</span><span class="sxs-lookup"><span data-stu-id="d632f-106">If the leasing convention is set to **None**, the commencement date is the same as the start date for the lease (that is, the value of the **Lease start date** field).</span></span> <span data-ttu-id="d632f-107">Si la convention de location est définie sur **Mois complet**, la date de début est le premier jour du mois où tombe la date de début du bail.</span><span class="sxs-lookup"><span data-stu-id="d632f-107">If the leasing convention is set to **Full month**, the commencement date is the first day of the month that the lease's start date falls in.</span></span>

<span data-ttu-id="d632f-108">La date de début détermine la date de début de la période pour les plans d'amortissement du passif et des actifs.</span><span class="sxs-lookup"><span data-stu-id="d632f-108">The commencement date determines the start date of the period for the liability amortization and asset depreciation schedules.</span></span> <span data-ttu-id="d632f-109">Les charges d'intérêts et les charges d'amortissement sont comptabilisées à la date de fin de la période des plans correspondants.</span><span class="sxs-lookup"><span data-stu-id="d632f-109">Interest expenses and depreciation expenses are posted on the period end date of the corresponding schedules.</span></span> <span data-ttu-id="d632f-110">La comptabilisation initiale et l'écriture dans le journal d'ajustement sont enregistrées à la date de début.</span><span class="sxs-lookup"><span data-stu-id="d632f-110">The initial recognition and adjustment journal entry are posted on the commencement date.</span></span>

> [!NOTE]
> <span data-ttu-id="d632f-111">La fonctionnalité pour les conventions de location doit être activée via la gestion des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="d632f-111">The feature for leasing conventions must be turned on through Feature Management.</span></span> <span data-ttu-id="d632f-112">Dans l'espace de travail **Gestion des fonctionnalités**, recherchez et sélectionnez la fonction intitulée **Convention de location pour la location d'actifs**, puis sélectionnez **Activer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="d632f-112">In the **Feature management** workspace, find and select the feature that is named **Leasing convention for asset leasing** feature, and then select **Enable now**.</span></span>

<span data-ttu-id="d632f-113">Les conventions de location sont affectées à la configuration d'un registre d'actifs de location.</span><span class="sxs-lookup"><span data-stu-id="d632f-113">Leasing conventions are assigned to the setup for a lease asset book.</span></span>

<span data-ttu-id="d632f-114">Pour afficher ou attribuer la convention de location, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d632f-114">To view or assign the leasing convention, follow these steps.</span></span>

1. <span data-ttu-id="d632f-115">Accédez à **Location d’actifs \> Configuration \> registres de baux**.</span><span class="sxs-lookup"><span data-stu-id="d632f-115">Go to **Asset leasing \> Setup \> Lease books**.</span></span>
2. <span data-ttu-id="d632f-116">Dans le champ **Convention de location**, sélectionnez l’une des valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="d632f-116">In the **Leasing convention** field, select one of the following values.</span></span>

    | <span data-ttu-id="d632f-117">Convention de leasing</span><span class="sxs-lookup"><span data-stu-id="d632f-117">Leasing convention</span></span> | <span data-ttu-id="d632f-118">Description</span><span class="sxs-lookup"><span data-stu-id="d632f-118">Description</span></span> |
    |--------------------|-------------|
    | <span data-ttu-id="d632f-119">None</span><span class="sxs-lookup"><span data-stu-id="d632f-119">None</span></span>               | <span data-ttu-id="d632f-120">Les plans d'amortissement du passif et des actifs commencent à la date de début du contrat de location, car la date de début correspond à la date de début du contrat de location.</span><span class="sxs-lookup"><span data-stu-id="d632f-120">The liability amortization and asset depreciation schedules start on the lease's start date, because the commencement date equals the lease's start date.</span></span> <span data-ttu-id="d632f-121">La date de fin est un mois plus tard.</span><span class="sxs-lookup"><span data-stu-id="d632f-121">The end date is one month later.</span></span> <span data-ttu-id="d632f-122">Cette convention de location ne garantit pas la comptabilisation des intérêts le dernier jour de chaque mois.</span><span class="sxs-lookup"><span data-stu-id="d632f-122">This leasing convention doesn't guarantee that the interest will be posted on the last day of each month.</span></span> |
    | <span data-ttu-id="d632f-123">Mois complet</span><span class="sxs-lookup"><span data-stu-id="d632f-123">Full month</span></span>         | <span data-ttu-id="d632f-124">Pour les contrats de location dont la date de début survient à n'importe quel moment du mois, les calendriers d'amortissement du passif et des actifs commencent à accumuler des charges le premier jour de ce mois.</span><span class="sxs-lookup"><span data-stu-id="d632f-124">For leases that have a start date that occurs at any time during the month, the liability amortization and asset depreciation schedules start to accrue expenses on the first day of that month.</span></span> <span data-ttu-id="d632f-125">Cette convention de location garantit que les intérêts courent le dernier jour de chaque mois pendant tout le mois.</span><span class="sxs-lookup"><span data-stu-id="d632f-125">This leasing convention ensures that interest is accrued on the last day of each month for the whole month.</span></span> |

3. <span data-ttu-id="d632f-126">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d632f-126">Select **Save**.</span></span>

<span data-ttu-id="d632f-127">Lorsqu'un contrat de location est créé, la date de début de chaque registre est automatiquement saisie en fonction de la date de début qui est entrée pour le contrat de location et de la convention de location spécifiée pour le registre.</span><span class="sxs-lookup"><span data-stu-id="d632f-127">When a lease is created, the commencement date of each book is automatically entered based on the start date that is entered for the lease and the leasing convention that is specified for the book.</span></span>
