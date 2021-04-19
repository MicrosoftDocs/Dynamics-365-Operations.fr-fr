---
title: Expédition partielle d’un chargement de transport
description: Cette rubrique explique comment expédier partiellement un chargement et reporter la planification de la capacité du chargement.
author: Mirzaab
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSTransportLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 179a784f1f02ed0840ba5219c350e274272b59eb
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818942"
---
# <a name="partial-shipment-of-a-transport-load"></a><span data-ttu-id="f53c3-103">Expédition partielle d’un chargement de transport</span><span class="sxs-lookup"><span data-stu-id="f53c3-103">Partial shipment of a transport load</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f53c3-104">En paramétrant l’expédition partielle des chargements, vous pouvez gérer des chargements pour lesquels la capacité ne peut pas être déterminée tant toutes les lignes de vente n’ont pas été ajoutées à un chargement.</span><span class="sxs-lookup"><span data-stu-id="f53c3-104">By setting up partial shipment of loads, you can handle loads where the capacity can't be determined until all the sales lines have been added to a load.</span></span> <span data-ttu-id="f53c3-105">Ce processus peut ensuite être finalisé lorsque le nombre exact de palettes est connu.</span><span class="sxs-lookup"><span data-stu-id="f53c3-105">The process can then be finalized when the exact pallet count is known.</span></span> <span data-ttu-id="f53c3-106">Par conséquent, vous ne devez pas décider quelles palettes sont affectées à lesquelles transport jusqu’au moment où un transport est physiquement déchargé du stock intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="f53c3-106">Therefore, you don't have to decide which pallets will be assigned to which transport until the moment when a transport is being physically loaded out of the staged inventory.</span></span>

<span data-ttu-id="f53c3-107">Cette fonctionnalité offre une alternative à l’application d’une structure plus rigide, dans laquelle vous devez déterminer quelles palettes sont affectées à quel transport avant que le travail de prélèvement ou de chargement puisse être créé.</span><span class="sxs-lookup"><span data-stu-id="f53c3-107">This feature offers an alternative to the enforcement of a more rigid structure, where you must determine which pallets will be assigned to which transport before picking work or loading work can be created.</span></span> <span data-ttu-id="f53c3-108">Au lieu de cela, les utilisateurs peuvent configurer des chargements individuels pour une confirmation d’expédition partielle.</span><span class="sxs-lookup"><span data-stu-id="f53c3-108">Instead, users can configure individual loads for a partial shipment confirmation.</span></span> <span data-ttu-id="f53c3-109">Le processus de chargement de transport pour ces chargement peut alors avoir lieu.</span><span class="sxs-lookup"><span data-stu-id="f53c3-109">The transport loading processes for those loads can then occur.</span></span> <span data-ttu-id="f53c3-110">Par conséquent, le service de planification du transport peut planifier des chargements sans avoir à prendre en compte la capacité des transports individuels.</span><span class="sxs-lookup"><span data-stu-id="f53c3-110">Therefore, the transportation planning department can plan loads without having to consider the capacity of individual transports.</span></span>

<span data-ttu-id="f53c3-111">Lors du chargement, les collaborateurs peuvent définir un nouveau chargement de transport dans lequel une palette peut être chargée.</span><span class="sxs-lookup"><span data-stu-id="f53c3-111">At the time of loading, workers can define a new transport load that a pallet can be loaded to.</span></span> <span data-ttu-id="f53c3-112">Sinon, ils peuvent identifier un chargement de transport existant.</span><span class="sxs-lookup"><span data-stu-id="f53c3-112">Alternatively, they can identify an existing transport load.</span></span> <span data-ttu-id="f53c3-113">Ces données peuvent être enregistrées via un appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="f53c3-113">This data can be recorded via a mobile device.</span></span> <span data-ttu-id="f53c3-114">Par conséquent, plusieurs magasiniers peuvent charger le stock avec les mêmes chargements ou des chargements différents sur le même camion.</span><span class="sxs-lookup"><span data-stu-id="f53c3-114">Therefore, several warehouse workers can load inventory from the same loads or different loads onto the same truck.</span></span> <span data-ttu-id="f53c3-115">Les chargements peuvent ensuite être entièrement ou partiellement expédiés.</span><span class="sxs-lookup"><span data-stu-id="f53c3-115">The loads can then be fully or partially shipped.</span></span>

> [!NOTE] 
> <span data-ttu-id="f53c3-116">Pour charger le stock d’un chargement vers un chargement de transport spécifique et expédier partiellement le chargement, le travail doit être généré à l’aide d’une classe de chargement dans un modèle de travail.</span><span class="sxs-lookup"><span data-stu-id="f53c3-116">In order to load inventory from a load to a specific transport load and partially ship the load, work must be generated by using a loading class in a work template.</span></span> <span data-ttu-id="f53c3-117">Le travail de prélèvement habituel de type **Prélèvement** ne peut pas être chargé sur un chargement de transport comme un camion.</span><span class="sxs-lookup"><span data-stu-id="f53c3-117">Ordinary picking work of the **Picking** type can't be loaded to a transport load such as a truck.</span></span>

## <a name="set-up-transport-loads-for-partial-shipment"></a><span data-ttu-id="f53c3-118">Paramétrer des chargements de transport pour une expédition partielle</span><span class="sxs-lookup"><span data-stu-id="f53c3-118">Set up transport loads for partial shipment</span></span>

<span data-ttu-id="f53c3-119">Le paramétrage de l’expédition partielle de chargements inclut les deux procédures suivantes.</span><span class="sxs-lookup"><span data-stu-id="f53c3-119">The setup for partial shipment of loads consists of the following two procedures.</span></span>

