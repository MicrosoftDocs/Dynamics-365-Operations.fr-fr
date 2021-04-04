---
title: Événements d’application d’entrepôt
description: Cette rubrique décrit le traitement des événements d’application d’entreposage utilisé pour traiter les messages d’événement de l’application d’entreposage dans le cadre d’un traitement par lots.
author: perlynne
manager: tfehr
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 0bafcbd5306860cb80d6e813aabf83853a9011c1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248641"
---
# <a name="warehouse-app-event-processing"></a><span data-ttu-id="18d91-103">Traitement des événements de l’application d’entreposage</span><span class="sxs-lookup"><span data-stu-id="18d91-103">Warehouse app event processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="18d91-104">Les traitements par lots exécutés dans Supply Chain Management peuvent utiliser les données d’une file d’attente pour traiter les événements émis par l’application d’entreposage afin de réagir selon les besoins aux événements signalés.</span><span class="sxs-lookup"><span data-stu-id="18d91-104">Batch jobs running in Supply Chain Management can use data from a queue for processing events issued by the warehouse app to react as needed to the signaled events.</span></span> <span data-ttu-id="18d91-105">Cette fonctionnalité ajoute les événements pertinents à la file d’attente en réponse à certains types d’actions entreprises par les employés utilisant l’application.</span><span class="sxs-lookup"><span data-stu-id="18d91-105">This feature add relevant events to the queue in response to certain types of actions taken by workers using the app.</span></span> <span data-ttu-id="18d91-106">Un exemple est l’utilisation de la fonction **Créer et traiter des ordres de transfert depuis l’application d’entreposage** ; l’en-tête et les lignes de l’ordre de transfert sont créés et mis à jour dans le back-end lorsque le système exécute le traitement par lots **Traiter les événements de l’application d’entreposage**.</span><span class="sxs-lookup"><span data-stu-id="18d91-106">An example is when using the **Create and process transfer orders from the warehouse app** feature, the transfer order header and lines get created and updated in the back end when the system is running the **Process warehouse app events** batch job.</span></span>

## <a name="enable-the-process-warehouse-app-events-feature"></a><span data-ttu-id="18d91-107">Activer la fonction Traiter les événements de l’application d’entreposage</span><span class="sxs-lookup"><span data-stu-id="18d91-107">Enable the Process warehouse app events feature</span></span>

<span data-ttu-id="18d91-108">Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="18d91-108">Before you can use this feature, it must be enabled on your system.</span></span> <span data-ttu-id="18d91-109">Les administrateurs peuvent utiliser les paramètres de la page de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="18d91-109">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) page to check the feature status and enable it if needed.</span></span> <span data-ttu-id="18d91-110">La fonction Traiter les événements de l’application d’entreposage comprend les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="18d91-110">The Process warehouse app events feature is listed as:</span></span>

- <span data-ttu-id="18d91-111">**Module** - Gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="18d91-111">**Module** - Warehouse management</span></span>
- <span data-ttu-id="18d91-112">**Nom de la fonction** - Traiter les événements de l’application d’entreposage</span><span class="sxs-lookup"><span data-stu-id="18d91-112">**Feature name** - Process warehouse app events</span></span>

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a><span data-ttu-id="18d91-113">Configurer un traitement par lots pour traiter les événements de l’application d’entreposage</span><span class="sxs-lookup"><span data-stu-id="18d91-113">Set up a batch job to process warehouse app events</span></span>

### <a name="process-warehouse-app-events"></a><span data-ttu-id="18d91-114">Traiter les événements d’application d’entrepôt</span><span class="sxs-lookup"><span data-stu-id="18d91-114">Process warehouse app events</span></span>

<span data-ttu-id="18d91-115">Configurez un traitement par lots planifié pour traiter les événements de l’application d’entreposage pour la création de l’ordre de transfert et les mises à jour des lignes.</span><span class="sxs-lookup"><span data-stu-id="18d91-115">Set up a scheduled batch job to process the warehouse app events for the transfer order creation and line updates.</span></span>

