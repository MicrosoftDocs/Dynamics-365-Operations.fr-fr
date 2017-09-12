--- 
title: "Créer un ordre de lancement d'achat à partir d'un contrat d'achat"
description: "Cette procédure indique comment utiliser un contrat d'achat lorsque vous créez une commande fournisseur."
author: mkirknel
manager: AnnBe
ms.date: 12/04/2015
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: cecda03dd4d224d4319f2b0b196560389bb54195
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-purchase-release-order-from-a-purchase-agreement"></a><span data-ttu-id="e3b3d-103">Créer un ordre de lancement d'achat à partir d'un contrat d'achat</span><span class="sxs-lookup"><span data-stu-id="e3b3d-103">Create a purchase release order from a purchase agreement</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e3b3d-104">Cette procédure indique comment utiliser un contrat d'achat lorsque vous créez une commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-104">This procedure shows how to use a purchase agreement when you create a purchase order.</span></span> <span data-ttu-id="e3b3d-105">Le contrat d'achat doit être appliqué lorsque vous créez la commande fournisseur car il existe des conditions générales qui doivent être copiées dans l'en-tête de la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-105">The purchase agreement has to be applied when you create the purchase order because there are general terms that should be copied to the purchase order header.</span></span> <span data-ttu-id="e3b3d-106">Cette tâche est généralement effectuée par un agent des achats.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-106">Typically this task would be carried out by a purchasing agent.</span></span> <span data-ttu-id="e3b3d-107">Comme préalable à ce guide, vous devez posséder un contrat d'achat effectif avec un engagement de quantité de produits pour un fournisseur et des articles.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-107">As a prerequisite for this guide, you must have an effective purchase agreement with a product quantity commitment for a vendor and items.</span></span> <span data-ttu-id="e3b3d-108">La même procédure peut être utilisée si vous avez un contrat d'achat avec d'autres types d'engagements.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-108">The same procedure can be used if you have a purchase agreement with other types of commitments.</span></span> <span data-ttu-id="e3b3d-109">Vous pouvez exécuter ce guide dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-109">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="e3b3d-110">Si vous utilisez USMF, vous pouvez d'abord exécuter le guide « Créer un contrat d'achat » pour paramétrer les conditions préalables nécessaires pour ce guide.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-110">If you’re using USMF, you can run the “Create a purchase agreement” guide first to set up the necessary preconditions for this guide.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="e3b3d-111">Créer une commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="e3b3d-111">Create a purchase order</span></span>
1. <span data-ttu-id="e3b3d-112">Ouvrez l'espace de travail de préparation des commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-112">Open the purchase order preparation workspace.</span></span>
2. <span data-ttu-id="e3b3d-113">Cliquez sur Nouvelle commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-113">Click New purchase order.</span></span>
3. <span data-ttu-id="e3b3d-114">Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-114">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e3b3d-115">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-115">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="e3b3d-116">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-116">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="e3b3d-117">Activez ou désactivez l'extension de la section Général.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-117">Toggle the expansion of the General section.</span></span>
7. <span data-ttu-id="e3b3d-118">Dans le champ Contrats d'achat, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-118">In the Purchase agreement field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e3b3d-119">Tous les accords disponibles pour le fournisseur sont répertoriés ici.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-119">All available agreements for the vendor are listed here.</span></span> <span data-ttu-id="e3b3d-120">Trouver l'accord effectif que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-120">Find the effective agreement that you want to use.</span></span>  
8. <span data-ttu-id="e3b3d-121">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-121">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="e3b3d-122">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-122">Click Yes.</span></span>
10. <span data-ttu-id="e3b3d-123">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-123">Click OK.</span></span>

## <a name="add-a-line"></a><span data-ttu-id="e3b3d-124">Ajouter une ligne</span><span class="sxs-lookup"><span data-stu-id="e3b3d-124">Add a line</span></span>
1. <span data-ttu-id="e3b3d-125">Tapez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-125">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="e3b3d-126">S'il existe des dimensions spécifiques de stock ou d'emplacement de l'engagement, vous devez entrer les mêmes valeurs dans la ligne de commande fournisseur pour utiliser l'accord.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-126">If there are specific inventory or location dimensions on the commitment you must enter the same values on the purchase order line to make use of the agreement.</span></span>  
2. <span data-ttu-id="e3b3d-127">Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-127">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e3b3d-128">Le site peut être déjà rempli avec la valeur par défaut de la commande ou du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-128">The site may already be populated with the default value from the order, or from the vendor.</span></span> <span data-ttu-id="e3b3d-129">Si c'est le cas, ignorez cette étape.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-129">If this is the case, skip this step.</span></span>  
3. <span data-ttu-id="e3b3d-130">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-130">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="e3b3d-131">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-131">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="e3b3d-132">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-132">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="e3b3d-133">Validez que le prix est copié à partir de l'engagement.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-133">Validate that the price is copied from the commitment.</span></span>  

## <a name="look-up-the-commitment"></a><span data-ttu-id="e3b3d-134">Rechercher l'engagement</span><span class="sxs-lookup"><span data-stu-id="e3b3d-134">Look up the commitment</span></span>
1. <span data-ttu-id="e3b3d-135">Cliquez sur Mettre à jour la ligne.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-135">Click Update line.</span></span>
2. <span data-ttu-id="e3b3d-136">Cliquez sur Joint.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-136">Click Attached.</span></span>
    * <span data-ttu-id="e3b3d-137">Ici, vous pouvez obtenir des détails sur le contrat d'achat.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-137">Here you can get details for the purchase agreement.</span></span> <span data-ttu-id="e3b3d-138">Par exemple, vous pouvez afficher le prix et savoir si le prix et la remise sont fixes, ce qui signifie que si vous modifiez le prix ou la remise sur la commande fournisseur sur une valeur différente de celle de l'engagement, le système supprimera le lien de sorte que la ligne de commande fournisseur n'honore pas l'engagement.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-138">For example, you can see the price and whether the price and discount are fixed, which means that if you change price or discount on the purchase order to a different value than on the commitment, the system will remove the link so the purchase order line does not fulfill the commitment.</span></span> <span data-ttu-id="e3b3d-139">Vous pouvez également voir si l'option Le max. est appliqué est sélectionnée, ce qui signifie que la quantité présente sur l'engagement ne peut pas être dépassée en additionnant tous les achats qui honorent l'engagement.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-139">You can also see if the Max is enforced option is selected, which means that the quantity on the commitment cannot be exceeded by summing all of the purchases that fulfill the commitment.</span></span>  
3. <span data-ttu-id="e3b3d-140">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-140">Close the page.</span></span>

## <a name="look-up-the-purchase-agreement"></a><span data-ttu-id="e3b3d-141">Rechercher le contrat d'achat</span><span class="sxs-lookup"><span data-stu-id="e3b3d-141">Look up the purchase agreement</span></span>
1. <span data-ttu-id="e3b3d-142">Cliquez sur Général dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-142">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="e3b3d-143">Cliquez sur Contrats d'achat.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-143">Click Purchase agreement.</span></span>
3. <span data-ttu-id="e3b3d-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-144">Close the page.</span></span>
4. <span data-ttu-id="e3b3d-145">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e3b3d-145">Close the page.</span></span>


