---
title: Mises en attente du paiement d'une facture fournisseur dans le secteur public en France
description: "Les processus standard liés aux mises en attente de paiement d'une facture fournisseur dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition ont été étendus pour les entités françaises du secteur public. Cette rubrique décrit la fonctionnalité de mises en attente de paiement d'une facture fournisseur utilisée par le secteur public en France."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 27331
ms.search.region: France
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: d561da4f331bd62ad74d81a5d0d6eea98fdde7d4
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="vendor-invoice-payment-holds-in-the-public-sector-in-france"></a><span data-ttu-id="2b0a0-104">Mises en attente du paiement d'une facture fournisseur dans le secteur public en France</span><span class="sxs-lookup"><span data-stu-id="2b0a0-104">Vendor invoice payment holds in the public sector in France</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2b0a0-105">Les processus standard liés aux mises en attente de paiement d'une facture fournisseur dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition ont été étendus pour les entités françaises du secteur public.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-105">The standard processes related to vendor invoice payment holds in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition are augmented for French entities in the public sector.</span></span> <span data-ttu-id="2b0a0-106">Cette rubrique décrit la fonctionnalité de mises en attente de paiement d'une facture fournisseur utilisée par le secteur public en France.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-106">This topic describes the vendor invoice payment holds functionality used by the public sector in France.</span></span>

<a name="set-up-rules-for-vendor-invoice-payment-holds"></a><span data-ttu-id="2b0a0-107">Définition de règles pour les mises en attente de paiement d'une facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="2b0a0-107">Set up rules for vendor invoice payment holds</span></span>
---------------------------------------------

<span data-ttu-id="2b0a0-108">Les règles pour la mise en attente du paiement d'une facture fournisseur sont paramétrées dans l'organisateur **Bloquer** de la page **Conditions de paiement**.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-108">Rules for vendor invoice payment holds are set up on the **Hold** FastTab on the **Terms of payment** page.</span></span> <span data-ttu-id="2b0a0-109">Chaque règle est constituée de trois parties :</span><span class="sxs-lookup"><span data-stu-id="2b0a0-109">Each rule has three parts:</span></span>

-   <span data-ttu-id="2b0a0-110">Un rôle utilisateur, tel que comptable, gestionnaire comptable ou contrôleur.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-110">A user role, such as accountant, accounting manager, or controller.</span></span> <span data-ttu-id="2b0a0-111">Seuls les utilisateurs dotés du rôle spécifié peuvent mettre en attente ou lancer un paiement sous les conditions de paiement spécifiées.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-111">Only users who are assigned the specified role can hold or release a payment under the specified terms of payment.</span></span>
-   <span data-ttu-id="2b0a0-112">Le nombre de jours minimal à ajouter à la date d'échéance du paiement de la facture lorsqu'un utilisateur doté du rôle sélectionné met fin à la mise en attente.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-112">The minimum number of days that will be added to the invoice payment due date when a user with the selected role releases the hold.</span></span>
-   <span data-ttu-id="2b0a0-113">Le nombre maximal de fois où un utilisateur doté du rôle spécifié peut mettre en attente un paiement sur chaque facture.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-113">The maximum number of times that a user with the selected role can hold a payment on each invoice.</span></span> <span data-ttu-id="2b0a0-114">**Conseil** : pour autoriser un nombre illimité de mises en attente, entrez un nombre important, tel que 9999.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-114">**Tip**: To allow unlimited holds, enter a large number, such as 9999.</span></span>

<span data-ttu-id="2b0a0-115">Par exemple, sur les conditions de paiement Net 30, vous pouvez créer deux règles : une pour les comptables et une pour les directeurs.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-115">For example, on the Net 30 term of payment, you might create two rules, one for accountants and one for directors.</span></span> <span data-ttu-id="2b0a0-116">La règle pour les comptables ajoute un minimum de 30 jours à la date d'échéance de paiement de la facture lorsque la mise en attente prend fin, et autorise un maximum de 3 mises en attente sur une facture.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-116">The rule for accountants adds a minimum of 30 days to the invoice payment due date when the hold is released, and allows a maximum of 3 holds on an invoice.</span></span> <span data-ttu-id="2b0a0-117">La règle pour les directeurs ajoute un minimum de 15 jours à la date d'échéance de paiement de la facture, avec un maximum de 10 mises en attente sur une facture.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-117">The rule for directors adds a minimum of 15 days to the invoice payment due date, with a maximum of 10 holds on an invoice.</span></span>

