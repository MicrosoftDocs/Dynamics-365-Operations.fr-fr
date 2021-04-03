---
title: Restreindre la modification des répartitions comptables dans les factures
description: Cette rubrique explique comment exiger que les dimensions financières d’une commande fournisseur (CF) correspondent aux dimensions de la facture fournisseur correspondante.
author: v-kiarnd
manager: AnnBe
ms.date: 10/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.search.industry: public sector
ms.author: v-kiarnd
ms.search.validFrom: 2020-10-15
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 56ad3ac4a883a6b75183f559c4e1f71a5c6a4e44
ms.sourcegitcommit: 88babb2fffe97e93bbde543633fc492120f2a4fc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2021
ms.locfileid: "5555439"
---
# <a name="restrict-editing-of-accounting-distributions-on-invoices"></a><span data-ttu-id="54271-103">Restreindre la modification des répartitions comptables dans les factures</span><span class="sxs-lookup"><span data-stu-id="54271-103">Restrict editing of accounting distributions on invoices</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="54271-104">Cette rubrique explique comment exiger que les dimensions financières d’une commande fournisseur (CF) correspondent aux dimensions de la facture fournisseur correspondante.</span><span class="sxs-lookup"><span data-stu-id="54271-104">This topic explains how to require that the financial dimensions on a purchase order (PO) match the dimensions on the corresponding vendor invoice.</span></span> <span data-ttu-id="54271-105">Vous pouvez configurer des dimensions financières spécifiques qui doivent correspondre entre une CF et une facture créée à partir de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="54271-105">You can set up specific financial dimensions that must match between a PO and an invoice that is created from it.</span></span> <span data-ttu-id="54271-106">Par exemple, vous pouvez exiger que toutes les dimensions financières correspondent entre les CF et les factures.</span><span class="sxs-lookup"><span data-stu-id="54271-106">For example, you can require that all financial dimensions match between POs and invoices.</span></span> <span data-ttu-id="54271-107">Sur les factures associées à une CF, vous ne pouvez pas modifier les comptes généraux sur les lignes de détail de la facture afin qu’ils diffèrent des comptes qui ont été saisis sur les lignes de CF.</span><span class="sxs-lookup"><span data-stu-id="54271-107">On invoices that are associated with a PO, you can't change the general ledger accounts on the invoice detail lines so that they differ from the accounts that were entered on the PO lines.</span></span>

## <a name="set-up-locked-financial-dimensions"></a><span data-ttu-id="54271-108">Paramétrer des dimensions financières verrouillées</span><span class="sxs-lookup"><span data-stu-id="54271-108">Set up locked financial dimensions</span></span>

<span data-ttu-id="54271-109">Suivez ces étapes pour définir les dimensions financières qui doivent correspondre entre une CF et les factures associées.</span><span class="sxs-lookup"><span data-stu-id="54271-109">Follow these steps to define the financial dimensions that must match between a PO and related invoices.</span></span>

1. <span data-ttu-id="54271-110">Allez dans **Comptabilité fournisseur \> Paramètres \> Paramètres de la comptabilité fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="54271-110">Go to **Accounts payable \> Setup \> Accounts payable parameters**.</span></span>
2. <span data-ttu-id="54271-111">Sur la page **Activer le contrôle de rapprochement de factures**, sélectionnez **Validation rapprochement de facture/CF**.</span><span class="sxs-lookup"><span data-stu-id="54271-111">On the **Accounts payable parameters** page, select **PO/Invoice matching validation**.</span></span>
3. <span data-ttu-id="54271-112">Cochez la case **Correspondance requise** pour les dimensions qui doivent correspondre.</span><span class="sxs-lookup"><span data-stu-id="54271-112">Select the **Matching required** check box for the dimensions that must match.</span></span> <span data-ttu-id="54271-113">Toutes les dimensions financières mises en place sur la page **Dimensions financières** sont disponibles pour la sélection.</span><span class="sxs-lookup"><span data-stu-id="54271-113">All the financial dimensions that are set up on the **Financial dimensions** page are available for selection.</span></span>
4. <span data-ttu-id="54271-114">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="54271-114">Select **Close**.</span></span>

## <a name="work-with-locked-financial-dimensions-on-an-invoice"></a><span data-ttu-id="54271-115">Travailler avec des dimensions financières verrouillées sur une facture</span><span class="sxs-lookup"><span data-stu-id="54271-115">Work with locked financial dimensions on an invoice</span></span>

<span data-ttu-id="54271-116">Lorsque vous créez une facture fournisseur à partir d’une CF, vous ne pouvez pas modifier les dimensions financières verrouillées.</span><span class="sxs-lookup"><span data-stu-id="54271-116">When you create a vendor invoice from a PO, you can't edit the locked financial dimensions.</span></span> <span data-ttu-id="54271-117">Si vous essayez de modifier une dimension financière verrouillée, vous recevez un message d’erreur et toute la chaîne de dimension financière revient à la chaîne d’origine.</span><span class="sxs-lookup"><span data-stu-id="54271-117">If you try to edit a locked financial dimension, you receive an error message, and the whole financial dimension string reverts to the original string.</span></span>

<span data-ttu-id="54271-118">Vous pouvez afficher des dimensions financières pour la facture.</span><span class="sxs-lookup"><span data-stu-id="54271-118">You can view financial dimensions for the invoice.</span></span>

1. <span data-ttu-id="54271-119">Accédez à **Comptabilité fournisseur \> Commun \> Factures fournisseur \> Factures fournisseur en attente**.</span><span class="sxs-lookup"><span data-stu-id="54271-119">Go to **Accounts payable \> Common \> Vendor invoices \> Pending vendor invoices**.</span></span>
2. <span data-ttu-id="54271-120">Ouvrez la facture.</span><span class="sxs-lookup"><span data-stu-id="54271-120">Open the invoice.</span></span>
3. <span data-ttu-id="54271-121">Sur la page **Facture fournisseur**, sur le raccourci **Lignes**, sélectionnez **Finances \> Distribuer le montant**.</span><span class="sxs-lookup"><span data-stu-id="54271-121">On the **Vendor invoice** page, on the **Lines** FastTab, select **Financials \> Distribute amount**.</span></span>

> [!NOTE]
> <span data-ttu-id="54271-122">Les dimensions financières ne sont pas verrouillées sur les lignes ajoutées manuellement à une facture et non basées sur la CF.</span><span class="sxs-lookup"><span data-stu-id="54271-122">Financial dimensions aren't locked on lines that are manually added to an invoice and not based on PO.</span></span> <span data-ttu-id="54271-123">Dans ce cas, vous pouvez modifier les dimensions financières de la facture selon vos besoins, jusqu’à ce que la facture soit validée.</span><span class="sxs-lookup"><span data-stu-id="54271-123">In this case, you can change the financial dimensions on the invoice as you require, until the invoice is posted.</span></span>
