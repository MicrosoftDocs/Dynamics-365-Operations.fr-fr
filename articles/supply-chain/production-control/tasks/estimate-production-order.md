---
title: Estimer un ordre de fabrication
description: Vous pouvez exécuter cette procédure en utilisant les données de démonstration de la société USMF ou utiliser vos propres données.
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
ms.openlocfilehash: 8274e390a177f51649f5cad70ef7ad5bd50a8830
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558471"
---
# <a name="estimate-a-production-order"></a><span data-ttu-id="054be-103">Estimer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="054be-103">Estimate a production order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="054be-104">Vous pouvez exécuter cette procédure en utilisant les données de démonstration de la société USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="054be-104">You can run this procedure by using the USMF demo data company or your own data set.</span></span> <span data-ttu-id="054be-105">Dans les deux cas, vous devez avoir un ordre de fabrication en cours dont le statut est Créé.</span><span class="sxs-lookup"><span data-stu-id="054be-105">In both cases, you need to have an open production order that has the Created status.</span></span> <span data-ttu-id="054be-106">Il s'agit de la deuxième des sept procédures expliquant le cycle de vie de l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="054be-106">This is the second procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="estimate-a-production-order"></a><span data-ttu-id="054be-107">Estimer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="054be-107">Estimate a production order</span></span>
1. <span data-ttu-id="054be-108">Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="054be-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="054be-109">Sélectionnez une commande dont le statut est Créé dans la grille.</span><span class="sxs-lookup"><span data-stu-id="054be-109">Select an order that has the Created status in the grid.</span></span>
3. <span data-ttu-id="054be-110">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="054be-110">On the Action Pane, click Production order.</span></span>
4. <span data-ttu-id="054be-111">Cliquez sur Estimer.</span><span class="sxs-lookup"><span data-stu-id="054be-111">Click Estimate.</span></span>
    * <span data-ttu-id="054be-112">Dans cette étape, les coûts estimés d'un ordre de fabrication unique sont calculés.</span><span class="sxs-lookup"><span data-stu-id="054be-112">In this step, the estimated costs of a single production order is calculated.</span></span>   
5. <span data-ttu-id="054be-113">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="054be-113">Click OK.</span></span>

## <a name="view-the-calculation-details"></a><span data-ttu-id="054be-114">Afficher les détails du calcul</span><span class="sxs-lookup"><span data-stu-id="054be-114">View the calculation details</span></span>
1. <span data-ttu-id="054be-115">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="054be-115">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="054be-116">Cliquez sur Afficher les détails du calcul.</span><span class="sxs-lookup"><span data-stu-id="054be-116">Click View calculation details.</span></span>
    * <span data-ttu-id="054be-117">Cette page affiche la répartition des coûts.</span><span class="sxs-lookup"><span data-stu-id="054be-117">This page displays the cost breakdown.</span></span> <span data-ttu-id="054be-118">Par exemple, vous pouvez afficher le prix de revient total par unité pour le produit fini dans la première ligne.</span><span class="sxs-lookup"><span data-stu-id="054be-118">For example, you can view the total cost price per unit for the finished product in the first row.</span></span> <span data-ttu-id="054be-119">Les lignes suivantes contiennent les coûts correspondant à la nomenclature, à la gamme de production, et aux coûts indirects.</span><span class="sxs-lookup"><span data-stu-id="054be-119">The subsequent rows contain costs according to the bill of materials, production route, and indirect costs.</span></span>  
