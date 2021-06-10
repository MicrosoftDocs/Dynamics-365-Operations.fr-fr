---
title: Niveau de classement
description: Cette rubrique décrit l’entité Niveau de classement pour Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8bbd10bcc47a928070da7cd82e6d996f71c65698
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054834"
---
# <a name="rating-level"></a><span data-ttu-id="65b3f-103">Niveau de classement</span><span class="sxs-lookup"><span data-stu-id="65b3f-103">Rating level</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="65b3f-104">Cette rubrique décrit l’entité Niveau de classement pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="65b3f-104">This topic describes the Rating level entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="65b3f-105">Nom physique : mshr_hcmratinglevelentity</span><span class="sxs-lookup"><span data-stu-id="65b3f-105">Physical name: mshr_hcmratinglevelentity</span></span>

## <a name="description"></a><span data-ttu-id="65b3f-106">Description</span><span class="sxs-lookup"><span data-stu-id="65b3f-106">Description</span></span>

<span data-ttu-id="65b3f-107">Cette entité fournit les niveaux de notation disponibles pour les compétences.</span><span class="sxs-lookup"><span data-stu-id="65b3f-107">This entity provides the available rating levels for skills.</span></span> <span data-ttu-id="65b3f-108">Les niveaux de notation s’appliquent à toutes les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="65b3f-108">Rating levels apply across all legal entities.</span></span>

## <a name="json-representation"></a><span data-ttu-id="65b3f-109">Représentation JSON</span><span class="sxs-lookup"><span data-stu-id="65b3f-109">JSON representation</span></span>

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

## <a name="properties"></a><span data-ttu-id="65b3f-110">Propriétés</span><span class="sxs-lookup"><span data-stu-id="65b3f-110">Properties</span></span>

