--- 
title: "Créer un format pour effectuer le comptage et la synthèse"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 7613b78d4a9ab63f5be9773a8699fe3ed94636eb
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="create-format-for-counting-and-summing"></a><span data-ttu-id="28d8d-103">Créer un format pour effectuer le comptage et la synthèse</span><span class="sxs-lookup"><span data-stu-id="28d8d-103">Create format for counting and summing</span></span> 

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="28d8d-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée.</span><span class="sxs-lookup"><span data-stu-id="28d8d-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="28d8d-105">Ces étapes peuvent être effectuées dans n'importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="28d8d-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="28d8d-106">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="28d8d-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="28d8d-107">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="28d8d-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="28d8d-108">Accéder à la liste des configurations fournies par Microsoft</span><span class="sxs-lookup"><span data-stu-id="28d8d-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="28d8d-109">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="28d8d-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="28d8d-110">Assurez-vous que le fournisseur « Litware, Inc. »</span><span class="sxs-lookup"><span data-stu-id="28d8d-110">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="28d8d-111">est disponible et marqué comme actif.</span><span class="sxs-lookup"><span data-stu-id="28d8d-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="28d8d-112">Sélectionnez le fournisseur « Litware, Inc. »</span><span class="sxs-lookup"><span data-stu-id="28d8d-112">Select the “Litware, Inc.”</span></span> <span data-ttu-id="28d8d-113">.</span><span class="sxs-lookup"><span data-stu-id="28d8d-113">provider.</span></span>
3. <span data-ttu-id="28d8d-114">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="28d8d-114">Click Repositories.</span></span>
    * <span data-ttu-id="28d8d-115">Si un référentiel du type « Ressources opérationnelles » existe déjà, ignorez les étapes restantes de la sous-tâche actuelle.</span><span class="sxs-lookup"><span data-stu-id="28d8d-115">If a repository of the "Operations resources" type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="28d8d-116">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="28d8d-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="28d8d-117">Dans le champ Type du référentiel de configuration, entrez « Ressources opérationnelles ».</span><span class="sxs-lookup"><span data-stu-id="28d8d-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="28d8d-118">Cliquez sur Créer un référentiel.</span><span class="sxs-lookup"><span data-stu-id="28d8d-118">Click Create repository.</span></span>
7. <span data-ttu-id="28d8d-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="28d8d-119">Click OK.</span></span>

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a><span data-ttu-id="28d8d-120">Obtenir les configurations de déclaration d'échanges de biens fournies par Microsoft</span><span class="sxs-lookup"><span data-stu-id="28d8d-120">Get the Intrastat configurations provided by Microsoft</span></span>
1. <span data-ttu-id="28d8d-121">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="28d8d-121">Click Open.</span></span>
2. <span data-ttu-id="28d8d-122">Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne) ».</span><span class="sxs-lookup"><span data-stu-id="28d8d-122">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
3. <span data-ttu-id="28d8d-123">Cliquez sur Importer.</span><span class="sxs-lookup"><span data-stu-id="28d8d-123">Click Import.</span></span>
    * <span data-ttu-id="28d8d-124">Cliquez sur Importer pour la version 1.1 de la configuration sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28d8d-124">Click Import for version 1.1 of the selected configuration.</span></span>  
4. <span data-ttu-id="28d8d-125">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="28d8d-125">Click Yes.</span></span>
5. <span data-ttu-id="28d8d-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="28d8d-126">Close the page.</span></span>
6. <span data-ttu-id="28d8d-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="28d8d-127">Close the page.</span></span>
7. <span data-ttu-id="28d8d-128">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="28d8d-128">Click Reporting configurations.</span></span>
8. <span data-ttu-id="28d8d-129">Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="28d8d-129">In the tree, expand 'Intrastat model'.</span></span>
9. <span data-ttu-id="28d8d-130">Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne) ».</span><span class="sxs-lookup"><span data-stu-id="28d8d-130">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>


