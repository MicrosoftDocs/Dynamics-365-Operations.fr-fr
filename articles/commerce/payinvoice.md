---
title: Paramétrer des scénarios de règlement de facture
description: Cette rubrique décrit la procédure de configuration de Dynamics 365 Commerce pour prendre en charge différents scénarios relatifs aux règlements de facture.
author: josaw1
ms.date: 11/14/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 08d3cf48c0bea6f0e13dda49e53b314a6037860d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804551"
---
# <a name="set-up-pay-invoice-scenarios"></a>Paramétrer des scénarios de règlement de facture

[!include [banner](includes/banner.md)]

La fonctionnalité Payer la facture de Dynamics 365 Commerce a été développée pour prendre en charge ce qui suit :

- Le règlement de plusieurs factures de commande client dans une transaction de point de vente unique.
- Le paiement de différents types de facture client, y compris des factures financières, des factures basées sur des projets et des avoirs.

Pour activer ces scénarios, le profil de fonctionnalité pour les magasins doit être configuré, comme indiqué ci-dessous.

1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage Point de vente \> Profils Point de vente \> Profils de fonctionnalité** et sélectionnez un profil associé au magasin auquel vous souhaitez apporter des modifications.
2. Dans l’onglet **Fonctions**, configurez les paramètres suivants selon les besoins.

    - **Facture de commande client** : Sélectionnez **Oui** pour autoriser les utilisateurs à régler une ou plusieurs factures basées sur une commande client dans une transaction de point de vente unique.
    - **Facture financière** : Sélectionnez **Oui** pour autoriser les utilisateurs à régler une ou plusieurs factures financières dans une transaction de point de vente unique.
    - **Facture de projet** : Sélectionnez **Oui** pour autoriser les utilisateurs à régler une ou plusieurs factures de projet dans une transaction de point de vente unique.
    - **Commande client - Avoir** : Sélectionnez **Oui** pour autoriser les utilisateurs à régler plusieurs avoirs basés sur des commandes dans le cadre des factures en cours ou pour rembourser un avoir en cours à un client.

> [!NOTE]
> Le paiement ou le règlement des montants partiels n’est pas encore pris en charge.


[!INCLUDE[footer-include](../includes/footer-banner.md)]