--- 
title: Entrer des contrats de vente
description: "Cette procédure vous explique comment créer un contrat de vente qui engage l'un de vos clients à acheter un produit pour un montant convenu sur une période définie en échange de remises spéciales."
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesAgreementListPage, SalesAgreementCreate, SalesAgreement, InventItemIdLookupSimple, AgreementConfirmRunForm, SrsReportViewerForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 874fee6de6e5aa5a29c271cc2e3d4cfd96672f3e
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="enter-sales-agreements"></a><span data-ttu-id="f225b-103">Entrer des contrats de vente</span><span class="sxs-lookup"><span data-stu-id="f225b-103">Enter sales agreements</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f225b-104">Cette procédure vous explique comment créer un contrat de vente qui engage l'un de vos clients à acheter un produit pour un</span><span class="sxs-lookup"><span data-stu-id="f225b-104">This procedure shows you how to create a sales agreement that commits one of your customers to buy a product for an</span></span>

<span data-ttu-id="f225b-105">montant convenu sur une période définie en échange de remises spéciales.</span><span class="sxs-lookup"><span data-stu-id="f225b-105">agreed amount over time in exchange for special discounts.</span></span> <span data-ttu-id="f225b-106">Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="f225b-106">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-sales-agreement-header"></a><span data-ttu-id="f225b-107">Paramétrer un en-tête de contrat de vente</span><span class="sxs-lookup"><span data-stu-id="f225b-107">Set up sales agreement header</span></span>
1. <span data-ttu-id="f225b-108">Accédez à Ventes et marketing > Contrats de vente > Contrats de vente.</span><span class="sxs-lookup"><span data-stu-id="f225b-108">Go to Sales and marketing > Sales agreements > Sales agreements.</span></span>
2. <span data-ttu-id="f225b-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f225b-109">Click New.</span></span>
3. <span data-ttu-id="f225b-110">Dans le champ Compte client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="f225b-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="f225b-111">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="f225b-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="f225b-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f225b-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="f225b-113">Dans le champ Classification du contrat de vente, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="f225b-113">In the Sales agreement classification field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="f225b-114">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f225b-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="f225b-115">Développez la section Général.</span><span class="sxs-lookup"><span data-stu-id="f225b-115">Expand the General section.</span></span>
9. <span data-ttu-id="f225b-116">Dans le champ Engagement par défaut, sélectionnez « Engagement à la valeur du produit ».</span><span class="sxs-lookup"><span data-stu-id="f225b-116">In the Default commitment field, select 'Product value commitment'.</span></span>
    * <span data-ttu-id="f225b-117">Un type d'engagement est un critère obligatoire que vous devez affecter à l'accord afin de définir la manière dont l'objectif du contrat est atteint.</span><span class="sxs-lookup"><span data-stu-id="f225b-117">A commitment type is a mandatory criterion that you must assign to the agreement to define how the agreement contract will be fulfilled.</span></span> <span data-ttu-id="f225b-118">Les quatre types prédéfinie vous permettent de paramétrer la cible de l'engagement du client, exprimée comme une quantité ou une valeur.</span><span class="sxs-lookup"><span data-stu-id="f225b-118">The four predefined types let you set up the customer's commitment target, expressed as a quantity or a value.</span></span> <span data-ttu-id="f225b-119">Le type d'engagement à la quantité peut uniquement être appliqué à un produit spécifique, mais les types basés sur la valeur s'appliquent aux ventes des produits spécifiques et non spécifiques.</span><span class="sxs-lookup"><span data-stu-id="f225b-119">The quantity commitment type can only be applied to a specific product, but the value-based types are applicable to sales of both specific and non-specific products.</span></span>  
10. <span data-ttu-id="f225b-120">Dans le champ Date d'expiration, définissez la date à une date future à laquelle vous souhaitez que l'accord arrive à expiration.</span><span class="sxs-lookup"><span data-stu-id="f225b-120">In the Expiration date field, set the date to a future date when you want the agreement to expire.</span></span>
11. <span data-ttu-id="f225b-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f225b-121">Click OK.</span></span>

