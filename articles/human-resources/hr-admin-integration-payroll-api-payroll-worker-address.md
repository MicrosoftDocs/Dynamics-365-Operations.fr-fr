---
title: Adresse du collaborateur avec paie
description: Cette rubrique fournit des détails et un exemple de requête pour l’entité Adresse du collaborateur avec paie dans Dynamics 365 Human Resources.
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
ms.openlocfilehash: 6d93c38b21e953446142fc32cc2a0911616ac61d
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881982"
---
# <a name="payroll-worker-address"></a><span data-ttu-id="1ab11-103">Adresse du collaborateur avec paie</span><span class="sxs-lookup"><span data-stu-id="1ab11-103">Payroll worker address</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="1ab11-104">Cette rubrique fournit des détails et un exemple de requête pour l’entité Adresse du collaborateur avec paie dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1ab11-104">This topic provides details and an example query for the Payroll worker address entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="1ab11-105">Propriétés</span><span class="sxs-lookup"><span data-stu-id="1ab11-105">Properties</span></span>

| <span data-ttu-id="1ab11-106">Propriété</span><span class="sxs-lookup"><span data-stu-id="1ab11-106">Property</span></span><br><span data-ttu-id="1ab11-107">**Nom physique**</span><span class="sxs-lookup"><span data-stu-id="1ab11-107">**Physical name**</span></span><br><span data-ttu-id="1ab11-108">**_Type_**</span><span class="sxs-lookup"><span data-stu-id="1ab11-108">**_Type_**</span></span> | <span data-ttu-id="1ab11-109">Cas d’emploi</span><span class="sxs-lookup"><span data-stu-id="1ab11-109">Use</span></span> | <span data-ttu-id="1ab11-110">Description</span><span class="sxs-lookup"><span data-stu-id="1ab11-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="1ab11-111">**Ville**</span><span class="sxs-lookup"><span data-stu-id="1ab11-111">**City**</span></span><br><span data-ttu-id="1ab11-112">mshr_city</span><span class="sxs-lookup"><span data-stu-id="1ab11-112">mshr_city</span></span><br><span data-ttu-id="1ab11-113">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="1ab11-113">*String*</span></span> | <span data-ttu-id="1ab11-114">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="1ab11-114">Read-only</span></span><br><span data-ttu-id="1ab11-115">Requis</span><span class="sxs-lookup"><span data-stu-id="1ab11-115">Required</span></span> | <span data-ttu-id="1ab11-116">Ville définie pour l'adresse.</span><span class="sxs-lookup"><span data-stu-id="1ab11-116">The city defined for the address.</span></span>   |
| <span data-ttu-id="1ab11-117">**Numéro personnel**</span><span class="sxs-lookup"><span data-stu-id="1ab11-117">**Personnel number**</span></span><br><span data-ttu-id="1ab11-118">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="1ab11-118">mshr_personnelnumber</span></span><br><span data-ttu-id="1ab11-119">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="1ab11-119">*String*</span></span> | <span data-ttu-id="1ab11-120">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="1ab11-120">Read-only</span></span><br><span data-ttu-id="1ab11-121">Requis</span><span class="sxs-lookup"><span data-stu-id="1ab11-121">Required</span></span> | <span data-ttu-id="1ab11-122">Numéro personnel unique du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="1ab11-122">The employee's unique personnel number.</span></span>  |
| <span data-ttu-id="1ab11-123">**Pays ou région**</span><span class="sxs-lookup"><span data-stu-id="1ab11-123">**Country region**</span></span><br><span data-ttu-id="1ab11-124">mshr_countryregionid</span><span class="sxs-lookup"><span data-stu-id="1ab11-124">mshr_countryregionid</span></span><br><span data-ttu-id="1ab11-125">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="1ab11-125">*String*</span></span> | <span data-ttu-id="1ab11-126">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="1ab11-126">Read-only</span></span><br><span data-ttu-id="1ab11-127">Requis</span><span class="sxs-lookup"><span data-stu-id="1ab11-127">Required</span></span> | <span data-ttu-id="1ab11-128">Le pays/région défini pour l'adresse.</span><span class="sxs-lookup"><span data-stu-id="1ab11-128">The country region defined for the address</span></span>  |
| <span data-ttu-id="1ab11-129">**Valide à partir du**</span><span class="sxs-lookup"><span data-stu-id="1ab11-129">**Valid from**</span></span><br><span data-ttu-id="1ab11-130">mshr_postaladdressvalidfrom</span><span class="sxs-lookup"><span data-stu-id="1ab11-130">mshr_postaladdressvalidfrom</span></span><br><span data-ttu-id="1ab11-131">*Décalage de date et heure*</span><span class="sxs-lookup"><span data-stu-id="1ab11-131">*Date Time Offset*</span></span> | <span data-ttu-id="1ab11-132">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="1ab11-132">Read-only</span></span> <br><span data-ttu-id="1ab11-133">Requis</span><span class="sxs-lookup"><span data-stu-id="1ab11-133">Required</span></span> | <span data-ttu-id="1ab11-134">Date à partir de laquelle l'adresse est valide.</span><span class="sxs-lookup"><span data-stu-id="1ab11-134">The date the address is valid from.</span></span> |
| <span data-ttu-id="1ab11-135">**Adresse de travail**</span><span class="sxs-lookup"><span data-stu-id="1ab11-135">**Worked in address**</span></span><br><span data-ttu-id="1ab11-136">mshr_isworkedinaddressbr>*Int32*</span><span class="sxs-lookup"><span data-stu-id="1ab11-136">mshr_isworkedinaddressbr>*Int32*</span></span> | <span data-ttu-id="1ab11-137">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="1ab11-137">Read-only</span></span><br><span data-ttu-id="1ab11-138">Requis</span><span class="sxs-lookup"><span data-stu-id="1ab11-138">Required</span></span> | <span data-ttu-id="1ab11-139">Indique si l'adresse est le lieu de travail du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="1ab11-139">Denotes if the address is where the employee works.</span></span> |
| <span data-ttu-id="1ab11-140">**Département**</span><span class="sxs-lookup"><span data-stu-id="1ab11-140">**County**</span></span><br><span data-ttu-id="1ab11-141">mshr_county</span><span class="sxs-lookup"><span data-stu-id="1ab11-141">mshr_county</span></span><br><span data-ttu-id="1ab11-142">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="1ab11-142">*String*</span></span> | <span data-ttu-id="1ab11-143">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="1ab11-143">Read-only</span></span><br><span data-ttu-id="1ab11-144">Requis</span><span class="sxs-lookup"><span data-stu-id="1ab11-144">Required</span></span> | <span data-ttu-id="1ab11-145">Département défini pour l'adresse.</span><span class="sxs-lookup"><span data-stu-id="1ab11-145">The county defined for the address.</span></span>  |
| <span data-ttu-id="1ab11-146">**ID de l'adresse du collaborateur avec paie**</span><span class="sxs-lookup"><span data-stu-id="1ab11-146">**Payroll worker address ID**</span></span><br><span data-ttu-id="1ab11-147">mshr_payrollworkeraddressentityid</span><span class="sxs-lookup"><span data-stu-id="1ab11-147">mshr_payrollworkeraddressentityid</span></span><br><span data-ttu-id="1ab11-148">*GUID*</span><span class="sxs-lookup"><span data-stu-id="1ab11-148">*GUID*</span></span> | <span data-ttu-id="1ab11-149">Requis</span><span class="sxs-lookup"><span data-stu-id="1ab11-149">Required</span></span><br><span data-ttu-id="1ab11-150">Généré par le système</span><span class="sxs-lookup"><span data-stu-id="1ab11-150">System generated</span></span> | <span data-ttu-id="1ab11-151">Valeur GUID générée par le système pour identifier l'adresse de manière unique.</span><span class="sxs-lookup"><span data-stu-id="1ab11-151">A system-generated GUID value to uniquely identify the address.</span></span>  |
| <span data-ttu-id="1ab11-152">**Champ principal**</span><span class="sxs-lookup"><span data-stu-id="1ab11-152">**Primary field**</span></span><br><span data-ttu-id="1ab11-153">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="1ab11-153">mshr_primaryfield</span></span><br><span data-ttu-id="1ab11-154">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="1ab11-154">*String*</span></span> | <span data-ttu-id="1ab11-155">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="1ab11-155">Read-only</span></span><br><span data-ttu-id="1ab11-156">Requis</span><span class="sxs-lookup"><span data-stu-id="1ab11-156">Required</span></span> |  |
| <span data-ttu-id="1ab11-157">**Rue**</span><span class="sxs-lookup"><span data-stu-id="1ab11-157">**Street**</span></span><br><span data-ttu-id="1ab11-158">mshr_street</span><span class="sxs-lookup"><span data-stu-id="1ab11-158">mshr_street</span></span><br><span data-ttu-id="1ab11-159">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="1ab11-159">*String*</span></span> | <span data-ttu-id="1ab11-160">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="1ab11-160">Read-only</span></span><br><span data-ttu-id="1ab11-161">Requis</span><span class="sxs-lookup"><span data-stu-id="1ab11-161">Required</span></span> | <span data-ttu-id="1ab11-162">Rue définie pour l'adresse.</span><span class="sxs-lookup"><span data-stu-id="1ab11-162">The street defined for the address.</span></span> |
| <span data-ttu-id="1ab11-163">**Valide jusqu’au**</span><span class="sxs-lookup"><span data-stu-id="1ab11-163">**Valid to**</span></span><br><span data-ttu-id="1ab11-164">mshr_postaladdressvalidto</span><span class="sxs-lookup"><span data-stu-id="1ab11-164">mshr_postaladdressvalidto</span></span><br><span data-ttu-id="1ab11-165">*Décalage de date et heure*</span><span class="sxs-lookup"><span data-stu-id="1ab11-165">*Date Time Offset*</span></span> | <span data-ttu-id="1ab11-166">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="1ab11-166">Read-only</span></span> <br><span data-ttu-id="1ab11-167">Requis</span><span class="sxs-lookup"><span data-stu-id="1ab11-167">Required</span></span> | <span data-ttu-id="1ab11-168">Date jusqu'à laquelle l'adresse est valide.</span><span class="sxs-lookup"><span data-stu-id="1ab11-168">The date the address is valid to.</span></span>  |
| <span data-ttu-id="1ab11-169">**ID emplacement**</span><span class="sxs-lookup"><span data-stu-id="1ab11-169">**Location ID**</span></span><br><span data-ttu-id="1ab11-170">mshr_locationidbr>*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="1ab11-170">mshr_locationidbr>*String*</span></span> | <span data-ttu-id="1ab11-171">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="1ab11-171">Read-only</span></span> <br><span data-ttu-id="1ab11-172">Requis</span><span class="sxs-lookup"><span data-stu-id="1ab11-172">Required</span></span> | <span data-ttu-id="1ab11-173">ID de l'adresse.</span><span class="sxs-lookup"><span data-stu-id="1ab11-173">The ID for the address.</span></span>  |
| <span data-ttu-id="1ab11-174">**Code postal**</span><span class="sxs-lookup"><span data-stu-id="1ab11-174">**Postal code**</span></span><br><span data-ttu-id="1ab11-175">mshr_zipcode</span><span class="sxs-lookup"><span data-stu-id="1ab11-175">mshr_zipcode</span></span><br><span data-ttu-id="1ab11-176">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="1ab11-176">*String*</span></span> | <span data-ttu-id="1ab11-177">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="1ab11-177">Read-only</span></span> <br><span data-ttu-id="1ab11-178">Requis</span><span class="sxs-lookup"><span data-stu-id="1ab11-178">Required</span></span> |<span data-ttu-id="1ab11-179">Le numéro d'identification défini pour le collaborateur.</span><span class="sxs-lookup"><span data-stu-id="1ab11-179">The identification number defined for the employee.</span></span>  |
| <span data-ttu-id="1ab11-180">**Adresse de résidence**</span><span class="sxs-lookup"><span data-stu-id="1ab11-180">**Lived in address**</span></span><br><span data-ttu-id="1ab11-181">mshr_islivedinaddressbr>*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="1ab11-181">mshr_islivedinaddressbr>*String*</span></span> | <span data-ttu-id="1ab11-182">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="1ab11-182">Read-only</span></span><br><span data-ttu-id="1ab11-183">Requis</span><span class="sxs-lookup"><span data-stu-id="1ab11-183">Required</span></span> | <span data-ttu-id="1ab11-184">Indique si l'adresse est le lieu de résidence du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="1ab11-184">Denotes if the address is where the employee lives.</span></span> |
| <span data-ttu-id="1ab11-185">**État**</span><span class="sxs-lookup"><span data-stu-id="1ab11-185">**State**</span></span><br><span data-ttu-id="1ab11-186">mshr_state</span><span class="sxs-lookup"><span data-stu-id="1ab11-186">mshr_state</span></span><br><span data-ttu-id="1ab11-187">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="1ab11-187">*String*</span></span> | <span data-ttu-id="1ab11-188">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="1ab11-188">Read-only</span></span><br><span data-ttu-id="1ab11-189">Requis</span><span class="sxs-lookup"><span data-stu-id="1ab11-189">Required</span></span> | <span data-ttu-id="1ab11-190">État défini pour l'adresse.</span><span class="sxs-lookup"><span data-stu-id="1ab11-190">The state defined for the address.</span></span>  |

## <a name="example-query"></a><span data-ttu-id="1ab11-191">Exemple de requête</span><span class="sxs-lookup"><span data-stu-id="1ab11-191">Example query</span></span>

<span data-ttu-id="1ab11-192">**Demande**</span><span class="sxs-lookup"><span data-stu-id="1ab11-192">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="1ab11-193">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="1ab11-193">**Response**</span></span>

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
