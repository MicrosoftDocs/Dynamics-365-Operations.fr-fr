---
title: Créer des commandes de centre d’appels
description: Cette procédure décrit la recherche d’un client, la création d’une commande, la recherche d’un produit et la collecte du paiement auprès du client.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d8dc9e19ecd6b835569ba80563bce33134895cb
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791653"
---
# <a name="create-call-center-orders"></a><span data-ttu-id="fa85e-103">Créer des commandes de centre d’appels</span><span class="sxs-lookup"><span data-stu-id="fa85e-103">Create call center orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fa85e-104">Cette procédure décrit la recherche d’un client, la création d’une commande, la recherche d’un produit et la collecte du paiement auprès du client.</span><span class="sxs-lookup"><span data-stu-id="fa85e-104">This procedure walks through looking up a customer, creating a new order, searching for a product, and collecting payment from the customer.</span></span> <span data-ttu-id="fa85e-105">Cette procédure utilise la société fictive USRT et est destinée au commis aux commandes client.</span><span class="sxs-lookup"><span data-stu-id="fa85e-105">This procedure uses demo data company USRT and is intended for the Sales Order Clerk.</span></span> <span data-ttu-id="fa85e-106">Conditions préalables : l’utilisateur exécutant la procédure est configuré en tant qu’utilisateur du centre d’appels et le catalogue semi-annuel de Fabrikam est publié avec au moins un code source.</span><span class="sxs-lookup"><span data-stu-id="fa85e-106">Pre-requisites:  The user who completes the procedure is set up as a Call center user and the Fabrikam Semi-Annual Catalog is published with at least one Source code on it.</span></span>

1. <span data-ttu-id="fa85e-107">Accédez à **Retail et Commerce \> Clients \> Service client**.</span><span class="sxs-lookup"><span data-stu-id="fa85e-107">Go to **Retail and Commerce \> Customers \> Customer service**.</span></span>
2. <span data-ttu-id="fa85e-108">Dans le champ **SearchText**, saisissez les critères de recherche du client.</span><span class="sxs-lookup"><span data-stu-id="fa85e-108">For **SearchText**, enter the search criteria to look up the customer.</span></span>
    * <span data-ttu-id="fa85e-109">Pour cet exemple de procédure, saisissez « Karen », puis sélectionnez **Onglet**.</span><span class="sxs-lookup"><span data-stu-id="fa85e-109">For this example procedure, enter "Karen" and select **Tab**.</span></span>  
3. <span data-ttu-id="fa85e-110">Sélectionnez Rechercher.</span><span class="sxs-lookup"><span data-stu-id="fa85e-110">Select Search.</span></span>
    * <span data-ttu-id="fa85e-111">Comme il n’existe qu’un seul client nommé "Karen" dans les données de démonstration, le résultat est automatiquement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="fa85e-111">Since there is only one customer named "Karen" in demo data, the result will be automatically selected.</span></span>  
4. <span data-ttu-id="fa85e-112">Sélectionnez **Nouvelle commande client**.</span><span class="sxs-lookup"><span data-stu-id="fa85e-112">Select **New sales order**.</span></span>
5. <span data-ttu-id="fa85e-113">Développez ou réduisez la section d’en-tête de **Commande client**.</span><span class="sxs-lookup"><span data-stu-id="fa85e-113">Expand or collapse the **Sales order** header section.</span></span>
6. <span data-ttu-id="fa85e-114">Sélectionnez le code source du catalogue.</span><span class="sxs-lookup"><span data-stu-id="fa85e-114">Select the source code for the catalog.</span></span>
    * <span data-ttu-id="fa85e-115">Si aucun code source n’est actif, vous pouvez ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="fa85e-115">If there are no active source codes you can skip this step.</span></span>  
