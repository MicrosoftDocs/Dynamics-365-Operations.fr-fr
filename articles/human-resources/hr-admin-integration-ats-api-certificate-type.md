---
title: Type de certificat
description: Cette rubrique décrit l’entité Type de certificat pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 962bccb3aaab16322d072417660ec3aac821183b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467479"
---
# <a name="certificate-type"></a><span data-ttu-id="f94cb-103">Type de certificat</span><span class="sxs-lookup"><span data-stu-id="f94cb-103">Certificate type</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f94cb-104">Cette rubrique décrit l’entité Type de certificat pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f94cb-104">This topic describes the Certificate type entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="f94cb-105">Nom physique : mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="f94cb-105">Physical name: mshr_hcmcertificatetypeentity</span></span>

## <a name="description"></a><span data-ttu-id="f94cb-106">Description</span><span class="sxs-lookup"><span data-stu-id="f94cb-106">Description</span></span>

<span data-ttu-id="f94cb-107">Cette entité définit la liste des types de certificats professionnels mis en place dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f94cb-107">This entity defines the list of professional certificate types set up in Human Resources.</span></span> <span data-ttu-id="f94cb-108">L’entité n’est pas spécifique à une entité juridique (entreprise).</span><span class="sxs-lookup"><span data-stu-id="f94cb-108">The entity isn't specific to a legal entity (company).</span></span>

## <a name="json-representation"></a><span data-ttu-id="f94cb-109">Représentation JSON</span><span class="sxs-lookup"><span data-stu-id="f94cb-109">JSON representation</span></span>

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="f94cb-110">Propriétés</span><span class="sxs-lookup"><span data-stu-id="f94cb-110">Properties</span></span>

| <span data-ttu-id="f94cb-111">Propriété</span><span class="sxs-lookup"><span data-stu-id="f94cb-111">Property</span></span><br><span data-ttu-id="f94cb-112">**Nom physique**</span><span class="sxs-lookup"><span data-stu-id="f94cb-112">**Physical name**</span></span><br><span data-ttu-id="f94cb-113">**_Type_**</span><span class="sxs-lookup"><span data-stu-id="f94cb-113">**_Type_**</span></span> | <span data-ttu-id="f94cb-114">Cas d’emploi</span><span class="sxs-lookup"><span data-stu-id="f94cb-114">Use</span></span> | <span data-ttu-id="f94cb-115">Description</span><span class="sxs-lookup"><span data-stu-id="f94cb-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="f94cb-116">**ID d’entité de type de certificat**</span><span class="sxs-lookup"><span data-stu-id="f94cb-116">**Certificate Type Entity ID**</span></span><br><span data-ttu-id="f94cb-117">mshr_hcmcertificatetypeentityid</span><span class="sxs-lookup"><span data-stu-id="f94cb-117">mshr_hcmcertificatetypeentityid</span></span><br><span data-ttu-id="f94cb-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f94cb-118">*GUID*</span></span> | <span data-ttu-id="f94cb-119">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="f94cb-119">Read-only</span></span><br><span data-ttu-id="f94cb-120">Requis</span><span class="sxs-lookup"><span data-stu-id="f94cb-120">Required</span></span> 
<span data-ttu-id="f94cb-121">Généré par le système</span><span class="sxs-lookup"><span data-stu-id="f94cb-121">System-generated</span></span> | <span data-ttu-id="f94cb-122">Identificateur principal unique pour le type de certificat.</span><span class="sxs-lookup"><span data-stu-id="f94cb-122">Unique primary identifier for the certificate type.</span></span> |
| <span data-ttu-id="f94cb-123">**Type de certificat**</span><span class="sxs-lookup"><span data-stu-id="f94cb-123">**Certificate Type**</span></span><br><span data-ttu-id="f94cb-124">mshr_certificatetype</span><span class="sxs-lookup"><span data-stu-id="f94cb-124">mshr_certificatetype</span></span><br><span data-ttu-id="f94cb-125">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="f94cb-125">*String*</span></span> | <span data-ttu-id="f94cb-126">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="f94cb-126">Read/write</span></span><br><span data-ttu-id="f94cb-127">Requis</span><span class="sxs-lookup"><span data-stu-id="f94cb-127">Required</span></span> | <span data-ttu-id="f94cb-128">Identificateur unique lisible par l’utilisateur pour le type de certificat.</span><span class="sxs-lookup"><span data-stu-id="f94cb-128">Unique user-readable identifier for the certificate type.</span></span> |
| <span data-ttu-id="f94cb-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="f94cb-129">**Description**</span></span><br><span data-ttu-id="f94cb-130">mshr_description</span><span class="sxs-lookup"><span data-stu-id="f94cb-130">mshr_description</span></span><br><span data-ttu-id="f94cb-131">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="f94cb-131">*String*</span></span> | <span data-ttu-id="f94cb-132">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="f94cb-132">Read/write</span></span><br><span data-ttu-id="f94cb-133">Requis</span><span class="sxs-lookup"><span data-stu-id="f94cb-133">Required</span></span> | <span data-ttu-id="f94cb-134">Description du type de certificat.</span><span class="sxs-lookup"><span data-stu-id="f94cb-134">Description of the certificate type.</span></span> |
| <span data-ttu-id="f94cb-135">**Demander un renouvellement**</span><span class="sxs-lookup"><span data-stu-id="f94cb-135">**Require Renewal**</span></span><br><span data-ttu-id="f94cb-136">mshr_requirerenewal</span><span class="sxs-lookup"><span data-stu-id="f94cb-136">mshr_requirerenewal</span></span><br><span data-ttu-id="f94cb-137">*Jeu d’options mshr_noyes*</span><span class="sxs-lookup"><span data-stu-id="f94cb-137">*mshr_noyes option set*</span></span> | <span data-ttu-id="f94cb-138">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="f94cb-138">Read/write</span></span><br><span data-ttu-id="f94cb-139">Facultatif</span><span class="sxs-lookup"><span data-stu-id="f94cb-139">Optional</span></span> | <span data-ttu-id="f94cb-140">Indique si le renouvellement est requis pour le certificat.</span><span class="sxs-lookup"><span data-stu-id="f94cb-140">Indicates whether renewal is required for the certificate.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f94cb-141">Voir également :</span><span class="sxs-lookup"><span data-stu-id="f94cb-141">See also</span></span>

[<span data-ttu-id="f94cb-142">Introduction à l’API d’intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="f94cb-142">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="f94cb-143">Exemple de requête pour l’entité Candidat à l’embauche</span><span class="sxs-lookup"><span data-stu-id="f94cb-143">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]