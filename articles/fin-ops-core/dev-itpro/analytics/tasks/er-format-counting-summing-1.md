---
title: ER Configurer le format pour effectuer le comptage et la synthèse (Partie 1 - Créer un format)
description: Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a2a3b3997b8d366f92192ff765dbcff9b68844ba
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182391"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-1-create-format"></a><span data-ttu-id="f648e-103">ER Configurer le format pour effectuer le comptage et la synthèse (Partie 1 : Créer un format)</span><span class="sxs-lookup"><span data-stu-id="f648e-103">ER Configure format to do counting and summing (Part 1: Create format)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f648e-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée.</span><span class="sxs-lookup"><span data-stu-id="f648e-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="f648e-105">Ces étapes peuvent être effectuées dans n'importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="f648e-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="f648e-106">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="f648e-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="f648e-107">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="f648e-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="f648e-108">Accéder à la liste des configurations fournies par Microsoft</span><span class="sxs-lookup"><span data-stu-id="f648e-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="f648e-109">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="f648e-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="f648e-110">Assurez-vous que le fournisseur « Litware, Inc. »</span><span class="sxs-lookup"><span data-stu-id="f648e-110">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="f648e-111">est disponible et marqué comme actif.</span><span class="sxs-lookup"><span data-stu-id="f648e-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="f648e-112">Sélectionnez le fournisseur « Litware, Inc. »</span><span class="sxs-lookup"><span data-stu-id="f648e-112">Select the “Litware, Inc.”</span></span> <span data-ttu-id="f648e-113">.</span><span class="sxs-lookup"><span data-stu-id="f648e-113">provider.</span></span>
3. <span data-ttu-id="f648e-114">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="f648e-114">Click Repositories.</span></span>
    * <span data-ttu-id="f648e-115">Si un référentiel du type « Ressources opérationnelles » existe déjà, ignorez les étapes restantes de la sous-tâche actuelle.</span><span class="sxs-lookup"><span data-stu-id="f648e-115">If a repository of the "Operations resources" type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="f648e-116">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f648e-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="f648e-117">Dans le champ Type du référentiel de configuration, entrez « Ressources opérationnelles ».</span><span class="sxs-lookup"><span data-stu-id="f648e-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="f648e-118">Cliquez sur Créer un référentiel.</span><span class="sxs-lookup"><span data-stu-id="f648e-118">Click Create repository.</span></span>
7. <span data-ttu-id="f648e-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f648e-119">Click OK.</span></span>

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a><span data-ttu-id="f648e-120">Obtenir les configurations de déclaration d'échanges de biens fournies par Microsoft</span><span class="sxs-lookup"><span data-stu-id="f648e-120">Get the Intrastat configurations provided by Microsoft</span></span>
1. <span data-ttu-id="f648e-121">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="f648e-121">Click Open.</span></span>
2. <span data-ttu-id="f648e-122">Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne) ».</span><span class="sxs-lookup"><span data-stu-id="f648e-122">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
3. <span data-ttu-id="f648e-123">Cliquez sur Importer.</span><span class="sxs-lookup"><span data-stu-id="f648e-123">Click Import.</span></span>
    * <span data-ttu-id="f648e-124">Cliquez sur Importer pour la version 1.1 de la configuration sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f648e-124">Click Import for version 1.1 of the selected configuration.</span></span>  
4. <span data-ttu-id="f648e-125">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="f648e-125">Click Yes.</span></span>
5. <span data-ttu-id="f648e-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f648e-126">Close the page.</span></span>
6. <span data-ttu-id="f648e-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f648e-127">Close the page.</span></span>
7. <span data-ttu-id="f648e-128">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="f648e-128">Click Reporting configurations.</span></span>
8. <span data-ttu-id="f648e-129">Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="f648e-129">In the tree, expand 'Intrastat model'.</span></span>
9. <span data-ttu-id="f648e-130">Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne) ».</span><span class="sxs-lookup"><span data-stu-id="f648e-130">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>

