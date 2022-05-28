---
title: Calcul TDS sur les paiements et les billets à ordre
description: Cette rubrique fournit des informations de référence sur les différentes opérations de paiement sur lesquelles la taxe déduite à la source (TDS) est calculée.
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
ms.openlocfilehash: 7f38a8c4b0416abb10bfdaf95c3379e964e9a41e
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726460"
---
# <a name="tds-calculation-on-payments-and-promissory-notes"></a>Calcul TDS sur les paiements et les billets à ordre

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations de référence sur les différentes opérations de paiement sur lesquelles la taxe déduite à la source (TDS) est calculée.

| Numéro de série | Type de transaction | Montant de la transaction | Nom et chemin d'accès de la page | Type de compte et type de compte de contrepartie |
|---------------|------------------|--------------------|--------------------|--------------------------------------|
| 1             | Acompte/Paiement contre facture (TDS payable) | Débit ou crédit | <ul><li>Journal des opérations (**Comptabilité \> Entrées de journal \> Journaux des opérations**)</li><li>Journal des factures (**Comptabilité fournisseur \> Factures \> Journal des factures**)</li><li>Journal des paiements (**Comptabilité fournisseur \> Paiements \> Journal des paiements fournisseur**)</li></ul> | Fournisseur (Dr.), Banque (Cr.) |
| 2             | Acompte/Paiement contre facture (Achat effectué auprès du client - TDS payable) | Débit ou crédit | <ul><li>Journal des opérations (**Comptabilité \> Entrées de journal \> Journaux des opérations**)</li><li>Journal des factures (**Comptabilité fournisseur \> Factures \> Journal des factures**)</li><li>Journal des paiements (**Comptabilité fournisseur \> Paiements \> Journal des paiements fournisseur**)</li></ul> | Client (Dr.), Banque (Cr.) |
| 3             | Billets à ordre | Débit | Journal de création des billets à ordre (**Comptabilité fournisseur \> Paiements\> Billets à ordre \> Journal de création des billets à ordre**) | Fournisseur (Dr.), Registre (Cr.) |
| 4             | Recettes diverses (créances TDS) | Débit ou crédit | Journal des opérations (**Comptabilité \> Entrées de journal \> Journaux des opérations**) | Banque (Dr.), Registre (Cr.) |
| 5             | Autres dépenses (TDS payable) | Débit ou crédit | Journal des opérations (**Comptabilité \> Entrées de journal \> Journaux des opérations**) | Banque (Dr.), Registre (Cr.) |

Suivez ces étapes pour calculer le TDS sur les paiements et les billets à ordre.

1. Sur les pages de journal, créez des lignes de journal. Sélectionnez le type de compte et le type de compte de contrepartie.
2. Sélectionnez **Fonctions \> Règlement** pour ouvrir la page **Édition d'une transaction en cours**. Sélectionnez ensuite une facture spécifique qui doit être réglée. Si TDS a déjà été calculé au niveau de la facture, le champ **Origine du montant** indique le montant de base sur lequel le TDS a été calculé. Le champ **Montant TDS** affiche le montant TDS qui a été calculé pour la transaction. Le champ **Montant** indique le montant net du paiement (c'est-à-dire le montant du paiement après déduction de TDS).

    > [!NOTE]
    > Pour un paiement effectué sur facture, les conditions suivantes s'appliquent :
    >
    > - Si le montant du paiement et le montant de la facture sont identiques, TDS n'est pas calculé s'il a déjà été calculé au niveau de la facture.
    > - Si le montant de la facture après déduction du montant TDS est supérieur au montant du paiement, TDS n'est pas calculé.
    > - Si le montant de la facture après déduction du montant TDS est inférieur au montant du paiement, TDS est calculé sur le montant qui dépasse le montant de la facture.

