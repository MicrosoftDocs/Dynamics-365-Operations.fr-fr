---
title: Vue d'ensemble de MyLeaveRequests
description: L'entité MyLeaveRequests dans Microsoft Dynamics 365 Human Resources fournit la liste des demandes de congé dans le système, étendue (limitée) aux demandes accessibles à l'utilisateur actuel interrogeant l'entité.
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: 4bf3b298af9eb39e03514a4005afb43a42908e47
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418433"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="004d5-103">Vue d'ensemble de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="004d5-103">MyLeaveRequests overview</span></span>

<span data-ttu-id="004d5-104">L'entité MyLeaveRequests dans Microsoft Dynamics 365 Human Resources fournit la liste des demandes de congé dans le système, étendue (limitée) aux demandes accessibles à l'utilisateur actuel interrogeant l'entité.</span><span class="sxs-lookup"><span data-stu-id="004d5-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="004d5-105">Clé</span><span class="sxs-lookup"><span data-stu-id="004d5-105">Key</span></span>

  | <span data-ttu-id="004d5-106">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="004d5-106">Property Name</span></span> | <span data-ttu-id="004d5-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="004d5-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="004d5-108">ID de zone de données</span><span class="sxs-lookup"><span data-stu-id="004d5-108">dataAreaId</span></span>    | <span data-ttu-id="004d5-109">Chaîne</span><span class="sxs-lookup"><span data-stu-id="004d5-109">String</span></span>    |
  | <span data-ttu-id="004d5-110">ID demande</span><span class="sxs-lookup"><span data-stu-id="004d5-110">RequestId</span></span>     | <span data-ttu-id="004d5-111">Chaîne</span><span class="sxs-lookup"><span data-stu-id="004d5-111">String</span></span>    |
  | <span data-ttu-id="004d5-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="004d5-112">LeaveType</span></span>     | <span data-ttu-id="004d5-113">Chaîne</span><span class="sxs-lookup"><span data-stu-id="004d5-113">String</span></span>    |
  | <span data-ttu-id="004d5-114">Date de congé</span><span class="sxs-lookup"><span data-stu-id="004d5-114">LeaveDate</span></span>     | <span data-ttu-id="004d5-115">Date</span><span class="sxs-lookup"><span data-stu-id="004d5-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="004d5-116">Propriétés</span><span class="sxs-lookup"><span data-stu-id="004d5-116">Properties</span></span>

  | <span data-ttu-id="004d5-117">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="004d5-117">Property Name</span></span>     | <span data-ttu-id="004d5-118">Type de données</span><span class="sxs-lookup"><span data-stu-id="004d5-118">Data Type</span></span> | <span data-ttu-id="004d5-119">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="004d5-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="004d5-120">ID de zone de données</span><span class="sxs-lookup"><span data-stu-id="004d5-120">dataAreaId</span></span>        | <span data-ttu-id="004d5-121">Chaîne</span><span class="sxs-lookup"><span data-stu-id="004d5-121">String</span></span>    | <span data-ttu-id="004d5-122">O</span><span class="sxs-lookup"><span data-stu-id="004d5-122">X</span></span>        |
  | <span data-ttu-id="004d5-123">ID demande</span><span class="sxs-lookup"><span data-stu-id="004d5-123">RequestId</span></span>         | <span data-ttu-id="004d5-124">Chaîne</span><span class="sxs-lookup"><span data-stu-id="004d5-124">String</span></span>    | <span data-ttu-id="004d5-125">O</span><span class="sxs-lookup"><span data-stu-id="004d5-125">X</span></span>        |
  | <span data-ttu-id="004d5-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="004d5-126">LeaveType</span></span>         | <span data-ttu-id="004d5-127">Chaîne</span><span class="sxs-lookup"><span data-stu-id="004d5-127">String</span></span>    | <span data-ttu-id="004d5-128">O</span><span class="sxs-lookup"><span data-stu-id="004d5-128">X</span></span>        |
  | <span data-ttu-id="004d5-129">Date de congé</span><span class="sxs-lookup"><span data-stu-id="004d5-129">LeaveDate</span></span>         | <span data-ttu-id="004d5-130">Date</span><span class="sxs-lookup"><span data-stu-id="004d5-130">Date</span></span>      | <span data-ttu-id="004d5-131">O</span><span class="sxs-lookup"><span data-stu-id="004d5-131">X</span></span>        |
  | <span data-ttu-id="004d5-132">ID code motif</span><span class="sxs-lookup"><span data-stu-id="004d5-132">ReasonCodeId</span></span>      | <span data-ttu-id="004d5-133">Chaîne</span><span class="sxs-lookup"><span data-stu-id="004d5-133">String</span></span>    |          |
  | <span data-ttu-id="004d5-134">Numéro personnel</span><span class="sxs-lookup"><span data-stu-id="004d5-134">PersonnelNumber</span></span>   | <span data-ttu-id="004d5-135">Chaîne</span><span class="sxs-lookup"><span data-stu-id="004d5-135">String</span></span>    | <span data-ttu-id="004d5-136">O</span><span class="sxs-lookup"><span data-stu-id="004d5-136">X</span></span>        |
  | <span data-ttu-id="004d5-137">Date de la demande</span><span class="sxs-lookup"><span data-stu-id="004d5-137">RequestDate</span></span>       | <span data-ttu-id="004d5-138">Date</span><span class="sxs-lookup"><span data-stu-id="004d5-138">Date</span></span>      | <span data-ttu-id="004d5-139">O</span><span class="sxs-lookup"><span data-stu-id="004d5-139">X</span></span>        |
  | <span data-ttu-id="004d5-140">Commentaire</span><span class="sxs-lookup"><span data-stu-id="004d5-140">Comment</span></span>           | <span data-ttu-id="004d5-141">Chaîne</span><span class="sxs-lookup"><span data-stu-id="004d5-141">String</span></span>    |          |
  | <span data-ttu-id="004d5-142">État </span><span class="sxs-lookup"><span data-stu-id="004d5-142">Status</span></span>            | <span data-ttu-id="004d5-143">Énumération</span><span class="sxs-lookup"><span data-stu-id="004d5-143">Enum</span></span>      | <span data-ttu-id="004d5-144">O</span><span class="sxs-lookup"><span data-stu-id="004d5-144">X</span></span>        |
  | <span data-ttu-id="004d5-145">Montant</span><span class="sxs-lookup"><span data-stu-id="004d5-145">Amount</span></span>            | <span data-ttu-id="004d5-146">Réel</span><span class="sxs-lookup"><span data-stu-id="004d5-146">Real</span></span>      |          |
  | <span data-ttu-id="004d5-147">Définition mi-journée</span><span class="sxs-lookup"><span data-stu-id="004d5-147">HalfDayDefinition</span></span> | <span data-ttu-id="004d5-148">Énumération</span><span class="sxs-lookup"><span data-stu-id="004d5-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="004d5-149">Actions</span><span class="sxs-lookup"><span data-stu-id="004d5-149">Actions</span></span>

 | <span data-ttu-id="004d5-150">Nom de l'action</span><span class="sxs-lookup"><span data-stu-id="004d5-150">Action Name</span></span>                               | <span data-ttu-id="004d5-151">Description</span><span class="sxs-lookup"><span data-stu-id="004d5-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="004d5-152">soumettre</span><span class="sxs-lookup"><span data-stu-id="004d5-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="004d5-153">Soumettez la demande à traiter par workflow.</span><span class="sxs-lookup"><span data-stu-id="004d5-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="004d5-154">Voir également :</span><span class="sxs-lookup"><span data-stu-id="004d5-154">See also</span></span>

- [<span data-ttu-id="004d5-155">Soumettre une demande d'absence au workflow</span><span class="sxs-lookup"><span data-stu-id="004d5-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="004d5-156">Authentification</span><span class="sxs-lookup"><span data-stu-id="004d5-156">Authentication</span></span>](hr-developer-api-authentication.md)