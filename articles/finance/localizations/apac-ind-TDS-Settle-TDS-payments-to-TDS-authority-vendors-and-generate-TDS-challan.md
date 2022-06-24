---
title: Régler les paiements TDS aux fournisseurs de l’autorité TDS et générer un challan TDS
description: Cet article explique comment régler les paiements de taxe déduite à la source (TDS) aux fournisseurs autorisés de TDS.
author: kailiang
ms.date: 03/12/2021
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
ms.openlocfilehash: e1ee65a555193433e6712a8caa892d7a3ad7bf61
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848508"
---
# <a name="settle-tds-payments-to-tds-authority-vendors-and-generate-tds-challan"></a>Régler les paiements TDS aux fournisseurs de l’autorité TDS et générer un challan TDS

[!include [banner](../includes/banner.md)]

Cet article explique comment régler les paiements de taxe déduite à la source (TDS) aux fournisseurs autorisés de TDS.

1. Accédez à **Comptabilité fournisseur \> Paiements \> Journal des paiements fournisseur**.

    [![Page du journal des paiements fournisseur.](./media/apac-ind-TDS-51.png)](./media/apac-ind-TDS-51.png)

2. Sur la page **Journal des paiements fournisseur**, sélectionnez **Nouveau** pour créer une ligne de journal.
3. Dans le champ **Compte**, sélectionnez le fournisseur de l’autorité TDS auquel régler les paiements TDS.
4. Sélectionnez **Opérations de règlement** pour ouvrir la page **Opérations de règlement**, où vous pouvez afficher les transactions TDS réglées pour le fournisseur de l’autorité TDS.

    Les transactions TDS réglées pour une période de règlement sont présentées de la manière suivante :

    - Les transactions TDS pour lesquelles la nature de la catégorie des personnes évaluées est **Compagnie** sont affichées comme une seule ligne de transaction.
    - Les transactions TDS pour lesquelles la nature de la catégorie des personnes évaluées est **HUF**, **Confirmée**, **Individuelle**, **AOP**, **BOI**, **Autorité locale** ou **Autres** sont affichés comme une seule ligne de transaction.
    - Le champ **Montant** indique le montant total de TDS qui doit être payé au fournisseur de l’autorité TDS.

5. Sélectionnez **Transactions de retenue à la source** pour afficher les détails des transactions TDS différents qui ont été réglées pour la période de règlement. Vous pouvez afficher le fractionnement de chaque transaction TDS qui a été incluse dans le processus de règlement pour la période de règlement sur cette page.
6. Dans l’onglet **Aperçu**, sélectionnez la case à cocher **Marquer** pour les transactions TDS à régler au fournisseur de l’autorité TDS.

    L’onglet **Aperçu** affiche les informations suivantes pour chaque transaction TDS en cours :

    - **Date** – Permet d’ajouter la date de transaction.
    - **Justificatif** – N° document de paiement.
    - **Source** - Le module dans lequel la transaction TDS est enregistrée.
    - **Fournisseur/Client** - Le numéro de compte du fournisseur ou du client sur lequel le TDS est déduit.
    - **Nom du bénéficiaire/de la partie** - Le nom du fournisseur ou du client dont le TDS est déduit.
    - **Nature de la personne évaluée** - La nature de la catégorie des personnes évaluées à laquelle appartient le déduit.
    - **Montant** – Le montant de la facture à partir duquel la transaction TDS a été calculée.
    - **Montant de la taxe** – Le montant TDS qui a été calculé pour la transaction.

    > [!NOTE]
    > Désactivez la case à cocher **Marquer** pour toutes les transactions TDS qui ne doivent pas être réglées au fournisseur de l’autorité TDS.

    Dans l’onglet **Général**, le champ **PAN** indique le numéro de compte permanent (PAN) du bénéficiaire. Le champ **Date** indique la date du calcul TDS, et le champ **Valeur** indique le pourcentage total utilisé pour le calcul TDS.

7. Sélectionnez **Justificatif** pour afficher les entrées de justificatif pour la transaction TDS.
8. Fermez la page.
10. Sélectionnez **Composants de retenue à la source** pour ouvrir la page **Composants de retenue à la source** où vous pouvez afficher le TDS qui a été calculé par composant de taxe TDS pour un code de taxe TDS spécifique.

    Sous l’onglet **Aperçu**, le champ **Composant de taxe** affiche le composant de taxe TDS qui a été utilisé pour la transaction. Le champ **Montant** affiche le montant TDS qui a été calculé pour le composant de taxe TDS, dans la devise de base. Le champ **Montant accumulé** affiche le montant total de TDS qui a été calculé pour le composant de taxe TDS pour toutes les transactions réglées.

    Dans l’ongle **Montant**, la section **Devise par défaut** affiche le montant TDS qui a été calculé pour le composant de taxe TDS, dans la devise par défaut. La section **Devise secondaire** affiche le montant dans la devise secondaire.

