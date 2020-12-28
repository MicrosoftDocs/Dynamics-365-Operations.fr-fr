---
title: Créer un nouveau produit
description: Cette rubrique décrit la procédure de création d'un nouveau produit partagé.
author: ShylaThompson
manager: tfehr
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2a4745fe4fc44f85bcfd388ee573f5a6d0cd8519
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427889"
---
# <a name="create-a-new-product"></a><span data-ttu-id="c4cb6-103">Créer un nouveau produit</span><span class="sxs-lookup"><span data-stu-id="c4cb6-103">Create a new product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c4cb6-104">Cette rubrique décrit la procédure de création d'un nouveau produit partagé.</span><span class="sxs-lookup"><span data-stu-id="c4cb6-104">This topic describes how to create a new shared product.</span></span> <span data-ttu-id="c4cb6-105">Elle est généralement effectuée par un concepteur de produit.</span><span class="sxs-lookup"><span data-stu-id="c4cb6-105">It is usually carried out by a product designer.</span></span> <span data-ttu-id="c4cb6-106">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="c4cb6-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-product"></a><span data-ttu-id="c4cb6-107">Créer un produit</span><span class="sxs-lookup"><span data-stu-id="c4cb6-107">Create a product</span></span>
1. <span data-ttu-id="c4cb6-108">Dans le volet de navigation, allez dans **Modules > Gestion d'informations sur les produits > Produits > Produits**.</span><span class="sxs-lookup"><span data-stu-id="c4cb6-108">In the Navigation pane, go to **Modules > Product information management > Products > Products**.</span></span>
2. <span data-ttu-id="c4cb6-109">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="c4cb6-109">Select **New**.</span></span>
3. <span data-ttu-id="c4cb6-110">Dans le champ **Numéro du produit**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c4cb6-110">In the **Product number** field, type a value.</span></span> <span data-ttu-id="c4cb6-111">Si une souche de numéros n'a pas été paramétrée pour le numéro de produit, elle doit être entrée manuellement.</span><span class="sxs-lookup"><span data-stu-id="c4cb6-111">If a number sequence has not been set up for the product number, it must be entered manually.</span></span>  
4. <span data-ttu-id="c4cb6-112">Dans le champ **Nom du produit**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c4cb6-112">In the **Product name** field, type a value.</span></span> <span data-ttu-id="c4cb6-113">Le nom de produit est par défaut le nom de recherche.</span><span class="sxs-lookup"><span data-stu-id="c4cb6-113">The product name defaults to the search name.</span></span> <span data-ttu-id="c4cb6-114">Vous pouvez la modifier si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="c4cb6-114">You can change this if needed.</span></span>  
5. <span data-ttu-id="c4cb6-115">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4cb6-115">Select **OK**.</span></span>

## <a name="set-up-dimension-groups"></a><span data-ttu-id="c4cb6-116">Paramétrer des groupes de dimensions</span><span class="sxs-lookup"><span data-stu-id="c4cb6-116">Set up dimension groups</span></span>
1. <span data-ttu-id="c4cb6-117">Sélectionnez **Groupes de dimensions** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="c4cb6-117">Select **Dimension groups** to open the drop dialog.</span></span>
2. <span data-ttu-id="c4cb6-118">Saisissez ou sélectionnez une valeur dans le champ **Groupe de dimension de stockage**.</span><span class="sxs-lookup"><span data-stu-id="c4cb6-118">In the **Storage dimension group** field, enter or select a value.</span></span> <span data-ttu-id="c4cb6-119">Le groupe de dimension de stockage détermine les dimensions de stockage que vous devez entrer dans chaque transaction pour le produit et la manière dont il est suivi dans le stock.</span><span class="sxs-lookup"><span data-stu-id="c4cb6-119">The storage dimension group determines which storage dimensions you must enter on each transaction for the product and how it will be tracked in inventory.</span></span>  
3. <span data-ttu-id="c4cb6-120">Saisissez ou sélectionnez une valeur dans le champ **Groupe de dimension de suivi**.</span><span class="sxs-lookup"><span data-stu-id="c4cb6-120">In the **Tracking dimension group** field, enter or select a value.</span></span> <span data-ttu-id="c4cb6-121">Le groupe de dimension de suivi détermine les dimensions de suivi que vous devez entrer pour chaque transaction pour le produit et la manière dont il sera géré dans le stock.</span><span class="sxs-lookup"><span data-stu-id="c4cb6-121">The tracking dimension group determines which tracking dimensions you must enter for each transaction for the product, and how it will be handled in inventory.</span></span>  
4. <span data-ttu-id="c4cb6-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4cb6-122">Select **OK**.</span></span>

