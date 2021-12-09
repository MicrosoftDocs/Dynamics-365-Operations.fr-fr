---
title: Vue d’ensemble de la comptabilité fournisseur (Secteur public)
description: Cet article présente la fonctionnalité de Comptabilité fournisseur dans le secteur public qui est intégrée à Microsoft Dynamics 365 Finance. Cette fonctionnalité pour les entités du secteur public concerne les capacités de gestion des fournisseurs, d’achat et de génération d’états.
author: v-kiarnd
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetParameters, CustParameters, LedgerJournalTable, OMLegalEntity, PurchAgreementListPage, PurchTableListPage, SrmParameters, VendCertificationType, VendCoverPageLayout, VendOpenInvoicesListPage, VendParametersVendParameters, VendTableListPage
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "19661"
- intro-internal
ms.assetid: b4c903dd-5ec7-4ec5-9dc9-77ba4f00fab8
ms.search.region: Global
ms.search.industry: Public sector
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7f36d9cf7ccb84c72c0bd1c73469590d739eab5d
ms.sourcegitcommit: 52a6b038d42ab28092bb942c61f5196330db3a7b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2021
ms.locfileid: "7817714"
---
# <a name="accounts-payable-in-the-public-sector-overview"></a>Vue d’ensemble de la comptabilité fournisseur (Secteur public)

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la fonctionnalité Secteur public dans le secteur public qui est intégrée à Dynamics 365 Finance. Cette fonctionnalité inclut des codes commande fournisseur, des définitions de validation, la facturation à un fournisseur occasionnel, les formulaires fiscaux 1099, les escomptes de règlement, les types de certification de fournisseur, la synthèse des activités comptables du projet, les paiements électroniques, les pages de garde et de signature des états, les montants des lignes de commande fournisseur, et les pages du journal des factures fournisseur. 

## <a name="what-are-the-prerequisites-for-setting-up-accounts-payable-in-the-public-sector"></a>Quelles sont les conditions préalables au paramétrage de la comptabilité fournisseur dans le secteur public ?

Avant de commencer à ajuster les paramètres et à entrer vos données, vous devez effectuer les tâches suivantes :

-   Paramétrer les fournisseurs.
-   Paramétrer les systèmes de numérotation pour les fournisseurs, les commandes fournisseur, etc.
-   Décider quels codes et messages de commande fournisseur (PO) seront utilisés.

Après avoir paramétré les conditions préalables, vous devez paramétrer les fonctionnalités suivantes de la comptabilité fournisseur :

- [Codes de commandes fournisseur dans le secteur public](purchase-order-codes-public-sector.md) – Vous pouvez créer des codes et des messages spéciaux pour la confirmation des commandes fournisseur. Une commande fournisseur de confirmation contourne le processus d’achat habituel. Par exemple, vous autorisez une commande non planifiée par l’intermédiaire d’un numéro de commande fournisseur au moment d’un achat, plutôt que via un document qui est fourni avant que l’article soit requis. 
  > [!NOTE]
  > Cela s’applique également à l’approvisionnement.

- [Définitions de validation dans le secteur public](posting-definitions-public-sector.md) – Les définitions permettent de créer les lignes du journal de comptabilité auxiliaire pour les transactions d’origine correspondant aux critères sélectionnés. Par exemple, les définitions de validation vous permettent de générer plusieurs écritures comptables équilibrées en fonction d’attributs tels que les types de transactions et les comptes. 
  > [!NOTE]
  > Cela s’applique également à la comptabilité, à la budgétisation et à la comptabilité client.


- [Fournisseurs occasionnels dans le secteur public](one-time-vendors-public-sector.md) – Lorsqu’une approbation ou un contrat sous forme d’une commande fournisseur n’est pas nécessaire, vous pouvez rapidement créer une ou plusieurs factures tout en créant un enregistrement pour le fournisseur. Pour plus d’informations, voir [Plan pour les fournisseurs occasionnels dans le secteur public](plan-one-time-vendors-public-sector.md).
- Vue d’ensemble du formulaire de déclaration des honoraires dans le secteur public – Si vous entretenez des relations commerciales avec des fournisseurs américains assujettis à la taxe sur les honoraires, vous devez effectuer le suivi du montant réglé à chaque fournisseur et le déclarer à la fin de l’année civile. Les organisations du secteur public utilisent les formulaires 1099-G et 1099-S.

> [!NOTE]
> Cela s’applique également à l’approvisionnement.

## <a name="additional-public-sector-functionality"></a>Fonctionnalité Secteur public supplémentaire
Les sections restantes de cet article décrivent la fonctionnalité Comptabilité fournisseur disponible pour le secteur public.

-   **Escomptes de règlement** – Permet de sélectionner le compte sur lequel effectuer la compensation lorsque les escomptes de règlement sont appliqués aux factures.
-   **Type de certification du fournisseur** – Permet de définir un type de certification pour toute condition requise du fournisseur dont vous souhaitez effectuer le suivi.
-   **Synthèse des activités de contrat d’achat** – Permet d’entrer les détails récapitulatifs pour les activités associées à un contrat d’achat.
-   **Paiements électroniques** – Permet de spécifier les paiements électroniques aux fournisseurs. 
-   **Pages de couverture et de signature pour les états de paiements** – Permet d’indiquer quelles informations doivent apparaître sur les pages de couverture et de signature pour une génération d’état de paiement.
-   **Montants des lignes des commandes fournisseur** – Permet d’afficher les montants de ligne pour une commande fournisseur, ainsi que tous les montants restant à facturer ou pour les factures en attente.

### <a name="how-can-i-apply-cash-discounts-to-vendor-invoices"></a>Comment appliquer des escomptes de règlement aux factures fournisseur ?

