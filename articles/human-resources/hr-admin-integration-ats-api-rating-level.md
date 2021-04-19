---
title: Niveau de classement
description: Cette rubrique décrit l’entité Niveau de classement pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: eac80599de07a045aa233f1cdfd16fe0db8733a2
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800331"
---
# <a name="rating-level"></a><span data-ttu-id="3bdba-103">Niveau de classement</span><span class="sxs-lookup"><span data-stu-id="3bdba-103">Rating level</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="3bdba-104">Cette rubrique décrit l’entité Niveau de classement pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="3bdba-104">This topic describes the Rating level entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="3bdba-105">Nom physique : mshr_hcmratinglevelentity</span><span class="sxs-lookup"><span data-stu-id="3bdba-105">Physical name: mshr_hcmratinglevelentity</span></span>

## <a name="description"></a><span data-ttu-id="3bdba-106">Description</span><span class="sxs-lookup"><span data-stu-id="3bdba-106">Description</span></span>

<span data-ttu-id="3bdba-107">Cette entité fournit les niveaux de notation disponibles pour les compétences.</span><span class="sxs-lookup"><span data-stu-id="3bdba-107">This entity provides the available rating levels for skills.</span></span> <span data-ttu-id="3bdba-108">Les niveaux de notation s’appliquent à toutes les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="3bdba-108">Rating levels apply across all legal entities.</span></span>

## <a name="json-representation"></a><span data-ttu-id="3bdba-109">Représentation JSON</span><span class="sxs-lookup"><span data-stu-id="3bdba-109">JSON representation</span></span>

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

## <a name="properties"></a><span data-ttu-id="3bdba-110">Propriétés</span><span class="sxs-lookup"><span data-stu-id="3bdba-110">Properties</span></span>

