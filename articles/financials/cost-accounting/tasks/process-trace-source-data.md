---
title: Traiter et effectuer le suivi des données source
description: Le traitement des données est exécuté par tâche.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a6e913f3630862ba07718592cdd039940c5d40b8
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841127"
---
# <a name="process-and-trace-source-data"></a><span data-ttu-id="0e901-103">Traiter et effectuer le suivi des données source</span><span class="sxs-lookup"><span data-stu-id="0e901-103">Process and trace source data</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0e901-104">Le traitement des données est exécuté par tâche.</span><span class="sxs-lookup"><span data-stu-id="0e901-104">All data processing is run by jobs.</span></span> <span data-ttu-id="0e901-105">Pour chaque tâche et fournisseur de données, un journal est créé pour indiquer que le processus a été exécuté et que les entrées ont été traitées dans la tâche actuelle.</span><span class="sxs-lookup"><span data-stu-id="0e901-105">For each job and data provider, a journal is created to document that the process has been run, and that the entries were processed in the current job.</span></span> <span data-ttu-id="0e901-106">Utilisez cette procédure pour paramétrer une source de données et suivre l'origine d'une entrée de coût spécifique.</span><span class="sxs-lookup"><span data-stu-id="0e901-106">Use this procedure to set up a data source and then  trace the origin of a specific cost entry.</span></span> <span data-ttu-id="0e901-107">Cet enregistrement utilise la société fictive USP2.</span><span class="sxs-lookup"><span data-stu-id="0e901-107">This recording uses the USP2 demo data company USP2.</span></span> <span data-ttu-id="0e901-108">Avant d'effectuer cette tâche, veillez à lire les guides de tâche suivants : « Créer une comptabilité de contrôle de gestion, « Définir les unités de contrôle des coûts « et « Gérer la source de données pour la comptabilité de contrôle de gestion ».</span><span class="sxs-lookup"><span data-stu-id="0e901-108">Before you complete this task, make sure that you play the following task guides: "Create a cost accounting ledger," "Define cost control units," and "Manage data source for the cost accounting ledger."</span></span>

1. <span data-ttu-id="0e901-109">Accédez à Contrôle de gestion > Paramétrage de la comptabilité > Comptabilités de contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="0e901-109">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="0e901-110">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="0e901-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="0e901-111">Sélectionnez la comptabilité de contrôle de gestion que vous avez créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="0e901-111">Select the cost accounting ledger that you created earlier.</span></span>  
3. <span data-ttu-id="0e901-112">Cliquez sur Versions réelles.</span><span class="sxs-lookup"><span data-stu-id="0e901-112">Click Actual versions.</span></span>
4. <span data-ttu-id="0e901-113">Dans le volet Actions, cliquez sur Traitement des données source.</span><span class="sxs-lookup"><span data-stu-id="0e901-113">On the Action Pane, click Source data processing.</span></span>
5. <span data-ttu-id="0e901-114">Cliquez sur Journaux de transfert d'écritures de comptabilité.</span><span class="sxs-lookup"><span data-stu-id="0e901-114">Click General ledger entry transfer journals.</span></span>
6. <span data-ttu-id="0e901-115">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="0e901-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="0e901-116">Cliquez sur Entrées de journal.</span><span class="sxs-lookup"><span data-stu-id="0e901-116">Click Journal entries.</span></span>
8. <span data-ttu-id="0e901-117">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0e901-117">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="0e901-118">Cliquez sur Entrées de coût.</span><span class="sxs-lookup"><span data-stu-id="0e901-118">Click Cost entries.</span></span>
10. <span data-ttu-id="0e901-119">Cliquez sur Entrée source.</span><span class="sxs-lookup"><span data-stu-id="0e901-119">Click Source entry.</span></span>
11. <span data-ttu-id="0e901-120">Dans le volet Actions, cliquez sur Traitement des données source.</span><span class="sxs-lookup"><span data-stu-id="0e901-120">On the Action Pane, click Source data processing.</span></span>
12. <span data-ttu-id="0e901-121">Cliquez sur Comptabilité.</span><span class="sxs-lookup"><span data-stu-id="0e901-121">Click General ledger.</span></span>
13. <span data-ttu-id="0e901-122">Dans le champ Période de calendrier fiscal, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0e901-122">In the Fiscal calendar period field, enter or select a value.</span></span>
    * <span data-ttu-id="0e901-123">Pour cet exemple, sélectionnez Période fiscale 9 2017.</span><span class="sxs-lookup"><span data-stu-id="0e901-123">For this example, select Fiscal 2017 Period 9.</span></span>  
14. <span data-ttu-id="0e901-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0e901-124">Click OK.</span></span>

