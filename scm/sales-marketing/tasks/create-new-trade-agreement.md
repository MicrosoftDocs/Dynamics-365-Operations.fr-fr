--- 
title: "Créer un accord commercial"
description: "Cette procédure vous indique comment créer un accord commercial dans lequel vous enregistrer un prix de vente de produit dont vous avez convenu avec un client spécifique."
author: omulvad
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1eb7a945243387f85ec5f38cc3b969d8d030ff25
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-new-trade-agreement"></a><span data-ttu-id="ef80d-103">Créer un accord commercial</span><span class="sxs-lookup"><span data-stu-id="ef80d-103">Create a new trade agreement</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ef80d-104">Cette procédure vous indique comment créer un accord commercial dans lequel vous enregistrer un prix de vente de produit dont vous avez convenu avec un client spécifique.</span><span class="sxs-lookup"><span data-stu-id="ef80d-104">This procedure shows you how to create a trade agreement where you register a new product sales price that you've agreed with a specific customer.</span></span> <span data-ttu-id="ef80d-105">Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="ef80d-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="ef80d-106">Si vous utilisez vos propres données, vous devez vous assurer qu'un nom de Journal d'accords commerciaux existe dans lequel la relation par défaut est définie sur « Prix (ventes) » avant de lancer ce guide.</span><span class="sxs-lookup"><span data-stu-id="ef80d-106">If you’re using your own data, before you start this guide you need to make sure that a Trade agreement journal name exists where the Default relation is set to “Price (sales)”.</span></span>


## <a name="create-and-post-a-new-trade-agreement-journal"></a><span data-ttu-id="ef80d-107">Créer et valider un journal d'accords commerciaux</span><span class="sxs-lookup"><span data-stu-id="ef80d-107">Create and post a new trade agreement journal</span></span>
1. <span data-ttu-id="ef80d-108">Accédez à Ventes et marketing > Prix et remises > Journaux des accords commerciaux.</span><span class="sxs-lookup"><span data-stu-id="ef80d-108">Go to Sales and marketing > Prices and discounts > Trade agreement journals.</span></span>
2. <span data-ttu-id="ef80d-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="ef80d-109">Click New.</span></span>
3. <span data-ttu-id="ef80d-110">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ef80d-110">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="ef80d-111">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="ef80d-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="ef80d-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ef80d-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="ef80d-113">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="ef80d-113">Click Lines.</span></span>
7. <span data-ttu-id="ef80d-114">Dans le champ Code de compte, sélectionnez « Table ».</span><span class="sxs-lookup"><span data-stu-id="ef80d-114">In the Account code field, select 'Table'.</span></span>
    * <span data-ttu-id="ef80d-115">Dans cet exemple, vous mettez à jour le prix pour un client spécifique, ce qui signifie que vous devez choisir Table.</span><span class="sxs-lookup"><span data-stu-id="ef80d-115">In this example, you're updating the price for a specific customer, which means you need to choose Table.</span></span> <span data-ttu-id="ef80d-116">Si vous mettez les prix du produit, sélectionnez Tout, afin que le nouveau prix soit valide pour tous les clients.</span><span class="sxs-lookup"><span data-stu-id="ef80d-116">If you were updating the product's list price, you would select All, so that the new price is valid for all customers.</span></span> <span data-ttu-id="ef80d-117">Si vous différenciez des prix entre différents segments de clients, sélectionnez Groupe.</span><span class="sxs-lookup"><span data-stu-id="ef80d-117">If you were differentiating prices among different customer segments, then you would select Group.</span></span> <span data-ttu-id="ef80d-118">Pour sélectionner Groupe, vous devez avoir configuré des Groupes de prix client.</span><span class="sxs-lookup"><span data-stu-id="ef80d-118">To select Group, you must have set up Customer price groups.</span></span>  
8. <span data-ttu-id="ef80d-119">Dans le champ Sélection du compte, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ef80d-119">In the Account selection field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="ef80d-120">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="ef80d-120">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="ef80d-121">Dans le champ Code d'article, sélectionnez « Table ».</span><span class="sxs-lookup"><span data-stu-id="ef80d-121">In the Item code field, select 'Table'.</span></span>
    * <span data-ttu-id="ef80d-122">Lorsque vous entrez un accord commercial de type « Prix (ventes) », vous devez sélectionner uniquement « Table » dans le champ Code article.</span><span class="sxs-lookup"><span data-stu-id="ef80d-122">When you are entering a trade agreement of type 'Price (sales)', you must only select 'Table' in the Item code field.</span></span> <span data-ttu-id="ef80d-123">Cela est dû au fait qu'un prix est une valeur absolue et qu'il ne peut pas être identique pour tous les produits ou pour un groupe de produits.</span><span class="sxs-lookup"><span data-stu-id="ef80d-123">This is because a price is an absolute value and cannot be same for all products or a group of products.</span></span>  
