---
title: Écarts de données de ligne de commande d’achat
description: Vous voyez des écarts de données ou des données corrompues sur vos lignes de bon de commande.
author: SmithaNataraj
ms.date: 12/07/2021
ms.topic: troubleshooting
ms.search.form: PurchLineManualCorrection, PurchTable, PurchLine, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-12-07
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: ee2cb9a07c8a00a92c71e3e99d8ec20aa27fb20e
ms.sourcegitcommit: b9799a58d6ec221df86788bc37c4fbd28b435e89
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2022
ms.locfileid: "8100801"
---
# <a name="purchase-order-line-data-discrepancies"></a>Écarts de données de ligne de commande d’achat

## <a name="symptoms"></a>Symptômes

Lorsque vous inspectez les lignes d’un bon de commande, vous remarquez un ou plusieurs des problèmes suivants :

- Il y a une incohérence ou une corruption de données dans les restes de ligne de commande d’achat (livraison ou facture).
- Il y a une corruption dans une ligne de bon de commande ou un statut d’en-tête.
- Vous ne pouvez pas facturer un bon de commande car, par exemple, vous recevez un ou plusieurs des messages d’erreur suivants :

    - "Arrêt (erreur) : la transaction a déjà été enregistrée. »
    - "Impossible de facturer la quantité car des mouvements de stock avec l’état Reçu ne sont pas suffisants."
    - "Transactions de stock insuffisantes avec le statut "Acheté" pour l’article %0 en quantité %1."

- Vous ne pouvez pas finaliser ou clôturer un bon de commande en raison, par exemple, de l’un des problèmes suivants :

    - Le bouton **Finaliser** n’est pas disponible.
    - Vous ne pouvez pas annuler la quantité commandée d’une ligne de commande fournisseur pour une commande fournisseur dont l’état est confirmé et reçu.

## <a name="cause"></a>Cause

Ces problèmes sont généralement dus à une corruption des données ou à un écart dans les quantités restantes pour une ou plusieurs lignes de bon de commande.

## <a name="resolution"></a>Résolution

Vous pouvez généralement résoudre ces problèmes en mettant à jour le statut d’achat, les reliquats de livraison et/ou les reliquats de facture pour les lignes de commande fournisseur concernées, comme décrit dans la procédure suivante.

1. Accédez à **Approvisionnements \> Tâches périodiques \> Nettoyer \> Corriger manuellement les lignes de bon de commande**.
1. Dans le champ **Bon de commande**, recherchez et sélectionnez le bon de commande qui vous pose problème.
1. Dans la section **Lignes de bon de commande**, sélectionnez une ligne où vous avez trouvé une divergence.
1. Dans la section **Mouvements d’inventaire**, inspectez les données affichées. Si vous remarquez des incohérences entre une ligne de commande fournisseur et ses transactions de stock, sélectionnez l’une des commandes suivantes dans le volet Actions, selon l’endroit où vous voyez les incohérences :

    - **Recalculer \> Recalculer le reste de livraison** – Mettre à jour automatiquement les statuts de la ligne et de l’en-tête du bon de commande. Cette fonction ne fonctionne que pour les lignes de bon de commande stockées (c’est-à-dire les lignes où l’article est un article stocké). Les articles non stockés et les articles à poids variable ne sont actuellement pas pris en charge.
    - **Recalculer \> Recalculer le reste de la facture** – Mettre à jour automatiquement les statuts de la ligne et de l’en-tête du bon de commande. Cette fonction ne fonctionne que pour les lignes de bon de commande stockées (c’est-à-dire les lignes où l’article est un article stocké). Les articles non stockés et les articles à poids variable ne sont actuellement pas pris en charge.
    - **Recalculer \> Recalculer le statut** – Recalculer l’état de la ligne sélectionnée. Ce calcul est basé sur la logique existante. Par conséquent, le statut de l’en-tête du bon de commande sera mis à jour selon les besoins, en fonction du nouveau statut de la ligne de bon de commande.

1. Si vous constatez encore des incohérences dans les quantités restantes, vous pouvez utiliser les champs suivants pour les modifier directement si nécessaire :

    - Livrer quantité restante
    - Quantité restante en stock
    - Solde de la facture
    - Quantité à facturer restante pour le stock
