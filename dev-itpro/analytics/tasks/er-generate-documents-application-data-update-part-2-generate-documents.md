--- 
title: "Générer des documents avec la mise à jour des données de l'application pour la gestion des états électroniques (ER)"
description: "Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, ER Générer des documents avec la mise à jour des données d'application (Partie 1 - Importer les configurations)."
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: aa737abc9273e0068d864416ffb85302468088ed
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="generate-documents-with-application-data-update-for-electronic-reporting-er"></a><span data-ttu-id="54370-103">Générer des documents avec la mise à jour des données de l'application pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="54370-103">Generate documents with application data update for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="54370-104">Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, ER Générer des documents avec la mise à jour des données d'application (Partie 1 : Importer les configurations).</span><span class="sxs-lookup"><span data-stu-id="54370-104">To complete the steps in this procedure, you must first complete the procedure, ER Generate documents with application data update (Part 1: Import configurations).</span></span>



<span data-ttu-id="54370-105">Les étapes de cette procédure expliquent comment créer des configurations ER pour générer un document électronique.</span><span class="sxs-lookup"><span data-stu-id="54370-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document.</span></span> <span data-ttu-id="54370-106">Dans cette procédure, vous exécutez la configuration importée du format ER qui a été créée pour la société fictive, Litware, Inc. pour générer des documents électroniques.</span><span class="sxs-lookup"><span data-stu-id="54370-106">In this procedure, you run the ER imported format configuration that has been created for the sample company, Litware, Inc. to generate electronic documents.</span></span>



<span data-ttu-id="54370-107">Cette procédure est créée pour les utilisateurs auxquels le rôle Administrateur système ou Développeur d'états électroniques a été affecté.</span><span class="sxs-lookup"><span data-stu-id="54370-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="54370-108">Ces étapes peuvent être effectuées à l'aide de l'ensemble de données DEMF.</span><span class="sxs-lookup"><span data-stu-id="54370-108">These steps can be completed using the DEMF dataset.</span></span> 



<span data-ttu-id="54370-109">Avant de commencer, modifiez le contexte de pays pour la société DEMF de DEU (Allemagne) à BEL (Belgique).</span><span class="sxs-lookup"><span data-stu-id="54370-109">Before you begin, change the country context for the DEMF company from DEU (Germany) to BEL (Belgium).</span></span> <span data-ttu-id="54370-110">Cliquez sur Administration d'organisation > Organisations > Entités juridiques pour mettre à jour le code pays dans l'adresse principale de l'entité juridique DEMF.</span><span class="sxs-lookup"><span data-stu-id="54370-110">Click Organization administration > Organizations > Legal entities to update the country code in the primary address of the legal entity DEMF.</span></span> <span data-ttu-id="54370-111">Redémarrez votre application.</span><span class="sxs-lookup"><span data-stu-id="54370-111">Restart your application.</span></span>


## <a name="run-imported-er-format"></a><span data-ttu-id="54370-112">Exécuter le format ER importé</span><span class="sxs-lookup"><span data-stu-id="54370-112">Run imported ER format</span></span>
1. <span data-ttu-id="54370-113">Accédez à Administration d'organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="54370-113">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="54370-114">Dans l'arborescence, développez « Déclaration d'échanges de biens (modèle) ».</span><span class="sxs-lookup"><span data-stu-id="54370-114">In the tree, expand 'Intrastat (model)'.</span></span>
3. <span data-ttu-id="54370-115">Dans l'arborescence, sélectionnez « Déclaration d'échanges de biens (modèle)\Déclaration d'échanges de biens (format) ».</span><span class="sxs-lookup"><span data-stu-id="54370-115">In the tree, select 'Intrastat (model)\Intrastat (format)'.</span></span>
4. <span data-ttu-id="54370-116">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="54370-116">Click Run.</span></span>
    * <span data-ttu-id="54370-117">Exécutez la version brouillon de la configuration du format ER pour générer l'état de déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="54370-117">Run the draft version of the ER format configuration to generate the Intrastat report.</span></span>  
5. <span data-ttu-id="54370-118">Dans le champ Entrer le nom du fichier, tapez « intrastat.xml ».</span><span class="sxs-lookup"><span data-stu-id="54370-118">In the Enter file name field, type 'intrastat.xml'.</span></span>
    * <span data-ttu-id="54370-119">Entrez le nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="54370-119">Specify the name of the file.</span></span>  
6. <span data-ttu-id="54370-120">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="54370-120">Click OK.</span></span>
    * <span data-ttu-id="54370-121">Examinez le fichier XML généré.</span><span class="sxs-lookup"><span data-stu-id="54370-121">Review the generated XML file.</span></span>  
7. <span data-ttu-id="54370-122">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="54370-122">Close the page.</span></span>
8. <span data-ttu-id="54370-123">Accédez à Taxe > Déclarations > Commerce extérieur > Déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="54370-123">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
    * <span data-ttu-id="54370-124">Ouvrez cet écran pour afficher les transactions de déclaration d'échanges de biens qui sont incluses dans le document électronique généré.</span><span class="sxs-lookup"><span data-stu-id="54370-124">Open this form to view the Intrastat transactions that are included in the generated electronic document.</span></span>  
9. <span data-ttu-id="54370-125">Cliquez sur Archive de la déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="54370-125">Click Intrastat archive.</span></span>
    * <span data-ttu-id="54370-126">Comme le format ER exécuté ne contient pas de paramètres pour la mise à jour des données d'application, les détails de l'état de déclaration d'échanges de biens n'ont pas été archivés.</span><span class="sxs-lookup"><span data-stu-id="54370-126">Because the executed ER format does not contain any settings for application data update, the details of the completed Intrastat report have not been archived.</span></span>  
10. <span data-ttu-id="54370-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="54370-127">Close the page.</span></span>
11. <span data-ttu-id="54370-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="54370-128">Close the page.</span></span>


