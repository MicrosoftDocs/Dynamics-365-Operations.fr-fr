---
title: Vérifier les différences entre les prix de commande intersociétés
description: Cet article explique comment vérifier les écarts de prix des commandes intersociétés
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: ca27e86545ba8179c595e55487dbbf49cd9ec528
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890681"
---
# <a name="check-intercompany-order-price-discrepancies"></a>Vérifier les différences entre les prix de commande intersociétés

[!include [banner](../../includes/banner.md)]

Cette procédure permet de contrôler les différences de prix des commandes intersociétés.

1. Accédez à **Approvisionnements \> Périodique \> Nettoyer \> Vérifier les écarts de prix des commandes intersociétés**.
1. Paramétrez un traitement par lots (le cas échéant), puis sélectionnez **OK** pour vérifier les prix et remises des commandes client et fournisseur intersociétés. Sinon, sélectionnez **Annuler** pour fermer la page sans effectuer la vérification.

    > [!TIP]
    > Les éventuels problèmes concernant la synchronisation ou les prix seront répertoriés dans un message d'information. que vous pouvez imprimer à des fins de référence.

1. Dans le message d'information, sélectionnez la ligne concernée pour ouvrir la commande dans l'entité juridique en cours. Ouvrez la commande dans l'entité juridique associée en sélectionnant **Intersociété**, puis **Bon de commande intersociétés** ou **Commande de vente intersociétés**.

    > [!NOTE]
    > Pour autoriser la mise à jour d'une commande intersociétés :
    >
    > 1. Allez dans **Comptabilité client \> Clients \> Tous les clients**.
    > 1. Dans le volet Actions, sélectionnez l'onglet **Général**, puis sélectionnez à nouveau **Intersociétés**.
    > 1. Sur la page **Intersociétés**, sélectionnez **Politiques de bons de commande** ou **Stratégies pour les commandes client**.
    > 1. Sélectionnez **Autoriser la modification du prix** et **Autoriser la modification de la remise** dans les deux zones.

1. Ouvrez la commande intersociétés dont vous voulez conserver le prix.
1. Pour chaque ligne de commande, modifiez le champ **Prix unitaire** pour la ligne, puis rétablissez sa valeur d'origine. Modifiez le champ **Remise** pour la ligne dans les deux sens, et modifiez les champs **Frais sur achats** ou **Frais de vente** pertinents dans les deux sens. Ce changement de valeurs déclenche une synchronisation des prix, des remises et des frais de cette ligne de commande intersociétés sur la ligne de commande intersociétés référencée afin qu'ils soient automatiquement alignés.

    > [!NOTE]
    > Cette synchronisation est valide uniquement si la commande client intersociétés n'a pas été facturée. Si elle a été validée par la facture et qu'un journal des factures client a été créé, des modifications doivent être directement apportées sur les lignes de commande fournisseur intersociétés en définissant les prix, les remises et les frais comme égaux à ceux du journal des factures client intersociétés. Si tel n'est pas le cas, la commande fournisseur intersociétés ne peut pas être validée par la facture car les totaux de la commande ne correspondent pas.

1. Répétez la procédure jusqu'à ce que toutes les commandes client et fournisseur intersociétés soient synchronisées.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
