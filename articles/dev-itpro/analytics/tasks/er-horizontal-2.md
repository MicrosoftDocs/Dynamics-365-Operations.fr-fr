---
title: ER Utiliser des plages extensibles horizontalement pour ajouter dynamiquement des colonnes dans les états Excel (Partie 2 - Exécuter le format)
description: Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format d'états électroniques pour générer des états en tant que fichiers de feuilles de calcul (Excel) OPENXML dans lesquels les colonnes requises peuvent être créées dynamiquement sous forme de plages extensibles horizontalement.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 33c1a3134659bb66a67166fec3d7f53af0aa4c6c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544424"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-2-run-format"></a><span data-ttu-id="25aa2-103">ER Utiliser des plages extensibles horizontalement pour ajouter dynamiquement des colonnes dans les états Excel (Partie 2 : Exécuter le format)</span><span class="sxs-lookup"><span data-stu-id="25aa2-103">ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 2: Run format)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="25aa2-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format d'états électroniques pour générer des états en tant que fichiers de feuilles de calcul (Excel) OPENXML dans lesquels les colonnes requises peuvent être créées dynamiquement sous forme de plages extensibles horizontalement.</span><span class="sxs-lookup"><span data-stu-id="25aa2-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to generate reports as OPENXML worksheets (Excel) files in which the required columns can be created dynamically as horizontally expandable ranges.</span></span> <span data-ttu-id="25aa2-105">Ces étapes peuvent être effectuées dans la société DEMF.</span><span class="sxs-lookup"><span data-stu-id="25aa2-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="25aa2-106">Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Utiliser les plages extensibles horizontalement pour ajouter dynamiquement des colonnes dans les états Excel (Partie 1 : Créer un format) ».</span><span class="sxs-lookup"><span data-stu-id="25aa2-106">To complete these steps, you must first complete the steps in the “ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 1: Design format)” procedure.</span></span>

<span data-ttu-id="25aa2-107">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="25aa2-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="find-created-format"></a><span data-ttu-id="25aa2-108">Rechercher le format créé</span><span class="sxs-lookup"><span data-stu-id="25aa2-108">Find created format</span></span>
1. <span data-ttu-id="25aa2-109">Accédez à Administration d'organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="25aa2-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="25aa2-110">Dans l'arborescence, développez « Exemple de modèle de dimensions financières ».</span><span class="sxs-lookup"><span data-stu-id="25aa2-110">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="25aa2-111">Dans l'arborescence, sélectionnez « Exemple de modèle de dimensions financières\Exemple d'état avec des plages extensibles horizontalement ».</span><span class="sxs-lookup"><span data-stu-id="25aa2-111">In the tree, select 'Financial dimensions sample model\Sample report with horizontally expandable ranges'.</span></span>

## <a name="execute-format-to-create-excel-output"></a><span data-ttu-id="25aa2-112">Exécuter le format pour créer la sortie Excel</span><span class="sxs-lookup"><span data-stu-id="25aa2-112">Execute format to create Excel output</span></span>
1. <span data-ttu-id="25aa2-113">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="25aa2-113">Click Run.</span></span>
2. <span data-ttu-id="25aa2-114">Dans le champ Nom de dimension, tapez « BusinessUnit;CostCenter;Department ».</span><span class="sxs-lookup"><span data-stu-id="25aa2-114">In the Dimension name field, type 'BusinessUnit;CostCenter;Department'.</span></span>
    * <span data-ttu-id="25aa2-115">Dans le champ Nom de dimension, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="25aa2-115">In the Dimension name field, enter or select a value.</span></span>  <span data-ttu-id="25aa2-116">Pour sélectionner toutes les dimensions de la société actuelle, entrez les informations suivantes : BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="25aa2-116">To select all dimensions for the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
3. <span data-ttu-id="25aa2-117">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="25aa2-117">Expand the Records to include section.</span></span>
4. <span data-ttu-id="25aa2-118">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="25aa2-118">Click Filter.</span></span>
5. <span data-ttu-id="25aa2-119">Sélectionnez la ligne de la table Journaux comptables et du champ Numéro de lot du journal.</span><span class="sxs-lookup"><span data-stu-id="25aa2-119">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
6. <span data-ttu-id="25aa2-120">Dans le champ Critères, tapez « 00057..00058 ».</span><span class="sxs-lookup"><span data-stu-id="25aa2-120">In the Criteria field, type '00057..00058'.</span></span>
    * <span data-ttu-id="25aa2-121">00057..00058</span><span class="sxs-lookup"><span data-stu-id="25aa2-121">00057..00058</span></span>  
7. <span data-ttu-id="25aa2-122">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="25aa2-122">Click OK.</span></span>
8. <span data-ttu-id="25aa2-123">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="25aa2-123">Click OK.</span></span>
    * <span data-ttu-id="25aa2-124">Examinez la sortie générée.</span><span class="sxs-lookup"><span data-stu-id="25aa2-124">Review the generated output.</span></span> <span data-ttu-id="25aa2-125">Notez que le fichier Excel nouvellement créé contient le même nombre de colonnes sélectionnées que pour les dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="25aa2-125">Note that the newly created Excel file contains the same number of columns that were selected for financial dimensions.</span></span> <span data-ttu-id="25aa2-126">L'en-tête d'état de ces colonnes représente les noms des dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="25aa2-126">The report header in those columns represents financial dimensions’ names.</span></span> <span data-ttu-id="25aa2-127">Les lignes de transactions de ces colonnes représentent les dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="25aa2-127">The transactions’ lines in those columns represent financial dimensions.</span></span> <span data-ttu-id="25aa2-128">Exécutez cet état et sélectionnez différentes dimensions pour vérifier que l'état n'est pas dépendant du nombre de dimensions sélectionnées ou du nombre de dimensions configurées pour cette instance de Dynamics 365 for Finance and Operations, Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="25aa2-128">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this Dynamics 365 for Finance and Operations, Enterprise edition instance.</span></span>  

