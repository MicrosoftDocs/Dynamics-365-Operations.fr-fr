---
title: Messages du processeur de messages
description: Cet article fournit des informations sur la fonctionnalité de messages du processeur de messages pour les charges de travail d’unité d’échelle.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: a5f8d48ba697df389150f70ac159e690156de33b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893611"
---
# <a name="message-processor-messages"></a>Messages du processeur de messages

[!include [banner](../includes/banner.md)]

Les messages du processeur de messages sont utilisés lors de l’exécution des unités d’échelle cloud et de périphérie pour les [charges de travail de fabrication](cloud-edge-workload-manufacturing.md) et les [charges de travail de gestion d’entrepôt](cloud-edge-workload-warehousing.md).

Les environnements de déploiement du hub et de l’unité d’échelle échangent une importante quantité de données pour rester synchronisés. Certaines des données échangées déclencheront une logique supplémentaire dans le *processeur de messages*. Vous pouvez afficher les messages traités par le processeur de messages en accédant à **Administration système > Processeur de messages > Messages du processeur de messages**.

## <a name="message-grid-columns-and-filters"></a>Colonnes et filtres de la grille de messages

Vous pouvez utiliser les champs en haut des **Messages du processeur de messages** pour trouver les messages que vous recherchez. La plupart de ces filtres correspondent aux en-têtes de colonne de la grille de messages. Les filtres et en-têtes de colonne suivants sont disponibles :

- **Type de message** – Spécifie le type de message.
- **File d’attente des messages** – Spécifie le nom de la file d’attente dans laquelle le message doit être traité. Les files d’attente suivantes sont fournies :
  - *Unité d’échelle vers hub*
  - *Hub de l’unité d’échelle d’exécution de l’entrepôt*
  - *Hub de l’unité d’échelle d’exécution de la fabrication*
- **État du message** – Spécifie l’état du message. Les états suivants existent :
  - *En file d’attente* – Le message est prêt à être traité par le processeur de messages.
  - *Traité* – Le message a été traité par le processeur de messages.
  - *Annulé* – Le message a été traité, mais le traitement a échoué.
- **Contenu du message** – Ce filtre lance une recherche en texte intégral du contenu du message. (Le contenu du message n’est pas affiché dans la grille.) Le filtre traite la plupart des symboles spéciaux (tels que « - ») comme des espaces et traite tous les caractères d’espacement comme des opérateurs booléens OR. Par exemple, cela signifie que si vous recherchez une valeur `journalid` égale à « USMF-123456 », le système trouvera tous les messages contenant « USMF » ou « 123456 », et vous obtiendrez probablement une longue liste. Par conséquent, il serait préférable de saisir uniquement « 123456 », car cela renverra des résultats plus spécifiques.

## <a name="example-message-type-request-inventory-adjustment-financial-update"></a>Exemple de type de message : demande de mise à jour financière de l’ajustement des stocks

Par exemple, le **Type de message** *Demande de mise à jour financière de l’ajustement des stocks* est utilisé pour créer et publier un journal de comptage sur le hub lorsqu’un collaborateur utilise l’application d’entrepôt pour [enregistrer un ajustement de stock](cloud-edge-warehouse-inventory-adjustment.md) sur une charge de travail de gestion d’entrepôt d’unité d’échelle. Parce que ce processus spécifique provient d’une unité d’échelle, le champ **File d’attente des messages** affichera la valeur *Unité d’échelle vers le hub*.

Pour ce type de message, une charge de travail d’unité d’échelle enregistre le message dans le cadre d’une opération d’ajustement de stock de l’application d’entrepôt. Les données du message sont ensuite transférées au hub dans le cadre du même processus utilisé pour l’[Architecture Commerce Data Exchange](../../commerce/commerce-architecture.md). Le message sera mis à jour pour afficher l’**État du message** comme *En file d’attente*. Le processeur de messages tente ensuite de traiter le message et met à jour l’**État du message** sur *Traité* en cas de succès, ou sur *Annulé* en cas d’échec.

## <a name="view-the-message-log-message-content-and-details"></a>Afficher le journal des messages, le contenu des messages et les détails

Vous trouverez des informations détaillées sur un message en le sélectionnant dans la grille puis en ouvrant les onglets **Journal** ou **Contenu du message** sous la grille de messages, où chaque événement de traitement est affiché.

Le **Contenu du message** dépend du **Type de message** et aura donc une longueur de texte différente. Un contenu de message typique commencera par **{** et se terminera par **}** et entre les deux ont trouvera des noms de champ tels que `journalId` suivis de **:** et des valeurs telles que *USMF-123456*.

La barre d’outils sur l’onglet **Journal** comprend les boutons suivants :

