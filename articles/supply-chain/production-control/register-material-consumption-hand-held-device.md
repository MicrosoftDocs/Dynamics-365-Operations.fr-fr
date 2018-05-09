---
title: "Enregistrement de la consommation de matières à l'aide d'un appareil mobile"
description: "Cette rubrique décrit un workflow qui active l'enregistrement de la consommation de matières premières dans la production à l'aide d'un appareil portable."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1706093
ms.assetid: 75ee68e0-4b9f-4f4d-b286-f498e0eb73fa
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 9f4685a349c79bbb421d4295485923ee151e7b29
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="register-material-consumption-using-a-mobile-device"></a><span data-ttu-id="35ee2-103">Enregistrement de la consommation de matières à l'aide d'un appareil mobile</span><span class="sxs-lookup"><span data-stu-id="35ee2-103">Register material consumption using a mobile device</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="35ee2-104">Cette rubrique décrit un workflow qui active l'enregistrement de la consommation de matières premières dans la production à l'aide d'un appareil portable.</span><span class="sxs-lookup"><span data-stu-id="35ee2-104">This topic describes a workflow that enables registration of raw material consumption in production by using a handheld device.</span></span>

<a name="introduction"></a><span data-ttu-id="35ee2-105">Introduction</span><span class="sxs-lookup"><span data-stu-id="35ee2-105">Introduction</span></span>
------------

<span data-ttu-id="35ee2-106">Ce workflow est utile s'il y a une obligation stricte de traçabilité des matières.</span><span class="sxs-lookup"><span data-stu-id="35ee2-106">This workflow is relevant if there is a strict requirement for material traceability.</span></span> <span data-ttu-id="35ee2-107">Dans ces cas, pour assurer la traçabilité des matières, le temps et la quantité exacts doivent être déclarés pour la consommation.</span><span class="sxs-lookup"><span data-stu-id="35ee2-107">In those cases, to maintain traceability of the materials, the exact time and quantity must be reported for the consumption.</span></span> <span data-ttu-id="35ee2-108">Ce processus peut être considéré comme opposé aux opérations de préconsommation ou postconsommation, où il existe un décalage entre le moment de l'enregistrement et le moment de la consommation réelle.</span><span class="sxs-lookup"><span data-stu-id="35ee2-108">This process can be seen as opposed to pre- or back-flushing operations, where there is an offset between the time of registration and the time when the actual consumption takes place.</span></span> <span data-ttu-id="35ee2-109">Cela explique pourquoi une stratégie de consommation automatique ne peut pas être utilisée pour certaines matières soumises à des obligations de traçabilité.</span><span class="sxs-lookup"><span data-stu-id="35ee2-109">This explains why a strategy of automatic consumption cannot be used for some materials with traceability requirements.</span></span> <span data-ttu-id="35ee2-110">Examinons un scénario simple qui explique comment paramétrer un workflow pour activer l'enregistrement de la consommation de matières premières dans la production à l'aide d'un appareil portable.</span><span class="sxs-lookup"><span data-stu-id="35ee2-110">Let’s look at a simple scenario that explains how to set up a workflow to enable registration of raw material consumption in production by using a handheld device.</span></span> <span data-ttu-id="35ee2-111">[![paramétrer un workflow pour activer l'enregistrement de la consommation de matières premières à l'aide d'un périphérique portable](./media/scenario3.png)](./media/scenario3.png)</span><span class="sxs-lookup"><span data-stu-id="35ee2-111">[![set up a workflow to enable registration of raw material consumption by using a handheld device](./media/scenario3.png)](./media/scenario3.png)</span></span>

### <a name="scenario-details"></a><span data-ttu-id="35ee2-112">Détails du scénario</span><span class="sxs-lookup"><span data-stu-id="35ee2-112">Scenario details</span></span>

