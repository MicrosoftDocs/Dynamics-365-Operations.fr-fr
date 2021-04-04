---
title: Configurer un collaborateur
description: Cette procédure illustre comment configurer un collaborateur en tant que commercial qui peut bénéficier d'une commission sur les ventes dans POS.
author: jblucher
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, HcmWorker
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 120705200f223e31c72290059e8634e7db6f9fdd
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232615"
---
# <a name="configure-a-worker"></a><span data-ttu-id="bdb5c-103"> Configurer un collaborateur</span><span class="sxs-lookup"><span data-stu-id="bdb5c-103">Configure a worker</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bdb5c-104">Cette procédure illustre comment configurer un collaborateur en tant que commercial qui peut bénéficier d'une commission sur les ventes dans POS.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-104">This procedure demonstrates how to configure a worker as a sales representative who is eligible for commission on sales in POS.</span></span> <span data-ttu-id="bdb5c-105">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-105">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-commission-sales-group-for-the-worker"></a><span data-ttu-id="bdb5c-106">Créer un groupe de vente avec commission pour le collaborateur</span><span class="sxs-lookup"><span data-stu-id="bdb5c-106">Create a commission sales group for the worker</span></span>
1. <span data-ttu-id="bdb5c-107">Accédez à Ventes et marketing > Commissions > Groupes de ventes.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-107">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="bdb5c-108">Les collaborateurs peuvent être affectés à un ou plusieurs groupes de vente.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-108">Workers can be assigned to one or more sales groups.</span></span> <span data-ttu-id="bdb5c-109">Dans POS, vous pouvez choisir n'importe quel groupe de vente contenant des collaborateurs issus du carnet d'adresses du magasin.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-109">In POS, you can choose any sales group that contains workers from the store's address book.</span></span>  
2. <span data-ttu-id="bdb5c-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-110">Click New.</span></span>
3. <span data-ttu-id="bdb5c-111">Dans le champ Groupe, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="bdb5c-112">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="bdb5c-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-113">Click Save.</span></span>
6. <span data-ttu-id="bdb5c-114">Cliquez sur Général dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-114">On the Action Pane, click General.</span></span>
7. <span data-ttu-id="bdb5c-115">Cliquez sur Commercial.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-115">Click Sales rep.</span></span>
    * <span data-ttu-id="bdb5c-116">Un groupe de vente peut contenir plusieurs collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-116">A sales group can contain more than one worker.</span></span> <span data-ttu-id="bdb5c-117">Les commissions peuvent être fractionnées entre les collaborateurs selon la façon dont vous définissez la part de commission.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-117">Commissions can be split between workers based on how you define the commission share.</span></span>  
8. <span data-ttu-id="bdb5c-118">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-118">In the Name field, enter or select a value.</span></span>
9. <span data-ttu-id="bdb5c-119">Dans le champ Part de commission, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-119">In the Commission share field, enter a number.</span></span>
10. <span data-ttu-id="bdb5c-120">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-120">Click Save.</span></span>
11. <span data-ttu-id="bdb5c-121">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-121">Close the page.</span></span>
12. <span data-ttu-id="bdb5c-122">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-122">Close the page.</span></span>

## <a name="assign-the-workers-default-sales-group"></a><span data-ttu-id="bdb5c-123">Affecter le groupe de vente par défaut des collaborateurs</span><span class="sxs-lookup"><span data-stu-id="bdb5c-123">Assign the workers default sales group</span></span>
1. <span data-ttu-id="bdb5c-124">Accédez à Retail et Commerce > Employés > Collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-124">Go to Retail and Commerce > Employees > Workers.</span></span>
2. <span data-ttu-id="bdb5c-125">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-125">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="bdb5c-126">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-126">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="bdb5c-127">Cliquez sur l'onglet Commerce.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-127">Click the Commerce tab.</span></span>
    * <span data-ttu-id="bdb5c-128">Un collaborateur peut être affecté à un groupe de vente par défaut.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-128">A worker can be assigned to a default sales group.</span></span> <span data-ttu-id="bdb5c-129">Le groupe de vente par défaut est automatiquement ajouté aux lignes de vente dans POS si l'option est activée dans le profil de la fonctionnalité pour le magasin.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-129">The default sales group will be automatically added to sales lines in POS if the option is enabled in the functionality profile for the store.</span></span>  
5. <span data-ttu-id="bdb5c-130">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-130">Click Edit.</span></span>
6. <span data-ttu-id="bdb5c-131">Dans le champ Groupe par défaut, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-131">In the Default group field, enter or select a value.</span></span>
7. <span data-ttu-id="bdb5c-132">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bdb5c-132">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]