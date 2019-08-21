---
title: Créer des calendriers et générer les horaires de travail
description: Les calendriers décrivent la capacité et les heures de travail des ressources opérationnelles. Cette rubrique explique comment définir un calendrier de travail fondé sur un modèle de temps de travail.
author: andreabichsel
manager: AnnBe
ms.date: 07/09/2019
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
ms.openlocfilehash: 50b81ae228d9aee4111ce8d161508d5ed1af4f27
ms.sourcegitcommit: 81e6eaa2178fda7f7d086ad978f4c891bc4ec10a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/10/2019
ms.locfileid: "1738994"
---
# <a name="create-calendar-and-generate-working-times"></a><span data-ttu-id="b6ad1-104">Créer un calendrier et générer les horaires de travail</span><span class="sxs-lookup"><span data-stu-id="b6ad1-104">Create calendar and generate working times</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b6ad1-105">Les calendriers décrivent la capacité et les heures de travail des ressources opérationnelles.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-105">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="b6ad1-106">Cette rubrique explique comment définir un calendrier de travail fondé sur un modèle de temps de travail.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-106">This topic explains how to define a work calendar based on a working time template.</span></span> <span data-ttu-id="b6ad1-107">Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-107">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="b6ad1-108">Sur la page d'accueil, sélectionnez **Gestion des cycles de vie des ressources**.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-108">On the home page, select **Resource lifecycle management**.</span></span>
2. <span data-ttu-id="b6ad1-109">Sélectionnez **Calendriers**.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-109">Select **Calendars**.</span></span>
3. <span data-ttu-id="b6ad1-110">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-110">Select **New**.</span></span>
4. <span data-ttu-id="b6ad1-111">Dans le champ **Calendrier**, classifiez votre calendrier.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-111">In the **Calendar** field, classify your calendar.</span></span> <span data-ttu-id="b6ad1-112">Il s'agit de l'ID du calendrier, lequel sert de référence lors de l'affectation de calendriers, par exemple à une ressource opérationnelle ou à un groupe de ressources.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-112">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="b6ad1-113">Dans le champ **Nom**, nommez votre calendrier.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-113">In the **Name** field, name your calendar.</span></span>
6. <span data-ttu-id="b6ad1-114">Dans le champ **Jour de travail standard en heures**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-114">In the **Standard work day in hours** field, enter a number.</span></span>
7. <span data-ttu-id="b6ad1-115">Assurez-vous que la ligne est activée, puis sélectionnez **Temps de travail** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-115">Make sure the row is selected, then select **Working times** from the Action Pane.</span></span>
8. <span data-ttu-id="b6ad1-116">Sélectionnez **Composer des heures de travail**.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-116">Select **Compose working times**.</span></span> <span data-ttu-id="b6ad1-117">Générez les heures de travail pour chaque jour de la période où vous voulez pouvoir planifier du travail.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="b6ad1-118">Au fur et à mesures, vous pourrez générer des heures de travail pour des périodes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-118">As time goes by, you can generate working times for additional periods.</span></span>  
9. <span data-ttu-id="b6ad1-119">Entrez une date dans le champ **Date de début**.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-119">In the **From date** field, enter a date.</span></span> <span data-ttu-id="b6ad1-120">Il s'agit du premier jour où ce calendrier doit être ouvert.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-120">This is the first day that this calendar must be open.</span></span>  
10. <span data-ttu-id="b6ad1-121">Entrez une date dans le champ **Date de fin**.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-121">In the **To date field**, enter a date.</span></span> <span data-ttu-id="b6ad1-122">Il s'agit du dernier jour où ce calendrier est ouvert.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-122">This is the last day that this calendar is open.</span></span>  
11. <span data-ttu-id="b6ad1-123">Saisissez ou sélectionnez une valeur dans le champ **Modèle de temps de travail**.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-123">In the **Working time template** field, enter or select a value.</span></span> <span data-ttu-id="b6ad1-124">Le modèle de temps de travail définit les heures de travail pour chaque jour de la semaine.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-124">The working time template defines the working hours for each day of the week.</span></span>  
12. <span data-ttu-id="b6ad1-125">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-125">Select **OK**.</span></span>
13. <span data-ttu-id="b6ad1-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b6ad1-126">Close the page.</span></span>

