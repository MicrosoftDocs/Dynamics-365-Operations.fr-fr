--- 
title: "Créer une commande fournisseur régie par budget"
description: "Cette procédure permet de créer une commande fournisseur dont la disponibilité budgétaire est vérifiée."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 7cc024caa54db6629a1e573df295fe8333996647
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-purchase-order-governed-by-budget"></a><span data-ttu-id="68e0d-103">Créer une commande fournisseur régie par budget</span><span class="sxs-lookup"><span data-stu-id="68e0d-103">Create a purchase order governed by budget</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="68e0d-104">Cette procédure permet de créer une commande fournisseur dont la disponibilité budgétaire est vérifiée.</span><span class="sxs-lookup"><span data-stu-id="68e0d-104">Use this procedure to create a purchase order that is checked for available budget.</span></span> <span data-ttu-id="68e0d-105">Cet enregistrement utilise la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="68e0d-105">This recording uses the USMF demo data company.</span></span>


## <a name="review-the-budget-control-configuration"></a><span data-ttu-id="68e0d-106">Examiner la configuration du contrôle budgétaire</span><span class="sxs-lookup"><span data-stu-id="68e0d-106">Review the budget control configuration</span></span>
1. <span data-ttu-id="68e0d-107">Accédez à Budgétisation > Paramétrage > Contrôle budgétaire > Configuration du contrôle budgétaire.</span><span class="sxs-lookup"><span data-stu-id="68e0d-107">Go to Budgeting > Setup > Budget control > Budget control configuration.</span></span>
2. <span data-ttu-id="68e0d-108">Cliquez sur l'onglet Fonds budgétaires disponibles.</span><span class="sxs-lookup"><span data-stu-id="68e0d-108">Click the Budget funds available tab.</span></span>
3. <span data-ttu-id="68e0d-109">Cliquez sur l'onglet Documents et journaux.</span><span class="sxs-lookup"><span data-stu-id="68e0d-109">Click the Documents and journals tab.</span></span>
4. <span data-ttu-id="68e0d-110">Cliquez sur l'onglet Définir les règles de contrôle budgétaire.</span><span class="sxs-lookup"><span data-stu-id="68e0d-110">Click the Define budget control rules tab.</span></span>
5. <span data-ttu-id="68e0d-111">Cliquez sur l'onglet Définir des groupes budgétaires.</span><span class="sxs-lookup"><span data-stu-id="68e0d-111">Click the Define budget groups tab.</span></span>
6. <span data-ttu-id="68e0d-112">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="68e0d-112">Close the page.</span></span>

## <a name="create-the-purchase-order-header"></a><span data-ttu-id="68e0d-113">Créer l'en-tête de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="68e0d-113">Create the purchase order header</span></span>
1. <span data-ttu-id="68e0d-114">Accédez à Approvisionnements > Commandes fournisseur > Toutes les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="68e0d-114">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="68e0d-115">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="68e0d-115">Click New.</span></span>
3. <span data-ttu-id="68e0d-116">Dans le champ Compte fournisseur, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="68e0d-116">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="68e0d-117">Développez la section Général.</span><span class="sxs-lookup"><span data-stu-id="68e0d-117">Expand the General section.</span></span>
5. <span data-ttu-id="68e0d-118">Dans le champ Date comptable, définissez la date sur « 01-01-2016 ».</span><span class="sxs-lookup"><span data-stu-id="68e0d-118">In the Accounting date field, set the date to '2016-01-01'.</span></span>
6. <span data-ttu-id="68e0d-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="68e0d-119">Click OK.</span></span>

## <a name="add-a-purchase-order-line"></a><span data-ttu-id="68e0d-120">Ajouter une ligne de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="68e0d-120">Add a purchase order line</span></span>
1. <span data-ttu-id="68e0d-121">Saisissez ou sélectionnez une valeur dans le champ Catégorie d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="68e0d-121">In the Procurement category field, enter or select a value.</span></span>
2. <span data-ttu-id="68e0d-122">Définissez la quantité sur 2.</span><span class="sxs-lookup"><span data-stu-id="68e0d-122">Set Quantity to '2'.</span></span>
3. <span data-ttu-id="68e0d-123">Saisissez ou sélectionnez une valeur dans le champ Unité.</span><span class="sxs-lookup"><span data-stu-id="68e0d-123">In the Unit field, enter or select a value.</span></span>
4. <span data-ttu-id="68e0d-124">Définissez le prix unitaire sur « 10 000 ».</span><span class="sxs-lookup"><span data-stu-id="68e0d-124">Set Unit price to '10000'.</span></span>
5. <span data-ttu-id="68e0d-125">Cliquez sur Finances.</span><span class="sxs-lookup"><span data-stu-id="68e0d-125">Click Financials.</span></span>
6. <span data-ttu-id="68e0d-126">Cliquez sur Distribuer les montants.</span><span class="sxs-lookup"><span data-stu-id="68e0d-126">Click Distribute amounts.</span></span>
7. <span data-ttu-id="68e0d-127">Dans le champ Compte général, indiquez la valeur « 601300-001-023-- ».</span><span class="sxs-lookup"><span data-stu-id="68e0d-127">In the Ledger account field, specify the value '601300-001-023--'.</span></span>
8. <span data-ttu-id="68e0d-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="68e0d-128">Close the page.</span></span>

## <a name="perform-budget-checking"></a><span data-ttu-id="68e0d-129">Réaliser un contrôle budgétaire</span><span class="sxs-lookup"><span data-stu-id="68e0d-129">Perform budget checking</span></span>
1. <span data-ttu-id="68e0d-130">Cliquez sur Finances.</span><span class="sxs-lookup"><span data-stu-id="68e0d-130">Click Financials.</span></span>
2. <span data-ttu-id="68e0d-131">Cliquez sur Réaliser un contrôle budgétaire.</span><span class="sxs-lookup"><span data-stu-id="68e0d-131">Click Perform budget checking.</span></span>
3. <span data-ttu-id="68e0d-132">Cliquez sur Finances.</span><span class="sxs-lookup"><span data-stu-id="68e0d-132">Click Financials.</span></span>
4. <span data-ttu-id="68e0d-133">Cliquez sur Erreurs ou avertissements du contrôle budgétaire.</span><span class="sxs-lookup"><span data-stu-id="68e0d-133">Click Budget check errors or warnings.</span></span>
5. <span data-ttu-id="68e0d-134">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="68e0d-134">Click Close.</span></span>


