---
title: EUR-00002 Générer un fichier de déclaration d’échanges de biens de l’UE
description: Cette procédure vous fait parcourir les étapes requises pour exporter la déclaration d’échanges de biens dans le format de fichier électronique et pour prévisualiser les données de déclaration dans un format Excel.
author: Anasyash
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, IntrastatParameters, IntrastatCommodityLookup, IntrastatCompressParameters, Intrastat, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 581a837049f239cb9b9fa41eb978304751cb3b54
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989979"
---
# <a name="eur-00002-generate-an-eu-intrastat-declaration"></a><span data-ttu-id="2b409-103">EUR-00002 Générer un fichier de déclaration d’échanges de biens de l’UE</span><span class="sxs-lookup"><span data-stu-id="2b409-103">EUR-00002 Generate an EU Intrastat declaration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2b409-104">Cette procédure vous fait parcourir les étapes requises pour exporter la déclaration d’échanges de biens dans le format de fichier électronique et pour prévisualiser les données de déclaration dans un format Excel.</span><span class="sxs-lookup"><span data-stu-id="2b409-104">This procedure walks you through the steps required to export the Intrastat declaration in the electronic file format and preview the declaration data in an Excel format.</span></span> 

<span data-ttu-id="2b409-105">Avant d’exécuter cette procédure, vous devez transférer des transactions dans la déclaration d’échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="2b409-105">Before you can complete this procedure, you must transfer transactions to the Intrastat.</span></span> 

<span data-ttu-id="2b409-106">Cette procédure a été créée à l’aide des données fictives de la société DEMF.</span><span class="sxs-lookup"><span data-stu-id="2b409-106">This procedure was created using the demo data company DEMF.</span></span>


## <a name="import-configurations-with-settings"></a><span data-ttu-id="2b409-107">Importer des configurations avec des paramètres</span><span class="sxs-lookup"><span data-stu-id="2b409-107">Import configurations with settings</span></span>
1. <span data-ttu-id="2b409-108">Accédez à Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="2b409-108">Go to Workspaces > Electronic reporting</span></span>
2. <span data-ttu-id="2b409-109">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="2b409-109">Click Set active.</span></span>
3. <span data-ttu-id="2b409-110">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="2b409-110">Click Repositories.</span></span>
4. <span data-ttu-id="2b409-111">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="2b409-111">Click Open.</span></span>
5. <span data-ttu-id="2b409-112">Ouvrez le filtre de la colonne Nom de la configuration.</span><span class="sxs-lookup"><span data-stu-id="2b409-112">Open Configuration name column filter.</span></span>
6. <span data-ttu-id="2b409-113">Appliquez un filtre sur le champ Nom de la configuration, avec la valeur Déclaration d’échanges de biens (DE), à l’aide de l’opérateur de filtre « commence par ».</span><span class="sxs-lookup"><span data-stu-id="2b409-113">Apply a filter on the "Configuration name" field, with a value of "Intrastat (DE)", using the "begins with" filter operator.</span></span>
    * <span data-ttu-id="2b409-114">Vous devez sélectionner le nom de configuration applicable pour le pays de votre entité juridique.</span><span class="sxs-lookup"><span data-stu-id="2b409-114">You should select the configuration name applicable for the country of your legal entity.</span></span> <span data-ttu-id="2b409-115">Cette procédure utilise l’entité juridique allemande (DEMF) comme exemple, donc « Déclaration d’échanges de biens (DE) » doit être sélectionné.</span><span class="sxs-lookup"><span data-stu-id="2b409-115">This procedure uses the German legal entity (DEMF) as an example, therefore "Intrastat (DE)" should be chosen.</span></span>  
    * <span data-ttu-id="2b409-116">Cliquez sur Importation, puis sur Oui.</span><span class="sxs-lookup"><span data-stu-id="2b409-116">Click Import and then click Yes.</span></span>  
