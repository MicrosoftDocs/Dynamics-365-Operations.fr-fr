---
title: Définitions de validation
description: Cet article fournit des informations sur les définitions de validation, et comment les définir et les lier. Pour les types et les documents de validation pris en charge, vous pouvez utiliser des définitions de validation au lieu de profils de validation pour classer les comptes principaux et les dimensions financières dans les écritures comptables.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans, LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15741
ms.assetid: 1495e7e0-2e39-464c-8da9-f55b1ca1c6bb
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1a8dc69ac668da46ccaa470a4e0e7dcb2ce4d0ac
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835020"
---
# <a name="posting-definitions"></a><span data-ttu-id="15685-104">Définitions de validation</span><span class="sxs-lookup"><span data-stu-id="15685-104">Posting definitions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="15685-105">Cet article fournit des informations sur les définitions de validation, et comment les définir et les lier.</span><span class="sxs-lookup"><span data-stu-id="15685-105">This article provides information about posting definitions, and how to define and link them.</span></span> <span data-ttu-id="15685-106">Pour les types et les documents de validation pris en charge, vous pouvez utiliser des définitions de validation au lieu de profils de validation pour classer les comptes principaux et les dimensions financières dans les écritures comptables.</span><span class="sxs-lookup"><span data-stu-id="15685-106">For supported posting types and documents, you can use posting definitions instead of posting profiles to classify main accounts and financial dimensions on accounting entries.</span></span>

<span data-ttu-id="15685-107">Pour les types et les documents de validation pris en charge, vous pouvez utiliser des définitions de validation au lieu de profils de validation pour classer les comptes principaux et les dimensions financières dans les écritures comptables.</span><span class="sxs-lookup"><span data-stu-id="15685-107">For supported posting types and documents, you can use posting definitions instead of posting profiles to classify main accounts and financial dimensions on accounting entries.</span></span> <span data-ttu-id="15685-108">Vous pouvez afficher les documents et les types de validation pris en charge dans la page **Définitions de validation de transaction**.</span><span class="sxs-lookup"><span data-stu-id="15685-108">You can view the supported documents and posting types on the **Transaction posting definitions** page.</span></span> 

<span data-ttu-id="15685-109">Pour commencer à utiliser les définitions de validation, sélectionnez l'option **Utiliser les définitions de validation** dans la page **Paramètres de comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="15685-109">To start using posting definitions, select the **Use posting definitions** option on the **General ledger parameters** page.</span></span> <span data-ttu-id="15685-110">Même si vous utilisez les définitions de validation, vous devez toujours définir les profils de validation des entrées d'origine et des types et documents de validation non pris en charge.</span><span class="sxs-lookup"><span data-stu-id="15685-110">Even when you use posting definitions, you must still define posting profiles for the originating entries and non-supported posting types and documents.</span></span> 

<span data-ttu-id="15685-111">Vous devez utiliser les définitions de validation pour activer la comptabilité d'engagement pour les commandes fournisseur et de la comptabilité d'engagement préalable pour les demandes d'achat.</span><span class="sxs-lookup"><span data-stu-id="15685-111">You must use posting definitions in order to enable encumbrance accounting for purchase orders and pre-encumbrance accounting for purchase requisitions.</span></span>

## <a name="defining-posting-definitions"></a><span data-ttu-id="15685-112">Définir les définitions de validation</span><span class="sxs-lookup"><span data-stu-id="15685-112">Defining posting definitions</span></span>
<span data-ttu-id="15685-113">Utilisez la page**Définitions de validation** pour spécifier les critères de correspondance et définir les entrées qui doivent être générées lorsqu'une correspondance se produit.</span><span class="sxs-lookup"><span data-stu-id="15685-113">Use the **Posting definitions** page to specify the match criteria and define the entries that should be generated when a match occurs.</span></span> <span data-ttu-id="15685-114">Les critères de correspondance sont évalués pour les entrées d'origine comme répartitions comptables.</span><span class="sxs-lookup"><span data-stu-id="15685-114">The match criteria are evaluated for the originating entries as accounting distributions.</span></span> 

<span data-ttu-id="15685-115">Dans la page **Définitions de validation**, vous pouvez aussi affecter des ordres de priorité aux lignes de saisie pour contrôler l'ordre dans lequel celles-ci sont évaluées.</span><span class="sxs-lookup"><span data-stu-id="15685-115">On the **Posting definitions** page, you can also assign priority numbers to entry lines to control the order in which the lines are evaluated.</span></span> <span data-ttu-id="15685-116">Les lignes ayant le plus petit numéro de priorité sont évaluées en premier.</span><span class="sxs-lookup"><span data-stu-id="15685-116">The lines that have the lowest priority number are evaluated first.</span></span> <span data-ttu-id="15685-117">Par exemple, les lignes qui ont la priorité 1 sont évaluées, puis les lignes qui ont la priorité 2, etc.</span><span class="sxs-lookup"><span data-stu-id="15685-117">For example, all lines that have a priority of 1 are evaluated, and then lines that have a priority of 2, and so on.</span></span> <span data-ttu-id="15685-118">Lorsqu'une correspondance est trouvée, les autres critères de correspondance sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="15685-118">When a match is found, the other match criteria are ignored.</span></span> <span data-ttu-id="15685-119">En outre, seuls les critères du groupe qui correspondent à la transaction d'origine créent les entrées générées.</span><span class="sxs-lookup"><span data-stu-id="15685-119">Additionally, only the criteria in the group that match the originating transaction create generated entries.</span></span> 

