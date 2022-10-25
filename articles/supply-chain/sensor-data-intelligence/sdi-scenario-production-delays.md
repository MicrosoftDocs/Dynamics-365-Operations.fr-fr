---
title: Le scénario des retards de production
description: Cet article décrit le scénario Retards de production, qui génère une notification si la cadence de production tombe en dessous d’une valeur seuil.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, IoTIntMfgResourceStatusConfiguration, IoTIntMfgResourceStatus
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 25ccbda1628544f14dc32d9bea3f2162ad47d79e
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690019"
---
# <a name="the-production-delays-scenario"></a>Le scénario des retards de production

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Le scénario *Retards de production* génère une notification si la cadence de production tombe en dessous d’une valeur seuil spécifique. Dans ce scénario, un signal *partiel* est envoyé au hub IoT Microsoft Azure pour chaque article qui est produit. Dans Dynamics 365 Supply Chain Management, le retard de commande est calculé en fonction de la durée prévue de l’exécution de l’ordre de fabrication, du nombre d’articles à produire, de la durée d’exécution du travail et du nombre de signaux *partiels* reçus. Une notification de retard est générée si le nombre de signaux *partiels* pour le travail tombent en dessous de la valeur seuil de la valeur attendue.

## <a name="scenario-dependencies"></a>Dépendances de scénario

Le scénario *Retards de production* a les dépendances suivantes :

- Une alerte peut être déclenchée uniquement si un ordre de production s’exécute sur une machine mappée.
- Un signal qui représentant le signal *partiel* d’une machine mappée doit être envoyé au hub IoT et un nom de propriété unique doit être inclus.
- Une propriété horodatage UNIX, où la valeur est exprimée en millisecondes (ms), doit être présente dans le message du hub Azure IoT.

## <a name="prepare-demo-data-for-the-product-delays-scenario"></a>Préparer les données de démonstration pour le scénario de retards de produit

Si vous souhaitez utiliser un système de démonstration pour tester le scénario *Retards de production*, utilisez un système où les [données de démonstration](../../fin-ops-core/fin-ops/get-started/demo-data.md) sont installées, sélectionnez l’entité juridique *USMF* (société) et préparez les données de démonstration supplémentaires comme décrit dans cette section. Si vous utilisez vos propres capteurs et données, vous pouvez ignorer cette section.

### <a name="set-up-sensor-simulator"></a>Mettre en place un simulateur de capteur

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

### <a name="configure-the-production-floor-execution-interface"></a>Configurer l’interface d’exécution de l’atelier de production

Si vous ne l’avez pas déjà fait, configurez l’interface d’exécution de l’atelier de production pour afficher les tâches affectées à la ressource *3118* (*Machine de découpe de mousse*). Pour obtenir des instructions, reportez-vous aux sections suivantes :