| <span data-ttu-id="3bdba-111">Propriété</span><span class="sxs-lookup"><span data-stu-id="3bdba-111">Property</span></span><br><span data-ttu-id="3bdba-112">**Nom physique**</span><span class="sxs-lookup"><span data-stu-id="3bdba-112">**Physical name**</span></span><br><span data-ttu-id="3bdba-113">**_Type_**</span><span class="sxs-lookup"><span data-stu-id="3bdba-113">**_Type_**</span></span> | <span data-ttu-id="3bdba-114">Cas d’emploi</span><span class="sxs-lookup"><span data-stu-id="3bdba-114">Use</span></span> | <span data-ttu-id="3bdba-115">Description</span><span class="sxs-lookup"><span data-stu-id="3bdba-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="3bdba-116">**ID d’entité de niveau de notation**</span><span class="sxs-lookup"><span data-stu-id="3bdba-116">**Rating Level Entity ID**</span></span><br><span data-ttu-id="3bdba-117">mshr_hcmratinglevelentityid</span><span class="sxs-lookup"><span data-stu-id="3bdba-117">mshr_hcmratinglevelentityid</span></span><br><span data-ttu-id="3bdba-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="3bdba-118">*GUID*</span></span> | <span data-ttu-id="3bdba-119">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="3bdba-119">Read-only</span></span><br><span data-ttu-id="3bdba-120">Requis</span><span class="sxs-lookup"><span data-stu-id="3bdba-120">Required</span></span><br><span data-ttu-id="3bdba-121">Généré par le système</span><span class="sxs-lookup"><span data-stu-id="3bdba-121">System-generated</span></span> | <span data-ttu-id="3bdba-122">Identificateur unique généré par le système pour le niveau.</span><span class="sxs-lookup"><span data-stu-id="3bdba-122">The system-generated unique identifier for the level.</span></span> |
| <span data-ttu-id="3bdba-123">**ID de niveau de classement**</span><span class="sxs-lookup"><span data-stu-id="3bdba-123">**Rating Level ID**</span></span><br><span data-ttu-id="3bdba-124">mshr_ratinglevelid</span><span class="sxs-lookup"><span data-stu-id="3bdba-124">mshr_ratinglevelid</span></span><br><span data-ttu-id="3bdba-125">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="3bdba-125">*String*</span></span> | <span data-ttu-id="3bdba-126">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="3bdba-126">Read/write</span></span><br><span data-ttu-id="3bdba-127">Requis</span><span class="sxs-lookup"><span data-stu-id="3bdba-127">Required</span></span> | <span data-ttu-id="3bdba-128">Identificateur unique lisible par l’utilisateur pour le niveau.</span><span class="sxs-lookup"><span data-stu-id="3bdba-128">User-readable unique identifier for the level.</span></span> |
| <span data-ttu-id="3bdba-129">**ID de modèle de classement**</span><span class="sxs-lookup"><span data-stu-id="3bdba-129">**Rating Model ID**</span></span><br><span data-ttu-id="3bdba-130">mshr_ratingmodelid</span><span class="sxs-lookup"><span data-stu-id="3bdba-130">mshr_ratingmodelid</span></span><br><span data-ttu-id="3bdba-131">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="3bdba-131">*String*</span></span> | <span data-ttu-id="3bdba-132">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="3bdba-132">Read/write</span></span><br><span data-ttu-id="3bdba-133">Requis</span><span class="sxs-lookup"><span data-stu-id="3bdba-133">Required</span></span> | <span data-ttu-id="3bdba-134">Modèle de classement auquel appartient le niveau de classement.</span><span class="sxs-lookup"><span data-stu-id="3bdba-134">The rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="3bdba-135">**ID d’entité de modèle de classement**</span><span class="sxs-lookup"><span data-stu-id="3bdba-135">**Rating Model Entity ID**</span></span><br><span data-ttu-id="3bdba-136">_mshr_fk_ratingmodelentity_id_value</span><span class="sxs-lookup"><span data-stu-id="3bdba-136">_mshr_fk_ratingmodelentity_id_value</span></span><br><span data-ttu-id="3bdba-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="3bdba-137">*GUID*</span></span> | <span data-ttu-id="3bdba-138">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="3bdba-138">Read-only</span></span><br><span data-ttu-id="3bdba-139">Requis</span><span class="sxs-lookup"><span data-stu-id="3bdba-139">Required</span></span><br><span data-ttu-id="3bdba-140">Clé étrangère : mshr_hcmratingmodelentityid de l’entité mshr_hcmratingmodelentity</span><span class="sxs-lookup"><span data-stu-id="3bdba-140">Foreign key: mshr_hcmratingmodelentityid of mshr_hcmratingmodelentity</span></span> | <span data-ttu-id="3bdba-141">Identificateur généré par le système pour le modèle d’évaluation auquel appartient le niveau d’évaluation.</span><span class="sxs-lookup"><span data-stu-id="3bdba-141">The system-generated identifier for the rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="3bdba-142">**Description**</span><span class="sxs-lookup"><span data-stu-id="3bdba-142">**Description**</span></span><br><span data-ttu-id="3bdba-143">mshr_description</span><span class="sxs-lookup"><span data-stu-id="3bdba-143">mshr_description</span></span><br><span data-ttu-id="3bdba-144">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="3bdba-144">*String*</span></span> | <span data-ttu-id="3bdba-145">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="3bdba-145">Read/write</span></span><br><span data-ttu-id="3bdba-146">Requis</span><span class="sxs-lookup"><span data-stu-id="3bdba-146">Required</span></span> | <span data-ttu-id="3bdba-147">Description du niveau de classement.</span><span class="sxs-lookup"><span data-stu-id="3bdba-147">The description of the rating level.</span></span> |
| <span data-ttu-id="3bdba-148">**Facteur**</span><span class="sxs-lookup"><span data-stu-id="3bdba-148">**Factor**</span></span><br><span data-ttu-id="3bdba-149">mshr_factor</span><span class="sxs-lookup"><span data-stu-id="3bdba-149">mshr_factor</span></span><br><span data-ttu-id="3bdba-150">*Entier*</span><span class="sxs-lookup"><span data-stu-id="3bdba-150">*Integer*</span></span> | <span data-ttu-id="3bdba-151">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="3bdba-151">Read/write</span></span><br><span data-ttu-id="3bdba-152">Requis</span><span class="sxs-lookup"><span data-stu-id="3bdba-152">Required</span></span> | <span data-ttu-id="3bdba-153">Facteur pour le niveau de classement.</span><span class="sxs-lookup"><span data-stu-id="3bdba-153">The factor for the rating level.</span></span> <span data-ttu-id="3bdba-154">Lorsque vous comparez des articles avec un autre nombre de niveaux de classement, le facteur permet de normaliser les scores.</span><span class="sxs-lookup"><span data-stu-id="3bdba-154">When you compare items with a different number of rating levels, the factor is used to normalize the scores.</span></span> <span data-ttu-id="3bdba-155">La valeur doit être un entier compris entre 0 et 9.</span><span class="sxs-lookup"><span data-stu-id="3bdba-155">The value must be an integer between 0 and 9.</span></span> |
| <span data-ttu-id="3bdba-156">**Remarque**</span><span class="sxs-lookup"><span data-stu-id="3bdba-156">**Note**</span></span><br><span data-ttu-id="3bdba-157">mshr_note</span><span class="sxs-lookup"><span data-stu-id="3bdba-157">mshr_note</span></span><br><span data-ttu-id="3bdba-158">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="3bdba-158">*String*</span></span> | <span data-ttu-id="3bdba-159">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="3bdba-159">Read/write</span></span><br><span data-ttu-id="3bdba-160">Facultatif</span><span class="sxs-lookup"><span data-stu-id="3bdba-160">Optional</span></span> | <span data-ttu-id="3bdba-161">Toutes les notes associées au niveau de classement.</span><span class="sxs-lookup"><span data-stu-id="3bdba-161">Any notes associated with the rating level.</span></span> |
| <span data-ttu-id="3bdba-162">**Champ primaire**</span><span class="sxs-lookup"><span data-stu-id="3bdba-162">**Primary Field**</span></span><br><span data-ttu-id="3bdba-163">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="3bdba-163">mshr_primaryfield</span></span><br><span data-ttu-id="3bdba-164">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="3bdba-164">*String*</span></span> | <span data-ttu-id="3bdba-165">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="3bdba-165">Read-only</span></span><br><span data-ttu-id="3bdba-166">Requis</span><span class="sxs-lookup"><span data-stu-id="3bdba-166">Required</span></span> | <span data-ttu-id="3bdba-167">Champ à utiliser comme identifiant principal de l’enregistrement d’entité.</span><span class="sxs-lookup"><span data-stu-id="3bdba-167">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="3bdba-168">Combinaison de l’ID du niveau de classification et de l’ID du modèle de classement.</span><span class="sxs-lookup"><span data-stu-id="3bdba-168">Combination of rating level ID and rating model ID.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3bdba-169">Voir également :</span><span class="sxs-lookup"><span data-stu-id="3bdba-169">See also</span></span>

[<span data-ttu-id="3bdba-170">Introduction à l’API d’intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="3bdba-170">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="3bdba-171">Exemple de requête pour l’entité Candidat à l’embauche</span><span class="sxs-lookup"><span data-stu-id="3bdba-171">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]