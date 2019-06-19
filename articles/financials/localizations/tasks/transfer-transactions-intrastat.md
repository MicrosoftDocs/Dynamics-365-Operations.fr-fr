---
title: Transférer des transactions dans la déclaration d'échanges de biens
description: Cette procédure vous guide dans le paramétrage des paramètres de déclaration d'échanges de biens et le transfert des transactions dans la déclaration d'échanges de biens.
author: Anasyash
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategory, UnitOfMeasureLookup, ProcCategoryAddCommodityCode, EcoResProductDetailsExtended, IntrastatCommodityLookup, IntrastatTransactionCode, IntrastatParameters, DeliveryMode, MarkupTable, SalesTableListPage, SalesCreateOrder, SalesTable, MarkupTrans, SalesEditLines,  Intrastat, SysQueryForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13cc9dc2119ad3dc85d580e92edee7bb9ef2075c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559319"
---
# <a name="transfer-transactions-to-the-intrastat"></a><span data-ttu-id="ef494-103">Transférer des transactions dans la déclaration d'échanges de biens</span><span class="sxs-lookup"><span data-stu-id="ef494-103">Transfer transactions to the Intrastat</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ef494-104">Cette procédure vous guide dans le paramétrage des paramètres de déclaration d'échanges de biens et le transfert des transactions dans la déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="ef494-104">This procedure walks you through how to set up Intrastat parameters and transfer transactions to Intrastat.</span></span> <span data-ttu-id="ef494-105">Cette procédure a été créée à l'aide des données fictives de la société DEMF.</span><span class="sxs-lookup"><span data-stu-id="ef494-105">This procedure was created using the demo data company DEMF.</span></span>


## <a name="create-new-and-update-existing-commodity-code"></a><span data-ttu-id="ef494-106">Crée et mettre à jour un code marchandise existant</span><span class="sxs-lookup"><span data-stu-id="ef494-106">Create new and update existing commodity code</span></span>
1. <span data-ttu-id="ef494-107">Accédez à Gestion des informations sur les produits > Paramétrage > Catégories et d'attributs > Hiérarchies de catégories.</span><span class="sxs-lookup"><span data-stu-id="ef494-107">Go to Product information management > Setup > Categories and attributes > Category hierarchies.</span></span>
2. <span data-ttu-id="ef494-108">Dans la liste, recherchez ou sélectionnez l'enregistrement « Codes marchandise de la déclaration d'échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="ef494-108">In the list, find or select the record "Intrastat commodity codes."</span></span>
3. <span data-ttu-id="ef494-109">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ef494-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="ef494-110">Sélectionnez un enregistrement dans l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="ef494-110">In the tree, select 'a record'.</span></span>
    * <span data-ttu-id="ef494-111">Sélectionnez Déclaration d'échanges de biens\Haut-parleur, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-111">For example, select 'Intrastat\Speaker'.</span></span>  
5. <span data-ttu-id="ef494-112">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="ef494-112">Click Edit.</span></span>
6. <span data-ttu-id="ef494-113">Développez la section Commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="ef494-113">Expand the Foreign trade section.</span></span>
7. <span data-ttu-id="ef494-114">Saisissez ou sélectionnez une valeur dans le champ Unités additionnelles.</span><span class="sxs-lookup"><span data-stu-id="ef494-114">In the Additional units field, enter or select a value.</span></span>
    * <span data-ttu-id="ef494-115">Sélectionnez pcs, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-115">For example, choose 'pcs'.</span></span>  
8. <span data-ttu-id="ef494-116">Sélectionnez Oui dans le champ Poids non applicable.</span><span class="sxs-lookup"><span data-stu-id="ef494-116">Select Yes in the Weight not applicable field.</span></span>
9. <span data-ttu-id="ef494-117">Sélectionnez Déclaration d'échanges de biens dans l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="ef494-117">In the tree, select 'Intrastat'.</span></span>
10. <span data-ttu-id="ef494-118">Cliquez sur Nouveau nœud de catégorie.</span><span class="sxs-lookup"><span data-stu-id="ef494-118">Click New category node.</span></span>
11. <span data-ttu-id="ef494-119">Entrez le nom de la marchandise dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="ef494-119">In the Name field, enter the name of commodity.</span></span>
    * <span data-ttu-id="ef494-120">Entrez Autre marchandise, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-120">For example, type 'Other commodity'.</span></span>  
