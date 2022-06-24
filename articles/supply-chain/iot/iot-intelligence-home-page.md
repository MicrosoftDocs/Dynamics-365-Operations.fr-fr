---
title: Page d’accueil Intelligence IoT
description: Cet article fournit des liens vers des informations sur l’intelligence IoT.
author: johanhoffmann
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b43681b036379a6f95103d4bb17cbde018724552
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877622"
---
# <a name="iot-intelligence-home-page"></a>Page d’accueil Intelligence IoT

[!include [banner](../../includes/banner.md)]

> [!IMPORTANT]
> Cette fonction est actuellement disponible uniquement dans les pays et régions suivants :
>
> - États-Unis (États-Unis d’Amérique)
> - UE (Union européenne)
> - AU (Australie)
> - CA (Canada)
> - UK (Royaume-Uni)

L’intelligence IoT est un complément pour Microsoft Dynamics 365 Supply Chain Management. Il intègre les signaux de l’Internet des objets (IoT) avec les données de Supply Chain Management pour produire des informations exploitables.

L’intelligence IoT prend en charge les scénarios suivants :

- **Retards de fabrication** – Ce scénario compare la durée de cycle réelle à la durée de cycle planifiée. Supply Chain Management vous avertit quand la production ne respecte pas les délais, afin que vous puissiez intervenir pour maximiser l’efficacité opérationnelle et éviter les retards de commande.
- **Temps d’arrêt de l’équipement** – Ce scénario compare la disponibilité mesurée aux paramètres définis par l’utilisateur. Supply Chain Management vous avertit quand un seuil de panne est dépassé, afin que vous puissiez prendre des mesures telles que la replanification d’un ordre de travail de production ou la création d’un ordre de travail de maintenance.
- **Qualité des produits** – Ce scénario compare les lectures des capteurs, telles que l’humidité et la température, aux mesures de qualité définies par l’utilisateur. Supply Chain Management vous avertit quand un écart se produit, afin que vous puissiez intervenir pour continuer à respecter les normes de qualité et minimiser les déchets.

L’illustration suivante montre l’interaction entre Azure IoT Hub, l’intelligence IoT et Supply Chain Management.

![IoT Hub, l’intelligence IoT et Supply Chain Management.](media/iot_intelligence.png)

<!-- KFM: hide setup info for now

## Setup

You can set up and configure IoT Intelligence without writing any code. Here are the basic steps.

1. [Set up Azure resources](iot-azure-setup.md) – Create an IoT hub, a Redis cache, and a key vault that can be accessed from Supply Chain Management.
2. [Message schema formats for IoT Hub](iot-schema-format.md) – Configure your devices to send messages to IoT Hub, and define the JavaScript Object Notation (JSON) message format.
3. In Feature Management, enable the IoT Intelligence feature flag. 
4. [Install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md) – Install the add-in in LCS, and configure the Azure secrets.
5. [Set up metrics](iot-metrics-setup.md) – Set up metrics in Supply Chain Management.
6. [Scenario setup](iot-scenario-setup.md) – Set up the scenarios in Supply Chain Management.

-->

## <a name="tracking-and-maintenance"></a>Suivi et maintenance

- [Surveiller des scénarios dans Dynamics 365 Supply Chain Management](iot-management.md#monitor-scenarios)
- [Désactiver un scénario](iot-scenario-setup.md#disable-a-scenario)
- [Modifier un scénario d’intelligence IoT en cours d’exécution](iot-management.md#modify-a-running-iot-intelligence-scenario)
- [Options de simulation](iot-management.md#simulation-options)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]