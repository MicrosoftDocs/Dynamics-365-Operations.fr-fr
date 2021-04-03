---
title: Niveau de classement
description: Cette rubrique décrit l’entité Niveau de classement pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 2dbdbea7087d8bca8563da10d1bf9a97df24e8b3
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464740"
---
# <a name="rating-level"></a><span data-ttu-id="39a7c-103">Niveau de classement</span><span class="sxs-lookup"><span data-stu-id="39a7c-103">Rating level</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="39a7c-104">Cette rubrique décrit l’entité Niveau de classement pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="39a7c-104">This topic describes the Rating level entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="39a7c-105">Nom physique : mshr_hcmratinglevelentity</span><span class="sxs-lookup"><span data-stu-id="39a7c-105">Physical name: mshr_hcmratinglevelentity</span></span>

## <a name="description"></a><span data-ttu-id="39a7c-106">Description</span><span class="sxs-lookup"><span data-stu-id="39a7c-106">Description</span></span>

<span data-ttu-id="39a7c-107">Cette entité fournit les niveaux de notation disponibles pour les compétences.</span><span class="sxs-lookup"><span data-stu-id="39a7c-107">This entity provides the available rating levels for skills.</span></span> <span data-ttu-id="39a7c-108">Les niveaux de notation s’appliquent à toutes les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="39a7c-108">Rating levels apply across all legal entities.</span></span>

## <a name="json-representation"></a><span data-ttu-id="39a7c-109">Représentation JSON</span><span class="sxs-lookup"><span data-stu-id="39a7c-109">JSON representation</span></span>

