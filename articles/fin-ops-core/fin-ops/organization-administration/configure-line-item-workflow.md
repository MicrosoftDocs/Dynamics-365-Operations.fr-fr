---
title: Configuration des workflows pour ligne
description: Cette rubrique explique comment configurer un élément de workflow pour ligne.
author: ChrisGarty
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c19693151399fc02ea9562757af7fc24124c9b6c
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798827"
---
# <a name="configure-line-item-workflows"></a><span data-ttu-id="ea61c-103">Configuration des workflows pour ligne</span><span class="sxs-lookup"><span data-stu-id="ea61c-103">Configure line-item workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ea61c-104">Cette rubrique explique comment configurer un élément de workflow pour ligne.</span><span class="sxs-lookup"><span data-stu-id="ea61c-104">This topic explains how to configure a line-item workflow element.</span></span>

<span data-ttu-id="ea61c-105">Pour configurer un élément de workflow pour ligne, dans l’éditeur de workflow, cliquez avec le bouton droit sur l’élément, puis cliquez sur **Propriétés** pour ouvrir la page **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ea61c-105">To configure a line-item workflow element, in the workflow editor, right-click the element, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="ea61c-106">Utilisez ensuite les procédures suivantes permettent de configurer les propriétés de l’élément de workflow pour ligne.</span><span class="sxs-lookup"><span data-stu-id="ea61c-106">Then use the following procedures to configure the properties of the line-item workflow element.</span></span>

## <a name="name-the-line-item-workflow-element"></a><span data-ttu-id="ea61c-107">Saisie d’un nom pour l’élément de workflow pour ligne</span><span class="sxs-lookup"><span data-stu-id="ea61c-107">Name the line-item workflow element</span></span>

<span data-ttu-id="ea61c-108">Procédez comme suit pour entrer un nom pour l’élément de workflow pour ligne.</span><span class="sxs-lookup"><span data-stu-id="ea61c-108">Follow these steps to enter a name for the line-item workflow element.</span></span>

1. <span data-ttu-id="ea61c-109">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="ea61c-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="ea61c-110">Dans le champ **Nom**, entrez un nom unique pour l’élément de workflow pour ligne.</span><span class="sxs-lookup"><span data-stu-id="ea61c-110">In the **Name** field, enter a unique name for the line-item workflow element.</span></span>

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a><span data-ttu-id="ea61c-111">Indication si le même workflow est utilisé pour traiter toutes les lignes</span><span class="sxs-lookup"><span data-stu-id="ea61c-111">Specify whether the same workflow is used to process all line items</span></span>

<span data-ttu-id="ea61c-112">Procédez comme suit pour indiquer si le même workflow est utilisé pour traiter toutes les lignes d’un document.</span><span class="sxs-lookup"><span data-stu-id="ea61c-112">Follow these steps to specify whether the same workflow is used to process all the line items on a document.</span></span>

1. <span data-ttu-id="ea61c-113">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="ea61c-113">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="ea61c-114">Si le même workflow traite tous les articles de lignes d’un document, cliquez sur **Invoquer un seul workflow pour tous les articles de ligne**.</span><span class="sxs-lookup"><span data-stu-id="ea61c-114">If the same workflow should process all the line items on a document, click **Invoke a single workflow for all line-items**.</span></span> <span data-ttu-id="ea61c-115">Sélectionnez ensuite le workflow à utiliser pour traiter les lignes.</span><span class="sxs-lookup"><span data-stu-id="ea61c-115">Then select the workflow to use to process the line items.</span></span>
3. <span data-ttu-id="ea61c-116">Si un workflow donné doit traiter les articles de lignes qui remplissent un ensemble spécifique de conditions, cliquez sur **Invoquer un workflow pour chaque article de ligne**.</span><span class="sxs-lookup"><span data-stu-id="ea61c-116">If a specific workflow should process line items that meet a specific set of conditions, click **Invoke a workflow for each line-item**.</span></span> <span data-ttu-id="ea61c-117">Puis procédez comme suit pour définir les conditions :</span><span class="sxs-lookup"><span data-stu-id="ea61c-117">Then follow these steps to define the set of conditions:</span></span>

    1. <span data-ttu-id="ea61c-118">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ea61c-118">Click **Add**.</span></span>
    2. <span data-ttu-id="ea61c-119">Sélectionnez la condition dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="ea61c-119">Select the condition in the table.</span></span>
    3. <span data-ttu-id="ea61c-120">Sous l’onglet **Nom de la condition**, entrez un nom pour l’ensemble de conditions que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="ea61c-120">On the **Condition name** tab, enter a name for the set of conditions that you're defining.</span></span>
    4. <span data-ttu-id="ea61c-121">Cliquez sur **Ajouter une condition** pour entrer une condition.</span><span class="sxs-lookup"><span data-stu-id="ea61c-121">Click **Add condition** to enter a condition.</span></span>
    5. <span data-ttu-id="ea61c-122">Entrez des conditions supplémentaires, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="ea61c-122">Enter any additional conditions that are required.</span></span>
    6. <span data-ttu-id="ea61c-123">Pour vérifier que l’ensemble de conditions que vous avez entrées est correctement paramétré, cliquez sur **Tester**.</span><span class="sxs-lookup"><span data-stu-id="ea61c-123">To verify that the set of conditions that you entered is configured correctly, click **Test**.</span></span> <span data-ttu-id="ea61c-124">Sur la page **Condition de workflow de test**, sélectionnez un enregistrement dans la zone **Contrôler la condition**, puis cliquez sur **Tester**.</span><span class="sxs-lookup"><span data-stu-id="ea61c-124">On the **Test workflow condition** page, in the **Validate condition** area, select a record, and then click **Test**.</span></span> <span data-ttu-id="ea61c-125">Le système évalue l’enregistrement pour déterminer s’il répond aux conditions que vous avez spécifiées.</span><span class="sxs-lookup"><span data-stu-id="ea61c-125">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span> <span data-ttu-id="ea61c-126">Cliquez sur **OK** ou sur **Annuler** pour revenir à la page **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ea61c-126">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

    <span data-ttu-id="ea61c-127">Sous l’onglet **Workflow**, sélectionnez le workflow à utiliser pour traiter les articles de lignes qui remplissent l’ensemble de conditions que vous avez définies.</span><span class="sxs-lookup"><span data-stu-id="ea61c-127">On the **Workflow** tab, select the workflow select the workflow to use to process line items that meet the set of conditions that you defined.</span></span>
