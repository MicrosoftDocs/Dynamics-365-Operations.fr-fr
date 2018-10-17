--- 
title: "EUR-00011 Paramétrer une déclaration de la liste des ventes intracommunautaires"
description: "Cette tâche vous accompagne dans une présentation des conditions préalables requises à la génération d'états de la liste des ventes intracommunautaires."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, SysQueryForm, SysQueryFieldLookUp,  TaxTable, TaxGroup, TaxItemGroup, TaxCountryRegionParameters, TaxVATNumTable, IntrastatParameters, CustTable, DirPartyQuickCreateForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: aef1d19aabb7937fcd961a9657b8ca65c064b0b1
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="eur-00011-set-up-eu-sales-list-reporting"></a><span data-ttu-id="d2b42-103">EUR-00011 Paramétrer une déclaration de la liste des ventes intracommunautaires</span><span class="sxs-lookup"><span data-stu-id="d2b42-103">EUR-00011 Set up EU sales list reporting</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d2b42-104">Cette tâche vous accompagne dans une présentation des conditions préalables requises à la génération d'états de la liste des ventes intracommunautaires.</span><span class="sxs-lookup"><span data-stu-id="d2b42-104">This task walks you through an overview of the prerequisites required for EU sales list reporting.</span></span> <span data-ttu-id="d2b42-105">Pour plus d'informations sur la déclaration de la liste des ventes intracommunautaires, notamment les conditions préalables requises, reportez-vous à l'aide de Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d2b42-105">For more information about EU Sales list reporting, including required prerequisites, refer to the Dynamics 365 for Finance and Operations Help.</span></span>

<span data-ttu-id="d2b42-106">Cette tâche s'applique à tous les pays/régions européens.</span><span class="sxs-lookup"><span data-stu-id="d2b42-106">This task applies to all European countries/regions.</span></span> <span data-ttu-id="d2b42-107">Le guide a été créé avec la société fictive DEMF ; par conséquent, l'Allemagne est pris comme exemple de pays/région local.</span><span class="sxs-lookup"><span data-stu-id="d2b42-107">The guide was created using the demo data company DEMF and consequently Germany as an exemplar domestic country/region.</span></span> <span data-ttu-id="d2b42-108">Le guide utilise également le Portugal comme pays/région européen d'exemple.</span><span class="sxs-lookup"><span data-stu-id="d2b42-108">The guide also uses Portugal as an exemplar EU country/region.</span></span>

<span data-ttu-id="d2b42-109">Ces tâches sont destinées aux administrateurs système.</span><span class="sxs-lookup"><span data-stu-id="d2b42-109">These tasks are intended for system administrators.</span></span>


