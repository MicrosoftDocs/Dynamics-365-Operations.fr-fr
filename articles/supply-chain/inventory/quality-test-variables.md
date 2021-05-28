---
title: Variables de test de gestion de la qualité
description: Cette rubrique décrit comment créer des variables de test, afin que plusieurs tests qualitatifs puissent être utilisés avec des ordres de qualité dans Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b5102d09f5762a390d6fd3aadafcb2ed23820982
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021706"
---
# <a name="quality-management-test-variables"></a><span data-ttu-id="873e1-103">Variables de test de gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="873e1-103">Quality management test variables</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="873e1-104">Cette rubrique décrit comment créer des variables de test, afin que plusieurs tests qualitatifs puissent être utilisés avec des ordres de qualité dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="873e1-104">This topic describes how to create test variables that can be used for qualitative tests on quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="873e1-105">Vous devez définir une variable de test et ses résultats éventuels pour chaque test qualitatif défini sur la page **Tests**.</span><span class="sxs-lookup"><span data-stu-id="873e1-105">For every qualitative test that is defined on the **Tests** page, you must define a test variable and its possible outcomes (results).</span></span> <span data-ttu-id="873e1-106">(Pour les tests qualitatifs, le champ **Type** de la page **Tests** est défini sur *Option*.)</span><span class="sxs-lookup"><span data-stu-id="873e1-106">(For qualitative tests, the **Type** field on the **Tests** page is set to *Option*.)</span></span>

<span data-ttu-id="873e1-107">La page **Variables de test** permet de paramétrer, de modifier et d’afficher les résultats possibles pour une variable de test associée à un test qualitatif.</span><span class="sxs-lookup"><span data-stu-id="873e1-107">You use the **Test variables** page to set up, edit, and view the possible outcomes for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="873e1-108">Pour chaque résultat, vous devez attribuer un statut de *Réussite* ou d'*Échec* pour indiquer si le test a réussi ou échoué lorsque ce résultat est sélectionné comme résultat de test.</span><span class="sxs-lookup"><span data-stu-id="873e1-108">For each outcome, you assign an outcome status of either *Pass* or *Fail* to indicate whether the test is passed or failed when that outcome is selected as a test result.</span></span> <span data-ttu-id="873e1-109">La page **Groupes de tests** permet d'affecter une variable de test et un résultat par défaut à un test qualificatif spécifique.</span><span class="sxs-lookup"><span data-stu-id="873e1-109">You use the **Test groups** page to assign a test variable and a default outcome for it to an individual qualitative test.</span></span>

<span data-ttu-id="873e1-110">Pour chaque variable de test, nous vous recommandons de définir au moins deux résultats : un dont le statut de résultat est *Réussite* et un qui a un statut de résultat *Échec*.</span><span class="sxs-lookup"><span data-stu-id="873e1-110">For every test variable, we recommend that you define at least two outcomes: one that has an outcome status of *Pass* and one that has an outcome status of *Fail*.</span></span> <span data-ttu-id="873e1-111">Il n'y a pas de limite au nombre total de variables ou de résultats qui peuvent être définis.</span><span class="sxs-lookup"><span data-stu-id="873e1-111">There is no limit on the total number of variables or outcomes that can be defined.</span></span> <span data-ttu-id="873e1-112">De plus, plusieurs tests peuvent utiliser les mêmes variables de test pour enregistrer les résultats.</span><span class="sxs-lookup"><span data-stu-id="873e1-112">Additionally, multiple tests can use the same test variables to record results.</span></span>

## <a name="examples-of-test-variables"></a><span data-ttu-id="873e1-113">Exemples de variables de test</span><span class="sxs-lookup"><span data-stu-id="873e1-113">Examples of test variables</span></span>

### <a name="example-1"></a><span data-ttu-id="873e1-114">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="873e1-114">Example 1</span></span>

<span data-ttu-id="873e1-115">Une entreprise de fabrication effectue deux tests sur des produits manufacturés.</span><span class="sxs-lookup"><span data-stu-id="873e1-115">A manufacturing company performs two tests on manufactured materials.</span></span> <span data-ttu-id="873e1-116">Dans un test, le niveau de pH est associé à une bande de couleur.</span><span class="sxs-lookup"><span data-stu-id="873e1-116">In one test, the pH level is associated with a color strip.</span></span> <span data-ttu-id="873e1-117">Les niveaux de pH acceptables sont dans des couleurs plus claires et les niveaux de pH inacceptables sont dans des couleurs plus foncées.</span><span class="sxs-lookup"><span data-stu-id="873e1-117">Acceptable pH levels are in lighter colors, and unacceptable pH levels are in darker colors.</span></span> <span data-ttu-id="873e1-118">Dans un autre test, plusieurs inspections visuelles sont effectuées et les responsables qualité utilisent leur jugement pour déterminer si l'article réussit ou échoue à l'inspection visuelle.</span><span class="sxs-lookup"><span data-stu-id="873e1-118">In another test, multiple visual inspections are performed, and quality workers use their judgement to determine whether the item passes or fails the visual inspection.</span></span>

