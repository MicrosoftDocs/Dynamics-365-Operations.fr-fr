---
title: Statut du poste pour la demande de recrutement
description: Cette rubrique décrit l’option Statut du poste pour la demande de recrutement définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 7e59e9381fb15b339095d6a71296813e0141e9ab
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5789730"
---
# <a name="recruiting-request-position-status"></a><span data-ttu-id="2c10c-103">Statut du poste pour la demande de recrutement</span><span class="sxs-lookup"><span data-stu-id="2c10c-103">Recruiting request position status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="2c10c-104">Cette rubrique décrit l’option Statut du poste pour la demande de recrutement définie pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2c10c-104">This topic describes the Recruiting request position status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="2c10c-105">Nom physique : mshr_hcmrecruitingrequestpositionstatus</span><span class="sxs-lookup"><span data-stu-id="2c10c-105">Physical name: mshr_hcmrecruitingrequestpositionstatus</span></span>

<span data-ttu-id="2c10c-106">Cette énumération fournit l’option définie pour les valeurs de statut de chaque poste ayant une demande de recrutement dans l’entité RecruitingRequestPosition.</span><span class="sxs-lookup"><span data-stu-id="2c10c-106">This enumeration provides the option set for the status values of each position a recruiting request in the RecruitingRequestPosition entity.</span></span>

| <span data-ttu-id="2c10c-107">Valeur</span><span class="sxs-lookup"><span data-stu-id="2c10c-107">Value</span></span> | <span data-ttu-id="2c10c-108">Étiquette</span><span class="sxs-lookup"><span data-stu-id="2c10c-108">Label</span></span> | <span data-ttu-id="2c10c-109">Description</span><span class="sxs-lookup"><span data-stu-id="2c10c-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="2c10c-110">200000000</span><span class="sxs-lookup"><span data-stu-id="2c10c-110">200000000</span></span> | <span data-ttu-id="2c10c-111">Ouverte(s)</span><span class="sxs-lookup"><span data-stu-id="2c10c-111">Open</span></span> | <span data-ttu-id="2c10c-112">Le poste dans la demande de recrutement est ouvert au recrutement.</span><span class="sxs-lookup"><span data-stu-id="2c10c-112">The position in the recruiting request is open for recruiting.</span></span> <span data-ttu-id="2c10c-113">Cela n’indique pas qu’il n’y a pas d’affectation de poste actuellement active pour le poste.</span><span class="sxs-lookup"><span data-stu-id="2c10c-113">This does not indicate that there is no currently active position assignment for the position.</span></span> <span data-ttu-id="2c10c-114">Il est possible qu’un employé occupe le poste au moment du recrutement.</span><span class="sxs-lookup"><span data-stu-id="2c10c-114">There may be an employee in the position at the time of recruiting.</span></span> <span data-ttu-id="2c10c-115">Cela indique uniquement que le poste est disponible pour le recrutement dans le cadre de la demande.</span><span class="sxs-lookup"><span data-stu-id="2c10c-115">It indicates only that the position is available for recruiting in the context of the recruiting request.</span></span> |
| <span data-ttu-id="2c10c-116">200000001</span><span class="sxs-lookup"><span data-stu-id="2c10c-116">200000001</span></span> | <span data-ttu-id="2c10c-117">Pourvu</span><span class="sxs-lookup"><span data-stu-id="2c10c-117">Filled</span></span> | <span data-ttu-id="2c10c-118">Un collaborateur a été sélectionné pour être affecté au poste.</span><span class="sxs-lookup"><span data-stu-id="2c10c-118">A worker has been selected for assignment to the position.</span></span> |
| <span data-ttu-id="2c10c-119">200000002</span><span class="sxs-lookup"><span data-stu-id="2c10c-119">200000002</span></span> | <span data-ttu-id="2c10c-120">Annulée</span><span class="sxs-lookup"><span data-stu-id="2c10c-120">Canceled</span></span> | <span data-ttu-id="2c10c-121">La demande de recrutement pour ce poste a été annulée.</span><span class="sxs-lookup"><span data-stu-id="2c10c-121">The request to recruit for this position has been canceled.</span></span> |

## <a name="see-also"></a><span data-ttu-id="2c10c-122">Voir également :</span><span class="sxs-lookup"><span data-stu-id="2c10c-122">See also</span></span>

[<span data-ttu-id="2c10c-123">Introduction à l’API d’intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="2c10c-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="2c10c-124">Exemple de requête pour une demande de recrutement</span><span class="sxs-lookup"><span data-stu-id="2c10c-124">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]