---
title: Définition des paramètres TDS dans Comptabilité client et Comptabilité fournisseur
description: Cette rubrique explique comment définir des paramètres dans Comptes fournisseurs et Comptes clients pour prendre en charge les déductions de la taxe retenue à la source (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: d2cb434346dbbe5487522fe9f7110716c3a8c761
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725147"
---
# <a name="set-tds-parameters-in-accounts-payable-and-accounts-receivable"></a>Définition des paramètres TDS dans Comptabilité client et Comptabilité fournisseur

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment définir des paramètres dans Comptes fournisseurs et Comptes clients pour prendre en charge les déductions de la taxe retenue à la source (TDS).

1. Accédez à **Taxe \> Configuration \> Paramètres \> Paramètres de la comptabilité client**.
2. Dans l'onglet **Mises à jour**, sélectionnez **Mettre à jour les lignes de commande** pour ouvrir la boîte de dialogue **Mettre à jour les lignes de commande**.
3. Dans la section **Groupe TDS**, dans le champ **Mise à jour du groupe TDS**, spécifiez la méthode à utiliser pour mettre à jour le groupe TDS au niveau de la ligne. Ce paramètre est utilisé lorsque le groupe TDS est mis à jour sur un en-tête de commande. Les options suivantes sont disponibles :

    - **Jamais** - Le groupe TDS n'est pas mis à jour sur les lignes de commande lorsqu'il est mis à jour sur l'en-tête de commande.
    - **Toujours** - Le groupe TDS est automatiquement mis à jour sur les lignes de commande lorsqu'il est mis à jour sur l'en-tête de commande.
    - **Rapide** - Les utilisateurs reçoivent un message qui les invite à mettre à jour le groupe TDS sur les lignes de commande.
4. Cliquez sur **OK**.

    [![Boîte de dialogue Mettre à jour les lignes de commande.](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)

5. Accédez à **Taxe \> Configuration \> Paramètres \> Paramètres de la comptabilité fournisseur**.
6. Dans l'onglet **Général**, dans le raccourci **Fractionner en fonction des informations de livraison**, définissez l'option **Reçu de produit** sur **Oui** pour enregistrer et fractionner un reçu de produit qui a des adresses de livraison et des numéros de compte fiscaux (TAN) différents. Si cette option est définie sur **Non**, vous ne pouvez pas valider un bon de livraison d'achat comportant des adresses de livraison et des TAN différents.
7. Définit l'option **Facturer** pour **Oui** pour enregistrer et fractionner une facture d'achat qui a des adresses de livraison et des TAN différents.

    [![Fractionnement basé sur les informations de livraison FastTab.](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)

8. Fermez la page.
