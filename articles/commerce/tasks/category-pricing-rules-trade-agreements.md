---
title: Règles de tarification de catégorie en vue de créer des accords commerciaux
description: Cette procédure illustre comment créer des accords commerciaux sur les prix de vente à l'aide d'une règle de tarification de catégorie.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, RetailDiscountPricingWorkspace, RetailPricingDiscountCategoryPriceRule, RetailCategoryPriceRule, EcoResCategorySingleLookup, RetailCategoryPriceWizard, PriceDiscAdm, PriceDiscAdmTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ca0a002328947746d67abed0d18a96de26b76ffc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5223096"
---
# <a name="category-pricing-rules-to-create-trade-agreements"></a><span data-ttu-id="3ca26-103">Règles de tarification de catégorie en vue de créer des accords commerciaux</span><span class="sxs-lookup"><span data-stu-id="3ca26-103">Category pricing rules to create trade agreements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3ca26-104">Cette procédure illustre comment créer des accords commerciaux sur les prix de vente à l'aide d'une règle de tarification de catégorie.</span><span class="sxs-lookup"><span data-stu-id="3ca26-104">This procedure demonstrates how to create sales price trade agreements using a category pricing rule.</span></span> <span data-ttu-id="3ca26-105">La société fictive utilisée pour créer cette tâche est USRT.</span><span class="sxs-lookup"><span data-stu-id="3ca26-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="3ca26-106">Cette tâche est destinée au rôle Gestionnaire du commerce de Commerce.</span><span class="sxs-lookup"><span data-stu-id="3ca26-106">This task is intended for the Commerce merchandising manager role.</span></span>

1. <span data-ttu-id="3ca26-107">Cliquez sur Gestion de la tarification et des remises.</span><span class="sxs-lookup"><span data-stu-id="3ca26-107">Click Pricing and discount management.</span></span>
2. <span data-ttu-id="3ca26-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3ca26-108">Click New.</span></span>
3. <span data-ttu-id="3ca26-109">Cliquez sur Règle de prix de catégorie.</span><span class="sxs-lookup"><span data-stu-id="3ca26-109">Click Category price rule.</span></span>
4. <span data-ttu-id="3ca26-110">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3ca26-110">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="3ca26-111">Dans le champ Code compte, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="3ca26-111">In the Account code field, select an option.</span></span>
    * <span data-ttu-id="3ca26-112">Un code de compte de type « Groupe » permet de paramétrer les accords commerciaux sur les prix de vente qui sont spécifiques aux canaux, aux programmes de fidélité, au catalogues, et aux affiliations.</span><span class="sxs-lookup"><span data-stu-id="3ca26-112">A "Group" type account code is used to set up sales price trade agreements that are specific for Channels, Loyalty programs, Catalogs, and Affiliations.</span></span>  
6. <span data-ttu-id="3ca26-113">Dans le champ Sélection de compte, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3ca26-113">In the Account selection field, enter or select a value.</span></span>
7. <span data-ttu-id="3ca26-114">Dans le champ Catégorie, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3ca26-114">In the Category field, enter or select a value.</span></span>
8. <span data-ttu-id="3ca26-115">Dans le champ Montant/Pourcentage, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="3ca26-115">In the Amount/Percent field, enter a number.</span></span>
9. <span data-ttu-id="3ca26-116">Dans le champ Version d'arrondi, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3ca26-116">In the Rounding version field, enter or select a value.</span></span>
10. <span data-ttu-id="3ca26-117">Cliquez sur Générer des accords commerciaux.</span><span class="sxs-lookup"><span data-stu-id="3ca26-117">Click Generate trade agreements.</span></span>
11. <span data-ttu-id="3ca26-118">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="3ca26-118">Click Next.</span></span>
12. <span data-ttu-id="3ca26-119">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="3ca26-119">In the From date field, enter a date.</span></span>
13. <span data-ttu-id="3ca26-120">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="3ca26-120">In the To date field, enter a date.</span></span>
14. <span data-ttu-id="3ca26-121">Dans le champ Suivant, sélectionnez Oui.</span><span class="sxs-lookup"><span data-stu-id="3ca26-121">Select Yes in the Find next field.</span></span>
15. <span data-ttu-id="3ca26-122">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="3ca26-122">Click Next.</span></span>
16. <span data-ttu-id="3ca26-123">Cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="3ca26-123">Click Finish.</span></span>
    * <span data-ttu-id="3ca26-124">Cette opération crée un journal d'accords commerciaux et l'ouvre pour que vous l'examiniez.</span><span class="sxs-lookup"><span data-stu-id="3ca26-124">This creates a Trade agreement journal and opens it for your review.</span></span>  
17. <span data-ttu-id="3ca26-125">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="3ca26-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3ca26-126">Les journaux d'accords commerciaux créés à partir des règles de tarification de catégorie ne sont pas validés.</span><span class="sxs-lookup"><span data-stu-id="3ca26-126">The trade agreement journals created from the Category pricing rules aren't posted.</span></span> <span data-ttu-id="3ca26-127">Vous pouvez examiner et modifier les prix générés avant de les valider.</span><span class="sxs-lookup"><span data-stu-id="3ca26-127">You can  review and edit the prices generated before posting them.</span></span>  
18. <span data-ttu-id="3ca26-128">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="3ca26-128">Click Edit.</span></span>
19. <span data-ttu-id="3ca26-129">Dans le champ Montant en devise, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="3ca26-129">In the Amount in currency field, enter a number.</span></span>
20. <span data-ttu-id="3ca26-130">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="3ca26-130">Click Post.</span></span>
21. <span data-ttu-id="3ca26-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3ca26-131">Click OK.</span></span>
22. <span data-ttu-id="3ca26-132">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3ca26-132">Close the page.</span></span>
23. <span data-ttu-id="3ca26-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3ca26-133">Close the page.</span></span>
24. <span data-ttu-id="3ca26-134">Cliquez sur l'onglet Règles de prix de catégorie.</span><span class="sxs-lookup"><span data-stu-id="3ca26-134">Click the Category price rules tab.</span></span>
    * <span data-ttu-id="3ca26-135">Les règles de tarification de catégorie spécifiques aux canaux s'affichent dans cette liste.</span><span class="sxs-lookup"><span data-stu-id="3ca26-135">Channel specific Category pricing rules will show in this list.</span></span>  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]