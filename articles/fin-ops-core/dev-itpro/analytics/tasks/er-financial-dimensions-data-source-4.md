---
title: ER Utiliser les dimensions financières comme source de données (Partie 4 – Exécuter le rapport)
description: Cette rubrique décrit comment configurer un modèle de gestion des états électroniques pour utiliser les dimensions financières comme source de données pour les rapports de gestion des états électroniques. (Partie 4)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a06936da71d7b05f312a99c8c11d148403d29c3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752386"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a><span data-ttu-id="46641-104">ER Utiliser les dimensions financières comme source de données (Partie 4 – Exécuter le rapport)</span><span class="sxs-lookup"><span data-stu-id="46641-104">ER Use financial dimensions as a data source (Part 4 - Run the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="46641-105">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut configurer un modèle de génération d’états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER.</span><span class="sxs-lookup"><span data-stu-id="46641-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="46641-106">Ces étapes peuvent être effectuées dans la société DEMF.</span><span class="sxs-lookup"><span data-stu-id="46641-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="46641-107">Pour effectuer ces étapes, vous devez d’abord effectuer les étapes de la procédure « ER Utiliser les dimensions financières comme source de données (Partie 3 : créer l’état) ».</span><span class="sxs-lookup"><span data-stu-id="46641-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 3: Design the report)" procedure.</span></span> <span data-ttu-id="46641-108">Vous devez également configurer les types de document par défaut sur la page Paramètres de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="46641-108">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="46641-109">Les types de document par défaut sont également définis lorsque vous téléchargez et importez une configuration ER.</span><span class="sxs-lookup"><span data-stu-id="46641-109">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="46641-110">Exécuter l’état</span><span class="sxs-lookup"><span data-stu-id="46641-110">Run report</span></span>
1. <span data-ttu-id="46641-111">Accédez à Administration d’organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="46641-111">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="46641-112">Dans l’arborescence, développez « Exemple de modèle de dimensions financières ».</span><span class="sxs-lookup"><span data-stu-id="46641-112">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="46641-113">Dans l’arborescence, sélectionnez « Exemple de modèle de dimensions financières\État du journal comptable ».</span><span class="sxs-lookup"><span data-stu-id="46641-113">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="46641-114">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="46641-114">Click Run.</span></span>
<span data-ttu-id="46641-115">![Page Configurations d’ER](../media/er-financial-dimensions-guides-run1.png)</span><span class="sxs-lookup"><span data-stu-id="46641-115">![ER configurations page](../media/er-financial-dimensions-guides-run1.png)</span></span>
5. <span data-ttu-id="46641-116">Dans le champ Nom de dimension, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="46641-116">In the Dimension name field, enter or select a value.</span></span>
    * <span data-ttu-id="46641-117">Pour sélectionner toutes les dimensions de la société actuelle, entrez les informations suivantes : BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="46641-117">To select all dimensions in the current company, enter the following information:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
![Page Configurations d’ER](../media/er-financial-dimensions-guides-run2.png)
6. <span data-ttu-id="46641-119">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="46641-119">Expand the Records to include section.</span></span>
7. <span data-ttu-id="46641-120">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="46641-120">Click Filter.</span></span>
8. <span data-ttu-id="46641-121">Sélectionnez la ligne de la table Journaux comptables et du champ Numéro de lot du journal.</span><span class="sxs-lookup"><span data-stu-id="46641-121">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="46641-122">Dans le champ Critères, tapez « 00057 ».</span><span class="sxs-lookup"><span data-stu-id="46641-122">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="46641-123">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="46641-123">Click OK.</span></span>
11. <span data-ttu-id="46641-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="46641-124">Click OK.</span></span>
<span data-ttu-id="46641-125">![Page Configurations d’ER](../media/er-financial-dimensions-guides-run3.png)</span><span class="sxs-lookup"><span data-stu-id="46641-125">![ER configurations page](../media/er-financial-dimensions-guides-run3.png)</span></span>
    * <span data-ttu-id="46641-126">Examinez la sortie générée.</span><span class="sxs-lookup"><span data-stu-id="46641-126">Review the generated output.</span></span> <span data-ttu-id="46641-127">Pour chaque transaction du lot sélectionné, les dimensions financières de l’ensemble de dimensions correspondant sont présentées.</span><span class="sxs-lookup"><span data-stu-id="46641-127">For each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="46641-128">Exécutez cet état et sélectionnez différentes dimensions pour vérifier que l’état n’est pas dépendant du nombre de dimensions sélectionnées ou du nombre de dimensions configurées pour cette instance.</span><span class="sxs-lookup"><span data-stu-id="46641-128">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this instance.</span></span>  
![Page Configurations d’ER](../media/er-financial-dimensions-guides-run4.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]