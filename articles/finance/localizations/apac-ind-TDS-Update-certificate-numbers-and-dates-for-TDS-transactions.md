---
title: Mettre à jour les numéros et les dates de certificat pour les transactions TDS
description: Cette rubrique explique comment mettre à jour les numéros de certificats récupérables et les dates enregistrés pour les comptes fournisseur, client et compte général pour la taxe déduite à la source (TDS).
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
ms.openlocfilehash: 7f8b5713e8ce3f9e9c89b8b3bc6ea84fe1f0fa54
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724809"
---
# <a name="update-certificate-numbers-and-dates-for-tds-transactions"></a>Mettre à jour les numéros et les dates de certificat pour les transactions TDS

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment mettre à jour les numéros de certificats récupérables et les dates enregistrés pour les comptes fournisseur, client et compte général pour la taxe déduite à la source (TDS). Vous pouvez afficher les certificats des transactions TDS sur la page **Certificats récupérables**. Vous pouvez mettre à jour les certificats en utilisant la page **Mettre à jour les certificats**.

Suivez ces étapes pour mettre à jour les numéros et les dates des transactions TDS.

1. Accédez à **Taxe \> Déclarations \> Retenue à la source \> Mettre à jour le certificat**.

    [![Mettre à jour la page du certificat.](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)

2. Sur la page **Mettre à jour le certificat**, dans la section **Sélectionner**, dans le champ **Type de taxe**, sélectionnez **TDS**.
3. Dans le champ **Numéro de certificat**, sélectionnez le numéro de certificat TDS du client ou du fournisseur.

    > [!NOTE]
    > Le champ **Numéro de certificat** répertorie uniquement les numéros de certificat TDS que la case à cocher **Fermé** est désactivée sur la page **Certificats récupérables**.

    Le champ **Date du certificat** affiche la date du certificat. Le champ **Type de compte** indique le type de compte pour lequel le numéro de certificat TDS est reçu et le champ **Nom** affiche le nom du compte.

5. Dans les champs **Date de début** et **Date de fin**, entrez les dates de début et de fin de la période pour lesquelles afficher les transactions TDS.
6. Sélectionnez **Afficher les données** pour afficher les transactions TDS qui ont été validées pendant la période sélectionnée.

    Dans l'onglet **Aperçu**, la grille du volet supérieur affiche les informations suivantes sur chaque transaction TDS qui a été validée pour le fournisseur ou le client au cours de la période sélectionnée :

    - **Justificatif** – Numéro de document de la transaction TDS.
    - **Date** – Date de la transaction TDS.
    - **Montant** – Le montant de la facture à partir duquel la transaction TDS a été calculée.
    - **Montant de la taxe** – Le montant de la taxe TDS qui a été calculé pour la transaction.

7. Pour déplacer des transactions TDS spécifiques de la grille supérieure vers la grille inférieure, sélectionnez les transactions, puis sélectionnez **Inclure**. Sinon, sélectionnez **Tout inclure** pour déplacer toutes les transactions TDS de la grille supérieure vers la grille inférieure.

    Pour déplacer des transactions TDS spécifiques ou toutes les transactions TDS de la grille inférieure vers la grille supérieure, utilisez le bouton **Exclure** ou **Tout exclure**.

8. Sélectionnez **Mettre à jour** pour mettre à jour les champs **Numéro de certificat** et **Date du certificat** pour les transactions TDS dans la grille inférieure.
10. Accédez à **Impôt \> Impôts indirects \> Retenue à la source \> Certificat récupérable** et sélectionnez **Enquête** pour afficher les lignes de transaction mises à jour qui ont les nouveaux numéros de certificat sur la page **Transactions de certificat**.

    [![Page Transactions de certificat.](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)
