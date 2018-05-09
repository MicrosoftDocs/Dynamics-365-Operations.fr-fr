--- 
title: "Approuver les fournisseurs pour des catégories d'approvisionnement spécifiques"
description: "Quand une demande d'achat est créée, il peut y avoir une condition pour choisir un fournisseur agréé ou préféré, selon la façon dont les politiques d'achat sont définies."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 26aa675e51957596cce9a1147df1fa300fcfe351
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---
# <a name="approve-vendors-for-specific-procurement-categories"></a><span data-ttu-id="fc6d6-103">Approuver les fournisseurs pour des catégories d'approvisionnement spécifiques</span><span class="sxs-lookup"><span data-stu-id="fc6d6-103">Approve vendors for specific procurement categories</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fc6d6-104">Quand une demande d'achat est créée, il peut y avoir une condition pour choisir un fournisseur agréé ou préféré, selon la façon dont les politiques d'achat sont définies.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-104">When a purchase requisition is created, there may be a requirement to select an approved or preferred vendor, depending on how the purchasing policies are set up.</span></span> <span data-ttu-id="fc6d6-105">Cette procédure vous montre comment spécifier qu'un vendeur est agréé ou préféré pour une catégorie spécifique d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-105">This procedure shows you how to specify that a vendor is approved or preferred for a specific procurement category.</span></span> <span data-ttu-id="fc6d6-106">Cette tâche est généralement effectuée par un professionnel de l'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-106">This task would usually be carried out by a procurement professional.</span></span> <span data-ttu-id="fc6d6-107">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-107">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="fc6d6-108">Accédez à Approvisionnements > Fournisseurs > Tous les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-108">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
2. <span data-ttu-id="fc6d6-109">Choisissez le fournisseur que vous voulez définir en tant que fournisseur agréé ou préféré pour une catégorie.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-109">Select the vendor that you want to set as an approved or preferred vendor for a category.</span></span>
3. <span data-ttu-id="fc6d6-110">Cliquez sur Général dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-110">On the Action Pane, click General.</span></span>
4. <span data-ttu-id="fc6d6-111">Cliquez sur Catégories.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-111">Click Categories.</span></span>
5. <span data-ttu-id="fc6d6-112">Cliquez sur Ajouter une catégorie.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-112">Click Add category.</span></span>
6. <span data-ttu-id="fc6d6-113">Dans le champ Catégorie, sélectionnez BUREAU ET ACCESSOIRES DE BUREAU (BUREAU ET ACCESSOIRES DE BUREAU).</span><span class="sxs-lookup"><span data-stu-id="fc6d6-113">In the Category field, select OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES).</span></span>
7. <span data-ttu-id="fc6d6-114">Dans le champ Statut de catégorie de fournisseur, sélectionnez Préféré.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-114">In the Vendor category status field, select 'Preferred'.</span></span>
    * <span data-ttu-id="fc6d6-115">Il est possible de spécifier plus d'un fournisseur préféré pour une catégorie.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-115">It’s possible to specify more than one preferred vendor for a category.</span></span>  
8. <span data-ttu-id="fc6d6-116">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-116">Click Save.</span></span>
9. <span data-ttu-id="fc6d6-117">Accédez à Approvisionnements > Catégories d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-117">Go to Procurement and sourcing > Procurement categories.</span></span>
10. <span data-ttu-id="fc6d6-118">Dans l'arborescence, sélectionnez « CATÉGORIES D'APPROVISIONNEMENT DE L'ENTREPRISE\BUREAU ET ACCESSOIRES DE BUREAU ».</span><span class="sxs-lookup"><span data-stu-id="fc6d6-118">In the tree, select 'CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES'.</span></span>
11. <span data-ttu-id="fc6d6-119">Développez la section Fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-119">Expand the Vendors section.</span></span>
    * <span data-ttu-id="fc6d6-120">Vérifiez si le fournisseur que vous avez choisi apparaît en tant que fournisseur préféré pour la catégorie d'accessoires de bureau et de bureau.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-120">Check if the vendor that you selected  appears as a preferred vendor for the Office and desk accessories category.</span></span> <span data-ttu-id="fc6d6-121">Si vous exécutez cette procédure en tant que guide de tâche, vous devrez peut-être cliquer sur le bouton Déverrouiller pour pouvoir faire descendre l'écran jusqu'à la liste de fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-121">If you’re running this procedure as a task guide, you may have to click the Unlock button to be able to scroll down to the list of vendors.</span></span>  <span data-ttu-id="fc6d6-122">Il est également possible d'ajouter les fournisseurs préférés et agréés à cette page.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-122">It’s also possible to add preferred and approved vendors on this page.</span></span>  
12. <span data-ttu-id="fc6d6-123">Dans l'arborescence, développez BUREAU ET ACCESSOIRES DE BUREAU.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-123">In the tree, expand 'OFFICE AND DESK ACCESSORIES'.</span></span>
13. <span data-ttu-id="fc6d6-124">Dans l'arborescence, sélectionnez Ciseaux.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-124">In the tree, select 'Scissors'.</span></span>
14. <span data-ttu-id="fc6d6-125">Choisissez Non dans le champ Héritez des fournisseurs de la catégorie parent.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-125">Select No in the Inherit vendors from parent category: field.</span></span>
15. <span data-ttu-id="fc6d6-126">Choisissez Oui dans le champ Héritez des fournisseurs de la catégorie parent.</span><span class="sxs-lookup"><span data-stu-id="fc6d6-126">Select Yes in the Inherit vendors from parent category: field.</span></span>


