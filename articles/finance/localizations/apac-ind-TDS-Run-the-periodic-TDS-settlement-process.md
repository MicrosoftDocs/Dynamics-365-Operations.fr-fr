---
title: Exécuter le processus de règlement TDS périodique
description: Cette rubrique explique comment régler la taxe déduite à la source (TDS) périodique.
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
ms.openlocfilehash: 6c0aca4d0a916b21ca5ac6ee14e6ab658e0bae26
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726432"
---
# <a name="run-the-periodic-tds-settlement-process"></a>Exécuter le processus de règlement TDS périodique

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment régler la taxe déduite à la source (TDS) périodique.

1. Accédez à **Taxe \> Déclarations \> Retenue à la source \> Paiement de la retenue à la source**.

    [![Boîte de dialogue Paiement de retenue à la source.](./media/apac-ind-TDS-47.png)](./media/apac-ind-TDS-47.png)

2. Dans la boîte de dialogue **Paiement de la retenue à la source**, dans le champ **Type de taxe**, sélectionnez **TDS**.
3. Dans le **Numéro de compte fiscal (TAN)**, sélectionnez le numéro de compte de taxe (TAN) pour lequel exécuter le processus de règlement.
4. Dans le champ **Groupe de composants de retenue à la source**, sélectionnez le groupe de composants TDS pour lequel exécuter le processus de règlement.
5. Dans le champ **Période de règlement**, sélectionnez la période de règlement TDS pour laquelle le processus de règlement TDS est exécuté.

    > [!NOTE]
    > Le processus de règlement TDS est exécuté pour toutes les périodes configurées pour la période de règlement TDS dans l'onglet **Périodes** de la page **Périodes de règlement de la retenue à la source** (**Impôt \> Impôts indirects \> Retenue à la source \> Périodes de règlement de la retenue à la source**).

6. Dans le champ **Date de début**, sélectionnez la date de début à partir de laquelle exécuter le processus de règlement TDS.

    Pour une période spécifique de la période de décompte, la date de début définie pour la période est considérée comme la date de début. Par exemple, la période de règlement TDS comprend deux périodes : du 1er avril au 30 avril 2009 et du 1er mai au 31 mai 2009. Si vous sélectionnez **04/06/2009** (6 avril 2009) comme date de début du champ **Date de début**, le processus de règlement se déroulera toujours à partir du 1er avril 2009.

    Si vous saisissez une période ultérieure dans le champ **Date de début**, mais sans régler une période précédente dans la période de règlement, le règlement ne se produira pas pour les périodes précédentes. Par exemple, la période de règlement TDS comprend trois périodes : du 1er avril au 30 avril 2009, du 1er mai au 31 mai 2009 et du 1er juin au 30 juin 2009. Si vous sélectionnez **05/01/2009** (1er mai 2009) comme date de début du champ **Date de début**, le processus de règlement ne se déroulera que du 1er mai au 31 mai 2009. Le règlement n'aura pas lieu du 1er avril au 30 avril 2009.

7. Dans le champ **Date de transaction**, sélectionnez la date de début à partir de laquelle valider le processus de règlement TDS.
8. Dans le champ **Paiement de la retenue à la source**, sélectionnez la version Règlement TDS :

     - **Original** - Utilisez cette option pour exécuter le processus de règlement TDS pour la première fois. La version de paiement d'origine n'est utilisée qu'une seule fois pour exécuter le processus de règlement TDS pour une combinaison d'un TAN, d'un groupe de composants de retenue à la source et d'une période de décompte de retenue à la source.
    - **Dernières versions** - Utilisez cette option si le processus de règlement TDS a déjà été exécuté pendant la période spécifiée. Incluez les transactions antidatées qui ont été validées après l'exécution du processus de règlement pour la période. Vous pouvez utiliser cette option pour exécuter le processus de règlement un nombre illimité de fois.

9. Cochez la case **Mettre à jour** pour exécuter le processus de règlement TDS et enregistrer les montants dans les comptes du compte général. Si cette case à cocher est désactivée, le processus de règlement ne sera pas exécuté et les écritures financières ne seront pas générées.
10. Sélectionnez **OK** pour exécuter le processus de règlement TDS et générer le rapport de paiement de la retenue à la source. Le statut des transactions TDS incluses dans le processus de règlement est indiqué sous la mention **Réglé** dans la page **Règlement** (accédez à **Comptabilité fournisseur \> Paiements \> Journal des paiements fournisseur**, sélectionnez **Lignes**, sélectionnez **Fonctions**, puis **Règlement**).

### <a name="important-points"></a>Les points importants

- Si un groupe de composants de retenue à la source n'est pas sélectionné pendant le processus de règlement, le décompte se produit pour tous les groupes de composants de retenue à la source pour le TAN et la période de décompte sélectionnés. Une ligne distincte est créée pour chaque groupe de composants de retenue à la source sur la page **Édition d'une transaction en cours**.
- Le processus de règlement est basé sur la nature de la catégorie des personnes évaluées pour une période de règlement. Transactions dans lesquelles la nature de la catégorie des personnes évaluées est **Société** sont réglés et sont affichés comme une ligne sur la page **Édition d'une transaction en cours**. Transactions dans lesquelles la nature de la catégorie des personnes évaluées est différente de **Société** sont réglés et sont affichés comme une ligne sur la page **Édition d'une transaction en cours**.
- La date d'échéance des lignes de transaction TDS réglées sur la page **Édition d'une transaction en cours** est basée sur les conditions de paiement définies pour le fournisseur de l'autorité TDS sur la page **Fournisseurs**. Si les conditions de paiement ne sont pas définies pour le fournisseur de l'autorité TDS, le dernier jour de la période de règlement est affiché comme date d'échéance.
