---
title: "Définitions de validation dans le secteur public"
description: "Cet article fournit des exemples de définitions de validation dans le secteur public qui vous permettent de créer les lignes du journal de comptabilité auxiliaire pour les transactions d'origine correspondant aux critères sélectionnés. Ces exemples incluent des affectations budgétaires, des réglementations en espèces regroupés, des radiations, des règlements de contre remboursement, des écritures comptables avancées, une clôture de fin d'exercice de comptabilité et des fonds propriétaires."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetDetailsInquiry, CustGroup, JournalizingDefinition, JournalizingDefinitionTrans, LedgerFund, LedgerParameters, LedgerTransferOpening, MainAccount
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 27271
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dc78b3721b35705ba65370a64bfe3606308766ce
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="posting-definitions-in-the-public-sector"></a>Définitions de validation dans le secteur public

[!include[banner](../includes/banner.md)]


Cet article fournit des exemples de définitions de validation dans le secteur public qui vous permettent de créer les lignes du journal de comptabilité auxiliaire pour les transactions d'origine correspondant aux critères sélectionnés. Ces exemples incluent des affectations budgétaires, des réglementations en espèces regroupés, des radiations, des règlements de contre remboursement, des écritures comptables avancées, une clôture de fin d'exercice de comptabilité et des fonds propriétaires.

Cet article décrit la fonctionnalité de définitions de validation pour le secteur public. Avant de lire cette rubrique, vous devez être familiarisé avec les définitions de validation.

## <a name="how-do-i-use-these-examples-of-public-sector-posting-definitions"></a>Comment utiliser ces exemples de définitions de validation pour le secteur public ?
Vous pouvez paramétrer les exemples de cet article sur la page **Définitions de validation**. Chaque exemple contient les sections suivantes :

-   Définition de validation – Critères de rapprochement
-   Définition de validation – Entrées générées
-   Transactions avec les comptes, valeurs de dimension et montants
-   Écritures comptables générées à partir de la définition de validation

Dans la zone **Critère de rapprochement**, lorsqu'une correspondance existe entre les comptes et les valeurs de dimension dans le pour la définition de validation, ainsi qu'entre les comptes et les valeurs de dimension de la transaction, les écritures comptables sont générées. Ces entrées sont basée sur les **entrées générées** pour la définition de validation. 

> [!NOTE]
> Pour associer une définition de validation à un type de transaction spécifique, utilisez la page **Définitions de validation de transaction**. Après avoir associé une définition de validation à un type de transaction et sélectionné la règle comptable **Utiliser les définitions de validation** sur la page **Paramètres de comptabilité**, toutes les transactions du type sélectionné doivent utiliser les définitions de validation.

## <a name="example-budget-appropriations"></a>Exemple : affectations du budget
Pour les organisations du secteur public, les soldes budgétaires d'origine sont enregistrés en tant qu'affectations pour les dépenses ou produits estimés. Ils sont utilisés pour suivre les soldes budgétaires disponibles par rapport aux dépenses et aux produits réels collectés.

Une définition de validation est créée pour prendre en charge l'enregistrement des écritures de registre budgétaires dans la comptabilité et une définition de validation de transaction est paramétrée pour les écritures de registre budgétaires dotées d'un budget de type **Budget d'origine**.

| Structure de compte | Numéro de compte de rapprochement\* | Priorité |
|-------------------|------------------------|----------|
| Frais           | - - -                  | 1        |

\*Une valeur vide dans le champ **Numéro de compte de rapprochement** signifie que tous les comptes correspondants de la structure de compte définie appartiennent à la règle de rapprochement.

### <a name="posting-definition--generated-entries-for-match-criteria--row-1"></a>Définition de validation – Entrées générées pour les critères de rapprochement – Ligne 1

| Structure de compte | Numéro de compte généré                | Débit/crédit généré |
|-------------------|-----------------------------------------|------------------------|
| Solde           | -36300 (Compte de bilan des fonds budgétaires) | Idem                   |
| Solde           | -36350 (Compte Affectations)          | Balancement              |

### <a name="posting-definition--match-criteria--row-2"></a>Définition de validation – Critères de rapprochement – Ligne 2

| Structure de compte | Numéro de compte de rapprochement\* | Priorité |
|-------------------|------------------------|----------|
| Produit           | - - -                  | 1        |

\*Une valeur vide dans le champ **Numéro de compte de rapprochement** signifie que tous les comptes correspondants de la structure de compte définie appartiennent à la règle de rapprochement.

### <a name="posting-definition--generated-entries-for-match-criteria--row-2"></a>Définition de validation – Entrées générées pour les critères de rapprochement – Ligne 2

| Structure de compte | Numéro de compte généré                | Débit/crédit généré |
|-------------------|-----------------------------------------|------------------------|
| Solde           | -36300 (Compte de bilan des fonds budgétaires) | Balancement              |
| Solde           | -36340 (Compte Produit estimé)      | Idem                   |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a>Transactions avec les comptes, valeurs de dimension et montants

La page de liste **Écritures de registre budgétaires** vous permet d'entrer les comptes, les valeurs de dimension et les montants dans l'écriture de compte budgétaire.

| Compte + Dimensions               | Débit | Crédit | Commentaire |
|------------------------------------|-------|--------|---------|
| 101-606400-OU\_1-OU\_3566-Training |       | 250,00 |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a>Écritures comptables générées à partir de la définition de validation

Les écritures comptables générées sont créées pour enregistrer le budget d'origine dans chaque dimension.

| Compte + Dimensions | Débit  | Crédit | Commentaire |
|----------------------|--------|--------|---------|
| 101-36300            |        | 250,00 |         |
| 101-36350            | 250,00 |        |         |

Dans cet exemple, les dimensions de fonds et les parties de compte de la structure de compte de dépenses correspondent aux critères de définition de validation. Donc, lorsque 101-606400-OU\_1-OU\_3566-Training est évalué, les écritures comptables générées sont créées.

