---
title: Formats de message pour les messages IoT Hub
description: Cette rubrique explique comment vous devez concevoir un schéma de message que vous pouvez utiliser dans l’intelligence IoT.
author: robinarh
ms.date: 04/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ecf4a70d69d24ea75f5448339057e7017cb93af
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/19/2021
ms.locfileid: "7651991"
---
# <a name="schema-formats-for-iot-hub-messages"></a>Formats de message pour les messages IoT Hub

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment vous devez concevoir un schéma de message que vous pouvez utiliser dans l’intelligence IoT.

## <a name="message-requirements"></a>Exigences relatives aux messages

Les règles suivantes s’appliquent à la surveillance des messages dans l’intelligence IoT :

+ Les schémas de message doivent être au format JavaScript Object Notation (JSON).
+ Une propriété **horodatage** UNIX, où la valeur est exprimée en millisecondes (ms), doit être présente dans le message Microsoft Azure IoT Hub.
+ Un message n’est suivi que s’il contient toutes les propriétés définies dans la configuration du scénario. Par exemple, si vous définissez les propriétés **id**, **horodatage** et **valeur**, le message suivant est surveillé.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True
    }
    ```

    Ce message n’est pas surveillé, car la propriété **valeur** est manquante.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
    }
    ```

+ L’intelligence IoT ignore les propriétés du message qui ne sont pas définies dans la configuration du scénario. Par exemple, si vous définissez les propriétés **id**, **horodatage** et **valeur**, l’intelligence IoT surveillera tous les messages suivants.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True
    },
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True,
        "machine" : "Machine1225",
    },
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True,
         "activity": "PartOut"
    },
    ```

+ L’intelligence IoT ignore en mode silencieux les messages qui ne correspondent pas aux critères de configuration du scénario.
+ Vous pouvez définir et utiliser plusieurs types de schémas de message.
+ Tous les types de schéma de message ne doivent pas être définis. Seuls les schémas qui seront utilisés pour les scénarios d’intelligence IoT doivent être définis.

## <a name="id-value-pair-schema"></a>Schéma de paire ID-valeur

Une paire ID-valeur est un modèle courant pour les schémas de message d’intelligence IoT. En utilisant une paire ID-valeur, vous vous assurez que votre schéma de message est le même dans tous les scénarios. Par exemple, voici un message pour le scénario **Temps d’arrêt de l’équipement** ou **Retards de fabrication**.

```json
{
    "id": "IoTInt.Machine1225.PartOut",
    "timestamp": 1576016821614,
    "value": True
}
```

Voici un message pour le scénario **Qualité des produits**.

```json
{
    "id": "IoTInt.Machine1225.Temperature",
    "timestamp": 1576016821614,
    "value": 105
}
```

Les deux messages précédents contiennent les propriétés **ID** et **valeur**. Les valeurs **ID** peuvent être mises en correspondance dans la table **Valeurs des données de signal** lors de la configuration du scénario. Pour le scénario **Temps d’arrêt de l’équipement**, vous mettrez en correspondance la valeur **IoTInt.Machine1225.PartOut**. Pour le scénario **Qualité des produits**, vous mettrez en correspondance la valeur **IoTInt.Machine1225.Temperature**.

Pour plus d’informations, voir la [Documentation Azure IoT Hub](/azure/iot-hub/).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]