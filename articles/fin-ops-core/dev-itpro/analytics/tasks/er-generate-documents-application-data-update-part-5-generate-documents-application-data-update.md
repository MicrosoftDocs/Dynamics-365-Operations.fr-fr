---
title: Générer des documents contenant des données d’application
description: 'Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, « ER Générer des documents avec la mise à jour des données d’application (Partie 4 : Modifier le format) ».'
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c474f4bc7940a429ed62870e00302c93581eb9a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569579"
---
# <a name="generate-documents-that-have-application-data"></a><span data-ttu-id="da8f4-103">Générer des documents contenant des données d’application</span><span class="sxs-lookup"><span data-stu-id="da8f4-103">Generate documents that have application data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="da8f4-104">Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, « ER Générer des documents avec la mise à jour des données d’application (Partie 4 : Modifier le format) ».</span><span class="sxs-lookup"><span data-stu-id="da8f4-104">To complete the steps in this procedure, you must first complete the procedure, "ER Generate documents with application data update (Part 4: Modify format)".</span></span>



<span data-ttu-id="da8f4-105">Les étapes de cette procédure expliquent comment créer des configurations ER pour générer un document électronique et mettre à jour les données d’application.</span><span class="sxs-lookup"><span data-stu-id="da8f4-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="da8f4-106">Dans cette procédure, vous exécutez la configuration du format ER pour générer l’état de déclaration d’échanges de biens et mettre à jour les données d’application pour archiver les détails du processus de génération d’états.</span><span class="sxs-lookup"><span data-stu-id="da8f4-106">In this procedure, you execute the ER format configuration to generate the Intrastat report and update application data for archiving details of the reporting process.</span></span>



<span data-ttu-id="da8f4-107">Cette procédure est créée pour les utilisateurs auxquels le rôle Administrateur système ou Développeur d’états électroniques a été affecté.</span><span class="sxs-lookup"><span data-stu-id="da8f4-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="da8f4-108">Ces étapes peuvent être effectuées à l’aide de l’ensemble de données DEMF.</span><span class="sxs-lookup"><span data-stu-id="da8f4-108">These steps can be completed using the DEMF dataset.</span></span> <span data-ttu-id="da8f4-109">Avant de commencer, vérifiez que le contexte de pays pour la société DEMF est BEL (Belgique).</span><span class="sxs-lookup"><span data-stu-id="da8f4-109">Before you begin, make sure that the country context for the DEMF company is BEL (Belgium).</span></span>


## <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="da8f4-110">Définir les paramètres de commerce extérieur</span><span class="sxs-lookup"><span data-stu-id="da8f4-110">Set up foreign trade parameters</span></span>
1. <span data-ttu-id="da8f4-111">Accédez à Taxe > Paramétrage > Commerce extérieur > Paramètres de commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="da8f4-111">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
2. <span data-ttu-id="da8f4-112">Cliquez sur l’onglet Souches de numéros.</span><span class="sxs-lookup"><span data-stu-id="da8f4-112">Click the Number sequences tab.</span></span>

    <span data-ttu-id="da8f4-113">Archivage des détails du processus de génération d’états de déclaration d’échanges de biens, nous devons identifier les enregistrements de chaque archive que nous avons créés.</span><span class="sxs-lookup"><span data-stu-id="da8f4-113">Archiving details of Intrastat reporting process, we need to identify records of each archive we created.</span></span> <span data-ttu-id="da8f4-114">Une souche de numéros spéciale doit être configurée à cet effet.</span><span class="sxs-lookup"><span data-stu-id="da8f4-114">A special number sequence must be configured for that.</span></span>  

3. <span data-ttu-id="da8f4-115">Sélectionnez la référence « ID archive de la déclaration d’échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="da8f4-115">Select the 'Intrastat archive ID' reference.</span></span>
4. <span data-ttu-id="da8f4-116">Tapez une valeur dans le champ Code souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="da8f4-116">In the Number sequence code field, type a value.</span></span>

    <span data-ttu-id="da8f4-117">Dans le champ Code souche de numéros, entrez ou sélectionnez la valeur « Fore_2 ».</span><span class="sxs-lookup"><span data-stu-id="da8f4-117">In the 'Number sequence code' field, enter or select the value 'Fore_2'.</span></span>  