## <a name="import-electronic-reporting-configurations-for-eu-sales-list-reporting"></a><span data-ttu-id="d2b42-110">Importer les configurations de génération d'états électroniques pour la déclaration de la liste des ventes intracommunautaires</span><span class="sxs-lookup"><span data-stu-id="d2b42-110">Import electronic reporting configurations for EU sales list reporting</span></span>
1. <span data-ttu-id="d2b42-111">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="d2b42-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="d2b42-112">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="d2b42-112">Click Set active.</span></span>
3. <span data-ttu-id="d2b42-113">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="d2b42-113">Click Repositories.</span></span>
4. <span data-ttu-id="d2b42-114">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="d2b42-114">Click Open.</span></span>
5. <span data-ttu-id="d2b42-115">Dans le volet Actions, cliquez sur Options.</span><span class="sxs-lookup"><span data-stu-id="d2b42-115">On the Action Pane, click Options.</span></span>
6. <span data-ttu-id="d2b42-116">Cliquez sur Filtre/tri avancé.</span><span class="sxs-lookup"><span data-stu-id="d2b42-116">Click Advanced Filter/Sort.</span></span>
7. <span data-ttu-id="d2b42-117">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d2b42-117">Click Add.</span></span>
8. <span data-ttu-id="d2b42-118">Dans le champ Champ, sélectionnez Nom de la configuration.</span><span class="sxs-lookup"><span data-stu-id="d2b42-118">In the Field field, select 'Configuration name'.</span></span>
9. <span data-ttu-id="d2b42-119">Dans le champ Critère, entrez « Liste des ventes intracommunautaires (DE) ».</span><span class="sxs-lookup"><span data-stu-id="d2b42-119">In the Criteria field, type 'EU Sales list (DE)'.</span></span>
10. <span data-ttu-id="d2b42-120">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d2b42-120">Click OK.</span></span>
11. <span data-ttu-id="d2b42-121">Cliquez sur Importer.</span><span class="sxs-lookup"><span data-stu-id="d2b42-121">Click Import.</span></span>
12. <span data-ttu-id="d2b42-122">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="d2b42-122">Click Yes.</span></span>
13. <span data-ttu-id="d2b42-123">Dans le volet Actions, cliquez sur Options.</span><span class="sxs-lookup"><span data-stu-id="d2b42-123">On the Action Pane, click Options.</span></span>
14. <span data-ttu-id="d2b42-124">Cliquez sur Filtre/tri avancé.</span><span class="sxs-lookup"><span data-stu-id="d2b42-124">Click Advanced Filter/Sort.</span></span>
15. <span data-ttu-id="d2b42-125">Cliquez sur Réinitialiser.</span><span class="sxs-lookup"><span data-stu-id="d2b42-125">Click Reset.</span></span>
16. <span data-ttu-id="d2b42-126">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d2b42-126">Click Add.</span></span>
17. <span data-ttu-id="d2b42-127">Dans le champ Champ, sélectionnez Nom de la configuration.</span><span class="sxs-lookup"><span data-stu-id="d2b42-127">In the Field field, select 'Configuration name'.</span></span>
18. <span data-ttu-id="d2b42-128">Dans le champ Critère, entrez « État de la liste des ventes intracommunautaires par lignes ».</span><span class="sxs-lookup"><span data-stu-id="d2b42-128">In the Criteria field, type 'EU Sales list by rows report'.</span></span>
19. <span data-ttu-id="d2b42-129">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d2b42-129">Click OK.</span></span>
20. <span data-ttu-id="d2b42-130">Cliquez sur Importer.</span><span class="sxs-lookup"><span data-stu-id="d2b42-130">Click Import.</span></span>
21. <span data-ttu-id="d2b42-131">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="d2b42-131">Click Yes.</span></span>

## <a name="set-up-sales-tax-codes-for-eu-sales-list-reporting"></a><span data-ttu-id="d2b42-132">Paramétrer les codes taxe pour la déclaration de la liste des ventes intracommunautaires</span><span class="sxs-lookup"><span data-stu-id="d2b42-132">Set up sales tax codes for EU sales list reporting</span></span>
1. <span data-ttu-id="d2b42-133">Accédez à Taxes > Taxes indirectes > Taxe > Codes taxe.</span><span class="sxs-lookup"><span data-stu-id="d2b42-133">Go to Tax > Indirect taxes > Sales tax > Sales tax codes.</span></span>
2. <span data-ttu-id="d2b42-134">Utiliser le filtre rapide pour filtrer le champ Taxe avec une valeur de « TVA19 ».</span><span class="sxs-lookup"><span data-stu-id="d2b42-134">Use the Quick Filter to filter on the Sales tax code field with a value of 'VAT19'.</span></span>
3. <span data-ttu-id="d2b42-135">Développez la section Paramétrage de l'état.</span><span class="sxs-lookup"><span data-stu-id="d2b42-135">Expand the Report setup section.</span></span>
    * <span data-ttu-id="d2b42-136">Vérifiez que la sélection Exclue est définie sur Non.</span><span class="sxs-lookup"><span data-stu-id="d2b42-136">Verify that the Excluded selection is set to No.</span></span>  
    * <span data-ttu-id="d2b42-137">Vous devez peut-être déverrouiller le guide pour modifier ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="d2b42-137">You may need to unlock the task guide to change this setting.</span></span>  

