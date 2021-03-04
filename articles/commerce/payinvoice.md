---
title: Paramétrer des scénarios de règlement de facture
description: Cette rubrique décrit la procédure de configuration de Dynamics 365 Commerce pour prendre en charge différents scénarios relatifs aux règlements de facture.
author: josaw1
manager: AnnBe
ms.date: 11/14/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: 8b65fe3968698da1c5b76cf2d0ef706f3f1ec4bb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972655"
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