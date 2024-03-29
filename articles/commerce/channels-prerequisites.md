---
title: Conditions préalables à la configuration de canal
description: Cet article présente une vue d’ensemble des conditions préalables au paramétrage des canaux dans Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 02/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 98ca2dc4691534853467c1680890199d08bc4e79
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282293"
---
# <a name="channel-setup-prerequisites"></a>Conditions préalables à la configuration de canal

[!include [banner](includes/banner.md)]

Cet article présente une vue d’ensemble des conditions préalables au paramétrage du canal dans Microsoft Dynamics 365 Commerce.

Avant qu’un canal Dynamics 365 Commerce puisse être créé, plusieurs tâches prérequises doivent être effectuées. Les listes de tâches prérequises suivantes sont organisées par type de canal.

> [!NOTE]
> Certains documents sont en cours de rédaction et les liens seront mis à jour au fur et à mesure que de nouveaux contenus seront publiés.

## <a name="initialization"></a>Initialisation

- [Initialiser les données de départ](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a>Prérequis globaux requis pour tous les types de canaux

- [Définissez et configurez votre structure d’entité juridique](channels-legal-entities.md) 
- [Configurer votre hiérarchie d’organisation](channels-org-hierarchies.md)
- [Paramétrer un entrepôt](channels-setup-warehouse.md)
- [Configurer la taxe de vente](../finance/general-ledger/indirect-taxes-overview.md?toc=/dynamics365/commerce/toc.json)
- [Paramétrer un profil de notification par e-mail](email-notification-profiles.md)
- [Définir des souches de numéros](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=/dynamics365/commerce/toc.json)
- [Paramétrer un client et un carnet d’adresses par défaut](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a>Conditions préalables du canal de vente au détail

- [Codes info et groupes de codes info](info-codes-retail.md)
- [Paramétrer un profil de fonctionnalité de la vente au détail](retail-functionality-profile.md)
- [Paramétrer un carnet d’adresses d’employé](new-address-book.md)
- [Paramétrer une mise en page d’écran](pos-screen-layouts.md)
- [Paramétrer une station matérielle](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a>Conditions préalables du canal de centre d’appels

- Paramètres du centre d’appels
- [Commande au centre d’appels et modes de paiement des remboursements](work-with-payments.md)
- [Modes de livraison et frais du centre d’appels](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a>Conditions préalables pour les canaux en ligne

- [Créer un profil de fonctionnalité en ligne](online-functionality-profile.md)

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation des canaux](channels-overview.md)

[Vue d’ensemble des organisations et des hiérarchies d’organisation](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Configurer des hiérarchies d’organisation](channels-org-hierarchies.md)

[Créer des entités juridiques](channels-legal-entities.md)

[Paramétrer un canal de vente au détail](channel-setup-retail.md)
    
[Paramétrer un canal en ligne](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
