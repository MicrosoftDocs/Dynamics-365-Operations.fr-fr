---
title: "Résolution des écarts lors du rapprochement des totaux de factures"
description: "Vous pouvez utiliser le rapprochement des totaux de facture pour vous assurer que l'écart entre les montants totaux de la facture et les montants attendus n'est pas supérieur à l'écart acceptable."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTotalPriceTolerance
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 48f7b8a7c1bb081b6cdc012ebe3668655b17f174
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="resolve-discrepancies-during-invoice-totals-matching"></a><span data-ttu-id="1fa3a-103">Résolution des écarts lors du rapprochement des totaux de factures</span><span class="sxs-lookup"><span data-stu-id="1fa3a-103">Resolve discrepancies during invoice totals matching</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1fa3a-104">Un type de validation du rapprochement de factures est le rapprochement des totaux de facture.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-104">One type of invoice matching validation is invoice totals matching.</span></span> <span data-ttu-id="1fa3a-105">Pour spécifier que le système doit effectuer le rapprochement des totaux de facture, sur la page **Paramètres de la comptabilité fournisseur**, sous l'onglet **Contrôle de la facture**, définissez l'option **Mettre en correspondance les totaux de la facture** à **Oui**.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-105">To specify that the system should perform invoice totals matching, on the **Accounts payable parameters** page, on the **Invoice validation** tab, set the **Match invoice totals** option **Yes**.</span></span> 

<span data-ttu-id="1fa3a-106">Vous pouvez utiliser le rapprochement des totaux de facture pour vous assurer que l'écart entre les montants totaux de la facture et les montants attendus n'est pas supérieur à l'écart acceptable.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-106">You can use invoice totals matching to help guarantee that total invoice amounts don't deviate from expected amounts by more than an acceptable variance.</span></span> <span data-ttu-id="1fa3a-107">Six totaux sont comparés sur la page **Détails de rapprochement de factures totales**.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-107">Six totals are compared on the **Invoice totals matching details** page.</span></span> <span data-ttu-id="1fa3a-108">Si l'un de ces totaux dévie du total correspondant prévu de la commande fournisseur, un écart de rapprochement est signalé.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-108">If any one of the totals deviates from the expected corresponding purchase order total, a matching discrepancy is flagged.</span></span> 

<span data-ttu-id="1fa3a-109">Pour réviser la facture qui comporte les écarts de rapprochement des totaux, dans l'espace de travail **Saisie de facture fournisseur**, cliquez sur la vignette **Factures en attente**.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-109">To review the invoice that has the totals matching discrepancies, in the **Vendor invoice entry** workspace, click the **Pending invoices** tile.</span></span> <span data-ttu-id="1fa3a-110">Ensuite, dans le volet Actions, sous l'onglet **Revoir**, cliquez sur **Mise en correspondance des détails**..</span><span class="sxs-lookup"><span data-stu-id="1fa3a-110">Then, on the Action Pane, on the **Review** tab, click **Matching details**.</span></span> <span data-ttu-id="1fa3a-111">Si des écarts de rapprochement ont été détectés, des icônes d'avertissement s'affichent en regard du montant de la facture.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-111">If matching discrepancies have been detected, warning icons appear next to the invoice amount.</span></span> <span data-ttu-id="1fa3a-112">Vous pouvez afficher plus de détails sur les totaux en affichant les détails de rapprochement des totaux de facture.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-112">You can view more detail about the totals by viewing the invoice totals matching details.</span></span> 

<span data-ttu-id="1fa3a-113">Après avoir identifié un écart, vous devrez peut-être prendre contact avec votre fournisseur si vous pensez que les informations de la facture sont erronées.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-113">After you identify a discrepancy, you might have to contact the vendor if you think that the information on the invoice is incorrect.</span></span> <span data-ttu-id="1fa3a-114">Selon l'accord trouvé avec votre fournisseur, vous pouvez alors effectuer l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1fa3a-114">Depending on the resulting agreement with the vendor, you can then take one of these actions:</span></span>

-   <span data-ttu-id="1fa3a-115">Accepter la différence de prix et valider la facture avec les écarts de rapprochement.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-115">Accept the price difference, and post the invoice that has matching discrepancies.</span></span> <span data-ttu-id="1fa3a-116">Votre système peut être paramétré pour exiger l'approbation avant d'être en mesure de valider s'il existe des écarts de rapprochement.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-116">Your system might be set up to require approval before it can post if there are matching discrepancies.</span></span> <span data-ttu-id="1fa3a-117">Dans ce cas, vous devez approuver l'écart de rapprochement et vous pouvez également saisir un commentaire d'approbation.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-117">In this case, you must approve the matching discrepancy and can optionally enter an approval comment.</span></span> <span data-ttu-id="1fa3a-118">Vous pouvez alors décider de valider la facture.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-118">You can then select to post the invoice.</span></span>
-   <span data-ttu-id="1fa3a-119">Corriger le montant de la facture et valider cette dernière.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-119">Revise the invoice amount to the expected amount, and post the invoice.</span></span>
-   <span data-ttu-id="1fa3a-120">Demander au fournisseur un crédit total et une nouvelle facture corrigée.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-120">Request a full credit and a new, corrected invoice from the vendor.</span></span>

<span data-ttu-id="1fa3a-121">Pour plus d'informations, voir [Rechercher ou résoudre les exceptions](tasks/research-resolve-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="1fa3a-121">For more information, see [Research or resolve exceptions](tasks/research-resolve-exceptions.md).</span></span>



