---
title: Page d'accueil de la comptabilité fournisseur
description: Cette rubrique fournit une vue d'ensemble de la comptabilité fournisseur.
author: ShylaThompson
manager: AnnBe
ms.date: 02/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 21901
ms.assetid: 1e4c2ac4-077b-4678-8733-5cec8f6ff659
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 39187cf900624c5fbc7e811f0ee9632355688ba4
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1507471"
---
# <a name="accounts-payable-home-page"></a>Page d'accueil de la comptabilité fournisseur

[!include [banner](../includes/banner.md)]

Cette rubrique fournit une vue d'ensemble de la comptabilité fournisseur. 

Vous pouvez entrer des factures fournisseur manuellement ou les recevoir par voie électronique via une entité de données. Une fois les factures entrées ou reçues, vous pouvez les réviser et les approuver en utilisant un journal d'approbation des factures ou l'écran **Facture fournisseur**. Vous pouvez utiliser le rapprochement des factures, les stratégies relatives aux factures fournisseur et le workflow pour automatiser le processus de révision afin que les factures qui répondent à certains critères soient automatiquement approuvées et que les autres soient marquées pour révision par un utilisateur autorisé.

**Processus d'entreprise**

[![Processus d'entreprise](./media/AP-process.PNG)](./media/AP-process.PNG)

## <a name="set-up-accounts-payable"></a>Paramétrer la comptabilité fournisseur

Paramétrez des groupes de fournisseurs, des fournisseurs, des profils de validation, différentes options de paiement, des paramètres concernant les fournisseurs, des frais, des livraisons et des destinations, des billets à ordre, ainsi que d'autres types d'informations relatives à la comptabilité fournisseur. 

[Configuration du module Comptabilité fournisseur](accounts-payable-overview.md)

[Répartitions comptables et écritures de journal de comptabilité auxiliaire pour les factures fournisseur](accounting-distributions-subledger-journal-entries-vendor-invoices.md) 

[Réévaluation des comptes en devises pour la comptabilité fournisseur et la comptabilité client](../cash-bank-management/foreign-currency-revaluation-accounts-payable-accounts-receivable.md)

## <a name="configure-vendor-invoices"></a>Configurer les factures fournisseur

La Comptabilité fournisseur permet de suivre les factures et les dépenses sortantes à destination des fournisseurs.

[Rapprochement des factures dans le module Comptabilité fournisseur](accounts-payable-invoice-matching.md)

[Profils de validation fournisseur](vendor-posting-profiles.md)

[Paramétrer la validation du rapprochement de factures de la comptabilité fournisseur](tasks/set-up-accounts-payable-invoice-matching-validation.md).

[Stratégies de rapprochement à trois facteurs](three-way-matching-policies.md)

[Rapprochement de factures et des commandes fournisseur intersociétés](invoice-matching-intercompany-purchase-orders.md)

[Résolution des écarts lors du rapprochement des totaux de factures](resolve-invoice-totals-invoice-matching-discrepancies.md)

[Comptes de contrepartie par défaut pour les journaux de facture fournisseur et les journaux d'approbation de facture](default-offset-accounts-vendor-invoice-journals.md)

[Approbations de factures par téléphone portable](mobile-invoice-approvals.md)

[Espace de travail de facturation de collaboration fournisseur](vendor-portal-invoicing-workspace.md)

[Automatisation des factures fournisseur](vendor-invoice-automation.md)

## <a name="configure-vendor-payments"></a>Configurer les paiements fournisseur 

Affectez un type de paiement défini par le système, tel que par chèque, paiement électronique ou billet à ordre, pour tout mode de paiement défini par l'utilisateur. Les types de paiements sont facultatifs mais utiles lorsque vous validez des paiements électroniques et souhaitez déterminer rapidement quel type de paiement est utilisé. 

[Espace de travail des paiements fournisseur](vendor-payments-workspace.md)

[Définir les commissions de paiement fournisseur](tasks/define-vendor-payment-fees.md)

[Définir les conditions de paiement fournisseur](tasks/define-vendor-payment-terms.md)

[Vue d'ensemble des paiements positifs](positive-pay-overview.md)

[Paramétrer et générer des fichiers de paiement positif](set-up-generate-positive-pay-files.md)

[Création de paiements fournisseur via une proposition de paiement](create-vendor-payments-payment-proposal.md)

[Paiements fournisseur pour un montant partiel](vendor-payments-partial-amount.md)

[Utilisation d'une remise supérieure à la remise calculée pour un paiement fournisseur](take-discount-more-calculated-discount-vendor-payment.md)

[Prélever un escompte de règlement en dehors de la période d'escompte de règlement](take-cash-discount-outside-cash-discount-timeframe.md)

[Gestion des états électroniques pour les chèques fournisseur](electronic-reporting-sample-vendor-checks.md)

[Contrepasser un paiement fournisseur](reverse-vendor-payment.md)

[Vue d'ensemble des acomptes et des factures d’acompte](prepayments-invoices-vs-prepayments.md)

[Paiements centralisés de la comptabilité fournisseur](centralized-payments-accounts-payable.md)

## <a name="settlements"></a>Règlements

Les rubriques suivantes fournissent des informations sur les règlements. Le règlement est le processus consistant à régler des paiements avec des factures. 

[Configurer un règlement](../cash-bank-management/configure-settlement.md)

[Régler un paiement partiel fournisseur avant la date d'escompte](settle-partial-vendor-payment-before-discount-or-final-payment-after.md)

[Régler un paiement partiel fournisseur ayant des remises sur les avoirs fournisseur](settle-partial-vendor-payment-discounts-vendor-credit-notes.md)

[Règlement d'un paiement fournisseur partiel avec plusieurs périodes de remise](settle-partial-vendor-payment-multiple-discount-periods.md)

[Régler un paiement fournisseur partiel ou final avant l'escompte](settle-partial-vendor-payment-or-final-payment-before-discount.md)

[N° de document unique avec plusieurs enregistrements client ou fournisseur](single-voucher-multiple-customer-vendor-records.md)



### <a name="additional-resources"></a>Ressources supplémentaires

#### <a name="whats-new-and-in-development"></a>Nouveautés et développements

Accédez au [Notes de publication de Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?linkid=2010158) pour découvrir les nouvelles fonctions qui sont en cours de développement. 

#### <a name="blogs"></a>Blogs

Vous trouverez des avis, des actualités et d'autres informations concernant la Comptabilité fournisseur et d'autres solutions sur le blog de [Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise)et le blog de [Microsoft Dynamics 365 Finance and Operations - Financials](https://community.dynamics.com/365/financeandoperations/b/financials).

Le [blog de la communauté de partenaires Microsoft Dynamics Operations](https://community.dynamics.com/partner/b/operationspartnercommunityblog) offre aux partenaires de Microsoft Dynamics une ressource unique pour découvrir les nouveautés et les tendances de MBS Operations.

#### <a name="community-blogs"></a>Blogs de la communauté

[Procédure de gestion des achats dans Dynamics 365 for Finance and Operations](https://financefunction.tech/2019/02/15/how-to-manage-payables-in-dynamics-365-for-finance-and-operations)

#### <a name="task-guides"></a>Guides de tâches
Une aide supplémentaire est disponible sous forme de guides de tâche dans Finance and Operations. Pour accéder aux guides de tâche, cliquez sur le bouton Aide de n'importe quelle page.

#### <a name="videos"></a>Vidéos

Consultez les vidéos de procédure qui sont désormais disponibles sur la [chaîne YouTube Microsoft Dynamics 365](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).