5. <span data-ttu-id="da8f4-118">Résolvez les modifications du code souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="da8f4-118">ResolveChanges the Number sequence code.</span></span>
6. <span data-ttu-id="da8f4-119">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="da8f4-119">Click Save.</span></span>
7. <span data-ttu-id="da8f4-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="da8f4-120">Close the page.</span></span>

## <a name="run-modified-er-format"></a><span data-ttu-id="da8f4-121">Exécuter le format ER modifié</span><span class="sxs-lookup"><span data-stu-id="da8f4-121">Run modified ER format</span></span>
1. <span data-ttu-id="da8f4-122">Accédez à Administration d’organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="da8f4-122">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="da8f4-123">Dans l’arborescence, développez « Déclaration d’échanges de biens (modèle) ».</span><span class="sxs-lookup"><span data-stu-id="da8f4-123">In the tree, expand 'Intrastat (model)'.</span></span>
3. <span data-ttu-id="da8f4-124">Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens (modèle)\Déclaration d’échanges de biens (format) ».</span><span class="sxs-lookup"><span data-stu-id="da8f4-124">In the tree, select 'Intrastat (model)\Intrastat (format)'.</span></span>
4. <span data-ttu-id="da8f4-125">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="da8f4-125">Click Run.</span></span>
5. <span data-ttu-id="da8f4-126">Dans le champ Entrer le nom du fichier, tapez « intrastat2.xml ».</span><span class="sxs-lookup"><span data-stu-id="da8f4-126">In the Enter file name field, type 'intrastat2.xml'.</span></span>
6. <span data-ttu-id="da8f4-127">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="da8f4-127">Click OK.</span></span>

## <a name="review-er-format-executions-results"></a><span data-ttu-id="da8f4-128">Examiner les résultats de l’exécution du format ER</span><span class="sxs-lookup"><span data-stu-id="da8f4-128">Review ER format execution's results</span></span>
<span data-ttu-id="da8f4-129">Examinez le fichier XML généré.</span><span class="sxs-lookup"><span data-stu-id="da8f4-129">Review the generated XML file.</span></span>  
1. <span data-ttu-id="da8f4-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="da8f4-130">Close the page.</span></span>
2. <span data-ttu-id="da8f4-131">Accédez à Taxe > Déclarations > Commerce extérieur > Déclaration d’échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="da8f4-131">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>

    <span data-ttu-id="da8f4-132">Ouvrez cet écran contenant les transactions de déclaration d’échanges de biens qui ont été incluses dans le document électronique généré.</span><span class="sxs-lookup"><span data-stu-id="da8f4-132">Open this form containing Intrastat transactions that have been included to the generated electronic document.</span></span>  

3. <span data-ttu-id="da8f4-133">Cliquez sur Archive de la déclaration d’échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="da8f4-133">Click Intrastat archive.</span></span>

    <span data-ttu-id="da8f4-134">Comme le format ER exécuté contient maintenant les paramètres pour la mise à jour des données d’application, les détails de la génération d’états de déclaration d’échanges de biens ont été archivés.</span><span class="sxs-lookup"><span data-stu-id="da8f4-134">Since the executed ER format contains now settings for application data update, the details of the completed Intrastat reporting have been archived.</span></span> <span data-ttu-id="da8f4-135">Dans cet écran, vous pouvez voir l’enregistrement d’en-tête de l’archive créée.</span><span class="sxs-lookup"><span data-stu-id="da8f4-135">In this form, you can see the header record of the created archive.</span></span>  

4. <span data-ttu-id="da8f4-136">Cliquez sur Détails.</span><span class="sxs-lookup"><span data-stu-id="da8f4-136">Click Details.</span></span>

    <span data-ttu-id="da8f4-137">Dans cet écran, vous pouvez voir les détails de l’archive créée.</span><span class="sxs-lookup"><span data-stu-id="da8f4-137">In this form, you can see the details for the created archive.</span></span>  

5. <span data-ttu-id="da8f4-138">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="da8f4-138">Close the page.</span></span>
6. <span data-ttu-id="da8f4-139">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="da8f4-139">Close the page.</span></span>
7. <span data-ttu-id="da8f4-140">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="da8f4-140">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]