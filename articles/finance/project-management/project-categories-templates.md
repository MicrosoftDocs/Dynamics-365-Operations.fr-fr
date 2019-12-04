---
title: Synchroniser les catégories de dépense de projet entre Finance and Operations et Project Service Automation
description: Cette rubrique décrit les modèles et les tâches sous-jacentes utilisés pour synchroniser les catégories de dépense du projet entre Microsoft Dynamics 365 Finance et Dynamics 365 Project Service Automation.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 7b0b3721c3b0755218c834d2bf77ec976be3bdcc
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770310"
---
# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="2305f-103">Synchroniser les catégories de dépense de projet entre Finance and Operations et Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="2305f-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2305f-104">Cette rubrique décrit les modèles et les tâches sous-jacentes utilisés pour synchroniser les catégories de dépense du projet entre Dynamics 365 Finance et Dynamics 365 Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="2305f-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Dynamics 365 Finance and Dynamics 365 Project Service Automation.</span></span>

> [!NOTE]
> - <span data-ttu-id="2305f-105">L'intégration des tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et le verrouillage des fonctionnalités sont disponibles dans la version 8.0.</span><span class="sxs-lookup"><span data-stu-id="2305f-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in version 8.0.</span></span>
> - <span data-ttu-id="2305f-106">L'intégration des chiffres réels est disponible dans version 8.0.1 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="2305f-106">Actuals integration is available in version 8.0.1 or later.</span></span>
> - <span data-ttu-id="2305f-107">Si vous utilisez Enterprise edition 7.3.0, après avoir installé KB 4132657 et KB 4132660, vous pourrez utiliser les modèles pour intégrer les tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et les transactions réelles, ainsi que pour configurer le verrouillage des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="2305f-107">If you're using Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="2305f-108">Si vous devez réinitialiser les répartitions comptables, nous vous recommandons d'installer également KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="2305f-108">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance"></a><span data-ttu-id="2305f-109">Flux de données pour Project Service Automation et Finance</span><span class="sxs-lookup"><span data-stu-id="2305f-109">Data flow for Project Service Automation and Finance</span></span>

<span data-ttu-id="2305f-110">La solution d'intégration de Project Service Automation avec Finance utilise la fonction Intégration des données pour synchroniser les données entre les instances de Project Service Automation et de Finance.</span><span class="sxs-lookup"><span data-stu-id="2305f-110">The Project Service Automation and Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance.</span></span> <span data-ttu-id="2305f-111">Les modèles d'intégration disponibles avec la fonction Intégration des données activent le flux de données sur les catégories de transaction de dépense du projet entre Finance et Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="2305f-111">The integration templates that are available with the Data integration feature enable the flow of data about project expense transaction categories between Finance and Project Service Automation.</span></span>

<span data-ttu-id="2305f-112">Si les catégories de dépense de projet sont gérées dans Finance, le flux d'intégration s'effectue d'abord de Finance vers Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="2305f-112">If the project expense categories are mastered in Finance, the integration flow is first from Finance to Project Service Automation.</span></span> <span data-ttu-id="2305f-113">Les ID d'intégration des catégories de dépenses du projet sont ensuite mis à jour par la synchronisation de Project Service Automation vers Finance.</span><span class="sxs-lookup"><span data-stu-id="2305f-113">The integration IDs of the project expense categories are then updated through synchronization from Project Service Automation to Finance.</span></span>

<span data-ttu-id="2305f-114">Si les catégories de dépense de projet sont gérées dans Project Service Automation, le flux d'intégration s'effectue d'abord de Project Service Automation vers Finance.</span><span class="sxs-lookup"><span data-stu-id="2305f-114">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance.</span></span> <span data-ttu-id="2305f-115">Les catégories de projet doivent déjà être configurées dans Finance avant la synchronisation à partir de Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="2305f-115">The project categories must already be configured in Finance before the synchronization from Project Service Automation.</span></span> <span data-ttu-id="2305f-116">Effectuez ensuite la synchronisation de Finance vers Project Service Automation, puis de Project Service Automation vers Finance.</span><span class="sxs-lookup"><span data-stu-id="2305f-116">Then synchronize from Finance back to Project Service Automation, and then from Project Service Automation to Finance again.</span></span> <span data-ttu-id="2305f-117">Ainsi, vous garantissez que les catégories sont liées, et qu'aucun double n'est créé.</span><span class="sxs-lookup"><span data-stu-id="2305f-117">In this way, you help guarantee that the categories are linked, and that no duplicates are created.</span></span>

