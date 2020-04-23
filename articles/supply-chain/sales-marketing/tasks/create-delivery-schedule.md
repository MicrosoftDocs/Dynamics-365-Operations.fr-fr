---
title: Créer un calendrier de livraison
description: Cette procédure illustre comment créer un calendrier de livraison pour une commande client.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesDeliverySchedule, SalesEditLines,  SrsReportViewerForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: af983b30530a7f5d0a82f98deeb12180c42d86cd
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215813"
---
# <a name="create-delivery-schedule"></a><span data-ttu-id="1de1d-103">Créer un calendrier de livraison</span><span class="sxs-lookup"><span data-stu-id="1de1d-103">Create delivery schedule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1de1d-104">Cette procédure illustre comment créer un calendrier de livraison pour une commande client.</span><span class="sxs-lookup"><span data-stu-id="1de1d-104">This procedure demonstrates how to create a delivery schedule for a sales order.</span></span> <span data-ttu-id="1de1d-105">Un plan de livraison est utilisé lorsqu'une quantité sur une commande ou un devis doit être livrée dans le cadre de plusieurs expéditions.</span><span class="sxs-lookup"><span data-stu-id="1de1d-105">A delivery schedule is used when a quantity on an order or a quotation is requested to be delivered in multiple shipments.</span></span> <span data-ttu-id="1de1d-106">Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="1de1d-106">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="create-delivery-schedule"></a><span data-ttu-id="1de1d-107">Créer un calendrier de livraison</span><span class="sxs-lookup"><span data-stu-id="1de1d-107">Create delivery schedule</span></span>
1. <span data-ttu-id="1de1d-108">Allez dans Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="1de1d-108">Go to All sales orders.</span></span>
2. <span data-ttu-id="1de1d-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="1de1d-109">Click New.</span></span>
3. <span data-ttu-id="1de1d-110">Entrez ou sélectionnez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="1de1d-110">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="1de1d-111">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1de1d-111">Click OK.</span></span>
5. <span data-ttu-id="1de1d-112">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="1de1d-112">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="1de1d-113">Entrez une valeur supérieure à 1 dans le champ Quantité.</span><span class="sxs-lookup"><span data-stu-id="1de1d-113">In the Quantity field, enter a number that is bigger than 1.</span></span>
7. <span data-ttu-id="1de1d-114">Cliquez sur Ligne de commandes client.</span><span class="sxs-lookup"><span data-stu-id="1de1d-114">Click Sales order line.</span></span>
8. <span data-ttu-id="1de1d-115">Cliquez sur Plan de livraison.</span><span class="sxs-lookup"><span data-stu-id="1de1d-115">Click Delivery schedule.</span></span>
    * <span data-ttu-id="1de1d-116">La page Plan de livraison est l'emplacement dans lequel vous pouvez spécifier le nombre d'expéditions pour lesquelles la quantité totale de la ligne de commande sera livrée au client.</span><span class="sxs-lookup"><span data-stu-id="1de1d-116">The Delivery schedule page is the place where you can specify the number of shipments in which the total quantity of the order line will be delivered to the customer.</span></span>    
    * <span data-ttu-id="1de1d-117">Par défaut, le système copie la quantité totale et d'autres détails de livraison de la ligne de vente d'origine dans la première ligne du calendrier de livraison.</span><span class="sxs-lookup"><span data-stu-id="1de1d-117">By default, the system copies the total quantity and other delivery details of the original sales line into the first delivery schedule line.</span></span> <span data-ttu-id="1de1d-118">Dans cet exemple, nous allons créer un programme pour deux expéditions. La date de la deuxième expédition sera décalée d'une semaine par rapport à la première.</span><span class="sxs-lookup"><span data-stu-id="1de1d-118">In this example, we'll create a schedule for two shipments, with the second shipment's date offset by a week from the first one.</span></span>  