<span data-ttu-id="35ee2-113">Un processus de production continue (5) consomme la matière première contrôlée par lots RM-100.</span><span class="sxs-lookup"><span data-stu-id="35ee2-113">A continuous production process (5) consumes the batch-controlled raw material RM-100.</span></span> <span data-ttu-id="35ee2-114">La matière est disponible à l'emplacement Bulk-001 (1) sur le contenant PL-1 avec deux lots, B1 et B2, tous deux d'une quantité de 100 kilos.</span><span class="sxs-lookup"><span data-stu-id="35ee2-114">The material is on-hand on location Bulk-001 (1) on license plate PL-1 with two batches, B1 and B2, both with a quantity of 100 lbs.</span></span> <span data-ttu-id="35ee2-115">Le travail d'entrepôt (2) est lancé et traité pour RM-100, et la matière est prélevée de Bulk-001 vers l'emplacement d'entrée en production PIL-01 (3), qui est défini comme un emplacement qui ne fait pas l'objet d'un contrôle de contenant.</span><span class="sxs-lookup"><span data-stu-id="35ee2-115">Warehouse work (2) is released and processed for RM-100, and the material is picked from Bulk-001 to the production input location PIL-01 (3), which is defined as non-license plate controlled.</span></span> <span data-ttu-id="35ee2-116">L'opérateur pèse la matière dans l'emplacement d'entrée en production (3) et enregistre le poids et le numéro de lot comme étant consommés (4).</span><span class="sxs-lookup"><span data-stu-id="35ee2-116">The machine operator weighs out material from the production input location (3) and registers the weight and batch number as consumed (4).</span></span> <span data-ttu-id="35ee2-117">Dans l'emplacement d'entrée en production, une partie de la matière est ajoutée manuellement au processus de production à des intervalles de temps définis.</span><span class="sxs-lookup"><span data-stu-id="35ee2-117">From the production input location, a portion of the material is manually added to the production process in defined time intervals.</span></span> <span data-ttu-id="35ee2-118">Lorsque l'opérateur ajoute la matière, elle est pesée sur une échelle et le numéro de lot est enregistré.</span><span class="sxs-lookup"><span data-stu-id="35ee2-118">When the machine operator adds material, it is weighed on a scale and the batch number is registered.</span></span>

## <a name="set-up-the-workflow-to-register-consumption-using-a-handheld-device"></a><span data-ttu-id="35ee2-119">Paramétrer le workflow pour enregistrer la consommation à l'aide d'un appareil portable</span><span class="sxs-lookup"><span data-stu-id="35ee2-119">Set up the workflow to register consumption using a handheld device</span></span>
<span data-ttu-id="35ee2-120">Créez un produit fini, FG-100, avec une nomenclature contenant la matière première contrôlée par lots RM-100.</span><span class="sxs-lookup"><span data-stu-id="35ee2-120">Create a finished-good product, FG-100, with a bill of material that has the batch-controlled raw material RM-100.</span></span> <span data-ttu-id="35ee2-121">Ajoutez deux lots, B1 et B2, de RM-100 d'une quantité de 100 à l'emplacement : Bulk-001 sur le contenant : PL-1.</span><span class="sxs-lookup"><span data-stu-id="35ee2-121">Add two batches, B1 and B2, of RM-100 in a quantity of 100 to location: Bulk-001 on license plate: PL-1.</span></span> <span data-ttu-id="35ee2-122">Le principe d'effacement sur la ligne de nomenclature pour RM-100 est défini sur **Manuel**.</span><span class="sxs-lookup"><span data-stu-id="35ee2-122">The flushing principle on the bill of material line for RM-100 is set to **Manual**.</span></span> <span data-ttu-id="35ee2-123">Définissez l'emplacement d'entrée en production sur PIL-01.</span><span class="sxs-lookup"><span data-stu-id="35ee2-123">Set  the production input location to PIL-01.</span></span> <span data-ttu-id="35ee2-124">Pour ce faire, sélectionnez cet emplacement comme emplacement d'entrée en production par défaut dans l'entrepôt 51.</span><span class="sxs-lookup"><span data-stu-id="35ee2-124">You can do that by selecting this location as the default production input location on warehouse 51.</span></span>

1.  <span data-ttu-id="35ee2-125">Créez une option de menu d'appareil mobile :</span><span class="sxs-lookup"><span data-stu-id="35ee2-125">Create a new mobile device menu item:</span></span> 

-    <span data-ttu-id="35ee2-126">**Nom de l'option de menu** - Permet d'enregistrer la consommation de matières.</span><span class="sxs-lookup"><span data-stu-id="35ee2-126">**Menu item name** - Register material consumption.</span></span> 
-    <span data-ttu-id="35ee2-127">**Titre** - Permet d'enregistrer la consommation de matières.</span><span class="sxs-lookup"><span data-stu-id="35ee2-127">**Title** - Register material consumption.</span></span> 
-    <span data-ttu-id="35ee2-128">**Mode** - Indirect.</span><span class="sxs-lookup"><span data-stu-id="35ee2-128">**Mode** - Indirect.</span></span> 
-    <span data-ttu-id="35ee2-129">**Code d'activité** – Permet d'enregistrer la consommation de matières.</span><span class="sxs-lookup"><span data-stu-id="35ee2-129">**Activity code** - Register material consumption.</span></span>

