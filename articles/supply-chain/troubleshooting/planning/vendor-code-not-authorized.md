---
title: Le code fournisseur n’est pas autorisé pour un produit et une date spécifiques
description: Lorsque vous essayez de confirmer une commande planifiée ou d’ajouter une ligne à une commande fournisseur, vous recevez un message d’erreur indiquant que le code fournisseur n’est pas autorisé pour un produit et une date.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO_ReqTransPoMarkFirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e6b1189e4fedfdb029f4b4503f0635133df9d87e
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294077"
---
# <a name="vendor-code-isnt-authorized-for-a-specific-product-and-date"></a>Le code fournisseur n’est pas autorisé pour un produit et une date spécifiques

Code d’erreur : SYP4881415

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez de confirmer une commande planifiée ou d’ajouter une ligne à une commande fournisseur, vous recevez le message d’erreur suivant :

> Le code fournisseur %1 n’est pas autorisé pour %2 sur %3.

## <a name="cause"></a>Cause

L’erreur se produit parce que le champ **Méthode de vérification fournisseur approuvée** est défini sur *Avertissement seulement* ou sur *Non autorisé* pour le produit spécifié, et le fournisseur n’est actuellement pas autorisé à fournir ce produit.

## <a name="resolution"></a>Résolution

Pour résoudre ce problème, désactivez la vérification du fournisseur pour le produit concerné ou approuvez le fournisseur.

Pour désactiver la vérification du fournisseur pour un produit, procédez comme suit.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Ouvrez le produit concerné.
1. Sur l’onglet **Achat**, définissez le champ **Méthode de vérification fournisseur approuvée** sur une valeur autre que *Avertissement seulement* ou sur *Non autorisé*.

Pour approuver un fournisseur pour un produit, procédez comme suit.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Ouvrez l’article concerné.
1. Dans le volet Actions, sous l’onglet **Achat**, dans le groupe **Fournisseur approuvé**, sélectionnez **Paramétrage**.
1. Dans la page de liste **Fournisseur approuvé**, ajoutez une ligne à la grille, puis définissez valeurs suivantes pour elle :

    - **Fournisseur** : sélectionnez le fournisseur à approuver pour le produit actuel.
    - **Date d’effet** : sélectionnez la première date à laquelle le fournisseur est approuvé.
    - **Date d’expiration** : sélectionnez la dernière date à laquelle le fournisseur est approuvé.

Pour plus d’informations, consultez [Approuver les fournisseurs pour des produits spécifiques](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).
