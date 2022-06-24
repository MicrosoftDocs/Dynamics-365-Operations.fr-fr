---
title: Définition des paramètres de validation d’une commande intersociétés
description: Cet article explique comment configurer les paramètres pour valider une commande intersociétés
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
ms.openlocfilehash: 97ea0061d57beede6350eecfd497c12dd37aea31
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900794"
---
# <a name="set-up-parameters-to-post-an-intercompany-order"></a>Définition des paramètres de validation d’une commande intersociétés

[!include [banner](../../includes/banner.md)]

Lorsqu'une facture client intersociétés est validée, vous pouvez la paramétrer pour valider automatiquement la commande fournisseur intersociétés et la facture client d'origine.

> [!NOTE]
> Avant de démarrer cette procédure, paramétrez la gestion de l'impression dans votre organisation pour qu'elle sélectionne l'imprimante appropriée pour les factures. Ainsi, vous serez certain que la facture de la commande client d'origine sera imprimée sur l'imprimante appropriée.

Vous devez définir les paramètres suivants :

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**. Sélectionnez la commande client que vous souhaitez utiliser.
1. Dans la commande client, dans le volet Actions, sélectionnez **Affichage de l'en-tête**, puis sélectionnez l'organisateur **Paramètres intersociétés** et ouvrez-le.
1. Accédez au volet Actions, sous l’onglet **Commande client**, sélectionnez **Modifier**.
1. Revenez à l'organisateur **Paramètres intersociétés**, puis sélectionnez **Livraison directe** pour activer la livraison directe via la chaîne intersociétés (toutes les commandes).
1. Sélectionnez **Enregistrer** pour enregistrer les nouveaux paramètres de la commande client. Puis sélectionnez **Fermer** pour fermer la commande client.
1. Accédez à **Approvisionnements \> Fournisseurs \> Tous les fournisseurs**. Sous l'onglet **Général**, sélectionnez **Intersociétés**.
1. Sur la page de liste **Intersociétés**, sélectionnez le lien **Politiques de bons de commande**. Dans le groupe de champs **Bon de commande intersociétés (livraison directe)**, sélectionnez **Valider la facture automatiquement** et décochez le champ **Imprimer la facture automatiquement**.
1. Dans le groupe de champs **Bon de commande d'origine (livraison directe)**, sélectionnez le champ **Valider la facture automatiquement** et le champ **Imprimer la facture automatiquement**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
