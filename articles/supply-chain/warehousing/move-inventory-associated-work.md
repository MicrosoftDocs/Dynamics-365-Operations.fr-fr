---
title: "Mouvements de stock avec le travail associé dans la gestion d'entrepôt"
description: "Cette rubrique décrit comment vous paramétrez et appliquez la confirmation de prélèvement des pièces d'un périphérique mobile."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7b330d6aa8e972d3c35bb7783ec0a39f09775011
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="movement-of-inventory-with-associated-work-in-warehouse-management"></a><span data-ttu-id="aa267-103">Mouvements de stock avec le travail associé dans la gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="aa267-103">Movement of inventory with associated work in Warehouse management</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="aa267-104">Grâce au mouvement de stock, vous pouvez déterminer quels collaborateurs d'entrepôt sont autorisés à déplacer le stock réservé.</span><span class="sxs-lookup"><span data-stu-id="aa267-104">Using movement of inventory, you can decide which warehouse workers are allowed to move reserved inventory.</span></span> <span data-ttu-id="aa267-105">Ceci permet une grande flexibilité dans les entrepôts définis où vous pouvez choisir de ne pas permettre à un collaborateur de choisir un nouvel emplacement de prélèvement pour le travail de prélèvement qui est déjà créé.</span><span class="sxs-lookup"><span data-stu-id="aa267-105">This provides a flexibility in regulated warehouses where you can decide to not allow a worker to choose a new pick location for pick work that is already created.</span></span> <span data-ttu-id="aa267-106">Il permet également à un gestionnaire d'entrepôt de contrôler les capacités que certains collaborateurs moins expérimentés doivent posséder.</span><span class="sxs-lookup"><span data-stu-id="aa267-106">It also allows a warehouse manager to control which capabilities some less experienced workers should have.</span></span>

<span data-ttu-id="aa267-107">La flexibilité à gérer les opérations quotidiennes des collaborateurs d'entrepôt peut être utile dans les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="aa267-107">The flexibility to manage the daily operations of warehouse workers can be useful in scenarios such as these:</span></span>

## <a name="scenario-1"></a><span data-ttu-id="aa267-108">Scénario 1</span><span class="sxs-lookup"><span data-stu-id="aa267-108">Scenario 1</span></span>
<span data-ttu-id="aa267-109">Une entreprise a une zone de réception relativement petite, et elle est encombrée de palettes et de boîtes qui traînent ça-et-là.</span><span class="sxs-lookup"><span data-stu-id="aa267-109">A company has a relatively small receiving area, and it’s congested with pallets and boxes awaiting put away.</span></span> <span data-ttu-id="aa267-110">Une grande expédition est prévue pour le jour en cours, donc la personne chargée de la réception décide de libérer la zone de réception en déplaçant une partie des palettes dans une zone secondaire.</span><span class="sxs-lookup"><span data-stu-id="aa267-110">A large shipment is expected on the current day, so the receiving clerk decides to clear up the receiving area by moving some of the pallets to a secondary inbound staging area.</span></span>

## <a name="scenario-2"></a><span data-ttu-id="aa267-111">Scénario 2</span><span class="sxs-lookup"><span data-stu-id="aa267-111">Scenario 2</span></span>
<span data-ttu-id="aa267-112">Un collaborateur expérimenté de l'entrepôt voit une opportunité dans un entrepôt pour consolider les éléments dans un endroit au lieu de les répartir sur 3 emplacements voisins avec peu de quantité de stockage dans chacun d'eux.</span><span class="sxs-lookup"><span data-stu-id="aa267-112">An experienced warehouse worker notices an opportunity in a warehouse to consolidate items in one location instead of having them divided across 3 nearby locations with little quantity on each.</span></span> <span data-ttu-id="aa267-113">Le collaborateur souhaite consolider la quantité en déplaçant des articles dans chacun de ces emplacements vers le même emplacement et sur le même contenant.</span><span class="sxs-lookup"><span data-stu-id="aa267-113">The worker wants to consolidate the quantity by moving items from each of these locations into the same location and onto the same license plate.</span></span>

## <a name="scenario-3"></a><span data-ttu-id="aa267-114">Scénario 3</span><span class="sxs-lookup"><span data-stu-id="aa267-114">Scenario 3</span></span>
<span data-ttu-id="aa267-115">Une palette est en attente d'expédition dans un emplacement intermédiaire, tel que STAGE01, qui est près de BAYDOOR01.</span><span class="sxs-lookup"><span data-stu-id="aa267-115">A pallet is awaiting shipment in a staging location, such as STAGE01, which is near BAYDOOR01.</span></span> <span data-ttu-id="aa267-116">Toutefois, en raison d'une modification des plans, le camion est planifié pour arriver à BAYDOOR04.</span><span class="sxs-lookup"><span data-stu-id="aa267-116">However, due to a change of plans the truck is scheduled to arrive at BAYDOOR04.</span></span> <span data-ttu-id="aa267-117">L'employé chargé des expéditions s'en rend compte et doit veiller à ce que le camion n'attende pas d'être chargé à STAGE01.</span><span class="sxs-lookup"><span data-stu-id="aa267-117">The shipping clerk is aware of this and needs to ensure that the truck does not have to wait to be loaded from STAGE01.</span></span> <span data-ttu-id="aa267-118">Il décide alors de déplacer les articles de cette expédition de STAGE01 vers STAGE04, qui est plus proche de la nouvelle destination.</span><span class="sxs-lookup"><span data-stu-id="aa267-118">The shipping clerk decides to move the items in that shipment from STAGE01 to STAGE04, which is closer to the new destination.</span></span>

