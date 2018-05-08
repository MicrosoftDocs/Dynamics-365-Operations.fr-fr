---
title: Espace de travail des paiements fournisseur
description: "Cette rubrique fournit des informations sur l'espace de travail Paiements fournisseur. L'espace de travail Paiements fournisseur affiche les informations associées au traitement des paiements fournisseur."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendPaymentWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.assetid: 
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: cb5a674472936a52b624c548fd37079d57eb6cb7
ms.openlocfilehash: fa8ddf52d34c3662e120509156ab0b343bb4cc16
ms.contentlocale: fr-fr
ms.lasthandoff: 12/14/2017

---

# <a name="vendor-payments-workspace"></a>Espace de travail des paiements fournisseur

[!include [banner](../includes/banner.md)]

L'espace de travail **Paiements fournisseur** affiche les informations associées au traitement des paiements fournisseur. Cet espace de travail contient une vue **Mon travail** et une page **Analyses**. La vue **Mon travail** affiche les vignettes récapitulatives, les grilles de transaction fournisseur et les informations fournisseur associées. La page **Analyses** utilise les fonctionnalités de Microsoft Power BI pour afficher les éléments visuels associés aux paiements fournisseur.

## <a name="my-work-view"></a>Vue Mon travail

### <a name="summary-tiles"></a>Vignettes récapitulatives

Les vignettes de la section **Synthèse** donnent une vue d'ensemble de l'état de vos informations de paiement. Vous pouvez afficher les journaux des paiements qui ne sont pas encore validés, les factures en retard, tous les fournisseurs et les fournisseurs en attente. Dans la section **Synthèse**, vous pouvez créer un cycle de paie.

Les informations de la section **Synthèse** concernent la société à laquelle vous êtes connecté.

### <a name="vendor-transactions-grids"></a>Grille des transactions fournisseur

La section **Transactions fournisseur** contient des grilles qui affichent les factures en retard et les paiements non réglés. Dans la grille **Factures en retard**, vous pouvez afficher l'historique des règlements pour une facture sélectionnée. Dans la grille **Paiements non réglés**, vous pouvez afficher l'historique des règlements pour une facture sélectionnée et régler une facture.

Les commis aux paiements centralisés peuvent utiliser le filtre qui apparaît en haut de chaque grille pour sélectionner une société. La grille est ensuite filtrée pour afficher uniquement les sociétés définies dans la hiérarchie organisationnelle des paiements centralisés que le commis aux paiements centralisés est autorisé à visualiser.

L'onglet **Rechercher les transactions** dans la section **Transactions fournisseur** vous permet de rechercher une transaction fournisseur.

### <a name="related-information"></a>Informations associées

Vous pouvez afficher l'état **Fournisseur âgé** et l'état **Synthèse des paiements par date** à l'aide des liens de la section **Informations associées** de l'espace de travail.

## <a name="analytics-page"></a>Page Analyses

La page **Analyses** fournit des mesures importantes, telles que les factures fournisseur en retard et les factures fournisseur à échéance future. Cette page contient neuf pages d'état. Une page donne une vue d'ensemble, et les huit autres pages fournissent des détails sur les mesures de paiement de la comptabilité fournisseur.

Le tableau suivant indique les visualisations qui sont disponibles sur chaque page d'état.


|            Page d'état            |                                                                                                                                                                                Visualisation                                                                                                                                                                                |
|-----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     Présentation des paiements fournisseurs      | <ul><li>Factures en retard</li><li>Factures échues aujourd'hui</li><li>Remises appliquées et remises perdues</li><li>Factures à échéance future par date d'escompte de règlement</li><li>Factures à échéance future par date d'échéance</li><li>Factures payées en retard et factures payées à temps</li><li>Affectation de workflow de paiement</li><li>Solde fournisseur et client</li><li>Factures en cours avec mise en attente du paiement</li></ul> |
|         Factures en retard         |                                                                                             <ul><li>Factures en retard</li><li>Détails des factures en retard</li><li>Total des factures en cours</li><li>Factures en retard par groupe de fournisseurs</li><li>Factures en retard par société</li></ul>                                                                                              |
|        Factures échues aujourd'hui         |                                                                                                         <ul><li>Factures échues aujourd'hui</li><li>Détails des factures échues aujourd'hui</li><li>Factures échues aujourd'hui par société</li><li>Factures échues aujourd'hui par groupe de fournisseurs</li></ul>                                                                                                          |
| Remises appliquées et remises perdues |                                                                             <ul><li>Remises appliquées et remises perdues</li><li>Détails des remises appliquées et remises perdues</li><li>Détails des remises appliquées et remises perdues par société</li><li>Détails des remises appliquées et remises perdues par groupe de fournisseurs</li></ul>                                                                              |
|      Factures à échéance future       |                                                 <ul><li>Factures à échéance future</li><li>Détails des factures à échéance future</li><li>Factures à échéance future par société</li><li>Factures à échéance future par groupe de fournisseurs</li><li>Factures à échéance future par date d'escompte de règlement</li><li>Factures à échéance future par date d'échéance</li></ul>                                                  |
|        Factures payées en retard         |                                                         <ul><li>Factures payées après la date d'échéance</li><li>Détails des factures payées après la date d'échéance</li><li>Factures payées après la date d'échéance par société</li><li>Factures payées après la date d'échéance par groupe de sociétés</li><li>Factures payées en retard et factures payées à temps</li></ul>                                                          |
|         Workflow de paiement          |                                                                                <ul><li>Instances de workflow de paiement fournisseur</li><li>Instances de workflow de paiement fournisseur par approbateur</li><li>Instances de workflow de paiement fournisseur par société</li><li>Nombre moyen de jours dans le workflow par approbateur</li></ul>                                                                                |
|    Solde fournisseur et client     |                                                                                                                   <ul><li>Solde fournisseur et client</li><li>Solde fournisseur et client par société</li><li>Détails du solde fournisseur et client</li></ul>                                                                                                                    |
|    Factures avec mise en attente du paiement     |                                                                                         <ul><li>Factures avec mise en attente du paiement</li><li>Détails des factures avec mise en attente du paiement</li><li>Factures avec mise en attente du paiement par société</li><li>Factures avec mise en attente du paiement par groupe de fournisseurs</li></ul>                                                                                          |


