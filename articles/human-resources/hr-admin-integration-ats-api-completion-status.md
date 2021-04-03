---
title: État d’achèvement
description: Cette rubrique décrit l’option État d’achèvement définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: d8ea90785f303301a21a4ac799578b08cabd0e3d
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468201"
---
# <a name="completion-status"></a><span data-ttu-id="72f33-103">État d’achèvement</span><span class="sxs-lookup"><span data-stu-id="72f33-103">Completion status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="72f33-104">Cette rubrique décrit l’option État d’achèvement définie pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="72f33-104">This topic describes the Completion status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="72f33-105">Nom physique : mshr_hcmcompletionstatus</span><span class="sxs-lookup"><span data-stu-id="72f33-105">Physical name: mshr_hcmcompletionstatus</span></span>

<span data-ttu-id="72f33-106">Cette énumération fournit le jeu d’options des valeurs de statut pour la présélection des candidats.</span><span class="sxs-lookup"><span data-stu-id="72f33-106">This enumeration provides the option set of status values for candidate screenings.</span></span> 

| <span data-ttu-id="72f33-107">Valeur</span><span class="sxs-lookup"><span data-stu-id="72f33-107">Value</span></span> | <span data-ttu-id="72f33-108">Étiquette</span><span class="sxs-lookup"><span data-stu-id="72f33-108">Label</span></span> | <span data-ttu-id="72f33-109">Description</span><span class="sxs-lookup"><span data-stu-id="72f33-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="72f33-110">200000000</span><span class="sxs-lookup"><span data-stu-id="72f33-110">200000000</span></span> | <span data-ttu-id="72f33-111">Incomplet</span><span class="sxs-lookup"><span data-stu-id="72f33-111">Not Complete</span></span> | <span data-ttu-id="72f33-112">Le candidat n’a pas encore effectué de présélection.</span><span class="sxs-lookup"><span data-stu-id="72f33-112">The candidate has not yet completed the screening.</span></span> |
| <span data-ttu-id="72f33-113">200000001</span><span class="sxs-lookup"><span data-stu-id="72f33-113">200000001</span></span> | <span data-ttu-id="72f33-114">Réussite</span><span class="sxs-lookup"><span data-stu-id="72f33-114">Pass</span></span> | <span data-ttu-id="72f33-115">Le candidat a réussi la présélection.</span><span class="sxs-lookup"><span data-stu-id="72f33-115">The candidate has passed the screening.</span></span> |
| <span data-ttu-id="72f33-116">200000002</span><span class="sxs-lookup"><span data-stu-id="72f33-116">200000002</span></span> | <span data-ttu-id="72f33-117">Échec</span><span class="sxs-lookup"><span data-stu-id="72f33-117">Fail</span></span> | <span data-ttu-id="72f33-118">Le candidat n’a pas réussi la présélection.</span><span class="sxs-lookup"><span data-stu-id="72f33-118">The candidate has failed the screening.</span></span> |

## <a name="see-also"></a><span data-ttu-id="72f33-119">Voir également :</span><span class="sxs-lookup"><span data-stu-id="72f33-119">See also</span></span>

[<span data-ttu-id="72f33-120">Introduction à l’API d’intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="72f33-120">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="72f33-121">Exemple de requête pour l’entité Candidat à l’embauche</span><span class="sxs-lookup"><span data-stu-id="72f33-121">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]