| <span data-ttu-id="65b3f-111">Propriété</span><span class="sxs-lookup"><span data-stu-id="65b3f-111">Property</span></span><br><span data-ttu-id="65b3f-112">**Nom physique**</span><span class="sxs-lookup"><span data-stu-id="65b3f-112">**Physical name**</span></span><br><span data-ttu-id="65b3f-113">**_Type_**</span><span class="sxs-lookup"><span data-stu-id="65b3f-113">**_Type_**</span></span> | <span data-ttu-id="65b3f-114">Cas d’emploi</span><span class="sxs-lookup"><span data-stu-id="65b3f-114">Use</span></span> | <span data-ttu-id="65b3f-115">Description</span><span class="sxs-lookup"><span data-stu-id="65b3f-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="65b3f-116">**ID d’entité de niveau de notation**</span><span class="sxs-lookup"><span data-stu-id="65b3f-116">**Rating Level Entity ID**</span></span><br><span data-ttu-id="65b3f-117">mshr_hcmratinglevelentityid</span><span class="sxs-lookup"><span data-stu-id="65b3f-117">mshr_hcmratinglevelentityid</span></span><br><span data-ttu-id="65b3f-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="65b3f-118">*GUID*</span></span> | <span data-ttu-id="65b3f-119">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="65b3f-119">Read-only</span></span><br><span data-ttu-id="65b3f-120">Requis</span><span class="sxs-lookup"><span data-stu-id="65b3f-120">Required</span></span><br><span data-ttu-id="65b3f-121">Généré par le système</span><span class="sxs-lookup"><span data-stu-id="65b3f-121">System-generated</span></span> | <span data-ttu-id="65b3f-122">Identificateur unique généré par le système pour le niveau.</span><span class="sxs-lookup"><span data-stu-id="65b3f-122">The system-generated unique identifier for the level.</span></span> |
| <span data-ttu-id="65b3f-123">**ID de niveau de classement**</span><span class="sxs-lookup"><span data-stu-id="65b3f-123">**Rating Level ID**</span></span><br><span data-ttu-id="65b3f-124">mshr_ratinglevelid</span><span class="sxs-lookup"><span data-stu-id="65b3f-124">mshr_ratinglevelid</span></span><br><span data-ttu-id="65b3f-125">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="65b3f-125">*String*</span></span> | <span data-ttu-id="65b3f-126">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="65b3f-126">Read/write</span></span><br><span data-ttu-id="65b3f-127">Requis</span><span class="sxs-lookup"><span data-stu-id="65b3f-127">Required</span></span> | <span data-ttu-id="65b3f-128">Identificateur unique lisible par l’utilisateur pour le niveau.</span><span class="sxs-lookup"><span data-stu-id="65b3f-128">User-readable unique identifier for the level.</span></span> |
| <span data-ttu-id="65b3f-129">**ID de modèle de classement**</span><span class="sxs-lookup"><span data-stu-id="65b3f-129">**Rating Model ID**</span></span><br><span data-ttu-id="65b3f-130">mshr_ratingmodelid</span><span class="sxs-lookup"><span data-stu-id="65b3f-130">mshr_ratingmodelid</span></span><br><span data-ttu-id="65b3f-131">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="65b3f-131">*String*</span></span> | <span data-ttu-id="65b3f-132">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="65b3f-132">Read/write</span></span><br><span data-ttu-id="65b3f-133">Requis</span><span class="sxs-lookup"><span data-stu-id="65b3f-133">Required</span></span> | <span data-ttu-id="65b3f-134">Modèle de classement auquel appartient le niveau de classement.</span><span class="sxs-lookup"><span data-stu-id="65b3f-134">The rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="65b3f-135">**ID d’entité de modèle de classement**</span><span class="sxs-lookup"><span data-stu-id="65b3f-135">**Rating Model Entity ID**</span></span><br><span data-ttu-id="65b3f-136">_mshr_fk_ratingmodelentity_id_value</span><span class="sxs-lookup"><span data-stu-id="65b3f-136">_mshr_fk_ratingmodelentity_id_value</span></span><br><span data-ttu-id="65b3f-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="65b3f-137">*GUID*</span></span> | <span data-ttu-id="65b3f-138">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="65b3f-138">Read-only</span></span><br><span data-ttu-id="65b3f-139">Requis</span><span class="sxs-lookup"><span data-stu-id="65b3f-139">Required</span></span><br><span data-ttu-id="65b3f-140">Clé étrangère : mshr_hcmratingmodelentityid de l’entité mshr_hcmratingmodelentity</span><span class="sxs-lookup"><span data-stu-id="65b3f-140">Foreign key: mshr_hcmratingmodelentityid of mshr_hcmratingmodelentity</span></span> | <span data-ttu-id="65b3f-141">Identificateur généré par le système pour le modèle d’évaluation auquel appartient le niveau d’évaluation.</span><span class="sxs-lookup"><span data-stu-id="65b3f-141">The system-generated identifier for the rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="65b3f-142">**Description**</span><span class="sxs-lookup"><span data-stu-id="65b3f-142">**Description**</span></span><br><span data-ttu-id="65b3f-143">mshr_description</span><span class="sxs-lookup"><span data-stu-id="65b3f-143">mshr_description</span></span><br><span data-ttu-id="65b3f-144">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="65b3f-144">*String*</span></span> | <span data-ttu-id="65b3f-145">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="65b3f-145">Read/write</span></span><br><span data-ttu-id="65b3f-146">Requis</span><span class="sxs-lookup"><span data-stu-id="65b3f-146">Required</span></span> | <span data-ttu-id="65b3f-147">Description du niveau de classement.</span><span class="sxs-lookup"><span data-stu-id="65b3f-147">The description of the rating level.</span></span> |
| <span data-ttu-id="65b3f-148">**Facteur**</span><span class="sxs-lookup"><span data-stu-id="65b3f-148">**Factor**</span></span><br><span data-ttu-id="65b3f-149">mshr_factor</span><span class="sxs-lookup"><span data-stu-id="65b3f-149">mshr_factor</span></span><br><span data-ttu-id="65b3f-150">*Entier*</span><span class="sxs-lookup"><span data-stu-id="65b3f-150">*Integer*</span></span> | <span data-ttu-id="65b3f-151">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="65b3f-151">Read/write</span></span><br><span data-ttu-id="65b3f-152">Requis</span><span class="sxs-lookup"><span data-stu-id="65b3f-152">Required</span></span> | <span data-ttu-id="65b3f-153">Facteur pour le niveau de classement.</span><span class="sxs-lookup"><span data-stu-id="65b3f-153">The factor for the rating level.</span></span> <span data-ttu-id="65b3f-154">Lorsque vous comparez des articles avec un autre nombre de niveaux de classement, le facteur permet de normaliser les scores.</span><span class="sxs-lookup"><span data-stu-id="65b3f-154">When you compare items with a different number of rating levels, the factor is used to normalize the scores.</span></span> <span data-ttu-id="65b3f-155">La valeur doit être un entier compris entre 0 et 9.</span><span class="sxs-lookup"><span data-stu-id="65b3f-155">The value must be an integer between 0 and 9.</span></span> |
| <span data-ttu-id="65b3f-156">**Remarque**</span><span class="sxs-lookup"><span data-stu-id="65b3f-156">**Note**</span></span><br><span data-ttu-id="65b3f-157">mshr_note</span><span class="sxs-lookup"><span data-stu-id="65b3f-157">mshr_note</span></span><br><span data-ttu-id="65b3f-158">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="65b3f-158">*String*</span></span> | <span data-ttu-id="65b3f-159">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="65b3f-159">Read/write</span></span><br><span data-ttu-id="65b3f-160">Facultatif</span><span class="sxs-lookup"><span data-stu-id="65b3f-160">Optional</span></span> | <span data-ttu-id="65b3f-161">Toutes les notes associées au niveau de classement.</span><span class="sxs-lookup"><span data-stu-id="65b3f-161">Any notes associated with the rating level.</span></span> |
| <span data-ttu-id="65b3f-162">**Champ primaire**</span><span class="sxs-lookup"><span data-stu-id="65b3f-162">**Primary Field**</span></span><br><span data-ttu-id="65b3f-163">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="65b3f-163">mshr_primaryfield</span></span><br><span data-ttu-id="65b3f-164">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="65b3f-164">*String*</span></span> | <span data-ttu-id="65b3f-165">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="65b3f-165">Read-only</span></span><br><span data-ttu-id="65b3f-166">Requis</span><span class="sxs-lookup"><span data-stu-id="65b3f-166">Required</span></span> | <span data-ttu-id="65b3f-167">Champ à utiliser comme identifiant principal de l’enregistrement d’entité.</span><span class="sxs-lookup"><span data-stu-id="65b3f-167">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="65b3f-168">Combinaison de l’ID du niveau de classification et de l’ID du modèle de classement.</span><span class="sxs-lookup"><span data-stu-id="65b3f-168">Combination of rating level ID and rating model ID.</span></span> |

## <a name="see-also"></a><span data-ttu-id="65b3f-169">Voir également :</span><span class="sxs-lookup"><span data-stu-id="65b3f-169">See also</span></span>

[<span data-ttu-id="65b3f-170">Introduction à l’API d’intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="65b3f-170">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="65b3f-171">Exemple de requête pour l’entité Candidat à l’embauche</span><span class="sxs-lookup"><span data-stu-id="65b3f-171">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]