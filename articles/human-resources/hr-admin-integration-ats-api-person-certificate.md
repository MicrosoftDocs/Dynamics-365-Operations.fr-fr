---
title: Certificat de la personne
description: Cette rubrique décrit l’entité Certificat de la personne pour Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 796a57a5f97de08ff8c8440bc00d4dc5ced18f58
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798127"
---
# <a name="person-certificate"></a><span data-ttu-id="4a669-103">Certificat de la personne</span><span class="sxs-lookup"><span data-stu-id="4a669-103">Person certificate</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="4a669-104">Cette rubrique décrit l’entité Certificat de la personne pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4a669-104">This topic describes the Person certificate entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="4a669-105">Nom physique : mshr_hcmpersoncertificateentity</span><span class="sxs-lookup"><span data-stu-id="4a669-105">Physical name: mshr_hcmpersoncertificateentity</span></span>

## <a name="description"></a><span data-ttu-id="4a669-106">Description</span><span class="sxs-lookup"><span data-stu-id="4a669-106">Description</span></span>

<span data-ttu-id="4a669-107">Cette entité décrit les certificats professionnels d’un candidat.</span><span class="sxs-lookup"><span data-stu-id="4a669-107">This entity describes the professional certificates of a candidate.</span></span>

## <a name="json-representation"></a><span data-ttu-id="4a669-108">Représentation JSON</span><span class="sxs-lookup"><span data-stu-id="4a669-108">JSON representation</span></span>

