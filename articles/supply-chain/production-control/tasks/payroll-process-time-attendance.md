---
title: Activer le processus de paie pour le pointage
description: Cette procédure décrit comment activer le processus de paie pour le pointage.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgPayTable, JmgPayRate, JmgPayAgreementTable, JmgPayAgreementLine, HcmWorker
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0174f438396d814d153befe4a59a79b6eebb2288
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "311103"
---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a><span data-ttu-id="975a8-103">Activer le processus de paie pour le pointage</span><span class="sxs-lookup"><span data-stu-id="975a8-103">Enable the payroll process for time and attendance</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="975a8-104">Cette procédure décrit comment activer le processus de paie pour le pointage.</span><span class="sxs-lookup"><span data-stu-id="975a8-104">This procedure shows how to enable the payroll process for time and attendance.</span></span> <span data-ttu-id="975a8-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="975a8-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-pay-type-with-a-related-pay-rate"></a><span data-ttu-id="975a8-106">Créer un type de salaire avec un taux de salaire associé</span><span class="sxs-lookup"><span data-stu-id="975a8-106">Create a pay type with a related pay rate</span></span>
1. <span data-ttu-id="975a8-107">Pointage > Paramétrage > Paie > Types de salaire</span><span class="sxs-lookup"><span data-stu-id="975a8-107">Time and attendance > Setup > Payroll > Pay types</span></span>
2. <span data-ttu-id="975a8-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="975a8-108">Click New.</span></span>
3. <span data-ttu-id="975a8-109">Tapez une valeur dans le champ Type de paie.</span><span class="sxs-lookup"><span data-stu-id="975a8-109">In the Pay type field, type a value.</span></span>
4. <span data-ttu-id="975a8-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="975a8-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="975a8-111">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="975a8-111">Click Save.</span></span>
6. <span data-ttu-id="975a8-112">Cliquez sur Taux.</span><span class="sxs-lookup"><span data-stu-id="975a8-112">Click Rates.</span></span>
    * <span data-ttu-id="975a8-113">Les taux pour les types de paie sont paramétrés pour des intervalles de temps spécifiques, et il est possible de créer des taux individuels pour les travailleurs.</span><span class="sxs-lookup"><span data-stu-id="975a8-113">Rates for pay types are set up for specific time intervals, and individual rates can be created for workers.</span></span> <span data-ttu-id="975a8-114">Il n'est pas toujours nécessaire de créer des taux pour les types de paie dans le module Pointage.</span><span class="sxs-lookup"><span data-stu-id="975a8-114">It is not always necessary to create rates for pay types in time and attendance.</span></span> <span data-ttu-id="975a8-115">Ces informations sont peut-être déjà présentes dans le système de paie utilisé pour générer les salaires.</span><span class="sxs-lookup"><span data-stu-id="975a8-115">This information may already exist in the payroll system that is used to generate wages.</span></span>  
7. <span data-ttu-id="975a8-116">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="975a8-116">Click New.</span></span>
8. <span data-ttu-id="975a8-117">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="975a8-117">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="975a8-118">Entrez un nombre dans le champ Taux.</span><span class="sxs-lookup"><span data-stu-id="975a8-118">In the Rate field, enter a number.</span></span>
10. <span data-ttu-id="975a8-119">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="975a8-119">Click Save.</span></span>

## <a name="create-a-pay-agreement"></a><span data-ttu-id="975a8-120">Création d'un accord salarial</span><span class="sxs-lookup"><span data-stu-id="975a8-120">Create a pay agreement</span></span>
1. <span data-ttu-id="975a8-121">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="975a8-121">Close the page.</span></span>
2. <span data-ttu-id="975a8-122">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="975a8-122">Close the page.</span></span>
3. <span data-ttu-id="975a8-123">Allez dans Accords salariaux.</span><span class="sxs-lookup"><span data-stu-id="975a8-123">Go to Pay agreements.</span></span>
    * <span data-ttu-id="975a8-124">Pointage > Paramétrage > Accords salariaux</span><span class="sxs-lookup"><span data-stu-id="975a8-124">Time and attendance > Setup > Pay agreements</span></span>  
4. <span data-ttu-id="975a8-125">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="975a8-125">Click New.</span></span>
5. <span data-ttu-id="975a8-126">Tapez une valeur dans le champ Accord salarial.</span><span class="sxs-lookup"><span data-stu-id="975a8-126">In the Pay agreement field, type a value.</span></span>
6. <span data-ttu-id="975a8-127">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="975a8-127">In the Description field, type a value.</span></span>
7. <span data-ttu-id="975a8-128">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="975a8-128">Click Save.</span></span>
8. <span data-ttu-id="975a8-129">Cliquez sur Lignes d'accord.</span><span class="sxs-lookup"><span data-stu-id="975a8-129">Click Agreement lines.</span></span>
9. <span data-ttu-id="975a8-130">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="975a8-130">Click New.</span></span>
10. <span data-ttu-id="975a8-131">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="975a8-131">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="975a8-132">Saisissez ou sélectionnez une valeur dans le champ Type de profil.</span><span class="sxs-lookup"><span data-stu-id="975a8-132">In the Profile type field, enter or select a value.</span></span>
12. <span data-ttu-id="975a8-133">Saisissez ou sélectionnez une valeur dans le champ Type de paie.</span><span class="sxs-lookup"><span data-stu-id="975a8-133">In the Pay type field, enter or select a value.</span></span>

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a><span data-ttu-id="975a8-134">Paramétrer un accord salarial pour le collaborateur qualifié pour l'enregistrement des heures</span><span class="sxs-lookup"><span data-stu-id="975a8-134">Set up pay agreement for time and registration worker</span></span>
1. <span data-ttu-id="975a8-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="975a8-135">Close the page.</span></span>
2. <span data-ttu-id="975a8-136">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="975a8-136">Close the page.</span></span>
3. <span data-ttu-id="975a8-137">Allez dans Enregistrement du temps des collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="975a8-137">Go to Time registration workers.</span></span>
    * <span data-ttu-id="975a8-138">Pointage > Paramétrage > Enregistrement du temps des collaborateurs</span><span class="sxs-lookup"><span data-stu-id="975a8-138">Time and attendance > Setup > Time registration workers</span></span>  
4. <span data-ttu-id="975a8-139">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="975a8-139">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="975a8-140">Cliquez sur l'onglet Emploi.</span><span class="sxs-lookup"><span data-stu-id="975a8-140">Click the Employment tab.</span></span>
6. <span data-ttu-id="975a8-141">Développez la section Enregistrement du temps.</span><span class="sxs-lookup"><span data-stu-id="975a8-141">Expand the Time registration section.</span></span>
7. <span data-ttu-id="975a8-142">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="975a8-142">Click Edit.</span></span>
8. <span data-ttu-id="975a8-143">Saisissez ou sélectionnez une valeur dans le champ Accord salarial.</span><span class="sxs-lookup"><span data-stu-id="975a8-143">In the Pay agreement field, enter or select a value.</span></span>