11. <span data-ttu-id="ef80d-124">Dans le champ Relation d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ef80d-124">In the Item relation field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="ef80d-125">Dans la liste, sélectionnez le produit que vous souhaitez inclure dans l'accord.</span><span class="sxs-lookup"><span data-stu-id="ef80d-125">In the list, select the product you want to include in the agreement.</span></span>
    * <span data-ttu-id="ef80d-126">Notez le produit que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ef80d-126">Make a note of which product you've selected.</span></span>  
13. <span data-ttu-id="ef80d-127">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ef80d-127">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="ef80d-128">Dans le champ De, entrez une quantité minimale.</span><span class="sxs-lookup"><span data-stu-id="ef80d-128">In the From field, enter a minimum quantity.</span></span>
    * <span data-ttu-id="ef80d-129">Si le client doit commander une quantité minimale avant de pouvoir bénéficier du nouveau prix, vous devez spécifier la quantité ici.</span><span class="sxs-lookup"><span data-stu-id="ef80d-129">If the customer has to order a minimum quantity  before they can qualify for the new price, then you need to specify that quantity here.</span></span>  
    * <span data-ttu-id="ef80d-130">Entrez une valeur dans le champ À pour spécifier la quantité maximale au-dessus de laquelle le prix de l'accord n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="ef80d-130">Enter a value in the To field to specify the maximum quantity above which the agreement's price will not be valid.</span></span> <span data-ttu-id="ef80d-131">Si vous proposez des prix et des remises par quantité, spécifiez chaque parenthèse de quantité comme paire de quantité minimale et maximale dans les champs « De » et « À », respectivement.</span><span class="sxs-lookup"><span data-stu-id="ef80d-131">If you offer prices and discounts based on multiple quantity breaks, then specify each quantity bracket as a pair of minimum and maximum quantity in the 'From' and 'To' fields respectively.</span></span>  
15. <span data-ttu-id="ef80d-132">Dans le champ Montant en devise, entrez un prix.</span><span class="sxs-lookup"><span data-stu-id="ef80d-132">In the Amount in currency field, enter a price.</span></span>
16. <span data-ttu-id="ef80d-133">Dans le champ Date de début, entrez une date à partir de laquelle cet accord est valide.</span><span class="sxs-lookup"><span data-stu-id="ef80d-133">In the From date field, enter a date from which this agreement will be valid.</span></span>
17. <span data-ttu-id="ef80d-134">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ef80d-134">Click Save.</span></span>
18. <span data-ttu-id="ef80d-135">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="ef80d-135">Click Validate.</span></span>
19. <span data-ttu-id="ef80d-136">Cliquez sur Valider les lignes sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="ef80d-136">Click Validate selected lines.</span></span>
20. <span data-ttu-id="ef80d-137">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ef80d-137">Click OK.</span></span>
21. <span data-ttu-id="ef80d-138">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="ef80d-138">Click Post.</span></span>
22. <span data-ttu-id="ef80d-139">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ef80d-139">Click OK.</span></span>

## <a name="view-trade-agreements-for-a-product"></a><span data-ttu-id="ef80d-140">Afficher les accords commerciaux d'un produit</span><span class="sxs-lookup"><span data-stu-id="ef80d-140">View trade agreements for a product</span></span>
1. <span data-ttu-id="ef80d-141">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="ef80d-141">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="ef80d-142">Dans la liste, localisez et sélectionnez le produit dont vous venez de mettre à jour le prix.</span><span class="sxs-lookup"><span data-stu-id="ef80d-142">In the list, find and select the product whose price you have just updated.</span></span>
3. <span data-ttu-id="ef80d-143">Cliquez sur Vendre dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="ef80d-143">On the Action Pane, click Sell.</span></span>
4. <span data-ttu-id="ef80d-144">Cliquez sur Afficher les accords commerciaux.</span><span class="sxs-lookup"><span data-stu-id="ef80d-144">Click View trade agreements.</span></span>
    * <span data-ttu-id="ef80d-145">Examinez les détails de l'accord commercial de prix que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="ef80d-145">Review the details of the price trade agreement you have just created.</span></span>    
5. <span data-ttu-id="ef80d-146">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ef80d-146">Close the page.</span></span>


