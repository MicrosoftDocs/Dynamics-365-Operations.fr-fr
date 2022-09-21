---
title: Le scénario de maintenance des actifs
description: Cet article décrit le scénario de maintenance des actifs, qui vous permet d’utiliser des données de capteur pour créer des enregistrements de compteur qui suivent l’utilisation d’un actif machine.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, EntAssetCounter
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: ff3944b987314a688a5829b05f8627479e3e79ed
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428342"
---
# <a name="the-asset-maintenance-scenario"></a>Le scénario de maintenance des actifs

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Le scénario *Maintenance des actifs* vous permet d’utiliser les données des capteurs pour créer des enregistrements de compteur. Les enregistrements de compteur suivent l’utilisation d’un actif machine et sont utilisés comme entrée pour générer le programme de maintenance des actifs machine.

## <a name="prepare-demo-data-for-the-asset-maintenance-scenario"></a>Préparer les données de démonstration pour le scénario de maintenance des actifs

Si vous souhaitez utiliser un système de démonstration pour tester le scénario *Maintenance des actifs*, utilisez un système où les [données de démonstration](../../fin-ops-core/fin-ops/get-started/demo-data.md) sont installées, sélectionnez l’entité juridique *USMF* (société) et préparez les données de démonstration supplémentaires comme décrit dans cette section. Si vous utilisez vos propres capteurs et données, vous pouvez ignorer cette section.

Dans cette section, vous configurerez l’actif *AK-101, Lame d’air* dans les données de démonstration à titre d’exemple. Vous verrez ensuite comment les travaux de maintenance à venir peuvent être prédits sur la base des signaux des capteurs qui mesurent le nombre d’heures de fonctionnement de la lame d’air. Vous établirez également un plan de maintenance où la lame d’air doit être entretenue toutes les 10 000 heures.

### <a name="set-up-a-sensor-simulator"></a>Mettre en place un simulateur de capteur

Si vous souhaitez essayer ce scénario sans utiliser de capteur physique, vous pouvez configurer un simulateur pour générer les signaux requis. Pour plus d’informations, voir [Paramétrer un capteur de simulation pour les tests](sdi-set-up-simulated-sensor.md).

### <a name="create-an-asset-counter-to-track-production-hours"></a>Créer un compteur d’actifs pour suivre les heures de production

Procédez comme suit pour créer un compteur d’actifs pour suivre les heures de production.

1. Accédez à **Gestion des actifs \> Paramétrage \> Types d’actifs \> Compteurs**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un compteur.
1. Dans l’en-tête, définissez les valeurs suivantes :

    - **Compteur :** *ProductionHr*
    - **Nom :** *Heures de production*

1. Dans l’organisateur **Général**, définissez les valeurs suivantes :

    - **Unité :** *heure*
    - **Mise à jour :** *Manuel*
    - **Regroupement total :** *Somme*

1. Dans l’organisateur **Types d’actif**, sélectionnez **Ajouter une ligne**.
1. Sur la nouvelle ligne, définissez le champ **Type d’actif** sur *Lame d’air*.

### <a name="create-a-maintenance-plan-for-the-asset"></a>Créer un plan de maintenance pour l’actif

Procédez comme suit pour créer un plan de maintenance pour l’actif.

1. Accédez à **Gestion des actifs \> Paramétrage \> Maintenance préventive \> Plan de maintenance**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un plan de maintenance.
1. Dans l’en-tête, définissez les valeurs suivantes :

    - **Plan de maintenance :** *AirKnife*
    - **Nom :** *Plan pour lames d’air*

1. Sur le raccourci **Général**, définissez les valeurs suivantes :

    - **Date de planification :** saisissez la date d’aujourd’hui.
    - **Actif :** *Oui*

1. Dans l’organisateur **Lignes**, sélectionnez **Ajouter une ligne de compteur d’actif** pour ajouter une ligne à la grille. Puis définissez les valeurs suivantes pour cette ligne :

    - **Description l’ordre de travail :** *Maintenance de la lame d’air*
    - **Type de tâche de maintenance :** *Préventive*
    - **Type d’intervalle :** *Répété depuis le dernier ordre de travail*
    - **Période fréquence :** *10000*
    - **Compteur :** *ProductionHr*

