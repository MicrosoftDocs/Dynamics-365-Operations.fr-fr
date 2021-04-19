---
title: Création en masse de devis de vente
description: Cette procédure illustre comment créer efficacement des devis offrant un ensemble de produits ou de services à envoyer à plusieurs clients.
author: omulvad
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesQuotationTemplateGroup, SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SysQueryForm, SalesQuickQuote
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0422817576d9d93d0ec6bbfb5f3777013ee09ece
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817699"
---
# <a name="mass-create-sales-quotations"></a><span data-ttu-id="1add1-103">Création en masse de devis de vente</span><span class="sxs-lookup"><span data-stu-id="1add1-103">Mass create sales quotations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1add1-104">Cette procédure illustre comment créer efficacement des devis offrant un ensemble de produits ou de services à envoyer à plusieurs clients.</span><span class="sxs-lookup"><span data-stu-id="1add1-104">This procedure demonstrates how to efficiently create quotations offering a set of products or services that are to be sent to multiple customers.</span></span> <span data-ttu-id="1add1-105">Cette création de devis en masse est basée sur des modèles de devis.</span><span class="sxs-lookup"><span data-stu-id="1add1-105">This mass quotation creation is based on quotation templates.</span></span> <span data-ttu-id="1add1-106">Vous pouvez exécuter cette procédure avec vos propres données ou avec la société fictive de démonstration USMF.</span><span class="sxs-lookup"><span data-stu-id="1add1-106">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-quotation-template"></a><span data-ttu-id="1add1-107">Créer un modèle de devis</span><span class="sxs-lookup"><span data-stu-id="1add1-107">Create a quotation template</span></span>
1. <span data-ttu-id="1add1-108">Accédez à Ventes et marketing > Configuration > Devis > Groupes de modèles.</span><span class="sxs-lookup"><span data-stu-id="1add1-108">Go to Sales and marketing > Setup > Quotations > Template groups.</span></span>
2. <span data-ttu-id="1add1-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="1add1-109">Click New.</span></span>
3. <span data-ttu-id="1add1-110">Dans le champ ID groupe, tapez un ID de votre choix.</span><span class="sxs-lookup"><span data-stu-id="1add1-110">In the Group ID field, type an ID of your choice.</span></span>
4. <span data-ttu-id="1add1-111">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1add1-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1add1-112">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1add1-112">Click Save.</span></span>
6. <span data-ttu-id="1add1-113">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1add1-113">Close the page.</span></span>
7. <span data-ttu-id="1add1-114">Accédez à Ventes et marketing > Devis de vente > Tous les devis.</span><span class="sxs-lookup"><span data-stu-id="1add1-114">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
8. <span data-ttu-id="1add1-115">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="1add1-115">Click New.</span></span>
9. <span data-ttu-id="1add1-116">Sélectionnez « Client » dans le champ Type de compte.</span><span class="sxs-lookup"><span data-stu-id="1add1-116">In the Account type field, select 'Customer'.</span></span>
10. <span data-ttu-id="1add1-117">Entrez ou sélectionnez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="1add1-117">In the Customer account field, enter or select a value.</span></span>
11. <span data-ttu-id="1add1-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1add1-118">Click OK.</span></span>
    * <span data-ttu-id="1add1-119">Pour qu’un devis devienne un modèle, vous devez effectuer des étapes de paramétrage dans l’en-tête du devis.</span><span class="sxs-lookup"><span data-stu-id="1add1-119">For a quotation to become a template you must carry out  setup steps on the quotation header.</span></span> <span data-ttu-id="1add1-120">Cela doit être effectué avant d’ajouter des lignes au devis.</span><span class="sxs-lookup"><span data-stu-id="1add1-120">This must be done before you add lines to the quotation.</span></span>   
12. <span data-ttu-id="1add1-121">Dans le volet Actions, cliquez sur Options.</span><span class="sxs-lookup"><span data-stu-id="1add1-121">On the Action Pane, click Options.</span></span>
13. <span data-ttu-id="1add1-122">Cliquez sur Changer de vue.</span><span class="sxs-lookup"><span data-stu-id="1add1-122">Click Change view.</span></span>
14. <span data-ttu-id="1add1-123">Cliquez sur Vue de l’en-tête.</span><span class="sxs-lookup"><span data-stu-id="1add1-123">Click Header view.</span></span>
15. <span data-ttu-id="1add1-124">Développez la section Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="1add1-124">Expand the Setup section.</span></span>
16. <span data-ttu-id="1add1-125">Saisissez ou sélectionnez une valeur dans le champ ID groupe.</span><span class="sxs-lookup"><span data-stu-id="1add1-125">In the Group ID field, enter or select a value.</span></span>
17. <span data-ttu-id="1add1-126">Tapez une valeur dans le champ Nom de modèle.</span><span class="sxs-lookup"><span data-stu-id="1add1-126">In the Template name field, type a value.</span></span>
18. <span data-ttu-id="1add1-127">Sélectionnez Oui dans le champ Actif.</span><span class="sxs-lookup"><span data-stu-id="1add1-127">Select Yes in the Active field.</span></span>
    * <span data-ttu-id="1add1-128">Seuls les modèles actifs peuvent être utilisés lorsque vous appliquez un modèle à un nouveau devis de vente.</span><span class="sxs-lookup"><span data-stu-id="1add1-128">Only active templates can be used when you apply a template to a new sales quotation.</span></span>  
