---
title: Créer des calendriers et générer les horaires de travail
description: Les calendriers décrivent la capacité et les heures de travail des ressources opérationnelles. Cet article explique comment définir un calendrier de travail fondé sur un modèle de temps de travail.
author: andreabichsel
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkCalendarTable, WorkCalendarDate, HcmPersonnelManagementWorkspace, WrkCtrGroupDateCalendar, WrkCtrDateCalendar
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f5c630297a8962d1bb383110881b2acdc872b9cd
ms.sourcegitcommit: 175f9394021322c685c5b37317c2f649c81a731a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "3826095"
---
# <a name="create-calendars-and-generate-working-times"></a><span data-ttu-id="5658a-104">Créer des calendriers et générer les horaires de travail</span><span class="sxs-lookup"><span data-stu-id="5658a-104">Create calendars and generate working times</span></span>



<span data-ttu-id="5658a-105">Les calendriers décrivent la capacité et les heures de travail des ressources opérationnelles.</span><span class="sxs-lookup"><span data-stu-id="5658a-105">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="5658a-106">Cet article explique comment définir un calendrier de travail fondé sur un modèle de temps de travail.</span><span class="sxs-lookup"><span data-stu-id="5658a-106">This article explains how to define a work calendar based on a working time template.</span></span> <span data-ttu-id="5658a-107">Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="5658a-107">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="5658a-108">Sur la page d'accueil, sélectionnez **Gestion des cycles de vie des ressources**.</span><span class="sxs-lookup"><span data-stu-id="5658a-108">On the home page, select **Resource lifecycle management**.</span></span>
2. <span data-ttu-id="5658a-109">Sélectionnez **Calendriers**.</span><span class="sxs-lookup"><span data-stu-id="5658a-109">Select **Calendars**.</span></span>
3. <span data-ttu-id="5658a-110">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="5658a-110">Select **New**.</span></span>
4. <span data-ttu-id="5658a-111">Dans le champ **Calendrier**, classifiez votre calendrier.</span><span class="sxs-lookup"><span data-stu-id="5658a-111">In the **Calendar** field, classify your calendar.</span></span> <span data-ttu-id="5658a-112">Il s'agit de l'ID du calendrier, lequel sert de référence lors de l'affectation de calendriers, par exemple à une ressource opérationnelle ou à un groupe de ressources.</span><span class="sxs-lookup"><span data-stu-id="5658a-112">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="5658a-113">Dans le champ **Nom**, nommez votre calendrier.</span><span class="sxs-lookup"><span data-stu-id="5658a-113">In the **Name** field, name your calendar.</span></span>
6. <span data-ttu-id="5658a-114">Dans le champ **Jour de travail standard en heures**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="5658a-114">In the **Standard work day in hours** field, enter a number.</span></span>
7. <span data-ttu-id="5658a-115">Assurez-vous que la ligne est activée, puis sélectionnez **Temps de travail** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="5658a-115">Make sure the row is selected, then select **Working times** from the Action Pane.</span></span>
8. <span data-ttu-id="5658a-116">Sélectionnez **Composer des heures de travail**.</span><span class="sxs-lookup"><span data-stu-id="5658a-116">Select **Compose working times**.</span></span> <span data-ttu-id="5658a-117">Générez les heures de travail pour chaque jour de la période où vous voulez pouvoir planifier du travail.</span><span class="sxs-lookup"><span data-stu-id="5658a-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="5658a-118">Au fur et à mesures, vous pourrez générer des heures de travail pour des périodes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="5658a-118">As time goes by, you can generate working times for additional periods.</span></span>  
9. <span data-ttu-id="5658a-119">Entrez une date dans le champ **Date de début**.</span><span class="sxs-lookup"><span data-stu-id="5658a-119">In the **From date** field, enter a date.</span></span> <span data-ttu-id="5658a-120">Il s'agit du premier jour où ce calendrier doit être ouvert.</span><span class="sxs-lookup"><span data-stu-id="5658a-120">This is the first day that this calendar must be open.</span></span>  
10. <span data-ttu-id="5658a-121">Entrez une date dans le champ **Date de fin**.</span><span class="sxs-lookup"><span data-stu-id="5658a-121">In the **To date field**, enter a date.</span></span> <span data-ttu-id="5658a-122">Il s'agit du dernier jour où ce calendrier est ouvert.</span><span class="sxs-lookup"><span data-stu-id="5658a-122">This is the last day that this calendar is open.</span></span>  
11. <span data-ttu-id="5658a-123">Saisissez ou sélectionnez une valeur dans le champ **Modèle de temps de travail**.</span><span class="sxs-lookup"><span data-stu-id="5658a-123">In the **Working time template** field, enter or select a value.</span></span> <span data-ttu-id="5658a-124">Le modèle de temps de travail définit les heures de travail pour chaque jour de la semaine.</span><span class="sxs-lookup"><span data-stu-id="5658a-124">The working time template defines the working hours for each day of the week.</span></span>  
12. <span data-ttu-id="5658a-125">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5658a-125">Select **OK**.</span></span>
13. <span data-ttu-id="5658a-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5658a-126">Close the page.</span></span>