12. <span data-ttu-id="ef494-121">Entrer le code marchandise dans le champ Code.</span><span class="sxs-lookup"><span data-stu-id="ef494-121">In the Code field, enter the commodity code.</span></span>
    * <span data-ttu-id="ef494-122">Entrez 995 00 00, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-122">For example, type '995 00 00'.</span></span>  
13. <span data-ttu-id="ef494-123">Dans le champ Nom convivial, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ef494-123">In the Friendly name field, type a value.</span></span>
    * <span data-ttu-id="ef494-124">Entrez Autre, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-124">For example, type 'Other'.</span></span>  
14. <span data-ttu-id="ef494-125">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ef494-125">Click Save.</span></span>
15. <span data-ttu-id="ef494-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ef494-126">Close the page.</span></span>

## <a name="assign-commodity-code-to-product-hierarchy-and-released-product"></a><span data-ttu-id="ef494-127">Affecter un code marchandise à la hiérarchie des produits et au produit lancé</span><span class="sxs-lookup"><span data-stu-id="ef494-127">Assign commodity code to product hierarchy and released product</span></span>
1. <span data-ttu-id="ef494-128">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="ef494-128">Use the Quick Filter to find records.</span></span> <span data-ttu-id="ef494-129">Par exemple, filtrez sur le champ Nom avec une valeur de « ventes ».</span><span class="sxs-lookup"><span data-stu-id="ef494-129">For example, filter on the Name field with a value of 'sales'.</span></span>
2. <span data-ttu-id="ef494-130">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ef494-130">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="ef494-131">Dans l'arborescence, développez un nœud de catégorie.</span><span class="sxs-lookup"><span data-stu-id="ef494-131">In the tree, expand 'a category node'.</span></span>
    * <span data-ttu-id="ef494-132">Développez Hiérarchie de vente\Audio d'accueil, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-132">For example, expand 'Sales hierarchy\Home audio'.</span></span>  
4. <span data-ttu-id="ef494-133">Dans l'arborescence, sélectionnez la catégorie à affecter au code marchandise.</span><span class="sxs-lookup"><span data-stu-id="ef494-133">In the tree, select 'the category to assign to the commodity code'.</span></span>
    * <span data-ttu-id="ef494-134">Sélectionnez Hiérarchie de vente\Audio d'accueil\Haut-parleurs, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-134">For example, select 'Sales hierarchy\Home audio\Speakers.</span></span>  
5. <span data-ttu-id="ef494-135">Développez la section Codes marchandise.</span><span class="sxs-lookup"><span data-stu-id="ef494-135">Expand the Commodity codes section.</span></span>
6. <span data-ttu-id="ef494-136">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="ef494-136">Click Add.</span></span>
7. <span data-ttu-id="ef494-137">Sélectionnez Déclaration d'échanges de biens dans le champ Sélectionner une hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="ef494-137">In the Select hierarchy field, select 'Intrastat'.</span></span>
8. <span data-ttu-id="ef494-138">Dans la liste, recherchez et sélectionnez le code marchandise.</span><span class="sxs-lookup"><span data-stu-id="ef494-138">In the list, find and select the commodity code</span></span>
    * <span data-ttu-id="ef494-139">Sélectionnez Haut-parleur 920 20 34, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-139">For example, select '920 20 34 Speaker'.</span></span>  
9. <span data-ttu-id="ef494-140">Cliquez sur SelectCodes.</span><span class="sxs-lookup"><span data-stu-id="ef494-140">Click SelectCodes.</span></span>
10. <span data-ttu-id="ef494-141">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ef494-141">Click OK.</span></span>
11. <span data-ttu-id="ef494-142">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="ef494-142">Go to Product information management > Products > Released products.</span></span>
12. <span data-ttu-id="ef494-143">Dans la liste, choisissez le produit lancé à affecter au code marchandise.</span><span class="sxs-lookup"><span data-stu-id="ef494-143">In the list, choose the released product that you will assign to the commodity code.</span></span>
    * <span data-ttu-id="ef494-144">Sélectionnez D0001, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-144">For example, choose 'D0001'.</span></span>  
13. <span data-ttu-id="ef494-145">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="ef494-145">Click Edit.</span></span>
14. <span data-ttu-id="ef494-146">Développez la section Commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="ef494-146">Expand the Foreign trade section.</span></span>
15. <span data-ttu-id="ef494-147">Entrez le code marchandise dans le champ Marchandise.</span><span class="sxs-lookup"><span data-stu-id="ef494-147">In the Commodity field, enter the commodity code</span></span>
    * <span data-ttu-id="ef494-148">Sélectionnez la valeur Haut-parleur 920 20 34, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-148">For example, select value '920 20 34 Speaker'.</span></span>    
