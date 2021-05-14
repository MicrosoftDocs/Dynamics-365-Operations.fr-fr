---
title: Messages du processeur de messages
description: Cette rubrique fournit des informations sur la fonctionnalité de messages du processeur de messages pour les charges de travail d'unité d'échelle.
author: perlynne
manager: tfehr
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysMessageProcessorMessage, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: b1428e2e657e653874d4ec07605932a32bd803b2
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938248"
---
# <a name="message-processor-messages"></a><span data-ttu-id="7ca19-103">Messages du processeur de messages</span><span class="sxs-lookup"><span data-stu-id="7ca19-103">Message processor messages</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="7ca19-104">Les messages du processeur de messages sont utilisés lors de l'exécution des unités d'échelle cloud et de périphérie pour les [charges de travail de fabrication](cloud-edge-workload-manufacturing.md) et les [charges de travail de gestion d'entrepôt](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="7ca19-104">Message processor messages are used when running cloud and edge scale units for [manufacturing workloads](cloud-edge-workload-manufacturing.md) and [warehouse management workloads](cloud-edge-workload-warehousing.md).</span></span>

<span data-ttu-id="7ca19-105">Une grande quantité de données est échangée entre les environnements de déploiement du hub et de l'unité d'échelle afin de les maintenir synchronisés, mais seuls quelques-uns de ces échanges de données seront traités par le *processeur de messages*.</span><span class="sxs-lookup"><span data-stu-id="7ca19-105">A large amount of data is exchanged between the hub and scale unit deployment environments to keep them in sync, but only a few of these data exchanges will be processed by the *message processor*.</span></span> <span data-ttu-id="7ca19-106">Vous pouvez afficher les messages traités par le processeur de messages en accédant à **Administration système > Processeur de messages > Messages du processeur de messages**.</span><span class="sxs-lookup"><span data-stu-id="7ca19-106">You can view the messages processed by the message processor by going to **System administration > Message processor > Message processor messages**.</span></span>

## <a name="message-grid-columns-and-filters"></a><span data-ttu-id="7ca19-107">Colonnes et filtres de la grille de messages</span><span class="sxs-lookup"><span data-stu-id="7ca19-107">Message grid columns and filters</span></span>

<span data-ttu-id="7ca19-108">Vous pouvez utiliser les champs en haut des **Messages du processeur de messages** pour trouver les messages que vous recherchez.</span><span class="sxs-lookup"><span data-stu-id="7ca19-108">You can use the fields at the top of the **Message processor messages** page to help find any particular messages you are looking for.</span></span> <span data-ttu-id="7ca19-109">La plupart de ces filtres correspondent aux en-têtes de colonne de la grille de messages.</span><span class="sxs-lookup"><span data-stu-id="7ca19-109">Most of these filters match the column headings in the message grid.</span></span> <span data-ttu-id="7ca19-110">Les filtres et en-têtes de colonne suivants sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="7ca19-110">The following filters and column headings are available:</span></span>

- <span data-ttu-id="7ca19-111">**Type de message** – Spécifie le type de message.</span><span class="sxs-lookup"><span data-stu-id="7ca19-111">**Message type** – Specifies the type of message.</span></span>
- <span data-ttu-id="7ca19-112">**File d'attente des messages** – Spécifie le nom de la file d'attente dans laquelle le message doit être traité.</span><span class="sxs-lookup"><span data-stu-id="7ca19-112">**Message queue** – Specifies the name of the queue in which the message is to be processed.</span></span> <span data-ttu-id="7ca19-113">Les files d'attente suivantes sont fournies :</span><span class="sxs-lookup"><span data-stu-id="7ca19-113">The following queues are provided:</span></span>
  - <span data-ttu-id="7ca19-114">*Unité d’échelle vers hub*</span><span class="sxs-lookup"><span data-stu-id="7ca19-114">*Scale unit to hub*</span></span>
  - <span data-ttu-id="7ca19-115">*Hub de l’unité d’échelle d’exécution de l’entrepôt*</span><span class="sxs-lookup"><span data-stu-id="7ca19-115">*Hub to warehouse execution scale unit*</span></span>
  - <span data-ttu-id="7ca19-116">*Hub de l’unité d’échelle d’exécution de la fabrication*</span><span class="sxs-lookup"><span data-stu-id="7ca19-116">*Hub to manufacturing execution scale unit*</span></span>
