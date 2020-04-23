---
title: Rapprochement du fret dans la gestion du transport
description: Cette rubrique décrit le processus de rapprochement du fret.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSInvoiceTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0e1680572f1ba9816c9ec45ef52498cab1f45247
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206217"
---
# <a name="reconcile-freight-in-transportation-management"></a><span data-ttu-id="0f20f-103">Rapprochement du fret dans la gestion du transport</span><span class="sxs-lookup"><span data-stu-id="0f20f-103">Reconcile freight in transportation management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0f20f-104">Cette rubrique décrit le processus de rapprochement du fret.</span><span class="sxs-lookup"><span data-stu-id="0f20f-104">This topic describes the freight reconciliation process.</span></span>

<span data-ttu-id="0f20f-105">Le rapprochement du fret peut être effectué manuellement, ou il peut être configuré pour se produire automatiquement.</span><span class="sxs-lookup"><span data-stu-id="0f20f-105">Freight reconciliation can be done manually, or it can be set up to occur automatically.</span></span> <span data-ttu-id="0f20f-106">Pour utiliser le rapprochement du fret automatique, vous devez paramétrer les données principales d'audit pour définir des critères qui déterminent les factures de transport qui sont automatiquement mis en correspondance.</span><span class="sxs-lookup"><span data-stu-id="0f20f-106">To use automatic freight reconciliation, you must set up an audit master where you can define criteria that determine which freight bills are matched automatically.</span></span>

## <a name="the-freight-reconciliation-process"></a><span data-ttu-id="0f20f-107">Processus de rapprochement du fret</span><span class="sxs-lookup"><span data-stu-id="0f20f-107">The freight reconciliation process</span></span>
<span data-ttu-id="0f20f-108">Les frais de transport sont calculés par le moteur de frais qui est associé au transporteur correspondant.</span><span class="sxs-lookup"><span data-stu-id="0f20f-108">Freight rates are calculated by the rate engine that is associated with the relevant shipping carrier.</span></span> <span data-ttu-id="0f20f-109">Lorsque vous confirmez une charge, une facture de fret est générée et les taux de fret sont transférés.</span><span class="sxs-lookup"><span data-stu-id="0f20f-109">When a load is confirmed, a freight bill is generated, and the freight rates are transferred to it.</span></span> <span data-ttu-id="0f20f-110">Les taux de fret sont répartis en tant que frais divers sur le document source correspondant (commande, commande client et/ou ordre de transfert), en fonction de la configuration qui est utilisée pour le processus de facturation régulier.</span><span class="sxs-lookup"><span data-stu-id="0f20f-110">The freight rates are apportioned as miscellaneous charges to the relevant source document (purchase order, sales order, and/or transfer order), depending on the setup that is used for the regular billing process.</span></span> <span data-ttu-id="0f20f-111">Le processus de rapprochement des frais de transport (aussi appelé processus de mise en correspondance) peut commencer dès la réception de la facture de transport du transporteur.</span><span class="sxs-lookup"><span data-stu-id="0f20f-111">The freight reconciliation process (which is also known as the matching process) can start as soon as the freight invoice arrives from the shipping carrier.</span></span> <span data-ttu-id="0f20f-112">La facture peut être reçue par voie électronique ou sur papier.</span><span class="sxs-lookup"><span data-stu-id="0f20f-112">The invoice can be received electronically or on paper.</span></span> <span data-ttu-id="0f20f-113">Si la facture est reçue sur papier, vous pouvez générer une facture électronique à l’aide de la facture de transport en tant que modèle.</span><span class="sxs-lookup"><span data-stu-id="0f20f-113">If the invoice is received on paper, you can generate an electronic invoice by using the freight bill as a template.</span></span> 

