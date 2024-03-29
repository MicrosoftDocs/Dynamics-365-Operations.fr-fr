---
title: Synchroniser les frais intersociétés
description: Cet article explique la synchronisation des frais intersociétés
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
ms.openlocfilehash: e7b3de3d7da7be6c1c8b5c3842862e7bccd78277
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857284"
---
# <a name="synchronize-intercompany-charges"></a>Synchroniser les frais intersociétés

[!include [banner](../../includes/banner.md)]

Les frais ne sont synchronisés qu'entre la commande client intersociétés et la commande fournisseur intersociétés, et la synchronisation a toujours lieu.

Si le champ **Autoriser la modification du prix** est sélectionné sur la commande fournisseur intersociétés ou la commande client intersociétés, vous pouvez ajouter manuellement des frais à la commande client intersociétés ou à la commande fournisseur intersociétés. Si ces champs sont désactivés, cette opération est impossible.

Si le champ **Autoriser la modification du prix** n'est pas sélectionné sur la commande client intersociétés, vous ne pouvez pas ajouter de frais divers manuellement à une commande client intersociétés.

Si le champ **Autoriser la modification du prix** n'est pas sélectionné sur la commande fournisseur intersociétés, vous ne pouvez pas ajouter de frais sur la commande fournisseur intersociétés.

Si le champ **Autoriser la modification du prix** est activé sur la commande fournisseur intersociétés et la commande client intersociétés, vous pouvez ajouter manuellement des frais à ces deux commandes. Toutefois, cette opération peut entraîner l'ajout de manière erronée de nombreux frais.

Pour éviter ces types de conflits, la meilleure solution consiste à autoriser l'ajout de frais soit à la commande client intersociétés, soit à la commande fournisseur intersociétés, mais pas aux deux.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
