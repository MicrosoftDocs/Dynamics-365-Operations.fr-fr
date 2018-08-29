--- 
title: "Générer des documents contenant des données d'application"
description: "Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, « ER Générer des documents avec la mise à jour des données d'application (Partie 4 - Modifier le format) »."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 90c6ebc456d3e137e43022fad7d59ce3ca2cdcab
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="generate-documents-that-have-application-data"></a><span data-ttu-id="80893-103">Générer des documents contenant des données d'application</span><span class="sxs-lookup"><span data-stu-id="80893-103">Generate documents that have application data</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="80893-104">Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, « ER Générer des documents avec la mise à jour des données d'application (Partie 4 : Modifier le format) ».</span><span class="sxs-lookup"><span data-stu-id="80893-104">To complete the steps in this procedure, you must first complete the procedure, “ER Generate documents with application data update (Part 4: Modify format)”.</span></span>



<span data-ttu-id="80893-105">Les étapes de cette procédure expliquent comment créer des configurations ER pour générer un document électronique et mettre à jour les données d'application.</span><span class="sxs-lookup"><span data-stu-id="80893-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="80893-106">Dans cette procédure, vous exécutez la configuration du format ER pour générer l'état de déclaration d'échanges de biens et mettre à jour les données d'application pour archiver les détails du processus de génération d'états.</span><span class="sxs-lookup"><span data-stu-id="80893-106">In this procedure, you execute the ER format configuration to generate the Intrastat report and update application data for archiving details of the reporting process.</span></span>



<span data-ttu-id="80893-107">Cette procédure est créée pour les utilisateurs auxquels le rôle Administrateur système ou Développeur d'états électroniques a été affecté.</span><span class="sxs-lookup"><span data-stu-id="80893-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="80893-108">Ces étapes peuvent être effectuées à l'aide de l'ensemble de données DEMF.</span><span class="sxs-lookup"><span data-stu-id="80893-108">These steps can be completed using the DEMF dataset.</span></span> <span data-ttu-id="80893-109">Avant de commencer, vérifiez que le contexte de pays pour la société DEMF est BEL (Belgique).</span><span class="sxs-lookup"><span data-stu-id="80893-109">Before you begin, make sure that the country context for the DEMF company is BEL (Belgium).</span></span>


## <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="80893-110">Définir les paramètres de commerce extérieur</span><span class="sxs-lookup"><span data-stu-id="80893-110">Set up foreign trade parameters</span></span>
1. <span data-ttu-id="80893-111">Accédez à Taxe > Paramétrage > Commerce extérieur > Paramètres de commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="80893-111">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
2. <span data-ttu-id="80893-112">Cliquez sur l'onglet Souches de numéros.</span><span class="sxs-lookup"><span data-stu-id="80893-112">Click the Number sequences tab.</span></span>
    * <span data-ttu-id="80893-113">Archivage des détails du processus de génération d'états de déclaration d'échanges de biens, nous devons identifier les enregistrements de chaque archive que nous avons créés.</span><span class="sxs-lookup"><span data-stu-id="80893-113">Archiving details of Intrastat reporting process, we need to identify records of each archive we created.</span></span> <span data-ttu-id="80893-114">Une souche de numéros spéciale doit être configurée à cet effet.</span><span class="sxs-lookup"><span data-stu-id="80893-114">A special number sequence must be configured for that.</span></span>  
3. <span data-ttu-id="80893-115">Sélectionnez la référence « ID archive de la déclaration d'échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="80893-115">Select the ‘Intrastat archive ID’ reference.</span></span>
4. <span data-ttu-id="80893-116">Tapez une valeur dans le champ Code souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="80893-116">In the Number sequence code field, type a value.</span></span>
    * <span data-ttu-id="80893-117">Dans le champ Code souche de numéros, entrez ou sélectionnez la valeur « Fore_2 ».</span><span class="sxs-lookup"><span data-stu-id="80893-117">In the ‘Number sequence code’ field, enter or select the value ‘Fore_2’.</span></span>  
