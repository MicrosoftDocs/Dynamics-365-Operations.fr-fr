---
title: Le paramètre Valider sur le compte de frais dans la comptabilité n’est pas activé
description: Ce problème se produit lorsqu’une commande fournisseur est facturée, si l’option « Valider sur le compte de frais dans la comptabilité » est activée sur l’onglet « Facture » de la page « Paramètres de la comptabilité fournisseur »
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 592444958dad4624fdc9098dc58df0a2e49e63de
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476356"
---
# <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a>Le paramètre Valider sur le compte de frais dans la comptabilité n’est pas activé

## <a name="symptoms"></a>Symptômes

Ce problème se produit lorsqu’une commande fournisseur est facturée, si l’option **Valider sur le compte de frais dans la comptabilité** est définie sur *Oui* sur l’onglet **Facture** de la page **Paramètres de la comptabilité fournisseur**.

## <a name="reproduce-the-issue"></a>Reproduire le problème

La procédure suivante montre comment reproduire le problème.

1. Allez dans **Comptabilité fournisseur \> Paramètres \> Paramètres de la comptabilité fournisseur**.
1. Sur l’onglet **Facture**, définissez l’option **Valider sur le compte de frais dans la comptabilité** sur *Oui*.
1. Accédez à **Gestion des stocks \> Paramétrage \> Validation \> Validation**.
1. Sur l’onglet **Commande fournisseur**, assurez-vous d’avoir supprimé toutes les lignes de dépenses d’achat pour le produit.
1. Accédez à **Comptabilité fournisseur \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Création d’une commande fournisseur. Dans le champ **Compte fournisseur**, sélectionnez *1001 Fournitures de bureau Acme*.
1. Ajoutez une ligne de commande fournisseur avec les paramètres suivants :

    - **Numéro d’article :** *Projecteur laser D0011*
    - **Site :** *1*
    - **Entrepôt :** *11*
    - **Quantité :** *4*

1. Dans le volet Actions, sous l’onglet **Achats**, dans le groupe **Action**, cliquez sur **Confirmer**.
1. Dans le volet Actions, sous l’onglet **Recevoir**, dans le groupe **Générer**, sélectionnez **Accusé de réception de marchandises**.
1. Dans la boîte de dialogue **Validation de l’accusé de réception de produits**, dans le champ **Accusé de réception de produits**, entrez un nombre arbitraire, puis sélectionnez **OK**.
1. Dans le volet Actions, sous l’onglet **Facture**, dans le groupe **Générer**, sélectionnez **Facture**.
1. Dans le champ **Numéro**, entrez un numéro arbitraire comme numéro de facture.
1. Mettez à jour le statut de rapprochement et validez.
1. Notez que vous recevez maintenant l’erreur suivante lorsque vous générez une facture à partir d’une commande fournisseur : "Le numéro de compte pour le type de transaction Dépenses d’achat pour le produit n’existe pas".

## <a name="resolution"></a>Résolution

Cela dépend des paramètres des factures et des groupes de factures. Pour plus d’informations, consultez l’article de blog suivant : [Comptabilité pour les frais d’achat et la variation des stocks](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).
