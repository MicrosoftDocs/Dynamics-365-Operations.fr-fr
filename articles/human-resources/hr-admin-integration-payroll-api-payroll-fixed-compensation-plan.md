---
title: Régime de rémunération fixe avec paie
description: Cette rubrique fournit des détails un exemple de requête pour l’entité Régime de rémunération fixe dans Dynamics 365 Human Resources.
author: jcart
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
ms.openlocfilehash: 85cfce6f626090adab422ea6c60fc0778fd1ac67
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021294"
---
# <a name="payroll-fixed-compensation-plan"></a><span data-ttu-id="44061-103">Régime de rémunération fixe avec paie</span><span class="sxs-lookup"><span data-stu-id="44061-103">Payroll fixed compensation plan</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="44061-104">Cette rubrique fournit des détails un exemple de requête pour l’entité Régime de rémunération fixe dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="44061-104">This topic provides details and an example query for the Payroll fixed compensation plan entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="44061-105">Propriétés</span><span class="sxs-lookup"><span data-stu-id="44061-105">Properties</span></span>

| <span data-ttu-id="44061-106">Propriété</span><span class="sxs-lookup"><span data-stu-id="44061-106">Property</span></span><br><span data-ttu-id="44061-107">**Nom physique**</span><span class="sxs-lookup"><span data-stu-id="44061-107">**Physical name**</span></span><br><span data-ttu-id="44061-108">**_Type_**</span><span class="sxs-lookup"><span data-stu-id="44061-108">**_Type_**</span></span> | <span data-ttu-id="44061-109">Cas d’emploi</span><span class="sxs-lookup"><span data-stu-id="44061-109">Use</span></span> | <span data-ttu-id="44061-110">Description</span><span class="sxs-lookup"><span data-stu-id="44061-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="44061-111">**ID employé**</span><span class="sxs-lookup"><span data-stu-id="44061-111">**Employee ID**</span></span><br><span data-ttu-id="44061-112">mshr_fk_employee_id_value</span><span class="sxs-lookup"><span data-stu-id="44061-112">mshr_fk_employee_id_value</span></span><br><span data-ttu-id="44061-113">*GUID*</span><span class="sxs-lookup"><span data-stu-id="44061-113">*GUID*</span></span> | <span data-ttu-id="44061-114">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="44061-114">Read-only</span></span><br><span data-ttu-id="44061-115">Requis</span><span class="sxs-lookup"><span data-stu-id="44061-115">Required</span></span><br><span data-ttu-id="44061-116">Clé étrangère : Foreign key:mshr_Employee_id de mshr_payrollemployeeentity entity</span><span class="sxs-lookup"><span data-stu-id="44061-116">Foreign key:mshr_Employee_id of mshr_payrollemployeeentity entity</span></span>  | <span data-ttu-id="44061-117">ID employé</span><span class="sxs-lookup"><span data-stu-id="44061-117">Employee ID</span></span> |
| <span data-ttu-id="44061-118">**Salaire**</span><span class="sxs-lookup"><span data-stu-id="44061-118">**Pay rate**</span></span><br><span data-ttu-id="44061-119">mshr_payrate</span><span class="sxs-lookup"><span data-stu-id="44061-119">mshr_payrate</span></span><br><span data-ttu-id="44061-120">*Décimal*</span><span class="sxs-lookup"><span data-stu-id="44061-120">*Decimal*</span></span> | <span data-ttu-id="44061-121">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="44061-121">Read-only</span></span><br><span data-ttu-id="44061-122">Requis</span><span class="sxs-lookup"><span data-stu-id="44061-122">Required</span></span> | <span data-ttu-id="44061-123">Taux de rémunération défini dans le régime de rémunération fixe.</span><span class="sxs-lookup"><span data-stu-id="44061-123">Pay rate defined in fixed compensation plan.</span></span> |
| <span data-ttu-id="44061-124">**ID plan**</span><span class="sxs-lookup"><span data-stu-id="44061-124">**Plan ID**</span></span><br><span data-ttu-id="44061-125">mshr_planid</span><span class="sxs-lookup"><span data-stu-id="44061-125">mshr_planid</span></span><br><span data-ttu-id="44061-126">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="44061-126">*String*</span></span> | <span data-ttu-id="44061-127">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="44061-127">Read-only</span></span><br><span data-ttu-id="44061-128">Requis</span><span class="sxs-lookup"><span data-stu-id="44061-128">Required</span></span> |<span data-ttu-id="44061-129">Spécifie le régime de rémunération.</span><span class="sxs-lookup"><span data-stu-id="44061-129">Specifies the compensation plan.</span></span>  |
| <span data-ttu-id="44061-130">**Valide à partir du**</span><span class="sxs-lookup"><span data-stu-id="44061-130">**Valid from**</span></span><br><span data-ttu-id="44061-131">mshr_validfrom</span><span class="sxs-lookup"><span data-stu-id="44061-131">mshr_validfrom</span></span><br><span data-ttu-id="44061-132">*Décalage de date et heure*</span><span class="sxs-lookup"><span data-stu-id="44061-132">*Date Time Offset*</span></span> |  <span data-ttu-id="44061-133">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="44061-133">Read-only</span></span><br><span data-ttu-id="44061-134">Requis</span><span class="sxs-lookup"><span data-stu-id="44061-134">Required</span></span> |<span data-ttu-id="44061-135">Date à partir de laquelle les informations relatives à la rémunération fixe sont valides.</span><span class="sxs-lookup"><span data-stu-id="44061-135">Date the employee fixed compensation is valid from.</span></span>  |
| <span data-ttu-id="44061-136">**Entité Régime de rémunération fixe avec paie**</span><span class="sxs-lookup"><span data-stu-id="44061-136">**Payroll Fixed Compensation Plan entity**</span></span><br><span data-ttu-id="44061-137">mshr_payrollfixedcompensationplanentityid</span><span class="sxs-lookup"><span data-stu-id="44061-137">mshr_payrollfixedcompensationplanentityid</span></span><br><span data-ttu-id="44061-138">*GUID*</span><span class="sxs-lookup"><span data-stu-id="44061-138">*GUID*</span></span> | <span data-ttu-id="44061-139">Requis</span><span class="sxs-lookup"><span data-stu-id="44061-139">Required</span></span><br><span data-ttu-id="44061-140">Généré par le système</span><span class="sxs-lookup"><span data-stu-id="44061-140">Sytem generated</span></span> | <span data-ttu-id="44061-141">Valeur GUID générée par le système pour identifier le rémunération fixe de manière unique.</span><span class="sxs-lookup"><span data-stu-id="44061-141">A system-generated GUID value to uniquely identify the compensation plan.</span></span> |
| <span data-ttu-id="44061-142">**Fréquence de paiement**</span><span class="sxs-lookup"><span data-stu-id="44061-142">**Pay frequency**</span></span><br><span data-ttu-id="44061-143">mshr_payfrequency</span><span class="sxs-lookup"><span data-stu-id="44061-143">mshr_payfrequency</span></span><br><span data-ttu-id="44061-144">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="44061-144">*String*</span></span> | <span data-ttu-id="44061-145">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="44061-145">Read-only</span></span><br><span data-ttu-id="44061-146">Requis</span><span class="sxs-lookup"><span data-stu-id="44061-146">Required</span></span> |<span data-ttu-id="44061-147">La fréquence à laquelle l'employé sera payé.</span><span class="sxs-lookup"><span data-stu-id="44061-147">The frequency the employee will be paid.</span></span>  |
| <span data-ttu-id="44061-148">**Valide jusqu’au**</span><span class="sxs-lookup"><span data-stu-id="44061-148">**Valid to**</span></span><br><span data-ttu-id="44061-149">mshr_validto</span><span class="sxs-lookup"><span data-stu-id="44061-149">mshr_validto</span></span><br><span data-ttu-id="44061-150">*Décalage de date et heure*</span><span class="sxs-lookup"><span data-stu-id="44061-150">*Date Time Offset*</span></span> | <span data-ttu-id="44061-151">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="44061-151">Read-only</span></span> <br><span data-ttu-id="44061-152">Requis</span><span class="sxs-lookup"><span data-stu-id="44061-152">Required</span></span> | <span data-ttu-id="44061-153">Date jusqu'à laquelle les informations relatives à la rémunération fixe sont valides.</span><span class="sxs-lookup"><span data-stu-id="44061-153">Date the employee fixed compensation is valid to.</span></span> |
| <span data-ttu-id="44061-154">**ID poste**</span><span class="sxs-lookup"><span data-stu-id="44061-154">**Position ID**</span></span><br><span data-ttu-id="44061-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="44061-155">mshr_positionid</span></span><br><span data-ttu-id="44061-156">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="44061-156">*String*</span></span> | <span data-ttu-id="44061-157">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="44061-157">Read-only</span></span> <br><span data-ttu-id="44061-158">Requis</span><span class="sxs-lookup"><span data-stu-id="44061-158">Required</span></span> | <span data-ttu-id="44061-159">ID de poste associé à l'employé et à l'inscription au régime de rémunération fixe.</span><span class="sxs-lookup"><span data-stu-id="44061-159">Postion ID associated with the employee and fixed compensation plan enrollment.</span></span> |
| <span data-ttu-id="44061-160">**Devise**</span><span class="sxs-lookup"><span data-stu-id="44061-160">**Currency**</span></span><br><span data-ttu-id="44061-161">mshr_currency</span><span class="sxs-lookup"><span data-stu-id="44061-161">mshr_currency</span></span><br><span data-ttu-id="44061-162">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="44061-162">*String*</span></span> | <span data-ttu-id="44061-163">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="44061-163">Read-only</span></span> <br><span data-ttu-id="44061-164">Requis</span><span class="sxs-lookup"><span data-stu-id="44061-164">Required</span></span> |<span data-ttu-id="44061-165">La devise définie pour le régime de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="44061-165">The currency defined for the fixed compensation plan</span></span>   |
| <span data-ttu-id="44061-166">**Numéro personnel**</span><span class="sxs-lookup"><span data-stu-id="44061-166">**Personnel number**</span></span><br><span data-ttu-id="44061-167">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="44061-167">mshr_personnelnumber</span></span><br><span data-ttu-id="44061-168">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="44061-168">*String*</span></span> | <span data-ttu-id="44061-169">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="44061-169">Read-only</span></span><br><span data-ttu-id="44061-170">Requis</span><span class="sxs-lookup"><span data-stu-id="44061-170">Required</span></span> |<span data-ttu-id="44061-171">Numéro personnel unique du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="44061-171">The employee's unique personnel number.</span></span>  |

<span data-ttu-id="44061-172">**Requête**</span><span class="sxs-lookup"><span data-stu-id="44061-172">**Query**</span></span>

<span data-ttu-id="44061-173">**Demande**</span><span class="sxs-lookup"><span data-stu-id="44061-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="44061-174">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="44061-174">**Response**</span></span>

```json
{
            "mshr_planid": "GradeC",
            "mshr_personnelnumber": "000041",
            "mshr_payrate": 75200,
            "mshr_positionid": "000276",
            "mshr_validfrom": "2011-04-05T00:00:00Z",
            "mshr_validto": "2154-12-31T00:00:00Z",
            "mshr_payfrequency": "Annual",
            "mshr_currency": "USD",
            "_mshr_fk_employee_id_value": "00000d3c-0000-0000-d5ff-004105000000",
            "_mshr_fk_plan_id_value": "0000070c-0000-0000-b328-fef003000000",
            "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
            "mshr_payrollfixedcompensationplanentityid": "0000029f-0000-0000-d5ff-004105000000",
            "_mshr_fk_payroll_id_value": null
}
```