```json
{
    "mshr_description": "String",
    "mshr_factor": Int,
    "mshr_note": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_ratingmodelentity_id_value": "Guid",
    "mshr_hcmratinglevelentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="39a7c-110">Propriétés</span><span class="sxs-lookup"><span data-stu-id="39a7c-110">Properties</span></span>

| <span data-ttu-id="39a7c-111">Propriété</span><span class="sxs-lookup"><span data-stu-id="39a7c-111">Property</span></span><br><span data-ttu-id="39a7c-112">**Nom physique**</span><span class="sxs-lookup"><span data-stu-id="39a7c-112">**Physical name**</span></span><br><span data-ttu-id="39a7c-113">**_Type_**</span><span class="sxs-lookup"><span data-stu-id="39a7c-113">**_Type_**</span></span> | <span data-ttu-id="39a7c-114">Cas d’emploi</span><span class="sxs-lookup"><span data-stu-id="39a7c-114">Use</span></span> | <span data-ttu-id="39a7c-115">Description</span><span class="sxs-lookup"><span data-stu-id="39a7c-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="39a7c-116">**ID d’entité de niveau de notation**</span><span class="sxs-lookup"><span data-stu-id="39a7c-116">**Rating Level Entity ID**</span></span><br><span data-ttu-id="39a7c-117">mshr_hcmratinglevelentityid</span><span class="sxs-lookup"><span data-stu-id="39a7c-117">mshr_hcmratinglevelentityid</span></span><br><span data-ttu-id="39a7c-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="39a7c-118">*GUID*</span></span> | <span data-ttu-id="39a7c-119">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="39a7c-119">Read-only</span></span><br><span data-ttu-id="39a7c-120">Requis</span><span class="sxs-lookup"><span data-stu-id="39a7c-120">Required</span></span><br><span data-ttu-id="39a7c-121">Généré par le système</span><span class="sxs-lookup"><span data-stu-id="39a7c-121">System-generated</span></span> | <span data-ttu-id="39a7c-122">Identificateur unique généré par le système pour le niveau.</span><span class="sxs-lookup"><span data-stu-id="39a7c-122">The system-generated unique identifier for the level.</span></span> |
| <span data-ttu-id="39a7c-123">**ID de niveau de classement**</span><span class="sxs-lookup"><span data-stu-id="39a7c-123">**Rating Level ID**</span></span><br><span data-ttu-id="39a7c-124">mshr_ratinglevelid</span><span class="sxs-lookup"><span data-stu-id="39a7c-124">mshr_ratinglevelid</span></span><br><span data-ttu-id="39a7c-125">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="39a7c-125">*String*</span></span> | <span data-ttu-id="39a7c-126">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="39a7c-126">Read/write</span></span><br><span data-ttu-id="39a7c-127">Requis</span><span class="sxs-lookup"><span data-stu-id="39a7c-127">Required</span></span> | <span data-ttu-id="39a7c-128">Identificateur unique lisible par l’utilisateur pour le niveau.</span><span class="sxs-lookup"><span data-stu-id="39a7c-128">User-readable unique identifier for the level.</span></span> |
| <span data-ttu-id="39a7c-129">**ID de modèle de classement**</span><span class="sxs-lookup"><span data-stu-id="39a7c-129">**Rating Model ID**</span></span><br><span data-ttu-id="39a7c-130">mshr_ratingmodelid</span><span class="sxs-lookup"><span data-stu-id="39a7c-130">mshr_ratingmodelid</span></span><br><span data-ttu-id="39a7c-131">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="39a7c-131">*String*</span></span> | <span data-ttu-id="39a7c-132">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="39a7c-132">Read/write</span></span><br><span data-ttu-id="39a7c-133">Requis</span><span class="sxs-lookup"><span data-stu-id="39a7c-133">Required</span></span> | <span data-ttu-id="39a7c-134">Modèle de classement auquel appartient le niveau de classement.</span><span class="sxs-lookup"><span data-stu-id="39a7c-134">The rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="39a7c-135">**ID d’entité de modèle de classement**</span><span class="sxs-lookup"><span data-stu-id="39a7c-135">**Rating Model Entity ID**</span></span><br><span data-ttu-id="39a7c-136">_mshr_fk_ratingmodelentity_id_value</span><span class="sxs-lookup"><span data-stu-id="39a7c-136">_mshr_fk_ratingmodelentity_id_value</span></span><br><span data-ttu-id="39a7c-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="39a7c-137">*GUID*</span></span> | <span data-ttu-id="39a7c-138">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="39a7c-138">Read-only</span></span><br><span data-ttu-id="39a7c-139">Requis</span><span class="sxs-lookup"><span data-stu-id="39a7c-139">Required</span></span><br><span data-ttu-id="39a7c-140">Clé étrangère : mshr_hcmratingmodelentityid de l’entité mshr_hcmratingmodelentity</span><span class="sxs-lookup"><span data-stu-id="39a7c-140">Foreign key: mshr_hcmratingmodelentityid of mshr_hcmratingmodelentity</span></span> | <span data-ttu-id="39a7c-141">Identificateur généré par le système pour le modèle d’évaluation auquel appartient le niveau d’évaluation.</span><span class="sxs-lookup"><span data-stu-id="39a7c-141">The system-generated identifier for the rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="39a7c-142">**Description**</span><span class="sxs-lookup"><span data-stu-id="39a7c-142">**Description**</span></span><br><span data-ttu-id="39a7c-143">mshr_description</span><span class="sxs-lookup"><span data-stu-id="39a7c-143">mshr_description</span></span><br><span data-ttu-id="39a7c-144">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="39a7c-144">*String*</span></span> | <span data-ttu-id="39a7c-145">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="39a7c-145">Read/write</span></span><br><span data-ttu-id="39a7c-146">Requis</span><span class="sxs-lookup"><span data-stu-id="39a7c-146">Required</span></span> | <span data-ttu-id="39a7c-147">Description du niveau de classement.</span><span class="sxs-lookup"><span data-stu-id="39a7c-147">The description of the rating level.</span></span> |
| <span data-ttu-id="39a7c-148">**Facteur**</span><span class="sxs-lookup"><span data-stu-id="39a7c-148">**Factor**</span></span><br><span data-ttu-id="39a7c-149">mshr_factor</span><span class="sxs-lookup"><span data-stu-id="39a7c-149">mshr_factor</span></span><br><span data-ttu-id="39a7c-150">*Entier*</span><span class="sxs-lookup"><span data-stu-id="39a7c-150">*Integer*</span></span> | <span data-ttu-id="39a7c-151">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="39a7c-151">Read/write</span></span><br><span data-ttu-id="39a7c-152">Requis</span><span class="sxs-lookup"><span data-stu-id="39a7c-152">Required</span></span> | <span data-ttu-id="39a7c-153">Facteur pour le niveau de classement.</span><span class="sxs-lookup"><span data-stu-id="39a7c-153">The factor for the rating level.</span></span> <span data-ttu-id="39a7c-154">Lorsque vous comparez des articles avec un autre nombre de niveaux de classement, le facteur permet de normaliser les scores.</span><span class="sxs-lookup"><span data-stu-id="39a7c-154">When you compare items with a different number of rating levels, the factor is used to normalize the scores.</span></span> <span data-ttu-id="39a7c-155">La valeur doit être un entier compris entre 0 et 9.</span><span class="sxs-lookup"><span data-stu-id="39a7c-155">The value must be an integer between 0 and 9.</span></span> |
| <span data-ttu-id="39a7c-156">**Remarque**</span><span class="sxs-lookup"><span data-stu-id="39a7c-156">**Note**</span></span><br><span data-ttu-id="39a7c-157">mshr_note</span><span class="sxs-lookup"><span data-stu-id="39a7c-157">mshr_note</span></span><br><span data-ttu-id="39a7c-158">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="39a7c-158">*String*</span></span> | <span data-ttu-id="39a7c-159">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="39a7c-159">Read/write</span></span><br><span data-ttu-id="39a7c-160">Facultatif</span><span class="sxs-lookup"><span data-stu-id="39a7c-160">Optional</span></span> | <span data-ttu-id="39a7c-161">Toutes les notes associées au niveau de classement.</span><span class="sxs-lookup"><span data-stu-id="39a7c-161">Any notes associated with the rating level.</span></span> |
| <span data-ttu-id="39a7c-162">**Champ primaire**</span><span class="sxs-lookup"><span data-stu-id="39a7c-162">**Primary Field**</span></span><br><span data-ttu-id="39a7c-163">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="39a7c-163">mshr_primaryfield</span></span><br><span data-ttu-id="39a7c-164">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="39a7c-164">*String*</span></span> | <span data-ttu-id="39a7c-165">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="39a7c-165">Read-only</span></span><br><span data-ttu-id="39a7c-166">Requis</span><span class="sxs-lookup"><span data-stu-id="39a7c-166">Required</span></span> | <span data-ttu-id="39a7c-167">Champ à utiliser comme identifiant principal de l’enregistrement d’entité.</span><span class="sxs-lookup"><span data-stu-id="39a7c-167">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="39a7c-168">Combinaison de l’ID du niveau de classification et de l’ID du modèle de classement.</span><span class="sxs-lookup"><span data-stu-id="39a7c-168">Combination of rating level ID and rating model ID.</span></span> |

## <a name="see-also"></a><span data-ttu-id="39a7c-169">Voir également :</span><span class="sxs-lookup"><span data-stu-id="39a7c-169">See also</span></span>

[<span data-ttu-id="39a7c-170">Introduction à l’API d’intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="39a7c-170">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="39a7c-171">Exemple de requête pour l’entité Candidat à l’embauche</span><span class="sxs-lookup"><span data-stu-id="39a7c-171">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]