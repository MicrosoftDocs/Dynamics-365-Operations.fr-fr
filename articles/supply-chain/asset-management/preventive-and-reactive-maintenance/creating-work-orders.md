---
title: Création d’ordres de travail
description: Cette rubrique explique comment créer des ordres de travail dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePoolsOpen
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 3982232e5008d6f8c283d6cecfaf2fa6e66150a1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836732"
---
# <a name="creating-work-orders"></a><span data-ttu-id="3a7ef-103">Création d’ordres de travail</span><span class="sxs-lookup"><span data-stu-id="3a7ef-103">Creating work orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3a7ef-104">Lorsque vous avez planifié des tâches de maintenance préventive, l’étape suivante consiste à créer des ordres de travail pour ces tâches.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-104">After you've scheduled preventive maintenance jobs, the next step is to create work orders for them.</span></span> <span data-ttu-id="3a7ef-105">Vous pouvez effectuer cette étape en utilisant l’un des programmes de maintenance.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-105">You can complete this step by using one of the maintenance schedules.</span></span> <span data-ttu-id="3a7ef-106">Les tâches prévues dans un programme de maintenance peuvent avoir des types de références différents, comme décrit dans la table suivante :</span><span class="sxs-lookup"><span data-stu-id="3a7ef-106">The scheduled jobs in a maintenance schedule can have different reference types, as described in the following table.</span></span>

| <span data-ttu-id="3a7ef-107">Type de référence</span><span class="sxs-lookup"><span data-stu-id="3a7ef-107">Reference type</span></span> | <span data-ttu-id="3a7ef-108">Description</span><span class="sxs-lookup"><span data-stu-id="3a7ef-108">Description</span></span> |
|---|---|
| <span data-ttu-id="3a7ef-109">Plans de maintenance</span><span class="sxs-lookup"><span data-stu-id="3a7ef-109">Maintenance plans</span></span> | <span data-ttu-id="3a7ef-110">Des tâches de maintenance préventive basées sur des types de plan de maintenance *Heure* ou *Compteur*.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-110">Preventive maintenance jobs that are based on the *Time* or *Counter* maintenance plan type.</span></span> |
| <span data-ttu-id="3a7ef-111">Visites de maintenance</span><span class="sxs-lookup"><span data-stu-id="3a7ef-111">Maintenance rounds</span></span> | <span data-ttu-id="3a7ef-112">Des tâches de maintenance préventive contenant plusieurs actifs nécessitant un type de maintenance similaire.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-112">Preventive maintenance jobs that contain several assets that require a similar type of maintenance.</span></span> |
| <span data-ttu-id="3a7ef-113">Demande de maintenance</span><span class="sxs-lookup"><span data-stu-id="3a7ef-113">Maintenance request</span></span> | <span data-ttu-id="3a7ef-114">Une demande créée manuellement pour la maintenance ou la réparation d’un actif.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-114">A manually created request for maintenance or repair of an asset.</span></span> <span data-ttu-id="3a7ef-115">Cette demande peut être convertie en ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-115">This request can be converted to a work order.</span></span> |

## <a name="create-work-orders-based-on-your-maintenance-schedule"></a><span data-ttu-id="3a7ef-116">Créer des ordres de travail en fonction de votre programme de maintenance</span><span class="sxs-lookup"><span data-stu-id="3a7ef-116">Create work orders based on your maintenance schedule</span></span>

<span data-ttu-id="3a7ef-117">Pour créer des ordres de travail basés sur votre programme de maintenance, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-117">To create work orders that are based on your maintenance schedule, follow these steps.</span></span>

1. <span data-ttu-id="3a7ef-118">Ouvrez l’une des pages suivantes, selon la manière dont vous souhaitez sélectionner les éléments de planification pour vos ordres de travail :</span><span class="sxs-lookup"><span data-stu-id="3a7ef-118">Open one of the following pages, depending on how you want to select schedule items for your work orders:</span></span>

    - <span data-ttu-id="3a7ef-119">Tout le programme de maintenance (**Gestion des actifs \> Programme de gestion \> Tout le programme de maintenance**)</span><span class="sxs-lookup"><span data-stu-id="3a7ef-119">All maintenance schedule (**Asset management \> Management schedule \> All maintenance schedule**)</span></span>
    - <span data-ttu-id="3a7ef-120">Ouvrir les lignes du programme de maintenance (**Gestion des actifs \> Programme de gestion \> Ouvrir les lignes du programme de maintenance**)</span><span class="sxs-lookup"><span data-stu-id="3a7ef-120">Open maintenance schedule lines (**Asset management \> Management schedule \> Open maintenance schedule lines**)</span></span>
    - <span data-ttu-id="3a7ef-121">Ouvrir les regroupements du programme de maintenance (**Gestion des actifs \> Programme de gestion \> Ouvrir les regroupements du programme de maintenance**)</span><span class="sxs-lookup"><span data-stu-id="3a7ef-121">Open maintenance schedule pools (**Asset management \> Management schedule \> Open maintenance schedule pools**)</span></span>

