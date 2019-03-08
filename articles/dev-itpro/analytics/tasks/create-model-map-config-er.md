---
title: Créer des configurations de mise en correspondance de modèles d'états électroniques
description: Cette procédure permet de créer une configuration de mise en correspondance des modèles d'états électroniques et d'utiliser les fonctions ER intégrées pour effectuer des calculs globaux efficaces.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 614ef06fcf5761f1cf2afb6e7655558d2858d763
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "357172"
---
# <a name="create-electronic-reporting-er-model-mapping-configurations"></a><span data-ttu-id="93db6-103">Créer des configurations de mise en correspondance de modèles d'états électroniques</span><span class="sxs-lookup"><span data-stu-id="93db6-103">Create Electronic reporting (ER) model mapping configurations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="93db6-104">Cette procédure permet de créer une configuration de mise en correspondance des modèles d'états électroniques et d'utiliser les fonctions ER intégrées pour effectuer des calculs globaux efficaces.</span><span class="sxs-lookup"><span data-stu-id="93db6-104">Use this procedure to design a new Electronic reporting (ER) model mapping configuration and use built-in ER functions for efficient aggregate calculations.</span></span> <span data-ttu-id="93db6-105">Dans cette procédure, vous créerez une configuration pour la société fictive, Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="93db6-105">In this procedure, you will create a configuration for sample company, Litware, Inc.</span></span> 

<span data-ttu-id="93db6-106">Cette procédure est créée pour les utilisateurs auxquels le rôle Administrateur système ou Développeur d'états électroniques a été affecté.</span><span class="sxs-lookup"><span data-stu-id="93db6-106">This procedure is created for uses with the assigned role of System administrator or Electronic reporting developer.</span></span>

<span data-ttu-id="93db6-107">Ces étapes peuvent être effectuées à l'aide d'un ensemble de données quelconque.</span><span class="sxs-lookup"><span data-stu-id="93db6-107">These steps can be completed using any dataset.</span></span> <span data-ttu-id="93db6-108">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="93db6-108">To complete these steps, you must first complete the steps in the procedure, “Create a configuration provider and mark it as active.”</span></span>

1. <span data-ttu-id="93db6-109">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="93db6-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="93db6-110">Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme actif.</span><span class="sxs-lookup"><span data-stu-id="93db6-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="93db6-111">Si ce fournisseur de configuration ne s'affiche pas, effectuez les étapes de la procédure, « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="93db6-111">If you don’t see this configuration provider, complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>  
2. <span data-ttu-id="93db6-112">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="93db6-112">Click Reporting configurations.</span></span>
3. <span data-ttu-id="93db6-113">Cliquez sur Afficher les filtres.</span><span class="sxs-lookup"><span data-stu-id="93db6-113">Click Show filters.</span></span>
4. <span data-ttu-id="93db6-114">Dans le champ « Nom », entrez la valeur de filtre « Déclaration d'échanges de biens » et utilisez l'opérateur de filtre « commence par ».</span><span class="sxs-lookup"><span data-stu-id="93db6-114">In the "Name" field, enter the filter value, "Intrastat" and use the filter operator "begins with".</span></span>
    * <span data-ttu-id="93db6-115">Appliquez ce filtre permettent de rechercher la configuration du modèle de données « Déclaration d'échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="93db6-115">Apply this filter to find the ‘Intrastat’ data model configuration.</span></span> <span data-ttu-id="93db6-116">Il peut exister dans l'arborescence de configurations.</span><span class="sxs-lookup"><span data-stu-id="93db6-116">This model may already exist in the configurations tree.</span></span> <span data-ttu-id="93db6-117">Dans ce cas, ignorez la prochaine sous-tâche.</span><span class="sxs-lookup"><span data-stu-id="93db6-117">If it does, skip the next sub-task.</span></span>   

