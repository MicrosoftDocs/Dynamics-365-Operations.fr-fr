--- 
title: "ER Configurer le format pour effectuer le comptage et la synthèse (Partie 1 - Créer un format)"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: d1f925ef8d772189a505f2793de1176756866bf4
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="er-configure-format-to-do-counting-and-summing-part-1-create-format"></a><span data-ttu-id="4c71f-103">ER Configurer le format pour effectuer le comptage et la synthèse (Partie 1 : Créer un format)</span><span class="sxs-lookup"><span data-stu-id="4c71f-103">ER Configure format to do counting and summing (Part 1: Create format)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4c71f-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée.</span><span class="sxs-lookup"><span data-stu-id="4c71f-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="4c71f-105">Ces étapes peuvent être effectuées dans n'importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="4c71f-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="4c71f-106">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="4c71f-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="4c71f-107">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="4c71f-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="4c71f-108">Accéder à la liste des configurations fournies par Microsoft</span><span class="sxs-lookup"><span data-stu-id="4c71f-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="4c71f-109">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="4c71f-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="4c71f-110">Assurez-vous que le fournisseur « Litware, Inc. »</span><span class="sxs-lookup"><span data-stu-id="4c71f-110">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="4c71f-111">est disponible et marqué comme actif.</span><span class="sxs-lookup"><span data-stu-id="4c71f-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="4c71f-112">Sélectionnez le fournisseur « Litware, Inc. »</span><span class="sxs-lookup"><span data-stu-id="4c71f-112">Select the “Litware, Inc.”</span></span> <span data-ttu-id="4c71f-113">.</span><span class="sxs-lookup"><span data-stu-id="4c71f-113">provider.</span></span>
3. <span data-ttu-id="4c71f-114">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="4c71f-114">Click Repositories.</span></span>
    * <span data-ttu-id="4c71f-115">Si un référentiel du type « Ressources opérationnelles » existe déjà, ignorez les étapes restantes de la sous-tâche actuelle.</span><span class="sxs-lookup"><span data-stu-id="4c71f-115">If a repository of the "Operations resources" type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="4c71f-116">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="4c71f-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="4c71f-117">Dans le champ Type du référentiel de configuration, entrez « Ressources opérationnelles ».</span><span class="sxs-lookup"><span data-stu-id="4c71f-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="4c71f-118">Cliquez sur Créer un référentiel.</span><span class="sxs-lookup"><span data-stu-id="4c71f-118">Click Create repository.</span></span>
7. <span data-ttu-id="4c71f-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="4c71f-119">Click OK.</span></span>

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a><span data-ttu-id="4c71f-120">Obtenir les configurations de déclaration d'échanges de biens fournies par Microsoft</span><span class="sxs-lookup"><span data-stu-id="4c71f-120">Get the Intrastat configurations provided by Microsoft</span></span>
1. <span data-ttu-id="4c71f-121">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="4c71f-121">Click Open.</span></span>
2. <span data-ttu-id="4c71f-122">Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne) ».</span><span class="sxs-lookup"><span data-stu-id="4c71f-122">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
3. <span data-ttu-id="4c71f-123">Cliquez sur Importer.</span><span class="sxs-lookup"><span data-stu-id="4c71f-123">Click Import.</span></span>
    * <span data-ttu-id="4c71f-124">Cliquez sur Importer pour la version 1.1 de la configuration sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4c71f-124">Click Import for version 1.1 of the selected configuration.</span></span>  
4. <span data-ttu-id="4c71f-125">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="4c71f-125">Click Yes.</span></span>
5. <span data-ttu-id="4c71f-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="4c71f-126">Close the page.</span></span>
6. <span data-ttu-id="4c71f-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="4c71f-127">Close the page.</span></span>
7. <span data-ttu-id="4c71f-128">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="4c71f-128">Click Reporting configurations.</span></span>
8. <span data-ttu-id="4c71f-129">Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="4c71f-129">In the tree, expand 'Intrastat model'.</span></span>
9. <span data-ttu-id="4c71f-130">Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne) ».</span><span class="sxs-lookup"><span data-stu-id="4c71f-130">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>


