---
title: Statut d'exemption de tâche
description: Cette rubrique décrit l'option Statut d'exonération d'un travail définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 0cd6ffc01793c8ff12e36175c7c9feaf8a4b3cdf
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125567"
---
# <a name="job-exempt-status"></a><span data-ttu-id="1dc38-103">Statut d'exonération d'un travail</span><span class="sxs-lookup"><span data-stu-id="1dc38-103">Job exempt status</span></span>

<span data-ttu-id="1dc38-104">Cette rubrique décrit l'option Statut d'exonération d'un travail définie pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1dc38-104">This topic describes the Job exempt status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="1dc38-105">Nom physique : cdm_jobexemptstatus</span><span class="sxs-lookup"><span data-stu-id="1dc38-105">Physical name: cdm_jobexemptstatus</span></span>

<span data-ttu-id="1dc38-106">Cette énumération spécifie l'option définie pour les valeurs du statut d'exonération FLSA (Fair Labor Standards Act).</span><span class="sxs-lookup"><span data-stu-id="1dc38-106">This enumeration specifies the option set for FLSA job exempt status values.</span></span> <span data-ttu-id="1dc38-107">Ceci est fourni dans le jeu d'options cdm_jobexemptstatus existant.</span><span class="sxs-lookup"><span data-stu-id="1dc38-107">This is provided in the existing cdm_jobexemptstatus option set.</span></span>

| <span data-ttu-id="1dc38-108">Valeur</span><span class="sxs-lookup"><span data-stu-id="1dc38-108">Value</span></span> | <span data-ttu-id="1dc38-109">Étiquette</span><span class="sxs-lookup"><span data-stu-id="1dc38-109">Label</span></span> | <span data-ttu-id="1dc38-110">Description</span><span class="sxs-lookup"><span data-stu-id="1dc38-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="1dc38-111">200000000</span><span class="sxs-lookup"><span data-stu-id="1dc38-111">200000000</span></span> | <span data-ttu-id="1dc38-112">Exempté</span><span class="sxs-lookup"><span data-stu-id="1dc38-112">Exempt</span></span> | <span data-ttu-id="1dc38-113">Le travail a un statut d'exonération basé sur les directives de la FLSA.</span><span class="sxs-lookup"><span data-stu-id="1dc38-113">The job has an exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="1dc38-114">200000001</span><span class="sxs-lookup"><span data-stu-id="1dc38-114">200000001</span></span> | <span data-ttu-id="1dc38-115">Non exonéré</span><span class="sxs-lookup"><span data-stu-id="1dc38-115">NonExempt</span></span> | <span data-ttu-id="1dc38-116">Le travail a un statut Non exonéré basé sur les directives de la FLSA.</span><span class="sxs-lookup"><span data-stu-id="1dc38-116">The job has a non-exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="1dc38-117">200000002</span><span class="sxs-lookup"><span data-stu-id="1dc38-117">200000002</span></span> | <span data-ttu-id="1dc38-118">Ne s'applique pas</span><span class="sxs-lookup"><span data-stu-id="1dc38-118">Does Not Apply</span></span> | <span data-ttu-id="1dc38-119">Les directives du statut FLSA ne s'appliquent pas à l'emploi.</span><span class="sxs-lookup"><span data-stu-id="1dc38-119">FLSA status guidelines do not apply to the job.</span></span> |

## <a name="see-also"></a><span data-ttu-id="1dc38-120">Voir également :</span><span class="sxs-lookup"><span data-stu-id="1dc38-120">See also</span></span>

[<span data-ttu-id="1dc38-121">Introduction à l'API d'intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="1dc38-121">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="1dc38-122">Exemple de requête pour une demande de recrutement</span><span class="sxs-lookup"><span data-stu-id="1dc38-122">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)
