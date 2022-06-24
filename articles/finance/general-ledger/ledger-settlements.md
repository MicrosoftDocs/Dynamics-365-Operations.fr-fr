---
title: Lettrages comptables
description: Cet article explique comment utiliser la page Règlements comptables pour régler des écritures comptables et contrepasser des règlements.
author: kweekley
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransSettlement
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-11-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 39fd6c6677565a4b1e9a9bf6f43a4c630cb5e07b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902485"
---
# <a name="ledger-settlements"></a>Lettrages comptables

[!include [banner](../includes/banner.md)]

Le règlement comptable désigne le processus de mise en correspondance des transactions de débit et de crédit dans la comptabilité. Le règlement des montants débiteurs et créditeurs est utilisé pour rapprocher le solde du compte général avec les transactions détaillées qui composent ce solde.

Les transactions réglées peuvent être exclues des demandes de renseignements et des rapports. De cette façon, il est plus facile d’analyser les transactions comptables qui composent le solde comptable.

> [!IMPORTANT] 
> Le règlement compare le compte général de la comptabilité client/comptabilité fournisseur à partir de la facture et du paiement. Lorsque le règlement se produit dans les registres auxiliaires Comptabilité fournisseur et Comptabilité client, les écritures comptables correspondantes ne sont pas réglées automatiquement.

## <a name="ledger-settlement-features"></a>Fonctionnalités du règlement comptable
Dans Microsoft Dynamics 365 Finance version 10.0.21, l’option **Activer les règlements comptables avancés** a été supprimée de la page **Paramètres de comptabilité**. Le règlement comptable avancé est désormais toujours activé.
Dans Finance, version 10.0.25, la fonctionnalité **Reconnaissance entre un règlement comptable et la clôture de fin d’exercice** a été introduite. Cette fonction modifie la fonctionnalité fondamentale du règlement comptable ainsi que la clôture de fin d’exercice comptable. Avant d’activer cette fonctionnalité dans l’espace de travail **Gestion des fonctionnalités**, reportez-vous à la rubrique [Reconnaissance entre un règlement comptable et la clôture de fin d’exercice](awareness-between-ledger-settlement-year-end-close.md).

## <a name="set-up-ledger-settlement"></a>Paramétrer le règlement comptable
Vous devez sélectionner les comptes principaux pour lesquels vous souhaitez effectuer le règlement comptable. Il existe deux manières de sélectionner ces comptes principaux.

1. Accédez à **Comptabilité** > **Paramétrage de la comptabilité** > **Paramètres de comptabilité**.
2. Sur l’onglet **Règlements comptables**, sélectionnez les plans comptables dont vous souhaitez sélectionner les comptes principaux.
3. Sélectionnez les comptes principaux pour lesquels effectuer le règlement comptable. Puisque les plans comptables sont globaux, toutes les sociétés pour lesquelles les plans comptables sont attribués auront les mêmes comptes principaux sélectionnés pour le règlement comptable.

  - ou -

1. Accédez à **Comptabilité** > **Tâches périodiques** > **Règlements comptables**.
2. Sélectionnez **Comptes de règlement comptable**.
3. Dans la boîte de dialogue, sélectionnez les plans comptables et les comptes principaux pour lesquels effectuer le règlement comptable. Cette boîte de dialogue est un raccourci. Tous les comptes principaux que vous ajoutez ici apparaîtront également sur la page **Paramètres comptables**.

Vous pouvez utiliser les mêmes procédures de base pour supprimer à tout moment les comptes principaux du règlement comptable. La suppression d’un compte principal n’a aucun effet sur les règlements comptables précédents. Cependant, le compte principal et les transactions n’apparaîtront plus sur la page **Règlement comptable**.

## <a name="settle-transactions"></a><a name="settle-transactions"></a>Régler les transactions
Pour régler des écritures comptables, procédez comme suit.

1. Accédez à **Comptabilité** > **Tâches périodiques** > **Règlements comptables**.
2. Définissez les filtres situés en haut de la page :

    - Sélecitonnez une plage de dates. Sinon, sélectionnez un code intervalle de dates pour renseigner automatiquement la plage de dates. Nous vous déconseillons d’effectuer un règlement comptable pour les transactions qui s’étendent sur plusieurs exercices.
    - Modifiez la couche de validation au besoin. Vous ne pouvez pas régler des transactions qui se trouvent dans différentes couches de validation.
    - Pour afficher le compte principal et les dimensions séparément, sélectionnez un ensemble de dimensions financières.

3. Sélectionnez **Afficher les transactions** pour afficher toutes les transactions qui correspondent aux filtres que vous avez définis et la liste des comptes que vous avez spécifiés lorsque du paramétrage la liste du plan de comptes dans la section précédente.

    - Si vous modifiez l’un des filtres ou des ensembles de dimensions, vous devez sélectionner **Afficher les transactions** de nouveau.
    - Pour filtrer les transactions vers un compte principal individuel, utilisez le filtre sur le champ **Compte général**. Nous vous déconseillons d’effectuer un règlement comptable pour les transactions qui sont validées sur différents comptes principaux.

4. Sélectionnez les lignes pour règlement. La valeur du champ **Montant sélectionné** en haut de la page augmente ou diminue pour indiquer le montant total des lignes sélectionnées.
5. Après avoir terminé la sélection des transactions, sélectionnez **Marquer sélectionnée**. Pour chaque transaction sélectionnée, une coche apparaît dans la colonne **Marquée**. En outre, la valeur du champ **Montant marqué** en haut de la grille augmente ou diminue pour indiquer le montant total des lignes marquées.
6. Lorsque la valeur **Montant marqué** est de **0** (zéro), sélectionnez **Régler les transactions marquées**. Le statut des transactions marquées est mis à jour sur **Réglée**.

    > [!IMPORTANT]
    > Toutes les transactions que vous avez marquées pour règlement pour l’entité juridique active seront réglées, même si elles ne sont pas actuellement affichées sur la page de règlement comptable parce que vous avez appliqué un filtre.

## <a name="make-transactions-easier-to-find"></a>Simplifier la recherche des transactions
La page **Règlements comptables** inclut des capacités qui facilitent l’affichage des transactions dont vous avez besoin pour le règlement.

- Utilisez le filtre **Marquée** permet de filtrer les transactions selon que la coche **Marquée** pour elles est activée ou non.
- Utilisez le filtre **Statut** filter pour filtrer les transactions en fonction de leur statut.
- Sélectionnez **Trier par montant absolu** pour trier les montants par valeur absolue. De cette façon, vous pouvez regrouper les débits et les crédits qui ont le même montant.

## <a name="reverse-a-settlement"></a>Contrepasser un règlement
Vous pouvez contrepasser un règlement effectué par erreur.

1. Suivez les étapes 1 à 3 de la rubrique [Régler les transactions](#settle-transactions) pour afficher les transactions qui vous intéressent.
2. Dans le filtre **Statut**, sélectionnez **Réglée**.
3. Sélectionnez les lignes pour contrepassation.
4. Sélectionnez **Contrepasser les transactions marquées**. Le statut de toutes les transactions qui ont le même ID de règlement est mis à jour pour **Non réglée**.

    > [!IMPORTANT]
    > Toutes les transactions qui ont le même ID de règlement seront contrepassées, même si elles ne sont pas marquées. Par exemple, quatre lignes ont été marquées et réglées. Les quatre lignes ont le même identifiant de règlement. Si vous marquez l’une de ces quatre lignes, puis sélectionnez **Contrepasser les transactions marquées**, les quatre lignes seront contrepassées.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
