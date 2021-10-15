---
title: Numéros de lot et de série intersociétés
description: Cette rubrique explique ce qui se passe lorsque vous enregistrez des numéros de lot et des numéros de série pour les commandes intersociétés
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
ms.openlocfilehash: 4da936263bb57c24eeb7021ac61b3945bb2777fb
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548274"
---
# <a name="intercompany-batch-and-serial-numbers"></a>Numéros de lot et de série intersociétés

[!include [banner](../../includes/banner.md)]

Les sociétés qui utilisent des numéros de série ou de lot pour suivre leurs articles doivent également suivre les numéros de série et de lot des articles prélevés. La fonctionnalité intersociétés automatise le déplacement/l'extraction des numéros de série et de lot d'une société à une autre. Lorsque vous enregistrez les numéros de lot et de série d'articles sur une commande client intersociétés, vous pouvez paramétrer le programme pour qu'il transmette automatiquement ces numéros à la commande fournisseur intersociétés et à la commande client originale. Vous devez définir les paramètres correspondants sur la page **Intersociétés** pour la commande client :

- Si vous sélectionnez le champ **Numéro du lot** de la page **Stratégies pour les commandes client**, le numéro du lot est synchronisé avec les mouvements de stock sur les lignes de la commande fournisseur intersociétés lors de la validation du bon de livraison de la commande client intersociétés.
- Si vous sélectionnez le champ **Numéro de série**, les numéros de série sont synchronisés avec les mouvements de stock sur les lignes de la commande fournisseur intersociétés lors de la validation du bon de livraison de la commande client intersociétés.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
