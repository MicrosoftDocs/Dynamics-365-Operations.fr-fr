---
title: Paramétrage des ressources de projet
description: Cette rubrique fournit des informations sur la configuration ou la demande de ressources de projet.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c882e23794e3937f85b3e73774b36deaf28ac3ed
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760548"
---
# <a name="set-up-project-resources"></a><span data-ttu-id="925a0-103">Paramétrage des ressources de projet</span><span class="sxs-lookup"><span data-stu-id="925a0-103">Set up project resources</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="925a0-104">Vous devez paramétrer un calendrier et l’associer à un employé ou un travailleur.</span><span class="sxs-lookup"><span data-stu-id="925a0-104">You must set up a calendar and associate it with an employee or a worker.</span></span> <span data-ttu-id="925a0-105">Le calendrier est utilisé pour planifier le projet et le temps de travail des ressources réservées au projet.</span><span class="sxs-lookup"><span data-stu-id="925a0-105">The calendar is used to schedule the project and the working time of the resources that are reserved for the project.</span></span> <span data-ttu-id="925a0-106">Pendant le paramétrage du calendrier, les chefs de projet peuvent effectuer la mise à niveau des ressources dans le cadre de l’optimisation des ressources.</span><span class="sxs-lookup"><span data-stu-id="925a0-106">During calendar setup, project managers can do resource leveling as part of resource optimization.</span></span> <span data-ttu-id="925a0-107">Selon le programme du calendrier, des restrictions peuvent être imposées aux ressources.</span><span class="sxs-lookup"><span data-stu-id="925a0-107">Based on the calendar schedule, restrictions can be put on resources.</span></span> <span data-ttu-id="925a0-108">Vous pouvez configurer un calendrier sur la page **Calendriers**.</span><span class="sxs-lookup"><span data-stu-id="925a0-108">You can set up a calendar on the **Calendars** page.</span></span>

<span data-ttu-id="925a0-109">Lorsque vous configurez un collaborateur en tant que ressource de projet, vous pouvez le sélectionner parmi les collaborateurs qui travaillent dans l’entreprise pour laquelle vous configurez des ressources.</span><span class="sxs-lookup"><span data-stu-id="925a0-109">When you set up a worker as a project resource, you can select from workers who work in the company that you're setting up resources for.</span></span> <span data-ttu-id="925a0-110">Sinon, vous pouvez sélectionner les collaborateurs d’autres sociétés de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="925a0-110">Alternatively, you can select workers from other companies in your organization.</span></span> <span data-ttu-id="925a0-111">Ces collaborateurs sont connus comme ressources intersociétés.</span><span class="sxs-lookup"><span data-stu-id="925a0-111">These workers are known as intercompany resources.</span></span>

<span data-ttu-id="925a0-112">Les procédures suivantes expliquent comment paramétrer un travailleur comme ressources de projet au sein de votre société et comment définir une ressource de projet intersociétés.</span><span class="sxs-lookup"><span data-stu-id="925a0-112">The following procedures explain how to set up a worker as a project resource in your company and how to set up an intercompany project resource.</span></span>

## <a name="set-up-a-worker-as-a-project-resource"></a><span data-ttu-id="925a0-113">Paramétrer un collaborateur comme ressource de projet</span><span class="sxs-lookup"><span data-stu-id="925a0-113">Set up a worker as a project resource</span></span>

1. <span data-ttu-id="925a0-114">Dans la page **Collaborateurs** sous la liste **Collaborateurs**, sélectionnez le collaborateur que vous ajoutez comme ressource de projet et ouvrez l’enregistrement de collaborateur.</span><span class="sxs-lookup"><span data-stu-id="925a0-114">On the **Workers** page, in the **Workers** list, select the worker that you're adding as a project resource, and open the worker record.</span></span>
2. <span data-ttu-id="925a0-115">Dans le volet Actions, sélectionnez **Projet** &gt; **Paramétrage** &gt; **Paramétrage de projet**.</span><span class="sxs-lookup"><span data-stu-id="925a0-115">On the Action Pane, select **Project** &gt; **Setup** &gt; **Project setup**.</span></span>
3. <span data-ttu-id="925a0-116">Sélectionnez un calendrier, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="925a0-116">Select a calendar, and then close the page.</span></span>

