---
title: Définir les agents de maintenance préférés
description: Cette rubrique explique comment paramétrer des agents de maintenance préférés dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f26be81e7057d0cea1473d81452216251633ad9
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887409"
---
# <a name="preferred-maintenance-workers"></a><span data-ttu-id="513a5-103">Agents de maintenance préférés</span><span class="sxs-lookup"><span data-stu-id="513a5-103">Preferred maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="513a5-104">Vous pouvez définir une préférence concernant les agents de maintenance affectés pour effectuer des ordres de travail lors de la planification des ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="513a5-104">You can make a preference regarding which maintenance workers are allocated to complete work orders during work order scheduling.</span></span> <span data-ttu-id="513a5-105">L'utilisation de cette fonctionnalité est facultative. Elle peut néanmoins vous aider à choisir l'agent de maintenance le plus qualifié pour effectuer une tâche, selon les compétences et les aptitudes des agents.</span><span class="sxs-lookup"><span data-stu-id="513a5-105">The use of this functionality is optional, but it can help you make a choice for the most qualified maintenance worker to complete a job, based on worker skills and competencies.</span></span> <span data-ttu-id="513a5-106">Par conséquent, lors de la planification des ordres de travail, le paramétrage dans **Agents de maintenance préférés** permet de déterminer si un agent de maintenance ou un groupe d'agents spécifique doit être prévu pour un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="513a5-106">Therefore, during work order scheduling, the setup in **Preferred maintenance workers** is used to determine if a specific maintenance worker or worker group should be scheduled for a work order.</span></span> <span data-ttu-id="513a5-107">Seuls les agents de maintenance qui sont disponibles pour le temps de planification sont planifiés.</span><span class="sxs-lookup"><span data-stu-id="513a5-107">Only maintenance workers that are available at scheduling time will be scheduled.</span></span> <span data-ttu-id="513a5-108">Si un paramétrage d'agent de maintenance préféré correspond à un ordre de travail durant la planification, mais si l'agent de maintenance est alloué à d'autres tâches, l'ordre de travail est alors planifié pour un autre agent de maintenance disponible.</span><span class="sxs-lookup"><span data-stu-id="513a5-108">If a preferred maintenance worker setup matches a work order during scheduling, but the maintenance worker is allocated to other jobs, the work order will be scheduled to another, available, maintenance worker.</span></span>