La page **Escomptes de règlement** du module Comptabilité fournisseur ou Comptabilité client permet de sélectionner le compte sur lequel effectuer la compensation lorsque les escomptes de règlement sont appliqués aux factures. Vous pouvez le faire pour une facture existante ou une facture que vous créez. Les codes escompte de règlement sont liés aux comptes client et fournisseur et s’appliquent aux commandes client et fournisseur. Dans l’organisateur **Paramétrage**, le champ **Comptes de contrepartie pour les remises** vous permet d’effectuer la contrepartie soit sur le compte principal spécifié pour le compte des remises fournisseur, soit sur les comptes spécifiés sur la ligne de facture.

### <a name="how-do-i-specify-and-assign-certification-types-for-vendors"></a>Comment spécifier et affecter les types de certification pour les fournisseurs ?

Vous pouvez créer et affecter aux organisations de fournisseurs n’importe quel type de certification que ces fournisseurs détiennent. Cette certification inclut des informations d’identification professionnelles, telles que la licence d’un ingénieur professionnel ou la certification Microsoft SQL Server. Toutefois, la certification peut également spécifier que les fournisseurs ont une assurance en responsabilité civile ou le statut de minorité, ou qu’ils sont en conformité avec diverses normes de sécurité relatives à l’environnement ou au consommateur. La page **Type de certification** vous permet de créer des types et des descriptions de certification.

### <a name="how-do-i-view-or-enter-summary-information-for-purchase-agreement-activity"></a>Comment afficher ou saisir des informations récapitulatives pour une activité de contrat d’achat ?

La page **Contrats d’achat** du module Comptabilité fournisseur ou Approvisionnements permet d’entrer les détails récapitulatifs pour les activités associées à un contrat d’achat. Vous pouvez le faire soit pour un contrat d’achat existant, soit pour un contrat d’achat que vous créez. Les exemples incluent notamment les jalons de projet, les dates prévues pour les paiements à un fournisseur, ou les dates auxquelles les articles répertoriés dans un contrat fournisseur doivent être révisés.

#### <a name="tips"></a>Conseils

-   Vous pouvez paramétrer un numéro unique pour l’activité sur la page **Entités juridiques** du module Administration d’organisation ou Comptabilité. Lorsque vous sélectionnez l’activité dans le contrat d’achat, le numéro est affecté automatiquement.
-   Vous pouvez également paramétrer un identificateur unique pour le contrat d’achat, dans la section **Souches de numéros** de la page **Paramètres d’approvisionnements**. Lorsque vous créez un contrat d’achat, le numéro est affecté automatiquement.

### <a name="how-do-i-specify-electronic-payments-to-vendors"></a>Comment spécifier les paiements électroniques aux fournisseurs ?

Vous pouvez répartir le paiement d’une facture sur les comptes bancaires de plusieurs fournisseurs. Vous pouvez sélectionner plusieurs comptes bancaires et affecter un pourcentage à chacun. En fonction des comptes sélectionnés, une ou plusieurs transactions en cours sont créées par rapport à la facture. Vous pouvez créer des paiements pour chaque ligne de journal sans créer de paiement partiel pour chaque compte bancaire fournisseur.

#### <a name="tip"></a>Conseil

Par exemple, il existe une commande fournisseur existante pour 100 €, et la banque A correspond au compte bancaire fournisseur par défaut. Dans la table de décaissement de paiement, la banque A a 100 % de la répartition. (S’il n’existe pas de compte bancaire fournisseur par défaut, la table est vide). Vous pouvez faire passer la répartition de la banque A à 30 %, puis ajouter une nouvelle ligne. Si ensuite vous sélectionnez une autre banque fournisseur sur la nouvelle ligne (par exemple, la banque B), la répartition de la nouvelle ligne est automatiquement mise à jour à 70 %.

### <a name="how-can-i-create-and-print-cover-and-signature-pages-for-payments-reports"></a>Comment créer et imprimer des pages de couverture et de signature pour les états de paiement ?

Lorsque vous créez les pages de couverture et de signature pour un état de paiement, vous pouvez spécifier les informations qui doivent y figurer. Notamment les noms et les fonctions des personnes qui doivent approuver les paiements proposés.

### <a name="how-do-i-view-purchase-order-line-amounts"></a>Comment afficher les montants de la ligne de commande fournisseur ?

Vous pouvez afficher les montants de ligne pour une commande fournisseur. Ces montants incluent le montant actuel commandé et tous les montants reçus ou facturés. Vous pouvez également afficher tous les montants restant à facturer ou ceux des factures en attente. Conseil : par exemple, vous affichez une ligne de commande fournisseur contenant des achats validés dans deux comptes généraux. Le premier inclut les articles commandés auprès d’un fournisseur de mobilier de bureau. Le second inclut les fournitures de bureau. Le montant commandé est égal à la somme des montants facturés, en attente de facturation et restants à facturer. Le montant reçu correspond à la partie du montant commandé reçu du fournisseur.


Pour plus d’informations, voir les rubriques suivantes :

[Ajouter une certification à un fournisseur](tasks/add-certification-type-vendor-public-sector.md)

[Contrôle de l’accès aux contrats d’achat](tasks/control-access-purchase-agreements-public-sector.md)

[Créer un fournisseur occasionnel et une facture](tasks/create-one-time-vendor-invoice-public-sector.md)

[Créer un type de certification de fournisseur](tasks/create-vendor-certification-type-public-sector.md)

[Importer et créer plusieurs fournisseurs occasionnels et factures](tasks/import-multiple-one-time-vendors.md)

[Paramétrer des classifications de contrat d’achat](tasks/set-up-purchase-agreement-classifications-public-sector.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
