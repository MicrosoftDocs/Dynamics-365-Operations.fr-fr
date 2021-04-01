---
title: Définir les agents de maintenance préférés
description: Cette rubrique explique comment paramétrer des agents de maintenance préférés dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkerPreferred
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 102f48d1273ac91d5cb42eca11d2dec337c30528
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5214960"
---
# <a name="set-up-preferred-maintenance-workers"></a><span data-ttu-id="fb304-103">Définir les agents de maintenance préférés</span><span class="sxs-lookup"><span data-stu-id="fb304-103">Set up preferred maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="fb304-104">Lors de la planification des ordres de travail, vous pouvez définir une préférence concernant l’agent de maintenance ou le groupe de collaborateurs affecté pour effectuer l’ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="fb304-104">During work order scheduling, you can make a preference regarding which maintenance worker or worker group is allocated to complete the work order.</span></span> <span data-ttu-id="fb304-105">L’utilisation de cette fonctionnalité est facultative. Elle peut néanmoins vous aider à choisir l’agent de maintenance le plus qualifié pour effectuer une tâche, selon les compétences et les aptitudes des agents.</span><span class="sxs-lookup"><span data-stu-id="fb304-105">The use of this functionality is optional, but it can help you make a choice for the most qualified maintenance worker to complete a job, based on worker skills and competencies.</span></span> <span data-ttu-id="fb304-106">Seuls les agents de maintenance qui sont disponibles pour le temps de planification sont planifiés.</span><span class="sxs-lookup"><span data-stu-id="fb304-106">Only maintenance workers that are available at scheduling time will be scheduled.</span></span> <span data-ttu-id="fb304-107">Si un paramétrage d’agent de maintenance préféré correspond à un ordre de travail durant la planification, mais si l’agent de maintenance est alloué à d’autres tâches, l’ordre de travail est alors planifié pour un autre agent de maintenance disponible.</span><span class="sxs-lookup"><span data-stu-id="fb304-107">If a preferred maintenance worker setup matches a work order during scheduling, but the maintenance worker is allocated to other jobs, the work order will be scheduled to another available maintenance worker.</span></span>

