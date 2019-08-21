---
title: Créer une structure d'entrepôt
description: Cette procédure vous montre comment définir des informations sur les emplacements d'un entrepôt.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f0a52c5d68816a81a94db019387b9ea3ec3efc5a
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845520"
---
# <a name="create-a-new-warehouse-layout"></a><span data-ttu-id="8596f-103">Créer une structure d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="8596f-103">Create a new warehouse layout</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8596f-104">Cette procédure vous montre comment définir des informations sur les emplacements d'un entrepôt.</span><span class="sxs-lookup"><span data-stu-id="8596f-104">This procedure shows you how to set up information about the locations in a warehouse.</span></span> <span data-ttu-id="8596f-105">Cela s'applique uniquement aux entrepôts créés à l'aide de « l'entreposage de base » dans le module Gestion des stocks, pas aux entrepôts créés dans le module Gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="8596f-105">This applies only to warehouses created using "basic warehousing" in the Inventory management module, not to warehouses created in the Warehouse management module.</span></span> <span data-ttu-id="8596f-106">Vous pouvez utiliser cette procédure dans la société USMF fictive ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="8596f-106">You can use this procedure in demo data company USMF, or on your own data.</span></span>


## <a name="set-the-default-location-capacity"></a><span data-ttu-id="8596f-107">Définir la capacité d'emplacement par défaut</span><span class="sxs-lookup"><span data-stu-id="8596f-107">Set the default location capacity</span></span>
1. <span data-ttu-id="8596f-108">Accédez à Gestion des stocks > Paramétrage > Paramètres de gestion des stocks et des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="8596f-108">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="8596f-109">Cliquez sur l'onglet Emplacements.</span><span class="sxs-lookup"><span data-stu-id="8596f-109">Click the Locations tab.</span></span>
3. <span data-ttu-id="8596f-110">Entrez un numéro dans le champ Largeur standard.</span><span class="sxs-lookup"><span data-stu-id="8596f-110">In the Standard width field, enter a number.</span></span>
4. <span data-ttu-id="8596f-111">Entrez un numéro dans le champ Profondeur standard.</span><span class="sxs-lookup"><span data-stu-id="8596f-111">In the Standard depth field, enter a number.</span></span>
5. <span data-ttu-id="8596f-112">Entrez un numéro dans le champ Hauteur standard.</span><span class="sxs-lookup"><span data-stu-id="8596f-112">In the Standard height field, enter a number.</span></span>
6. <span data-ttu-id="8596f-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="8596f-113">Click Save.</span></span>
7. <span data-ttu-id="8596f-114">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8596f-114">Close the page.</span></span>

## <a name="define-the-location-name-format"></a><span data-ttu-id="8596f-115">Définir le format du nom d'emplacement</span><span class="sxs-lookup"><span data-stu-id="8596f-115">Define the location name format</span></span>
1. <span data-ttu-id="8596f-116">Accédez à Gestion des stocks > Paramétrage > Décomposition du stock > Entrepôts.</span><span class="sxs-lookup"><span data-stu-id="8596f-116">Go to Inventory management > Setup > Inventory breakdown > Warehouses.</span></span>
2. <span data-ttu-id="8596f-117">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="8596f-117">Click New.</span></span>
3. <span data-ttu-id="8596f-118">Tapez une valeur dans le champ Entrepôts.</span><span class="sxs-lookup"><span data-stu-id="8596f-118">In the Warehouse field, type a value.</span></span>
4. <span data-ttu-id="8596f-119">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="8596f-119">In the Name field, type a value.</span></span>
5. <span data-ttu-id="8596f-120">Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="8596f-120">In the Site field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="8596f-121">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="8596f-121">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="8596f-122">Activez ou désactivez l'extension de la section Noms d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="8596f-122">Toggle the expansion of the Location names section.</span></span>
    * <span data-ttu-id="8596f-123">Les options de cette section définissent le format par défaut pour les noms d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="8596f-123">The options in this section define the default format for location names.</span></span> <span data-ttu-id="8596f-124">Dans notre exemple, le numéro d'allée, le nombre de rayon et le nombre d'étagère sont inclus.</span><span class="sxs-lookup"><span data-stu-id="8596f-124">In our example, we'll include the aisle number, rack number and shelf number.</span></span>  