<span data-ttu-id="0f20f-114">[![Processus de rapprochement du fret](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span><span class="sxs-lookup"><span data-stu-id="0f20f-114">[![Freight reconcilation process](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span></span>

## <a name="manual-reconciliation"></a><span data-ttu-id="0f20f-115">Rapprochement manuel</span><span class="sxs-lookup"><span data-stu-id="0f20f-115">Manual reconciliation</span></span>
<span data-ttu-id="0f20f-116">Si vous rapprochez manuellement le fret, vous devez faire correspondre chaque ligne de facture avec la ou les lignes de facturation de fret pour la charge en cours de facturation.</span><span class="sxs-lookup"><span data-stu-id="0f20f-116">If you're reconciling freight manually, you must match each invoice line with the freight bill line or lines for the load that is being invoiced.</span></span> <span data-ttu-id="0f20f-117">Vous effectuez cette correspondance sur la page **Facture des frais de transport et rapprochement de factures**.</span><span class="sxs-lookup"><span data-stu-id="0f20f-117">You do this matching on the **Freight bill and invoice matching** page.</span></span> <span data-ttu-id="0f20f-118">Si le montant de la ligne de facture ne correspond pas au montant de la facture de transport, vous devez sélectionner un motif de rapprochement de la différence.</span><span class="sxs-lookup"><span data-stu-id="0f20f-118">If the amount on the invoice line doesn’t match the freight bill amount, you must select a reconciliation reason for the difference.</span></span> <span data-ttu-id="0f20f-119">S’il existe plusieurs motifs pour le rapprochement, vous pouvez répartir le montant qui ne correspond pas entre eux.</span><span class="sxs-lookup"><span data-stu-id="0f20f-119">If there are multiple reasons for reconciliation, you can split the unmatched amount across them.</span></span> <span data-ttu-id="0f20f-120">Le motif du rapprochement détermine comment les montants de différence sont validés dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="0f20f-120">The reconciliation reason determines how the difference amounts are posted in the general ledger.</span></span> <span data-ttu-id="0f20f-121">Lorsque le rapprochement de l’intégralité du montant de la facture est comptabilisé, il est soumis pour approbation, et ensuite le journal est validé.</span><span class="sxs-lookup"><span data-stu-id="0f20f-121">When the reconciliation of the whole invoice amount is accounted for, it's submitted for approval, and then the journal is posted.</span></span> <span data-ttu-id="0f20f-122">La figure suivante indique comment générer une facture de transport et exécuter le rapprochement du fret.</span><span class="sxs-lookup"><span data-stu-id="0f20f-122">The following illustration shows how to generate a freight invoice and do freight reconciliation.</span></span> 
<span data-ttu-id="0f20f-123">[![Tâches de rapprochement des frais de transport](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span><span class="sxs-lookup"><span data-stu-id="0f20f-123">[![Freight reconcilation tasks](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span></span>
## <a name="automatic-reconciliation"></a><span data-ttu-id="0f20f-124">Rapprochement automatique</span><span class="sxs-lookup"><span data-stu-id="0f20f-124">Automatic reconciliation</span></span>
<span data-ttu-id="0f20f-125">Pour utiliser le rapprochement automatique, vous devez spécifier la planification du rapprochement et les factures et les transporteurs à utiliser.</span><span class="sxs-lookup"><span data-stu-id="0f20f-125">To use automatic reconciliation, you must specify the schedule for reconciliation, and the invoices and shipping carriers to use.</span></span> <span data-ttu-id="0f20f-126">La mise en correspondance des lignes de facture et des factures de transport s’effectue en fonction du paramétrage des données principales d’audit et du type de facture de transport.</span><span class="sxs-lookup"><span data-stu-id="0f20f-126">The matching of the invoice lines and freight bills is done according to the setup of the audit master and freight bill type.</span></span> <span data-ttu-id="0f20f-127">Après avoir exécuté le rapprochement automatique, vous devez gérer toutes les factures que le système ne peut pas faire correspondre.</span><span class="sxs-lookup"><span data-stu-id="0f20f-127">After you run the automatic reconciliation, you must handle any invoices that the system can't match.</span></span> <span data-ttu-id="0f20f-128">Vous devez traiter ces factures manuellement avant de pouvoir valider toutes les factures à des fins de paiement.</span><span class="sxs-lookup"><span data-stu-id="0f20f-128">You must then process these invoices manually before you can post all the invoices for payment.</span></span>



