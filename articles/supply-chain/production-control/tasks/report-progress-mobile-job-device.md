---
title: Générer un état de la progression sur un périphérique mobile
description: Cette procédure vous indique comment démarrer une tâche de production et générer un état de la progression de celle-ci dans le formulaire d'enregistrement du périphérique de tâche.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationTouch, JmgRegistrationTouchUserConfiguration, JmgRegistrationTouchStart, JmgRegistrationTouchReportFeedback, JmgRegistrationTouchAssignedJobs, JmgRegistrationTouchBreak, JmgRegistrationTouchLeave, JmgRegistrationTouchIndirectActivity, JmgDialogForm, JmgRegistrationTouchReportProgress, JmgFeedbackWizard, JmgJobBundleProdFeedback
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 34067902f05546b5c420feca633f77f16033ed2c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427872"
---
# <a name="report-progress-on-a-mobile-job-device"></a><span data-ttu-id="1a547-103">Générer un état de la progression sur un périphérique mobile</span><span class="sxs-lookup"><span data-stu-id="1a547-103">Report progress on a mobile job device</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1a547-104">Cette procédure vous indique comment démarrer une tâche de production et générer un état de la progression de celle-ci dans le formulaire d'enregistrement du périphérique de tâche.</span><span class="sxs-lookup"><span data-stu-id="1a547-104">This procedure shows you how to start and report progress on a production job in the job device registration form.</span></span>



<span data-ttu-id="1a547-105">Pour que vous soyez en mesure d'exécuter cette procédure, le rôle Administrateur système ou Opérateur doit être associé au compte utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a547-105">To be able to run this procedure you must have the System administator or Machine Operator role associated with the user account.</span></span>

