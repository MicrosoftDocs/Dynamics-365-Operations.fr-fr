---
title: Niveau de classement
description: Cette rubrique décrit l'entité Niveau de classement pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 1ad37c7a5b961bb03d37775168dac91e606d2b08
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125255"
---
# <a name="rating-level"></a><span data-ttu-id="02588-103">Niveau de classement</span><span class="sxs-lookup"><span data-stu-id="02588-103">Rating level</span></span>

<span data-ttu-id="02588-104">Cette rubrique décrit l'entité Niveau de classement pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="02588-104">This topic describes the Rating level entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="02588-105">Nom physique : mshr_hcmratinglevelentity</span><span class="sxs-lookup"><span data-stu-id="02588-105">Physical name: mshr_hcmratinglevelentity</span></span>

## <a name="description"></a><span data-ttu-id="02588-106">Description</span><span class="sxs-lookup"><span data-stu-id="02588-106">Description</span></span>

<span data-ttu-id="02588-107">Cette entité fournit les niveaux de notation disponibles pour les compétences.</span><span class="sxs-lookup"><span data-stu-id="02588-107">This entity provides the available rating levels for skills.</span></span> <span data-ttu-id="02588-108">Les niveaux de notation s'appliquent à toutes les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="02588-108">Rating levels apply across all legal entities.</span></span>

## <a name="json-representation"></a><span data-ttu-id="02588-109">Représentation JSON</span><span class="sxs-lookup"><span data-stu-id="02588-109">JSON representation</span></span>

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

## <a name="properties"></a><span data-ttu-id="02588-110">Propriétés</span><span class="sxs-lookup"><span data-stu-id="02588-110">Properties</span></span>