1. <span data-ttu-id="3a7ef-122">Dans la grille, cochez la case de chaque tâche de maintenance planifiée pour laquelle vous souhaitez créer un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-122">In the grid, select the check box for every scheduled maintenance job that you want to create a work order for.</span></span> <span data-ttu-id="3a7ef-123">Puis, dans le volet Actions, sélectionnez **Ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-123">Then, on the Action Pane, select **Work order**.</span></span>

    <span data-ttu-id="3a7ef-124">La boîte de dialogue **Créer des ordres de travail** apparaît.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-124">The **Create work orders** dialog box appears.</span></span> <span data-ttu-id="3a7ef-125">Le champ **Heures de prévision en matière de maintenance** affiche le nombre total d’heures prévues pour les lignes sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-125">The **Maintenance forecast hours** field shows the total number of forecast hours for the selected lines.</span></span>

    ![Boîte de dialogue Créer des ordres de travail](media/18-preventive-maintenance.png)

1. <span data-ttu-id="3a7ef-127">Dans la section **Paramètres**, spécifiez le nombre d’ordres de travail à créer.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-127">In the **Parameters** section, specify the number of work orders that should be created.</span></span> <span data-ttu-id="3a7ef-128">Permet de sélectionner l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="3a7ef-128">Select one of the following options:</span></span>

    - <span data-ttu-id="3a7ef-129">**Un ordre de travail par ligne** : créez un ordre de travail par ligne du programme de maintenance.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-129">**One work order per line** – Create one work order per maintenance schedule line.</span></span>
    - <span data-ttu-id="3a7ef-130">**Un ordre de travail par** : créez des ordres de travail regroupés en fonction des paramètres des autres options disponibles lorsque vous sélectionnez cette option.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-130">**One work order per** – Create work orders that are grouped according to the settings of the other options that become available when you select this option.</span></span>

1. <span data-ttu-id="3a7ef-131">Dans le champ **Type d’ordre de travail**, sélectionnez le type d’ordre de travail à utiliser pour tous les ordres de travail que vous créez.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-131">In the **Work order type** field, select the work order type to use for all the work orders that you create.</span></span>
1. <span data-ttu-id="3a7ef-132">Sélectionnez **OK** pour créer les ordres de travail selon vos paramètres.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-132">Select **OK** to create the work orders according to your settings.</span></span>

## <a name="group-work-order-lines-that-are-automatically-created-while-a-maintenance-plan-runs"></a><span data-ttu-id="3a7ef-133">Regrouper les lignes d’ordre de travail qui sont automatiquement créées lors de l’exécution d’un plan de maintenance</span><span class="sxs-lookup"><span data-stu-id="3a7ef-133">Group work order lines that are automatically created while a maintenance plan runs</span></span>

<span data-ttu-id="3a7ef-134">Cette fonction vous permet de définir des règles de regroupement des lignes d’ordre de travail sous un seul ordre de travail lorsque le système est configuré pour générer automatiquement des ordres de travail, en fonction d’un plan de maintenance.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-134">This feature lets you define rules for grouping work order lines under a single work order when the system is set up to generate work orders automatically, based on a maintenance plan.</span></span> <span data-ttu-id="3a7ef-135">Auparavant, les ordres de travail générés automatiquement ne pouvaient contenir qu’une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-135">Previously, automatically generated work orders could contain only one line.</span></span> <span data-ttu-id="3a7ef-136">Cependant, vous pouvez désormais regrouper les ordres de travail par exemple, par actif, par type d’actif ou par emplacement fonctionnel.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-136">However, you can now group work orders by, for example, asset, asset type, or functional location.</span></span> <span data-ttu-id="3a7ef-137">(Les ordres de travail générés manuellement peuvent déjà être regroupés de cette manière, comme décrit dans la section précédente de cette rubrique.)</span><span class="sxs-lookup"><span data-stu-id="3a7ef-137">(Manually generated work orders could already be grouped in this way, as described in the previous section of this topic.)</span></span>

### <a name="enable-grouping-for-automatically-generated-work-orders"></a><span data-ttu-id="3a7ef-138">Activer le regroupement pour les ordres de travail générés automatiquement</span><span class="sxs-lookup"><span data-stu-id="3a7ef-138">Enable grouping for automatically generated work orders</span></span>

<span data-ttu-id="3a7ef-139">Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-139">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="3a7ef-140">Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-140">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="3a7ef-141">Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="3a7ef-141">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="3a7ef-142">**Module :** *Gestion des actifs*</span><span class="sxs-lookup"><span data-stu-id="3a7ef-142">**Module:** *Asset Management*</span></span>
- <span data-ttu-id="3a7ef-143">**Nom de fonctionnalité :** *Appliquer les règles de regroupement d’ordres de travail lors de l’exécution d’un plan de maintenance*</span><span class="sxs-lookup"><span data-stu-id="3a7ef-143">**Feature name:** *Apply rules for grouping work orders while running a maintenance plan*</span></span>