### <a name="example-2"></a><span data-ttu-id="873e1-119">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="873e1-119">Example 2</span></span>

<span data-ttu-id="873e1-120">Une société de fabrication de biscuits utilise un test d’inspection pour le produit fini.</span><span class="sxs-lookup"><span data-stu-id="873e1-120">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="873e1-121">Ce test d’inspection comporte plusieurs variables.</span><span class="sxs-lookup"><span data-stu-id="873e1-121">This inspection test has several variables.</span></span> <span data-ttu-id="873e1-122">L’une des variables est le goût et les résultats possibles pour cette variable sont bon et mauvais.</span><span class="sxs-lookup"><span data-stu-id="873e1-122">One variable is taste, and the possible outcomes for it are good and bad.</span></span> <span data-ttu-id="873e1-123">Une deuxième variable est la couleur et les résultats possibles sont trop foncé, trop clair et correct.</span><span class="sxs-lookup"><span data-stu-id="873e1-123">A second variable is color, and the possible outcomes for it are too dark, too light, and correct.</span></span>

## <a name="create-a-test-variable"></a><span data-ttu-id="873e1-124">Créer une variable de test</span><span class="sxs-lookup"><span data-stu-id="873e1-124">Create a test variable</span></span>

<span data-ttu-id="873e1-125">Pour créer une variable de test, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="873e1-125">Follow these steps to create a test variable.</span></span>

1. <span data-ttu-id="873e1-126">Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Variables de test**.</span><span class="sxs-lookup"><span data-stu-id="873e1-126">Go to **Inventory management \> Setup \> Quality control \> Test variables**.</span></span>
1. <span data-ttu-id="873e1-127">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="873e1-127">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="873e1-128">Définissez ensuite les champs suivants pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="873e1-128">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="873e1-129">**Variable** - Entrez un ID ou un nom unique pour la variable.</span><span class="sxs-lookup"><span data-stu-id="873e1-129">**Variable** – Enter a unique ID or name for the variable.</span></span>
    - <span data-ttu-id="873e1-130">**Description** - Entrez une description détaillée de la variable.</span><span class="sxs-lookup"><span data-stu-id="873e1-130">**Description** – Enter a detailed description of the variable.</span></span>

1. <span data-ttu-id="873e1-131">Alors que la nouvelle ligne est toujours sélectionnée, sélectionnez **Résultats** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="873e1-131">While the new row is still selected, select **Outcomes** on the Action Pane.</span></span>
1. <span data-ttu-id="873e1-132">Sur la page **Résultats de la variable de test**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="873e1-132">On the **Test variable outcomes** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="873e1-133">Définissez ensuite les champs suivants pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="873e1-133">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="873e1-134">**Résultat** - Entrez un ID ou un nom unique pour le résultat.</span><span class="sxs-lookup"><span data-stu-id="873e1-134">**Outcome** – Enter a unique ID or name for the outcome.</span></span>
    - <span data-ttu-id="873e1-135">**Description** - Entrez une description détaillée du résultat.</span><span class="sxs-lookup"><span data-stu-id="873e1-135">**Description** – Enter a detailed description of the outcome.</span></span>
    - <span data-ttu-id="873e1-136">**Statut du résultat** – Sélectionnez *Réussite* ou *Échec* pour indiquer si le test a réussi ou échoué lorsque ce résultat est sélectionné comme résultat de test.</span><span class="sxs-lookup"><span data-stu-id="873e1-136">**Outcome status** – Select either *Pass* or *Fail* to indicate whether the test is passed or failed when the outcome is selected as a test result.</span></span>

1. <span data-ttu-id="873e1-137">Répétez l'étape précédente pour chaque résultat supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="873e1-137">Repeat the previous step for each additional outcome.</span></span> <span data-ttu-id="873e1-138">Assurez-vous qu'au moins un résultat a un statut de résultat *Réussite* et au moins un a un statut de résultat *Échec*.</span><span class="sxs-lookup"><span data-stu-id="873e1-138">Make sure that at least one outcome has an outcome status of *Pass* and at least one has an outcome status of *Fail*.</span></span>
1. <span data-ttu-id="873e1-139">Fermez les pages.</span><span class="sxs-lookup"><span data-stu-id="873e1-139">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="873e1-140">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="873e1-140">Additional resources</span></span>

- [<span data-ttu-id="873e1-141">Instruments de test de gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="873e1-141">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="873e1-142">Tests de gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="873e1-142">Quality management tests</span></span>](quality-tests.md)
- [<span data-ttu-id="873e1-143">Groupes de tests de gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="873e1-143">Quality management test groups</span></span>](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
