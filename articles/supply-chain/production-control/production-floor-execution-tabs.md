---
title: Concevoir l’interface d’exécution de l’atelier de production
description: Cette rubrique décrit comment concevoir le contenu de l'interface utilisateur pour chaque configuration.
author: johanhoffmann
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 786ea9a3da98e9f1812b007d4301cb47680e6894
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/28/2021
ms.locfileid: "5077576"
---
# <a name="design-the-production-floor-execution-interface"></a><span data-ttu-id="74c9f-103">Concevoir l’interface d’exécution de l’atelier de production</span><span class="sxs-lookup"><span data-stu-id="74c9f-103">Design the production floor execution interface</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="74c9f-104">Vous pouvez concevoir le contenu de l'interface utilisateur pour chaque configuration utilisée par l'interface d'exécution de l'atelier de production.</span><span class="sxs-lookup"><span data-stu-id="74c9f-104">You can design the content of the user interface for each configuration used by the production floor execution interface.</span></span> <span data-ttu-id="74c9f-105">Par exemple, les collaborateurs d'une cellule de travail peuvent avoir besoin de pouvoir ouvrir des instructions de travail dans l'atelier de production, tandis que dans une autre cellule de travail, les instructions ne sont pas nécessaires.</span><span class="sxs-lookup"><span data-stu-id="74c9f-105">For example, workers in one work cell might need to be able to open job instructions on the production floor, while in another work cell, instructions are not needed.</span></span> <span data-ttu-id="74c9f-106">Dans ce cas, deux configurations doivent être créées, l'une avec un bouton pour ouvrir les pièces jointes et l'autre sans ce bouton.</span><span class="sxs-lookup"><span data-stu-id="74c9f-106">In that case, two configurations should be created, one with a button for opening document attachments and one without this button.</span></span>

## <a name="design-a-tab"></a><span data-ttu-id="74c9f-107">Concevoir un onglet</span><span class="sxs-lookup"><span data-stu-id="74c9f-107">Design a tab</span></span>

<span data-ttu-id="74c9f-108">Sur la page **Configurer l'exécution de l'atelier de production**, vous pouvez créer et configurer des onglets en sélectionnant des **onglets Conception** sur le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="74c9f-108">On the **Configure production floor execution** page, you can create and configure tabs by selecting **Design tabs** on the Action Pane.</span></span>

<span data-ttu-id="74c9f-109">Chaque onglet est divisé en quatre sections, comme indiqué dans l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="74c9f-109">Each tab is divided into four sections, as shown in the following illustration.</span></span>

<span data-ttu-id="74c9f-110">![Disposition des onglets](media/pfe-tab-layout.png "Disposition des onglets")</span><span class="sxs-lookup"><span data-stu-id="74c9f-110">![Tab layout](media/pfe-tab-layout.png "Tab layout")</span></span>

<span data-ttu-id="74c9f-111">Les éléments suivants sont présentés dans l'illustration :</span><span class="sxs-lookup"><span data-stu-id="74c9f-111">The following elements are shown in the illustration:</span></span>

1. <span data-ttu-id="74c9f-112">Barre d’outils principale</span><span class="sxs-lookup"><span data-stu-id="74c9f-112">Primary toolbar</span></span>
1. <span data-ttu-id="74c9f-113">Barre d’outils secondaire</span><span class="sxs-lookup"><span data-stu-id="74c9f-113">Secondary toolbar</span></span>
1. <span data-ttu-id="74c9f-114">Vue principale</span><span class="sxs-lookup"><span data-stu-id="74c9f-114">Main view</span></span>
1. <span data-ttu-id="74c9f-115">Vue détaillée</span><span class="sxs-lookup"><span data-stu-id="74c9f-115">Detailed view</span></span>

<span data-ttu-id="74c9f-116">Pour créer et configurer un nouvel onglet, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="74c9f-116">To create and configure a new tab, follow these steps:</span></span>

1. <span data-ttu-id="74c9f-117">Accédez à **Contrôle de la production &gt; Configuration &gt; Exécution de la production**.</span><span class="sxs-lookup"><span data-stu-id="74c9f-117">Go to **Production control &gt; Setup &gt; Manufacturing execution**.</span></span>

