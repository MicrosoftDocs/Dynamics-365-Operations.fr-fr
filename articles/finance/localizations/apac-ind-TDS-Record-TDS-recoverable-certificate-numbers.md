---
title: Enregistrer les numéros de certificat récupérables
description: Cette rubrique explique comment utiliser la page Certificats récupérables pour enregistrer les numéros de certificat et les dates des certificats TDS (Tax Deduced at Source) reçus pour un fournisseur, un client ou un compte général spécifique.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 8fa4d1200818b4657b044a376ebb292426250ae1
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407738"
---
# <a name="record-tds-recoverable-certificate-numbers"></a>Enregistrer les numéros de certificat récupérables

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment utiliser la page **Certificats récupérables** pour enregistrer les numéros de certificat et les dates des certificats TDS (Tax Deduced at Source) reçus pour un fournisseur, un client ou un compte général spécifique. Pour mettre à jour les numéros et dates de certificat TDS enregistrés pour les transactions TDS sur cette page, utilisez la page **Mettre à jour le certificat** (**Comptabilité \> Périodique \> Retenue à la source \> Mettre à jour le certificat**). Une fois la mise à jour des numéros de certificat TDS terminée, fermez-les.

Suivez ces étapes pour enregistrer les numéros et les dates des certificats TDS.

1. Accédez à **Taxe \> > Taxes indirectes \> Retenue à la source \> Certificats récupérables**.

    [![Page des certificats récupérables.](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png) 

2. Sur la page **Certificats récupérables**, dans le champ **Type de taxe**, sélectionnez **TDS**.
3. Sélectionnez **Nouveau** pour créer un enregistrement.
4. Dans le champ **Numéro de certificat**, entrez le numéro de certificat TDS.
5. Dans le cham p **Type de compte**, sélectionnez le type de compte pour lequel le certificat TDS est reçu : **Fournisseur**, **Client** ou **Registre**.
6. Dans le champ **Compte**, sélectionnez le numéro de compte fournisseur, compte client ou compte général, selon le type de compte que vous avez sélectionné. Le champ **Nom** affiche le nom du fournisseur, du client ou du compte général.
7. Dans le champ **Montant du certificat**, entrez le montant du certificat TDS.
8. Dans le champ **Date**, saisissez la date du certificat pour le numéro de certificat.
9. Sélectionnez **Demandes de renseignements** pour ouvrir la page **Transactions de certificat**, dans laquelle vous pouvez afficher les transactions TDS pour lesquelles le numéro et la date du certificat TDS sont mis à jour. Ces informations peuvent être mises à jour sur la page **Mettre à jour le certificat** (**Impôt \> Déclarations \> Retenue d'impôt \> Mettre à jour le certificat**).

    La page **Mettre à jour le certificat** affiche les informations suivantes pour chaque transaction TDS :

    - **Date** – Date de validation de la transaction TDS.
    - **Justificatif** – Numéro de document de la transaction TDS.
    - **Source** - Le module dans lequel la transaction TDS a été créée.
    - **Compte** - Le numéro de compte fournisseur, compte client ou compte général pour lequel la transaction TDS a été créée.
    - **Nom** - Le nom du compte fournisseur, compte client ou compte général pour lequel la transaction TDS a été créée.
    - **Montant** – Le montant de la facture à partir duquel la transaction TDS a été calculée.
    - **Montant de la taxe** – Le montant de la taxe TDS qui a été calculé pour la transaction.
    - **Date du certificat** - La date du certificat TDS qui a été mise à jour pour la transaction TDS.
    - **Numéro du certificat** - Le numéro du certificat TDS qui a été mis à jour pour la transaction TDS.

10. Sur la page **Certificats récupérables**, sélectionnez la case à cocher **Fermé** pour fermer le numéro de certificat TDS une fois que vous avez fini de le mettre à jour pour les transactions TDS sur la page **Mettre à jour le certificat**.

    Pour cocher la case **Fermé** pour tous les enregistrements de la page, sélectionnez **Marquer tout**.

    > [!NOTE]
    > Les numéros de certificat TDS pour lesquels la case à cocher **Fermé** est cochée pour cause de non-disponibilité sur la page **Mettre à jour le certificat**.