3. Sur la page **Justificatif de journal**, dans l'onglet **Aperçu**, dans le champ **Groupes TDS**, vérifiez ou modifiez le groupe TDS par défaut défini pour le fournisseur ou le client. Le TDS calculé sur les lignes de journal est basé sur la formule définie pour les codes TVA TDS dans le groupe TDS.

    > [!NOTE]
    > TDS est calculé uniquement si l'option **Calcul de la retenue à la source** est définie sur **Oui** pour le fournisseur sur la page **Fournisseurs**.

4. Dans l'onglet **Informations fiscales**, dans la section **Informations sur la société**, dans le champ **Nom**, vous pouvez sélectionner un nom de société pour les adresses alternatives configurées pour la société.

    Dans la section **Retenue à la source**, le champ **Nature de la personne évaluée** affiche la nature de la catégorie du fournisseur ou du client. Le champ **Numéro de compte fiscal (TAN)** affiche le numéro de compte fiscal (TAN) de la société sélectionnée.

5. Sélectionnez **Bouton de retenue d'impôt \> Retenue à la source** pour ouvrir la page **Opérations de retenue à la source temporaire**. La partie supérieure de cette page contient les champs suivants :

    - **Montant total de la retenue à la source** - Le TDS total qui a été calculé pour la transaction pour le groupe TDS.
    - **Valeur** - Le pourcentage total qui a été utilisé pour calculer TDS pour la transaction. Le pourcentage total est basé sur la formule définie pour les codes de taxe TDS et attachée au groupe TDS.
    - **Montant de la retenue à la source ajusté au total** - Le montant total ajusté du TDS pour tous les codes de taxe du groupe TDS.
    - **TDS** - Une case cochée indique qu'un groupe TDS est attaché à la transaction.

    Les champs des onglets **Aperçu**, **Général** et **Ajustement** affichent le montant TDS calculé et les détails du montant TDS ajusté pour chaque code de taxe TDS associé au groupe TDS.

6. Sélectionnez **Seuil** pour ouvrir la page **Seuil** dans laquelle vous pouvez consulter la limite de seuil définie pour la composant de taxe TDS associée à un code de taxe TDS spécifique.
7. Sélectionnez **Concepteur de formule** pour ouvrir la page **Concepteur de formule**, où vous pouvez consulter la formule définie pour un code de taxe TDS spécifique.
8. Fermez les pages **Concepteur de formule** et **Opérations de retenue à la source temporaire** pour revenir à la page **Justificatif de journal**.
9. Contrôlez et validez le journal. Le montant TDS qui a été calculé est imputé au compte fournisseur défini pour chaque code TVA TDS du groupe TDS. Les comptes clients pour les codes TVA TDS sont définis sur la page **Codes de retenue à la source**.
10. Sélectionnez **Retenue à la source validée** pour ouvrir la page **Opérations de retenue à la source**. Le champ **Valeur** affiche le pourcentage total qui a été utilisé pour calculer TDS pour la transaction.

    Les champs des onglets **Aperçu**, **Général** et **Montant** affichent les montants TDS qui ont été calculés pour le groupe TDS associé à la transaction.

11. Vérifiez les informations de calcul TDS pour chaque code de taxe TDS associé au groupe TDS.

## <a name="generate-payments"></a>Générer des paiements

Pour générer des paiements, suivez ces étapes.

1. Utilisez l’une des procédures suivantes :

    - Accédez à **Comptabilité fournisseur \> Paiements \> Journal des paiements fournisseur**.
    - Accédez à **Comptabilité client \> Paiements \> Journal des paiements client**.
    - Accédez à **Comptabilité fournisseur \> Paiements \> Billets à ordre \> Journal de création des billets à ordre**.
    - Accédez à **Comptabilité client \> Paiements \> Lettre de change \> Journal de création des lettres de change**.
    - Accédez à **Comptabilité client \> Paiements \> Lettre de change \> Journal de renouvellement des lettres de change**.

2. Sélectionnez **Lignes**.
3. Sélectionnez **Fonctions \> Générer des paiements**.