## <a name="get-the-intrastat-model-configuration-provided-by-microsoft"></a><span data-ttu-id="93db6-118">Obtenir la configuration du modèle de déclaration d'échanges de biens fournie par Microsoft</span><span class="sxs-lookup"><span data-stu-id="93db6-118">Get the Intrastat model configuration provided by Microsoft</span></span>
1. <span data-ttu-id="93db6-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="93db6-119">Close the page.</span></span>
2. <span data-ttu-id="93db6-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="93db6-120">Close the page.</span></span>
3. <span data-ttu-id="93db6-121">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="93db6-121">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
4. <span data-ttu-id="93db6-122">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="93db6-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="93db6-123">Sélectionnez la vignette Fournisseur Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93db6-123">Select the Microsoft provider tile.</span></span>  
5. <span data-ttu-id="93db6-124">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="93db6-124">Click Repositories.</span></span>
    * <span data-ttu-id="93db6-125">Cliquez sur Référentiels dans la vignette Fournisseur Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93db6-125">Click Repositories in the Microsoft provider tile.</span></span>  
6. <span data-ttu-id="93db6-126">Cliquez sur Afficher les filtres.</span><span class="sxs-lookup"><span data-stu-id="93db6-126">Click Show filters.</span></span>
7. <span data-ttu-id="93db6-127">Dans le champ « Nom du type », entrez la valeur de filtre « ressources » et utilisez l'opérateur de filtre « contient ».</span><span class="sxs-lookup"><span data-stu-id="93db6-127">In the "Type name" field, enter the filter value, “resources” and use the filter operator "contains".</span></span> 
8. <span data-ttu-id="93db6-128">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="93db6-128">Click Open.</span></span>
9. <span data-ttu-id="93db6-129">Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="93db6-129">In the tree, select 'Intrastat model'.</span></span>
10. <span data-ttu-id="93db6-130">Cliquez sur Importer.</span><span class="sxs-lookup"><span data-stu-id="93db6-130">Click Import.</span></span>
11. <span data-ttu-id="93db6-131">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="93db6-131">Click Yes.</span></span>
    * <span data-ttu-id="93db6-132">Vous avez importé la configuration de modèle ER contenant le modèle de données que vous utiliserez pour explorer la façon dont la nouvelle fonctionnalité ER peut être utilisée.</span><span class="sxs-lookup"><span data-stu-id="93db6-132">You imported the ER model configuration that contains the data model that you will use to explore how the new ER functionality can be used.</span></span>  
12. <span data-ttu-id="93db6-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="93db6-133">Close the page.</span></span>
13. <span data-ttu-id="93db6-134">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="93db6-134">Close the page.</span></span>
14. <span data-ttu-id="93db6-135">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="93db6-135">Click Reporting configurations.</span></span>

## <a name="add-a-new-model-mapping-configuration"></a><span data-ttu-id="93db6-136">Ajouter une nouvelle configuration de mise en correspondance de modèle</span><span class="sxs-lookup"><span data-stu-id="93db6-136">Add a new model mapping configuration</span></span>
1. <span data-ttu-id="93db6-137">Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="93db6-137">In the tree, select 'Intrastat model'.</span></span>
2. <span data-ttu-id="93db6-138">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="93db6-138">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="93db6-139">Dans le champ Nouveau, entrez « Mise en correspondance de modèle basée sur le modèle de données Déclaration d'échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="93db6-139">In the New field, enter 'Model Mapping based on data model Intrastat'.</span></span>
4. <span data-ttu-id="93db6-140">Dans le champ Nom, tapez « Exemple de mise en correspondance de déclaration d'échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="93db6-140">In the Name field, type 'Intrastat sample mapping'.</span></span>
    * <span data-ttu-id="93db6-141">Exemple de mise en correspondance de déclaration d'échanges de biens</span><span class="sxs-lookup"><span data-stu-id="93db6-141">Intrastat sample mapping</span></span>  
5. <span data-ttu-id="93db6-142">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="93db6-142">Click Create configuration.</span></span>

