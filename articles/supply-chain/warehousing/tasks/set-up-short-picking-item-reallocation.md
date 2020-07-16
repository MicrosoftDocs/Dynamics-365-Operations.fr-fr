---
title: Paramétrer la réaffectation des articles pour les prélèvements partiels
description: Cette rubrique décrit comment les magasiniers peuvent trouver rapidement d’autres emplacements si le stock n’est pas suffisant à l’emplacement où ils ont été redirigés.
author: ShylaThompson
manager: tfehr
ms.date: 06/29/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e14a4fc72d256bea31296bff80d5b5818b95ea9d
ms.sourcegitcommit: ce397c2759f642c595e30fef58a770b50360b2bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2020
ms.locfileid: "3527417"
---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="cea01-103">Paramétrer la réaffectation des articles pour les prélèvements partiels</span><span class="sxs-lookup"><span data-stu-id="cea01-103">Set up short picking item reallocation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cea01-104">Cette procédure décrit comment les magasiniers peuvent trouver rapidement d’autres emplacements si le stock n’est pas suffisant à l’emplacement où ils ont été redirigés.</span><span class="sxs-lookup"><span data-stu-id="cea01-104">This procedure shows how to enable warehouse workers to quickly find alternative locations if there isn’t sufficient inventory at the location they’ve been directed to.</span></span> 

<span data-ttu-id="cea01-105">Le processus de réaffectation est contrôlé par une **Exception de travail** et utilisé par le **manutentionnaire.**</span><span class="sxs-lookup"><span data-stu-id="cea01-105">The reallocation process is controlled by a **Work exception** and used by the warehouse **worker.**</span></span>

<span data-ttu-id="cea01-106">Il est possible d’utiliser les processus de réallocation Automatique, Manuelle ou les deux :</span><span class="sxs-lookup"><span data-stu-id="cea01-106">It is possible to use Automatic, Manual, or both reallocation processes:</span></span>

- <span data-ttu-id="cea01-107">Réallocation automatique - Les directives d’emplacement sont utilisées pour déterminer si les marchandises sont disponibles à un autre emplacement.</span><span class="sxs-lookup"><span data-stu-id="cea01-107">Automatic reallocation - Location directives are used to determine if the goods are available at another location.</span></span> <span data-ttu-id="cea01-108">Si possible, le travail sera mis à jour et l’utilisateur de l’entrepôt sera dirigé vers un autre emplacement.</span><span class="sxs-lookup"><span data-stu-id="cea01-108">If possible, the work will be updated and the warehouse user will be directed to the alternative location.</span></span>
- <span data-ttu-id="cea01-109">Réallocation manuelle - Permet à l’utilisateur de l’entrepôt de sélectionner un ou plusieurs emplacements avec des quantités de marchandises non réservées.</span><span class="sxs-lookup"><span data-stu-id="cea01-109">Manual reallocation - Allows the warehouse user to select from one or more locations with unreserved quantities of goods.</span></span> 
- <span data-ttu-id="cea01-110">Automatique et manuelle - Si le système n’est pas en mesure d’effectuer une réaffectation automatique et que des emplacements sont disponibles avec des quantités non réservées, l’utilisateur sera invité à sélectionner un emplacement.</span><span class="sxs-lookup"><span data-stu-id="cea01-110">Automatic and manual - If the system is unable to perform an automatic reallocation, and locations are available with unreserved quantities, the user will be prompted to select a location.</span></span>

## <a name="set-up-work-exceptions"></a><span data-ttu-id="cea01-111">Définir des exceptions de travail</span><span class="sxs-lookup"><span data-stu-id="cea01-111">Set up work exceptions</span></span>
<span data-ttu-id="cea01-112">Il est possible de définir plusieurs exceptions de travail avec différentes stratégies de réaffectation des articles pour permettre au magasinier d’en choisir une selon les besoins de l’expédition qu’il traite.</span><span class="sxs-lookup"><span data-stu-id="cea01-112">It's possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>

<span data-ttu-id="cea01-113">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="cea01-113">The USMF demo data company was used to create this procedure.</span></span>