## <a name="set-up-sales-tax-groups-for-eu-sales-list-reporting"></a><span data-ttu-id="d2b42-138">Paramétrer les groupes de taxe pour la déclaration de la liste des ventes intracommunautaires</span><span class="sxs-lookup"><span data-stu-id="d2b42-138">Set up sales tax groups for EU sales list reporting</span></span>
1. <span data-ttu-id="d2b42-139">Accédez à Taxe > Taxes indirectes > Taxe > Groupes de taxe.</span><span class="sxs-lookup"><span data-stu-id="d2b42-139">Go to Tax > Indirect taxes > Sales tax > Sales tax groups.</span></span>
2. <span data-ttu-id="d2b42-140">Utiliser le filtre rapide pour filtrer le champ Groupe de taxes avec une valeur « AR-DOM ».</span><span class="sxs-lookup"><span data-stu-id="d2b42-140">Use the Quick Filter to filter on the Sales tax group field with a value of 'AR-DOM'.</span></span>
3. <span data-ttu-id="d2b42-141">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="d2b42-141">Click Edit.</span></span>
4. <span data-ttu-id="d2b42-142">Développez la section Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="d2b42-142">Expand the Setup section.</span></span>
5. <span data-ttu-id="d2b42-143">Dans la liste, sélectionnez la première ligne.</span><span class="sxs-lookup"><span data-stu-id="d2b42-143">In the list, select the first row.</span></span>
6. <span data-ttu-id="d2b42-144">Activer cette case à cocher Exonéré.</span><span class="sxs-lookup"><span data-stu-id="d2b42-144">Select the Exempt check box.</span></span>
7. <span data-ttu-id="d2b42-145">Dans la liste, sélectionnez la deuxième ligne.</span><span class="sxs-lookup"><span data-stu-id="d2b42-145">In the list, select the second row.</span></span>
8. <span data-ttu-id="d2b42-146">Activer cette case à cocher Exonéré.</span><span class="sxs-lookup"><span data-stu-id="d2b42-146">Select the Exempt check box.</span></span>
9. <span data-ttu-id="d2b42-147">Dans la liste, sélectionnez la troisième ligne.</span><span class="sxs-lookup"><span data-stu-id="d2b42-147">In the list, select the third row.</span></span>
10. <span data-ttu-id="d2b42-148">Activer cette case à cocher Exonéré.</span><span class="sxs-lookup"><span data-stu-id="d2b42-148">Select the Exempt check box.</span></span>

## <a name="set-up-item-sales-tax-groups-for-eu-sales-list-reporting"></a><span data-ttu-id="d2b42-149">Paramétrer les groupes de taxe d'article pour la déclaration de la liste des ventes intracommunautaires</span><span class="sxs-lookup"><span data-stu-id="d2b42-149">Set up item sales tax groups for EU sales list reporting</span></span>
1. <span data-ttu-id="d2b42-150">Accédez à Taxe > Taxes indirectes > Taxe > Groupes de taxe d'article.</span><span class="sxs-lookup"><span data-stu-id="d2b42-150">Go to Tax > Indirect taxes > Sales tax > Item sales tax groups.</span></span>
2. <span data-ttu-id="d2b42-151">Utilisez le filtre rapide pour filtrer le champ Groupe de taxe d'article avec une valeur « FULL ».</span><span class="sxs-lookup"><span data-stu-id="d2b42-151">Use the Quick Filter to filter on the Item sales tax group field with a value of 'FULL '.</span></span>
    * <span data-ttu-id="d2b42-152">Vérifiez que la sélection du Type de génération d'états est définie sur Article.</span><span class="sxs-lookup"><span data-stu-id="d2b42-152">Verify that the Reporting type selection is set to 'Item'.</span></span>  
    * <span data-ttu-id="d2b42-153">Vous devez peut-être déverrouiller le guide pour modifier la valeur de ce champ.</span><span class="sxs-lookup"><span data-stu-id="d2b42-153">You may need to unlock the task guide to change the value in this field.</span></span>  
3. <span data-ttu-id="d2b42-154">Utilisez le filtre rapide pour filtrer le champ Groupe de taxe d'article avec une valeur « RED ».</span><span class="sxs-lookup"><span data-stu-id="d2b42-154">Use the Quick Filter to filter on the Item sales tax group field with a value of 'RED '.</span></span>
    * <span data-ttu-id="d2b42-155">Vérifiez que la sélection du Type de génération d'états est définie sur Service.</span><span class="sxs-lookup"><span data-stu-id="d2b42-155">Verify that the Reporting type selection is set to 'Service'.</span></span>  
    * <span data-ttu-id="d2b42-156">Vous devez peut-être déverrouiller le guide pour modifier la valeur de ce champ.</span><span class="sxs-lookup"><span data-stu-id="d2b42-156">You may need to unlock the task guide to change the value in this field.</span></span>  

