---
title: Scénario du statut de l’ordinateur
description: Cet article décrit le scénario du statut de l’ordinateur, qui vous permet d’utiliser les données des capteurs pour surveiller la disponibilité de votre équipement.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreNotification, IoTIntMfgResourceStatusConfiguration, IoTIntMfgResourceStatus
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 30fdfb898384aea4c1f8cb2f36f9e104cd316f90
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689637"
---
# <a name="the-machine-status-scenario"></a>Scénario du statut de l’ordinateur

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Cet article décrit le scénario du *statut de l’ordinateur*, qui vous permet d’utiliser les données des capteurs pour surveiller la disponibilité de votre équipement. Si vous configurez un capteur qui envoie un signal lorsqu’un travail de production sur une ressource ordinateur produit une sortie, mais qu’aucun signal de capteur n’est reçu dans un intervalle spécifié, une notification s’affiche sur le tableau de bord du superviseur.

## <a name="scenario-dependencies"></a>Dépendances de scénario

Le scénario *Statut de l’ordinateur* a les dépendances suivantes :

- Une notification peut être déclenchée uniquement si une tâche de production est en cours sur un ordinateur mappé.
- Un signal qui représente un signal *partiel* doit être envoyé au hub IoT.

## <a name="prepare-demo-data-for-the-machine-status-scenario"></a>Préparer les données de démonstration pour le scénario de statut de l’ordinateur

Si vous souhaitez utiliser un système de démonstration pour tester le scénario *Statut de l’ordinateur*, utilisez un système où les [données de démonstration](../../fin-ops-core/fin-ops/get-started/demo-data.md) sont installées, sélectionnez l’entité juridique *USMF* (société) et préparez les données de démonstration supplémentaires comme décrit dans cette section. Si vous utilisez vos propres capteurs et données, vous pouvez ignorer cette section.

### <a name="set-up-a-sensor-simulator"></a>Mettre en place un simulateur de capteur

Si vous souhaitez essayer ce scénario sans utiliser de capteur physique, vous pouvez configurer un simulateur pour générer les signaux requis. Pour plus d’informations, voir [Paramétrer un capteur de simulation pour les tests](sdi-set-up-simulated-sensor.md).

### <a name="verify-that-resource-3118-is-used-for-product-p0111"></a>Vérifiez que la ressource 3118 est utilisée pour le produit P0111

Un ordre de fabrication sera programmé et lancé. Par conséquent, un travail de production est libéré pour la ressource *3118* (*Machine de découpe de mousse*). Suivez ces étapes pour vérifier que cette ressource *3118* est utilisée pour le produit *P0111* dans vos données de démonstration.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Recherchez le produit dont le champ **Numéro d’article** est défini sur *P0111*.
1. Dans le volet Actions, sous l’onglet **Ingénieur**, dans le groupe **Afficher**, sélectionnez **Route**.
1. Sur la page **Route**, sur l’onglet **Vue d’ensemble** en bas de la page, sélectionnez la ligne où le champ **N° opér.** est défini sur *30*.
1. Sur l’onglet **Besoins en ressources** en bas de la page, assurez-vous que la ressource *3118* (*Machine de découpe de mousse*) est associée à l’opération.

### <a name="create-and-release-a-production-order-for-product-p0111"></a>Créer et mettre en production un ordre de fabrication pour le produit P0111

Suivez ces étapes pour créer et lancer un ordre de fabrication pour le produit *P0111*.

1. Allez dans **Contrôle de la production \> Ordres de fabrication \> Tous les ordres de fabrication**.
1. Sur la page **Tous les ordres de production**, dans le volet Actions, sélectionnez **Nouveau lot de commandes**.
1. Dans la boîte de dialogue **Créer un traitement par lot**, définissez les valeurs suivantes :

    - **Numéro d’article :** *P0111*
    - **Quantité :** *10*

1. Sélectionnez **Créer** pour créer l’ordre et revenir à la page **Tous les ordres de fabrication**.
1. Utilisez le champ **Filtre** pour rechercher des ordres de fabrication où le champ **Numéro d’article** est défini sur *P0111*. Puis recherchez l’ordre de fabrication que vous venez de créer.
1. Dans le volet Actions, sous l’onglet **Ordre de fabrication**, dans le groupe **Processus**, sélectionnez **Estimer**.
1. Dans la boîte de dialogue **Estimation**, sélectionnez **OK** pour exécuter l’estimation.
1. Dans le volet Actions, sous l’onglet **Ordre de fabrication**, dans le groupe **Processus**, sélectionnez **Lancement**.
1. Dans la boîte de dialogue **Lancement**, notez le numéro de la commande groupée que vous venez de créer.
1. Sélectionnez **OK** pour lancer la commande.

