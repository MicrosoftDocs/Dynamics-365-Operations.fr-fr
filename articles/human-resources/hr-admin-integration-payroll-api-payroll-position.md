---
title: Détails de la paie pour les postes
description: Cette rubrique fournit des détails et un exemple de requête pour l’entité Détails de la paie pour les postes dans Dynamics 365 Human Resources.
author: jcart
manager: tfehr
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f6c4bb0e2f4521e8c870f6c4fb645e2ce506138c
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881980"
---
# <a name="payroll-position"></a><span data-ttu-id="b1606-103">Poste de paie</span><span class="sxs-lookup"><span data-stu-id="b1606-103">Payroll position</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b1606-104">Cette rubrique fournit des détails et un exemple de requête pour l’entité Détails de la paie pour les postes dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b1606-104">This topic provides details and an example query for the Payroll details for the Positions entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="b1606-105">Propriétés</span><span class="sxs-lookup"><span data-stu-id="b1606-105">Properties</span></span>

| <span data-ttu-id="b1606-106">Propriété</span><span class="sxs-lookup"><span data-stu-id="b1606-106">Property</span></span><br><span data-ttu-id="b1606-107">**Nom physique**</span><span class="sxs-lookup"><span data-stu-id="b1606-107">**Physical name**</span></span><br><span data-ttu-id="b1606-108">**_Type_**</span><span class="sxs-lookup"><span data-stu-id="b1606-108">**_Type_**</span></span> | <span data-ttu-id="b1606-109">Cas d’emploi</span><span class="sxs-lookup"><span data-stu-id="b1606-109">Use</span></span> | <span data-ttu-id="b1606-110">Description</span><span class="sxs-lookup"><span data-stu-id="b1606-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="b1606-111">**Durée annuelle normale**</span><span class="sxs-lookup"><span data-stu-id="b1606-111">**Annual regular hours**</span></span><br><span data-ttu-id="b1606-112">annualregularhours</span><span class="sxs-lookup"><span data-stu-id="b1606-112">annualregularhours</span></span><br><span data-ttu-id="b1606-113">*Décimal*</span><span class="sxs-lookup"><span data-stu-id="b1606-113">*Decimal*</span></span> | <span data-ttu-id="b1606-114">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="b1606-114">Read-only</span></span><br><span data-ttu-id="b1606-115">Requis</span><span class="sxs-lookup"><span data-stu-id="b1606-115">Required</span></span> | <span data-ttu-id="b1606-116">Heures normales annuelles définies sur le poste.</span><span class="sxs-lookup"><span data-stu-id="b1606-116">Annual regular hours defined on the position.</span></span>  |
| <span data-ttu-id="b1606-117">**ID de l'entité Détails du poste de paie**</span><span class="sxs-lookup"><span data-stu-id="b1606-117">**Payroll position details entity ID**</span></span><br><span data-ttu-id="b1606-118">payrollpositiondetailsentityid</span><span class="sxs-lookup"><span data-stu-id="b1606-118">payrollpositiondetailsentityid</span></span><br><span data-ttu-id="b1606-119">*Guid*</span><span class="sxs-lookup"><span data-stu-id="b1606-119">*Guid*</span></span> | <span data-ttu-id="b1606-120">Requis</span><span class="sxs-lookup"><span data-stu-id="b1606-120">Required</span></span><br><span data-ttu-id="b1606-121">Généré par le système.</span><span class="sxs-lookup"><span data-stu-id="b1606-121">System generated.</span></span> | <span data-ttu-id="b1606-122">Valeur GUID générée par le système pour identifier le poste de manière unique.</span><span class="sxs-lookup"><span data-stu-id="b1606-122">A system-generated GUID value to uniquely identify the position.</span></span>  |
| <span data-ttu-id="b1606-123">**Champ principal**</span><span class="sxs-lookup"><span data-stu-id="b1606-123">**Primary field**</span></span><br><span data-ttu-id="b1606-124">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="b1606-124">mshr_primaryfield</span></span><br><span data-ttu-id="b1606-125">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="b1606-125">*String*</span></span> | <span data-ttu-id="b1606-126">Requis</span><span class="sxs-lookup"><span data-stu-id="b1606-126">Required</span></span><br><span data-ttu-id="b1606-127">Généré par le système</span><span class="sxs-lookup"><span data-stu-id="b1606-127">System generated</span></span> |  |
| <span data-ttu-id="b1606-128">**Valeur d’ID du poste**</span><span class="sxs-lookup"><span data-stu-id="b1606-128">**Position job ID value**</span></span><br><span data-ttu-id="b1606-129">_mshr_fk_positionjob_id_value</span><span class="sxs-lookup"><span data-stu-id="b1606-129">_mshr_fk_positionjob_id_value</span></span><br><span data-ttu-id="b1606-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="b1606-130">*GUID*</span></span> | <span data-ttu-id="b1606-131">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="b1606-131">Read-only</span></span><br><span data-ttu-id="b1606-132">Requis</span><span class="sxs-lookup"><span data-stu-id="b1606-132">Required</span></span><br><span data-ttu-id="b1606-133">Clé étrangère : mshr_PayrollPositionJobEntity de mshr_payrollpositionjobentity</span><span class="sxs-lookup"><span data-stu-id="b1606-133">Foreign key:mshr_PayrollPositionJobEntity of the mshr_payrollpositionjobentity</span></span> |<span data-ttu-id="b1606-134">ID du travail associé au poste.</span><span class="sxs-lookup"><span data-stu-id="b1606-134">The ID of the job associated with the position.</span></span>|
| <span data-ttu-id="b1606-135">**Valeur de l'ID du régime de rémunération fixe**</span><span class="sxs-lookup"><span data-stu-id="b1606-135">**Fixed compensation plan ID value**</span></span><br><span data-ttu-id="b1606-136">_mshr_fk_fixedcompplan_id_value</span><span class="sxs-lookup"><span data-stu-id="b1606-136">_mshr_fk_fixedcompplan_id_value</span></span><br><span data-ttu-id="b1606-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="b1606-137">*GUID*</span></span> | <span data-ttu-id="b1606-138">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="b1606-138">Read-only</span></span><br><span data-ttu-id="b1606-139">Requis</span><span class="sxs-lookup"><span data-stu-id="b1606-139">Required</span></span><br><span data-ttu-id="b1606-140">Clé étrangère : mshr_FixedCompPlan_id de mshr_payrollfixedcompensationplanentity</span><span class="sxs-lookup"><span data-stu-id="b1606-140">Foreign key: mshr_FixedCompPlan_id of mshr_payrollfixedcompensationplanentity</span></span>  | <span data-ttu-id="b1606-141">ID du régime de rémunération fixe associé au poste.</span><span class="sxs-lookup"><span data-stu-id="b1606-141">The ID of the fixed compensation plan associated with the position.</span></span> |
| <span data-ttu-id="b1606-142">**ID du cycle de paie**</span><span class="sxs-lookup"><span data-stu-id="b1606-142">**Pay cycle ID**</span></span><br><span data-ttu-id="b1606-143">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="b1606-143">mshr_primaryfield</span></span><br><span data-ttu-id="b1606-144">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="b1606-144">*String*</span></span> | <span data-ttu-id="b1606-145">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="b1606-145">Read-only</span></span><br><span data-ttu-id="b1606-146">Requis</span><span class="sxs-lookup"><span data-stu-id="b1606-146">Required</span></span> | <span data-ttu-id="b1606-147">Le cycle de paie défini sur le poste.</span><span class="sxs-lookup"><span data-stu-id="b1606-147">The pay cycle defined on the position.</span></span> |
| <span data-ttu-id="b1606-148">**Rémunéré par l’entité juridique**</span><span class="sxs-lookup"><span data-stu-id="b1606-148">**Paid by legal entity**</span></span><br><span data-ttu-id="b1606-149">paidbylegalentity</span><span class="sxs-lookup"><span data-stu-id="b1606-149">paidbylegalentity</span></span><br><span data-ttu-id="b1606-150">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="b1606-150">*String*</span></span> | <span data-ttu-id="b1606-151">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="b1606-151">Read-only</span></span><br><span data-ttu-id="b1606-152">Requis</span><span class="sxs-lookup"><span data-stu-id="b1606-152">Required</span></span> | <span data-ttu-id="b1606-153">L'entité juridique définie sur le poste, responsable de l'émission du paiement.</span><span class="sxs-lookup"><span data-stu-id="b1606-153">The legal entity defined on the positoin responsible for issuing payment.</span></span> |
| <span data-ttu-id="b1606-154">**ID poste**</span><span class="sxs-lookup"><span data-stu-id="b1606-154">**Position ID**</span></span><br><span data-ttu-id="b1606-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="b1606-155">mshr_positionid</span></span><br><span data-ttu-id="b1606-156">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="b1606-156">*String*</span></span> | <span data-ttu-id="b1606-157">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="b1606-157">Read-only</span></span><br><span data-ttu-id="b1606-158">Requis</span><span class="sxs-lookup"><span data-stu-id="b1606-158">Required</span></span> | <span data-ttu-id="b1606-159">ID du poste.</span><span class="sxs-lookup"><span data-stu-id="b1606-159">The ID of the position.</span></span> |
| <span data-ttu-id="b1606-160">**Valide jusqu’au**</span><span class="sxs-lookup"><span data-stu-id="b1606-160">**Valid to**</span></span><br><span data-ttu-id="b1606-161">validto</span><span class="sxs-lookup"><span data-stu-id="b1606-161">validto</span></span><br><span data-ttu-id="b1606-162">*Décalage de date et heure*</span><span class="sxs-lookup"><span data-stu-id="b1606-162">*Date Time Offset*</span></span> | <span data-ttu-id="b1606-163">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="b1606-163">Read-only</span></span><br><span data-ttu-id="b1606-164">Requis</span><span class="sxs-lookup"><span data-stu-id="b1606-164">Required</span></span> |<span data-ttu-id="b1606-165">La date à partir de laquelle les détails du poste sont valides.</span><span class="sxs-lookup"><span data-stu-id="b1606-165">The date the position details are valid from.</span></span>  |
| <span data-ttu-id="b1606-166">**Valide à partir du**</span><span class="sxs-lookup"><span data-stu-id="b1606-166">**Valid from**</span></span><br><span data-ttu-id="b1606-167">validfrom</span><span class="sxs-lookup"><span data-stu-id="b1606-167">validfrom</span></span><br><span data-ttu-id="b1606-168">*Décalage de date et heure*</span><span class="sxs-lookup"><span data-stu-id="b1606-168">*Date Time Offset*</span></span> | <span data-ttu-id="b1606-169">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="b1606-169">Read-only</span></span><br><span data-ttu-id="b1606-170">Requis</span><span class="sxs-lookup"><span data-stu-id="b1606-170">Required</span></span> |<span data-ttu-id="b1606-171">La date jusqu'à laquelle les détails du poste sont valides.</span><span class="sxs-lookup"><span data-stu-id="b1606-171">The date the position details are valid to.</span></span>  |

<span data-ttu-id="b1606-172">**Requête**</span><span class="sxs-lookup"><span data-stu-id="b1606-172">**Query**</span></span>

<span data-ttu-id="b1606-173">**Demande**</span><span class="sxs-lookup"><span data-stu-id="b1606-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

<span data-ttu-id="b1606-174">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="b1606-174">**Response**</span></span>

```json
{
            "mshr_positionid": "000276",
            "mshr_paycycleid": "w",
            "mshr_annualregularhours": 3000,
            "mshr_paidbylegalentity": "USMF",
            "mshr_validfrom": "2021-03-14T00:00:00Z",
            "mshr_validto": "2154-12-31T00:00:00Z",
            "mshr_primaryfield": "000276 | 3/14/2021",
            "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
            "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
            "mshr_payrollpositionentityid": "00010097-0000-0000-df00-014105000000"
}
```
