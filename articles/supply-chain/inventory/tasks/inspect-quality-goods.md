---
title: Inspecter la qualité des marchandises
description: Cette rubrique explique comment traiter un ordre de qualité.
author: perlynne
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 47e7156e5c57d5f983564cc966b4108f1180ff8d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825913"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="c0f20-103">Inspecter la qualité des marchandises</span><span class="sxs-lookup"><span data-stu-id="c0f20-103">Inspect the quality of goods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c0f20-104">Cette rubrique explique comment traiter un ordre de qualité.</span><span class="sxs-lookup"><span data-stu-id="c0f20-104">This topic explains how to process a quality order.</span></span> <span data-ttu-id="c0f20-105">Vous pouvez exécuter ce guide dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="c0f20-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="c0f20-106">Avant de commencer cet procédure d’exemple, vous devez confirmer la commande fournisseur « 000016 » et valider un accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="c0f20-106">Before you start this example procedure, you need to confirm purchase order "000016" and post a product receipt.</span></span> <span data-ttu-id="c0f20-107">Cette opération crée automatiquement un ordre de qualité.</span><span class="sxs-lookup"><span data-stu-id="c0f20-107">This will automatically create a quality order.</span></span> <span data-ttu-id="c0f20-108">Les inspections de qualité sont généralement effectuées par un commis au contrôle de la qualité.</span><span class="sxs-lookup"><span data-stu-id="c0f20-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="c0f20-109">Sélectionnez un ordre de qualité.</span><span class="sxs-lookup"><span data-stu-id="c0f20-109">Select a quality order</span></span>
1. <span data-ttu-id="c0f20-110">Dans le volet de navigation, accédez à **Modules > Gestion des stocks > Tâches périodiques > Gestion de la qualité > Ordres de qualité**.</span><span class="sxs-lookup"><span data-stu-id="c0f20-110">In the navigation pane, go to **Modules > Inventory management > Periodic tasks > Quality management > Quality orders**.</span></span>
2. <span data-ttu-id="c0f20-111">Sélectionnez l’ordre de qualité créé avant d’avoir commencé cette procédure.</span><span class="sxs-lookup"><span data-stu-id="c0f20-111">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="c0f20-112">Enregistrement des résultats de test</span><span class="sxs-lookup"><span data-stu-id="c0f20-112">Record test results</span></span>
1. <span data-ttu-id="c0f20-113">Sélectionnez **Résultats**.</span><span class="sxs-lookup"><span data-stu-id="c0f20-113">Select **Results**.</span></span>
2. <span data-ttu-id="c0f20-114">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="c0f20-114">Select **Edit**.</span></span>
3. <span data-ttu-id="c0f20-115">Dans le champ **Quantité du résultat**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="c0f20-115">In the **Result quantity** field, enter a number.</span></span>
4. <span data-ttu-id="c0f20-116">Dans le champ **Résultat**, sélectionnez l’enregistrement souhaité dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="c0f20-116">In the **Outcome** field, select the desired record in the drop-down menu.</span></span>  
- <span data-ttu-id="c0f20-117">Dans cet exemple, le résultat est basé sur les résultats prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="c0f20-117">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="c0f20-118">Normalement vous devez enregistrer un résultat de test plus spécifique, par exemple une taille ou autre dimension.</span><span class="sxs-lookup"><span data-stu-id="c0f20-118">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
5. <span data-ttu-id="c0f20-119">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c0f20-119">Select **Save**.</span></span>
6. <span data-ttu-id="c0f20-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c0f20-120">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="c0f20-121">Contrôler l’ordre de qualité</span><span class="sxs-lookup"><span data-stu-id="c0f20-121">Validate the quality order</span></span>
1. <span data-ttu-id="c0f20-122">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="c0f20-122">Select **Validate**.</span></span>
2. <span data-ttu-id="c0f20-123">Dans le champ **Validé par**, sélectionnez l’utilisateur effectuant l’inspection dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="c0f20-123">In the **Validated by** field, select the user performing the inspection from the drop-down menu.</span></span>  
3. <span data-ttu-id="c0f20-124">Cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="c0f20-124">Click **Select**.</span></span>
4. <span data-ttu-id="c0f20-125">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0f20-125">Select **OK**.</span></span>
5. <span data-ttu-id="c0f20-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c0f20-126">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]