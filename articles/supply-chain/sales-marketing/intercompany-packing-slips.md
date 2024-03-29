---
title: Bons de livraison intersociétés
description: Cet article explique comment générer et imprimer des bons de livraison pour les transactions intersociétés
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
ms.openlocfilehash: 3516058bbf925df4b0a0c75286a3d97457cc1e69
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900852"
---
# <a name="intercompany-packing-slips"></a>Bons de livraison intersociétés

## <a name="generate-intercompany-packing-slips"></a>Générer les bons de livraison intersociétés

[!include [banner](../../includes/banner.md)]

Si vous utilisez une livraison directe, le bon de livraison est toujours généré automatiquement sur la commande fournisseur intersociétés et la commande client d'origine lorsque vous le générez sur la commande client intersociétés. La facture de la commande fournisseur intersociétés est basée sur le bon de livraison de la commande fournisseur intersociétés précédemment généré.

Si vous effectuez des mises à jour du bon de livraison sur la commande client intersociétés, celles-ci sont répercutées sur la commande fournisseur intersociétés et la commande client d'origine.

Si vous n'utilisez pas de livraison directe, vous devez générer manuellement le bon de livraison sur la commande client intersociétés, sur la commande fournisseur intersociétés et sur la commande client d'origine.

## <a name="print-intercompany-packing-slips"></a>Imprimer les bons de livraison intersociétés

[!include [banner](../../includes/banner.md)]

Si vous utilisez la livraison directe, un bon de livraison peut être imprimé automatiquement pour la commande fournisseur intersociétés et la commande client originale lorsque vous validez le bon de commande sur la commande client intersociétés.

Pour imprimer automatiquement les bons de livraison, sur la page **Intersociétés** pour les bons de commande, sélectionnez les deux champs **Imprimer le bordereau d'expédition automatiquement**.

Si vous mettez à jour le bon de livraison figurant dans la commande client intersociétés, les modifications apportées sont répercutées automatiquement dans la commande fournisseur intersociétés et la commande client originale.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
