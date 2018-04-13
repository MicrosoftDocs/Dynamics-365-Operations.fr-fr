---
title: "Répartitions comptables"
description: "Cet article fournit des informations sur les répartitions comptables et décrit les options disponibles pour les traiter. Les répartitions comptables sont utilisées pour répartir les montants en devises d'un document source dans des comptes généraux spécifiques."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AccountingDistribution
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 17231
ms.assetid: 9030355d-8e6e-408b-9e7d-7b346eaa652c
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: bbf23d9cab01e8cdbae776c9310fbd19b429443d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="accounting-distributions"></a>Répartitions comptables

[!INCLUDE [banner](../includes/banner.md)]

Cet article fournit des informations sur les répartitions comptables et décrit les options disponibles pour les traiter. Les répartitions comptables sont utilisées pour répartir les montants en devises d'un document source dans des comptes généraux spécifiques. 

Les répartitions comptables sont une capacité à l'échelle du programme utilisée et étendue par chaque document source, tel qu'une commande fournisseur, une facture fournisseur, un état de dépenses et une facture financière. Par défaut, une répartition comptable par défaut est générée pour chaque ligne de document source et de montant en devises, et est conditionnellement activée pour la modification. 

> [!Note] 
> Certains documents prennent également en charge les montants en devises des documents d'en-tête, comme les frais de commande et de facture. 

Les fonctionnalités de répartition comptable générique fournissent les options suivantes pour traiter les répartitions comptables :

-   **Répartir les montants** – permet d'afficher et de modifier les répartitions comptables pour un en-tête de document ou une ligne individuelle et toutes les lignes enfants, telles que les taxes ou des frais.
    -   Pour les répartitions de montant en devises supérieures (les distributions parentes), le compte principal et les dimensions financières peuvent être modifiables directement dans le contrôle d'entrée segmentée dans la grille. Le prix global est un exemple classique d'une répartition parent.
    -   Les montants des distributions sont fondés sur la devise pour le document. En général, la devise est la devise utilisée pour la transaction. Les montant en devise de comptabilité et en devise de déclaration sont générés dans le cadre de la comptabilité auxiliaire.
    -   Les distributions permettent d'afficher la date comptable et l'événement comptable. Généralement, l'événement comptable est défini sur **Aucun(e)** tant que le document n'est pas validé/journalisé. À ce stade, l'événement comptable devient **Initial**. Une fois les répartitions validées, vous ne pouvez plus les modifier.
    -   Le bouton **Fractionnement** peut être activé pour les distributions parent. Le bouton **Fractionnement** génère de nouvelles répartitions comptables, et le fractionnement peut être basé sur un pourcentage, un montant ou une quantité.
    -   Le bouton **Répartir en valeurs égales** peut être utilisé en association avec **Fractionnement** pour répartir automatiquement le montant également entre toutes les distributions.
    -   Le bouton **Réinitialiser** peut être activé pour les distributions parent lorsque plusieurs distributions existent. **Rétablir** contrepasse toute modification manuelle à la distribution supprimant toutes les répartitions existantes ou en régénérant les distributions par défaut.
    -   Une répartition enfant, telle qu'une remise, les frais ou la taxe, suit toujours la distribution parent. Vous pouvez afficher la relation parent/enfant dans **Référence** &gt; **Informations parent**.
    -   Le compte principal et la dimension financière peuvent être modifiables pour les enfants aussi.
    -   Les dimensions financières sur les répartitions comptables suivent un motif par défaut qui peut être étendu par un document. Pour plus d'informations, consultez les articles connexes.
    -   Les répartitions des écarts peuvent être générées dans des scénarios de correspondance, tels qu'une correspondance entre une facture fournisseur et une commande fournisseur. Vous pouvez afficher les relations de correspondance entre répartitions comptables dans **Référence** &gt; **Informations du document**.
    -   Le bouton **Corriger** s'affiche et est activé pour les documents qui prennent en charge les corrections. **Corriger** crée les nouvelles répartitions. En premier sont créées les répartitions qui contrepassent les répartitions d'origine. Ces répartitions ne peuvent pas être modifiées. Ensuite, les répartitions comptables correctes sont créées. Ces répartitions peuvent être modifiées si les distributions d'origine pouvaient être modifiées.
    -   Le bouton **Détails du projet** est activé comme extension lorsqu'une ligne est liée à un projet. Les répartitions comptables de projet permettent de modifier les détails tels que la source du financement et la propriété de ligne.
    -   Vous pouvez afficher le statut comptable du document actuel dans **Référence**. Le statut concerne le document entier, et indique si le document est en cours de traitement ou terminé.
-   **Afficher les distributions** – Permet d'afficher les répartitions comptables pour toutes les lignes et les montants en devises du document. Vous ne pouvez pas modifier les répartitions comptables de cette vue.


Pour plus d'informations, voir [Répartitions comptables et écritures de journal de comptabilité auxiliaire pour les factures financières](accounting-distributions-subledger-journal-entries-vendor-invoices.md).