<span data-ttu-id="925a0-117">Vous pouvez également spécifier des projets par défaut pour une ressource comme un type de pré-affectation.</span><span class="sxs-lookup"><span data-stu-id="925a0-117">You can also specify default projects for a resource as a type of pre-assignment.</span></span> <span data-ttu-id="925a0-118">Les pré-affectations peuvent être utilisées lorsque le responsable de ressources ou le chef de projet sait à l’avance sur quels projets travaillera la ressource.</span><span class="sxs-lookup"><span data-stu-id="925a0-118">Pre-assignments can be used when the resource manager or project manager knows which projects the resource will be working on in advance.</span></span> <span data-ttu-id="925a0-119">Les pré-affectations peuvent également être basées sur la demande d’un commanditaire ou d’un client de projet.</span><span class="sxs-lookup"><span data-stu-id="925a0-119">Pre-assignments can also be based on the request of a project sponsor or customer.</span></span> <span data-ttu-id="925a0-120">Pour pré-affecter un projet, sur la page **Affecter des projets**, sous l’onglet **Projets**, dans la liste **Projets restants**, sélectionnez le projet approprié.</span><span class="sxs-lookup"><span data-stu-id="925a0-120">To pre-assign a project, on the **Assign projects** page, on the **Projects** tab, in the **Remaining projects** list, select the appropriate project.</span></span>

## <a name="set-up-an-intercompany-resource"></a><span data-ttu-id="925a0-121">Paramétrer une ressource intersociétés</span><span class="sxs-lookup"><span data-stu-id="925a0-121">Set up an intercompany resource</span></span>

<span data-ttu-id="925a0-122">Lorsque vous paramétrez un collaborateur comme ressource intersociétés, vous devez compléter le paramétrage dans la société de prêt et la société d’emprunt.</span><span class="sxs-lookup"><span data-stu-id="925a0-122">When you set up a worker as an intercompany resource, you must complete the setup in both the lending company and the borrowing company.</span></span>

### <a name="in-the-lending-company"></a><span data-ttu-id="925a0-123">Dans la société de prêt</span><span class="sxs-lookup"><span data-stu-id="925a0-123">In the lending company</span></span>

1. <span data-ttu-id="925a0-124">Dans Finance, vérifiez que la société de prêt est sélectionnée, puis suivez la procédure ci-dessus dans la section précédente, « Paramétrer un collaborateur comme ressource de projet ».</span><span class="sxs-lookup"><span data-stu-id="925a0-124">In Finance, verify that the lending company is selected, and then complete the procedure in the previous section, "Set up a worker as a project resource."</span></span>
2. <span data-ttu-id="925a0-125">Sur la page **Comptabilité intersociétés**, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="925a0-125">On the **Intercompany accounting** page, select **New**.</span></span>
3. <span data-ttu-id="925a0-126">Dans le champ **ID de l’entité juridique**, sélectionnez la société de prêt.</span><span class="sxs-lookup"><span data-stu-id="925a0-126">In the **Legal entity ID** field, select the lending company.</span></span> <span data-ttu-id="925a0-127">Complétez les champs restants appropriés, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="925a0-127">Fill in the remaining fields as appropriate, and then select **Save**.</span></span>
4. <span data-ttu-id="925a0-128">Sur la page **Prix de transfert**, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="925a0-128">On the **Transfer price** page, select **New**.</span></span>
5. <span data-ttu-id="925a0-129">Dans le champ **Entité juridique emprunteuse**, sélectionnez la société appropriée.</span><span class="sxs-lookup"><span data-stu-id="925a0-129">In the **Borrowing legal entity** field, select the appropriate company.</span></span>
6. <span data-ttu-id="925a0-130">Pour prêter à la société d’emprunt uniquement la ressource que vous avez créée au début de cette section, dans le champ **Ressource**, sélectionnez le nom de la ressource que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="925a0-130">To lend the borrowing company only the resource that you created at the beginning of this section, in the **Resource** field, select the name of the resource that you created.</span></span> <span data-ttu-id="925a0-131">Pour rendre toutes les ressources de la société d’emprunt disponibles à la société d’emprunt, laissez le champ **Ressource** vide.</span><span class="sxs-lookup"><span data-stu-id="925a0-131">To make all resources in the lending company available to the borrowing company, leave the **Resource** field blank.</span></span>
7. <span data-ttu-id="925a0-132">Sur la page **Paramètres de gestion et comptabilité des projets**, sous l’onglet **Intersociétés**, définissez l’option **Activer les feuilles de temps et la programmation des ressources intersociétés** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="925a0-132">On the **Project management and accounting parameters** page, on the **Intercompany** tab, set the **Enable intercompany resource scheduling and timesheets** option to **Yes**.</span></span>

