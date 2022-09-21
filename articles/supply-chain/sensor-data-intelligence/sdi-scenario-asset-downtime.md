---
title: Le scénario d’interruption des actifs
description: Cet article décrit le scénario d’interruption des actifs, qui vous permet d’utiliser les données des capteurs pour surveiller la disponibilité de vos actifs.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, EntAssetObjectProductionStop
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 944818557deebed06c02c00fd69de6e8f08bda83
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428376"
---
# <a name="the-asset-downtime-scenario"></a>Le scénario d’interruption des actifs

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Le scénario d’interruption des actifs génère un enregistrement d’interruption pour maintenance si aucun signal n’est reçu d’une machine dans un délai défini depuis la réception du dernier signal. Le scénario nécessite que vous équipiez votre machine d’un capteur qui envoie périodiquement un signal à votre Azure IoT Hub pendant que la machine fonctionne, mais n’envoie pas de signal lorsque la machine ne fonctionne pas.

## <a name="set-up-the-asset-downtime-scenario"></a>Configurer le scénario d’interruption des actifs

Procédez comme suit pour configurer le scénario *Interruption des actifs* dans Supply Chain Management.

1. Accédez à **Gestion d’actifs \> Configurer \> Sensor Data Intelligence \> Scénarios** pour ouvrir la page **Scénarios**.
2. Dans la zone du scénario **Interruption des actifs**, sélectionnez **Configurer** pour ouvrir l’assistant de configuration de ce scénario.
3. Sur la page **Capteurs**, sélectionnez **Nouveau** pour ajouter un capteur à la grille. Définissez ensuite les champs suivants correspondants :

    - **Identifiant du capteur** : saisissez l’ID du capteur que vous utilisez. (Si vous utilisez le simulateur en ligne Raspberry PI Azure IoT et que vous l’avez configuré comme décrit dans [Configurer un capteur simulé pour les tests](sdi-set-up-simulated-sensor.md), saisissez *AssetDownTime*.)
    - **Description du capteur** : entrez une description du capteur.

4. Répétez l’étape précédente pour chaque capteur que vous souhaitez ajouter maintenant. Vous pouvez revenir et ajouter d’autres capteurs à tout moment.
5. Cliquez sur **Suivant**.
6. Sur la page **Mise en correspondance des enregistrements commerciaux**, dans la section **Capteurs**, sélectionnez l’enregistrement de l’un des capteurs que vous venez d’ajouter.
7. Dans la section **Mise en correspondance des enregistrements commerciaux**, sélectionnez **Nouveau** dans la barre d’outils pour ajouter une ligne à la grille.
8. Dans la nouvelle ligne, définissez le champ **Enregistrement commercial** sur la ressource avec laquelle vous surveillez le capteur sélectionné. (Si vous utilisez les données de démonstration, sélectionnez *AK-101, Air Knife for Line 1*.)
9. Cliquez sur **Suivant**.
10. Sur la page **Seuil d’interruption de l’actif**, définissez combien de temps après le dernier signal le système doit attendre avant d’envoyer une notification d’interruption des actifs. Il existe deux manières de définir le seuil :

    - **Seuil par défaut (minutes)**  : définissez ce champ pour définir le seuil par défaut. Cette valeur s’applique à toutes les ressources où le champ **Seuil de notification (minutes)** est défini sur deux minutes ou moins. La valeur minimale est *2* (minutes).
    - **Seuil permettant de déterminer si l’ordinateur ne répond pas (minutes)**  : pour chaque ressource de la grille où vous ne souhaitez pas utiliser le seuil par défaut, entrez une valeur de remplacement dans ce champ. Les ressources configurées pour utiliser un seuil de deux minutes ou moins utiliseront le paramètre **Seuil par défaut (minutes)** à la place.
11. Cliquez sur **Suivant**.
12. Sur la page **Activer les capteurs**, dans la grille, sélectionnez le capteur que vous avez configuré, puis sélectionnez **Activer**. Pour chaque capteur activé dans la grille, une coche apparaît dans la colonne **Actif**.
13. Sélectionnez **Terminer**.

## <a name="work-with-the-asset-downtime-scenario"></a>Utiliser le scénario d’interruption des actifs

Si aucun signal de capteur n’est reçu d’un actif dans le seuil défini dans la configuration du scénario, le système créera un enregistrement de temps d’arrêt pour maintenance pour cet actif. Les responsables doivent examiner périodiquement les enregistrements des temps d’arrêt (par exemple, une fois pendant chaque période de travail) et appliquer les codes de motif et les heures de fin appropriés pour chaque enregistrement de temps d’arrêt. Suivez ces étapes pour afficher les enregistrements de temps d’arrêt pour maintenance d’un actif :

1. Accédez à **Gestion des actifs > Actifs > Tous les Actifs**.
2. Recherchez et sélectionnez l’actif à inspecter. (Si vous utilisez les données de démonstration, sélectionnez *AK-101*.)
3. Dans le volet Actions, ouvrez l’onglet **Actif** et, à partir du groupe **Ordre de travail**, sélectionnez **Temps d’arrêt pour maintenance** pour ouvrir la page des enregistrements de temps d’arrêt pour maintenance pour l’actif sélectionné.