9. <span data-ttu-id="1de1d-119">Dans le champ Quantité, entrez un nombre qui fait partie de la quantité totale.</span><span class="sxs-lookup"><span data-stu-id="1de1d-119">In the Quantity field, enter a number that is part of the total quantity.</span></span>
10. <span data-ttu-id="1de1d-120">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="1de1d-120">Click New.</span></span>
11. <span data-ttu-id="1de1d-121">Entrez la quantité restante dans le champ Quantité.</span><span class="sxs-lookup"><span data-stu-id="1de1d-121">In the Quantity field, enter the remaining quantity.</span></span>
12. <span data-ttu-id="1de1d-122">Dans le champ Date d'expédition demandée, entrez une date ayant une semaine d'avance sur la date de la première ligne de livraison.</span><span class="sxs-lookup"><span data-stu-id="1de1d-122">In the Requested ship date field, enter a date a date that is one week ahead from the date of the first delivery line.</span></span>
    * <span data-ttu-id="1de1d-123">Les deux options de l'organisateur Conversion de frais contrôlent la manière dont vous souhaitez répartir les frais entre les lignes du plan de livraison, une fois qu'ils ont été affectés à la ligne de commande d'origine.</span><span class="sxs-lookup"><span data-stu-id="1de1d-123">The two options on the Charges conversion FastTab control how you want the charges to be distributed across the delivery schedule lines, once they've been assigned to the original order line.</span></span> <span data-ttu-id="1de1d-124">Si vous sélectionnez Copier les montants bruts, le même montant des frais est copié dans chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="1de1d-124">If you select Copy gross amounts, the same charge amount is copied to each line.</span></span> <span data-ttu-id="1de1d-125">L'option Allouer aux lignes de livraison divise les frais de manière égale entre les lignes de livraison.</span><span class="sxs-lookup"><span data-stu-id="1de1d-125">The Allocate to delivery lines option divides the charge equally across the delivery lines.</span></span>  
    * <span data-ttu-id="1de1d-126">Seuls les frais fixes peuvent être divisés alors que les frais variables sont toujours copiés dans les lignes.</span><span class="sxs-lookup"><span data-stu-id="1de1d-126">Only fixed charges can be divided, whereas variable charges will still be copied to the lines.</span></span>  
13. <span data-ttu-id="1de1d-127">Déplacez le curseur de la deuxième ligne de livraison pour mettre la page à jour.</span><span class="sxs-lookup"><span data-stu-id="1de1d-127">Move the cursor away from the second delivery line to update the page.</span></span>
    * <span data-ttu-id="1de1d-128">Vous pouvez suivre la quantité totale répartie sur les lignes du plan de livraison en regardant les champs Total et Restant.</span><span class="sxs-lookup"><span data-stu-id="1de1d-128">You can keep track of the total quantity that's allocated to the delivery schedule lines by looking at the Total and Remaining fields.</span></span> <span data-ttu-id="1de1d-129">Lorsque la quantité restante est nulle cela signifie que la quantité totale de la ligne d'origine a été affectée au plan.</span><span class="sxs-lookup"><span data-stu-id="1de1d-129">When the remaining quantity is zero, the full quantity from the original line has been allocated to the schedule.</span></span>   