- **Journal** – Affiche les résultats du traitement. Ceci est particulièrement utile pour comprendre les raisons d’un échec de traitement pour les messages ayant un **Résultat du traitement** défini sur *Échec*.
- **Groupe** – Plusieurs opérations de traitement de messages peuvent s’exécuter dans le cadre du même traitement par lots. Sélectionnez ce bouton pour afficher ces données détaillées. Par exemple, vous pouvez voir s’il existe des dépendances qui obligent le système à traiter certains messages dans une séquence spécifique.

## <a name="message-processor-batch-job"></a>Tâche par lots du processeur de messages

Lors de l’exécution d’une topologie hybride distribué avec des unités d’échelle, la tâche par lots *Processeur de messages* sera automatiquement invoquée lorsqu’un nouveau message est créé pour le traitement, vous ne devriez donc pas avoir besoin de planifier ce travail manuellement.

Si nécessaire, vous pouvez accéder à la tâche par lots via **Administration système > Processeur de messages > Processeur de messages**.

## <a name="manually-process-or-cancel-a-message"></a>Traiter ou annuler manuellement un message

Si nécessaire, vous pouvez traiter ou annuler manuellement un message, en fonction de son état actuel. Pour ce faire, sélectionnez le message dans la grille, puis sélectionnez **Traiter** ou alors **Annuler** sur le volet Actions

## <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a>Configurer des événements commerciaux pour envoyer des alertes en cas d’échec du traitement des résultats

En plus du filtrage sur la valeur *Annulé* pour **État du message**, pour vous renseigner sur les messages ayant échoué, vous pouvez configurer des [Événements commerciaux](../../fin-ops-core/dev-itpro/business-events/home-page.md) sur le hub qui vous avertissent de l’échec du traitement des résultats. Pour ce faire, activez l’événement commercial nommé *Message du processeur de messages traité* sur la page **Catalogue des événements commerciaux** (**Administration système > Configuration > Événements commerciaux > Catalogue des événements commerciaux**).

Dans le cadre du processus d’activation, vous serez guidé pour spécifier si l’événement est spécifique à une ou à toutes les entités juridiques et pour fournir un **Nom de point de terminaison**, qui doit être défini en premier.

>[!NOTE]
> Si **Quand un événement commercial se produit** est défini sur *Microsoft Power Automate* (plutôt que *HTTPS*, par exemple), le **Nom de point de terminaison** sera automatiquement créé dans la gestion Supply Chain Management en fonction de la configuration *Microsoft Power Automate*.

### <a name="microsoft-power-automate-example"></a>Exemple Microsoft Power Automate

Dans cet exemple, utilisez **Quand un événement commercial se produit** avec *Microsoft Power Automate* pour envoyer des e-mails contenant des messages InfoLog et des hyperliens et ouvrir la page **Messages du processeur de messages** pour un message d’échec spécifique concernant le déploiement du hub. Si nécessaire, vous pouvez ajouter une logique supplémentaire pour envoyer les notifications en parallèle en utilisant différents canaux et contrôler les destinataires en fonction des données d’événement.

1. Dans [Power Automate](https://preview.flow.microsoft.com), créez un nouveau flux cloud automatisé pour le déclencheur de flux **Quand un événement commercial se produit – Application Fin & Ops (Dynamics 365)** suivi des étapes **Analyser JSON** et **Envoi d’un message e-mail**, comme indiqué dans l’illustration suivante.

    :::image type="content" source="./media/cloud-edge-power-automate-example1.png" alt-text="Flux cloud automatisé Power Automate.":::

1. Dans l’étape **Quand un événement commercial se produit**, vous pouvez rechercher ou entrer l’**Instance** de hub après la **Catégorie** et puis l’**Événement commercial** *Message du processeur de messages traité*, comme indiqué dans l’illustration suivante.

    :::image type="content" source="./media/cloud-edge-power-automate-example2.png" alt-text="Power Automate – Étape : Quand un événement commercial se produit.":::

1. Pour l’étape **Analyser JSON**, entrez un **Schéma** qui définit les champs étendus. Vous pouvez utiliser l’option *Télécharger le schéma* sur la page **Catalogue des événements commerciaux** dans Supply Chain Management ou commencer par coller le texte du schéma donné en exemple. Cet exemple de texte est fourni après l’illustration suivante.

    :::image type="content" source="./media/cloud-edge-power-automate-example3.png" alt-text="Power Automate- Étape : Analyser JSON.":::

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

1. Dans l’étape **Envoyer un e-mail**, vous pouvez sélectionner les champs individuels ou commencer par coller l’exemple du corps de l’e-mail dans le champ **Corps**. Cet exemple est fourni après l’illustration suivante.

    :::image type="content" source="./media/cloud-edge-power-automate-example4.png" alt-text="Power Automate – Étape : Envoi d’un message e-mail.":::

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

1. Lorsque vous enregistrez l’événement commercial, il sera automatiquement activé et prêt à être utilisé dans le cadre de la gestion de Supply Chain Management.
