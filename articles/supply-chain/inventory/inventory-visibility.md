---
title: Vue d'ensemble du complément de visibilité des stocks
description: Cette rubrique explique ce qu'est la visibilité des stocks et décrit ses fonctionnalités.
author: sherry-zheng
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: defbcdc7ada4471345f8c728522e15f16a8bec8f
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344286"
---
# <a name="inventory-visibility-add-in-overview"></a>Vue d'ensemble du complément de visibilité des stocks

[!include [banner](../includes/banner.md)]

Le complément de visibilité des stocks (également appelé *Visibilité du stock*) est un microservice indépendant et hautement évolutif qui permet un suivi des stocks en temps réel. Par conséquent, il fournit une vue globale du stock.

Les systèmes externes accèdent au service via des API RESTful. De cette façon, ils peuvent soit interroger les informations disponibles sur des ensembles de dimensions donnés, soit apporter des modifications à votre stock dans différentes sources de données personnalisées.

En tant que microservice basé sur Microsoft Dataverse, la visibilité des stocks offre une extensibilité. Vous pouvez utiliser Power Apps pour créer des applications. Vous pouvez également appliquer Power BI pour fournir des fonctionnalités personnalisées qui répondent aux besoins de votre entreprise.

Vous pouvez intégrer la visibilité des stocks à plusieurs systèmes tiers en définissant des options de configuration pour les dimensions de stock standardisées et en définissant des types de transaction. la visibilité des stocks prend également en charge l'extensibilité personnalisée grâce à des quantités calculées configurables.

## <a name="supported-features"></a>Fonctionnalités prises en charge

### <a name="inventory-visibility-integration-with-dynamics-365-supply-chain-management"></a>Intégration de la visibilité des stocks avec Dynamics 365 Supply Chain Management

La solution intégrée extrait les données de stock de Dynamics 365 Supply Chain Management et suit en permanence les changements de niveau des stocks. Pour plus d’informations, voir [Paramétrage de la visibilité des stocks](inventory-visibility-setup.md).

### <a name="get-a-global-view-of-inventory"></a>Obtenir une vue globale des stocks

La solution intégrée vous permet de définir vos propres sources de données et de centraliser les données de stock. Pour plus d’informations, voir [Configuration de la visibilité des stocks](inventory-visibility-configuration.md).

Il existe deux approches pour afficher vos stocks :

- Soumettez une requête via l'API hautes performances. Cette API peut renvoyer des données de stock en temps quasi réel directement à partir d'une instance mise en cache. Vous pouvez trouver des contrats et des exemples dans [API publiques de visibilité des stocks](inventory-visibility-api.md).
- Consultez la liste brute du stock disponible. Cette liste est périodiquement synchronisée à partir d'une instance mise en cache et est visible dans Dataverse. Pour plus d’informations, voir [Application de visibilité des stocks](inventory-visibility-power-platform.md).

### <a name="soft-reservations"></a>Réservations provisoires

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

La réservation provisoire s'applique lorsqu'une entreprise doit réserver une quantité spécifique de produits afin de prendre en charge, par exemple, l'exécution des commandes client tout en évitant la survente. Lorsqu'une commande client est créée et confirmée dans Supply Chain Management ou d'autres systèmes de gestion des commandes, une demande de réservation de la quantité est envoyée à la visibilité des stocks. La visibilité des stocks vous permet de réserver des produits qui ont des détails de dimension et des types de mouvement de stock spécifiques. (Pour plus d'informations, voir [Application de visibilité des stocks](inventory-visibility-power-platform.md).) Une fois la quantité réservée avec succès, un ID de réservation est renvoyé. Vous pouvez utiliser cet ID de réservation pour revenir à la commande d'origine dans Supply Chain Management ou d''autres systèmes de gestion des commandes.

La fonctionnalité est conçue pour qu'une réservation dans la visibilité des stocks ne modifie pas la quantité totale. Au lieu de cela, elle signale uniquement la quantité réservée. (Pour cette raison, cela s'appelle une *réservation provisoire* .) La quantité provisoire-réservée peut être contrepassée lorsque les produits sont consommés dans Supply Chain Management ou un système tiers en appelant à nouveau l'API pour effectuer une déduction de quantité et mettre à jour la quantité totale dans la visibilité des stocks. Pour plus d’informations, voir [Réservation dans la visibilité des stocks](inventory-visibility-reservations.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