2.  <span data-ttu-id="35ee2-130">Ajoutez l'option de menu au menu d'appareil mobile **Production**.</span><span class="sxs-lookup"><span data-stu-id="35ee2-130">Add the menu item to the **Production Mobile** device menu.</span></span>
3.  <span data-ttu-id="35ee2-131">Créez un ordre de fabrication pour le produit fini :</span><span class="sxs-lookup"><span data-stu-id="35ee2-131">Create a production order for the finished product:</span></span> 

-    <span data-ttu-id="35ee2-132">**Numéro d'article** - FG-100</span><span class="sxs-lookup"><span data-stu-id="35ee2-132">**Item number** - FG-100</span></span> 
-    <span data-ttu-id="35ee2-133">**Site** - 5</span><span class="sxs-lookup"><span data-stu-id="35ee2-133">**Site** - 5</span></span> 
-    <span data-ttu-id="35ee2-134">**Entrepôt** - 51</span><span class="sxs-lookup"><span data-stu-id="35ee2-134">**Warehouse** - 51</span></span> 
-    <span data-ttu-id="35ee2-135">**Quantité** - 150</span><span class="sxs-lookup"><span data-stu-id="35ee2-135">**Quantity** - 150</span></span>

<span data-ttu-id="35ee2-136">L'ordre de fabrication est **Estimé** et **Lancé** et le travail d'entrepôt est créé.</span><span class="sxs-lookup"><span data-stu-id="35ee2-136">The production order is **Estimated** and **Released** and warehouse work is created.</span></span>

4.  <span data-ttu-id="35ee2-137">Terminez le travail à l'aide du workflow pour le prélèvement des matières premières pour l'appareil portable.</span><span class="sxs-lookup"><span data-stu-id="35ee2-137">Complete the work using the workflow for raw material picking for the handheld device.</span></span>

<span data-ttu-id="35ee2-138">Les matières sont transférées de l'emplacement de stockage en gros vers l'emplacement d'entrée en production PIL-01.</span><span class="sxs-lookup"><span data-stu-id="35ee2-138">This will bring the material from the bulk location to the production input location PIL-01.</span></span> <span data-ttu-id="35ee2-139">Une fois le travail terminé, les matières ont le statut **Prélevé sur l'emplacement d'entrée en production**.</span><span class="sxs-lookup"><span data-stu-id="35ee2-139">After the work is completed, the material has the status **Picked on the production input location**.</span></span> <span data-ttu-id="35ee2-140">Le statut après traitement du travail peut être **Prélevé** ou **Physique réservé**.</span><span class="sxs-lookup"><span data-stu-id="35ee2-140">The status after work has been processed can be either **Picked** or **Reserved physical**.</span></span> <span data-ttu-id="35ee2-141">Ceci est configuré avec le paramètre **Statut de sortie après placement dans l'écran Entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="35ee2-141">This is configured with the parameter **Issue status after put on the warehouse form**.</span></span>

5.  <span data-ttu-id="35ee2-142">Démarrez l'ordre de fabrication à partir du client ou de l'appareil portable à l'aide de l'option de menu **Démarrage de la production**.</span><span class="sxs-lookup"><span data-stu-id="35ee2-142">Start the production order either from the client or from the handheld device by using the **Production start** menu item.</span></span>

<span data-ttu-id="35ee2-143">Une fois l'ordre de fabrication démarré, vous pouvez enregistrer la consommation de matières avec le workflow pour l'appareil portable.</span><span class="sxs-lookup"><span data-stu-id="35ee2-143">After the production order has been started, you can register material consumption with the workflow for the handheld device.</span></span> <span data-ttu-id="35ee2-144">Commençons par enregistrer la consommation de 25 kilos du lot B1.</span><span class="sxs-lookup"><span data-stu-id="35ee2-144">Let's start by registering consumption of 25 lbs of batch B1.</span></span>

6.  <span data-ttu-id="35ee2-145">Sélectionnez l'option de menu **Enregistrer la consommation de** **matières** et, dans le menu de l'appareil portable, entrez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="35ee2-145">Select the **Register material** **consumption** menu item in the menu for the hand held device, enter the following details:</span></span> 

