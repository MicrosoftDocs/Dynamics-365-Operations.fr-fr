---
title: Résoudre les problèmes de prix, de remises, d’accords et de rabais
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lorsque vous utilisez des prix, des remises, des accords et des rabais.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 5d17f2ec594901404fcd251e463f293258af051c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237153"
---
# <a name="troubleshoot-prices-discounts-agreements-and-rebates"></a><span data-ttu-id="442b8-103">Résoudre les problèmes de prix, de remises, d’accords et de rabais</span><span class="sxs-lookup"><span data-stu-id="442b8-103">Troubleshoot prices, discounts, agreements, and rebates</span></span>

<span data-ttu-id="442b8-104">Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lorsque vous utilisez des prix, des remises, des accords et des rabais.</span><span class="sxs-lookup"><span data-stu-id="442b8-104">This topic describes how to fix issues that you might encounter while you work with prices, discounts, agreements, and rebates.</span></span>

## <a name="i-cant-link-a-purchase-agreement-to-a-purchase-order-line-after-the-purchase-order-is-created"></a><span data-ttu-id="442b8-105">Je ne peux pas lier un contrat d’achat à une ligne de commande fournisseur après la création du bon de commande.</span><span class="sxs-lookup"><span data-stu-id="442b8-105">I can't link a purchase agreement to a purchase order line after the purchase order is created.</span></span>

<span data-ttu-id="442b8-106">Un contrat d’achat doit être associé à une ligne de commande fournisseur quand le bon de commande est créé.</span><span class="sxs-lookup"><span data-stu-id="442b8-106">A purchase agreement must be associated with a purchase order when the purchase order is created.</span></span> <span data-ttu-id="442b8-107">Sinon, les lignes de la commande fournisseur ne peuvent pas être associées aux lignes du contrat d’achat.</span><span class="sxs-lookup"><span data-stu-id="442b8-107">Otherwise, purchase order lines can't be associated with purchase agreement lines.</span></span>

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a><span data-ttu-id="442b8-108">Quel contrôle déclenche le message "Mettre à jour les prix et remises saisis manuellement ou via un document externe" ?</span><span class="sxs-lookup"><span data-stu-id="442b8-108">What check triggers the "Update prices and discounts entered manually or external document" message?</span></span>

<span data-ttu-id="442b8-109">Lorsque vous modifiez la date d’expédition, vous pouvez recevoir un message indiquant "Mettre à jour les prix et les remises saisis manuellement ou via un document externe".</span><span class="sxs-lookup"><span data-stu-id="442b8-109">When you change the shipping date, you might receive a message that states, "Update prices and discounts entered manually or external document."</span></span> <span data-ttu-id="442b8-110">Vous recevez ce message car, si la date d’expédition est modifiée, un autre accord de vente ou commercial peut être déclenché et entraîner une modification de prix.</span><span class="sxs-lookup"><span data-stu-id="442b8-110">You receive this message because, if the shipping date is changed, a different trade or sales agreement might be triggered and cause a price change.</span></span> <span data-ttu-id="442b8-111">Une modification de la date d’expédition peut également affecter les planning d’entrepôt et d’autres informations connexes.</span><span class="sxs-lookup"><span data-stu-id="442b8-111">A change to the shipping date can also affect warehouse schedules and other related information.</span></span>

<span data-ttu-id="442b8-112">Le message est déclenché chaque fois que l’une des dates ou certains autres paramètres sont modifiés.</span><span class="sxs-lookup"><span data-stu-id="442b8-112">The message is triggered whenever any of the dates or some other parameters are changed.</span></span> <span data-ttu-id="442b8-113">Le but du message est de vous assurer que vous êtes au courant des changements de prix qui peuvent survenir en raison de ces changements.</span><span class="sxs-lookup"><span data-stu-id="442b8-113">The purpose of the message is to make sure that you're aware of price changes that can occur because of those changes.</span></span>

<span data-ttu-id="442b8-114">Le message est l’invite d’évaluation de l’accord commercial (TAE).</span><span class="sxs-lookup"><span data-stu-id="442b8-114">The message is the trade agreement evaluation (TAE) prompt.</span></span> <span data-ttu-id="442b8-115">Pour une description complète, voir [Politiques d’évaluation des accords commerciaux](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).</span><span class="sxs-lookup"><span data-stu-id="442b8-115">For a full description, see [Trade agreement evaluation policies](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).</span></span>