19. <span data-ttu-id="1add1-129">Dans le volet Actions, cliquez sur Options.</span><span class="sxs-lookup"><span data-stu-id="1add1-129">On the Action Pane, click Options.</span></span>
20. <span data-ttu-id="1add1-130">Cliquez sur Changer de vue.</span><span class="sxs-lookup"><span data-stu-id="1add1-130">Click Change view.</span></span>
21. <span data-ttu-id="1add1-131">Cliquez sur Affichage des lignes.</span><span class="sxs-lookup"><span data-stu-id="1add1-131">Click Line view.</span></span>
22. <span data-ttu-id="1add1-132">Dans le champ Article, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1add1-132">In the Item field, enter or select a value.</span></span>
23. <span data-ttu-id="1add1-133">Dans le champ Article, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1add1-133">In the Item field, type a value.</span></span>
24. <span data-ttu-id="1add1-134">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1add1-134">Close the page.</span></span>
25. <span data-ttu-id="1add1-135">Entrez un nombre dans le champ Pourcentage de remise.</span><span class="sxs-lookup"><span data-stu-id="1add1-135">In the Discount percent field, enter a number.</span></span>
26. <span data-ttu-id="1add1-136">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="1add1-136">Click Add line.</span></span>
27. <span data-ttu-id="1add1-137">Dans le champ Article, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1add1-137">In the Item field, enter or select a value.</span></span>
28. <span data-ttu-id="1add1-138">Dans le champ Article, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1add1-138">In the Item field, type a value.</span></span>
29. <span data-ttu-id="1add1-139">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1add1-139">Close the page.</span></span>
30. <span data-ttu-id="1add1-140">Dans le champ Prix unitaire, entrez un nouveau prix ou modifiez le prix actuel.</span><span class="sxs-lookup"><span data-stu-id="1add1-140">In the Unit price field, enter a new price or change the current one.</span></span>
31. <span data-ttu-id="1add1-141">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="1add1-141">Click Add line.</span></span>
32. <span data-ttu-id="1add1-142">Dans le champ Article, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1add1-142">In the Item field, enter or select a value.</span></span>
33. <span data-ttu-id="1add1-143">Dans le champ Article, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1add1-143">In the Item field, type a value.</span></span>
34. <span data-ttu-id="1add1-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1add1-144">Close the page.</span></span>
35. <span data-ttu-id="1add1-145">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="1add1-145">In the Quantity field, enter a number.</span></span>
36. <span data-ttu-id="1add1-146">Entrez un nombre dans le champ Remise.</span><span class="sxs-lookup"><span data-stu-id="1add1-146">In the Discount field, enter a number.</span></span>
37. <span data-ttu-id="1add1-147">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1add1-147">Click Save.</span></span>