16. <span data-ttu-id="ef494-149">Entrez un nombre dans le champ Pourcentage de frais.</span><span class="sxs-lookup"><span data-stu-id="ef494-149">In the Charges percentage field, enter a number.</span></span>
    * <span data-ttu-id="ef494-150">Entrez 3, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-150">For example, enter '3'.</span></span>  
17. <span data-ttu-id="ef494-151">Dans le champ Pays/Région, entrez ou sélectionnez un pays ou une région d'origine.</span><span class="sxs-lookup"><span data-stu-id="ef494-151">In the Country/region field, enter or select a country or region of origin</span></span>
    * <span data-ttu-id="ef494-152">Sélectionnez AUT, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-152">For example, select 'AUT'.</span></span>  
18. <span data-ttu-id="ef494-153">Développez la section Gérer le stock.</span><span class="sxs-lookup"><span data-stu-id="ef494-153">Expand the Manage inventory section.</span></span>
19. <span data-ttu-id="ef494-154">Entrez un poids en kg dans le champ Poids net.</span><span class="sxs-lookup"><span data-stu-id="ef494-154">In the Net weight field, enter a weight in kg.</span></span>
    * <span data-ttu-id="ef494-155">Entrez 2,5 par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-155">For example, enter '2.5'.</span></span>  
20. <span data-ttu-id="ef494-156">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ef494-156">Click Save.</span></span>

## <a name="set-up-intrastat-transaction-codes-and-foreign-trade-parameters"></a><span data-ttu-id="ef494-157">Paramétrer des codes de transaction de déclaration d'échanges de biens et des paramètres de commerce extérieur</span><span class="sxs-lookup"><span data-stu-id="ef494-157">Set up Intrastat transaction codes and foreign trade parameters</span></span>
1. <span data-ttu-id="ef494-158">Accédez à Taxes > Paramétrage > Commerce extérieur > Codes transaction.</span><span class="sxs-lookup"><span data-stu-id="ef494-158">Go to Tax > Setup > Foreign trade > Transaction codes</span></span>
2. <span data-ttu-id="ef494-159">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="ef494-159">Click New.</span></span>
3. <span data-ttu-id="ef494-160">Tapez une valeur dans le champ Code transaction.</span><span class="sxs-lookup"><span data-stu-id="ef494-160">In the Transaction code field, type a value.</span></span>
    * <span data-ttu-id="ef494-161">Entrez 21, par exemple pour le code de transaction utilisé comme retour.</span><span class="sxs-lookup"><span data-stu-id="ef494-161">For example, enter '21' for the transaction code used as return.</span></span>  
4. <span data-ttu-id="ef494-162">Tapez le nom du code de transaction dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="ef494-162">In the Name field, type the name of transaction code.</span></span>
    * <span data-ttu-id="ef494-163">Entrez Retour, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-163">For example, enter 'Return'.</span></span>  
5. <span data-ttu-id="ef494-164">Sélectionnez une option dans le champ Montant statistique.</span><span class="sxs-lookup"><span data-stu-id="ef494-164">In the Statistical amount field, select an option.</span></span>
    * <span data-ttu-id="ef494-165">Sélectionnez Vide, par exemple, ce qui indique que la valeur statistique à déclarer pour les transactions avec le code transaction 21 est toujours zéro.</span><span class="sxs-lookup"><span data-stu-id="ef494-165">For example, select 'Empty' which indicates that the Statistical value to be reported for transactions with Transaction code of "21" will always be zero.</span></span>  
6. <span data-ttu-id="ef494-166">Accédez à Taxe > Paramétrage > Commerce extérieur > Paramètres de commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="ef494-166">Go to Tax > Setup > Foreign trade > Foreign trade parameters</span></span>
7. <span data-ttu-id="ef494-167">Saisissez ou sélectionnez une valeur dans le champ Code transaction.</span><span class="sxs-lookup"><span data-stu-id="ef494-167">In the Transaction code field, enter or select a value.</span></span>
    * <span data-ttu-id="ef494-168">Sélectionnez 11, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-168">For example, select '11'.</span></span>  