## <a name="set-up-product-value-commitment-lines"></a><span data-ttu-id="f225b-122">Paramétrer des lignes d'engagement à la valeur du produit</span><span class="sxs-lookup"><span data-stu-id="f225b-122">Set up product value commitment lines</span></span>
1. <span data-ttu-id="f225b-123">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="f225b-123">Click Add line.</span></span>
2. <span data-ttu-id="f225b-124">Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="f225b-124">In the Item number field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="f225b-125">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="f225b-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="f225b-126">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f225b-126">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f225b-127">Le type d'engagement que vous avez choisi pour l'accord affecte le type d'informations que vous pouvez spécifier pour les lignes d'accord.</span><span class="sxs-lookup"><span data-stu-id="f225b-127">The type of commitment that you have chosen for the agreement affects the kind of information you can enter for the agreement lines.</span></span> <span data-ttu-id="f225b-128">Par exemple, pour un accord basé sur des valeurs vous devez spécifier le montant net total (dans la devise acceptée) pour lequel le client s'engage à vous acheter des marchandises.</span><span class="sxs-lookup"><span data-stu-id="f225b-128">For example, for a value-based agreement you must specify the total net amount (in the agreed currency) for which the customer commits to buys goods from you.</span></span> <span data-ttu-id="f225b-129">Dans cet exemple, les champs Quantité et Unité de la ligne sont indisponibles car vous êtes en train de créer un accord pour que le client achète une valeur spécifique d'un produit.</span><span class="sxs-lookup"><span data-stu-id="f225b-129">In this example the Quantity and Unit fields on the line are unavailable because you’re creating an agreement for the customer to buy a specific value of a product.</span></span>   
5. <span data-ttu-id="f225b-130">Dans le champ Montant net, spécifiez le montant en devises pour lequel le client s'est engagé en matière d'achat.</span><span class="sxs-lookup"><span data-stu-id="f225b-130">In the Net amount field, enter the monetary amount that the customer has committed to buying.</span></span>
6. <span data-ttu-id="f225b-131">Dans le champ Pourcentage de remise, entrez une valeur en pourcentage qui s'appliquera aux lignes de commande du client liées à cet accord.</span><span class="sxs-lookup"><span data-stu-id="f225b-131">In the Discount percent field, enter a percentage value that will apply to the customer's sales order lines that are linked to this agreement.</span></span>
7. <span data-ttu-id="f225b-132">Développez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="f225b-132">Expand the Line details section.</span></span>
8. <span data-ttu-id="f225b-133">Dans le champ Le max. est appliqué, sélectionnez Oui.</span><span class="sxs-lookup"><span data-stu-id="f225b-133">Select Yes in the Max is enforced field.</span></span>
    * <span data-ttu-id="f225b-134">Sélectionnez l'option « Le max. est appliqué » signifie que le montant total de toutes les lignes de commande client qui utilisent les prix spéciaux, les remises et/ou les conditions de paiement de l'engagement ne doit pas dépasser le montant spécifié dans l'engagement.</span><span class="sxs-lookup"><span data-stu-id="f225b-134">Selecting Max is enforced means that the total amount of all the sales order lines that use the commitment's special prices, discounts and/or payment terms must not exceed the amount specified on the commitment.</span></span>  
    * <span data-ttu-id="f225b-135">Les montants de lancement minimal et maximal spécifient une plage de valeurs qui doivent être vendues sur chaque commande client qui utilise l'accord sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f225b-135">The minimum and maximum release amounts specify a range of values that must be sold on each sales order that uses the selected agreement.</span></span>   
9. <span data-ttu-id="f225b-136">Développez la section En-tête de contrat de vente.</span><span class="sxs-lookup"><span data-stu-id="f225b-136">Expand the Sales agreement header section.</span></span>
    * <span data-ttu-id="f225b-137">À moins que le statut de l'accord soit défini à Effectif, les commandes client ne peuvent pas être associées à l'accord et ne peuvent donc pas contribuer à l'accomplissement de cet accord.</span><span class="sxs-lookup"><span data-stu-id="f225b-137">Unless the status of the agreement is set to Effective, sales orders cannot be associated with the agreement and can therefore not contribute to the fulfilment of that agreement.</span></span> <span data-ttu-id="f225b-138">À ce stade, vous pouvez modifier le statut manuellement.</span><span class="sxs-lookup"><span data-stu-id="f225b-138">You can change the status manually at this stage.</span></span> <span data-ttu-id="f225b-139">Toutefois, le statut serait normalement modifié lorsque vous confirmez l'accord pour le client.</span><span class="sxs-lookup"><span data-stu-id="f225b-139">However, the status would normally be changed when you confirm the agreement for the customer.</span></span>  
10. <span data-ttu-id="f225b-140">Dans le volet Actions, cliquez sur Contrats de vente.</span><span class="sxs-lookup"><span data-stu-id="f225b-140">On the Action Pane, click Sales agreement.</span></span>
11. <span data-ttu-id="f225b-141">Cliquez sur Confirmation.</span><span class="sxs-lookup"><span data-stu-id="f225b-141">Click Confirmation.</span></span>
    * <span data-ttu-id="f225b-142">Assurez-vous que l'option Marquer l'accord comme effectif est définie à Oui.</span><span class="sxs-lookup"><span data-stu-id="f225b-142">Make sure that the Mark agreement as effective option is set to Yes.</span></span>  
12. <span data-ttu-id="f225b-143">Dans le champ Imprimer un état, sélectionnez Oui.</span><span class="sxs-lookup"><span data-stu-id="f225b-143">Select Yes in the Print report field.</span></span>
13. <span data-ttu-id="f225b-144">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f225b-144">Click OK.</span></span>
14. <span data-ttu-id="f225b-145">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f225b-145">Close the page.</span></span>
    * <span data-ttu-id="f225b-146">L'accord est désormais effectif et vous pouvez commencer à lier les commandes du client à l'accord, à déduire de la cible de l'engagement.</span><span class="sxs-lookup"><span data-stu-id="f225b-146">The agreement is now effective and you can start linking the customer's orders to the agreement, to offset against the committed target.</span></span>  