## <a name="set-up-countryregion-parameters-for-eu-sales-list-reporting"></a><span data-ttu-id="d2b42-157">Paramétrer les paramètres des pays/régions pour la déclaration de la liste des ventes intracommunautaires</span><span class="sxs-lookup"><span data-stu-id="d2b42-157">Set up country/region parameters for EU sales list reporting</span></span>
1. <span data-ttu-id="d2b42-158">Accédez à Taxe > Paramétrage > Taxe > Paramètres de pays/région.</span><span class="sxs-lookup"><span data-stu-id="d2b42-158">Go to Tax > Setup > Sales tax > Country/region parameters.</span></span>
2. <span data-ttu-id="d2b42-159">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="d2b42-159">Click New.</span></span>
3. <span data-ttu-id="d2b42-160">Tapez PRT dans le champ Pays/Région.</span><span class="sxs-lookup"><span data-stu-id="d2b42-160">In the Country/region field, type 'PRT'.</span></span>
4. <span data-ttu-id="d2b42-161">Dans le champ Taxe, entrez « PT ».</span><span class="sxs-lookup"><span data-stu-id="d2b42-161">In the Sales tax field, type 'PT'.</span></span>

## <a name="create-tax-exempt-numbers"></a><span data-ttu-id="d2b42-162">Créer des numéros identifiant TVA</span><span class="sxs-lookup"><span data-stu-id="d2b42-162">Create tax exempt numbers</span></span>
1. <span data-ttu-id="d2b42-163">Accédez à Taxe > Paramétrage > Taxe > Numéros d'exonération fiscale.</span><span class="sxs-lookup"><span data-stu-id="d2b42-163">Go to Tax > Setup > Sales tax > Tax exempt numbers.</span></span>
2. <span data-ttu-id="d2b42-164">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="d2b42-164">Click New.</span></span>
3. <span data-ttu-id="d2b42-165">Tapez PRT dans le champ Pays/Région.</span><span class="sxs-lookup"><span data-stu-id="d2b42-165">In the Country/region field, type 'PRT'.</span></span>
4. <span data-ttu-id="d2b42-166">Tapez PT12345 dans le champ Numéros identifiant TVA.</span><span class="sxs-lookup"><span data-stu-id="d2b42-166">In the Tax exempt number field, type 'PT12345'.</span></span>

## <a name="set-up-eu-sales-list-reporting-parameters"></a><span data-ttu-id="d2b42-167">Paramétrer les paramètres de déclaration de la liste des ventes intracommunautaires</span><span class="sxs-lookup"><span data-stu-id="d2b42-167">Set up EU sales list reporting parameters</span></span>
1. <span data-ttu-id="d2b42-168">Accédez à Taxe > Paramétrage > Commerce extérieur > Paramètres de commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="d2b42-168">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
2. <span data-ttu-id="d2b42-169">Cliquez sur l'onglet Liste des ventes intracommunautaires.</span><span class="sxs-lookup"><span data-stu-id="d2b42-169">Click the EU sales list tab.</span></span>
3. <span data-ttu-id="d2b42-170">Sélectionnez Oui dans le champ Transférer les achats.</span><span class="sxs-lookup"><span data-stu-id="d2b42-170">Select Yes in the Transfer purchases field.</span></span>
4. <span data-ttu-id="d2b42-171">Développez la section Règles d'arrondi.</span><span class="sxs-lookup"><span data-stu-id="d2b42-171">Expand the Rounding rules section.</span></span>
5. <span data-ttu-id="d2b42-172">Définissez la règle d'arrondi sur 0,1.</span><span class="sxs-lookup"><span data-stu-id="d2b42-172">Set Rounding rule to '0.1'.</span></span>
6. <span data-ttu-id="d2b42-173">Sélectionnez Oui dans le champ Utiliser la valeur minimale.</span><span class="sxs-lookup"><span data-stu-id="d2b42-173">Select Yes in the Use minimum value field.</span></span>
7. <span data-ttu-id="d2b42-174">Entrez 2 dans le champ Nombre de décimales.</span><span class="sxs-lookup"><span data-stu-id="d2b42-174">In the Number of decimals field, enter '2'.</span></span>
8. <span data-ttu-id="d2b42-175">Développez la section Génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="d2b42-175">Expand the Electronic reporting section.</span></span>
9. <span data-ttu-id="d2b42-176">Dans le champ Mise en correspondance des formats de fichier, sélectionnez « liste des ventes intracommunautaires (DE) ».</span><span class="sxs-lookup"><span data-stu-id="d2b42-176">In the File format mapping field, select 'EU Sales list (DE)'.</span></span>
10. <span data-ttu-id="d2b42-177">Dans le champ Mise en correspondance des formats d'état, sélectionnez « État de la liste des ventes intracommunautaires par lignes ».</span><span class="sxs-lookup"><span data-stu-id="d2b42-177">In the Report format mapping field, select 'EU Sales list by rows report'.</span></span>
11. <span data-ttu-id="d2b42-178">Cliquez sur l'onglet Propriétés de pays/régions.</span><span class="sxs-lookup"><span data-stu-id="d2b42-178">Click the Country/region properties tab.</span></span>
    * <span data-ttu-id="d2b42-179">Vérifiez que le champ Pays/région est défini sur « Local » défini pour le pays/la région DEU.</span><span class="sxs-lookup"><span data-stu-id="d2b42-179">Verify that the Country/region type field is set to 'Domestic' for Country/region DEU.</span></span>  
    * <span data-ttu-id="d2b42-180">Vous devez peut-être déverrouiller le guide pour modifier la valeur de ce champ.</span><span class="sxs-lookup"><span data-stu-id="d2b42-180">You may need to unlock the task guide to change the value in this field.</span></span>  
