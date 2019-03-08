---
title: Affecter un état du cycle de vie des produits à un produit générique lancé
description: Cette procédure décrit comment affecter un état du cycle de vie des produits à un produit générique lancé et ses variantes.
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd9d40bb331b9e024617c8be55330dfce8ba1cc6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "309470"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a><span data-ttu-id="8b2f3-103">Affecter un état du cycle de vie des produits à un produit générique lancé</span><span class="sxs-lookup"><span data-stu-id="8b2f3-103">Assign a product lifecycle state to a released product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8b2f3-104">Cette procédure décrit comment affecter un état du cycle de vie des produits à un produit générique lancé et ses variantes.</span><span class="sxs-lookup"><span data-stu-id="8b2f3-104">This procedure shows how to assign a product lifecycle state to a released product master and its variants.</span></span> <span data-ttu-id="8b2f3-105">Conditions préalables : vous devez d'abord lire le guide de tâche « Créer un état du cycle de vie des produits » pour vérifier qu'au moins un état du cycle de vie des produits a été créé avant de lire ce guide de tâche.</span><span class="sxs-lookup"><span data-stu-id="8b2f3-105">Prerequisite: You need to play the task guide "Create a new product lifecycle state" first to make sure that you have at least one product lifecycle state created before you can play this task guide.</span></span>


## <a name="find-a-released-product-master"></a><span data-ttu-id="8b2f3-106">Rechercher un produit générique lancé</span><span class="sxs-lookup"><span data-stu-id="8b2f3-106">Find a released product master</span></span>
1. <span data-ttu-id="8b2f3-107">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="8b2f3-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="8b2f3-108">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="8b2f3-108">In the list, find and select the desired record.</span></span>

> [!NOTE]
> <span data-ttu-id="8b2f3-109">Un produit générique a le sous-type Produit.</span><span class="sxs-lookup"><span data-stu-id="8b2f3-109">A product master has the Product subtype Product master.</span></span>  

## <a name="update-the-lifecycle-state"></a><span data-ttu-id="8b2f3-110">Mettre à jour l'état du cycle de vie</span><span class="sxs-lookup"><span data-stu-id="8b2f3-110">Update the lifecycle state</span></span>
1. <span data-ttu-id="8b2f3-111">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="8b2f3-111">Click Edit.</span></span>
2. <span data-ttu-id="8b2f3-112">Dans le champ État du cycle de vie des produits, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8b2f3-112">In the Product lifecycle state field, enter or select a value.</span></span>
3. <span data-ttu-id="8b2f3-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="8b2f3-113">Click Save.</span></span>
4. <span data-ttu-id="8b2f3-114">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="8b2f3-114">Click Yes.</span></span>

> [!NOTE]
> <span data-ttu-id="8b2f3-115">Si Oui est sélectionné, toutes les variantes de produit associées ayant le même statut d'origine que le produit générique lancé sont également mises à jour vers le nouvel état du cycle de vie des produits.</span><span class="sxs-lookup"><span data-stu-id="8b2f3-115">If Yes is selected, all the related released product variants that have the same original status as the released product master are also updated to the new product lifecycle state.</span></span> <span data-ttu-id="8b2f3-116">Si Non est sélectionné, toutes les variantes conservent leur état réel.</span><span class="sxs-lookup"><span data-stu-id="8b2f3-116">If No is selected, all variants keep their actual state.</span></span> <span data-ttu-id="8b2f3-117">Les variantes dont l'état du cycle de vie des produits est différent de celui du produit générique lancé ne sont pas mises à jour.</span><span class="sxs-lookup"><span data-stu-id="8b2f3-117">Variants that have a different product lifecycle state from the released product master are not updated.</span></span>  

## <a name="verify-the-lifecycle-state-of-the-variants"></a><span data-ttu-id="8b2f3-118">Vérifier l'état du cycle de vie des variantes</span><span class="sxs-lookup"><span data-stu-id="8b2f3-118">Verify the lifecycle state of the variants</span></span>
1. <span data-ttu-id="8b2f3-119">Cliquez sur Variantes de produit lancé.</span><span class="sxs-lookup"><span data-stu-id="8b2f3-119">Click Released product variants.</span></span>

> [!NOTE]
> <span data-ttu-id="8b2f3-120">Notez que toutes les variantes ont hérité l'état du cycle de vie sélectionné du produit générique lancé.</span><span class="sxs-lookup"><span data-stu-id="8b2f3-120">Note that all variants have inherited the selected lifecycle state from the released product master.</span></span>  

2. <span data-ttu-id="8b2f3-121">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8b2f3-121">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="8b2f3-122">Dans le champ État du cycle de vie des produits, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8b2f3-122">In the Product lifecycle state field, enter or select a value.</span></span>