## <a name="apply-the-template-to-create-a-single-quotation"></a><span data-ttu-id="1add1-148">Appliquer le modèle pour créer un devis unique</span><span class="sxs-lookup"><span data-stu-id="1add1-148">Apply the template to create a single quotation</span></span>
1. <span data-ttu-id="1add1-149">Accédez à Ventes et marketing > Devis de vente > Tous les devis.</span><span class="sxs-lookup"><span data-stu-id="1add1-149">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="1add1-150">Notez que le devis que vous venez de créer est marqué comme modèle.</span><span class="sxs-lookup"><span data-stu-id="1add1-150">Note that the quotation you have just created is marked as template.</span></span>  
2. <span data-ttu-id="1add1-151">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="1add1-151">Click New.</span></span>
3. <span data-ttu-id="1add1-152">Sélectionnez « Client » dans le champ Type de compte.</span><span class="sxs-lookup"><span data-stu-id="1add1-152">In the Account type field, select 'Customer'.</span></span>
4. <span data-ttu-id="1add1-153">Entrez ou sélectionnez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="1add1-153">In the Customer account field, enter or select a value.</span></span>
5. <span data-ttu-id="1add1-154">Développez la section Modèle.</span><span class="sxs-lookup"><span data-stu-id="1add1-154">Expand the Template section.</span></span>
6. <span data-ttu-id="1add1-155">Saisissez ou sélectionnez une valeur dans le champ ID groupe.</span><span class="sxs-lookup"><span data-stu-id="1add1-155">In the Group ID field, enter or select a value.</span></span>
7. <span data-ttu-id="1add1-156">Saisissez ou sélectionnez une valeur dans le champ Nom du modèle.</span><span class="sxs-lookup"><span data-stu-id="1add1-156">In the Template name field, enter or select a value.</span></span>
8. <span data-ttu-id="1add1-157">Dans le champ Mode de calcul, sélectionnez « En fonction des valeurs du modèle ».</span><span class="sxs-lookup"><span data-stu-id="1add1-157">In the Calculation method field, select 'Based on template values'.</span></span>
9. <span data-ttu-id="1add1-158">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1add1-158">Click OK.</span></span>
    * <span data-ttu-id="1add1-159">Le nouveau devis a maintenant été créé, en fonction des données et des conditions du modèle.</span><span class="sxs-lookup"><span data-stu-id="1add1-159">The new quotation has now been created, based on the data and terms of the template.</span></span>  
10. <span data-ttu-id="1add1-160">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1add1-160">Close the page.</span></span>
11. <span data-ttu-id="1add1-161">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1add1-161">Close the page.</span></span>

## <a name="apply-the-template-to-mass-create-quotations"></a><span data-ttu-id="1add1-162">Appliquer le modèle à la création en masse de devis</span><span class="sxs-lookup"><span data-stu-id="1add1-162">Apply the template to mass create quotations</span></span>
1. <span data-ttu-id="1add1-163">Accédez à Ventes et marketing > Devis de vente > Mise à jour du devis > Création en masse de devis.</span><span class="sxs-lookup"><span data-stu-id="1add1-163">Go to Sales and marketing > Sales quotations > Quotation update > Mass create quotations.</span></span>
2. <span data-ttu-id="1add1-164">Sélectionnez « Client » dans le champ Type de compte.</span><span class="sxs-lookup"><span data-stu-id="1add1-164">In the Account type field, select 'Customer'.</span></span>
3. <span data-ttu-id="1add1-165">Saisissez ou sélectionnez une valeur dans le champ ID groupe.</span><span class="sxs-lookup"><span data-stu-id="1add1-165">In the Group ID field, enter or select a value.</span></span>
4. <span data-ttu-id="1add1-166">Saisissez ou sélectionnez une valeur dans le champ Nom du modèle.</span><span class="sxs-lookup"><span data-stu-id="1add1-166">In the Template name field, enter or select a value.</span></span>
5. <span data-ttu-id="1add1-167">Dans le champ Mode de calcul, sélectionnez « En fonction des valeurs du modèle ».</span><span class="sxs-lookup"><span data-stu-id="1add1-167">In the Calculation method field, select 'Based on template values'.</span></span>
6. <span data-ttu-id="1add1-168">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="1add1-168">Expand the Records to include section.</span></span>
7. <span data-ttu-id="1add1-169">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="1add1-169">Click Filter.</span></span>
8. <span data-ttu-id="1add1-170">Dans le champ Critères définissez le filtre de sorte à couvrir une gamme de clients à inclure dans cette création en masse de devis.</span><span class="sxs-lookup"><span data-stu-id="1add1-170">In the Criteria field, set the filter to cover a range of customers you want to include in this mass quotation creation.</span></span> <span data-ttu-id="1add1-171">Utilisez le format suivant : "Client1..ClientN.</span><span class="sxs-lookup"><span data-stu-id="1add1-171">Use the following format "Customer1..CustomerN.</span></span>
    * <span data-ttu-id="1add1-172">Par exemple, vous pouvez définir le filtre sur : US-001...US-004</span><span class="sxs-lookup"><span data-stu-id="1add1-172">For example, you could set the filter to: US-001..US-004</span></span>  
9. <span data-ttu-id="1add1-173">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1add1-173">Click OK.</span></span>
10. <span data-ttu-id="1add1-174">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1add1-174">Click OK.</span></span>
11. <span data-ttu-id="1add1-175">Accédez à Ventes et marketing > Devis de vente > Tous les devis.</span><span class="sxs-lookup"><span data-stu-id="1add1-175">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="1add1-176">Vérifiez que des devis ont été créés pour tous les clients spécifiés dans la routine de mise à jour collective, comme l’indique le modèle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="1add1-176">Verify that quotations have been created for all the customers specified in the mass update routine, as based on the selected template.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]