### <a name="set-up-grouping-for-automatically-generated-work-orders"></a><span data-ttu-id="3a7ef-144">Configurer le regroupement pour les ordres de travail générés automatiquement</span><span class="sxs-lookup"><span data-stu-id="3a7ef-144">Set up grouping for automatically generated work orders</span></span>

<span data-ttu-id="3a7ef-145">Pour configurer le regroupement pour les ordres de travail générés automatiquement, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-145">To set up grouping for automatically generated work orders, follow these steps.</span></span>

1. <span data-ttu-id="3a7ef-146">Accédez à **Gestion des actifs \> Paramétrage \> Maintenance préventive \> Plans de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-146">Go to **Asset management \> Setup \> Preventative maintenance \> Maintenance plans**.</span></span>
1. <span data-ttu-id="3a7ef-147">Pour chaque plan dans lequel vous souhaitez générer des ordres de travail groupés, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="3a7ef-147">For each plan where you want to generate grouped work orders, follow these steps:</span></span>

    1. <span data-ttu-id="3a7ef-148">Dans le volet de liste, sélectionnez le plan.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-148">Select the plan in the list pane.</span></span>
    1. <span data-ttu-id="3a7ef-149">Sur l’organisateur **Lignes**, veillez à ce que la case **Création automatique** soit cochée sur chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-149">On the **Lines** FastTab, make sure that the **Auto create** check box is selected on every line.</span></span>

1. <span data-ttu-id="3a7ef-150">Accédez à **Gestion des actifs \> Périodique \> Maintenance préventive \> Planifier les plans de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-150">Go to **Asset management \> Periodic \> Preventive maintenance \> Schedule maintenance plans**.</span></span>
1. <span data-ttu-id="3a7ef-151">Dans la boîte de dialogue **Planifier les plans de maintenance**, dans la section **Période**, spécifiez la période du plan (jusqu’où il faut regarder vers l’avant lors de la recherche de tâches de maintenance planifiées pour lesquelles générer du travail).</span><span class="sxs-lookup"><span data-stu-id="3a7ef-151">In the **Schedule maintenance plans** dialog box, in the **Period** section, specify the time horizon for the plan (how far to look ahead when finding scheduled maintenance jobs to generate work for).</span></span>
1. <span data-ttu-id="3a7ef-152">Définissez l’option **Créer automatiquement un ordre de travail à partir du calendrier** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-152">Set the **Automatically create work order from schedule** option to *Yes*.</span></span>
1. <span data-ttu-id="3a7ef-153">Dans la section **Ordre de travail**, sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="3a7ef-153">In the **Work order** section, select one of the following options:</span></span>

    - <span data-ttu-id="3a7ef-154">**Un ordre de travail par ligne** : créez un ordre de travail par ligne du programme de maintenance.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-154">**One work order per line** – Create one work order per maintenance schedule line.</span></span> <span data-ttu-id="3a7ef-155">(Cette option fournit les mêmes fonctionnalités disponibles lorsque la fonctionnalité *Appliquer les règles de regroupement d’ordres de travail lors de l’exécution d’un plan de maintenance* est désactivée.)</span><span class="sxs-lookup"><span data-stu-id="3a7ef-155">(This option provides the same functionality that is available when the *Apply rules for grouping work orders while running a maintenance plan* feature is turned off.)</span></span>
    - <span data-ttu-id="3a7ef-156">**Un ordre de travail par** : créez des ordres de travail regroupés en fonction des paramètres des autres options disponibles lorsque vous sélectionnez cette option.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-156">**One work order per** – Create work orders that are grouped according to the settings of the other options that become available when you select this option.</span></span>

1. <span data-ttu-id="3a7ef-157">Si vous souhaitez que les options s’appliquent lorsque vous n’exécutez que certains de vos plans de maintenance, sur l’organisateur **Enregistrements à inclure**, ajoutez des filtres selon vos besoins, comme vous pourriez le faire pour d’autres tâches de traitement par lots dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-157">If you want the options to apply when you run only some of your maintenance plans, on the **Records to include** FastTab, add filters as you require, just as you might do for other batch jobs in Microsoft Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="3a7ef-158">Sur l’organisateur **Exécuter à l’arrière-plan**, configurez les options de traitement par lots et de planification selon vos besoins, comme vous le feriez pour d’autres tâches de traitement par lots dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-158">On the **Run in the background** FastTab, set up batch and scheduling options as you require, just as you might do for other batch jobs in Supply Chain Management.</span></span>
1. <span data-ttu-id="3a7ef-159">Sélectionnez **OK** pour exécuter et/ou planifier les plans de maintenance sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="3a7ef-159">Select **OK** to run and/or schedule the selected maintenance plans.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]