---
title: Planifier la création de travail pendant la vague
description: Cette rubrique décrit comment configurer et utiliser la méthode de traitement de vague Planifier la création de travail.
author: perlynne
manager: mirzaab
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ed8f43c7db139b7b16ac6901d5db56ba2f021690
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/28/2021
ms.locfileid: "5078260"
---
# <a name="schedule-work-creation-during-wave"></a><span data-ttu-id="79e14-103">Planifier la création de travail pendant la vague</span><span class="sxs-lookup"><span data-stu-id="79e14-103">Schedule work creation during wave</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="79e14-104">Utilisez la fonctionnalité *Planifier la création de travail* dans le cadre de votre processus de traitement de vague pour accroître le débit de traitement de vague en faisant en sorte que le système crée le travail à l’aide du traitement parallèle.</span><span class="sxs-lookup"><span data-stu-id="79e14-104">Use the *Schedule work creation* feature as part of your waving process to help increase wave processing throughput by having the system create work using parallel processing.</span></span>

<span data-ttu-id="79e14-105">Lorsque la fonctionnalité est activée, le travail planifié est automatiquement créé, ce que le système traitera éventuellement pour créer un travail réel.</span><span class="sxs-lookup"><span data-stu-id="79e14-105">When the functionality is enabled, planned work will automatically get created, which the system will eventually process to create actual work.</span></span> <span data-ttu-id="79e14-106">Si le nombre de lignes de chargement d’onde atteint un seuil prédéterminé, le système créera un travail réel plus rapidement en appliquant un traitement parallèle et asynchrone.</span><span class="sxs-lookup"><span data-stu-id="79e14-106">If the number of wave load lines reaches a predetermined threshold, the system will create actual work more quickly by applying parallel, asynchronous processing.</span></span>

## <a name="enable-the-schedule-work-creation-feature"></a><span data-ttu-id="79e14-107">Activer la fonction Planifier la création de travail</span><span class="sxs-lookup"><span data-stu-id="79e14-107">Enable the Schedule work creation feature</span></span>

### <a name="enable-the-feature-in-feature-management"></a><span data-ttu-id="79e14-108">Activer la fonctionnalité dans la gestion des fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="79e14-108">Enable the feature in feature management</span></span>

<span data-ttu-id="79e14-109">Avant de pouvoir utiliser la fonctionnalité *Planifier la création de travail* doit être activée sur votre système.</span><span class="sxs-lookup"><span data-stu-id="79e14-109">Before you can use the *Schedule work creation* feature, it must be turned on in your system.</span></span> <span data-ttu-id="79e14-110">Les administrateurs peuvent utiliser l’espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="79e14-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="79e14-111">Là, la fonctionnalité est répertoriée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="79e14-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="79e14-112">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="79e14-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="79e14-113">**Nom de la fonctionnalité :** *Planifier la création de travail*</span><span class="sxs-lookup"><span data-stu-id="79e14-113">**Feature name:** *Schedule work creation*</span></span>

> [!NOTE]
> <span data-ttu-id="79e14-114">La fonctionnalité *Blocage des tâches à l’échelle de l’organisation* doit être activée avant que vous puissiez activer la fonctionnalité *Planifier la création de travail*.</span><span class="sxs-lookup"><span data-stu-id="79e14-114">The *Organization-wide work blocking* feature must be enabled before you can enable *Schedule work creation*.</span></span>

### <a name="manually-enable-batch-processing-of-waves"></a><span data-ttu-id="79e14-115">Activer manuellement le traitement par lots des vagues</span><span class="sxs-lookup"><span data-stu-id="79e14-115">Manually enable batch processing of waves</span></span>

<span data-ttu-id="79e14-116">Pour tirer parti d’une méthode asynchrone parallèle pour créer un travail d’entrepôt, votre processus de vague doit être exécuté par lots.</span><span class="sxs-lookup"><span data-stu-id="79e14-116">To take advantage of a parallel asynchronous method to create warehouse work, your wave process must be running in batch.</span></span> <span data-ttu-id="79e14-117">Pour configurer cela :</span><span class="sxs-lookup"><span data-stu-id="79e14-117">To set this up:</span></span>

1. <span data-ttu-id="79e14-118">Accédez à  **Gestion des entrepôts\>Configuration \> Paramètres de gestion des entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="79e14-118">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>