-    <span data-ttu-id="35ee2-146">Numéro de l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="35ee2-146">The production order number.</span></span> 
-    <span data-ttu-id="35ee2-147">Emplacement dans lequel les matières seront consommées, dans ce cas PIL-01.</span><span class="sxs-lookup"><span data-stu-id="35ee2-147">The location on which the material is going to be consumed, in this case PIL-01.</span></span> 
-    <span data-ttu-id="35ee2-148">Numéro d'article RM-100.</span><span class="sxs-lookup"><span data-stu-id="35ee2-148">Item number RM-100.</span></span> 
-    <span data-ttu-id="35ee2-149">Numéro de lot B1.</span><span class="sxs-lookup"><span data-stu-id="35ee2-149">Batch number B1.</span></span> 
-    <span data-ttu-id="35ee2-150">Quantité 25.</span><span class="sxs-lookup"><span data-stu-id="35ee2-150">A quantity of 25.</span></span>

7.  <span data-ttu-id="35ee2-151">Sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="35ee2-151">Select **OK**.</span></span>

<span data-ttu-id="35ee2-152">Notez que le message « La ligne de journal est créée » apparaît sur l'écran.</span><span class="sxs-lookup"><span data-stu-id="35ee2-152">Note that the message "Journal line is created" appears on the display.</span></span> <span data-ttu-id="35ee2-153">Sur l'ordre de fabrication, il existe un journal en cours de type **Prélèvement de production** pour le numéro d'article RM-100 et le numéro de lot B1.</span><span class="sxs-lookup"><span data-stu-id="35ee2-153">On the production order there is an open journal of the type **Production picking list** for item number RM-100 and batch number B1.</span></span> 

<span data-ttu-id="35ee2-154">Vous pouvez maintenant choisir de continuer votre enregistrement, par exemple sur le numéro de lot B2, et chaque fois que vous sélectionnez **OK**, une nouvelle ligne de journal est ajoutée au journal en cours.</span><span class="sxs-lookup"><span data-stu-id="35ee2-154">You can now choose to continue your registration, for example on batch number B2, and each time you select **OK,** a new journal line is added to the open journal.</span></span> 

<span data-ttu-id="35ee2-155">Après avoir terminé votre enregistrement, sélectionnez **Terminé** pour valider le journal et terminer le workflow.</span><span class="sxs-lookup"><span data-stu-id="35ee2-155">After you have finished your registration, select **Done** to post the journal and end the workflow.</span></span>

### <a name="additional-comments"></a><span data-ttu-id="35ee2-156">Commentaires supplémentaires</span><span class="sxs-lookup"><span data-stu-id="35ee2-156">Additional comments</span></span> 

-   <span data-ttu-id="35ee2-157">Si un utilisateur annule le workflow après la création d'une ligne de journal, le journal est à l'état non validé, mais si l'utilisateur utilise le workflow pour le même ordre de fabrication à un moment ultérieur, les lignes sont ajoutées au journal en cours et non à un nouveau journal.</span><span class="sxs-lookup"><span data-stu-id="35ee2-157">If a user cancels the workflow after a journal line is created, the journal is in an unposted state but if the user at a later point uses the workflow for the same production order, then the lines will be added to the open journal rather than to a new journal.</span></span>
-   <span data-ttu-id="35ee2-158">Le nouveau workflow prend également en charge l'enregistrement de numéros de série.</span><span class="sxs-lookup"><span data-stu-id="35ee2-158">The new workflow also supports the registration of serial numbers.</span></span>
-   <span data-ttu-id="35ee2-159">Il est uniquement possible d'enregistrer un numéro d'article défini dans la nomenclature ou dans la formule pour l'ordre de fabrication ou le lot de commandes sélectionné.</span><span class="sxs-lookup"><span data-stu-id="35ee2-159">It is only possible to register an item number that is defined in the bill of material or in the formula for the selected production order or batch order.</span></span>
-   <span data-ttu-id="35ee2-160">Les matières peuvent être surconsommées.</span><span class="sxs-lookup"><span data-stu-id="35ee2-160">Material can be overconsumed.</span></span> <span data-ttu-id="35ee2-161">Par exemple, si les matières sont estimées pour être utilisées avec la quantité de 100 kilos, elles peuvent être surconsommées avec une quantité de 105 kilos, par exemple.</span><span class="sxs-lookup"><span data-stu-id="35ee2-161">For example, if the material is estimated to be consumed with the quantity of 100 lbs, then it can be overconsumed with a quantity of, for example, 105 lbs.</span></span>



