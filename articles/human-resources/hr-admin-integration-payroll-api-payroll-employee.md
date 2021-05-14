---
title: Employé avec paie
description: Cette rubrique fournit des détails et un exemple de requête pour l’entité Collaborateur avec paie dans Dynamics 365 Human Resources.
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
ms.openlocfilehash: d3977b758f65875a36749a49459c2a81459a7b69
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881986"
---
# <a name="payroll-employee"></a><span data-ttu-id="ef880-103">Employé avec paie</span><span class="sxs-lookup"><span data-stu-id="ef880-103">Payroll employee</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="ef880-104">Cette rubrique fournit des détails et un exemple de requête pour l’entité Collaborateur avec paie dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ef880-104">This topic provides details and an example query for the Payroll employee entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="ef880-105">Propriétés</span><span class="sxs-lookup"><span data-stu-id="ef880-105">Properties</span></span>

| <span data-ttu-id="ef880-106">Propriété</span><span class="sxs-lookup"><span data-stu-id="ef880-106">Property</span></span><br><span data-ttu-id="ef880-107">**Nom physique**</span><span class="sxs-lookup"><span data-stu-id="ef880-107">**Physical name**</span></span><br><span data-ttu-id="ef880-108">**_Type_**</span><span class="sxs-lookup"><span data-stu-id="ef880-108">**_Type_**</span></span> | <span data-ttu-id="ef880-109">Cas d’emploi</span><span class="sxs-lookup"><span data-stu-id="ef880-109">Use</span></span> | <span data-ttu-id="ef880-110">Description</span><span class="sxs-lookup"><span data-stu-id="ef880-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="ef880-111">**Numéro personnel**</span><span class="sxs-lookup"><span data-stu-id="ef880-111">**Personnel number**</span></span><br><span data-ttu-id="ef880-112">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="ef880-112">mshr_personnelnumber</span></span><br><span data-ttu-id="ef880-113">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ef880-113">*String*</span></span> | <span data-ttu-id="ef880-114">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="ef880-114">Read-only</span></span><br><span data-ttu-id="ef880-115">Requis</span><span class="sxs-lookup"><span data-stu-id="ef880-115">Required</span></span> | <span data-ttu-id="ef880-116">Numéro personnel unique du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="ef880-116">The employee's unique personnel number.</span></span> |
| <span data-ttu-id="ef880-117">**Champ principal**</span><span class="sxs-lookup"><span data-stu-id="ef880-117">**Primary field**</span></span><br><span data-ttu-id="ef880-118">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="ef880-118">mshr_primaryfield</span></span><br><span data-ttu-id="ef880-119">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ef880-119">*String*</span></span> | <span data-ttu-id="ef880-120">Requis</span><span class="sxs-lookup"><span data-stu-id="ef880-120">Required</span></span><br><span data-ttu-id="ef880-121">Généré par le système</span><span class="sxs-lookup"><span data-stu-id="ef880-121">System generated</span></span> |  |
| <span data-ttu-id="ef880-122">**Nom**</span><span class="sxs-lookup"><span data-stu-id="ef880-122">**Last name**</span></span><br><span data-ttu-id="ef880-123">mshr_lastname</span><span class="sxs-lookup"><span data-stu-id="ef880-123">mshr_lastname</span></span><br><span data-ttu-id="ef880-124">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ef880-124">*String*</span></span> | <span data-ttu-id="ef880-125">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="ef880-125">Read only</span></span><br><span data-ttu-id="ef880-126">Requis</span><span class="sxs-lookup"><span data-stu-id="ef880-126">Required</span></span> | <span data-ttu-id="ef880-127">Nom de famille du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="ef880-127">Employee last name.</span></span> |
| <span data-ttu-id="ef880-128">**ID entité juridique**</span><span class="sxs-lookup"><span data-stu-id="ef880-128">**Legal entity ID**</span></span><br><span data-ttu-id="ef880-129">mshr_legalentityID</span><span class="sxs-lookup"><span data-stu-id="ef880-129">mshr_legalentityID</span></span><br><span data-ttu-id="ef880-130">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ef880-130">*String*</span></span> | <span data-ttu-id="ef880-131">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="ef880-131">Read-only</span></span><br><span data-ttu-id="ef880-132">Requis</span><span class="sxs-lookup"><span data-stu-id="ef880-132">Required</span></span> | <span data-ttu-id="ef880-133">Spécifie l’entité juridique (société).</span><span class="sxs-lookup"><span data-stu-id="ef880-133">Specifies the legal entity (company).</span></span> |
| <span data-ttu-id="ef880-134">**Valide à partir du**</span><span class="sxs-lookup"><span data-stu-id="ef880-134">**Valid from**</span></span><br><span data-ttu-id="ef880-135">mshr_namevalidfrom</span><span class="sxs-lookup"><span data-stu-id="ef880-135">mshr_namevalidfrom</span></span><br><span data-ttu-id="ef880-136">*Décalage de date et heure*</span><span class="sxs-lookup"><span data-stu-id="ef880-136">*Date Time Offset*</span></span> | <span data-ttu-id="ef880-137">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="ef880-137">Read-only</span></span> <br><span data-ttu-id="ef880-138">Requis</span><span class="sxs-lookup"><span data-stu-id="ef880-138">Required</span></span> | <span data-ttu-id="ef880-139">Date à partir de laquelle les informations relatives au collaborateur sont valides.</span><span class="sxs-lookup"><span data-stu-id="ef880-139">Date the employee information is valid from.</span></span>  |
| <span data-ttu-id="ef880-140">**Sexe**</span><span class="sxs-lookup"><span data-stu-id="ef880-140">**Gender**</span></span><br><span data-ttu-id="ef880-141">mshr_gender</span><span class="sxs-lookup"><span data-stu-id="ef880-141">mshr_gender</span></span><br><span data-ttu-id="ef880-142">*Int32*</span><span class="sxs-lookup"><span data-stu-id="ef880-142">*Int32*</span></span> | <span data-ttu-id="ef880-143">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="ef880-143">Read-only</span></span><br><span data-ttu-id="ef880-144">Requis</span><span class="sxs-lookup"><span data-stu-id="ef880-144">Required</span></span> | <span data-ttu-id="ef880-145">Genre du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="ef880-145">The employee's gender.</span></span> |
| <span data-ttu-id="ef880-146">**ID d'entité Collaborateur avec paie**</span><span class="sxs-lookup"><span data-stu-id="ef880-146">**Payroll employee entity ID**</span></span><br><span data-ttu-id="ef880-147">mshr_payrollemployeeentityid</span><span class="sxs-lookup"><span data-stu-id="ef880-147">mshr_payrollemployeeentityid</span></span><br><span data-ttu-id="ef880-148">*GUID*</span><span class="sxs-lookup"><span data-stu-id="ef880-148">*GUID*</span></span> | <span data-ttu-id="ef880-149">Requis</span><span class="sxs-lookup"><span data-stu-id="ef880-149">Required</span></span><br><span data-ttu-id="ef880-150">Généré par le système</span><span class="sxs-lookup"><span data-stu-id="ef880-150">System generated</span></span> | <span data-ttu-id="ef880-151">Valeur GUID générée par le système pour identifier le collaborateur de manière unique.</span><span class="sxs-lookup"><span data-stu-id="ef880-151">A system-generated GUID value to uniquely identify the employee.</span></span> |
| <span data-ttu-id="ef880-152">**Date de début de l'emploi**</span><span class="sxs-lookup"><span data-stu-id="ef880-152">**Employment start date**</span></span><br><span data-ttu-id="ef880-153">mshr_employmentstartdate</span><span class="sxs-lookup"><span data-stu-id="ef880-153">mshr_employmentstartdate</span></span><br><span data-ttu-id="ef880-154">*Décalage de date et heure*</span><span class="sxs-lookup"><span data-stu-id="ef880-154">*Date time offset*</span></span> | <span data-ttu-id="ef880-155">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="ef880-155">Read-only</span></span><br><span data-ttu-id="ef880-156">Requis</span><span class="sxs-lookup"><span data-stu-id="ef880-156">Required</span></span> | <span data-ttu-id="ef880-157">Date de début de l’emploi du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="ef880-157">The start date of the employee's employment.</span></span> |
| <span data-ttu-id="ef880-158">**ID du type d’identification**</span><span class="sxs-lookup"><span data-stu-id="ef880-158">**Identification type ID**</span></span><br><span data-ttu-id="ef880-159">mshr_identificationtypeid</span><span class="sxs-lookup"><span data-stu-id="ef880-159">mshr_identificationtypeid</span></span><br><span data-ttu-id="ef880-160">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ef880-160">*String*</span></span> |<span data-ttu-id="ef880-161">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="ef880-161">Read-only</span></span><br><span data-ttu-id="ef880-162">Requis</span><span class="sxs-lookup"><span data-stu-id="ef880-162">Required</span></span> | <span data-ttu-id="ef880-163">Le type d'identification défini pour le collaborateur.</span><span class="sxs-lookup"><span data-stu-id="ef880-163">The identification type defined for the employee.</span></span> |
| <span data-ttu-id="ef880-164">**Date de fin de l'emploi**</span><span class="sxs-lookup"><span data-stu-id="ef880-164">**Employment end date**</span></span><br><span data-ttu-id="ef880-165">mshr_employmentenddate</span><span class="sxs-lookup"><span data-stu-id="ef880-165">mshr_employmentenddate</span></span><br><span data-ttu-id="ef880-166">*Décalage de date et heure*</span><span class="sxs-lookup"><span data-stu-id="ef880-166">*Date time offset*</span></span> | <span data-ttu-id="ef880-167">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="ef880-167">Read-only</span></span><br><span data-ttu-id="ef880-168">Requis</span><span class="sxs-lookup"><span data-stu-id="ef880-168">Required</span></span> |<span data-ttu-id="ef880-169">Date de fin de l’emploi du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="ef880-169">The end of the employee's employment.</span></span>  |
| <span data-ttu-id="ef880-170">**ID zone de données**</span><span class="sxs-lookup"><span data-stu-id="ef880-170">**Data area ID**</span></span><br><span data-ttu-id="ef880-171">mshr_dataareaid_id</span><span class="sxs-lookup"><span data-stu-id="ef880-171">mshr_dataareaid_id</span></span><br><span data-ttu-id="ef880-172">*GUID*</span><span class="sxs-lookup"><span data-stu-id="ef880-172">*GUID*</span></span> | <span data-ttu-id="ef880-173">Requis</span><span class="sxs-lookup"><span data-stu-id="ef880-173">Required</span></span> <br><span data-ttu-id="ef880-174">Généré par le système</span><span class="sxs-lookup"><span data-stu-id="ef880-174">System generated</span></span> | <span data-ttu-id="ef880-175">Valeur GUID générée par le système identifiant l’entité juridique (société).</span><span class="sxs-lookup"><span data-stu-id="ef880-175">System-generated GUID value identifying the legal entity (company).</span></span> |
| <span data-ttu-id="ef880-176">**Valide jusqu’au**</span><span class="sxs-lookup"><span data-stu-id="ef880-176">**Valid to**</span></span><br><span data-ttu-id="ef880-177">mshr_namevalidto</span><span class="sxs-lookup"><span data-stu-id="ef880-177">mshr_namevalidto</span></span><br><span data-ttu-id="ef880-178">*Décalage de date et heure*</span><span class="sxs-lookup"><span data-stu-id="ef880-178">*Date Time Offset*</span></span> |  <span data-ttu-id="ef880-179">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="ef880-179">Read-only</span></span><br><span data-ttu-id="ef880-180">Requis</span><span class="sxs-lookup"><span data-stu-id="ef880-180">Required</span></span> | <span data-ttu-id="ef880-181">Date jusqu'à laquelle les informations relatives au collaborateur sont valides.</span><span class="sxs-lookup"><span data-stu-id="ef880-181">Date the employee information is valid to.</span></span> |
| <span data-ttu-id="ef880-182">**Date de naissance**</span><span class="sxs-lookup"><span data-stu-id="ef880-182">**Birth date**</span></span><br><span data-ttu-id="ef880-183">mshr_birthdate</span><span class="sxs-lookup"><span data-stu-id="ef880-183">mshr_birthdate</span></span><br><span data-ttu-id="ef880-184">*Décalage de date et heure*</span><span class="sxs-lookup"><span data-stu-id="ef880-184">*Date Time Offset*</span></span> | <span data-ttu-id="ef880-185">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="ef880-185">Read-only</span></span> <br><span data-ttu-id="ef880-186">Requis</span><span class="sxs-lookup"><span data-stu-id="ef880-186">Required</span></span> | <span data-ttu-id="ef880-187">La date de naissance du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="ef880-187">The employee's birth date</span></span> |
| <span data-ttu-id="ef880-188">**Numéro d’identification**</span><span class="sxs-lookup"><span data-stu-id="ef880-188">**Identification number to**</span></span><br><span data-ttu-id="ef880-189">mshr_identificationnumber</span><span class="sxs-lookup"><span data-stu-id="ef880-189">mshr_identificationnumber</span></span><br><span data-ttu-id="ef880-190">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ef880-190">*String*</span></span> | <span data-ttu-id="ef880-191">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="ef880-191">Read-only</span></span> <br><span data-ttu-id="ef880-192">Requis</span><span class="sxs-lookup"><span data-stu-id="ef880-192">Required</span></span> |<span data-ttu-id="ef880-193">Le numéro d'identification défini pour le collaborateur.</span><span class="sxs-lookup"><span data-stu-id="ef880-193">The identification number defined for the employee.</span></span>  |
| <span data-ttu-id="ef880-194">**Prénom**</span><span class="sxs-lookup"><span data-stu-id="ef880-194">**First name**</span></span><br><span data-ttu-id="ef880-195">mshr_firstname</span><span class="sxs-lookup"><span data-stu-id="ef880-195">mshr_firstname</span></span><br><span data-ttu-id="ef880-196">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ef880-196">*String*</span></span> | <span data-ttu-id="ef880-197">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="ef880-197">Read-only</span></span><br><span data-ttu-id="ef880-198">Requis</span><span class="sxs-lookup"><span data-stu-id="ef880-198">Required</span></span> | <span data-ttu-id="ef880-199">Prénom du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="ef880-199">Employee first name.</span></span> |
| <span data-ttu-id="ef880-200">**Autres prénoms**</span><span class="sxs-lookup"><span data-stu-id="ef880-200">**Middle name**</span></span><br><span data-ttu-id="ef880-201">mshr_middlename</span><span class="sxs-lookup"><span data-stu-id="ef880-201">mshr_middlename</span></span><br><span data-ttu-id="ef880-202">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ef880-202">*String*</span></span> | <span data-ttu-id="ef880-203">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="ef880-203">Read-only</span></span><br><span data-ttu-id="ef880-204">Requis</span><span class="sxs-lookup"><span data-stu-id="ef880-204">Required</span></span> |<span data-ttu-id="ef880-205">Deuxième prénom du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="ef880-205">Employee middle name.</span></span>  |

