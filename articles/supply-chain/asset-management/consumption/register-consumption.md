---
title: Enregistrer la consommation
description: Cette rubrique explique comment enregistrer la consommation dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7f785b0935b952d6de68fd120a3639077ad124bd
ms.sourcegitcommit: c0b581e4c647b6c47bc14d1d7bfe267832afecba
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/21/2019
ms.locfileid: "1913085"
---
# <a name="register-consumption"></a><span data-ttu-id="197b5-103">Enregistrer la consommation</span><span class="sxs-lookup"><span data-stu-id="197b5-103">Register consumption</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="197b5-104">Lorsqu'une tâche de maintenance a été effectuée sur un ordre de travail, l'étape suivante consiste à effectuer les enregistrements de la consommation et à valider les journaux.</span><span class="sxs-lookup"><span data-stu-id="197b5-104">When a maintenance job has been completed on a work order, the next step is to make consumption registrations and post the journals.</span></span> <span data-ttu-id="197b5-105">Vous pouvez effectuer les enregistrements sur les types de consommation suivants : heures, articles et dépenses.</span><span class="sxs-lookup"><span data-stu-id="197b5-105">You can make registrations on the following consumption types: Hours, items, and expenses.</span></span> <span data-ttu-id="197b5-106">Les différents types de consommation sont enregistrés et validés sur la page **Journaux des ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="197b5-106">The different consumption types are registered and posted on the **Work order journals** page.</span></span> <span data-ttu-id="197b5-107">Le paramétrage du journal dans **Gestion des actifs** permet de créer et de valider les journaux distincts pour les heures, les articles et les dépenses dans le module **Gestion de projets et comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="197b5-107">The journal setup in **Asset Management** is used for creating and posting separate journals for hours, items, and expenses in the **Project management and accounting** module.</span></span>

<span data-ttu-id="197b5-108">Vous pouvez être en mesure d'ajouter ou de supprimer des lignes de prévisions sur un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="197b5-108">You may be able to add or delete forecast lines on a work order.</span></span> <span data-ttu-id="197b5-109">La configuration d'un état du cycle de vie de l'ordre de travail, le type de projet associé et les règles de stade liées au type de projet déterminent si vous êtes en mesure d'ajouter ou de modifier les lignes de journal.</span><span class="sxs-lookup"><span data-stu-id="197b5-109">The setup of a work order lifecycle state, the related project type, and the stage rules related to the project type determine if you are able to add or edit journal lines.</span></span> <span data-ttu-id="197b5-110">Découvrez-en plus sur les états du cycle de vie de l'ordre de travail et les étapes de projet associées dans [Intégration à la gestion de projets et à la comptabilité](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="197b5-110">Read more about work order lifecycle states and related project stages in [Integration to project management and accounting](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span></span>

