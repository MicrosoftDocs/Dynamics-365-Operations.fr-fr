--- 
title: "Copier les coproduits à partir d'une version de formule existante"
description: "Cette procédure vous indique comment copier des coproduits à partir d'une version de formule existante vers une autre version de formule pour un produit lancé."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, PmfFormulaCoBy, BOMRouteCopyDialog
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 179c12da0c2ddc7b5e2f2fdddd21168eac121811
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="copy-co-products-from-an-existing-formula-version"></a><span data-ttu-id="89091-103">Copier les coproduits à partir d'une version de formule existante</span><span class="sxs-lookup"><span data-stu-id="89091-103">Copy co-products from an existing formula version</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="89091-104">Cette procédure vous indique comment copier des coproduits à partir d'une version de formule existante vers une autre version de formule pour un produit lancé.</span><span class="sxs-lookup"><span data-stu-id="89091-104">This procedure shows how to copy co-products from an existing formula version to a different formula version for a released product.</span></span> <span data-ttu-id="89091-105">Condition préalable : au moins une version de formule doit être associée à des coproduits.</span><span class="sxs-lookup"><span data-stu-id="89091-105">It is a prerequisite that there is at least one formula version associated with co-products.</span></span> <span data-ttu-id="89091-106">Pour créer cette procédure, la société fictive de démonstration USP2 est utilisée.</span><span class="sxs-lookup"><span data-stu-id="89091-106">The demo data company USP2 is used to create this procedure.</span></span>


## <a name="find-a-released-product"></a><span data-ttu-id="89091-107">Rechercher un produit lancé</span><span class="sxs-lookup"><span data-stu-id="89091-107">Find a released product</span></span>
1. <span data-ttu-id="89091-108">Allez dans Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="89091-108">Go to Released products.</span></span>
2. <span data-ttu-id="89091-109">Cliquez sur Afficher les filtres.</span><span class="sxs-lookup"><span data-stu-id="89091-109">Click Show filters.</span></span>
    * <span data-ttu-id="89091-110">Vous êtes sur le point d'ajouter le champ Type de production dans la boîte de dialogue de filtre.</span><span class="sxs-lookup"><span data-stu-id="89091-110">You are about to add the field Production type in the filter dialog box.</span></span>  
3. <span data-ttu-id="89091-111">Cliquez sur Ajouter un champ de filtre pour ajouter le champ Type de production.</span><span class="sxs-lookup"><span data-stu-id="89091-111">Click Add a filter field to add the field Production type.</span></span>
    * <span data-ttu-id="89091-112">Dans l'étape suivante, vous devez entrer manuellement une formule dans le champ Type de production avant de sélectionner Appliquer.</span><span class="sxs-lookup"><span data-stu-id="89091-112">In the next step, you need to manually enter Formula in the Production type field before you select Apply.</span></span> <span data-ttu-id="89091-113">Cela définit le filtre sur la liste des produits lancés.</span><span class="sxs-lookup"><span data-stu-id="89091-113">This sets the filter on the list of released products.</span></span>  
4. <span data-ttu-id="89091-114">Entrez manuellement la formule dans le champ Type de production.</span><span class="sxs-lookup"><span data-stu-id="89091-114">Manually enter Formula in the Production type field.</span></span>
5. <span data-ttu-id="89091-115">Cliquez sur Appliquer.</span><span class="sxs-lookup"><span data-stu-id="89091-115">Click Apply.</span></span>

## <a name="select-a-released-product"></a><span data-ttu-id="89091-116">Sélectionner un produit lancé</span><span class="sxs-lookup"><span data-stu-id="89091-116">Select a released product</span></span>
1. <span data-ttu-id="89091-117">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="89091-117">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="89091-118">Cliquez sur Versions de formule.</span><span class="sxs-lookup"><span data-stu-id="89091-118">Click Formula versions.</span></span>
    * <span data-ttu-id="89091-119">Dans le volet Action d'ingénierie, cliquez sur Versions de formule.</span><span class="sxs-lookup"><span data-stu-id="89091-119">On the Engineering Action Pane, click Formula versions.</span></span>  

## <a name="copy-co-products"></a><span data-ttu-id="89091-120">Copier des coproduits</span><span class="sxs-lookup"><span data-stu-id="89091-120">Copy co-products</span></span>
1. <span data-ttu-id="89091-121">Dans le volet Actions, cliquez Version de formule.</span><span class="sxs-lookup"><span data-stu-id="89091-121">On the Action Pane, click Formula version.</span></span>
2. <span data-ttu-id="89091-122">Cliquez sur Co-produits.</span><span class="sxs-lookup"><span data-stu-id="89091-122">Click Co-products.</span></span>
3. <span data-ttu-id="89091-123">Cliquez sur Copier.</span><span class="sxs-lookup"><span data-stu-id="89091-123">Click Copy.</span></span>
4. <span data-ttu-id="89091-124">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="89091-124">In the Item number field, enter or select a value.</span></span>
5. <span data-ttu-id="89091-125">Dans le champ Version de formule, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="89091-125">In the Formula version field, enter or select a value.</span></span>
6. <span data-ttu-id="89091-126">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="89091-126">Click OK.</span></span>
7. <span data-ttu-id="89091-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="89091-127">Close the page.</span></span>


