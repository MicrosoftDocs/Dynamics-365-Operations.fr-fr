---
title: Le scénario de la qualité du produit
description: Cet article fournit des informations sur le scénario de qualité du produit. Ce scénario utilise un capteur pour mesurer la qualité d’un lot de produits et génère une alerte si une mesure dépasse un seuil défini.
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
ms.openlocfilehash: 8c4808ea3a0389c2a8699f0e11ea154705a6916d
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428357"
---
# <a name="the-product-quality-scenario"></a>Le scénario de la qualité du produit

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Dans le scénario *Qualité du produit*, un capteur est mis en place pour mesurer la qualité d’un lot de produits dans l’atelier. Si une mesure dépasse un seuil défini pour le produit, une notification s’affiche sur le tableau de bord du superviseur. Par exemple, un capteur mesure l’humidité d’un produit alimentaire qui sort de la chaîne de production. Si la mesure est en dehors de la valeur minimale ou maximale autorisée pour l’humidité du produit, une notification est générée.

## <a name="scenario-dependencies"></a>Dépendances de scénario

Le scénario *Qualité du produit* a les dépendances suivantes :

- Une alerte peut être déclenchée si un ordre de fabrication s’exécute sur une machine mappée, et si cette machine produit un produit avec un attribut de lot mappé.
- Un signal représentant l’attribut de lot doit être envoyé au hub IoT et un nom de propriété unique doit être inclus.

## <a name="prepare-demo-data-for-the-product-quality-scenario"></a>Préparer les données de démonstration pour le scénario de qualité de produit

Si vous souhaitez utiliser un système de démonstration pour tester le scénario *Qualité du produit*, utilisez un système où les [données de démonstration](../../fin-ops-core/fin-ops/get-started/demo-data.md) sont installées, sélectionnez l’entité juridique *USMF* (société) et préparez les données de démonstration supplémentaires comme décrit dans cette section. Si vous utilisez vos propres capteurs et données, vous pouvez ignorer cette section.

Dans cette section, vous allez configurer les données de démonstration afin que vous puissiez utiliser le produit lancé *P0111* (*Boîtier composite*) avec le scénario de *qualité du produit*. Dans ce scénario, le système vérifie si une valeur d’attribut de lot mesurée par un capteur est en dehors du seuil défini pour un attribut de lot associé au produit.

### <a name="set-up-a-sensor-simulator"></a>Mettre en place un simulateur de capteur

Si vous souhaitez essayer ce scénario sans utiliser de capteur physique, vous pouvez configurer un simulateur pour générer les signaux requis. Pour plus d’informations, voir [Paramétrer un capteur de simulation pour les tests](sdi-set-up-simulated-sensor.md).

### <a name="associate-a-batch-attribute-and-resource-with-product-p0111"></a>Associer un attribut de lot et une ressource au produit P0111

Suivez ces étapes pour associer un attribut de lot au produit *P0111* (*Boîtier composite*) et vérifiez que la ressource *3118* (*Machine de découpe de mousse*) est utilisée à cette fin.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Recherchez le produit dont le champ **Numéro d’article** est défini sur *P0111*.
1. Dans le volet Actions, sous l’onglet **Gérer le stock**, dans le groupe **Attributs de lot**, sélectionnez **Spécifique au produit**.
1. Sur la page **Spécifique au produit**, sélectionnez **Nouveau** pour créer un attribut de lot spécifique au produit.
1. Dans l’en-tête, définissez les champs suivants :

    - **Code d’attribut** : sélectionnez la portée des attributs que vous surveillerez (*Table*, *Groupe* ou *Tout*). Pour ce scénario, sélectionnez *Table*, car vous surveillerez toujours un seul attribut.
    - **Relation d’attribut** : sélectionnez l’attribut que vous utiliserez pour surveiller la valeur du scénario de *qualité du produit*. Pour cet exemple, sélectionnez *Concentration*, qui est un attribut inclus dans les données de démonstration standard.

1. Sur le raccourci **Valeurs**, dans les champs **Minimum** et **Maximum**, définissez la plage de valeurs acceptables que l’attribut doit signaler pour réussir le contrôle de qualité. Si le capteur signale une valeur en dehors de cette plage, le système l’identifiera comme une violation de la qualité. Les autres champs de ce raccourci ne sont pas pertinents pour le scénario de *qualité du produit*. Les valeurs par défaut que vous voyez actuellement proviennent des données de démonstration. Par conséquent, laissez-les tels quels et fermez la page **Spécifique au produit** pour revenir à la page **Détails du produit lancé** pour l’article *P0111*.
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

## <a name="set-up-the-product-quality-scenario"></a>Configurer le scénario de la qualité du produit

Procédez comme suit pour configurer le scénario *Qualité du produit* dans Supply Chain Management.

