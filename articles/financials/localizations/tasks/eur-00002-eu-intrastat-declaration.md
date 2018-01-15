--- 
title: "Générer un fichier de déclaration d'échanges de biens de l'UE"
description: "Cette procédure vous fait parcourir les étapes requises pour exporter la déclaration d'échanges de biens dans le format de fichier électronique et pour prévisualiser les données de déclaration dans un format Excel."
author: Anasyash
manager: AnnBe
ms.date: 06/09/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 34ec97b7cf761ee4478fa982fa6c153e66ad3a28
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="generate-an-eu-intrastat-declaration"></a><span data-ttu-id="34e03-103">Générer un fichier de déclaration d'échanges de biens de l'UE</span><span class="sxs-lookup"><span data-stu-id="34e03-103">Generate an EU Intrastat declaration</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="34e03-104">Cette procédure vous fait parcourir les étapes requises pour exporter la déclaration d'échanges de biens dans le format de fichier électronique et pour prévisualiser les données de déclaration dans un format Excel.</span><span class="sxs-lookup"><span data-stu-id="34e03-104">This procedure walks you through the steps required to export the Intrastat declaration in the electronic file format and preview the declaration data in an Excel format.</span></span> 

<span data-ttu-id="34e03-105">Avant d'exécuter cette procédure, vous devez transférer des transactions dans la déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="34e03-105">Before you can complete this procedure, you must transfer transactions to the Intrastat.</span></span> 

<span data-ttu-id="34e03-106">Cette procédure a été créée à l'aide des données fictives de la société DEMF.</span><span class="sxs-lookup"><span data-stu-id="34e03-106">This procedure was created using the demo data company DEMF.</span></span>


## <a name="import-configurations-with-settings"></a><span data-ttu-id="34e03-107">Importer des configurations avec des paramètres</span><span class="sxs-lookup"><span data-stu-id="34e03-107">Import configurations with settings</span></span>
1. <span data-ttu-id="34e03-108">Accédez à Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="34e03-108">Go to Workspaces > Electronic reporting</span></span>
2. <span data-ttu-id="34e03-109">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="34e03-109">Click Set active.</span></span>
3. <span data-ttu-id="34e03-110">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="34e03-110">Click Repositories.</span></span>
4. <span data-ttu-id="34e03-111">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="34e03-111">Click Open.</span></span>
5. <span data-ttu-id="34e03-112">Ouvrez le filtre de la colonne Nom de la configuration.</span><span class="sxs-lookup"><span data-stu-id="34e03-112">Open Configuration name column filter.</span></span>
6. <span data-ttu-id="34e03-113">Appliquez un filtre sur le champ Nom de la configuration, avec la valeur Déclaration d'échanges de biens (DE), à l'aide de l'opérateur de filtre « commence par ».</span><span class="sxs-lookup"><span data-stu-id="34e03-113">Apply a filter on the "Configuration name" field, with a value of "Intrastat (DE)", using the "begins with" filter operator.</span></span>
    * <span data-ttu-id="34e03-114">Vous devez sélectionner le nom de configuration applicable pour le pays de votre entité juridique.</span><span class="sxs-lookup"><span data-stu-id="34e03-114">You should select the configuration name applicable for the country of your legal entity.</span></span> <span data-ttu-id="34e03-115">Cette procédure utilise l'entité juridique allemande (DEMF) comme exemple, donc « Déclaration d'échanges de biens (DE) » doit être sélectionné.</span><span class="sxs-lookup"><span data-stu-id="34e03-115">This procedure uses the German legal entity (DEMF) as an example, therefore "Intrastat (DE)" should be chosen.</span></span>  
    * <span data-ttu-id="34e03-116">Cliquez sur Importation, puis sur Oui.</span><span class="sxs-lookup"><span data-stu-id="34e03-116">Click Import and then click Yes.</span></span>  
