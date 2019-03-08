---
title: Créer des articles empruntés
description: Les articles empruntés sont des enregistrements qui permettent de suivre les articles physiques (comme des téléphones ou des ordinateurs) que votre société prête aux collaborateurs.
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e17005bda302c58f5a6560fe9c4eda04e918c92f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "341831"
---
# <a name="create-loan-items"></a><span data-ttu-id="4a5e8-103">Créer des articles empruntés</span><span class="sxs-lookup"><span data-stu-id="4a5e8-103">Create loan items</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4a5e8-104">Les articles empruntés sont des enregistrements qui permettent de suivre les articles physiques (comme des téléphones ou des ordinateurs) que votre société prête aux collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-104">Loan items are records that help you track physical items, such as phones or computers, that your company lends to workers.</span></span> <span data-ttu-id="4a5e8-105">Chaque article physique doit avoir un article de prêt correspondant.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-105">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="4a5e8-106">Chaque enregistrement d'article emprunté doit décrire la nature de l'emprunt, le responsable de l'emprunt et le nombre de jours d'emprunt de l'article.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-106">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can be on loan.</span></span> <span data-ttu-id="4a5e8-107">Vous pouvez créer plusieurs articles empruntés, tels que des clés, cartes d'accès ou uniformes, simultanément.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-107">You can create multiple loan items, such as keys, access cards, or uniforms, at the same time.</span></span> <span data-ttu-id="4a5e8-108">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-loan-types"></a><span data-ttu-id="4a5e8-109">Créer des types d'emprunt</span><span class="sxs-lookup"><span data-stu-id="4a5e8-109">Create Loan types</span></span>
1. <span data-ttu-id="4a5e8-110">Allez dans Ressources humaines > Collaborateurs > Articles empruntés > Types d'emprunt.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-110">Go to Human resources > Workers > Loan items > Loan types.</span></span>
2. <span data-ttu-id="4a5e8-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-111">Click New.</span></span>
3. <span data-ttu-id="4a5e8-112">Tapez une valeur dans le champ Type d'emprunt.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-112">In the Loan type field, type a value.</span></span>
4. <span data-ttu-id="4a5e8-113">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="4a5e8-114">Entrez le nombre de jours pendant lesquels les articles associés à ce type d'emprunt peuvent être en retard.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-114">Enter the number of days that items assigned to this loan type can be overdue.</span></span> 
6. <span data-ttu-id="4a5e8-115">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-115">Click Save.</span></span>
7. <span data-ttu-id="4a5e8-116">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-116">Close the page.</span></span>
8. <span data-ttu-id="4a5e8-117">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-117">Refresh the page.</span></span>

## <a name="create-loan-items"></a><span data-ttu-id="4a5e8-118">Créer des articles empruntés</span><span class="sxs-lookup"><span data-stu-id="4a5e8-118">Create Loan items</span></span>
1. <span data-ttu-id="4a5e8-119">Allez dans Ressources humaines > Collaborateurs > Articles empruntés > Articles empruntés.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-119">Go to Human resources > Workers > Loan items > Loan items.</span></span>
2. <span data-ttu-id="4a5e8-120">Cliquez sur Créer des articles empruntés.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-120">Click Create loan items.</span></span>
3. <span data-ttu-id="4a5e8-121">Dans le champ Qté, saisissez un nombre.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-121">In the Qty. field, enter a number.</span></span>
4. <span data-ttu-id="4a5e8-122">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-122">In the Description field, type a value.</span></span>
5. <span data-ttu-id="4a5e8-123">Dans le champ Type d'emprunt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-123">In the Loan type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="4a5e8-124">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-124">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="4a5e8-125">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-125">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="4a5e8-126">Permet d'entrer le nombre de jours pendant lesquels un article peut être emprunté.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-126">Enter the number of days the item can be on loan.</span></span>
    * <span data-ttu-id="4a5e8-127">La valeur par défaut du champ Retour prévu de la page Équipement emprunté est calculée comme suit : date du jour plus ce nombre.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-127">The default value for the Planned return field on the Loaned equipment page is calculated as the current date plus this number.</span></span>  
9. <span data-ttu-id="4a5e8-128">Dans le champ Responsable, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-128">In the Person in charge field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="4a5e8-129">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-129">Click Select.</span></span>
11. <span data-ttu-id="4a5e8-130">Entrez un nombre dans le champ Valeur de début.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-130">In the Starting value field, enter a number.</span></span>
12. <span data-ttu-id="4a5e8-131">Entrez un nombre dans le champ Intervalle.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-131">In the Interval field, enter a number.</span></span>
13. <span data-ttu-id="4a5e8-132">Tapez une valeur dans le champ Format.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-132">In the Format field, type a value.</span></span>
    * <span data-ttu-id="4a5e8-133">Par exemple, si le numéro de départ pour un article emprunté est 10, entrez deux symboles numériques dans le champ Format.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-133">For example, if the starting number for a loan item is 10, enter two number symbols symbols in the Format field.</span></span>  
14. <span data-ttu-id="4a5e8-134">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-134">Click OK.</span></span>
15. <span data-ttu-id="4a5e8-135">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="4a5e8-135">Refresh the page.</span></span>

