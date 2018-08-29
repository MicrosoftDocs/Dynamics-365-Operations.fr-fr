--- 
title: "Préparer des modèles de données pour utiliser les fichiers dans la sortie ER"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER."
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: fcafaf17315f54594116a143f36e924bc705d839
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="prepare-data-models-to-use-document-management-files-in-er-output"></a><span data-ttu-id="26530-103">Préparer des modèles de données pour utiliser les fichiers dans la sortie ER</span><span class="sxs-lookup"><span data-stu-id="26530-103">Prepare data models to use Document Management files in ER output</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="26530-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER.</span><span class="sxs-lookup"><span data-stu-id="26530-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="26530-105">Ces étapes peuvent être effectuées dans n'importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="26530-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="26530-106">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="26530-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="26530-107">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="26530-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="26530-108">Accéder à la liste des configurations fournies par Microsoft</span><span class="sxs-lookup"><span data-stu-id="26530-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="26530-109">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="26530-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="26530-110">Assurez-vous que le fournisseur « Litware, Inc. »</span><span class="sxs-lookup"><span data-stu-id="26530-110">Make sure that the 'Litware, Inc.'</span></span> <span data-ttu-id="26530-111">est disponible et marqué comme actif.</span><span class="sxs-lookup"><span data-stu-id="26530-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="26530-112">Sélectionnez le fournisseur « Litware, Inc. »</span><span class="sxs-lookup"><span data-stu-id="26530-112">Select the 'Litware, Inc.'</span></span> <span data-ttu-id="26530-113">.</span><span class="sxs-lookup"><span data-stu-id="26530-113">provider.</span></span>
3. <span data-ttu-id="26530-114">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="26530-114">Click Repositories.</span></span>
    * <span data-ttu-id="26530-115">Si un référentiel du type « Ressources opérationnelles » existe déjà, ignorez les étapes restantes de la sous-tâche actuelle.</span><span class="sxs-lookup"><span data-stu-id="26530-115">If a repository of the 'Operations resources' type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="26530-116">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="26530-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="26530-117">Dans le champ Type du référentiel de configuration, entrez « Ressources opérationnelles ».</span><span class="sxs-lookup"><span data-stu-id="26530-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="26530-118">Cliquez sur Créer un référentiel.</span><span class="sxs-lookup"><span data-stu-id="26530-118">Click Create repository.</span></span>
7. <span data-ttu-id="26530-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="26530-119">Click OK.</span></span>

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a><span data-ttu-id="26530-120">Obtenir les configurations de modèle de facture client fournies par Microsoft</span><span class="sxs-lookup"><span data-stu-id="26530-120">Get the Customer invoice model configurations provided by Microsoft</span></span>
1. <span data-ttu-id="26530-121">Cliquez sur Afficher les filtres.</span><span class="sxs-lookup"><span data-stu-id="26530-121">Click Show filters.</span></span>
2. <span data-ttu-id="26530-122">Appliquez les filtres suivants : entrez la valeur de filtre « Ressources opérationnelles » dans le champ « Nom » en utilisant l'opérateur de filtre « commence par ». Entrez la valeur de filtre « » dans le champ « Description » en utilisant l'opérateur de filtre « commence par »</span><span class="sxs-lookup"><span data-stu-id="26530-122">Apply the following filters: Enter a filter value of "Operations resources" on the "Name" field using the "begins with" filter operator; Enter a filter value of "" on the "Description" field using the "begins with" filter operator</span></span>
3. <span data-ttu-id="26530-123">Cliquez sur Afficher les filtres.</span><span class="sxs-lookup"><span data-stu-id="26530-123">Click Show filters.</span></span>
4. <span data-ttu-id="26530-124">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="26530-124">Click Open.</span></span>
5. <span data-ttu-id="26530-125">Dans l'arborescence, sélectionnez « Modèle de facture client ».</span><span class="sxs-lookup"><span data-stu-id="26530-125">In the tree, select 'Customer invoice model'.</span></span>
    * <span data-ttu-id="26530-126">Sélectionnez la configuration du modèle « Modèle de facture client » pour l'importer.</span><span class="sxs-lookup"><span data-stu-id="26530-126">Select the model configuration 'Customer invoice model' to import it.</span></span>  
6. <span data-ttu-id="26530-127">Cliquez sur Importer.</span><span class="sxs-lookup"><span data-stu-id="26530-127">Click Import.</span></span>
    * <span data-ttu-id="26530-128">Cliquez sur Importer pour la version 1 de la configuration sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="26530-128">Click Import for version 1 of the selected configuration.</span></span>  
7. <span data-ttu-id="26530-129">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="26530-129">Click Yes.</span></span>
8. <span data-ttu-id="26530-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="26530-130">Close the page.</span></span>
9. <span data-ttu-id="26530-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="26530-131">Close the page.</span></span>
10. <span data-ttu-id="26530-132">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="26530-132">Click Reporting configurations.</span></span>
11. <span data-ttu-id="26530-133">Dans l'arborescence, sélectionnez « Modèle de facture client ».</span><span class="sxs-lookup"><span data-stu-id="26530-133">In the tree, select 'Customer invoice model'.</span></span>

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a><span data-ttu-id="26530-134">Créez le modèle dérivé pour prendre en charge l'accès aux fichiers de gestion des documents.</span><span class="sxs-lookup"><span data-stu-id="26530-134">Create the derived model to support access to the Document Management files.</span></span>
    * <span data-ttu-id="26530-135">Vous créerez votre propre configuration du modèle de facture client en la dérivant de la configuration fournie par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="26530-135">You will create our own configuration of the Customer invoice model deriving it from the configuration provided by Microsoft.</span></span> <span data-ttu-id="26530-136">Vous utiliserez cette configuration pour implémenter l'accès aux fichiers de gestion des documents et les rendre disponibles pour les documents électroniques que vous créerez en fonction de ce modèle.</span><span class="sxs-lookup"><span data-stu-id="26530-136">You will use this configuration to implement access to the Document Management files and make them available for electronic documents that you will create based on this model.</span></span>  
1. <span data-ttu-id="26530-137">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="26530-137">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="26530-138">Dans le champ Nouveau, entrez « Provenant du nom : Modèle de facture client, Microsoft ».</span><span class="sxs-lookup"><span data-stu-id="26530-138">In the New field, enter 'Derive from Name: Customer invoice model, Microsoft'.</span></span>
3. <span data-ttu-id="26530-139">Dans le champ Nom, tapez « Modèle de facture client (personnalisé) ».</span><span class="sxs-lookup"><span data-stu-id="26530-139">In the Name field, type 'Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="26530-140">Modèle de facture client (personnalisé)</span><span class="sxs-lookup"><span data-stu-id="26530-140">Customer invoice model (custom)</span></span>  
4. <span data-ttu-id="26530-141">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="26530-141">Click Create configuration.</span></span>


