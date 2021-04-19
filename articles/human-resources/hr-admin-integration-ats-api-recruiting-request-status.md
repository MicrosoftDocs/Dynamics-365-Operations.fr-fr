---
title: Statut de la demande de recrutement
description: Cette rubrique décrit l’option Statut de la demande de recrutement définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 888fbc511bffbecd837c929049006266191da5ba
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5806040"
---
# <a name="recruiting-request-status"></a><span data-ttu-id="e8fd0-103">Statut de la demande de recrutement</span><span class="sxs-lookup"><span data-stu-id="e8fd0-103">Recruiting request status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e8fd0-104">Cette rubrique décrit l’option Statut de la demande de recrutement définie pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e8fd0-104">This topic describes the Recruiting request status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="e8fd0-105">Nom physique : mshr_hcmrecruitingrequeststatus</span><span class="sxs-lookup"><span data-stu-id="e8fd0-105">Physical name: mshr_hcmrecruitingrequeststatus</span></span>

<span data-ttu-id="e8fd0-106">Cette énumération fournit le jeu d’options pour les valeurs de statut d’une demande de recrutement.</span><span class="sxs-lookup"><span data-stu-id="e8fd0-106">This enumeration provides the option set for the status values of a RecruitingRequest.</span></span>

| <span data-ttu-id="e8fd0-107">Valeur</span><span class="sxs-lookup"><span data-stu-id="e8fd0-107">Value</span></span> | <span data-ttu-id="e8fd0-108">Étiquette</span><span class="sxs-lookup"><span data-stu-id="e8fd0-108">Label</span></span> | <span data-ttu-id="e8fd0-109">Description</span><span class="sxs-lookup"><span data-stu-id="e8fd0-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="e8fd0-110">200000000</span><span class="sxs-lookup"><span data-stu-id="e8fd0-110">200000000</span></span> | <span data-ttu-id="e8fd0-111">Brouillon</span><span class="sxs-lookup"><span data-stu-id="e8fd0-111">Draft</span></span> | <span data-ttu-id="e8fd0-112">La demande est en projet et n’est pas prête pour le recrutement actif.</span><span class="sxs-lookup"><span data-stu-id="e8fd0-112">The request is in draft and isn't ready for active recruiting.</span></span> |
| <span data-ttu-id="e8fd0-113">200000001</span><span class="sxs-lookup"><span data-stu-id="e8fd0-113">200000001</span></span> | <span data-ttu-id="e8fd0-114">En cours de révision</span><span class="sxs-lookup"><span data-stu-id="e8fd0-114">In Review</span></span> | <span data-ttu-id="e8fd0-115">La demande a été soumise et est acheminée pour approbation par le workflow.</span><span class="sxs-lookup"><span data-stu-id="e8fd0-115">The request has been submitted and is being routed for approval by workflow.</span></span> <span data-ttu-id="e8fd0-116">Uniquement disponible lorsque le workflow est activé.</span><span class="sxs-lookup"><span data-stu-id="e8fd0-116">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="e8fd0-117">200000002</span><span class="sxs-lookup"><span data-stu-id="e8fd0-117">200000002</span></span> | <span data-ttu-id="e8fd0-118">Facture en attente</span><span class="sxs-lookup"><span data-stu-id="e8fd0-118">Pending</span></span> | <span data-ttu-id="e8fd0-119">La demande est en attente d’une action de workflow.</span><span class="sxs-lookup"><span data-stu-id="e8fd0-119">The request is pending workflow action.</span></span> <span data-ttu-id="e8fd0-120">Uniquement disponible lorsque le workflow est activé.</span><span class="sxs-lookup"><span data-stu-id="e8fd0-120">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="e8fd0-121">200000003</span><span class="sxs-lookup"><span data-stu-id="e8fd0-121">200000003</span></span> | <span data-ttu-id="e8fd0-122">Annulée</span><span class="sxs-lookup"><span data-stu-id="e8fd0-122">Canceled</span></span> | <span data-ttu-id="e8fd0-123">La demande a été annulée.</span><span class="sxs-lookup"><span data-stu-id="e8fd0-123">The request has been canceled.</span></span> <span data-ttu-id="e8fd0-124">Uniquement disponible lorsque le workflow est activé.</span><span class="sxs-lookup"><span data-stu-id="e8fd0-124">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="e8fd0-125">200000004</span><span class="sxs-lookup"><span data-stu-id="e8fd0-125">200000004</span></span> | <span data-ttu-id="e8fd0-126">Refusé</span><span class="sxs-lookup"><span data-stu-id="e8fd0-126">Denied</span></span> | <span data-ttu-id="e8fd0-127">La demande a été refusée.</span><span class="sxs-lookup"><span data-stu-id="e8fd0-127">The request has been denied.</span></span> <span data-ttu-id="e8fd0-128">Uniquement disponible lorsque le workflow est activé.</span><span class="sxs-lookup"><span data-stu-id="e8fd0-128">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="e8fd0-129">200000005</span><span class="sxs-lookup"><span data-stu-id="e8fd0-129">200000005</span></span> | <span data-ttu-id="e8fd0-130">Actif.ve</span><span class="sxs-lookup"><span data-stu-id="e8fd0-130">Active</span></span> | <span data-ttu-id="e8fd0-131">Workflow quelconque terminé et approuvé, et demande prête pour un recrutement actif.</span><span class="sxs-lookup"><span data-stu-id="e8fd0-131">Any workflow is completed and approved, and the request is ready for active recruiting.</span></span> |
| <span data-ttu-id="e8fd0-132">200000006</span><span class="sxs-lookup"><span data-stu-id="e8fd0-132">200000006</span></span> | <span data-ttu-id="e8fd0-133">Clôturée(s)</span><span class="sxs-lookup"><span data-stu-id="e8fd0-133">Closed</span></span> | <span data-ttu-id="e8fd0-134">La demande de recrutement est clôturée.</span><span class="sxs-lookup"><span data-stu-id="e8fd0-134">The recruiting request is closed.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e8fd0-135">Voir également :</span><span class="sxs-lookup"><span data-stu-id="e8fd0-135">See also</span></span>

[<span data-ttu-id="e8fd0-136">Introduction à l’API d’intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="e8fd0-136">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="e8fd0-137">Exemple de requête pour une demande de recrutement</span><span class="sxs-lookup"><span data-stu-id="e8fd0-137">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]