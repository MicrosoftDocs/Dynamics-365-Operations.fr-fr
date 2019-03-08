---
title: Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (1 octobre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 92eb1508905309294e17b770829b1c5a22be1316
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "304409"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-8-2018"></a><span data-ttu-id="6530f-103">Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (8 octobre 2018)</span><span class="sxs-lookup"><span data-stu-id="6530f-103">What's new or changed in Dynamics 365 for Talent Core HR (October 8, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6530f-104">**Version 8.1.1050.0**</span><span class="sxs-lookup"><span data-stu-id="6530f-104">**Build 8.1.1050.0**</span></span>

<span data-ttu-id="6530f-105">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.</span><span class="sxs-lookup"><span data-stu-id="6530f-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="allow-other-dates-to-be-used-on-leave-tier-basis-leave-management"></a><span data-ttu-id="6530f-106">Autoriser l'utilisation d'autres dates sur la base de niveau de congé (Gestion des congés)</span><span class="sxs-lookup"><span data-stu-id="6530f-106">Allow other dates to be used on leave tier basis (Leave Management)</span></span>

<span data-ttu-id="6530f-107">Lors de l'attribuant de congés aux employés, la base de niveau de prime détermine le nombre d'heures de congés qu'un employé régularise.</span><span class="sxs-lookup"><span data-stu-id="6530f-107">When awarding leave to employees, the award tier basis determines how much time off an employee accrues.</span></span> <span data-ttu-id="6530f-108">Actuellement, ces niveaux dépendent de la date de début de l'employé et de sa date d'ancienneté.</span><span class="sxs-lookup"><span data-stu-id="6530f-108">Currently, these tiers are based on employee start date and seniority date.</span></span> <span data-ttu-id="6530f-109">Dans certains cas, les organisations ont besoin que ces niveaux soient basés sur d'autres dates, telles que la date d'anniversaire ou la date d'embauche d'origine.</span><span class="sxs-lookup"><span data-stu-id="6530f-109">In some scenarios, organizations need these tiers to be based on other dates, like anniversary date or original hire date.</span></span> <span data-ttu-id="6530f-110">Ces dates sont déjà utilisées sur le plan de congé pour déterminer si les régularisations ont lieu, la capacité pour ces mêmes dates d'être utilisées lorsqu'un employé est inscrit dans un plan ont été ajoutés pour déterminer le montant de régularisation.</span><span class="sxs-lookup"><span data-stu-id="6530f-110">These dates are already used on the leave plan to determine when accruals happen, the ability for these same dates to be used when an employee is enrolled in a plan have been added to determine the accrual amount.</span></span> 

## <a name="other-changes"></a><span data-ttu-id="6530f-111">Autres modifications</span><span class="sxs-lookup"><span data-stu-id="6530f-111">Other changes</span></span>
<span data-ttu-id="6530f-112">Divers correctifs ont été inclus dans cette version.</span><span class="sxs-lookup"><span data-stu-id="6530f-112">Miscellanous fixes have been included in this release.</span></span>

## <a name="known-issue"></a><span data-ttu-id="6530f-113">Problème connu</span><span class="sxs-lookup"><span data-stu-id="6530f-113">Known issue</span></span>

<span data-ttu-id="6530f-114">**Problème** : lors de l'ajout d'une nouvelle pièce jointe à un collaborateur, les boutons **Nouveau** et **Modifier** sont grisés. **Solution de contournement** : avant d'ouvrir la page de la pièce jointe, vérifiez que les récapitulatifs de la page **Collaborateur** sont fermés.</span><span class="sxs-lookup"><span data-stu-id="6530f-114">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="6530f-115">Si les récapitulatifs sont fermés lorsque la page **Collaborateur** est chargée, les boutons de pièces jointes sont activés.</span><span class="sxs-lookup"><span data-stu-id="6530f-115">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="6530f-116">(Ce problème sera résolu dans la prochaine mise à jour de la plateforme.)</span><span class="sxs-lookup"><span data-stu-id="6530f-116">(This issue will be fixed in the next platform update.)</span></span>
