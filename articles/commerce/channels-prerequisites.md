---
title: Conditions préalables au paramétrage du canal
description: Cette rubrique présente une vue d'ensemble des conditions préalables au paramétrage des canaux dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b861d90f1333c8f6e61a83602ed74e30b65f3dc1
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002287"
---
# <a name="channel-setup-prerequisites"></a>Conditions préalables au paramétrage du canal


[!include [banner](includes/banner.md)]

Cette rubrique présente une vue d'ensemble des conditions préalables au paramétrage du canal dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Avant qu'un canal Dynamics 365 Commerce puisse être créé, plusieurs tâches prérequises doivent être effectuées. Les listes de tâches prérequises suivantes sont organisées par type de canal.

> [!NOTE]
> Certains documents sont en cours de rédaction et les liens seront mis à jour au fur et à mesure que de nouveaux contenus seront publiés.

## <a name="initialization"></a>Initialisation

- [Initialiser les données de départ](../retail/enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a>Prérequis globaux requis pour tous les types de canaux

- [Définissez et configurez votre structure d'entité juridique](channels-legal-entities.md) 
- [Configurer votre hiérarchie d'organisation](channels-org-hierarchies.md)
- [Paramétrer un entrepôt](channels-setup-warehouse.md)
- [Configurer la taxe de vente](https://docs.microsoft.com/en-us/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json)
- [Paramétrer un profil de notification par e-mail](email-notification-profiles.md)
- [Définir des souches de numéros](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview?toc=/dynamics365/commerce/toc.json)
- [Paramétrer un client et un carnet d'adresses par défaut](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a>Conditions préalables du canal de vente au détail

- [Codes info et groupes de codes info](https://docs.microsoft.com/en-us/dynamics365/retail/info-codes-retail?toc=/dynamics365/commerce/toc.json)
- [Paramétrer un profil de fonctionnalité de la vente au détail](retail-functionality-profile.md)
- [Paramétrer un carnet d'adresses d'employé](new-address-book.md)
- [Paramétrer une mise en page d'écran](https://docs.microsoft.com/en-us/dynamics365/retail/pos-screen-layouts?toc=/dynamics365/commerce/toc.json)
- [Paramétrer une station matérielle](https://docs.microsoft.com/en-us/dynamics365/retail/retail-hardware-station-configuration-installation?toc=/dynamics365/commerce/toc.json)

## <a name="call-center-channel-prerequisites"></a>Conditions préalables du canal de centre d'appels

- Paramètres du centre d'appels
- Modes de remboursement du centre d'appels
- Types de locations
- Services de paiement
- Codes de blocage de commande

## <a name="online-channel-prerequisites"></a>Conditions préalables du canal en ligne

- [Créer un profil de fonctionnalité en ligne](online-functionality-profile.md)

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation des canaux](channels-overview.md)

[Vue d'ensemble des organisations et des hiérarchies d'organisation](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Configurer des hiérarchies d'organisation](channels-org-hierarchies.md)

[Créer des entités juridiques](channels-legal-entities.md)

[Paramétrer un canal de vente au détail](channel-setup-retail.md)
    
[Paramétrer un canal en ligne](channel-setup-online.md)
