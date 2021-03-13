---
title: Présélection
description: Cette rubrique décrit l'entité Présélection pour Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d76bb57d85ee16f4faa0bb9cfec77047feb7df5f
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125375"
---
# <a name="person-screening"></a><span data-ttu-id="1bd5d-103">Présélection</span><span class="sxs-lookup"><span data-stu-id="1bd5d-103">Person screening</span></span>

<span data-ttu-id="1bd5d-104">Cette rubrique décrit l'entité Présélection pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1bd5d-104">This topic describes the Person screening entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="1bd5d-105">Nom physique : mshr_hcmpersonscreeningentity</span><span class="sxs-lookup"><span data-stu-id="1bd5d-105">Physical name: mshr_hcmpersonscreeningentity</span></span>

## <a name="description"></a><span data-ttu-id="1bd5d-106">Description</span><span class="sxs-lookup"><span data-stu-id="1bd5d-106">Description</span></span>

<span data-ttu-id="1bd5d-107">Cette entité décrit les présélections qu'un candidat a réussies ou doit réussir pour le poste.</span><span class="sxs-lookup"><span data-stu-id="1bd5d-107">This entity describes screenings a candidate has passed or must pass for employment.</span></span>

## <a name="json-representation"></a><span data-ttu-id="1bd5d-108">Représentation JSON</span><span class="sxs-lookup"><span data-stu-id="1bd5d-108">JSON representation</span></span>

