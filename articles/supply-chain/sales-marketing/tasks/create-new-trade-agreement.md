---
title: Créer un accord commercial
description: Cette procédure vous indique comment créer un accord commercial dans lequel vous enregistrer un prix de vente de produit dont vous avez convenu avec un client spécifique.
author: omulvad
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 58ad2a5571138f1a82b021af63cdae9d567b92d8
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835583"
---
# <a name="create-a-new-trade-agreement"></a><span data-ttu-id="e4ad5-103">Créer un accord commercial</span><span class="sxs-lookup"><span data-stu-id="e4ad5-103">Create a new trade agreement</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e4ad5-104">Cette procédure vous indique comment créer un accord commercial dans lequel vous enregistrer un prix de vente de produit dont vous avez convenu avec un client spécifique.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-104">This procedure shows you how to create a trade agreement where you register a new product sales price that you've agreed with a specific customer.</span></span> <span data-ttu-id="e4ad5-105">Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="e4ad5-106">Si vous utilisez vos propres données, vous devez vous assurer qu'un nom de Journal d'accords commerciaux existe dans lequel la relation par défaut est définie sur « Prix (ventes) » avant de lancer ce guide.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-106">If you’re using your own data, before you start this guide you need to make sure that a Trade agreement journal name exists where the Default relation is set to “Price (sales)”.</span></span>


## <a name="create-and-post-a-new-trade-agreement-journal"></a><span data-ttu-id="e4ad5-107">Créer et valider un journal d'accords commerciaux</span><span class="sxs-lookup"><span data-stu-id="e4ad5-107">Create and post a new trade agreement journal</span></span>
1. <span data-ttu-id="e4ad5-108">Accédez à **Volet de navigation > Modules > Ventes et marketing > Prix et remises > Journaux des accords commerciaux**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-108">Go to **Navigation pane > Modules > Sales and marketing > Prices and discounts > Trade agreement journals**.</span></span>
2. <span data-ttu-id="e4ad5-109">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-109">Click **New**.</span></span>
3. <span data-ttu-id="e4ad5-110">Dans le champ **Nom**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-110">In the **Name** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e4ad5-111">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="e4ad5-112">Dans le volet **Action**, cliquez sur **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-112">On **Action pane**, click **Lines**.</span></span>
6. <span data-ttu-id="e4ad5-113">Dans le champ **Code de compte**, sélectionnez « Table ».</span><span class="sxs-lookup"><span data-stu-id="e4ad5-113">In the **Account code** field, select 'Table'.</span></span>
    
    <span data-ttu-id="e4ad5-114">Dans cet exemple, vous mettez à jour le prix pour un client spécifique, ce qui signifie que vous devez choisir Table.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-114">In this example, you're updating the price for a specific customer, which means you need to choose Table.</span></span> <span data-ttu-id="e4ad5-115">Si vous mettez à jour les prix du produit, sélectionnez « Tout », afin que le nouveau prix soit valide pour tous les clients.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-115">If you were updating the product's list price, you would select 'All', so that the new price is valid for all customers.</span></span> <span data-ttu-id="e4ad5-116">Si vous différenciez des prix entre différents segments de clients, sélectionnez Groupe.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-116">If you were differentiating prices among different customer segments, then you would select Group.</span></span> <span data-ttu-id="e4ad5-117">Pour sélectionner Groupe, vous devez avoir configuré des Groupes de prix client.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-117">To select Group, you must have set up Customer price groups.</span></span>  

7. <span data-ttu-id="e4ad5-118">Dans le champ **Sélection du compte**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-118">In the **Account selection** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="e4ad5-119">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="e4ad5-120">Dans le champ **Code d'article**, sélectionnez « Table ».</span><span class="sxs-lookup"><span data-stu-id="e4ad5-120">In the **Item code** field, select 'Table'.</span></span>
    
    <span data-ttu-id="e4ad5-121">Lorsque vous entrez un accord commercial de type « Prix (ventes) », vous devez sélectionner uniquement « Table » dans le champ **Code article**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-121">When you are entering a trade agreement of type 'Price (sales)', you must only select 'Table' in the **Item code** field.</span></span> <span data-ttu-id="e4ad5-122">Cela est dû au fait qu'un prix est une valeur absolue et qu'il ne peut pas être identique pour tous les produits ou pour un groupe de produits.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-122">This is because a price is an absolute value and cannot be same for all products or a group of products.</span></span>
    