1. <span data-ttu-id="79e14-119">Sur l’onglet **Général**, définissez **Traiter les vagues dans des traitements par lots** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="79e14-119">On the **General** tab, set **Process waves in batch** to *Yes*.</span></span> <span data-ttu-id="79e14-120">En option, vous pouvez également sélectionner un **Groupe de traitements par lots pour le traitement de la vague** pour empêcher le traitement de votre file d’attente par lots de s’exécuter en même temps que d’autres processus.</span><span class="sxs-lookup"><span data-stu-id="79e14-120">Optionally, you can also select a dedicated **Wave processing batch group** to prevent your batch queue processing from running at the same time as other processes.</span></span>

1. <span data-ttu-id="79e14-121">Définissez **Attendre le verrouillage (ms)**, qui s’applique lorsque le système traite plusieurs vagues en même temps.</span><span class="sxs-lookup"><span data-stu-id="79e14-121">Set the **Wait for lock (ms) time**, which applies when the system is processing several waves at the same time.</span></span> <span data-ttu-id="79e14-122">Pour la plupart des processus de traitement par vague plus volumineux, nous recommandons une valeur de *60000*.</span><span class="sxs-lookup"><span data-stu-id="79e14-122">For most larger waving processes, we recommend a value of *60000*.</span></span>

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a><span data-ttu-id="79e14-123">Activer manuellement la nouvelle méthode d’étape de vague pour les modèles de vague existants</span><span class="sxs-lookup"><span data-stu-id="79e14-123">Manually enable the new wave step method for existing wave templates</span></span>

<span data-ttu-id="79e14-124">Commencez par créer la nouvelle méthode d’étape de vague et activez-la pour le traitement de tâche asynchrone parallèle.</span><span class="sxs-lookup"><span data-stu-id="79e14-124">Start by creating the new wave step method and enabling it for parallel asynchronous task processing.</span></span>

1. <span data-ttu-id="79e14-125">Accédez à  **Gestion des entrepôts \>Configuration \> Vagues \> Méthodes de traitement de la vague**.</span><span class="sxs-lookup"><span data-stu-id="79e14-125">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>

1. <span data-ttu-id="79e14-126">Sélectionnez  **Regenérer des méthodes** et notez que *WHSScheduleWorkCreationWaveStepMethod* a été ajouté à la liste des méthodes de traitement de vague que vous pouvez utiliser dans vos modèles de vague d’expédition.</span><span class="sxs-lookup"><span data-stu-id="79e14-126">Select  **Regenerate method** and note that *WHSScheduleWorkCreationWaveStepMethod* has been added to the list of wave process methods you can use in your shipping wave templates.</span></span>

1. <span data-ttu-id="79e14-127">Sélectionnez l’enregistrement avec le **Nom de méthode** *WHSScheduleWorkCreationWaveStepMethod* et sélectionnez **Configuration des tâches**.</span><span class="sxs-lookup"><span data-stu-id="79e14-127">Select the record with the **Method name** *WHSScheduleWorkCreationWaveStepMethod* and select **Task configuration**.</span></span>

1. <span data-ttu-id="79e14-128">Pour ajouter une nouvelle ligne à la grille, sélectionnez **Nouveau** sur le volet Actions et utilisez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="79e14-128">To add a new row to the grid, select **New** on the Action Pane and use the following settings:</span></span>

    - <span data-ttu-id="79e14-129">**Entrepôt** : sélectionnez l’entrepôt que vous utiliserez pour planifier le traitement de la création de travail.</span><span class="sxs-lookup"><span data-stu-id="79e14-129">**Warehouse** - Select the warehouse you will use to schedule work creation processing.</span></span>

    - <span data-ttu-id="79e14-130">**Nombre maximum de tâches par lots** : spécifiez un nombre maximum de tâches par lots.</span><span class="sxs-lookup"><span data-stu-id="79e14-130">**Maximum number of batch tasks** - Specify a maximum number of batch tasks.</span></span> <span data-ttu-id="79e14-131">Dans la plupart des cas, cette valeur doit être comprise entre 8 et 16, mais nous vous recommandons de tester le paramètre optimal en fonction de vos scénarios.</span><span class="sxs-lookup"><span data-stu-id="79e14-131">In most cases, this value should be in the range from 8-16, however we recommend that you experiment with the optimal setting based on your scenarios.</span></span>

    - <span data-ttu-id="79e14-132">**Groupe de traitements par lots pour le traitement de la vague** : sélectionnez un groupe de traitement par lots de vague dédié pour optimiser le traitement de votre file d’attente des traitements par lots.</span><span class="sxs-lookup"><span data-stu-id="79e14-132">**Wave processing batch group** - Select a dedicated wave processing batch group to optimize your batch queue processing.</span></span>

