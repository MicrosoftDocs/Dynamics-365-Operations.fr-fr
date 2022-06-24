---
title: Commandes et ordres de retour intersociétés
description: Cet article décrit les commandes et ordres de retour intersociétés
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
ms.openlocfilehash: 65d0dc6049969ff7d8f84ca4eb3baf486ddad660
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859025"
---
# <a name="intercompany-orders-and-return-orders"></a>Commandes et ordres de retour intersociétés

[!include [banner](../../includes/banner.md)]

Cet article décrit la manière dont les commandes fournisseur intersociétés, les commandes client, les ordres de retour, les contrats d'achat et les contrats de vente sont créés et mis à jour.

## <a name="about-intercompany-orders"></a>À propos des commandes intersociétés

Lorsque vous créez une commande client intersociétés, Microsoft Dynamics 365 Supply Chain Management crée une commande fournisseur correspondante automatiquement. De même, la création d'une commande fournisseur intersociétés entraîne la création automatique d'une commande client intersociétés correspondante.

Ceci s'applique aux commandes à deux branches (transactions entre deux sociétés liées) et à la plupart des sociétés à trois branches (lorsqu'une transaction intersociétés est associée à une commande client pour un client externe).

## <a name="intercompany-order-example"></a>Exemple de commande intersociétés

Vous avez deux sociétés liées. La société A est une filiale commerciale et la société B une unité de distribution. Les commandes client intersociétés et commandes fournisseur sont créées automatiquement dans les scénarios suivants :

- Lorsque la société A crée une commande fournisseur et que le fournisseur est la société B, une commande client intersociétés est créée automatiquement dans la société B. La chaîne de commande à deux branches comporte une commande fournisseur dans la société A et une commande client intersociétés dans la société B.
- Lorsque la société B crée une commande client et que le client est la société A, une commande fournisseur intersociétés est créée automatiquement dans la société A. La chaîne de commande à deux branches comporte une commande fournisseur dans la société B et une commande fournisseur intersociétés dans la société A.
- Lorsque la société A crée pour la première fois une commande client pour un client externe, une commande fournisseur peut être créée automatiquement dans la société A, ce qui entraîne la création automatique d'une commande client intersociétés dans la société B. La chaîne de commande à trois branches comporte une commande client et une commande fournisseur dans la société A, et une commande client intersociétés dans la société B.

## <a name="about-intercompany-return-orders"></a>À propos des ordres de retour intersociétés

Vous pouvez retourner des articles intersociétés comme des articles ordinaires. Toutefois, avec les articles intersociétés, l'ordre de retour d'un client externe crée une commande fournisseur intersociétés. Ceci entraîne la création automatique d'un ordre de retour de vente intersociétés. Vous pouvez également retourner un article intersociétés sans ordre de retour de client externe.

Les ordres de retour intersociétés, comme les ordres de retour ordinaires, sont créés sur la page **Créer des lignes d’ordre de retour**.

Dans Microsoft Dynamics 365 Supply Chain Management, les ventes intersociétés et les contrats d'achat sont automatiquement mis à jour pour refléter un article retourné. Les ventes ou l'engagement de contrat d'achat pour cet article est automatiquement ajusté pour refléter les modifications de la quantité ou du montant lorsqu'un article est retourné.

## <a name="intercompany-return-order-example"></a>Exemple d'ordre de retour intersociétés

La société A crée une commande fournisseur qui est liée à un contrat d'achat pour un article intersociétés. Une commande client intersociétés est créée automatiquement dans la société B liée au contrat de vente correspondant. Le contrat d'achat et le contrat de vente sont liés comme accords intersociétés.

La société A renvoie l'article intersociétés à la société B. La société B crée un ordre de retour pour l'article, et une commande fournisseur de retour est créé automatiquement dans la société A. Les engagements figurant dans le contrat d'achat et le contrat de vente liés aux commandes d'origine sont automatiquement ajustés pour refléter les modifications de la quantité ou du montant.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
