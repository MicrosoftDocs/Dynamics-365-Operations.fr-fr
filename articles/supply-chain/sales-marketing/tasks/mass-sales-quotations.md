---
title: Création en masse de devis de vente
description: Cette procédure illustre comment créer efficacement des devis offrant un ensemble de produits ou de services à envoyer à plusieurs clients.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTemplateGroup, SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SysQueryForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 77f7a2df813eb0bf211b72646c1e99306fdf3f88
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148605"
---
# <a name="mass-create-sales-quotations"></a><span data-ttu-id="44e53-103">Création en masse de devis de vente</span><span class="sxs-lookup"><span data-stu-id="44e53-103">Mass create sales quotations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="44e53-104">Cette procédure illustre comment créer efficacement des devis offrant un ensemble de produits ou de services à envoyer à plusieurs clients.</span><span class="sxs-lookup"><span data-stu-id="44e53-104">This procedure demonstrates how to efficiently create quotations offering a set of products or services that are to be sent to multiple customers.</span></span> <span data-ttu-id="44e53-105">Cette création de devis en masse est basée sur des modèles de devis.</span><span class="sxs-lookup"><span data-stu-id="44e53-105">This mass quotation creation is based on quotation templates.</span></span> <span data-ttu-id="44e53-106">Vous pouvez exécuter cette procédure avec vos propres données ou avec la société fictive de démonstration USMF.</span><span class="sxs-lookup"><span data-stu-id="44e53-106">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-quotation-template"></a><span data-ttu-id="44e53-107">Créer un modèle de devis</span><span class="sxs-lookup"><span data-stu-id="44e53-107">Create a quotation template</span></span>
1. <span data-ttu-id="44e53-108">Accédez à Ventes et marketing > Configuration > Devis > Groupes de modèles.</span><span class="sxs-lookup"><span data-stu-id="44e53-108">Go to Sales and marketing > Setup > Quotations > Template groups.</span></span>
2. <span data-ttu-id="44e53-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="44e53-109">Click New.</span></span>
3. <span data-ttu-id="44e53-110">Dans le champ ID groupe, tapez un ID de votre choix.</span><span class="sxs-lookup"><span data-stu-id="44e53-110">In the Group ID field, type an ID of your choice.</span></span>
4. <span data-ttu-id="44e53-111">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="44e53-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="44e53-112">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="44e53-112">Click Save.</span></span>
6. <span data-ttu-id="44e53-113">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="44e53-113">Close the page.</span></span>
7. <span data-ttu-id="44e53-114">Accédez à Ventes et marketing > Devis de vente > Tous les devis.</span><span class="sxs-lookup"><span data-stu-id="44e53-114">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
8. <span data-ttu-id="44e53-115">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="44e53-115">Click New.</span></span>
9. <span data-ttu-id="44e53-116">Sélectionnez « Client » dans le champ Type de compte.</span><span class="sxs-lookup"><span data-stu-id="44e53-116">In the Account type field, select 'Customer'.</span></span>
10. <span data-ttu-id="44e53-117">Entrez ou sélectionnez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="44e53-117">In the Customer account field, enter or select a value.</span></span>
11. <span data-ttu-id="44e53-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="44e53-118">Click OK.</span></span>
    * <span data-ttu-id="44e53-119">Pour qu'un devis devienne un modèle, vous devez effectuer des étapes de paramétrage dans l'en-tête du devis.</span><span class="sxs-lookup"><span data-stu-id="44e53-119">For a quotation to become a template you must carry out  setup steps on the quotation header.</span></span> <span data-ttu-id="44e53-120">Cela doit être effectué avant d'ajouter des lignes au devis.</span><span class="sxs-lookup"><span data-stu-id="44e53-120">This must be done before you add lines to the quotation.</span></span>   
12. <span data-ttu-id="44e53-121">Dans le volet Actions, cliquez sur Options.</span><span class="sxs-lookup"><span data-stu-id="44e53-121">On the Action Pane, click Options.</span></span>
13. <span data-ttu-id="44e53-122">Cliquez sur Changer de vue.</span><span class="sxs-lookup"><span data-stu-id="44e53-122">Click Change view.</span></span>
14. <span data-ttu-id="44e53-123">Cliquez sur Vue de l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="44e53-123">Click Header view.</span></span>
15. <span data-ttu-id="44e53-124">Développez la section Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="44e53-124">Expand the Setup section.</span></span>
16. <span data-ttu-id="44e53-125">Saisissez ou sélectionnez une valeur dans le champ ID groupe.</span><span class="sxs-lookup"><span data-stu-id="44e53-125">In the Group ID field, enter or select a value.</span></span>
17. <span data-ttu-id="44e53-126">Tapez une valeur dans le champ Nom de modèle.</span><span class="sxs-lookup"><span data-stu-id="44e53-126">In the Template name field, type a value.</span></span>
18. <span data-ttu-id="44e53-127">Sélectionnez Oui dans le champ Actif.</span><span class="sxs-lookup"><span data-stu-id="44e53-127">Select Yes in the Active field.</span></span>
    * <span data-ttu-id="44e53-128">Seuls les modèles actifs peuvent être utilisés lorsque vous appliquez un modèle à un nouveau devis de vente.</span><span class="sxs-lookup"><span data-stu-id="44e53-128">Only active templates can be used when you apply a template to a new sales quotation.</span></span>  