10. <span data-ttu-id="e4ad5-123">Dans le champ **Relation d'article**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-123">In the **Item relation** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="e4ad5-124">Dans la liste, sélectionnez le produit que vous souhaitez inclure dans l'accord.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-124">In the list, select the product you want to include in the agreement.</span></span> <span data-ttu-id="e4ad5-125">Notez le produit que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-125">Make a note of which product you've selected.</span></span>  
12. <span data-ttu-id="e4ad5-126">Dans le champ **De**, entrez une quantité minimale.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-126">In the **From** field, enter a minimum quantity.</span></span>
    - <span data-ttu-id="e4ad5-127">Si le client doit commander une quantité minimale pour bénéficier du nouveau prix, vous devez spécifier la quantité ici.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-127">If the customer has to order a minimum quantity before they can qualify for the new price, then you need to specify that quantity here.</span></span>  
    - <span data-ttu-id="e4ad5-128">Entrez une valeur dans le champ **À** pour spécifier la quantité maximale au-dessus de laquelle le prix de l'accord n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-128">Enter a value in the **To** field to specify the maximum quantity above which the agreement's price will not be valid.</span></span> <span data-ttu-id="e4ad5-129">Si vous proposez des prix et des remises par quantité, spécifiez chaque seuil de quantité comme paire de quantité minimale et maximale dans les champs **De** et **À**, respectivement.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-129">If you offer prices and discounts based on multiple quantity breaks, then specify each quantity bracket as a pair of minimum and maximum quantity in the **From** and **To** fields respectively.</span></span>
13. <span data-ttu-id="e4ad5-130">Dans le champ **Montant en devise**, entrez un prix.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-130">In the **Amount in currency field**, enter a price.</span></span>
14. <span data-ttu-id="e4ad5-131">Dans la section **Détails**, dans le champ **Date de début**, entrez une date à partir de laquelle cet accord est valide.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-131">Under the **Details** section, in the **From date** field, enter a date from which this agreement will be valid.</span></span>
15. <span data-ttu-id="e4ad5-132">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-132">Click **Save**.</span></span>
16. <span data-ttu-id="e4ad5-133">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-133">Click **Validate**.</span></span>
17. <span data-ttu-id="e4ad5-134">Cliquez sur **Valider les lignes sélectionnées**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-134">Click **Validate selected lines**.</span></span>
18. <span data-ttu-id="e4ad5-135">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-135">Click **OK**.</span></span>
19. <span data-ttu-id="e4ad5-136">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-136">Click **Post**.</span></span>
20. <span data-ttu-id="e4ad5-137">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-137">Click **OK**.</span></span>

## <a name="view-trade-agreements-for-a-product"></a><span data-ttu-id="e4ad5-138">Afficher les accords commerciaux d'un produit</span><span class="sxs-lookup"><span data-stu-id="e4ad5-138">View trade agreements for a product</span></span>
1. <span data-ttu-id="e4ad5-139">Accédez à **Volet de navigation > Modules > Gestion d'informations sur les produits > Produits > Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-139">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="e4ad5-140">Dans la liste, localisez et sélectionnez le produit dont vous venez de mettre à jour le prix.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-140">In the list, find and select the product whose price you have just updated.</span></span>
3. <span data-ttu-id="e4ad5-141">Dans le volet **Action**, cliquez sur **Vendre**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-141">On the **Action Pane**, click **Sell**.</span></span>
4. <span data-ttu-id="e4ad5-142">Cliquez sur **Afficher les accords commerciaux**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-142">Click **View trade agreements**.</span></span>
    
    <span data-ttu-id="e4ad5-143">Examinez les détails de l'accord commercial de prix que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-143">Review the details of the price trade agreement you have just created.</span></span>    

5. <span data-ttu-id="e4ad5-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-144">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e4ad5-145">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e4ad5-145">Additional resources</span></span>
### <a name="community-blogs"></a><span data-ttu-id="e4ad5-146">Blogs de la communauté</span><span class="sxs-lookup"><span data-stu-id="e4ad5-146">Community blogs</span></span>
- [<span data-ttu-id="e4ad5-147">Prix de vente dans Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e4ad5-147">Sales prices in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)