7. <span data-ttu-id="34e03-117">Ouvrez le filtre de la colonne Nom de la configuration.</span><span class="sxs-lookup"><span data-stu-id="34e03-117">Open Configuration name column filter.</span></span>
8. <span data-ttu-id="34e03-118">Appliquez un filtre sur le champ Nom de la configuration, avec la valeur État de déclaration d'échanges de biens, à l'aide de l'opérateur de filtre « commence par ».</span><span class="sxs-lookup"><span data-stu-id="34e03-118">Apply a filter on the "Configuration name" field, with a value of "intrastat report", using the "begins with" filter operator.</span></span>
    * <span data-ttu-id="34e03-119">Cliquez sur Importation, puis sur Oui.</span><span class="sxs-lookup"><span data-stu-id="34e03-119">Click Import and then click Yes.</span></span>  

## <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="34e03-120">Définir les paramètres de commerce extérieur</span><span class="sxs-lookup"><span data-stu-id="34e03-120">Set up Foreign trade parameters</span></span>
1. <span data-ttu-id="34e03-121">Accédez à Taxe > Paramétrage > Commerce extérieur > Paramètres de commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="34e03-121">Go to Tax > Setup > Foreign trade > Foreign trade parameters</span></span>
2. <span data-ttu-id="34e03-122">Développez la section Génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="34e03-122">Expand the Electronic reporting section.</span></span>
3. <span data-ttu-id="34e03-123">Saisissez ou sélectionnez une valeur Déclaration d'échanges de biens (DE) dans le champ Mise en correspondance des formats de fichier.</span><span class="sxs-lookup"><span data-stu-id="34e03-123">In the File format mapping field, enter or select a value Intrastat (DE)</span></span>
4. <span data-ttu-id="34e03-124">Saisissez ou sélectionnez une valeur État de déclaration d'échanges de biens dans le champ Mise en correspondance des formats d'état.</span><span class="sxs-lookup"><span data-stu-id="34e03-124">In the Report format mapping field, enter or select a value Intrastat report</span></span>
5. <span data-ttu-id="34e03-125">Développez la section Règles d'arrondi.</span><span class="sxs-lookup"><span data-stu-id="34e03-125">Expand the Rounding rules section.</span></span>
    * <span data-ttu-id="34e03-126">Vous devez paramétrer des règles d'arrondi applicables dans votre pays/région pour la génération d'états de déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="34e03-126">You should set up rounding rules that are applicable in your country/region for Intrastat reporting.</span></span>  
6. <span data-ttu-id="34e03-127">Entrez un nombre dans le champ Règle d'arrondi.</span><span class="sxs-lookup"><span data-stu-id="34e03-127">In the Rounding rule field, enter a number.</span></span>
    * <span data-ttu-id="34e03-128">Entrez la précision de l'arrondi, par exemple, entrez 0,01.</span><span class="sxs-lookup"><span data-stu-id="34e03-128">Enter rounding precision, for example, enter '0.01'.</span></span>  
7. <span data-ttu-id="34e03-129">Entrez un nombre dans le champ Nombre de décimales pour le montant.</span><span class="sxs-lookup"><span data-stu-id="34e03-129">In the Number of decimals for amount field, enter a number.</span></span>
    * <span data-ttu-id="34e03-130">Entrez 2, par exemple.</span><span class="sxs-lookup"><span data-stu-id="34e03-130">For example, enter '2'.</span></span>  
8. <span data-ttu-id="34e03-131">Sélectionnez une option dans le champ Arrondi en dessous d'un (1) kg.</span><span class="sxs-lookup"><span data-stu-id="34e03-131">In the Rounding below 1 kg field, select an option.</span></span>
    * <span data-ttu-id="34e03-132">Sélectionnez Arrondi à 1 kg, par exemple.</span><span class="sxs-lookup"><span data-stu-id="34e03-132">For example, select 'Rounding up to 1 kg'.</span></span>  
9. <span data-ttu-id="34e03-133">Entrez un nombre dans le champ Règle d'arrondi.</span><span class="sxs-lookup"><span data-stu-id="34e03-133">In the Rounding rule field, enter a number.</span></span>
    * <span data-ttu-id="34e03-134">Entrez 1, par exemple pour arrondir le poids à l'entier.</span><span class="sxs-lookup"><span data-stu-id="34e03-134">For example, enter '1' for rounding weight to the integer.</span></span>  
