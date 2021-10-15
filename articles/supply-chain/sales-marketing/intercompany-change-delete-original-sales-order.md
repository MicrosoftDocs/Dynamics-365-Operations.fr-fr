---
title: Modifier ou supprimer une commande client intersociétés d’origine
description: Cette rubrique explique la modification et la suppression d'une fonctionnalité de commande client d'origine
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
ms.openlocfilehash: 7bd6bdbf65499e9f18bf6bb5e160a5634bc37fba
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548260"
---
# <a name="change-or-delete-an-original-intercompany-sales-order"></a>Modifier ou supprimer une commande client intersociétés d’origine

[!include [banner](../../includes/banner.md)]

Lorsque vous modifiez une commande client, vos modifications sont automatiquement synchronisées avec la commande fournisseur intersociétés et la commande client intersociétés concernées.

> [!NOTE]
> Les commandes fournisseur relatives à des fournisseurs externes ne sont pas affectées par les modifications que vous apportez. Les lignes de vente originales liées aux lignes de commande fournisseur relatives à des fournisseurs externes ne le sont pas davantage.

Le tableau suivant résume les modifications que vous pouvez apporter et les résultats attendus.

| Opération | Résultat |
|---|---|
| Supprimer&nbsp;une&nbsp;commande&nbsp;client&nbsp;d'origine. | La commande fournisseur intersociétés et la commande client intersociétés associées sont également supprimées. Si le statut de la commande est **Prélèvements** ou plus avancé dans le processus, vous ne pouvez pas supprimer la ligne de commande client. |
| Supprimer une ligne de commande client originale | La ligne de commande fournisseur intersociétés et la ligne de commande client intersociétés associées sont supprimées. Si le statut de la commande est **Prélèvements** ou plus avancé dans le processus, vous ne pouvez pas supprimer la ligne de commande client. |
| Ajouter une nouvelle ligne de vente à une commande client originale | La nouvelle ligne de vente est créée sur la commande fournisseur intersociétés et la commande client intersociétés. |
| Modifier la quantité d'une ligne de commande client originale | La quantité est synchronisée avec la ligne de commande fournisseur intersociétés et la ligne de commande client intersociétés. Le montant net est recalculé pour toutes les commandes. |
| Désactiver la livraison directe pour une commande client originale | Vous ne pouvez pas changer le champ **Livraison directe** sur la commande client d'origine si la ligne de commande client intersociétés a atteint un statut minimum de **Prélèvement**, **Ordre de sortie** ou **Journal des prélèvements**. L'adresse de livraison sur la commande fournisseur intersociétés est remplacée par l'adresse de livraison standard (adresse de livraison standard de la commande fournisseur). Par ailleurs, les lignes de la commande fournisseur intersociétés sont remplacées par l'adresse de livraison standard pour les lignes. Les deux sont synchronisées avec la commande client intersociétés et les lignes. Le type de livraison de toutes les lignes de la commande client originale est modifié en **Aucun** et le champ est synchronisé avec les lignes de commande fournisseur intersociétés. Les commandes fournisseur relatives aux fournisseurs externes ne sont pas affectées. Les lignes de vente originales associées aux lignes de commande fournisseur relatives aux fournisseurs externes ne le sont pas davantage. La date de livraison de la commande fournisseur intersociétés et les lignes, ainsi que les dates de réception et d'expédition demandées de la commande client intersociétés et les lignes, sont mises à jour. |
| Activer la livraison directe pour une commande client originale | Si la ligne de commande client intersociétés a atteint un statut minimum de **Prélèvement**, **Ordre de sortie** ou **Journal des prélèvements**, vous ne pouvez pas changer le champ **Livraison directe** dans la commande client d'origine. L'adresse de livraison sur la commande fournisseur intersociétés est remplacée par l'adresse de livraison de la commande client originale et synchronisée avec la commande client intersociétés. Le type de livraison de toutes les lignes de la commande client originale est modifié en **Livraison directe** et le champ est synchronisé avec les lignes de commande fournisseur intersociétés. L'adresse de livraison de chaque ligne de commande client originale est synchronisée avec les lignes de commande fournisseur intersociétés et les lignes de commande client intersociétés. La date de livraison de la commande fournisseur intersociétés et les lignes, ainsi que les dates de réception et d'expédition demandées de la commande client intersociétés et les lignes, sont mises à jour. |
| Ajouter une note à un en-tête et aux lignes de commande client originale | La note est copiée dans la commande fournisseur intersociétés et la commande client intersociétés. |
| Modifier ou supprimer une note | Si vous modifiez ou supprimez une note, la note correspondante sur la commande fournisseur intersociétés et la commande client intersociétés est modifiée ou supprimée en conséquence. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
