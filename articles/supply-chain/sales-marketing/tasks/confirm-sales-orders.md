---
title: Confirmer les commandes client
description: Cette procédure illustre comment confirmer des commandes client.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, CustConfirmJournal, SysQueryForm, SysQueryFieldLookUp, SysLookup, SalesParmIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c01c5e070954b3791df3cb67ba7c4f4ec79e3003
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1833976"
---
# <a name="confirm-sales-orders"></a><span data-ttu-id="cc476-103">Confirmer les commandes client</span><span class="sxs-lookup"><span data-stu-id="cc476-103">Confirm sales orders</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cc476-104">Cette procédure illustre comment confirmer des commandes client.</span><span class="sxs-lookup"><span data-stu-id="cc476-104">This procedure demonstrates how to confirm sales orders.</span></span> <span data-ttu-id="cc476-105">Vous découvrirez comment confirmer une seule commande et comment confirmer plusieurs commandes à la fois.</span><span class="sxs-lookup"><span data-stu-id="cc476-105">You’ll be shown how to confirm a single order, and how to confirm multiple orders at once.</span></span> <span data-ttu-id="cc476-106">Ces tâches sont généralement effectuées par un préparateur de commandes client.</span><span class="sxs-lookup"><span data-stu-id="cc476-106">These tasks would typically be carried out by a sales order processor.</span></span> <span data-ttu-id="cc476-107">Vous pouvez utiliser cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="cc476-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="cc476-108">Avant de commencer, assurez-vous qu'il existe plusieurs commandes client en cours pour le même client.</span><span class="sxs-lookup"><span data-stu-id="cc476-108">Before you start, make sure there are several open sales orders for the same customer.</span></span> <span data-ttu-id="cc476-109">Si vous utilisez USMF, vous pouvez utiliser le client US-027.</span><span class="sxs-lookup"><span data-stu-id="cc476-109">If you’re using USMF, you can use customer US-027.</span></span>


## <a name="confirm-a-single-sales-order"></a><span data-ttu-id="cc476-110">Confirmer une seule commande client</span><span class="sxs-lookup"><span data-stu-id="cc476-110">Confirm a single sales order</span></span>
1. <span data-ttu-id="cc476-111">Allez dans Ventes et marketing > Commandes client > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="cc476-111">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="cc476-112">Dans la liste, localisez et sélectionnez la commande que vous voulez confirmer.</span><span class="sxs-lookup"><span data-stu-id="cc476-112">In the list, find and select the order that you want to confirm.</span></span>
3. <span data-ttu-id="cc476-113">Cliquez sur le lien sur le numéro de commande client pour ouvrir la commande sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cc476-113">Click the link on the sales order number to open the selected order.</span></span>
4. <span data-ttu-id="cc476-114">Cliquez sur Vendre dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="cc476-114">On the Action Pane, click Sell.</span></span>
5. <span data-ttu-id="cc476-115">Cliquez sur Confirmer la commande client.</span><span class="sxs-lookup"><span data-stu-id="cc476-115">Click Confirm sales order.</span></span>
6. <span data-ttu-id="cc476-116">Développez ou réduisez la section Paramètres.</span><span class="sxs-lookup"><span data-stu-id="cc476-116">Expand or collapse the Parameters section.</span></span>
    * <span data-ttu-id="cc476-117">Veillez à ce que le champ Validation Oui soit actif.</span><span class="sxs-lookup"><span data-stu-id="cc476-117">Make sure that the Posting Yes field is active.</span></span>  
7. <span data-ttu-id="cc476-118">Définissez l'option Impression de la confirmation sur Oui.</span><span class="sxs-lookup"><span data-stu-id="cc476-118">Set the Print confirmation option to Yes.</span></span>
    * <span data-ttu-id="cc476-119">Le champ Vérifier la limite de crédit, spécifie la méthode utilisée pour calculer le crédit restant d'un client.</span><span class="sxs-lookup"><span data-stu-id="cc476-119">The Check credit limit field specifies the method that’s used to calculate a customer's remaining credit.</span></span> <span data-ttu-id="cc476-120">Par défaut, il est copié à partir de la page Paramètres de la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="cc476-120">By default, it’s copied from the Accounts receivable parameters page.</span></span> <span data-ttu-id="cc476-121">Si vous souhaitez ignorer la vérification de la limite de crédit lors de la confirmation d'une commande client spécifique, définissez la limite de crédit de chèque sur Aucune.</span><span class="sxs-lookup"><span data-stu-id="cc476-121">If you want to skip the credit limit check when confirming a specific sales order, set the Check credit limit to None.</span></span> <span data-ttu-id="cc476-122">Toutefois, vous devez être conscient que même avec ce champ est défini sur Aucune, la vérification de la limite de crédit est toujours effectuée si l'option Limite de crédit obligatoire est activée dans les données principales du client.</span><span class="sxs-lookup"><span data-stu-id="cc476-122">However, you should be aware that even with if this field is set to None, the credit limit check will still be performed if the Mandatory credit limit option is selected on the customer master data.</span></span>  
8. <span data-ttu-id="cc476-123">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cc476-123">Click OK.</span></span>
9. <span data-ttu-id="cc476-124">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="cc476-124">Click Yes.</span></span>
10. <span data-ttu-id="cc476-125">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="cc476-125">Close the page.</span></span>
11. <span data-ttu-id="cc476-126">Dans le volet Actions, cliquez sur Options.</span><span class="sxs-lookup"><span data-stu-id="cc476-126">On the Action Pane, click Options.</span></span>
12. <span data-ttu-id="cc476-127">Cliquez sur Changer de vue.</span><span class="sxs-lookup"><span data-stu-id="cc476-127">Click Change view.</span></span>
13. <span data-ttu-id="cc476-128">Cliquez sur Vue de l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="cc476-128">Click Header view.</span></span>
    * <span data-ttu-id="cc476-129">Lorsqu'une commande est confirmée, le statut du document est défini sur Confirmation.</span><span class="sxs-lookup"><span data-stu-id="cc476-129">When an order is confirmed, the Document status is set to Confirmation.</span></span>  