## <a name="set-up-the-asset-maintenance-scenario"></a>Configurer le scénario de maintenance des actifs

Procédez comme suit pour configurer le scénario *Maintenance des actifs* dans Supply Chain Management.

1. Accédez à **Gestion d’actifs \> Configurer \> Sensor Data Intelligence \> Scénarios**.
1. Dans la zone du scénario **Maintenance des actifs**, sélectionnez **Configurer** pour ouvrir l’assistant de configuration de ce scénario.
1. Sur la page **Capteurs**, sélectionnez **Nouveau** pour ajouter un capteur à la grille. Définissez ensuite les champs suivants correspondants :

    - **Identifiant du capteur** : saisissez l’ID du capteur que vous utilisez. (Si vous utilisez le simulateur en ligne Raspberry PI Azure IoT et que vous l’avez configuré comme décrit dans [Configurer un capteur simulé pour les tests](sdi-set-up-simulated-sensor.md), saisissez *AssetMaintenance*.)
    - **Description du capteur** : entrez une description du capteur.

1. Répétez l’étape précédente pour chaque capteur que vous souhaitez ajouter maintenant. Vous pouvez revenir et ajouter d’autres capteurs à tout moment.
1. Cliquez sur **Suivant**.
1. Sur la page **Mise en correspondance des enregistrements commerciaux**, dans la section **Capteurs**, sélectionnez l’enregistrement de l’un des capteurs que vous venez d’ajouter.
1. Dans la section **Mise en correspondance des enregistrements commerciaux**, sélectionnez **Nouveau** dans la barre d’outils pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, le champ **Type d’enregistrement commercial** doit automatiquement être défini sur *Assets(EntAssetObjectTable)*. Définissez le champ **Enregistrement commercial** sur la ressource avec laquelle vous surveillez le capteur sélectionné. (Si vous utilisez les données de démonstration que vous avez créées précédemment dans cet article, définissez-les sur *AK-101, AK-101 Lame d’air pour Ligne 1*.)
1. Immédiatement après avoir sélectionné un type d’enregistrement commercial pour la ligne que vous avez ajoutée à l’étape précédente, une deuxième ligne est automatiquement ajoutée à la grille. Sur cette ligne, le champ **Type d’enregistrement commercial** doit être défini sur *Counters(EntAssetCounterType)*. Définissez le champ **Enregistrement commercial** sur le compteur d’actifs que vous mettez à jour en fonction des signaux du capteur sélectionné. (Si vous utilisez les données de démonstration que vous avez créées précédemment dans cet article, définissez-les sur *ProductionHr, Heures de production*.)
1. Cliquez sur **Suivant**.
1. Sur la page **Activer les capteurs**, dans la grille, sélectionnez le capteur que vous avez ajouté, puis sélectionnez **Activer**. Pour chaque capteur activé dans la grille, une coche apparaît dans la colonne **Actif**.
1. Sélectionnez **Terminer**.

## <a name="work-with-the-asset-maintenance-scenario"></a>Utiliser le scénario de maintenance des actifs

### <a name="view-counter-values"></a>Afficher les valeurs de compteur

Une fois les données préparées et le scénario *Maintenance des actifs* configuré et activé, vous pouvez voir comment les enregistrements d’un compteur d’actifs sont insérés en fonction des données du capteur.

1. Accédez à **Gestion des actifs \> Actifs \> Tous les Actifs**.
1. Recherchez et sélectionnez l’actif à inspecter. (Si vous utilisez les données de démonstration que vous avez créées précédemment dans cet article, sélectionnez *AK-101*.)
1. Sur le volet Actions, sous l’onglet **Actif**, dans le groupe **Préventif**, sélectionnez **Compteurs** pour ouvrir la page pour les enregistrements du compteur pour l’actif *AK-101*.

### <a name="generate-maintenance-work-orders"></a>Générer les ordres de travail de maintenance

Après avoir activé le scénario *Maintenance des actifs* et configuré le plan de maintenance, vous pouvez exécuter le calendrier de maintenance pour générer des ordres de travail de maintenance. Pour plus d’informations sur l’utilisation de la maintenance préventive, voir [Vue d’ensemble de la maintenance préventive](../asset-management/preventive-and-reactive-maintenance/preventive-maintenance-overview.md).