- <span data-ttu-id="7ca19-117">**État du message** – Spécifie l'état du message.</span><span class="sxs-lookup"><span data-stu-id="7ca19-117">**Message state** – Specifies the state of the message.</span></span> <span data-ttu-id="7ca19-118">Les états suivants existent :</span><span class="sxs-lookup"><span data-stu-id="7ca19-118">The following states exists:</span></span>
  - <span data-ttu-id="7ca19-119">*En file d'attente* – Le message est prêt à être traité par le processeur de messages.</span><span class="sxs-lookup"><span data-stu-id="7ca19-119">*Queued* – The message is ready to be processed by the message processor.</span></span>
  - <span data-ttu-id="7ca19-120">*Traité* – Le message a été traité par le processeur de messages.</span><span class="sxs-lookup"><span data-stu-id="7ca19-120">*Processed* – The message was successfully processed by the message processor.</span></span>
  - <span data-ttu-id="7ca19-121">*Annulé* - Le message a été traité, mais le traitement a échoué.</span><span class="sxs-lookup"><span data-stu-id="7ca19-121">*Canceled* – The message was processed, but processing failed.</span></span>
- <span data-ttu-id="7ca19-122">**Contenu du message** – Ce filtre lance une recherche en texte intégral du contenu du message.</span><span class="sxs-lookup"><span data-stu-id="7ca19-122">**Message content** – This filter does a full-text search of message content.</span></span> <span data-ttu-id="7ca19-123">(Le contenu du message n'est pas affiché dans la grille.) Le filtre traite la plupart des symboles spéciaux (tels que « - ») comme des espaces et traite tous les caractères d’espacement comme des opérateurs booléens OR.</span><span class="sxs-lookup"><span data-stu-id="7ca19-123">(Message content is not shown in the grid.) The filter treats most special symbols (such as "-") as spaces, and treats all space characters as Boolean OR operators.</span></span> <span data-ttu-id="7ca19-124">T = Par exemple, cela signifie que si vous recherchez une valeur `journalid` égale à « USMF-123456 », le système trouvera tous les messages contenant « USMF » ou « 123456 », et vous obtiendrez probablement une longue liste.</span><span class="sxs-lookup"><span data-stu-id="7ca19-124">T=For example, this means if you search for a specific `journalid` value equal "USMF-123456", the system will find all messages that contain "USMF" or "123456", which is likely to be a long list.</span></span> <span data-ttu-id="7ca19-125">Par conséquent, il serait préférable de saisir uniquement « 123456 », car cela renverra des résultats plus spécifiques.</span><span class="sxs-lookup"><span data-stu-id="7ca19-125">Therefore, it would be better to enter just "123456" alone because that will return more specific results.</span></span>

## <a name="example-message-type-request-inventory-adjustment-financial-update"></a><span data-ttu-id="7ca19-126">Exemple de type de message : demande de mise à jour financière de l'ajustement des stocks</span><span class="sxs-lookup"><span data-stu-id="7ca19-126">Example message type: Request inventory adjustment financial update</span></span>

<span data-ttu-id="7ca19-127">Par exemple, le **Type de message** *Demande de mise à jour financière de l'ajustement des stocks* est utilisé pour créer et publier un journal de comptage sur le hub lorsqu'un collaborateur utilise l'application d'entrepôt pour [enregistrer un ajustement de stock](cloud-edge-warehouse-inventory-adjustment.md) sur une charge de travail de gestion d'entrepôt d'unité d'échelle.</span><span class="sxs-lookup"><span data-stu-id="7ca19-127">For example, the **Message type** *Request inventory adjustment financial update* is used to create and post a counting journal on the hub when a worker uses the warehouse app to [register an inventory adjustment](cloud-edge-warehouse-inventory-adjustment.md) on a scale unit warehouse management workload.</span></span> <span data-ttu-id="7ca19-128">Parce que ce processus spécifique provient d'une unité d'échelle, le champ **File d'attente des messages** affichera la valeur *Unité d'échelle vers le hub*.</span><span class="sxs-lookup"><span data-stu-id="7ca19-128">Because this specific process originates from a scale unit, the **Message queue** field will show the value *Scale unit to hub*.</span></span>

<span data-ttu-id="7ca19-129">Pour ce type de message, une charge de travail d'unité d'échelle enregistre le message dans le cadre d'une opération d'ajustement de stock de l'application d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="7ca19-129">For this message type, a scale unit workload records the message as part of a warehouse app inventory adjustment operation.</span></span> <span data-ttu-id="7ca19-130">Les données du message sont ensuite transférées au hub dans le cadre du même processus utilisé pour l'[Architecture Commerce Data Exchange](../../commerce/commerce-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="7ca19-130">The message data is then transferred to the hub as part of the same process used for the [Commerce data exchange architecture](../../commerce/commerce-architecture.md).</span></span> <span data-ttu-id="7ca19-131">Le message sera mis à jour pour afficher l'**État du message** comme *En file d'attente*.</span><span class="sxs-lookup"><span data-stu-id="7ca19-131">The message will be updated to show **Message state** as *Queued*.</span></span> <span data-ttu-id="7ca19-132">Le processeur de messages tente ensuite de traiter le message et met à jour l'**État du message** sur *Traité* en cas de succès, ou sur *Annulé* en cas d'échec.</span><span class="sxs-lookup"><span data-stu-id="7ca19-132">The message processor then attempts to process the message and updates the **Message state** to *Processed* on success, or *Canceled* on failure.</span></span>

## <a name="view-the-message-log-message-content-and-details"></a><span data-ttu-id="7ca19-133">Afficher le journal des messages, le contenu des messages et les détails</span><span class="sxs-lookup"><span data-stu-id="7ca19-133">View the message log, message content, and details</span></span>

<span data-ttu-id="7ca19-134">Vous trouverez des informations détaillées sur un message en le sélectionnant dans la grille puis en ouvrant les onglets **Journal** ou **Contenu du message** sous la grille de messages, où chaque événement de traitement est affiché.</span><span class="sxs-lookup"><span data-stu-id="7ca19-134">You can find detailed information about a message by selecting it in the grid and then opening the **Log** or **Message content** tabs under the message grid, where each processing event is shown.</span></span>

<span data-ttu-id="7ca19-135">Le **Contenu du message** dépend du **Type de message** et aura donc une longueur de texte différente.</span><span class="sxs-lookup"><span data-stu-id="7ca19-135">The **Message content** depends on the **Message type** and will therefore have different text length.</span></span> <span data-ttu-id="7ca19-136">Un contenu de message typique commencera par **{** et se terminera par **}** et entre les deux ont trouvera des noms de champ tels que `journalId` suivis de **:** et des valeurs telles que *USMF-123456*.</span><span class="sxs-lookup"><span data-stu-id="7ca19-136">A typical message content text will start with a **{** and end with a **}** and in between have field names such as `journalId` followed by a **:** and a value such as *USMF-123456*.</span></span>

<span data-ttu-id="7ca19-137">La barre d'outils sur l'onglet **Journal** comprend les boutons suivants :</span><span class="sxs-lookup"><span data-stu-id="7ca19-137">The toolbar on the **Log** tab includes the following buttons:</span></span>

- <span data-ttu-id="7ca19-138">**Journal** - Affiche les résultats du traitement.</span><span class="sxs-lookup"><span data-stu-id="7ca19-138">**Log** – Displays the processing results.</span></span> <span data-ttu-id="7ca19-139">Ceci est particulièrement utile pour comprendre les raisons d'un échec de traitement pour les messages ayant un **Résultat du traitement** défini sur *Échec*.</span><span class="sxs-lookup"><span data-stu-id="7ca19-139">This is especially helpful for understanding the reasons for a processing failure for messages having a **Processing result** of *Failed*.</span></span>
- <span data-ttu-id="7ca19-140">**Groupe** - Plusieurs opérations de traitement de messages peuvent s'exécuter dans le cadre du même traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="7ca19-140">**Bundle** – Multiple message processing operations can run as part of the same batch process.</span></span> <span data-ttu-id="7ca19-141">Sélectionnez ce bouton pour afficher ces données détaillées.</span><span class="sxs-lookup"><span data-stu-id="7ca19-141">Select this button to view this detailed data.</span></span> <span data-ttu-id="7ca19-142">Par exemple, vous pouvez voir s'il existe des dépendances qui obligent le système à traiter certains messages dans une séquence spécifique.</span><span class="sxs-lookup"><span data-stu-id="7ca19-142">For example, you can see whether dependencies exist that require the system to process certain messages in a specific sequence.</span></span>

## <a name="message-processor-batch-job"></a><span data-ttu-id="7ca19-143">Tâche par lots du processeur de messages</span><span class="sxs-lookup"><span data-stu-id="7ca19-143">Message processor batch job</span></span>

<span data-ttu-id="7ca19-144">Lors de l'exécution d'un déploiement cloud et périphérique, la tâche par lots *Processeur de messages* sera automatiquement invoquée lorsqu'un nouveau message est créé pour le traitement, vous ne devriez donc pas avoir besoin de planifier ce travail manuellement.</span><span class="sxs-lookup"><span data-stu-id="7ca19-144">When running a cloud and edge deployment, the *Message processor* batch job will automatically be evoked when a new message is created for processing, so you should not need to schedule this job manually.</span></span>

<span data-ttu-id="7ca19-145">Si nécessaire, vous pouvez accéder à la tâche par lots via **Administration système > Processeur de messages > Processeur de messages**.</span><span class="sxs-lookup"><span data-stu-id="7ca19-145">If necessary, you can access the batch job by going to **System administration > Message  processor > Message processor**.</span></span>

## <a name="manually-process-or-cancel-a-message"></a><span data-ttu-id="7ca19-146">Traiter ou annuler manuellement un message</span><span class="sxs-lookup"><span data-stu-id="7ca19-146">Manually process or cancel a message</span></span>

<span data-ttu-id="7ca19-147">Si nécessaire, vous pouvez traiter ou annuler manuellement un message, en fonction de son état actuel.</span><span class="sxs-lookup"><span data-stu-id="7ca19-147">If needed, you can manually process or cancel a message, depending on its current state.</span></span> <span data-ttu-id="7ca19-148">Pour ce faire, sélectionnez le message dans la grille, puis sélectionnez **Traiter** ou alors **Annuler** sur le volet Actions</span><span class="sxs-lookup"><span data-stu-id="7ca19-148">To do so, select the message in the grid and then select **Process** or **Cancel** on the Action Pane</span></span>

## <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a><span data-ttu-id="7ca19-149">Configurer des événements commerciaux pour envoyer des alertes en cas d'échec du traitement des résultats</span><span class="sxs-lookup"><span data-stu-id="7ca19-149">Set up business events to deliver alerts for failed processing results</span></span>

<span data-ttu-id="7ca19-150">En plus du filtrage sur la valeur *Annulé* pour **État du message**, pour vous renseigner sur les messages ayant échoué, vous pouvez configurer des [Événements commerciaux](../../fin-ops-core/dev-itpro/business-events/home-page.md) sur le hub qui vous avertissent de l'échec du traitement des résultats.</span><span class="sxs-lookup"><span data-stu-id="7ca19-150">In addition to filtering on the **Message state** value *Canceled* to inquire for failed messages, you can set up [Business events](../../fin-ops-core/dev-itpro/business-events/home-page.md) on the hub to alert you to failed processing results.</span></span> <span data-ttu-id="7ca19-151">Pour ce faire, activez l'événement commercial nommé *Message du processeur de messages traité* sur la page **Catalogue des événements commerciaux** (**Administration système > Configuration > Événements commerciaux > Catalogue des événements commerciaux**).</span><span class="sxs-lookup"><span data-stu-id="7ca19-151">To do so, activate the business event named *Message processor message processed*  on the **Business events catalog** page (**System administration > Setup > Business events > Business events catalog**).</span></span>

<span data-ttu-id="7ca19-152">Dans le cadre du processus d'activation, vous serez guidé pour spécifier si l'événement est spécifique à une ou à toutes les entités juridiques et pour fournir un **Nom de point de terminaison**, qui doit être défini en premier.</span><span class="sxs-lookup"><span data-stu-id="7ca19-152">As part of the activation process, you will be guided to specify whether the event is specific to one or all legal entities and provide an **Endpoint name**, which must be defined first.</span></span>

>[!NOTE]
> <span data-ttu-id="7ca19-153">Si **Quand un événement commercial se produit** est défini sur *Microsoft Power Automate* (plutôt que *HTTPS*, par exemple), le **Nom de point de terminaison** sera automatiquement créé dans la gestion Supply Chain Management en fonction de la configuration *Microsoft Power Automate*.</span><span class="sxs-lookup"><span data-stu-id="7ca19-153">If **When a Business Event occurs** is set to *Microsoft Power Automate* (rather than *HTTPS*, for example), the **Endpoint name** will automatically be created in Supply Chain Management based on the *Microsoft Power Automate* setup.</span></span>

### <a name="microsoft-power-automate-example"></a><span data-ttu-id="7ca19-154">Exemple Microsoft Power Automate</span><span class="sxs-lookup"><span data-stu-id="7ca19-154">Microsoft Power Automate example</span></span>

<span data-ttu-id="7ca19-155">Dans cet exemple, utilisez **Quand un événement commercial se produit** avec *Microsoft Power Automate* pour envoyer des e-mails contenant des messages InfoLog et des hyperliens et ouvrir la page **Messages du processeur de messages** pour un message d'échec spécifique concernant le déploiement du hub.</span><span class="sxs-lookup"><span data-stu-id="7ca19-155">In this example, use **When a Business Event occurs** with *Microsoft Power Automate* sends emails containing InfoLog messages and hyperlinks to open the **Message processor messages** page for a specific failed message on the hub deployment.</span></span> <span data-ttu-id="7ca19-156">Si nécessaire, vous pouvez ajouter une logique supplémentaire pour envoyer les notifications en parallèle en utilisant différents canaux et contrôler les destinataires en fonction des données d'événement.</span><span class="sxs-lookup"><span data-stu-id="7ca19-156">If needed, you can add extra logic to send the notifications in parallel using different channels and control the recipients based on the event data.</span></span>

1. <span data-ttu-id="7ca19-157">Dans [Power Automate](https://preview.flow.microsoft.com), créez un nouveau flux cloud automatisé pour le déclencheur de flux **Quand un événement commercial se produit - Application Fin & Ops (Dynamics 365)** suivi des étapes **Analyser JSON** et **Envoi d'un message e-mail**, comme indiqué dans l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="7ca19-157">In [Power Automate](https://preview.flow.microsoft.com), create a new automated cloud flow for the flow trigger **When a Business Event occurs - Fin & Ops App (Dynamics 365)** followed by the **Parse JSON** and **Send an email** steps, as shown in the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example1.png" alt-text="Flux cloud automatisé Power Automate":::

1. <span data-ttu-id="7ca19-159">Dans l'étape **Quand un événement commercial se produit**, vous pouvez rechercher ou entrer l'**Instance** de hub après la **Catégorie** et puis l'**Événement commercial** *Message du processeur de messages traité*, comme indiqué dans l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="7ca19-159">In the **When a Business Event occurs** step, you can look up or enter the hub **Instance** following the **Category** and then the **Business event** *Message processor message processed*, as shown in the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example2.png" alt-text="Power Automate - Étape : Quand un événement commercial se produit":::

1. <span data-ttu-id="7ca19-161">Pour l'étape **Analyser JSON**, entrez un **Schéma** qui définit les champs étendus.</span><span class="sxs-lookup"><span data-stu-id="7ca19-161">For the **Parse JSON** step, enter a **Schema** that defines the extended fields.</span></span> <span data-ttu-id="7ca19-162">Vous pouvez utiliser l'option *Télécharger le schéma* sur la page **Catalogue des événements commerciaux** dans Supply Chain Management ou commencer par coller le texte du schéma donné en exemple.</span><span class="sxs-lookup"><span data-stu-id="7ca19-162">You can use the *Download schema* option on the **Business events catalog** page in Supply Chain Management or start by pasting in the example schema text.</span></span> <span data-ttu-id="7ca19-163">Cet exemple de texte est fourni après l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="7ca19-163">This example text is provided after the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example3.png" alt-text="Power Automate- Étape : Analyser JSON":::

    ```json
    {
        "properties": {
            "BusinessEventId": {
                "type": "string"
            },
            "ControlNumber": {
                "type": "integer"
            },
            "EventId": {
                "type": "string"
            },
            "EventTime": {
                "type": "string"
            },
            "MajorVersion": {
                "type": "integer"
            },
            "MessageContent": {
                "type": "string"
            },
            "MessageDestinationCompanyId": {
                "type": "string"
            },
            "MessageDestinationOperationalSiteId": {
                "type": "string"
            },
            "MessageDestinationWarehouseId": {
                "type": "string"
            },
            "MessageDestinationWorkloadName": {
                "type": "string"
            },
            "MessageInfolog": {
                "type": "string"
            },
            "MessageProcessingResult": {
                "type": "string"
            },
            "MessageProcessingResultLabel": {
                "type": "string"
            },
            "MessageProcessorMessagePageUrl": {
                "type": "string"
            },
            "MessageQueue": {
                "type": "string"
            },
            "MessageQueueLabel": {
                "type": "string"
            },
            "MessageSourceCompanyId": {
                "type": "string"
            },
            "MessageSourceOperationalSiteId": {
                "type": "string"
            },
            "MessageSourceWarehouseId": {
                "type": "string"
            },
            "MessageSourceWorkloadName": {
                "type": "string"
            },
            "MessageState": {
                "type": "string"
            },
            "MessageStateLabel": {
                "type": "string"
            },
            "MessageType": {
                "type": "string"
            },
            "MessageTypeLabel": {
                "type": "string"
            },
            "MinorVersion": {
                "type": "integer"
            }
        },
        "type": "object"
    }
    ```

1. <span data-ttu-id="7ca19-165">Dans l'étape **Envoyer un e-mail**, vous pouvez sélectionner les champs individuels ou commencer par coller l'exemple du corps de l'e-mail dans le champ **Corps**.</span><span class="sxs-lookup"><span data-stu-id="7ca19-165">In the **Send an email** step, you can select the individual fields or start by pasting the email body example into the **Body** field.</span></span> <span data-ttu-id="7ca19-166">Cet exemple est fourni après l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="7ca19-166">This example is provided after the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example4.png" alt-text="Power Automate - Étape : Envoi d'un message e-mail":::

    ```plaintext
    Message queue: @{body('Parse_JSON')?['MessageQueue']}
    Message queue label: @{body('Parse_JSON')?['MessageQueueLabel']}
    Message type: @{body('Parse_JSON')?['MessageQueueType']}
    Message type label: @{body('Parse_JSON')?['MessageQueueTypeLabel']}
    Message content: @{body('Parse_JSON')?['MessageContent']}
    Message state: @{body('Parse_JSON')?['MessageState']}
    Message state label: @{body('Parse_JSON')?['MessageStateLabel']}
    Message processing result: @{body('Parse_JSON')?['MessageProcessingResult']}
    Message processing result label: @{body('Parse_JSON')?['MessageProcessingResultLabel']}
    Message infolog: @{body('Parse_JSON')?['MessageInfolog']}
    Message source company ID: @{body('Parse_JSON')?['MessageSourceCompanyId']}
    Message source workload name: @{body('Parse_JSON')?['MessageSourceWorkloadName']}
    Message source site ID: @{body('Parse_JSON')?['MessageSourceOperationalSiteId']}
    Message source warehouse ID: @{body('Parse_JSON')?['MessageSourceWarehouseId']}
    Message destination company ID: @{body('Parse_JSON')?['MessageDestinationCompanyId']}
    Message destination workload name: @{body('Parse_JSON')?['MessageDestinationWorkloadName']}
    Message destination site ID: @{body('Parse_JSON')?['MessageDestinationOperationalSiteId']}
    Message destination warehouse ID: @{body('Parse_JSON')?['MessageDestinationWarehouseId']}
    Message processor message page URL: @{body('Parse_JSON')?['MessageProcessorMessagePageUrl']}
    ```

1. <span data-ttu-id="7ca19-168">Lorsque vous enregistrez l'événement commercial, il sera automatiquement activé et prêt à être utilisé dans le cadre de la gestion de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7ca19-168">When you save the business event, it will automatically be activated and ready to use as part of Supply Chain Management.</span></span>
