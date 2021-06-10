---
title: Statut du poste pour la demande de recrutement
description: Cette rubrique décrit l’option Statut du poste pour la demande de recrutement définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: e287ec4b9b78194b76ef3c993c6ce32f808e26f9
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051879"
---
# <a name="recruiting-request-position-status"></a><span data-ttu-id="b627a-103">Statut du poste pour la demande de recrutement</span><span class="sxs-lookup"><span data-stu-id="b627a-103">Recruiting request position status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b627a-104">Cette rubrique décrit l’option Statut du poste pour la demande de recrutement définie pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b627a-104">This topic describes the Recruiting request position status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="b627a-105">Nom physique : mshr_hcmrecruitingrequestpositionstatus</span><span class="sxs-lookup"><span data-stu-id="b627a-105">Physical name: mshr_hcmrecruitingrequestpositionstatus</span></span>

<span data-ttu-id="b627a-106">Cette énumération fournit l’option définie pour les valeurs de statut de chaque poste ayant une demande de recrutement dans l’entité RecruitingRequestPosition.</span><span class="sxs-lookup"><span data-stu-id="b627a-106">This enumeration provides the option set for the status values of each position a recruiting request in the RecruitingRequestPosition entity.</span></span>

| <span data-ttu-id="b627a-107">Valeur</span><span class="sxs-lookup"><span data-stu-id="b627a-107">Value</span></span> | <span data-ttu-id="b627a-108">Étiquette</span><span class="sxs-lookup"><span data-stu-id="b627a-108">Label</span></span> | <span data-ttu-id="b627a-109">Description</span><span class="sxs-lookup"><span data-stu-id="b627a-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="b627a-110">200000000</span><span class="sxs-lookup"><span data-stu-id="b627a-110">200000000</span></span> | <span data-ttu-id="b627a-111">Ouverte(s)</span><span class="sxs-lookup"><span data-stu-id="b627a-111">Open</span></span> | <span data-ttu-id="b627a-112">Le poste dans la demande de recrutement est ouvert au recrutement.</span><span class="sxs-lookup"><span data-stu-id="b627a-112">The position in the recruiting request is open for recruiting.</span></span> <span data-ttu-id="b627a-113">Cela n’indique pas qu’il n’y a pas d’affectation de poste actuellement active pour le poste.</span><span class="sxs-lookup"><span data-stu-id="b627a-113">This does not indicate that there is no currently active position assignment for the position.</span></span> <span data-ttu-id="b627a-114">Il est possible qu’un employé occupe le poste au moment du recrutement.</span><span class="sxs-lookup"><span data-stu-id="b627a-114">There may be an employee in the position at the time of recruiting.</span></span> <span data-ttu-id="b627a-115">Cela indique uniquement que le poste est disponible pour le recrutement dans le cadre de la demande.</span><span class="sxs-lookup"><span data-stu-id="b627a-115">It indicates only that the position is available for recruiting in the context of the recruiting request.</span></span> |
| <span data-ttu-id="b627a-116">200000001</span><span class="sxs-lookup"><span data-stu-id="b627a-116">200000001</span></span> | <span data-ttu-id="b627a-117">Pourvu</span><span class="sxs-lookup"><span data-stu-id="b627a-117">Filled</span></span> | <span data-ttu-id="b627a-118">Un collaborateur a été sélectionné pour être affecté au poste.</span><span class="sxs-lookup"><span data-stu-id="b627a-118">A worker has been selected for assignment to the position.</span></span> |
| <span data-ttu-id="b627a-119">200000002</span><span class="sxs-lookup"><span data-stu-id="b627a-119">200000002</span></span> | <span data-ttu-id="b627a-120">Annulée</span><span class="sxs-lookup"><span data-stu-id="b627a-120">Canceled</span></span> | <span data-ttu-id="b627a-121">La demande de recrutement pour ce poste a été annulée.</span><span class="sxs-lookup"><span data-stu-id="b627a-121">The request to recruit for this position has been canceled.</span></span> |

## <a name="see-also"></a><span data-ttu-id="b627a-122">Voir également :</span><span class="sxs-lookup"><span data-stu-id="b627a-122">See also</span></span>

[<span data-ttu-id="b627a-123">Introduction à l’API d’intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="b627a-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="b627a-124">Exemple de requête pour une demande de recrutement</span><span class="sxs-lookup"><span data-stu-id="b627a-124">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]