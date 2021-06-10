---
title: Résultat de l’intégration du candidat
description: Cette rubrique décrit l’option Résultat de l’intégration du candidat définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 8bef974abff18d7c07ecd679b7e01b31ea1459c4
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053897"
---
# <a name="applicant-integration-result"></a><span data-ttu-id="2d495-103">Résultat de l’intégration du candidat</span><span class="sxs-lookup"><span data-stu-id="2d495-103">Applicant integration result</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="2d495-104">Cette rubrique décrit l’option Résultat de l’intégration du candidat définie pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2d495-104">This topic describes the Applicant integration result option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="2d495-105">Nom physique : mshr_hcmapplicantintegrationresult</span><span class="sxs-lookup"><span data-stu-id="2d495-105">Physical name: mshr_hcmapplicantintegrationresult</span></span>

<span data-ttu-id="2d495-106">Cette énumération fournit le statut d’un dossier de candidature.</span><span class="sxs-lookup"><span data-stu-id="2d495-106">This enumeration provides status for a candidate record.</span></span>

| <span data-ttu-id="2d495-107">Valeur</span><span class="sxs-lookup"><span data-stu-id="2d495-107">Value</span></span> | <span data-ttu-id="2d495-108">Étiquette</span><span class="sxs-lookup"><span data-stu-id="2d495-108">Label</span></span> | <span data-ttu-id="2d495-109">Description</span><span class="sxs-lookup"><span data-stu-id="2d495-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="2d495-110">200000000</span><span class="sxs-lookup"><span data-stu-id="2d495-110">200000000</span></span> | <span data-ttu-id="2d495-111">Non traité</span><span class="sxs-lookup"><span data-stu-id="2d495-111">Not processed</span></span> | <span data-ttu-id="2d495-112">La candidature est toujours à l’étude.</span><span class="sxs-lookup"><span data-stu-id="2d495-112">Candidate is still under consideration.</span></span> |
| <span data-ttu-id="2d495-113">200000001</span><span class="sxs-lookup"><span data-stu-id="2d495-113">200000001</span></span> | <span data-ttu-id="2d495-114">Embauché</span><span class="sxs-lookup"><span data-stu-id="2d495-114">Hired</span></span> | <span data-ttu-id="2d495-115">Le candidat a été embauché.</span><span class="sxs-lookup"><span data-stu-id="2d495-115">The candidate has been hired.</span></span> |
| <span data-ttu-id="2d495-116">200000002</span><span class="sxs-lookup"><span data-stu-id="2d495-116">200000002</span></span> | <span data-ttu-id="2d495-117">Non embauché</span><span class="sxs-lookup"><span data-stu-id="2d495-117">Not hired</span></span> | <span data-ttu-id="2d495-118">Il a été décidé de ne pas embaucher le candidat.</span><span class="sxs-lookup"><span data-stu-id="2d495-118">Decision was made to not hire the candidate.</span></span> |
| <span data-ttu-id="2d495-119">200000003</span><span class="sxs-lookup"><span data-stu-id="2d495-119">200000003</span></span> | <span data-ttu-id="2d495-120">Ignoré</span><span class="sxs-lookup"><span data-stu-id="2d495-120">Dismissed</span></span> | <span data-ttu-id="2d495-121">La candidature n’a pas été retenue.</span><span class="sxs-lookup"><span data-stu-id="2d495-121">The candidate was dismissed from consideration.</span></span> |

## <a name="see-also"></a><span data-ttu-id="2d495-122">Voir également :</span><span class="sxs-lookup"><span data-stu-id="2d495-122">See also</span></span>

[<span data-ttu-id="2d495-123">Introduction à l’API d’intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="2d495-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="2d495-124">Exemple de requête pour l’entité Candidat à l’embauche</span><span class="sxs-lookup"><span data-stu-id="2d495-124">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]