8. <span data-ttu-id="ef494-169">Entrez ou sélectionnez une valeur dans le champ Avoir.</span><span class="sxs-lookup"><span data-stu-id="ef494-169">In the Credit note field, enter or select a value.</span></span>
    * <span data-ttu-id="ef494-170">Cette valeur identifie également le retour physique.</span><span class="sxs-lookup"><span data-stu-id="ef494-170">This value also identifies the physical return.</span></span> <span data-ttu-id="ef494-171">L'avoir pour le retour physique est transféré dans le journal de déclaration d'échanges de biens dans le sens opposé.</span><span class="sxs-lookup"><span data-stu-id="ef494-171">The credit note for the physical return will be transferred in the Intrastat journal with opposite direction.</span></span> <span data-ttu-id="ef494-172">Par exemple, le retour de l'arrivée est transféré en tant qu'expédition.</span><span class="sxs-lookup"><span data-stu-id="ef494-172">For example, the return of arrival is transferred as dispatch.</span></span>   <span data-ttu-id="ef494-173">Sinon, l'avoir est considéré comme une correction et il est transféré avec le même sens et le signe contraire.</span><span class="sxs-lookup"><span data-stu-id="ef494-173">Otherwise, the credit note is considered a correction and is transferred with the same direction and opposite sign.</span></span> <span data-ttu-id="ef494-174">Par exemple, la correction de l'arrivée est transférée sous la forme d'une arrivée avec un montant négatif et la balise active est définie sur « Correction ».</span><span class="sxs-lookup"><span data-stu-id="ef494-174">For example, the correction of arrival is transferred as an arrival with negative amount and the active flag is set to "Correction".</span></span>  
9. <span data-ttu-id="ef494-175">Développez la section Transfert.</span><span class="sxs-lookup"><span data-stu-id="ef494-175">Expand the Transfer section.</span></span>
10. <span data-ttu-id="ef494-176">Sélectionnez Oui dans le champ Articles avec code marchandise.</span><span class="sxs-lookup"><span data-stu-id="ef494-176">Select Yes in the Items with commodity code field.</span></span>
    * <span data-ttu-id="ef494-177">Sélectionnez cette option pour transférer uniquement les transactions ayant un code marchandise affecté.</span><span class="sxs-lookup"><span data-stu-id="ef494-177">Select this option to transfer only the transactions with a commodity code assigned.</span></span> <span data-ttu-id="ef494-178">Les transactions sans code marchandise ne sont pas transférées à la déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="ef494-178">Transactions without a commodity code won't be transferred to Intrastat.</span></span>  
11. <span data-ttu-id="ef494-179">Sélectionnez une option dans le champ Transférer en cas de réalisation du critère.</span><span class="sxs-lookup"><span data-stu-id="ef494-179">In the Transfer when meeting criterion for field, select an option.</span></span>
    * <span data-ttu-id="ef494-180">Sélectionnez « Un des critères », par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-180">For example, select 'One of the selected'.</span></span>  
12. <span data-ttu-id="ef494-181">Développez la section Hiérarchie des nomenclatures douanières.</span><span class="sxs-lookup"><span data-stu-id="ef494-181">Expand the Commodity code hierarchy section.</span></span>
13. <span data-ttu-id="ef494-182">Cliquez sur l'onglet Propriétés de pays/régions.</span><span class="sxs-lookup"><span data-stu-id="ef494-182">Click the Country/region properties tab.</span></span>
14. <span data-ttu-id="ef494-183">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="ef494-183">Click New.</span></span>
15. <span data-ttu-id="ef494-184">Dans le champ Pays/Région, sélectionnez ou entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ef494-184">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="ef494-185">Sélectionnez la valeur FRA, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-185">For example, select the value 'FRA'.</span></span>  
16. <span data-ttu-id="ef494-186">Entrez le code pays ISO pour le pays dans le champ Code de déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="ef494-186">In the Intrastat code field, enter the ISO code for the country.</span></span>
    * <span data-ttu-id="ef494-187">Entrez FR, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-187">For example, type 'FR'.</span></span>  
17. <span data-ttu-id="ef494-188">Dans le champ Type de pays/région, sélectionnez UE.</span><span class="sxs-lookup"><span data-stu-id="ef494-188">In the Country/region type field, select 'EU'.</span></span>
18. <span data-ttu-id="ef494-189">Cliquez sur l'onglet Souches de numéros.</span><span class="sxs-lookup"><span data-stu-id="ef494-189">Click the Number sequences tab.</span></span>

