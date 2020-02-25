---
title: Créer des articles empruntés
description: Les articles empruntés sont des enregistrements qui permettent de suivre les articles physiques (comme des téléphones ou des ordinateurs) que votre société prête aux collaborateurs.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5245b82c81178ff41d5351cd8f73650aa497d555
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008994"
---
# <a name="create-loan-items"></a><span data-ttu-id="08dd2-103">Créer des articles empruntés</span><span class="sxs-lookup"><span data-stu-id="08dd2-103">Create loan items</span></span>



<span data-ttu-id="08dd2-104">Les articles empruntés sont des enregistrements qui permettent de suivre les articles physiques (comme des téléphones ou des ordinateurs) que votre société prête aux collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="08dd2-104">Loan items are records that help you track physical items, such as phones or computers, that your company lends to workers.</span></span> <span data-ttu-id="08dd2-105">Chaque article physique doit avoir un article de prêt correspondant.</span><span class="sxs-lookup"><span data-stu-id="08dd2-105">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="08dd2-106">Chaque enregistrement d'article emprunté doit décrire la nature de l'emprunt, le responsable de l'emprunt et le nombre de jours d'emprunt de l'article.</span><span class="sxs-lookup"><span data-stu-id="08dd2-106">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can be on loan.</span></span> <span data-ttu-id="08dd2-107">Vous pouvez créer plusieurs articles empruntés, tels que des clés, cartes d'accès ou uniformes, simultanément.</span><span class="sxs-lookup"><span data-stu-id="08dd2-107">You can create multiple loan items, such as keys, access cards, or uniforms, at the same time.</span></span> <span data-ttu-id="08dd2-108">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="08dd2-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-loan-types"></a><span data-ttu-id="08dd2-109">Créer des types d'emprunt</span><span class="sxs-lookup"><span data-stu-id="08dd2-109">Create Loan types</span></span>
1. <span data-ttu-id="08dd2-110">Allez dans Ressources humaines > Collaborateurs > Articles empruntés > Types d'emprunt.</span><span class="sxs-lookup"><span data-stu-id="08dd2-110">Go to Human resources > Workers > Loan items > Loan types.</span></span>
2. <span data-ttu-id="08dd2-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="08dd2-111">Click New.</span></span>
3. <span data-ttu-id="08dd2-112">Tapez une valeur dans le champ Type d'emprunt.</span><span class="sxs-lookup"><span data-stu-id="08dd2-112">In the Loan type field, type a value.</span></span>
4. <span data-ttu-id="08dd2-113">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="08dd2-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="08dd2-114">Entrez le nombre de jours pendant lesquels les articles associés à ce type d'emprunt peuvent être en retard.</span><span class="sxs-lookup"><span data-stu-id="08dd2-114">Enter the number of days that items assigned to this loan type can be overdue.</span></span> 
6. <span data-ttu-id="08dd2-115">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="08dd2-115">Click Save.</span></span>
7. <span data-ttu-id="08dd2-116">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="08dd2-116">Close the page.</span></span>
8. <span data-ttu-id="08dd2-117">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="08dd2-117">Refresh the page.</span></span>

## <a name="create-loan-items"></a><span data-ttu-id="08dd2-118">Créer des articles empruntés</span><span class="sxs-lookup"><span data-stu-id="08dd2-118">Create Loan items</span></span>
1. <span data-ttu-id="08dd2-119">Allez dans Ressources humaines > Collaborateurs > Articles empruntés > Articles empruntés.</span><span class="sxs-lookup"><span data-stu-id="08dd2-119">Go to Human resources > Workers > Loan items > Loan items.</span></span>
2. <span data-ttu-id="08dd2-120">Cliquez sur Créer des articles empruntés.</span><span class="sxs-lookup"><span data-stu-id="08dd2-120">Click Create loan items.</span></span>
3. <span data-ttu-id="08dd2-121">Dans le champ Qté, saisissez un nombre.</span><span class="sxs-lookup"><span data-stu-id="08dd2-121">In the Qty. field, enter a number.</span></span>
4. <span data-ttu-id="08dd2-122">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="08dd2-122">In the Description field, type a value.</span></span>
5. <span data-ttu-id="08dd2-123">Dans le champ Type d'emprunt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="08dd2-123">In the Loan type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="08dd2-124">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="08dd2-124">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="08dd2-125">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="08dd2-125">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="08dd2-126">Permet d'entrer le nombre de jours pendant lesquels un article peut être emprunté.</span><span class="sxs-lookup"><span data-stu-id="08dd2-126">Enter the number of days the item can be on loan.</span></span>
    * <span data-ttu-id="08dd2-127">La valeur par défaut du champ Retour prévu de la page Équipement emprunté est calculée comme suit : date du jour plus ce nombre.</span><span class="sxs-lookup"><span data-stu-id="08dd2-127">The default value for the Planned return field on the Loaned equipment page is calculated as the current date plus this number.</span></span>  
9. <span data-ttu-id="08dd2-128">Dans le champ Responsable, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="08dd2-128">In the Person in charge field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="08dd2-129">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="08dd2-129">Click Select.</span></span>
11. <span data-ttu-id="08dd2-130">Entrez un nombre dans le champ Valeur de début.</span><span class="sxs-lookup"><span data-stu-id="08dd2-130">In the Starting value field, enter a number.</span></span>
12. <span data-ttu-id="08dd2-131">Entrez un nombre dans le champ Intervalle.</span><span class="sxs-lookup"><span data-stu-id="08dd2-131">In the Interval field, enter a number.</span></span>
13. <span data-ttu-id="08dd2-132">Tapez une valeur dans le champ Format.</span><span class="sxs-lookup"><span data-stu-id="08dd2-132">In the Format field, type a value.</span></span>
    * <span data-ttu-id="08dd2-133">Par exemple, si le numéro de départ pour un article emprunté est 10, entrez deux symboles numériques dans le champ Format.</span><span class="sxs-lookup"><span data-stu-id="08dd2-133">For example, if the starting number for a loan item is 10, enter two number symbols symbols in the Format field.</span></span>  
14. <span data-ttu-id="08dd2-134">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="08dd2-134">Click OK.</span></span>
15. <span data-ttu-id="08dd2-135">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="08dd2-135">Refresh the page.</span></span>