<span data-ttu-id="79e14-133">Vous êtes maintenant prêt à mettre à jour un modèle de vague existant (ou à en créer un nouveau) pour utiliser la méthode de traitement de vague *Planifier la création de travail*.</span><span class="sxs-lookup"><span data-stu-id="79e14-133">Now you are ready to update an existing wave template (or create a new one) to use the *Schedule work creation* wave processing method.</span></span>

1. <span data-ttu-id="79e14-134">Accédez à  **Gestion des entrepôts\>Configuration \> Vagues \> Modèles de vague**.</span><span class="sxs-lookup"><span data-stu-id="79e14-134">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>

1. <span data-ttu-id="79e14-135">Sélectionnez **Modifier** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="79e14-135">Select **Edit** on the Action Pane.</span></span>

1. <span data-ttu-id="79e14-136">Dans le volet de listes, sélectionnez le modèle de vague que vous souhaitez mettre à jour (si vous testez à l’aide de données de démonstration, vous pouvez utiliser la fonctionnalité *Expédition par défaut 24*).</span><span class="sxs-lookup"><span data-stu-id="79e14-136">In the list pane, select the wave template you would like to update (if you are testing using demo data, then you could use *24 Shipping default*).</span></span>

1. <span data-ttu-id="79e14-137">Développez l’organisateur **Méthodes** et sélectionnez la ligne avec le **Nom** *Planifier la création de travail* dans la grille **Méthodes restantes**.</span><span class="sxs-lookup"><span data-stu-id="79e14-137">Expand the **Methods** FastTab and select the row with the **Name** *Schedule work creation* in the **Remaining methods** grid.</span></span>

1. <span data-ttu-id="79e14-138">Sélectionnez la flèche pointant vers la colonne **Méthodes sélectionnées** pour déplacer la ligne sélectionnée vers cette colonne.</span><span class="sxs-lookup"><span data-stu-id="79e14-138">Select the arrow pointing to the **Selected methods** column to move the selected row to that column.</span></span> <span data-ttu-id="79e14-139">(Vous ne pouvez avoir qu’une seule méthode sélectionnée à la fois qui utilise soit *WHSScheduleWorkCreationWaveStepMethod* ou *createWork*, de telle sorte que la ligne existante avec **Nom de méthode** *createWork* soit automatiquement déplacé vers la grille **Méthodes restantes**.)</span><span class="sxs-lookup"><span data-stu-id="79e14-139">(You can only have one selected method at a time that uses either *WHSScheduleWorkCreationWaveStepMethod* or *createWork*, so the existing row with **Method name** *createWork* is automatically moved to the **Remaining methods** grid.)</span></span>

## <a name="set-wave-task-processing-threshold-data"></a><span data-ttu-id="79e14-140">Définir les données de seuil de traitement de la tâche de vague</span><span class="sxs-lookup"><span data-stu-id="79e14-140">Set wave task processing threshold data</span></span>

<span data-ttu-id="79e14-141">Le système créera des données de seuil de traitement de tâche de vague par défaut la première fois qu’un processus de vague s’exécute en utilisant un traitement basé sur une tâche.</span><span class="sxs-lookup"><span data-stu-id="79e14-141">The system will create default wave task processing threshold data the first time a wave process runs using any task-based processing.</span></span> <span data-ttu-id="79e14-142">Les données sont utilisées pour contrôler le moment où le traitement de vague s’exécutera de manière asynchrone et sera basé sur les tâches, ce qui lui permet de traiter et de créer un travail en parallèle.</span><span class="sxs-lookup"><span data-stu-id="79e14-142">The data is used to control when wave processing will run asynchronously and be task-based, which enables it to process and create work in parallel.</span></span>

<span data-ttu-id="79e14-143">Les données par défaut utiliseront initialement une valeur seuil de 15 pour le nombre minimum de lignes de chargement (MINIMUMWAVELOADLINES).</span><span class="sxs-lookup"><span data-stu-id="79e14-143">The default data will initially use a threshold value of 15 for the minimum number of load lines (MINIMUMWAVELOADLINES).</span></span> <span data-ttu-id="79e14-144">Cela signifie que lorsque le système traite une vague avec plus de 15 lignes de chargement, il utilisera un traitement de tâche asynchrone.</span><span class="sxs-lookup"><span data-stu-id="79e14-144">This means that when the system processes a wave with more than 15 loads lines, it will use asynchronous task processing.</span></span> <span data-ttu-id="79e14-145">Vous pouvez insérer/mettre à jour manuellement ces données dans la table **WHSWaveTaskProcessingThresholdParameters** dans vos environnements de test, mais si vous devez modifier ce paramètre dans un environnement de production, vous devez contacter le support Microsoft pour demander la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="79e14-145">You can manually insert/update this data in the **WHSWaveTaskProcessingThresholdParameters** table in your test environments, but if you need to change this setting in a production environment, you must contact Microsoft Support to request the update.</span></span>

