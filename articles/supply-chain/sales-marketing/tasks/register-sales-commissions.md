---
title: Enregistrer les commissions sur les ventes
description: Cette procédure vous montre comment les commissions sur les ventes sont calculées et enregistrées.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4c0e63923d0cb9a4a2c2bed87cfb72edfb0d2741
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1833904"
---
# <a name="register-sales-commissions"></a><span data-ttu-id="80e88-103">Enregistrer les commissions sur les ventes</span><span class="sxs-lookup"><span data-stu-id="80e88-103">Register sales commissions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="80e88-104">Cette procédure vous montre comment les commissions sur les ventes sont calculées et enregistrées.</span><span class="sxs-lookup"><span data-stu-id="80e88-104">This procedure shows you how sales commissions are calculated and registered.</span></span> <span data-ttu-id="80e88-105">Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="80e88-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="80e88-106">Avant de lancer ce guide, exécutez le guide appelé « Configurer les règles de commission sur les ventes » pour vous assurer que vous disposez de tout le paramétrage nécessaire au calcul de la commission.</span><span class="sxs-lookup"><span data-stu-id="80e88-106">Before starting this guide, run the guide called "Set up sales commission rules" to make sure that you have all the necessary commission calculation setup.</span></span>

<span data-ttu-id="80e88-107">Prenez note des numéros de client et d'article que vous avez choisis pour le processus de commission et utilisez-les quand il vous sera demandé de créer une commande client dans ce guide.</span><span class="sxs-lookup"><span data-stu-id="80e88-107">Take note of the customer and item numbers that you have chosen for the commission process and use them when asked to create a sales order in this guide.</span></span>


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a><span data-ttu-id="80e88-108">Facturer une commande client qui qualifie un commercial pour une commission</span><span class="sxs-lookup"><span data-stu-id="80e88-108">Invoice a sales order that qualifies a salesperson for a commission</span></span>
1. <span data-ttu-id="80e88-109">Allez dans Ventes et marketing > Commandes client > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="80e88-109">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="80e88-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="80e88-110">Click New.</span></span>
3. <span data-ttu-id="80e88-111">Dans le champ Compte client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="80e88-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="80e88-112">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="80e88-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="80e88-113">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="80e88-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="80e88-114">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="80e88-114">Click OK.</span></span>
7. <span data-ttu-id="80e88-115">Dans le volet Actions, cliquez sur Options.</span><span class="sxs-lookup"><span data-stu-id="80e88-115">On the Action Pane, click Options.</span></span>
8. <span data-ttu-id="80e88-116">Cliquez sur Changer de vue.</span><span class="sxs-lookup"><span data-stu-id="80e88-116">Click Change view.</span></span>
9. <span data-ttu-id="80e88-117">Cliquez sur Vue de l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="80e88-117">Click Header view.</span></span>
10. <span data-ttu-id="80e88-118">Développez la section Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="80e88-118">Expand the Setup section.</span></span>
    * <span data-ttu-id="80e88-119">La valeur dans le champ Groupe de ventes représente un groupe avec un ou plusieurs commerciaux lui étant affectés.</span><span class="sxs-lookup"><span data-stu-id="80e88-119">The value in the Sales group field represents a group with one or more sales representatives assigned to it.</span></span> <span data-ttu-id="80e88-120">Les personnes du groupe sont celles qui reçoivent les commissions à la facturation de la commande, selon les taux prédéfinis et la répartition.</span><span class="sxs-lookup"><span data-stu-id="80e88-120">The people in the group are the ones who will receive commissions when the order is invoiced, as per predefined rates and distribution.</span></span>   <span data-ttu-id="80e88-121">La valeur est copiée de la fiche client, mais vous pouvez la modifier si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="80e88-121">The value is copied from the Customer card, but you can change it if you wish.</span></span>  <span data-ttu-id="80e88-122">Le groupe de ventes est également copié dans la ligne de commande client.</span><span class="sxs-lookup"><span data-stu-id="80e88-122">The Sales group is also copied to the sales order line.</span></span> <span data-ttu-id="80e88-123">Vous pouvez le modifier de sorte qu'il diffère de celui de l'en-tête et/ou des lignes.</span><span class="sxs-lookup"><span data-stu-id="80e88-123">You can change it so that it can differ from the one in the header and/or between lines.</span></span>  
    * <span data-ttu-id="80e88-124">La valeur dans le champ Groupe de commissions représente un groupe que vous avez créé pour un ou plusieurs clients avec l'objectif de suivre les commissions.</span><span class="sxs-lookup"><span data-stu-id="80e88-124">The value in the Commission group field represents a group that you have created for one or more customers with the purpose of tracking commissions.</span></span>   <span data-ttu-id="80e88-125">La valeur est copiée de la fiche client, mais vous pouvez la modifier si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="80e88-125">The value is copied from the Customer card, but you can change it if you wish.</span></span>   
