---
title: Créer une commande fournisseur régie par budget
description: Cette procédure permet de créer une commande fournisseur dont la disponibilité budgétaire est vérifiée.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e82e40d67547f5932a4805f2580e8c9f58def284
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569981"
---
# <a name="create-a-purchase-order-governed-by-budget"></a><span data-ttu-id="25c51-103">Créer une commande fournisseur régie par budget</span><span class="sxs-lookup"><span data-stu-id="25c51-103">Create a purchase order governed by budget</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="25c51-104">Cette procédure permet de créer une commande fournisseur dont la disponibilité budgétaire est vérifiée.</span><span class="sxs-lookup"><span data-stu-id="25c51-104">Use this procedure to create a purchase order that is checked for available budget.</span></span> <span data-ttu-id="25c51-105">Cet enregistrement utilise la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="25c51-105">This recording uses the USMF demo data company.</span></span>


## <a name="review-the-budget-control-configuration"></a><span data-ttu-id="25c51-106">Examiner la configuration du contrôle budgétaire</span><span class="sxs-lookup"><span data-stu-id="25c51-106">Review the budget control configuration</span></span>
1. <span data-ttu-id="25c51-107">Accédez à Budgétisation > Paramétrage > Contrôle budgétaire > Configuration du contrôle budgétaire.</span><span class="sxs-lookup"><span data-stu-id="25c51-107">Go to Budgeting > Setup > Budget control > Budget control configuration.</span></span>
2. <span data-ttu-id="25c51-108">Cliquez sur l'onglet Fonds budgétaires disponibles.</span><span class="sxs-lookup"><span data-stu-id="25c51-108">Click the Budget funds available tab.</span></span>
3. <span data-ttu-id="25c51-109">Cliquez sur l'onglet Documents et journaux.</span><span class="sxs-lookup"><span data-stu-id="25c51-109">Click the Documents and journals tab.</span></span>
4. <span data-ttu-id="25c51-110">Cliquez sur l'onglet Définir les règles de contrôle budgétaire.</span><span class="sxs-lookup"><span data-stu-id="25c51-110">Click the Define budget control rules tab.</span></span>
5. <span data-ttu-id="25c51-111">Cliquez sur l'onglet Définir des groupes budgétaires.</span><span class="sxs-lookup"><span data-stu-id="25c51-111">Click the Define budget groups tab.</span></span>
6. <span data-ttu-id="25c51-112">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="25c51-112">Close the page.</span></span>

## <a name="create-the-purchase-order-header"></a><span data-ttu-id="25c51-113">Créer l'en-tête de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="25c51-113">Create the purchase order header</span></span>
1. <span data-ttu-id="25c51-114">Accédez à Approvisionnements > Commandes fournisseur > Toutes les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="25c51-114">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="25c51-115">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="25c51-115">Click New.</span></span>
3. <span data-ttu-id="25c51-116">Dans le champ Compte fournisseur, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="25c51-116">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="25c51-117">Développez la section Général.</span><span class="sxs-lookup"><span data-stu-id="25c51-117">Expand the General section.</span></span>
5. <span data-ttu-id="25c51-118">Dans le champ Date comptable, définissez la date sur « 01-01-2016 ».</span><span class="sxs-lookup"><span data-stu-id="25c51-118">In the Accounting date field, set the date to '2016-01-01'.</span></span>
6. <span data-ttu-id="25c51-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="25c51-119">Click OK.</span></span>

## <a name="add-a-purchase-order-line"></a><span data-ttu-id="25c51-120">Ajouter une ligne de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="25c51-120">Add a purchase order line</span></span>
1. <span data-ttu-id="25c51-121">Saisissez ou sélectionnez une valeur dans le champ Catégorie d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="25c51-121">In the Procurement category field, enter or select a value.</span></span>
2. <span data-ttu-id="25c51-122">Définissez la quantité sur 2.</span><span class="sxs-lookup"><span data-stu-id="25c51-122">Set Quantity to '2'.</span></span>
3. <span data-ttu-id="25c51-123">Saisissez ou sélectionnez une valeur dans le champ Unité.</span><span class="sxs-lookup"><span data-stu-id="25c51-123">In the Unit field, enter or select a value.</span></span>
4. <span data-ttu-id="25c51-124">Définissez le prix unitaire sur « 10 000 ».</span><span class="sxs-lookup"><span data-stu-id="25c51-124">Set Unit price to '10000'.</span></span>
5. <span data-ttu-id="25c51-125">Cliquez sur Finances.</span><span class="sxs-lookup"><span data-stu-id="25c51-125">Click Financials.</span></span>
6. <span data-ttu-id="25c51-126">Cliquez sur Distribuer les montants.</span><span class="sxs-lookup"><span data-stu-id="25c51-126">Click Distribute amounts.</span></span>
7. <span data-ttu-id="25c51-127">Dans le champ Compte général, indiquez la valeur « 601300-001-023-- ».</span><span class="sxs-lookup"><span data-stu-id="25c51-127">In the Ledger account field, specify the value '601300-001-023--'.</span></span>
8. <span data-ttu-id="25c51-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="25c51-128">Close the page.</span></span>

## <a name="perform-budget-checking"></a><span data-ttu-id="25c51-129">Réaliser un contrôle budgétaire</span><span class="sxs-lookup"><span data-stu-id="25c51-129">Perform budget checking</span></span>
1. <span data-ttu-id="25c51-130">Cliquez sur Finances.</span><span class="sxs-lookup"><span data-stu-id="25c51-130">Click Financials.</span></span>
2. <span data-ttu-id="25c51-131">Cliquez sur Réaliser un contrôle budgétaire.</span><span class="sxs-lookup"><span data-stu-id="25c51-131">Click Perform budget checking.</span></span>
3. <span data-ttu-id="25c51-132">Cliquez sur Finances.</span><span class="sxs-lookup"><span data-stu-id="25c51-132">Click Financials.</span></span>
4. <span data-ttu-id="25c51-133">Cliquez sur Erreurs ou avertissements du contrôle budgétaire.</span><span class="sxs-lookup"><span data-stu-id="25c51-133">Click Budget check errors or warnings.</span></span>
5. <span data-ttu-id="25c51-134">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="25c51-134">Click Close.</span></span>

