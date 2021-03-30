---
title: Ajustements de prix de la vente au détail
description: Cette procédure décrit la création d'un ajustement du prix de commerce.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailDiscountPriceGroup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dbd2f818930424313e1d76aea4a257efa7c7b3be
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232783"
---
# <a name="retail-price-adjustments"></a><span data-ttu-id="e8dec-103">Ajustements de prix de la vente au détail</span><span class="sxs-lookup"><span data-stu-id="e8dec-103">Retail price adjustments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e8dec-104">Cette procédure décrit la création d'un ajustement du prix de commerce.</span><span class="sxs-lookup"><span data-stu-id="e8dec-104">This procedure will walk through creating a commerce price adjustment.</span></span> <span data-ttu-id="e8dec-105">Un ajustement du prix permet de définir directement le prix de vente d'un article ou de modifier son prix de vente de base ou le prix de vente indiqué dans l'accord commercial.</span><span class="sxs-lookup"><span data-stu-id="e8dec-105">A price adjustment can set an item's sale price directly, or modify its base sale price or trade agreement sale price.</span></span> <span data-ttu-id="e8dec-106">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="e8dec-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="e8dec-107">Cliquez sur Gestion de la tarification et des remises.</span><span class="sxs-lookup"><span data-stu-id="e8dec-107">Click Pricing and discount management.</span></span>
2. <span data-ttu-id="e8dec-108">Cliquez sur l'onglet Ajustements de prix.</span><span class="sxs-lookup"><span data-stu-id="e8dec-108">Click the Price adjustments tab.</span></span>
3. <span data-ttu-id="e8dec-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e8dec-109">Click New.</span></span>
    * <span data-ttu-id="e8dec-110">Vous pouvez créer toutes les règles de tarification et de remise les plus fréquemment utilisées, notamment les remises, les ajustements de prix, les journaux d'accords commerciaux et les règles de tarification de catégorie.</span><span class="sxs-lookup"><span data-stu-id="e8dec-110">From here you can create all of the most commonly used price and discount rules, including discounts, price adjustments, trade agreement journals, and category pricing rules.</span></span>  
4. <span data-ttu-id="e8dec-111">Cliquez sur Ajustement de prix.</span><span class="sxs-lookup"><span data-stu-id="e8dec-111">Click Price adjustment.</span></span>
5. <span data-ttu-id="e8dec-112">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e8dec-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="e8dec-113">Développez la section Lignes.</span><span class="sxs-lookup"><span data-stu-id="e8dec-113">Expand the Lines section.</span></span>
7. <span data-ttu-id="e8dec-114">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e8dec-114">Click Add.</span></span>
    * <span data-ttu-id="e8dec-115">Pour cet exemple, saisissez « 81126 » dans le champ Produit.</span><span class="sxs-lookup"><span data-stu-id="e8dec-115">For this example, enter '81126' in the Product field.</span></span> <span data-ttu-id="e8dec-116">Ensuite, saisissez « 10.0 » dans le champ Pourcentage de remise.</span><span class="sxs-lookup"><span data-stu-id="e8dec-116">Then, enter '10.0' in the Discount percentage field.</span></span>  
    * <span data-ttu-id="e8dec-117">Un ajustement de prix de type Pourcentage de remise réduit un prix de vente de base ou le prix de vente indiqué dans l'accord commercial.</span><span class="sxs-lookup"><span data-stu-id="e8dec-117">A discount percentage type price adjustment will reduce a base sales price or trade agreement sales price.</span></span>  
8. <span data-ttu-id="e8dec-118">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e8dec-118">Click Add.</span></span>
    * <span data-ttu-id="e8dec-119">Pour cet exemple, saisissez « 81125 » dans le champ Produit.</span><span class="sxs-lookup"><span data-stu-id="e8dec-119">For this example, enter '81125' in the Product field.</span></span> <span data-ttu-id="e8dec-120">Ensuite, sélectionnez « Montant de l'escompte de règlement » dans le champ Méthode d'application de la remise.</span><span class="sxs-lookup"><span data-stu-id="e8dec-120">Then, select 'Cash discount amount' in the Discount method field.</span></span>    <span data-ttu-id="e8dec-121">Enfin, saisissez « 5.0 » dans le champ Montant de l'escompte de règlement.</span><span class="sxs-lookup"><span data-stu-id="e8dec-121">Finally, enter '5.0' in the Cash discount amount field.</span></span>  
    * <span data-ttu-id="e8dec-122">Le type de remise Montant de l'escompte de règlement est un montant déduit d'un prix de base ou du prix indiqué dans un accord commercial.</span><span class="sxs-lookup"><span data-stu-id="e8dec-122">A Cash discount amount discount type is an amount taken off from a base price or a trade agreement price.</span></span>  
9. <span data-ttu-id="e8dec-123">Cliquez sur Groupes de prix.</span><span class="sxs-lookup"><span data-stu-id="e8dec-123">Click Price groups.</span></span>
    * <span data-ttu-id="e8dec-124">Sélectionnez « RP-Houston » dans le champ Groupe de prix.</span><span class="sxs-lookup"><span data-stu-id="e8dec-124">Select 'RP-Houston' in the Price group field.</span></span>  
    * <span data-ttu-id="e8dec-125">L'ajustement de prix sera associé au magasin de Houston.</span><span class="sxs-lookup"><span data-stu-id="e8dec-125">This will associate the Price adjustment to the Houston store.</span></span>  
10. <span data-ttu-id="e8dec-126">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e8dec-126">Click Save.</span></span>
11. <span data-ttu-id="e8dec-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e8dec-127">Close the page.</span></span>
12. <span data-ttu-id="e8dec-128">Dans le champ Statut, sélectionnez « Activé ».</span><span class="sxs-lookup"><span data-stu-id="e8dec-128">In the Status field, select 'Enabled'.</span></span>
13. <span data-ttu-id="e8dec-129">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e8dec-129">Click Save.</span></span>
14. <span data-ttu-id="e8dec-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e8dec-130">Close the page.</span></span>
15. <span data-ttu-id="e8dec-131">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="e8dec-131">Refresh the page.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]