14. <span data-ttu-id="cc476-130">Cliquez sur Vendre dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="cc476-130">On the Action Pane, click Sell.</span></span>
15. <span data-ttu-id="cc476-131">Cliquez sur Confirmation de commande client.</span><span class="sxs-lookup"><span data-stu-id="cc476-131">Click Sales order confirmation.</span></span>
16. <span data-ttu-id="cc476-132">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="cc476-132">Close the page.</span></span>

## <a name="confirm-multiple-sales-orders-at-once"></a><span data-ttu-id="cc476-133">Confirmer plusieurs commandes client simultanément</span><span class="sxs-lookup"><span data-stu-id="cc476-133">Confirm multiple sales orders at once</span></span>
1. <span data-ttu-id="cc476-134">Accédez à Ventes et marketing > Commandes client > Confirmation de commande > Confirmer la commande client.</span><span class="sxs-lookup"><span data-stu-id="cc476-134">Go to Sales and marketing > Sales orders > Order confirmation > Confirm sales order.</span></span>
2. <span data-ttu-id="cc476-135">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="cc476-135">Click Select.</span></span>
3. <span data-ttu-id="cc476-136">Dans la liste de l'onglet Plage, localisez et sélectionnez l'enregistrement qui fait référence au champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="cc476-136">In the list on the Range tab, find and select the record that references the Customer account field.</span></span>
4. <span data-ttu-id="cc476-137">Dans le champ Critères, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="cc476-137">In the Criteria field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="cc476-138">Dans la liste, localisez et sélectionnez le compte client qui a plusieurs commandes que vous souhaitez confirmer simultanément.</span><span class="sxs-lookup"><span data-stu-id="cc476-138">In the list, find and select the customer account that has multiple orders which you want to mass confirm.</span></span>
    * <span data-ttu-id="cc476-139">Si vous utilisez USMF, vous pouvez sélectionner le compte US-027.</span><span class="sxs-lookup"><span data-stu-id="cc476-139">If you’re using USMF, you can select account US-027.</span></span>  
6. <span data-ttu-id="cc476-140">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cc476-140">Click OK.</span></span>
    * <span data-ttu-id="cc476-141">L'onglet Vue d'ensemble affiche la liste des commandes qui correspondent aux critères de requête.</span><span class="sxs-lookup"><span data-stu-id="cc476-141">The Overview tab displays a list of the orders that match the query criteria.</span></span> <span data-ttu-id="cc476-142">Ceux-ci sont inclus dans la confirmation.</span><span class="sxs-lookup"><span data-stu-id="cc476-142">These will be included in the confirmation.</span></span>  
    * <span data-ttu-id="cc476-143">Le champ Mise à jour récapitulative pour spécifie le paramètre par lequel plusieurs commandes doivent être synthétisées dans un document de confirmation.</span><span class="sxs-lookup"><span data-stu-id="cc476-143">The Summary update for field specifies the parameter by which multiple orders are to be summarized into one confirmation document.</span></span> <span data-ttu-id="cc476-144">Par défaut, l'option est copiée à partir des valeurs par défaut pour le paramètre de mise à jour récapitulative sur la page Paramètres de la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="cc476-144">By default, the option is copied from the Default values for summary update setting on the Accounts receivable parameters page.</span></span>  
7. <span data-ttu-id="cc476-145">Dans le champ Mise à jour récapitulative, sélectionnez « Commande ».</span><span class="sxs-lookup"><span data-stu-id="cc476-145">In the Summary update for field, select 'Order'.</span></span>
    * <span data-ttu-id="cc476-146">Les paramètres minimaux requis pour créer des mises à jour récapitulatives sont Compte de facturation et Devise.</span><span class="sxs-lookup"><span data-stu-id="cc476-146">The minimum parameters that are required to create summary updates are Invoice account and Currency.</span></span> <span data-ttu-id="cc476-147">Cela signifie que les mises à jour récapitulatives présentant des comptes de facturation et des devises différents ne sont pas autorisées.</span><span class="sxs-lookup"><span data-stu-id="cc476-147">This means that summary updates that have different invoice accounts and different currencies are not allowed.</span></span> <span data-ttu-id="cc476-148">Les paramètres supplémentaires peuvent être paramétrées dans la page Paramètres de mise à jour récapitulative qui est accessible à partir de la page Paramètres de la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="cc476-148">Additional parameters can be set up in the Summary update parameters page which is accessible from the Accounts receivable parameters page.</span></span>  
8. <span data-ttu-id="cc476-149">Dans le champ Commande client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="cc476-149">In the Sales order field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="cc476-150">Dans la liste, sélectionnez le numéro de la commande qui servira de commande récapitulative.</span><span class="sxs-lookup"><span data-stu-id="cc476-150">In the list, select the order number that you want to be the summary order.</span></span>
10. <span data-ttu-id="cc476-151">Cliquez sur Organiser.</span><span class="sxs-lookup"><span data-stu-id="cc476-151">Click Arrange.</span></span>
11. <span data-ttu-id="cc476-152">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cc476-152">Click OK.</span></span>
12. <span data-ttu-id="cc476-153">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cc476-153">Click OK.</span></span>

