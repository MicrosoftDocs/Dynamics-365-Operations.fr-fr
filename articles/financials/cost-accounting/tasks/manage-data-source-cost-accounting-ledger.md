---
title: Gérer une source de données pour la comptabilité de contrôle de gestion
description: Utilisez cette procédure pour gérer la source de données pour une comptabilité de contrôle de gestion.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f53101d73bc69199fafb00de0fa1759d59ea4ce8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "319314"
---
# <a name="manage-a-data-source-for-the-cost-accounting-ledger"></a><span data-ttu-id="5d8c3-103">Gérer une source de données pour la comptabilité de contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="5d8c3-103">Manage a data source for the cost accounting ledger</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5d8c3-104">Utilisez cette procédure pour gérer la source de données pour une comptabilité de contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-104">Use this procedure to manage the general ledger data source for a cost accounting ledger.</span></span> <span data-ttu-id="5d8c3-105">Avant d'effectuer cette tâche, veillez à lire les guides de tâche « Créer une comptabilité de contrôle de gestion » et « Définir les unités de contrôle des coûts ».</span><span class="sxs-lookup"><span data-stu-id="5d8c3-105">Before you complete this task, make sure that you play the "Create a cost accounting ledger" and "Define cost control units" task guides.</span></span> <span data-ttu-id="5d8c3-106">Cet enregistrement utilise la société fictive USP2.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="5d8c3-107">Accédez à Contrôle de gestion > Paramétrage de la comptabilité > Comptabilités de contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-107">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="5d8c3-108">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="5d8c3-109">Cliquez sur Versions réelles.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-109">Click Actual versions.</span></span>
4. <span data-ttu-id="5d8c3-110">Dans le volet Actions, cliquez sur Gérer.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-110">On the Action Pane, click Manage.</span></span>
5. <span data-ttu-id="5d8c3-111">Cliquez sur Comptabilité.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-111">Click General ledger.</span></span>
6. <span data-ttu-id="5d8c3-112">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-112">Click New.</span></span>
7. <span data-ttu-id="5d8c3-113">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="5d8c3-114">Dans le champ Fournisseur de données, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-114">In the Data provider field, enter or select a value.</span></span>
    * <span data-ttu-id="5d8c3-115">Pour cet exemple, sélectionnez Dynamics 365 for Finance and Operations - Écritures de comptabilité.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-115">For this example, select Dynamics 365 for Finance and Operations - General ledger entries.</span></span>  
9. <span data-ttu-id="5d8c3-116">Dans le champ Dimension d'élément de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-116">In the Cost element dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="5d8c3-117">Pour cet exemple, sélectionnez Éléments de coût.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-117">For this example, select Cost elements.</span></span>  
10. <span data-ttu-id="5d8c3-118">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-118">Click Save.</span></span>
11. <span data-ttu-id="5d8c3-119">Cliquez sur Configurer le fournisseur de données.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-119">Click Configure data provider.</span></span>
12. <span data-ttu-id="5d8c3-120">Dans le champ Entité juridique, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-120">In the Legal entity field, enter or select a value.</span></span>
    * <span data-ttu-id="5d8c3-121">Pour cet exemple, sélectionnez USP2.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-121">For this example, select USP2.</span></span>  
13. <span data-ttu-id="5d8c3-122">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-122">Click New.</span></span>
14. <span data-ttu-id="5d8c3-123">Dans le champ Couche de validation, sélectionnez Actuel.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-123">In the Posting layer field, select Current.</span></span>
15. <span data-ttu-id="5d8c3-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="5d8c3-124">Click OK.</span></span>

