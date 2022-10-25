---
title: Configurer un capteur simulé pour les tests
description: Cet article décrit comment configurer un simulateur que vous pouvez utiliser pour tester Sensor Data Intelligence sans installer de capteurs physiques.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: f12d6e1d417a260477b1eb4e027b850d1862f51f
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689802"
---
# <a name="set-up-a-simulated-sensor-for-testing"></a>Configurer un capteur simulé pour les tests

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Si vous souhaitez tester Sensor Data Intelligence sans installer de capteurs physiques, vous pouvez utiliser le service *Simulateur en ligne Raspberry PI Azure IoT* pour émuler les signaux des capteurs et les envoyer à votre solution Internet des objets (IoT) sur Microsoft Azure. Pour plus d’informations sur le simulateur, voir [Connecter le simulateur en ligne Raspberry Pi à Azure IoT Hub (Node.js)](/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started).

## <a name="video-instructions"></a>Instructions vidéo

La vidéo suivante montre comment configurer un capteur simulé pour le test. Les sections restantes de cet article fournissent les mêmes instructions dans un format texte.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE588g6]

## <a name="create-a-device-in-azure-iot-hub"></a>Créer un appareil dans Azure IoT Hub

Vous devez d’abord configurer un appareil pour authentifier les signaux du capteur auprès d’Azure IoT Hub.

1. Dans Azure, accédez à la liste des ressources du groupe de ressources que vous avez créé pour une utilisation avec Sensor Data Intelligence. (Pour plus d’informations, voir [Déployer une solution IoT sur Azure](sdi-deploy-iot-solution-on-azure.md).)
1. Dans la liste des ressources, recherchez l’enregistrement où le champ **Type** est défini sur *hub IoT*. Dans la colonne **Nom**, sélectionnez le nom pour ouvrir la page Détails pour la ressource.
1. Dans le volet de navigation de gauche, sélectionnez **Appareils**.
1. Sur la page **Appareils**, sélectionnez **Ajouter un appareil**.
1. Sur la page **Créer un appareil**, définissez les champs suivants :

    - **ID de périphérique** : saisissez un nom pour le nouvel appareil (par exemple,*My-IoT-Device*).
    - **Type d’identification** : sélectionnez *Clés symétriques*.
    - **Générer automatiquement des clés** : cochez cette case.
    - **Connecter cet appareil à un hub IoT** : sélectionnez *Activer*.

1. Sélectionnez **Enregistrer** pour revenir à la page **Appareils**.
1. Recherchez le nouvel appareil dans la liste. Dans la colonne **ID de périphérique**, sélectionnez le nom pour ouvrir la page Détails pour l‘appareil. Si vous ne voyez pas le nouvel appareil dans la liste, actualisez la page.
1. Copiez la valeur **Chaîne de connexion principale** (par exemple, en sélectionnant le bouton **Copier dans le presse-papier**). Vous aurez besoin de cette valeur plus tard lorsque vous configurerez le simulateur Raspberry Pi IoT pour émuler les signaux des capteurs. Par conséquent, pensez à le coller dans un fichier texte pour le moment.

## <a name="add-the-azure-connection-string-to-the-raspberry-pi-iot-simulator"></a>Ajouter la chaîne de connexion Azure au simulateur Raspberry Pi IoT

Suivez ces étapes pour ajouter la chaîne de connexion de l’appareil dans Azure IoT Hub au script dans le service Raspberry.

1. Ouvrez le [simulateur Raspberry Pi IoT](https://azure-samples.github.io/raspberry-pi-web-simulator/).
1. Dans le volet de l’éditeur de code, recherchez la ligne contenant la commande suivante.

    `const connectionString = '[Your IoT hub device connection string]';`

1. Remplacez le texte d’aide, y compris les crochets, par la valeur **Chaîne de connexion principale** que vous avez copiée dans la section précédente. Le résultat doit ressembler à l’exemple ci-dessous.

    `const connectionString = 'HostName=XXX;DeviceId=YYY;SharedAccessKey=ZZZ';`

## <a name="add-sensor-ids-and-values-to-the-payload-in-the-raspberry-pi-iot-simulator"></a>Ajouter des ID de capteur et des valeurs à la charge utile dans le simulateur Raspberry Pi IoT

Vous devez maintenant configurer le simulateur Raspberry Pi IoT avec des capteurs simulés et les valeurs qu’ils enverront en tant que charges utiles.

- Dans l’éditeur de code du simulateur Raspberry Pi IoT, recherchez la fonction `getMessage` et éditez-la pour qu’elle corresponde au code suivant. (Les capteurs sont installés dans les lignes `cb()`.)

    ```cpp
    function getMessage(cb) {
        messageId++;
        sensor.readSensorData()
        .then(function (data) {
            cb(JSON.stringify({ value: 1, sensorId: 'MachineStatus' }), false);
            cb(JSON.stringify({ value: 70, sensorId: 'Quality' }), false);
            cb(JSON.stringify({ value: 1, sensorId: 'AssetMaintenance' }), false);
            cb(JSON.stringify({ value: 1, sensorId: 'ProductionDelay' }), false);
            cb(JSON.stringify({ value: 20, sensorId: 'AssetDowntime' }), false);
        })
        .catch(function (err) {
            console.error('Failed to read out sensor data: ' + err);
        });
    }
    ```

    > [!IMPORTANT]
    > Les ID des capteurs qui sont définis dans l’éditeur de code pour le simulateur Raspberry Pi IoT doivent être identiques aux ID des capteurs que vous spécifierez ultérieurement pour les scénarios dans Supply Chain Management. L’exemple de code précédent utilise des ID de capteur lisibles par l’homme. Cependant, dans un scénario réel, les ID de capteur seront des valeurs d’identificateur global unique (GUID) fournies par le fabricant du capteur. Les ID de capteur lisibles par l’homme qui sont utilisés dans cet exemple de code sont également utilisés dans les exemples de [Scénario de la qualité du produit](sdi-scenario-product-quality.md), [Scénario de maintenance des actifs](sdi-scenario-asset-maintenance.md), [Scénario des retards de production](sdi-scenario-production-delays.md), et [Scénario de statut de l’ordinateur](sdi-scenario-equipment-downtime.md)). Par conséquent, utilisez ce code si vous allez utiliser ces scénarios.

## <a name="edit-the-interval-for-sending-sensor-signals"></a>Modifier l’intervalle d’envoi des signaux de capteur

Vous devez maintenant définir l’intervalle auquel le simulateur Raspberry Pi IoT doit envoyer les signaux du capteur émulé.

1. Dans l’éditeur de code du simulateur Raspberry Pi IoT, recherchez l’appel de fonction suivant.

    `setInterval(sendMessage, 2000);`

2. Par défaut, le simulateur Raspberry Pi IoT envoie un signal de capteur toutes les 2 000 millisecondes (deux secondes). Vous pouvez ajuster la valeur comme vous le voulez.

## <a name="run-the-raspberry-pi-iot-simulator"></a>Exécuter le simulateur Raspberry Pi IoT

- Sélectionnez **Exécuter** pour démarrer le simulateur et commencer à envoyer des données de capteur simulées.