## <a name="example-query-for-payroll-employee"></a><span data-ttu-id="ef880-206">Exemple de requête pour un Collaborateur avec paie</span><span class="sxs-lookup"><span data-stu-id="ef880-206">Example query for Payroll employee</span></span>

<span data-ttu-id="ef880-207">**Demande**</span><span class="sxs-lookup"><span data-stu-id="ef880-207">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollemployeeentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_identificationtypeid eq @idtype and mshr_namevalidfrom le @asofdate and mshr_namevalidto ge @asofdate&@personnelnumber='000041'&@idtype='SSN'&@asofdate=2021-04-01
```

<span data-ttu-id="ef880-208">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="ef880-208">**Response**</span></span>

```json
{
         "mshr_legalentityid": "USMF",
            "mshr_personnelnumber": "000041",
            "mshr_employmentstartdate": "2011-04-05T07:00:00Z",
            "mshr_employmentenddate": "2154-12-31T23:59:59Z",
            "mshr_firstname": "Cassie",
            "mshr_middlename": "Lassie",
            "mshr_lastname": "Hicks",
            "mshr_namevalidfrom": "2021-03-12T20:34:25Z",
            "mshr_namevalidto": "2154-12-31T23:59:59Z",
            "mshr_birthdate": "1987-09-12T00:00:00Z",
            "mshr_gender": 200000002,
            "mshr_identificationtypeid": "SSN",
            "mshr_identificationnumber": "888-99-9342",
            "mshr_dataareaid": "USMF",
            "mshr_primaryfield": "000041 | USMF | 4/5/2011 07:00:00 am",
            "_mshr_fk_worker_id_value": "000000ad-0000-0000-d5ff-004105000000",
            "_mshr_fk_employment_id_value": "00000d0d-0000-0000-0600-014105000000",
            "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
            "mshr_payrollemployeeentityid": "00000d3c-0000-0000-d5ff-004105000000",
            "_mshr_dataareaid_id_value": null
}
```