<span data-ttu-id="fb304-108">Avant de paramétrer des agents de maintenance recommandés, vous devez d’abord paramétrer les agents de maintenance et les groupes de collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="fb304-108">Before you can set up preferred maintenance workers, you must first set up the maintenance workers and worker groups.</span></span> <span data-ttu-id="fb304-109">Pour une description de la manière de configurer les agents et groupes d’agents de maintenance, consultez [Agents et groupes d’agents de maintenance](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="fb304-109">For a description about how to set up maintenance workers and worker groups, see to [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

## <a name="set-up-preferred-workers"></a><span data-ttu-id="fb304-110">Configurer les agents préférés</span><span class="sxs-lookup"><span data-stu-id="fb304-110">Set up preferred workers</span></span>

<span data-ttu-id="fb304-111">Un agent de maintenance ou un groupe d’agents de maintenance préféré peut être associé à l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="fb304-111">A preferred maintenance worker or worker group can be related to one or more of the following:</span></span>

- <span data-ttu-id="fb304-112">commerce</span><span class="sxs-lookup"><span data-stu-id="fb304-112">trade</span></span>  
- <span data-ttu-id="fb304-113">variante du type de tâche de maintenance</span><span class="sxs-lookup"><span data-stu-id="fb304-113">maintenance job type variant</span></span>  
- <span data-ttu-id="fb304-114">type de tâche de maintenance</span><span class="sxs-lookup"><span data-stu-id="fb304-114">maintenance job type</span></span>  
- <span data-ttu-id="fb304-115">catégorie de type tâche de maintenance</span><span class="sxs-lookup"><span data-stu-id="fb304-115">maintenance job type category</span></span>  
- <span data-ttu-id="fb304-116">actif</span><span class="sxs-lookup"><span data-stu-id="fb304-116">asset</span></span>  
- <span data-ttu-id="fb304-117">type d’actif spécifique</span><span class="sxs-lookup"><span data-stu-id="fb304-117">asset type</span></span>  

<span data-ttu-id="fb304-118">Plus vous faites de sélections pour le même enregistrement, plus votre paramétrage est spécifique.</span><span class="sxs-lookup"><span data-stu-id="fb304-118">The more selections you make for the same record, the more specific your setup will be.</span></span>

1. <span data-ttu-id="fb304-119">Cliquez sur **Gestion des actifs** > **Paramétrage** > **Agents** > **Agents de maintenance préférés**.</span><span class="sxs-lookup"><span data-stu-id="fb304-119">Click **Asset management** > **Setup** > **Workers** > **Preferred maintenance workers**.</span></span>

2. <span data-ttu-id="fb304-120">Cliquez sur **Nouveau** pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="fb304-120">Click **New** to create a new record.</span></span>

3. <span data-ttu-id="fb304-121">Commencez par créer un agents et groupes d’agents de maintenance « par défaut ».</span><span class="sxs-lookup"><span data-stu-id="fb304-121">Start by creating a "default" maintenance worker or worker group.</span></span> <span data-ttu-id="fb304-122">Autrement dit, vous effectuez une seule sélection dans le champ **Groupe d’agents de maintenance préféré** ou le champ **Agent de maintenance préféré**.</span><span class="sxs-lookup"><span data-stu-id="fb304-122">This means that you only make a selection in the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field.</span></span> <span data-ttu-id="fb304-123">Dans la capture d’écran ci-dessous, vous voyez un exemple dans le premier enregistrement dans lequel « Demandes » est sélectionné comme le **groupe d’agents de maintenance préféré**.</span><span class="sxs-lookup"><span data-stu-id="fb304-123">In the screenshot below, you see an example in the first record in which "Requests" is selected as **Preferred maintenance worker group**.</span></span>

    [!NOTE] <span data-ttu-id="fb304-124">Le paramétrage par défaut sera utilisé lors de la planification des ordres de travail si aucune autre combinaison plus spécifique ne correspond au contenu de l’ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="fb304-124">The default setup will be used during work order scheduling if no other, more specific, combination matches the contents of the work order.</span></span>

4. <span data-ttu-id="fb304-125">Répétez l’étape 2 pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="fb304-125">Repeat step 2 to create a new record.</span></span> <span data-ttu-id="fb304-126">Effectuez les sélections nécessaires, selon le niveau de détail pour l’agent ou le groupe d’agents de maintenance préféré.</span><span class="sxs-lookup"><span data-stu-id="fb304-126">Make the required selections, depending on the detail level for the preferred worker or worker group.</span></span> 

    <span data-ttu-id="fb304-127">*Exemple :* dans la capture d’écran ci-dessous, dans le sixième enregistrement, l’agent de maintenance Shawn Richardson est sélectionné comme agent préféré.</span><span class="sxs-lookup"><span data-stu-id="fb304-127">*Example:* In the screenshot below, in the sixth record, the maintenance worker Shawn Richardson is selected as preferred worker.</span></span> <span data-ttu-id="fb304-128">Il est automatiquement sélectionné lors de la planification d’un ordre de travail contenant l’agent « CH-BP1-03-02 et la tâche de maintenance de type "Évaluation du site" », s’il est disponible au moment prévu.</span><span class="sxs-lookup"><span data-stu-id="fb304-128">He will automatically be selected during scheduling of a work order that includes the asset "CH-BP1-03-02 and the maintenance job type "Facility assessment", if he is available at the scheduled time.</span></span>

    [!NOTE] <span data-ttu-id="fb304-129">En général, si un agent de maintenance préféré est sélectionné lors de la planification des ordres de travail, le module Gestion des actifs parcourt tous les enregistrements **Agents de maintenance préférés** pour vérifier une correspondance éventuelle, en vérifiant toujours la combinaison la plus spécifique en premier.</span><span class="sxs-lookup"><span data-stu-id="fb304-129">Generally, when a preferred maintenance worker is selected during work order scheduling, Asset Management goes through all **Preferred maintenance workers** records to check for a possible match, always checking the most specific combination first.</span></span> <span data-ttu-id="fb304-130">Si aucune correspondance n’est trouvée, l’enregistrement « par défaut » avec une sélection dans le champ **Groupe d’agents de maintenance préféré** ou le champ **Agent de maintenance préféré** est utilisé.</span><span class="sxs-lookup"><span data-stu-id="fb304-130">If no match is found, the "default" record with a selection in either the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field is used.</span></span>

![Figure 1](media/02-work-order-scheduling.png)

<span data-ttu-id="fb304-132">Vous pouvez également paramétrer les agents de maintenance *responsables* à sélectionner lorsqu’une demande de maintenance ou un ordre de travail est créé.</span><span class="sxs-lookup"><span data-stu-id="fb304-132">You can also set up *responsible* maintenance workers who can be selected when a maintenance request or a work order is created.</span></span> <span data-ttu-id="fb304-133">Vous pouvez modifier la sélection dans **Tous les ordres de travail** et **Toutes les demandes de maintenance**, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="fb304-133">You can edit the selection in **All work orders** and **All maintenance requests**, if required.</span></span> <span data-ttu-id="fb304-134">Pour plus d’informations, consultez [Agents de maintenance responsables](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="fb304-134">For more information, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>

<span data-ttu-id="fb304-135">Lors de la planification des ordres de travail, différents scores sont calculés pour déterminer quels agents doivent effectuer les tâches associées à un ordre de travail (ces scores sont paramétrés dans le lien **Paramètres de la gestion des actifs** **Planification des ordres de travail** > ).</span><span class="sxs-lookup"><span data-stu-id="fb304-135">During work order scheduling, different scores are calculated to determine which workers should complete the jobs related to a work order (those scores are set up in **Asset management parameters** > **Work order scheduling** link).</span></span> <span data-ttu-id="fb304-136">Si au moins deux agents de maintenance préférés ou responsables obtiennent le même score lors de la planification des ordres de travail, un agent est sélectionné de manière aléatoire.</span><span class="sxs-lookup"><span data-stu-id="fb304-136">If two or more preferred maintenance workers or responsible maintenance workers get the same score during work order scheduling, one worker is randomly selected.</span></span> <span data-ttu-id="fb304-137">Sinon, il s’agit toujours de l’agent ayant le score le plus élevé qui est affecté pour exécuter un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="fb304-137">Otherwise, it is always the worker with the highest score who is allocated to complete a work order.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]