| <span data-ttu-id="02588-111">Propriété</span><span class="sxs-lookup"><span data-stu-id="02588-111">Property</span></span><br><span data-ttu-id="02588-112">**Nom physique**</span><span class="sxs-lookup"><span data-stu-id="02588-112">**Physical name**</span></span><br><span data-ttu-id="02588-113">**_Type_**</span><span class="sxs-lookup"><span data-stu-id="02588-113">**_Type_**</span></span> | <span data-ttu-id="02588-114">Cas d’emploi</span><span class="sxs-lookup"><span data-stu-id="02588-114">Use</span></span> | <span data-ttu-id="02588-115">Description</span><span class="sxs-lookup"><span data-stu-id="02588-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="02588-116">**ID d'entité de niveau de notation**</span><span class="sxs-lookup"><span data-stu-id="02588-116">**Rating Level Entity ID**</span></span><br><span data-ttu-id="02588-117">mshr_hcmratinglevelentityid</span><span class="sxs-lookup"><span data-stu-id="02588-117">mshr_hcmratinglevelentityid</span></span><br><span data-ttu-id="02588-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="02588-118">*GUID*</span></span> | <span data-ttu-id="02588-119">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="02588-119">Read-only</span></span><br><span data-ttu-id="02588-120">Requis</span><span class="sxs-lookup"><span data-stu-id="02588-120">Required</span></span><br><span data-ttu-id="02588-121">Généré par le système</span><span class="sxs-lookup"><span data-stu-id="02588-121">System-generated</span></span> | <span data-ttu-id="02588-122">Identificateur unique généré par le système pour le niveau.</span><span class="sxs-lookup"><span data-stu-id="02588-122">The system-generated unique identifier for the level.</span></span> |
| <span data-ttu-id="02588-123">**ID de niveau de classement**</span><span class="sxs-lookup"><span data-stu-id="02588-123">**Rating Level ID**</span></span><br><span data-ttu-id="02588-124">mshr_ratinglevelid</span><span class="sxs-lookup"><span data-stu-id="02588-124">mshr_ratinglevelid</span></span><br><span data-ttu-id="02588-125">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="02588-125">*String*</span></span> | <span data-ttu-id="02588-126">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="02588-126">Read/write</span></span><br><span data-ttu-id="02588-127">Requis</span><span class="sxs-lookup"><span data-stu-id="02588-127">Required</span></span> | <span data-ttu-id="02588-128">Identificateur unique lisible par l'utilisateur pour le niveau.</span><span class="sxs-lookup"><span data-stu-id="02588-128">User-readable unique identifier for the level.</span></span> |
| <span data-ttu-id="02588-129">**ID de modèle de classement**</span><span class="sxs-lookup"><span data-stu-id="02588-129">**Rating Model ID**</span></span><br><span data-ttu-id="02588-130">mshr_ratingmodelid</span><span class="sxs-lookup"><span data-stu-id="02588-130">mshr_ratingmodelid</span></span><br><span data-ttu-id="02588-131">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="02588-131">*String*</span></span> | <span data-ttu-id="02588-132">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="02588-132">Read/write</span></span><br><span data-ttu-id="02588-133">Requis</span><span class="sxs-lookup"><span data-stu-id="02588-133">Required</span></span> | <span data-ttu-id="02588-134">Modèle de classement auquel appartient le niveau de classement.</span><span class="sxs-lookup"><span data-stu-id="02588-134">The rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="02588-135">**ID d'entité de modèle de classement**</span><span class="sxs-lookup"><span data-stu-id="02588-135">**Rating Model Entity ID**</span></span><br><span data-ttu-id="02588-136">_mshr_fk_ratingmodelentity_id_value</span><span class="sxs-lookup"><span data-stu-id="02588-136">_mshr_fk_ratingmodelentity_id_value</span></span><br><span data-ttu-id="02588-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="02588-137">*GUID*</span></span> | <span data-ttu-id="02588-138">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="02588-138">Read-only</span></span><br><span data-ttu-id="02588-139">Requis</span><span class="sxs-lookup"><span data-stu-id="02588-139">Required</span></span><br><span data-ttu-id="02588-140">Clé étrangère : mshr_hcmratingmodelentityid de l'entité mshr_hcmratingmodelentity</span><span class="sxs-lookup"><span data-stu-id="02588-140">Foreign key: mshr_hcmratingmodelentityid of mshr_hcmratingmodelentity</span></span> | <span data-ttu-id="02588-141">Identificateur généré par le système pour le modèle d'évaluation auquel appartient le niveau d'évaluation.</span><span class="sxs-lookup"><span data-stu-id="02588-141">The system-generated identifier for the rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="02588-142">**Description**</span><span class="sxs-lookup"><span data-stu-id="02588-142">**Description**</span></span><br><span data-ttu-id="02588-143">mshr_description</span><span class="sxs-lookup"><span data-stu-id="02588-143">mshr_description</span></span><br><span data-ttu-id="02588-144">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="02588-144">*String*</span></span> | <span data-ttu-id="02588-145">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="02588-145">Read/write</span></span><br><span data-ttu-id="02588-146">Requis</span><span class="sxs-lookup"><span data-stu-id="02588-146">Required</span></span> | <span data-ttu-id="02588-147">Description du niveau de classement.</span><span class="sxs-lookup"><span data-stu-id="02588-147">The description of the rating level.</span></span> |
| <span data-ttu-id="02588-148">**Facteur**</span><span class="sxs-lookup"><span data-stu-id="02588-148">**Factor**</span></span><br><span data-ttu-id="02588-149">mshr_factor</span><span class="sxs-lookup"><span data-stu-id="02588-149">mshr_factor</span></span><br><span data-ttu-id="02588-150">*Entier*</span><span class="sxs-lookup"><span data-stu-id="02588-150">*Integer*</span></span> | <span data-ttu-id="02588-151">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="02588-151">Read/write</span></span><br><span data-ttu-id="02588-152">Requis</span><span class="sxs-lookup"><span data-stu-id="02588-152">Required</span></span> | <span data-ttu-id="02588-153">Facteur pour le niveau de classement.</span><span class="sxs-lookup"><span data-stu-id="02588-153">The factor for the rating level.</span></span> <span data-ttu-id="02588-154">Lorsque vous comparez des articles avec un autre nombre de niveaux de classement, le facteur permet de normaliser les scores.</span><span class="sxs-lookup"><span data-stu-id="02588-154">When you compare items with a different number of rating levels, the factor is used to normalize the scores.</span></span> <span data-ttu-id="02588-155">La valeur doit être un entier compris entre 0 et 9.</span><span class="sxs-lookup"><span data-stu-id="02588-155">The value must be an integer between 0 and 9.</span></span> |
| <span data-ttu-id="02588-156">**Remarque**</span><span class="sxs-lookup"><span data-stu-id="02588-156">**Note**</span></span><br><span data-ttu-id="02588-157">mshr_note</span><span class="sxs-lookup"><span data-stu-id="02588-157">mshr_note</span></span><br><span data-ttu-id="02588-158">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="02588-158">*String*</span></span> | <span data-ttu-id="02588-159">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="02588-159">Read/write</span></span><br><span data-ttu-id="02588-160">Facultatif</span><span class="sxs-lookup"><span data-stu-id="02588-160">Optional</span></span> | <span data-ttu-id="02588-161">Toutes les notes associées au niveau de classement.</span><span class="sxs-lookup"><span data-stu-id="02588-161">Any notes associated with the rating level.</span></span> |
| <span data-ttu-id="02588-162">**Champ primaire**</span><span class="sxs-lookup"><span data-stu-id="02588-162">**Primary Field**</span></span><br><span data-ttu-id="02588-163">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="02588-163">mshr_primaryfield</span></span><br><span data-ttu-id="02588-164">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="02588-164">*String*</span></span> | <span data-ttu-id="02588-165">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="02588-165">Read-only</span></span><br><span data-ttu-id="02588-166">Requis</span><span class="sxs-lookup"><span data-stu-id="02588-166">Required</span></span> | <span data-ttu-id="02588-167">Champ à utiliser comme identifiant principal de l'enregistrement d'entité.</span><span class="sxs-lookup"><span data-stu-id="02588-167">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="02588-168">Combinaison de l'ID du niveau de classification et de l'ID du modèle de classement.</span><span class="sxs-lookup"><span data-stu-id="02588-168">Combination of rating level ID and rating model ID.</span></span> |

## <a name="see-also"></a><span data-ttu-id="02588-169">Voir également :</span><span class="sxs-lookup"><span data-stu-id="02588-169">See also</span></span>

[<span data-ttu-id="02588-170">Introduction à l'API d'intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="02588-170">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="02588-171">Exemple de requête pour l'entité Candidat à l'embauche</span><span class="sxs-lookup"><span data-stu-id="02588-171">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