7. <span data-ttu-id="2b409-117">Ouvrez le filtre de la colonne Nom de la configuration.</span><span class="sxs-lookup"><span data-stu-id="2b409-117">Open Configuration name column filter.</span></span>
8. <span data-ttu-id="2b409-118">Appliquez un filtre sur le champ Nom de la configuration, avec la valeur État de déclaration d’échanges de biens, à l’aide de l’opérateur de filtre « commence par ».</span><span class="sxs-lookup"><span data-stu-id="2b409-118">Apply a filter on the "Configuration name" field, with a value of "intrastat report", using the "begins with" filter operator.</span></span>
    * <span data-ttu-id="2b409-119">Cliquez sur Importation, puis sur Oui.</span><span class="sxs-lookup"><span data-stu-id="2b409-119">Click Import and then click Yes.</span></span>  

## <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="2b409-120">Définir les paramètres de commerce extérieur</span><span class="sxs-lookup"><span data-stu-id="2b409-120">Set up Foreign trade parameters</span></span>
1. <span data-ttu-id="2b409-121">Accédez à Taxe > Paramétrage > Commerce extérieur > Paramètres de commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="2b409-121">Go to Tax > Setup > Foreign trade > Foreign trade parameters</span></span>
2. <span data-ttu-id="2b409-122">Développez la section Génération d’états électroniques.</span><span class="sxs-lookup"><span data-stu-id="2b409-122">Expand the Electronic reporting section.</span></span>
3. <span data-ttu-id="2b409-123">Saisissez ou sélectionnez une valeur Déclaration d’échanges de biens (DE) dans le champ Mise en correspondance des formats de fichier.</span><span class="sxs-lookup"><span data-stu-id="2b409-123">In the File format mapping field, enter or select a value Intrastat (DE)</span></span>
4. <span data-ttu-id="2b409-124">Saisissez ou sélectionnez une valeur État de déclaration d’échanges de biens dans le champ Mise en correspondance des formats d’état.</span><span class="sxs-lookup"><span data-stu-id="2b409-124">In the Report format mapping field, enter or select a value Intrastat report</span></span>
5. <span data-ttu-id="2b409-125">Développez la section Règles d’arrondi.</span><span class="sxs-lookup"><span data-stu-id="2b409-125">Expand the Rounding rules section.</span></span>
    * <span data-ttu-id="2b409-126">Vous devez paramétrer des règles d’arrondi applicables dans votre pays/région pour la génération d’états de déclaration d’échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="2b409-126">You should set up rounding rules that are applicable in your country/region for Intrastat reporting.</span></span>  
6. <span data-ttu-id="2b409-127">Entrez un nombre dans le champ Règle d’arrondi.</span><span class="sxs-lookup"><span data-stu-id="2b409-127">In the Rounding rule field, enter a number.</span></span>
    * <span data-ttu-id="2b409-128">Entrez la précision de l’arrondi, par exemple, entrez 0,01.</span><span class="sxs-lookup"><span data-stu-id="2b409-128">Enter rounding precision, for example, enter '0.01'.</span></span>  
7. <span data-ttu-id="2b409-129">Entrez un nombre dans le champ Nombre de décimales pour le montant.</span><span class="sxs-lookup"><span data-stu-id="2b409-129">In the Number of decimals for amount field, enter a number.</span></span>
    * <span data-ttu-id="2b409-130">Entrez 2, par exemple.</span><span class="sxs-lookup"><span data-stu-id="2b409-130">For example, enter '2'.</span></span>  
8. <span data-ttu-id="2b409-131">Sélectionnez une option dans le champ Arrondi en dessous d’un (1) kg.</span><span class="sxs-lookup"><span data-stu-id="2b409-131">In the Rounding below 1 kg field, select an option.</span></span>
    * <span data-ttu-id="2b409-132">Sélectionnez Arrondi à 1 kg, par exemple.</span><span class="sxs-lookup"><span data-stu-id="2b409-132">For example, select 'Rounding up to 1 kg'.</span></span>  
9. <span data-ttu-id="2b409-133">Entrez un nombre dans le champ Règle d’arrondi.</span><span class="sxs-lookup"><span data-stu-id="2b409-133">In the Rounding rule field, enter a number.</span></span>
    * <span data-ttu-id="2b409-134">Entrez 1, par exemple pour arrondir le poids à l’entier.</span><span class="sxs-lookup"><span data-stu-id="2b409-134">For example, enter '1' for rounding weight to the integer.</span></span>  