10. <span data-ttu-id="34e03-135">Développez la section Limite inférieure.</span><span class="sxs-lookup"><span data-stu-id="34e03-135">Expand the Minimum limit section.</span></span>
11. <span data-ttu-id="34e03-136">Dans le champ Poids, saisissez un nombre.</span><span class="sxs-lookup"><span data-stu-id="34e03-136">In the Weight field, enter a number.</span></span>
    * <span data-ttu-id="34e03-137">Entrez 10, par exemple comme poids minimal.</span><span class="sxs-lookup"><span data-stu-id="34e03-137">For example, enter '10' as the minimum weight.</span></span>  
12. <span data-ttu-id="34e03-138">Dans le champ Montant, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="34e03-138">In the Amount field, enter a number.</span></span>
    * <span data-ttu-id="34e03-139">Entrez 200, par exemple comme montant minimal.</span><span class="sxs-lookup"><span data-stu-id="34e03-139">For example, enter '200' as the minimum amount.</span></span>  
13. <span data-ttu-id="34e03-140">Saisissez ou sélectionnez une valeur dans le champ Marchandise.</span><span class="sxs-lookup"><span data-stu-id="34e03-140">In the Commodity field, enter or select a value.</span></span>

## <a name="set-up-compression-of-intrastat"></a><span data-ttu-id="34e03-141">Paramétrer la compression de la déclaration d'échanges de biens</span><span class="sxs-lookup"><span data-stu-id="34e03-141">Set up Compression of Intrastat</span></span>
1. <span data-ttu-id="34e03-142">Accédez à Taxes > Paramétrage > Commerce extérieur > Compression de la déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="34e03-142">Go to Tax > Setup > Foreign trade > Compression of Intrastat.</span></span>
2. <span data-ttu-id="34e03-143">Cliquez sur Supprimer.</span><span class="sxs-lookup"><span data-stu-id="34e03-143">Click Remove.</span></span>
3. <span data-ttu-id="34e03-144">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="34e03-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="34e03-145">Sélectionnez Marchandise dans la section Disponible.</span><span class="sxs-lookup"><span data-stu-id="34e03-145">For example, select Commodity in the Available section.</span></span>  
4. <span data-ttu-id="34e03-146">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="34e03-146">Click Add.</span></span>

## <a name="generate-intrastat-declaration"></a><span data-ttu-id="34e03-147">Générer la déclaration d'échanges de biens</span><span class="sxs-lookup"><span data-stu-id="34e03-147">Generate Intrastat declaration</span></span>
1. <span data-ttu-id="34e03-148">Accédez à Taxe > Déclarations > Commerce extérieur > Déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="34e03-148">Go to Tax > Declarations > Foreign trade > Intrastat</span></span>
2. <span data-ttu-id="34e03-149">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="34e03-149">Click Validate.</span></span>
    * <span data-ttu-id="34e03-150">La validation est effectuée en fonction du champ Vérifier le paramétrage de la page Paramètres de commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="34e03-150">The validation is done according to the Check setup field on the Foreign trade parameters page.</span></span>  
3. <span data-ttu-id="34e03-151">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="34e03-151">Click OK.</span></span>
4. <span data-ttu-id="34e03-152">Cliquez sur Mise à jour.</span><span class="sxs-lookup"><span data-stu-id="34e03-152">Click Update.</span></span>
5. <span data-ttu-id="34e03-153">Cliquez sur Limite inférieure.</span><span class="sxs-lookup"><span data-stu-id="34e03-153">Click Minimum limit.</span></span>
6. <span data-ttu-id="34e03-154">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="34e03-154">In the Start date field, enter a date.</span></span>
    * <span data-ttu-id="34e03-155">Entrez 1er janvier 2015, par exemple.</span><span class="sxs-lookup"><span data-stu-id="34e03-155">For example, enter January 1, 2015.</span></span>  
7. <span data-ttu-id="34e03-156">Sélectionnez Oui dans le champ Compresser.</span><span class="sxs-lookup"><span data-stu-id="34e03-156">Select Yes in the Compress field.</span></span>
8. <span data-ttu-id="34e03-157">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="34e03-157">In the End date field, enter a date.</span></span>
    * <span data-ttu-id="34e03-158">Entrez 31 janvier 2015, par exemple.</span><span class="sxs-lookup"><span data-stu-id="34e03-158">For example, enter January 31, 2015.</span></span>  