1. Aller à **Contrôle de production \> Configurer \> Sensor Data Intelligence \> Scénarios**.
1. Dans la zone du scénario **Qualité du produit**, sélectionnez **Configurer** pour ouvrir l’assistant de configuration de ce scénario.
1. Sur la page **Capteurs**, sélectionnez **Nouveau** pour ajouter un capteur à la grille. Définissez ensuite les champs suivants correspondants :

    - **Identifiant du capteur** : saisissez l’ID du capteur que vous utilisez. (Si vous utilisez le simulateur en ligne Raspberry PI Azure IoT et que vous l’avez configuré comme décrit dans [Configurer un capteur simulé pour les tests](sdi-set-up-simulated-sensor.md), saisissez *Quality*.)
    - **Description du capteur** : entrez une description du capteur.

1. Répétez l’étape précédente pour chaque capteur que vous souhaitez ajouter maintenant. Vous pouvez revenir et ajouter d’autres capteurs à tout moment.
1. Cliquez sur **Suivant**.
1. Sur la page **Mise en correspondance des enregistrements commerciaux**, dans la section **Capteurs**, sélectionnez l’enregistrement de l’un des capteurs que vous venez d’ajouter.
1. Dans la section **Mise en correspondance des enregistrements commerciaux**, sélectionnez **Nouveau** dans la barre d’outils pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, le champ **Type d’enregistrement commercial** doit automatiquement être défini sur *Resources(WrkCtrTable)*. Définissez le champ **Enregistrement commercial** sur la ressource avec laquelle vous surveillez le capteur sélectionné. (Si vous utilisez les données de démonstration que vous avez créées précédemment dans cet article, définissez le champ sur *3118, Machine de découpe de la mousse*.)
1. Immédiatement après avoir sélectionné un type d’enregistrement commercial pour la ligne que vous avez ajoutée à l’étape précédente, une deuxième ligne est automatiquement ajoutée à la grille. Sur cette ligne, le champ **Type d’enregistrement commercial** doit être défini sur *Batch attributes(PdsBatchAttrib)*. Définissez le champ **Enregistrement commercial** sur l’attribut de traitement par lots avec lequel vous surveillez le capteur sélectionné. (Si vous utilisez les données de démonstration que vous avez créées précédemment dans cet article, définissez-les sur *Concentration, Pourcentage de concentration*.)
1. Cliquez sur **Suivant**.
1. Sur la page **Activer les capteurs**, dans la grille, sélectionnez le capteur que vous avez ajouté, puis sélectionnez **Activer**. Pour chaque capteur activé dans la grille, une coche apparaît dans la colonne **Actif**.
1. Sélectionnez **Terminer**.

## <a name="work-with-the-product-quality-scenario"></a>Utiliser le scénario de la qualité du produit

### <a name="view-product-quality-data-on-the-resource-status-page"></a>Afficher les données de qualité du produit sur la page Statut de la ressource

Sur la page **Statut de la ressource**, les superviseurs peuvent surveiller une chronologie du signal de qualité du produit reçu des capteurs qui sont mappés à chaque ressource machine. Procédez comme suit pour configurer la chronologie.

1. Accédez à **Contrôle de la production \> Exécution de la fabrication \> Statut de la ressource**.
1. Dans la boîte de dialogue **Configurer**, définissez les champs suivants :

    - **Ressource** : sélectionnez les ressources que vous souhaitez surveiller. (Si vous utilisez les données de démonstration, sélectionnez *3118*.)
    - **Série chronologique 1** : sélectionnez l’enregistrement (clé de mesure) avec le format de nom suivant : *ProductQuality:&lt;JobId&gt;.&lt;AttributeName&gt;*
    - **Nom d’affichage** : saisissez *Valeurs d’attribut de lot*.

L’illustration suivante montre un exemple de données de qualité du produit sur la page **Statut de la ressource** lorsque la valeur se situe dans la plage des valeurs acceptables.

![Données de qualité du produit sur la page Statut de la ressource lorsque la valeur est dans la plage.](media/sdi-product-quality-in-range.png "Données de qualité du produit sur la page Statut de la ressource lorsque la valeur est dans la plage")

L’illustration suivante montre un exemple de données de qualité du produit lorsqu’une valeur hors plage est détectée.

![Données de qualité du produit sur la page Statut de la ressource lorsque une valeur hors plage est détectée.](media/sdi-product-quality-out-of-range.png "Données de qualité du produit sur la page Statut de la ressource lorsque une valeur hors plage est détectée")

### <a name="view-product-quality-data-on-the-notifications-page"></a>Afficher les données de qualité du produit sur la page Notifications

Sur la page **Notifications**, les superviseurs peuvent afficher la notification générée lorsque le capteur mesure une valeur d’attribut de lot qui tombe en dehors du seuil défini pour l’attribut de lot. Chaque notification fournit une vue d’ensemble de la tâche de production affectée par la panne et offre la possibilité de réaffecter la tâche affectée à une autre ressource.

Pour ouvrir la page **Notification**, accédez à **Contrôle de la production \> Recherches et états \> Sensor Data Intelligence \> Notifications**.

L’illustration suivante présente un exemple de notification de la qualité du produit.

![Exemple de notification de la qualité du produit.](media/sdi-product-quality-notification.png "Exemple de notification de la qualité du produit")
