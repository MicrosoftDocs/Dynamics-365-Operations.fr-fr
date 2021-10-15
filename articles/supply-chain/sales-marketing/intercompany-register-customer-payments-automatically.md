---
title: Enregistrement automatique des paiements pour les factures client intersociétés
description: Cette rubrique explique comment enregistrer automatiquement des paiements pour les factures client intersociétés
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: ffc5c7bf44989fbcc18e940b5a7c9df81260d770
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548269"
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
