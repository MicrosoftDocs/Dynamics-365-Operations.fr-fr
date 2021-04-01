---
title: Créer une méthode d’attribution pour les demandes de devis
description: Cette procédure vous indique comment créer une méthode d’attribution de score.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQScoringMethod
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba3f0b2be16c02129616025c0ee6258996189c6a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211812"
---
# <a name="create-a-scoring-method-for-rfqs"></a><span data-ttu-id="40ca7-103">Créer une méthode d’attribution pour les demandes de devis</span><span class="sxs-lookup"><span data-stu-id="40ca7-103">Create a scoring method for RFQs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="40ca7-104">Cette procédure vous indique comment créer une méthode d’attribution de score.</span><span class="sxs-lookup"><span data-stu-id="40ca7-104">This procedure shows you how to create a scoring method.</span></span> <span data-ttu-id="40ca7-105">Une méthode d’attribution de score est un ensemble de critères qui peut être employé pour comparer les offres qui sont envoyées en réponse à un appel d’offre.</span><span class="sxs-lookup"><span data-stu-id="40ca7-105">A scoring method is a set of criteria that can be used to compare bids that are sent in reply to a request for quotation (RFQ).</span></span> <span data-ttu-id="40ca7-106">Par exemple, vous pouvez souhaiter évaluer une performance passée d’un fournisseur, ou évaluer si la société est écologique ou un bon collaborateur, ou comparer des offres selon le prix.</span><span class="sxs-lookup"><span data-stu-id="40ca7-106">For example, you might want to rate a vendor on past performance, or rate whether the company is environmentally friendly or a good collaborator, or you might want to compare bids based on price.</span></span> <span data-ttu-id="40ca7-107">La méthode d’attribution de score peut être associée à un type de sollicitation comme méthode d’attribution de score par défaut pour les demandes de devis de ce type.</span><span class="sxs-lookup"><span data-stu-id="40ca7-107">The scoring method can be associated with a solicitation type as the default scoring method for RFQs of that type.</span></span> <span data-ttu-id="40ca7-108">Ces tâches sont généralement effectuées par un responsable des achats.</span><span class="sxs-lookup"><span data-stu-id="40ca7-108">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="40ca7-109">Vous pouvez utiliser cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="40ca7-109">You can use this procedure in demo data company USMF or on your own data.</span></span>

1. <span data-ttu-id="40ca7-110">Allez dans Approvisionnements > Paramétrage > Appel d’offre > Méthode d’attribution de score.</span><span class="sxs-lookup"><span data-stu-id="40ca7-110">Go to Procurement and sourcing > Setup > Request for quotation > Scoring method.</span></span>
2. <span data-ttu-id="40ca7-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="40ca7-111">Click New.</span></span>
3. <span data-ttu-id="40ca7-112">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="40ca7-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="40ca7-113">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="40ca7-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="40ca7-114">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="40ca7-114">Click Save.</span></span>
6. <span data-ttu-id="40ca7-115">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="40ca7-115">Click New.</span></span>
7. <span data-ttu-id="40ca7-116">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="40ca7-116">In the Name field, type a value.</span></span>
8. <span data-ttu-id="40ca7-117">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="40ca7-117">In the Description field, type a value.</span></span>
    * <span data-ttu-id="40ca7-118">Cette description est indiquée avec le nom de méthode d’attribution de score quand une méthode d’attribution de score est choisie pour un appel d’offre.</span><span class="sxs-lookup"><span data-stu-id="40ca7-118">This description is shown along with the scoring method name when a scoring method is selected for an RFQ.</span></span>  
9. <span data-ttu-id="40ca7-119">Entrez un nombre dans le champ À.</span><span class="sxs-lookup"><span data-stu-id="40ca7-119">In the Range from field, enter a number.</span></span>
    * <span data-ttu-id="40ca7-120">La plage limite ce que le professionnel de l’approvisionnement peut entrer dans comme score.</span><span class="sxs-lookup"><span data-stu-id="40ca7-120">The range limits what the procurement professional can enter as a score.</span></span> <span data-ttu-id="40ca7-121">Quand il y a des critères d’attribution de score multiples sur un appel d’offre, les scores qui ont été entrés sont ajoutés entre eux et la somme est rendue disponible pour permettre aux offres d’être comparées.</span><span class="sxs-lookup"><span data-stu-id="40ca7-121">When there are multiple scoring criteria on an RFQ, the scores that have been entered are added to each other and the sum is made available to allow the bids to be compared.</span></span>  
10. <span data-ttu-id="40ca7-122">Entrez un nombre dans le champ De.</span><span class="sxs-lookup"><span data-stu-id="40ca7-122">In the Range to field, enter a number.</span></span>
11. <span data-ttu-id="40ca7-123">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="40ca7-123">Click New.</span></span>
12. <span data-ttu-id="40ca7-124">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="40ca7-124">In the Name field, type a value.</span></span>
13. <span data-ttu-id="40ca7-125">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="40ca7-125">In the Description field, type a value.</span></span>
14. <span data-ttu-id="40ca7-126">Entrez un nombre dans le champ À.</span><span class="sxs-lookup"><span data-stu-id="40ca7-126">In the Range from field, enter a number.</span></span>
15. <span data-ttu-id="40ca7-127">Entrez un nombre dans le champ De.</span><span class="sxs-lookup"><span data-stu-id="40ca7-127">In the Range to field, enter a number.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]