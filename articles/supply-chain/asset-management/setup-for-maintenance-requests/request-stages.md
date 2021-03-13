---
title: États du cycle de vie de la demande de maintenance
description: Cette rubrique décrit comment paramétrer les états du cycle de vie de la demande de maintenance dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetRequestLifecycleState, EntAssetRequestLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d3c2f717969b938d05e68ac775d31b6a5d5ec26a
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5022078"
---
# <a name="maintenance-request-lifecycle-states"></a><span data-ttu-id="314b5-103">États du cycle de vie de la demande de maintenance</span><span class="sxs-lookup"><span data-stu-id="314b5-103">Maintenance request lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="314b5-104">Les états du cycle de vie de la demande de maintenance définissent les différentes étapes d'une demande.</span><span class="sxs-lookup"><span data-stu-id="314b5-104">Maintenance request lifecycle states define the stages that a request can go through.</span></span> <span data-ttu-id="314b5-105">**Créé**, **Actif** et **Terminé** sont des exemples.</span><span class="sxs-lookup"><span data-stu-id="314b5-105">Examples include **Created**, **Active**, and **Ended**.</span></span> <span data-ttu-id="314b5-106">Lorsqu'une demande de maintenance est convertie en bon de travail, l'état du cycle de vie de la demande de maintenance doit être mis jour sur **Terminé** ou **Clôturé** pour indiquer que la demande de maintenance n'est plus active.</span><span class="sxs-lookup"><span data-stu-id="314b5-106">When a maintenance request is converted to a work order, the maintenance request lifecycle state should be updated to **Ended** or **Closed** to indicate that the maintenance request is no longer active.</span></span> <span data-ttu-id="314b5-107">Dans la page de liste **Toutes les demandes de maintenance**, vous pouvez afficher toutes les demandes de maintenance, quel que soit leur état du cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="314b5-107">On the **All maintenance requests** list page, you can view all maintenance requests, regardless of their lifecycle state.</span></span>

## <a name="set-up-maintenance-request-lifecycle-states"></a><span data-ttu-id="314b5-108">Définir les états du cycle de vie de la demande de maintenance</span><span class="sxs-lookup"><span data-stu-id="314b5-108">Set up maintenance request lifecycle states</span></span>

1. <span data-ttu-id="314b5-109">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Demandes de maintenance** \> **États du cycle de vie**.</span><span class="sxs-lookup"><span data-stu-id="314b5-109">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Lifecycle states**.</span></span>
2. <span data-ttu-id="314b5-110">Sélectionnez **Nouveau** pour créer un état du cycle de vie de la demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="314b5-110">Select **New** to create a maintenance request lifecycle state.</span></span>
3. <span data-ttu-id="314b5-111">Dans le champ **État du cycle de vie**, entrez un ID pour l'état du cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="314b5-111">In the **Lifecycle state** field, enter an ID for the lifecycle state.</span></span>
4. <span data-ttu-id="314b5-112">Dans le champ **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="314b5-112">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="314b5-113">Dans le raccourci **Détails**, le champ **Modèles de cycle de vie** affiche le nombre de modèles de cycle de vie de la demande de maintenance qui utilisent cet état du cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="314b5-113">On the **Details** FastTab, the **Lifecycle models** field shows the number of maintenance request lifecycle models that use this lifecycle state.</span></span>

