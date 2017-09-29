---
title: "Explorateur de comptabilité source"
description: "Cet article fournit des informations sur l'explorateur de comptabilité source, que vous pouvez utiliser pour l'analyse détaillée d'informations sources à l'origine des écritures comptables."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 3f5ed28400f333776ce4a5de47ce52aed49094e3
ms.contentlocale: fr-fr
ms.lasthandoff: 06/29/2017


---

# <a name="accounting-source-explorer"></a><span data-ttu-id="fb455-103">Explorateur de comptabilité source</span><span class="sxs-lookup"><span data-stu-id="fb455-103">Accounting source explorer</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="fb455-104">Cet article fournit des informations sur l'explorateur de comptabilité source, que vous pouvez utiliser pour l'analyse détaillée d'informations sources à l'origine des écritures comptables.</span><span class="sxs-lookup"><span data-stu-id="fb455-104">This article provides information about Accounting source explorer, which you can use for detailed analysis of the source information behind general ledger accounting entries.</span></span>

<span data-ttu-id="fb455-105">L'explorateur de comptabilité source est une nouvelle page qui affiche les informations source.</span><span class="sxs-lookup"><span data-stu-id="fb455-105">Accounting source explorer is a new page that shows source information.</span></span> <span data-ttu-id="fb455-106">Vous pouvez utiliser l'explorateur de comptabilité source comme un outil autonome ou pour analyser les détails à l'origine des écritures comptables.</span><span class="sxs-lookup"><span data-stu-id="fb455-106">You can use Accounting source explorer either as a stand-alone tool or to analyze the details behind general ledger accounting entries.</span></span> <span data-ttu-id="fb455-107">Par exemple, vous pouvez utiliser l'explorateur de comptabilité source pour obtenir les informations sources les plus détaillées pour un solde dans la balance comptable ou pour une transaction de N° document.</span><span class="sxs-lookup"><span data-stu-id="fb455-107">For example, you can use Accounting source explorer to get the most detailed source information for a balance in Trail balance or for a voucher transaction.</span></span> <span data-ttu-id="fb455-108">Vous pouvez ensuite utiliser la fonctionnalité d'exportation de MS Excel pour découper davantage les informations dans Microsoft Excel (par exemple, dans un tableau croisé dynamique ou un état de tableau croisé dynamique).</span><span class="sxs-lookup"><span data-stu-id="fb455-108">You can then use the Export to MS Excel feature to further slice and dice the information in Microsoft Excel (for example, in a PivotTable or on a PivotTable report).</span></span>

<span data-ttu-id="fb455-109">L'explorateur de comptabilité source affiche toujours le même montant total par compte général comme la comptabilité l'indique (par exemple, dans la balance comptable).</span><span class="sxs-lookup"><span data-stu-id="fb455-109">Accounting source explorer always shows the same total amount per ledger account as General ledger shows (for example, in Trial balance).</span></span> <span data-ttu-id="fb455-110">Comme dans la balance comptable, vous pouvez afficher les segments dans des colonnes distinctes.</span><span class="sxs-lookup"><span data-stu-id="fb455-110">As in Trial balance, you can display segments in separate columns.</span></span> <span data-ttu-id="fb455-111">Il suffit de sélectionner un ensemble de dimensions financières approprié.</span><span class="sxs-lookup"><span data-stu-id="fb455-111">Just select the appropriate financial dimension set.</span></span> 

<span data-ttu-id="fb455-112">Vous pouvez utiliser les paramètres pour définir un intervalle de dates pour l'analyse.</span><span class="sxs-lookup"><span data-stu-id="fb455-112">You can use parameters to define a date interval for the analysis.</span></span> <span data-ttu-id="fb455-113">Cette fonction est semblable également à la fonctionnalité de la balance comptable.</span><span class="sxs-lookup"><span data-stu-id="fb455-113">This functionality also resembles the functionality in Trial balance.</span></span>

<span data-ttu-id="fb455-114">Pour tous les documents qui utilisent la structure de document source, l'explorateur de comptabilité source affiche des informations supplémentaires, selon les répartitions comptables et, le cas échéant, les répartitions comptables du projet.</span><span class="sxs-lookup"><span data-stu-id="fb455-114">For all documents that use the source document framework, Accounting source explorer shows additional information, based on accounting distributions and, if applicable, project accounting distributions.</span></span> <span data-ttu-id="fb455-115">Ces informations incluent le type de montant en devises, le projet, l'activité, la catégorie et la propriété de ligne.</span><span class="sxs-lookup"><span data-stu-id="fb455-115">This information includes the monetary amount type, project, activity, category, and line property.</span></span> <span data-ttu-id="fb455-116">Voici quelques exemples de l'analyse que vous pouvez effectuer :</span><span class="sxs-lookup"><span data-stu-id="fb455-116">Here are some examples of the analysis that you can do:</span></span>

-   <span data-ttu-id="fb455-117">Écarts entre les commandes fournisseur et les factures fournisseur, car chaque écart est représenté par un montant en devises type, telles que l'écart de frais</span><span class="sxs-lookup"><span data-stu-id="fb455-117">Variances between purchase orders and vendor invoices, because each variance is represented by a monetary amount type, such as charge variance</span></span>
-   <span data-ttu-id="fb455-118">Heures et dépenses facturables/non facturables par projet, unité commerciale et compte principal</span><span class="sxs-lookup"><span data-stu-id="fb455-118">Billable versus non-billable hours and expenses per project, business unit, and main account</span></span>

<span data-ttu-id="fb455-119">Pour les documents sources qui utilisent le concept des identités de référence de document source, l'explorateur de comptabilité source indique bien plus de détails, tels que le client, fournisseur, le collaborateur, le produit, la quantité, le texte d'unité, et descriptions.</span><span class="sxs-lookup"><span data-stu-id="fb455-119">For source documents that use the source document reference identities concept, Accounting source explorer shows even more details, such as the customer, vendor, worker, product, quantity, unit text, and descriptions.</span></span> <span data-ttu-id="fb455-120">Voici quelques exemples de l'analyse que vous pouvez effectuer :</span><span class="sxs-lookup"><span data-stu-id="fb455-120">Here are some examples of the analysis that you can do:</span></span>

-   <span data-ttu-id="fb455-121">Frais d'hôtel par unité commerciale et marque d'hôtel pour une période fiscale, selon les états de dépenses</span><span class="sxs-lookup"><span data-stu-id="fb455-121">Hotel expenses per business unit and hotel brand for a fiscal period, based on expense reports</span></span>
-   <span data-ttu-id="fb455-122">Remises par fournisseur, produit, département</span><span class="sxs-lookup"><span data-stu-id="fb455-122">Discounts per vendor, product, department</span></span>

<span data-ttu-id="fb455-123">Pour ces documents, vous pouvez également accéder au document source réel de l'explorateur de comptabilité source.</span><span class="sxs-lookup"><span data-stu-id="fb455-123">For these documents, you can also navigate to the actual source document from Accounting source explorer.</span></span>




