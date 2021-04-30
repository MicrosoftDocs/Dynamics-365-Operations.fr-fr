---
title: Mapper les magasins et les équipes si votre organisation a des équipes préexistantes dans Microsoft Teams
description: Cette rubrique explique comment mapper les magasins et les équipes correspondantes dans Dynamics 365 Commerce Headquarters si votre organisation a déjà créé des équipes dans Microsoft Teams avant l’intégration de Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 5a711c1057b87bd792755ef91a84d1c28879c590
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908493"
---
# <a name="map-stores-and-teams-if-there-are-pre-existing-teams-in-microsoft-teams"></a><span data-ttu-id="dc74d-103">Mapper les magasins et les équipes si votre organisation a des équipes préexistantes dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dc74d-103">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dc74d-104">Cette rubrique explique comment mapper les magasins et les équipes correspondantes dans Dynamics 365 Commerce Headquarters si votre organisation a déjà créé des équipes dans Microsoft Teams avant l’intégration de Commerce.</span><span class="sxs-lookup"><span data-stu-id="dc74d-104">This topic covers how to map stores and corresponding teams in Dynamics 365 Commerce headquarters if your organization has already created teams in Microsoft Teams before Commerce integration.</span></span>

<span data-ttu-id="dc74d-105">Votre organisation peut avoir créé des équipes pour certains magasins ou tous avant l’intégration de Dynamics 365 Commerce et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dc74d-105">Your organization may have teams created for some or all of your stores before integrating Dynamics 365 Commerce and Microsoft Teams.</span></span> <span data-ttu-id="dc74d-106">Si tel est le cas, pour établir la synchronisation des tâches entre les PDV Commerce et Microsoft Teams, vous devez fournir le mappage des magasins et des équipes correspondantes dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="dc74d-106">If this is the case, to establish task synchronization between Commerce POS and Microsoft Teams you must provide the mapping of stores and corresponding team in Commerce headquarters.</span></span>

## <a name="map-stores-and-corresponding-teams-in-commerce-headquarters"></a><span data-ttu-id="dc74d-107">Mapper les magasins et les équipes correspondantes dans Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="dc74d-107">Map stores and corresponding teams in Commerce headquarters</span></span> 