### <a name="set-the-loading-strategy"></a><span data-ttu-id="f53c3-120">Définir la stratégie de chargement</span><span class="sxs-lookup"><span data-stu-id="f53c3-120">Set the loading strategy</span></span>

<span data-ttu-id="f53c3-121">Vous devez activer le chargement partiel en définissant la stratégie de chargement.</span><span class="sxs-lookup"><span data-stu-id="f53c3-121">You must enable partial loading by setting the loading strategy.</span></span> <span data-ttu-id="f53c3-122">Vous pouvez définir la stratégie de chargement après avoir créé un chargement.</span><span class="sxs-lookup"><span data-stu-id="f53c3-122">You can set the loading strategy after you've created a load.</span></span>

1. <span data-ttu-id="f53c3-123">Sélectionnez **Gestion des entrepôts** \> **Charges** \> **Toutes les charges**.</span><span class="sxs-lookup"><span data-stu-id="f53c3-123">Select **Warehouse management** \> **Loads** \> **All loads**.</span></span>
2. <span data-ttu-id="f53c3-124">Sélectionnez une charge, puis cliquez sur **En-tête**.</span><span class="sxs-lookup"><span data-stu-id="f53c3-124">Select a load, and then click **Header**.</span></span>
3. <span data-ttu-id="f53c3-125">Dans le champ **Stratégie de chargement**, sélectionnez **Expédition partielle du chargement autorisée**.</span><span class="sxs-lookup"><span data-stu-id="f53c3-125">In the **Loading strategy** field, select **Partial load shipping allowed**.</span></span>

### <a name="create-a-menu-item-for-loading-of-transport-loads"></a><span data-ttu-id="f53c3-126">Créez une option de menu pour le chargement des charges de transport</span><span class="sxs-lookup"><span data-stu-id="f53c3-126">Create a menu item for loading of transport loads</span></span>

<span data-ttu-id="f53c3-127">Vous devez créer une option de menu qui active des charges de transport à charger.</span><span class="sxs-lookup"><span data-stu-id="f53c3-127">You must create a new menu item that enables transport loads to be loaded.</span></span> <span data-ttu-id="f53c3-128">Un chargement de transport vous permet de regrouper des lignes de travail entre une charge ou plusieurs charges.</span><span class="sxs-lookup"><span data-stu-id="f53c3-128">A transport load lets you group work lines from one load or multiple loads.</span></span> <span data-ttu-id="f53c3-129">Tout ce qui est ajouté au chargement de transport peut ensuite être expédié à l’aide d’un scanneur portable.</span><span class="sxs-lookup"><span data-stu-id="f53c3-129">Everything that is added to the transport load can then be shipped by using a mobile scanner.</span></span>

1. <span data-ttu-id="f53c3-130">Sélectionnez **Gestion des entrepôts** \> **Configuration** \> **Appareil mobile** \> **Options de menu d’appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="f53c3-130">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**.</span></span>
2. <span data-ttu-id="f53c3-131">Sélectionnez **Nouveau**, puis, dans le champ **Mode**, sélectionnez **Travail**.</span><span class="sxs-lookup"><span data-stu-id="f53c3-131">Select **New**, and then, in the **Mode** field, select **Work**.</span></span>
3. <span data-ttu-id="f53c3-132">Définissez l’option **Utiliser un travail existant** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="f53c3-132">Set the **Use existing work** option to **Yes**.</span></span>
4. <span data-ttu-id="f53c3-133">Sous l’onglet **Général**, dans le champ **Dirigé par**, sélectionnez **Chargement de transport**.</span><span class="sxs-lookup"><span data-stu-id="f53c3-133">On the **General** tab, in the **Directed by** field, select **Transport loading**.</span></span>
5. <span data-ttu-id="f53c3-134">Pour activer la confirmation d’expédition sur un scanneur mobile, dans le champ **Type de confirmation d’expédition autorisé**, sélectionnez **Chargement de transport**.</span><span class="sxs-lookup"><span data-stu-id="f53c3-134">To enable shipment confirmation on a mobile scanner, in the **Allowed ship confirmation type** field, select **Transport load**.</span></span>

## <a name="confirm-shipment-of-a-transport-load-from-the-client"></a><span data-ttu-id="f53c3-135">Confirmer l’expédition d’un chargement de transport depuis le client</span><span class="sxs-lookup"><span data-stu-id="f53c3-135">Confirm shipment of a transport load from the client</span></span>

<span data-ttu-id="f53c3-136">Ce paramétrage vous permet de confirmer un chargement de transport qui inclut un chargement complet ou une charge partiellement chargée à expédier.</span><span class="sxs-lookup"><span data-stu-id="f53c3-136">This setup lets you confirm a transport load that includes a full load or a partially loaded load to be shipped.</span></span>

1. <span data-ttu-id="f53c3-137">Sélectionnez **Gestion des entrepôts** \> **Charges** \> **Chargements de transport**.</span><span class="sxs-lookup"><span data-stu-id="f53c3-137">Select **Warehouse management** \> **Loads** \> **Transport loads**.</span></span>
2. <span data-ttu-id="f53c3-138">Dans le volet Actions, sous l’onglet **Expédier et recevoir**, dans le groupe **Confirmer**, sélectionnez **Transport**.</span><span class="sxs-lookup"><span data-stu-id="f53c3-138">On the Action Pane, on the **Ship and receive** tab, in the **Confirm** group, select **Transport**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]