1. <span data-ttu-id="1a547-106">Accédez à Contrôle de la production > Contrôle et suivi de la production > Périphérique pour le bon de travail.</span><span class="sxs-lookup"><span data-stu-id="1a547-106">Go to Production control > Manufacturing execution > Job card device.</span></span>
2. <span data-ttu-id="1a547-107">Dans le champ WorkerTextField, entrez le numéro de badge d'un collaborateur.</span><span class="sxs-lookup"><span data-stu-id="1a547-107">In the WorkerTextField field, enter the badge of a worker.</span></span> <span data-ttu-id="1a547-108">Dans la société fictive USMF, tapez « 123 » pour Christina. Portra.</span><span class="sxs-lookup"><span data-stu-id="1a547-108">In the USMF demo data type '123' for Christina Portra..</span></span>
3. <span data-ttu-id="1a547-109">Cliquez sur Connexion.</span><span class="sxs-lookup"><span data-stu-id="1a547-109">Click Log in.</span></span>
4. <span data-ttu-id="1a547-110">Cliquez sur le bouton de filtre.</span><span class="sxs-lookup"><span data-stu-id="1a547-110">Click the Filter button.</span></span>
5. <span data-ttu-id="1a547-111">Cochez ou décochez la case Appliquer le filtre de configuration.</span><span class="sxs-lookup"><span data-stu-id="1a547-111">Check or uncheck the Apply configuration filter check box.</span></span> <span data-ttu-id="1a547-112">Si vous définissez un filtre, vous pouvez utiliser l'unité de production 110 dans USMF.</span><span class="sxs-lookup"><span data-stu-id="1a547-112">If you set a filter you can use production unit 110 in USMF.</span></span>
6. <span data-ttu-id="1a547-113">Dans le champ Unité de production, sélectionnez le groupe de ressources sur les tâches de production duquel les collaborateurs peuvent travailler.</span><span class="sxs-lookup"><span data-stu-id="1a547-113">In the Production unit field, select the ressource group for which production jobs the worker can work on.</span></span>
7. <span data-ttu-id="1a547-114">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1a547-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="1a547-115">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1a547-115">Click OK.</span></span>
9. <span data-ttu-id="1a547-116">Cliquez sur le bouton Démarrer la tâche.</span><span class="sxs-lookup"><span data-stu-id="1a547-116">Click the Start job button.</span></span>
10. <span data-ttu-id="1a547-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1a547-117">Click OK.</span></span>
11. <span data-ttu-id="1a547-118">Cliquez sur le bouton Connaître l'état de progression.</span><span class="sxs-lookup"><span data-stu-id="1a547-118">Click the Report progress button.</span></span>
12. <span data-ttu-id="1a547-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1a547-119">Click OK.</span></span>
13. <span data-ttu-id="1a547-120">Cliquez sur le bouton Tâche suivante.</span><span class="sxs-lookup"><span data-stu-id="1a547-120">Click the Next job button.</span></span>
14. <span data-ttu-id="1a547-121">Cliquez sur Affecté pour afficher une vue d'ensemble de tous les boutons des tâches de production.</span><span class="sxs-lookup"><span data-stu-id="1a547-121">Click the Assigned to see an overview of all production jobs button.</span></span>
15. <span data-ttu-id="1a547-122">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1a547-122">Close the page.</span></span>
16. <span data-ttu-id="1a547-123">Cliquez sur le bouton Pause.</span><span class="sxs-lookup"><span data-stu-id="1a547-123">Click the Break button.</span></span>
17. <span data-ttu-id="1a547-124">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1a547-124">In the list, find and select the desired record.</span></span>
18. <span data-ttu-id="1a547-125">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1a547-125">Click OK.</span></span>
19. <span data-ttu-id="1a547-126">Cliquez sur le bouton Sortie.</span><span class="sxs-lookup"><span data-stu-id="1a547-126">Click the Leaving button.</span></span>
20. <span data-ttu-id="1a547-127">Sélectionnez cette option pour vous déconnecter.</span><span class="sxs-lookup"><span data-stu-id="1a547-127">Select to log out.</span></span>
21. <span data-ttu-id="1a547-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1a547-128">Click OK.</span></span>
22. <span data-ttu-id="1a547-129">Dans le champ WorkerTextField, connectez-vous de nouveau.</span><span class="sxs-lookup"><span data-stu-id="1a547-129">In the WorkerTextField field, log in again.</span></span> <span data-ttu-id="1a547-130">Vous pouvez sélectionner le travailleur « 123 » dans la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="1a547-130">You can select worker '123' in USMF demo data.</span></span>
23. <span data-ttu-id="1a547-131">Cliquez sur Connexion.</span><span class="sxs-lookup"><span data-stu-id="1a547-131">Click Log in.</span></span>
24. <span data-ttu-id="1a547-132">Cliquez sur Fin de pause.</span><span class="sxs-lookup"><span data-stu-id="1a547-132">Click Stop break.</span></span>
25. <span data-ttu-id="1a547-133">Cliquez sur le bouton Activité.</span><span class="sxs-lookup"><span data-stu-id="1a547-133">Click the Activity button.</span></span>
26. <span data-ttu-id="1a547-134">Cliquez sur Annuler.</span><span class="sxs-lookup"><span data-stu-id="1a547-134">Click Cancel.</span></span>
27. <span data-ttu-id="1a547-135">Cliquez sur le bouton Sortie.</span><span class="sxs-lookup"><span data-stu-id="1a547-135">Click the Leaving button.</span></span>
28. <span data-ttu-id="1a547-136">Sélectionnez cette option pour pointer à la sortie.</span><span class="sxs-lookup"><span data-stu-id="1a547-136">Select to clock out.</span></span>
29. <span data-ttu-id="1a547-137">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1a547-137">Click OK.</span></span>
30. <span data-ttu-id="1a547-138">Sélectionnez une raison pour laquelle vous pointez à la sortie de façon anticipée.</span><span class="sxs-lookup"><span data-stu-id="1a547-138">Select a reason why you are clocking out early.</span></span>

