---
title: Vue d’ensemble de MyLeaveRequests
description: L’entité MyLeaveRequests dans Microsoft Dynamics 365 Human Resources fournit la liste des demandes de congé dans le système, étendue (limitée) aux demandes accessibles à l’utilisateur actuel interrogeant l’entité.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 44e23a076733bac782a0366aeba3456911522abe
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803631"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="15bc6-103">Vue d’ensemble de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="15bc6-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="15bc6-104">L’entité MyLeaveRequests dans Microsoft Dynamics 365 Human Resources fournit la liste des demandes de congé dans le système, étendue (limitée) aux demandes accessibles à l’utilisateur actuel interrogeant l’entité.</span><span class="sxs-lookup"><span data-stu-id="15bc6-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="15bc6-105">Clé</span><span class="sxs-lookup"><span data-stu-id="15bc6-105">Key</span></span>

  | <span data-ttu-id="15bc6-106">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="15bc6-106">Property Name</span></span> | <span data-ttu-id="15bc6-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="15bc6-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="15bc6-108">ID de zone de données</span><span class="sxs-lookup"><span data-stu-id="15bc6-108">dataAreaId</span></span>    | <span data-ttu-id="15bc6-109">Chaîne</span><span class="sxs-lookup"><span data-stu-id="15bc6-109">String</span></span>    |
  | <span data-ttu-id="15bc6-110">ID demande</span><span class="sxs-lookup"><span data-stu-id="15bc6-110">RequestId</span></span>     | <span data-ttu-id="15bc6-111">Chaîne</span><span class="sxs-lookup"><span data-stu-id="15bc6-111">String</span></span>    |
  | <span data-ttu-id="15bc6-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="15bc6-112">LeaveType</span></span>     | <span data-ttu-id="15bc6-113">Chaîne</span><span class="sxs-lookup"><span data-stu-id="15bc6-113">String</span></span>    |
  | <span data-ttu-id="15bc6-114">Date de congé</span><span class="sxs-lookup"><span data-stu-id="15bc6-114">LeaveDate</span></span>     | <span data-ttu-id="15bc6-115">Date</span><span class="sxs-lookup"><span data-stu-id="15bc6-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="15bc6-116">Propriétés</span><span class="sxs-lookup"><span data-stu-id="15bc6-116">Properties</span></span>

  | <span data-ttu-id="15bc6-117">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="15bc6-117">Property Name</span></span>     | <span data-ttu-id="15bc6-118">Type de données</span><span class="sxs-lookup"><span data-stu-id="15bc6-118">Data Type</span></span> | <span data-ttu-id="15bc6-119">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="15bc6-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="15bc6-120">ID de zone de données</span><span class="sxs-lookup"><span data-stu-id="15bc6-120">dataAreaId</span></span>        | <span data-ttu-id="15bc6-121">Chaîne</span><span class="sxs-lookup"><span data-stu-id="15bc6-121">String</span></span>    | <span data-ttu-id="15bc6-122">O</span><span class="sxs-lookup"><span data-stu-id="15bc6-122">X</span></span>        |
  | <span data-ttu-id="15bc6-123">ID demande</span><span class="sxs-lookup"><span data-stu-id="15bc6-123">RequestId</span></span>         | <span data-ttu-id="15bc6-124">Chaîne</span><span class="sxs-lookup"><span data-stu-id="15bc6-124">String</span></span>    | <span data-ttu-id="15bc6-125">O</span><span class="sxs-lookup"><span data-stu-id="15bc6-125">X</span></span>        |
  | <span data-ttu-id="15bc6-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="15bc6-126">LeaveType</span></span>         | <span data-ttu-id="15bc6-127">Chaîne</span><span class="sxs-lookup"><span data-stu-id="15bc6-127">String</span></span>    | <span data-ttu-id="15bc6-128">O</span><span class="sxs-lookup"><span data-stu-id="15bc6-128">X</span></span>        |
  | <span data-ttu-id="15bc6-129">Date de congé</span><span class="sxs-lookup"><span data-stu-id="15bc6-129">LeaveDate</span></span>         | <span data-ttu-id="15bc6-130">Date</span><span class="sxs-lookup"><span data-stu-id="15bc6-130">Date</span></span>      | <span data-ttu-id="15bc6-131">O</span><span class="sxs-lookup"><span data-stu-id="15bc6-131">X</span></span>        |
  | <span data-ttu-id="15bc6-132">ID code motif</span><span class="sxs-lookup"><span data-stu-id="15bc6-132">ReasonCodeId</span></span>      | <span data-ttu-id="15bc6-133">Chaîne</span><span class="sxs-lookup"><span data-stu-id="15bc6-133">String</span></span>    |          |
  | <span data-ttu-id="15bc6-134">Numéro personnel</span><span class="sxs-lookup"><span data-stu-id="15bc6-134">PersonnelNumber</span></span>   | <span data-ttu-id="15bc6-135">Chaîne</span><span class="sxs-lookup"><span data-stu-id="15bc6-135">String</span></span>    | <span data-ttu-id="15bc6-136">O</span><span class="sxs-lookup"><span data-stu-id="15bc6-136">X</span></span>        |
  | <span data-ttu-id="15bc6-137">Date de la demande</span><span class="sxs-lookup"><span data-stu-id="15bc6-137">RequestDate</span></span>       | <span data-ttu-id="15bc6-138">Date</span><span class="sxs-lookup"><span data-stu-id="15bc6-138">Date</span></span>      | <span data-ttu-id="15bc6-139">O</span><span class="sxs-lookup"><span data-stu-id="15bc6-139">X</span></span>        |
  | <span data-ttu-id="15bc6-140">Commentaire</span><span class="sxs-lookup"><span data-stu-id="15bc6-140">Comment</span></span>           | <span data-ttu-id="15bc6-141">Chaîne</span><span class="sxs-lookup"><span data-stu-id="15bc6-141">String</span></span>    |          |
  | <span data-ttu-id="15bc6-142">Statut</span><span class="sxs-lookup"><span data-stu-id="15bc6-142">Status</span></span>            | <span data-ttu-id="15bc6-143">Énumération</span><span class="sxs-lookup"><span data-stu-id="15bc6-143">Enum</span></span>      | <span data-ttu-id="15bc6-144">O</span><span class="sxs-lookup"><span data-stu-id="15bc6-144">X</span></span>        |
  | <span data-ttu-id="15bc6-145">Montant</span><span class="sxs-lookup"><span data-stu-id="15bc6-145">Amount</span></span>            | <span data-ttu-id="15bc6-146">Réel</span><span class="sxs-lookup"><span data-stu-id="15bc6-146">Real</span></span>      |          |
  | <span data-ttu-id="15bc6-147">Définition mi-journée</span><span class="sxs-lookup"><span data-stu-id="15bc6-147">HalfDayDefinition</span></span> | <span data-ttu-id="15bc6-148">Énumération</span><span class="sxs-lookup"><span data-stu-id="15bc6-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="15bc6-149">Actions</span><span class="sxs-lookup"><span data-stu-id="15bc6-149">Actions</span></span>

 | <span data-ttu-id="15bc6-150">Nom de l’action</span><span class="sxs-lookup"><span data-stu-id="15bc6-150">Action Name</span></span>                               | <span data-ttu-id="15bc6-151">Description</span><span class="sxs-lookup"><span data-stu-id="15bc6-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="15bc6-152">soumettre</span><span class="sxs-lookup"><span data-stu-id="15bc6-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="15bc6-153">Soumettez la demande à traiter par workflow.</span><span class="sxs-lookup"><span data-stu-id="15bc6-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="15bc6-154">Voir également :</span><span class="sxs-lookup"><span data-stu-id="15bc6-154">See also</span></span>

- [<span data-ttu-id="15bc6-155">Soumettre une demande d’absence au workflow</span><span class="sxs-lookup"><span data-stu-id="15bc6-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="15bc6-156">Authentification</span><span class="sxs-lookup"><span data-stu-id="15bc6-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]