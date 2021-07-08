---
title: Vous recevez une erreur lors de l’exécution du moteur de planification générale intégré
description: Lorsque vous exécutez le moteur de planification générale intégré obsolète, vous recevez un message d’erreur.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: Dialog_ReqCalcScheduleItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9c950292a4f43319d21a7deafdfb341b7bef15d8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294075"
---
# <a name="you-receive-an-error-when-running-the-built-in-master-planning-engine"></a><span data-ttu-id="741bd-103">Vous recevez une erreur lors de l’exécution du moteur de planification générale intégré</span><span class="sxs-lookup"><span data-stu-id="741bd-103">You receive an error when running the built-in master planning engine</span></span>

<span data-ttu-id="741bd-104">Code d’erreur : ReqCalcScheduleItemTablePlanningOptimizationFitError</span><span class="sxs-lookup"><span data-stu-id="741bd-104">Error code: ReqCalcScheduleItemTablePlanningOptimizationFitError</span></span>

## <a name="symptoms"></a><span data-ttu-id="741bd-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="741bd-105">Symptoms</span></span>

<span data-ttu-id="741bd-106">Lorsque vous exécutez la planification en utilisant le moteur de planification générale intégré obsolète, vous recevez le message d’erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="741bd-106">When you run master planning by using the deprecated built-in master planning engine, you receive the following error message:</span></span>

> <span data-ttu-id="741bd-107">Vous recevez ce message d’erreur car le moteur de planification intégré a été utilisé pour les scénarios pris en charge par l’Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="741bd-107">You receive this error message because the built-in master planning engine was used for scenarios supported by Planning Optimization.</span></span> <span data-ttu-id="741bd-108">Vous devez migrer vers l’Optimisation de la planification maintenant, car la planification intégrée actuelle sera obsolète.</span><span class="sxs-lookup"><span data-stu-id="741bd-108">You should migrate to Planning Optimization now, as the current built-in master planning will be deprecated.</span></span> <span data-ttu-id="741bd-109">Notez que ce cycle de planification s’est terminé avec succès.</span><span class="sxs-lookup"><span data-stu-id="741bd-109">Note that this master planning run did complete successfully.</span></span> <span data-ttu-id="741bd-110">Si votre migration a de fortes dépendances sur les fonctionnalités en attente, une exception à l’utilisation continue du moteur de planification intégré peut être demandée.</span><span class="sxs-lookup"><span data-stu-id="741bd-110">In case your migration has strong dependencies on pending features, an exception to continued usage of the built-in master planning engine can be requested.</span></span> <span data-ttu-id="741bd-111">Remplissez le questionnaire suivant pour commencer et, le cas échéant, demander une exception pour la migration vers l’Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="741bd-111">Please complete the following questionnaire to get started and, if relevant, request an exception from migration to Planning Optimization.</span></span> [<span data-ttu-id="741bd-112">Questionnaire pour la migration vers l’optimisation de la planification et les exceptions</span><span class="sxs-lookup"><span data-stu-id="741bd-112">Planning Optimization migration and exception questionnaire</span></span>](https://go.microsoft.com/fwlink/?linkid=2144962)

## <a name="cause"></a><span data-ttu-id="741bd-113">Cause</span><span class="sxs-lookup"><span data-stu-id="741bd-113">Cause</span></span>

<span data-ttu-id="741bd-114">Si vous exécutez la planification et n’utilisez pas les fonctionnalités de contrôle de la production, vous devez envisager de migrer vers l’Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="741bd-114">If you run planning and don't use production control features, you should consider migrating to Planning Optimization.</span></span> <span data-ttu-id="741bd-115">Le moteur de planification générale intégré est en cours d’abandon.</span><span class="sxs-lookup"><span data-stu-id="741bd-115">The built-in master planning engine is being deprecated.</span></span> <span data-ttu-id="741bd-116">Par conséquent, si vous souhaitez continuer à l’utiliser sans recevoir le message d’erreur, vous devez demander une exception auprès de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="741bd-116">Therefore, if you want to continue to use it without receiving the error message, you must apply for an exception from Microsoft.</span></span>

## <a name="resolution"></a><span data-ttu-id="741bd-117">Résolution</span><span class="sxs-lookup"><span data-stu-id="741bd-117">Resolution</span></span>

<span data-ttu-id="741bd-118">Pour plus d’informations sur la migration vers l’optimisation de la planification ou sur la demande d’exception afin de pouvoir continuer à utiliser le moteur de planification générale intégré obsolète, consultez [Migration vers l’Optimisation de la planification pour la planification](/dynamics365/supply-chain/master-planning/new-master-planning-engine).</span><span class="sxs-lookup"><span data-stu-id="741bd-118">For more information about how to migrate to Planning Optimization, or how to apply for an exception so that you can continue to use the deprecated built-in planning engine instead, see [Migration to Planning Optimization for master planning](/dynamics365/supply-chain/master-planning/new-master-planning-engine).</span></span>