<span data-ttu-id="513a5-109">Avant de paramétrer des agents de maintenance préférés, vous devez paramétrer tout d'abord les agents et groupes d'agents de maintenance qui doivent être disponibles pour sélection.</span><span class="sxs-lookup"><span data-stu-id="513a5-109">Before you can set up preferred maintenance workers, you must first set up the maintenance workers and worker groups that should be available for selection.</span></span> <span data-ttu-id="513a5-110">Consultez la section [Agents et groupes d'agents de maintenance](../setup-for-objects/workers-and-worker-groups.md) pour obtenir une description sur la manière de configurer les agents et groupes d'agents de maintenance.</span><span class="sxs-lookup"><span data-stu-id="513a5-110">Refer to [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md) for a description on how to set up maintenance workers and worker groups.</span></span>

## <a name="set-up-preferred-workers"></a><span data-ttu-id="513a5-111">Configurer les agents préférés</span><span class="sxs-lookup"><span data-stu-id="513a5-111">Set up preferred workers</span></span>

<span data-ttu-id="513a5-112">Un agent de maintenance ou un groupe d'agents de maintenance préféré peut être associé à un(e)</span><span class="sxs-lookup"><span data-stu-id="513a5-112">A preferred maintenance worker or worker group can be related to a specific</span></span>

- <span data-ttu-id="513a5-113">commerce</span><span class="sxs-lookup"><span data-stu-id="513a5-113">trade</span></span>  
- <span data-ttu-id="513a5-114">variante du type de tâche de maintenance</span><span class="sxs-lookup"><span data-stu-id="513a5-114">maintenance job type variant</span></span>  
- <span data-ttu-id="513a5-115">type de tâche de maintenance</span><span class="sxs-lookup"><span data-stu-id="513a5-115">maintenance job type</span></span>  
- <span data-ttu-id="513a5-116">catégorie de type tâche de maintenance</span><span class="sxs-lookup"><span data-stu-id="513a5-116">maintenance job type category</span></span>  
- <span data-ttu-id="513a5-117">actif</span><span class="sxs-lookup"><span data-stu-id="513a5-117">asset</span></span>  
- <span data-ttu-id="513a5-118">type d'actif spécifique</span><span class="sxs-lookup"><span data-stu-id="513a5-118">asset type</span></span>  

<span data-ttu-id="513a5-119">ou à une combinaison de ces sélections.</span><span class="sxs-lookup"><span data-stu-id="513a5-119">or a combination of those selections.</span></span> <span data-ttu-id="513a5-120">Plus vous faites de sélections pour le même enregistrement, plus votre paramétrage est spécifique.</span><span class="sxs-lookup"><span data-stu-id="513a5-120">The more selections you make for the same record, the more specific your setup will be.</span></span>

1. <span data-ttu-id="513a5-121">Cliquez sur **Gestion des actifs** > **Paramétrage** > **Agents** > **Agents de maintenance préférés**.</span><span class="sxs-lookup"><span data-stu-id="513a5-121">Click **Asset management** > **Setup** > **Workers** > **Preferred maintenance workers**.</span></span>

2. <span data-ttu-id="513a5-122">Cliquez sur **Nouveau** pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="513a5-122">Click **New** to create a new record.</span></span>

3. <span data-ttu-id="513a5-123">Commencez en créant un paramétrage de groupe d'agents ou d'agent de maintenance « par défaut » sans sélection dans les champs indiqués dans la liste à puce ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="513a5-123">Start by creating a "default" maintenance worker or worker group setup that has no selections in the fields shown in the bullet list above.</span></span> <span data-ttu-id="513a5-124">Autrement dit, vous effectuez une seule sélection dans le champ **Groupe d'agents de maintenance préféré** ou le champ **Agent de maintenance préféré**.</span><span class="sxs-lookup"><span data-stu-id="513a5-124">This means that you only make a selection in the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field.</span></span> <span data-ttu-id="513a5-125">Dans la figure ci-dessous, vous voyez un exemple dans le premier enregistrement dans lequel « Demandes » est sélectionné comme le groupe d'agents de maintenance préféré.</span><span class="sxs-lookup"><span data-stu-id="513a5-125">In the figure below, you see an example in the first record in which "Requests" is selected as preferred maintenance worker group.</span></span>

>[!NOTE]
><span data-ttu-id="513a5-126">Ce paramétrage par défaut sera utilisé lors de la planification des ordres de travail si aucune autre combinaison plus spécifique ne correspond au contenu de l'ordre de travail dans le cadre de la planification des ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="513a5-126">The default setup will be used during work order scheduling in case no other, more specific, combination matches the contents of the work order during work order scheduling.</span></span>

4. <span data-ttu-id="513a5-127">Répétez l'étape 2 pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="513a5-127">Repeat step 2 to create a new record.</span></span> <span data-ttu-id="513a5-128">Effectuez les sélections nécessaires, selon le niveau de détail pour l'agent ou le groupe d'agents de maintenance préféré.</span><span class="sxs-lookup"><span data-stu-id="513a5-128">Make the required selections, depending on the detail level for the preferred worker or worker group.</span></span> <span data-ttu-id="513a5-129">*Exemple :* dans la figure ci-dessous, dans le sixième enregistrement, l'agent de maintenance Shawn Richardson est sélectionné comme agent préféré.</span><span class="sxs-lookup"><span data-stu-id="513a5-129">*Example:* In the figure below, in the sixth record, the maintenance worker Shawn Richardson is selected as preferred worker.</span></span> <span data-ttu-id="513a5-130">Il est automatiquement sélectionné lors de la planification d'un ordre de travail contenant l'agent « CH-BP1-03-02 et la tâche de maintenance de type "Évaluation du site" », s'il est disponible au moment prévu.</span><span class="sxs-lookup"><span data-stu-id="513a5-130">He will automatically be selected during scheduling of a work order that includes the asset "CH-BP1-03-02 and the maintennace job type "Facility assessment", if he is available at the scheduled time.</span></span>

>[!NOTE]
><span data-ttu-id="513a5-131">En général, si un agent de maintenance préféré est sélectionné lors de la planification des ordres de travail, le module Gestion des actifs parcourt tous les enregistrements **Agents de maintenance préférés** pour vérifier une correspondance éventuelle, en vérifiant toujours la combinaison la plus spécifique en premier.</span><span class="sxs-lookup"><span data-stu-id="513a5-131">Generally, when a preferred maintenance worker is selected during work order scheduling, Asset Management goes through all **Preferred maintenance workers** records to check for a possible match, always checking the most specific combination first.</span></span> <span data-ttu-id="513a5-132">Si aucune correspondance n'est trouvée, l'enregistrement « par défaut » avec une sélection dans le champ **Groupe d'agents de maintenance préféré** ou le champ **Agent de maintenance préféré** est utilisé.</span><span class="sxs-lookup"><span data-stu-id="513a5-132">If no match is found, the "default" record with a selection in either the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field is used.</span></span>


![Figure 1](media/02-work-order-scheduling.png)

<span data-ttu-id="513a5-134">Vous pouvez également paramétrer les agents de maintenance responsables à sélectionner lorsqu'une demande de maintenance ou un ordre de travail est créé.</span><span class="sxs-lookup"><span data-stu-id="513a5-134">You can also set up responsible maintenance workers who can be selected when a maintenance request or a work order is created.</span></span> <span data-ttu-id="513a5-135">Dans **Tous les ordres de travail** et **Toutes les demandes de maintenance**, vous pouvez modifier la sélection, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="513a5-135">In **All work orders** and **All maintenance requests**, you can edit the selection, if required.</span></span> <span data-ttu-id="513a5-136">Consultez [Agents de maintenance responsables](../setup-for-maintenance-requests/responsible-workers.md) pour en savoir plus.</span><span class="sxs-lookup"><span data-stu-id="513a5-136">Refer to [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md) for more information.</span></span>

<span data-ttu-id="513a5-137">Lors de la planification des ordres de travail, différents scores sont calculés pour déterminer quels agents doivent effectuer les tâches associées à un ordre de travail (ces scores sont paramétrés dans le lien**Paramètres de la gestion des actifs** **Planification des ordres de travail** > ).</span><span class="sxs-lookup"><span data-stu-id="513a5-137">During work order scheduling, different scores are calculated to determine which workers should complete the jobs related to a work order (those scores are set up in **Asset management parameters** > **Work order scheduling** link).</span></span> <span data-ttu-id="513a5-138">Si au moins deux agents de maintenance préférés ou responsables obtiennent le même score lors de la planification des ordres de travail, un agent est sélectionné de manière aléatoire.</span><span class="sxs-lookup"><span data-stu-id="513a5-138">If two or more preferred maintenance workers or responsible maintenance workers get the same score during work order scheduling, one worker is randomly selected.</span></span> <span data-ttu-id="513a5-139">Sinon, il s'agit toujours de l'agent ayant le score le plus élevé qui est affecté pour exécuter un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="513a5-139">Otherwise, it is always the worker with the highest score who is allocated to complete a work order.</span></span>

