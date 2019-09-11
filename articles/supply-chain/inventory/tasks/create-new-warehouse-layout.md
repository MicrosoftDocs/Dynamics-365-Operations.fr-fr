---
title: Créer une structure d'entrepôt
description: Cette rubrique décrit comment paramétrer les informations pour les emplacements d'un entrepôt.
author: perlynne
manager: AnnBe
ms.date: 07/29/2019
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
ms.openlocfilehash: 302c028a93dfdb57972e4759abbbc4fdedabbd17
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867231"
---
# <a name="create-a-new-warehouse-layout"></a><span data-ttu-id="8d1cf-103">Créer une structure d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="8d1cf-103">Create a new warehouse layout</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8d1cf-104">Cette rubrique décrit comment paramétrer les informations pour les emplacements d'un entrepôt.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-104">This topic describes how to set up information about the locations in a warehouse.</span></span> <span data-ttu-id="8d1cf-105">Cela s'applique uniquement aux entrepôts créés à l'aide de « l'entreposage de base » dans le module Gestion des stocks, pas aux entrepôts créés dans le module Gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-105">This applies only to warehouses created using "basic warehousing" in the Inventory management module, not to warehouses created in the Warehouse management module.</span></span> <span data-ttu-id="8d1cf-106">Vous pouvez utiliser cette procédure dans la société USMF fictive ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-106">You can use this procedure in demo data company USMF, or on your own data.</span></span>


## <a name="set-the-default-location-capacity"></a><span data-ttu-id="8d1cf-107">Définir la capacité d'emplacement par défaut</span><span class="sxs-lookup"><span data-stu-id="8d1cf-107">Set the default location capacity</span></span>
1. <span data-ttu-id="8d1cf-108">Dans le volet de navigation, allez dans **Modules > Gestion des stocks > Paramétrage > Paramètres de gestion des stocks et des entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-108">In the navigation pane, go to **Modules > Inventory management > Setup > Inventory and warehouse management parameters**.</span></span>
2. <span data-ttu-id="8d1cf-109">Cliquez sur l'onglet **Emplacements**.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-109">Select the **Locations** tab.</span></span>
3. <span data-ttu-id="8d1cf-110">Entrez un chiffre dans le champ **Largeur standard**.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-110">In the **Standard width** field, enter a number.</span></span>
4. <span data-ttu-id="8d1cf-111">Entrez un chiffre dans le champ **Profondeur standard**.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-111">In the **Standard depth** field, enter a number.</span></span>
5. <span data-ttu-id="8d1cf-112">Entrez un chiffre dans le champ **Hauteur standard**.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-112">In the **Standard height** field, enter a number.</span></span>
6. <span data-ttu-id="8d1cf-113">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-113">Select **Save**.</span></span>
7. <span data-ttu-id="8d1cf-114">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-114">Close the page.</span></span>

## <a name="define-the-location-name-format"></a><span data-ttu-id="8d1cf-115">Définir le format du nom d'emplacement</span><span class="sxs-lookup"><span data-stu-id="8d1cf-115">Define the location name format</span></span>
1. <span data-ttu-id="8d1cf-116">Dans le volet de navigation, accédez à **Modules > Gestion des stocks > Paramétrage > Décomposition du stock > Entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-116">In the navigation pane, go to **Modules > Inventory management > Setup > Inventory breakdown > Warehouses**.</span></span>
2. <span data-ttu-id="8d1cf-117">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-117">Select **New**.</span></span>
3. <span data-ttu-id="8d1cf-118">Dans le champ **Entrepôts**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-118">In the **Warehouse** field, type a value.</span></span>
4. <span data-ttu-id="8d1cf-119">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-119">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="8d1cf-120">Dans le champ **Site**, sélectionnez l'enregistrement souhaité dans le champ de recherche.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-120">In the **Site** field, select the desired record in the lookup.</span></span>
6. <span data-ttu-id="8d1cf-121">Activez ou désactivez l'extension de la section **Noms d'emplacement**.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-121">Toggle the expansion of the **Location names** section.</span></span> <span data-ttu-id="8d1cf-122">Les options de cette section définissent le format par défaut pour les noms d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-122">The options in this section define the default format for location names.</span></span> <span data-ttu-id="8d1cf-123">Dans notre exemple, le numéro d'allée, le nombre de rayon et le nombre d'étagère sont inclus.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-123">In our example, we'll include the aisle number, rack number and shelf number.</span></span>  
7. <span data-ttu-id="8d1cf-124">Définissez l'option **Inclure allée** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-124">Set the **Include aisle** option to **Yes**.</span></span>
8. <span data-ttu-id="8d1cf-125">Définissez l'option **Inclure rayon** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-125">Set the **Include rack** option to **Yes**.</span></span> 
9. <span data-ttu-id="8d1cf-126">Tapez une valeur pour le rayon dans le champ **Format**.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-126">In the **Format** field, for the rack, type a value.</span></span>
10. <span data-ttu-id="8d1cf-127">Définissez l'option **Inclure étagère** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-127">Set the **Include shelf** option to **Yes**.</span></span>
11. <span data-ttu-id="8d1cf-128">Tapez une valeur pour l'étagère dans le champ **Format**.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-128">In the **Format** field, for the shelf, type a value.</span></span>

## <a name="define-warehouse-locations"></a><span data-ttu-id="8d1cf-129">Définir les emplacements des entrepôts</span><span class="sxs-lookup"><span data-stu-id="8d1cf-129">Define warehouse locations</span></span>
1. <span data-ttu-id="8d1cf-130">Cliquez sur **Entrepôt** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-130">On the Action Pane, select **Warehouse**.</span></span>
2. <span data-ttu-id="8d1cf-131">Sélectionnez **Assistant Emplacement**.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-131">Select **Location Wizard**.</span></span>
3. <span data-ttu-id="8d1cf-132">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-132">Select **Next**.</span></span>
4. <span data-ttu-id="8d1cf-133">Annuler la sélection de l'option **Quais d’expédition**</span><span class="sxs-lookup"><span data-stu-id="8d1cf-133">De-select the **Outbound docks** option</span></span>
5. <span data-ttu-id="8d1cf-134">Annuler la sélection de l'option **Emplacements de stockage en gros**</span><span class="sxs-lookup"><span data-stu-id="8d1cf-134">De-select the **Bulk locations** option</span></span>
6. <span data-ttu-id="8d1cf-135">Sélectionnez **Suivant** jusqu'à arriver à l'option permettant de sélectionner **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-135">Select **Next** until you come to the option to select **Finish**.</span></span>
7. <span data-ttu-id="8d1cf-136">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-136">Close the page.</span></span>
8. <span data-ttu-id="8d1cf-137">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="8d1cf-137">Refresh the page.</span></span>

