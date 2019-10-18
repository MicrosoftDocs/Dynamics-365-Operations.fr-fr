---
title: Règlements comptables
description: Cette rubrique explique comment utiliser la page Règlements comptables pour régler des écritures comptables et contrepasser des règlements.
author: mikefalkner
manager: aolson
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransSettlement
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-11-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 01764db27eb7061deeddc01997f16a43f9cb00c6
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186438"
---
# <a name="ledger-settlements"></a>Règlements comptables

[!include [banner](../includes/banner.md)]

Les règlements comptables vous permettent de mettre en correspondance les transactions de débit et de crédit dans la comptabilité, et de les marquer comme réglés. De cette manière, vous pouvez vous assurer que les transactions associées ont été effacées. Vous pouvez également contrepasser les règlements si ils ont été effectuer par erreur.

## <a name="enable-advanced-ledger-settlements"></a>Activer les règlements comptables avancés

La page Règlements comptables avancés fournit des fonctionnalités supplémentaires pour le filtrage et la sélection de transactions. Pour activer la page Règlements comptables avancés, procédez comme suit.

1. Sélectionnez **Comptabilité** \> **Paramétrage de la comptabilité** \> **Paramètres de comptabilité**. 
2. Sous l'onglet **Règlements comptables**, définissez l'option **Règlement comptable avancés** sur **Oui** pour activer la fonctionnalité de règlement comptable avancé. La page **Règlements comptables** avancés est utilisée lorsque vous sélectionnez **Règlements comptables** dans **Tâches périodiques**. 
3. Vous devez entrer la liste des comptes à utiliser pour les règlements comptables pour chaque plan de comptes. Cette liste est utilisée pour filtrer la liste des transactions qui apparaît sur la page **Règlements comptables**. Dans la liste **Plan de comptes**, sélectionnez un plan de comptes, puis sélectionnez **Nouveau** pour ajouter de nouveaux comptes à la liste.

## <a name="settle-transactions-by-using-the-advanced-ledger-settlements-page"></a>Régler les transactions à l'aide de la page de règlements comptables avancés

Pour régler des écritures comptables, procédez comme suit.

1. Sélectionnez **Comptabilité** \> **Tâches périodiques** \> **Règlements comptables**.
2. Définissez les filtres situés en haut de la page :

    - Sélectionnez une plage de dates ou sélectionnez **Code intervalle de dates** pour renseigner automatiquement la plage de dates.
    - Modifiez la couche de validation au besoin.
    - Pour afficher le compte général et les dimensions séparément, sélectionnez un ensemble de dimensions financières.

3. Sélectionnez **Afficher les transactions** pour afficher toutes les transactions qui correspondent aux filtres que vous avez définis et la liste des comptes que vous avez spécifiés lorsque du paramétrage la liste du plan de comptes dans la section précédente. Si vous modifiez l'un des filtres ou des ensembles de dimensions, vous devez sélectionner **Afficher les transactions** de nouveau.
4. Sélectionnez une ou plusieurs lignes que vous prenez en compte pour le règlement. La valeur du champ **Montant sélectionné** en haut de la page augmente ou diminue en fonction du montant total des lignes sélectionnées.
5. Après avoir terminé la sélection des transactions, sélectionnez **Marquer sélectionnée**. Une coche apparaît dans la colonne **Marquée** pour chaque transaction sélectionnée. En outre, la valeur du champ **Montant marqué** en haut de la grille augmente ou diminue en fonction du montant total des lignes marquées.
6. Lorsque la valeur **Montant marqué** est de **0** (zéro), sélectionnez **Régler les transactions marquées**. Le statut des transactions marquées est mis à jour sur **Réglée**.

## <a name="make-transactions-easier-to-find"></a>Simplifier la recherche des transactions

La page **Règlements comptables** inclut des capacités qui facilitent l'affichage des transactions dont vous avez besoin pour le règlement.

- Le bouton **Supprimer le marquage de la sélection** efface le champ **Marquée** pour toutes les lignes sélectionnées.
- Le filtre **Marquée** permet de filtrer les transactions selon que le champ **Marquée** pour elles est activé ou désactivé.
- Le filtre **Statut** vous permet de filtrer les transactions selon que leur statut est **Réglée** ou **Non réglée**.
- Le bouton **Trier par montant absolu** vous permet de trier les montants par valeur absolue, afin de regrouper les débits et les crédits ayant le même montant.

## <a name="reverse-a-settlement"></a>Contrepasser un règlement

Vous pouvez contrepasser un règlement effectué par erreur.

1. Suivez les étapes 1 à 3 de la section « Régler les transactions à l'aide de la page de règlements comptables avancés » pour afficher les transactions que vous recherchez.
2. Dans le filtre **Statut**, sélectionnez **Réglée**.
3. Sélectionnez une ou plusieurs lignes que vous prenez en compte pour la contrepassation. La valeur du champ **Montant sélectionné** en haut de la page augmente ou diminue en fonction du montant total des lignes sélectionnées.
4. Après avoir terminé la sélection des transactions, sélectionnez **Marquer sélectionnée**. Une coche apparaît dans la colonne **Marquée** pour chaque transaction sélectionnée. En outre, la valeur du champ **Montant marqué** en haut de la page augmente ou diminue en fonction du montant total des lignes marquées.
5. Lorsque la valeur **Montant marqué** est de **0** (zéro), sélectionnez **Contrepasser les transactions marquées**. Le statut des transactions marquées est mis à jour sur **Non réglée**.

## <a name="update-the-list-of-accounts-that-are-included-in-the-list-of-transactions"></a>Mettre à jour la liste des comptes inclus dans la liste des transactions

Sélectionnez **Comptes de règlement comptable** pour ouvrir une boîte de dialogue dans laquelle vous pouvez modifier les comptes inclus dans la liste des transactions. Sélectionnez **Nouveau** pour ajouter de nouveaux comptes à la liste. Cette liste est utilisée pour filtrer la liste des transactions qui apparaît sur la page **Règlements comptables**.
