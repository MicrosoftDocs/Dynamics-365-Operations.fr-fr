---
title: " Prix de base et accords commerciaux"
description: Cette procédure décrit la création d'accords commerciaux sur les prix de vente spécifiques au canal.
author: josaw1
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PriceDiscGroup, RetailStoreTable, RetailChannelPriceGroup, EcoResProductDetailsExtended, PriceDiscAdmTable, PriceDiscAdm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7576c4218118724562ff739ff9805a06b7ba22d5
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022529"
---
# <a name="base-price-and-trade-agreements"></a><span data-ttu-id="22d23-103"> Prix de base et accords commerciaux</span><span class="sxs-lookup"><span data-stu-id="22d23-103">Base price and trade agreements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="22d23-104">Cette procédure décrit la création d'accords commerciaux sur les prix de vente spécifiques au canal.</span><span class="sxs-lookup"><span data-stu-id="22d23-104">This procedure walks through creating channel-specific sales price trade agreements.</span></span> <span data-ttu-id="22d23-105">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="22d23-105">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="22d23-106">Dans le **Volet de navigation**, accédez à **Modules > Commerce et vente au détail > Gestion de la tarification et des remises > Groupes de prix > Tous les groupes de prix**.</span><span class="sxs-lookup"><span data-stu-id="22d23-106">In the **Navigation pane**, go to **Modules > Retail and Commerce > Pricing and discounts management > Price groups > All price groups**.</span></span> <span data-ttu-id="22d23-107">Les groupes de prix désignent la manière dont les accords commerciaux sont affectés à des canaux spécifiques.</span><span class="sxs-lookup"><span data-stu-id="22d23-107">Price groups are how trade agreements are assigned to specific channels.</span></span> <span data-ttu-id="22d23-108">L'utilisation de groupes de prix pour affecter des accords commerciaux à un canal active la tarification propre au canal.</span><span class="sxs-lookup"><span data-stu-id="22d23-108">Using price groups to assign trade agreements to a channel enables channel-specific pricing.</span></span>  
2. <span data-ttu-id="22d23-109">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="22d23-109">Click **New**.</span></span>
3. <span data-ttu-id="22d23-110">Tapez une valeur dans le champ **Groupes de prix**.</span><span class="sxs-lookup"><span data-stu-id="22d23-110">In the **Price groups** field, type a value.</span></span>
4. <span data-ttu-id="22d23-111">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="22d23-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="22d23-112">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="22d23-112">Click **Save**.</span></span>
6. <span data-ttu-id="22d23-113">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="22d23-113">Close the page.</span></span>
7. <span data-ttu-id="22d23-114">Dans le **Volet de navigation**, accédez à **Modules > Commerce et vente au détail > Canaux > Magasins > Tous les magasins**.</span><span class="sxs-lookup"><span data-stu-id="22d23-114">In the **Navigation pane**, go to **Modules > Retail and Commerce > Channels > Stores > All stores**.</span></span>
8. <span data-ttu-id="22d23-115">Dans la liste, sélectionnez « New York ».</span><span class="sxs-lookup"><span data-stu-id="22d23-115">In the list, select 'New York'</span></span>
9. <span data-ttu-id="22d23-116">Dans le volet Actions, cliquez sur **Magasin**.</span><span class="sxs-lookup"><span data-stu-id="22d23-116">On the Action Pane, click **Store**.</span></span>
10. <span data-ttu-id="22d23-117">Cliquez sur **Groupes de prix**.</span><span class="sxs-lookup"><span data-stu-id="22d23-117">Click **Price groups**.</span></span>
11. <span data-ttu-id="22d23-118">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="22d23-118">Click **New**.</span></span>
12. <span data-ttu-id="22d23-119">Dans le champ **Groupes de prix**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="22d23-119">In the **Price groups** field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="22d23-120">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="22d23-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="22d23-121">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="22d23-121">Click **Save**.</span></span>
15. <span data-ttu-id="22d23-122">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="22d23-122">Close the page.</span></span>
16. <span data-ttu-id="22d23-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="22d23-123">Close the page.</span></span>
17. <span data-ttu-id="22d23-124">Dans le **Volet de navigation**, accédez à **Modules > Commerce et vente au détail > Produits et catégories > Produits lancés par catégorie**.</span><span class="sxs-lookup"><span data-stu-id="22d23-124">In the **Navigation pane**, go to **Modules > Retail and Commerce > Products and categories > Released products by category**.</span></span>
18. <span data-ttu-id="22d23-125">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="22d23-125">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="22d23-126">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="22d23-126">Click **Edit**.</span></span>
20. <span data-ttu-id="22d23-127">Développez le raccourci **Vendre**.</span><span class="sxs-lookup"><span data-stu-id="22d23-127">Expand the **Sell** fastTab.</span></span>
21. <span data-ttu-id="22d23-128">Tapez un chiffre dans le champ **Prix**.</span><span class="sxs-lookup"><span data-stu-id="22d23-128">In the **Price** field, enter a number.</span></span> <span data-ttu-id="22d23-129">Ce prix est utilisé si aucun accord commercial applicable n'est trouvé.</span><span class="sxs-lookup"><span data-stu-id="22d23-129">This price is used if no applicable trade agreements are found.</span></span>  
22. <span data-ttu-id="22d23-130">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="22d23-130">Click **Save**.</span></span>
23. <span data-ttu-id="22d23-131">Dans le volet **Action**, cliquez sur **Vendre**.</span><span class="sxs-lookup"><span data-stu-id="22d23-131">On the **Action Pane**, click **Sell**.</span></span>
24. <span data-ttu-id="22d23-132">Cliquez sur **Créer des accords commerciaux**.</span><span class="sxs-lookup"><span data-stu-id="22d23-132">Click **Create trade agreements**.</span></span>
25. <span data-ttu-id="22d23-133">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="22d23-133">Click **New**.</span></span>
26. <span data-ttu-id="22d23-134">Dans le champ **Nom**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="22d23-134">In the **Name** field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="22d23-135">Dans la liste, sélectionnez **Commerce**.</span><span class="sxs-lookup"><span data-stu-id="22d23-135">In the list, select **Commerce**.</span></span> <span data-ttu-id="22d23-136">Dans les données de démonstration, le nom de journal **Commerce** a la relation par défaut **Prix (vente)**.</span><span class="sxs-lookup"><span data-stu-id="22d23-136">In the demo data, the **Commerce** journal name has the default relation of **Price (sales)**.</span></span> <span data-ttu-id="22d23-137">Cela signifie que toutes les lignes créées utilisent par défaut les accords commerciaux sur les prix de vente.</span><span class="sxs-lookup"><span data-stu-id="22d23-137">That means all new lines created will default to sales price trade agreements.</span></span>  
28. <span data-ttu-id="22d23-138">Dans le **Volet Actions**, cliquez sur **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="22d23-138">On the **Action pane**, click **Lines**.</span></span>
29. <span data-ttu-id="22d23-139">Sélectionnez « Groupe » dans le champ **Code de compte**.</span><span class="sxs-lookup"><span data-stu-id="22d23-139">In the **Account code** field, select 'Group'.</span></span>
30. <span data-ttu-id="22d23-140">Dans le champ **Sélection du compte**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="22d23-140">In the **Account selection** field, click the drop-down button to open the lookup.</span></span>
31. <span data-ttu-id="22d23-141">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="22d23-141">In the list, find and select the desired record.</span></span> <span data-ttu-id="22d23-142">Cela exécutera le lien entre le canal et le groupe de prix pour l'accord commercial.</span><span class="sxs-lookup"><span data-stu-id="22d23-142">This will complete the link from Channel to Price group to Trade agreement.</span></span>  
32. <span data-ttu-id="22d23-143">Tapez une valeur dans le champ **Relation d'article**.</span><span class="sxs-lookup"><span data-stu-id="22d23-143">In the **Item relation** field, type a value.</span></span>
33. <span data-ttu-id="22d23-144">Tapez un chiffre dans le champ **Montant en devise**.</span><span class="sxs-lookup"><span data-stu-id="22d23-144">In the **Amount in currency** field, enter a number.</span></span>
34. <span data-ttu-id="22d23-145">Dans l'organisateur **Détails**, activez ou désactivez la case à cocher **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="22d23-145">In the **Details** fastTab, check or uncheck the **Find next** checkbox.</span></span> <span data-ttu-id="22d23-146">Lorsque l'option **Suivant** est définie sur « Oui », le moteur de tarification continue de rechercher des accords commerciaux applicables avec un prix de vente inférieur.</span><span class="sxs-lookup"><span data-stu-id="22d23-146">When **Find next** is set to 'Yes', the pricing engine will continue to search for applicable trade agreements with a lower sale price.</span></span> <span data-ttu-id="22d23-147">Lorsque l'option **Suivant** est définie sur « Non », le moteur de tarification arrête la recherche et utilise l'accord commercial.</span><span class="sxs-lookup"><span data-stu-id="22d23-147">When **Find next** is set to 'No', the price engine stops searching and uses the trade agreement.</span></span>  
35. <span data-ttu-id="22d23-148">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="22d23-148">Click **Post**.</span></span>
36. <span data-ttu-id="22d23-149">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="22d23-149">Click **OK**.</span></span>
37. <span data-ttu-id="22d23-150">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="22d23-150">Close the page.</span></span>
38. <span data-ttu-id="22d23-151">Cliquez sur Vendre dans le volet **Actions**.</span><span class="sxs-lookup"><span data-stu-id="22d23-151">On the **Action Pane**, click Sell.</span></span>
39. <span data-ttu-id="22d23-152">Cliquez sur **Prix de vente**.</span><span class="sxs-lookup"><span data-stu-id="22d23-152">Click **Sales price**.</span></span>