1. <span data-ttu-id="18d91-116">Accédez à **Gestion des entrepôts \> Tâches périodiques \> Traiter les événements de l’application d’entreposage**.</span><span class="sxs-lookup"><span data-stu-id="18d91-116">Go to **Warehouse management \> Periodic tasks \> Process warehouse app events**.</span></span>
1. <span data-ttu-id="18d91-117">La boîte de dialogue Traiter les événements de l’application d’entreposage s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="18d91-117">The Process warehouse app events dialog box opens.</span></span> <span data-ttu-id="18d91-118">Développez l’organisateur **Exécuter en arrière-plan** et définissez **Traitement par lots** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="18d91-118">Expand the **Run in background** FastTab and set **Batch processing** to **Yes**.</span></span>
1. <span data-ttu-id="18d91-119">Dans l’organisateur **Exécuter en arrière-plan**, sélectionnez **Récurrence**.</span><span class="sxs-lookup"><span data-stu-id="18d91-119">On the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="18d91-120">La boîte de dialogue **Définir la récurrence** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="18d91-120">The **Define recurrence** dialog box opens.</span></span> <span data-ttu-id="18d91-121">Définissez le programme d’exécution selon les besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="18d91-121">Set the run schedule as needed for your business.</span></span>
1. <span data-ttu-id="18d91-122">Sélectionnez **OK** pour revenir à la boîte de dialogue **Traiter les événements de l’application d’entreposage**.</span><span class="sxs-lookup"><span data-stu-id="18d91-122">Select **OK** to return to the **Process warehouse app events** dialog box.</span></span>
1. <span data-ttu-id="18d91-123">Sélectionnez **OK** dans la boîte de dialogue **Traiter les événements de l’application d’entreposage** pour ajouter le traitement par lots à la file d’attente des traitements par lots.</span><span class="sxs-lookup"><span data-stu-id="18d91-123">Select **OK** in the **Process warehouse app events** dialog box to add the batch job to the batch queue.</span></span>

## <a name="query-warehouse-app-events"></a><span data-ttu-id="18d91-124">Interroger les événements de l’application d’entreposage</span><span class="sxs-lookup"><span data-stu-id="18d91-124">Query warehouse app events</span></span>

<span data-ttu-id="18d91-125">Vous pouvez afficher la file d’attente et les messages d’événements générés par l’application d’entreposage en accédant à **Gestion des entrepôts \> Recherches et états \> Journaux des appareils mobiles \> Événements de l’application d’entreposage**.</span><span class="sxs-lookup"><span data-stu-id="18d91-125">You can view the event queue and events messages generated by the warehouse app by going to **Warehouse management \> Inquiries and reports \> Mobile device logs \> Warehouse app events**.</span></span>

## <a name="the-standard-event-queue-process"></a><span data-ttu-id="18d91-126">Le processus de file d’attente d’événements standard</span><span class="sxs-lookup"><span data-stu-id="18d91-126">The standard event queue process</span></span>

<span data-ttu-id="18d91-127">La file d’attente des événements de l’application d’entreposage est généralement utilisée avec le flux décrit ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="18d91-127">The warehouse apps events queue will typically be used with the following described flow:</span></span>

1. <span data-ttu-id="18d91-128">Un événement est ajouté à la file d’attente avec un message d’événement.</span><span class="sxs-lookup"><span data-stu-id="18d91-128">An event gets added to the queue  with an event message.</span></span> <span data-ttu-id="18d91-129">Le nouveau message a initialement un état d’événement de **En attente**, ce qui signifie que le traitement par lots **Traiter les événements de l’application d’entreposage** ne sélectionnera pas ce message et ne le traitera pas.</span><span class="sxs-lookup"><span data-stu-id="18d91-129">The new message initially has an Event state of **Waiting**, which means that the **Process warehouse app events** batch job will not pick up and process this message.</span></span>
1. <span data-ttu-id="18d91-130">Dès que l’état du message sera actualisé en **En file d’attente**, le traitement par lots **Traiter les événements de l’application d’entreposage** sélectionnera et traitera l’événement.</span><span class="sxs-lookup"><span data-stu-id="18d91-130">As soon as the message state is updated to **Queued**, the **Process warehouse app** events batch job will pick up and process the event.</span></span>
1. <span data-ttu-id="18d91-131">Le traitement par lots actualise les états d’événement soit en **Terminé**, soit en **Échoué**, selon que le processus demandé était possible.</span><span class="sxs-lookup"><span data-stu-id="18d91-131">The batch job updates the event states to either **Completed** or **Failed**, depending on whether the requested process was possible.</span></span>
1. <span data-ttu-id="18d91-132">Lorsque tous les messages d’événements associés sont **Terminés**, l’événement est supprimé de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="18d91-132">When all the related event messages are **Completed**, the event is deleted from the queue.</span></span>

 <span data-ttu-id="18d91-133">Pour voir un exemple détaillé, voir [Créer un ordre de transfert à partir du processus de l’application d’entreposage](create-transfer-order-from-warehouse-app.md).</span><span class="sxs-lookup"><span data-stu-id="18d91-133">For a detailed example, see [Create transfer order from warehouse app process](create-transfer-order-from-warehouse-app.md).</span></span>

