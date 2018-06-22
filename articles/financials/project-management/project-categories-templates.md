---
title: "Synchroniser les catégories de dépense de projet à partir de Project Service Automation"
description: "Cette rubrique décrit les modèles et les tâches sous-jacentes qui sont utilisés pour synchroniser les catégories de dépense de projet entre Microsoft Dynamics 365 for Finance and Operations et Dynamics 365 for Project Service Automation."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: dcdb9b6ec296073d511c069cdceb1c61080b6d97
ms.contentlocale: fr-fr
ms.lasthandoff: 05/29/2018

---

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="a3bc3-103">Synchroniser les catégories de dépense de projet entre Finance and Operations et Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="a3bc3-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

<span data-ttu-id="a3bc3-104">Cette rubrique décrit les modèles et les tâches sous-jacentes qui sont utilisés pour synchroniser les catégories de dépense de projet entre Microsoft Dynamics 365 for Finance and Operations et Dynamics 365 for Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Microsoft Dynamics 365 for Finance and Operations and Dynamics 365 for Project Service Automation.</span></span>

> [!NOTE]
> <span data-ttu-id="a3bc3-105">L'intégration des tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et le verrouillage des fonctionnalités sont disponibles dans la version 8.0 de Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-105">Project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in Dynamics 365 for Finance and Operations version 8.0.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a><span data-ttu-id="a3bc3-106">Flux de données pour Project Service Automation et Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a3bc3-106">Data flow for Project Service Automation and Finance and Operations</span></span>

<span data-ttu-id="a3bc3-107">La solution d'intégration de Project Service Automation avec Finance and Operations utilise la fonction Intégration des données pour synchroniser les données entre les instances de Project Service Automation et de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-107">The Project Service Automation and Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="a3bc3-108">Les modèles d'intégration disponibles avec la fonction Intégration des données activent le flux de données sur les catégories de transaction de dépense du projet entre Finance and Operations et Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-108">The integration templates that are available with the Data integration feature enables the flow of data about project expense transaction categories between Finance and Operations and Project Service Automation.</span></span>

<span data-ttu-id="a3bc3-109">Si les catégories de dépense de projet sont gérées dans Finance and Operations, le flux d'intégration s'effectue d'abord de Finance and Operations vers Project Service Automation, puis les ID d'intégration des catégories de dépense de projet sont mis à jour par synchronisation entre Project Service Automation et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-109">If the project expense categories are mastered in Finance and Operations, the integration flow is first from Finance and Operations to Project Service Automation, and then updating the project expense categories integration IDs by synchronizing from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="a3bc3-110">Si les catégories de dépense de projet sont gérées dans Project Service Automation, le flux d'intégration s'effectue d'abord de Project Service Automation vers Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-110">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance and Operations.</span></span> <span data-ttu-id="a3bc3-111">Les catégories de projet doivent déjà être configurées dans Finance and Operations avant la synchronisation à partir de Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-111">The project categories must already be configured in Finance and Operations prior to the synchronization from Project Service Automation.</span></span> <span data-ttu-id="a3bc3-112">Effectuez ensuite la synchronisation de Finance and Operations vers Project Service Automation, puis de Project Service Automation vers Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-112">Then synchronize from Finance and Operations back to Project Service Automation and then from Project Service Automation to Finance and Operations again.</span></span> <span data-ttu-id="a3bc3-113">Cela garantit que les catégories sont liées et que des doublons ne sont pas créés.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-113">This ensures the categories are linked and duplicates are not created.</span></span>

> [!NOTE]
> <span data-ttu-id="a3bc3-114">Généralement, les catégories de dépense de projet sont gérées dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-114">Typically, the project expense categories will be mastered in Finance and Operations.</span></span> <span data-ttu-id="a3bc3-115">Si tel n'est pas votre cas, ou si des catégories de dépense sont déjà créées dans Project Service Automation, vous devez d'abord effectuer la synchronisation à l'aide des catégories de transaction de dépense de projet (PSA vers Fin and Ops), puis effectuer la synchronisation à l'aide des catégories de transaction de dépense de projet (Fin and Ops vers PSA).</span><span class="sxs-lookup"><span data-stu-id="a3bc3-115">If that is not your situation, or you already have expense categories created in Project Service Automation, you must first sync using the Project expense transaction categories (PSA to Fin and Ops) and then sync using Project expense transaction categories (Fin and Ops to PSA).</span></span> <span data-ttu-id="a3bc3-116">Vous devez ensuite effectuer la synchronisation de PSA vers Fin and Ops encore une fois.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-116">You should then run the sync from PSA to Fin and Ops one more time.</span></span>

