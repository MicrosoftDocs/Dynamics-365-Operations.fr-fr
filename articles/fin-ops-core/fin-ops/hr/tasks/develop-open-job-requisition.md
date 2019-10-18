---
title: Développer et ouvrir une demande de poste
description: Les projets de recrutement permettent de gérer le processus de recrutement.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMRecruitingTable, HcmWorkerLookUp, HcmJobLookup, HRMRecruitingMedia, HRMRecruitingJobAd
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 556f99d34521cce70efb64c5fbababd815e8429d
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190463"
---
# <a name="develop-and-open-job-requisition"></a><span data-ttu-id="c6a4a-103">Développer et ouvrir une demande de poste</span><span class="sxs-lookup"><span data-stu-id="c6a4a-103">Develop and open job requisition</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c6a4a-104">Les projets de recrutement permettent de gérer le processus de recrutement.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-104">Recruitment projects help manage the recruiting process.</span></span> <span data-ttu-id="c6a4a-105">Pour chaque projet de recrutement, vous pouvez paramétrer des informations, telles que l'emploi pour lequel vous recrutez, le nom du recruteur, le statut du projet et le département auquel l'employé sera rattaché.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-105">For each recruitment project, you can set up information, such as the job that recruiting is for, the name of the recruiter, the status of the project and the department that the job will be located in.</span></span> <span data-ttu-id="c6a4a-106">Après avoir créé un projet de recrutement, vous pouvez rédiger une annonce d'emploi pour le projet, la publier dans les pages Libre-service employé, associer des demandes d'emploi au projet et suivre les activités du projet.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-106">After creating a recruitment project, you can write a job advertisement for the project, publish the ad on Employee self-service pages, associate applications for employment with the project, and track activities for that project.</span></span> <span data-ttu-id="c6a4a-107">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c6a4a-108">Pour démarrer la procédure, allez dans Ressources humaines > Recrutement > Projets de recrutement > Projets de recrutement.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-108">To begin the procedure, go to Human resources > Recruitment > Recruitment projects > Recruitment projects</span></span>

1. <span data-ttu-id="c6a4a-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-109">Click New.</span></span>
2. <span data-ttu-id="c6a4a-110">Tapez une valeur dans le champ Projet de recrutement.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-110">In the Recruitment project field, type a value.</span></span>
3. <span data-ttu-id="c6a4a-111">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-111">In the Description field, type a value.</span></span>
4. <span data-ttu-id="c6a4a-112">Cliquez sur le bouton de liste déroulante pour ouvrir la recherche dans le champ Recruteur.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-112">In the Recruiter field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="c6a4a-113">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-113">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="c6a4a-114">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-114">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="c6a4a-115">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-115">Click Select.</span></span>
8. <span data-ttu-id="c6a4a-116">Cliquez sur le bouton de liste déroulante pour ouvrir la recherche dans le champ Département.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-116">In the Department field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="c6a4a-117">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-117">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="c6a4a-118">Cliquez sur le bouton de liste déroulante pour ouvrir la recherche dans le champ Tâche.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-118">In the Job field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="c6a4a-119">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-119">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="c6a4a-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-120">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="c6a4a-121">Entrez un nombre dans le champ Nombre de postes à pourvoir.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-121">In the Number of openings field, enter a number.</span></span>
14. <span data-ttu-id="c6a4a-122">Cliquez sur le bouton de liste déroulante pour ouvrir la recherche dans le champ Responsable de l'embauche.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-122">In the Hiring manager field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="c6a4a-123">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-123">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="c6a4a-124">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-124">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="c6a4a-125">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-125">Click Select.</span></span>
18. <span data-ttu-id="c6a4a-126">Entrez une date dans le champ Date limite de candidature.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-126">In the Application deadline field, enter a date.</span></span>
19. <span data-ttu-id="c6a4a-127">Cliquez sur Support.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-127">Click Media.</span></span>
    * <span data-ttu-id="c6a4a-128">Les projets de recrutement offrent la possibilité de spécifier les établissements de communication à utiliser pour signaler des postes vacants.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-128">Recruitment projects include the option to specify media outlets to use to advertise open positions.</span></span>  
20. <span data-ttu-id="c6a4a-129">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-129">Click New.</span></span>
21. <span data-ttu-id="c6a4a-130">Cliquez sur le bouton de liste déroulante pour ouvrir la recherche dans le champ Support.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-130">In the Media field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="c6a4a-131">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-131">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="c6a4a-132">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-132">In the Start date field, enter a date.</span></span>
24. <span data-ttu-id="c6a4a-133">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-133">In the End date field, enter a date.</span></span>
25. <span data-ttu-id="c6a4a-134">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-134">Click Save.</span></span>
26. <span data-ttu-id="c6a4a-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-135">Close the page.</span></span>
27. <span data-ttu-id="c6a4a-136">Cliquez sur Annonces d'emploi.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-136">Click Job ads.</span></span>
28. <span data-ttu-id="c6a4a-137">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-137">Click Save.</span></span>
29. <span data-ttu-id="c6a4a-138">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-138">Close the page.</span></span>
30. <span data-ttu-id="c6a4a-139">Activez ou désactivez la case à cocher Afficher dans le libre-service pour employés.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-139">Check or uncheck the Display on employee self service checkbox.</span></span>
    * <span data-ttu-id="c6a4a-140">Activez la case à cocher Afficher dans le libre-service pour employés pour que les employés puissent consulter le projet de recrutement dans les pages Libre-service employé.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-140">Select the Display on employee self service check box to make the recruitment project visible to employees on their Employee self-service pages.</span></span>  
31. <span data-ttu-id="c6a4a-141">Cliquez sur Statut du projet de recrutement.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-141">Click Recruitment project status.</span></span>
32. <span data-ttu-id="c6a4a-142">Cliquez sur Démarrer.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-142">Click Start.</span></span>
    * <span data-ttu-id="c6a4a-143">Le statut Démarré indique qu'il est possible d'envoyer des candidatures pour le projet.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-143">The Started status means that the project is ready to receive applications.</span></span>  
33. <span data-ttu-id="c6a4a-144">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c6a4a-144">Click OK.</span></span>

