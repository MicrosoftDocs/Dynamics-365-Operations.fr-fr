---
title: Fonctionnalité de vente du centre d’appels
description: Cet article fournit une vue d’ensemble de la fonctionnalité de vente du centre d’appels dans Dynamics 365 Commerce.
author: josaw1
ms.date: 04/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 7167dbd99da7969bc3887a5980c0df0d22ee35be
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884028"
---
# <a name="call-center-sales-functionality"></a>Fonctionnalité de vente du centre d’appels

[!include [banner](includes/banner.md)]


Dans Dynamics 365 Commerce, un centre d’appels est un type de canal qui peut être défini dans l’application. La définition d’un canal spécifique pour vos entités de centre d’appels permet au système d’associer les valeurs par défaut de données spécifiques et les valeurs par défaut du traitement des commandes aux commandes client créées par un utilisateur du canal de centre d’appels.

Les fonctionnalités du centre d’appels comprennent les prix et les promotions avancés, les catalogues, les cartes cadeaux, les programmes de fidélité et les coupons. Les commandes du centre d’appels sont également utilisées par l’application POS pour prendre en charge les scénarios d’exécution des commandes sur plusieurs canaux.

Il est important de noter que le module Centre d’appels peut être utilisé par d’autres secteurs d’activité en dehors de Commerce, mais la version actuelle de l’application de centre d’appels n’a pas été optimisée pour une utilisation dans les scénarios de traitement des commandes interentreprises (B2B), ou les scénarios où les commandes contiennent un grand nombre de lignes de vente. Il est recommandé aux utilisateurs qui souhaitent utiliser les fonctionnalités du centre d’appels pour le traitement des commandes en dehors du traitement standard des transactions destinées directement aux consommateurs, de prendre le temps nécessaire de tester et de valider que l’activation de la fonctionnalité de centre d’appels répond aux besoins fonctionnels et de performances.

Outre la prise en charge de la création des commandes, le module Centre d’appels fournit également une application de service client conviviale qui permet aux utilisateurs de localiser facilement les comptes client et d’examiner l’ensemble des données et attributs de commande client associés. L’écran du service client est conçu pour permettre à un utilisateur d’accéder rapidement aux données associées aux commandes afin de répondre aux questions les plus courantes transmises par les clients.

Cette page fournit des liens vers la documentation appropriée associée au paramétrage, à la configuration et à l’utilisation fonctionnelle des fonctionnalités du centre d’appels.


## <a name="configure-the-call-center"></a>Configurer le centre d’appels

[Paramétrer des canaux de centre d’appels](set-up-order-processing-options.md)

## <a name="configure-order-processing"></a>Configurer le traitement des commandes

[Paramétrer et utiliser les alertes pour fraude dans le centre d’appels](set-up-fraud-alerts.md)

[Configurer et utiliser les blocages de commande dans le centre d’appels](work-with-order-holds.md)

## <a name="configure-payment-processing"></a>Configurer le traitement des paiements

[Modes de paiement dans les centres d’appels](work-with-payments.md)

## <a name="configure-delivery-modes"></a>Configurer les modes de livraison

[Configurer les modes de livraison et les frais du centre d’appels](configure-call-center-delivery.md)

## <a name="configure-direct-marketing"></a>Configurer le marketing direct

[Catalogues de centre d’appels](call-center-catalogs.md)

[Paramétrer l’analyse RFM (récence, fréquence et valeur monétaire)](set-up-rfm-analysis.md)

## <a name="configure-continuity-programs"></a>Configurer les programmes de continuité

[Paramétrer des programmes périodiques pour les centres d’appels](set-up-continuity-program.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]