5. <span data-ttu-id="314b5-114">Dans le raccourci **Général**, définissez l'option **Actif** sur **Oui** si une demande de maintenance doit être active lorsqu'elle est dans cet état du cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="314b5-114">On the **General** FastTab, set the **Active** option to **Yes** if a maintenance request should be active while it's in this lifecycle state.</span></span>
6. <span data-ttu-id="314b5-115">Définissez l'option **Définir la fin réelle** sur **Oui** si une date et une heure de fin réelles doivent être automatiquement entrées dans une demande de maintenance qui est dans cet état du cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="314b5-115">Set the **Set actual end** option to **Yes** if an actual end date and time should automatically be entered on a maintenance request that is in this lifecycle state.</span></span>
7. <span data-ttu-id="314b5-116">Définissez l'option **Créer un ordre de travail** sur **Oui** si un ordre de travail peut être créé à partir d'une demande de maintenance qui est dans cet état du cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="314b5-116">Set the **Create work order** option to **Yes** if a work order can be created from a maintenance request that is in this lifecycle state.</span></span>
8. <span data-ttu-id="314b5-117">Définissez l'option **Supprimer** sur **Oui** si une demande de maintenance peut être supprimée lorsqu'elle est dans cet état du cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="314b5-117">Set the **Delete** option to **Yes** if a maintenance request can be deleted while it's in this lifecycle state.</span></span>
9. <span data-ttu-id="314b5-118">Sur l'organisateur **Mettre à jour**, les options **Entrant** et **Sortant** dans la section **Actif** sont pertinentes si vous utilisez la réparation de dépôt.</span><span class="sxs-lookup"><span data-stu-id="314b5-118">On the **Update** FastTab, the **Inbound** and **Outbound** options in the **Asset** section are relevant if you use depot repair.</span></span> <span data-ttu-id="314b5-119">Définissez l'option appropriée sur **Oui** si l'état du cycle de vie des actifs sélectionnés sur une demande de maintenance doit être automatiquement mis à jour sur **Entrant** ou **Sortant** lorsque l'état du cycle de vie de la demande de maintenance de cette demande de maintenance est défini sur **Entrant** ou **Sortant**.</span><span class="sxs-lookup"><span data-stu-id="314b5-119">Set the appropriate option to **Yes** if the asset lifecycle state of assets that are selected on a maintenance request should automatically be updated to **Inbound** or **Outbound** when the maintenance request lifecycle state of that maintenance request is set to **Inbound** or **Outbound**.</span></span>

<span data-ttu-id="314b5-120">L'illustration suivante présente un exemple de la page **États du cycle de vie de la demande de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="314b5-120">The follow illustration shows an example of the **Maintenance request lifecycle states** page.</span></span>

![Page États du cycle de vie de la demande de maintenance](media/02-setup-for-requests.png)

> [!NOTE]
> <span data-ttu-id="314b5-122">Les états du cycle de vie de la demande de maintenance, les groupes d'états du cycle de vie et les types sont liés et utilisés de la même manière que les états du cycle de vie de l'ordre de travail, les groupes d'états du cycle de vie et les types.</span><span class="sxs-lookup"><span data-stu-id="314b5-122">Maintenance request lifecycle states, lifecycle state groups, and types are related to, and used in the same way as, work order lifecycle states, lifecycle state groups, and types.</span></span> 

## <a name="set-up-maintenance-request-lifecycle-models"></a><span data-ttu-id="314b5-123">Définir les modèles de cycle de vie de la demande de maintenance</span><span class="sxs-lookup"><span data-stu-id="314b5-123">Set up maintenance request lifecycle models</span></span>

<span data-ttu-id="314b5-124">Après avoir créé les états du cycle de vie requis pour vos demandes de maintenance, ils peuvent être divisés en groupes d'états du cycle de vie ou en modèles de cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="314b5-124">After you've created the lifecycle states that are required for your maintenance requests, they can be divided into lifecycle state groups, or lifecycle models.</span></span> <span data-ttu-id="314b5-125">Les modèles de cycle de vie de la demande de maintenance permettent de créer le flux qui peut être utilisé pour différents types de demandes de maintenance.</span><span class="sxs-lookup"><span data-stu-id="314b5-125">Maintenance request lifecycle models are used to create the flow that can be used for different types of maintenance requests.</span></span> <span data-ttu-id="314b5-126">Au minimum, un modèle de cycle de vie de la demande de maintenance standard doit être créé.</span><span class="sxs-lookup"><span data-stu-id="314b5-126">At a minimum, one standard maintenance request lifecycle model should be created.</span></span>

1. <span data-ttu-id="314b5-127">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Demandes de maintenance** \> **Modèles de cycle de vie**.</span><span class="sxs-lookup"><span data-stu-id="314b5-127">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Lifecycle models**.</span></span>
2. <span data-ttu-id="314b5-128">Sélectionnez **Nouveau** pour créer un modèle de cycle de vie de la demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="314b5-128">Select **New** to create a maintenance request lifecycle model.</span></span>
3. <span data-ttu-id="314b5-129">Dans le champ **Modèle de cycle de vie**, entrez un ID pour le modèle de cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="314b5-129">In the **Lifecycle model** field, enter an ID for the lifecycle model.</span></span>
4. <span data-ttu-id="314b5-130">Dans le champ **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="314b5-130">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="314b5-131">Dans le raccourci **Détails**, le champ **États du cycle de vie** affiche le nombre d'états du cycle de vie qui sont sélectionnés dans ce modèle de cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="314b5-131">On the **Details** FastTab, the **Lifecycle states** shows the number of lifecycle states that are selected in this lifecycle model.</span></span> <span data-ttu-id="314b5-132">Le champ **Types de demandes de maintenance** affiche le nombre de types de demandes de maintenance qui utilisent ce modèle de cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="314b5-132">The **Maintenance request types** field shows the number of maintenance request types that use this lifecycle model.</span></span>

