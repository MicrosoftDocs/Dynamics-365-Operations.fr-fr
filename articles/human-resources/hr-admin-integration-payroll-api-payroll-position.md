---
title: Détails de la paie pour les postes
description: Cette rubrique fournit des détails et un exemple de requête pour l’entité Détails de la paie pour les postes dans Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8918044dbf84e79015dc3bca904f204123a37db8
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056778"
---
# <a name="payroll-position"></a><span data-ttu-id="4dd64-103">Poste de paie</span><span class="sxs-lookup"><span data-stu-id="4dd64-103">Payroll position</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="4dd64-104">Cette rubrique fournit des détails et un exemple de requête pour l’entité Détails de la paie pour les postes dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4dd64-104">This topic provides details and an example query for the Payroll details for the Positions entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="4dd64-105">Propriétés</span><span class="sxs-lookup"><span data-stu-id="4dd64-105">Properties</span></span>

| <span data-ttu-id="4dd64-106">Propriété</span><span class="sxs-lookup"><span data-stu-id="4dd64-106">Property</span></span><br><span data-ttu-id="4dd64-107">**Nom physique**</span><span class="sxs-lookup"><span data-stu-id="4dd64-107">**Physical name**</span></span><br><span data-ttu-id="4dd64-108">**_Type_**</span><span class="sxs-lookup"><span data-stu-id="4dd64-108">**_Type_**</span></span> | <span data-ttu-id="4dd64-109">Cas d’emploi</span><span class="sxs-lookup"><span data-stu-id="4dd64-109">Use</span></span> | <span data-ttu-id="4dd64-110">Description</span><span class="sxs-lookup"><span data-stu-id="4dd64-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="4dd64-111">**Durée annuelle normale**</span><span class="sxs-lookup"><span data-stu-id="4dd64-111">**Annual regular hours**</span></span><br><span data-ttu-id="4dd64-112">annualregularhours</span><span class="sxs-lookup"><span data-stu-id="4dd64-112">annualregularhours</span></span><br><span data-ttu-id="4dd64-113">*Décimal*</span><span class="sxs-lookup"><span data-stu-id="4dd64-113">*Decimal*</span></span> | <span data-ttu-id="4dd64-114">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="4dd64-114">Read-only</span></span><br><span data-ttu-id="4dd64-115">Requis</span><span class="sxs-lookup"><span data-stu-id="4dd64-115">Required</span></span> | <span data-ttu-id="4dd64-116">Heures normales annuelles définies sur le poste.</span><span class="sxs-lookup"><span data-stu-id="4dd64-116">Annual regular hours defined on the position.</span></span>  |
| <span data-ttu-id="4dd64-117">**ID de l'entité Détails du poste de paie**</span><span class="sxs-lookup"><span data-stu-id="4dd64-117">**Payroll position details entity ID**</span></span><br><span data-ttu-id="4dd64-118">payrollpositiondetailsentityid</span><span class="sxs-lookup"><span data-stu-id="4dd64-118">payrollpositiondetailsentityid</span></span><br><span data-ttu-id="4dd64-119">*Guid*</span><span class="sxs-lookup"><span data-stu-id="4dd64-119">*Guid*</span></span> | <span data-ttu-id="4dd64-120">Requis</span><span class="sxs-lookup"><span data-stu-id="4dd64-120">Required</span></span><br><span data-ttu-id="4dd64-121">Généré par le système.</span><span class="sxs-lookup"><span data-stu-id="4dd64-121">System generated.</span></span> | <span data-ttu-id="4dd64-122">Valeur GUID générée par le système pour identifier le poste de manière unique.</span><span class="sxs-lookup"><span data-stu-id="4dd64-122">A system-generated GUID value to uniquely identify the position.</span></span>  |
| <span data-ttu-id="4dd64-123">**Champ principal**</span><span class="sxs-lookup"><span data-stu-id="4dd64-123">**Primary field**</span></span><br><span data-ttu-id="4dd64-124">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="4dd64-124">mshr_primaryfield</span></span><br><span data-ttu-id="4dd64-125">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="4dd64-125">*String*</span></span> | <span data-ttu-id="4dd64-126">Requis</span><span class="sxs-lookup"><span data-stu-id="4dd64-126">Required</span></span><br><span data-ttu-id="4dd64-127">Généré par le système</span><span class="sxs-lookup"><span data-stu-id="4dd64-127">System generated</span></span> |  |
| <span data-ttu-id="4dd64-128">**Valeur d’ID du poste**</span><span class="sxs-lookup"><span data-stu-id="4dd64-128">**Position job ID value**</span></span><br><span data-ttu-id="4dd64-129">_mshr_fk_positionjob_id_value</span><span class="sxs-lookup"><span data-stu-id="4dd64-129">_mshr_fk_positionjob_id_value</span></span><br><span data-ttu-id="4dd64-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="4dd64-130">*GUID*</span></span> | <span data-ttu-id="4dd64-131">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="4dd64-131">Read-only</span></span><br><span data-ttu-id="4dd64-132">Requis</span><span class="sxs-lookup"><span data-stu-id="4dd64-132">Required</span></span><br><span data-ttu-id="4dd64-133">Clé étrangère : mshr_PayrollPositionJobEntity de mshr_payrollpositionjobentity</span><span class="sxs-lookup"><span data-stu-id="4dd64-133">Foreign key:mshr_PayrollPositionJobEntity of the mshr_payrollpositionjobentity</span></span> |<span data-ttu-id="4dd64-134">ID du travail associé au poste.</span><span class="sxs-lookup"><span data-stu-id="4dd64-134">The ID of the job associated with the position.</span></span>|
| <span data-ttu-id="4dd64-135">**Valeur de l'ID du régime de rémunération fixe**</span><span class="sxs-lookup"><span data-stu-id="4dd64-135">**Fixed compensation plan ID value**</span></span><br><span data-ttu-id="4dd64-136">_mshr_fk_fixedcompplan_id_value</span><span class="sxs-lookup"><span data-stu-id="4dd64-136">_mshr_fk_fixedcompplan_id_value</span></span><br><span data-ttu-id="4dd64-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="4dd64-137">*GUID*</span></span> | <span data-ttu-id="4dd64-138">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="4dd64-138">Read-only</span></span><br><span data-ttu-id="4dd64-139">Requis</span><span class="sxs-lookup"><span data-stu-id="4dd64-139">Required</span></span><br><span data-ttu-id="4dd64-140">Clé étrangère : mshr_FixedCompPlan_id de mshr_payrollfixedcompensationplanentity</span><span class="sxs-lookup"><span data-stu-id="4dd64-140">Foreign key: mshr_FixedCompPlan_id of mshr_payrollfixedcompensationplanentity</span></span>  | <span data-ttu-id="4dd64-141">ID du régime de rémunération fixe associé au poste.</span><span class="sxs-lookup"><span data-stu-id="4dd64-141">The ID of the fixed compensation plan associated with the position.</span></span> |
| <span data-ttu-id="4dd64-142">**ID du cycle de paie**</span><span class="sxs-lookup"><span data-stu-id="4dd64-142">**Pay cycle ID**</span></span><br><span data-ttu-id="4dd64-143">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="4dd64-143">mshr_primaryfield</span></span><br><span data-ttu-id="4dd64-144">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="4dd64-144">*String*</span></span> | <span data-ttu-id="4dd64-145">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="4dd64-145">Read-only</span></span><br><span data-ttu-id="4dd64-146">Requis</span><span class="sxs-lookup"><span data-stu-id="4dd64-146">Required</span></span> | <span data-ttu-id="4dd64-147">Le cycle de paie défini sur le poste.</span><span class="sxs-lookup"><span data-stu-id="4dd64-147">The pay cycle defined on the position.</span></span> |
| <span data-ttu-id="4dd64-148">**Rémunéré par l’entité juridique**</span><span class="sxs-lookup"><span data-stu-id="4dd64-148">**Paid by legal entity**</span></span><br><span data-ttu-id="4dd64-149">paidbylegalentity</span><span class="sxs-lookup"><span data-stu-id="4dd64-149">paidbylegalentity</span></span><br><span data-ttu-id="4dd64-150">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="4dd64-150">*String*</span></span> | <span data-ttu-id="4dd64-151">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="4dd64-151">Read-only</span></span><br><span data-ttu-id="4dd64-152">Requis</span><span class="sxs-lookup"><span data-stu-id="4dd64-152">Required</span></span> | <span data-ttu-id="4dd64-153">L'entité juridique définie sur le poste, responsable de l'émission du paiement.</span><span class="sxs-lookup"><span data-stu-id="4dd64-153">The legal entity defined on the positoin responsible for issuing payment.</span></span> |
| <span data-ttu-id="4dd64-154">**ID poste**</span><span class="sxs-lookup"><span data-stu-id="4dd64-154">**Position ID**</span></span><br><span data-ttu-id="4dd64-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="4dd64-155">mshr_positionid</span></span><br><span data-ttu-id="4dd64-156">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="4dd64-156">*String*</span></span> | <span data-ttu-id="4dd64-157">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="4dd64-157">Read-only</span></span><br><span data-ttu-id="4dd64-158">Requis</span><span class="sxs-lookup"><span data-stu-id="4dd64-158">Required</span></span> | <span data-ttu-id="4dd64-159">ID du poste.</span><span class="sxs-lookup"><span data-stu-id="4dd64-159">The ID of the position.</span></span> |
| <span data-ttu-id="4dd64-160">**Valide jusqu’au**</span><span class="sxs-lookup"><span data-stu-id="4dd64-160">**Valid to**</span></span><br><span data-ttu-id="4dd64-161">validto</span><span class="sxs-lookup"><span data-stu-id="4dd64-161">validto</span></span><br><span data-ttu-id="4dd64-162">*Décalage de date et heure*</span><span class="sxs-lookup"><span data-stu-id="4dd64-162">*Date Time Offset*</span></span> | <span data-ttu-id="4dd64-163">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="4dd64-163">Read-only</span></span><br><span data-ttu-id="4dd64-164">Requis</span><span class="sxs-lookup"><span data-stu-id="4dd64-164">Required</span></span> |<span data-ttu-id="4dd64-165">La date à partir de laquelle les détails du poste sont valides.</span><span class="sxs-lookup"><span data-stu-id="4dd64-165">The date the position details are valid from.</span></span>  |
| <span data-ttu-id="4dd64-166">**Valide à partir du**</span><span class="sxs-lookup"><span data-stu-id="4dd64-166">**Valid from**</span></span><br><span data-ttu-id="4dd64-167">validfrom</span><span class="sxs-lookup"><span data-stu-id="4dd64-167">validfrom</span></span><br><span data-ttu-id="4dd64-168">*Décalage de date et heure*</span><span class="sxs-lookup"><span data-stu-id="4dd64-168">*Date Time Offset*</span></span> | <span data-ttu-id="4dd64-169">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="4dd64-169">Read-only</span></span><br><span data-ttu-id="4dd64-170">Requis</span><span class="sxs-lookup"><span data-stu-id="4dd64-170">Required</span></span> |<span data-ttu-id="4dd64-171">La date jusqu'à laquelle les détails du poste sont valides.</span><span class="sxs-lookup"><span data-stu-id="4dd64-171">The date the position details are valid to.</span></span>  |

<span data-ttu-id="4dd64-172">**Requête**</span><span class="sxs-lookup"><span data-stu-id="4dd64-172">**Query**</span></span>

<span data-ttu-id="4dd64-173">**Demande**</span><span class="sxs-lookup"><span data-stu-id="4dd64-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

<span data-ttu-id="4dd64-174">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="4dd64-174">**Response**</span></span>

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