12. <span data-ttu-id="d2b42-181">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="d2b42-181">Click New.</span></span>
13. <span data-ttu-id="d2b42-182">Tapez PRT dans le champ Pays/Région.</span><span class="sxs-lookup"><span data-stu-id="d2b42-182">In the Country/region field, type 'PRT'.</span></span>
14. <span data-ttu-id="d2b42-183">Dans le champ Code de déclaration d'échanges de biens, tapez PT.</span><span class="sxs-lookup"><span data-stu-id="d2b42-183">In the Intrastat code field, type 'PT'.</span></span>
15. <span data-ttu-id="d2b42-184">Dans le champ Type de pays/région, sélectionnez UE.</span><span class="sxs-lookup"><span data-stu-id="d2b42-184">In the Country/region type field, select 'EU'.</span></span>
16. <span data-ttu-id="d2b42-185">Cliquez sur l'onglet Souches de numéros.</span><span class="sxs-lookup"><span data-stu-id="d2b42-185">Click the Number sequences tab.</span></span>
    * <span data-ttu-id="d2b42-186">Vérifiez qu'un code souche de numéros est spécifié pour la référence « Liste des ventes intracommunautaires ».</span><span class="sxs-lookup"><span data-stu-id="d2b42-186">Verify that a Number sequence code is specified for the Reference 'EU sales list'.</span></span>  

## <a name="create-a-customer-for-eu-sales-list-reporting-demo-purposes"></a><span data-ttu-id="d2b42-187">Créer un client pour démonstration de la déclaration d'états de liste des ventes intracommunautaires</span><span class="sxs-lookup"><span data-stu-id="d2b42-187">Create a customer for EU sales list reporting demo purposes</span></span>
1. <span data-ttu-id="d2b42-188">Accédez à Comptabilité client > Clients > Tous les clients.</span><span class="sxs-lookup"><span data-stu-id="d2b42-188">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="d2b42-189">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="d2b42-189">Click New.</span></span>
3. <span data-ttu-id="d2b42-190">Tapez PRT-001 dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="d2b42-190">In the Customer account field, type 'PRT-001'.</span></span>
4. <span data-ttu-id="d2b42-191">Dans le champ Nom, entrez « Un client du Portugal ».</span><span class="sxs-lookup"><span data-stu-id="d2b42-191">In the Name field, type 'A customer from Portugal'.</span></span>
5. <span data-ttu-id="d2b42-192">Sélectionnez 10 dans le champ Groupe de clients.</span><span class="sxs-lookup"><span data-stu-id="d2b42-192">In the Customer group field, select '10'.</span></span>
6. <span data-ttu-id="d2b42-193">Dans le champ Groupe de taxe, sélectionnez AR-DOM.</span><span class="sxs-lookup"><span data-stu-id="d2b42-193">In the Sales tax group field, select 'AR-DOM'.</span></span>
7. <span data-ttu-id="d2b42-194">Sélectionnez PT12345 dans le champ Numéros identifiant TVA.</span><span class="sxs-lookup"><span data-stu-id="d2b42-194">In the Tax exempt number field, select 'PT12345'.</span></span>
8. <span data-ttu-id="d2b42-195">Tapez PRT dans le champ Pays/Région.</span><span class="sxs-lookup"><span data-stu-id="d2b42-195">In the Country/region field, type 'PRT'.</span></span>
9. <span data-ttu-id="d2b42-196">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="d2b42-196">Click Save.</span></span>


