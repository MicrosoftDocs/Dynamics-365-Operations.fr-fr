---
title: Rembourser les clients
description: Cet article explique la création des transactions de remboursement pour un groupe de clients. Si un client a un solde créditeur, vous pouvez le rembourser pour le montant du solde.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 36e7e684e207e13baffa7eefd13e8e4a29d99914
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549650"
---
# <a name="reimburse-customers"></a><span data-ttu-id="45247-104">Rembourser les clients</span><span class="sxs-lookup"><span data-stu-id="45247-104">Reimburse customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="45247-105">Cet article explique la création des transactions de remboursement pour un groupe de clients.</span><span class="sxs-lookup"><span data-stu-id="45247-105">This article explains how to create reimbursement transactions for a group of customers.</span></span> <span data-ttu-id="45247-106">Si un client a un solde créditeur, vous pouvez le rembourser pour le montant du solde.</span><span class="sxs-lookup"><span data-stu-id="45247-106">If a customer has a credit balance, you can reimburse the customer for the amount of the balance.</span></span> 

<span data-ttu-id="45247-107">Le tableau suivant indique la configuration requise qui doit être en place avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="45247-107">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="45247-108">Logiciel requis</span><span class="sxs-lookup"><span data-stu-id="45247-108">Prerequisite</span></span>                                                            | <span data-ttu-id="45247-109">Description</span><span class="sxs-lookup"><span data-stu-id="45247-109">Description</span></span>                                                                                                                                                                                 |
|-------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="45247-110">Spécification du montant minimal de remboursement pour l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="45247-110">Specify the minimum reimbursement amount for the legal entity.</span></span>          | <span data-ttu-id="45247-111">Dans la page **Paramètres de comptabilité client**, dans la zone **Général**, dans le champ **Remboursement minimal**, entrez le montant minimal qui peut être remboursé des trop-perçus client.</span><span class="sxs-lookup"><span data-stu-id="45247-111">On the **Accounts receivable parameters** page, in the **General** area, in the **Minimum reimbursement** field, enter the minimum amount that can be reimbursed for customer overpayments.</span></span> |
| <span data-ttu-id="45247-112">Facultatif : ajoutez un compte fournisseur à chaque client qui peut être remboursé.</span><span class="sxs-lookup"><span data-stu-id="45247-112">Optional: Add a vendor account to each customer that can be reimbursed.</span></span> | <span data-ttu-id="45247-113">Sur la page **Client**, dans l'organisateur **Détails divers**, dans le champ **Compte fournisseur**, sélectionnez le compte fournisseur pour le client.</span><span class="sxs-lookup"><span data-stu-id="45247-113">On the **Customers** page, on the **Miscellaneous details** FastTab, in the **Vendor account** field, select the vendor account for the customer.</span></span>                                           |

<span data-ttu-id="45247-114">Lorsque vous créez des transactions de remboursement, une facture fournisseur est créée pour le montant du solde créditeur.</span><span class="sxs-lookup"><span data-stu-id="45247-114">When you create reimbursement transactions, a vendor invoice is created for the amount of the credit balance.</span></span> <span data-ttu-id="45247-115">Le processus de remboursement permet de supprimer le solde créditeur du compte client et crée un solde dû pour le compte fournisseur correspondant au client.</span><span class="sxs-lookup"><span data-stu-id="45247-115">The reimbursement process removes the credit balance for the customer account and creates a balance due for the vendor account that corresponds to the customer.</span></span>

1.  <span data-ttu-id="45247-116">Dans Comptabilité client, exécutez le processus **Remboursement**.</span><span class="sxs-lookup"><span data-stu-id="45247-116">In Accounts receivable, run the **Reimbursement** process.</span></span>
2.  <span data-ttu-id="45247-117">Utilisez l'une des procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="45247-117">Follow one of these steps:</span></span>
    -   <span data-ttu-id="45247-118">Pour rembourser des comptes client spécifiques, cliquez sur **Sélectionner** et spécifiez les comptes client dans la requête.</span><span class="sxs-lookup"><span data-stu-id="45247-118">To reimburse specific customer accounts, click **Select**, and specify the customer accounts in the query.</span></span>
    -   <span data-ttu-id="45247-119">Pour rembourser tous les comptes client, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="45247-119">To reimburse all customer accounts, click **OK**.</span></span>

    <span data-ttu-id="45247-120">Les montants de crédit sont transférés vers les comptes fournisseur des clients et sont traités comme des paiements ordinaires.</span><span class="sxs-lookup"><span data-stu-id="45247-120">The credit amounts are transferred to the vendor accounts of the customers and are processed as ordinary payments.</span></span> <span data-ttu-id="45247-121">Si un client n'a pas de compte fournisseur, un compte fournisseur occasionnel est créé automatiquement pour le client.</span><span class="sxs-lookup"><span data-stu-id="45247-121">If a customer doesn't have a vendor account, a one-time vendor account is automatically created for the customer.</span></span>
3.  <span data-ttu-id="45247-122">Pour afficher les transactions de remboursement créées, utilisez la page **Remboursement**.</span><span class="sxs-lookup"><span data-stu-id="45247-122">To view the reimbursement transactions that were created, use the **Reimbursement** page.</span></span>
4.  <span data-ttu-id="45247-123">Dans Comptabilité fournisseur, créez un paiement pour les factures fournisseur créées par le processus de remboursement.</span><span class="sxs-lookup"><span data-stu-id="45247-123">In Accounts payable, create a payment for the vendor invoices that were created by the reimbursement process.</span></span>




