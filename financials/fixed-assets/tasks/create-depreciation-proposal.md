--- 
title: "Créer une proposition d'amortissement"
description: "Cette procédure décrit le fonctionnement des propositions de traitements par lots d'amortissement et explique comment proposer l'amortissement pour les immobilisations."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 07d8cf2f1c46b99dfcd1d7c3419fe835f37c5a02
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-depreciation-proposal"></a><span data-ttu-id="29729-103">Créer une proposition d'amortissement</span><span class="sxs-lookup"><span data-stu-id="29729-103">Create a depreciation proposal</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="29729-104">Cette procédure décrit le fonctionnement des propositions de traitements par lots d'amortissement et explique comment proposer l'amortissement pour les immobilisations.</span><span class="sxs-lookup"><span data-stu-id="29729-104">This procedure describes how depreciation batch proposals work and explains how to propose depreciation for fixed assets.</span></span> <span data-ttu-id="29729-105">La société fictive USMF et le rôle de comptable sont cités en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="29729-105">This task uses the USMF demo company and the accountant role.</span></span>


## <a name="create-depreciation-proposal"></a><span data-ttu-id="29729-106">Créer une proposition d'amortissement</span><span class="sxs-lookup"><span data-stu-id="29729-106">Create depreciation proposal</span></span>
1. <span data-ttu-id="29729-107">Accédez à Immobilisations > Entrées de journal > Créer une proposition d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="29729-107">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="29729-108">Dans le champ Nom de journal, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="29729-108">In the Name of journal field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="29729-109">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="29729-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="29729-110">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="29729-110">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="29729-111">Sélectionnez l'option Cumuler l'amortissement pour synthétiser les amortissements mensuels dans une ligne de journal.</span><span class="sxs-lookup"><span data-stu-id="29729-111">Select the Summarize depreciation option to summarize monthly depreciations into one journal line.</span></span>  
    * <span data-ttu-id="29729-112">Par exemple, si la valeur de date de fin correspond au 31 mars 2015, la description suivante est générée : « Amortissement depuis le 31 janvier 2015 ».</span><span class="sxs-lookup"><span data-stu-id="29729-112">For example, if the To date value is March 31, 2015, the following description is generated: “Depreciation since January 31, 2015.”</span></span> <span data-ttu-id="29729-113">Le champ Date sur les lignes de journal proposées est alors défini sur le 31 mars 2015.</span><span class="sxs-lookup"><span data-stu-id="29729-113">The Date field on the proposed journal lines is then set to March 31, 2015.</span></span>  
    * <span data-ttu-id="29729-114">La proposition d'amortissement peut être filtrée par actif, par groupe d'immobilisations, ou par d'autres critères à l'aide de l'option Filtre.</span><span class="sxs-lookup"><span data-stu-id="29729-114">The depreciation proposal can be filtered by asset, asset group, or other criteria using the Filter option.</span></span>  
    * <span data-ttu-id="29729-115">Lorsque vous utilisez l'écran Créer des propositions d'acquisition ou d'amortissement pour des immobilisations, vous pouvez proposer l'amortissement en traitements par lots.</span><span class="sxs-lookup"><span data-stu-id="29729-115">When you use the Create acquisition or depreciation proposals for fixed assets form, you can propose depreciation in batches.</span></span> <span data-ttu-id="29729-116">Ceci est recommandé pour les plus grandes propositions qui vont utiliser plus de ressources système.</span><span class="sxs-lookup"><span data-stu-id="29729-116">This is recommended for larger proposals that will use more system resources.</span></span> <span data-ttu-id="29729-117">Si vous sélectionnez l'option de traitement par lots, vous pouvez toujours effectuer d'autres tâches pendant ce temps.</span><span class="sxs-lookup"><span data-stu-id="29729-117">If you select the batch option, you can still complete other tasks during that time.</span></span> <span data-ttu-id="29729-118">Lorsque vous proposez l'amortissement de cette manière, l'amortissement est calculé pour les modèles de valeur pour les immobilisations.</span><span class="sxs-lookup"><span data-stu-id="29729-118">When you propose depreciation in this way, depreciation is calculated for value models for fixed assets.</span></span>  
5. <span data-ttu-id="29729-119">Cliquez sur Créer un journal.</span><span class="sxs-lookup"><span data-stu-id="29729-119">Click Create journal.</span></span>

## <a name="review-depreciation-entries"></a><span data-ttu-id="29729-120">Passer en revue les entrées d'amortissement</span><span class="sxs-lookup"><span data-stu-id="29729-120">Review depreciation entries</span></span>
1. <span data-ttu-id="29729-121">Accédez à Immobilisations > Entrées de journal > Journal des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="29729-121">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="29729-122">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="29729-122">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="29729-123">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="29729-123">Click Lines.</span></span>
4. <span data-ttu-id="29729-124">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="29729-124">Click Post.</span></span>