> [!NOTE]
> <span data-ttu-id="2305f-118">Généralement, les catégories de dépense de projet sont gérées dans Finance.</span><span class="sxs-lookup"><span data-stu-id="2305f-118">Typically, the project expense categories are mastered in Finance.</span></span> <span data-ttu-id="2305f-119">Toutefois, si elles ne sont pas gérées, ou si des catégories de dépenses ont déjà été créées dans Project Service Automation, vous devez d'abord synchroniser à l'aide du modèle des catégories de transaction de dépense de projet (PSA vers Fin and Ops).</span><span class="sxs-lookup"><span data-stu-id="2305f-119">However, if they aren't, or if expense categories have already been created in Project Service Automation, you must first synchronize by using the Project expense transaction categories (PSA to Fin and Ops) template.</span></span> <span data-ttu-id="2305f-120">Ensuite, effectuez la synchronisation à l'aide du modèle des catégories de transaction de dépense de projet (Fin and Ops vers PSA).</span><span class="sxs-lookup"><span data-stu-id="2305f-120">Then synchronize by using the Project expense transaction categories (Fin and Ops to PSA) template.</span></span> <span data-ttu-id="2305f-121">Vous devez ensuite exécuter la synchronisation de Project Service Automation vers Finance une fois encore.</span><span class="sxs-lookup"><span data-stu-id="2305f-121">You should then run the synchronization from Project Service Automation to Finance one more time.</span></span>
>
> <span data-ttu-id="2305f-122">Si vous synchronisez d'abord depuis Project Service Automation, les conditions suivantes doivent être remplies dans Finance avant que la synchronisation soit exécutée :</span><span class="sxs-lookup"><span data-stu-id="2305f-122">If you synchronize first from Project Service Automation, the following requirements must be met in Finance before the synchronization is run:</span></span>
>
> - <span data-ttu-id="2305f-123">La catégorie partagée correspondant à la catégorie de projet paramétrée dans Project Service Automation doit exister, et elle doit être activée pour **Projet** et **Dépenses**.</span><span class="sxs-lookup"><span data-stu-id="2305f-123">The shared category that matches the project category that is set up in Project Service Automation must exist, and it must be enabled for both **Project** and **Expense**.</span></span>
> - <span data-ttu-id="2305f-124">Pour chaque entité juridique Finance qui doit y être intégrée, les catégories de projet suivantes doivent exister :</span><span class="sxs-lookup"><span data-stu-id="2305f-124">For each Finance legal entity that must be integrated with, the following project categories must exist:</span></span>
>
>     - <span data-ttu-id="2305f-125">**Catégorie de projet** existe.</span><span class="sxs-lookup"><span data-stu-id="2305f-125">**Project category** exists.</span></span> 
>     - <span data-ttu-id="2305f-126">**Utiliser dans Dépense** est activé.</span><span class="sxs-lookup"><span data-stu-id="2305f-126">**Use in Expense** is enabled.</span></span>
>     - <span data-ttu-id="2305f-127">**Actif/active dans les journaux** est activé.</span><span class="sxs-lookup"><span data-stu-id="2305f-127">**Active in journal** is enabled.</span></span>
>     - <span data-ttu-id="2305f-128">**Type de transaction** est défini sur **Dépense**.</span><span class="sxs-lookup"><span data-stu-id="2305f-128">**Transaction type** is set to **Expense**.</span></span>

<span data-ttu-id="2305f-129">L'illustration suivante indique comment les données sont synchronisées entre Project Service Automation et Finance.</span><span class="sxs-lookup"><span data-stu-id="2305f-129">The following illustration shows how the data is synchronized between Project Service Automation and Finance.</span></span>

