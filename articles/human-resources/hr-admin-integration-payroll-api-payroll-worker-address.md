---
title: Adresse du collaborateur avec paie
description: Cette rubrique fournit des détails et un exemple de requête pour l’entité Adresse du collaborateur avec paie dans Dynamics 365 Human Resources.
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
ms.openlocfilehash: 964f04261ea95ee6fa2880b0905a669855f6c58a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020703"
---
# <a name="payroll-worker-address"></a><span data-ttu-id="130d1-103">Adresse du collaborateur avec paie</span><span class="sxs-lookup"><span data-stu-id="130d1-103">Payroll worker address</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="130d1-104">Cette rubrique fournit des détails et un exemple de requête pour l’entité Adresse du collaborateur avec paie dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="130d1-104">This topic provides details and an example query for the Payroll worker address entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="130d1-105">Propriétés</span><span class="sxs-lookup"><span data-stu-id="130d1-105">Properties</span></span>

| <span data-ttu-id="130d1-106">Propriété</span><span class="sxs-lookup"><span data-stu-id="130d1-106">Property</span></span><br><span data-ttu-id="130d1-107">**Nom physique**</span><span class="sxs-lookup"><span data-stu-id="130d1-107">**Physical name**</span></span><br><span data-ttu-id="130d1-108">**_Type_**</span><span class="sxs-lookup"><span data-stu-id="130d1-108">**_Type_**</span></span> | <span data-ttu-id="130d1-109">Cas d’emploi</span><span class="sxs-lookup"><span data-stu-id="130d1-109">Use</span></span> | <span data-ttu-id="130d1-110">Description</span><span class="sxs-lookup"><span data-stu-id="130d1-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="130d1-111">**Ville**</span><span class="sxs-lookup"><span data-stu-id="130d1-111">**City**</span></span><br><span data-ttu-id="130d1-112">mshr_city</span><span class="sxs-lookup"><span data-stu-id="130d1-112">mshr_city</span></span><br><span data-ttu-id="130d1-113">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="130d1-113">*String*</span></span> | <span data-ttu-id="130d1-114">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="130d1-114">Read-only</span></span><br><span data-ttu-id="130d1-115">Requis</span><span class="sxs-lookup"><span data-stu-id="130d1-115">Required</span></span> | <span data-ttu-id="130d1-116">Ville définie pour l'adresse.</span><span class="sxs-lookup"><span data-stu-id="130d1-116">The city defined for the address.</span></span>   |
| <span data-ttu-id="130d1-117">**Numéro personnel**</span><span class="sxs-lookup"><span data-stu-id="130d1-117">**Personnel number**</span></span><br><span data-ttu-id="130d1-118">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="130d1-118">mshr_personnelnumber</span></span><br><span data-ttu-id="130d1-119">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="130d1-119">*String*</span></span> | <span data-ttu-id="130d1-120">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="130d1-120">Read-only</span></span><br><span data-ttu-id="130d1-121">Requis</span><span class="sxs-lookup"><span data-stu-id="130d1-121">Required</span></span> | <span data-ttu-id="130d1-122">Numéro personnel unique du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="130d1-122">The employee's unique personnel number.</span></span>  |
| <span data-ttu-id="130d1-123">**Pays ou région**</span><span class="sxs-lookup"><span data-stu-id="130d1-123">**Country region**</span></span><br><span data-ttu-id="130d1-124">mshr_countryregionid</span><span class="sxs-lookup"><span data-stu-id="130d1-124">mshr_countryregionid</span></span><br><span data-ttu-id="130d1-125">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="130d1-125">*String*</span></span> | <span data-ttu-id="130d1-126">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="130d1-126">Read-only</span></span><br><span data-ttu-id="130d1-127">Requis</span><span class="sxs-lookup"><span data-stu-id="130d1-127">Required</span></span> | <span data-ttu-id="130d1-128">Le pays/région défini pour l'adresse.</span><span class="sxs-lookup"><span data-stu-id="130d1-128">The country region defined for the address</span></span>  |
| <span data-ttu-id="130d1-129">**Valide à partir du**</span><span class="sxs-lookup"><span data-stu-id="130d1-129">**Valid from**</span></span><br><span data-ttu-id="130d1-130">mshr_postaladdressvalidfrom</span><span class="sxs-lookup"><span data-stu-id="130d1-130">mshr_postaladdressvalidfrom</span></span><br><span data-ttu-id="130d1-131">*Décalage de date et heure*</span><span class="sxs-lookup"><span data-stu-id="130d1-131">*Date Time Offset*</span></span> | <span data-ttu-id="130d1-132">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="130d1-132">Read-only</span></span> <br><span data-ttu-id="130d1-133">Requis</span><span class="sxs-lookup"><span data-stu-id="130d1-133">Required</span></span> | <span data-ttu-id="130d1-134">Date à partir de laquelle l'adresse est valide.</span><span class="sxs-lookup"><span data-stu-id="130d1-134">The date the address is valid from.</span></span> |
| <span data-ttu-id="130d1-135">**Adresse de travail**</span><span class="sxs-lookup"><span data-stu-id="130d1-135">**Worked in address**</span></span><br><span data-ttu-id="130d1-136">mshr_isworkedinaddressbr>*Int32*</span><span class="sxs-lookup"><span data-stu-id="130d1-136">mshr_isworkedinaddressbr>*Int32*</span></span> | <span data-ttu-id="130d1-137">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="130d1-137">Read-only</span></span><br><span data-ttu-id="130d1-138">Requis</span><span class="sxs-lookup"><span data-stu-id="130d1-138">Required</span></span> | <span data-ttu-id="130d1-139">Indique si l'adresse est le lieu de travail du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="130d1-139">Denotes if the address is where the employee works.</span></span> |
| <span data-ttu-id="130d1-140">**Département**</span><span class="sxs-lookup"><span data-stu-id="130d1-140">**County**</span></span><br><span data-ttu-id="130d1-141">mshr_county</span><span class="sxs-lookup"><span data-stu-id="130d1-141">mshr_county</span></span><br><span data-ttu-id="130d1-142">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="130d1-142">*String*</span></span> | <span data-ttu-id="130d1-143">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="130d1-143">Read-only</span></span><br><span data-ttu-id="130d1-144">Requis</span><span class="sxs-lookup"><span data-stu-id="130d1-144">Required</span></span> | <span data-ttu-id="130d1-145">Département défini pour l'adresse.</span><span class="sxs-lookup"><span data-stu-id="130d1-145">The county defined for the address.</span></span>  |
| <span data-ttu-id="130d1-146">**ID de l'adresse du collaborateur avec paie**</span><span class="sxs-lookup"><span data-stu-id="130d1-146">**Payroll worker address ID**</span></span><br><span data-ttu-id="130d1-147">mshr_payrollworkeraddressentityid</span><span class="sxs-lookup"><span data-stu-id="130d1-147">mshr_payrollworkeraddressentityid</span></span><br><span data-ttu-id="130d1-148">*GUID*</span><span class="sxs-lookup"><span data-stu-id="130d1-148">*GUID*</span></span> | <span data-ttu-id="130d1-149">Requis</span><span class="sxs-lookup"><span data-stu-id="130d1-149">Required</span></span><br><span data-ttu-id="130d1-150">Généré par le système</span><span class="sxs-lookup"><span data-stu-id="130d1-150">System generated</span></span> | <span data-ttu-id="130d1-151">Valeur GUID générée par le système pour identifier l'adresse de manière unique.</span><span class="sxs-lookup"><span data-stu-id="130d1-151">A system-generated GUID value to uniquely identify the address.</span></span>  |
| <span data-ttu-id="130d1-152">**Champ principal**</span><span class="sxs-lookup"><span data-stu-id="130d1-152">**Primary field**</span></span><br><span data-ttu-id="130d1-153">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="130d1-153">mshr_primaryfield</span></span><br><span data-ttu-id="130d1-154">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="130d1-154">*String*</span></span> | <span data-ttu-id="130d1-155">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="130d1-155">Read-only</span></span><br><span data-ttu-id="130d1-156">Requis</span><span class="sxs-lookup"><span data-stu-id="130d1-156">Required</span></span> |  |
| <span data-ttu-id="130d1-157">**Rue**</span><span class="sxs-lookup"><span data-stu-id="130d1-157">**Street**</span></span><br><span data-ttu-id="130d1-158">mshr_street</span><span class="sxs-lookup"><span data-stu-id="130d1-158">mshr_street</span></span><br><span data-ttu-id="130d1-159">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="130d1-159">*String*</span></span> | <span data-ttu-id="130d1-160">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="130d1-160">Read-only</span></span><br><span data-ttu-id="130d1-161">Requis</span><span class="sxs-lookup"><span data-stu-id="130d1-161">Required</span></span> | <span data-ttu-id="130d1-162">Rue définie pour l'adresse.</span><span class="sxs-lookup"><span data-stu-id="130d1-162">The street defined for the address.</span></span> |
| <span data-ttu-id="130d1-163">**Valide jusqu’au**</span><span class="sxs-lookup"><span data-stu-id="130d1-163">**Valid to**</span></span><br><span data-ttu-id="130d1-164">mshr_postaladdressvalidto</span><span class="sxs-lookup"><span data-stu-id="130d1-164">mshr_postaladdressvalidto</span></span><br><span data-ttu-id="130d1-165">*Décalage de date et heure*</span><span class="sxs-lookup"><span data-stu-id="130d1-165">*Date Time Offset*</span></span> | <span data-ttu-id="130d1-166">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="130d1-166">Read-only</span></span> <br><span data-ttu-id="130d1-167">Requis</span><span class="sxs-lookup"><span data-stu-id="130d1-167">Required</span></span> | <span data-ttu-id="130d1-168">Date jusqu'à laquelle l'adresse est valide.</span><span class="sxs-lookup"><span data-stu-id="130d1-168">The date the address is valid to.</span></span>  |
| <span data-ttu-id="130d1-169">**ID emplacement**</span><span class="sxs-lookup"><span data-stu-id="130d1-169">**Location ID**</span></span><br><span data-ttu-id="130d1-170">mshr_locationidbr>*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="130d1-170">mshr_locationidbr>*String*</span></span> | <span data-ttu-id="130d1-171">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="130d1-171">Read-only</span></span> <br><span data-ttu-id="130d1-172">Requis</span><span class="sxs-lookup"><span data-stu-id="130d1-172">Required</span></span> | <span data-ttu-id="130d1-173">ID de l'adresse.</span><span class="sxs-lookup"><span data-stu-id="130d1-173">The ID for the address.</span></span>  |
| <span data-ttu-id="130d1-174">**Code postal**</span><span class="sxs-lookup"><span data-stu-id="130d1-174">**Postal code**</span></span><br><span data-ttu-id="130d1-175">mshr_zipcode</span><span class="sxs-lookup"><span data-stu-id="130d1-175">mshr_zipcode</span></span><br><span data-ttu-id="130d1-176">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="130d1-176">*String*</span></span> | <span data-ttu-id="130d1-177">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="130d1-177">Read-only</span></span> <br><span data-ttu-id="130d1-178">Requis</span><span class="sxs-lookup"><span data-stu-id="130d1-178">Required</span></span> |<span data-ttu-id="130d1-179">Le numéro d'identification défini pour le collaborateur.</span><span class="sxs-lookup"><span data-stu-id="130d1-179">The identification number defined for the employee.</span></span>  |
| <span data-ttu-id="130d1-180">**Adresse de résidence**</span><span class="sxs-lookup"><span data-stu-id="130d1-180">**Lived in address**</span></span><br><span data-ttu-id="130d1-181">mshr_islivedinaddressbr>*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="130d1-181">mshr_islivedinaddressbr>*String*</span></span> | <span data-ttu-id="130d1-182">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="130d1-182">Read-only</span></span><br><span data-ttu-id="130d1-183">Requis</span><span class="sxs-lookup"><span data-stu-id="130d1-183">Required</span></span> | <span data-ttu-id="130d1-184">Indique si l'adresse est le lieu de résidence du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="130d1-184">Denotes if the address is where the employee lives.</span></span> |
| <span data-ttu-id="130d1-185">**État**</span><span class="sxs-lookup"><span data-stu-id="130d1-185">**State**</span></span><br><span data-ttu-id="130d1-186">mshr_state</span><span class="sxs-lookup"><span data-stu-id="130d1-186">mshr_state</span></span><br><span data-ttu-id="130d1-187">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="130d1-187">*String*</span></span> | <span data-ttu-id="130d1-188">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="130d1-188">Read-only</span></span><br><span data-ttu-id="130d1-189">Requis</span><span class="sxs-lookup"><span data-stu-id="130d1-189">Required</span></span> | <span data-ttu-id="130d1-190">État défini pour l'adresse.</span><span class="sxs-lookup"><span data-stu-id="130d1-190">The state defined for the address.</span></span>  |