### <a name="in-the-borrowing-company"></a><span data-ttu-id="925a0-133">Dans la société d’emprunt</span><span class="sxs-lookup"><span data-stu-id="925a0-133">In the borrowing company</span></span>

- <span data-ttu-id="925a0-134">Sur la page **Liste des ressources**, dans le filtre de recherche, entrez le nom de la ressource que vous avez créée dans la procédure précédente pour la société de prêt afin de vérifier que le nom est inclus dans la liste des ressources de la société d’emprunt.</span><span class="sxs-lookup"><span data-stu-id="925a0-134">On the **Resources list** page, in the search filter, enter the name of the resource that you created for the lending company, to verify that the name is included in the resource list for the borrowing company.</span></span>

## <a name="request-project-resources"></a><span data-ttu-id="925a0-135">Demander des ressources de projet</span><span class="sxs-lookup"><span data-stu-id="925a0-135">Request project resources</span></span>
<span data-ttu-id="925a0-136">La fonctionnalité de planification des ressources de projet permet uniquement aux responsables de ressources de répartir les ressources avec personnel entre les engagements ou les projets.</span><span class="sxs-lookup"><span data-stu-id="925a0-136">The functionality for project resource scheduling only lets resource managers distribute staffed resources on engagements or projects.</span></span> <span data-ttu-id="925a0-137">Pour activer cette fonctionnalité, effectuez les tâches suivantes ou vérifiez qu’elles ont été effectuées :</span><span class="sxs-lookup"><span data-stu-id="925a0-137">To enable this functionality, complete the following tasks, or verify that they have been completed:</span></span>

- <span data-ttu-id="925a0-138">Permet de définir des souches de numéros.</span><span class="sxs-lookup"><span data-stu-id="925a0-138">Set up number sequences.</span></span>
- <span data-ttu-id="925a0-139">Paramétrage des workflows du module Gestion de projets et comptabilité.</span><span class="sxs-lookup"><span data-stu-id="925a0-139">Set up project management and accounting workflows.</span></span>
- <span data-ttu-id="925a0-140">Activer les workflows de demande de la ressource.</span><span class="sxs-lookup"><span data-stu-id="925a0-140">Enable resource request workflows.</span></span>

<span data-ttu-id="925a0-141">Après avoir vérifié ou avoir effectué les tâches ci-dessus, vous pouvez effectuer les tâches suivantes si nécessaire :</span><span class="sxs-lookup"><span data-stu-id="925a0-141">After the preceding tasks have been completed, you can complete the following tasks as you require:</span></span>

- <span data-ttu-id="925a0-142">Créer une demande de ressource à partir d’une ressource avec personnel réservé provisoirement.</span><span class="sxs-lookup"><span data-stu-id="925a0-142">Create a resource request from a soft-booked staffed resource.</span></span>
- <span data-ttu-id="925a0-143">Contrôler les demandes de ressources.</span><span class="sxs-lookup"><span data-stu-id="925a0-143">Monitor resource requests.</span></span>
- <span data-ttu-id="925a0-144">Traiter les demandes de ressources.</span><span class="sxs-lookup"><span data-stu-id="925a0-144">Fulfill resource requests.</span></span>
- <span data-ttu-id="925a0-145">Demander une ressource avec personnel auprès d’un WBS.</span><span class="sxs-lookup"><span data-stu-id="925a0-145">Request a staffed resource from a WBS.</span></span>
- <span data-ttu-id="925a0-146">Réserver des ressources pour un projet sans demander de ressource avec personnel.</span><span class="sxs-lookup"><span data-stu-id="925a0-146">Book resources to a project without having a request for a staffed resource.</span></span>
