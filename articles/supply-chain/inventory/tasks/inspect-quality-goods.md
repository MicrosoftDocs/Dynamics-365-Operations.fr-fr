---
title: Inspecter la qualité des marchandises
description: Cette procédure indique comment traiter un ordre de qualité.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9e9d750f116db62519ac7148f19bf62050430e9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "315427"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="fee8e-103">Inspecter la qualité des marchandises</span><span class="sxs-lookup"><span data-stu-id="fee8e-103">Inspect the quality of goods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fee8e-104">Cette procédure indique comment traiter un ordre de qualité.</span><span class="sxs-lookup"><span data-stu-id="fee8e-104">This procedure shows you how to process a quality order.</span></span> <span data-ttu-id="fee8e-105">Vous pouvez exécuter ce guide dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="fee8e-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="fee8e-106">Avant de commencer cet procédure d'exemple, vous devez confirmer la commande fournisseur 000016 et valider un accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="fee8e-106">Before you start this example procedure, you need to confirm purchase order “000016” and post a product receipt.</span></span> <span data-ttu-id="fee8e-107">Cette opération crée automatiquement un ordre de qualité.</span><span class="sxs-lookup"><span data-stu-id="fee8e-107">This will automatically create a quality order.</span></span> <span data-ttu-id="fee8e-108">Les inspections de qualité sont généralement effectuées par un commis au contrôle de la qualité.</span><span class="sxs-lookup"><span data-stu-id="fee8e-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="fee8e-109">Sélectionnez un ordre de qualité.</span><span class="sxs-lookup"><span data-stu-id="fee8e-109">Select a quality order</span></span>
1. <span data-ttu-id="fee8e-110">Allez dans Gestion des stocks > Tâches périodiques > Gestion de la qualité > Ordres de qualité.</span><span class="sxs-lookup"><span data-stu-id="fee8e-110">Go to Inventory management > Periodic tasks > Quality management > Quality orders.</span></span>
2. <span data-ttu-id="fee8e-111">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fee8e-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="fee8e-112">Sélectionnez l'ordre de qualité créé avant d'avoir commencé cette procédure.</span><span class="sxs-lookup"><span data-stu-id="fee8e-112">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="fee8e-113">Enregistrement des résultats de test</span><span class="sxs-lookup"><span data-stu-id="fee8e-113">Record test results</span></span>
1. <span data-ttu-id="fee8e-114">Cliquez sur Résultats.</span><span class="sxs-lookup"><span data-stu-id="fee8e-114">Click Results.</span></span>
2. <span data-ttu-id="fee8e-115">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="fee8e-115">Click Edit.</span></span>
3. <span data-ttu-id="fee8e-116">Entrez un nombre dans le champ Quantité du résultat.</span><span class="sxs-lookup"><span data-stu-id="fee8e-116">In the Result quantity field, enter a number.</span></span>
4. <span data-ttu-id="fee8e-117">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fee8e-117">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="fee8e-118">Dans le champ Résultat, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fee8e-118">In the Outcome field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="fee8e-119">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fee8e-119">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="fee8e-120">Dans cet exemple, le résultat est basé sur les résultats prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="fee8e-120">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="fee8e-121">Normalement vous devez enregistrer un résultat de test plus spécifique, par exemple une taille ou autre dimension.</span><span class="sxs-lookup"><span data-stu-id="fee8e-121">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
7. <span data-ttu-id="fee8e-122">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fee8e-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="fee8e-123">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fee8e-123">Click Save.</span></span>
9. <span data-ttu-id="fee8e-124">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fee8e-124">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="fee8e-125">Contrôler l'ordre de qualité</span><span class="sxs-lookup"><span data-stu-id="fee8e-125">Validate the quality order</span></span>
1. <span data-ttu-id="fee8e-126">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="fee8e-126">Click Validate.</span></span>
2. <span data-ttu-id="fee8e-127">Dans le champ Validé par, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fee8e-127">In the Validated by field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="fee8e-128">Sélectionnez l'utilisateur qui effectue l'inspection.</span><span class="sxs-lookup"><span data-stu-id="fee8e-128">Select the user performing the inspection.</span></span>  
3. <span data-ttu-id="fee8e-129">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fee8e-129">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="fee8e-130">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="fee8e-130">Click Select.</span></span>
5. <span data-ttu-id="fee8e-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fee8e-131">Click OK.</span></span>
6. <span data-ttu-id="fee8e-132">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fee8e-132">Close the page.</span></span>