<span data-ttu-id="dc74d-108">Pour mapper les magasins et les équipes correspondantes dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="dc74d-108">To map stores and corresponding teams in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="dc74d-109">Accédez à **Administration système \> Espace de travail \> Gestion des données**.</span><span class="sxs-lookup"><span data-stu-id="dc74d-109">Go to **System Administration \> Workspace \> Data management**.</span></span>
1. <span data-ttu-id="dc74d-110">Sélectionnez **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="dc74d-110">Select **Export**.</span></span> 
1. <span data-ttu-id="dc74d-111">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="dc74d-111">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="dc74d-112">Sous **Nom de groupe**, entrez « Exporter le mappage des équipes ».</span><span class="sxs-lookup"><span data-stu-id="dc74d-112">Under **Group name**, enter "Export Teams mapping".</span></span>
1. <span data-ttu-id="dc74d-113">Dans le raccourci **Entités sélectionnées**, sélectionnez **Ajouter une entité**.</span><span class="sxs-lookup"><span data-stu-id="dc74d-113">On the **Selected entities** FastTab, select **Add entity**.</span></span> <span data-ttu-id="dc74d-114">La boîte de dialogue **Ajouter une entité** apparaît.</span><span class="sxs-lookup"><span data-stu-id="dc74d-114">The **Add entity** dialog box appears.</span></span>  
1. <span data-ttu-id="dc74d-115">Dans la liste déroulante **Nom de l’entité**, sélectionnez **Mappage Teams entre la source et les équipes**.</span><span class="sxs-lookup"><span data-stu-id="dc74d-115">In the **Entity name** drop-down list, select **Teams mapping between source and team**.</span></span>
1. <span data-ttu-id="dc74d-116">Dans la liste déroulante **Format de données cible**, sélectionnez **CSV**.</span><span class="sxs-lookup"><span data-stu-id="dc74d-116">In the **Target data format** drop-down list, select **CSV**.</span></span>
1. <span data-ttu-id="dc74d-117">Sélectionnez **Ajouter**, puis sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="dc74d-117">Select **Add**, and then select **Close**.</span></span>
1. <span data-ttu-id="dc74d-118">En haut à gauche sous le volet Actions, sélectionnez **Exporter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="dc74d-118">On the top left under the Action Pane, select **Export now**.</span></span>
1. <span data-ttu-id="dc74d-119">Sous **Statut de traitement de l’entité**, sélectionnez **Télécharger un fichier**.</span><span class="sxs-lookup"><span data-stu-id="dc74d-119">Under **Entity processing status**, select **Download file**.</span></span>
1. <span data-ttu-id="dc74d-120">Dans le fichier CSV exporté, saisissez des valeurs pour **SOURCETYPE**, **SOURCEID** et **TEAMID**, comme suit :</span><span class="sxs-lookup"><span data-stu-id="dc74d-120">In the exported CSV file, enter values for **SOURCETYPE**, **SOURCEID**, and **TEAMID** as follows:</span></span>
    - <span data-ttu-id="dc74d-121">Pour **SOURCETYPE**, saisissez « RetailStore ».</span><span class="sxs-lookup"><span data-stu-id="dc74d-121">For **SOURCETYPE**, enter "RetailStore".</span></span> 
    - <span data-ttu-id="dc74d-122">Pour **SOURCEID**, entrez le numéro de magasin (par exemple, « 000135 » pour le magasin de San Francisco).</span><span class="sxs-lookup"><span data-stu-id="dc74d-122">For **SOURCEID**, enter the store number (for example, "000135" for the San Francisco store).</span></span> <span data-ttu-id="dc74d-123">Vous pouvez trouver les numéros de magasins dans **Retail et Commerce \> Canaux \> Magasins**.</span><span class="sxs-lookup"><span data-stu-id="dc74d-123">You can find store numbers at **Retail and Commerce \> Channels \> Stores**.</span></span>
    - <span data-ttu-id="dc74d-124">Pour **TEAMID**, saisissez l’ID d’équipe correspondant à partir de Microsoft Teams (par exemple, « 5f8bc92b-6aa8-451e-85d1-3949c01ddc6c »).</span><span class="sxs-lookup"><span data-stu-id="dc74d-124">For **TEAMID**, enter the corresponding team ID from Microsoft Teams (for example, "5f8bc92b-6aa8-451e-85d1-3949c01ddc6c").</span></span> <span data-ttu-id="dc74d-125">Vous pouvez trouver des informations sur l’ID d’équipe sur [admin.teams.microsoft.com](https://admin.teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="dc74d-125">You can find team ID information at [admin.teams.microsoft.com](https://admin.teams.microsoft.com).</span></span>
1. <span data-ttu-id="dc74d-126">Enregistrez le fichier CSV sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="dc74d-126">Save the CSV file to your local machine.</span></span>
1. <span data-ttu-id="dc74d-127">Accédez à **Administration système \> Espace de travail \> Gestion des données**, puis sélectionnez **Importer**.</span><span class="sxs-lookup"><span data-stu-id="dc74d-127">Go to **System Administration \> Workspace \> Data management**, and then select **Import**.</span></span>
1. <span data-ttu-id="dc74d-128">Dans le raccourci **Entités sélectionnées**, sélectionnez **Ajouter un fichier**.</span><span class="sxs-lookup"><span data-stu-id="dc74d-128">On the **Selected entities** FastTab, select **Add file**.</span></span> <span data-ttu-id="dc74d-129">La boîte de dialogue **Ajouter un fichier** apparaît.</span><span class="sxs-lookup"><span data-stu-id="dc74d-129">The **Add file** dialog box appears.</span></span>
1. <span data-ttu-id="dc74d-130">Dans la liste déroulante **Nom de l’entité**, sélectionnez **Mappage Teams entre la source et les équipes**.</span><span class="sxs-lookup"><span data-stu-id="dc74d-130">In the **Entity name** drop-down list, select **Teams mapping between source and team**.</span></span>
1. <span data-ttu-id="dc74d-131">Dans la liste déroulante **Format de données source**, sélectionnez **CSV**.</span><span class="sxs-lookup"><span data-stu-id="dc74d-131">In the **Source data format** drop-down list, select **CSV**.</span></span>
1. <span data-ttu-id="dc74d-132">Sélectionnez **Charger et ajouter**, sélectionnez le fichier CSV que vous avez enregistré précédemment, puis sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="dc74d-132">Select **Upload and add**, select the CSV file that you saved previously, and then select **Open**.</span></span>
1. <span data-ttu-id="dc74d-133">Dans la boîte de dialogue **Ajouter un fichier**, sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="dc74d-133">In the **Add file** dialog box, select **Close**.</span></span>
1. <span data-ttu-id="dc74d-134">Sur le volet Actions, sélectionnez **Enregistrer**, puis sélectionnez **Importer**.</span><span class="sxs-lookup"><span data-stu-id="dc74d-134">On the Action Pane, select **Save** , and then select **Import**.</span></span>

<span data-ttu-id="dc74d-135">L’image d’exemple suivante montre le groupe **Exporter le mappage des équipes** dans Commerce avec les éléments **Ajouter une entité** et les en-têtes du fichier CSV exporté mis en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="dc74d-135">The following example image shows the **Export teams mapping** group in Commerce with **Add entity** elements and the exported CSV file headers highlighted.</span></span>

![Exporter le mappage des équipes dans Commerce avec les éléments Ajouter une entité et les en-têtes du fichier CSV exporté mis en surbrillance](media/d365-commerce-data-mgmt-export-entity.png)

> [!NOTE]
> <span data-ttu-id="dc74d-137">Après avoir terminé les étapes précédentes, suivez les étapes de la rubrique [Synchroniser la gestion des tâches entre Microsoft Teams et les PDV](synchronize-tasks-teams-pos.md) pour synchroniser la gestion des tâches.</span><span class="sxs-lookup"><span data-stu-id="dc74d-137">After you complete the preceeding steps, follow the steps in [Synchronize task management between Microsoft Teams and POS](synchronize-tasks-teams-pos.md) to synchronize task management.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="dc74d-138">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="dc74d-138">Additional resources</span></span>

[<span data-ttu-id="dc74d-139">Présentation de l’intégration de Dynamics 365 Commerce et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dc74d-139">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="dc74d-140">Activer l’intégration de Dynamics 365 Commerce et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dc74d-140">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="dc74d-141">Configuration de Microsoft Teams à partir de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="dc74d-141">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="dc74d-142">Synchroniser la gestion des tâches entre Microsoft Teams et les PDV Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="dc74d-142">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="dc74d-143">Gérer les rôles utilisateur dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dc74d-143">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="dc74d-144">FAQ sur l’intégration de Dynamics 365 Commerce et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dc74d-144">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