## <a name="examples-pooled-cash-settlements"></a>Exemples : Règlements en espèces regroupés
La comptabilité avec disponibilités regroupées est composée des montants déposés par différents fonds dans un compte général combiné. Cela permet d'améliorer le contrôle et la conservation des liquidités et encourage la gestion efficace des fonds excessifs. Ces montants peuvent être gérés à l'aide du fonds du trésorier. Par conséquent, le montant proportionnel approprié des disponibilités regroupées et des soldes d'investissement doit être déclaré pour chaque fonds participant au regroupement. Pour garantir cela, les écritures d'échéance appropriées doivent être ajoutées aux règlements qui transfèrent des montants d'un fonds vers un autre pour réaliser le règlement. 

> [!NOTE] 
> Aucun message d'erreur n'est affiché si aucune définition de validation n'est indiquée pour les règlements ou que les critères de rapprochement de la définition de validation ne sont pas disponibles. Les installations qui n'utilisent pas les règlements en espèces regroupés ou qui ne nécessitent pas d'écriture d'équilibrage sur le n° document du règlement ne doivent pas établir de définitions de validation pour les règlements lorsque des définitions de validation sont activées pour les autres transactions. 

Pour les règlements de comptabilité fournisseur, les achats fournisseur à payer dans un ou plusieurs fonds sont utilisés pour enregistrer les transactions de capitaux propres du fonds appropriées dans le fonds du trésorier. Pour les règlements de comptabilité client, le crédit client découlant des paiements effectués dans le fonds du trésorier permet de régler les ventes dans un ou plusieurs fonds. Les entrées de validation du solde fournisseur ou du solde client pour les transactions qui sont en cours de règlement sont automatiquement contrepassées. L'utilisation de définitions de validation pour le règlement est facultative. Les définitions de validation sont appliquées au moment du règlement afin de générer les écritures comptables supplémentaires pour les écritures d'échéance pour équilibrer le n° document de règlement par fonds. 

Vous pouvez utiliser les définitions de validation pour les types de transactions de règlement suivants :

-   Les journaux des paiements fournisseur, qui incluent les paiements fournisseur avec factures, les remboursements, les n° documents de crédit de comptabilité et les avoirs avec factures
-   Les billets à ordre, qui incluent des paiements utilisant la création, le renouvellement, la remise et le règlement de billets à ordre
-   Les journaux des paiements client, qui incluent les paiements client, les n° documents de crédit de comptabilité de client, et les avoirs avec factures financières, les factures de projet, les notes d'intérêt et les transactions de lettre de relance

Pour paramétrer les définitions de validation pour les journaux des paiements fournisseur, les billets à ordre et les journaux des paiements client, sur la page **Définitions de validation**, dans le champ **Module**, sélectionnez **Banque**. Puis, sur la page **Définitions de validation de transaction**, sous l'onglet **Banque**, vous pouvez sélectionner les types de transaction appropriés à associer aux définitions de validation.

> [!NOTE] 
> Une définition de validation unique, si elle est définie de façon large, peut être utilisée pour la plupart des scénarios de règlement fournisseur et client. La définition de validation unique doit tout de même être associée à des journaux de paiement fournisseur et client sous l'onglet **Banque**. 

Vous pouvez spécifier une définition de validation différente pour une banque et un mode de paiement spécifiques pour les journaux de paiements fournisseur et client. 

Avant l'application des définitions de validation aux règlements, vous devez effectuer les tâches suivantes :

-   Associez chaque fournisseur ou client doté du fonds du trésorier (999) dans l'organisateur **Dimensions financières** de la page de détails du fournisseur ou du client. Les paiements fournisseur ou client peuvent alors être générés dans le fonds du trésorier par rapport au compte collectif fournisseur ou client spécifié dans les profils de validation fournisseur ou client.
-   Pour définir le fonds par défaut, dans le module Comptabilité client, sur la page **Groupes de clients**, dans le Volet Actions, cliquez sur **Paramétrage**, puis sur **Dimensions financières par défaut**. Le fonds du trésorier deviendra alors le fonds par défaut lorsque de nouveaux clients seront associés à un groupe de clients.
-   Associez le fonds du trésorier à chaque compte bancaire utilisé dans les règlements. Le compte bancaire validé peut alors être équilibré par le fonds avec le paiement fournisseur ou client.

Vous devez également exécuter l'une des tâches suivantes :

-   **Option A :** spécifiez un compte « date de fin de l'échéance » unique dans le fonds du trésorier pour tous les fonds.
-   **Option B :** spécifiez un autre compte « date de fin de l'échéance » dans le fonds du trésorier pour chaque fonds.

### <a name="option-a-specify-a-single-due-to-account-for-all-funds"></a>Option A : spécifiez un compte « date de fin de l'échéance » unique pour tous les fonds.

Vous pouvez spécifier un compte « date de fin de l'échéance » unique dans le fonds du trésorier pour tous les fonds. Dans ce cas, un critère de correspondance global unique concerne tous les fonds (à l'exclusion du fonds du trésorier), et vous devez spécifier les critères de rapprochement et les écritures générées suivants sur la définition de validation.

#### <a name="settlement-posting-definition--match-criteria"></a>Définition de validation de règlement – Critères de rapprochement

| Structure de compte | Numéro de compte de rapprochement\*                 | Priorité |
|-------------------|----------------------------------------|----------|
| Bilan           | 999 – Spécifiez une écriture de correspondance à priorité plus élevée pour le fonds du trésorier afin qu'aucune écriture d'équilibrage ne soit générée pour ce fonds. | 1        |

\*Une valeur vide dans le champ **Numéro de compte de rapprochement** signifie que tous les comptes correspondants de la structure de compte définie appartiennent à la règle de rapprochement.

#### <a name="settlement-posting-definition--generated-entries-for-match-criteria"></a>Définition de validation de règlement – Entrées générées pour les critères de rapprochement

| Structure de compte | Numéro de compte généré                                                           | Débit/crédit généré |
|-------------------|------------------------------------------------------------------------------------|------------------------|
|                   | Aucune entrée générée n'est définie par rapport à l'écriture de correspondance pour le fonds du trésorier. |                        |

#### <a name="settlement-posting-definition--match-criteria"></a>Définition de validation de règlement – Critères de rapprochement

