---
title: Calcul TDS sur les transactions intersociétés
description: Cette rubrique décrit le processus utilisé pour calculer la taxe déduite à la source (TDS) sur les transactions intersociétés par phases.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 0e304747cc93bfe0a39beababc3182ca14664b11
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023241"
---
# <a name="tds-calculation-on-intercompany-transactions"></a><span data-ttu-id="dcfb0-103">Calcul TDS sur les transactions intersociétés</span><span class="sxs-lookup"><span data-stu-id="dcfb0-103">TDS calculation on intercompany transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dcfb0-104">Cette rubrique décrit le processus utilisé pour calculer la taxe déduite à la source (TDS) sur les transactions intersociétés par phases.</span><span class="sxs-lookup"><span data-stu-id="dcfb0-104">This topic describes the process that is used to calculate Tax Deducted at Source (TDS) on intercompany transactions in phases.</span></span>

<span data-ttu-id="dcfb0-105">Lorsqu'une commande fournisseur ou une commande client intersociétés est créée, le groupe TDS par défaut défini pour le client ou le fournisseur est utilisé pour calculer le montant TDS.</span><span class="sxs-lookup"><span data-stu-id="dcfb0-105">When an intercompany purchase order or sales order is created, the default TDS group that is defined for the customer or vendor is used to calculate the TDS amount.</span></span> <span data-ttu-id="dcfb0-106">Le montant TDS est imputé aux comptes récupérables ou à payer après la validation de la facture.</span><span class="sxs-lookup"><span data-stu-id="dcfb0-106">The TDS amount is posted to the recoverable or payable accounts after the invoice is posted.</span></span>

<span data-ttu-id="dcfb0-107">Une commande client intersociétés ou une commande fournisseur est automatiquement créée pour la commande fournisseur ou la commande client d'origine.</span><span class="sxs-lookup"><span data-stu-id="dcfb0-107">An intercompany sales order or purchase order is automatically created for the original purchase order or sales order.</span></span> <span data-ttu-id="dcfb0-108">Le groupe TDS par défaut est affiché sur la commande intersociétés, afin que TDS puisse être calculé.</span><span class="sxs-lookup"><span data-stu-id="dcfb0-108">The default TDS group is shown on the intercompany order, so that TDS can be calculated.</span></span> <span data-ttu-id="dcfb0-109">Vous pouvez modifier le groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="dcfb0-109">You can change the TDS group.</span></span> <span data-ttu-id="dcfb0-110">La facture ne peut être validée que si le montant net de la facture de la commande intersociétés créée automatiquement correspond au montant net de la facture de la commande d'origine.</span><span class="sxs-lookup"><span data-stu-id="dcfb0-110">The invoice can be posted only if the net invoice amount on the intercompany order that is automatically created matches the net invoice amount on the original order.</span></span> <span data-ttu-id="dcfb0-111">(Le montant net est le montant de la facture après déduction de TDS.)</span><span class="sxs-lookup"><span data-stu-id="dcfb0-111">(The net amount is the invoice amount after TDS is deducted.)</span></span>

<span data-ttu-id="dcfb0-112">Par exemple, une facture de vente est créée pour 50 000 et le groupe TDS **10 %** y est attaché.</span><span class="sxs-lookup"><span data-stu-id="dcfb0-112">For example, a sales invoice is created for 50,000, and the **10%** TDS group is attached to it.</span></span> <span data-ttu-id="dcfb0-113">Le montant de la facture validée est de 45 000 et le montant TDS validé pour la facture de vente est de 5 000.</span><span class="sxs-lookup"><span data-stu-id="dcfb0-113">The posted invoice amount is 45,000, and the posted TDS amount for the sales invoice is 5,000.</span></span> <span data-ttu-id="dcfb0-114">Une commande fournisseur est automatiquement créée pour la commande client intersociétés et le groupe TDS **10 %** y est attaché.</span><span class="sxs-lookup"><span data-stu-id="dcfb0-114">A purchase order is automatically created for the intercompany sales order, and the  **10%** TDS group is attached to it.</span></span> <span data-ttu-id="dcfb0-115">Si vous modifiez le groupe TDS à **15%**, vous ne pouvez pas valider la facture, car le montant net de la facture de la commande client intersociétés créée automatiquement ne correspond pas au montant net de la facture de la commande client d'origine.</span><span class="sxs-lookup"><span data-stu-id="dcfb0-115">If you change the TDS group to **15%**, you can't post the invoice, because the net invoice amount of the intercompany sales order that was automatically created doesn't match the net invoice amount of the original sales order.</span></span>

<span data-ttu-id="dcfb0-116">Un journal des paiements créé pour une facture intersociétés est automatiquement validé.</span><span class="sxs-lookup"><span data-stu-id="dcfb0-116">A payment journal that is created for an intercompany invoice is automatically posted.</span></span> <span data-ttu-id="dcfb0-117">Ce journal des paiements ne peut être validé que si le montant net du paiement qu'il contient correspond au montant net du paiement indiqué dans le journal des paiements d'origine.</span><span class="sxs-lookup"><span data-stu-id="dcfb0-117">That payment journal can be posted only if the net payment amount on it matches the net payment amount on the original payment journal.</span></span>