## <a name="set-up-modes-of-delivery-and-rules-for-including-charges-in-intrastat"></a><span data-ttu-id="ef494-190">Paramétrer des modes de livraison et des règles pour inclure les frais de déclaration d'échanges de biens</span><span class="sxs-lookup"><span data-stu-id="ef494-190">Set up Modes of delivery and rules for including charges in Intrastat</span></span>
1. <span data-ttu-id="ef494-191">Accédez à Ventes et marketing > Paramétrage > Distribution > Modes de livraison.</span><span class="sxs-lookup"><span data-stu-id="ef494-191">Go to Sales and marketing > Setup > Distribution > Modes of delivery</span></span>
2. <span data-ttu-id="ef494-192">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="ef494-192">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ef494-193">Sélectionnez 20 Air, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-193">For example, select '20 Air'.</span></span>  
3. <span data-ttu-id="ef494-194">Développez la section Commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="ef494-194">Expand the Foreign trade section.</span></span>
4. <span data-ttu-id="ef494-195">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="ef494-195">Click Edit.</span></span>
5. <span data-ttu-id="ef494-196">Saisissez ou sélectionnez une valeur dans le champ Transport.</span><span class="sxs-lookup"><span data-stu-id="ef494-196">In the Transport field, enter or select a value.</span></span>
    * <span data-ttu-id="ef494-197">Sélectionnez 02, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-197">For example, select '02'.</span></span>  
6. <span data-ttu-id="ef494-198">Accédez à Comptabilité client > Paramétrage des frais > Code frais.</span><span class="sxs-lookup"><span data-stu-id="ef494-198">Go to Accounts receivable > Charges setup > Charges code.</span></span>
7. <span data-ttu-id="ef494-199">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="ef494-199">Use the Quick Filter to find records.</span></span> <span data-ttu-id="ef494-200">Par exemple, filtrez sur le champ Code frais avec une valeur de « transport ».</span><span class="sxs-lookup"><span data-stu-id="ef494-200">For example, filter on the Charges code field with a value of 'freight'.</span></span>
8. <span data-ttu-id="ef494-201">Développez la section Commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="ef494-201">Expand the Foreign trade section.</span></span>
9. <span data-ttu-id="ef494-202">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="ef494-202">Click Edit.</span></span>
10. <span data-ttu-id="ef494-203">Sélectionnez Oui dans le champ Valeur de la facture de la déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="ef494-203">Select Yes in the Intrastat invoice value field.</span></span>
    * <span data-ttu-id="ef494-204">Le montant est transféré dans le champ Frais de la facture et il est résumé avec le montant transféré dans le champ Montant de la facture.</span><span class="sxs-lookup"><span data-stu-id="ef494-204">The amount will be transferred to the  Invoice charges field and will be summarized with the amount transferred in the Invoice amount field.</span></span>    <span data-ttu-id="ef494-205">Sélectionnez Oui dans le champ Valeur statistique de la déclaration d'échanges de biens si la quantité de modifications doit être transférée vers le champ des frais statistiques et être récapitulée avec le montant statistique.</span><span class="sxs-lookup"><span data-stu-id="ef494-205">Select Yes in the Intrastat statistical value field if the amount of changes need to be transferred to the field Statistical charges and summarized with Statistical amount.</span></span>  

## <a name="sell-products-for-eu-customers"></a><span data-ttu-id="ef494-206">Vendre des produits pour les clients de l'UE</span><span class="sxs-lookup"><span data-stu-id="ef494-206">Sell products for EU customers</span></span>
1. <span data-ttu-id="ef494-207">Accédez à Comptabilité client > Commandes > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="ef494-207">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="ef494-208">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="ef494-208">Click New.</span></span>
3. <span data-ttu-id="ef494-209">Sélectionnez un client de l'UE dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="ef494-209">In the Customer account field, select an EU customer</span></span>
    * <span data-ttu-id="ef494-210">Sélectionnez DE-012 Litware Retail, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-210">For example, select "DE-012 Litware Retail".</span></span>  
4. <span data-ttu-id="ef494-211">Développez la section Livraison.</span><span class="sxs-lookup"><span data-stu-id="ef494-211">Expand the Delivery section.</span></span>
5. <span data-ttu-id="ef494-212">Saisissez ou sélectionnez une valeur dans le champ Mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="ef494-212">In the Mode of delivery field, enter or select a value.</span></span>
    * <span data-ttu-id="ef494-213">Sélectionnez 20 Air, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-213">For example, select '20 Air'.</span></span>  
