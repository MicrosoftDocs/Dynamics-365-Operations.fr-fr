---
title: Page d’accueil de Sensor Data Intelligence
description: Cet article fournit une vue d’ensemble de Sensor Data Intelligence. Les organisations peuvent utiliser cette fonctionnalité pour piloter les processus métier dans Microsoft Dynamics 365 Supply Chain Management, basé sur les signaux de l’Internet des objets (IoT) provenant des machines et des équipements de l’atelier de production.
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
ms.openlocfilehash: 2e4cd8d4d4ffcd10d02fbf26615f12cdd6ccca9e
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428368"
---
# <a name="sensor-data-intelligence-home-page"></a>Page d’accueil de Sensor Data Intelligence

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Sensor Data Intelligence pour Microsoft Dynamics 365 Supply Chain Management permet aux organisations de piloter des processus métier dans Supply Chain Management, sur les signaux de l’Internet des objets (IoT) provenant des machines et des équipements de l’atelier de production. Il s’agit d’une version mise à jour et renommée de la fonctionnalité *Intelligence IoT* qui était auparavant disponible pour Supply Chain Management.

Sensor Data Intelligence vous permet d’effectuer les tâches suivantes :

- Collectez les détails des machines et des équipements pour mettre à jour les valeurs des compteurs d’actifs de maintenance dans Supply Chain Management et pilotez la maintenance prédictive.
- Configurez la solution à l’aide d’un simple assistant d’intégration au lieu d’installer et de configurer manuellement les composants dans Microsoft Dynamics Lifecycle Services (LCS).
- Déployez des composants sur votre propre abonnement, afin d’avoir plus de flexibilité pour gérer les composants Azure.
- Configurez, mettez à l’échelle et étendez la solution en tant que logique métier qui s’exécute sur les composants Azure. Ces composants sont maintenant gérés sur votre propre abonnement. Par conséquent, vous pouvez les personnaliser selon vos besoins pour répondre aux besoins uniques de votre entreprise.

## <a name="business-scenarios"></a>Scénarios métier

Sensor Data Intelligence permet plusieurs types de fonctionnalités, chacune étant représentée par un *scénario* spécifique dans le système. Chaque scénario fournit un ensemble spécialisé d’options de configuration dans le système, comme détaillé dans le tableau suivant.

| Scénario | Description |
|---|---|
| [Interruption de l’actif](sdi-scenario-asset-downtime.md) | Suivez avec précision l’efficacité des actifs de la machine en utilisant les données des capteurs pour suivre les temps d’arrêt de la machine. |
| [Maintenance de l’actif](sdi-scenario-asset-maintenance.md) | Minimisez les coûts de maintenance et prolongez la durée de vie des actifs en améliorant les plans de maintenance basés sur les lectures de capteurs des points de contrôle critiques pour les actifs des machines. |
| [Statut de l’ordinateur](sdi-scenario-equipment-downtime.md) | Garantissez l’efficacité des opérations en utilisant les lectures des capteurs pour informer les planificateurs des pannes de machine et fournir des options pour atténuer les retards potentiels. |
| [Qualité des produits](sdi-scenario-product-quality.md) | Assurez la qualité des lots de produits en comparant les lectures des capteurs pour les propriétés réelles de chaque lot de produits, telles que l’humidité, la température ou les mesures de qualité personnalisées. Le système informera les utilisateurs lorsque des écarts se produisent. |
| [Retards de production](sdi-scenario-production-delays.md) | Utilisez les lectures des capteurs pour comparer le temps de cycle réel au temps de cycle prévu et avertissez les superviseurs lorsque la production n’est pas dans les délais. Les superviseurs peuvent alors intervenir au besoin pour assurer une efficacité maximale des opérations. |

## <a name="architecture"></a>Architecture

Le schéma d’architecture suivant donne un aperçu de la solution et de ses composants.

![Diagramme architectural de Sensor Data Intelligence.](media/sdi-architecture.png "Diagramme architectural de Sensor Data Intelligence")
