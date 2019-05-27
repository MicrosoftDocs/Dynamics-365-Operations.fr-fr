---
title: Registres dérivés
description: Cet article fournit une vue d'ensemble de la fonctionnalité de registre déduit.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3401
ms.assetid: 862d6450-187b-497f-9822-cce45f2c65a9
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 153b6437205d5a849fa6a90c0d3b9f3d51dd6768
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557357"
---
# <a name="derived-books"></a><span data-ttu-id="fdcc1-103">Registres dérivés</span><span class="sxs-lookup"><span data-stu-id="fdcc1-103">Derived books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fdcc1-104">Cet article fournit une vue d'ensemble de la fonctionnalité de registre déduit.</span><span class="sxs-lookup"><span data-stu-id="fdcc1-104">This article provides an overview of derived book functionality.</span></span>

<span data-ttu-id="fdcc1-105">L'objectif des registres déduits consiste à simplifier la validation des transactions de registre des immobilisations prévue à intervalles réguliers.</span><span class="sxs-lookup"><span data-stu-id="fdcc1-105">The purpose of derived books is to simplify the posting of fixed asset book transactions that are planned for regular intervals.</span></span>  <span data-ttu-id="fdcc1-106">Vous choisissez un registre comme registre principal.</span><span class="sxs-lookup"><span data-stu-id="fdcc1-106">You choose one book as the primary book.</span></span> <span data-ttu-id="fdcc1-107">Il s'agit généralement du registre qui utilisé pour l'amortissement comptable.</span><span class="sxs-lookup"><span data-stu-id="fdcc1-107">This usually is the book that is used for accounting depreciation.</span></span> <span data-ttu-id="fdcc1-108">Vous l'associez ensuite à d'autres registre qui sont paramétrés pour valider des transactions dans les mêmes intervalles que le registre principal.</span><span class="sxs-lookup"><span data-stu-id="fdcc1-108">You then attach to it other books that are set up to post transactions in the same intervals as the primary book.</span></span> <span data-ttu-id="fdcc1-109">Les registres d'amortissement des taxes sont souvent paramétrés comme des registres déduits.</span><span class="sxs-lookup"><span data-stu-id="fdcc1-109">Tax depreciation books are often set up as derived books.</span></span> 

<span data-ttu-id="fdcc1-110">Les transactions les plus courantes à paramétrer pour validation dans des registres déduits sont les acquisitions, les ajustements d'acquisition et les cessions.</span><span class="sxs-lookup"><span data-stu-id="fdcc1-110">The most common transactions to set up to post to derived books are acquisitions, acquisition adjustments, and disposals.</span></span> 

## <a name="example"></a><span data-ttu-id="fdcc1-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="fdcc1-111">Example</span></span>

<span data-ttu-id="fdcc1-112">Le registre B et le registre C sont paramétrés comme des registres déduits pour le registre A pour le type de transaction d'acquisition.</span><span class="sxs-lookup"><span data-stu-id="fdcc1-112">Book B and book C are set up as derived books for book A for the Acquisition transaction type.</span></span> <span data-ttu-id="fdcc1-113">Dans le registre A, vous entrez une transaction d'acquisition de 1 500,00 EUR pour les actifs 123.</span><span class="sxs-lookup"><span data-stu-id="fdcc1-113">In book A, you enter an acquisition transaction for asset 123 for 1,500.00.</span></span> 

<span data-ttu-id="fdcc1-114">Lors de sa validation, une transaction d'acquisition est générée et validée dans les actifs 123 pour le registre B et dans les actifs 123 pour le registre C, pour une valeur de 1 500,00.</span><span class="sxs-lookup"><span data-stu-id="fdcc1-114">When the transaction is posted, an acquisition transaction is generated and posted in asset 123 for book B and in asset 123 for book C for 1,500.00.</span></span> <span data-ttu-id="fdcc1-115">Lorsque vous préparez les transactions du registre principal pour validation dans le journal des immobilisations, vous pouvez également afficher et modifier les transactions des registres déduits.</span><span class="sxs-lookup"><span data-stu-id="fdcc1-115">When you prepare the transactions of the primary book for posting in the fixed asset journal, you can also view and modify the transactions of the derived books.</span></span> <span data-ttu-id="fdcc1-116">Si vous préparez les transactions du registre principal dans un autre journal, vous ne pouvez pas afficher les transactions de la valeur déduite.</span><span class="sxs-lookup"><span data-stu-id="fdcc1-116">If you prepare the primary book transactions in another journal, the transactions of the derived value are not displayed.</span></span> <span data-ttu-id="fdcc1-117">Toutefois, elles sont validées dans les comptes et les couches de validations appropriés lorsque vous validez les transactions du registre principal.</span><span class="sxs-lookup"><span data-stu-id="fdcc1-117">However, they are posted to the appropriate accounts and posting layers when you post the primary book transactions.</span></span>

> [!NOTE]                                                                                                                               
> <span data-ttu-id="fdcc1-118">Les registre paramétrés pour valider les transactions à des intervalles autres que ceux du registre principal doivent être associés aux immobilisations en tant que registres distincts et non comme registres déduits.</span><span class="sxs-lookup"><span data-stu-id="fdcc1-118">Books that are set up to post transactions at intervals other than the primary book intervals must be attached to the fixed asset as separate books and not as derived books.</span></span>  

<span data-ttu-id="fdcc1-119">Pour plus d'informations, voir [Validation avec des registres déduits](post-derived-value-models.md).</span><span class="sxs-lookup"><span data-stu-id="fdcc1-119">For more information, see [Posting with derived books](post-derived-value-models.md).</span></span>



