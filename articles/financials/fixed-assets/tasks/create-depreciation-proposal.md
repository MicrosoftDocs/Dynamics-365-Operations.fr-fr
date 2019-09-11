---
title: Créer une proposition d'amortissement
description: Cette rubrique décrit le fonctionnement des propositions de traitements par lots d'amortissement et explique comment proposer l'amortissement pour les immobilisations.
author: abruer
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 90c24e9d89c055ea95ca5f25cd85ef4042476a90
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867605"
---
# <a name="create-a-depreciation-proposal"></a><span data-ttu-id="2b7df-103">Créer une proposition d'amortissement</span><span class="sxs-lookup"><span data-stu-id="2b7df-103">Create a depreciation proposal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2b7df-104">Cette rubrique décrit le fonctionnement des propositions de traitements par lots d'amortissement et explique comment proposer l'amortissement pour les immobilisations.</span><span class="sxs-lookup"><span data-stu-id="2b7df-104">This topic describes how depreciation batch proposals work and explains how to propose depreciation for fixed assets.</span></span> <span data-ttu-id="2b7df-105">La société fictive USMF et le rôle de comptable sont cités en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="2b7df-105">This task uses the USMF demo company and the accountant role.</span></span>


## <a name="create-a-depreciation-proposal"></a><span data-ttu-id="2b7df-106">Créer une proposition d'amortissement</span><span class="sxs-lookup"><span data-stu-id="2b7df-106">Create a depreciation proposal</span></span>
1. <span data-ttu-id="2b7df-107">Dans le volet de navigation, accédez à **Modules > Immobilisations > Entrées de journal > Créer une proposition d'amortissement**.</span><span class="sxs-lookup"><span data-stu-id="2b7df-107">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Create depreciation proposal**.</span></span>
2. <span data-ttu-id="2b7df-108">Dans le champ **Nom de journal**, sélectionnez une option dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="2b7df-108">In the **Name of journal** field, select an option from the drop-down menu.</span></span>
3. <span data-ttu-id="2b7df-109">Entrez une date dans le champ **Date de fin**.</span><span class="sxs-lookup"><span data-stu-id="2b7df-109">In the **To date** field, enter a date.</span></span>

    - <span data-ttu-id="2b7df-110">Sélectionnez l'option **Cumuler l'amortissement** pour synthétiser les amortissements mensuels dans une ligne de journal.</span><span class="sxs-lookup"><span data-stu-id="2b7df-110">Select the **Summarize depreciation** option to summarize monthly depreciations into one journal line.</span></span>  
    - <span data-ttu-id="2b7df-111">Par exemple, si la valeur de date de fin correspond au 31 mars 2015, la description suivante est générée : « Amortissement depuis le 31 janvier 2015 ».</span><span class="sxs-lookup"><span data-stu-id="2b7df-111">For example, if the To date value is March 31, 2015, the following description is generated: “Depreciation since January 31, 2015.”</span></span> <span data-ttu-id="2b7df-112">Le champ **Date** sur les lignes de journal proposées est alors défini sur le 31 mars 2015.</span><span class="sxs-lookup"><span data-stu-id="2b7df-112">The **Date** field on the proposed journal lines is then set to March 31, 2015.</span></span>  
    - <span data-ttu-id="2b7df-113">La proposition d'amortissement peut être filtrée par actif, par groupe d'actifs, ou par d'autres critères à l'aide de l'option **Filtre**.</span><span class="sxs-lookup"><span data-stu-id="2b7df-113">The depreciation proposal can be filtered by asset, asset group, or other criteria using the **Filter** option.</span></span>  
    - <span data-ttu-id="2b7df-114">Lorsque vous utilisez l'écran **Créer des propositions d'acquisition ou d'amortissement pour des immobilisations**, vous pouvez proposer l'amortissement en traitements par lots.</span><span class="sxs-lookup"><span data-stu-id="2b7df-114">When you use the **Create acquisition or depreciation proposals for fixed assets** form, you can propose depreciation in batches.</span></span> <span data-ttu-id="2b7df-115">Ceci est recommandé pour les plus grandes propositions qui vont utiliser plus de ressources système.</span><span class="sxs-lookup"><span data-stu-id="2b7df-115">This is recommended for larger proposals that will use more system resources.</span></span> <span data-ttu-id="2b7df-116">Si vous sélectionnez l'option de traitement par lots, vous pouvez toujours effectuer d'autres tâches pendant ce temps.</span><span class="sxs-lookup"><span data-stu-id="2b7df-116">If you select the batch option, you can still complete other tasks during that time.</span></span> <span data-ttu-id="2b7df-117">Lorsque vous proposez l'amortissement de cette manière, l'amortissement est calculé pour les modèles de valeur pour les immobilisations.</span><span class="sxs-lookup"><span data-stu-id="2b7df-117">When you propose depreciation in this way, depreciation is calculated for value models for fixed assets.</span></span>  

4. <span data-ttu-id="2b7df-118">Sélectionnez **Créer un journal**.</span><span class="sxs-lookup"><span data-stu-id="2b7df-118">Select **Create journal**.</span></span>

## <a name="review-depreciation-entries"></a><span data-ttu-id="2b7df-119">Passer en revue les entrées d'amortissement</span><span class="sxs-lookup"><span data-stu-id="2b7df-119">Review depreciation entries</span></span>
1. <span data-ttu-id="2b7df-120">Dans le volet de navigation, accédez à **Modules > Immobilisations > Entrées de journal > Journal des immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="2b7df-120">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="2b7df-121">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2b7df-121">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="2b7df-122">Sélectionnez **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="2b7df-122">Select **Lines**.</span></span>
4. <span data-ttu-id="2b7df-123">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="2b7df-123">Select **Post**.</span></span>

