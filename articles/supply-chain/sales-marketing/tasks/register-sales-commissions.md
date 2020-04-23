---
title: Enregistrer les commissions sur les ventes
description: Cette rubrique explique comment les commissions sur les ventes sont calculées et enregistrées.
author: omulvad
manager: tfehr
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5c6dbccc3e2c33c8dfec2373bd21c7bd217a889b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203226"
---
# <a name="register-sales-commissions"></a><span data-ttu-id="c5223-103">Enregistrer les commissions sur les ventes</span><span class="sxs-lookup"><span data-stu-id="c5223-103">Register sales commissions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c5223-104">Cette rubrique explique comment les commissions sur les ventes sont calculées et enregistrées.</span><span class="sxs-lookup"><span data-stu-id="c5223-104">This topic explains how sales commissions are calculated and registered.</span></span> <span data-ttu-id="c5223-105">Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="c5223-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="c5223-106">Avant de lancer ce guide, exécutez le guide appelé « Configurer les règles de commission sur les ventes » pour vous assurer que vous disposez de tout le paramétrage nécessaire au calcul de la commission.</span><span class="sxs-lookup"><span data-stu-id="c5223-106">Before starting this guide, run the guide called "Set up sales commission rules" to make sure that you have all the necessary commission calculation setup.</span></span>

<span data-ttu-id="c5223-107">Prenez note des numéros de client et d'article que vous avez choisis pour le processus de commission et utilisez-les quand il vous sera demandé de créer une commande client dans ce guide.</span><span class="sxs-lookup"><span data-stu-id="c5223-107">Take note of the customer and item numbers that you have chosen for the commission process and use them when asked to create a sales order in this guide.</span></span>


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a><span data-ttu-id="c5223-108">Facturer une commande client qui qualifie un commercial pour une commission</span><span class="sxs-lookup"><span data-stu-id="c5223-108">Invoice a sales order that qualifies a salesperson for a commission</span></span>
1. <span data-ttu-id="c5223-109">Dans le volet de navigation, accédez à **Volet de navigation > Modules > Ventes et marketing > Commandes client > Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="c5223-109">In the navigation pane, go to **Modules > Sales and marketing > Sales orders > All sales orders**.</span></span>
2. <span data-ttu-id="c5223-110">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="c5223-110">Select **New**.</span></span>
3. <span data-ttu-id="c5223-111">Dans le champ **Compte client**, sélectionnez l'enregistrement souhaité dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="c5223-111">In the **Customer account** field, select the desired record from the drop-down menu.</span></span>
4. <span data-ttu-id="c5223-112">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5223-112">Select **OK**.</span></span>
5. <span data-ttu-id="c5223-113">Dans le volet Actions, sélectionnez **Options**.</span><span class="sxs-lookup"><span data-stu-id="c5223-113">On the Action Pane, select **Options**.</span></span>
6. <span data-ttu-id="c5223-114">Sélectionnez **Modifier la vue**.</span><span class="sxs-lookup"><span data-stu-id="c5223-114">Select **Change view**.</span></span>
7. <span data-ttu-id="c5223-115">Sélectionnez **Vue de l'en-tête**.</span><span class="sxs-lookup"><span data-stu-id="c5223-115">Select **Header view**.</span></span>
8. <span data-ttu-id="c5223-116">Développez la section **Paramétrage**.</span><span class="sxs-lookup"><span data-stu-id="c5223-116">Expand the **Setup** section.</span></span>

    - <span data-ttu-id="c5223-117">La valeur dans le champ **Groupe de ventes** représente un groupe avec un ou plusieurs commerciaux lui étant affectés.</span><span class="sxs-lookup"><span data-stu-id="c5223-117">The value in the **Sales group** field represents a group with one or more sales representatives assigned to it.</span></span> <span data-ttu-id="c5223-118">Les personnes du groupe sont celles qui reçoivent les commissions à la facturation de la commande, selon les taux prédéfinis et la répartition.</span><span class="sxs-lookup"><span data-stu-id="c5223-118">The people in the group are the ones who will receive commissions when the order is invoiced, as per predefined rates and distribution.</span></span>   
    - <span data-ttu-id="c5223-119">La valeur est copiée de la fiche client, mais vous pouvez la modifier si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="c5223-119">The value is copied from the Customer card, but you can change it if you wish.</span></span>  
    - <span data-ttu-id="c5223-120">Le groupe de ventes est également copié dans la ligne de commande client.</span><span class="sxs-lookup"><span data-stu-id="c5223-120">The Sales group is also copied to the sales order line.</span></span> <span data-ttu-id="c5223-121">Vous pouvez le modifier de sorte qu'il diffère de celui de l'en-tête et/ou des lignes.</span><span class="sxs-lookup"><span data-stu-id="c5223-121">You can change it so that it can differ from the one in the header and/or between lines.</span></span>  
    - <span data-ttu-id="c5223-122">La valeur dans le champ **Groupe de commissions** représente un groupe que vous avez créé pour un ou plusieurs clients avec l'objectif de suivre les commissions.</span><span class="sxs-lookup"><span data-stu-id="c5223-122">The value in the **Commission group** field represents a group that you have created for one or more customers with the purpose of tracking commissions.</span></span>   
    - <span data-ttu-id="c5223-123">La valeur est copiée de la fiche client, mais vous pouvez la modifier si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="c5223-123">The value is copied from the Customer card, but you can change it if you wish.</span></span>   

