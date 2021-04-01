---
title: Fenêtres Délai
description: Vous pouvez utiliser les fenêtres Délai pour optimiser la planification des lignes de commande de service.
author: ShylaThompson
manager: tfehr
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATimeAgreement
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 40ab085c84b54e15030e73fe43909e616dccbdcd
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259648"
---
# <a name="time-windows"></a><span data-ttu-id="5c2d6-103">Fenêtres Délai</span><span class="sxs-lookup"><span data-stu-id="5c2d6-103">Time windows</span></span>  

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5c2d6-104">Vous pouvez utiliser les fenêtres Délai pour optimiser la planification des lignes de commande de service.</span><span class="sxs-lookup"><span data-stu-id="5c2d6-104">You can use time windows to optimize the scheduling of service order lines.</span></span> <span data-ttu-id="5c2d6-105">Vous pouvez paramétrer le système afin qu’il crée automatiquement des commandes de service.</span><span class="sxs-lookup"><span data-stu-id="5c2d6-105">You can set up the system so that it automatically creates service orders.</span></span> <span data-ttu-id="5c2d6-106">En fonction des critères spécifiés dans une fenêtre Délai, vous pouvez connecter autant de lignes de commande de service que possible à aussi peu de commandes de service que possible.</span><span class="sxs-lookup"><span data-stu-id="5c2d6-106">Based on the criteria specified by a time window, you can connect as many service order lines as possible to as few service orders as possible.</span></span>

<span data-ttu-id="5c2d6-107">Les fenêtres Délai indiquent l’ampleur du déplacement d’une ligne de commande par rapport à sa date calculée.</span><span class="sxs-lookup"><span data-stu-id="5c2d6-107">Time windows specify how far a service order line can move from its calculated date.</span></span> <span data-ttu-id="5c2d6-108">La date calculée est la date à laquelle il est prévu que la ligne de commande de service soit générée.</span><span class="sxs-lookup"><span data-stu-id="5c2d6-108">The calculated date is the date when the service order line was scheduled to occur.</span></span> <span data-ttu-id="5c2d6-109">La date est basée sur son paramètre d’intervalle et la période de service que vous avez définis dans la page **Créer des commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="5c2d6-109">The date is based on its interval setting and the service period that you defined in the **Create service orders** page.</span></span> <span data-ttu-id="5c2d6-110">Pour définir une fenêtre Délai, utilisez les valeurs du tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="5c2d6-110">You define a time window by using the values in the following table.</span></span>

| <span data-ttu-id="5c2d6-111">Mode</span><span class="sxs-lookup"><span data-stu-id="5c2d6-111">Method</span></span> | <span data-ttu-id="5c2d6-112">Description</span><span class="sxs-lookup"><span data-stu-id="5c2d6-112">Description</span></span>                                                                                                                                                                                                                                                                                           |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5c2d6-113">Semaine</span><span class="sxs-lookup"><span data-stu-id="5c2d6-113">Week</span></span>   | <span data-ttu-id="5c2d6-114">Vous pouvez déplacer la date de la ligne de commande de service vers tout jour ouvré s’inscrivant la même semaine que la date calculée initiale.</span><span class="sxs-lookup"><span data-stu-id="5c2d6-114">The date that the service order line can be moved to any open day in the same week as the initial calculated date.</span></span>                                                                                                                                                                                    |
| <span data-ttu-id="5c2d6-115">Mois</span><span class="sxs-lookup"><span data-stu-id="5c2d6-115">Month</span></span>  | <span data-ttu-id="5c2d6-116">Vous pouvez déplacer la date de la ligne de commande de service vers tout jour ouvré s’inscrivant le même mois que la date calculée initiale.</span><span class="sxs-lookup"><span data-stu-id="5c2d6-116">The date that the service order line can be moved to any open day in the same month as the initial calculated date.</span></span> <span data-ttu-id="5c2d6-117">Par exemple, la date calculée pour une ligne de commande de service est le 15 février 2017.</span><span class="sxs-lookup"><span data-stu-id="5c2d6-117">For example, the calculated date for a service order line is February 15, 2017.</span></span> <span data-ttu-id="5c2d6-118">La ligne de commande de service peut être planifiée pour un jour de la semaine entre le 1er février et le 28 février 2017.</span><span class="sxs-lookup"><span data-stu-id="5c2d6-118">The service order line can be scheduled for any weekday between February 1 and February 28, 2017.</span></span> |
| <span data-ttu-id="5c2d6-119">Manuel</span><span class="sxs-lookup"><span data-stu-id="5c2d6-119">Manual</span></span> | <span data-ttu-id="5c2d6-120">Vous définissez le nombre maximal de jours avant ou après la date calculée initiale où la ligne de commande de service peut être déplacée.</span><span class="sxs-lookup"><span data-stu-id="5c2d6-120">You define the maximum number of days before or after the initial calculated date that the service order line can be moved.</span></span>                                                                                                                                                                           |

<span data-ttu-id="5c2d6-121">Si vous n’indiquez aucune fenêtre Délai pour une ligne d’accord de service, la ligne de commande de service dérivée de l’accord de service doit être exécutée à la date précise planifiée initialement.</span><span class="sxs-lookup"><span data-stu-id="5c2d6-121">If you do not specify a time window for a service agreement line, the service order line that is derived from the service agreement must be on the exact date for which it was originally scheduled.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5c2d6-122">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="5c2d6-122">Related topics</span></span>

[<span data-ttu-id="5c2d6-123">Création de fenêtres Délai</span><span class="sxs-lookup"><span data-stu-id="5c2d6-123">Create time windows</span></span>](create-time-windows.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]