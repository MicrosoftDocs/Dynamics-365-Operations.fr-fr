---
title: Contrôle de date et de coût
description: Cette rubrique explique le contrôle de date et de coût dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.openlocfilehash: 2bcd1584f6a858f7589387fbfe96267b7c16176a
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918393"
---
# <a name="cost-and-date-control"></a><span data-ttu-id="3aa89-103">Contrôle de date et de coût</span><span class="sxs-lookup"><span data-stu-id="3aa89-103">Cost and date control</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="3aa89-104">Dans le module Gestion des actifs, vous pouvez calculer des coûts pour obtenir une vue d'ensemble des coûts réels comparés aux coûts budgétaires des actifs, des postes techniques et des ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="3aa89-104">In Asset Management, you can calculate costs to get an overview of actual costs compared to budget costs on assets, functional locations, and work orders.</span></span> <span data-ttu-id="3aa89-105">Les coûts réels sont basés sur des transactions validées.</span><span class="sxs-lookup"><span data-stu-id="3aa89-105">Actual costs are based on posted transactions.</span></span> <span data-ttu-id="3aa89-106">Vous pouvez également effectuer un calcul de date si vous souhaitez comparer les dates de début et de fin prévues par rapport aux dates de début et de fin réelles sur les ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="3aa89-106">You can also make a date calculation if you want to compare scheduled start and end dates to actual start and end dates on work orders.</span></span>

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a><span data-ttu-id="3aa89-107">Contrôle des coûts pour des actifs, des postes techniques et des ordres de travail</span><span class="sxs-lookup"><span data-stu-id="3aa89-107">Cost control for assets, functional locations, and work orders</span></span>

<span data-ttu-id="3aa89-108">Les calculs effectués pour les actifs, les postes techniques et les ordres de travail sont quasiment identiques.</span><span class="sxs-lookup"><span data-stu-id="3aa89-108">The calculations made for assets, functional locations, and work orders are almost identical.</span></span> <span data-ttu-id="3aa89-109">L'unique différence réside dans le fait que pour les actifs et les postes techniques, vous pouvez également inclure les sous-actifs et les sous-postes dans votre calcul.</span><span class="sxs-lookup"><span data-stu-id="3aa89-109">Only difference is that for assets and functional locations, you can also include sub assets and sub locations in your calculation.</span></span> <span data-ttu-id="3aa89-110">La date est la date de transaction à laquelle l'enregistrement a été enregistré.</span><span class="sxs-lookup"><span data-stu-id="3aa89-110">The date is the transaction date when the registration was recorded.</span></span>

1. <span data-ttu-id="3aa89-111">Cliquez sur **Gestion des actifs** > **Recherches** > **Actifs** > **Contrôle des coûts d'actif** ou **Contrôle des coûts du poste technique** ou **Gestion des actifs** > **Recherches** > **Ordres de travail** > **Contrôle des coûts des ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="3aa89-111">Click **Asset management** > **Inquiries** > **Assets** > **Asset cost control** or **Functional location cost control**, or **Asset management** > **Inquiries** > **Work orders** > **Work order cost control**.</span></span>

2. <span data-ttu-id="3aa89-112">Dans la boîte de dialogue **Contrôle des coûts d'actif** / **Contrôle des coûts du poste technique** / **Contrôle des coûts des ordres de travail**, sélectionnez une période à calculer.</span><span class="sxs-lookup"><span data-stu-id="3aa89-112">In the **Asset cost control** / **Functional location cost control** / **Work order cost control** dialog, select a period to be calculated.</span></span>

3. <span data-ttu-id="3aa89-113">Si nécessaire, sélectionnez un ensemble de dimensions financières à inclure dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="3aa89-113">If required, select a financial dimension set to be included in the calculation.</span></span>

4. <span data-ttu-id="3aa89-114">Sélectionnez « Oui » sur le bouton bascule **Ignorer lignes nulles** si vous ne souhaitez pas afficher les résultats ayant des coûts supérieurs à zéro.</span><span class="sxs-lookup"><span data-stu-id="3aa89-114">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="3aa89-115">Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes de contrôle de coût en fonction des postes techniques.</span><span class="sxs-lookup"><span data-stu-id="3aa89-115">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> <span data-ttu-id="3aa89-116">Par exemple, si vous insérez le chiffre 1 dans le champ, et que vous avez une hiérarchie de postes techniques à plusieurs niveaux, toutes les lignes de contrôle des coûts pour un poste technique s'affichent dans le niveau supérieur et il est donc possible d'ajouter les heures sur une ligne à partir des postes techniques situés à un niveau inférieur.</span><span class="sxs-lookup"><span data-stu-id="3aa89-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location hierarchy, all cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="3aa89-117">Par exemple, si vous insérez le chiffre 0 dans le champ **Niveau**, un résultat détaillé s'affiche et indique toutes les lignes de contrôle de coût sur tout le niveau du poste technique auquel elles sont liées.</span><span class="sxs-lookup"><span data-stu-id="3aa89-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all cost control lines on all the functional location level to which they are related.</span></span>

