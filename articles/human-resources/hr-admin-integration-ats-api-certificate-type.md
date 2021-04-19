---
title: Type de certificat
description: Cette rubrique décrit l’entité Type de certificat pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: fe5713b6b5f38ad7f6857b36c6b2f63a1dc0c320
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798391"
---
# <a name="certificate-type"></a><span data-ttu-id="558ec-103">Type de certificat</span><span class="sxs-lookup"><span data-stu-id="558ec-103">Certificate type</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="558ec-104">Cette rubrique décrit l’entité Type de certificat pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="558ec-104">This topic describes the Certificate type entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="558ec-105">Nom physique : mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="558ec-105">Physical name: mshr_hcmcertificatetypeentity</span></span>

## <a name="description"></a><span data-ttu-id="558ec-106">Description</span><span class="sxs-lookup"><span data-stu-id="558ec-106">Description</span></span>

<span data-ttu-id="558ec-107">Cette entité définit la liste des types de certificats professionnels mis en place dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="558ec-107">This entity defines the list of professional certificate types set up in Human Resources.</span></span> <span data-ttu-id="558ec-108">L’entité n’est pas spécifique à une entité juridique (entreprise).</span><span class="sxs-lookup"><span data-stu-id="558ec-108">The entity isn't specific to a legal entity (company).</span></span>

## <a name="json-representation"></a><span data-ttu-id="558ec-109">Représentation JSON</span><span class="sxs-lookup"><span data-stu-id="558ec-109">JSON representation</span></span>

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="558ec-110">Propriétés</span><span class="sxs-lookup"><span data-stu-id="558ec-110">Properties</span></span>

| <span data-ttu-id="558ec-111">Propriété</span><span class="sxs-lookup"><span data-stu-id="558ec-111">Property</span></span><br><span data-ttu-id="558ec-112">**Nom physique**</span><span class="sxs-lookup"><span data-stu-id="558ec-112">**Physical name**</span></span><br><span data-ttu-id="558ec-113">**_Type_**</span><span class="sxs-lookup"><span data-stu-id="558ec-113">**_Type_**</span></span> | <span data-ttu-id="558ec-114">Cas d’emploi</span><span class="sxs-lookup"><span data-stu-id="558ec-114">Use</span></span> | <span data-ttu-id="558ec-115">Description</span><span class="sxs-lookup"><span data-stu-id="558ec-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="558ec-116">**ID d’entité de type de certificat**</span><span class="sxs-lookup"><span data-stu-id="558ec-116">**Certificate Type Entity ID**</span></span><br><span data-ttu-id="558ec-117">mshr_hcmcertificatetypeentityid</span><span class="sxs-lookup"><span data-stu-id="558ec-117">mshr_hcmcertificatetypeentityid</span></span><br><span data-ttu-id="558ec-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="558ec-118">*GUID*</span></span> | <span data-ttu-id="558ec-119">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="558ec-119">Read-only</span></span><br><span data-ttu-id="558ec-120">Requis</span><span class="sxs-lookup"><span data-stu-id="558ec-120">Required</span></span> 
<span data-ttu-id="558ec-121">Généré par le système</span><span class="sxs-lookup"><span data-stu-id="558ec-121">System-generated</span></span> | <span data-ttu-id="558ec-122">Identificateur principal unique pour le type de certificat.</span><span class="sxs-lookup"><span data-stu-id="558ec-122">Unique primary identifier for the certificate type.</span></span> |
| <span data-ttu-id="558ec-123">**Type de certificat**</span><span class="sxs-lookup"><span data-stu-id="558ec-123">**Certificate Type**</span></span><br><span data-ttu-id="558ec-124">mshr_certificatetype</span><span class="sxs-lookup"><span data-stu-id="558ec-124">mshr_certificatetype</span></span><br><span data-ttu-id="558ec-125">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="558ec-125">*String*</span></span> | <span data-ttu-id="558ec-126">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="558ec-126">Read/write</span></span><br><span data-ttu-id="558ec-127">Requis</span><span class="sxs-lookup"><span data-stu-id="558ec-127">Required</span></span> | <span data-ttu-id="558ec-128">Identificateur unique lisible par l’utilisateur pour le type de certificat.</span><span class="sxs-lookup"><span data-stu-id="558ec-128">Unique user-readable identifier for the certificate type.</span></span> |
| <span data-ttu-id="558ec-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="558ec-129">**Description**</span></span><br><span data-ttu-id="558ec-130">mshr_description</span><span class="sxs-lookup"><span data-stu-id="558ec-130">mshr_description</span></span><br><span data-ttu-id="558ec-131">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="558ec-131">*String*</span></span> | <span data-ttu-id="558ec-132">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="558ec-132">Read/write</span></span><br><span data-ttu-id="558ec-133">Requis</span><span class="sxs-lookup"><span data-stu-id="558ec-133">Required</span></span> | <span data-ttu-id="558ec-134">Description du type de certificat.</span><span class="sxs-lookup"><span data-stu-id="558ec-134">Description of the certificate type.</span></span> |
| <span data-ttu-id="558ec-135">**Demander un renouvellement**</span><span class="sxs-lookup"><span data-stu-id="558ec-135">**Require Renewal**</span></span><br><span data-ttu-id="558ec-136">mshr_requirerenewal</span><span class="sxs-lookup"><span data-stu-id="558ec-136">mshr_requirerenewal</span></span><br><span data-ttu-id="558ec-137">*Jeu d’options mshr_noyes*</span><span class="sxs-lookup"><span data-stu-id="558ec-137">*mshr_noyes option set*</span></span> | <span data-ttu-id="558ec-138">Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="558ec-138">Read/write</span></span><br><span data-ttu-id="558ec-139">Facultatif</span><span class="sxs-lookup"><span data-stu-id="558ec-139">Optional</span></span> | <span data-ttu-id="558ec-140">Indique si le renouvellement est requis pour le certificat.</span><span class="sxs-lookup"><span data-stu-id="558ec-140">Indicates whether renewal is required for the certificate.</span></span> |

## <a name="see-also"></a><span data-ttu-id="558ec-141">Voir également :</span><span class="sxs-lookup"><span data-stu-id="558ec-141">See also</span></span>

[<span data-ttu-id="558ec-142">Introduction à l’API d’intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="558ec-142">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="558ec-143">Exemple de requête pour l’entité Candidat à l’embauche</span><span class="sxs-lookup"><span data-stu-id="558ec-143">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]