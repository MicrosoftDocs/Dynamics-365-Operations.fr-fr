---
title: Contrôle des coûts de problème de l'actif
description: Cette rubrique explique le contrôle des coûts de défaillance d'un actif dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCostControlFault
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 93bd6fb320822f17af5725e227936df623f8d0be
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889167"
---
# <a name="asset-fault-cost-control"></a><span data-ttu-id="16207-103">Contrôle des coûts de problème de l'actif</span><span class="sxs-lookup"><span data-stu-id="16207-103">Asset fault cost control</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="16207-104">Dans le module Gestion des actifs, vous pouvez calculer les coûts des enregistrements de défaillance des actifs pour obtenir une vue d'ensemble des coûts réels comparés aux coûts budgétaires.</span><span class="sxs-lookup"><span data-stu-id="16207-104">In Asset Management, you can calculate costs on asset fault registrations to get an overview of actual costs compared to budget costs.</span></span> <span data-ttu-id="16207-105">Les coûts réels sont basés sur des transactions validées.</span><span class="sxs-lookup"><span data-stu-id="16207-105">Actual costs are based on posted transactions.</span></span> <span data-ttu-id="16207-106">La date est la date de défaillance à laquelle le symptôme a été enregistré.</span><span class="sxs-lookup"><span data-stu-id="16207-106">The date is the fault date on which the symptom was recorded.</span></span>

1. <span data-ttu-id="16207-107">Cliquez sur **Gestion des actifs** > **Recherches** > **Défaillances des actifs** > **Contrôle des coûts de défaillance d'un actif**.</span><span class="sxs-lookup"><span data-stu-id="16207-107">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault cost control**.</span></span>

2. <span data-ttu-id="16207-108">Dans la boîte de dialogue **Contrôle des coûts de défaillance d'actif**, sélectionnez un ensemble de dimension financière à inclure dans le calcul, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="16207-108">In the **Asset fault cost control** dialog, select a financial dimension set to be included in the calculation, if required.</span></span>

4. <span data-ttu-id="16207-109">Sélectionnez « Oui » sur le bouton bascule **Ignorer lignes nulles** si vous ne souhaitez pas afficher les résultats ayant des coûts supérieurs à zéro.</span><span class="sxs-lookup"><span data-stu-id="16207-109">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="16207-110">Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes de contrôle de coût en fonction des postes techniques.</span><span class="sxs-lookup"><span data-stu-id="16207-110">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="16207-111">Par exemple, si vous insérez le chiffre 1 dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes de contrôle des coûts de défaillance d'un actif pour un poste technique s'affichent dans le niveau supérieur et il est donc possible d'ajouter des heures à partir des postes techniques situés à un niveau inférieur.</span><span class="sxs-lookup"><span data-stu-id="16207-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="16207-112">Par exemple, si vous insérez le chiffre 0 dans le champ **Niveau**, un résultat détaillé s'affiche et indique toutes les lignes de contrôle des coûts de défaillance d'un actif sur tous les niveaux du poste technique auquel elles sont liées.</span><span class="sxs-lookup"><span data-stu-id="16207-112">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault cost control lines on all the functional location levels to which they are related.</span></span>

6. <span data-ttu-id="16207-113">Pour limiter la recherche, vous pouvez sélectionner des actifs, des dates de défaillance et des causes de défaillance spécifiques sur l'organisateur **Enregistrements à inclure**.</span><span class="sxs-lookup"><span data-stu-id="16207-113">If you want to limit the search, you can select specific assets, fault dates, and fault causes on the **Records to include** FastTab.</span></span>

7. <span data-ttu-id="16207-114">Cliquez sur **OK** pour démarrer le calcul.</span><span class="sxs-lookup"><span data-stu-id="16207-114">Click **OK** to start the calculation.</span></span>

8. <span data-ttu-id="16207-115">Cliquez sur les boutons **Grouper par** pour afficher le niveau requis de détail du calcul.</span><span class="sxs-lookup"><span data-stu-id="16207-115">Click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="16207-116">Les boutons **Grouper par** sélectionnés sont mis en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="16207-116">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="16207-117">Cliquez sur un bouton pour l'activer ou le désactiver.</span><span class="sxs-lookup"><span data-stu-id="16207-117">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="16207-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="16207-118">Example</span></span>

<span data-ttu-id="16207-119">Cet exemple affiche un calcul du contrôle des coûts de défaillance d'un actif.</span><span class="sxs-lookup"><span data-stu-id="16207-119">This example shows an asset fault cost control calculation.</span></span>

- <span data-ttu-id="16207-120">Le champ **Budget d'origine** indique les coûts budgétaires à partir des prévisions de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="16207-120">The **Original budget** field shows budget costs from the work order forecast.</span></span> 
- <span data-ttu-id="16207-121">Le champ **Coût réel** indique les coûts validés sur les ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="16207-121">The **Actual cost** field shows posted costs on work orders.</span></span> 
- <span data-ttu-id="16207-122">Le champ **Coût engagé** indique les coûts totaux dans lesquels votre société s'engage en termes d'ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="16207-122">The **Committed cost** field shows total costs that your company is committed to in relation to work orders.</span></span>

    ![Figure 1](media/05-controlling-and-reporting.png)

<span data-ttu-id="16207-124">Pour obtenir des informations sur la configuration de défaillances, consultez la rubrique [Gestion des défaillances](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="16207-124">For information about how to set up faults, see the [Fault management](../setup-for-work-orders/fault-management.md) topic.</span></span>