## <a name="handle-event-errors"></a><span data-ttu-id="18d91-134">Gérer les erreurs d’événement</span><span class="sxs-lookup"><span data-stu-id="18d91-134">Handle event errors</span></span>

<span data-ttu-id="18d91-135">Dans le cadre du traitement des événements d’entrepôt, l’activité de message demandée peut ne pas recevoir de processus du traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="18d91-135">As part of the warehouse event processing, the requested message activity may not receive processes from the batch job.</span></span> <span data-ttu-id="18d91-136">Dans ce cas, le message d’événement sera changé en **Échoué**.</span><span class="sxs-lookup"><span data-stu-id="18d91-136">In this case, the event message will change to **Failed**.</span></span> <span data-ttu-id="18d91-137">Vous pouvez utiliser les informations du **Journal des traitements par lots** pour savoir pourquoi et prendre les mesures nécessaires pour corriger les éventuels problèmes.</span><span class="sxs-lookup"><span data-stu-id="18d91-137">You can use the **Batch log** information to learn why and take needed action to correct any problems.</span></span>

<span data-ttu-id="18d91-138">Pour voir un exemple détaillé, voir [Créer un ordre de transfert à partir de l’application d’entreposage](create-transfer-order-from-warehouse-app.md).</span><span class="sxs-lookup"><span data-stu-id="18d91-138">For a detailed example, see [Create transfer order from warehouse app](create-transfer-order-from-warehouse-app.md).</span></span>

<span data-ttu-id="18d91-139">Pour réinitialiser un message d’événement d’application d’entreposage ayant échoué :</span><span class="sxs-lookup"><span data-stu-id="18d91-139">To reset a failed warehouse app event message:</span></span>

1. <span data-ttu-id="18d91-140">Accédez à **Gestion des entrepôts \> Recherches et états \> Journaux des appareils mobiles \> Événements de l’application d’entreposage**.</span><span class="sxs-lookup"><span data-stu-id="18d91-140">Go to **Warehouse management \> Inquiries and reports \> Mobile device logs \> Warehouse app events**.</span></span>
1. <span data-ttu-id="18d91-141">Dans l’organisateur **Messages d’événement de l’application d’entreposage**, recherchez et sélectionnez un événement pertinent qui affiche **Échoué** dans la colonne **État de l’événement**.</span><span class="sxs-lookup"><span data-stu-id="18d91-141">On the **Warehouse app event messages** FastTab, find and select a relevant event that is showing **Failed** in the **Event state** column.</span></span>
1. <span data-ttu-id="18d91-142">Sélectionnez **Réinitialiser** dans la barre d’outils **Messages d’événement de l’application d’entreposage**.</span><span class="sxs-lookup"><span data-stu-id="18d91-142">Select **Reset** from the **Warehouse app event messages** toolbar.</span></span>
1. <span data-ttu-id="18d91-143">Continuez jusqu’à ce que tous les messages pertinents soient réinitialisés.</span><span class="sxs-lookup"><span data-stu-id="18d91-143">Continue working until all relevant messages are reset.</span></span>

<span data-ttu-id="18d91-144">Vous pouvez également supprimer un message d’événement **Échoué** à l’aide de l’option **Supprimer** de la barre d’outils **Messages d’événement de l’application d’entreposage**.</span><span class="sxs-lookup"><span data-stu-id="18d91-144">You can also remove a **Failed** event message by using the **Delete** option on the **Warehouse app event messages** toolbar.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]