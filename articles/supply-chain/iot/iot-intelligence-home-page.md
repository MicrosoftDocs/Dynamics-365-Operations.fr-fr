---
title: Page d’accueil Intelligence IoT
description: Cette rubrique fournit des liens vers des informations sur l’intelligence IoT.
author: tonyafehr
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.custom: intro-internal
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6b6c179052cdb9d1ca808d9cba089163bde0d5d5
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782679"
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

+ **Retards de fabrication** – Ce scénario compare la durée de cycle réelle à la durée de cycle planifiée. Supply Chain Management vous avertit lorsque la production ne respecte pas les délais, afin que vous puissiez intervenir pour maximiser l’efficacité opérationnelle et éviter les retards de commande.
+ **Temps d’arrêt de l’équipement** – Ce scénario compare la disponibilité mesurée aux paramètres définis par l’utilisateur. Supply Chain Management vous avertit lorsqu’un seuil de panne est dépassé, afin que vous puissiez prendre des mesures telles que la replanification d’un ordre de travail de production ou la création d’un ordre de travail de maintenance.
+ **Qualité des produits** – Ce scénario compare les lectures des capteurs, telles que l’humidité et la température, aux mesures de qualité définies par l’utilisateur. Supply Chain Management vous avertit lorsqu’un écart se produit, afin que vous puissiez intervenir pour continuer à respecter les normes de qualité et minimiser les déchets.

L’illustration suivante montre l’interaction entre Azure IoT Hub, l’intelligence IoT et Supply Chain Management.

![IoT Hub, l’intelligence IoT et Supply Chain Management.](media/iot_intelligence.png)

## <a name="setup"></a>Paramétrage

Vous pouvez installer et configurer l’intelligence IoT sans écrire de code. Voici les étapes de base.

1. [Paramétrer les ressources Azure](iot-azure-setup.md) – Créez un hub IoT, un cache Redis et un coffre de clés accessibles depuis Supply Chain Management.
2. [Formats du schéma de message pour hub IoT](iot-schema-format.md) – Configurez vos appareils pour envoyer des messages à IoT Hub et définissez le format de message JavaScript Object Notation (JSON).
3. Dans Gestion des fonctionnalités, activez l’indicateur de la fonctionnalité d’intelligence IoT. 
4. [Installez le complément d’intelligence IoT dans Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md) – Installez le complément dans LCS et configurez les secrets Azure.
5. [Configurer des mesures](iot-metrics-setup.md) – Configurez des mesures dans Supply Chain Management.
6. [Configuration d’un scénario](iot-scenario-setup.md) – Configurez les scénarios dans Supply Chain Management.

## <a name="tracking-and-maintenance"></a>Suivi et maintenance

+ [Surveiller des scénarios dans Dynamics 365 Supply Chain Management](iot-management.md#monitor-scenarios)
+ [Désactiver un scénario](iot-scenario-setup.md#disable-a-scenario)
+ [Désinstaller le complément](iot-lcs-setup.md#uninstall-addin)
+ [Modifier un scénario d’intelligence IoT en cours d’exécution](iot-management.md#modify-a-running-iot-intelligence-scenario)
+ [Options de simulation](iot-management.md#simulation-options)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]