10. <span data-ttu-id="2b409-135">Développez la section Limite inférieure.</span><span class="sxs-lookup"><span data-stu-id="2b409-135">Expand the Minimum limit section.</span></span>
11. <span data-ttu-id="2b409-136">Dans le champ Poids, saisissez un nombre.</span><span class="sxs-lookup"><span data-stu-id="2b409-136">In the Weight field, enter a number.</span></span>
    * <span data-ttu-id="2b409-137">Entrez 10, par exemple comme poids minimal.</span><span class="sxs-lookup"><span data-stu-id="2b409-137">For example, enter '10' as the minimum weight.</span></span>  
12. <span data-ttu-id="2b409-138">Dans le champ Montant, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="2b409-138">In the Amount field, enter a number.</span></span>
    * <span data-ttu-id="2b409-139">Entrez 200, par exemple comme montant minimal.</span><span class="sxs-lookup"><span data-stu-id="2b409-139">For example, enter '200' as the minimum amount.</span></span>  
13. <span data-ttu-id="2b409-140">Saisissez ou sélectionnez une valeur dans le champ Marchandise.</span><span class="sxs-lookup"><span data-stu-id="2b409-140">In the Commodity field, enter or select a value.</span></span>

## <a name="set-up-compression-of-intrastat"></a><span data-ttu-id="2b409-141">Paramétrer la compression de la déclaration d’échanges de biens</span><span class="sxs-lookup"><span data-stu-id="2b409-141">Set up Compression of Intrastat</span></span>
1. <span data-ttu-id="2b409-142">Accédez à Taxes > Paramétrage > Commerce extérieur > Compression de la déclaration d’échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="2b409-142">Go to Tax > Setup > Foreign trade > Compression of Intrastat.</span></span>
2. <span data-ttu-id="2b409-143">Cliquez sur Supprimer.</span><span class="sxs-lookup"><span data-stu-id="2b409-143">Click Remove.</span></span>
3. <span data-ttu-id="2b409-144">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2b409-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2b409-145">Sélectionnez Marchandise dans la section Disponible.</span><span class="sxs-lookup"><span data-stu-id="2b409-145">For example, select Commodity in the Available section.</span></span>  
4. <span data-ttu-id="2b409-146">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="2b409-146">Click Add.</span></span>

## <a name="generate-intrastat-declaration"></a><span data-ttu-id="2b409-147">Générer la déclaration d’échanges de biens</span><span class="sxs-lookup"><span data-stu-id="2b409-147">Generate Intrastat declaration</span></span>
1. <span data-ttu-id="2b409-148">Accédez à Taxe > Déclarations > Commerce extérieur > Déclaration d’échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="2b409-148">Go to Tax > Declarations > Foreign trade > Intrastat</span></span>
2. <span data-ttu-id="2b409-149">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="2b409-149">Click Validate.</span></span>
    * <span data-ttu-id="2b409-150">La validation est effectuée en fonction du champ Vérifier le paramétrage de la page Paramètres de commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="2b409-150">The validation is done according to the Check setup field on the Foreign trade parameters page.</span></span>  
3. <span data-ttu-id="2b409-151">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2b409-151">Click OK.</span></span>
4. <span data-ttu-id="2b409-152">Cliquez sur Mise à jour.</span><span class="sxs-lookup"><span data-stu-id="2b409-152">Click Update.</span></span>
5. <span data-ttu-id="2b409-153">Cliquez sur Limite inférieure.</span><span class="sxs-lookup"><span data-stu-id="2b409-153">Click Minimum limit.</span></span>
6. <span data-ttu-id="2b409-154">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="2b409-154">In the Start date field, enter a date.</span></span>
    * <span data-ttu-id="2b409-155">Entrez 1er janvier 2015, par exemple.</span><span class="sxs-lookup"><span data-stu-id="2b409-155">For example, enter January 1, 2015.</span></span>  
7. <span data-ttu-id="2b409-156">Sélectionnez Oui dans le champ Compresser.</span><span class="sxs-lookup"><span data-stu-id="2b409-156">Select Yes in the Compress field.</span></span>
8. <span data-ttu-id="2b409-157">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="2b409-157">In the End date field, enter a date.</span></span>
    * <span data-ttu-id="2b409-158">Entrez 31 janvier 2015, par exemple.</span><span class="sxs-lookup"><span data-stu-id="2b409-158">For example, enter January 31, 2015.</span></span>  
