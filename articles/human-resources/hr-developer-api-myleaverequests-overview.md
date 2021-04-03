---
title: Vue d’ensemble de MyLeaveRequests
description: L’entité MyLeaveRequests dans Microsoft Dynamics 365 Human Resources fournit la liste des demandes de congé dans le système, étendue (limitée) aux demandes accessibles à l’utilisateur actuel interrogeant l’entité.
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
ms.openlocfilehash: c2c14a0cc935ad166a2c6600f1e96c3e09ab16ca
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465508"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="19f6c-103">Vue d’ensemble de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="19f6c-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="19f6c-104">L’entité MyLeaveRequests dans Microsoft Dynamics 365 Human Resources fournit la liste des demandes de congé dans le système, étendue (limitée) aux demandes accessibles à l’utilisateur actuel interrogeant l’entité.</span><span class="sxs-lookup"><span data-stu-id="19f6c-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="19f6c-105">Clé</span><span class="sxs-lookup"><span data-stu-id="19f6c-105">Key</span></span>

  | <span data-ttu-id="19f6c-106">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="19f6c-106">Property Name</span></span> | <span data-ttu-id="19f6c-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="19f6c-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="19f6c-108">ID de zone de données</span><span class="sxs-lookup"><span data-stu-id="19f6c-108">dataAreaId</span></span>    | <span data-ttu-id="19f6c-109">Chaîne</span><span class="sxs-lookup"><span data-stu-id="19f6c-109">String</span></span>    |
  | <span data-ttu-id="19f6c-110">ID demande</span><span class="sxs-lookup"><span data-stu-id="19f6c-110">RequestId</span></span>     | <span data-ttu-id="19f6c-111">Chaîne</span><span class="sxs-lookup"><span data-stu-id="19f6c-111">String</span></span>    |
  | <span data-ttu-id="19f6c-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="19f6c-112">LeaveType</span></span>     | <span data-ttu-id="19f6c-113">Chaîne</span><span class="sxs-lookup"><span data-stu-id="19f6c-113">String</span></span>    |
  | <span data-ttu-id="19f6c-114">Date de congé</span><span class="sxs-lookup"><span data-stu-id="19f6c-114">LeaveDate</span></span>     | <span data-ttu-id="19f6c-115">Date</span><span class="sxs-lookup"><span data-stu-id="19f6c-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="19f6c-116">Propriétés</span><span class="sxs-lookup"><span data-stu-id="19f6c-116">Properties</span></span>

  | <span data-ttu-id="19f6c-117">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="19f6c-117">Property Name</span></span>     | <span data-ttu-id="19f6c-118">Type de données</span><span class="sxs-lookup"><span data-stu-id="19f6c-118">Data Type</span></span> | <span data-ttu-id="19f6c-119">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="19f6c-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="19f6c-120">ID de zone de données</span><span class="sxs-lookup"><span data-stu-id="19f6c-120">dataAreaId</span></span>        | <span data-ttu-id="19f6c-121">Chaîne</span><span class="sxs-lookup"><span data-stu-id="19f6c-121">String</span></span>    | <span data-ttu-id="19f6c-122">O</span><span class="sxs-lookup"><span data-stu-id="19f6c-122">X</span></span>        |
  | <span data-ttu-id="19f6c-123">ID demande</span><span class="sxs-lookup"><span data-stu-id="19f6c-123">RequestId</span></span>         | <span data-ttu-id="19f6c-124">Chaîne</span><span class="sxs-lookup"><span data-stu-id="19f6c-124">String</span></span>    | <span data-ttu-id="19f6c-125">O</span><span class="sxs-lookup"><span data-stu-id="19f6c-125">X</span></span>        |
  | <span data-ttu-id="19f6c-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="19f6c-126">LeaveType</span></span>         | <span data-ttu-id="19f6c-127">Chaîne</span><span class="sxs-lookup"><span data-stu-id="19f6c-127">String</span></span>    | <span data-ttu-id="19f6c-128">O</span><span class="sxs-lookup"><span data-stu-id="19f6c-128">X</span></span>        |
  | <span data-ttu-id="19f6c-129">Date de congé</span><span class="sxs-lookup"><span data-stu-id="19f6c-129">LeaveDate</span></span>         | <span data-ttu-id="19f6c-130">Date</span><span class="sxs-lookup"><span data-stu-id="19f6c-130">Date</span></span>      | <span data-ttu-id="19f6c-131">O</span><span class="sxs-lookup"><span data-stu-id="19f6c-131">X</span></span>        |
  | <span data-ttu-id="19f6c-132">ID code motif</span><span class="sxs-lookup"><span data-stu-id="19f6c-132">ReasonCodeId</span></span>      | <span data-ttu-id="19f6c-133">Chaîne</span><span class="sxs-lookup"><span data-stu-id="19f6c-133">String</span></span>    |          |
  | <span data-ttu-id="19f6c-134">Numéro personnel</span><span class="sxs-lookup"><span data-stu-id="19f6c-134">PersonnelNumber</span></span>   | <span data-ttu-id="19f6c-135">Chaîne</span><span class="sxs-lookup"><span data-stu-id="19f6c-135">String</span></span>    | <span data-ttu-id="19f6c-136">O</span><span class="sxs-lookup"><span data-stu-id="19f6c-136">X</span></span>        |
  | <span data-ttu-id="19f6c-137">Date de la demande</span><span class="sxs-lookup"><span data-stu-id="19f6c-137">RequestDate</span></span>       | <span data-ttu-id="19f6c-138">Date</span><span class="sxs-lookup"><span data-stu-id="19f6c-138">Date</span></span>      | <span data-ttu-id="19f6c-139">O</span><span class="sxs-lookup"><span data-stu-id="19f6c-139">X</span></span>        |
  | <span data-ttu-id="19f6c-140">Commentaire</span><span class="sxs-lookup"><span data-stu-id="19f6c-140">Comment</span></span>           | <span data-ttu-id="19f6c-141">Chaîne</span><span class="sxs-lookup"><span data-stu-id="19f6c-141">String</span></span>    |          |
  | <span data-ttu-id="19f6c-142">État </span><span class="sxs-lookup"><span data-stu-id="19f6c-142">Status</span></span>            | <span data-ttu-id="19f6c-143">Énumération</span><span class="sxs-lookup"><span data-stu-id="19f6c-143">Enum</span></span>      | <span data-ttu-id="19f6c-144">O</span><span class="sxs-lookup"><span data-stu-id="19f6c-144">X</span></span>        |
  | <span data-ttu-id="19f6c-145">Montant</span><span class="sxs-lookup"><span data-stu-id="19f6c-145">Amount</span></span>            | <span data-ttu-id="19f6c-146">Réel</span><span class="sxs-lookup"><span data-stu-id="19f6c-146">Real</span></span>      |          |
  | <span data-ttu-id="19f6c-147">Définition mi-journée</span><span class="sxs-lookup"><span data-stu-id="19f6c-147">HalfDayDefinition</span></span> | <span data-ttu-id="19f6c-148">Énumération</span><span class="sxs-lookup"><span data-stu-id="19f6c-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="19f6c-149">Actions</span><span class="sxs-lookup"><span data-stu-id="19f6c-149">Actions</span></span>

 | <span data-ttu-id="19f6c-150">Nom de l’action</span><span class="sxs-lookup"><span data-stu-id="19f6c-150">Action Name</span></span>                               | <span data-ttu-id="19f6c-151">Description</span><span class="sxs-lookup"><span data-stu-id="19f6c-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="19f6c-152">soumettre</span><span class="sxs-lookup"><span data-stu-id="19f6c-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="19f6c-153">Soumettez la demande à traiter par workflow.</span><span class="sxs-lookup"><span data-stu-id="19f6c-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="19f6c-154">Voir également :</span><span class="sxs-lookup"><span data-stu-id="19f6c-154">See also</span></span>

- [<span data-ttu-id="19f6c-155">Soumettre une demande d’absence au workflow</span><span class="sxs-lookup"><span data-stu-id="19f6c-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="19f6c-156">Authentification</span><span class="sxs-lookup"><span data-stu-id="19f6c-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]