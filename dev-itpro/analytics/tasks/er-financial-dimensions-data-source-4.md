--- 
title: "Exécuter un état qui utilise les dimensions financières comme source de données pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un modèle de génération d'états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER."
author: NickSelin
manager: AnnBe
ms.date: 10/14/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: e319c9d11ccc4311437ce1e74d4f6c8be0e0de35
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="run-a-report-that-uses-financial-dimensions-as-a-data-source-for-electronic-reporting-er"></a><span data-ttu-id="6b7e9-103">Exécuter un état qui utilise les dimensions financières comme source de données pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="6b7e9-103">Run a report that uses financial dimensions as a data source for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6b7e9-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un modèle de génération d'états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER.</span><span class="sxs-lookup"><span data-stu-id="6b7e9-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="6b7e9-105">Ces étapes peuvent être effectuées dans la société DEMF.</span><span class="sxs-lookup"><span data-stu-id="6b7e9-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="6b7e9-106">Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Utiliser les dimensions financières comme source de données (Partie 3 : créer l'état) ».</span><span class="sxs-lookup"><span data-stu-id="6b7e9-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 3: Design the report)” procedure.</span></span> <span data-ttu-id="6b7e9-107">Vous devez également configurer les types de document par défaut sur la page Paramètres de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="6b7e9-107">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="6b7e9-108">Les types de document par défaut sont également définis lorsque vous téléchargez et importez une configuration ER.</span><span class="sxs-lookup"><span data-stu-id="6b7e9-108">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="6b7e9-109">Exécuter l'état</span><span class="sxs-lookup"><span data-stu-id="6b7e9-109">Run report</span></span>
1. <span data-ttu-id="6b7e9-110">Accédez à Administration d'organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="6b7e9-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="6b7e9-111">Dans l'arborescence, développez « Exemple de modèle de dimensions financières ».</span><span class="sxs-lookup"><span data-stu-id="6b7e9-111">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="6b7e9-112">Dans l'arborescence, sélectionnez « Exemple de modèle de dimensions financières\État du journal comptable ».</span><span class="sxs-lookup"><span data-stu-id="6b7e9-112">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="6b7e9-113">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="6b7e9-113">Click Run.</span></span>
5. <span data-ttu-id="6b7e9-114">Dans le champ Nom de dimension, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6b7e9-114">In the Dimension name field, In the Dimension name field, enter or select a value..</span></span>
    * <span data-ttu-id="6b7e9-115">Pour sélectionner toutes les dimensions de la société actuelle, entrez les informations suivantes : BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="6b7e9-115">To select all dimensions in the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
6. <span data-ttu-id="6b7e9-116">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="6b7e9-116">Expand the Records to include section.</span></span>
7. <span data-ttu-id="6b7e9-117">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="6b7e9-117">Click Filter.</span></span>
8. <span data-ttu-id="6b7e9-118">Sélectionnez la ligne de la table Journaux comptables et du champ Numéro de lot du journal.</span><span class="sxs-lookup"><span data-stu-id="6b7e9-118">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="6b7e9-119">Dans le champ Critères, tapez « 00057 ».</span><span class="sxs-lookup"><span data-stu-id="6b7e9-119">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="6b7e9-120">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="6b7e9-120">Click OK.</span></span>
11. <span data-ttu-id="6b7e9-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="6b7e9-121">Click OK.</span></span>
    * <span data-ttu-id="6b7e9-122">Examinez la sortie générée.</span><span class="sxs-lookup"><span data-stu-id="6b7e9-122">Review the generated output.</span></span> <span data-ttu-id="6b7e9-123">Notez que pour chaque transaction du lot sélectionné, les dimensions financières de l'ensemble de dimensions correspondant sont présentées.</span><span class="sxs-lookup"><span data-stu-id="6b7e9-123">Note that for each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="6b7e9-124">Exécutez cet état et sélectionnez différentes dimensions pour vérifier que l'état n'est pas dépendant du nombre de dimensions sélectionnées ou du nombre de dimensions configurées pour cette instance de Dynamics 365 for Finance and Operations, Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="6b7e9-124">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this Dynamics 365 for Finance and Operations, Enterprise edition instance.</span></span>  