## <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a><span data-ttu-id="442b8-116">Un accusé de réception de commande fournisseur n’inclut pas tous les frais.</span><span class="sxs-lookup"><span data-stu-id="442b8-116">A purchase order receipt doesn't include all charges.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="442b8-117">Reproduire le problème</span><span class="sxs-lookup"><span data-stu-id="442b8-117">Reproduce the issue</span></span>

<span data-ttu-id="442b8-118">La procédure suivante montre comment reproduire le problème.</span><span class="sxs-lookup"><span data-stu-id="442b8-118">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="442b8-119">Sur la page **Paramètres d’approvisionnements**, sur l’onglet **Livraison**, assurez-vous que l’option **Générer des frais sur l’accusé de réception de marchandises** est définie sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="442b8-119">On the **Procurement and sourcing parameters** page, on the **Delivery** tab, make sure that the **Generate charges on product receipt** option is set to *Yes*.</span></span>
1. <span data-ttu-id="442b8-120">Créez une commande fournisseur qui inclut des frais.</span><span class="sxs-lookup"><span data-stu-id="442b8-120">Create a purchase order that includes charges.</span></span>
1. <span data-ttu-id="442b8-121">Confirmez la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="442b8-121">Confirm the purchase order.</span></span>
1. <span data-ttu-id="442b8-122">Recevez la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="442b8-122">Receive the purchase order.</span></span>
1. <span data-ttu-id="442b8-123">Regardez le total de l’accusé de réception et comparez-le au total attendu.</span><span class="sxs-lookup"><span data-stu-id="442b8-123">Look at the receipt total, and compare it to the expected total.</span></span>
1. <span data-ttu-id="442b8-124">Notez que tous les frais ne sont pas inclus sur l’accusé de réception de la commande.</span><span class="sxs-lookup"><span data-stu-id="442b8-124">Notice that not all the charges are included on the purchase order receipt.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="442b8-125">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="442b8-125">Issue resolution</span></span>

