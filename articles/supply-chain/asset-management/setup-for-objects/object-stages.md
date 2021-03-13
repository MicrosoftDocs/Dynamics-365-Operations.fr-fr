---
title: États du cycle de vie de l'actif
description: Cette rubrique explique les états du cycle de vie de l'actif et les modèles de cycle de vie dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetLifecycleModelStateNext, EntAssetObjectLifecycleState, EntAssetLifecycleStateUpdate, EntAssetObjectLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dffedfafd9d75320accf0e27f072bab6fd51f135
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016550"
---
# <a name="asset-lifecycle-states"></a><span data-ttu-id="ed763-103">États du cycle de vie de l'actif</span><span class="sxs-lookup"><span data-stu-id="ed763-103">Asset lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="ed763-104">Cette rubrique explique les états du cycle de vie de l'actif et les modèles de cycle de vie dans le module Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="ed763-104">This topic explains asset lifecycle states and lifecycle models in Asset Management.</span></span> <span data-ttu-id="ed763-105">Les états du cycle de vie de l'actif permettent de définir si un actif est actif ou inactif.</span><span class="sxs-lookup"><span data-stu-id="ed763-105">Asset lifecycle states are used to define whether an asset is active or inactive.</span></span> <span data-ttu-id="ed763-106">Par exemple, vous pouvez paramétrer des états du cycle de vie de l'actif, comme **Créé**, **Actif** et **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="ed763-106">For example, you can set up asset lifecycle states such as **Created**, **Active**, and **Terminated**.</span></span>

> [!NOTE]
> - <span data-ttu-id="ed763-107">Les états du cycle de vie de la demande sont liés aux états du cycle de vie de l'actif.</span><span class="sxs-lookup"><span data-stu-id="ed763-107">Request lifecycle states are linked to asset lifecycle states.</span></span> <span data-ttu-id="ed763-108">Ainsi, lorsqu'une demande est remplacée par un nouvel état du cycle de vie de la demande, l'actif joint à la demande est remplacé par un nouvel état du cycle de vie de l'actif.</span><span class="sxs-lookup"><span data-stu-id="ed763-108">Therefore, when a request is changed to a new request lifecycle state, the asset that is attached to the request is changed to a new asset lifecycle state.</span></span> <span data-ttu-id="ed763-109">Par exemple, si l'état du cycle de vie d'une demande passe à **Entrant**, l'état du cycle de vie de l'actif joint est remplacé par l'état du cycle de vie sélectionné dans le champ **État du cycle de vie entrant** du raccourci **État du cycle de vie de l'actif** de la page **Modèles d'état du cycle de vie de l'actif**.</span><span class="sxs-lookup"><span data-stu-id="ed763-109">For example, if the lifecycle state of a request is changed to **Inbound**, the lifecycle state of the attached asset is changed to the lifecycle state that is selected in the **Inbound lifecycle state** field on the **Asset lifecycle state** FastTab of the **Asset lifecycle state models** page.</span></span> 


<span data-ttu-id="ed763-110">Les états du cycle de vie de l'actif peuvent être paramétrés dans les modèles de cycle de vie de l'actif, où vous pouvez définir les états du cycle de vie requis pour différents types d'actifs.</span><span class="sxs-lookup"><span data-stu-id="ed763-110">Asset lifecycle states can be set up in asset lifecycle models, where you can define the required lifecycle states for various types of assets.</span></span> <span data-ttu-id="ed763-111">Vous paramétrez d'abord les états du cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="ed763-111">You first set up lifecycle states.</span></span> <span data-ttu-id="ed763-112">Vous créez ensuite un modèle de cycle de vie et sélectionnez les états du cycle de vie associés.</span><span class="sxs-lookup"><span data-stu-id="ed763-112">You then create a lifecycle model and select lifecycle states for it.</span></span>

