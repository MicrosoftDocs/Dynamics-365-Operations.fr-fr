---
title: Inspecter la qualité des marchandises
description: Cette rubrique explique comment traiter des ordres de qualité.
author: perlynne
ms.date: 03/23/2021
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
ms.openlocfilehash: ec67e7864db12178c0f3cfe8b93d510a46e8a0d4
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956132"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="71c40-103">Inspecter la qualité des marchandises</span><span class="sxs-lookup"><span data-stu-id="71c40-103">Inspect the quality of goods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="71c40-104">Cette rubrique explique comment traiter des ordres de qualité.</span><span class="sxs-lookup"><span data-stu-id="71c40-104">This topic describes how to process quality orders.</span></span> <span data-ttu-id="71c40-105">Les inspections de qualité sont généralement réalisées par un adjoint au contrôle de la qualité.</span><span class="sxs-lookup"><span data-stu-id="71c40-105">Quality inspections are typically done by a quality clerk.</span></span>

<span data-ttu-id="71c40-106">Si les données de démonstration standard sont installées, vous pouvez les utiliser pour exécuter les procédures de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="71c40-106">If the standard demo data is installed, you can use it to complete the procedures in this topic.</span></span> <span data-ttu-id="71c40-107">Pour utiliser les données de démonstration, vous devez sélectionner l’entité juridique *USMF* avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="71c40-107">To use the demo data, select the *USMF* legal entity before you begin.</span></span> <span data-ttu-id="71c40-108">Vous devez ensuite confirmer le bon de commande *000016* et afficher un accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="71c40-108">You must then confirm purchase order *000016* and post a product receipt.</span></span> <span data-ttu-id="71c40-109">Un ordre de qualité est généré automatiquement.</span><span class="sxs-lookup"><span data-stu-id="71c40-109">A quality order is automatically generated.</span></span>

## <a name="step-1-select-a-quality-order"></a><span data-ttu-id="71c40-110">Étape 1: Sélectionner un ordre de qualité</span><span class="sxs-lookup"><span data-stu-id="71c40-110">Step 1: Select a quality order</span></span>

<span data-ttu-id="71c40-111">Pour sélectionner un ordre de qualité, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="71c40-111">To select a quality order, follow these steps.</span></span>

1. <span data-ttu-id="71c40-112">Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Ordres de qualité**.</span><span class="sxs-lookup"><span data-stu-id="71c40-112">Go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>
1. <span data-ttu-id="71c40-113">Sélectionnez l’ordre de qualité généré avant d’avoir commencé cette procédure.</span><span class="sxs-lookup"><span data-stu-id="71c40-113">Select the quality order that was generated before you started this procedure.</span></span>

## <a name="step-2-record-test-results"></a><span data-ttu-id="71c40-114">Étape 2 : Enregistrer les résultats de test</span><span class="sxs-lookup"><span data-stu-id="71c40-114">Step 2: Record test results</span></span>

<span data-ttu-id="71c40-115">Pour enregistrer les résultats de test, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="71c40-115">To record test results, follow these steps.</span></span>

1. <span data-ttu-id="71c40-116">Sélectionnez **Résultats**.</span><span class="sxs-lookup"><span data-stu-id="71c40-116">Select **Results**.</span></span>
1. <span data-ttu-id="71c40-117">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="71c40-117">Select **Edit**.</span></span>
1. <span data-ttu-id="71c40-118">Dans le champ **Quantité du résultat**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="71c40-118">In the **Result quantity** field, enter a number.</span></span>
1. <span data-ttu-id="71c40-119">Sélectionnez le dossier souhaité dans le champ **Résultat**.</span><span class="sxs-lookup"><span data-stu-id="71c40-119">In the **Outcome** field, select the desired record.</span></span> <span data-ttu-id="71c40-120">Dans cet exemple, le résultat est basé sur un résultat prédéfini.</span><span class="sxs-lookup"><span data-stu-id="71c40-120">In this example, the result is based on a predefined outcome.</span></span> <span data-ttu-id="71c40-121">Vous devez normalement enregistrer un résultat de test plus spécifique, par exemple une taille ou autre dimension.</span><span class="sxs-lookup"><span data-stu-id="71c40-121">Usually, you will record a more specific test result, such as a size or other dimension.</span></span>
1. <span data-ttu-id="71c40-122">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="71c40-122">Select **Save**.</span></span>
1. <span data-ttu-id="71c40-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="71c40-123">Close the page.</span></span>

## <a name="step-3-validate-the-quality-order"></a><span data-ttu-id="71c40-124">Étape 3 : Contrôler l’ordre de qualité</span><span class="sxs-lookup"><span data-stu-id="71c40-124">Step 3: Validate the quality order</span></span>

<span data-ttu-id="71c40-125">Pour contrôler l'ordre de qualité, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="71c40-125">To validate the quality order, follow these steps.</span></span>

1. <span data-ttu-id="71c40-126">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="71c40-126">Select **Validate**.</span></span>
1. <span data-ttu-id="71c40-127">Dans le champ **Validé par**, sélectionnez l'utilisateur qui effectue l'inspection.</span><span class="sxs-lookup"><span data-stu-id="71c40-127">In the **Validated by** field, select the user who is doing the inspection.</span></span>
1. <span data-ttu-id="71c40-128">Cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="71c40-128">Select **Select**.</span></span>
1. <span data-ttu-id="71c40-129">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="71c40-129">Select **OK**.</span></span>
1. <span data-ttu-id="71c40-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="71c40-130">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
