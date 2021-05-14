---
title: Créer et tenir à jour un blocage du stock
description: Cette rubrique explique comment utiliser un blocage du stock pour éviter que le stock physique disponible soit réservé par d’autres documents sources sortants.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e9aa38ca52da577fff258bb330922ad7f4044330
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956156"
---
# <a name="create-and-maintain-an-inventory-blocking"></a><span data-ttu-id="ccb78-103">Créer et tenir à jour un blocage du stock</span><span class="sxs-lookup"><span data-stu-id="ccb78-103">Create and maintain an inventory blocking</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ccb78-104">Cette rubrique explique comment utiliser un blocage du stock pour éviter que le stock physique disponible soit réservé par d’autres documents sources sortants.</span><span class="sxs-lookup"><span data-stu-id="ccb78-104">This topic describes how to use an inventory blocking to prevent physical on-hand inventory from being reserved by other outbound source documents.</span></span> <span data-ttu-id="ccb78-105">Avant de commencer les procédures de cette rubrique, vous devez disposer d'un article dans le stock physique disponible.</span><span class="sxs-lookup"><span data-stu-id="ccb78-105">Before you start the procedures in this topic, you must have an item that physical on-hand inventory is available for.</span></span>

## <a name="block-inventory"></a><span data-ttu-id="ccb78-106">Bloquer le stock</span><span class="sxs-lookup"><span data-stu-id="ccb78-106">Block inventory</span></span>

<span data-ttu-id="ccb78-107">Pour créer un enregistrement de blocage de stock afin que le stock soit bloqué, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ccb78-107">To create an inventory blocking record so that inventory is blocked, follow these steps.</span></span>

1. <span data-ttu-id="ccb78-108">Accédez à **Gestion des stocks \> Tâches périodiques \> Blocage du stock**.</span><span class="sxs-lookup"><span data-stu-id="ccb78-108">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="ccb78-109">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ccb78-109">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="ccb78-110">Dans l'en-tête du nouvel enregistrement de blocage, définissez le **Numéro d'article** sur l'élément que vous souhaitez bloquer, puis saisissez une description.</span><span class="sxs-lookup"><span data-stu-id="ccb78-110">On the header of the new blocking record, set the **Item number** field to the item that you want to block, and enter a description.</span></span>
1. <span data-ttu-id="ccb78-111">Dans le raccourci **Général**, dans le champ **Quantité**, saisissez le nombre d'articles à bloquer.</span><span class="sxs-lookup"><span data-stu-id="ccb78-111">On the **General** FastTab, in the **Quantity** field, enter the number of items to block.</span></span>
1. <span data-ttu-id="ccb78-112">Sur le raccourci **Dimensions de stock**, spécifiez le site et l'entrepôt où se trouvent actuellement les éléments que vous souhaitez bloquer.</span><span class="sxs-lookup"><span data-stu-id="ccb78-112">On the **Inventory dimensions** FastTab, specify the site and warehouse where the items that you want to block are currently located.</span></span>
1. <span data-ttu-id="ccb78-113">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ccb78-113">On the Action Pane, select **Save**.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="ccb78-114">Mettre à jour les conditions du blocage du stock</span><span class="sxs-lookup"><span data-stu-id="ccb78-114">Update the conditions of the inventory blocking</span></span>

<span data-ttu-id="ccb78-115">Pour mettre à jour un enregistrement de blocage de stock, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ccb78-115">To update an inventory blocking record, follow these steps.</span></span>

1. <span data-ttu-id="ccb78-116">Accédez à **Gestion des stocks \> Tâches périodiques \> Blocage du stock**.</span><span class="sxs-lookup"><span data-stu-id="ccb78-116">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="ccb78-117">Dans le volet de liste, sélectionnez l’enregistrement du blocage pertinent.</span><span class="sxs-lookup"><span data-stu-id="ccb78-117">In the list pane, select the relevant blocking record.</span></span>
1. <span data-ttu-id="ccb78-118">Modifiez l'enregistrement comme requis.</span><span class="sxs-lookup"><span data-stu-id="ccb78-118">Edit the record as required.</span></span> <span data-ttu-id="ccb78-119">Par exemple, vous pouvez modifier la valeur du champ **Date prévue** pour indiquer à quel moment il est prévu que le stock bloqué devienne disponible pour réservation.</span><span class="sxs-lookup"><span data-stu-id="ccb78-119">For example, you might change the value of the **Expected date** field to indicate when the blocked inventory is expected to become available for reservation.</span></span> <span data-ttu-id="ccb78-120">Si l'option **Reçus attendus** est sélectionnée, la date apparaîtra sur la transaction attendue.</span><span class="sxs-lookup"><span data-stu-id="ccb78-120">If the **Expected receipts** option is selected, the date will appear on the expected transaction.</span></span> <span data-ttu-id="ccb78-121">(L'option **Reçus attendus** est sélectionnée par défaut lorsque vous créez manuellement un enregistrement de blocage.)</span><span class="sxs-lookup"><span data-stu-id="ccb78-121">(The **Expected receipts** option is selected by default when you manually create a blocking record.)</span></span>
1. <span data-ttu-id="ccb78-122">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ccb78-122">On the Action Pane, select **Save**.</span></span>

## <a name="unblock-inventory"></a><span data-ttu-id="ccb78-123">Débloquer le stock</span><span class="sxs-lookup"><span data-stu-id="ccb78-123">Unblock inventory</span></span>

<span data-ttu-id="ccb78-124">Pour supprimer un enregistrement de blocage de stock afin que le stock soit débloqué, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ccb78-124">To remove an inventory blocking record so that inventory is unblocked, follow these steps.</span></span>

1. <span data-ttu-id="ccb78-125">Accédez à **Gestion des stocks \> Tâches périodiques \> Blocage du stock**.</span><span class="sxs-lookup"><span data-stu-id="ccb78-125">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="ccb78-126">Dans le volet de liste, sélectionnez l’enregistrement du blocage pertinent.</span><span class="sxs-lookup"><span data-stu-id="ccb78-126">In the list pane, select the relevant blocking record.</span></span>
1. <span data-ttu-id="ccb78-127">Dans le volet Actions, sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ccb78-127">On the Action Pane, select **Delete**.</span></span>
1. <span data-ttu-id="ccb78-128">Vous êtes invité à confirmer l'opération.</span><span class="sxs-lookup"><span data-stu-id="ccb78-128">You're prompted to confirm the operation.</span></span> <span data-ttu-id="ccb78-129">Sélectionnez **Oui** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="ccb78-129">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="ccb78-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ccb78-130">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