1. <span data-ttu-id="ed763-113">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Actifs** \> **États du cycle de vie**.</span><span class="sxs-lookup"><span data-stu-id="ed763-113">Select **Asset management** \> **Setup** \> **Assets** \> **Lifecycle states**.</span></span>
2. <span data-ttu-id="ed763-114">Sélectionnez **Nouveau** pour créer un état du cycle de vie de l'actif.</span><span class="sxs-lookup"><span data-stu-id="ed763-114">Select **New** to create a new asset lifecycle state.</span></span>
3. <span data-ttu-id="ed763-115">Dans le champ **État du cycle de vie**, entrez l'ID de l'état du cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="ed763-115">In the **Lifecycle state** field, enter the lifecycle state ID.</span></span>
4. <span data-ttu-id="ed763-116">Dans le champ **Nom**, entrez une description.</span><span class="sxs-lookup"><span data-stu-id="ed763-116">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="ed763-117">Le champ **Modèles de cycle de vie** affiche le nombre de modèles de cycle de vie de l'actif qui utilisent l'état du cycle de vie de l'actif.</span><span class="sxs-lookup"><span data-stu-id="ed763-117">The **Lifecycle models** field shows the number of asset lifecycle models that use the asset lifecycle state.</span></span>

5. <span data-ttu-id="ed763-118">Définissez l'option **Actif** sur **Oui** si cet état du cycle de vie doit être actif (autrement dit, si des ordres de travail peuvent être créés pour les actifs qui figurent dans cet état du cycle de vie).</span><span class="sxs-lookup"><span data-stu-id="ed763-118">Set the **Active** option to **Yes** if this lifecycle state should be an active lifecycle state (in other words, if work orders can be created for assets that are in this lifecycle state).</span></span>
6. <span data-ttu-id="ed763-119">Définissez l'option **Supprimer les lignes de calendrier en cours** sur **Oui** si des lignes de calendrier en cours dont l'état du cycle de vie de l'actif est **Créé** doivent être supprimées lorsqu'elles sont dans cet état du cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="ed763-119">Set the **Delete open calendar lines** option to **Yes** if open asset calendar lines that have an asset lifecycle state of **Created** should be deleted when they are in this lifecycle state.</span></span> <span data-ttu-id="ed763-120">Ce paramètre est utile si vous souhaitez nettoyer les programmes de maintenance en cours qui ne sont plus pertinents pour l'actif (par exemple, si l'actif n'est plus actif).</span><span class="sxs-lookup"><span data-stu-id="ed763-120">This setting is useful if you want to clean up any open maintenance schedules that are no longer relevant for the asset (for example, if the asset is no longer active).</span></span>

> [!NOTE]
> <span data-ttu-id="ed763-121">Les états du cycle de vie de l'actif, les modèles de cycle de vie de l'actif et les types d'actif sont liés.</span><span class="sxs-lookup"><span data-stu-id="ed763-121">Asset lifecycle states, asset lifecycle models, and asset types are related.</span></span> <span data-ttu-id="ed763-122">Ils sont utilisés de la même manière que les états du cycle de vie de l'ordre de travail, les modèles de cycle de vie de l'ordre de travail et les types d'ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="ed763-122">They are used in the same way as work order lifecycle states, work order lifecycle models, and work order types.</span></span> 


<span data-ttu-id="ed763-123">Après avoir créé les états du cycle de vie de l'actif requis, vous pouvez paramétrer les états du cycle de vie dans les modèles de cycle de vie de l'actif.</span><span class="sxs-lookup"><span data-stu-id="ed763-123">After you've created the required asset lifecycle states, you can set up lifecycle states in asset lifecycle models.</span></span>

1. <span data-ttu-id="ed763-124">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Actifs** \> **Modèles de cycle de vie**.</span><span class="sxs-lookup"><span data-stu-id="ed763-124">Select **Asset management** \> **Setup** \> **assets** \> **lifecycle models**.</span></span>
2. <span data-ttu-id="ed763-125">Sélectionnez **Nouveau** pour créer un modèle de cycle de vie de l'actif.</span><span class="sxs-lookup"><span data-stu-id="ed763-125">Select **New** to create a new asset lifecycle model.</span></span>
3. <span data-ttu-id="ed763-126">Dans le champ **Modèle de cycle de vie**, entrez l'ID du modèle de cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="ed763-126">In the **Lifecycle model** field, enter the lifecycle model ID.</span></span>
4. <span data-ttu-id="ed763-127">Dans le champ **Nom**, entrez une description.</span><span class="sxs-lookup"><span data-stu-id="ed763-127">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="ed763-128">Le champ **États du cycle de vie** affiche le nombre d'états du cycle de vie de l'actif qui sont sélectionnés dans le modèle de cycle de vie de l'actif.</span><span class="sxs-lookup"><span data-stu-id="ed763-128">The **Lifecycle states** field shows the number of asset lifecycle states that are selected in the asset lifecycle model.</span></span> <span data-ttu-id="ed763-129">Le champ **Types d'actif** affiche le nombre de types d'actif qui utilisent le modèle de cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="ed763-129">The **Asset types** field shows the number of asset types that use the lifecycle model.</span></span>

