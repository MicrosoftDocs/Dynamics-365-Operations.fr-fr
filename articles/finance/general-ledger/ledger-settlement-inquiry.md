---
title: Recherche de règlement comptable
description: Cet article décrit la fenêtre de consultation de règlement comptable
author: kweekley
ms.date: 12/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33ae49d9503c0a83bda7e0093ab6ef69fb4aef0a
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853126"
---
# <a name="ledger-settlement-inquiry"></a>Recherche de règlement comptable

[!include [banner](../includes/banner.md)]

Cet article décrit la fenêtre **Recherche de règlement comptable** qui peut être utilisée pour afficher les transactions comptables réglées, non réglées ou à la fois réglées et non réglées pour une période fiscale.

## <a name="view-ledger-settlement-transactions"></a>Affichage des transactions de règlement comptable
1.  Accédez à **Comptabilité générale > Recherches et états > Recherche de règlement comptable**.
2.  Utilisez les champs **Date de début** et **Date de fin** ou **Intervalle de dates** pour spécifier une plage de dates. Comme pour la balance de vérification, la plage de dates doit être comprise dans un seul exercice.
3.  Dans le champ **Comptes principaux**, sélectionnez un ou plusieurs comptes principaux pour lesquels afficher les transactions du grand livre. La liste déroulante affiche uniquement les comptes principaux configurés pour le règlement comptable sur la page **Paramètres comptable**.
4.  Utilisez le champ **Ensemble de dimensions financières** pour afficher les dimensions financières dans la grille. Étant donné que le compte principal est obligatoire, la valeur du champ **Compte principal** sera toujours affichée dans la première colonne, même si vous sélectionnez un ensemble de dimensions financières qui n’inclut pas le compte principal.
5.  Dans le champ **Statut**, sélectionnez :
-   **Tous** pour afficher les transactions réglées et non réglées
-   **Non réglé** pour afficher uniquement les transactions non réglées 
-   **Réglé** pour afficher uniquement les transactions réglées
6.  Sélectionnez **Affichage les transactions**. Les transactions comptables apparaissent dans la grille, en fonction des critères que vous avez saisis. Vous pouvez exporter les résultats de la recherche vers Microsoft Excel aux fins d’analyse supplémentaire. Cliquez et maintenez sélectionné ou cliquez avec le bouton droit sur la grille.

### <a name="column-details"></a>Détails de la colonne
La grille de la page **Demande de règlement comptable** comprend les colonnes suivantes :
-   **Compte principal** – Ce champ est obligatoire et est toujours affiché.
-   **Dimensions financières** – Les dimensions financières sont affichées en fonction de l’ensemble de dimensions financières sélectionné.
-   **Date de transaction** – Date de validation de la transaction comptable.
-   **Date de transaction d’origine** – Si la clôture de fin d’année a été exécutée et que le règlement comptable est configuré de manière à conserver les détails d’un compte principal, les transactions non réglées sont transférées en détail en tant que solde d’ouverture. La date de publication d’origine de la transaction comptable est conservée dans le champ **Date de transaction d’origine**.
-   **Âge de la transaction** – La valeur est 0 (zéro) pour toutes les transactions réglées. Pour les transactions non réglées, la valeur est calculée comme le nombre de jours entre la date de transaction d’origine ou la date de transaction et la date d’exécution de la recherche.
Par exemple, une transaction comptable a une date de transaction du 1er janvier 2022 (1/1/2022) et une date de transaction d’origine du 30 décembre 2021 (12/30/2021). Si l’enquête est exécutée le 2 janvier 2022 (1/2/2022) pour l’exercice 2022, la **Valeur de l’âge de la transaction** sera 4. Cette valeur est calculée comme le nombre de jours entre la date de transaction d’origine (30/12/2021) et le 02/01/2022.

S’il n’y a pas de date de transaction d’origine, la date de transaction est utilisée à la place.
-   **(Autres informations sur les transactions)** – Des colonnes supplémentaires affichent des informations telles que le numéro du bon, la description et les montants de débit et de crédit dans les trois devises (transaction, comptabilité et rapport).
-   **Statut** – Cette valeur est soit **Réglée** ou **Non réglée**.
-   **ID règlement** – ID unique affecté aux transactions réglées.

[![Page Recherche de règlement comptable](./media/Inquiry1.png)](./media/Inquiry1.png)

 
Les totaux peuvent être affichés sous la grille.
1.  Sélectionnez les points de suspension (…) à droite de la grille, puis sélectionnez **Afficher le pied de page**.
2.  Sélectionnez et maintenez sélectionné sur chaque colonne de montant, puis sélectionnez **Regrouper selon la colonne** pour afficher les totaux. Les totaux sont affichés dans le pied de page. Si la demande est filtrée de sorte qu’elle n’affiche que les transactions non réglées, vous pouvez utiliser les totaux pour rapprocher les montants avec la balance comptable.







