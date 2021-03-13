---
title: ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 1 - Préparer le modèle de données)
description: Cette rubrique décrit comment configurer un format de gestion des états électroniques pour utiliser les fichiers de gestion des documents dans la sortie de gestion des états électroniques (pièces jointes). (Partie 1)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bff518c60f0f36bdc88245d79bd82f0c4d0599ed
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092639"
---
# <a name="er-use-document-management-files-in-format-outputs-part-1---prepare-data-model"></a><span data-ttu-id="01aaa-104">ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 1 - Préparer le modèle de données)</span><span class="sxs-lookup"><span data-stu-id="01aaa-104">ER Use Document Management files in format outputs (Part 1 - Prepare data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="01aaa-105">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut configurer un format de génération d’états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER.</span><span class="sxs-lookup"><span data-stu-id="01aaa-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="01aaa-106">Ces étapes peuvent être effectuées dans n’importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="01aaa-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="01aaa-107">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="01aaa-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

<span data-ttu-id="01aaa-108">Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="01aaa-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="01aaa-109">Accéder à la liste des configurations fournies par Microsoft</span><span class="sxs-lookup"><span data-stu-id="01aaa-109">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="01aaa-110">Accédez à Administration d’organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="01aaa-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="01aaa-111">Assurez-vous que le fournisseur « Litware, Inc. »</span><span class="sxs-lookup"><span data-stu-id="01aaa-111">Make sure that the 'Litware, Inc.'</span></span> <span data-ttu-id="01aaa-112">est disponible et marqué comme actif.</span><span class="sxs-lookup"><span data-stu-id="01aaa-112">provider is available and marked as active.</span></span>  

2. <span data-ttu-id="01aaa-113">Sélectionnez le fournisseur « Litware, Inc. »</span><span class="sxs-lookup"><span data-stu-id="01aaa-113">Select the 'Litware, Inc.'</span></span> <span data-ttu-id="01aaa-114">.</span><span class="sxs-lookup"><span data-stu-id="01aaa-114">provider.</span></span>
3. <span data-ttu-id="01aaa-115">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="01aaa-115">Click Repositories.</span></span>

    <span data-ttu-id="01aaa-116">Si un référentiel du type « Ressources opérationnelles » existe déjà, ignorez les étapes restantes de la sous-tâche actuelle.</span><span class="sxs-lookup"><span data-stu-id="01aaa-116">If a repository of the 'Operations resources' type already exists, skip the remaining steps of the current sub-task.</span></span>  

4. <span data-ttu-id="01aaa-117">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="01aaa-117">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="01aaa-118">Dans le champ Type du référentiel de configuration, entrez « Ressources opérationnelles ».</span><span class="sxs-lookup"><span data-stu-id="01aaa-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="01aaa-119">Cliquez sur Créer un référentiel.</span><span class="sxs-lookup"><span data-stu-id="01aaa-119">Click Create repository.</span></span>
7. <span data-ttu-id="01aaa-120">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="01aaa-120">Click OK.</span></span>

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a><span data-ttu-id="01aaa-121">Obtenir les configurations de modèle de facture client fournies par Microsoft</span><span class="sxs-lookup"><span data-stu-id="01aaa-121">Get the Customer invoice model configurations provided by Microsoft</span></span>
1. <span data-ttu-id="01aaa-122">Cliquez sur Afficher les filtres.</span><span class="sxs-lookup"><span data-stu-id="01aaa-122">Click Show filters.</span></span>
2. <span data-ttu-id="01aaa-123">Appliquez les filtres suivants : entrez la valeur de filtre « Ressources opérationnelles » dans le champ « Nom » en utilisant l’opérateur de filtre « commence par ». Entrez la valeur de filtre « » dans le champ « Description » en utilisant l’opérateur de filtre « commence par »</span><span class="sxs-lookup"><span data-stu-id="01aaa-123">Apply the following filters: Enter a filter value of "Operations resources" on the "Name" field using the "begins with" filter operator; Enter a filter value of "" on the "Description" field using the "begins with" filter operator</span></span>
3. <span data-ttu-id="01aaa-124">Cliquez sur Afficher les filtres.</span><span class="sxs-lookup"><span data-stu-id="01aaa-124">Click Show filters.</span></span>
4. <span data-ttu-id="01aaa-125">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="01aaa-125">Click Open.</span></span>
5. <span data-ttu-id="01aaa-126">Dans l’arborescence, sélectionnez « Modèle de facture client ».</span><span class="sxs-lookup"><span data-stu-id="01aaa-126">In the tree, select 'Customer invoice model'.</span></span>

    <span data-ttu-id="01aaa-127">Sélectionnez la configuration du modèle « Modèle de facture client » pour l’importer.</span><span class="sxs-lookup"><span data-stu-id="01aaa-127">Select the model configuration 'Customer invoice model' to import it.</span></span>  

6. <span data-ttu-id="01aaa-128">Cliquez sur Importer.</span><span class="sxs-lookup"><span data-stu-id="01aaa-128">Click Import.</span></span>

    <span data-ttu-id="01aaa-129">Cliquez sur Importer pour la version 1 de la configuration sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="01aaa-129">Click Import for version 1 of the selected configuration.</span></span>  

7. <span data-ttu-id="01aaa-130">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="01aaa-130">Click Yes.</span></span>
8. <span data-ttu-id="01aaa-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="01aaa-131">Close the page.</span></span>
9. <span data-ttu-id="01aaa-132">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="01aaa-132">Close the page.</span></span>
10. <span data-ttu-id="01aaa-133">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="01aaa-133">Click Reporting configurations.</span></span>
11. <span data-ttu-id="01aaa-134">Dans l’arborescence, sélectionnez « Modèle de facture client ».</span><span class="sxs-lookup"><span data-stu-id="01aaa-134">In the tree, select 'Customer invoice model'.</span></span>

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a><span data-ttu-id="01aaa-135">Créez le modèle dérivé pour prendre en charge l’accès aux fichiers de gestion des documents.</span><span class="sxs-lookup"><span data-stu-id="01aaa-135">Create the derived model to support access to the Document Management files.</span></span>
<span data-ttu-id="01aaa-136">Vous créerez votre propre configuration du modèle de facture client en la dérivant de la configuration fournie par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="01aaa-136">You will create our own configuration of the Customer invoice model deriving it from the configuration provided by Microsoft.</span></span> <span data-ttu-id="01aaa-137">Vous utiliserez cette configuration pour implémenter l’accès aux fichiers de gestion des documents et les rendre disponibles pour les documents électroniques que vous créerez en fonction de ce modèle.</span><span class="sxs-lookup"><span data-stu-id="01aaa-137">You will use this configuration to implement access to the Document Management files and make them available for electronic documents that you will create based on this model.</span></span>  
1. <span data-ttu-id="01aaa-138">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="01aaa-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="01aaa-139">Dans le champ Nouveau, entrez « Provenant du nom : Modèle de facture client, Microsoft ».</span><span class="sxs-lookup"><span data-stu-id="01aaa-139">In the New field, enter 'Derive from Name: Customer invoice model, Microsoft'.</span></span>
3. <span data-ttu-id="01aaa-140">Dans le champ Nom, tapez « Modèle de facture client (personnalisé) ».</span><span class="sxs-lookup"><span data-stu-id="01aaa-140">In the Name field, type 'Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="01aaa-141">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="01aaa-141">Click Create configuration.</span></span>