1. <span data-ttu-id="74c9f-118">Sélectionnez **Onglets de conception** dans le volet Actions pour ouvrir la page **Onglets de conception**.</span><span class="sxs-lookup"><span data-stu-id="74c9f-118">Select **Design tabs** on the Action Pane to open the **Design tabs** page.</span></span>

    <span data-ttu-id="74c9f-119">![Page Onglets de conception](media/pfe-design-tabs.png "Page Onglets de conception")</span><span class="sxs-lookup"><span data-stu-id="74c9f-119">![The Design tabs page](media/pfe-design-tabs.png "The Design tabs page")</span></span>

1. <span data-ttu-id="74c9f-120">Sélectionnez **Nouveau** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="74c9f-120">Select **New** on the Action Pane.</span></span>

1. <span data-ttu-id="74c9f-121">Définissez les paramètres suivants dans l'en-tête de la page :</span><span class="sxs-lookup"><span data-stu-id="74c9f-121">Make the following settings in the header of the page:</span></span>

    - <span data-ttu-id="74c9f-122">**Nom de l'onglet** – Spécifiez un nom pour l'onglet.</span><span class="sxs-lookup"><span data-stu-id="74c9f-122">**Tab name** - Specify a name for the tab.</span></span>
    - <span data-ttu-id="74c9f-123">**Vue principale** – Choisissez entre les deux listes de tâches prédéfinies (*Tâches actives*, *Toutes les tâches* ou *Ma machine*).</span><span class="sxs-lookup"><span data-stu-id="74c9f-123">**Main view** - Select between the two pre-defined job lists (*Active jobs*, *All jobs*, or *My machine*).</span></span>
    - <span data-ttu-id="74c9f-124">**Vue détaillée** – Choisissez entre une valeur vide ou **Détails de la tâche**.</span><span class="sxs-lookup"><span data-stu-id="74c9f-124">**Details view** - Select between a blank value or **Job details**.</span></span> <span data-ttu-id="74c9f-125">Si vous sélectionnez la valeur vide, il n'y aura pas de vue détaillée dans l'onglet. Si vous sélectionnez **Détails de la tâche**, la vue détaillée contiendra une description détaillée de la tâche sélectionnée dans la liste des travaux de la vue principale.</span><span class="sxs-lookup"><span data-stu-id="74c9f-125">If you select the blank value, there will be no detailed view in the tab. If you select **Job details**, the detailed view will contain a detailed description of the job selected in the job list in the main view.</span></span>

1. <span data-ttu-id="74c9f-126">Dans la section **Barre d'outils principale**, choisissez les boutons qui doivent être disponibles dans la barre d'outils principale.</span><span class="sxs-lookup"><span data-stu-id="74c9f-126">In the **Primary toolbar** section, choose which buttons should be available in the primary toolbar.</span></span> <span data-ttu-id="74c9f-127">La colonne **Actions disponibles** affiche une liste de tous les boutons qui peuvent être ajoutés.</span><span class="sxs-lookup"><span data-stu-id="74c9f-127">The **Available actions** column shows a list of all the buttons that can be added.</span></span> <span data-ttu-id="74c9f-128">Les colonnes **Actions sélectionnées** affichent une liste de tous les boutons inclus dans la configuration actuelle.</span><span class="sxs-lookup"><span data-stu-id="74c9f-128">The **Selected actions** columns shows a list of all the buttons that are included in the current configuration.</span></span> <span data-ttu-id="74c9f-129">Utilisez les boutons entre les colonnes pour déplacer les éléments sélectionnés entre les colonnes selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="74c9f-129">Use the buttons between the columns to move selected items between the columns as needed.</span></span> <span data-ttu-id="74c9f-130">Utilisez les boutons haut et bas à côté de la colonne **Actions sélectionnées** pour contrôler l'ordre dans lequel les boutons sont présentés dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="74c9f-130">Use the up and down buttons next to the **Selected actions** column to control the order in which the buttons are presented in the user interface.</span></span>