| Structure de compte | Numéro de compte de rapprochement\*                                                                      | Priorité |
|-------------------|---------------------------------------------------------------------------------------------|----------|
| Bilan           | Utilisez une écriture de correspondance globale d'une priorité plus basse pour créer des écritures d'équilibrage pour tous les autres fonds. | 10       |

\*Une valeur vide dans le champ **Numéro de compte de rapprochement** signifie que tous les comptes correspondants de la structure de compte définie appartiennent à la règle de rapprochement.

#### <a name="settlement-posting-definition--generated-entries-for-match-criteria"></a>Définition de validation de règlement – Entrées générées pour les critères de rapprochement

| Structure de compte | Numéro de compte généré                                           | Débit/crédit généré |
|-------------------|--------------------------------------------------------------------|------------------------|
| Solde           | - 10110 (Compte de capitaux propres de l'entrée de correspondance – Compte de disponibilités)         | Balancement              |
| Solde           | 999 - 37000 (Compte de capitaux propres du fonds du trésorier pour tous les fonds) | Idem                   |

### <a name="option-b-specify-a-different-due-to-account-for-each-fund"></a>Option B : spécifiez un autre compte « date de fin de l'échéance » pour chaque fonds.

Vous pouvez spécifier un autre compte « date de fin de l'échéance » dans le fonds du trésorier pour chaque fonds. Vous devez spécifier, pour chaque fonds dans lequel un montant payable au fournisseur ou à recevoir du client est généré (à l'exclusion du fonds du trésorier), les critères de rapprochement et les entrées générées suivants dans la définition de validation.

#### <a name="settlement-posting-definition--match-criteria"></a>Définition de validation de règlement – Critères de rapprochement

| Structure de compte | Numéro de compte de rapprochement\*                                                                                                                | Priorité |
|-------------------|---------------------------------------------------------------------------------------------------------------------------------------|----------|
| Bilan           | 101 – Si vous utilisez une valeur de fonds et un compte principal vide, le critère de correspondance s'applique aux montants à recevoir et à payer. | 1        |

\*Une valeur vide dans le champ **Numéro de compte de rapprochement** signifie que tous les comptes correspondants de la structure de compte définie appartiennent à la règle de rapprochement.

#### <a name="settlement-posting-definition--generated-entries-for-match-criteria"></a>Définition de validation de règlement – Entrées générées pour les critères de rapprochement

| Structure de compte | Numéro de compte généré                                          | Débit/crédit généré |
|-------------------|-------------------------------------------------------------------|------------------------|
| Solde           | 101 - 10110 (Compte de capitaux propres du fonds 101 – Compte de disponibilités)           | Balancement              |
| Solde           | 999 - 37101 (Compte de capitaux propres du fonds du trésorier pour le fonds 101) | Idem                   |

Vous devez ajouter des lignes de **critères de correspondance** pour chaque fonds doté d'écritures générées, afin de refléter l'écriture d'équilibrage de fonds appropriée et le compte de capitaux propres du fonds dans le fonds du trésorier. 

Dans le journal des paiements fournisseur ou client, entrez les comptes fournisseur ou client, ou créez une proposition de paiement, puis sélectionnez les factures à payer. Lorsque le journal est validé, les entrées de validation du solde fournisseur ou client sur la facture et le paiement sont rapprochés par rapport à la définition de validation pour le règlement. Si les critères de rapprochement sont trouvés, les entrées d'échéance générées sont ajoutées au n° document de règlement. 

Les n° documents suivants sont représentatifs d'un scénario typique de facture, paiement et règlement.

## <a name="accounts-payable-example"></a>Exemple de comptabilité fournisseur
### <a name="accounts-payable-invoice-voucher"></a>N° document de facture de comptabilité fournisseur

| Compte + Dimensions | Débit  | Crédit | Commentaire             |
|----------------------|--------|--------|---------------------|
| 101 - 66100 - 150    | 250,00 |        | Compte de dépenses |
| 101 - 24210          |        | 250,00 | Module Comptabilité fournisseur    |

### <a name="accounts-payable-payment-voucher"></a>N° document de paiement de comptabilité fournisseur

| Compte + Dimensions | Débit  | Crédit | Commentaire           |
|----------------------|--------|--------|-------------------|
| 999 - 24210          | 250,00 |        | Écriture collective fournisseur    |
| 999 - 11020          |        | 250,00 | Compte bancaire/de caisse |

### <a name="accounts-payable-settlement-voucher"></a>N° document de règlement de comptabilité fournisseur

Le N° document de règlement de comptabilité fournisseur est consultable via les N° document associés du N° document de paiement fournisseur. 

Dans cet exemple, les valeurs **Numéro de compte de rapprochement** pour la définition de validation correspondent aux comptes de type de validation du solde fournisseur. Lorsque 999 - 24210 et 101 – 24210 seront évalués, les écritures comptables générées seront créées uniquement pour le fonds 101 car aucune entrée de rapprochement n'est définie pour le fonds du trésorier (999).

| Compte + Dimensions | Débit  | Crédit | Commentaire                                                                  |
|----------------------|--------|--------|--------------------------------------------------------------------------|
| 999 - 24210          |        | 250,00 | Écriture collective fournisseur (générée par le système)                                        |
| 101 - 24210          | 250,00 |        | Facture à payer (générée par le système)                                       |
| 101 - 11010          |        | 250,00 | Capitaux propres pour le fonds 101 (définition de validation pour le règlement)                  |
| 999 - 37101          | 250,00 |        | Fonds du trésorier – Fonds d'échéance 101 (définition de validation pour le règlement) |

### <a name="summarizing-the-entries-across-the-invoice-payment-and-settlement-vouchers"></a>Synthèse des entrées entre la facture, le paiement et les N° document de règlement

Le tableau suivant indique comment les comptes généraux finaux sont affectés.

| Compte + Dimensions | Débit  | Crédit | Commentaire                                                                  |
|----------------------|--------|--------|--------------------------------------------------------------------------|
| 999 - 11020          |        | 250,00 | Compte bancaire/de caisse                                                        |
| 101 - 66100 - 150    | 250,00 |        | Compte de dépenses                                                      |
| 101 - 11010          |        | 250,00 | Capitaux propres pour le fonds 101 (définition de validation pour le règlement)                  |
| 999 - 37101          | 250,00 |        | Fonds du trésorier – Fonds d'échéance 101 (définition de validation pour le règlement) |

