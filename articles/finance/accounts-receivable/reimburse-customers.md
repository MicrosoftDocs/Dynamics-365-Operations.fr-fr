---
title: Rembourser les clients
description: Cet article explique la création des transactions de remboursement pour un groupe de clients. Si un client a un solde créditeur, vous pouvez le rembourser pour le montant du solde.
author: JodiChristiansen
manager: AnnBe
ms.date: 09/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ca087b5a39432eec6b2711cc4c4decf23932b611
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251117"
---
# <a name="reimburse-customers"></a><span data-ttu-id="02dfe-104">Rembourser les clients</span><span class="sxs-lookup"><span data-stu-id="02dfe-104">Reimburse customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="02dfe-105">Cet article explique la création des transactions de remboursement pour un groupe de clients.</span><span class="sxs-lookup"><span data-stu-id="02dfe-105">This article explains how to create reimbursement transactions for a group of customers.</span></span> <span data-ttu-id="02dfe-106">Si un client a un solde créditeur, vous pouvez le rembourser pour le montant du solde.</span><span class="sxs-lookup"><span data-stu-id="02dfe-106">If a customer has a credit balance, you can reimburse the customer for the amount of the balance.</span></span> 

<span data-ttu-id="02dfe-107">Le tableau suivant indique la configuration requise qui doit être en place avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="02dfe-107">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="02dfe-108">Logiciel requis</span><span class="sxs-lookup"><span data-stu-id="02dfe-108">Prerequisite</span></span>                                                            | <span data-ttu-id="02dfe-109">Description</span><span class="sxs-lookup"><span data-stu-id="02dfe-109">Description</span></span> |
|-------------------------------------------------------------------------|-------------|
| <span data-ttu-id="02dfe-110">Spécification du montant minimal de remboursement pour l’entité juridique.</span><span class="sxs-lookup"><span data-stu-id="02dfe-110">Specify the minimum reimbursement amount for the legal entity.</span></span>          | <span data-ttu-id="02dfe-111">Dans la page **Paramètres de comptabilité client**, dans la zone **Général**, dans le champ **Remboursement minimal**, entrez le montant minimal qui peut être remboursé des trop-perçus client.</span><span class="sxs-lookup"><span data-stu-id="02dfe-111">On the **Accounts receivable parameters** page, in the **General** area, in the **Minimum reimbursement** field, enter the minimum amount that can be reimbursed for customer overpayments.</span></span> |
| <span data-ttu-id="02dfe-112">Facultatif : ajoutez un compte fournisseur à chaque client qui peut être remboursé.</span><span class="sxs-lookup"><span data-stu-id="02dfe-112">Optional: Add a vendor account to each customer that can be reimbursed.</span></span> | <span data-ttu-id="02dfe-113">Sur la page **Client**, dans l’organisateur **Détails divers**, dans le champ **Compte fournisseur**, sélectionnez le compte fournisseur pour le client.</span><span class="sxs-lookup"><span data-stu-id="02dfe-113">On the **Customers** page, on the **Miscellaneous details** FastTab, in the **Vendor account** field, select the vendor account for the customer.</span></span> |

<span data-ttu-id="02dfe-114">Lorsque vous créez des transactions de remboursement, une facture fournisseur est créée pour le montant du solde créditeur.</span><span class="sxs-lookup"><span data-stu-id="02dfe-114">When you create reimbursement transactions, a vendor invoice is created for the amount of the credit balance.</span></span> <span data-ttu-id="02dfe-115">Le processus de remboursement permet de supprimer le solde créditeur du compte client et crée un solde dû pour le compte fournisseur correspondant au client.</span><span class="sxs-lookup"><span data-stu-id="02dfe-115">The reimbursement process removes the credit balance for the customer account and creates a balance due for the vendor account that corresponds to the customer.</span></span>

1. <span data-ttu-id="02dfe-116">Dans Comptabilité client, exécutez le processus **Remboursement** (**Comptabilité client \> Tâches périodiques \> Remboursement**).</span><span class="sxs-lookup"><span data-stu-id="02dfe-116">In Accounts receivable, run the **Reimbursement** process (**Accounts receivable \> Periodic tasks \> Reimbursement**).</span></span>
2. <span data-ttu-id="02dfe-117">Pour regrouper toutes les transactions, quelles que soient les dimensions comptables, définissez l’option **Résumer le client** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="02dfe-117">To group all transactions, regardless of ledger dimensions, set the **Summarize customer** option to **Yes**.</span></span> <span data-ttu-id="02dfe-118">Pour regrouper uniquement les transactions qui ont des dimensions comptables similaires, définissez l’option sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="02dfe-118">To group only transactions that have similar ledger dimensions, set the option to **No**.</span></span>
3. <span data-ttu-id="02dfe-119">Sélectionnez **Inclure les clients avec des transactions de débit en cours** pour sélectionner les clients qui ont des montants débiteurs non réglés.</span><span class="sxs-lookup"><span data-stu-id="02dfe-119">Select **Include customers with outstanding debit transactions** to select customers who have unsettled debit amounts.</span></span>
4. <span data-ttu-id="02dfe-120">Pour rembourser des comptes clients spécifiques, sur l’organisateur **Enregistrements à inclure**, sélectionnez **Filtrer**, puis spécifiez les comptes clients dans la requête.</span><span class="sxs-lookup"><span data-stu-id="02dfe-120">To reimburse specific customer accounts, on the **Records to include** FastTab, select **Filter**, and then specify the customer accounts in the query.</span></span>

    <span data-ttu-id="02dfe-121">Les montants de crédit sont transférés vers les comptes fournisseur des clients et sont traités comme des paiements ordinaires.</span><span class="sxs-lookup"><span data-stu-id="02dfe-121">The credit amounts are transferred to the vendor accounts of the customers and are processed as ordinary payments.</span></span> <span data-ttu-id="02dfe-122">Si un client n’a pas de compte fournisseur, un compte fournisseur occasionnel est créé automatiquement pour le client.</span><span class="sxs-lookup"><span data-stu-id="02dfe-122">If a customer doesn't have a vendor account, a one-time vendor account is automatically created for the customer.</span></span>

5. <span data-ttu-id="02dfe-123">Pour afficher les opérations de remboursement qui ont été créées, utilisez l’état **Remboursement** (**Comptabilité client \> Demandes de renseignements et rapports \> Rapport de remboursement**).</span><span class="sxs-lookup"><span data-stu-id="02dfe-123">To view the reimbursement transactions that were created, use the **Reimbursement** report (**Accounts Receivable \> Inquiries and reports \> Reimbursement report**).</span></span>
6. <span data-ttu-id="02dfe-124">Dans Comptabilité fournisseur, créez un paiement pour les factures fournisseur créées par le processus de remboursement.</span><span class="sxs-lookup"><span data-stu-id="02dfe-124">In Accounts payable, create a payment for the vendor invoices that were created by the reimbursement process.</span></span> <span data-ttu-id="02dfe-125">Pour plus d’informations sur la façon de payer les fournisseurs, voir [Aperçu du paiement du fournisseur](../accounts-payable/Vendor-payments-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="02dfe-125">For information about how to pay vendors, see [Vendor payment overview](../accounts-payable/Vendor-payments-workspace.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]