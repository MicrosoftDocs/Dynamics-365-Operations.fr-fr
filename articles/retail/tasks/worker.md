--- 
title: " Configurer un collaborateur"
description: "Cette procédure illustre comment configurer un collaborateur de vente au détail comme commercial qui peut bénéficier d'une commission sur les ventes dans POS."
author: jblucher
manager: AnnBe
ms.date: 02/22/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 27b075cf1152f16fc4726b224e877eacb2f2572c
ms.contentlocale: fr-fr
ms.lasthandoff: 02/07/2018

---
# <a name="configure-a-worker"></a><span data-ttu-id="2d968-103"> Configurer un collaborateur</span><span class="sxs-lookup"><span data-stu-id="2d968-103">Configure a worker</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="2d968-104">Cette procédure illustre comment configurer un collaborateur de vente au détail comme commercial qui peut bénéficier d'une commission sur les ventes dans POS.</span><span class="sxs-lookup"><span data-stu-id="2d968-104">This procedure demonstrates how to configure a retail worker as a sales representative who is eligible for commission on sales in POS.</span></span> <span data-ttu-id="2d968-105">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="2d968-105">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-commission-sales-group-for-the-worker"></a><span data-ttu-id="2d968-106">Créer un groupe de vente avec commission pour le collaborateur</span><span class="sxs-lookup"><span data-stu-id="2d968-106">Create a commission sales group for the worker</span></span>
1. <span data-ttu-id="2d968-107">Accédez à Ventes et marketing > Commissions > Groupes de ventes.</span><span class="sxs-lookup"><span data-stu-id="2d968-107">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="2d968-108">Les collaborateurs peuvent être affectés à un ou plusieurs groupes de vente.</span><span class="sxs-lookup"><span data-stu-id="2d968-108">Workers can be assigned to one or more sales groups.</span></span> <span data-ttu-id="2d968-109">Dans POS, vous pouvez choisir n'importe quel groupe de vente contenant des collaborateurs issus du carnet d'adresses du magasin.</span><span class="sxs-lookup"><span data-stu-id="2d968-109">In POS, you can choose any sales group that contains workers from the store's address book.</span></span>  
2. <span data-ttu-id="2d968-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="2d968-110">Click New.</span></span>
3. <span data-ttu-id="2d968-111">Dans le champ Groupe, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2d968-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="2d968-112">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="2d968-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="2d968-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="2d968-113">Click Save.</span></span>
6. <span data-ttu-id="2d968-114">Cliquez sur Général dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="2d968-114">On the Action Pane, click General.</span></span>
7. <span data-ttu-id="2d968-115">Cliquez sur Commercial.</span><span class="sxs-lookup"><span data-stu-id="2d968-115">Click Sales rep.</span></span>
    * <span data-ttu-id="2d968-116">Un groupe de vente peut contenir plusieurs collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="2d968-116">A sales group can contain more than one worker.</span></span> <span data-ttu-id="2d968-117">Les commissions peuvent être fractionnées entre les collaborateurs selon la façon dont vous définissez la part de commission.</span><span class="sxs-lookup"><span data-stu-id="2d968-117">Commissions can be split between workers based on how you define the commission share.</span></span>  
8. <span data-ttu-id="2d968-118">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="2d968-118">In the Name field, enter or select a value.</span></span>
9. <span data-ttu-id="2d968-119">Dans le champ Part de commission, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="2d968-119">In the Commission share field, enter a number.</span></span>
10. <span data-ttu-id="2d968-120">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="2d968-120">Click Save.</span></span>
11. <span data-ttu-id="2d968-121">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2d968-121">Close the page.</span></span>
12. <span data-ttu-id="2d968-122">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2d968-122">Close the page.</span></span>

## <a name="assign-the-workers-default-sales-group"></a><span data-ttu-id="2d968-123">Affecter le groupe de vente par défaut des collaborateurs</span><span class="sxs-lookup"><span data-stu-id="2d968-123">Assign the workers default sales group</span></span>
1. <span data-ttu-id="2d968-124">Accédez à Commerce et vente au détail > Employés > Collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="2d968-124">Go to Retail and commerce > Employees > Workers.</span></span>
2. <span data-ttu-id="2d968-125">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2d968-125">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="2d968-126">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2d968-126">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="2d968-127">Cliquez sur l'onglet Vente au détail.</span><span class="sxs-lookup"><span data-stu-id="2d968-127">Click the Retail tab.</span></span>
    * <span data-ttu-id="2d968-128">Un collaborateur peut être affecté à un groupe de vente par défaut.</span><span class="sxs-lookup"><span data-stu-id="2d968-128">A worker can be assigned to a default sales group.</span></span> <span data-ttu-id="2d968-129">Le groupe de vente par défaut est automatiquement ajouté aux lignes de vente dans POS si l'option est activée dans le profil de la fonctionnalité pour le magasin.</span><span class="sxs-lookup"><span data-stu-id="2d968-129">The default sales group will be automatically added to sales lines in POS if the option is enabled in the functionality profile for the store.</span></span>  
5. <span data-ttu-id="2d968-130">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="2d968-130">Click Edit.</span></span>
6. <span data-ttu-id="2d968-131">Dans le champ Groupe par défaut, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2d968-131">In the Default group field, enter or select a value.</span></span>
7. <span data-ttu-id="2d968-132">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="2d968-132">Click Save.</span></span>


