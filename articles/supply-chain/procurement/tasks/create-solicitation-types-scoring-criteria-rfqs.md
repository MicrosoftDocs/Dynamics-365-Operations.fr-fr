---
title: Créer des types de sollicitation et des critères d'attribution pour les demandes de devis
description: Ce guide montre comment créer un type de sollicitation et l'associer à une méthode d'attribution de score.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQSolicitationType, PurchRFQCaseTableListPage, PurchCreateRFQCase, PurchRFQCaseTable, PurchRFQScoringRFQCaseCriteria, PurchRFQScoringCriteriaCopy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1b3876238a191cbbacc4e8c435bb798232e6fd6f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427993"
---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a><span data-ttu-id="d87fd-103">Créer des types de sollicitation et des critères d'attribution pour les demandes de devis</span><span class="sxs-lookup"><span data-stu-id="d87fd-103">Create solicitation types and scoring criteria for RFQs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d87fd-104">Ce guide montre comment créer un type de sollicitation et l'associer à une méthode d'attribution de score.</span><span class="sxs-lookup"><span data-stu-id="d87fd-104">This guide shows you how to create a solicitation type and associate this with a scoring method.</span></span> <span data-ttu-id="d87fd-105">Il montre également comment utiliser le type de sollicitation sur un appel d'offre qui définit ensuite la méthode d'attribution de score par défaut.</span><span class="sxs-lookup"><span data-stu-id="d87fd-105">It also shows how to use the solicitation type on a request for quotation (RFQ) which then sets the default scoring method.</span></span> <span data-ttu-id="d87fd-106">Ces tâches sont généralement effectuées par un responsable des achats.</span><span class="sxs-lookup"><span data-stu-id="d87fd-106">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="d87fd-107">Vous pouvez utiliser cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="d87fd-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="d87fd-108">Vous devez avoir une méthode d'attribution de score disponible avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="d87fd-108">You need to have a scoring method available before you start.</span></span>


## <a name="create-a-solicitation-type"></a><span data-ttu-id="d87fd-109">Créer un type de sollicitation</span><span class="sxs-lookup"><span data-stu-id="d87fd-109">Create a solicitation type</span></span>
1. <span data-ttu-id="d87fd-110">Allez dans Approvisionnements > Paramétrage > Appel d'offre > Type de sollicitation.</span><span class="sxs-lookup"><span data-stu-id="d87fd-110">Go to Procurement and sourcing > Setup > Request for quotation > Solicitation type.</span></span>
2. <span data-ttu-id="d87fd-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="d87fd-111">Click New.</span></span>
3. <span data-ttu-id="d87fd-112">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d87fd-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="d87fd-113">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d87fd-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d87fd-114">Dans le champ Méthode d'attribution de score, choisissez la méthode d'attribution de score que vous voulez utiliser pour ce type de sollicitation.</span><span class="sxs-lookup"><span data-stu-id="d87fd-114">In the Scoring method field, select the scoring method that you want to use for this solicitation type.</span></span>
6. <span data-ttu-id="d87fd-115">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="d87fd-115">Click Save.</span></span>
7. <span data-ttu-id="d87fd-116">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d87fd-116">Close the page.</span></span>

## <a name="use-the-solicitation-type"></a><span data-ttu-id="d87fd-117">Utiliser le type de sollicitation</span><span class="sxs-lookup"><span data-stu-id="d87fd-117">Use the solicitation type</span></span>
1. <span data-ttu-id="d87fd-118">Accédez à Approvisionnements > Demandes de devis > Toutes les demandes de devis</span><span class="sxs-lookup"><span data-stu-id="d87fd-118">Go to Procurement and sourcing > Requests for quotations > All requests for quotations.</span></span>
2. <span data-ttu-id="d87fd-119">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="d87fd-119">Click New.</span></span>
3. <span data-ttu-id="d87fd-120">Dans le champ Type de sollicitation, choisissez le type de sollicitation que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="d87fd-120">In the Solicitation type field, select the solicitation type that you have just created.</span></span> 
    *   
4. <span data-ttu-id="d87fd-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d87fd-121">Click OK.</span></span>
5. <span data-ttu-id="d87fd-122">Cliquez sur Critères d'attribution de score.</span><span class="sxs-lookup"><span data-stu-id="d87fd-122">Click Scoring criteria.</span></span>
    * <span data-ttu-id="d87fd-123">Les critères d'attribution de score qui sont montrés sont ceux de la méthode d'attribution de score associée au type de sollicitation.</span><span class="sxs-lookup"><span data-stu-id="d87fd-123">The scoring criteria that are shown are the ones from the scoring method that you associated with the solicitation type.</span></span> <span data-ttu-id="d87fd-124">Vous pouvez choisir d'ajouter ou de supprimer des critères sur cette page.</span><span class="sxs-lookup"><span data-stu-id="d87fd-124">You can choose to add or delete criteria on this page.</span></span> <span data-ttu-id="d87fd-125">Il est également possible d'ajouter de nouveaux critères en les copiant à partir d'autres méthodes d'attribution de score.</span><span class="sxs-lookup"><span data-stu-id="d87fd-125">It's also possible to add new criteria by copying them from other scoring methods.</span></span>  
6. <span data-ttu-id="d87fd-126">Cliquez sur Copier les critères.</span><span class="sxs-lookup"><span data-stu-id="d87fd-126">Click Copy criteria.</span></span>
7. <span data-ttu-id="d87fd-127">Entrez ou sélectionnez une valeur dans le champ Méthode d'attribution de score.</span><span class="sxs-lookup"><span data-stu-id="d87fd-127">In the Scoring method field, enter or select a value.</span></span>
8. <span data-ttu-id="d87fd-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d87fd-128">Click OK.</span></span>
9. <span data-ttu-id="d87fd-129">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d87fd-129">Close the page.</span></span>

