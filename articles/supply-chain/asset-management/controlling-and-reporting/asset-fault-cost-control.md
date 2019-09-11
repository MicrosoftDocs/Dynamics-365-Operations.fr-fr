---
title: Contrôle des coûts de problème de l'actif
description: Cette rubrique explique le contrôle des coûts de défaillance d'un actif dans le module Gestion des actifs.
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
ms.openlocfilehash: 2fe75c327cdc2bdd76173430ed551895f5941c7b
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918301"
---
# <a name="asset-fault-cost-control"></a><span data-ttu-id="621ad-103">Contrôle des coûts de problème de l'actif</span><span class="sxs-lookup"><span data-stu-id="621ad-103">Asset fault cost control</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="621ad-104">Dans le module Gestion des actifs, vous pouvez calculer les coûts des enregistrements de défaillance des actifs pour obtenir une vue d'ensemble des coûts réels comparés aux coûts budgétaires des défaillances.</span><span class="sxs-lookup"><span data-stu-id="621ad-104">In Asset Management, you can calculate costs on asset fault registrations to get an overview of actual costs compared to budget costs on faults.</span></span> <span data-ttu-id="621ad-105">Les coûts réels sont basés sur des transactions validées.</span><span class="sxs-lookup"><span data-stu-id="621ad-105">Actual costs are based on posted transactions.</span></span> <span data-ttu-id="621ad-106">La date est la date de défaillance à laquelle le symptôme a été enregistré.</span><span class="sxs-lookup"><span data-stu-id="621ad-106">The date is the fault date on which the symptom was recorded.</span></span>

1. <span data-ttu-id="621ad-107">Cliquez sur **Gestion des actifs** > **Recherches** > **Défaillances des actifs** > **Contrôle des coûts de défaillance d'un actif**.</span><span class="sxs-lookup"><span data-stu-id="621ad-107">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault cost control**.</span></span>

2. <span data-ttu-id="621ad-108">Dans la boîte de dialogue **Contrôle des coûts de défaillance d'actif**, sélectionnez un ensemble de dimension financière à inclure dans le calcul, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="621ad-108">In the **Asset fault cost control** dialog, select a financial dimension set to be included in the calculation, if required.</span></span>

4. <span data-ttu-id="621ad-109">Sélectionnez « Oui » sur le bouton bascule **Ignorer lignes nulles** si vous ne souhaitez pas afficher les résultats ayant des coûts supérieurs à zéro.</span><span class="sxs-lookup"><span data-stu-id="621ad-109">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="621ad-110">Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes de contrôle de coût en fonction des postes techniques.</span><span class="sxs-lookup"><span data-stu-id="621ad-110">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> <span data-ttu-id="621ad-111">Par exemple, si vous insérez le chiffre 1 dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes de contrôle des coûts de défaillance d'un actif pour un poste technique s'affichent dans le niveau supérieur et il est donc possible d'ajouter des heures à partir des postes techniques situés à un niveau inférieur.</span><span class="sxs-lookup"><span data-stu-id="621ad-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="621ad-112">Par exemple, si vous insérez le chiffre 0 dans le champ **Niveau**, un résultat détaillé s'affiche et indique toutes les lignes de contrôle des coûts de défaillance d'un actif sur tous les niveaux du poste technique auquel elles sont liées.</span><span class="sxs-lookup"><span data-stu-id="621ad-112">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault cost control lines on all the functional location levels to which they are related.</span></span>

6. <span data-ttu-id="621ad-113">Pour limiter la recherche, vous pouvez sélectionner des actifs, des dates de défaillance et des causes de défaillance spécifiques sur l'organisateur **Enregistrements à inclure**.</span><span class="sxs-lookup"><span data-stu-id="621ad-113">If you want to limit the search, you can select specific assets, fault dates, and fault causes on the **Records to include** FastTab.</span></span>

7. <span data-ttu-id="621ad-114">Cliquez sur **OK** pour démarrer le calcul.</span><span class="sxs-lookup"><span data-stu-id="621ad-114">Click **OK** to start the calculation.</span></span>

8. <span data-ttu-id="621ad-115">Dans les groupes de volet Actions **Grouper par…**, cliquez sur les boutons appropriés à afficher le niveau requis de détail du calcul.</span><span class="sxs-lookup"><span data-stu-id="621ad-115">In the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="621ad-116">Les boutons sélectionnés du volet Actions sont mis en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="621ad-116">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="621ad-117">Cliquez sur un bouton pour l'activer ou le désactiver.</span><span class="sxs-lookup"><span data-stu-id="621ad-117">Click on a button to activate or deactivate it.</span></span>

<span data-ttu-id="621ad-118">L'illustration suivante présente un exemple de calcul de contrôle des coûts de défaillance d'actif.</span><span class="sxs-lookup"><span data-stu-id="621ad-118">The figure below shows an example of an asset fault cost control calculation.</span></span>

![Figure 1](media/05-controlling-and-reporting.png)

<span data-ttu-id="621ad-120">Reportez-vous à la section [Gestion des défaillances](../setup-for-work-orders/fault-management.md) pour obtenir des informations sur la procédure de paramétrage des défaillances.</span><span class="sxs-lookup"><span data-stu-id="621ad-120">Refer to the [Fault management](../setup-for-work-orders/fault-management.md) section for information on how to set up faults.</span></span>

>[!NOTE]
><span data-ttu-id="621ad-121">Le champ **Budget d'origine** indique les coûts budgétaires à partir des prévisions de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="621ad-121">The **Original budget** field shows budget costs from the work order forecast.</span></span> <span data-ttu-id="621ad-122">Le champ **Coût réel** indique les coûts validés sur les ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="621ad-122">The **Actual cost** field shows posted costs on work orders.</span></span> <span data-ttu-id="621ad-123">Le champ **Coût engagé** indique les coûts totaux dans lesquels votre société s'engage en termes d'ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="621ad-123">The **Committed cost** field shows total costs that your company is committed to in relation to work orders.</span></span>