9. <span data-ttu-id="34e03-159">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="34e03-159">Click OK.</span></span>
10. <span data-ttu-id="34e03-160">Cliquez sur Mise à jour.</span><span class="sxs-lookup"><span data-stu-id="34e03-160">Click Update.</span></span>
11. <span data-ttu-id="34e03-161">Cliquez sur Compresser.</span><span class="sxs-lookup"><span data-stu-id="34e03-161">Click Compress.</span></span>
    * <span data-ttu-id="34e03-162">Cette compression se produit en fonction de la manière dont vous définissez la compression des paramètres de déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="34e03-162">This compression happens according to how you set the Compression of intrastate settings.</span></span>  
12. <span data-ttu-id="34e03-163">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="34e03-163">In the Start date field, enter a date.</span></span>
    * <span data-ttu-id="34e03-164">Entrez 1er janvier 2015, par exemple.</span><span class="sxs-lookup"><span data-stu-id="34e03-164">For example, enter January 1, 2015.</span></span>  
13. <span data-ttu-id="34e03-165">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="34e03-165">In the End date field, enter a date.</span></span>
    * <span data-ttu-id="34e03-166">Entrez le 31 janvier 2015, par exemple.</span><span class="sxs-lookup"><span data-stu-id="34e03-166">For example, enter 31st January 2015.</span></span>  
14. <span data-ttu-id="34e03-167">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="34e03-167">Click OK.</span></span>
15. <span data-ttu-id="34e03-168">Cliquez sur Mise à jour.</span><span class="sxs-lookup"><span data-stu-id="34e03-168">Click Update.</span></span>
16. <span data-ttu-id="34e03-169">Cliquez sur Régénérer les numéros de souche.</span><span class="sxs-lookup"><span data-stu-id="34e03-169">Click Regenerate sequence numbers.</span></span>
17. <span data-ttu-id="34e03-170">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="34e03-170">Click OK.</span></span>
18. <span data-ttu-id="34e03-171">Cliquez sur Résultat.</span><span class="sxs-lookup"><span data-stu-id="34e03-171">Click Output.</span></span>
19. <span data-ttu-id="34e03-172">Cliquez sur État.</span><span class="sxs-lookup"><span data-stu-id="34e03-172">Click Report.</span></span>
20. <span data-ttu-id="34e03-173">Entrez le premier jour de la période de déclaration dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="34e03-173">In the From date field, enter the first date of the reporting period.</span></span>
    * <span data-ttu-id="34e03-174">Définissez la date sur le 1er janvier 2015, par exemple.</span><span class="sxs-lookup"><span data-stu-id="34e03-174">For example, set the date to January 1, 2015.</span></span>  
21. <span data-ttu-id="34e03-175">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="34e03-175">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="34e03-176">Entrez 31 janvier 2015, par exemple.</span><span class="sxs-lookup"><span data-stu-id="34e03-176">For example, enter January 31, 2015.</span></span>  
22. <span data-ttu-id="34e03-177">Sélectionnez Oui dans le champ Générer un fichier.</span><span class="sxs-lookup"><span data-stu-id="34e03-177">Select Yes in the Generate file field.</span></span>
23. <span data-ttu-id="34e03-178">Tapez une valeur dans le champ Nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="34e03-178">In the File name field, type a value.</span></span>
24. <span data-ttu-id="34e03-179">Sélectionnez Oui dans le champ Générer un état.</span><span class="sxs-lookup"><span data-stu-id="34e03-179">Select Yes in the Generate report field.</span></span>
25. <span data-ttu-id="34e03-180">Tapez une valeur dans le champ Nom du fichier d'état.</span><span class="sxs-lookup"><span data-stu-id="34e03-180">In the Report file name field, type a value.</span></span>
26. <span data-ttu-id="34e03-181">Sélectionnez une option dans le champ Direction.</span><span class="sxs-lookup"><span data-stu-id="34e03-181">In the Direction field, select an option.</span></span>
    * <span data-ttu-id="34e03-182">Sélectionnez Répartitions, par exemple.</span><span class="sxs-lookup"><span data-stu-id="34e03-182">For example, select 'Dispatches'.</span></span>  
27. <span data-ttu-id="34e03-183">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="34e03-183">Click OK.</span></span>

