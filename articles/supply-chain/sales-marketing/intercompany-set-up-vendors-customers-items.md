---
title: Paramétrer des fournisseurs, des clients et des articles pour le commerce intersociétés
description: Cette rubrique explique comment paramétrer des fournisseurs, des clients et des articles pour le commerce intersociétés
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 062b8fe956fef0f8172d26aac3df54b93e1941ef
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548255"
---
# <a name="set-up-vendors-customers-and-items-for-intercompany-trade"></a>Paramétrer des fournisseurs, des clients et des articles pour le commerce intersociétés

[!include [banner](../../includes/banner.md)]

Pour préparer votre organisation pour le commerce intersociétés, vous devez définir les fournisseurs et les clients avec lesquels vous entretiendrez des relations commerciales en interne. Vous devez ensuite associer ces fournisseurs et clients aux articles que vous achèterez ou vendrez.

1. Accédez à **Approvisionnements \> Fournisseurs \> Tous les fournisseurs**.
1. Sélectionnez le fournisseur à définir comme fournisseur intersociétés.
1. Dans le volet Actions, sous l’onglet **Général**, sélectionnez **Intersociétés**.
1. Spécifiez les paramètres de paramétrage intersociétés pour le compte fournisseur. Ces paramètres incluent le compte et l'entité juridique du client, les stratégies de commande client, les stratégies de commande fournisseur, la mise en correspondance des valeurs et les stratégies pour les contrats d'achat et les contrats de vente. Vous spécifiez également s'il faut utiliser les valeurs de données de base du compte fournisseur ou du compte client dans l'autre entité juridique.
1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Dans la page de liste **Produits lancés**, sélectionnez les articles à affecter au fournisseur, de sorte que les articles soient disponibles pour le commerce intersociétés. Pour chaque élément, ouvrez la page **Détails des produits lancés**. Sous l'onglet **Achat**, dans le champ **Fournisseur**, tapez le numéro du fournisseur.
1. Allez dans **Comptabilité client \> Clients \> Tous les clients**.
1. Sélectionnez le client à définir comme client intersociétés.
1. Dans le volet Actions, sous l’onglet **Général**, sélectionnez **Intersociétés**.
1. Spécifiez les paramètres de paramétrage intersociétés pour le compte client. Ces paramètres incluent le compte et l'entité juridique du fournisseur, les stratégies de commande fournisseur, les stratégies de commande client, la mise en correspondance des valeurs et les stratégies pour les contrats d'achat et les contrats de vente. Vous spécifiez également s'il faut utiliser les valeurs de données de base du compte client ou du compte fournisseur dans l'autre entité juridique.
1. Sur la page **Clients**, dans le raccourci **Facture et livraison**, sélectionnez la case **Créer des commandes intersociétés**. Pour que les commandes soient livrées directement aux clients, activez la case à cocher **Livraison directe**.

    > [!NOTE]
    > Si certains articles sont stockés et livrés aux clients par votre organisation, vous risquez de ne pas pouvoir créer de commandes intersociétés automatiquement, même si vous avez l'article en stock. Pour désactiver la génération automatique des commandes pour les articles que vous pouvez parfois avoir en stock, désactivez la case à cocher **Créer des commandes intersociétés**.

1. Si vous voulez autoriser la création indirecte de lignes supplémentaires sur une commande client, activez la case à cocher **Créer des lignes de commande indirecte**. Un utilisateur peut ensuite ajouter des lignes à la commande client originale à partir de la commande client intersociétés.

> [!WARNING]
> Si vous autorisez la création indirecte des lignes de commande, vous autorisez tous les ajouts à la commande client originale à partir de la commande client intersociétés. Chaque ajout est alors traité en direction du client, et ajouté à la commande et à la facture. En outre, chaque document impliqué dans la vente est imprimé et validé automatiquement. Les utilisateurs ne sont pas avertis de l'ajout.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
