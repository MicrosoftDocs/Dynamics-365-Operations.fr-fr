---
title: Créer un budget préliminaire pour le secteur public
description: Vous pouvez créer des écritures de registre budgétaires préliminaires pour un modèle de budget et des valeurs de dimension spécifiques.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTransaction, BudgetAccountStructureLookup, BudgetTransactionMultiPost
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 05e8059f44000fd305ed2c2555511da29b130af9
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443263"
---
# <a name="create-a-preliminary-budget-for-public-sector"></a><span data-ttu-id="fd2dd-103">Créer un budget préliminaire pour le secteur public</span><span class="sxs-lookup"><span data-stu-id="fd2dd-103">Create a preliminary budget for Public sector</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fd2dd-104">Vous pouvez créer des écritures de registre budgétaires préliminaires pour un modèle de budget et des valeurs de dimension spécifiques.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-104">You can create preliminary budget register entries for a specific budget model and dimension values.</span></span> <span data-ttu-id="fd2dd-105">Une fois le budget réel approuvé, vous pouvez créer des écritures de registre budgétaires d’origine.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-105">After the actual budget is approved, you can create original budget register entries.</span></span> <span data-ttu-id="fd2dd-106">Cette procédure a été créée à l’aide des données de la société fictive PSUS dans la partition du secteur public.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-106">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="fd2dd-107">Accédez à Budgétisation > Écritures de registre budgétaires.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-107">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="fd2dd-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-108">Click New.</span></span>
3. <span data-ttu-id="fd2dd-109">Dans le champ Modèle de budget, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-109">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="fd2dd-110">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-110">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="fd2dd-111">Dans le champ Code budgétaire, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-111">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="fd2dd-112">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="fd2dd-113">Dans le champ Code motif, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-113">In the Reason code field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="fd2dd-114">Dans la liste, cliquez sur l’enregistrement de votre choix.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-114">In the list, click the desired record.</span></span>
9. <span data-ttu-id="fd2dd-115">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-115">Click Save.</span></span>
10. <span data-ttu-id="fd2dd-116">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-116">Click Add line.</span></span>
    * <span data-ttu-id="fd2dd-117">Facultatif : si vous souhaitez modifier la date figurant dans l’en-tête, spécifiez une nouvelle date.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-117">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="fd2dd-118">Cette date détermine la période fiscale dans laquelle le budget sera enregistré.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-118">This date determines the fiscal period that the budget will be recorded to.</span></span> <span data-ttu-id="fd2dd-119">Lorsque vous affichez le guide de tâche, et que vous souhaitez renseigner d’autres champs, cliquez sur Déverrouiller en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-119">When viewing the task guide, to fill out other fields, click Unlock at the top of the page.</span></span>  
11. <span data-ttu-id="fd2dd-120">Dans le champ Structure de compte, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-120">In the Account structure field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="fd2dd-121">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-121">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="fd2dd-122">Dans le champ Valeurs de dimension, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-122">In the Dimension values field, specify the desired values.</span></span>
14. <span data-ttu-id="fd2dd-123">Dans le champ Montant, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-123">In the Amount field, enter a number.</span></span>
    * <span data-ttu-id="fd2dd-124">Vous pouvez également entrer un type de montant.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-124">You can also enter an amount type.</span></span>  
15. <span data-ttu-id="fd2dd-125">Dans le champ Devise, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-125">In the Currency field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="fd2dd-126">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-126">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="fd2dd-127">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-127">Click Save.</span></span>
18. <span data-ttu-id="fd2dd-128">Cliquez sur Mettre à jour les soldes budgétaires.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-128">Click Update budget balances.</span></span>
19. <span data-ttu-id="fd2dd-129">Cliquez sur Mise à jour.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-129">Click Update.</span></span>
    * <span data-ttu-id="fd2dd-130">Pour afficher les résultats de la mise à jour, cliquez sur Détails du message dans la barre bleue.</span><span class="sxs-lookup"><span data-stu-id="fd2dd-130">To see the results of the update, click Message details on the blue bar.</span></span>  

