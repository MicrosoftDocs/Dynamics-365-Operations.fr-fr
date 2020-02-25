---
title: Création d'un calendrier du temps de travail
description: Définissez un calendrier du temps de travail, des jours fériés et du temps libre dans Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 641f66c75875cfba51af3753223a070d7cb7dc50
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009053"
---
# <a name="create-a-working-time-calendar"></a><span data-ttu-id="126e7-103">Création d'un calendrier du temps de travail</span><span class="sxs-lookup"><span data-stu-id="126e7-103">Create a working time calendar</span></span>

<span data-ttu-id="126e7-104">Un calendrier du temps de travail Dynamics 365 Human Resources affiche les jours et les heures de travail des employés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="126e7-104">A working time calendar in Dynamics 365 Human Resources shows the days and hours that employees work in your organization.</span></span> <span data-ttu-id="126e7-105">Lorsqu'un employé soumet une demande de congé, il n'a pas à se soucier des congés et des fermetures.</span><span class="sxs-lookup"><span data-stu-id="126e7-105">When an employee submits a time-off request, they don't have to worry about holidays and closures.</span></span>

<span data-ttu-id="126e7-106">Pour rationaliser les demandes de congés, configurez ces éléments pour votre organisation :</span><span class="sxs-lookup"><span data-stu-id="126e7-106">To streamline time-off requests, configure these items for your organization:</span></span>

- <span data-ttu-id="126e7-107">Calendrier du temps de travail</span><span class="sxs-lookup"><span data-stu-id="126e7-107">Working time calendar</span></span>
- <span data-ttu-id="126e7-108">Congés et fermetures</span><span class="sxs-lookup"><span data-stu-id="126e7-108">Holidays and closures</span></span>
- <span data-ttu-id="126e7-109">Temps libre</span><span class="sxs-lookup"><span data-stu-id="126e7-109">Non-work time</span></span>

<span data-ttu-id="126e7-110">Vous pouvez ajouter les deux derniers éléments pendant que vous configurez un calendrier du temps de travail.</span><span class="sxs-lookup"><span data-stu-id="126e7-110">You can add the last two items while you're setting up a working time calendar.</span></span> <span data-ttu-id="126e7-111">Vous pouvez également les configurer ou les mettre à jour séparément.</span><span class="sxs-lookup"><span data-stu-id="126e7-111">You can also configure or update them separately.</span></span>

## <a name="set-up-a-working-time-calendar"></a><span data-ttu-id="126e7-112">Paramétrage d'un calendrier de temps de travail</span><span class="sxs-lookup"><span data-stu-id="126e7-112">Set up a working time calendar</span></span>

<span data-ttu-id="126e7-113">Configurez au moins un calendrier de temps de travail qui affiche vos jours et heures d'ouverture.</span><span class="sxs-lookup"><span data-stu-id="126e7-113">Set up at least one working time calendar that shows your days and hours of operation.</span></span> <span data-ttu-id="126e7-114">Si vous avez des emplacements dans plusieurs pays et régions, vous pouvez configurer un calendrier de temps de travail pour chaque zone.</span><span class="sxs-lookup"><span data-stu-id="126e7-114">If you have locations in multiple countries and regions, you might want to set up a working time calendar for each area.</span></span>

1. <span data-ttu-id="126e7-115">Dans la page **Administration d'organisation**, sélectionnez **Calendriers**.</span><span class="sxs-lookup"><span data-stu-id="126e7-115">On the **Organization administration** page, select **Calendars**.</span></span>

2. <span data-ttu-id="126e7-116">Sélectionnez **Nouveau** et entrez un nom et une description pour votre calendrier.</span><span class="sxs-lookup"><span data-stu-id="126e7-116">Select **New** and enter a name and description for your calendar.</span></span>

3. <span data-ttu-id="126e7-117">Sous **Options de génération**, sélectionnez les jours ouvrables de votre organisation et saisissez les heures de travail.</span><span class="sxs-lookup"><span data-stu-id="126e7-117">Under **Generation options**, select the work days for your organization and enter work times.</span></span> 
   - <span data-ttu-id="126e7-118">Pour ajouter un jour férié ou une fermeture, sélectionnez le bouton **Ajouter** à côté de **Congés et fermetures**.</span><span class="sxs-lookup"><span data-stu-id="126e7-118">To add a holiday or closure, select the **Add** button next to **Holidays and closures**.</span></span>
   - <span data-ttu-id="126e7-119">Pour ajouter du temps libre, comme des déjeuners ou des pauses, sélectionnez **Ajouter** sous **TEMPS LIBRE** et entrez le nom et la plage horaire.</span><span class="sxs-lookup"><span data-stu-id="126e7-119">To add non-work time, like lunches or breaks, select **Add** under **NON-WORK TIME** and enter the name and time range.</span></span>

