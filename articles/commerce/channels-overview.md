---
title: Vue d’ensemble des canaux
description: Cet article présente une vue d’ensemble des canaux dans Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.assetid: ''
ms.openlocfilehash: ad31f466563aeb38f28f9761828e6708895005b8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280418"
---
# <a name="channels-overview"></a>Vue d’ensemble des canaux


[!include [banner](includes/banner.md)]

Cet article présente une vue d’ensemble des canaux dans Microsoft Dynamics 365 Commerce. Elle inclut des informations sur les tâches que vous devez effectuer avant et après avoir paramétré chaque canal.

## <a name="types-of-channels"></a>Types de canaux

Dynamics 365 Commerce prend en charge trois types de canaux différents : vente au détail, centre d’appels et canaux en ligne.

### <a name="retail-channels"></a>Canaux de vente au détail

Les canaux de vente au détail représentent les magasins physiques standards. Chaque magasin peut avoir ses propres registres, comptes de revenus et dépenses et personnel de point de vente (PDV). 

### <a name="call-center-channels"></a>Canaux de centre d’appels

Les canaux de centre d’appels représentent la gestion des commandes et des clients du centre d’appels.

### <a name="online-channels"></a>Canaux en ligne

Les canaux en ligne représentent les vitrines de commerce électronique en ligne. Une fois qu’un canal en ligne est créé, un site doit être créé à l’aide de l’outil générateur de site Microsoft Dynamics 365 Commerce ou d’une autre solution de commerce électronique tiers.

## <a name="channel-setup-basics"></a>Principes de base du paramétrage des canaux

Le paramétrage des canaux est effectuée dans l’outil Commerce. Chaque canal peut avoir ses propres modes de paiement, groupes de prix, hiérarchies de produits, assortiments et ensemble de produits. Une fois un canal créé, vous affectez les produits dont vous souhaitez la présence dans ce magasin et que vous voulez vendre. Chaque type de canal possède un ensemble unique de fonctionnalités qui peuvent avoir besoin d’être configurées. Par exemple, un canal de vente au détail a besoin d’employés, de registres et de clients affectés. Une fois qu’un nouveau canal est créé, il doit être affecté à une hiérarchie d’organisation.

## <a name="channel-setup-prerequisites"></a>Conditions préalables au paramétrage du canal

Avant de pouvoir paramétrer un canal, vous devez effectuer certaines tâches prérequises en fonction du type de canal. Pour plus d’informations, voir [Conditions préalables au paramétrage du canal](channels-prerequisites.md).

## <a name="set-up-a-channel"></a>Paramétrer un canal

Après avoir effectué les tâches prérequises, pour obtenir des instructions de paramétrage supplémentaires, utilisez les liens suivants.

- [Paramétrer un canal de vente au détail](channel-setup-retail.md)
- [Paramétrer un canal de centre d’appels](channel-setup-callcenter.md)
- [Paramétrer un canal en ligne](channel-setup-online.md)

<!--
## Post-channel configuration

After you create a channel, you may need to complete some of the below tasks:

- [Add channel to an organizational hierarchy](add-channel-org-hierarchy.md)
- Set up fulfillment groups. (LINK TBD)
- Configure the POS registers for the store. (LINK TBD)
- Assign product assortments to the store. (LINK TBD)
- Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store. (LINK TBD)
- Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.(LINK TBD)
- Publish the retail store to send store data to Retail POS. (LINK TBD)
- Run the jobs to send the store data to Retail POS. (LINK TBD)
-->

## <a name="additional-resources"></a>Ressources supplémentaires

[Conditions préalables au paramétrage du canal](channels-prerequisites.md)

[Paramétrer un canal de vente au détail](channel-setup-retail.md)
    
[Paramétrer un canal en ligne](channel-setup-online.md)

[Paramétrer un canal de centre d’appels](channel-setup-callcenter.md)

[Configurer des hiérarchies d’organisation](channels-org-hierarchies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
