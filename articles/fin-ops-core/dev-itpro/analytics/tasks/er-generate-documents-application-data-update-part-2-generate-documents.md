---
title: Concevoir des configurations pour générer des documents avec des données d’application
description: Cette rubrique décrit comment créer des configurations d’états électroniques pour générer un document électronique entrant. (Partie 1 - Importer les configurations).
author: NickSelin
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
ms.openlocfilehash: 9d3f528d48f345ec4b5cc2a46d7740cb6d0a36cd
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751080"
---
# <a name="design-configurations-to-generate-documents-that-have-application-data"></a><span data-ttu-id="50cdb-104">Concevoir des configurations pour générer des documents avec des données d’application</span><span class="sxs-lookup"><span data-stu-id="50cdb-104">Design configurations to generate documents that have application data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="50cdb-105">Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, ER Générer des documents avec la mise à jour des données d’application (Partie 1 : Importer les configurations).</span><span class="sxs-lookup"><span data-stu-id="50cdb-105">To complete the steps in this procedure, you must first complete the procedure, ER Generate documents with application data update (Part 1: Import configurations).</span></span>



<span data-ttu-id="50cdb-106">Les étapes de cette procédure expliquent comment créer des configurations ER pour générer un document électronique.</span><span class="sxs-lookup"><span data-stu-id="50cdb-106">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document.</span></span> <span data-ttu-id="50cdb-107">Dans cette procédure, vous exécutez la configuration importée du format ER qui a été créée pour la société fictive, Litware, Inc. pour générer des documents électroniques.</span><span class="sxs-lookup"><span data-stu-id="50cdb-107">In this procedure, you run the ER imported format configuration that has been created for the sample company, Litware, Inc. to generate electronic documents.</span></span>



<span data-ttu-id="50cdb-108">Cette procédure est créée pour les utilisateurs auxquels le rôle Administrateur système ou Développeur d’états électroniques a été affecté.</span><span class="sxs-lookup"><span data-stu-id="50cdb-108">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="50cdb-109">Ces étapes peuvent être effectuées à l’aide de l’ensemble de données DEMF.</span><span class="sxs-lookup"><span data-stu-id="50cdb-109">These steps can be completed using the DEMF dataset.</span></span> 



<span data-ttu-id="50cdb-110">Avant de commencer, modifiez le contexte de pays pour la société DEMF de DEU (Allemagne) à BEL (Belgique).</span><span class="sxs-lookup"><span data-stu-id="50cdb-110">Before you begin, change the country context for the DEMF company from DEU (Germany) to BEL (Belgium).</span></span> <span data-ttu-id="50cdb-111">Cliquez sur Administration d’organisation > Organisations > Entités juridiques pour mettre à jour le code pays dans l’adresse principale de l’entité juridique DEMF.</span><span class="sxs-lookup"><span data-stu-id="50cdb-111">Click Organization administration > Organizations > Legal entities to update the country code in the primary address of the legal entity DEMF.</span></span> <span data-ttu-id="50cdb-112">Redémarrez votre application.</span><span class="sxs-lookup"><span data-stu-id="50cdb-112">Restart your application.</span></span>


## <a name="run-imported-er-format"></a><span data-ttu-id="50cdb-113">Exécuter le format ER importé</span><span class="sxs-lookup"><span data-stu-id="50cdb-113">Run imported ER format</span></span>
1. <span data-ttu-id="50cdb-114">Accédez à Administration d’organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="50cdb-114">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="50cdb-115">Dans l’arborescence, développez « Déclaration d’échanges de biens (modèle) ».</span><span class="sxs-lookup"><span data-stu-id="50cdb-115">In the tree, expand 'Intrastat (model)'.</span></span>
3. <span data-ttu-id="50cdb-116">Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens (modèle)\Déclaration d’échanges de biens (format) ».</span><span class="sxs-lookup"><span data-stu-id="50cdb-116">In the tree, select 'Intrastat (model)\Intrastat (format)'.</span></span>
4. <span data-ttu-id="50cdb-117">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="50cdb-117">Click Run.</span></span>
    * <span data-ttu-id="50cdb-118">Exécutez la version brouillon de la configuration du format ER pour générer l’état de déclaration d’échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="50cdb-118">Run the draft version of the ER format configuration to generate the Intrastat report.</span></span>  
5. <span data-ttu-id="50cdb-119">Dans le champ Entrer le nom du fichier, tapez « intrastat.xml ».</span><span class="sxs-lookup"><span data-stu-id="50cdb-119">In the Enter file name field, type 'intrastat.xml'.</span></span>
    * <span data-ttu-id="50cdb-120">Entrez le nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="50cdb-120">Specify the name of the file.</span></span>  
6. <span data-ttu-id="50cdb-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="50cdb-121">Click OK.</span></span>
    * <span data-ttu-id="50cdb-122">Examinez le fichier XML généré.</span><span class="sxs-lookup"><span data-stu-id="50cdb-122">Review the generated XML file.</span></span>  
7. <span data-ttu-id="50cdb-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="50cdb-123">Close the page.</span></span>
8. <span data-ttu-id="50cdb-124">Accédez à Taxe > Déclarations > Commerce extérieur > Déclaration d’échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="50cdb-124">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
    * <span data-ttu-id="50cdb-125">Ouvrez cet écran pour afficher les transactions de déclaration d’échanges de biens qui sont incluses dans le document électronique généré.</span><span class="sxs-lookup"><span data-stu-id="50cdb-125">Open this form to view the Intrastat transactions that are included in the generated electronic document.</span></span>  
9. <span data-ttu-id="50cdb-126">Cliquez sur Archive de la déclaration d’échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="50cdb-126">Click Intrastat archive.</span></span>
    * <span data-ttu-id="50cdb-127">Comme le format ER exécuté ne contient pas de paramètres pour la mise à jour des données d’application, les détails de l’état de déclaration d’échanges de biens n’ont pas été archivés.</span><span class="sxs-lookup"><span data-stu-id="50cdb-127">Because the executed ER format does not contain any settings for application data update, the details of the completed Intrastat report have not been archived.</span></span>  
10. <span data-ttu-id="50cdb-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="50cdb-128">Close the page.</span></span>
11. <span data-ttu-id="50cdb-129">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="50cdb-129">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]