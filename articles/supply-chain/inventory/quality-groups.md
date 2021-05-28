---
title: Groupes de qualité d'article
description: Cette rubrique décrit comment utiliser et créer des groupes de qualité d'article pour regrouper logiquement des produits afin qu'ils puissent être affectés à des associations de qualité pour la génération automatique d'ordres de qualité.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestQualityGroup, InventTestItemQualityGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 272cb748e0a2722d9744fe6b357d767a1d6aeb26
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022250"
---
# <a name="item-quality-groups"></a><span data-ttu-id="b1644-103">Groupes de qualité d'article</span><span class="sxs-lookup"><span data-stu-id="b1644-103">Item quality groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b1644-104">Un groupe de qualité représente des besoins de test communs pour les articles.</span><span class="sxs-lookup"><span data-stu-id="b1644-104">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="b1644-105">Cette rubrique décrit comment utiliser et créer des groupes de qualité d'article pour regrouper logiquement des produits afin qu'ils puissent être affectés à des associations de qualité pour la génération automatique d'ordres de qualité.</span><span class="sxs-lookup"><span data-stu-id="b1644-105">This topic describes how to use and create item quality groups to logically group products so that they can be assigned to quality associations for the automatic generation of quality orders.</span></span>

<span data-ttu-id="b1644-106">Pour paramétrer, modifier et afficher les articles affectés à un groupe de qualité ou les groupes de qualité affectés à un article, accédez à **Gestion des stocks \> Paramétrage \> Groupes de qualité**.</span><span class="sxs-lookup"><span data-stu-id="b1644-106">To set up, edit, and view the items that are assigned to a quality group, or the quality groups that are assigned to an item, go to **Inventory management \> Setup \> Quality groups**.</span></span> <span data-ttu-id="b1644-107">Une fois que vous avez défini les besoins de test sur la page **Groupes de test**, vous pouvez définir les règles de génération automatique des ordres de qualité.</span><span class="sxs-lookup"><span data-stu-id="b1644-107">After you define the test requirements on the **Test groups** page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="b1644-108">Pour simplifier le processus, vous ne devez pas définir de règles pour des articles individuels.</span><span class="sxs-lookup"><span data-stu-id="b1644-108">To simplify the process, you don't define rules for individual items.</span></span> <span data-ttu-id="b1644-109">Au lieu de cela, vous pouvez définir des règles pour un groupe de qualité sur la page **Associations de qualité**.</span><span class="sxs-lookup"><span data-stu-id="b1644-109">Instead, you can define the rules for a quality group on the **Quality associations** page.</span></span>

## <a name="example-of-an-item-quality-group"></a><span data-ttu-id="b1644-110">Exemple de groupe de qualité d'article</span><span class="sxs-lookup"><span data-stu-id="b1644-110">Example of an item quality group</span></span>

<span data-ttu-id="b1644-111">Une société de fabrication achète diverses matières premières présentant les mêmes besoins de test pour l’inspection à venir.</span><span class="sxs-lookup"><span data-stu-id="b1644-111">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="b1644-112">Par conséquent, la société définit un groupe de qualité, puis affecte les numéros d’articles associés aux matières premières à ce groupe.</span><span class="sxs-lookup"><span data-stu-id="b1644-112">Therefore, the company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="b1644-113">Ensuite, la société achète un nouveau type de matières premières ayant les mêmes besoins de test.</span><span class="sxs-lookup"><span data-stu-id="b1644-113">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="b1644-114">Au lieu de paramétrer de nouveaux besoins de test pour les nouvelles matières, la société ajoute le numéro d’article pour la nouvelle matière au groupe de qualité existant.</span><span class="sxs-lookup"><span data-stu-id="b1644-114">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span>

<span data-ttu-id="b1644-115">La même société produit également des articles ayant les mêmes besoins de test de production et expédie les articles dotés des mêmes besoins en tests de pré-expédition.</span><span class="sxs-lookup"><span data-stu-id="b1644-115">The same company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="b1644-116">Par conséquent, la société définit deux groupes de qualité supplémentaires, puis affecte les numéros d’articles pertinents à chaque groupe.</span><span class="sxs-lookup"><span data-stu-id="b1644-116">Therefore, the company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span>

## <a name="create-a-quality-group"></a><span data-ttu-id="b1644-117">Créer un groupe de qualité</span><span class="sxs-lookup"><span data-stu-id="b1644-117">Create a quality group</span></span>

<span data-ttu-id="b1644-118">Pour créer un groupe de qualité, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b1644-118">To create a quality group, follow these steps.</span></span>

