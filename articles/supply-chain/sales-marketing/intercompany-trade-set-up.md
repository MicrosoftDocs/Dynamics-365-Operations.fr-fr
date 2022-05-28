---
title: Paramétrage du commerce intersociétés
description: Cette rubrique explique comment paramétrer le commerce intersociétés
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage, InterCompanyTradingRelationSetupCustomer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 5080267568f4d0626d2c727efb533295e7d8e397
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669388"
---
# <a name="set-up-intercompany-trade"></a>Paramétrage du commerce intersociétés

[!include [banner](../../includes/banner.md)]

Pour permettre à Microsoft Dynamics 365 Supply Chain Management d’exécuter le commerce intersociétés, vous devez paramétrer des clients et des fournisseurs. Vous devez également paramétrer les modules Achats, Ventes, Approvisionnements et Ventes et marketing.

## <a name="before-you-set-up-intercompany-trade"></a>Avant le paramétrage du commerce intersociétés

Avant de paramétrer le commerce intersociétés, vous devez définir vos clients et vos fournisseurs intersociétés. Pour chaque entité juridique dans Microsoft Dynamics 365 Supply Chain Management, vous devez décider de la stratégie commerciale à appliquer à la relation commerciale intersociétés avec le client ou le fournisseur intersociétés concerné.

En particulier, il est recommandé que vous et votre organisation vous familiarisiez avec les paramètres intersociétés.

- Examinez les implications du paramétrage avec les responsables commerce intersociétés dans chaque entité juridique.
- Paramétrez les valeurs appropriées pour chaque entité juridique.

## <a name="set-up-trading-relations"></a>Paramétrage des relations commerciales

Pour paramétrer le commerce intersociétés pour des clients et des fournisseurs, procédez comme suit :

1. Allez dans **Comptabilité client \> Clients \> Tous les clients**.
1. Permet de sélectionner un compte client.
1. Dans le volet Actions, sous l’onglet **Général**, sélectionnez **Intersociétés**.
1. Spécifiez les paramètres de paramétrage intersociétés pour le compte client. Ces paramètres incluent l’entité juridique qui contient le fournisseur correspondant et le compte fournisseur. Les paramètres incluent également les stratégies de commande fournisseur, les stratégies de commande client, la mise en correspondance des valeurs et les stratégies pour les contrats de vente et les contrats d’achat. Vous spécifiez également s’il faut utiliser les valeurs de données de base du compte client ou du compte fournisseur dans l’autre entité juridique.
1. Répétez les étapes 1 à 4 pour les autres clients intersociétés de l’entité juridique.
1. Accédez à **Comptabilité fournisseur \> Fournisseurs \> Tous les fournisseurs**.
1. Sélectionnez un compte fournisseur.
1. Dans le volet Actions, sous l’onglet **Général**, sélectionnez **Intersociétés**.
1. Spécifiez les paramètres de paramétrage intersociétés pour le compte fournisseur. Ces paramètres incluent l’entité juridique qui contient le client correspondant et le compte client. Les paramètres incluent également les stratégies de commande client, les stratégies de commande fournisseur, la mise en correspondance des valeurs et les stratégies pour les contrats d’achat et les contrats de vente. Vous spécifiez également s’il faut utiliser les valeurs de données de base du compte fournisseur ou du compte client dans l’autre entité juridique.
1. Répétez les étapes 6 à 9 pour les autres fournisseurs intersociétés de l’entité juridique.

## <a name="set-up-products"></a>Paramétrage de produits

Pour paramétrer le commerce intersociétés pour des clients et des fournisseurs, procédez comme suit :

1. Accédez à **Gestion des informations sur les produits \> Produits \> Tous les produits et produits génériques**.
1. Définissez les produits qui sont lancés dans les entités juridiques dans lesquelles vous souhaitez effectuer du commerce intersociétés.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