9. <span data-ttu-id="2b409-159">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2b409-159">Click OK.</span></span>
10. <span data-ttu-id="2b409-160">Cliquez sur Mise à jour.</span><span class="sxs-lookup"><span data-stu-id="2b409-160">Click Update.</span></span>
11. <span data-ttu-id="2b409-161">Cliquez sur Compresser.</span><span class="sxs-lookup"><span data-stu-id="2b409-161">Click Compress.</span></span>
    * <span data-ttu-id="2b409-162">Cette compression se produit en fonction de la manière dont vous définissez la compression des paramètres de déclaration d’échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="2b409-162">This compression happens according to how you set the Compression of intrastate settings.</span></span>  
12. <span data-ttu-id="2b409-163">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="2b409-163">In the Start date field, enter a date.</span></span>
    * <span data-ttu-id="2b409-164">Entrez 1er janvier 2015, par exemple.</span><span class="sxs-lookup"><span data-stu-id="2b409-164">For example, enter January 1, 2015.</span></span>  
13. <span data-ttu-id="2b409-165">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="2b409-165">In the End date field, enter a date.</span></span>
    * <span data-ttu-id="2b409-166">Entrez le 31 janvier 2015, par exemple.</span><span class="sxs-lookup"><span data-stu-id="2b409-166">For example, enter 31st January 2015.</span></span>  
14. <span data-ttu-id="2b409-167">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2b409-167">Click OK.</span></span>
15. <span data-ttu-id="2b409-168">Cliquez sur Mise à jour.</span><span class="sxs-lookup"><span data-stu-id="2b409-168">Click Update.</span></span>
16. <span data-ttu-id="2b409-169">Cliquez sur Régénérer les numéros de souche.</span><span class="sxs-lookup"><span data-stu-id="2b409-169">Click Regenerate sequence numbers.</span></span>
17. <span data-ttu-id="2b409-170">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2b409-170">Click OK.</span></span>
18. <span data-ttu-id="2b409-171">Cliquez sur Résultat.</span><span class="sxs-lookup"><span data-stu-id="2b409-171">Click Output.</span></span>
19. <span data-ttu-id="2b409-172">Cliquez sur État.</span><span class="sxs-lookup"><span data-stu-id="2b409-172">Click Report.</span></span>
20. <span data-ttu-id="2b409-173">Entrez le premier jour de la période de déclaration dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="2b409-173">In the From date field, enter the first date of the reporting period.</span></span>
    * <span data-ttu-id="2b409-174">Définissez la date sur le 1er janvier 2015, par exemple.</span><span class="sxs-lookup"><span data-stu-id="2b409-174">For example, set the date to January 1, 2015.</span></span>  
21. <span data-ttu-id="2b409-175">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="2b409-175">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="2b409-176">Entrez 31 janvier 2015, par exemple.</span><span class="sxs-lookup"><span data-stu-id="2b409-176">For example, enter January 31, 2015.</span></span>  
22. <span data-ttu-id="2b409-177">Sélectionnez Oui dans le champ Générer un fichier.</span><span class="sxs-lookup"><span data-stu-id="2b409-177">Select Yes in the Generate file field.</span></span>
23. <span data-ttu-id="2b409-178">Tapez une valeur dans le champ Nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="2b409-178">In the File name field, type a value.</span></span>
24. <span data-ttu-id="2b409-179">Sélectionnez Oui dans le champ Générer un état.</span><span class="sxs-lookup"><span data-stu-id="2b409-179">Select Yes in the Generate report field.</span></span>
25. <span data-ttu-id="2b409-180">Tapez une valeur dans le champ Nom du fichier d’état.</span><span class="sxs-lookup"><span data-stu-id="2b409-180">In the Report file name field, type a value.</span></span>
26. <span data-ttu-id="2b409-181">Sélectionnez une option dans le champ Direction.</span><span class="sxs-lookup"><span data-stu-id="2b409-181">In the Direction field, select an option.</span></span>
    * <span data-ttu-id="2b409-182">Sélectionnez Répartitions, par exemple.</span><span class="sxs-lookup"><span data-stu-id="2b409-182">For example, select 'Dispatches'.</span></span>  
27. <span data-ttu-id="2b409-183">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2b409-183">Click OK.</span></span>