1. <span data-ttu-id="b1644-119">Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Groupes de qualité**.</span><span class="sxs-lookup"><span data-stu-id="b1644-119">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="b1644-120">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="b1644-120">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="b1644-121">Définissez ensuite les champs suivants pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="b1644-121">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="b1644-122">**Groupe qualité** - Saisissez un identifiant ou un nom unique pour le groupe de qualité.</span><span class="sxs-lookup"><span data-stu-id="b1644-122">**Quality group** – Enter a unique ID or name for the quality group.</span></span>
    - <span data-ttu-id="b1644-123">**Description** - Entrez une description détaillée du groupe de qualité.</span><span class="sxs-lookup"><span data-stu-id="b1644-123">**Description** – Enter a detailed description of the quality group.</span></span>

1. <span data-ttu-id="b1644-124">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b1644-124">Close the page.</span></span>

## <a name="manually-add-items-to-a-quality-group"></a><span data-ttu-id="b1644-125">Ajouter manuellement des articles à un groupe de qualité</span><span class="sxs-lookup"><span data-stu-id="b1644-125">Manually add items to a quality group</span></span>

<span data-ttu-id="b1644-126">Pour ajouter manuellement des éléments à un groupe de qualité, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b1644-126">To manually add items to a quality group, follow these steps.</span></span>

1. <span data-ttu-id="b1644-127">Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Groupes de qualité**.</span><span class="sxs-lookup"><span data-stu-id="b1644-127">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="b1644-128">Sélectionnez le groupe de qualité auquel vous souhaitez ajouter des éléments.</span><span class="sxs-lookup"><span data-stu-id="b1644-128">Select the quality group that you want to add items to.</span></span>
1. <span data-ttu-id="b1644-129">Dans le volet Actions, sélectionnez **Articles**.</span><span class="sxs-lookup"><span data-stu-id="b1644-129">On the Action Pane, select **Items**.</span></span>
1. <span data-ttu-id="b1644-130">Sur la page **Articles dans les groupes de qualité**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="b1644-130">On the **Items in quality groups** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="b1644-131">Ensuite, pour la nouvelle ligne, définissez le champ **Numéro d'article** du numéro d'article que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1644-131">Then, for the new row, set the **Item number** field to the item number that you want to add.</span></span>
1. <span data-ttu-id="b1644-132">Répétez l'étape précédente pour chaque article supplémentaire à ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1644-132">Repeat the previous step for each additional item that must be added.</span></span>
1. <span data-ttu-id="b1644-133">Fermez les pages.</span><span class="sxs-lookup"><span data-stu-id="b1644-133">Close the pages.</span></span>

## <a name="add-multiple-items-to-a-quality-group"></a><span data-ttu-id="b1644-134">Ajouter plusieurs articles à un groupe de qualité</span><span class="sxs-lookup"><span data-stu-id="b1644-134">Add multiple items to a quality group</span></span>

<span data-ttu-id="b1644-135">Pour ajouter plusieurs articles à un groupe de qualité, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b1644-135">To add multiple items to a quality group, follow these steps.</span></span>

1. <span data-ttu-id="b1644-136">Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Groupes de qualité**.</span><span class="sxs-lookup"><span data-stu-id="b1644-136">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="b1644-137">Créez ou sélectionnez le groupe de qualité auquel vous souhaitez ajouter des éléments.</span><span class="sxs-lookup"><span data-stu-id="b1644-137">Create or select the quality group that you want to add items to.</span></span>
1. <span data-ttu-id="b1644-138">Dans le volet Actions, sélectionnez **Ajouter des articles**.</span><span class="sxs-lookup"><span data-stu-id="b1644-138">On the Action Pane, select **Add items**.</span></span>
1. <span data-ttu-id="b1644-139">Dans la boîte de dialogue **Recherche**, entrez les critères de filtre pour les éléments que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1644-139">In the **Inquiry** dialog box, enter the filter criteria for the items that you want to add.</span></span> <span data-ttu-id="b1644-140">Par exemple, vous pouvez filtrer tous les éléments d'un groupe d'éléments spécifique.</span><span class="sxs-lookup"><span data-stu-id="b1644-140">For example, you might filter for all items in a specific item group.</span></span>
1. <span data-ttu-id="b1644-141">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1644-141">Select **OK**.</span></span>
1. <span data-ttu-id="b1644-142">Dans la boîte de dialogue **Ajouter des articles**, une grille affiche tous les éléments qui correspondent à votre requête.</span><span class="sxs-lookup"><span data-stu-id="b1644-142">In the **Add items** dialog box, a grid shows all the items that match your query.</span></span> <span data-ttu-id="b1644-143">Examinez les résultats.</span><span class="sxs-lookup"><span data-stu-id="b1644-143">Review the results.</span></span>

    <span data-ttu-id="b1644-144">Si des modifications sont nécessaires, sélectionnez **Sélectionner** pour revenir dans la boîte de dialogue **Recherche** et modifiez votre requête.</span><span class="sxs-lookup"><span data-stu-id="b1644-144">If any changes are required, select **Select** to return to the **Inquiry** dialog box, and adjust your query.</span></span>

