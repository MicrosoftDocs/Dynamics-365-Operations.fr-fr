--- 
title: Terminer un ordre de fabrication
description: "Cette procédure permet d'indiquer comment mettre fin à un ordre de fabrication."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 75b91ea330258a5b57e9e58cb32539d57e458f28
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="end-a-production-order"></a><span data-ttu-id="c1fd0-103">Terminer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="c1fd0-103">End a production order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c1fd0-104">Cette procédure permet d'indiquer comment mettre fin à un ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="c1fd0-104">This procedure shows how to end a production order.</span></span> <span data-ttu-id="c1fd0-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="c1fd0-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c1fd0-106">Il s'agit de la dernière des sept procédures expliquant le cycle de vie de l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="c1fd0-106">This is the final procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="end-a-production-order"></a><span data-ttu-id="c1fd0-107">Terminer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="c1fd0-107">End a production order</span></span>
1. <span data-ttu-id="c1fd0-108">Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="c1fd0-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="c1fd0-109">Sélectionnez un ordre de fabrication dont le statut est Déclaré terminé.</span><span class="sxs-lookup"><span data-stu-id="c1fd0-109">Select a production order that has the status Reported as finished.</span></span>  
2. <span data-ttu-id="c1fd0-110">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="c1fd0-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="c1fd0-111">Cliquez sur Fin.</span><span class="sxs-lookup"><span data-stu-id="c1fd0-111">Click End.</span></span>
    * <span data-ttu-id="c1fd0-112">Dans cette page, vous pouvez confirmer que vous voulez mettre fin à l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="c1fd0-112">On this page, you can confirm that you want to end the production order.</span></span>  
4. <span data-ttu-id="c1fd0-113">Cliquez sur l'onglet Général.</span><span class="sxs-lookup"><span data-stu-id="c1fd0-113">Click the General tab.</span></span>
5. <span data-ttu-id="c1fd0-114">Entrez une date dans le champ Date.</span><span class="sxs-lookup"><span data-stu-id="c1fd0-114">In the Date field, enter a date.</span></span>
6. <span data-ttu-id="c1fd0-115">Dans le champ Mode de mise au rebut, sélectionnez « Répartition ».</span><span class="sxs-lookup"><span data-stu-id="c1fd0-115">In the Scrap method field, select 'Allocation'.</span></span>
    * <span data-ttu-id="c1fd0-116">Lorsque vous sélectionnez la méthode de répartition, les coûts des matières mises au rebut sont ajoutés à ceux des produits finis.</span><span class="sxs-lookup"><span data-stu-id="c1fd0-116">When you select the Allocation method, costs from the scrapped materials are added to the finished goods.</span></span>  
7. <span data-ttu-id="c1fd0-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c1fd0-117">Click OK.</span></span>

## <a name="validate-calculation-results"></a><span data-ttu-id="c1fd0-118">Valider les résultats du calcul</span><span class="sxs-lookup"><span data-stu-id="c1fd0-118">Validate calculation results</span></span>
1. <span data-ttu-id="c1fd0-119">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="c1fd0-119">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="c1fd0-120">Cliquez sur Afficher la comparaison du coût.</span><span class="sxs-lookup"><span data-stu-id="c1fd0-120">Click View cost comparison.</span></span>
    * <span data-ttu-id="c1fd0-121">Après avoir terminé l'ordre de fabrication, vous pouvez comparer le prix de revient estimé par rapport au prix de revient réel afin d'obtenir une vue d'ensemble des écarts de production.</span><span class="sxs-lookup"><span data-stu-id="c1fd0-121">After you have ended the production order, you can compare the estimated cost price against the realized cost price to get an overview of the production variances.</span></span>  


