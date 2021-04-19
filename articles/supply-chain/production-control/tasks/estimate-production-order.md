---
title: Estimer un ordre de fabrication
description: Vous pouvez exécuter cette procédure en utilisant les données de démonstration de la société USMF ou utiliser vos propres données.
author: johanhoffmann
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8544f468b7870b265b0c206471ad88e219258a03
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828656"
---
# <a name="estimate-a-production-order"></a><span data-ttu-id="143d1-103">Estimer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="143d1-103">Estimate a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="143d1-104">Vous pouvez exécuter cette procédure en utilisant les données de démonstration de la société USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="143d1-104">You can run this procedure by using the USMF demo data company or your own data set.</span></span> <span data-ttu-id="143d1-105">Dans les deux cas, vous devez avoir un ordre de fabrication en cours dont le statut est Créé.</span><span class="sxs-lookup"><span data-stu-id="143d1-105">In both cases, you need to have an open production order that has the Created status.</span></span> <span data-ttu-id="143d1-106">Il s’agit de la deuxième des sept procédures expliquant le cycle de vie de l’ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="143d1-106">This is the second procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="estimate-a-production-order"></a><span data-ttu-id="143d1-107">Estimer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="143d1-107">Estimate a production order</span></span>
1. <span data-ttu-id="143d1-108">Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="143d1-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="143d1-109">Sélectionnez une commande dont le statut est Créé dans la grille.</span><span class="sxs-lookup"><span data-stu-id="143d1-109">Select an order that has the Created status in the grid.</span></span>
3. <span data-ttu-id="143d1-110">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="143d1-110">On the Action Pane, click Production order.</span></span>
4. <span data-ttu-id="143d1-111">Cliquez sur Estimer.</span><span class="sxs-lookup"><span data-stu-id="143d1-111">Click Estimate.</span></span>
    * <span data-ttu-id="143d1-112">Dans cette étape, les coûts estimés d’un ordre de fabrication unique sont calculés.</span><span class="sxs-lookup"><span data-stu-id="143d1-112">In this step, the estimated costs of a single production order is calculated.</span></span>   
5. <span data-ttu-id="143d1-113">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="143d1-113">Click OK.</span></span>

## <a name="view-the-calculation-details"></a><span data-ttu-id="143d1-114">Afficher les détails du calcul</span><span class="sxs-lookup"><span data-stu-id="143d1-114">View the calculation details</span></span>
1. <span data-ttu-id="143d1-115">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="143d1-115">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="143d1-116">Cliquez sur Afficher les détails du calcul.</span><span class="sxs-lookup"><span data-stu-id="143d1-116">Click View calculation details.</span></span>
    * <span data-ttu-id="143d1-117">Cette page affiche la répartition des coûts.</span><span class="sxs-lookup"><span data-stu-id="143d1-117">This page displays the cost breakdown.</span></span> <span data-ttu-id="143d1-118">Par exemple, vous pouvez afficher le prix de revient total par unité pour le produit fini dans la première ligne.</span><span class="sxs-lookup"><span data-stu-id="143d1-118">For example, you can view the total cost price per unit for the finished product in the first row.</span></span> <span data-ttu-id="143d1-119">Les lignes suivantes contiennent les coûts correspondant à la nomenclature, à la gamme de production, et aux coûts indirects.</span><span class="sxs-lookup"><span data-stu-id="143d1-119">The subsequent rows contain costs according to the bill of materials, production route, and indirect costs.</span></span>  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]