7. <span data-ttu-id="fa85e-116">Sélectionnez **Ajouter la ligne**.</span><span class="sxs-lookup"><span data-stu-id="fa85e-116">Select **Add line**.</span></span>
8. <span data-ttu-id="fa85e-117">Pour **Numéro d’article**, saisissez le terme de recherche de l’article.</span><span class="sxs-lookup"><span data-stu-id="fa85e-117">For **Item number**, enter the item search term.</span></span>
    * <span data-ttu-id="fa85e-118">Pour cet exemple de procédure, entrez le numéro d’article partiel « 8111 » et appuyez sur l’onglet. Cette action fera apparaître la fenêtre de recherche d’élément.</span><span class="sxs-lookup"><span data-stu-id="fa85e-118">For this sample procedure, enter a partial item number of '8111' and press tab. This action will bring up the item search window.</span></span>  
9. <span data-ttu-id="fa85e-119">Sélectionnez le produit à ajouter à la commande client.</span><span class="sxs-lookup"><span data-stu-id="fa85e-119">Select the product to add to the sales order.</span></span>
10. <span data-ttu-id="fa85e-120">Saisissez la quantité vendue.</span><span class="sxs-lookup"><span data-stu-id="fa85e-120">Enter the sales quantity.</span></span>
11. <span data-ttu-id="fa85e-121">Sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="fa85e-121">Select **Create**.</span></span>
12. <span data-ttu-id="fa85e-122">Cliquez sur **Terminer** pour capturer le paiement du client.</span><span class="sxs-lookup"><span data-stu-id="fa85e-122">Select **Complete** to capture the customer payment.</span></span>
13. <span data-ttu-id="fa85e-123">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="fa85e-123">Select **Add**.</span></span>
    * <span data-ttu-id="fa85e-124">Le lien Ajouter figure dans l’onglet Paiements. Développez l’onglet Paiements s’il est réduit.</span><span class="sxs-lookup"><span data-stu-id="fa85e-124">The Add link is in the Payments tab. Expand the Payments tab if it is collapsed.</span></span>  
14. <span data-ttu-id="fa85e-125">Sélectionnez le mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="fa85e-125">Select the payment method.</span></span>
    * <span data-ttu-id="fa85e-126">Pour cette procédure, sélectionnez le mode de paiement au comptant.</span><span class="sxs-lookup"><span data-stu-id="fa85e-126">For this procedure, select the cash payment method.</span></span>  
15. <span data-ttu-id="fa85e-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fa85e-127">Close the page.</span></span>
16. <span data-ttu-id="fa85e-128">Entrez le montant.</span><span class="sxs-lookup"><span data-stu-id="fa85e-128">Enter the amount.</span></span>
    * <span data-ttu-id="fa85e-129">Pour cette procédure, saisissez un montant égal au solde de la commande qui s’affiche dans la page Résumé de la commande client à gauche du champ de montant.</span><span class="sxs-lookup"><span data-stu-id="fa85e-129">For this procedure, enter an amount equal to the order balance that can be seen in the Sales order summary page to the left of the amount field.</span></span> <span data-ttu-id="fa85e-130">Cette action vous permet de terminer la commande comme étant intégralement payée.</span><span class="sxs-lookup"><span data-stu-id="fa85e-130">This action will allow you to complete the order as fully paid.</span></span>  
17. <span data-ttu-id="fa85e-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa85e-131">Select **OK**.</span></span>
18. <span data-ttu-id="fa85e-132">Sélectionnez **Soumettre**.</span><span class="sxs-lookup"><span data-stu-id="fa85e-132">Select **Submit**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fa85e-133">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="fa85e-133">Additional resources</span></span>

[<span data-ttu-id="fa85e-134">Personnalisez les e-mails transactionnels par mode de livraison</span><span class="sxs-lookup"><span data-stu-id="fa85e-134">Customize transactional emails by mode of delivery</span></span>](../customize-email-delivery-mode.md)

[<span data-ttu-id="fa85e-135">Modifier le mode de livraison dans le PDV</span><span class="sxs-lookup"><span data-stu-id="fa85e-135">Change mode of delivery in POS</span></span>](../pos-change-delivery-mode.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]