6. <span data-ttu-id="3aa89-118">Sélectionnez « Oui » sur le bouton bascule **Afficher les coûts engagés en cours** pour inclure cette colonne dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="3aa89-118">Select "Yes" on the **Show open committed cost** toggle button if you want to include that column in the calculation.</span></span>

7. <span data-ttu-id="3aa89-119">Sélectionnez « Oui » sur le bouton à bascule **Inclure les sous-actifs** pour afficher les coûts associés aux sous-actifs comme lignes distinctes.</span><span class="sxs-lookup"><span data-stu-id="3aa89-119">Select "Yes" on the **Include sub assets** toggle button to show costs related to sub assets as separate lines.</span></span>

8. <span data-ttu-id="3aa89-120">Pour limiter la recherche, vous pouvez sélectionner des actifs/postes techniques/ordres de travail sur l'organisateur **Enregistrements à inclure**.</span><span class="sxs-lookup"><span data-stu-id="3aa89-120">If you want to limit the search, you can select specific assets / functional locations / work orders on the **Records to include** FastTab.</span></span>

9. <span data-ttu-id="3aa89-121">Cliquez sur **OK** pour démarrer le calcul.</span><span class="sxs-lookup"><span data-stu-id="3aa89-121">Click **OK** to start the calculation.</span></span>

<span data-ttu-id="3aa89-122">L'illustration suivante présente un exemple de la boîte de dialogue **Contrôle des coûts d'actif**.</span><span class="sxs-lookup"><span data-stu-id="3aa89-122">The figure below shows an example of the **Asset cost control** dialog.</span></span>

![Figure 1](media/01-controlling-and-reporting.png)

10. <span data-ttu-id="3aa89-124">Dans les groupes de volet Actions **Grouper par...** de la page **Contrôle des coûts d'actif**, cliquez sur les boutons appropriés pour afficher le niveau requis de détail du calcul.</span><span class="sxs-lookup"><span data-stu-id="3aa89-124">In the **Group by...** action pane groups on the **Asset cost control** page, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="3aa89-125">Les boutons sélectionnés du volet Actions sont mis en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="3aa89-125">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="3aa89-126">Cliquez sur un bouton pour l'activer ou le désactiver.</span><span class="sxs-lookup"><span data-stu-id="3aa89-126">Click on a button to activate or deactivate it.</span></span>

<span data-ttu-id="3aa89-127">L'illustration suivante présente un exemple de résultats du calcul dans **Contrôle des coûts d'actif**.</span><span class="sxs-lookup"><span data-stu-id="3aa89-127">The figure below shows an example of calculation results in **Asset cost control**.</span></span>

![Figure 2](media/02-controlling-and-reporting.png)

<span data-ttu-id="3aa89-129">Une autre manière d'effectuer un calcul du coût est de choisir plusieurs actifs dans **Tous les actifs** ou **Actifs actifs**.</span><span class="sxs-lookup"><span data-stu-id="3aa89-129">Another way of making a cost calculation is to multi-select assets in **All assets** or **Active assets**.</span></span> <span data-ttu-id="3aa89-130">Cliquez ensuite sur le bouton **Contrôle des coûts** sur l'onglet **Général** . Dans la boîte de dialogue **Contrôle des coûts d'actif**, les actifs sélectionnés sont insérés automatiquement dans le champ **Actif** sur l'organisateur **Enregistrements à inclure**.</span><span class="sxs-lookup"><span data-stu-id="3aa89-130">Then, you click the **Cost control** button on the **General** tab. In the **Asset cost control** dialog, the selected assets are automatically inserted in the **Asset** field on the **Records to include** FastTab.</span></span> <span data-ttu-id="3aa89-131">Cliquez sur **OK** et un calcul des coûts pour les actifs sélectionnés s'affiche.</span><span class="sxs-lookup"><span data-stu-id="3aa89-131">Click **OK**, and a cost calculation for the selected assets is shown.</span></span> <span data-ttu-id="3aa89-132">La même procédure peut être effectuée pour les postes techniques dans **Tous les postes techniques** ou **Postes techniques actifs**, et pour les ordres de travail dans **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="3aa89-132">The same procedure can be done for functional locations in **All functional locations** or **Active functional locations**, and for work orders in **All work orders** or **Active work orders**.</span></span>

>[!NOTE]
><span data-ttu-id="3aa89-133">Le champ **Budget d'origine** indique les coûts budgétaires à partir des prévisions de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="3aa89-133">The **Original budget** field shows budget costs from the work order forecast.</span></span> <span data-ttu-id="3aa89-134">Le champ **Coût engagé** indique le montant total de dépenses que l'entité juridique s'est engagée à payer.</span><span class="sxs-lookup"><span data-stu-id="3aa89-134">The **Committed cost** field shows the total amount of expenses that a legal entity has committed itself to pay.</span></span> <span data-ttu-id="3aa89-135">Le champ **Coûts engagés en cours** indique les engagements à payer des articles, des heures, et des services commandés ou reçus mais pas encore réglés.</span><span class="sxs-lookup"><span data-stu-id="3aa89-135">The **Open committed cost** field shows commitments to pay for items, hours, and services you have ordered or received but not yet paid for.</span></span> <span data-ttu-id="3aa89-136">Lorsque tous les enregistrements de consommation ont été validés, les coûts associés sont inclus dans le champ **Coût réel**.</span><span class="sxs-lookup"><span data-stu-id="3aa89-136">When all consumption registrations have been posted, the related costs are included in the **Actual cost** field.</span></span>