9. <span data-ttu-id="c5223-124">Dans le volet Actions, sélectionnez **Options**.</span><span class="sxs-lookup"><span data-stu-id="c5223-124">On the Action Pane, select **Options**.</span></span>
10. <span data-ttu-id="c5223-125">Sélectionnez **Modifier la vue**.</span><span class="sxs-lookup"><span data-stu-id="c5223-125">Select **Change view**.</span></span>
11. <span data-ttu-id="c5223-126">Sélectionnez **Vue de ligne**.</span><span class="sxs-lookup"><span data-stu-id="c5223-126">Select **Line view**.</span></span>
12. <span data-ttu-id="c5223-127">Dans le menu déroulant du champ **Numéro d’article**, sélectionnez l'article à paramétrer pour les commissions.</span><span class="sxs-lookup"><span data-stu-id="c5223-127">In the drop down menu of the **Item number** field, select the item you have set up for commissions.</span></span> 
13. <span data-ttu-id="c5223-128">Entrez un nombre dans le champ **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="c5223-128">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="c5223-129">Prenez note du Montant HT de la ligne.</span><span class="sxs-lookup"><span data-stu-id="c5223-129">Take note of the line's Net amount.</span></span> <span data-ttu-id="c5223-130">Il représente le produit de la vente, qui dans cet exemple sert de base au calcul de la commission.</span><span class="sxs-lookup"><span data-stu-id="c5223-130">It represents the sales revenue, which in this example is the basis for commission calculation.</span></span>  
14. <span data-ttu-id="c5223-131">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c5223-131">Select **Save**.</span></span>
15. <span data-ttu-id="c5223-132">Dans le volet Actions, sélectionnez **Facture**.</span><span class="sxs-lookup"><span data-stu-id="c5223-132">On the Action Pane, select **Invoice**.</span></span>
16. <span data-ttu-id="c5223-133">Sélectionnez **Facture**.</span><span class="sxs-lookup"><span data-stu-id="c5223-133">Select **Invoice**.</span></span>
17. <span data-ttu-id="c5223-134">Développez la section **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="c5223-134">Expand the **Parameters** section.</span></span>
18. <span data-ttu-id="c5223-135">Sélectionnez **Tout** dans le champ **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="c5223-135">In the **Quantity** field, select **All**.</span></span>
19. <span data-ttu-id="c5223-136">Sélectionnez **Oui** dans le champ **Validation**.</span><span class="sxs-lookup"><span data-stu-id="c5223-136">Select **Yes** in the **Posting** field.</span></span>
20. <span data-ttu-id="c5223-137">Sélectionnez **OK**, puis sélectionnez **OK** dans le prochain volet.</span><span class="sxs-lookup"><span data-stu-id="c5223-137">Select **OK**, then select **OK** in the next pane.</span></span> <span data-ttu-id="c5223-138">La validation de la transaction peut prendre une minute environ.</span><span class="sxs-lookup"><span data-stu-id="c5223-138">It may take a minute or so to post the transaction.</span></span> <span data-ttu-id="c5223-139">Laissez le traitement s'achever sans fermer la page.</span><span class="sxs-lookup"><span data-stu-id="c5223-139">Allow the processing to complete and don't close the page.</span></span>  

## <a name="review-the-registered-sales-commissions"></a><span data-ttu-id="c5223-140">Examiner les commissions sur les ventes enregistrées</span><span class="sxs-lookup"><span data-stu-id="c5223-140">Review the registered sales commissions</span></span>
1. <span data-ttu-id="c5223-141">Dans le volet Actions, sélectionnez **Facture**, puis sélectionnez à nouveau **Facture**.</span><span class="sxs-lookup"><span data-stu-id="c5223-141">On the Action Pane, select **Invoice**, then select **Invoice** again.</span></span>
2. <span data-ttu-id="c5223-142">Dans le volet Actions, sélectionnez **Facture**, puis sélectionnez à nouveau **Transactions de commission**.</span><span class="sxs-lookup"><span data-stu-id="c5223-142">On the Action Pane, select **Invoice**, then select **Commission transactions**.</span></span>

    - <span data-ttu-id="c5223-143">L'onglet **Vue d'ensemble** présente des lignes représentant les montants de commission à payer aux commerciaux associés à la commande client facturée.</span><span class="sxs-lookup"><span data-stu-id="c5223-143">The **Overview** tab displays lines representing the commission amounts payable to sales representatives who are associated with the invoiced sales order.</span></span> <span data-ttu-id="c5223-144">Examinons les détails.</span><span class="sxs-lookup"><span data-stu-id="c5223-144">Let's review the details.</span></span>  
    - <span data-ttu-id="c5223-145">Si vous avez utilisé le guide « Configurer les règles de **commission sur les ventes** » pour définir le groupe de commissions de vente, deux commerciaux vont recevoir une commission et celle-ci est divisée équitablement entre eux.</span><span class="sxs-lookup"><span data-stu-id="c5223-145">If you used the "Set up sales commission rules" guide to set up the **Commission sales** group, there are two sales people to receive a sales commissions, and the commission is split equally between them.</span></span>  
    - <span data-ttu-id="c5223-146">Dans cet exemple, le montant total de la commission est calculé comme un pourcentage du produit de la vente (montant HT de la ligne de commande).</span><span class="sxs-lookup"><span data-stu-id="c5223-146">In this example, the total amount of the commission is calculated as a percentage of the sales revenue (the net amount of order line).</span></span>  
3. <span data-ttu-id="c5223-147">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c5223-147">Close the page.</span></span>
4. <span data-ttu-id="c5223-148">Sélectionnez **N° document**.</span><span class="sxs-lookup"><span data-stu-id="c5223-148">Select **Voucher**.</span></span> <span data-ttu-id="c5223-149">Vous pouvez examiner les transactions du N° document pour les montants de commission qui ont été validés dans les comptes prédéfinis de dépense et de commission à payer.</span><span class="sxs-lookup"><span data-stu-id="c5223-149">You can review the voucher transactions for the commission amounts that have been posted to the predefined commission expense and commission payable accounts.</span></span>  