### <a name="configure-the-production-floor-execution-interface"></a><a name="config-pfe"></a>Configurer l’interface d’exécution de l’atelier de production

Vous utiliserez l’interface d’exécution de l’atelier de production pour démarrer le travail qui a été planifié et lancé pour le numéro d’article *P0111* dans la section précédente. Procédez comme suit pour configurer l’interface d’exécution de l’atelier de production.

1. Accédez à **Contrôle de la production \> Contrôle et suivi de la production \> Exécution de l’atelier de production**.
1. Si vous n’avez pas encore configuré l’interface, une page de connexion s’affiche. Entrez vos informations d’identification.
1. Sur la page d’accueil, sélectionnez **Configurer** pour ouvrir l’assistant **Configurer l’appareil**.
1. Sur la page **Configurer l’appareil - Étape 1 - Sélectionner la configuration**, sélectionnez la configuration *Par défaut*.
1. Cliquez sur **Suivant**.
1. Sur la page **Configurer l’appareil - Étape 2 - Définir la surface de production**, définissez le champ **Ressource** sur *3118*.
1. Cliquez sur **OK**.

### <a name="enable-the-search-option-in-the-production-floor-execution-interface"></a><a name="enable-pfe-search"></a>Activation de l’option de recherche dans l’interface d’exécution de l’atelier de production

Pour faciliter la recherche de la tâche de production pour l’ordre de fabrication qui a été publié précédemment, suivez ces étapes pour activer l’option de recherche dans l’interface d’exécution de l’atelier de production.

1. Accédez à **Contrôle de la production \> Paramétrage \> Contrôle et suivi de la production \> Configurer l’exécution de l’atelier de production**.
1. Sélectionnez la configuration *Par défaut*.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans le raccourci **Général**, définissez l’option **Activer la recherche** sur *Oui*.
1. Fermez la page.

### <a name="start-the-first-job-in-the-batch-order"></a>Démarrer la première tâche dans la commande par lots

Suivez ces étapes pour démarrer la tâche planifiée sur la ressource *3118*.

1. Accédez à **Contrôle de la production \> Contrôle et suivi de la production \> Exécution de l’atelier de production**.
1. Dans le champ **ID badge**, entrez *123*. Ensuite, sélectionnez **Se connecter**.
1. Si vous êtes invité à fournir un motif d’absence, sélectionnez l’une des cartes d’absence, puis sélectionnez **OK**.
1. Dans le champ **Rechercher**, saisissez le numéro de lot de commande que vous avez préalablement noté. Sélectionnez ensuite la clé **Retour**.
1. Sélectionnez la commande client, puis sélectionnez **Démarrer la tâche**.
1. Dans la boîte de dialogue **Démarrer la tâche**, sélectionnez **Démarrer**.

## <a name="set-up-the-machine-status-scenario"></a>Configurer le scénario du statut de l’ordinateur

Procédez comme suit pour configurer le scénario *Statut de l’ordinateur* dans Supply Chain Management.

1. Aller à **Contrôle de production \> Configurer \> Sensor Data Intelligence \> Scénarios**.
1. Dans la zone du scénario **Statut de l’ordinateur**, sélectionnez **Configurer** pour ouvrir l’assistant de configuration de ce scénario.
1. Sur la page **Capteurs**, sélectionnez **Nouveau** pour ajouter un capteur à la grille. Définissez ensuite les champs suivants correspondants :

    - **Identifiant du capteur** : saisissez l’ID du capteur que vous utilisez. (Si vous utilisez le simulateur en ligne Raspberry PI Azure IoT et que vous l’avez configuré comme décrit dans [Configurer un capteur simulé pour les tests](sdi-set-up-simulated-sensor.md), saisissez *MachineStatus*.)
    - **Description du capteur** : entrez une description du capteur.