<span data-ttu-id="2305f-130">[![Flux de données pour l'intégration de Project Service Automation avec Finance](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="2305f-130">[![Data flow for Project Service Automation integration with Finance](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>

## <a name="project-expense-category-synchronization-from-finance-to-project-service-automation"></a><span data-ttu-id="2305f-131">Synchronisation de la catégorie de dépense de projet entre Finance et Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="2305f-131">Project expense category synchronization from Finance to Project Service Automation</span></span>

### <a name="template-and-task"></a><span data-ttu-id="2305f-132">Modèle et tâche</span><span class="sxs-lookup"><span data-stu-id="2305f-132">Template and task</span></span>

<span data-ttu-id="2305f-133">Pour accéder au modèle, dans le centre d'administrateur de Microsoft Power Apps, sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner des modèles publics.</span><span class="sxs-lookup"><span data-stu-id="2305f-133">To access the template, in the Microsoft Power Apps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="2305f-134">Le modèle et la tâche sous-jacente ci-après sont utilisés pour synchroniser les catégories de dépense de projet entre Finance et Project Service Automation :</span><span class="sxs-lookup"><span data-stu-id="2305f-134">The following template and underlying task are used to synchronize project expense categories from Finance to Project Service Automation:</span></span>

- <span data-ttu-id="2305f-135">**Nom du modèle dans le module Intégration des données :** Catégories de transaction de dépense de projet (Fin and Ops vers PSA)</span><span class="sxs-lookup"><span data-stu-id="2305f-135">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
- <span data-ttu-id="2305f-136">**Nom de la tâche dans le projet :** Synchroniser les catégories avec PSA</span><span class="sxs-lookup"><span data-stu-id="2305f-136">**Name of the task in the project:** Sync categories to PSA</span></span>

### <a name="entity-set"></a><span data-ttu-id="2305f-137">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="2305f-137">Entity set</span></span>

| <span data-ttu-id="2305f-138">Finances</span><span class="sxs-lookup"><span data-stu-id="2305f-138">Finance</span></span>                           | <span data-ttu-id="2305f-139">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="2305f-139">Project Service Automation</span></span> |
|-----------------------------------|----------------------------|
| <span data-ttu-id="2305f-140">Entité d'intégration des catégories</span><span class="sxs-lookup"><span data-stu-id="2305f-140">Integration entity for categories</span></span> | <span data-ttu-id="2305f-141">Catégories de transaction</span><span class="sxs-lookup"><span data-stu-id="2305f-141">Transaction categories</span></span>     |

### <a name="entity-flow"></a><span data-ttu-id="2305f-142">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="2305f-142">Entity flow</span></span>

<span data-ttu-id="2305f-143">Les catégories de dépense de projet sont gérées dans Finance, et elles sont synchronisées avec Project Service Automation en tant que catégories de transaction.</span><span class="sxs-lookup"><span data-stu-id="2305f-143">Project expense categories are managed in Finance, and they are synchronized to Project Service Automation as transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="2305f-144">Power Query</span><span class="sxs-lookup"><span data-stu-id="2305f-144">Power Query</span></span>

<span data-ttu-id="2305f-145">Lors de la synchronisation avec Project Service Automation, vous devez utiliser Microsoft Power Query pour Excel pour définir le type de facturation sur la catégorie de transaction.</span><span class="sxs-lookup"><span data-stu-id="2305f-145">When you're synchronizing to Project Service Automation, you must use Microsoft Power Query for Excel to set the billing type on the transaction category.</span></span> <span data-ttu-id="2305f-146">Une colonne par défaut et une mise en correspondance sont fournies pour le modèle Catégories de transaction de dépense de projet (Fin and Ops vers PSA).</span><span class="sxs-lookup"><span data-stu-id="2305f-146">The Project expense transaction categories (Fin and Ops to PSA) template provides a default column and mapping.</span></span> <span data-ttu-id="2305f-147">Si vous créez votre propre modèle, vous devez ajouter une colonne conditionnelle dans Power Query.</span><span class="sxs-lookup"><span data-stu-id="2305f-147">If you create your own template, you must add a conditional column in Power Query.</span></span> <span data-ttu-id="2305f-148">Procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="2305f-148">Follow these steps.</span></span>

1. <span data-ttu-id="2305f-149">Cliquez sur la flèche pour ouvrir la mise en correspondance de la tâche des catégories de dépenses de projet dans le modèle de catégories de transaction de dépense de projet (Fin and Ops vers PSA).</span><span class="sxs-lookup"><span data-stu-id="2305f-149">Click the arrow to open the mapping of the project expense categories task in the Project expense transaction categories (Fin and Ops to PSA) template.</span></span>
2. <span data-ttu-id="2305f-150">Cliquez sur le lien **Requête et filtrage avancés** pour ouvrir Power Query.</span><span class="sxs-lookup"><span data-stu-id="2305f-150">Click the **Advance Query and Filtering** link to open Power Query.</span></span>
2. <span data-ttu-id="2305f-151">Sélectionnez **Ajouter une colonne conditionnelle**.</span><span class="sxs-lookup"><span data-stu-id="2305f-151">Select **Add Conditional Column**.</span></span>
3. <span data-ttu-id="2305f-152">Entrez un nom pour la nouvelle colonne, comme **Type de facturation**.</span><span class="sxs-lookup"><span data-stu-id="2305f-152">Enter a name for the new column, such as **BillingType**.</span></span>
4. <span data-ttu-id="2305f-153">Entrez la condition suivante : **si CATEGORYID n'est pas égal à null, alors 19235001 ; sinon null**.</span><span class="sxs-lookup"><span data-stu-id="2305f-153">Enter the following condition: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
5. <span data-ttu-id="2305f-154">Cliquez sur **OK** dans la colonne.</span><span class="sxs-lookup"><span data-stu-id="2305f-154">Click **OK** on the column.</span></span>
6. <span data-ttu-id="2305f-155">Veillez à mettre en correspondance cette nouvelle colonne sur la page de mise en correspondance.</span><span class="sxs-lookup"><span data-stu-id="2305f-155">Be sure to map this new column on the mapping page.</span></span>

<span data-ttu-id="2305f-156">L'illustration suivante présente un exemple de mise en correspondance des tâches du modèle dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="2305f-156">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="2305f-157">La mise en correspondance indique les informations de champ qui sont synchronisées entre Finance et Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="2305f-157">The mapping shows the field information that will be synchronized from Finance to Project Service Automation.</span></span>

<span data-ttu-id="2305f-158">[![Mise en correspondance des modèles](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="2305f-158">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance"></a><span data-ttu-id="2305f-159">Synchronisation de la catégorie de dépense de projet entre Finance et Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="2305f-159">Project expense category synchronization from Project Service Automation to Finance</span></span>

### <a name="template-and-task"></a><span data-ttu-id="2305f-160">Modèle et tâche</span><span class="sxs-lookup"><span data-stu-id="2305f-160">Template and task</span></span>

<span data-ttu-id="2305f-161">Le modèle et la tâche sous-jacente ci-après sont utilisés pour synchroniser les catégories de dépense de projet entre Finance et Project Service Automation :</span><span class="sxs-lookup"><span data-stu-id="2305f-161">The following template and underlying task are used to synchronize project expense categories from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="2305f-162">**Nom du modèle dans le module Intégration des données :** Catégories de transaction de dépense de projet (PSA vers Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="2305f-162">**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="2305f-163">**Nom de la tâche dans le projet :** Synchroniser les catégories vers Fin Ops</span><span class="sxs-lookup"><span data-stu-id="2305f-163">**Name of the task in the project:** Sync categories to Fin Ops</span></span>

### <a name="entity-set"></a><span data-ttu-id="2305f-164">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="2305f-164">Entity set</span></span>

| <span data-ttu-id="2305f-165">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="2305f-165">Project Service Automation</span></span> | <span data-ttu-id="2305f-166">Finances</span><span class="sxs-lookup"><span data-stu-id="2305f-166">Finance</span></span>                           |
|----------------------------|-----------------------------------|
| <span data-ttu-id="2305f-167">Catégories de transaction</span><span class="sxs-lookup"><span data-stu-id="2305f-167">Transaction categories</span></span>     | <span data-ttu-id="2305f-168">Entité d'intégration des catégories</span><span class="sxs-lookup"><span data-stu-id="2305f-168">Integration entity for categories</span></span> |

### <a name="entity-flow"></a><span data-ttu-id="2305f-169">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="2305f-169">Entity flow</span></span>

<span data-ttu-id="2305f-170">Les catégories de dépense de projet sont gérées dans Finance, et elles sont synchronisées avec Project Service Automation en tant que catégories de transaction.</span><span class="sxs-lookup"><span data-stu-id="2305f-170">Project expense categories are managed in Finance, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="2305f-171">La synchronisation avec Finance met à jour la catégorie de projet dans Finance avec l'ID d'intégration de Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="2305f-171">The synchronization back to Finance updates the project category in Finance with the integration ID from Project Service Automation.</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="2305f-172">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="2305f-172">Template mapping in Data integration</span></span>

<span data-ttu-id="2305f-173">L'illustration suivante présente un exemple de mise en correspondance des tâches du modèle dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="2305f-173">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="2305f-174">La mise en correspondance indique les informations de champ qui sont synchronisées entre Finance et Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="2305f-174">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="2305f-175">[![Mise en correspondance des modèles](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="2305f-175">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>