- [Configurer l’interface d’exécution de l’atelier de production](sdi-scenario-equipment-downtime.md#config-pfe)
- [Activation de l’option de recherche dans l’interface d’exécution de l’atelier de production](sdi-scenario-equipment-downtime.md#enable-pfe-search)

### <a name="start-the-first-job-in-the-batch-order"></a>Démarrer la première tâche dans la commande par lots

Suivez ces étapes pour démarrer la première tâche de la commande par lots.

1. Accédez à **Contrôle de la production \> Contrôle et suivi de la production \> Exécution de l’atelier de production**.
1. Dans le champ **ID badge**, entrez *123*. Ensuite, sélectionnez **Se connecter**.
1. Si vous êtes invité à fournir un motif d’absence, sélectionnez l’une des cartes d’absence, puis sélectionnez **OK**.
1. Dans le champ **Rechercher**, saisissez le numéro de lot de commande que vous avez préalablement noté. Sélectionnez ensuite la clé **Retour**.
1. Sélectionnez la commande client, puis sélectionnez **Démarrer la tâche**.
1. Dans la boîte de dialogue **Démarrer la tâche**, sélectionnez **Démarrer**.

## <a name="set-up-the-production-delays-scenario"></a>Scénario de configuration des retards de production

Procédez comme suit pour configurer le scénario *Retards de production* dans Supply Chain Management.

1. Aller à **Contrôle de production \> Configurer \> Sensor Data Intelligence \> Scénarios**.
1. Dans la zone du scénario **Retards de production**, sélectionnez **Configurer** pour ouvrir l’assistant de configuration de ce scénario.
1. Sur la page **Capteurs**, sélectionnez **Nouveau** pour ajouter un capteur à la grille. Définissez ensuite les champs suivants correspondants :

    - **Identifiant du capteur** : saisissez l’ID du capteur que vous utilisez. (Si vous utilisez le simulateur en ligne Raspberry PI Azure IoT et que vous l’avez configuré comme décrit dans [Configurer un capteur simulé pour les tests](sdi-set-up-simulated-sensor.md), saisissez *ProductionDelay*.)
    - **Description du capteur** : entrez une description du capteur.

1. Répétez l’étape précédente pour chaque capteur que vous souhaitez ajouter maintenant. Vous pouvez revenir et ajouter d’autres capteurs à tout moment.
1. Cliquez sur **Suivant**.
1. Sur la page **Mise en correspondance des enregistrements commerciaux**, dans la section **Capteurs**, sélectionnez l’enregistrement de l’un des capteurs que vous venez d’ajouter.
1. Dans la section **Mise en correspondance des enregistrements commerciaux**, sélectionnez **Nouveau** dans la barre d’outils pour ajouter une ligne à la grille.
1. Dans la nouvelle ligne, définissez **Enregistrement commercial** sur la ressource avec laquelle vous surveillez le capteur sélectionné. (Si vous utilisez les données de démonstration que vous avez créées précédemment dans cet article, définissez le champ sur *3118, Machine de découpe de la mousse*.)
1. Cliquez sur **Suivant**.
1. Sur la page **Seuil d’écart pour le retard de production**, si vous utilisez les données de démonstration que vous avez créées précédemment dans cet article, procédez comme suit :

    1. Sélectionnez l’en-tête de colonne **Relation d’article** pour ouvrir une boîte de dialogue déroulante qui inclut des filtres de recherche pour la colonne. Saisissez *P0111* dans la zone de recherche, puis sélectionnez **Appliquer**.
    2. Sélectionnez la ligne où le champ **Opération** est défini sur *Découper/Couper*. Définissez le champ **Seuil de notification du délai (%)** sur le seuil (en pourcentage) auquel une notification doit être envoyée.

1. Cliquez sur **Suivant**.
1. Sur la page **Activer les capteurs**, dans la grille, sélectionnez le capteur que vous avez ajouté, puis sélectionnez **Activer**. Pour chaque capteur activé dans la grille, une coche apparaît dans la colonne **Actif**.
1. Sélectionnez **Terminer**.

## <a name="work-with-the-production-delays-scenario"></a>Utiliser le scénario de configuration des retards de production

### <a name="view-production-delay-data-on-the-resource-status-page"></a>Afficher les données de retard de production sur la page Statut de la ressource

Sur la page **Statut de la ressource**, les superviseurs peuvent surveiller une chronologie des signaux reçus des capteurs qui sont mappés à chaque ressource machine. Procédez comme suit pour configurer la chronologie.

1. Accédez à **Contrôle de la production \> Exécution de la fabrication \> Statut de la ressource**.
1. Dans la boîte de dialogue **Configurer**, définissez les champs suivants :

    - **Ressource** : sélectionnez les ressources que vous souhaitez surveiller. (Si vous utilisez les données de démonstration, sélectionnez *3118*.)
    - **Série chronologique 1** : sélectionnez l’enregistrement (clé de mesure) avec le format de nom suivant : *ProductionJobDelayed:ActualQuantity:&lt;JobId&gt;*
    - **Nom d’affichage** : saisissez *Signal partiel*.
