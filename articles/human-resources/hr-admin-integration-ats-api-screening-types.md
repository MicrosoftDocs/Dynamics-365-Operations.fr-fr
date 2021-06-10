---
title: Types de présélection
description: Cette rubrique décrit l’entité Types de présélection pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 2acb99c2fb57df883ab376c7f6aab547073bd0ff
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6058294"
---
# <a name="screening-types"></a><span data-ttu-id="cd763-103">Types de présélection</span><span class="sxs-lookup"><span data-stu-id="cd763-103">Screening types</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="cd763-104">Cette rubrique décrit l’entité Types de présélection pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cd763-104">This topic describes the Screening types entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="cd763-105">Nom physique : mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="cd763-105">Physical name: mshr_hcmscreeningtypeentity</span></span>

## <a name="description"></a><span data-ttu-id="cd763-106">Description</span><span class="sxs-lookup"><span data-stu-id="cd763-106">Description</span></span>

<span data-ttu-id="cd763-107">Cette entité décrit les types de présélection mis en place par l’entreprise pour les processus de présélection avant l’embauche des employés.</span><span class="sxs-lookup"><span data-stu-id="cd763-107">This entity describes the screening types set up by the company for pre-employment and ongoing employee screening processes.</span></span>

## <a name="json-representation"></a><span data-ttu-id="cd763-108">Représentation JSON</span><span class="sxs-lookup"><span data-stu-id="cd763-108">JSON representation</span></span>