> <span data-ttu-id="a3bc3-117">Si vous effectuez la synchronisation à partir de Project Service Automation, les catégories de projet doivent déjà être paramétrées dans Finance and Operations, et les catégories de projet devant être synchronisées avec les catégories de transaction de Project Service Automation doivent être paramétrées comme **Actives dans les journaux**.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-117">If synchronizing first from Project Service Automation, the project categories must already be set up in Finance and Operations and any project categories that need to be synched with the Project Service Automation transaction categories must be set up to be **Active in journals**.</span></span>

<span data-ttu-id="a3bc3-118">L'illustration suivante indique comment les données sont synchronisées entre Project Service Automation et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-118">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="a3bc3-119">[![Flux de données pour l'intégration de Project Service Automation avec Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="a3bc3-119">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>


## <a name="templates-and-tasks"></a><span data-ttu-id="a3bc3-120">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="a3bc3-120">Templates and tasks</span></span>

<span data-ttu-id="a3bc3-121">Pour accéder aux modèles disponibles, dans le centre d'administrateur de Microsoft PowerApps, sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner des modèles publics.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-121">To access available templates, in the Microsoft PowerApps Admin Center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="a3bc3-122">Le modèle et la tâche sous-jacente ci-après sont utilisés pour synchroniser les catégories de dépense de projet entre Finance and Operations et Project Service Automation :</span><span class="sxs-lookup"><span data-stu-id="a3bc3-122">The following template and underlying task is used to synchronize project expense categories from Finance and Operations to Project Service Automation:</span></span>

-  <span data-ttu-id="a3bc3-123">**Nom du modèle dans le module Intégration des données :** Catégories de transaction de dépense de projet (Fin and Ops vers PSA)</span><span class="sxs-lookup"><span data-stu-id="a3bc3-123">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
-  <span data-ttu-id="a3bc3-124">**Nom de la tâche dans le projet :** Synchroniser les catégories avec PSA</span><span class="sxs-lookup"><span data-stu-id="a3bc3-124">**Name of the task in the project:** Sync categories to PSA</span></span>

## <a name="entity-set"></a><span data-ttu-id="a3bc3-125">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="a3bc3-125">Entity set</span></span>

| <span data-ttu-id="a3bc3-126">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a3bc3-126">Finance and Operations</span></span>               | <span data-ttu-id="a3bc3-127">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="a3bc3-127">Project Service Automation</span></span>    |
|--------------------------------------|-------------------------------|
| <span data-ttu-id="a3bc3-128">Entité d'intégration des catégories</span><span class="sxs-lookup"><span data-stu-id="a3bc3-128">Integration entity for categories</span></span>    | <span data-ttu-id="a3bc3-129">Catégories de transaction</span><span class="sxs-lookup"><span data-stu-id="a3bc3-129">Transaction categories</span></span>        |

## <a name="entity-flow"></a><span data-ttu-id="a3bc3-130">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="a3bc3-130">Entity flow</span></span>

<span data-ttu-id="a3bc3-131">Les catégories de dépense de projet sont gérées dans Finance and Operations, et elles sont synchronisées avec Project Service Automation en tant que catégories de transaction.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-131">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span>

## <a name="power-query"></a><span data-ttu-id="a3bc3-132">Power Query</span><span class="sxs-lookup"><span data-stu-id="a3bc3-132">Power Query</span></span>

