---
title: Notifications d’exécution de vague
description: Cet article décrit les notifications d’exécution de vague et explique comment les configurer.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WhsWaveNotificationPolicy, WHSParameters, WHSWaveTemplateTable, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: a6a554965c11eea3b4fa53fe4dbc4bac04624026
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336573"
---
# <a name="wave-execution-notifications"></a>Notifications d’exécution de vague

[!include [banner](../includes/banner.md)]

La fonctionnalité *Notifications d’exécution de vague* utilise des événements commerciaux et le centre de notifications pour envoyer des notifications liées à l’exécution de la vague. Elle vous permet de spécifier les types d’événements qui génèrent des notifications, les entrepôts qui les génèrent et les utilisateurs qui les reçoivent.

Le bouton **Afficher les messages** (symbole de la cloche) sur le côté droit de la barre de navigation indique quand un message du centre d’action est disponible pour l’utilisateur actuel. L’utilisateur peut sélectionner le bouton **Afficher les messages** pour ouvrir le centre de notifications et consulter les messages.

Les événements commerciaux se produisent lors de l’exécution des processus métier. Les processus métier sont constitués de tâches. Au cours d’un processus métier, les utilisateurs qui y participent exécutent des actions métier pour effectuer ces tâches. Les événements commerciaux fournissent un mécanisme permettant aux systèmes externes de recevoir des notifications de la part des applications de finances et d’opérations. De cette manière, les systèmes peuvent effectuer des actions métier en réponse aux événements commerciaux. Pour plus d’informations, consultez [Présentation des événements commerciaux](../../fin-ops-core/dev-itpro/business-events/home-page.md).

## <a name="turn-the-wave-execution-notifications-feature-on-or-off"></a>Activer ou désactiver la fonctionnalité de notifications d’exécution de vague

Pour pouvoir utiliser cette fonctionnalité, il doit être activé pour votre système. Depuis la version 10.0.25 de Supply Chain Management, cette fonctionnalité est activée par défaut. Depuis la version 10.0.29 de Supply Chain Management, la fonctionnalité est obligatoire et ne peut pas être désactivée. Si vous exécutez une version antérieure à 10.0.29, les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Notifications d'exécution Wave* dans l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="scenario-send-wave-batch-execution-notifications-to-the-action-center"></a>Scénario : envoyer des notifications d’exécution du traitement par lots d’une vague au centre de notifications

Ce scénario montre le flux de bout en bout pour envoyer des notifications sur les erreurs d’exécution du traitement par lots d’une vague à un rôle spécifique via le centre de notifications.

### <a name="make-demo-data-available"></a>Rendre les données de démonstration disponibles

Pour suivre ce scénario, vous devez avoir des données de démonstration installées, et vous devez sélectionner l’entité juridique **USMF**.

### <a name="make-sure-that-waves-are-run-in-batch-mode"></a>Assurez-vous que les vagues sont exécutées en mode de traitement par lots

1. Accédez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**.
1. Dans le raccourci **Traitement de vague**, définissez l’option **Traiter les vagues par lots** sur *Oui*.

> [!NOTE]
> Si vous souhaitez désactiver les notifications d’exécution du traitement par lots d’une vague, définissez l’option **Désactiver les notifications du traitement par lots d’une vague** sur *Oui*.

### <a name="configure-a-wave-notification-policy"></a>Configurer une stratégie de notification de vague

Les stratégies de notification de vague définissent les types de notifications envoyées et les utilisateurs qui sont notifiés.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Vagues \> Stratégies de notification de vague**.
1. Créez un enregistrement possédant les paramètres suivants :

    - **Stratégie de notification de vague :** *24BatchError*
    - **Description :** *Erreur du traitement par lots de la vague de l’entrepôt 24*
    - **Envoyer une notification sur :** *Erreur uniquement*
    - **Rôle de destination :** *Administrateur système*

        > [!NOTE]
        > Étant donné que ce scénario utilise des données de démonstration, le rôle *Administrateur système* est choisi par souci de simplicité. Par conséquent, comme vous êtes connecté en tant qu’utilisateur administrateur système, vous recevrez les notifications. Cependant, en pratique, vous devrez généralement sélectionner un rôle plus spécifique pour notifier les erreurs d’exécution du traitement par lots de vagues, tel que *Gestionnaire d’entrepôt*.

1. Dans le volet Actions, sélectionnez **Enregistrer**.

### <a name="configure-a-wave-template"></a>Configurer un modèle de vague

Les modèles de vague vous permettent de lier des instances spécifiques de méthodes de vague à des modèles d’étiquette de vague correspondants.

1. Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.
1. Dans le volet de liste, définissez le champ **Type de modèle de vague** sur *Expédition*, puis sélectionnez le modèle de vague *Livraison par défaut 24* pour l’entrepôt 24.
1. Dans le raccourci **Général**, définissez le champ **Stratégie de notification de vague** sur *24BatchError*.

### <a name="configure-a-work-template"></a>Configurer un modèle de travail

Les modèles de travail sont utilisés lors de l’exécution de la vague pour générer du travail. Pour ce scénario, l’exécution de la vague doit déclencher une erreur. En définissant la requête de modèle de travail pour utiliser un entrepôt inexistant, vous vous assurez que l’exécution de la vague échouera et enverra donc une notification.

1. Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.
1. Dans le volet de liste, définissez le champ **Type de modèle de travail** sur *Commandes clients*, puis sélectionnez le modèle de travail *Phase CC 24* pour l’entrepôt 24.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Dans la boîte de dialogue de l’éditeur de requêtes, sur l’onglet **Plage**, modifiez la ligne suivante (ou ajoutez-la si elle n’existe pas) :

    - **Table :** *Transactions de travail temporaire*
    - **Table dérivée :** *Transactions de travail temporaire*
    - **Champ :** *Entrepôt*
    - **Critères :** Changer la valeur de *24* en *Erreur*.

1. Sélectionnez **OK** et confirmez la modification.

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Créer une commande client et la lancer dans l’entrepôt

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Créez une commande client possédant les paramètres suivants :

    - **Compte client :** *US-001*
    - **Entrepôt :** *24*

1. Dans le raccourci **Lignes de commande client**, ajoutez une commande client présentant les paramètres suivants :

    - **Numéro d’article :** *A0001*
    - **Quantité :** *10*

    > [!NOTE]
    > Ces articles et quantités ne sont que des exemples. L’entrepôt spécifié doit contenir suffisamment de stock.

1. Alors que la nouvelle ligne de commande est toujours sélectionnée dans le raccourci **Lignes de commande client**, sélectionnez **Stock \> Réservation** dans la barre d’outils.
1. Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot**. Fermez ensuite la page.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.

### <a name="notifications-from-wave-batch-job-execution"></a>Notifications de l’exécution du traitement par lots d’une vague

En fonction de la configuration de vos événements commerciaux, vous recevrez éventuellement une notification d’échec de l’exécution de la vague. Le message du centre de notifications ressemblera à l’exemple suivant et inclura un lien vers la vague qui a échoué.

> **Erreur lors de l’exécution de la vague**  
> Une erreur s’est produite lors de l’exécution de la vague USMF-000000001.  
> Derniers messages : Aucun travail n’a été créé pour la vague USMF-000000001.
>
> **STATUT**  
> Actif.ve
>
> Ouvrir les détails de la vague

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