```json
{
    "mshr_certificatetypeid": "String",
    "mshr_startdate": "Date",
    "mshr_enddate": "Date",
    "mshr_notes": "String",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_certificatetype_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersoncertificateentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="4a669-109">Propriétés</span><span class="sxs-lookup"><span data-stu-id="4a669-109">Properties</span></span>

| <span data-ttu-id="4a669-110">Propriété</span><span class="sxs-lookup"><span data-stu-id="4a669-110">Property</span></span><br><span data-ttu-id="4a669-111">**Nom physique**</span><span class="sxs-lookup"><span data-stu-id="4a669-111">**Physical name**</span></span><br><span data-ttu-id="4a669-112">**_Type_**</span><span class="sxs-lookup"><span data-stu-id="4a669-112">**_Type_**</span></span> | <span data-ttu-id="4a669-113">Cas d’emploi</span><span class="sxs-lookup"><span data-stu-id="4a669-113">Use</span></span> | <span data-ttu-id="4a669-114">Description</span><span class="sxs-lookup"><span data-stu-id="4a669-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="4a669-115">**ID d’entité de certificat de la personne**</span><span class="sxs-lookup"><span data-stu-id="4a669-115">**Person Certificate Entity ID**</span></span><br><span data-ttu-id="4a669-116">mshr_hcmpersoncertificateentityid</span><span class="sxs-lookup"><span data-stu-id="4a669-116">mshr_hcmpersoncertificateentityid</span></span><br><span data-ttu-id="4a669-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="4a669-117">*GUID*</span></span> | <span data-ttu-id="4a669-118">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="4a669-118">Read-only</span></span><br><span data-ttu-id="4a669-119">Requis</span><span class="sxs-lookup"><span data-stu-id="4a669-119">Required</span></span> | <span data-ttu-id="4a669-120">Identificateur unique généré par le système pour le dossier d’entité de certificat de la personne.</span><span class="sxs-lookup"><span data-stu-id="4a669-120">System-generated unique identifier for the person certificate entity record.</span></span> |
| <span data-ttu-id="4a669-121">**Numéro tiers**</span><span class="sxs-lookup"><span data-stu-id="4a669-121">**Party Number**</span></span><br><span data-ttu-id="4a669-122">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="4a669-122">mshr_partynumber</span></span><br><span data-ttu-id="4a669-123">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="4a669-123">*String*</span></span> | <span data-ttu-id="4a669-124">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="4a669-124">Read/write</span></span><br><span data-ttu-id="4a669-125">Requis</span><span class="sxs-lookup"><span data-stu-id="4a669-125">Required</span></span> | <span data-ttu-id="4a669-126">ID de tiers (personne) du candidat.</span><span class="sxs-lookup"><span data-stu-id="4a669-126">The party (person) ID of the candidate.</span></span> |
| <span data-ttu-id="4a669-127">**Valeur de l’ID de personne**</span><span class="sxs-lookup"><span data-stu-id="4a669-127">**Person ID Value**</span></span><br><span data-ttu-id="4a669-128">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="4a669-128">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="4a669-129">*GUID*</span><span class="sxs-lookup"><span data-stu-id="4a669-129">*GUID*</span></span> | <span data-ttu-id="4a669-130">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="4a669-130">Read-only</span></span><br><span data-ttu-id="4a669-131">Requis</span><span class="sxs-lookup"><span data-stu-id="4a669-131">Required</span></span><br><span data-ttu-id="4a669-132">Clé étrangère : mshr_dirpersonentityid de l’entité mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="4a669-132">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="4a669-133">Identificateur généré par le système de l’enregistrement de l’entité de tiers (personne).</span><span class="sxs-lookup"><span data-stu-id="4a669-133">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="4a669-134">**ID de type de certificat**</span><span class="sxs-lookup"><span data-stu-id="4a669-134">**Certificate Type ID**</span></span><br><span data-ttu-id="4a669-135">mshr_certificatetypeid</span><span class="sxs-lookup"><span data-stu-id="4a669-135">mshr_certificatetypeid</span></span><br><span data-ttu-id="4a669-136">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="4a669-136">*String*</span></span> | <span data-ttu-id="4a669-137">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="4a669-137">Read/write</span></span><br><span data-ttu-id="4a669-138">Requis</span><span class="sxs-lookup"><span data-stu-id="4a669-138">Required</span></span> |  <span data-ttu-id="4a669-139">Identifiant du type de certificat défini dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4a669-139">The identifier of the certificate type defined in Human Resources.</span></span> |
| <span data-ttu-id="4a669-140">**Valeur de l’ID de type de certificat**</span><span class="sxs-lookup"><span data-stu-id="4a669-140">**Certificate Type ID Value**</span></span><br><span data-ttu-id="4a669-141">_mshr_fk_certificatetype_id_value</span><span class="sxs-lookup"><span data-stu-id="4a669-141">_mshr_fk_certificatetype_id_value</span></span><br><span data-ttu-id="4a669-142">*GUID*</span><span class="sxs-lookup"><span data-stu-id="4a669-142">*GUID*</span></span> | <span data-ttu-id="4a669-143">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="4a669-143">Read-only</span></span><br><span data-ttu-id="4a669-144">Requis</span><span class="sxs-lookup"><span data-stu-id="4a669-144">Required</span></span><br><span data-ttu-id="4a669-145">Clé étrangère : mshr_hcmcertificatetypeentityid de l’entité mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="4a669-145">Foreign key: mshr_hcmcertificatetypeentityid of mshr_hcmcertificatetypeentity</span></span> | <span data-ttu-id="4a669-146">Identificateur unique généré par le système du type de certificat de l’entité associée.</span><span class="sxs-lookup"><span data-stu-id="4a669-146">System-generated unique identifier of the certificate type in the associated entity.</span></span> |
| <span data-ttu-id="4a669-147">**Date de début**</span><span class="sxs-lookup"><span data-stu-id="4a669-147">**Start Date**</span></span><br><span data-ttu-id="4a669-148">mshr_startdate</span><span class="sxs-lookup"><span data-stu-id="4a669-148">mshr_startdate</span></span><br><span data-ttu-id="4a669-149">*DateHeure*</span><span class="sxs-lookup"><span data-stu-id="4a669-149">*Datetime*</span></span> | <span data-ttu-id="4a669-150">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="4a669-150">Read/write</span></span><br><span data-ttu-id="4a669-151">Requis</span><span class="sxs-lookup"><span data-stu-id="4a669-151">Required</span></span> | <span data-ttu-id="4a669-152">Date à laquelle le certificat a été délivré.</span><span class="sxs-lookup"><span data-stu-id="4a669-152">The date at which the certificate was issued.</span></span> |
| <span data-ttu-id="4a669-153">**Date de fin**</span><span class="sxs-lookup"><span data-stu-id="4a669-153">**End Date**</span></span><br><span data-ttu-id="4a669-154">mshr_enddate</span><span class="sxs-lookup"><span data-stu-id="4a669-154">mshr_enddate</span></span><br><span data-ttu-id="4a669-155">*DateHeure*</span><span class="sxs-lookup"><span data-stu-id="4a669-155">*Datetime*</span></span> | <span data-ttu-id="4a669-156">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="4a669-156">Read/write</span></span><br><span data-ttu-id="4a669-157">Facultatif</span><span class="sxs-lookup"><span data-stu-id="4a669-157">Optional</span></span> | <span data-ttu-id="4a669-158">Date à laquelle le certificat va expirer.</span><span class="sxs-lookup"><span data-stu-id="4a669-158">The date at which the certificate will expire.</span></span> |
| <span data-ttu-id="4a669-159">**Notes**</span><span class="sxs-lookup"><span data-stu-id="4a669-159">**Notes**</span></span><br><span data-ttu-id="4a669-160">mshr_notes</span><span class="sxs-lookup"><span data-stu-id="4a669-160">mshr_notes</span></span><br><span data-ttu-id="4a669-161">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="4a669-161">*String*</span></span> | <span data-ttu-id="4a669-162">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="4a669-162">Read/write</span></span><br><span data-ttu-id="4a669-163">Facultatif</span><span class="sxs-lookup"><span data-stu-id="4a669-163">Optional</span></span> | <span data-ttu-id="4a669-164">Notes à l’intention des recruteurs et des responsables du recrutement.</span><span class="sxs-lookup"><span data-stu-id="4a669-164">Notes for use by hiring managers and recruiters.</span></span> |
| <span data-ttu-id="4a669-165">**Champ primaire**</span><span class="sxs-lookup"><span data-stu-id="4a669-165">**Primary Field**</span></span><br><span data-ttu-id="4a669-166">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="4a669-166">mshr_primaryfield</span></span><br><span data-ttu-id="4a669-167">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="4a669-167">*String*</span></span> | <span data-ttu-id="4a669-168">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="4a669-168">Read-only</span></span><br><span data-ttu-id="4a669-169">Requis</span><span class="sxs-lookup"><span data-stu-id="4a669-169">Required</span></span> |  <span data-ttu-id="4a669-170">Champ à utiliser comme identifiant principal de l’enregistrement d’entité.</span><span class="sxs-lookup"><span data-stu-id="4a669-170">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="4a669-171">Combinaison du numéro de tiers, de l’ID du type de certificat et de la date de début.</span><span class="sxs-lookup"><span data-stu-id="4a669-171">Combination of party number, certificate type ID, and start date.</span></span> |

## <a name="see-also"></a><span data-ttu-id="4a669-172">Voir également :</span><span class="sxs-lookup"><span data-stu-id="4a669-172">See also</span></span>

[<span data-ttu-id="4a669-173">Introduction à l’API d’intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="4a669-173">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="4a669-174">Exemple de requête pour l’entité Candidat à l’embauche</span><span class="sxs-lookup"><span data-stu-id="4a669-174">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]