<span data-ttu-id="15685-120">Vous pouvez valider vos définitions de validation à l'aide de l'assistant **Test de définition de validation**.</span><span class="sxs-lookup"><span data-stu-id="15685-120">You can validate your posting definitions by using the **Test posting definition** wizard.</span></span> <span data-ttu-id="15685-121">Après avoir défini un exemple d'entrée d'origine pour une définition de validation, vous verrez les entrées générées.</span><span class="sxs-lookup"><span data-stu-id="15685-121">After you define a sample originating entry for a posting definition, you'll see the generated entries.</span></span> 

<span data-ttu-id="15685-122">Vous pouvez utiliser les versions de définition de validation avec des dates d'effet.</span><span class="sxs-lookup"><span data-stu-id="15685-122">You can use posting definition versions together with effective dates.</span></span> <span data-ttu-id="15685-123">Par exemple, vous pouvez créer une version future d'une définition de validation pour effectuer une validation dans un autre compte général dans un nouvel exercice.</span><span class="sxs-lookup"><span data-stu-id="15685-123">For example, you can create a future version of a posting definition to post to a different ledger account in a new fiscal year.</span></span> 

<span data-ttu-id="15685-124">Utilisez la page **Définitions de validation de transaction** pour affecter les définitions de validation aux types de transactions.</span><span class="sxs-lookup"><span data-stu-id="15685-124">Use the **Transaction posting definitions** page to assign posting definitions to transaction types.</span></span>

## <a name="linking-posting-definitions"></a><span data-ttu-id="15685-125">Lier les définitions de validation</span><span class="sxs-lookup"><span data-stu-id="15685-125">Linking posting definitions</span></span>
<span data-ttu-id="15685-126">Vous pouvez créer un lien entre deux définitions de validation lors de leur création.</span><span class="sxs-lookup"><span data-stu-id="15685-126">You can link from one posting definition to another when you create posting definitions.</span></span> <span data-ttu-id="15685-127">Les critères de la définition liée sont alors pris en compte en plus des critères de la définition de validation actuelle.</span><span class="sxs-lookup"><span data-stu-id="15685-127">The criteria for the definition that you linked to are then considered in addition to the criteria for the current posting definition.</span></span> <span data-ttu-id="15685-128">Cette fonctionnalité vous fait gagner du temps car vous n'avez pas besoin d'entrer de nouveau les critères dans l'organisateur **Entrées** de la page **Définitions de validation** pour la définition de validation actuelle si vous avez déjà entré ces lignes pour une autre définition.</span><span class="sxs-lookup"><span data-stu-id="15685-128">This feature helps save you time, because you don't have to reenter criteria on the **Entries** FastTab on the **Posting definitions** page for the current posting definition if you already entered those lines for another definition.</span></span> 

<span data-ttu-id="15685-129">Dans les diagrammes ou les tableaux, incluez les liens à utiliser.</span><span class="sxs-lookup"><span data-stu-id="15685-129">In the diagrams or tables, include any links that you might use.</span></span> <span data-ttu-id="15685-130">Pour éviter des conflits avec la définition de validation actuelle, vérifiez que les lignes des définitions de validation liées sont uniques.</span><span class="sxs-lookup"><span data-stu-id="15685-130">To avoid conflicts with the current posting definition, make sure that the lines in any posting definitions that you link to are unique.</span></span> 

<span data-ttu-id="15685-131">Les restrictions suivantes s'appliquent lorsque vous créez des liens dans les définitions de validation :</span><span class="sxs-lookup"><span data-stu-id="15685-131">The following restrictions apply when you create links in posting definitions:</span></span>

-   <span data-ttu-id="15685-132">Une définition de validation donnée peut inclure un lien vers une autre définition de validation, ou être la cible d'un lien à partir d'une autre définition de validation.</span><span class="sxs-lookup"><span data-stu-id="15685-132">A given posting definition can either link to another posting definition or be linked to from another posting definition, but not both.</span></span> <span data-ttu-id="15685-133">Toutefois, une définition de validation peut pointer vers plusieurs définitions de validation.</span><span class="sxs-lookup"><span data-stu-id="15685-133">However, a posting definition can link to multiple posting definitions.</span></span>
-   <span data-ttu-id="15685-134">Vous pouvez paramétrer des liens uniquement pour les définitions de validation appartenant au même module.</span><span class="sxs-lookup"><span data-stu-id="15685-134">You can set up links only among posting definitions that are in the same module.</span></span>
-   <span data-ttu-id="15685-135">Vous pouvez affecter une définition de validation à n'importe quel type de transaction, mais ce dernier doit appartenir au même module que la définition de validation.</span><span class="sxs-lookup"><span data-stu-id="15685-135">You can assign a posting definition to any transaction type, but the transaction type must be in the same module as the posting definition.</span></span> <span data-ttu-id="15685-136">Utilisez la page **Définitions de validation de transaction** pour afficher dans quel module se trouve un type de transaction.</span><span class="sxs-lookup"><span data-stu-id="15685-136">Use the **Transaction posting definitions** page to see what module a transaction type is in.</span></span>


<span data-ttu-id="15685-137">Pour plus d'informations, voir [Exemples de définitions de validation](example-posting-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="15685-137">For more information, see [Posting definitions examples](example-posting-definitions.md).</span></span> 


