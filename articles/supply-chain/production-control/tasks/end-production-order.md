---
title: Terminer un ordre de fabrication
description: Cette procédure permet d'indiquer comment mettre fin à un ordre de fabrication.
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cb84d3b1908d6be889a49f7386de876cb52141ab
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149042"
---
# <a name="end-a-production-order"></a><span data-ttu-id="87db1-103">Terminer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="87db1-103">End a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="87db1-104">Cette procédure permet d'indiquer comment mettre fin à un ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="87db1-104">This procedure shows how to end a production order.</span></span> <span data-ttu-id="87db1-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="87db1-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="87db1-106">Il s'agit de la dernière des sept procédures expliquant le cycle de vie de l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="87db1-106">This is the final procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="end-a-production-order"></a><span data-ttu-id="87db1-107">Terminer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="87db1-107">End a production order</span></span>
1. <span data-ttu-id="87db1-108">Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="87db1-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="87db1-109">Sélectionnez un ordre de fabrication dont le statut est Déclaré terminé.</span><span class="sxs-lookup"><span data-stu-id="87db1-109">Select a production order that has the status Reported as finished.</span></span>  
2. <span data-ttu-id="87db1-110">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="87db1-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="87db1-111">Cliquez sur Fin.</span><span class="sxs-lookup"><span data-stu-id="87db1-111">Click End.</span></span>
    * <span data-ttu-id="87db1-112">Dans cette page, vous pouvez confirmer que vous voulez mettre fin à l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="87db1-112">On this page, you can confirm that you want to end the production order.</span></span>  
4. <span data-ttu-id="87db1-113">Cliquez sur l'onglet Général.</span><span class="sxs-lookup"><span data-stu-id="87db1-113">Click the General tab.</span></span>
5. <span data-ttu-id="87db1-114">Entrez une date dans le champ Date.</span><span class="sxs-lookup"><span data-stu-id="87db1-114">In the Date field, enter a date.</span></span>
6. <span data-ttu-id="87db1-115">Dans le champ Mode de mise au rebut, sélectionnez « Répartition ».</span><span class="sxs-lookup"><span data-stu-id="87db1-115">In the Scrap method field, select 'Allocation'.</span></span>
    * <span data-ttu-id="87db1-116">Lorsque vous sélectionnez la méthode de répartition, les coûts des matières mises au rebut sont ajoutés à ceux des produits finis.</span><span class="sxs-lookup"><span data-stu-id="87db1-116">When you select the Allocation method, costs from the scrapped materials are added to the finished goods.</span></span>  
7. <span data-ttu-id="87db1-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="87db1-117">Click OK.</span></span>

## <a name="validate-calculation-results"></a><span data-ttu-id="87db1-118">Valider les résultats du calcul</span><span class="sxs-lookup"><span data-stu-id="87db1-118">Validate calculation results</span></span>
1. <span data-ttu-id="87db1-119">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="87db1-119">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="87db1-120">Cliquez sur Afficher la comparaison du coût.</span><span class="sxs-lookup"><span data-stu-id="87db1-120">Click View cost comparison.</span></span>
    * <span data-ttu-id="87db1-121">Après avoir terminé l'ordre de fabrication, vous pouvez comparer le prix de revient estimé par rapport au prix de revient réel afin d'obtenir une vue d'ensemble des écarts de production.</span><span class="sxs-lookup"><span data-stu-id="87db1-121">After you have ended the production order, you can compare the estimated cost price against the realized cost price to get an overview of the production variances.</span></span>  