1. <span data-ttu-id="cea01-114">Dans le **Volet de navigation**, accédez à **Gestion des entrepôts > Paramétrage > Travail > Exceptions de travail**.</span><span class="sxs-lookup"><span data-stu-id="cea01-114">In the **Navigation pane**, go to **Warehouse management > Setup > Work > Work exceptions**.</span></span>
2. <span data-ttu-id="cea01-115">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="cea01-115">Click **New**</span></span> 
3. <span data-ttu-id="cea01-116">Dans le champ **Code d’exception de travail**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="cea01-116">In the **Work exception code** field, type a value.</span></span> <span data-ttu-id="cea01-117">Ce sera le titre de cette exception .</span><span class="sxs-lookup"><span data-stu-id="cea01-117">This will be the title of this exception .</span></span> <span data-ttu-id="cea01-118">Par exemple, Prélèvement partiel manuel.</span><span class="sxs-lookup"><span data-stu-id="cea01-118">For example, Short picking manual.</span></span>
4. <span data-ttu-id="cea01-119">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="cea01-119">In the **Description** field, type a value.</span></span> <span data-ttu-id="cea01-120">Ce sera une brève description de l’utilisation de cette exception.</span><span class="sxs-lookup"><span data-stu-id="cea01-120">This will be a short description of the usage of this exception.</span></span> <span data-ttu-id="cea01-121">Par exemple, Prélèvement partiel - article non disponible.</span><span class="sxs-lookup"><span data-stu-id="cea01-121">For example, Short picking - item not available.</span></span>
5. <span data-ttu-id="cea01-122">Dans le champ **Type d’exception**, sélectionnez **Prélèvement partiel**.</span><span class="sxs-lookup"><span data-stu-id="cea01-122">In the **Exception** type field, select **Short pick**.</span></span>
6. <span data-ttu-id="cea01-123">Activez la case à cocher **Ajuster le stock**.</span><span class="sxs-lookup"><span data-stu-id="cea01-123">Select the **Adjust inventory** check box.</span></span> <span data-ttu-id="cea01-124">Si cette option est sélectionnée, cela signifie que le stock est automatiquement ajusté sur 0 à l’emplacement de prélèvement partiel.</span><span class="sxs-lookup"><span data-stu-id="cea01-124">If selected, inventory will automatically be adjusted to 0 at the short picked location.</span></span>
7. <span data-ttu-id="cea01-125">Dans le champ **Code type d’ajustement par défaut**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="cea01-125">In the **Default adjustment type code** field, enter or select a value.</span></span> <span data-ttu-id="cea01-126">Par exemple, dans USMF, vous pouvez sélectionner **Supprimer Res Adj Out**. Chaque code de type d’ajustement contient quatre caractéristiques : nom, description, nom du journal de stock et **Supprimer les réservations**.</span><span class="sxs-lookup"><span data-stu-id="cea01-126">For example, in USMF you can select **Remove Res Adj Out**. Each Adjustment type code contains four characteristics: name, description, inventory journal name, and **Remove reservations**.</span></span> <span data-ttu-id="cea01-127">Si **Supprimer les réservations** est activé, les réservations de la ligne de commande sélectionnée seront supprimées.</span><span class="sxs-lookup"><span data-stu-id="cea01-127">If **Remove reservations** is enabled, the short-picked order line's reservations will be removed.</span></span>  
8. <span data-ttu-id="cea01-128">Dans le champ **Réaffectation des articles**, sélectionnez une valeur, comme Manuelle.</span><span class="sxs-lookup"><span data-stu-id="cea01-128">In the **Item reallocation** field, select a value, such as Manual.</span></span> <span data-ttu-id="cea01-129">Si vous sélectionnez Manuel ou Automatique et manuel, le magasinier doit être autorisé à utiliser la réaffectation manuelle.</span><span class="sxs-lookup"><span data-stu-id="cea01-129">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="cea01-130">Paramétrer un collaborateur pour utiliser la réaffectation manuelle des articles</span><span class="sxs-lookup"><span data-stu-id="cea01-130">Set up a worker to use manual item reallocation</span></span>

<span data-ttu-id="cea01-131">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="cea01-131">The USMF demo data company was used to create this procedure.</span></span>

1. <span data-ttu-id="cea01-132">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="cea01-132">Close the page.</span></span>
2. <span data-ttu-id="cea01-133">Dans le **Volet de navigation**, accédez à **Gestion des entrepôts > Paramétrage > Agent**.</span><span class="sxs-lookup"><span data-stu-id="cea01-133">In the **Navigation pane**, go to **Warehouse management > Setup > Worker**.</span></span>
3. <span data-ttu-id="cea01-134">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="cea01-134">Click **Edit**.</span></span>
4. <span data-ttu-id="cea01-135">Dans la liste, sélectionnez un collaborateur.</span><span class="sxs-lookup"><span data-stu-id="cea01-135">In the list, select worker.</span></span> <span data-ttu-id="cea01-136">Par exemple, Julia Funderburk.</span><span class="sxs-lookup"><span data-stu-id="cea01-136">For example, Julia Funderburk.</span></span>
5. <span data-ttu-id="cea01-137">Développez l’organisateur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="cea01-137">Expand the **Users** FastTab.</span></span>
6. <span data-ttu-id="cea01-138">Dans la liste, sélectionnez un **Identifiant utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="cea01-138">In the list, select a **User ID**.</span></span> <span data-ttu-id="cea01-139">Par exemple, 24.</span><span class="sxs-lookup"><span data-stu-id="cea01-139">For example, 24.</span></span>
7. <span data-ttu-id="cea01-140">Développez l’organisateur **Travail**.</span><span class="sxs-lookup"><span data-stu-id="cea01-140">Expand the **Work** FastTab.</span></span>
8. <span data-ttu-id="cea01-141">Sélectionnez **Oui** dans le champ **Autoriser la réaffectation manuelle des articles**.</span><span class="sxs-lookup"><span data-stu-id="cea01-141">Select **Yes** in the **Allow manual item reallocation** field.</span></span>