1. <span data-ttu-id="74c9f-131">Dans la section **Barre d'outils** **secondaire**, choisissez les boutons qui doivent être disponibles dans la barre d'outils secondaire.</span><span class="sxs-lookup"><span data-stu-id="74c9f-131">In the **Secondary** **toolbar** section, choose which buttons should be available in the secondary toolbar.</span></span> <span data-ttu-id="74c9f-132">La colonne **Actions disponibles** affiche une liste de tous les boutons qui peuvent être ajoutés.</span><span class="sxs-lookup"><span data-stu-id="74c9f-132">The **Available actions** column shows a list of all the buttons that can be added.</span></span> <span data-ttu-id="74c9f-133">Les colonnes **Actions sélectionnées** affichent une liste de tous les boutons inclus dans la configuration actuelle.</span><span class="sxs-lookup"><span data-stu-id="74c9f-133">The **Selected actions** columns shows a list of all the buttons that are included in the current configuration.</span></span> <span data-ttu-id="74c9f-134">Utilisez les boutons entre les colonnes pour déplacer les éléments sélectionnés entre les colonnes selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="74c9f-134">Use the buttons between the columns to move selected items between the columns as needed.</span></span> <span data-ttu-id="74c9f-135">Utilisez les boutons haut et bas à côté de la colonne **Actions sélectionnées** pour contrôler l'ordre dans lequel les boutons sont présentés dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="74c9f-135">Use the up and down buttons next to the **Selected actions** column to control the order in which the buttons are presented in the user interface.</span></span>

## <a name="associate-a-tab-with-a-configuration"></a><span data-ttu-id="74c9f-136">Associer un onglet à une configuration</span><span class="sxs-lookup"><span data-stu-id="74c9f-136">Associate a tab with a configuration</span></span>

<span data-ttu-id="74c9f-137">Une fois que vous avez conçu tous les onglets dont vous avez besoin, vous pouvez les associer à une configuration.</span><span class="sxs-lookup"><span data-stu-id="74c9f-137">After you designed all the tabs you need, you can associate them with a configuration.</span></span>

1. <span data-ttu-id="74c9f-138">Accédez à **Contrôle de la production &gt; Configuration &gt; Configurer l'exécution de l'atelier de production**.</span><span class="sxs-lookup"><span data-stu-id="74c9f-138">Go to **Production control &gt; Setup &gt; Configure production floor execution**.</span></span>

    <span data-ttu-id="74c9f-139">![Configurer l’exécution de l’atelier de production](media/pfe-config-prod-floor-execution.png "Configurer l’exécution de l’atelier de production")</span><span class="sxs-lookup"><span data-stu-id="74c9f-139">![Configure production floor execution](media/pfe-config-prod-floor-execution.png "Configure production floor execution")</span></span>

1. <span data-ttu-id="74c9f-140">Dans le raccourci **Sélection d'onglet**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="74c9f-140">On the **Tab selection** FastTab, select **Add**.</span></span>

1. <span data-ttu-id="74c9f-141">Une nouvelle ligne est ajoutée à la grille.</span><span class="sxs-lookup"><span data-stu-id="74c9f-141">A new row is added to the grid.</span></span> <span data-ttu-id="74c9f-142">Pour cette nouvelle ligne, sélectionnez le nom d'un onglet que vous souhaitez ajouter à la configuration.</span><span class="sxs-lookup"><span data-stu-id="74c9f-142">For this new row, select the name of a tab that you want to add to the configuration.</span></span>

1. <span data-ttu-id="74c9f-143">Continuez à ajouter des onglets supplémentaires si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="74c9f-143">Continue to add additional tabs as needed.</span></span>

1. <span data-ttu-id="74c9f-144">Utilisez les boutons **Déplacer vers le haut** et **Déplacer vers le bas** de la barre d'outils pour organiser les onglets selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="74c9f-144">Use the **Move up** and **Move down** buttons on the toolbar to arrange the tabs as needed.</span></span> <span data-ttu-id="74c9f-145">Les onglets seront affichés de gauche à droite dans l'ordre indiqué dans la capture d'écran ci-dessus (l'onglet en haut est affiché à gauche).</span><span class="sxs-lookup"><span data-stu-id="74c9f-145">The tabs will be displayed from left to right in the order shown in the above screenshot (the tab at the top is shown on the left).</span></span>