11. Fermez la page **Composants de retenue à la source**.
12. Dans la page **Édition d’une transaction en cours**, dans le champ **Montant**, notez que le montant total à régler au fournisseur de l’autorité TDS pour la période de décompte est mis à jour.
13. Pour régler les transactions TDS de différentes périodes de règlement TDS au fournisseur de l’autorité TDS, sélectionnez la case à cocher **Marquer** pour les transactions.
14. Fermez la page **Édition d’une transaction en cours**.

    > [!NOTE]
    > Si seules quelques transactions sont sélectionnées pour le règlement sur la page **Transactions de retenue à la source**, le montant TDS total des transactions sélectionnées est mis à jour dans le champ **Correction** dans la page **Édition d’une transaction en cours**. Le montant de la correction est mis à jour sur la ligne de journal sur la page **Justificatif de journal**, et la page **Édition d’une transaction en cours** est fermée.

    Sur la page **Justificatif de journal**, le champ **Débit** indique le montant total à payer au fournisseur de l’autorité TDS.

15. Entrez les détails du compte de contrepartie.

    > [!NOTE]
    > Si les transactions TDS ont des numéros de compte de taxe (TAN) différents, des lignes de journal sont créées par TAN sur la page **Justificatif de journal**.

16. Dans l’onglet **Frais de paiement**, dans le champ **ID frais**, sélectionnez un ID de frais dont le type de frais est **Intérêt** ou **Autres** pour facturer les frais de paiement pour les paiements différés qui sont effectués auprès du fournisseur de l’autorité TDS.

    Dans l’onglet **Informations fiscales**, dans la section **Informations sur la société**, le champ **Nom** affiche le nom de l’entreprise. Dans la section **Retenue à la source**, le **Numéro de compte de la taxe (TAN)** affiche le TAN attaché à la ligne de transaction.

17. Contrôlez et validez le journal.
18. Sélectionnez **Retenue à la source \> Informations Challan** pour saisir les détails du challan pour la transaction.

    Le champ **Justificatif** affiche le numéro de document de la transaction.
    
19. Sélectionnez la case à cocher **TDS déposé par écriture comptable** si le montant TDS est déposé en utilisant l’écriture comptable.
20. Dans le champ **Numéro de Challan**, entrez le numéro de challan utilisé pour effectuer le paiement au fournisseur de l’autorité TDS.
21. Dans le champ **Date**, saisissez la date du challan.
22. Dans le champ **Nom de la banque**, sélectionnez le nom de la banque à laquelle le montant TDS payable au fournisseur de l’autorité TDS doit être déposé. Ce champ répertorie tous les comptes bancaires qui ont été configurés pour le fournisseur de l’autorité TDS via **Comptabilité fournisseur \> Tous les fournisseurs \> Configurer \> Comptes bancaires**.
23. Dans le champ **Code BSR**, entrez le code de retour statistique de base (BSR) de la banque.
24. Fermez la page.

### <a name="example"></a>Exemple

La période 04/01/2009 est réglée pour le groupe de composants TDS **Location** à l’aide du processus de règlement TDS périodique. Le montant total TDS de 141 625 est imputé au compte d’autorité fournisseur TDS pour la période de décompte TDS. Vous pouvez consulter ce montant dans le champ **Montant** sur la page **Édition d’une transaction en cours** pour le fournisseur de l’autorité TDS.

Si vous sélectionnez **Opérations de retenue à la source** pour afficher les différentes transactions TDS qui ont été réglées pour la période, les informations suivantes s’affichent.

| Montant TDS |
|------------|
| 16,995.00  |
| 22,660.00  |
| 28,325.00  |
| 16,995.00  |
| 28,325.00  |
| 16,995.00  |
| 11,330.00  |

Pour un montant TDS spécifique, vous pouvez sélectionner **Composants de retenue à la source** pour afficher le TDS qui a été calculé par composant de taxe TDS pour un code de taxe TDS spécifique. Pour cet exemple, vous sélectionnez **Composants de retenue à la source** pour le montant TDS 16 995. Le montant de la taxe calculé par composant pour la transaction s’affiche.

| Composant fiscal | Montant    | Montant cumulé |
|---------------|-----------|--------------------|
| TDS           | 1,5000.00 | 125,000.00         |
| Surcharge     | 1,500.00  | 12,500.00          |
| PE-Cess       | 330.00    | 2,750.00           |
| SHECess      | 165.00    | 1,375.00           |

Si vous avez sélectionné uniquement les montants TDS 16 995, 22 660 et 2 8325 pour le règlement sur la page **Transactions de retenue à la source**, le montant total du règlement est affiché sous la forme **67 980** dans le champ **Correction** sur la page **Édition d’une transaction en cours**. Si cette transaction est marquée pour règlement, et que la page **Édition d’une transaction en cours** est fermée, le montant **67 980** s’affiche dans le champ **Débit** sur la page **Justificatif de journal**.

Vous pouvez maintenant valider le journal et générer le challan TDS.

### <a name="adjustment-of-advance-payments-that-are-made-to-tds-authority-vendors"></a>Ajustement des acomptes versés aux fournisseurs autorisés de TDS

Pour ajuster un paiement anticipé qui a été versé au fournisseur de l’autorité TDS à un paiement réel, accédez à **Comptabilité fournisseur \> Fournisseurs \> Tous les fournisseurs \> Modification des transactions**. Si le paiement réel effectué dépasse le paiement anticipé, deux numéros challan sont générés pour la transaction. Cependant, seul le premier numéro challan est affiché dans l’enquête TDS.
