---
title: Vue d'ensemble de MyLeaveRequests
description: ''
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
ms.openlocfilehash: 66f161d6736b1bb544d02871d9d51b2949b1cfa0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009011"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="28186-102">Vue d'ensemble de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="28186-102">MyLeaveRequests overview</span></span>

<span data-ttu-id="28186-103">L'entité MyLeaveRequests dans Microsoft Dynamics 365 Human Resources fournit la liste des demandes de congé dans le système, étendue (limitée) aux demandes accessibles à l'utilisateur actuel interrogeant l'entité.</span><span class="sxs-lookup"><span data-stu-id="28186-103">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="28186-104">Clé</span><span class="sxs-lookup"><span data-stu-id="28186-104">Key</span></span>

  | <span data-ttu-id="28186-105">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="28186-105">Property Name</span></span> | <span data-ttu-id="28186-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="28186-106">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="28186-107">ID de zone de données</span><span class="sxs-lookup"><span data-stu-id="28186-107">dataAreaId</span></span>    | <span data-ttu-id="28186-108">Chaîne</span><span class="sxs-lookup"><span data-stu-id="28186-108">String</span></span>    |
  | <span data-ttu-id="28186-109">ID demande</span><span class="sxs-lookup"><span data-stu-id="28186-109">RequestId</span></span>     | <span data-ttu-id="28186-110">Chaîne</span><span class="sxs-lookup"><span data-stu-id="28186-110">String</span></span>    |
  | <span data-ttu-id="28186-111">LeaveType</span><span class="sxs-lookup"><span data-stu-id="28186-111">LeaveType</span></span>     | <span data-ttu-id="28186-112">Chaîne</span><span class="sxs-lookup"><span data-stu-id="28186-112">String</span></span>    |
  | <span data-ttu-id="28186-113">Date de congé</span><span class="sxs-lookup"><span data-stu-id="28186-113">LeaveDate</span></span>     | <span data-ttu-id="28186-114">Date</span><span class="sxs-lookup"><span data-stu-id="28186-114">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="28186-115">Propriétés</span><span class="sxs-lookup"><span data-stu-id="28186-115">Properties</span></span>

  | <span data-ttu-id="28186-116">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="28186-116">Property Name</span></span>     | <span data-ttu-id="28186-117">Type de données</span><span class="sxs-lookup"><span data-stu-id="28186-117">Data Type</span></span> | <span data-ttu-id="28186-118">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="28186-118">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="28186-119">ID de zone de données</span><span class="sxs-lookup"><span data-stu-id="28186-119">dataAreaId</span></span>        | <span data-ttu-id="28186-120">Chaîne</span><span class="sxs-lookup"><span data-stu-id="28186-120">String</span></span>    | <span data-ttu-id="28186-121">O</span><span class="sxs-lookup"><span data-stu-id="28186-121">X</span></span>        |
  | <span data-ttu-id="28186-122">ID demande</span><span class="sxs-lookup"><span data-stu-id="28186-122">RequestId</span></span>         | <span data-ttu-id="28186-123">Chaîne</span><span class="sxs-lookup"><span data-stu-id="28186-123">String</span></span>    | <span data-ttu-id="28186-124">O</span><span class="sxs-lookup"><span data-stu-id="28186-124">X</span></span>        |
  | <span data-ttu-id="28186-125">LeaveType</span><span class="sxs-lookup"><span data-stu-id="28186-125">LeaveType</span></span>         | <span data-ttu-id="28186-126">Chaîne</span><span class="sxs-lookup"><span data-stu-id="28186-126">String</span></span>    | <span data-ttu-id="28186-127">O</span><span class="sxs-lookup"><span data-stu-id="28186-127">X</span></span>        |
  | <span data-ttu-id="28186-128">Date de congé</span><span class="sxs-lookup"><span data-stu-id="28186-128">LeaveDate</span></span>         | <span data-ttu-id="28186-129">Date</span><span class="sxs-lookup"><span data-stu-id="28186-129">Date</span></span>      | <span data-ttu-id="28186-130">O</span><span class="sxs-lookup"><span data-stu-id="28186-130">X</span></span>        |
  | <span data-ttu-id="28186-131">ID code motif</span><span class="sxs-lookup"><span data-stu-id="28186-131">ReasonCodeId</span></span>      | <span data-ttu-id="28186-132">Chaîne</span><span class="sxs-lookup"><span data-stu-id="28186-132">String</span></span>    |          |
  | <span data-ttu-id="28186-133">Numéro personnel</span><span class="sxs-lookup"><span data-stu-id="28186-133">PersonnelNumber</span></span>   | <span data-ttu-id="28186-134">Chaîne</span><span class="sxs-lookup"><span data-stu-id="28186-134">String</span></span>    | <span data-ttu-id="28186-135">O</span><span class="sxs-lookup"><span data-stu-id="28186-135">X</span></span>        |
  | <span data-ttu-id="28186-136">Date de la demande</span><span class="sxs-lookup"><span data-stu-id="28186-136">RequestDate</span></span>       | <span data-ttu-id="28186-137">Date</span><span class="sxs-lookup"><span data-stu-id="28186-137">Date</span></span>      | <span data-ttu-id="28186-138">O</span><span class="sxs-lookup"><span data-stu-id="28186-138">X</span></span>        |
  | <span data-ttu-id="28186-139">Commentaire</span><span class="sxs-lookup"><span data-stu-id="28186-139">Comment</span></span>           | <span data-ttu-id="28186-140">Chaîne</span><span class="sxs-lookup"><span data-stu-id="28186-140">String</span></span>    |          |
  | <span data-ttu-id="28186-141">État </span><span class="sxs-lookup"><span data-stu-id="28186-141">Status</span></span>            | <span data-ttu-id="28186-142">Énumération</span><span class="sxs-lookup"><span data-stu-id="28186-142">Enum</span></span>      | <span data-ttu-id="28186-143">O</span><span class="sxs-lookup"><span data-stu-id="28186-143">X</span></span>        |
  | <span data-ttu-id="28186-144">Montant</span><span class="sxs-lookup"><span data-stu-id="28186-144">Amount</span></span>            | <span data-ttu-id="28186-145">Réel</span><span class="sxs-lookup"><span data-stu-id="28186-145">Real</span></span>      |          |
  | <span data-ttu-id="28186-146">Définition mi-journée</span><span class="sxs-lookup"><span data-stu-id="28186-146">HalfDayDefinition</span></span> | <span data-ttu-id="28186-147">Énumération</span><span class="sxs-lookup"><span data-stu-id="28186-147">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="28186-148">Actions</span><span class="sxs-lookup"><span data-stu-id="28186-148">Actions</span></span>

 | <span data-ttu-id="28186-149">Nom de l'action</span><span class="sxs-lookup"><span data-stu-id="28186-149">Action Name</span></span>                               | <span data-ttu-id="28186-150">Description</span><span class="sxs-lookup"><span data-stu-id="28186-150">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="28186-151">soumettre</span><span class="sxs-lookup"><span data-stu-id="28186-151">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="28186-152">Soumettez la demande à traiter par workflow.</span><span class="sxs-lookup"><span data-stu-id="28186-152">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="28186-153">Voir également :</span><span class="sxs-lookup"><span data-stu-id="28186-153">See also</span></span>

- [<span data-ttu-id="28186-154">Soumettre une demande d'absence au workflow</span><span class="sxs-lookup"><span data-stu-id="28186-154">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="28186-155">Authentification</span><span class="sxs-lookup"><span data-stu-id="28186-155">Authentication</span></span>](hr-developer-api-authentication.md)