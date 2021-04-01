---
title: Répartir un ordre de travail
description: Cette rubrique explique comment répartir un ordre de travail dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetScheduledExecution
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cd9965ec8f3c3ff58f16b53abc8b9b114444946d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215008"
---
# <a name="dispatch-work-order"></a><span data-ttu-id="ea502-103">Répartir un ordre de travail</span><span class="sxs-lookup"><span data-stu-id="ea502-103">Dispatch work order</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="ea502-104">Vous pouvez planifier un ordre de travail ou des tâches d’un ordre de travail pour un collaborateur à l’aide de la fonctionnalité **Répartir**.</span><span class="sxs-lookup"><span data-stu-id="ea502-104">You can schedule one work order or work order jobs to one worker using the **Dispatch** functionality.</span></span>

1. <span data-ttu-id="ea502-105">Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="ea502-105">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="ea502-106">Sélectionnez l’ordre de travail dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ea502-106">Select the work order in the list.</span></span>

3. <span data-ttu-id="ea502-107">Sous l’onglet **Général**, cliquez sur **Répartir**.</span><span class="sxs-lookup"><span data-stu-id="ea502-107">On the **General** tab, click **Dispatch**.</span></span>

4. <span data-ttu-id="ea502-108">Dans la boîte de dialogue **Planifier un ordre de travail**, sélectionnez le collaborateur dans le champ **Collaborateur**.</span><span class="sxs-lookup"><span data-stu-id="ea502-108">In the **Schedule work order** dialog, select the worker in the **Worker** field.</span></span>

5. <span data-ttu-id="ea502-109">Dans le champ **Planifier les heures**, vous pouvez insérer des heures de travail prévues si jamais elles différent des heures de la prévision.</span><span class="sxs-lookup"><span data-stu-id="ea502-109">In the **Schedule hours** field, you can insert expected work hours in case expected work hours differ from forecast hours.</span></span>

6. <span data-ttu-id="ea502-110">Dans le champ **Début prévu**, vous pouvez modifier la date et l’heure de début, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="ea502-110">In the **Scheduled start** field, you can edit start date and time, if required.</span></span>

7. <span data-ttu-id="ea502-111">Si le processus de planification doit respecter des limites de capacité pour les ressources déjà planifiées avec d’autres tâches, assurez-vous que les boutons à bascule **Actif**, **Outil** et **Collaborateur** sont définis sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="ea502-111">If the scheduling process should observe capacity limitations regarding resources already scheduled on other jobs, make sure that the **Asset**, **Tool**, and **Worker** toggle buttons are set to **Yes**.</span></span> <span data-ttu-id="ea502-112">Si vous souhaitez afficher des informations détaillées sur le processus de planification, sélectionnez **Oui** sur le bouton à bascule **Détaillé**.</span><span class="sxs-lookup"><span data-stu-id="ea502-112">If you want to see detailed information about the scheduling process, select **Yes** on the **Verbose** toggle button.</span></span> <span data-ttu-id="ea502-113">Cela signifie que des informations détaillées sur les scores calculés sur l’ordre de travail sont affichées dans la fenêtre infos.</span><span class="sxs-lookup"><span data-stu-id="ea502-113">This means detailed information about the calculated scores on the work order is shown in the Infolog.</span></span>

8. <span data-ttu-id="ea502-114">Sélectionnez **Oui** sur le bouton à bascule **Ignorer la planification** pour ignorer les jours fermés dans le calendrier (s’applique à l’actif, au collaborateur et aux outils).</span><span class="sxs-lookup"><span data-stu-id="ea502-114">Select **Yes** on the **Ignore schedule** toggle button to ignore closed days in the calendar (applies to asset, worker, and tools).</span></span> <span data-ttu-id="ea502-115">Sélectionnez **Oui** sur le bouton à bascule **Ignore l’exécution planifiée** pour ignorer les limitations qui peuvent avoir été sélectionnées sur l’ordre de travail concernant la planification.</span><span class="sxs-lookup"><span data-stu-id="ea502-115">Select **Yes** on the **Ignore scheduled execution** toggle button to ignore limitations that may have been selected on the work order regarding scheduling.</span></span> 

    <span data-ttu-id="ea502-116">Pour obtenir des informations sur le paramétrage de l’exécution prévue, reportez à la section [Exécution prévue](../setup-for-work-orders/scheduled-execution.md).</span><span class="sxs-lookup"><span data-stu-id="ea502-116">For information on the setup of scheduled execution, see the [Scheduled execution](../setup-for-work-orders/scheduled-execution.md) section.</span></span>

9. <span data-ttu-id="ea502-117">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea502-117">Click **OK**.</span></span> <span data-ttu-id="ea502-118">L’état du cycle de vie du bon de travail est automatiquement mis à jour dans l’état du cycle de vie **Planifié** spécifié dans **Gestion des actifs** > **Paramétrage** > **Ordres de travail** > **Modèles de cycle de vie**.</span><span class="sxs-lookup"><span data-stu-id="ea502-118">The work order lifecycle state is automatically updated to the **Scheduled** lifecycle state specified **Asset management** > **Setup** > **Work orders** > **Lifecycle models**.</span></span>

<span data-ttu-id="ea502-119">L’illustration suivante présente un exemple de sélection d’expédition dans la boîte de dialogue **Planifier un ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="ea502-119">The figure below shows an example of dispatch selections in the **Schedule work order** dialog.</span></span>

![Figure 1](media/04-work-order-scheduling.png)

[!NOTE]
<span data-ttu-id="ea502-121">Si vous souhaitez supprimer le programme sur un ordre de travail, sélectionnez ce dernier dans **Tous les ordres de travail**, puis cliquez sur **Supprimer programme** dans l’onglet **Général**. N’oubliez pas de mettre à jour manuellement l’état du cycle de vie de l’ordre de travail si vous supprimez le programme.</span><span class="sxs-lookup"><span data-stu-id="ea502-121">If you want to delete the schedule on a work order, select the work order in **All work orders**, and then click **Delete schedule** on the **General** tab. Remember to manually update the work order lifecycle state if you delete the schedule.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]