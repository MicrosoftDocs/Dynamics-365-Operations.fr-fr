---
title: Modifier les commandes intersociétés
description: Cette rubrique explique la modification de la fonctionnalité des commandes intersociétés
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
ms.openlocfilehash: 10efc397c64833785f286983987fd05854a69c0f
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672904"
---
# <a name="change-intercompany-orders"></a>Modifier les commandes intersociétés

[!include [banner](../../includes/banner.md)]

Si vous modifiez une commande client intersociétés ou une commande fournisseur intersociétés, cette modification est répercutée sur la commande client ou la commande fournisseur correspondante dans la société adéquate.

## <a name="adding-new-lines"></a>Ajout de lignes

Vous pouvez ajouter de nouvelles lignes à une commande client intersociétés et à une commande fournisseur intersociétés si la commande client d'origine fait partie de la chaîne de commandes intersociétés. Vous pouvez également ajouter des lignes si la commande client d'origine n'est pas une livraison directe. Si la commande client d'origine est une livraison directe, vous pouvez ajouter de nouvelles lignes de commande à la commande client intersociétés et à la commande fournisseur intersociétés uniquement si le champ **Autoriser la création indirecte** est sélectionné dans l'organisateur **Paramètres intersociétés** de la commande client d'origine.

## <a name="changing-prices-and-discounts"></a>Modification des prix et des remises

Vous pouvez modifier les prix et les remises si les cases **Autoriser la modification du prix** et **Autoriser la modification de la remise** sont cochées sur la page **Intersociétés**.

Si vous modifiez le prix unitaire de l'une des lignes existantes dans la commande client intersociétés, le prix unitaire dans la commande fournisseur intersociétés est également modifié.

Si vous modifiez l'un des champs de remise de la ligne de commande client intersociétés, les champs de remise appropriés de la commande fournisseur intersociétés sont mis à jour.

## <a name="changing-and-adding-new-charges"></a>Modification et ajout de frais

Vous pouvez modifier les frais si les cases **Autoriser la modification du prix** et **Autoriser la modification de la remise** sont cochées sur la page **Intersociétés**.

Si vous ajoutez des frais à l'en-tête de la commande client intersociétés ainsi qu'à la ligne de commande client intersociétés, les deux frais sont copiés dans la commande fournisseur intersociétés. Par conséquent, la commande client intersociétés et la commande fournisseur intersociétés possèdent le même montant total. Les frais ne sont jamais copiés vers la commande client d'origine.

## <a name="copying-a-fee"></a>Copie de frais

Pour copier des frais vers la commande client d'origine, créez-les en tant que ligne de commande client avec un article du type **Service**.

## <a name="changing-quantities-and-deleting-intercompany-purchases-and-sales-order-lines"></a>Modification des quantités et suppression des lignes de commande client ou fournisseur intersociétés

Vous ne pouvez modifier ou supprimer la quantité d'une ligne de commande client ou fournisseur intersociétés que si la ligne a été créée directement dans l'écran **Commande client** ou **Commande fournisseur**. Cette modification fait de la commande ou des lignes de commande client ou fournisseur intersociétés la source.

## <a name="origins-of-orders-and-order-lines"></a>Origines des commandes et des lignes de commande

Les commandes et lignes de commande intersociétés peuvent avoir une des deux origines suivantes :

- **Dérivé** – La commande a été créée automatiquement d'après une chaîne de commandes intersociétés.
- **Source** – Un utilisateur a créé la commande manuellement.

L'origine est indiquée dans l'en-tête de commande des commandes fournisseur ou client intersociétés, dans le champ **Origine**. Ce champ est situé dans l'organisateur **Paramètres intersociétés** de la commande client et dans l'organisateur **Configuration** de la commande fournisseur.

Les origines **Dérivé** et **Source** s'appliquent uniquement aux commandes intersociétés. Le champ **Origine** est vide pour toutes les autres commandes client, commandes fournisseur et lignes de commande. Ce champ est également vide sur la commande client d'origine.

## <a name="example-derived-origin"></a>Exemple : origine Dérivé

Vous pouvez créer une commande client d'origine pour un client externe. Cette commande contient une ligne de commande. Elle crée une commande fournisseur intersociétés contenant une ligne de commande, qui crée une commande client intersociétés contenant une ligne de commande. L'en-tête de la commande fournisseur intersociétés et la ligne de commande sont créés automatiquement à partir de la commande client d'origine.

La valeur du champ **Origine** de l'organisateur **Configuration** de la commande fournisseur intersociétés et celle de l'organisateur **Paramètres intersociétés** des en-têtes de la commande client intersociétés est **Dérivé**. La valeur du champ **Origine** sous l'onglet **Détails de la ligne** de la commande fournisseur et des lignes de commande client est également **Dérivé**.

Si une ligne de commande a une origine **Dérivé**, vous ne pouvez pas supprimer la ligne de commande directement. Vous ne pouvez supprimer la ligne de commande qu'à partir de la source qui a permis de créer la ligne de commande. De même, vous ne pouvez modifier la quantité de la commande que dans la source à partir de laquelle la ligne de commande a été créée.

Si une commande client d'origine et une ligne de commande client d'origine fait partie de la chaîne de commandes intersociétés, vous pouvez modifier les quantités de la commande et supprimer des lignes de commande dans la commande client d'origine.

## <a name="example-source-origin"></a>Exemple : origine Source

Vous pouvez créer une commande fournisseur pour un fournisseur intersociétés. La commande fournisseur intersociétés et la ligne de commande ont toutes les deux une origine **Source**. Par conséquent, cette commande fournisseur intersociétés est le contrôleur et la commande client intersociétés créée automatiquement dans la société du fournisseur a une origine **Dérivé**.

En outre, vous ne pouvez pas modifier les quantités d'une ligne de commande créée dans la commande fournisseur intersociétés sur la commande client intersociétés. La ligne de commande peut uniquement être supprimée à partir de la commande fournisseur intersociétés. En cas d'ajout d'une ligne à la commande client intersociétés, cette ligne a une origine **Source**.

Lorsqu'une commande client d'origine fait partie de la chaîne de commandes intersociétés, vous pouvez toujours contrôler les commandes intersociétés et les lignes de commande intersociétés de la commande client d'origine.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
