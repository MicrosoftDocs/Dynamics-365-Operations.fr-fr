---
title: Prix de base et accords commerciaux
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
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bab25988a9d4aad4d4e36fd9bdffbbf52473435e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259462"
---
# <a name="base-price-and-trade-agreements"></a><span data-ttu-id="31041-103">Prix de base et accords commerciaux</span><span class="sxs-lookup"><span data-stu-id="31041-103">Base price and trade agreements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="31041-104">Cette procédure décrit la création d'accords commerciaux sur les prix de vente spécifiques au canal.</span><span class="sxs-lookup"><span data-stu-id="31041-104">This procedure walks through creating channel-specific sales price trade agreements.</span></span> <span data-ttu-id="31041-105">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="31041-105">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="31041-106">Dans le **Volet de navigation**, accédez à **Modules > Commerce et vente au détail > Gestion de la tarification et des remises > Groupes de prix > Tous les groupes de prix**.</span><span class="sxs-lookup"><span data-stu-id="31041-106">In the **Navigation pane**, go to **Modules > Retail and Commerce > Pricing and discounts management > Price groups > All price groups**.</span></span> <span data-ttu-id="31041-107">Les groupes de prix désignent la manière dont les accords commerciaux sont affectés à des canaux spécifiques.</span><span class="sxs-lookup"><span data-stu-id="31041-107">Price groups are how trade agreements are assigned to specific channels.</span></span> <span data-ttu-id="31041-108">L'utilisation de groupes de prix pour affecter des accords commerciaux à un canal active la tarification propre au canal.</span><span class="sxs-lookup"><span data-stu-id="31041-108">Using price groups to assign trade agreements to a channel enables channel-specific pricing.</span></span>  
2. <span data-ttu-id="31041-109">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="31041-109">Click **New**.</span></span>
3. <span data-ttu-id="31041-110">Tapez une valeur dans le champ **Groupes de prix**.</span><span class="sxs-lookup"><span data-stu-id="31041-110">In the **Price groups** field, type a value.</span></span>
4. <span data-ttu-id="31041-111">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="31041-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="31041-112">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="31041-112">Click **Save**.</span></span>
6. <span data-ttu-id="31041-113">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="31041-113">Close the page.</span></span>
7. <span data-ttu-id="31041-114">Dans le **Volet de navigation**, accédez à **Modules > Commerce et vente au détail > Canaux > Magasins > Tous les magasins**.</span><span class="sxs-lookup"><span data-stu-id="31041-114">In the **Navigation pane**, go to **Modules > Retail and Commerce > Channels > Stores > All stores**.</span></span>
8. <span data-ttu-id="31041-115">Dans la liste, sélectionnez « New York ».</span><span class="sxs-lookup"><span data-stu-id="31041-115">In the list, select 'New York'</span></span>
9. <span data-ttu-id="31041-116">Dans le volet Actions, cliquez sur **Magasin**.</span><span class="sxs-lookup"><span data-stu-id="31041-116">On the Action Pane, click **Store**.</span></span>
10. <span data-ttu-id="31041-117">Cliquez sur **Groupes de prix**.</span><span class="sxs-lookup"><span data-stu-id="31041-117">Click **Price groups**.</span></span>
11. <span data-ttu-id="31041-118">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="31041-118">Click **New**.</span></span>
12. <span data-ttu-id="31041-119">Dans le champ **Groupes de prix**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="31041-119">In the **Price groups** field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="31041-120">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="31041-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="31041-121">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="31041-121">Click **Save**.</span></span>
15. <span data-ttu-id="31041-122">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="31041-122">Close the page.</span></span>
16. <span data-ttu-id="31041-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="31041-123">Close the page.</span></span>
17. <span data-ttu-id="31041-124">Dans le **Volet de navigation**, accédez à **Modules > Commerce et vente au détail > Produits et catégories > Produits lancés par catégorie**.</span><span class="sxs-lookup"><span data-stu-id="31041-124">In the **Navigation pane**, go to **Modules > Retail and Commerce > Products and categories > Released products by category**.</span></span>
18. <span data-ttu-id="31041-125">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="31041-125">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="31041-126">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="31041-126">Click **Edit**.</span></span>
20. <span data-ttu-id="31041-127">Développez le raccourci **Vendre**.</span><span class="sxs-lookup"><span data-stu-id="31041-127">Expand the **Sell** fastTab.</span></span>
21. <span data-ttu-id="31041-128">Tapez un chiffre dans le champ **Prix**.</span><span class="sxs-lookup"><span data-stu-id="31041-128">In the **Price** field, enter a number.</span></span> <span data-ttu-id="31041-129">Ce prix est utilisé si aucun accord commercial applicable n'est trouvé.</span><span class="sxs-lookup"><span data-stu-id="31041-129">This price is used if no applicable trade agreements are found.</span></span>  
22. <span data-ttu-id="31041-130">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="31041-130">Click **Save**.</span></span>
23. <span data-ttu-id="31041-131">Dans le volet **Action**, cliquez sur **Vendre**.</span><span class="sxs-lookup"><span data-stu-id="31041-131">On the **Action Pane**, click **Sell**.</span></span>
24. <span data-ttu-id="31041-132">Cliquez sur **Créer des accords commerciaux**.</span><span class="sxs-lookup"><span data-stu-id="31041-132">Click **Create trade agreements**.</span></span>
25. <span data-ttu-id="31041-133">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="31041-133">Click **New**.</span></span>
26. <span data-ttu-id="31041-134">Dans le champ **Nom**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="31041-134">In the **Name** field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="31041-135">Dans la liste, sélectionnez **Commerce**.</span><span class="sxs-lookup"><span data-stu-id="31041-135">In the list, select **Commerce**.</span></span> <span data-ttu-id="31041-136">Dans les données de démonstration, le nom de journal **Commerce** a la relation par défaut **Prix (vente)**.</span><span class="sxs-lookup"><span data-stu-id="31041-136">In the demo data, the **Commerce** journal name has the default relation of **Price (sales)**.</span></span> <span data-ttu-id="31041-137">Cela signifie que toutes les lignes créées utilisent par défaut les accords commerciaux sur les prix de vente.</span><span class="sxs-lookup"><span data-stu-id="31041-137">That means all new lines created will default to sales price trade agreements.</span></span>  
28. <span data-ttu-id="31041-138">Dans le **Volet Actions**, cliquez sur **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="31041-138">On the **Action pane**, click **Lines**.</span></span>
29. <span data-ttu-id="31041-139">Dans le champ **Type de code partie**, sélectionnez « Groupe ».</span><span class="sxs-lookup"><span data-stu-id="31041-139">In the **Party code type** field, select 'Group'.</span></span>
30. <span data-ttu-id="31041-140">Dans le champ **Sélection du compte**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="31041-140">In the **Account selection** field, click the drop-down button to open the lookup.</span></span>
31. <span data-ttu-id="31041-141">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="31041-141">In the list, find and select the desired record.</span></span> <span data-ttu-id="31041-142">Cela exécutera le lien entre le canal et le groupe de prix pour l'accord commercial.</span><span class="sxs-lookup"><span data-stu-id="31041-142">This will complete the link from Channel to Price group to Trade agreement.</span></span>  
32. <span data-ttu-id="31041-143">Tapez une valeur dans le champ **Relation d'article**.</span><span class="sxs-lookup"><span data-stu-id="31041-143">In the **Item relation** field, type a value.</span></span>
33. <span data-ttu-id="31041-144">Tapez un chiffre dans le champ **Montant en devise**.</span><span class="sxs-lookup"><span data-stu-id="31041-144">In the **Amount in currency** field, enter a number.</span></span>
34. <span data-ttu-id="31041-145">Dans l'organisateur **Détails**, activez ou désactivez la case à cocher **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="31041-145">In the **Details** fastTab, check or uncheck the **Find next** checkbox.</span></span> <span data-ttu-id="31041-146">Lorsque l'option **Suivant** est définie sur « Oui », le moteur de tarification continue de rechercher des accords commerciaux applicables avec un prix de vente inférieur.</span><span class="sxs-lookup"><span data-stu-id="31041-146">When **Find next** is set to 'Yes', the pricing engine will continue to search for applicable trade agreements with a lower sale price.</span></span> <span data-ttu-id="31041-147">Lorsque l'option **Suivant** est définie sur « Non », le moteur de tarification arrête la recherche et utilise l'accord commercial.</span><span class="sxs-lookup"><span data-stu-id="31041-147">When **Find next** is set to 'No', the price engine stops searching and uses the trade agreement.</span></span>  
35. <span data-ttu-id="31041-148">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="31041-148">Click **Post**.</span></span>
36. <span data-ttu-id="31041-149">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="31041-149">Click **OK**.</span></span>
37. <span data-ttu-id="31041-150">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="31041-150">Close the page.</span></span>
38. <span data-ttu-id="31041-151">Cliquez sur Vendre dans le volet **Actions**.</span><span class="sxs-lookup"><span data-stu-id="31041-151">On the **Action Pane**, click Sell.</span></span>
39. <span data-ttu-id="31041-152">Cliquez sur **Prix de vente**.</span><span class="sxs-lookup"><span data-stu-id="31041-152">Click **Sales price**.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]