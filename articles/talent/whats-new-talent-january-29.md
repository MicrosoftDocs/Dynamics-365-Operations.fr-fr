---
title: Nouveautés ou modifications dans Dynamics 365 for Talent (31 janvier 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 1/31/2019
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
ms.search.validFrom: 2019-01-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 5c9449e2bdec8c17cc2cf659ed68ac1d713a26ad
ms.sourcegitcommit: 1e32d78868098fd76124bb41363f15c4ec3ea15a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2019
ms.locfileid: "374732"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-january-31-2019"></a><span data-ttu-id="9291f-103">Nouveautés ou modifications dans Dynamics 365 for Talent (31 janvier 2019)</span><span class="sxs-lookup"><span data-stu-id="9291f-103">What's new or changed in Dynamics 365 for Talent (January 31, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9291f-104">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="9291f-104">This topic describes features that are either new or changed in Dynamics 365 for Talent</span></span>

<span data-ttu-id="9291f-105">**Version 8.1.2128**</span><span class="sxs-lookup"><span data-stu-id="9291f-105">**Build 8.1.2128**</span></span>

## <a name="core-hr-changes"></a><span data-ttu-id="9291f-106">Modifications apportées à Core HR</span><span class="sxs-lookup"><span data-stu-id="9291f-106">Core HR Changes</span></span>

### <a name="time-off-taken-on-leave-people-card-doesnt-consider-leave-plan-dates"></a><span data-ttu-id="9291f-107">Les congés pris sur la fiche individuelle des congés ne tient pas compte des dates prévisionnelles de congés.</span><span class="sxs-lookup"><span data-stu-id="9291f-107">Time off taken on leave people card doesn't consider leave plan dates</span></span>
<span data-ttu-id="9291f-108">Pour tous les employés ayant des plans de congés qui ne sont pas exécutés sur une année civile, la fiche **Déduit** affiche maintenant les congés pris au cours de l'année définie dans le plan.</span><span class="sxs-lookup"><span data-stu-id="9291f-108">For those that have leave plans that don’t run on a calendar year, the **Taken** card now displays time off that’s been taken in the plan-defined leave year.</span></span> <span data-ttu-id="9291f-109">Par exemple, si l'année de congés d'une organisation court du 1er juin au 30 mai, et si un employé a pris 3 jours de congés en décembre, la fiche **Déduit** affichera, le 15 janvier, 3 jours.</span><span class="sxs-lookup"><span data-stu-id="9291f-109">For example, if an organization’s leave year is June 1 through May 30 and an employee has taken 3 days off in December, the **Taken** card on January 15, will display 3 days.</span></span> 

### <a name="accrual-amounts-not-matching-tier-date-basis"></a><span data-ttu-id="9291f-110">Montants réels ne correspondant pas à une base de date</span><span class="sxs-lookup"><span data-stu-id="9291f-110">Accrual amounts not matching tier date basis</span></span>
<span data-ttu-id="9291f-111">De nouvelles options ont été ajoutées aux congés et absences (paramètres **Ressources humaines**) pour permettre aux clients de déterminer quand les mois de date de service des employés sont effectifs.</span><span class="sxs-lookup"><span data-stu-id="9291f-111">New options have been added to leave and absence (**Human resources** parameters) to enable customers to determine when employees’ months of service date are effective.</span></span> <span data-ttu-id="9291f-112">Pour certaines organisations, la date est la fin du mois, mais pour d'autres, il peut s'agir du début du mois prochain.</span><span class="sxs-lookup"><span data-stu-id="9291f-112">For some organizations, the date is the end of the month, but for others it may be the start of the next month.</span></span> <span data-ttu-id="9291f-113">Par exemple, une organisation peut accorder un congé le 31 décembre, tandis qu'une autre peut en accorder un le 1er janvier.</span><span class="sxs-lookup"><span data-stu-id="9291f-113">For example, one organization may award time off on December 31, while another may award time off on January 1.</span></span> <span data-ttu-id="9291f-114">Cette option vous permettra de choisir quand doit survenir l'attribution.</span><span class="sxs-lookup"><span data-stu-id="9291f-114">This option will allow you to choose when the award should occur.</span></span> 

### <a name="worker-hire-actions-are-stuck-in-workflow-complete-state"></a><span data-ttu-id="9291f-115">Les actions de recrutement d'employés sont répertoriées dans l'état « Workflow terminé ».</span><span class="sxs-lookup"><span data-stu-id="9291f-115">Worker hire actions are stuck in "Workflow complete" state</span></span>
<span data-ttu-id="9291f-116">Des modifications ont été apportées pour corriger un problème lorsqu'un petit nombre de workflows sont terminés avec un statut « Workflow terminé ».</span><span class="sxs-lookup"><span data-stu-id="9291f-116">Changes have been made to correct an issue where a small number of workflows finished with a "Workflow complete" status.</span></span> <span data-ttu-id="9291f-117">Les nouveaux workflows doivent se déplacer vers un état « Terminé » une fois qu'il est terminé.</span><span class="sxs-lookup"><span data-stu-id="9291f-117">New workflows should now move to a "Completed" state when the workflow finishes.</span></span> <span data-ttu-id="9291f-118">Tous les workflows ayant le statut Terminé seront transférés vers un statut d'erreur pour permettre la mise à jour ou la suppression, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="9291f-118">Any workflows in a workflow completed status will be transitioned to an error status to allow for updating or removal if required.</span></span> 