```json
{
    "mshr_note": "String",
    "mshr_requiredby": "Date",
    "mshr_status": Int,
    "mshr_partynumber": "String",
    "mshr_screeningtypeid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a><span data-ttu-id="1bd5d-109">Propriétés</span><span class="sxs-lookup"><span data-stu-id="1bd5d-109">Properties</span></span>

| <span data-ttu-id="1bd5d-110">Propriété</span><span class="sxs-lookup"><span data-stu-id="1bd5d-110">Property</span></span><br><span data-ttu-id="1bd5d-111">**Nom physique**</span><span class="sxs-lookup"><span data-stu-id="1bd5d-111">**Physical name**</span></span><br><span data-ttu-id="1bd5d-112">**_Type_**</span><span class="sxs-lookup"><span data-stu-id="1bd5d-112">**_Type_**</span></span> | <span data-ttu-id="1bd5d-113">Cas d’emploi</span><span class="sxs-lookup"><span data-stu-id="1bd5d-113">Use</span></span> | <span data-ttu-id="1bd5d-114">Description</span><span class="sxs-lookup"><span data-stu-id="1bd5d-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="1bd5d-115">**ID d'entité de présélection**</span><span class="sxs-lookup"><span data-stu-id="1bd5d-115">**Person Screening Entity ID**</span></span><br><span data-ttu-id="1bd5d-116">mshr_hcmpersonscreeningentityid</span><span class="sxs-lookup"><span data-stu-id="1bd5d-116">mshr_hcmpersonscreeningentityid</span></span><br><span data-ttu-id="1bd5d-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="1bd5d-117">*GUID*</span></span> | <span data-ttu-id="1bd5d-118">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="1bd5d-118">Read-only</span></span><br><span data-ttu-id="1bd5d-119">Requis</span><span class="sxs-lookup"><span data-stu-id="1bd5d-119">Required</span></span><br><span data-ttu-id="1bd5d-120">Généré par le système</span><span class="sxs-lookup"><span data-stu-id="1bd5d-120">System-generated</span></span> | <span data-ttu-id="1bd5d-121">Identificateur principal unique pour le dossier de présélection.</span><span class="sxs-lookup"><span data-stu-id="1bd5d-121">Unique primary identifier for the person screening record.</span></span> |
| <span data-ttu-id="1bd5d-122">**Numéro tiers**</span><span class="sxs-lookup"><span data-stu-id="1bd5d-122">**Party Number**</span></span><br><span data-ttu-id="1bd5d-123">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="1bd5d-123">mshr_partynumber</span></span><br><span data-ttu-id="1bd5d-124">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="1bd5d-124">*String*</span></span> | <span data-ttu-id="1bd5d-125">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="1bd5d-125">Read/write</span></span><br><span data-ttu-id="1bd5d-126">Requis</span><span class="sxs-lookup"><span data-stu-id="1bd5d-126">Required</span></span> | <span data-ttu-id="1bd5d-127">Le numéro tiers (personne) associé au candidat.</span><span class="sxs-lookup"><span data-stu-id="1bd5d-127">The party (person) number associated with the candidate.</span></span> |
| <span data-ttu-id="1bd5d-128">**Valeur de l'ID de personne**</span><span class="sxs-lookup"><span data-stu-id="1bd5d-128">**Person ID Value**</span></span><br><span data-ttu-id="1bd5d-129">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="1bd5d-129">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="1bd5d-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="1bd5d-130">*GUID*</span></span> | <span data-ttu-id="1bd5d-131">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="1bd5d-131">Read-only</span></span><br><span data-ttu-id="1bd5d-132">Requis</span><span class="sxs-lookup"><span data-stu-id="1bd5d-132">Required</span></span><br><span data-ttu-id="1bd5d-133">Clé étrangère : mshr_dirpersonentityid de l'entité mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="1bd5d-133">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="1bd5d-134">Identificateur généré par le système de l'enregistrement de l'entité de tiers (personne).</span><span class="sxs-lookup"><span data-stu-id="1bd5d-134">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="1bd5d-135">**ID type de présélection**</span><span class="sxs-lookup"><span data-stu-id="1bd5d-135">**Screening Type ID**</span></span><br><span data-ttu-id="1bd5d-136">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="1bd5d-136">mshr_screeningtypeid</span></span><br><span data-ttu-id="1bd5d-137">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="1bd5d-137">*String*</span></span> | <span data-ttu-id="1bd5d-138">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="1bd5d-138">Read/write</span></span><br><span data-ttu-id="1bd5d-139">Requis</span><span class="sxs-lookup"><span data-stu-id="1bd5d-139">Required</span></span><br><span data-ttu-id="1bd5d-140">Clé étrangère : ScreeningType</span><span class="sxs-lookup"><span data-stu-id="1bd5d-140">Foreign key: ScreeningType</span></span> | <span data-ttu-id="1bd5d-141">Identifiant du type de présélection défini dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1bd5d-141">The identifier of the screening type defined in Human Resources.</span></span> |
| <span data-ttu-id="1bd5d-142">**Valeur de l'ID de type de présélection**</span><span class="sxs-lookup"><span data-stu-id="1bd5d-142">**Screening Type ID Value**</span></span><br><span data-ttu-id="1bd5d-143">_mshr_fk_screeningtype_id_value</span><span class="sxs-lookup"><span data-stu-id="1bd5d-143">_mshr_fk_screeningtype_id_value</span></span><br><span data-ttu-id="1bd5d-144">*GUID*</span><span class="sxs-lookup"><span data-stu-id="1bd5d-144">*GUID*</span></span> | <span data-ttu-id="1bd5d-145">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="1bd5d-145">Read-only</span></span><br><span data-ttu-id="1bd5d-146">Requis</span><span class="sxs-lookup"><span data-stu-id="1bd5d-146">Required</span></span><br><span data-ttu-id="1bd5d-147">Clé étrangère : mshr_hcmscreeningtypeentityid de l'entité mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="1bd5d-147">Foreign key: mshr_hcmscreeningtypeentityid of mshr_hcmscreeningtypeentity</span></span> | <span data-ttu-id="1bd5d-148">Identificateur généré par le système pour le dossier du type de présélection de l'entité associée.</span><span class="sxs-lookup"><span data-stu-id="1bd5d-148">System-generated identifier for the screening type record in the associated entity.</span></span> |
| <span data-ttu-id="1bd5d-149">**Requis par**</span><span class="sxs-lookup"><span data-stu-id="1bd5d-149">**Required By**</span></span><br><span data-ttu-id="1bd5d-150">mshr_requiredby</span><span class="sxs-lookup"><span data-stu-id="1bd5d-150">mshr_requiredby</span></span><br><span data-ttu-id="1bd5d-151">*DateHeure*</span><span class="sxs-lookup"><span data-stu-id="1bd5d-151">*Datetime*</span></span> | <span data-ttu-id="1bd5d-152">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="1bd5d-152">Read/write</span></span><br><span data-ttu-id="1bd5d-153">Facultatif</span><span class="sxs-lookup"><span data-stu-id="1bd5d-153">Optional</span></span> | <span data-ttu-id="1bd5d-154">Date à laquelle la présélection doit être terminée.</span><span class="sxs-lookup"><span data-stu-id="1bd5d-154">The date by which the screening is required to be completed.</span></span> |
| <span data-ttu-id="1bd5d-155">**État**</span><span class="sxs-lookup"><span data-stu-id="1bd5d-155">**Status**</span></span><br><span data-ttu-id="1bd5d-156">mshr_status</span><span class="sxs-lookup"><span data-stu-id="1bd5d-156">mshr_status</span></span><br><span data-ttu-id="1bd5d-157">*Jeu d'options mshr_hcmcompletionstatus*</span><span class="sxs-lookup"><span data-stu-id="1bd5d-157">*mshr_hcmcompletionstatus option set*</span></span><br><span data-ttu-id="1bd5d-158">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="1bd5d-158">Read/write</span></span><br><span data-ttu-id="1bd5d-159">Requis</span><span class="sxs-lookup"><span data-stu-id="1bd5d-159">Required</span></span> | <span data-ttu-id="1bd5d-160">Fournit le statut du candidat pour la présélection.</span><span class="sxs-lookup"><span data-stu-id="1bd5d-160">Provides the candidate’s status for the screening.</span></span> |
| <span data-ttu-id="1bd5d-161">**Date de fin**</span><span class="sxs-lookup"><span data-stu-id="1bd5d-161">**Completed Date**</span></span><br><span data-ttu-id="1bd5d-162">mshr_completeddate</span><span class="sxs-lookup"><span data-stu-id="1bd5d-162">mshr_completeddate</span></span><br><span data-ttu-id="1bd5d-163">*DateHeure*</span><span class="sxs-lookup"><span data-stu-id="1bd5d-163">*Datetime*</span></span> | <span data-ttu-id="1bd5d-164">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="1bd5d-164">Read/write</span></span><br><span data-ttu-id="1bd5d-165">Facultatif</span><span class="sxs-lookup"><span data-stu-id="1bd5d-165">Optional</span></span> | <span data-ttu-id="1bd5d-166">Date à laquelle la présélection s'est terminée.</span><span class="sxs-lookup"><span data-stu-id="1bd5d-166">The date the screening was completed.</span></span> |
| <span data-ttu-id="1bd5d-167">**Notes**</span><span class="sxs-lookup"><span data-stu-id="1bd5d-167">**Notes**</span></span><br><span data-ttu-id="1bd5d-168">mshr_note</span><span class="sxs-lookup"><span data-stu-id="1bd5d-168">mshr_note</span></span><br><span data-ttu-id="1bd5d-169">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="1bd5d-169">*String*</span></span> | <span data-ttu-id="1bd5d-170">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="1bd5d-170">Read/write</span></span><br><span data-ttu-id="1bd5d-171">Facultatif</span><span class="sxs-lookup"><span data-stu-id="1bd5d-171">Optional</span></span> | <span data-ttu-id="1bd5d-172">Notes à l'intention des recruteurs et des responsables du recrutement.</span><span class="sxs-lookup"><span data-stu-id="1bd5d-172">Notes for use by hiring managers and recruiters.</span></span> |

## <a name="see-also"></a><span data-ttu-id="1bd5d-173">Voir également :</span><span class="sxs-lookup"><span data-stu-id="1bd5d-173">See also</span></span>

[<span data-ttu-id="1bd5d-174">Introduction à l'API d'intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="1bd5d-174">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="1bd5d-175">Exemple de requête pour l'entité Candidat à l'embauche</span><span class="sxs-lookup"><span data-stu-id="1bd5d-175">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

