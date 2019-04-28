---
title: Créer un calendrier et générer les horaires de travail
description: Les calendriers décrivent la capacité et les heures de travail des ressources opérationnelles.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkCalendarTable, WorkCalendarDate
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba4bd51d2102b3036307f34ab46f94f83df4f461
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "856989"
---
# <a name="create-calendar-and-generate-working-times"></a><span data-ttu-id="b8d25-103">Créer un calendrier et générer les horaires de travail</span><span class="sxs-lookup"><span data-stu-id="b8d25-103">Create calendar and generate working times</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b8d25-104">Les calendriers décrivent la capacité et les heures de travail des ressources opérationnelles.</span><span class="sxs-lookup"><span data-stu-id="b8d25-104">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="b8d25-105">Cette procédure vous aide à définir un calendrier de travail fondé sur un modèle de temps de travail.</span><span class="sxs-lookup"><span data-stu-id="b8d25-105">This procedure will help you define a work calendar based on a working time template.</span></span> <span data-ttu-id="b8d25-106">Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="b8d25-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="b8d25-107">Accédez à Tous les espaces de travail > Gestion des cycles de vie des ressources.</span><span class="sxs-lookup"><span data-stu-id="b8d25-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="b8d25-108">Cliquez sur Calendriers.</span><span class="sxs-lookup"><span data-stu-id="b8d25-108">Click Calendars.</span></span>
3. <span data-ttu-id="b8d25-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="b8d25-109">Click New.</span></span>
4. <span data-ttu-id="b8d25-110">Dans le champ Calendrier, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b8d25-110">In the Calendar field, type a value.</span></span>
    * <span data-ttu-id="b8d25-111">Il s'agit de l'ID du calendrier, lequel sert de référence lors de l'affectation de calendriers, par exemple à une ressource opérationnelle ou à un groupe de ressources.</span><span class="sxs-lookup"><span data-stu-id="b8d25-111">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="b8d25-112">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="b8d25-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="b8d25-113">Dans le champ Jour de travail standard, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="b8d25-113">In the Standard work day in hours field, enter a number.</span></span>
7. <span data-ttu-id="b8d25-114">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b8d25-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="b8d25-115">Cliquez sur Temps de travail.</span><span class="sxs-lookup"><span data-stu-id="b8d25-115">Click Working times.</span></span>
9. <span data-ttu-id="b8d25-116">Cliquez sur Composer des heures de travail.</span><span class="sxs-lookup"><span data-stu-id="b8d25-116">Click Compose working times.</span></span>
    * <span data-ttu-id="b8d25-117">Générez les heures de travail pour chaque jour de la période où vous voulez pouvoir planifier du travail.</span><span class="sxs-lookup"><span data-stu-id="b8d25-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="b8d25-118">Au fur et à mesures, vous pourrez générer des heures de travail pour des périodes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="b8d25-118">As time goes by, you can generate working times for additional periods.</span></span>  
10. <span data-ttu-id="b8d25-119">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="b8d25-119">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="b8d25-120">Il s'agit du premier jour où ce calendrier doit être ouvert.</span><span class="sxs-lookup"><span data-stu-id="b8d25-120">This is the first day that this calendar must be open.</span></span>  
11. <span data-ttu-id="b8d25-121">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="b8d25-121">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="b8d25-122">Il s'agit du dernier jour où ce calendrier est ouvert.</span><span class="sxs-lookup"><span data-stu-id="b8d25-122">This is the last day that this calendar is open.</span></span>  
12. <span data-ttu-id="b8d25-123">Saisissez ou sélectionnez une valeur dans le champ Modèle de temps de travail.</span><span class="sxs-lookup"><span data-stu-id="b8d25-123">In the Working time template field, enter or select a value.</span></span>
    * <span data-ttu-id="b8d25-124">Le modèle de temps de travail définit les heures de travail pour chaque jour de la semaine.</span><span class="sxs-lookup"><span data-stu-id="b8d25-124">The working time template defines the working hours for each day of the week.</span></span>  
13. <span data-ttu-id="b8d25-125">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b8d25-125">Click OK.</span></span>
14. <span data-ttu-id="b8d25-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b8d25-126">Close the page.</span></span>