### <a name="current-limitations"></a><span data-ttu-id="aa267-119">Restrictions actuelles</span><span class="sxs-lookup"><span data-stu-id="aa267-119">Current limitations</span></span>

<span data-ttu-id="aa267-120">Les réservations de travail que vous pouvez déplacer sont limitées à Commande client, Émission d'un ordre de transfert, Réception d'un ordre de transfert, Commande fournisseur et Travail de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="aa267-120">The work reservations that you can move are limited to Sales order, Transfer order issue, Transfer order receipt, Purchase order, and Replenishment work.</span></span>

<span data-ttu-id="aa267-121">Le déplacement des articles est restreint pour empêcher le fractionnement des lignes de travail.</span><span class="sxs-lookup"><span data-stu-id="aa267-121">Moving items is restricted to prevent splitting of work lines.</span></span> <span data-ttu-id="aa267-122">Cela signifie que si vous avez une ligne de travail pour 100 PC de l'article A situés sur l'emplacement Loc1, vous ne pourrez déplacer que 30 PC de l'article A à partir de là vers un autre emplacement.</span><span class="sxs-lookup"><span data-stu-id="aa267-122">This means that if you have a work line for 100 pcs of item A from location Loc1, you won’t be able to move only 30 pcs of item A from there to another location.</span></span> <span data-ttu-id="aa267-123">Cela mènerait à un fractionnement de la ligne existante de travail à 30 et 70, car les emplacements sont désormais différents.</span><span class="sxs-lookup"><span data-stu-id="aa267-123">This would lead to a split of the existing work line to 30 and 70, because the locations are now different.</span></span>

<span data-ttu-id="aa267-124">Pour les scénarios intermédiaires, où le contenant à partir duquel vous déplacez les marchandises ou le contenant vers lequel vous déplacez les marchandises, sont définis en tant que Contenant cible pour un ordre d'exécution, seul le mouvement du contenant entier est autorisé, et ce pour ne pas diviser le contenant cible.</span><span class="sxs-lookup"><span data-stu-id="aa267-124">For staging scenarios, where the license plate you move the goods from or the license plate you move the goods to, are set as a Target LP for a work order, only movement of the entire LP is allowed, so as not to break up the Target LP.</span></span>
<span data-ttu-id="aa267-125">Seul le mouvement ad-hoc est actuellement pris en charge.</span><span class="sxs-lookup"><span data-stu-id="aa267-125">Only the ad hoc movement is currently supported.</span></span> <span data-ttu-id="aa267-126">Cela signifie que vous ne pourrez pas déplacer le stock réservé via le mouvement à l'aide des options de menu de l'appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="aa267-126">That means that you will not be able to move reserved inventory through the movement by template mobile device menu items.</span></span>

### <a name="set-up-permission-to-move-reserved-inventory-for-individual-workers"></a><span data-ttu-id="aa267-127">Paramétrer l'autorisation de déplacer le stock réservé pour différents collaborateurs</span><span class="sxs-lookup"><span data-stu-id="aa267-127">Set up permission to move reserved inventory for individual workers</span></span>

<span data-ttu-id="aa267-128">Pour le collaborateur qui doit être autorisé à déplacer le stock réservé, activez la case à cocher **Autoriser le mouvement de stock avec le travail associé** sous **Gestion des entrepôts** > **Paramétrage** > **Collaborateur**.</span><span class="sxs-lookup"><span data-stu-id="aa267-128">For the worker who should be allowed to move reserved inventory, select the **Allow movement of inventory with work associated** check box under **Warehouse management** > **Setup** > **Worker**.</span></span>  

### <a name="backported"></a><span data-ttu-id="aa267-129">Ajout</span><span class="sxs-lookup"><span data-stu-id="aa267-129">Backported</span></span>

<span data-ttu-id="aa267-130">Cette fonction a également été ajoutée à Microsoft Dynamics AX 2012 R3 et est disponible dans le cadre de CU12.</span><span class="sxs-lookup"><span data-stu-id="aa267-130">This feature has also been back-ported to Microsoft Dynamics AX 2012 R3 and will be available as part of CU12.</span></span>
<span data-ttu-id="aa267-131">Elle peut être chargée individuellement via le numéro 3192548 de la Base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="aa267-131">It can also be downloaded individually through KB number 3192548.</span></span> 

