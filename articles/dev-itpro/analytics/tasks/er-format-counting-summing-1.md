--- 
title: "Créer le format pour effectuer le comptage et la synthèse pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: efdb64fa157af0d96c2ff0e5de3db5a98190bc68
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="create-formate-for-counting-and-summing-for-electronic-reporting-er"></a><span data-ttu-id="f4809-103">Créer le format pour effectuer le comptage et la synthèse pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="f4809-103">Create formate for counting and summing for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f4809-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée.</span><span class="sxs-lookup"><span data-stu-id="f4809-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="f4809-105">Ces étapes peuvent être effectuées dans n'importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="f4809-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="f4809-106">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="f4809-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="f4809-107">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="f4809-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="f4809-108">Accéder à la liste des configurations fournies par Microsoft</span><span class="sxs-lookup"><span data-stu-id="f4809-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="f4809-109">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="f4809-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="f4809-110">Assurez-vous que le fournisseur « Litware, Inc. »</span><span class="sxs-lookup"><span data-stu-id="f4809-110">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="f4809-111">est disponible et marqué comme actif.</span><span class="sxs-lookup"><span data-stu-id="f4809-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="f4809-112">Sélectionnez le fournisseur « Litware, Inc. »</span><span class="sxs-lookup"><span data-stu-id="f4809-112">Select the “Litware, Inc.”</span></span> <span data-ttu-id="f4809-113">.</span><span class="sxs-lookup"><span data-stu-id="f4809-113">provider.</span></span>
3. <span data-ttu-id="f4809-114">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="f4809-114">Click Repositories.</span></span>
    * <span data-ttu-id="f4809-115">Si un référentiel du type « Ressources opérationnelles » existe déjà, ignorez les étapes restantes de la sous-tâche actuelle.</span><span class="sxs-lookup"><span data-stu-id="f4809-115">If a repository of the "Operations resources" type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="f4809-116">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f4809-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="f4809-117">Dans le champ Type du référentiel de configuration, entrez « Ressources opérationnelles ».</span><span class="sxs-lookup"><span data-stu-id="f4809-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="f4809-118">Cliquez sur Créer un référentiel.</span><span class="sxs-lookup"><span data-stu-id="f4809-118">Click Create repository.</span></span>
7. <span data-ttu-id="f4809-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f4809-119">Click OK.</span></span>

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a><span data-ttu-id="f4809-120">Obtenir les configurations de déclaration d'échanges de biens fournies par Microsoft</span><span class="sxs-lookup"><span data-stu-id="f4809-120">Get the Intrastat configurations provided by Microsoft</span></span>
1. <span data-ttu-id="f4809-121">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="f4809-121">Click Open.</span></span>
2. <span data-ttu-id="f4809-122">Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne) ».</span><span class="sxs-lookup"><span data-stu-id="f4809-122">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
3. <span data-ttu-id="f4809-123">Cliquez sur Importer.</span><span class="sxs-lookup"><span data-stu-id="f4809-123">Click Import.</span></span>
    * <span data-ttu-id="f4809-124">Cliquez sur Importer pour la version 1.1 de la configuration sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f4809-124">Click Import for version 1.1 of the selected configuration.</span></span>  
4. <span data-ttu-id="f4809-125">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="f4809-125">Click Yes.</span></span>
5. <span data-ttu-id="f4809-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f4809-126">Close the page.</span></span>
6. <span data-ttu-id="f4809-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f4809-127">Close the page.</span></span>
7. <span data-ttu-id="f4809-128">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="f4809-128">Click Reporting configurations.</span></span>
8. <span data-ttu-id="f4809-129">Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="f4809-129">In the tree, expand 'Intrastat model'.</span></span>
9. <span data-ttu-id="f4809-130">Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne) ».</span><span class="sxs-lookup"><span data-stu-id="f4809-130">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>