## <a name="work-with-the-feature"></a><span data-ttu-id="79e14-146">Utiliser la fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="79e14-146">Work with the feature</span></span>

<span data-ttu-id="79e14-147">Quand la fonctionnalité *Planifier la création de travail* est activée, le traitement de vague créera un travail planifié, qui sera éventuellement utilisé par le nouveau processus de création de travail.</span><span class="sxs-lookup"><span data-stu-id="79e14-147">When the *Schedule work creation* functionality is enabled, wave processing will create planned work, which will eventually be used by the new work creation process.</span></span> <span data-ttu-id="79e14-148">Lors de la création de travail, le travail est bloqué à l’aide de la fonctionnalité *Blocage des tâches à l’échelle de l’organisation*.</span><span class="sxs-lookup"><span data-stu-id="79e14-148">During work creation, the work will be blocked using the *Organization-wide work blocking* feature.</span></span>

<span data-ttu-id="79e14-149">L’organigramme suivant montre comment le travail planifié est créé pendant le traitement de vague.</span><span class="sxs-lookup"><span data-stu-id="79e14-149">The following flowchart shows how planned work is created during wave processing.</span></span>

![Planifier la création du travail](media/schedule-work-creation-process.png)

### <a name="planned-work"></a><span data-ttu-id="79e14-151">Travail planifié</span><span class="sxs-lookup"><span data-stu-id="79e14-151">Planned work</span></span>

<span data-ttu-id="79e14-152">La page **Détails du travail planifié** (**Gestion des entrepôts \> Travail \> Détails du travail planifié**) affiche des informations sur le travail planifié, qui est initialement créé lors du traitement de vague.</span><span class="sxs-lookup"><span data-stu-id="79e14-152">The **Planned work details** page (**Warehouse management \> Work \> Planned work details**) shows information about the planned work, which is initially created during wave processing.</span></span> <span data-ttu-id="79e14-153">Les valeurs **Statut du processus** suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="79e14-153">The following **Process status** values are available:</span></span>

- <span data-ttu-id="79e14-154">**En file d’attente** : le travail planifié attend d’être utilisé pour créer du travail.</span><span class="sxs-lookup"><span data-stu-id="79e14-154">**Queued** - The planned work is waiting to be used to create work.</span></span>
- <span data-ttu-id="79e14-155">**Terminé** : le travail planifié a été utilisé pour créer du travail.</span><span class="sxs-lookup"><span data-stu-id="79e14-155">**Completed** - The planned work has been used to create work.</span></span>
- <span data-ttu-id="79e14-156">**Échec** : le traitement de vague a échoué.</span><span class="sxs-lookup"><span data-stu-id="79e14-156">**Failed** – The wave processing has failed.</span></span> <span data-ttu-id="79e14-157">Notez que le travail planifié peut avoir un état défini sur **Échec** avec ou sans travail réel connexe.</span><span class="sxs-lookup"><span data-stu-id="79e14-157">Note that the planned work can be in a **Failed** state with or without related actual work.</span></span> <span data-ttu-id="79e14-158">En cas d’échec du processus de création de travail réel, le travail réel reste défini sur l’état *Annulé*.</span><span class="sxs-lookup"><span data-stu-id="79e14-158">When the actual work creation process fails, the actual work remains in status *Cancelled*.</span></span>

### <a name="batch-job-for-the-work-creation-process"></a><span data-ttu-id="79e14-159">Travail par lots pour le processus de création de travail</span><span class="sxs-lookup"><span data-stu-id="79e14-159">Batch job for the work creation process</span></span>

<span data-ttu-id="79e14-160">Pour afficher les travaux par lots pour le traitement des vagues, sélectionnez **Tâches de traitement par lots** dans le volet Actions sur la page **Toutes les vagues**.</span><span class="sxs-lookup"><span data-stu-id="79e14-160">To view the batch jobs for processing waves, select **Batch jobs** on the Action Pane on the **All waves** page.</span></span>

<span data-ttu-id="79e14-161">À partir de là, vous pouvez afficher tous les détails de la tâche par lots pour chacun des ID de tâche de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="79e14-161">From here, you can view all the batch task details for each of the batch job IDs.</span></span>
