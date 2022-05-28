---
title: Synchroniser les prix et les remises intersociétés
description: Cette rubrique explique la synchronisation des prix et des remises pour les commandes client et les commandes fournisseur intersociétés
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
ms.openlocfilehash: 90fa2244b5947c37b8498d1c70cddf894979f931
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673632"
---
# <a name="synchronize-intercompany-prices-and-discounts"></a>Synchroniser les prix et les remises intersociétés

[!include [banner](../../includes/banner.md)]

Les remises et les prix sont toujours synchronisés entre la commande client intersociétés et la commande fournisseur intersociétés. Vous pouvez également synchroniser les prix et les remises avec / à partir de la commande client originale afin que toutes les commandes aient les mêmes prix et remises. Vous faites cela à partir de la page **Intersociétés** accessible depuis l'onglet **Général** sur la page de liste **Tous les clients** - à partir de **Ventes et marketing** ou de **Approvisionnements**.

Le champ **Prix et remise** est synchronisé avec la ligne de commande client intersociétés. Cela signifie qu'en sélectionnant les champs **Autoriser la modification du prix** et **Autoriser la modification de la remise**, vous avez autorisé une modification entre la commande client intersociétés et la commande fournisseur intersociétés. Une modification du prix unitaire, de l'unité de prix ou des frais de vente sur la commande client intersociétés détermine le prix sur la ligne de commande fournisseur intersociétés.

Si les champs **Autoriser la modification du prix** et **Autoriser la modification de la remise** sont activés sur la commande client intersociétés ou la commande fournisseur intersociétés, vous pouvez modifier manuellement le prix ou la remise figurant sur celle-ci. Si ces champs sont désactivés, cette opération est impossible.

Si les champs **Autoriser la modification du prix** et **Autoriser la modification de la remise** ne sont pas activés sur la commande client intersociétés, vous ne pourrez pas modifier manuellement le prix (ou les frais) ou la remise figurant sur la commande client intersociétés.

Si les champs **Autoriser la modification du prix** et **Autoriser la modification de la remise** ne sont pas activés sur la commande fournisseur intersociétés, vous ne pourrez pas modifier manuellement le prix (ou les frais) ou la remise figurant sur la commande fournisseur intersociétés.

Si les champs **Autoriser la modification du prix** et **Autoriser la modification de la remise** sont activés à la fois sur la commande fournisseur intersociétés et la commande client intersociétés, vous pouvez apporter des modifications manuelles aux deux commandes. Toutefois, il se peut que les mises à jour effectuées par une personne soient remplacées par celles effectuées par une autre personne d'une autre société sur la même commande.

> [!NOTE]
> Si vous avez activé le champ **Prix et remise** sur la commande fournisseur intersociétés et sur la commande client intersociétés, vous ne pouvez pas contrôler la tarification.

Pour éviter ces types de conflits, la meilleure solution consiste à autoriser la modification des prix et des remises uniquement sur la commande client intersociétés ou sur la commande fournisseur intersociétés. Ceci est accompli en permettant les champs **Autoriser la modification du prix** et **Autoriser la modification de la remise** sur l'une ou l'autre de ces commandes.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