## <a name="when-can-i-place-and-release-vendor-invoice-payment-holds"></a><span data-ttu-id="2b0a0-118">Quand puis-je créer et supprimer des mises en attente de paiement d'une facture fournisseur ?</span><span class="sxs-lookup"><span data-stu-id="2b0a0-118">When can I place and release vendor invoice payment holds?</span></span>
<span data-ttu-id="2b0a0-119">Des mises en attente de paiement peuvent être effectuées ou supprimées dans les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="2b0a0-119">Holds can be placed and released in the following circumstances:</span></span>

-   <span data-ttu-id="2b0a0-120">Pour pouvoir effectuer une mise en attente de paiement, il faut que des conditions de paiement aient été définies pour la facture fournisseur concernée ou pour toutes les factures fournisseur associées au fournisseur concerné.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-120">Payment terms must be set up for a vendor invoice, or for all vendor invoices for a specific vendor, before you can place a hold.</span></span>
-   <span data-ttu-id="2b0a0-121">Pour créer une mise en attente de paiement ou la supprimer, vous devez être affecté à un rôle d'utilisateur pour lequel des règles ont été définies pour les mises en attente de paiement.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-121">To place or release a hold, you must be assigned to a user role where rules have been set up for payment holds.</span></span>
-   <span data-ttu-id="2b0a0-122">Si une mise en attente est activée pour un fournisseur, il est impossible de procéder à la mise en attente d'une facture du même fournisseur.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-122">If a hold is active for a vendor, you cannot release a hold for an invoice for that same vendor.</span></span> <span data-ttu-id="2b0a0-123">Vous devez d'abord supprimer la mise en attente du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-123">You must first release the hold for the vendor.</span></span>
-   <span data-ttu-id="2b0a0-124">Seul l'utilisateur qui a procédé à la mise en attente ou les utilisateurs qui assument le même rôle que ce dernier sont habilités à supprimer la mise en attente.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-124">You cannot release a hold unless you are the user who placed the hold, or you are assigned to the same user role as the user who placed the hold.</span></span>
-   <span data-ttu-id="2b0a0-125">Il est impossible de valider une facture fournisseur dont le paiement a été mis en attente.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-125">You cannot post a vendor invoice if it has a payment hold.</span></span> <span data-ttu-id="2b0a0-126">Il convient d'abord de supprimer la mise en attente.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-126">The hold must first be released.</span></span>

## <a name="where-do-i-place-and-release-vendor-invoice-payment-holds"></a><span data-ttu-id="2b0a0-127">Où dois-je créer et supprimer des mises en attente de paiement d'une facture fournisseur ?</span><span class="sxs-lookup"><span data-stu-id="2b0a0-127">Where do I place and release vendor invoice payment holds?</span></span>
### <a name="for-a-vendor"></a><span data-ttu-id="2b0a0-128">Pour un fournisseur</span><span class="sxs-lookup"><span data-stu-id="2b0a0-128">For a vendor</span></span>
<span data-ttu-id="2b0a0-129">Créez ou supprimez une mise en attente de paiement pour toutes les factures d'un fournisseur sélectionné sur la page **Transactions fournisseur** ou sur la page **Règlement des transactions**.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-129">Place or release a payment hold for all invoices for a selected vendor on the **Vendor transactions** page or the **Settle transactions** page.</span></span> <span data-ttu-id="2b0a0-130">Si vous appliquez une mise en attente de paiement à un fournisseur, cette dernière concernera toutes les factures de ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-130">If you place a payment hold for a vendor, this hold includes all existing invoices for that vendor.</span></span> <span data-ttu-id="2b0a0-131">Si vous supprimez la mise en attente de paiement appliquée à un fournisseur, les mises en attente ne seront supprimées que sur les factures fournisseur qui n'ont pas été mises en attente individuellement.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-131">If you release a payment hold for a vendor, this releases the payment hold only for those vendor invoices that do not have individual payment holds.</span></span> <span data-ttu-id="2b0a0-132">Par exemple, vous procédez à des mises en attente de paiement individuelles de deux factures fournisseur différentes, concernant le même fournisseur.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-132">For example, you place individual payment holds on two different vendor invoices for the same vendor.</span></span> <span data-ttu-id="2b0a0-133">Ultérieurement, vous appliquez une mise en attente de paiement au fournisseur.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-133">You later place a payment hold for that vendor.</span></span> <span data-ttu-id="2b0a0-134">Lorsque vous supprimerez la mise en attente de paiement appliquée au fournisseur, les mises en attente individuelles des deux factures ne seront pas supprimées.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-134">If you later release the payment hold for that vendor, it will not release the individual holds for the two vendor invoices.</span></span>

