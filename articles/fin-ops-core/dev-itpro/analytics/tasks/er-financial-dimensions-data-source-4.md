---
title: ER Utiliser les dimensions financières comme source de données (Partie 4 - Exécuter le rapport)
description: Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un modèle de génération d'états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER.
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
ms.openlocfilehash: 7ae9f72df5d6ff6add4eb97836cf32509aebd511
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141964"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a><span data-ttu-id="c0114-103">ER Utiliser les dimensions financières comme source de données (Partie 4 - Exécuter le rapport)</span><span class="sxs-lookup"><span data-stu-id="c0114-103">ER Use financial dimensions as a data source (Part 4 - Run the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c0114-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un modèle de génération d'états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER.</span><span class="sxs-lookup"><span data-stu-id="c0114-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="c0114-105">Ces étapes peuvent être effectuées dans la société DEMF.</span><span class="sxs-lookup"><span data-stu-id="c0114-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="c0114-106">Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Utiliser les dimensions financières comme source de données (Partie 3 : créer l'état) ».</span><span class="sxs-lookup"><span data-stu-id="c0114-106">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 3: Design the report)" procedure.</span></span> <span data-ttu-id="c0114-107">Vous devez également configurer les types de document par défaut sur la page Paramètres de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="c0114-107">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="c0114-108">Les types de document par défaut sont également définis lorsque vous téléchargez et importez une configuration ER.</span><span class="sxs-lookup"><span data-stu-id="c0114-108">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="c0114-109">Exécuter l'état</span><span class="sxs-lookup"><span data-stu-id="c0114-109">Run report</span></span>
1. <span data-ttu-id="c0114-110">Accédez à Administration d'organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="c0114-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="c0114-111">Dans l'arborescence, développez « Exemple de modèle de dimensions financières ».</span><span class="sxs-lookup"><span data-stu-id="c0114-111">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="c0114-112">Dans l'arborescence, sélectionnez « Exemple de modèle de dimensions financières\État du journal comptable ».</span><span class="sxs-lookup"><span data-stu-id="c0114-112">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="c0114-113">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="c0114-113">Click Run.</span></span>
5. <span data-ttu-id="c0114-114">Dans le champ Nom de dimension, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c0114-114">In the Dimension name field, In the Dimension name field, enter or select a value..</span></span>
    * <span data-ttu-id="c0114-115">Pour sélectionner toutes les dimensions de la société actuelle, entrez les informations suivantes : BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="c0114-115">To select all dimensions in the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
6. <span data-ttu-id="c0114-116">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="c0114-116">Expand the Records to include section.</span></span>
7. <span data-ttu-id="c0114-117">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="c0114-117">Click Filter.</span></span>
8. <span data-ttu-id="c0114-118">Sélectionnez la ligne de la table Journaux comptables et du champ Numéro de lot du journal.</span><span class="sxs-lookup"><span data-stu-id="c0114-118">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="c0114-119">Dans le champ Critères, tapez « 00057 ».</span><span class="sxs-lookup"><span data-stu-id="c0114-119">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="c0114-120">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c0114-120">Click OK.</span></span>
11. <span data-ttu-id="c0114-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c0114-121">Click OK.</span></span>
    * <span data-ttu-id="c0114-122">Examinez la sortie générée.</span><span class="sxs-lookup"><span data-stu-id="c0114-122">Review the generated output.</span></span> <span data-ttu-id="c0114-123">Notez que pour chaque transaction du lot sélectionné, les dimensions financières de l'ensemble de dimensions correspondant sont présentées.</span><span class="sxs-lookup"><span data-stu-id="c0114-123">Note that for each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="c0114-124">Exécutez cet état et sélectionnez différentes dimensions pour vérifier que l'état n'est pas dépendant du nombre de dimensions sélectionnées ou du nombre de dimensions configurées pour cette instance.</span><span class="sxs-lookup"><span data-stu-id="c0114-124">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this instance.</span></span>  