## <a name="accounts-receivable-example"></a>Exemple de comptabilité client
### <a name="accounts-receivable-invoice-voucher"></a>N° document de facture de comptabilité client

| Compte + Dimensions | Débit  | Crédit | Commentaire             |
|----------------------|--------|--------|---------------------|
| 101 - 44400          |        | 250,00 | Compte de produit     |
| 101 - 11530          | 250,00 |        | Module Comptabilité client |

### <a name="accounts-receivable-payment-voucher"></a>N° document de paiement de la comptabilité client

| Compte + Dimensions | Débit  | Crédit | Commentaire           |
|----------------------|--------|--------|-------------------|
| 999 - 11530          |        | 250,00 | Écriture collective client  |
| 999 - 11020          | 250,00 |        | Compte bancaire/de caisse |

### <a name="accounts-receivable-settlement-voucher"></a>N° document de règlement de comptabilité client

Le N° document de règlement de comptabilité client est consultable via les N° document associés du N° document de paiement client.

Dans cet exemple, les valeurs **Numéro de compte de rapprochement** pour la définition de validation correspondent aux comptes de type de validation du solde client. Lorsque 999 - 11530 et 101 – 11530 sont évalués, les écritures comptables générées sont créées uniquement pour le fonds 101, car aucune entrée de rapprochement n'est définie pour le fonds du trésorier (999).

| Compte + Dimensions | Débit  | Crédit | Commentaire                                                                |
|----------------------|--------|--------|------------------------------------------------------------------------|
| 999 - 11530          | 250,00 |        | Écriture collective client (générée par le système)                                    |
| 101 - 11530          |        | 250,00 | Facture à recevoir (générée par le système)                                  |
| 101 - 11010          | 250,00 |        | Capitaux propres pour le fonds 101 (définition de validation pour le règlement)                |
| 999 - 37101          |        | 250,00 | Fonds du trésorier – Fonds d'échéance 101 (définition de validation pour le règlement) |

### <a name="summarizing-the-entries-across-the-invoice-payment-and-settlement-vouchers"></a>Synthèse des entrées entre la facture, le paiement et les N° document de règlement

Le tableau suivant indique comment les comptes généraux finaux sont affectés.

| Compte + Dimensions | Débit  | Crédit | Commentaire                                                                |
|----------------------|--------|--------|------------------------------------------------------------------------|
| 999 - 11020          | 250,00 |        | Compte bancaire/de caisse                                                      |
| 101 - 44400          |        | 250,00 | Compte de produit                                                        |
| 101 - 11010          | 250,00 |        | Capitaux propres pour le fonds 101 (définition de validation pour le règlement)                |
| 999 - 37101          |        | 250,00 | Fonds du trésorier – Fonds d'échéance 101 (définition de validation pour le règlement) |

En sus de l'exemple exposé plus haut dans cette section, les définitions de validation pour les règlements qui sont associées au type de transaction de journal des paiements client peuvent également être appliquées aux scénarios suivants :

-   Annulations de comptabilité client
-   Règlements en contre remboursement de facture financière de comptabilité client (paiement en espèces)

Les annulations de comptabilité client peuvent utiliser les définitions de validation définies pour le règlement. Par conséquent, le N° document de journal de crédit de comptabilité peut être généré lorsque les soldes sont validés par les fonds. Les entrées des types compte général et compte client des lignes de journal sont évaluées par rapport à la définition de validation pour le règlement. Les deux utilisent la définition de validation affectée au type de transaction sous l'onglet **Comptabilité client** de la page **Définitions de validation de transaction**. Selon la façon dont l'annulation est conçue pour être exécutée, la définition de validation pour le règlement peut nécessiter des critères de rapprochement supplémentaires. 

