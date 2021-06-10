---
title: Type de certificat
description: Cette rubrique décrit l’entité Type de certificat pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: b8e979f242eb689b730b7f8a8684b3e697adbee6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054690"
---
# <a name="certificate-type"></a><span data-ttu-id="c2f19-103">Type de certificat</span><span class="sxs-lookup"><span data-stu-id="c2f19-103">Certificate type</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="c2f19-104">Cette rubrique décrit l’entité Type de certificat pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c2f19-104">This topic describes the Certificate type entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="c2f19-105">Nom physique : mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="c2f19-105">Physical name: mshr_hcmcertificatetypeentity</span></span>

## <a name="description"></a><span data-ttu-id="c2f19-106">Description</span><span class="sxs-lookup"><span data-stu-id="c2f19-106">Description</span></span>

<span data-ttu-id="c2f19-107">Cette entité définit la liste des types de certificats professionnels mis en place dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c2f19-107">This entity defines the list of professional certificate types set up in Human Resources.</span></span> <span data-ttu-id="c2f19-108">L’entité n’est pas spécifique à une entité juridique (entreprise).</span><span class="sxs-lookup"><span data-stu-id="c2f19-108">The entity isn't specific to a legal entity (company).</span></span>

## <a name="json-representation"></a><span data-ttu-id="c2f19-109">Représentation JSON</span><span class="sxs-lookup"><span data-stu-id="c2f19-109">JSON representation</span></span>

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="c2f19-110">Propriétés</span><span class="sxs-lookup"><span data-stu-id="c2f19-110">Properties</span></span>

| <span data-ttu-id="c2f19-111">Propriété</span><span class="sxs-lookup"><span data-stu-id="c2f19-111">Property</span></span><br><span data-ttu-id="c2f19-112">**Nom physique**</span><span class="sxs-lookup"><span data-stu-id="c2f19-112">**Physical name**</span></span><br><span data-ttu-id="c2f19-113">**_Type_**</span><span class="sxs-lookup"><span data-stu-id="c2f19-113">**_Type_**</span></span> | <span data-ttu-id="c2f19-114">Cas d’emploi</span><span class="sxs-lookup"><span data-stu-id="c2f19-114">Use</span></span> | <span data-ttu-id="c2f19-115">Description</span><span class="sxs-lookup"><span data-stu-id="c2f19-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="c2f19-116">**ID d’entité de type de certificat**</span><span class="sxs-lookup"><span data-stu-id="c2f19-116">**Certificate Type Entity ID**</span></span><br><span data-ttu-id="c2f19-117">mshr_hcmcertificatetypeentityid</span><span class="sxs-lookup"><span data-stu-id="c2f19-117">mshr_hcmcertificatetypeentityid</span></span><br><span data-ttu-id="c2f19-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="c2f19-118">*GUID*</span></span> | <span data-ttu-id="c2f19-119">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="c2f19-119">Read-only</span></span><br><span data-ttu-id="c2f19-120">Requis</span><span class="sxs-lookup"><span data-stu-id="c2f19-120">Required</span></span> 
<span data-ttu-id="c2f19-121">Généré par le système</span><span class="sxs-lookup"><span data-stu-id="c2f19-121">System-generated</span></span> | <span data-ttu-id="c2f19-122">Identificateur principal unique pour le type de certificat.</span><span class="sxs-lookup"><span data-stu-id="c2f19-122">Unique primary identifier for the certificate type.</span></span> |
| <span data-ttu-id="c2f19-123">**Type de certificat**</span><span class="sxs-lookup"><span data-stu-id="c2f19-123">**Certificate Type**</span></span><br><span data-ttu-id="c2f19-124">mshr_certificatetype</span><span class="sxs-lookup"><span data-stu-id="c2f19-124">mshr_certificatetype</span></span><br><span data-ttu-id="c2f19-125">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="c2f19-125">*String*</span></span> | <span data-ttu-id="c2f19-126">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="c2f19-126">Read/write</span></span><br><span data-ttu-id="c2f19-127">Requis</span><span class="sxs-lookup"><span data-stu-id="c2f19-127">Required</span></span> | <span data-ttu-id="c2f19-128">Identificateur unique lisible par l’utilisateur pour le type de certificat.</span><span class="sxs-lookup"><span data-stu-id="c2f19-128">Unique user-readable identifier for the certificate type.</span></span> |
| <span data-ttu-id="c2f19-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="c2f19-129">**Description**</span></span><br><span data-ttu-id="c2f19-130">mshr_description</span><span class="sxs-lookup"><span data-stu-id="c2f19-130">mshr_description</span></span><br><span data-ttu-id="c2f19-131">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="c2f19-131">*String*</span></span> | <span data-ttu-id="c2f19-132">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="c2f19-132">Read/write</span></span><br><span data-ttu-id="c2f19-133">Requis</span><span class="sxs-lookup"><span data-stu-id="c2f19-133">Required</span></span> | <span data-ttu-id="c2f19-134">Description du type de certificat.</span><span class="sxs-lookup"><span data-stu-id="c2f19-134">Description of the certificate type.</span></span> |
| <span data-ttu-id="c2f19-135">**Demander un renouvellement**</span><span class="sxs-lookup"><span data-stu-id="c2f19-135">**Require Renewal**</span></span><br><span data-ttu-id="c2f19-136">mshr_requirerenewal</span><span class="sxs-lookup"><span data-stu-id="c2f19-136">mshr_requirerenewal</span></span><br><span data-ttu-id="c2f19-137">*Jeu d’options mshr_noyes*</span><span class="sxs-lookup"><span data-stu-id="c2f19-137">*mshr_noyes option set*</span></span> | <span data-ttu-id="c2f19-138">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="c2f19-138">Read/write</span></span><br><span data-ttu-id="c2f19-139">Facultatif</span><span class="sxs-lookup"><span data-stu-id="c2f19-139">Optional</span></span> | <span data-ttu-id="c2f19-140">Indique si le renouvellement est requis pour le certificat.</span><span class="sxs-lookup"><span data-stu-id="c2f19-140">Indicates whether renewal is required for the certificate.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c2f19-141">Voir également :</span><span class="sxs-lookup"><span data-stu-id="c2f19-141">See also</span></span>

[<span data-ttu-id="c2f19-142">Introduction à l’API d’intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="c2f19-142">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="c2f19-143">Exemple de requête pour l’entité Candidat à l’embauche</span><span class="sxs-lookup"><span data-stu-id="c2f19-143">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]