1. Répétez l’étape précédente pour chaque capteur que vous souhaitez ajouter maintenant. Vous pouvez revenir et ajouter d’autres capteurs à tout moment.
1. Cliquez sur **Suivant**.
1. Sur la page **Mise en correspondance des enregistrements commerciaux**, dans la section **Capteurs**, sélectionnez l’enregistrement de l’un des capteurs que vous venez d’ajouter.
1. Dans la section **Mise en correspondance des enregistrements commerciaux**, sélectionnez **Nouveau** dans la barre d’outils pour ajouter une ligne à la grille.
1. Dans la nouvelle ligne, définissez le champ **Enregistrement commercial** sur la ressource avec laquelle vous surveillez le capteur sélectionné. (Si vous utilisez les données de démonstration que vous avez créées précédemment dans cet article, définissez le champ sur *3118, Machine de découpe de la mousse*.)
1. Cliquez sur **Suivant**.
1. Sur la page **Seuil de statut de l’ordinateur**, définissez combien de temps après le dernier signal *partiel* le système doit envoyer une notification sur le statut de l’ordinateur. Il existe deux manières de définir le seuil :

    - **Seuil par défaut (minutes)**  : définissez ce champ pour définir le seuil par défaut. La valeur s’appliquera alors à toutes les ressources où le champ **Seuil permettant de déterminer si l’ordinateur ne répond pas (minutes)** est défini sur deux minutes ou moins. La valeur minimale est *2* (minutes).
    - **Seuil permettant de déterminer si l’ordinateur ne répond pas (minutes)**  : pour chaque ressource de la grille où vous ne souhaitez pas utiliser le seuil par défaut, entrez une valeur de remplacement dans ce champ. Les ressources configurées pour utiliser un seuil de deux minutes ou moins utiliseront le paramètre **Seuil par défaut (minutes)** à la place.

    > [!NOTE]
    > Généralement, vous utiliserez un signal *partiel* pour surveiller le statut de l’ordinateur. Par conséquent, vous devez vérifier que le seuil de chaque ressource ordinateur est supérieur à celui dont l’ordinateur a besoin pour produire chaque pièce.

1. Cliquez sur **Suivant**.
1. Sur la page **Activer les capteurs**, dans la grille, sélectionnez le capteur que vous avez ajouté, puis sélectionnez **Activer**. Pour chaque capteur activé dans la grille, une coche apparaît dans la colonne **Actif**.
1. Sélectionnez **Terminer**.

## <a name="work-with-the-machine-status-scenario"></a>Utiliser le scénario du statut de l’ordinateur

Après avoir installé vos capteurs et configuré le scénario, vous pouvez afficher les événements de statut de l’ordinateur dans Supply Chain Management. Cette section décrit où et comment afficher ces informations.

### <a name="view-machine-status-data-on-the-resource-status-page"></a>Afficher les données de statut de l’ordinateur sur la page Statut de la ressource

Sur la page **Statut de la ressource**, les superviseurs peuvent surveiller une chronologie du signal *partiel* reçu des capteurs qui sont mappés à chaque ressource machine. Procédez comme suit pour configurer la chronologie.

1. Accédez à **Contrôle de la production \> Exécution de la fabrication \> Statut de la ressource**.
1. Dans la boîte de dialogue **Configurer**, définissez les champs suivants :

    - **Ressource** : sélectionnez les ressources que vous souhaitez surveiller. (Si vous utilisez les données de démonstration, sélectionnez *3118*.)
    - **Série chronologique 1** : sélectionnez l’enregistrement (clé de mesure) avec le format de nom suivant : *MachineReportingStatus&lt;Sensor&gt;*
    - **Nom d’affichage** : saisissez *Signal partiel*.

L’illustration suivante montre un exemple de données de statut de l’ordinateur sur la page **Statut de la ressource** pendant le fonctionnement standard.

![Données de statut de l’ordinateur sur la page Statut de la ressource pendant le fonctionnement standard.](media/sdi-resource-status-downtime-up.png "Données de statut de l’ordinateur sur la page Statut de la ressource pendant le fonctionnement standard")

L’illustration suivante montre un exemple de données de statut de l’ordinateur lorsqu’un temps d’arrêt est détecté.

![Données du statut de l’ordinateur sur la page Statut des ressources lorsqu’un temps d’arrêt est détecté.](media/sdi-resource-status-downtime-down.png "Données du statut de l’ordinateur sur la page Statut des ressources lorsqu’un temps d’arrêt est détecté")

### <a name="view-machine-status-on-the-notifications-page"></a>Afficher le statut de l’ordinateur sur la page Notifications

Sur la page **Notifications**, les superviseurs peuvent afficher les notifications qui sont générées lorsque trop de temps s’est écoulé depuis que le capteur a émis un signal *partiel*. Chaque notification fournit une vue d’ensemble de la tâche de production affectée par la panne et offre la possibilité de réaffecter la tâche affectée à une autre ressource.

Pour ouvrir la page **Notification**, accédez à **Contrôle de la production \> Recherches et états \> Sensor Data Intelligence \> Notifications**.

L’illustration suivante présente un exemple de notification du statut de l’ordinateur.

![Exemple de notification de statut de l’ordinateur.](media/sdi-resource-status-downtime-notification.png "Exemple de notification de statut de l’ordinateur")
