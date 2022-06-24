---
title: Enregistrement automatique des paiements pour les factures client intersociétés
description: Cet article explique comment enregistrer automatiquement des paiements pour les factures client intersociétés
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 4e8f784cd310026f0a647a0f509999e11ab26ce5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878785"
---
# <a name="register-payments-automatically-for-intercompany-customer-invoices"></a>Enregistrement automatique des paiements pour les factures client intersociétés

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management crée une transaction client lorsqu'une facture client intersociétés est validée. Cette transaction client reste en cours jusqu'à ce qu'elle soit réglée (payée). Lorsque la commande fournisseur intersociétés correspondante est mise à jour par une facture, une transaction fournisseur correspondant à la transaction client est créée. Cette transaction fournisseur reste en cours jusqu'à ce qu'elle soit réglée. Pour réduire les risques de différences de montant, un journal des paiements des ventes peut être créé et validé automatiquement lors de la validation du journal des paiements des achats.

1. Allez dans **Ventes et marketing \> Clients \> Tous les clients**.
1. Dans le volet Actions, sous l’onglet **Général**, sélectionnez **Intersociétés**.
1. Pour configurer les paiements des comptes clients intersociétés sur la page des commandes clients **Intersociétés**, sélectionnez le lien **Stratégies pour les commandes client**.
1. Dans le champ **Journal des paiements**, sélectionnez le journal des paiements des ventes dans lequel enregistrer les paiements fournisseur intersociétés. Effectuez la configuration sur la page **Paramètres des ventes**.
1. Si vous souhaitez publier automatiquement dans ce journal, cochez la case **Publier le journal automatiquement**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
