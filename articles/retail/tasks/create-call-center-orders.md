--- 
title: "Créer des commandes de centre d'appels"
description: "Cette procédure décrit la recherche d'un client, la création d'une commande, la recherche d'un produit et la collecte du paiement auprès du client."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: dcb4216c78899e68ff2c6c85208f3e82074267cc
ms.contentlocale: fr-fr
ms.lasthandoff: 01/19/2018

---
# <a name="create-call-center-orders"></a><span data-ttu-id="08615-103">Créer des commandes de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="08615-103">Create call center orders</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="08615-104">Cette procédure décrit la recherche d'un client, la création d'une commande, la recherche d'un produit et la collecte du paiement auprès du client.</span><span class="sxs-lookup"><span data-stu-id="08615-104">This procedure walks through looking up a customer, creating a new order, searching for a product, and collecting payment from the customer.</span></span> <span data-ttu-id="08615-105">Cette procédure utilise la société fictive USRT et est destinée au commis aux commandes client.</span><span class="sxs-lookup"><span data-stu-id="08615-105">This procedure uses demo data company USRT and is intended for the Sales Order Clerk.</span></span> <span data-ttu-id="08615-106">Conditions préalables : l'utilisateur exécutant la procédure est configuré en tant qu'utilisateur du centre d'appels et le catalogue semi-annuel de Fabrikam est publié avec au moins un code source.</span><span class="sxs-lookup"><span data-stu-id="08615-106">Pre-requisites:  The user who completes the procedure is set up as a Call center user and the Fabrikam Semi-Annual Catalog is published with at least one Source code on it.</span></span>

1. <span data-ttu-id="08615-107">Accédez à Commerce et vente au détail > Clients > Service client.</span><span class="sxs-lookup"><span data-stu-id="08615-107">Go to Retail and commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="08615-108">Dans le champ Texte recherché, saisissez les critères de recherche du client.</span><span class="sxs-lookup"><span data-stu-id="08615-108">In the SearchText field, enter the search criteria to look up the customer.</span></span>
    * <span data-ttu-id="08615-109">Pour cet exemple de procédure, saisissez « Karen », puis appuyez sur l'onglet.</span><span class="sxs-lookup"><span data-stu-id="08615-109">For this example procedure type in 'karen' and press tab.</span></span>  
3. <span data-ttu-id="08615-110">Cliquez sur Rechercher.</span><span class="sxs-lookup"><span data-stu-id="08615-110">Click Search.</span></span>
    * <span data-ttu-id="08615-111">Comme il n'existe qu'un seul client nommé Karen dans les données de démonstration, il est automatiquement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="08615-111">Since there is only one customer named Karen in demo data they will be automatically selected.</span></span>  
4. <span data-ttu-id="08615-112">Cliquez sur Nouvelle commande client.</span><span class="sxs-lookup"><span data-stu-id="08615-112">Click New sales order.</span></span>
5. <span data-ttu-id="08615-113">Développez ou réduisez la section En-tête de commande client.</span><span class="sxs-lookup"><span data-stu-id="08615-113">Expand or collapse the Sales order header section.</span></span>
6. <span data-ttu-id="08615-114">Sélectionnez le code source du catalogue.</span><span class="sxs-lookup"><span data-stu-id="08615-114">Select the source code for the catalog.</span></span>
    * <span data-ttu-id="08615-115">Si aucun code source n'est actif, vous pouvez fermer le champ Source et ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="08615-115">If there are no active Source codes you can close the Source field and skip this step.</span></span>  
7. <span data-ttu-id="08615-116">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="08615-116">Click Add line.</span></span>
8. <span data-ttu-id="08615-117">Dans le champ Numéro d'article, saisissez le terme de recherche de l'article.</span><span class="sxs-lookup"><span data-stu-id="08615-117">In the Item number field, enter the item search term.</span></span>
    * <span data-ttu-id="08615-118">Pour cet exemple de procédure, entrez le numéro d'article partiel « 8111 » et appuyez sur l'onglet. Cela fera apparaître la fenêtre de recherche d'élément.</span><span class="sxs-lookup"><span data-stu-id="08615-118">For this sample procedure enter a partial item number of '8111' and press tab. This will pop up the item search window.</span></span>  
9. <span data-ttu-id="08615-119">Sélectionner le produit à ajouter à la commande client</span><span class="sxs-lookup"><span data-stu-id="08615-119">Select the product to add to the sales order</span></span>
10. <span data-ttu-id="08615-120">Saisissez la quantité vendue.</span><span class="sxs-lookup"><span data-stu-id="08615-120">Enter the sales quantity.</span></span>
11. <span data-ttu-id="08615-121">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="08615-121">Click Create.</span></span>
12. <span data-ttu-id="08615-122">Cliquez sur Terminer pour capturer le paiement du client.</span><span class="sxs-lookup"><span data-stu-id="08615-122">Click Complete to capture the customer payment.</span></span>
13. <span data-ttu-id="08615-123">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="08615-123">Click Add.</span></span>
    * <span data-ttu-id="08615-124">Le lien Ajouter figure dans l'onglet Paiements. Développez l'onglet Paiements s'il est réduit.</span><span class="sxs-lookup"><span data-stu-id="08615-124">The Add link is in the Payments tab. Expand the Payments tab if it is collapsed.</span></span>  
14. <span data-ttu-id="08615-125">Sélectionnez le mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="08615-125">Select the payment method.</span></span>
    * <span data-ttu-id="08615-126">Pour cette procédure, sélectionnez le mode de paiement au comptant.</span><span class="sxs-lookup"><span data-stu-id="08615-126">For this procedure, select the cash payment method.</span></span>  
15. <span data-ttu-id="08615-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="08615-127">Close the page.</span></span>
16. <span data-ttu-id="08615-128">Entrez le montant.</span><span class="sxs-lookup"><span data-stu-id="08615-128">Enter the amount.</span></span>
    * <span data-ttu-id="08615-129">Pour cette procédure, saisissez un montant égal au solde de la commande qui s'affiche dans la page Résumé de la commande client à gauche du champ de montant.</span><span class="sxs-lookup"><span data-stu-id="08615-129">For this procedure enter an amount equal to the order balance which can be seen in the Sales order summary page to the left of the amount field.</span></span> <span data-ttu-id="08615-130">Vous pourrez ainsi terminer la commande comme étant intégralement payée.</span><span class="sxs-lookup"><span data-stu-id="08615-130">This will allow you to complete the order as fully paid.</span></span>  
17. <span data-ttu-id="08615-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="08615-131">Click OK.</span></span>
18. <span data-ttu-id="08615-132">Cliquez sur Soumettre.</span><span class="sxs-lookup"><span data-stu-id="08615-132">Click Submit.</span></span>