5. <span data-ttu-id="80893-118">Résolvez les modifications du code souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="80893-118">ResolveChanges the Number sequence code.</span></span>
6. <span data-ttu-id="80893-119">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="80893-119">Click Save.</span></span>
7. <span data-ttu-id="80893-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="80893-120">Close the page.</span></span>

## <a name="run-modified-er-format"></a><span data-ttu-id="80893-121">Exécuter le format ER modifié</span><span class="sxs-lookup"><span data-stu-id="80893-121">Run modified ER format</span></span>
1. <span data-ttu-id="80893-122">Accédez à Administration d'organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="80893-122">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="80893-123">Dans l'arborescence, développez « Déclaration d'échanges de biens (modèle) ».</span><span class="sxs-lookup"><span data-stu-id="80893-123">In the tree, expand 'Intrastat (model)'.</span></span>
3. <span data-ttu-id="80893-124">Dans l'arborescence, sélectionnez « Déclaration d'échanges de biens (modèle)\Déclaration d'échanges de biens (format) ».</span><span class="sxs-lookup"><span data-stu-id="80893-124">In the tree, select 'Intrastat (model)\Intrastat (format)'.</span></span>
4. <span data-ttu-id="80893-125">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="80893-125">Click Run.</span></span>
5. <span data-ttu-id="80893-126">Dans le champ Entrer le nom du fichier, tapez « intrastat2.xml ».</span><span class="sxs-lookup"><span data-stu-id="80893-126">In the Enter file name field, type 'intrastat2.xml'.</span></span>
    * <span data-ttu-id="80893-127">intrastat2.xml</span><span class="sxs-lookup"><span data-stu-id="80893-127">intrastat2.xml</span></span>  
6. <span data-ttu-id="80893-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="80893-128">Click OK.</span></span>

## <a name="review-er-format-executions-results"></a><span data-ttu-id="80893-129">Examiner les résultats de l'exécution du format ER</span><span class="sxs-lookup"><span data-stu-id="80893-129">Review ER format execution’s results</span></span>
    * <span data-ttu-id="80893-130">Examinez le fichier XML généré.</span><span class="sxs-lookup"><span data-stu-id="80893-130">Review the generated XML file.</span></span>  
1. <span data-ttu-id="80893-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="80893-131">Close the page.</span></span>
2. <span data-ttu-id="80893-132">Accédez à Taxe > Déclarations > Commerce extérieur > Déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="80893-132">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
    * <span data-ttu-id="80893-133">Ouvrez cet écran contenant les transactions de déclaration d'échanges de biens qui ont été incluses dans le document électronique généré.</span><span class="sxs-lookup"><span data-stu-id="80893-133">Open this form containing Intrastat transactions that have been included to the generated electronic document.</span></span>  
3. <span data-ttu-id="80893-134">Cliquez sur Archive de la déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="80893-134">Click Intrastat archive.</span></span>
    * <span data-ttu-id="80893-135">Comme le format ER exécuté contient maintenant les paramètres pour la mise à jour des données d'application, les détails de la génération d'états de déclaration d'échanges de biens ont été archivés.</span><span class="sxs-lookup"><span data-stu-id="80893-135">Since the executed ER format contains now settings for application data update, the details of the completed Intrastat reporting have been archived.</span></span> <span data-ttu-id="80893-136">Dans cet écran, vous pouvez voir l'enregistrement d'en-tête de l'archive créée.</span><span class="sxs-lookup"><span data-stu-id="80893-136">In this form, you can see the header record of the created archive.</span></span>  
4. <span data-ttu-id="80893-137">Cliquez sur Détails.</span><span class="sxs-lookup"><span data-stu-id="80893-137">Click Details.</span></span>
    * <span data-ttu-id="80893-138">Dans cet écran, vous pouvez voir les détails de l'archive créée.</span><span class="sxs-lookup"><span data-stu-id="80893-138">In this form, you can see the details for the created archive.</span></span>  
5. <span data-ttu-id="80893-139">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="80893-139">Close the page.</span></span>
6. <span data-ttu-id="80893-140">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="80893-140">Close the page.</span></span>
7. <span data-ttu-id="80893-141">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="80893-141">Close the page.</span></span>