19. <span data-ttu-id="44e53-129">Dans le volet Actions, cliquez sur Options.</span><span class="sxs-lookup"><span data-stu-id="44e53-129">On the Action Pane, click Options.</span></span>
20. <span data-ttu-id="44e53-130">Cliquez sur Changer de vue.</span><span class="sxs-lookup"><span data-stu-id="44e53-130">Click Change view.</span></span>
21. <span data-ttu-id="44e53-131">Cliquez sur Affichage des lignes.</span><span class="sxs-lookup"><span data-stu-id="44e53-131">Click Line view.</span></span>
22. <span data-ttu-id="44e53-132">Dans le champ Article, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="44e53-132">In the Item field, enter or select a value.</span></span>
23. <span data-ttu-id="44e53-133">Dans le champ Article, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="44e53-133">In the Item field, type a value.</span></span>
24. <span data-ttu-id="44e53-134">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="44e53-134">Close the page.</span></span>
25. <span data-ttu-id="44e53-135">Entrez un nombre dans le champ Pourcentage de remise.</span><span class="sxs-lookup"><span data-stu-id="44e53-135">In the Discount percent field, enter a number.</span></span>
26. <span data-ttu-id="44e53-136">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="44e53-136">Click Add line.</span></span>
27. <span data-ttu-id="44e53-137">Dans le champ Article, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="44e53-137">In the Item field, enter or select a value.</span></span>
28. <span data-ttu-id="44e53-138">Dans le champ Article, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="44e53-138">In the Item field, type a value.</span></span>
29. <span data-ttu-id="44e53-139">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="44e53-139">Close the page.</span></span>
30. <span data-ttu-id="44e53-140">Dans le champ Prix unitaire, entrez un nouveau prix ou modifiez le prix actuel.</span><span class="sxs-lookup"><span data-stu-id="44e53-140">In the Unit price field, enter a new price or change the current one.</span></span>
31. <span data-ttu-id="44e53-141">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="44e53-141">Click Add line.</span></span>
32. <span data-ttu-id="44e53-142">Dans le champ Article, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="44e53-142">In the Item field, enter or select a value.</span></span>
33. <span data-ttu-id="44e53-143">Dans le champ Article, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="44e53-143">In the Item field, type a value.</span></span>
34. <span data-ttu-id="44e53-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="44e53-144">Close the page.</span></span>
35. <span data-ttu-id="44e53-145">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="44e53-145">In the Quantity field, enter a number.</span></span>
36. <span data-ttu-id="44e53-146">Entrez un nombre dans le champ Remise.</span><span class="sxs-lookup"><span data-stu-id="44e53-146">In the Discount field, enter a number.</span></span>
37. <span data-ttu-id="44e53-147">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="44e53-147">Click Save.</span></span>