<span data-ttu-id="442b8-126">La résolution dépend de la manière dont les frais divers ont été configurés.</span><span class="sxs-lookup"><span data-stu-id="442b8-126">The resolution depends on the way that the miscellaneous charges have been set up.</span></span> <span data-ttu-id="442b8-127">Pour plus d’informations sur la configuration des frais divers pour répondre à vos besoins, consultez l’article de blog suivant : [Valider des frais divers au moment de la réception des produits](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span><span class="sxs-lookup"><span data-stu-id="442b8-127">For information about how to set up miscellaneous charges to meet your requirements, see the following blog post: [Post misc. charges at time of product receipt](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span></span>

## <a name="trade-agreement-prices-and-discounts-arent-applied-on-sales-or-purchase-order-lines-that-are-imported-through-data-management"></a><span data-ttu-id="442b8-128">Les prix et les remises des accords commerciaux ne sont pas appliqués aux lignes de commande fournisseur ou client importées via la gestion des données.</span><span class="sxs-lookup"><span data-stu-id="442b8-128">Trade agreement prices and discounts aren't applied on sales or purchase order lines that are imported through data management.</span></span>

### <a name="issue-description"></a><span data-ttu-id="442b8-129">Description du problème</span><span class="sxs-lookup"><span data-stu-id="442b8-129">Issue description</span></span>

<span data-ttu-id="442b8-130">Les accords commerciaux qui sont applicables aux lignes de commande fournisseur ou client ne sont pas appliqués sur les lignes importées via la gestion des données.</span><span class="sxs-lookup"><span data-stu-id="442b8-130">Trade agreements that are applicable to sales or purchase order lines aren't applied on lines that are imported through data management.</span></span> <span data-ttu-id="442b8-131">Cependant, les mêmes accords commerciaux sont appliqués sur les lignes de commande client ou fournisseur créées manuellement.</span><span class="sxs-lookup"><span data-stu-id="442b8-131">However, the same trade agreements are applied on sales or purchase order lines that are manually created.</span></span>

### <a name="reason-for-the-issue"></a><span data-ttu-id="442b8-132">Raison du problème</span><span class="sxs-lookup"><span data-stu-id="442b8-132">Reason for the issue</span></span>

<span data-ttu-id="442b8-133">Si les lignes de commande fournisseur importées via la gestion des données incluent déjà des informations de prix, l’accord commercial ne sera pas réévalué pour ces lignes.</span><span class="sxs-lookup"><span data-stu-id="442b8-133">If purchase order lines that are imported via data management already include price information, the trade agreement won't be reevaluated for those lines.</span></span> <span data-ttu-id="442b8-134">Par exemple, si **Pourcentage de remise de ligne** ou l’une des valeurs de prix et de remise est définie pour une ligne, les accords commerciaux ne seront pas recherchés pour cette ligne.</span><span class="sxs-lookup"><span data-stu-id="442b8-134">For example, if **Line discount percentage** or any of the price and discount values is set for a line, then trade agreements will not be looked up for that line.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="442b8-135">Solution de contournement du problème</span><span class="sxs-lookup"><span data-stu-id="442b8-135">Issue workaround</span></span>

<span data-ttu-id="442b8-136">Ce comportement est attendu et est similaire pour les commandes client et les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="442b8-136">This behavior is expected, and is similar for both sales orders and purchase orders.</span></span>

<span data-ttu-id="442b8-137">Pour contourner le problème, importez les lignes de commande fournisseur sans définir aucune information de prix.</span><span class="sxs-lookup"><span data-stu-id="442b8-137">As a workaround, import the purchase order lines without setting any price information.</span></span> <span data-ttu-id="442b8-138">Les accords commerciaux seront alors appliqués et les lignes de commande fournisseur seront mises à jour en fonction des accords commerciaux définis.</span><span class="sxs-lookup"><span data-stu-id="442b8-138">The trade agreements will then be applied, and the purchase order lines will be updated based on the defined trade agreements.</span></span>

## <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a><span data-ttu-id="442b8-139">Une remise fournisseur n’est pas cumulée en fonction des factures.</span><span class="sxs-lookup"><span data-stu-id="442b8-139">A vendor rebate isn't cumulated based on invoices.</span></span>

### <a name="issue-description"></a><span data-ttu-id="442b8-140">Description du problème</span><span class="sxs-lookup"><span data-stu-id="442b8-140">Issue description</span></span>

<span data-ttu-id="442b8-141">Si les factures validées ont des dates d’échéance différentes, ces factures ne sont pas reflétées dans les remises fournisseur générées à partir d’elles.</span><span class="sxs-lookup"><span data-stu-id="442b8-141">If invoices that are posted have different due dates, those invoices aren't reflected in vendor rebates that are generated from them.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="442b8-142">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="442b8-142">Issue resolution</span></span>

<span data-ttu-id="442b8-143">Par défaut, la date d’échéance n’est pas prise en compte lors du calcul de la remise fournisseur.</span><span class="sxs-lookup"><span data-stu-id="442b8-143">By design, the due date isn't considered when the vendor rebate is calculated.</span></span> <span data-ttu-id="442b8-144">Envisagez de personnaliser le système afin que la date d’échéance et la relation avec la facture soient plus apparentes par rapport à la remise fournisseur réelle.</span><span class="sxs-lookup"><span data-stu-id="442b8-144">Consider customizing the system so that the due date and the relation to the invoice are more apparent with respect to the actual vendor rebate.</span></span>

## <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a><span data-ttu-id="442b8-145">Les prix unitaires sur les commandes fournisseur ne sont pas calculés en fonction de la conversion des unités.</span><span class="sxs-lookup"><span data-stu-id="442b8-145">Unit prices on purchase orders aren't calculated based on the unit conversion.</span></span>

### <a name="issue-description"></a><span data-ttu-id="442b8-146">Description du problème</span><span class="sxs-lookup"><span data-stu-id="442b8-146">Issue description</span></span>

<span data-ttu-id="442b8-147">Lorsqu’une unité est modifiée sur une commande fournisseur, les prix de l’accord commercial ne sont pas recalculés en fonction des définitions de la conversion d’unité.</span><span class="sxs-lookup"><span data-stu-id="442b8-147">When a unit is changed on a purchase order, trade agreement prices aren't recalculated according to unit conversion definitions.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="442b8-148">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="442b8-148">Issue resolution</span></span>

<span data-ttu-id="442b8-149">Les prix sont toujours obtenus à partir d’accords commerciaux (ou d’autres paramètres de prix dans le système, tels que les accords de vente ou les prix des articles) et ils sont définis pour une unité.</span><span class="sxs-lookup"><span data-stu-id="442b8-149">Prices are always obtained from trade agreements (or other price settings in the system, such as sales agreements or item prices), and they are set for a unit.</span></span>

<span data-ttu-id="442b8-150">Si l’unité est modifiée sur une ligne de commande, le système recherche un prix pour la nouvelle unité et applique ce prix.</span><span class="sxs-lookup"><span data-stu-id="442b8-150">If the unit is changed on an order line, the system looks for a price for the new unit and applies that price.</span></span> <span data-ttu-id="442b8-151">Si aucun prix n’est trouvé pour l’unité, le système n’applique pas de prix.</span><span class="sxs-lookup"><span data-stu-id="442b8-151">If no price is found for the unit, the system doesn't apply a price.</span></span> <span data-ttu-id="442b8-152">La conversion d’unité ne peut pas être utilisée pour recalculer le prix dans une autre unité.</span><span class="sxs-lookup"><span data-stu-id="442b8-152">The unit conversion can't be used to recalculate the price into another unit.</span></span> <span data-ttu-id="442b8-153">Théoriquement, le prix d’une boîte de dix pourrait ne pas être égal à dix fois le prix d’une boîte.</span><span class="sxs-lookup"><span data-stu-id="442b8-153">Theoretically, the price for one box of ten might not equal ten times the price of one box.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="442b8-154">Solution de contournement du problème</span><span class="sxs-lookup"><span data-stu-id="442b8-154">Issue workaround</span></span>

<span data-ttu-id="442b8-155">Une façon de contourner ce problème consiste à vous assurer qu’il existe des accords commerciaux pour les unités qui, selon vous, seront utilisées sur les lignes de commande de l’article.</span><span class="sxs-lookup"><span data-stu-id="442b8-155">One way to work around this issue is to make sure that there are trade agreements for the units that you expect will be used on order lines for the item.</span></span>

## <a name="currency-conversion-issues-occur-with-trade-agreements"></a><span data-ttu-id="442b8-156">Des problèmes de conversion de devises surviennent avec les accords commerciaux.</span><span class="sxs-lookup"><span data-stu-id="442b8-156">Currency conversion issues occur with trade agreements.</span></span>

<span data-ttu-id="442b8-157">Les prix des accords commerciaux ne sont pas recalculés en fonction de la devise lorsque la devise diffère sur une commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="442b8-157">Trade agreement prices aren't recalculated according to the currency when the currency differs on a purchase order.</span></span>

<span data-ttu-id="442b8-158">La fonction *Devise générique* vous permet de définir les prix et les remises dans une seule devise.</span><span class="sxs-lookup"><span data-stu-id="442b8-158">The *Generic currency* feature lets you define prices and discounts in only one currency.</span></span> <span data-ttu-id="442b8-159">Vous pouvez ensuite convertir vers d’autres devises selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="442b8-159">You can then convert to other currencies as you require.</span></span> <span data-ttu-id="442b8-160">En outre, une fois la conversion terminée, la fonction peut automatiquement appliquer un arrondi intelligent.</span><span class="sxs-lookup"><span data-stu-id="442b8-160">Furthermore, after the conversion is done, the feature can automatically apply smart rounding.</span></span>

## <a name="when-i-open-the-purchase-agreement-page-in-a-line-view-mode-i-cant-personalize-the-page-by-adding-the-price-unit-field-in-the-overview-of-the-line"></a><span data-ttu-id="442b8-161">Lorsque j’ouvre la page Contrat d’achat en mode d’affichage de ligne, je ne peux pas personnaliser la page en ajoutant le champ Unité de prix dans l’aperçu de la ligne.</span><span class="sxs-lookup"><span data-stu-id="442b8-161">When I open the Purchase agreement page in a line view mode, I can't personalize the page by adding the Price unit field in the overview of the line.</span></span>

<span data-ttu-id="442b8-162">Certains champs partagés dans le cadre de l’accord ne peuvent pas être inclus dans les personnalisations.</span><span class="sxs-lookup"><span data-stu-id="442b8-162">Some shared fields in the agreement framework can't be included in personalizations.</span></span> <span data-ttu-id="442b8-163">Cette limitation se produit en raison du modèle de données implémenté.</span><span class="sxs-lookup"><span data-stu-id="442b8-163">This limitation occurs because of the data model that is implemented.</span></span> <span data-ttu-id="442b8-164">Par conséquent, vous ne pouvez pas personnaliser le champ **Unité de prix**.</span><span class="sxs-lookup"><span data-stu-id="442b8-164">Therefore, you can't personalize the **Price unit** field.</span></span>

## <a name="the-maximum-limit-from-a-purchase-agreement-isnt-effective-on-a-purchase-requisition"></a><span data-ttu-id="442b8-165">La limite maximale d’un contrat d’achat n’est pas effective sur une demande d’achat.</span><span class="sxs-lookup"><span data-stu-id="442b8-165">The maximum limit from a purchase agreement isn't effective on a purchase requisition.</span></span>

### <a name="issue-description"></a><span data-ttu-id="442b8-166">Description du problème</span><span class="sxs-lookup"><span data-stu-id="442b8-166">Issue description</span></span>

<span data-ttu-id="442b8-167">Lorsqu’une demande d’achat est liée à un contrat d’achat, la limite maximale du contrat d’achat n’est pas effective sur la demande d’achat.</span><span class="sxs-lookup"><span data-stu-id="442b8-167">When a purchase requisition is linked to a purchase agreement, the maximum limit from the purchase agreement isn't effective on the purchase requisition.</span></span> <span data-ttu-id="442b8-168">Les informations de prix par défaut sont correctement saisies, mais la limite maximale du contrat d’achat peut être dépassée dans la demande d’achat.</span><span class="sxs-lookup"><span data-stu-id="442b8-168">The default price information is correctly entered, but more than the maximum limit from the purchase agreement can be ordered in the purchase requisition.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="442b8-169">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="442b8-169">Issue resolution</span></span>

<span data-ttu-id="442b8-170">Ce comportement est attendu.</span><span class="sxs-lookup"><span data-stu-id="442b8-170">This behavior is expected.</span></span> <span data-ttu-id="442b8-171">Étant donné que les demandes d’approvisionnement ne sont pas toujours approuvées, une quantité ou un montant ne doit pas être réservé sur le contrat d’achat.</span><span class="sxs-lookup"><span data-stu-id="442b8-171">Because requisitions aren't always approved, a quantity or amount should not be reserved on the purchase agreement.</span></span> <span data-ttu-id="442b8-172">Par conséquent, vous ne respecterez pas la limite maximale du contrat d’achat.</span><span class="sxs-lookup"><span data-stu-id="442b8-172">Therefore, you won't meet the maximum limit from the purchase agreement.</span></span>

## <a name="trade-agreements-can-be-created-from-rejected-rfqs-therefore-the-system-doesnt-prevent-trade-agreement-journals-from-being-created-if-the-rfq-line-hasnt-been-accepted"></a><span data-ttu-id="442b8-173">Des accords commerciaux peuvent être créés à partir d’appels d’offres rejetés.</span><span class="sxs-lookup"><span data-stu-id="442b8-173">Trade agreements can be created from rejected RFQs.</span></span> <span data-ttu-id="442b8-174">Par conséquent, le système n’empêche pas la création de journaux d’accords commerciaux si la ligne d’appel d’offres n’a pas été acceptée.</span><span class="sxs-lookup"><span data-stu-id="442b8-174">Therefore, the system doesn't prevent trade agreement journals from being created if the RFQ line hasn't been accepted.</span></span>

<span data-ttu-id="442b8-175">Vous pouvez créer des accords commerciaux pour toutes les réponses à un appel d’offres, qu’elles aient été acceptées ou rejetées.</span><span class="sxs-lookup"><span data-stu-id="442b8-175">You can create trade agreements for any replies for a request for quotation (RFQ), regardless of whether they were accepted or rejected.</span></span> <span data-ttu-id="442b8-176">Pour plus d’informations, voir [Vue d’ensemble des appels d’offre](request-quotations.md).</span><span class="sxs-lookup"><span data-stu-id="442b8-176">For more information, see [Requests for quotation (RFQs) overview](request-quotations.md).</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]