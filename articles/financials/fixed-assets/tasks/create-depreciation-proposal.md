---
title: Créer une proposition d'amortissement
description: Cette procédure décrit le fonctionnement des propositions de traitements par lots d'amortissement et explique comment proposer l'amortissement pour les immobilisations.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d11554ee5f26ef5a85e799194d2f75757a31c254
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "361289"
---
# <a name="create-depreciation-proposal"></a><span data-ttu-id="fd698-103">Créer une proposition d'amortissement</span><span class="sxs-lookup"><span data-stu-id="fd698-103">Create depreciation proposal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fd698-104">Cette procédure décrit le fonctionnement des propositions de traitements par lots d'amortissement et explique comment proposer l'amortissement pour les immobilisations.</span><span class="sxs-lookup"><span data-stu-id="fd698-104">This procedure describes how depreciation batch proposals work and explains how to propose depreciation for fixed assets.</span></span> <span data-ttu-id="fd698-105">La société fictive USMF et le rôle de comptable sont cités en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="fd698-105">This task uses the USMF demo company and the accountant role.</span></span>


## <a name="create-depreciation-proposal"></a><span data-ttu-id="fd698-106">Créer une proposition d'amortissement</span><span class="sxs-lookup"><span data-stu-id="fd698-106">Create depreciation proposal</span></span>
1. <span data-ttu-id="fd698-107">Accédez à Immobilisations > Entrées de journal > Créer une proposition d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="fd698-107">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="fd698-108">Dans le champ Nom de journal, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fd698-108">In the Name of journal field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="fd698-109">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fd698-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="fd698-110">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="fd698-110">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="fd698-111">Sélectionnez l'option Cumuler l'amortissement pour synthétiser les amortissements mensuels dans une ligne de journal.</span><span class="sxs-lookup"><span data-stu-id="fd698-111">Select the Summarize depreciation option to summarize monthly depreciations into one journal line.</span></span>  
    * <span data-ttu-id="fd698-112">Par exemple, si la valeur de date de fin correspond au 31 mars 2015, la description suivante est générée : « Amortissement depuis le 31 janvier 2015 ».</span><span class="sxs-lookup"><span data-stu-id="fd698-112">For example, if the To date value is March 31, 2015, the following description is generated: “Depreciation since January 31, 2015.”</span></span> <span data-ttu-id="fd698-113">Le champ Date sur les lignes de journal proposées est alors défini sur le 31 mars 2015.</span><span class="sxs-lookup"><span data-stu-id="fd698-113">The Date field on the proposed journal lines is then set to March 31, 2015.</span></span>  
    * <span data-ttu-id="fd698-114">La proposition d'amortissement peut être filtrée par actif, par groupe d'immobilisations, ou par d'autres critères à l'aide de l'option Filtre.</span><span class="sxs-lookup"><span data-stu-id="fd698-114">The depreciation proposal can be filtered by asset, asset group, or other criteria using the Filter option.</span></span>  
    * <span data-ttu-id="fd698-115">Lorsque vous utilisez l'écran Créer des propositions d'acquisition ou d'amortissement pour des immobilisations, vous pouvez proposer l'amortissement en traitements par lots.</span><span class="sxs-lookup"><span data-stu-id="fd698-115">When you use the Create acquisition or depreciation proposals for fixed assets form, you can propose depreciation in batches.</span></span> <span data-ttu-id="fd698-116">Ceci est recommandé pour les plus grandes propositions qui vont utiliser plus de ressources système.</span><span class="sxs-lookup"><span data-stu-id="fd698-116">This is recommended for larger proposals that will use more system resources.</span></span> <span data-ttu-id="fd698-117">Si vous sélectionnez l'option de traitement par lots, vous pouvez toujours effectuer d'autres tâches pendant ce temps.</span><span class="sxs-lookup"><span data-stu-id="fd698-117">If you select the batch option, you can still complete other tasks during that time.</span></span> <span data-ttu-id="fd698-118">Lorsque vous proposez l'amortissement de cette manière, l'amortissement est calculé pour les modèles de valeur pour les immobilisations.</span><span class="sxs-lookup"><span data-stu-id="fd698-118">When you propose depreciation in this way, depreciation is calculated for value models for fixed assets.</span></span>  
5. <span data-ttu-id="fd698-119">Cliquez sur Créer un journal.</span><span class="sxs-lookup"><span data-stu-id="fd698-119">Click Create journal.</span></span>

## <a name="review-depreciation-entries"></a><span data-ttu-id="fd698-120">Passer en revue les entrées d'amortissement</span><span class="sxs-lookup"><span data-stu-id="fd698-120">Review depreciation entries</span></span>
1. <span data-ttu-id="fd698-121">Accédez à Immobilisations > Entrées de journal > Journal des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="fd698-121">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="fd698-122">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fd698-122">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="fd698-123">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="fd698-123">Click Lines.</span></span>
4. <span data-ttu-id="fd698-124">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="fd698-124">Click Post.</span></span>

