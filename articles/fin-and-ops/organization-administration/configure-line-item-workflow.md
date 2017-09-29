---
title: Configuration d'un workflow pour ligne
description: "Cette rubrique explique comment configurer un élément de workflow pour ligne."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: d888bf4285a27369b197ed66e5975cc806c640d3
ms.contentlocale: fr-fr
ms.lasthandoff: 07/18/2017

---

# <a name="configure-a-line-item-workflow"></a><span data-ttu-id="d62c3-103">Configuration d'un workflow pour ligne</span><span class="sxs-lookup"><span data-stu-id="d62c3-103">Configure a line-item workflow</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d62c3-104">Cette rubrique explique comment configurer un élément de workflow pour ligne.</span><span class="sxs-lookup"><span data-stu-id="d62c3-104">This topic explains how to configure a line-item workflow element.</span></span>

<span data-ttu-id="d62c3-105">Pour configurer un élément de workflow pour ligne, dans l'éditeur de workflow, cliquez avec le bouton droit sur l'élément, puis cliquez sur **Propriétés** pour ouvrir la page **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d62c3-105">To configure a line-item workflow element, in the workflow editor, right-click the element, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="d62c3-106">Utilisez ensuite les procédures suivantes permettent de configurer les propriétés de l'élément de workflow pour ligne.</span><span class="sxs-lookup"><span data-stu-id="d62c3-106">Then use the following procedures to configure the properties of the line-item workflow element.</span></span>

## <a name="name-the-lineitem-workflow-element"></a><span data-ttu-id="d62c3-107">Saisie d'un nom pour l'élément de workflow pour ligne</span><span class="sxs-lookup"><span data-stu-id="d62c3-107">Name the lineitem workflow element</span></span>
<span data-ttu-id="d62c3-108">Procédez comme suit pour entrer un nom pour l'élément de workflow pour ligne.</span><span class="sxs-lookup"><span data-stu-id="d62c3-108">Follow these steps to enter a name for the line-item workflow element.</span></span>

1.  <span data-ttu-id="d62c3-109">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="d62c3-109">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="d62c3-110">Dans le champ **Nom**, entrez un nom unique pour l'élément de workflow pour ligne.</span><span class="sxs-lookup"><span data-stu-id="d62c3-110">In the **Name** field, enter a unique name for the line-item workflow element.</span></span>

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a><span data-ttu-id="d62c3-111">Indication si le même workflow est utilisé pour traiter toutes les lignes</span><span class="sxs-lookup"><span data-stu-id="d62c3-111">Specify whether the same workflow is used to process all line items</span></span>
<span data-ttu-id="d62c3-112">Procédez comme suit pour indiquer si le même workflow est utilisé pour traiter toutes les lignes d'un document.</span><span class="sxs-lookup"><span data-stu-id="d62c3-112">Follow these steps to specify whether the same workflow is used to process all the line items on a document.</span></span>

1.  <span data-ttu-id="d62c3-113">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="d62c3-113">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="d62c3-114">Si le même workflow traite tous les articles de lignes d'un document, cliquez sur **Invoquer un seul workflow pour tous les articles de ligne**.</span><span class="sxs-lookup"><span data-stu-id="d62c3-114">If the same workflow should process all the line items on a document, click **Invoke a single workflow for all line-items**.</span></span> <span data-ttu-id="d62c3-115">Sélectionnez ensuite le workflow à utiliser pour traiter les lignes.</span><span class="sxs-lookup"><span data-stu-id="d62c3-115">Then select the workflow to use to process the line items.</span></span>
3.  <span data-ttu-id="d62c3-116">Si un workflow donné doit traiter les articles de lignes qui remplissent un ensemble spécifique de conditions, cliquez sur **Invoquer un workflow pour chaque article de ligne**.</span><span class="sxs-lookup"><span data-stu-id="d62c3-116">If a specific workflow should process line items that meet a specific set of conditions, click **Invoke a workflow for each line-item**.</span></span> <span data-ttu-id="d62c3-117">Puis procédez comme suit pour définir les conditions :</span><span class="sxs-lookup"><span data-stu-id="d62c3-117">Then follow these steps to define the set of conditions:</span></span>
    1.  <span data-ttu-id="d62c3-118">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="d62c3-118">Click **Add**.</span></span>
    2.  <span data-ttu-id="d62c3-119">Sélectionnez la condition dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="d62c3-119">Select the condition in the table.</span></span>
    3.  <span data-ttu-id="d62c3-120">Sous l'onglet **Nom de la condition**, entrez un nom pour l'ensemble de conditions que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="d62c3-120">On the **Condition name** tab, enter a name for the set of conditions that you're defining.</span></span>
    4.  <span data-ttu-id="d62c3-121">Cliquez sur **Ajouter une condition** pour entrer une condition.</span><span class="sxs-lookup"><span data-stu-id="d62c3-121">Click **Add condition** to enter a condition.</span></span>
    5.  <span data-ttu-id="d62c3-122">Entrez des conditions supplémentaires, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="d62c3-122">Enter any additional conditions that are required.</span></span>
    6.  <span data-ttu-id="d62c3-123">Pour vérifier que l'ensemble de conditions que vous avez entrées est correctement paramétré, cliquez sur **Tester**.</span><span class="sxs-lookup"><span data-stu-id="d62c3-123">To verify that the set of conditions that you entered is configured correctly, click **Test**.</span></span> <span data-ttu-id="d62c3-124">Sur la page **Condition de workflow de test**, sélectionnez un enregistrement dans la zone **Contrôler la condition**, puis cliquez sur **Tester**.</span><span class="sxs-lookup"><span data-stu-id="d62c3-124">On the **Test workflow condition** page, in the **Validate condition** area, select a record, and then click **Test**.</span></span> <span data-ttu-id="d62c3-125">Le système évalue l'enregistrement pour déterminer s'il répond aux conditions que vous avez spécifiées.</span><span class="sxs-lookup"><span data-stu-id="d62c3-125">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span> <span data-ttu-id="d62c3-126">Cliquez sur **OK** ou sur **Annuler** pour revenir à la page **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d62c3-126">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

    <span data-ttu-id="d62c3-127">Sous l'onglet **Workflow**, sélectionnez le workflow à utiliser pour traiter les articles de lignes qui remplissent l'ensemble de conditions que vous avez définies.</span><span class="sxs-lookup"><span data-stu-id="d62c3-127">On the **Workflow** tab, select the workflow select the workflow to use to process line items that meet the set of conditions that you defined.</span></span>