14. <span data-ttu-id="1de1d-130">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1de1d-130">Click OK.</span></span>
    * <span data-ttu-id="1de1d-131">Le plan de livraison vient d'être copié dans les lignes de commande.</span><span class="sxs-lookup"><span data-stu-id="1de1d-131">The delivery schedule has now been copied to the order lines.</span></span>   
    * <span data-ttu-id="1de1d-132">La ligne de commande d'origine (appelée Ligne commerciale) a été convertie en une ligne de commande contenant plusieurs livraisons.</span><span class="sxs-lookup"><span data-stu-id="1de1d-132">The original order line, referred to as a Commercial line, has been converted to an Order line with multiple deliveries.</span></span> <span data-ttu-id="1de1d-133">Elle est identifiée par une icône distincte et fait office d'en-tête pour les lignes de livraison.</span><span class="sxs-lookup"><span data-stu-id="1de1d-133">It is marked with a distinct icon and acts as a header for the delivery lines.</span></span>  
    * <span data-ttu-id="1de1d-134">Les deux nouvelles lignes (appelées lignes de livraison) constituent un plan de livraison.</span><span class="sxs-lookup"><span data-stu-id="1de1d-134">The two new lines, referred to as delivery lines, make up one delivery schedule.</span></span> <span data-ttu-id="1de1d-135">La commande sera traitée par rapport à ces lignes et non la ligne d'origine.</span><span class="sxs-lookup"><span data-stu-id="1de1d-135">The order will be processed against these lines and not the original line.</span></span> <span data-ttu-id="1de1d-136">Si des documents tels que les bordereaux de confirmation, les prélèvements, les bons de livraison ou les factures sont imprimés, seules les lignes de livraison sont affichées.</span><span class="sxs-lookup"><span data-stu-id="1de1d-136">If documents such as confirmation slips, picking lists, packing slips, or invoices are printed, only the delivery lines are shown.</span></span>   
    * <span data-ttu-id="1de1d-137">Les lignes de livraison peuvent avoir des dates de livraison, des quantités, des modes de livraison et des dimensions de stockage différents (telles qu'un site ou un entrepôt).</span><span class="sxs-lookup"><span data-stu-id="1de1d-137">The delivery lines can have different delivery dates, quantities, modes of delivery, and storage dimensions, such as site and warehouse.</span></span> <span data-ttu-id="1de1d-138">Toutefois, les dimensions de produit doivent toujours correspondre à celles de la ligne commerciale et ne peuvent pas être changées.</span><span class="sxs-lookup"><span data-stu-id="1de1d-138">However, the product dimensions must always match the ones on the commercial line and can't be changed.</span></span>  
15. <span data-ttu-id="1de1d-139">Entrez une valeur supérieure à celle actuelle dans le champ Quantité.</span><span class="sxs-lookup"><span data-stu-id="1de1d-139">In the Quantity field, enter a number that's bigger than the current one.</span></span>
16. <span data-ttu-id="1de1d-140">Sélectionnez la ligne commerciale pour voir l'effet du nouveau calcul de quantité.</span><span class="sxs-lookup"><span data-stu-id="1de1d-140">Select the commercial line to see the effect of the quantity recalculation.</span></span>
17. <span data-ttu-id="1de1d-141">Cliquez sur Prélever et emballer dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="1de1d-141">On the Action Pane, click Pick and pack.</span></span>
18. <span data-ttu-id="1de1d-142">Cliquez sur Validation du bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="1de1d-142">Click Post packing slip.</span></span>
19. <span data-ttu-id="1de1d-143">Développez la section Paramètres.</span><span class="sxs-lookup"><span data-stu-id="1de1d-143">Expand the Parameters section.</span></span>
20. <span data-ttu-id="1de1d-144">Sélectionnez « Tout » dans le champ Quantité.</span><span class="sxs-lookup"><span data-stu-id="1de1d-144">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="1de1d-145">Notez que le bon de livraison sera créé pour les deux lignes du plan de livraison et non pour la ligne de commande d'origine.</span><span class="sxs-lookup"><span data-stu-id="1de1d-145">Note that the packing slip will be created for the two delivery schedule lines and not the original order line.</span></span>  
21. <span data-ttu-id="1de1d-146">Sélectionnez Oui dans le champ Imprimer le bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="1de1d-146">Select Yes in the Print packing slip field.</span></span>
22. <span data-ttu-id="1de1d-147">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1de1d-147">Click OK.</span></span>
23. <span data-ttu-id="1de1d-148">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="1de1d-148">Click Yes.</span></span>
24. <span data-ttu-id="1de1d-149">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1de1d-149">Close the page.</span></span>