5. <span data-ttu-id="314b5-133">Dans le raccourci **États du cycle de vie**, sélectionnez les états du cycle de vie qui doivent être inclus dans le modèle de cycle de vie :</span><span class="sxs-lookup"><span data-stu-id="314b5-133">On the **Lifecycle states** FastTab, select the lifecycle states that should be included in the lifecycle model:</span></span>

    - <span data-ttu-id="314b5-134">Pour inclure un état du cycle de vie dans le modèle de cycle de vie, sélectionnez-le dans la section **États du cycle de vie restants**, puis utilisez le bouton Flèche droite ![Flèche droite](media/03-setup-for-requests.png) pour le déplacer vers la section **États du cycle de vie sélectionnés**.</span><span class="sxs-lookup"><span data-stu-id="314b5-134">To include a lifecycle state in the lifecycle model, select it in the **Lifecycle states remaining** section, and then select the right arrow button ![Right arrow](media/03-setup-for-requests.png) to move it to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="314b5-135">Pour inclure tous les états du cycle de vie disponibles dans le modèle de cycle de vie, sélectionnez le bouton **Sélectionner tous les états disponibles** ![Sélectionner tous les états disponibles](media/04-setup-for-requests.png).</span><span class="sxs-lookup"><span data-stu-id="314b5-135">To include all the available lifecycle states in the lifecycle model, select the **Select all available states** button ![Select all available states](media/04-setup-for-requests.png).</span></span> <span data-ttu-id="314b5-136">Tous les états du cycle de vie sont déplacés vers la section **États du cycle de vie sélectionnés**.</span><span class="sxs-lookup"><span data-stu-id="314b5-136">All lifecycle states are moved to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="314b5-137">Pour supprimer un état du cycle de vie du modèle de cycle de vie, sélectionnez-le dans la section **États du cycle de vie sélectionnés**, puis utilisez le bouton Flèche gauche ![Flèche gauche](media/05-setup-for-requests.png) pour le déplacer vers la section **États du cycle de vie restants**.</span><span class="sxs-lookup"><span data-stu-id="314b5-137">To remove a lifecycle state from the lifecycle model, select it in the **Lifecycle states selected** section, and then select the left arrow button ![Left arrow](media/05-setup-for-requests.png) to move it to the **Lifecycle states remaining** section.</span></span>

6. <span data-ttu-id="314b5-138">Dans le raccourci **Général**, les champs de la section **Mises à jour** sont utiles si vous utilisez la réparation au dépôt.</span><span class="sxs-lookup"><span data-stu-id="314b5-138">On the **General** FastTab, the fields in the **Updates** section are relevant if you use depot repair.</span></span>

    - <span data-ttu-id="314b5-139">Dans le champ **État du cycle de vie pour l'actif reçu**, sélectionnez l'état du cycle de vie vers lequel les actifs sélectionnés dans une demande de maintenance doivent être automatiquement mis à jour lorsqu'ils sont reçus pour réparation au dépôt.</span><span class="sxs-lookup"><span data-stu-id="314b5-139">In the **Lifecycle state for asset received** field, select the asset lifecycle state that assets that are selected on a maintenance request should automatically be updated to when they are received for depot repair.</span></span>
    - <span data-ttu-id="314b5-140">Dans le champ **État du cycle de vie pour l'actif livré**, sélectionnez l'état du cycle de vie vers lequel les actifs sélectionnés dans une demande de maintenance doivent être automatiquement mis à jour lorsqu'ils sont retournés après réparation.</span><span class="sxs-lookup"><span data-stu-id="314b5-140">In the **Lifecycle state for asset delivered** field, select the lifecycle state that assets that are selected on a maintenance request should automatically be updated to when they are returned after repair.</span></span>

<span data-ttu-id="314b5-141">L'illustration suivante présente un exemple de la page **Modèles de cycle de vie de la demande de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="314b5-141">The following illustration shows an example of the **Maintenance request lifecycle models** page.</span></span>

![Page Modèles de cycle de vie de la demande de maintenance](media/06-setup-for-requests.png)