5. <span data-ttu-id="ed763-130">Dans le raccourci **États du cycle de vie**, sélectionnez les états du cycle de vie de l'actif qui doivent être inclus dans le modèle de cycle de vie de l'actif :</span><span class="sxs-lookup"><span data-stu-id="ed763-130">On the **Lifecycle states** FastTab, select the asset lifecycle states that should be included in the asset lifecycle model:</span></span>

    - <span data-ttu-id="ed763-131">Pour utiliser un état du cycle de vie pour le modèle, sélectionnez-le dans la section **États du cycle de vie restants**, puis utilisez le bouton Flèche droite ![Flèche droite](media/15-setup-for-objects.png) pour le déplacer vers la section **États du cycle de vie sélectionnés**.</span><span class="sxs-lookup"><span data-stu-id="ed763-131">To use a lifecycle state for the model, select it in the **Lifecycle states remaining** section, and then select the right arrow button ![Right arrow](media/15-setup-for-objects.png) to move it to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="ed763-132">Pour utiliser tous les états du cycle de vie disponibles pour le modèle, sélectionnez le bouton **Tous les états du cycle de vie disponibles** ![Tous les états du cycle de vie disponibles](media/20-setup-for-objects.png).</span><span class="sxs-lookup"><span data-stu-id="ed763-132">To use all the available lifecycle states for the model, select the **All available lifecycle states** button ![All available lifecycle states](media/20-setup-for-objects.png).</span></span> <span data-ttu-id="ed763-133">Tous les états du cycle de vie sont transférés vers la section **États du cycle de vie sélectionnés**.</span><span class="sxs-lookup"><span data-stu-id="ed763-133">All lifecycle states are transferred to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="ed763-134">Pour supprimer un état du cycle de vie du modèle, sélectionnez-le dans la section **États du cycle de vie sélectionnés**, puis utilisez le bouton Flèche gauche ![Flèche gauche](media/16-setup-for-objects.png) pour le déplacer vers la section **États du cycle de vie restants**.</span><span class="sxs-lookup"><span data-stu-id="ed763-134">To remove a lifecycle state from the model, select it in the **lifecycle states selected** section, and then select the left arrow button ![Left arrow](media/16-setup-for-objects.png) to move it to the **Lifecycle states remaining** section.</span></span>

6. <span data-ttu-id="ed763-135">Sélectionnez **Mises à jour de l'état du cycle de vie** pour définir les états du cycle de vie de l'actif qui peuvent suivre un état du cycle de vie sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ed763-135">Select **Lifecycle state updates** to define the asset lifecycle states that can follow a selected lifecycle state.</span></span>
7. <span data-ttu-id="ed763-136">Vous utilisez le raccourci **État de l'actif** si vous gérez des actifs que vous recevez pour réparation.</span><span class="sxs-lookup"><span data-stu-id="ed763-136">You use the **Asset state** FastTab if you handle assets that you receive for repair.</span></span> <span data-ttu-id="ed763-137">Dans la section **Entrant/Sortant**, vous pouvez sélectionner les états du cycle de vie de l'actif pour indiquer le workflow d'un actif que vous recevez pour réparation.</span><span class="sxs-lookup"><span data-stu-id="ed763-137">In the **Inbound/outbound** section, you can select asset lifecycle states to indicate the workflow of an asset that you receive for repair.</span></span> <span data-ttu-id="ed763-138">Si vous offrez des actifs d'emprunt aux clients ou aux départements, dans la section **Emprunt**, vous pouvez sélectionner les états du cycle de vie pour les actifs d'emprunt.</span><span class="sxs-lookup"><span data-stu-id="ed763-138">If you offer loan assets to customers or departments, in the **Loan** section, you can select lifecycle states for loan assets.</span></span>