6. <span data-ttu-id="ef494-214">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ef494-214">Click OK.</span></span>
7. <span data-ttu-id="ef494-215">Placez le curseur sur la première ligne des lignes de commande client.</span><span class="sxs-lookup"><span data-stu-id="ef494-215">Place the cursor on the first row of sales order lines.</span></span>
8. <span data-ttu-id="ef494-216">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="ef494-216">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="ef494-217">Sélectionnez D001, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-217">For example, select 'D001'.</span></span>  
9. <span data-ttu-id="ef494-218">Développez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="ef494-218">Expand the Line details section.</span></span>
10. <span data-ttu-id="ef494-219">Cliquez sur l'onglet Commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="ef494-219">Click the Foreign trade tab.</span></span>
    * <span data-ttu-id="ef494-220">Le transport est renseigné automatiquement à partir du mode de livraison sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ef494-220">The transport is filled automatically from the chosen Mode of delivery.</span></span>  
11. <span data-ttu-id="ef494-221">Saisissez ou sélectionnez une valeur dans le champ Port.</span><span class="sxs-lookup"><span data-stu-id="ef494-221">In the Port field, enter or select a value.</span></span>
12. <span data-ttu-id="ef494-222">Cliquez sur Finances.</span><span class="sxs-lookup"><span data-stu-id="ef494-222">Click Financials.</span></span>
    * <span data-ttu-id="ef494-223">Conformément aux paramètres, ce montant sera inclus dans la valeur de la facture de la déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="ef494-223">As per the settings, this amount will be included in Intrastat invoice value.</span></span>  
13. <span data-ttu-id="ef494-224">Cliquez sur Tenir les frais à jour.</span><span class="sxs-lookup"><span data-stu-id="ef494-224">Click Maintain charges.</span></span>
14. <span data-ttu-id="ef494-225">Saisissez ou sélectionnez une valeur dans le champ Code frais.</span><span class="sxs-lookup"><span data-stu-id="ef494-225">In the Charges code field, enter or select a value.</span></span>
    * <span data-ttu-id="ef494-226">Sélectionnez FREIGHT, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-226">For example, select 'FREIGHT'.</span></span>  
15. <span data-ttu-id="ef494-227">Activez la case à cocher Conserver.</span><span class="sxs-lookup"><span data-stu-id="ef494-227">Select the Keep check box.</span></span>
16. <span data-ttu-id="ef494-228">Entrez un nombre dans le champ Valeur des frais.</span><span class="sxs-lookup"><span data-stu-id="ef494-228">In the Charges value field, enter a number.</span></span>
    * <span data-ttu-id="ef494-229">Entrez 10, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-229">For example, enter '10'.</span></span>  
17. <span data-ttu-id="ef494-230">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ef494-230">Click Save.</span></span>
18. <span data-ttu-id="ef494-231">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ef494-231">Close the page.</span></span>
19. <span data-ttu-id="ef494-232">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="ef494-232">On the Action Pane, click Invoice.</span></span>
20. <span data-ttu-id="ef494-233">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="ef494-233">Click Invoice.</span></span>
21. <span data-ttu-id="ef494-234">Développez la section Paramètres.</span><span class="sxs-lookup"><span data-stu-id="ef494-234">Expand the Parameters section.</span></span>
22. <span data-ttu-id="ef494-235">Sélectionnez « Tout » dans le champ Quantité.</span><span class="sxs-lookup"><span data-stu-id="ef494-235">In the Quantity field, select 'All'.</span></span>
23. <span data-ttu-id="ef494-236">Développez la section Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="ef494-236">Expand the Setup section.</span></span>
24. <span data-ttu-id="ef494-237">Entrez une date dans le champ Date de facture.</span><span class="sxs-lookup"><span data-stu-id="ef494-237">In the Invoice date field, enter a date.</span></span>
    * <span data-ttu-id="ef494-238">Entrez 31-01-2015, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-238">For example, enter '2015-01-31'.</span></span>  