8. <span data-ttu-id="8596f-125">Définissez l'option Inclure allée sur Oui.</span><span class="sxs-lookup"><span data-stu-id="8596f-125">Set the Include aisle option to Yes.</span></span>
9. <span data-ttu-id="8596f-126">Définissez l'option Inclure rayon sur Oui.</span><span class="sxs-lookup"><span data-stu-id="8596f-126">Set the Include rack option to Yes.</span></span> 
10. <span data-ttu-id="8596f-127">Tapez une valeur pour le rayon dans le champ Format.</span><span class="sxs-lookup"><span data-stu-id="8596f-127">In the Format field, for the rack, type a value.</span></span>
    * <span data-ttu-id="8596f-128">Par exemple : -##</span><span class="sxs-lookup"><span data-stu-id="8596f-128">For example: -##</span></span>  
11. <span data-ttu-id="8596f-129">Définissez l'option Inclure étagère sur Oui.</span><span class="sxs-lookup"><span data-stu-id="8596f-129">Set the Include shelf option to Yes.</span></span>
12. <span data-ttu-id="8596f-130">Tapez une valeur pour l'étagère dans le champ Format.</span><span class="sxs-lookup"><span data-stu-id="8596f-130">In the Format field, for the shelf, type a value.</span></span>
    * <span data-ttu-id="8596f-131">Par exemple : -##</span><span class="sxs-lookup"><span data-stu-id="8596f-131">For example: -##</span></span>  

## <a name="define-warehouse-locations"></a><span data-ttu-id="8596f-132">Définir les emplacements des entrepôts</span><span class="sxs-lookup"><span data-stu-id="8596f-132">Define warehouse locations</span></span>
1. <span data-ttu-id="8596f-133">Cliquez sur Entrepôt dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="8596f-133">On the Action Pane, click Warehouse.</span></span>
2. <span data-ttu-id="8596f-134">Cliquez sur Assistant Emplacement.</span><span class="sxs-lookup"><span data-stu-id="8596f-134">Click Location Wizard.</span></span>
3. <span data-ttu-id="8596f-135">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="8596f-135">Click Next.</span></span>
4. <span data-ttu-id="8596f-136">Annuler la sélection de l'option Quais d’expédition</span><span class="sxs-lookup"><span data-stu-id="8596f-136">De-select the Outbound docks option</span></span>
5. <span data-ttu-id="8596f-137">Annuler la sélection de l'option Emplacements de stockage en gros</span><span class="sxs-lookup"><span data-stu-id="8596f-137">De-select the Bulk locations option</span></span>
6. <span data-ttu-id="8596f-138">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="8596f-138">Click Next.</span></span>
7. <span data-ttu-id="8596f-139">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="8596f-139">Click Next.</span></span>
8. <span data-ttu-id="8596f-140">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="8596f-140">Click Next.</span></span>
9. <span data-ttu-id="8596f-141">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="8596f-141">Click Next.</span></span>
10. <span data-ttu-id="8596f-142">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="8596f-142">Click Next.</span></span>
11. <span data-ttu-id="8596f-143">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="8596f-143">Click Next.</span></span>
12. <span data-ttu-id="8596f-144">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="8596f-144">Click Next.</span></span>
    * <span data-ttu-id="8596f-145">Notez que les dimensions physiques affichées dans cette page sont celles que vous définissez au début de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="8596f-145">Note that the physical dimensions shown on this page are the ones that you set at the start of this procedure.</span></span>  
13. <span data-ttu-id="8596f-146">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="8596f-146">Click Next.</span></span>
14. <span data-ttu-id="8596f-147">Cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="8596f-147">Click Finish.</span></span>
15. <span data-ttu-id="8596f-148">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8596f-148">Close the page.</span></span>
16. <span data-ttu-id="8596f-149">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="8596f-149">Refresh the page.</span></span>