11. <span data-ttu-id="80e88-126">Dans le volet Actions, cliquez sur Options.</span><span class="sxs-lookup"><span data-stu-id="80e88-126">On the Action Pane, click Options.</span></span>
12. <span data-ttu-id="80e88-127">Cliquez sur Changer de vue.</span><span class="sxs-lookup"><span data-stu-id="80e88-127">Click Change view.</span></span>
13. <span data-ttu-id="80e88-128">Cliquez sur Affichage des lignes.</span><span class="sxs-lookup"><span data-stu-id="80e88-128">Click Line view.</span></span>
14. <span data-ttu-id="80e88-129">Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="80e88-129">In the Item number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="80e88-130">Dans la liste, sélectionnez l'article que vous avez paramétré pour des commissions.</span><span class="sxs-lookup"><span data-stu-id="80e88-130">In the list, select the item you have set up for commissions.</span></span> 
16. <span data-ttu-id="80e88-131">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="80e88-131">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="80e88-132">Prenez note du Montant HT de la ligne.</span><span class="sxs-lookup"><span data-stu-id="80e88-132">Take note of the line's Net amount.</span></span> <span data-ttu-id="80e88-133">Il représente le produit de la vente, qui dans cet exemple sert de base au calcul de la commission.</span><span class="sxs-lookup"><span data-stu-id="80e88-133">It represents the sales revenue, which in this example is the basis for commission calculation.</span></span>  
17. <span data-ttu-id="80e88-134">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="80e88-134">Click Save.</span></span>
18. <span data-ttu-id="80e88-135">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="80e88-135">On the Action Pane, click Invoice.</span></span>
19. <span data-ttu-id="80e88-136">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="80e88-136">Click Invoice.</span></span>
20. <span data-ttu-id="80e88-137">Développez la section Paramètres.</span><span class="sxs-lookup"><span data-stu-id="80e88-137">Expand the Parameters section.</span></span>
21. <span data-ttu-id="80e88-138">Sélectionnez « Tout » dans le champ Quantité.</span><span class="sxs-lookup"><span data-stu-id="80e88-138">In the Quantity field, select 'All'.</span></span>
22. <span data-ttu-id="80e88-139">Sélectionnez Oui dans le champ Validation.</span><span class="sxs-lookup"><span data-stu-id="80e88-139">Select Yes in the Posting field.</span></span>
23. <span data-ttu-id="80e88-140">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="80e88-140">Click OK.</span></span>
24. <span data-ttu-id="80e88-141">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="80e88-141">Click OK.</span></span>
    * <span data-ttu-id="80e88-142">La validation de la transaction peut prendre une minute environ.</span><span class="sxs-lookup"><span data-stu-id="80e88-142">It may take a minute or so to post the transaction.</span></span> <span data-ttu-id="80e88-143">Laissez le traitement s'achever sans fermer la page.</span><span class="sxs-lookup"><span data-stu-id="80e88-143">Allow the processing to complete and don’t close the page.</span></span>  

## <a name="review-the-registered-sales-commissions"></a><span data-ttu-id="80e88-144">Examiner les commissions sur les ventes enregistrées</span><span class="sxs-lookup"><span data-stu-id="80e88-144">Review the registered sales commissions</span></span>
1. <span data-ttu-id="80e88-145">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="80e88-145">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="80e88-146">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="80e88-146">Click Invoice.</span></span>
3. <span data-ttu-id="80e88-147">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="80e88-147">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="80e88-148">Cliquez sur Transactions de commission.</span><span class="sxs-lookup"><span data-stu-id="80e88-148">Click Commission transactions.</span></span>
    * <span data-ttu-id="80e88-149">L'onglet Vue d'ensemble présente des lignes représentant les montants de commission à payer aux commerciaux associés à la commande client facturée.</span><span class="sxs-lookup"><span data-stu-id="80e88-149">The Overview tab displays lines representing the commission amounts payable to sales representatives who are associated with the invoiced sales order.</span></span> <span data-ttu-id="80e88-150">Examinons les détails.</span><span class="sxs-lookup"><span data-stu-id="80e88-150">Let's review the details.</span></span>     
    * <span data-ttu-id="80e88-151">Si vous avez utilisé le guide « Configurer les règles de commission sur les ventes » pour définir le groupe de commissions de vente, deux commerciaux vont recevoir une commission et celle-ci est divisée équitablement entre eux.</span><span class="sxs-lookup"><span data-stu-id="80e88-151">If you used the "Set up sales commission rules" guide to set up the Commission sales group, there are two sales people to receive a sales commissions, and the commission is split equally between them.</span></span>  
    * <span data-ttu-id="80e88-152">Dans cet exemple, le montant total de la commission est calculé comme un pourcentage du produit de la vente (montant HT de la ligne de commande).</span><span class="sxs-lookup"><span data-stu-id="80e88-152">In this example, the total amount of the commission is calculated as a percentage of the sales revenue (the net amount of order line).</span></span>   
5. <span data-ttu-id="80e88-153">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="80e88-153">Close the page.</span></span>
6. <span data-ttu-id="80e88-154">Cliquez Document.</span><span class="sxs-lookup"><span data-stu-id="80e88-154">Click Voucher.</span></span>
    * <span data-ttu-id="80e88-155">Vous pouvez examiner les transactions du N° document pour les montants de commission qui ont été validés dans les comptes prédéfinis de dépense et de commission à payer.</span><span class="sxs-lookup"><span data-stu-id="80e88-155">You can review the voucher transactions for the commission amounts that have been posted to the predefined commission expense and commission payable accounts.</span></span>  