## <a name="example-query"></a><span data-ttu-id="130d1-191">Exemple de requête</span><span class="sxs-lookup"><span data-stu-id="130d1-191">Example query</span></span>

<span data-ttu-id="130d1-192">**Demande**</span><span class="sxs-lookup"><span data-stu-id="130d1-192">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="130d1-193">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="130d1-193">**Response**</span></span>

```json
{
            "mshr_personnelnumber": "000041",
            "mshr_locationid": "000000538",
            "mshr_islivedinaddress": 200000001,
            "mshr_isworkedinaddress": 200000000,
            "mshr_countryregionid": "USA",
            "mshr_zipcode": "99025",
            "mshr_street": "6543 Cypress Ave",
            "mshr_city": "Tacoma",
            "mshr_state": "WA",
            "mshr_county": "KING",
            "mshr_postaladdressvalidfrom": "2012-09-20T20:14:27Z",
            "mshr_postaladdressvalidto": "2154-12-31T23:59:59Z",
            "mshr_primaryfield": "000041 | 000000538 | 9/20/2012 08:14:27 pm",
            "_mshr_fk_worker_id_value": "00000d3c-0000-0000-d5ff-004105000000",
            "mshr_payrollworkeraddressentityid": "000006f0-0000-0000-f90f-014105000000"

}
```
