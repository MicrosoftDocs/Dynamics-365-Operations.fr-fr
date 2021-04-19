---
title: État d’achèvement
description: Cette rubrique décrit l’option État d’achèvement définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: f1b0c61ac9d9dc611d2a4700a1a004e3d15b4445
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798367"
---
# <a name="completion-status"></a><span data-ttu-id="26d5d-103">État d’achèvement</span><span class="sxs-lookup"><span data-stu-id="26d5d-103">Completion status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="26d5d-104">Cette rubrique décrit l’option État d’achèvement définie pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="26d5d-104">This topic describes the Completion status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="26d5d-105">Nom physique : mshr_hcmcompletionstatus</span><span class="sxs-lookup"><span data-stu-id="26d5d-105">Physical name: mshr_hcmcompletionstatus</span></span>

<span data-ttu-id="26d5d-106">Cette énumération fournit le jeu d’options des valeurs de statut pour la présélection des candidats.</span><span class="sxs-lookup"><span data-stu-id="26d5d-106">This enumeration provides the option set of status values for candidate screenings.</span></span> 

| <span data-ttu-id="26d5d-107">Valeur</span><span class="sxs-lookup"><span data-stu-id="26d5d-107">Value</span></span> | <span data-ttu-id="26d5d-108">Étiquette</span><span class="sxs-lookup"><span data-stu-id="26d5d-108">Label</span></span> | <span data-ttu-id="26d5d-109">Description</span><span class="sxs-lookup"><span data-stu-id="26d5d-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="26d5d-110">200000000</span><span class="sxs-lookup"><span data-stu-id="26d5d-110">200000000</span></span> | <span data-ttu-id="26d5d-111">Incomplet</span><span class="sxs-lookup"><span data-stu-id="26d5d-111">Not Complete</span></span> | <span data-ttu-id="26d5d-112">Le candidat n’a pas encore effectué de présélection.</span><span class="sxs-lookup"><span data-stu-id="26d5d-112">The candidate has not yet completed the screening.</span></span> |
| <span data-ttu-id="26d5d-113">200000001</span><span class="sxs-lookup"><span data-stu-id="26d5d-113">200000001</span></span> | <span data-ttu-id="26d5d-114">Réussite</span><span class="sxs-lookup"><span data-stu-id="26d5d-114">Pass</span></span> | <span data-ttu-id="26d5d-115">Le candidat a réussi la présélection.</span><span class="sxs-lookup"><span data-stu-id="26d5d-115">The candidate has passed the screening.</span></span> |
| <span data-ttu-id="26d5d-116">200000002</span><span class="sxs-lookup"><span data-stu-id="26d5d-116">200000002</span></span> | <span data-ttu-id="26d5d-117">Échec</span><span class="sxs-lookup"><span data-stu-id="26d5d-117">Fail</span></span> | <span data-ttu-id="26d5d-118">Le candidat n’a pas réussi la présélection.</span><span class="sxs-lookup"><span data-stu-id="26d5d-118">The candidate has failed the screening.</span></span> |

## <a name="see-also"></a><span data-ttu-id="26d5d-119">Voir également :</span><span class="sxs-lookup"><span data-stu-id="26d5d-119">See also</span></span>

[<span data-ttu-id="26d5d-120">Introduction à l’API d’intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="26d5d-120">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="26d5d-121">Exemple de requête pour l’entité Candidat à l’embauche</span><span class="sxs-lookup"><span data-stu-id="26d5d-121">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]