## <a name="work-order-date-control"></a><span data-ttu-id="3aa89-137">Contrôle de la date de l'ordre de travail</span><span class="sxs-lookup"><span data-stu-id="3aa89-137">Work order date control</span></span>

<span data-ttu-id="3aa89-138">Cette page permet d'obtenir une vue d'ensemble des dates de début et de fin attendues par rapport aux dates de début et de fin réelles sur les ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="3aa89-138">Use this page to get an overview of expected start and end dates compared to actual start and end dates on work orders.</span></span>

1. <span data-ttu-id="3aa89-139">Cliquez sur **Gestion des actifs** > **Recherches** > **Ordres de travail** > **Contrôle de date d'ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="3aa89-139">Click **Asset management** > **Inquiries** > **Work orders** > **Work order date control**.</span></span>

2. <span data-ttu-id="3aa89-140">Cliquez sur **Calculer.**</span><span class="sxs-lookup"><span data-stu-id="3aa89-140">Click **Calculate**.</span></span>

3. <span data-ttu-id="3aa89-141">Sélectionnez un poste technique dans le champ **Poste technique**.</span><span class="sxs-lookup"><span data-stu-id="3aa89-141">Select a functional location in the **Functional location** field.</span></span>

4. <span data-ttu-id="3aa89-142">Insérez la période pour laquelle vous souhaitez effectuer le calcul dans les champs **Date de début** et **Date de fin**.</span><span class="sxs-lookup"><span data-stu-id="3aa89-142">Insert the period for which you want to make the calculation in the **From date** and **To date** fields.</span></span> <span data-ttu-id="3aa89-143">Tous les bons de travail avec la date de début prévue dans la période seront inclus.</span><span class="sxs-lookup"><span data-stu-id="3aa89-143">All work orders with expected start within the period will be included.</span></span>

5. <span data-ttu-id="3aa89-144">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3aa89-144">Click **OK**.</span></span>

6. <span data-ttu-id="3aa89-145">Dans les groupes de volet Actions **Grouper par…**, cliquez sur les boutons appropriés à afficher le niveau requis de détail du calcul.</span><span class="sxs-lookup"><span data-stu-id="3aa89-145">In the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="3aa89-146">Les boutons sélectionnés du volet Actions sont mis en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="3aa89-146">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="3aa89-147">Cliquez sur un bouton pour l'activer ou le désactiver.</span><span class="sxs-lookup"><span data-stu-id="3aa89-147">Click on a button to activate or deactivate it.</span></span>

<span data-ttu-id="3aa89-148">L'illustration suivante présente un exemple des résultats des calculs dans **Contrôle de date d'ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="3aa89-148">The figure below shows an example of calculation results in **Work order date control**.</span></span>

![Figure 3](media/03-controlling-and-reporting.png)

- <span data-ttu-id="3aa89-150">Le champ **Retard de début moyen** indique la différence en jours entre la date de début prévue pour un bon de travail par rapport à la date de début réelle.</span><span class="sxs-lookup"><span data-stu-id="3aa89-150">The **Avg. start delay** field shows the difference in days between scheduled start date for a work order compared to actual start date.</span></span> <span data-ttu-id="3aa89-151">Si, par exemple, la date de début réelle était deux jours avant la date de début prévue, « -2 » s'affichera dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="3aa89-151">If, for example, the actual start date was two days before the scheduled start date, "-2" will be displayed in this field.</span></span>  
- <span data-ttu-id="3aa89-152">Le champ **Retard de fin moyen** indique la différence en jours entre la date de fin prévue pour un bon de travail par rapport à la date de fin réelle.</span><span class="sxs-lookup"><span data-stu-id="3aa89-152">The **Avg. end delay** field shows the difference in days between scheduled end date for a work order compared to actual end date.</span></span> <span data-ttu-id="3aa89-153">Si, par exemple, la date de fin réelle était trois jours après la date de fin prévue, « -3 » s'affichera dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="3aa89-153">If, for example, the actual end date was three days after the scheduled end date, "3" will be displayed in this field.</span></span>  
- <span data-ttu-id="3aa89-154">Les champs **Occurrences** indiquent le nombre d'écarts entre les dates de début et de fin prévues et celles de début et de fin réelles sur les ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="3aa89-154">The **Occurrences** fields show the number of times deviations occur in relation to scheduled and actual start date, and scheduled and actual end date on the work order.</span></span>