1. <span data-ttu-id="b1644-145">Lorsque les résultats incluent tous les éléments que vous souhaitez ajouter, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1644-145">When the results include all the items that you want to add, select **OK**.</span></span>
1. <span data-ttu-id="b1644-146">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b1644-146">Close the page.</span></span>

## <a name="manually-associate-an-item-with-a-quality-group"></a><span data-ttu-id="b1644-147">Associer manuellement un article à un groupe de qualité</span><span class="sxs-lookup"><span data-stu-id="b1644-147">Manually associate an item with a quality group</span></span>

<span data-ttu-id="b1644-148">Pour associer manuellement un article à un groupe de qualité, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b1644-148">To manually associate an item with a quality group, follow these steps.</span></span>

1. <span data-ttu-id="b1644-149">Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Groupes de qualité d’article**.</span><span class="sxs-lookup"><span data-stu-id="b1644-149">Go to **Inventory management \> Setup \> Quality control \> Item quality groups**.</span></span>
1. <span data-ttu-id="b1644-150">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="b1644-150">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="b1644-151">Définissez ensuite les champs suivants pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="b1644-151">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="b1644-152">**Numéro d'article** - Sélectionnez le numéro d'article à ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1644-152">**Item number** – Select the item number to add.</span></span>
    - <span data-ttu-id="b1644-153">**Groupe de qualité** - Sélectionnez le groupe de qualité à attribuer à l'article.</span><span class="sxs-lookup"><span data-stu-id="b1644-153">**Quality group** – Select the quality group to assign to the item.</span></span>

1. <span data-ttu-id="b1644-154">Répétez l'étape précédente pour chaque combinaison supplémentaire d'un article et d'un groupe de qualité à ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1644-154">Repeat the previous step for each additional combination of an item and a quality group that must be added.</span></span>
1. <span data-ttu-id="b1644-155">Fermez les pages.</span><span class="sxs-lookup"><span data-stu-id="b1644-155">Close the pages.</span></span>

## <a name="manually-add-a-quality-group-from-the-released-products-page"></a><span data-ttu-id="b1644-156">Ajouter manuellement un groupe de qualité à partir de la page Produits lancés</span><span class="sxs-lookup"><span data-stu-id="b1644-156">Manually add a quality group from the Released products page</span></span>

<span data-ttu-id="b1644-157">Pour ajouter manuellement un groupe de qualité à partir de la page **Produits lancés**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b1644-157">To manually add a quality group from the **Released products** page, follow these steps.</span></span>

1. <span data-ttu-id="b1644-158">Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="b1644-158">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="b1644-159">Sélectionnez le produit auquel affecter un groupe de qualité.</span><span class="sxs-lookup"><span data-stu-id="b1644-159">Select the product that you want to assign a quality group to.</span></span>
1. <span data-ttu-id="b1644-160">Dans le volet Actions, sous l’onglet **Gérer le stock**, dans le groupe **Qualité**, sélectionnez **Groupes de qualité d’article**.</span><span class="sxs-lookup"><span data-stu-id="b1644-160">On the Action Pane, on the **Manage inventory** tab, in the **Quality** group, select **Item quality groups**.</span></span>
1. <span data-ttu-id="b1644-161">Sur la page **Articles dans les groupes de qualité**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="b1644-161">On the **Items in quality groups** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="b1644-162">Ensuite, pour la nouvelle ligne, définissez le champ **Groupe qualité** du groupe de qualité que vous souhaitez affecter au produit.</span><span class="sxs-lookup"><span data-stu-id="b1644-162">Then, for the new row, set the **Quality group** field to the quality group that you want to assign to the product.</span></span>
1. <span data-ttu-id="b1644-163">Répétez l'étape précédente pour chaque groupe de qualité supplémentaire que vous souhaitez attribuer au produit.</span><span class="sxs-lookup"><span data-stu-id="b1644-163">Repeat the previous step for each additional quality group that you want to assign to the product.</span></span>
1. <span data-ttu-id="b1644-164">Fermez les pages.</span><span class="sxs-lookup"><span data-stu-id="b1644-164">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b1644-165">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b1644-165">Additional resources</span></span>

- [<span data-ttu-id="b1644-166">Instruments de test de gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="b1644-166">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="b1644-167">Tests de gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="b1644-167">Quality management tests</span></span>](quality-tests.md)
- [<span data-ttu-id="b1644-168">Groupes de tests de gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="b1644-168">Quality management test groups</span></span>](quality-test-groups.md)
- [<span data-ttu-id="b1644-169">Variables de test de gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="b1644-169">Quality management test variables</span></span>](quality-test-variables.md)
- [<span data-ttu-id="b1644-170">Associations de qualité</span><span class="sxs-lookup"><span data-stu-id="b1644-170">Quality associations</span></span>](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
