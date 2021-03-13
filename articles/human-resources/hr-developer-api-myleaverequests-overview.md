---
title: Vue d'ensemble de MyLeaveRequests
description: L'entité MyLeaveRequests dans Microsoft Dynamics 365 Human Resources fournit la liste des demandes de congé dans le système, étendue (limitée) aux demandes accessibles à l'utilisateur actuel interrogeant l'entité.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0ca5bc225400338e76faee41a279e91fc00ce570
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115534"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="f1681-103">Vue d'ensemble de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="f1681-103">MyLeaveRequests overview</span></span>

<span data-ttu-id="f1681-104">L'entité MyLeaveRequests dans Microsoft Dynamics 365 Human Resources fournit la liste des demandes de congé dans le système, étendue (limitée) aux demandes accessibles à l'utilisateur actuel interrogeant l'entité.</span><span class="sxs-lookup"><span data-stu-id="f1681-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="f1681-105">Clé</span><span class="sxs-lookup"><span data-stu-id="f1681-105">Key</span></span>

  | <span data-ttu-id="f1681-106">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="f1681-106">Property Name</span></span> | <span data-ttu-id="f1681-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="f1681-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="f1681-108">ID de zone de données</span><span class="sxs-lookup"><span data-stu-id="f1681-108">dataAreaId</span></span>    | <span data-ttu-id="f1681-109">Chaîne</span><span class="sxs-lookup"><span data-stu-id="f1681-109">String</span></span>    |
  | <span data-ttu-id="f1681-110">ID demande</span><span class="sxs-lookup"><span data-stu-id="f1681-110">RequestId</span></span>     | <span data-ttu-id="f1681-111">Chaîne</span><span class="sxs-lookup"><span data-stu-id="f1681-111">String</span></span>    |
  | <span data-ttu-id="f1681-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="f1681-112">LeaveType</span></span>     | <span data-ttu-id="f1681-113">Chaîne</span><span class="sxs-lookup"><span data-stu-id="f1681-113">String</span></span>    |
  | <span data-ttu-id="f1681-114">Date de congé</span><span class="sxs-lookup"><span data-stu-id="f1681-114">LeaveDate</span></span>     | <span data-ttu-id="f1681-115">Date</span><span class="sxs-lookup"><span data-stu-id="f1681-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="f1681-116">Propriétés</span><span class="sxs-lookup"><span data-stu-id="f1681-116">Properties</span></span>

  | <span data-ttu-id="f1681-117">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="f1681-117">Property Name</span></span>     | <span data-ttu-id="f1681-118">Type de données</span><span class="sxs-lookup"><span data-stu-id="f1681-118">Data Type</span></span> | <span data-ttu-id="f1681-119">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="f1681-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="f1681-120">ID de zone de données</span><span class="sxs-lookup"><span data-stu-id="f1681-120">dataAreaId</span></span>        | <span data-ttu-id="f1681-121">Chaîne</span><span class="sxs-lookup"><span data-stu-id="f1681-121">String</span></span>    | <span data-ttu-id="f1681-122">O</span><span class="sxs-lookup"><span data-stu-id="f1681-122">X</span></span>        |
  | <span data-ttu-id="f1681-123">ID demande</span><span class="sxs-lookup"><span data-stu-id="f1681-123">RequestId</span></span>         | <span data-ttu-id="f1681-124">Chaîne</span><span class="sxs-lookup"><span data-stu-id="f1681-124">String</span></span>    | <span data-ttu-id="f1681-125">O</span><span class="sxs-lookup"><span data-stu-id="f1681-125">X</span></span>        |
  | <span data-ttu-id="f1681-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="f1681-126">LeaveType</span></span>         | <span data-ttu-id="f1681-127">Chaîne</span><span class="sxs-lookup"><span data-stu-id="f1681-127">String</span></span>    | <span data-ttu-id="f1681-128">O</span><span class="sxs-lookup"><span data-stu-id="f1681-128">X</span></span>        |
  | <span data-ttu-id="f1681-129">Date de congé</span><span class="sxs-lookup"><span data-stu-id="f1681-129">LeaveDate</span></span>         | <span data-ttu-id="f1681-130">Date</span><span class="sxs-lookup"><span data-stu-id="f1681-130">Date</span></span>      | <span data-ttu-id="f1681-131">O</span><span class="sxs-lookup"><span data-stu-id="f1681-131">X</span></span>        |
  | <span data-ttu-id="f1681-132">ID code motif</span><span class="sxs-lookup"><span data-stu-id="f1681-132">ReasonCodeId</span></span>      | <span data-ttu-id="f1681-133">Chaîne</span><span class="sxs-lookup"><span data-stu-id="f1681-133">String</span></span>    |          |
  | <span data-ttu-id="f1681-134">Numéro personnel</span><span class="sxs-lookup"><span data-stu-id="f1681-134">PersonnelNumber</span></span>   | <span data-ttu-id="f1681-135">Chaîne</span><span class="sxs-lookup"><span data-stu-id="f1681-135">String</span></span>    | <span data-ttu-id="f1681-136">O</span><span class="sxs-lookup"><span data-stu-id="f1681-136">X</span></span>        |
  | <span data-ttu-id="f1681-137">Date de la demande</span><span class="sxs-lookup"><span data-stu-id="f1681-137">RequestDate</span></span>       | <span data-ttu-id="f1681-138">Date</span><span class="sxs-lookup"><span data-stu-id="f1681-138">Date</span></span>      | <span data-ttu-id="f1681-139">O</span><span class="sxs-lookup"><span data-stu-id="f1681-139">X</span></span>        |
  | <span data-ttu-id="f1681-140">Commentaire</span><span class="sxs-lookup"><span data-stu-id="f1681-140">Comment</span></span>           | <span data-ttu-id="f1681-141">Chaîne</span><span class="sxs-lookup"><span data-stu-id="f1681-141">String</span></span>    |          |
  | <span data-ttu-id="f1681-142">État </span><span class="sxs-lookup"><span data-stu-id="f1681-142">Status</span></span>            | <span data-ttu-id="f1681-143">Énumération</span><span class="sxs-lookup"><span data-stu-id="f1681-143">Enum</span></span>      | <span data-ttu-id="f1681-144">O</span><span class="sxs-lookup"><span data-stu-id="f1681-144">X</span></span>        |
  | <span data-ttu-id="f1681-145">Montant</span><span class="sxs-lookup"><span data-stu-id="f1681-145">Amount</span></span>            | <span data-ttu-id="f1681-146">Réel</span><span class="sxs-lookup"><span data-stu-id="f1681-146">Real</span></span>      |          |
  | <span data-ttu-id="f1681-147">Définition mi-journée</span><span class="sxs-lookup"><span data-stu-id="f1681-147">HalfDayDefinition</span></span> | <span data-ttu-id="f1681-148">Énumération</span><span class="sxs-lookup"><span data-stu-id="f1681-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="f1681-149">Actions</span><span class="sxs-lookup"><span data-stu-id="f1681-149">Actions</span></span>

 | <span data-ttu-id="f1681-150">Nom de l'action</span><span class="sxs-lookup"><span data-stu-id="f1681-150">Action Name</span></span>                               | <span data-ttu-id="f1681-151">Description</span><span class="sxs-lookup"><span data-stu-id="f1681-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="f1681-152">soumettre</span><span class="sxs-lookup"><span data-stu-id="f1681-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="f1681-153">Soumettez la demande à traiter par workflow.</span><span class="sxs-lookup"><span data-stu-id="f1681-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f1681-154">Voir également :</span><span class="sxs-lookup"><span data-stu-id="f1681-154">See also</span></span>

- [<span data-ttu-id="f1681-155">Soumettre une demande d'absence au workflow</span><span class="sxs-lookup"><span data-stu-id="f1681-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="f1681-156">Authentification</span><span class="sxs-lookup"><span data-stu-id="f1681-156">Authentication</span></span>](hr-developer-api-authentication.md)