Lorsque la définition de validation d'annulation est paramétrée pour annuler les soldes sur une provision pour le compte d'actifs de créances douteuses, la définition de validation pour le règlement peut également être utilisée pour les annulations si le critère de rapprochement est déjà défini pour les comptes de bilan ayant un masque pour le compte principal. (Pour plus d'informations, voir les exemples précédents, notamment la section « Définition de validation de règlement - Critères de rapprochement ».) 

Lorsque la définition de validation d'annulation est paramétrée pour contrepasser le compte de produit d'origine, la définition de validation pour le règlement doit présenter les critères de rapprochement appropriés pour les structures de comptabilité de produit, spécifiquement avec des écritures comptables d'échéance sur les entrées générées. Les entrées suivantes doivent être présentes dans la définition de validation pour le règlement pour chaque fonds ne figurant pas dans le fonds du trésorier (999).

### <a name="posting-definition--match-criteria"></a>Définition de validation – Critères de rapprochement

| Structure de compte | Numéro de compte de rapprochement\*                                                     | Priorité |
|-------------------|---------------------------------------------------------------------------|----------|
| Produit           | 101 – Si vous utilisez une valeur de fonds et un compte principal vide, le critère est applicable à toutes les écritures comptables. | 1        |

\*Une valeur vide dans le champ **Numéro de compte de rapprochement** signifie que tous les comptes correspondants de la structure de compte définie appartiennent à la règle de rapprochement.

### <a name="posting-definition--generated-entries-for-match-criteria"></a>Définition de validation – Entrées générées pour les critères de rapprochement

| Structure de compte | Numéro de compte généré                                                           | Débit/crédit généré |
|-------------------|------------------------------------------------------------------------------------|------------------------|
| Solde           | 101 - 10110 (Compte de capitaux propres du fonds 101)                                           | Balancement              |
| Idem              | 999 - 37101 (Fonds du trésorier – Compte de fonds capitaux propres pour le fonds 101. Un seul compte peut être utilisé à la place des comptes de capitaux propres de fonds individuels) | Idem                   |

## <a name="accounts-receivable-writeoff-example"></a>Exemple d'annulation de comptabilité client
### <a name="accounts-receivable-invoice-voucher"></a>N° document de facture de comptabilité client

| Compte + Dimensions | Débit  | Crédit | Commentaire             |
|----------------------|--------|--------|---------------------|
| 101 - 44400 - -      |        | 250,00 | Compte de produit     |
| 101 - 11530          | 250,00 |        | Module Comptabilité client |

### <a name="accounts-receivable-write-off--general-ledger-credit-voucher"></a>Annulation de comptabilité client – N° document de comptabilité

Dans cet exemple, la définition de validation pour l'annulation est définie pour contrepasser le compte de produit.

| Compte + Dimensions | Débit  | Crédit | Commentaire                                                                |
|----------------------|--------|--------|------------------------------------------------------------------------|
| 999 - 11530          |        | 250,00 | Écriture collective client                                                       |
| 101 - 44400 - -      | 250,00 |        | Compte bancaire/de caisse                                                      |
| 101 - 11010          |        | 250,00 | Capitaux propres pour le fonds 101 (définition de validation pour le règlement)                |
| 999 - 37101          | 250,00 |        | Fonds du trésorier – Fonds d'échéance 101 (définition de validation pour le règlement) |

### <a name="accounts-receivable-write-off--settlement-voucher"></a>Annulation de comptabilité client – N° document de règlement

Dans cet exemple, le crédit qui est créé dans le N° document de comptabilité est appliqué à la transaction d'annulation. En outre, les valeurs **Numéro de compte de rapprochement** pour la définition de validation correspondent aux comptes du type de validation du solde client. Par conséquent, lorsque 999 - 11530 et 101 – 11530 sont évalués, les écritures comptables générées sont créées uniquement pour le fonds 101, car aucune entrée de rapprochement n'est définie pour le fonds du trésorier (999).

| Compte + Dimensions | Débit  | Crédit | Commentaire                                                                |
|----------------------|--------|--------|------------------------------------------------------------------------|
| 999 - 11530          | 250,00 |        | Écriture collective client (générée par le système)                                    |
| 101 - 11530          |        | 250,00 | Facture à recevoir (générée par le système)                                  |
| 101 - 11010          | 250,00 |        | Capitaux propres pour le fonds 101 (définition de validation pour le règlement)                |
| 999 - 37101          |        | 250,00 | Fonds du trésorier – Fonds d'échéance 101 (définition de validation pour le règlement) |

### <a name="summarizing-the-entries-across-the-invoice-write-off-credit-and-settlement-vouchers"></a>Synthèse des entrées entre la facture, , le crédit d'annulation et les N° document de règlement

Il n'existe aucune valeur nette sur les comptes généraux après l'annulation d'une facture entière.

## <a name="accounts-receivable-free-text-invoice-cash-on-delivery-cash-payment-settlement-example"></a>Exemple de règlement en contre remboursement de facture financière de comptabilité client (paiement en espèces)
Les factures financières utilisent des conditions de paiement dans lesquelles le mode de paiement est défini à **Contre remboursement** et le paiement en espèces est activé. Par conséquent, elles sont immédiatement réglées au moment de la validation sans devoir utiliser le journal des paiements. Lorsque ce type de règlement se produit, un avoir est créé. Cet avoir utilise le compte de disponibilités spécifié sur la contrepartie des conditions de paiement et les dimensions financières sur le compte collectif client. Dans ce type de règlement, les comptes à recevoir appropriés qui sont spécifiés sur la facture ne sont pas automatiquement contrepassés. Par conséquent, la définition de validation pour le règlement doit répondre à la contrepassation des entrées de validation du solde client sur la facture et le crédit, en plus de générer les entrées d'échéance pour règlement. 

Pour utiliser les définitions de validation pour le règlement dans ce scénario, effectuez les tâches de paramétrage supplémentaires suivantes :

-   Créez un mode de paiement distinct pour les factures financières qui seront réglées via cette méthode.
-   Créez une définition de validation pour le règlement en contre remboursement des factures financières.
-   Associez la nouvelle définition de validation (pour le journal des paiements client par rapport au mode de paiement spécifique) sous l'onglet **Banque** de la page **Définitions de validation de transaction**. Pour appliquer le paramètre de définition de validation spécifiée pour ce type de règlement, sélectionnez ce mode de paiement unique et les conditions de paiement en contre-remboursement/espèces sur la facture.

Ensuite, dans la définition de validation, entrez les critères de rapprochement et les entrées générées suivants pour le fonds du trésorier (999).

### <a name="posting-definition--match-criteria--row-1"></a>Définition de validation – Critères de rapprochement – Ligne 1

| Structure de compte | Numéro de compte de rapprochement\*                                          | Débit/crédit généré |
|-------------------|-----------------------------------------------------------------|------------------------|
| Bilan           | 999 – Ce critère de rapprochement est uniquement utilisé pour les ventes dans le fonds du trésorier (999). Seules deux entrées générées sont exigées pour ce critère de rapprochement, car les entrées d'échéance ne s'appliquent pas au fonds du trésorier. | 1                      |

\*Une valeur vide dans le champ **Numéro de compte de rapprochement** signifie que tous les comptes correspondants de la structure de compte définie appartiennent à la règle de rapprochement.

### <a name="posting-definition--generated-entries-for-match-criteria--row-1"></a>Définition de validation – Entrées générées pour les critères de rapprochement – Ligne 1

| Structure de compte | Numéro de compte généré                                                               | Débit/crédit généré |
|-------------------|----------------------------------------------------------------------------------------|------------------------|
| Solde           | 999 - 11530 (Débite l'entrée de type validation du solde client sur le crédit qui est émis.) | Balancement          |
| Idem              | 999 - (Crédite les ventes dans le fonds 999.)                                         | Idem                   |La définition de validation doit contenir l'entrée suivante pour chaque fonds autre que le fonds du trésorier (999).

### <a name="posting-definition--match-criteria--row-2"></a>Définition de validation – Critères de rapprochement – Ligne 2

| Structure de compte | Numéro de compte de rapprochement\*                                                | Priorité |
|-------------------|-----------------------------------------------------------------------|----------|
| Bilan           | 101 – Pour les critères de correspondance n'appartenant pas au fonds du trésorier, quatre ensembles d'entrées générées sont exigées. Deux entrées contrepassent les entrées du type de validation du solde client sur le crédit et la facture, et deux entrées supplémentaires génèrent les entrées d'échéance exigées. | 1        |

\*Une valeur vide dans le champ **Numéro de compte de rapprochement** signifie que tous les comptes correspondants de la structure de compte définie appartiennent à la règle de rapprochement.

### <a name="posting-definition--generated-entries-for-match-criteria--row-2"></a>Définition de validation – Entrées générées pour les critères de rapprochement – Ligne 2

| Structure de compte | Numéro de compte généré                                          | Débit/crédit généré |
|-------------------|-------------------------------------------------------------------|------------------------|
| Solde           | 999 - 11530 (Débite l'entrée de type validation du solde client sur le crédit qui est émis.)  | Balancement              |
| Idem              | 999 - (Crédite les ventes dans le fonds 101.)                         | Idem                   |
| Solde           | 101 - 10110 (Compte de capitaux propres du fonds 101)                           | Balancement              |
| Idem              | 999 - 37101 (Fonds du trésorier – Compte de fonds capitaux propres pour le fonds 101. Un seul compte peut être utilisé à la place des comptes de capitaux propres de fonds individuels) | Idem                   |

## <a name="accounts-receivable-cashondelivery-cash-payment-settlement-example"></a>Exemple de règlement en contre remboursement de comptabilité client (paiement en espèces)
### <a name="accounts-receivable-invoice-voucher"></a>N° document de facture de comptabilité client

| Compte + Dimensions | Débit  | Crédit | Commentaire                          |
|----------------------|--------|--------|----------------------------------|
| 101 - 44400 - -      |        | 250,00 | Compte de produit dans le fonds 101      |
| 999 - 44400 - -      |        | 250,00 | Compte de produit dans le fonds 999      |
| 101 - 11530          | 250,00 |        | Comptabilité client dans le fonds 101  |
| 999 - 11535          | 250,00 |        | Comptabilité client dans le fonds 999  |
| 999-11530            |        | 500,00 | Écriture collective client                 |
| 999 - 11020          | 500,00 |        | Compte de disponibilités sur les conditions de paiement |

Cela inclut les entrées de crédit supplémentaire dans le N° document.

### <a name="accounts-receivable-settlement-voucher"></a>N° document de règlement de comptabilité client

Dans cet exemple, les valeurs **Numéro de compte de rapprochement** pour la définition de validation correspondent aux comptes de type de validation du solde client uniquement sur la facture.

| Compte + Dimensions | Débit  | Crédit | Commentaire                                                                |
|----------------------|--------|--------|------------------------------------------------------------------------|
| 999 - 11530          | 250,00 |        | Écriture collective client (définition de validation pour le règlement)                   |
| 101 - 11530          |        | 250,00 | Facture à recevoir (définition de validation pour le règlement)                 |
| 101 - 11010          | 250,00 |        | Capitaux propres pour le fonds 101 (définition de validation pour le règlement)                |
| 999 - 37101          |        | 250,00 | Fonds du trésorier – Fonds d'échéance 101 (définition de validation pour le règlement) |
| 999 - 11530          | 250,00 |        | Écriture collective client (définition de validation pour le règlement)                   |
| 999 - 11535          |        | 250,00 | Écriture collective client (définition de validation pour le règlement)                   |

### <a name="summarizing-the-entries-across-the-invoice-payment-and-settlement-vouchers"></a>Synthèse des entrées entre la facture, le paiement et les N° document de règlement

Le tableau suivant indique comment les comptes généraux finaux sont affectés.

| Compte + Dimensions | Débit  | Crédit | Commentaire                                                                |
|----------------------|--------|--------|------------------------------------------------------------------------|
| 999 - 11020          | 500,00 |        | Compte de disponibilités sur les conditions de paiement                                       |
| 101 - 44400 - -      |        | 250,00 | Produit dans le fonds 101                                                    |
| 999 - 44400 - -      |        | 250,00 | Produit dans le fonds 999                                                    |
| 101 - 11010          | 250,00 |        | Capitaux propres pour le fonds 101 (définition de validation pour le règlement)                |
| 999 - 37101          |        | 250,00 | Fonds du trésorier – Fonds d'échéance 101 (définition de validation pour le règlement) |

## <a name="example-advanced-ledger-entries"></a>Exemple : Écritures comptables avancées
Lorsque vous créez des écritures comptables avancées, vous devez sélectionner une définition de validation par défaut. Ensuite, pour chaque ligne d'écriture comptable avancée, vous pouvez soit utiliser la définition de validation par défaut, soit en sélectionner une autre. Les définitions de validation génèrent les répartitions comptables et les écritures de journal de comptabilité auxiliaire qui créent, ajustent ou contrepassent les écritures comptables et mettent à jour les comptes généraux. Vous paramétrez chaque définition de validation pour l'application Comptabilité. Toutefois, vous n'associez pas la définition de validation avec un type de transaction, comme vous le faites pour les autres définitions de validation. Au lieu de cela, vous sélectionnez la définition de validation dans l'écriture comptable avancée. 

Ici, la facture AP\_0949 de la comptabilité fournisseur a été validée par erreur sur le fonds d'amélioration du capital 300-12300-51002 plutôt que sur le fonds général 100-39810-51001. L'exemple suivant montre comment une écriture comptable avancée peut utiliser une définition de validation pour débiter le fonds d'amélioration du capital et créditer le fonds général.

### <a name="posting-definition--match-criteria--row-1"></a>Définition de validation – Critères de rapprochement – Ligne 1

| Structure de compte | Numéro de compte de rapprochement\* | Priorité |
|-------------------|------------------------|----------|
| Bilan           | 300- -                 | 1        |

\*Une valeur vide dans le champ **Numéro de compte de rapprochement** signifie que tous les comptes correspondants de la structure de compte définie appartiennent à la règle de rapprochement.

### <a name="posting-definition--generated-entries-for-match-criteria--row-1"></a>Définition de validation – Entrées générées pour les critères de rapprochement – Ligne 1

| Structure de compte | Numéro de compte généré | Débit/crédit généré |
|-------------------|--------------------------|------------------------|
| Solde           | 300-11001                | Balancement              |
| Solde           | 900-11001                | Balancement              |
| Solde           | 900-37300                | Idem                   |

### <a name="posting-definition--match-criteria--row-2"></a>Définition de validation – Critères de rapprochement – Ligne 2

| Structure de compte | Numéro de compte de rapprochement\* | Priorité |
|-------------------|------------------------|----------|
| Bilan           | 100 - -                | 1        |

\*Une valeur vide dans le champ **Numéro de compte de rapprochement** signifie que tous les comptes correspondants de la structure de compte définie appartiennent à la règle de rapprochement.

### <a name="posting-definition--generated-entries-for-match-criteria--row-2"></a>Définition de validation – Entrées générées pour les critères de rapprochement – Ligne 2

| Structure de compte | Numéro de compte généré | Débit/crédit généré |
|-------------------|--------------------------|------------------------|
| Solde           | 100-11001                | Balancement              |
| Solde           | 900-11001                | Balancement              |
| Solde           | 900-37301                | Idem                   |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a>Transactions avec les comptes, valeurs de dimension et montants

| Compte + Dimensions | Débit | Crédit | Commentaire                    |
|----------------------|-------|--------|----------------------------|
| 300-12300-51002      | 350   |        | Ligne d'écriture comptable avancée |
| 100-39810-51001      |       | 350    | Ligne d'écriture comptable avancée |

### <a name="ledger-entries-generated-from-the-posting-definition"></a>Écritures comptables générées à partir de la définition de validation

| Compte + Dimensions | Débit | Crédit | Commentaire       |
|----------------------|-------|--------|---------------|
| 300-11001            |       | 350    | Écriture collective |
| 900-11001            |       | 350    | Écriture collective |
| 900-37300            | 350   |        | Écriture collective |
| 100-11001            | 350   |        | Écriture collective |
| 900-11001            | 350   |        | Écriture collective |
| 900-37301            |       | 350    | Écriture collective |

## <a name="examples-general-ledger-year-end-close"></a>Exemples : Clôture de fin d'exercice de comptabilité
Les organisations utilisent les définitions de validation dans le cadre de la clôture de fin d'exercice des comptes généraux. Les définitions de validation permettent de clôturer les comptes pour les soldes de fonds ou les bénéfices non répartis, selon l'attribut de la classe (dimension) Fonds et l'attribut de type Clôture du compte. Les définitions de validation sont requises pour clôturer les comptes généraux et transférer les soldes vers la période d'ouverture du nouvel exercice. 

> [!NOTE]
> Pour utiliser les définitions de validation pour la clôture et l'ouverture de fin d'exercice, vous devez effectuer les tâches de paramétrage suivantes :

-   Sur la page **Paramètres de comptabilité**, dans la section **Comptabilité**, dans l'organisateur **Clôture d'exercice**, sélectionnez l'option **Créer des transactions de clôture lors du transfert**.
-   Sur la page **Comptes principaux - plan de comptes : %1**, créez un compte de clôture.

Les exemples suivants de définition de validation indiquent la clôture de fin d'exercice pour les fonds gouvernementaux et les fonds propriétaires.

### <a name="governmental-funds-example"></a>Exemple de fonds gouvernemental

#### <a name="governmental-funds--posting-definition--match-criteria--row-1"></a>Fonds gouvernemental – Définition de validation – Critères de rapprochement – Ligne 1

| Structure de compte | Numéro de compte de rapprochement\* | Priorité |
|-------------------|------------------------|----------|
| Frais           | - - -                  | 1        |

\*Une valeur vide dans le champ **Numéro de compte de rapprochement** signifie que tous les comptes correspondants de la structure de compte définie appartiennent à la règle de rapprochement.

#### <a name="governmental-funds--posting-definition--generated-entries-for-match-criteria--row-1"></a>Fonds gouvernemental – Définition de validation – Entrées générées pour les critères de rapprochement – Ligne 1

| Structure de compte | Numéro de compte généré          | Débit/crédit généré |
|-------------------|-----------------------------------|------------------------|
| Structure de compte | -37300 (Solde des fonds non réservés) | Balancement              |

#### <a name="governmental-funds--posting-definition--match-criteria--row-2"></a>Fonds gouvernemental – Définition de validation – Critères de rapprochement – Ligne 2

| Structure de compte | Numéro de compte de rapprochement\* | Priorité |
|-------------------|------------------------|----------|
| Frais           | - - -                  | 1        |

\*Une valeur vide dans le champ **Numéro de compte de rapprochement** signifie que tous les comptes correspondants de la structure de compte définie appartiennent à la règle de rapprochement.

#### <a name="governmental-funds--posting-definition--generated-entries-for-match-criteria--row-2"></a>Fonds gouvernemental – Définition de validation – Entrées générées pour les critères de rapprochement – Ligne 2

| Structure de compte | Numéro de compte généré          | Débit/crédit généré |
|-------------------|-----------------------------------|------------------------|
| Structure de compte | -37300 (Solde des fonds non réservés) | Balancement              |

#### <a name="governmental-funds--posting-definition--match-criteria--row-3"></a>Fonds gouvernemental – Définition de validation – Critères de rapprochement – Ligne 3

| Structure de compte | Numéro de compte de rapprochement\* | Priorité |
|-------------------|------------------------|----------|
| Produit           | - - -                  | 1        |

\*Une valeur vide dans le champ **Numéro de compte de rapprochement** signifie que tous les comptes correspondants de la structure de compte définie appartiennent à la règle de rapprochement.

#### <a name="governmental-funds--posting-definition--generated-entries-for-match-criteria--row-3"></a>Fonds gouvernemental – Définition de validation – Entrées générées pour les critères de rapprochement – Ligne 3

| Structure de compte | Numéro de compte généré          | Débit/crédit généré |
|-------------------|-----------------------------------|------------------------|
| Structure de compte | -37300 (Solde des fonds non réservés) | Balancement              |

Après avoir paramétré la définition de validation, affectez-la au type de transaction **Comptabilité - Clôture** sur la page **Définitions de validation de transaction**.

#### <a name="governmental-funds--transactions-with-the-accounts-dimension-values-and-amounts"></a>Fonds gouvernemental – Transactions avec les comptes, valeurs de dimension et montants

Le solde des comptes généraux au cours de la période sélectionnée s'affiche sur la page **Transactions d'ouverture**.

| Compte + Dimensions | Débit  | Crédit | Commentaire |
|----------------------|--------|--------|---------|
| 101-66100-130        | 250,00 |        |         |

#### <a name="governmental-funds--ledger-entries-generated-from-the-posting-definition"></a>Fonds gouvernemental – Écritures comptables générées à partir de la définition de validation

Les écritures comptables générées sont créées pour enregistrer l'entrée de clôture.

| Compte + Dimensions | Débit  | Crédit | Commentaire |
|----------------------|--------|--------|---------|
| 101-66100-130-       |        | 250,00 |         |
| 101-37300            | 250,00 |        |         |

Dans cet exemple, le fonds 101 est défini en tant que classe de fonds **Gouvernemental** sur la page **Fonds** du module Comptabilité. Sur la page **Définitions de validation de transaction**, le type de transaction de clôture **Comptabilité** est associé à la classe de fonds **Gouvernemental** et à la définition de validation. 

La définition de validation recherche un rapprochement avec toute partie du compte de la structure de compte Dépenses. C'est pourquoi, lorsque 101-66100-130- est évalué, le même compte général est utilisé, le montant est contrepassé pour clôturer le compte et l'écriture comptable générée par le solde est créée.

### <a name="proprietary-funds-example"></a>Exemple de fonds propriétaire

#### <a name="proprietary-funds--posting-definition--match-criteria--row-1"></a>Fonds propriétaire – Définition de validation – Critères de rapprochement – Ligne 1

| Structure de compte | Numéro de compte de rapprochement\* | Priorité |
|-------------------|------------------------|----------|
| Bilan           | - - -                  | 1        |

\*Une valeur vide dans le champ **Numéro de compte de rapprochement** signifie que tous les comptes correspondants de la structure de compte définie appartiennent à la règle de rapprochement.

#### <a name="proprietary-funds--posting-definition--generated-entries-for-match-criteria--row-1"></a>Fonds propriétaire – Définition de validation – Entrées générées pour les critères de rapprochement – Ligne 1

| Structure de compte | Numéro de compte généré   | Débit/crédit généré |
|-------------------|----------------------------|------------------------|
| Structure de compte | -37310 (Bénéfices non répartis) | Balancement              |

#### <a name="proprietary-funds--posting-definition--match-criteria--row-2"></a>Fonds propriétaire – Définition de validation – Critères de rapprochement – Ligne 2

| Structure de compte | Numéro de compte de rapprochement\* | Priorité |
|-------------------|------------------------|----------|
| Frais           | - - -                  | 1        |

\*Une valeur vide dans le champ **Numéro de compte de rapprochement** signifie que tous les comptes correspondants de la structure de compte définie appartiennent à la règle de rapprochement.

#### <a name="proprietary-funds--posting-definition--generated-entries-for-match-criteria--row-2"></a>Fonds propriétaire – Définition de validation – Entrées générées pour les critères de rapprochement – Ligne 2

| Structure de compte | Numéro de compte généré   | Débit/crédit généré |
|-------------------|----------------------------|------------------------|
| Structure de compte | -37310 (Bénéfices non répartis) | Balancement              |

#### <a name="proprietary-funds--posting-definition--match-criteria--row-3"></a>Fonds propriétaire – Définition de validation – Critères de rapprochement – Ligne 3

| Structure de compte | Numéro de compte de rapprochement\* | Priorité |
|-------------------|------------------------|----------|
| Produit           | - - -                  | 1        |

\*Une valeur vide dans le champ **Numéro de compte de rapprochement** signifie que tous les comptes correspondants de la structure de compte définie appartiennent à la règle de rapprochement.

#### <a name="proprietary-funds--posting-definition--generated-entries-for-match-criteria--row-3"></a>Fonds propriétaire – Définition de validation – Entrées générées pour les critères de rapprochement – Ligne 3

| Structure de compte | Numéro de compte généré   | Débit/crédit généré |
|-------------------|----------------------------|------------------------|
| Structure de compte | -37310 (Bénéfices non répartis) | Balancement              |

Après avoir paramétré la définition de validation, vous l'affectez à la transaction de clôture **Comptabilité** sur la page **Définitions de validation de transaction**.

#### <a name="proprietary-funds--transactions-with-the-accounts-dimension-values-and-amounts"></a>Fonds propriétaire – Transactions avec les comptes, valeurs de dimension et montants

Le solde des comptes généraux au cours de la période sélectionnée s'affiche sur la page **Transactions d'ouverture**.

| Compte + Dimensions | Débit  | Crédit | Commentaire |
|----------------------|--------|--------|---------|
| 601-66100-130        | 250,00 |        |         |

#### <a name="proprietary-funds--ledger-entries-generated-from-the-posting-definition"></a>Fonds propriétaire – Écritures comptables générées à partir de la définition de validation

Les écritures comptables générées sont créées pour enregistrer l'entrée de clôture.

| Compte + Dimensions | Débit  | Crédit | Commentaire |
|----------------------|--------|--------|---------|
| 601-66100-130-       |        | 250,00 |         |
| 601-37310            | 250,00 |        |         |

Dans cet exemple, le fonds 601 est défini en tant que classe de fonds **Propriétaire** sur la page **Fonds**. Sur la page **Définitions de validation de transaction**, le type de transaction de clôture **Comptabilité** est associé à la classe de fonds **Propriétaire** et à la définition de validation. 

La définition de validation recherche un rapprochement avec toute partie du compte de la structure de compte Dépenses. C'est pourquoi, lorsque 601-66100-130- est évalué, le même compte général est utilisé, le montant est contrepassé pour clôturer le compte et l'écriture comptable générée par le solde est créée.

<a name="see-also"></a>Voir également :
--------

[Comptabilité fournisseur](../accounts-payable/accounts-payable.md)

[Comptabilité fournisseur dans le secteur public](accounts-payable-public-sector.md)

[Comptabilité client dans le secteur public](accounts-receivable-public-sector.md)

[Budgétisation dans le secteur public](budgeting-public-sector.md)

[Comptabilité dans le secteur public](general-ledger-public-sector.md)




