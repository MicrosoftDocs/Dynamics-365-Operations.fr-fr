--- 
title: "Créer une méthode d'attribution pour les demandes de devis"
description: "Cette procédure vous indique comment créer une méthode d'attribution de score."
author: mkirknel
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchRFQScoringMethod
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 0235723e0e5668c53ca6f6ac79732502aeae551a
ms.contentlocale: fr-fr
ms.lasthandoff: 09/11/2018

---
# <a name="create-a-scoring-method-for-rfqs"></a><span data-ttu-id="676fd-103">Créer une méthode d'attribution pour les demandes de devis</span><span class="sxs-lookup"><span data-stu-id="676fd-103">Create a scoring method for RFQs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="676fd-104">Cette procédure vous indique comment créer une méthode d'attribution de score.</span><span class="sxs-lookup"><span data-stu-id="676fd-104">This procedure shows you how to create a scoring method.</span></span> <span data-ttu-id="676fd-105">Une méthode d'attribution de score est un ensemble de critères qui peut être employé pour comparer les offres qui sont envoyées en réponse à un appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="676fd-105">A scoring method is a set of criteria that can be used to compare bids that are sent in reply to a request for quotation (RFQ).</span></span> <span data-ttu-id="676fd-106">Par exemple, vous pouvez souhaiter évaluer une performance passée d'un fournisseur, ou évaluer si la société est écologique ou un bon collaborateur, ou comparer des offres selon le prix.</span><span class="sxs-lookup"><span data-stu-id="676fd-106">For example, you might want to rate a vendor on past performance, or rate whether the company is environmentally friendly or a good collaborator, or you might want to compare bids based on price.</span></span> <span data-ttu-id="676fd-107">La méthode d'attribution de score peut être associée à un type de sollicitation comme méthode d'attribution de score par défaut pour les demandes de devis de ce type.</span><span class="sxs-lookup"><span data-stu-id="676fd-107">The scoring method can be associated with a solicitation type as the default scoring method for RFQs of that type.</span></span> <span data-ttu-id="676fd-108">Ces tâches sont généralement effectuées par un responsable des achats.</span><span class="sxs-lookup"><span data-stu-id="676fd-108">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="676fd-109">Vous pouvez utiliser cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="676fd-109">You can use this procedure in demo data company USMF or on your own data.</span></span>

1. <span data-ttu-id="676fd-110">Allez dans Approvisionnements > Paramétrage > Appel d'offre > Méthode d'attribution de score.</span><span class="sxs-lookup"><span data-stu-id="676fd-110">Go to Procurement and sourcing > Setup > Request for quotation > Scoring method.</span></span>
2. <span data-ttu-id="676fd-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="676fd-111">Click New.</span></span>
3. <span data-ttu-id="676fd-112">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="676fd-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="676fd-113">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="676fd-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="676fd-114">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="676fd-114">Click Save.</span></span>
6. <span data-ttu-id="676fd-115">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="676fd-115">Click New.</span></span>
7. <span data-ttu-id="676fd-116">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="676fd-116">In the Name field, type a value.</span></span>
8. <span data-ttu-id="676fd-117">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="676fd-117">In the Description field, type a value.</span></span>
    * <span data-ttu-id="676fd-118">Cette description est indiquée avec le nom de méthode d'attribution de score quand une méthode d'attribution de score est choisie pour un appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="676fd-118">This description is shown along with the scoring method name when a scoring method is selected for an RFQ.</span></span>  
9. <span data-ttu-id="676fd-119">Entrez un nombre dans le champ À.</span><span class="sxs-lookup"><span data-stu-id="676fd-119">In the Range from field, enter a number.</span></span>
    * <span data-ttu-id="676fd-120">La plage limite ce que le professionnel de l'approvisionnement peut entrer dans comme score.</span><span class="sxs-lookup"><span data-stu-id="676fd-120">The range limits what the procurement professional can enter as a score.</span></span> <span data-ttu-id="676fd-121">Quand il y a des critères d'attribution de score multiples sur un appel d'offre, les scores qui ont été entrés sont ajoutés entre eux et la somme est rendue disponible pour permettre aux offres d'être comparées.</span><span class="sxs-lookup"><span data-stu-id="676fd-121">When there are multiple scoring criteria on an RFQ, the scores that have been entered are added to each other and the sum is made available to allow the bids to be compared.</span></span>  
10. <span data-ttu-id="676fd-122">Entrez un nombre dans le champ De.</span><span class="sxs-lookup"><span data-stu-id="676fd-122">In the Range to field, enter a number.</span></span>
11. <span data-ttu-id="676fd-123">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="676fd-123">Click New.</span></span>
12. <span data-ttu-id="676fd-124">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="676fd-124">In the Name field, type a value.</span></span>
13. <span data-ttu-id="676fd-125">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="676fd-125">In the Description field, type a value.</span></span>
14. <span data-ttu-id="676fd-126">Entrez un nombre dans le champ À.</span><span class="sxs-lookup"><span data-stu-id="676fd-126">In the Range from field, enter a number.</span></span>
15. <span data-ttu-id="676fd-127">Entrez un nombre dans le champ De.</span><span class="sxs-lookup"><span data-stu-id="676fd-127">In the Range to field, enter a number.</span></span>


