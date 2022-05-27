---
title: Synchroniser les codes de disposition
description: Cette rubrique explique la synchronisation des codes de disposition pour le commerce intersociétés
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
ms.openlocfilehash: 27b587e576900f2b7f7fed7ee2a27a282306f0fe
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671756"
---
# <a name="synchronize-intercompany-disposition-codes"></a>Synchroniser les codes de disposition intersociétés

[!include [banner](../../includes/banner.md)]

Pour prendre en charge les retours intersociétés, Microsoft Dynamics 365 Supply Chain Management vous permet de mapper des codes disposition définis en externe aux codes disposition internes correspondants. Lorsqu'une chaîne intersociétés est en cours de paramétrage, les actions de disposition des deux sociétés mappées l'une à l'autre doivent être identiques. Si elles diffèrent, le processus de synchronisation échoue.

## <a name="about-disposition-codes-for-three-legged-direct-returns"></a>À propos des codes disposition pour les retours directs à trois branches

Les codes disposition sont synchronisés de la ligne de commande client intersociétés à la ligne de commande client d'origine. Toutefois, la synchronisation n'a d'effet immédiat que sur la ligne de commande client d'origine. Cet effet est que les frais divers de la ligne sont supprimés sur la base du code disposition et des frais divers paramétrés dans la Société A, à savoir celle créant l'ordre de retour.

Dans une chaîne de livraison directe à trois branches, toutes les actions de disposition sont prises en charge sur la ligne de commande client intersociétés. Toutefois, si un produit est retourné au client, il est important de confirmer que l'adresse de livraison de l'ordre de retour correspond à l'adresse de livraison du client spécifiée dans la commande d'origine.

> [!NOTE]
> Il n'existe pas de codes disposition pour les commandes fournisseur. Par conséquent, la synchronisation des codes disposition de la commande client intersociétés à l'ordre de retour d'origine doit être exécutée entre des commandes client.

## <a name="replacing-returned-items"></a>Remplacement des articles retournés

Lorsqu'un article retourné est remplacé et qu'un ordre de remplacement a déjà été créé dans la Société B, il est impossible de sélectionner un code disposition et aucun ordre de remplacement supplémentaire n'est créé dans la Société A.

## <a name="rules-for-intercompany-direct-deliveries"></a>Règles pour les livraisons directes intersociétés

Les règles générales suivantes s'appliquent aux ordres de retour d'origine dans des scénarios impliquant des livraisons directes intersociétés :

- Si l'action de disposition sous-jacente de la ligne de commande client d'origine est Créditer et mettre au rebut, Créditer ou Retourner au client, l'action de disposition qui s'applique est Créditer. Toutefois, le code action Retourner au client définit le montant net sur 0 (zéro) sur la ligne existante et sur la ligne nouvellement synchronisée de la commande client intersociétés. En outre, les lignes de rebut ne sont jamais synchronisées. Quand une ligne est ajoutée à une commande client intersociétés, elle n'est jamais synchronisée pour une commande client dont la quantité est positive et dont l' action de disposition est Mettre au rebut (par exemple, Créditer et mettre au rebut ou Remplacer et mettre au rebut).
- Une action de disposition sous-jacente dont le statut est Remplacer et créditer ou Remplacer et mettre au rebut n'est pas remplacée. Elle est traitée comme une action de disposition dont le statut est Remplacer et créditer ou Remplacer et mettre au rebu. Cette règle s'applique même si aucune ligne de rebut n'est créée dans la Société A et aucun ordre de remplacement dans la Société B (la société qui a reçu le retour marchandise). Un ordre de remplacement n'est créé dans la Société A que si une mise à jour du bon de livraison a lieu.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
