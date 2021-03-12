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
ms.search.form: CAMAXGeneralLedgerEntryProviderConfiguration
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7246d42b42404f0f1215bbf14b8ad168fe12691c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990715"
---
# <a name="manage-a-data-source-for-the-cost-accounting-ledger"></a><span data-ttu-id="e4668-103">Gérer une source de données pour la comptabilité de contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="e4668-103">Manage a data source for the cost accounting ledger</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e4668-104">Utilisez cette procédure pour gérer la source de données pour une comptabilité de contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="e4668-104">Use this procedure to manage the general ledger data source for a cost accounting ledger.</span></span> <span data-ttu-id="e4668-105">Avant d’effectuer cette tâche, veillez à lire les guides de tâche « Créer une comptabilité de contrôle de gestion » et « Définir les unités de contrôle des coûts ».</span><span class="sxs-lookup"><span data-stu-id="e4668-105">Before you complete this task, make sure that you play the "Create a cost accounting ledger" and "Define cost control units" task guides.</span></span> <span data-ttu-id="e4668-106">Cet enregistrement utilise la société fictive USP2.</span><span class="sxs-lookup"><span data-stu-id="e4668-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="e4668-107">Accédez à Contrôle de gestion > Paramétrage de la comptabilité > Comptabilités de contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="e4668-107">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="e4668-108">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e4668-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="e4668-109">Cliquez sur Versions réelles.</span><span class="sxs-lookup"><span data-stu-id="e4668-109">Click Actual versions.</span></span>
4. <span data-ttu-id="e4668-110">Dans le volet Actions, cliquez sur Gérer.</span><span class="sxs-lookup"><span data-stu-id="e4668-110">On the Action Pane, click Manage.</span></span>
5. <span data-ttu-id="e4668-111">Cliquez sur Comptabilité.</span><span class="sxs-lookup"><span data-stu-id="e4668-111">Click General ledger.</span></span>
6. <span data-ttu-id="e4668-112">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e4668-112">Click New.</span></span>
7. <span data-ttu-id="e4668-113">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e4668-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="e4668-114">Dans le champ Fournisseur de données, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e4668-114">In the Data provider field, enter or select a value.</span></span>
    * <span data-ttu-id="e4668-115">Pour cet exemple, sélectionnez Dynamics 365 Finance - Écritures de comptabilité.</span><span class="sxs-lookup"><span data-stu-id="e4668-115">For this example, select Dynamics 365 Finance - General ledger entries.</span></span>  
9. <span data-ttu-id="e4668-116">Dans le champ Dimension d’élément de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e4668-116">In the Cost element dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="e4668-117">Pour cet exemple, sélectionnez Éléments de coût.</span><span class="sxs-lookup"><span data-stu-id="e4668-117">For this example, select Cost elements.</span></span>  
10. <span data-ttu-id="e4668-118">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e4668-118">Click Save.</span></span>
11. <span data-ttu-id="e4668-119">Cliquez sur Configurer le fournisseur de données.</span><span class="sxs-lookup"><span data-stu-id="e4668-119">Click Configure data provider.</span></span>
12. <span data-ttu-id="e4668-120">Dans le champ Entité juridique, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e4668-120">In the Legal entity field, enter or select a value.</span></span>
    * <span data-ttu-id="e4668-121">Pour cet exemple, sélectionnez USP2.</span><span class="sxs-lookup"><span data-stu-id="e4668-121">For this example, select USP2.</span></span>  
13. <span data-ttu-id="e4668-122">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e4668-122">Click New.</span></span>
14. <span data-ttu-id="e4668-123">Dans le champ Couche de validation, sélectionnez Actuel.</span><span class="sxs-lookup"><span data-stu-id="e4668-123">In the Posting layer field, select Current.</span></span>
15. <span data-ttu-id="e4668-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e4668-124">Click OK.</span></span>