>[!NOTE]
><span data-ttu-id="197b5-111">Il est possible de paramétrer la validation automatique des journaux dans un état du cycle de vie de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="197b5-111">It is possible to set up automatic posting of journals on a work order lifecycle state.</span></span> <span data-ttu-id="197b5-112">Consultez [États du cycle de vie de l'ordre de travail](../setup-for-work-orders/work-order-lifecycle-states.md) pour en savoir plus.</span><span class="sxs-lookup"><span data-stu-id="197b5-112">Refer to [Work order lifecycle states](../setup-for-work-orders/work-order-lifecycle-states.md) for more information.</span></span>

1. <span data-ttu-id="197b5-113">Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="197b5-113">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="197b5-114">Sélectionnez l'ordre de travail et cliquez sur **Journaux**.</span><span class="sxs-lookup"><span data-stu-id="197b5-114">Select the work order and click **Journals**.</span></span>

3. <span data-ttu-id="197b5-115">Cliquez sur **Copier à partir des prévisions** pour transférer les lignes de prévision qui peuvent être liées à l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="197b5-115">Click **Copy from forecast** to transfer any forecast lines that may be connected to the work order.</span></span> <span data-ttu-id="197b5-116">Vous pouvez sélectionner les types de consommation que vous souhaitez transférer.</span><span class="sxs-lookup"><span data-stu-id="197b5-116">You can select which consumption types you want to transfer.</span></span>

4. <span data-ttu-id="197b5-117">Si nécessaire, vous pouvez ajouter des lignes de consommation sur l'organisateur pertinent en cliquant sur **Ajouter une ligne** et en remplissant les données sur la ligne.</span><span class="sxs-lookup"><span data-stu-id="197b5-117">If necessary, you can add more consumption lines on the relevant FastTab by clicking **Add line** and filling out data on the line.</span></span>

5. <span data-ttu-id="197b5-118">Cliquez sur **Valider les journaux** pour valider les lignes de journal avant la validation.</span><span class="sxs-lookup"><span data-stu-id="197b5-118">Click **Validate journals** to validate the journal lines before posting.</span></span>

6. <span data-ttu-id="197b5-119">Cliquez sur **Valider les journaux** pour valider les lignes de journal.</span><span class="sxs-lookup"><span data-stu-id="197b5-119">Click **Post journals** to post the journal lines.</span></span>

7. <span data-ttu-id="197b5-120">Après avoir validé les journaux de consommation, vous pouvez mettre à jour l'état du cycle de vie de l'ordre de travail, par exemple sur « Terminé », pour indiquer que l'ordre de travail a été effectué.</span><span class="sxs-lookup"><span data-stu-id="197b5-120">After you've posted the consumption journals, you can update the work order lifecycle state, for example to "Ended", to indicate that the work order has been completed.</span></span>

- <span data-ttu-id="197b5-121">Dans le champ **Afficher** situé en haut de la page **Journaux des ordres de travail**, sélectionnez les lignes de journal à afficher : Toutes, Non validées ou Validées.</span><span class="sxs-lookup"><span data-stu-id="197b5-121">In the **Show** field placed at the top of the **Work order journals** page, select which journal lines you want to see: All, Not posted, or Posted.</span></span> <span data-ttu-id="197b5-122">Les journaux validés ont une coche dans la case **Validé**.</span><span class="sxs-lookup"><span data-stu-id="197b5-122">Posted journals have a check mark in the **Posted** check box.</span></span>  
- <span data-ttu-id="197b5-123">Lorsque des lignes d'article sont créées dans le journal des ordres de travail, les dimensions de produit et de suivi associées à l'article sont automatiquement transférées vers la ligne de journal.</span><span class="sxs-lookup"><span data-stu-id="197b5-123">When item lines are created in the work order journal, product dimensions and tracking dimensions related to the item are automatically transferred to the journal line.</span></span>  

<span data-ttu-id="197b5-124">Le capture d'écran suivante présente un exemple des enregistrements d'heure et d'article sur un bon de travail dans **Journaux des ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="197b5-124">The screenshot below shows an example of hour and item registrations on a work order in **Work order journals**.</span></span>

![Figure 1](media/01-consumption.png)


## <a name="split-hours-on-work-orders-with-several-work-order-jobs"></a><span data-ttu-id="197b5-126">Répartir les heures sur les ordres de travail avec plusieurs tâches de l'ordre de travail</span><span class="sxs-lookup"><span data-stu-id="197b5-126">Split hours on work orders with several work order jobs</span></span>

<span data-ttu-id="197b5-127">Si un ordre de travail contient plusieurs tâches de l'ordre de travail, vous pouvez enregistrer les heures de travail à l'aide de la fonctionnalité **Répartir les heures**, ce qui signifie qu'une ligne d'enregistrement horaire peut être distribuée de manière uniforme sur chaque tâche de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="197b5-127">If a work order contains several work order jobs, you can register work hours using the **Split hours** functionality, meaning one hour registration line can be distributed evenly on each work order job.</span></span>

1. <span data-ttu-id="197b5-128">Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="197b5-128">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="197b5-129">Sélectionnez l'ordre de travail et cliquez sur **Journaux**.</span><span class="sxs-lookup"><span data-stu-id="197b5-129">Select the work order and click **Journals**.</span></span>

3. <span data-ttu-id="197b5-130">Sélectionnez la ligne d'enregistrement horaire à fractionner, puis cliquez sur **Fractionner les heures**.</span><span class="sxs-lookup"><span data-stu-id="197b5-130">Select the hour registration line you want to split, and click **Split hours**.</span></span>

4. <span data-ttu-id="197b5-131">Dans la boîte de dialogue **Fractionner les heures sur les tâches de maintenance de l'ordre de travail**, le nom de l'agent qui est connecté est automatiquement affiché dans le champ **Agent**.</span><span class="sxs-lookup"><span data-stu-id="197b5-131">In the **Split hours on work order maintenance jobs** dialog, the name of the worker who is logged in is automatically shown in the **Worker** field.</span></span> <span data-ttu-id="197b5-132">Si nécessaire, vous pouvez sélectionner un autre agent.</span><span class="sxs-lookup"><span data-stu-id="197b5-132">If required, you can select another worker.</span></span>

5. <span data-ttu-id="197b5-133">Sélectionnez une catégorie pour l'enregistrement des heures dans le champ **Catégorie**.</span><span class="sxs-lookup"><span data-stu-id="197b5-133">Select a category for the hour registration in the **Category** field.</span></span>

6. <span data-ttu-id="197b5-134">Insérez le nombre d'heures de travail à répartir dans le champ **Heures**.</span><span class="sxs-lookup"><span data-stu-id="197b5-134">Insert number of work hours to be split in the **Hours** field.</span></span>

![Figure 2](media/02-consumption.png)

7. <span data-ttu-id="197b5-136">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="197b5-136">Click **OK**.</span></span>

<span data-ttu-id="197b5-137">*Exemple :* dans la capture d'écran ci-dessous, les lignes de journal pour un ordre de travail contenant trois tâches d'ordre de travail sont affichées.</span><span class="sxs-lookup"><span data-stu-id="197b5-137">*Example:* In the screenshot below, journal lines for a work order containing three work order jobs are shown.</span></span> <span data-ttu-id="197b5-138">La première ligne, contenant trois heures de travail, a été fractionnée, et une heure de travail est enregistrée sur chaque tâche de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="197b5-138">The first line, containing three work hours, has been split, and one work hour is registered on each work order job.</span></span> <span data-ttu-id="197b5-139">Une fois que trois lignes d'enregistrement horaire ont été créées, vous décidez ce qu'il convient de faire avec la ligne d'enregistrement horaire d'origine (la première ligne dans l'exemple).</span><span class="sxs-lookup"><span data-stu-id="197b5-139">After the three hour registration lines have been created, you decide what to do with the original hour registration line (the first line in the example).</span></span> <span data-ttu-id="197b5-140">Vous pouvez la garder telle quelle ou la supprimer.</span><span class="sxs-lookup"><span data-stu-id="197b5-140">You can keep it as is or delete it.</span></span> 

![Figure 3](media/03-consumption.png)

## <a name="financial-dimensions-on-consumption-registrations"></a><span data-ttu-id="197b5-142">Dimensions financières sur les enregistrements de consommation</span><span class="sxs-lookup"><span data-stu-id="197b5-142">Financial dimensions on consumption registrations</span></span>

<span data-ttu-id="197b5-143">Lorsque vous effectuez des enregistrements de consommation, les dimensions financières associées aux différents types d'enregistrement sont ajoutées aux enregistrements dans une séquence spécifique.</span><span class="sxs-lookup"><span data-stu-id="197b5-143">When you make consumption registrations, financial dimensions related to the different registration types are added to the registrations in a specific sequence.</span></span> 

<span data-ttu-id="197b5-144">*Enregistrements d'heures et de dépenses :* tout d'abord, les dimensions financières de l'en-tête de journal sont ajoutées, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="197b5-144">*Hour and Expense registrations:* First, financial dimensions from the journal header are added, if any.</span></span> <span data-ttu-id="197b5-145">Ensuite, les dimensions financières du projet de l'ordre de travail associé sont ajoutées.</span><span class="sxs-lookup"><span data-stu-id="197b5-145">Next, financial dimensions from the related work order project are added.</span></span> <span data-ttu-id="197b5-146">Enfin, les dimensions financières de la ressources (agent) sont ajoutées.</span><span class="sxs-lookup"><span data-stu-id="197b5-146">Finally, financial dimensions from the resource (worker) are added.</span></span>

<span data-ttu-id="197b5-147">*Enregistrements de l'article :* tout d'abord, les dimensions financières de l'en-tête de journal sont ajoutées, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="197b5-147">*Item registrations:* First, financial dimensions from the journal header are added, if any.</span></span> <span data-ttu-id="197b5-148">Puis, les dimensions financières du projet de l'ordre de travail associé sont ajoutées.</span><span class="sxs-lookup"><span data-stu-id="197b5-148">Then, financial dimensions from the related work order project are added.</span></span> <span data-ttu-id="197b5-149">Ensuite, les dimensions financières du site sont ajoutées.</span><span class="sxs-lookup"><span data-stu-id="197b5-149">Next, financial dimensions from the site are added.</span></span> <span data-ttu-id="197b5-150">Enfin, les dimensions financières de l'article sont ajoutées.</span><span class="sxs-lookup"><span data-stu-id="197b5-150">Finally, financial dimensions from the item are added.</span></span>

>[!NOTE]
><span data-ttu-id="197b5-151">Pour tous les types d'enregistrement, la combinaison de dimensions financières est ajoutée et les combinaisons non valides sont grisées.</span><span class="sxs-lookup"><span data-stu-id="197b5-151">For all three registration types, the financial dimension combination is validated, and invalid combinations are blanked.</span></span> <span data-ttu-id="197b5-152">Il s'agit du paramétrage standard dans Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="197b5-152">This is standard setup in Dynamics 365 for Finance and Operations.</span></span>