### <a name="for-a-vendor-invoice"></a><span data-ttu-id="2b0a0-135">Pour une facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="2b0a0-135">For a vendor invoice</span></span>

<span data-ttu-id="2b0a0-136">Créez ou supprimez une mise en attente de paiement une facture unique sur la page **Facture fournisseur** ou sur la page **Règlement des transactions**.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-136">Place or release a payment hold for a single invoice on the **Vendor invoice** page or the **Settle transactions** page.</span></span>

### <a name="for-a-posted-vendor-invoice"></a><span data-ttu-id="2b0a0-137">Pour une facture fournisseur validée</span><span class="sxs-lookup"><span data-stu-id="2b0a0-137">For a posted vendor invoice</span></span>

<span data-ttu-id="2b0a0-138">Créez ou supprimez une mise en attente de paiement pour une facture fournisseur validée sur la page **Journal des factures**.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-138">Place or release a payment hold for a posted vendor invoice on the **Invoice journal** page.</span></span>

### <a name="for-all-vendor-invoices-associated-with-a-purchase-order"></a><span data-ttu-id="2b0a0-139">Pour toutes les factures fournisseur associées à une commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-139">For all vendor invoices associated with a purchase order</span></span>

<span data-ttu-id="2b0a0-140">Créez ou supprimer une mise en attente de paiement pour toutes les factures fournisseur qui sont associées à une commande fournisseur sur la page **Règlement des transactions**.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-140">Place or release a payment hold for all vendor invoices that are associated with a purchase order on the **Settle transactions** page.</span></span>

## <a name="can-i-settle-an-invoice-that-is-on-hold"></a><span data-ttu-id="2b0a0-141">Puis-je régler une facture qui est en attente ?</span><span class="sxs-lookup"><span data-stu-id="2b0a0-141">Can I settle an invoice that is on hold?</span></span>
<span data-ttu-id="2b0a0-142">Si vous assumez le même rôle utilisateur que la personne qui a créé la mise en attente, vous pouvez y mettre fin à partir de la page **Règlement des transactions** et régler la facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-142">If you are assigned to the same user role as the user who placed the hold, you can clear the hold from the **Settle transactions** page and settle the vendor invoice.</span></span> <span data-ttu-id="2b0a0-143">Lorsque vous créez une mise en attente de paiement, l'option **Blocage de paiement de facture** est automatiquement sélectionnée sous l'onglet **Paiement** de la page **Règlement des transactions**.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-143">When you place a payment hold, the **Invoice payment hold** option is automatically selected on the **Payment** tab of the **Settle transactions** page.</span></span> <span data-ttu-id="2b0a0-144">Cela permet d'empêcher qu'une facture fournisseur ne soit réglée avant la suppression de la mise en attente.</span><span class="sxs-lookup"><span data-stu-id="2b0a0-144">This prevents a vendor invoice from being settled until the hold is released.</span></span>




