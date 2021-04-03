---
title: Résultat de l’intégration du candidat
description: Cette rubrique décrit l’option Résultat de l’intégration du candidat définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: dd25eca9cccf46ec4e4bb2a1d948ca98985e73e4
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467551"
---
# <a name="applicant-integration-result"></a><span data-ttu-id="cec4f-103">Résultat de l’intégration du candidat</span><span class="sxs-lookup"><span data-stu-id="cec4f-103">Applicant integration result</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="cec4f-104">Cette rubrique décrit l’option Résultat de l’intégration du candidat définie pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cec4f-104">This topic describes the Applicant integration result option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="cec4f-105">Nom physique : mshr_hcmapplicantintegrationresult</span><span class="sxs-lookup"><span data-stu-id="cec4f-105">Physical name: mshr_hcmapplicantintegrationresult</span></span>

<span data-ttu-id="cec4f-106">Cette énumération fournit le statut d’un dossier de candidature.</span><span class="sxs-lookup"><span data-stu-id="cec4f-106">This enumeration provides status for a candidate record.</span></span>

| <span data-ttu-id="cec4f-107">Valeur </span><span class="sxs-lookup"><span data-stu-id="cec4f-107">Value</span></span> | <span data-ttu-id="cec4f-108">Étiquette</span><span class="sxs-lookup"><span data-stu-id="cec4f-108">Label</span></span> | <span data-ttu-id="cec4f-109">Description </span><span class="sxs-lookup"><span data-stu-id="cec4f-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cec4f-110">200000000</span><span class="sxs-lookup"><span data-stu-id="cec4f-110">200000000</span></span> | <span data-ttu-id="cec4f-111">Non traité</span><span class="sxs-lookup"><span data-stu-id="cec4f-111">Not processed</span></span> | <span data-ttu-id="cec4f-112">La candidature est toujours à l’étude.</span><span class="sxs-lookup"><span data-stu-id="cec4f-112">Candidate is still under consideration.</span></span> |
| <span data-ttu-id="cec4f-113">200000001</span><span class="sxs-lookup"><span data-stu-id="cec4f-113">200000001</span></span> | <span data-ttu-id="cec4f-114">Embauché</span><span class="sxs-lookup"><span data-stu-id="cec4f-114">Hired</span></span> | <span data-ttu-id="cec4f-115">Le candidat a été embauché.</span><span class="sxs-lookup"><span data-stu-id="cec4f-115">The candidate has been hired.</span></span> |
| <span data-ttu-id="cec4f-116">200000002</span><span class="sxs-lookup"><span data-stu-id="cec4f-116">200000002</span></span> | <span data-ttu-id="cec4f-117">Non embauché</span><span class="sxs-lookup"><span data-stu-id="cec4f-117">Not hired</span></span> | <span data-ttu-id="cec4f-118">Il a été décidé de ne pas embaucher le candidat.</span><span class="sxs-lookup"><span data-stu-id="cec4f-118">Decision was made to not hire the candidate.</span></span> |
| <span data-ttu-id="cec4f-119">200000003</span><span class="sxs-lookup"><span data-stu-id="cec4f-119">200000003</span></span> | <span data-ttu-id="cec4f-120">Ignoré</span><span class="sxs-lookup"><span data-stu-id="cec4f-120">Dismissed</span></span> | <span data-ttu-id="cec4f-121">La candidature n’a pas été retenue.</span><span class="sxs-lookup"><span data-stu-id="cec4f-121">The candidate was dismissed from consideration.</span></span> |

## <a name="see-also"></a><span data-ttu-id="cec4f-122">Voir également :</span><span class="sxs-lookup"><span data-stu-id="cec4f-122">See also</span></span>

[<span data-ttu-id="cec4f-123">Introduction à l’API d’intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="cec4f-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="cec4f-124">Exemple de requête pour l’entité Candidat à l’embauche</span><span class="sxs-lookup"><span data-stu-id="cec4f-124">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]