4. <span data-ttu-id="126e7-120">Sous **Jours**, sélectionnez **Générer** pour générer les jours dans votre calendrier.</span><span class="sxs-lookup"><span data-stu-id="126e7-120">Under **Days**, select **Generate** to generate the days in your calendar.</span></span> <span data-ttu-id="126e7-121">Saisissez la plage de dates de votre calendrier, puis sélectionnez **Générer des jours**.</span><span class="sxs-lookup"><span data-stu-id="126e7-121">Enter the date range for your calendar and then select **Generate days**.</span></span>

5. <span data-ttu-id="126e7-122">Pour ajouter des plannings de travail, sous **Planning de travail**, sélectionnez **Ajouter**, puis entrez les heures de chaque planning de travail.</span><span class="sxs-lookup"><span data-stu-id="126e7-122">To add work schedules, under **Work schedule**, select **Add** and then enter the times for each work schedule.</span></span>

## <a name="configure-holidays-and-closures"></a><span data-ttu-id="126e7-123">Configuration des congés et fermetures</span><span class="sxs-lookup"><span data-stu-id="126e7-123">Configure holidays and closures</span></span>

<span data-ttu-id="126e7-124">Vous pouvez ajouter ou modifier des congés et des fermetures séparément d'un calendrier de temps de travail.</span><span class="sxs-lookup"><span data-stu-id="126e7-124">You can add or change holidays and closures separately from a working time calendar.</span></span>

1. <span data-ttu-id="126e7-125">Dans la page **Administration d'organisation**, sélectionnez **Congés et fermetures**.</span><span class="sxs-lookup"><span data-stu-id="126e7-125">On the **Organization administration** page, select **Holidays and closures**.</span></span>

2. <span data-ttu-id="126e7-126">Sélectionnez **Nouveau** et entrez un nom et une date de congés ou de fermeture.</span><span class="sxs-lookup"><span data-stu-id="126e7-126">Select **New** and enter a name and date for the holiday or closure.</span></span>

## <a name="configure-non-work-time"></a><span data-ttu-id="126e7-127">Configuration du temps libre</span><span class="sxs-lookup"><span data-stu-id="126e7-127">Configure non-work time</span></span>

<span data-ttu-id="126e7-128">Vous pouvez ajouter ou modifier du temps libre séparément d'un calendrier de temps de travail.</span><span class="sxs-lookup"><span data-stu-id="126e7-128">You can add or change non-work times separately from a working time calendar.</span></span>

1. <span data-ttu-id="126e7-129">Dans la page **Administration d'organisation**, sélectionnez **Temps libre**.</span><span class="sxs-lookup"><span data-stu-id="126e7-129">On the **Organization administration** page, select **Non-work time**.</span></span>

2. <span data-ttu-id="126e7-130">Sélectionnez **Nouveau** et entrez le nom et la plage de temps pour le temps libre.</span><span class="sxs-lookup"><span data-stu-id="126e7-130">Select **New** and enter a name and time range for the non-work time.</span></span>

## <a name="leave-and-absence-preview-feature"></a><span data-ttu-id="126e7-131">Fonctionnalité d'aperçu des congés et absences</span><span class="sxs-lookup"><span data-stu-id="126e7-131">Leave and absence preview feature</span></span>

[!include [banner](includes/preview-feature-leave-absence.md)]

<span data-ttu-id="126e7-132">Si vous avez activé la fonction d'aperçu des corrections des jours fériés pour les congés et absences, Human Resources utilise les dates de congés et de fermeture pour déterminer le nombre de jours à ajuster pour les employés inscrits au calendrier.</span><span class="sxs-lookup"><span data-stu-id="126e7-132">If you've enabled the Leave and absence bank holiday corrections preview feature, Human Resources uses holidays and closure dates to determine the number of days to adjust for employees enrolled in the calendar.</span></span>

## <a name="see-also"></a><span data-ttu-id="126e7-133">Voir également :</span><span class="sxs-lookup"><span data-stu-id="126e7-133">See also</span></span>

- [<span data-ttu-id="126e7-134">Vue d'ensemble des congés et des absences</span><span class="sxs-lookup"><span data-stu-id="126e7-134">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="126e7-135">Configuration des types de congé et d'absence</span><span class="sxs-lookup"><span data-stu-id="126e7-135">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)
