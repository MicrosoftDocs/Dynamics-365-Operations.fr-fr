---
title: Stades de commande de service
description: En définissant les stades d'une commande de service et en les affectant aux collaborateurs, vous contrôlez le flux d'une commande de service via les tâches attribuées aux différents personnes dans l'organisation du service.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAStageTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d126b68bea8d2083fcf1d08e168b9ead1511b25c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001247"
---
# <a name="service-order-stages"></a><span data-ttu-id="3b179-103">Stades de commande de service</span><span class="sxs-lookup"><span data-stu-id="3b179-103">Service order stages</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="3b179-104">Vous pouvez définir des stades pour une commande de service afin de définir les tâches qui doivent être effectuées, l'ordre dans lequel elles sont effectuées, et les collaborateurs chargés de les exécuter.</span><span class="sxs-lookup"><span data-stu-id="3b179-104">You can set up stages for a service order to define the tasks that must be completed, the order in which they are completed, and the workers who are responsible for completing them.</span></span> <span data-ttu-id="3b179-105">En définissant les stades d'une commande de service et en les affectant aux collaborateurs, vous pouvez contrôler le flux d'une commande de service via les tâches attribuées aux différents personnes dans l'organisation du service.</span><span class="sxs-lookup"><span data-stu-id="3b179-105">By defining the stages for a service order and assigning them to workers, you can control the flow of a service order through the tasks that various people perform in the service organization.</span></span> <span data-ttu-id="3b179-106">L'ordre des stades doit inclure un stade initial.</span><span class="sxs-lookup"><span data-stu-id="3b179-106">The sequence of stages must include an initial stage.</span></span>

<span data-ttu-id="3b179-107">Vous pouvez également définir les actions autorisées à chaque stade.</span><span class="sxs-lookup"><span data-stu-id="3b179-107">You can also define the actions that are permitted at each stage.</span></span> <span data-ttu-id="3b179-108">Par exemple, si vous désactivez la case à cocher **Valider** pour tous les stades à l'exception du dernier, vous empêchez la validation des commandes de service avant que celles-ci ne soient passées par tous les stades de la séquence.</span><span class="sxs-lookup"><span data-stu-id="3b179-108">For example, if you clear the **Post** check box for all stages except the final stage, you prevent any service orders from being posted before the service orders are processed through the complete sequence of stages.</span></span>

## <a name="branching-in-service-order-stages"></a><span data-ttu-id="3b179-109">Création de branches dans les stades de commande de service</span><span class="sxs-lookup"><span data-stu-id="3b179-109">Branching in service order stages</span></span>

<span data-ttu-id="3b179-110">Lorsque vous paramétrez un stade de service, vous pouvez créer des options multiples, ou branches, pouvant être sélectionnées pour le stade de service suivant.</span><span class="sxs-lookup"><span data-stu-id="3b179-110">When you set up a service stage, you can create multiple options, or branches, to select from for the next service stage.</span></span> <span data-ttu-id="3b179-111">Toutes les branches que vous créez sont disponibles à la sélection dès que le stade initial est terminé.</span><span class="sxs-lookup"><span data-stu-id="3b179-111">All the branches that you create are available to select from when the initial stage is completed.</span></span> <span data-ttu-id="3b179-112">Par exemple, vous paramétrez la **Planification** comme premier stade.</span><span class="sxs-lookup"><span data-stu-id="3b179-112">For example, you set up **Planning** as an initial stage.</span></span> <span data-ttu-id="3b179-113">Vous créez ensuite deux stades nommés **En cours** et **Annuler**, puis vous sélectionnez **Planification** comme parent.</span><span class="sxs-lookup"><span data-stu-id="3b179-113">You create two stages named **In process** and **Cancel**, and then select **Planning** as the parent for them.</span></span> <span data-ttu-id="3b179-114">Vous affectez ensuite le stade **Planification** à la commande client.</span><span class="sxs-lookup"><span data-stu-id="3b179-114">You assign the **Planning** stage to sales order.</span></span> <span data-ttu-id="3b179-115">Lorsque la phase de planification de la commande client est terminée, vous pouvez sélectionner le stade **En cours** si la commande client est prête pour le traitement, ou le stade **Annuler** si la commande client est annulée.</span><span class="sxs-lookup"><span data-stu-id="3b179-115">When the planning stage for the sales order is completed, you can select the **In process** stage if the sales order is ready to work on, or you can select the **Cancel** stage if the sales order is canceled.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b179-116">Voir également :</span><span class="sxs-lookup"><span data-stu-id="3b179-116">See also</span></span>

[<span data-ttu-id="3b179-117">Paramétrer des stades de commande de service</span><span class="sxs-lookup"><span data-stu-id="3b179-117">Set up service order stages</span></span>](set-up-service-order-stages.md)

[<span data-ttu-id="3b179-118">Modifier le stade de la commande de service</span><span class="sxs-lookup"><span data-stu-id="3b179-118">Change the service order stage</span></span>](change-service-order-stage.md)

  