## <a name="apply-the-template-to-create-a-single-quotation"></a><span data-ttu-id="44e53-148">Appliquer le modèle pour créer un devis unique</span><span class="sxs-lookup"><span data-stu-id="44e53-148">Apply the template to create a single quotation</span></span>
1. <span data-ttu-id="44e53-149">Accédez à Ventes et marketing > Devis de vente > Tous les devis.</span><span class="sxs-lookup"><span data-stu-id="44e53-149">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="44e53-150">Notez que le devis que vous venez de créer est marqué comme modèle.</span><span class="sxs-lookup"><span data-stu-id="44e53-150">Note that the quotation you have just created is marked as template.</span></span>  
2. <span data-ttu-id="44e53-151">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="44e53-151">Click New.</span></span>
3. <span data-ttu-id="44e53-152">Sélectionnez « Client » dans le champ Type de compte.</span><span class="sxs-lookup"><span data-stu-id="44e53-152">In the Account type field, select 'Customer'.</span></span>
4. <span data-ttu-id="44e53-153">Entrez ou sélectionnez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="44e53-153">In the Customer account field, enter or select a value.</span></span>
5. <span data-ttu-id="44e53-154">Développez la section Modèle.</span><span class="sxs-lookup"><span data-stu-id="44e53-154">Expand the Template section.</span></span>
6. <span data-ttu-id="44e53-155">Saisissez ou sélectionnez une valeur dans le champ ID groupe.</span><span class="sxs-lookup"><span data-stu-id="44e53-155">In the Group ID field, enter or select a value.</span></span>
7. <span data-ttu-id="44e53-156">Saisissez ou sélectionnez une valeur dans le champ Nom du modèle.</span><span class="sxs-lookup"><span data-stu-id="44e53-156">In the Template name field, enter or select a value.</span></span>
8. <span data-ttu-id="44e53-157">Dans le champ Mode de calcul, sélectionnez « En fonction des valeurs du modèle ».</span><span class="sxs-lookup"><span data-stu-id="44e53-157">In the Calculation method field, select 'Based on template values'.</span></span>
9. <span data-ttu-id="44e53-158">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="44e53-158">Click OK.</span></span>
    * <span data-ttu-id="44e53-159">Le nouveau devis a maintenant été créé, en fonction des données et des conditions du modèle.</span><span class="sxs-lookup"><span data-stu-id="44e53-159">The new quotation has now been created, based on the data and terms of the template.</span></span>  
10. <span data-ttu-id="44e53-160">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="44e53-160">Close the page.</span></span>
11. <span data-ttu-id="44e53-161">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="44e53-161">Close the page.</span></span>

## <a name="apply-the-template-to-mass-create-quotations"></a><span data-ttu-id="44e53-162">Appliquer le modèle à la création en masse de devis</span><span class="sxs-lookup"><span data-stu-id="44e53-162">Apply the template to mass create quotations</span></span>
1. <span data-ttu-id="44e53-163">Accédez à Ventes et marketing > Devis de vente > Mise à jour du devis > Création en masse de devis.</span><span class="sxs-lookup"><span data-stu-id="44e53-163">Go to Sales and marketing > Sales quotations > Quotation update > Mass create quotations.</span></span>
2. <span data-ttu-id="44e53-164">Sélectionnez « Client » dans le champ Type de compte.</span><span class="sxs-lookup"><span data-stu-id="44e53-164">In the Account type field, select 'Customer'.</span></span>
3. <span data-ttu-id="44e53-165">Saisissez ou sélectionnez une valeur dans le champ ID groupe.</span><span class="sxs-lookup"><span data-stu-id="44e53-165">In the Group ID field, enter or select a value.</span></span>
4. <span data-ttu-id="44e53-166">Saisissez ou sélectionnez une valeur dans le champ Nom du modèle.</span><span class="sxs-lookup"><span data-stu-id="44e53-166">In the Template name field, enter or select a value.</span></span>
5. <span data-ttu-id="44e53-167">Dans le champ Mode de calcul, sélectionnez « En fonction des valeurs du modèle ».</span><span class="sxs-lookup"><span data-stu-id="44e53-167">In the Calculation method field, select 'Based on template values'.</span></span>
6. <span data-ttu-id="44e53-168">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="44e53-168">Expand the Records to include section.</span></span>
7. <span data-ttu-id="44e53-169">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="44e53-169">Click Filter.</span></span>
8. <span data-ttu-id="44e53-170">Dans le champ Critères définissez le filtre de sorte à couvrir une gamme de clients à inclure dans cette création en masse de devis.</span><span class="sxs-lookup"><span data-stu-id="44e53-170">In the Criteria field, set the filter to cover a range of customers you want to include in this mass quotation creation.</span></span> <span data-ttu-id="44e53-171">Utilisez le format suivant : "Client1..ClientN.</span><span class="sxs-lookup"><span data-stu-id="44e53-171">Use the following format "Customer1..CustomerN.</span></span>
    * <span data-ttu-id="44e53-172">Par exemple, vous pouvez définir le filtre sur : US-001...US-004</span><span class="sxs-lookup"><span data-stu-id="44e53-172">For example, you could set the filter to: US-001..US-004</span></span>  
9. <span data-ttu-id="44e53-173">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="44e53-173">Click OK.</span></span>
10. <span data-ttu-id="44e53-174">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="44e53-174">Click OK.</span></span>
11. <span data-ttu-id="44e53-175">Accédez à Ventes et marketing > Devis de vente > Tous les devis.</span><span class="sxs-lookup"><span data-stu-id="44e53-175">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="44e53-176">Vérifiez que des devis ont été créés pour tous les clients spécifiés dans la routine de mise à jour collective, comme l'indique le modèle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="44e53-176">Verify that quotations have been created for all the customers specified in the mass update routine, as based on the selected template.</span></span>  

