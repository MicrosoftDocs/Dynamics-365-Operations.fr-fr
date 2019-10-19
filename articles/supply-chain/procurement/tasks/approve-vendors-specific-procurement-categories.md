---
title: Approuver les fournisseurs pour des catégories d'approvisionnement spécifiques
description: Cette rubrique explique comment approuver des fournisseurs pour des catégories d'approvisionnement spécifiques dans Dynamics 365 Supply Chain Management.
author: mkirknel
manager: AnnBe
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e47124e22dd6c0e756bf42429327254f966b48a2
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2018087"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a><span data-ttu-id="3bcf5-103">Approuver les fournisseurs pour des catégories d'approvisionnement spécifiques</span><span class="sxs-lookup"><span data-stu-id="3bcf5-103">Approve vendors for specific procurement categories</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3bcf5-104">Cette rubrique explique comment approuver des fournisseurs pour des catégories d'approvisionnement spécifiques dans Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-104">This topic explains how to approve vendors for specific procurement categories in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="3bcf5-105">Quand une demande d'achat est créée, il peut y avoir une condition pour choisir un fournisseur agréé ou préféré, selon la façon dont les politiques d'achat sont définies.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-105">When a purchase requisition is created, there may be a requirement to select an approved or preferred vendor, depending on how the purchasing policies are set up.</span></span> <span data-ttu-id="3bcf5-106">Cette procédure vous montre comment spécifier qu'un vendeur est agréé ou préféré pour une catégorie spécifique d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-106">This procedure shows you how to specify that a vendor is approved or preferred for a specific procurement category.</span></span> <span data-ttu-id="3bcf5-107">Cette tâche est généralement effectuée par un professionnel de l'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-107">This task would usually be carried out by a procurement professional.</span></span> <span data-ttu-id="3bcf5-108">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-108">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="3bcf5-109">Dans le volet de navigation, accédez à **Modules > Approvisionnements > Fournisseurs > Tous les fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-109">In the navigation pane, go to **Modules > Procurement and sourcing > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="3bcf5-110">Choisissez le fournisseur que vous voulez définir en tant que fournisseur agréé ou préféré pour une catégorie.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-110">Select the vendor that you want to set as an approved or preferred vendor for a category.</span></span>
3. <span data-ttu-id="3bcf5-111">Dans le volet Actions, sélectionnez **Général**.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-111">On the Action Pane, select **General**.</span></span>
4. <span data-ttu-id="3bcf5-112">Sélectionnez **Catégories**.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-112">Select **Categories**.</span></span>
5. <span data-ttu-id="3bcf5-113">Sélectionnez **Ajouter une catégorie**.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-113">Select **Add category**.</span></span>
6. <span data-ttu-id="3bcf5-114">Dans le champ **Catégorie**, sélectionnez **BUREAU ET ACCESSOIRES DE BUREAU (BUREAU ET ACCESSOIRES DE BUREAU)**.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-114">In the **Category** field, select **OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES)**.</span></span>
7. <span data-ttu-id="3bcf5-115">Dans le champ **Statut de catégorie de fournisseur**, sélectionnez **Préféré**.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-115">In the **Vendor category status** field, select **Preferred**.</span></span> <span data-ttu-id="3bcf5-116">Il est possible de spécifier plus d'un fournisseur préféré pour une catégorie.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-116">It’s possible to specify more than one preferred vendor for a category.</span></span>  
8. <span data-ttu-id="3bcf5-117">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-117">Select **Save**.</span></span>
9. <span data-ttu-id="3bcf5-118">Dans le volet de navigation, accédez à **Modules > Approvisionnements > Catégories d'approvisionnement**.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-118">In the navigation pane, go to **Modules > Procurement and sourcing > Procurement categories**.</span></span>
10. <span data-ttu-id="3bcf5-119">Dans l'arborescence, sélectionnez **CATÉGORIES D'APPROVISIONNEMENT DE L'ENTREPRISE\BUREAU ET ACCESSOIRES DE BUREAU**.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-119">In the tree, select **CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES**.</span></span>
11. <span data-ttu-id="3bcf5-120">Développez la section **Fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-120">Expand the **Vendors** section.</span></span> <span data-ttu-id="3bcf5-121">Vérifiez si le fournisseur que vous avez choisi apparaît en tant que fournisseur préféré pour la catégorie d'accessoires de bureau et de bureau.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-121">Check if the vendor that you selected appears as a preferred vendor for the Office and desk accessories category.</span></span> <span data-ttu-id="3bcf5-122">Si vous exécutez cette procédure en tant que guide de tâche, vous devrez peut-être cliquer sur le bouton **Déverrouiller** pour pouvoir faire descendre l'écran jusqu'à la liste de fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-122">If you’re running this procedure as a task guide, you may have to select the **Unlock** button to be able to scroll down to the list of vendors.</span></span>  <span data-ttu-id="3bcf5-123">Il est également possible d'ajouter les fournisseurs préférés et agréés à cette page.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-123">It’s also possible to add preferred and approved vendors on this page.</span></span>  
12. <span data-ttu-id="3bcf5-124">Dans l'arborescence, développez **BUREAU ET ACCESSOIRES DE BUREAU** et sélectionnez **Ciseaux**.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-124">In the tree, expand **OFFICE AND DESK ACCESSORIES** and select **Scissors**.</span></span>
13. <span data-ttu-id="3bcf5-125">Choisissez **Non** dans le champ **Hériter des fournisseurs de la catégorie parente :**.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-125">Select **No** in the **Inherit vendors from parent category:** field.</span></span>
14. <span data-ttu-id="3bcf5-126">Choisissez **Oui** dans le champ **Hériter des fournisseurs de la catégorie parente :**.</span><span class="sxs-lookup"><span data-stu-id="3bcf5-126">Select **Yes** in the **Inherit vendors from parent category:** field.</span></span>