25. <span data-ttu-id="ef494-239">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ef494-239">Click OK.</span></span>
26. <span data-ttu-id="ef494-240">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ef494-240">Click OK.</span></span>
27. <span data-ttu-id="ef494-241">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ef494-241">Close the page.</span></span>
28. <span data-ttu-id="ef494-242">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="ef494-242">Click New.</span></span>
29. <span data-ttu-id="ef494-243">Sélectionnez un client de l'UE dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="ef494-243">In the Customer account field, select an EU customer.</span></span>
    * <span data-ttu-id="ef494-244">Sélectionnez DE-013 Trey Wholesales, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-244">For example, select 'DE-013 Trey Wholesales'</span></span>  
30. <span data-ttu-id="ef494-245">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ef494-245">Click OK.</span></span>
31. <span data-ttu-id="ef494-246">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="ef494-246">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="ef494-247">Sélectionnez D0001, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-247">For example, select 'D0001'.</span></span>  
32. <span data-ttu-id="ef494-248">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ef494-248">Click Save.</span></span>
33. <span data-ttu-id="ef494-249">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="ef494-249">Click Invoice.</span></span>
34. <span data-ttu-id="ef494-250">Entrez une date dans le champ Date de facture.</span><span class="sxs-lookup"><span data-stu-id="ef494-250">In the Invoice date field, enter a date.</span></span>
    * <span data-ttu-id="ef494-251">Entrez la date 31-01-2015, par exemple.</span><span class="sxs-lookup"><span data-stu-id="ef494-251">For example, enter the date '2015-01-31'.</span></span>  
35. <span data-ttu-id="ef494-252">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ef494-252">Click OK.</span></span>
36. <span data-ttu-id="ef494-253">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ef494-253">Click OK.</span></span>

## <a name="transfer-transactions-to-the-intrastat"></a><span data-ttu-id="ef494-254">Transférer des transactions dans la déclaration d'échanges de biens</span><span class="sxs-lookup"><span data-stu-id="ef494-254">Transfer transactions to the Intrastat</span></span>
1. <span data-ttu-id="ef494-255">Accédez à Taxe > Déclarations > Commerce extérieur > Déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="ef494-255">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
2. <span data-ttu-id="ef494-256">Cliquez sur Transférer.</span><span class="sxs-lookup"><span data-stu-id="ef494-256">Click Transfer.</span></span>
3. <span data-ttu-id="ef494-257">Sélectionnez Oui dans le champ Facture client.</span><span class="sxs-lookup"><span data-stu-id="ef494-257">Select Yes in the Customer invoice field.</span></span>
4. <span data-ttu-id="ef494-258">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="ef494-258">Click Filter.</span></span>
5. <span data-ttu-id="ef494-259">Dans la liste, marquer la ligne avec la date.</span><span class="sxs-lookup"><span data-stu-id="ef494-259">In the list, mark the row with Date</span></span>
6. <span data-ttu-id="ef494-260">Tapez une valeur dans le champ Critères.</span><span class="sxs-lookup"><span data-stu-id="ef494-260">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="ef494-261">Par exemple, entrez le filtre pour janvier 2015 (la valeur exacte dépend du format de date) : 1/1/2015..31/1/2015</span><span class="sxs-lookup"><span data-stu-id="ef494-261">For example, enter the filter for the period January 2015 (the exact value depends on your date format): 1/1/2015..1/31/2015</span></span>  
7. <span data-ttu-id="ef494-262">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ef494-262">Click OK.</span></span>
8. <span data-ttu-id="ef494-263">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ef494-263">Click OK.</span></span>
9. <span data-ttu-id="ef494-264">Dans la liste, recherchez et sélectionnez l'enregistrement transféré.</span><span class="sxs-lookup"><span data-stu-id="ef494-264">In the list, find and selected the transferred record.</span></span>
10. <span data-ttu-id="ef494-265">Cliquez sur l'onglet Général.</span><span class="sxs-lookup"><span data-stu-id="ef494-265">Click the General tab.</span></span>
    * <span data-ttu-id="ef494-266">Examinez les données transférées, notamment pays\la région de destination/d'expédition, pays d'origine, poids, quantité, quantité en unités supplémentaires, marchandise, code de transaction, montants facturés et montants statistiques.</span><span class="sxs-lookup"><span data-stu-id="ef494-266">Review transferred data, including country\region of destination/dispatch, country of origin, weight, quantity, quantity in additional units, commodity, transaction code, invoice amounts and statistical amounts.</span></span>   <span data-ttu-id="ef494-267">Vous pouvez modifier les données, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="ef494-267">You can modify data if necessary.</span></span>  