<span data-ttu-id="a3bc3-133">Vous devez utiliser Microsoft Power Query pour définir le type de facturation sur la catégorie de transaction lors de la synchronisation avec Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-133">You must use Microsoft Power Query to set the billing type on the transaction category when synchronizing to Project Service Automation.</span></span> <span data-ttu-id="a3bc3-134">Une colonne par défaut et une mise en correspondance sont déjà fournies pour le modèle Catégories de transaction de dépense de projet (Fin and Ops vers PSA).</span><span class="sxs-lookup"><span data-stu-id="a3bc3-134">The Project expense transaction categories (Fin and Ops to PSA) template has a default column and mapping already provided.</span></span> <span data-ttu-id="a3bc3-135">Si vous créez votre propre modèle, vous devez ajouter une colonne conditionnelle dans Power Query.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-135">If you create your own template, you must add a conditional column in Power Query.</span></span>
- <span data-ttu-id="a3bc3-136">Ouvrez l'écran Requête et filtrage avancés dans la mise en correspondance de la tâche de catégories de dépense de projet.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-136">Open the Advance Query and Filtering form from within the mapping of project expense categories task.</span></span>
- <span data-ttu-id="a3bc3-137">Sélectionnez **Ajouter une colonne conditionnelle**.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-137">Select **Add Conditional Column**.</span></span>
- <span data-ttu-id="a3bc3-138">Attribuez un nom à la nouvelle colonne, par exemple BillingType.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-138">Give the new column a name, such as BillingType.</span></span>
- <span data-ttu-id="a3bc3-139">Entrez la condition suivante : si **CATEGORYID n'est pas égal à null, alors 19235001 ; sinon null**.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-139">Enter the following condition: if **CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
- <span data-ttu-id="a3bc3-140">Cliquez sur **OK** dans la colonne.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-140">Click **OK** on the column.</span></span>
- <span data-ttu-id="a3bc3-141">Veillez à mettre en correspondance cette nouvelle colonne dans la page de mise en correspondance.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-141">Be sure to map this new column in the mapping page.</span></span>

<span data-ttu-id="a3bc3-142">L'illustration suivante présente un exemple de mise en correspondance des tâches du modèle dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-142">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="a3bc3-143">La mise en correspondance indique les informations de champ qui sont synchronisées entre Finance and Operations et Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-143">The mapping shows the field information that will be synchronized from Finance and Operations to Project Service Automation.</span></span>

<span data-ttu-id="a3bc3-144">[![Mise en correspondance des modèles](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="a3bc3-144">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

<span data-ttu-id="a3bc3-145">Le modèle et la tâche sous-jacente ci-après sont utilisés pour synchroniser les catégories de dépense de projet entre Project Service Automation et Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="a3bc3-145">The following template and underlying task is used to synchronize project expense categories from Project Service Automation to Finance and Operations:</span></span>

<span data-ttu-id="a3bc3-146">-**Nom du modèle dans le module Intégration des données :** Catégories de transaction de dépense de projet (PSA vers Fin and Ops) -**Nom de la tâche dans le projet :** Synchroniser les catégories avec Fin Ops</span><span class="sxs-lookup"><span data-stu-id="a3bc3-146">-**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops) -**Name of the task in the project:** Sync categories to Fin Ops</span></span>

## <a name="entity-set"></a><span data-ttu-id="a3bc3-147">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="a3bc3-147">Entity set</span></span>

| <span data-ttu-id="a3bc3-148">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="a3bc3-148">Project Service Automation</span></span>      | <span data-ttu-id="a3bc3-149">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a3bc3-149">Finance and Operations</span></span>             |
|---------------------------------|------------------------------------|
| <span data-ttu-id="a3bc3-150">Catégories de transaction</span><span class="sxs-lookup"><span data-stu-id="a3bc3-150">Transaction categories</span></span>          | <span data-ttu-id="a3bc3-151">Entité d'intégration des catégories</span><span class="sxs-lookup"><span data-stu-id="a3bc3-151">Integration entity for categories</span></span>  | 

## <a name="entity-flow"></a><span data-ttu-id="a3bc3-152">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="a3bc3-152">Entity flow</span></span>

<span data-ttu-id="a3bc3-153">Les catégories de dépense de projet sont gérées dans Finance and Operations, et elles sont synchronisées avec Project Service Automation en tant que catégories de transaction.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-153">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="a3bc3-154">La synchronisation avec Finance and Operations met à jour l'ID d'intégration de Project Service Automation sur la catégorie de projet Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-154">The synchronization back to Finance and Operations updates the integration ID from Project Service Automation on the Finance and Operations project category.</span></span>

<span data-ttu-id="a3bc3-155">L'illustration suivante présente un exemple de mise en correspondance des tâches du modèle dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-155">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="a3bc3-156">La mise en correspondance indique les informations de champ qui sont synchronisées entre Project Service Automation et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a3bc3-156">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="a3bc3-157">[![Mise en correspondance des modèles](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="a3bc3-157">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>