```json
{
    "mshr_description": "String",
    "mshr_frequencyunit": Int,
    "mshr_generatefrom": Int,
    "mshr_frequencyinterval": Int,
    "mshr_screeningtypeid": "String",
    "mshr_hcmscreeningtypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="cd763-109">Propriétés</span><span class="sxs-lookup"><span data-stu-id="cd763-109">Properties</span></span>

| <span data-ttu-id="cd763-110">Propriété</span><span class="sxs-lookup"><span data-stu-id="cd763-110">Property</span></span><br><span data-ttu-id="cd763-111">**Nom physique**</span><span class="sxs-lookup"><span data-stu-id="cd763-111">**Physical name**</span></span><br><span data-ttu-id="cd763-112">**_Type_**</span><span class="sxs-lookup"><span data-stu-id="cd763-112">**_Type_**</span></span> | <span data-ttu-id="cd763-113">Cas d’emploi</span><span class="sxs-lookup"><span data-stu-id="cd763-113">Use</span></span> | <span data-ttu-id="cd763-114">Description</span><span class="sxs-lookup"><span data-stu-id="cd763-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cd763-115">**ID de l’entité de type de présélection**</span><span class="sxs-lookup"><span data-stu-id="cd763-115">**Screening Type Entity ID**</span></span><br><span data-ttu-id="cd763-116">mshr_hcmscreeningtypeentityid</span><span class="sxs-lookup"><span data-stu-id="cd763-116">mshr_hcmscreeningtypeentityid</span></span><br><span data-ttu-id="cd763-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="cd763-117">*GUID*</span></span> | <span data-ttu-id="cd763-118">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="cd763-118">Read-only</span></span><br><span data-ttu-id="cd763-119">Requis</span><span class="sxs-lookup"><span data-stu-id="cd763-119">Required</span></span><br><span data-ttu-id="cd763-120">Généré par le système</span><span class="sxs-lookup"><span data-stu-id="cd763-120">System-generated</span></span> | <span data-ttu-id="cd763-121">Identificateur principal unique de l’enregistrement de type de test.</span><span class="sxs-lookup"><span data-stu-id="cd763-121">Unique primary identifier for the screening type record.</span></span> |
| <span data-ttu-id="cd763-122">**ID type de présélection**</span><span class="sxs-lookup"><span data-stu-id="cd763-122">**Screening Type ID**</span></span><br><span data-ttu-id="cd763-123">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="cd763-123">mshr_screeningtypeid</span></span><br><span data-ttu-id="cd763-124">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="cd763-124">*String*</span></span> | <span data-ttu-id="cd763-125">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="cd763-125">Read/write</span></span><br><span data-ttu-id="cd763-126">Requis</span><span class="sxs-lookup"><span data-stu-id="cd763-126">Required</span></span> | <span data-ttu-id="cd763-127">Identificateur unique défini par l’utilisateur pour le type de présélection.</span><span class="sxs-lookup"><span data-stu-id="cd763-127">User-defined unique identifier for the screening type.</span></span> |
| <span data-ttu-id="cd763-128">**Description**</span><span class="sxs-lookup"><span data-stu-id="cd763-128">**Description**</span></span><br><span data-ttu-id="cd763-129">mshr_description</span><span class="sxs-lookup"><span data-stu-id="cd763-129">mshr_description</span></span><br><span data-ttu-id="cd763-130">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="cd763-130">*String*</span></span> | <span data-ttu-id="cd763-131">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="cd763-131">Read/write</span></span><br><span data-ttu-id="cd763-132">Requis</span><span class="sxs-lookup"><span data-stu-id="cd763-132">Required</span></span> | <span data-ttu-id="cd763-133">Description du type de test.</span><span class="sxs-lookup"><span data-stu-id="cd763-133">The description of the screening type.</span></span> |
| <span data-ttu-id="cd763-134">**Unité de fréquence**</span><span class="sxs-lookup"><span data-stu-id="cd763-134">**Frequency Unit**</span></span><br><span data-ttu-id="cd763-135">mshr_frequencyunit</span><span class="sxs-lookup"><span data-stu-id="cd763-135">mshr_frequencyunit</span></span><br><span data-ttu-id="cd763-136">*Jeu d’options mshr_hcmfrequencyunit*</span><span class="sxs-lookup"><span data-stu-id="cd763-136">*mshr_hcmfrequencyunit option set*</span></span> | <span data-ttu-id="cd763-137">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="cd763-137">Read/write</span></span><br><span data-ttu-id="cd763-138">Requis</span><span class="sxs-lookup"><span data-stu-id="cd763-138">Required</span></span> | <span data-ttu-id="cd763-139">Décrit la fréquence à laquelle les présélections doivent être effectuées pour la personne désignée.</span><span class="sxs-lookup"><span data-stu-id="cd763-139">Describes the frequency with which the screening must be completed for the assigned person.</span></span> |
| <span data-ttu-id="cd763-140">**Date de début pour le calcul**</span><span class="sxs-lookup"><span data-stu-id="cd763-140">**Generate From**</span></span><br><span data-ttu-id="cd763-141">mshr_generatefrom</span><span class="sxs-lookup"><span data-stu-id="cd763-141">mshr_generatefrom</span></span><br><span data-ttu-id="cd763-142">*Jeu d’options mshr_hcmfrequencygeneratefrom*</span><span class="sxs-lookup"><span data-stu-id="cd763-142">*mshr_hcmfrequencygeneratefrom option set*</span></span> | <span data-ttu-id="cd763-143">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="cd763-143">Read-write</span></span><br><span data-ttu-id="cd763-144">Requis</span><span class="sxs-lookup"><span data-stu-id="cd763-144">Required</span></span> | <span data-ttu-id="cd763-145">Si la valeur de fréquence est une valeur autre que Occasionnelle uniquement, la valeur GenerateFrom détermine la date à partir de laquelle calculer le prochain événement de présélection.</span><span class="sxs-lookup"><span data-stu-id="cd763-145">If the Frequency value is any value other than “One-time only”, the GenerateFrom value determines the date from which to calculate the next screening event.</span></span> |
| <span data-ttu-id="cd763-146">**Intervalle de fréquence**</span><span class="sxs-lookup"><span data-stu-id="cd763-146">**Frequency Interval**</span></span><br><span data-ttu-id="cd763-147">mshr_frequencyinterval</span><span class="sxs-lookup"><span data-stu-id="cd763-147">mshr_frequencyinterval</span></span><br><span data-ttu-id="cd763-148">*Entier*</span><span class="sxs-lookup"><span data-stu-id="cd763-148">*Integer*</span></span> | <span data-ttu-id="cd763-149">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="cd763-149">Read-write</span></span><br><span data-ttu-id="cd763-150">Requis</span><span class="sxs-lookup"><span data-stu-id="cd763-150">Required</span></span> | <span data-ttu-id="cd763-151">Si la valeur de fréquence est une valeur autre que Occasionnelle uniquement, vous devez définir un intervalle pour les unités de temps entre chaque événement de présélection.</span><span class="sxs-lookup"><span data-stu-id="cd763-151">If the Frequency value is any value other than “One-time only”, you must define an interval for the units of time between each screening event.</span></span> |

## <a name="see-also"></a><span data-ttu-id="cd763-152">Voir également :</span><span class="sxs-lookup"><span data-stu-id="cd763-152">See also</span></span>

[<span data-ttu-id="cd763-153">Introduction à l’API d’intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="cd763-153">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="cd763-154">Exemple de requête pour l’entité Candidat à l’embauche</span><span class="sxs-lookup"><span data-stu-id="cd763-154">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]