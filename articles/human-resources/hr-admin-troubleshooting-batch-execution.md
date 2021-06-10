---
title: Réinitialiser les traitements par lots bloqués
description: Cette rubrique explique comment résoudre les problèmes liés aux traitements par lots bloqués.
author: andreabichsel
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: d0b12908993070a41d21ac57d6fb504fc6e3b06a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053513"
---
# <a name="reset-stuck-batch-jobs"></a><span data-ttu-id="0ed55-103">Réinitialiser les traitements par lots bloqués</span><span class="sxs-lookup"><span data-stu-id="0ed55-103">Reset stuck batch jobs</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a><span data-ttu-id="0ed55-104">Sortie</span><span class="sxs-lookup"><span data-stu-id="0ed55-104">Issue</span></span>

<span data-ttu-id="0ed55-105">Microsoft Dynamics 365 Human Resources peut rencontrer des problèmes avec des traitements par lots bloqués dans un état **Exécution** ou **Annulation** et qui n’aboutissent pas.</span><span class="sxs-lookup"><span data-stu-id="0ed55-105">Microsoft Dynamics 365 Human Resources can experience issues with batch jobs that are stuck in either an **Executing** or **Canceling** state and don't complete.</span></span>

## <a name="resolution"></a><span data-ttu-id="0ed55-106">Résolution</span><span class="sxs-lookup"><span data-stu-id="0ed55-106">Resolution</span></span>

<span data-ttu-id="0ed55-107">Lorsqu’un traitement par lots est bloqué dans un état **Exécution** ou **Annulation**, vous pouvez réinitialiser le statut en forçant l’annulation de la tâche.</span><span class="sxs-lookup"><span data-stu-id="0ed55-107">When a batch job is stuck in an **Executing** or **Canceling** state, you can reset the status by forcing the cancellation of the job.</span></span> <span data-ttu-id="0ed55-108">Une fois que vous l’avez annulé, vous pouvez réinitialiser le traitement par lots en le définissant sur un statut **En attente**.</span><span class="sxs-lookup"><span data-stu-id="0ed55-108">After you cancel it, you can reset the batch job by setting it to a **Waiting** status.</span></span> <span data-ttu-id="0ed55-109">Il sera ensuite repris pour exécution lors de la prochaine exécution planifiée de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="0ed55-109">It will then be picked up again for execution in the next scheduled batch run.</span></span>

1. <span data-ttu-id="0ed55-110">Dans l’espace de travail **Administration système**, sélectionnez la page **Liens** et sélectionnez **Traitements par lots**.</span><span class="sxs-lookup"><span data-stu-id="0ed55-110">In the **System administration** workspace, select the **Links** page, and select **Batch jobs**.</span></span>

2. <span data-ttu-id="0ed55-111">Sur la page de liste **Traitement par lots**, sélectionnez la tâche à réinitialiser.</span><span class="sxs-lookup"><span data-stu-id="0ed55-111">On the **Batch job** list page, select the job that needs to be reset.</span></span>

3. <span data-ttu-id="0ed55-112">Sur le ruban d’action, sélectionnez **Forcer l’annulation** et confirmez l’action.</span><span class="sxs-lookup"><span data-stu-id="0ed55-112">On the action ribbon, select **Force cancel**, and confirm the action.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0ed55-113">L’action **Forcer l’annulation** n’est disponible que lorsque le traitement par lots sélectionné a un statut **Exécution** ou **Annulation** et qu’aucun processus d’exécution ou d’annulation de traitement par lots n’est en cours d’exécution pour la tâche.</span><span class="sxs-lookup"><span data-stu-id="0ed55-113">The **Force cancel** action is only available when the selected batch job has a status of either **Executing** or **Canceling**, and no batch execution or cancellation processes are running for the job.</span></span>

4. <span data-ttu-id="0ed55-114">Sur le ruban d’action, sélectionnez **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="0ed55-114">On the action ribbon, select **Change status**.</span></span>

5. <span data-ttu-id="0ed55-115">Sur la page **Sélectionner un nouveau statut**, sélectionnez **En attente**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ed55-115">On the **Select new status** page, select **Waiting**, and then select **OK**.</span></span>

   ![Sélectionner un nouveau statut de traitement par lots](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a><span data-ttu-id="0ed55-117">Voir également :</span><span class="sxs-lookup"><span data-stu-id="0ed55-117">See also</span></span>

[<span data-ttu-id="0ed55-118">Optimiser les performances en planifiant des traitements par lots en dehors des heures d’ouverture</span><span class="sxs-lookup"><span data-stu-id="0ed55-118">Optimize performance by scheduling batch jobs after hours</span></span>](hr-admin-troubleshooting-batch-jobs.md)<br>
[<span data-ttu-id="0ed55-119">Optimiser les performances grâce aux tâches automatiques de nettoyage</span><span class="sxs-lookup"><span data-stu-id="0ed55-119">Optimize performance with auto cleanup tasks</span></span>](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
