---
title: Page Liste des transactions fournisseur
description: Cette rubrique fournit des informations sur la page Liste des transactions fournisseur pour Microsoft Dynamics 365 for Finance and Operations.
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: 1ef7d97f059801f2fb2c0d451546b57055208f81
ms.contentlocale: fr-fr
ms.lasthandoff: 08/31/2018

---

# <a name="vendor-transaction-list-page"></a>Page Liste des transactions fournisseur

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a>Afficher les règlements

L'onglet **Afficher les règlements** du volet Actions permet d'accéder rapidement à l'historique des règlements et à d'autres informations sur l'ensemble de la transaction de règlement. Vous pouvez également afficher des transactions supplémentaires associées à la transaction sélectionnée, soit parce qu'elles faisaient partie du même règlement, soit parce qu'il s'agit de paiements créés dans le même journal des paiements.

1. Sélectionnez **Comptabilité fournisseur \> Tous les fournisseurs**.
2. Sélectionnez un fournisseur avec des transactions, puis sélectionnez **Fournisseur \> Transactions**.
3. Sélectionnez une transaction à rechercher.
4. Sélectionnez l'onglet **Afficher les règlements** dans le volet Actions.

    La boîte de dialogue **Afficher les règlements** s'ouvre et affiche la transaction sélectionnée et tous les documents réglés qui lui sont associés. Cette boîte de dialogue ressemble à la vue de l'historique des règlements, mais elle comprend tous les documents associés.

5. Vous pouvez effectuer plusieurs tâches dans cette boîte de dialogue. Sélectionnez un ou plusieurs N° documents, puis sélectionnez l'un des menus suivants :

   - **Afficher la comptabilité** – Tous les N° documents associés aux documents sélectionnés s'affichent. Sélectionnez **Fermer** pour fermer la boîte de dialogue.
   - **Exporter** – Exportez les N° documents sélectionnés vers Microsoft Excel.
   - **Afficher les paiements associés** – Toutes les transactions du journal des paiements qui ont été créées dans le journal des paiements associé au document sélectionné s'affichent. En outre, tous les règlements associés à ces paiements s'affichent. L'intitulé de ce menu est également remplacé par **Afficher les règlements**. Sélectionnez **Afficher les règlements** pour afficher uniquement les transactions disponibles lorsque vous avez ouvert pour la première fois la boîte de dialogue **Afficher les règlements**.
    - **Régler les transactions** – Ce menu apparaît si le document initial sélectionné n'était pas totalement réglé. Lorsque vous le sélectionnez, la boîte de dialogue **Afficher les règlements** s'ouvre pour vous permettre de sélectionner des transactions à régler.
    - **Annuler les règlements** – Ce menu apparaît si le document initial sélectionné était totalement réglé. Lorsque vous le sélectionnez, la boîte de dialogue **Annuler les règlements** s'affiche pour vous permettre d'annuler les règlements effectués pour ce document.

