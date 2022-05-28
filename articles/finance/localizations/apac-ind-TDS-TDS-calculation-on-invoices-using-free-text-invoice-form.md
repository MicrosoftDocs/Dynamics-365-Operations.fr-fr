---
title: Calcul TDS sur les factures à partir de la page Facture financière
description: Cette rubrique explique comment calculer la taxe déduite à la source (TDS) sur les factures à l'aide de la page Facture financière.
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
ms.openlocfilehash: 5a1960974dff90ef5f0cc8eab018351a9e412858
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725175"
---
# <a name="tds-calculation-on-invoices-from-the-free-text-invoice-page"></a>Calcul TDS sur les factures à partir de la page Facture financière

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment calculer la taxe déduite à la source (TDS) sur les factures à l'aide de la page **Facture financière**.

1. Allez dans **Comptabilité client \> Factures \> Toutes factures financières**.

    [![Page Facture financière.](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)

2. Sélectionnez **Nouveau** pour créer une facture financière, puis entrez les informations requises.
3. Sélectionnez l'onglet **Facture**. Dans la section **Retenue à la source**, le champ **Nature de la personne évaluée** affiche la nature de la catégorie du fournisseur ou du client.
4. Dans le champ **Groupe TDS**, révisez ou modifiez le groupe TDS par défaut défini pour le client.

    > [!NOTE]
    > Lorsque vous sélectionnez une valeur dans le champ **Groupe TDS**, le champ **Groupe TCS** n'est pas disponible. TDS est calculé uniquement si l'option **Calcul de la retenue à la source** est définie sur **Oui** pour le client sur la page **Tous les clients**.

5. Dans l'onglet **Informations fiscales**, dans la section **Informations sur la société**, dans le champ **Nom**, vous pouvez sélectionner un nom de société pour une adresse alternative configurée pour la société.

    Dans la section **Retenue à la source**, le champ **Numéro de compte fiscal (TAN)** affiche le numéro de compte fiscal (TAN) de la société sélectionnée.

6. Dans l'onglet **Lignes de facture**, créez des lignes de facture, puis entrez les détails requis.

    Dans la section **Groupe de retenue à la source**, le champ **Numéro de compte fiscal (TAN)** affiche le TAN, et le champ **Groupe TDS** affiche le groupe TDS.

7. Sélectionnez **Retenue à la source** pour ouvrir la page **Opérations de retenue à la source temporaire**. La partie supérieure de cette page contient les champs suivants :

    - **Montant total de la retenue à la source** - Le TDS total qui a été calculé pour la transaction pour le groupe TDS.
    - **Valeur** - Le pourcentage total qui a été utilisé pour calculer TDS pour la transaction. Le pourcentage total est basé sur la formule définie pour les codes de taxe TDS et attachée au groupe TDS.
    - **Montant de la retenue à la source ajusté au total** - Le montant total ajusté du TDS pour tous les codes de taxe du groupe TDS.
    - **TDS** - Une case cochée indique qu'un groupe TDS est attaché à la transaction.

    Les champs des onglets **Aperçu**, **Général** et **Ajustement** affichent le montant TDS calculé et les détails du montant TDS ajusté pour chaque code de taxe TDS associé au groupe TDS.

8. Sélectionnez **Seuil** pour ouvrir la page **Seuil** dans laquelle vous pouvez consulter la limite de seuil définie pour la composant de taxe TDS associée à un code de taxe TDS spécifique.
9. Sélectionnez **Concepteur de formule** pour ouvrir la page **Concepteur de formule**, où vous pouvez consulter la formule définie pour un code de taxe TDS spécifique.
10. Validez la facture financière. Le montant TDS qui est calculé pour la facture financière est imputé au compte fournisseur défini pour chaque code TVA TDS du groupe TDS. Les comptes clients pour les codes TVA TDS sont définis sur la page **Codes de retenue à la source**.
11. Sélectionnez **Retenue à la source validée** pour ouvrir la page **Opérations de retenue à la source**. Le champ **Valeur** affiche le pourcentage total qui a été utilisé pour calculer TDS pour la transaction.

    Les champs sur les onglets **Aperçu**, **Général** et **Montant** affichent les montants TDS qui ont été calculés sur les lignes de facture.

12. Vérifiez les informations de calcul TDS pour chaque code de taxe TDS associé au groupe TDS.
