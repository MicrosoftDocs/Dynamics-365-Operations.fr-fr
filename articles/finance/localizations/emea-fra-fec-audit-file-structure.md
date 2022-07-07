---
title: Structure des sources de données Dynamics 365 Finance pour le FEC
description: Cet article décrit la structure des sources de données Microsoft Dynamics 365 Finance pour le Fichier des écritures comptables (FEC).
author: liza-golub
ms.date: 06/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.author: elgolu
ms.reviewer: kfend
ms.search.region: France
ms.openlocfilehash: 2cb8acf3aad6213c5081105aa8d2fb27a111c68e
ms.sourcegitcommit: d9d111d7420ca8f1071689afe38a1ccf4b8051f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/21/2022
ms.locfileid: "9033706"
---
# <a name="structure-of-dynamics-365-finance-data-sources-for-the-fec"></a>Structure des sources de données Dynamics 365 Finance pour le FEC

Dans Microsoft Dynamics 365 Finance, vous pouvez générer le fichier [FEC principal](#fec-main) (Fichier des écritures comptables) et les annexes suivantes :

- **[Solde client](#customers-balances) :** Annexe sur les soldes d’ouverture de l’exercice des clients
- **[Solde fournisseur](#vendors-balances) :** Annexe sur les soldes d’ouverture de l’exercice des fournisseurs
- **[Transactions client](#customers-transactions) :** Annexe des transactions client pour une période déterminée
- **[Transactions fournisseur](#vendors-transactions) :** Annexe des transactions fournisseur pour une période déterminée

Vous pouvez également générer un fichier FEC qui inclut les soldes d’ouverture des exercices client et fournisseur ([FEC principal étendu](#fec-main-extended)). Utilisez cette option pour les entreprises qui n’ont que quelques enregistrements au cours de la période de reporting. La période de déclaration doit inclure le début de l’exercice financier.

Comme expliqué dans les [Prérequis pour générer un fichier d’audit FEC en France](emea-fra-fec-audit-file-pre-requisites.md), pour tenir compte de l’article 100 du BOI-CF-IOR-60-40-20, la numérotation doit être continue, cohérente et séquentielle. En raison de ces exigences de numérotation, nous vous recommandons de définir l’option **Continu** sur **Oui** pour les souches de numéros. Dans certains scénarios, la cohérence de la souche de numéros pour les écritures du compte général (document) peut être interrompue dans le fichier FEC principal pour les raisons suivantes :

- Une écriture du compte général est créée dans la comptabilité, mais n’est pas indiquée dans le fichier FEC lorsque le montant est 0,00.
- Un numéro de document est utilisé pour une transaction de stock ayant un montant nul qui n’est pas reflété dans le tableau des écritures du compte général.
- Un écart dans la souche de numéros pour les écritures de compte général se produit en raison d’un problème technique.

À partir de la version 10.0.23 de Finance, utilisez l’annexe [Justification pour les numéros manquants](#missing-numbers-justification) pour déclarer les transactions du compte général manquantes dans le fichier FEC principal.

Les sections suivantes répertorient les sources de données utilisées dans le fichier principal et les annexes FEC.

Les sources de données sont décrites en détail dans la section [Descriptions détaillées des sources de données](#fec-detailed-datasources) de cette rubrique.

## <a name="main-fec-file-for-the-period-specified"></a><a id="fec-main"></a>Fichier FEC principal pour la période spécifiée

Le tableau suivant montre les définitions de structure de données **Fichier FEC principal pour la période spécifiée** (\$GeneralJournalView\_FR).

| Nombre | Nom          | Type           | Description (FR) | Description (EN) | Source de données pour la gestion des états électroniques |
|--------|---------------|----------------|------------------|------------------|---------------------------------------|
| 1      | JournalCode   | Alphanumérique | Le code journal de l’écriture comptable | Le code journal de l’écriture comptable. | \$GeneralJournalView\_FR/\$JournalCodeText |
| 2      | JournalLib    | Alphanumérique | Le libellé journal de l’écriture comptable | La légende du journal de l’écriture comptable. | \$GeneralJournalView\_FR/getGeneralJournalEntry()/deJournalLib\_FR() |
| 3      | EcritureNum   | Alphanumérique | Le numéro sur une séquence continue de l’écriture comptable | Le numéro dans une séquence continue pour l’écriture comptable. | \$GeneralJournalView\_FR/GeneralJournalEntrySubledgerVoucher |
| 4      | EcritureDate  | Date           | La date de comptabilisation de l’écriture comptable | Date de validation de l’entrée comptable. | \$GeneralJournalView\_FR/GeneralJournalEntryAccountingDate |
| 5      | CompteNum     | Alphanumérique | Le numéro de compte, dont les trois premiers caractères doivent correspondre à des chiffres respectant les normes du plan comptable français | Le numéro de compte dont les trois premiers caractères doivent correspondre à des chiffres respectant les normes du plan comptable français. Des informations sur les transactions de plusieurs clients ou fournisseurs se trouvent dans les annexes respectives. | \$GeneralJournalView\_FR/\$MainAccountId |
| 6      | CompteLib     | Alphanumérique | Le libellé de compte, conformément à la nomenclature du plan comptable français | Le nom du compte selon la nomenclature du plan comptable français. | \$GeneralJournalView\_FR/getGeneralJournalAccountEntry()/getMainAccountName() |
| 7      | CompAuxNum    | Alphanumérique | Le numéro de compte auxiliaire (à blanc si non utilisé) | Numéro de compte auxiliaire. Ce champ est vide s’il n’est pas utilisé. | \$GeneralJournalView\_FR/getGeneralJournalAccountEntry()/deCompteAuxNum\_FR() |
| 8      | CompAuxLib    | Alphanumérique | Le libellé du compte auxiliaire (à blanc si non utilisé) | Description du compte auxiliaire. Ce champ est vide s’il n’est pas utilisé. | \$GeneralJournalView\_FR/getGeneralJournalAccountEntry()/deCompteAuxLib\_FR() |
| 9      | PieceRef      | Alphanumérique | La référence de la pièce justificative | La référence de la pièce justificative. Si la référence du document de support est introuvable, ce champ est rempli avec EcritureNum. | \$GeneralJournalView\_FR/getGeneralJournalEntry()/dePieceNum\_FR() |
| 10     | PieceDate     | Date           | La date de la pièce justificative | La date de la pièce justificative. | \$GeneralJournalView\_FR/getGeneralJournalEntry()/dePieceDate\_FR() |
| 11     | EcritureLib   | Alphanumérique | Le libellé de l’écriture comptable | La formulation de l’écriture comptable. | \$GeneralJournalView\_FR/\$ReplaceIntoDeEcritureLib\_FR |
| 12     | Montant       | Numérique      | Le montant au débit/au crédit | Le montant de débit/crédit. | \$GeneralJournalView\_FR/\$AbsAmount |
| 13     | Sens          | Numérique      | Le sens : "D" au débit ; "C" au crédit | Le sens : **D** = débit, **C** = crédit | \$GeneralJournalView\_FR/\$Direction |
| 14     | EcritureLet   | Alphanumérique | Le lettrage de l’écriture comptable (à blanc si non utilisé) | Le lettrage de l’écriture comptable. Ce champ est vide s’il n’est pas utilisé. | \$GeneralJournalView\_FR/\$deEcritureLet |
| 15     | DateLet       | Date           | La date de lettrage (à blanc si non utilisé) | La date du lettrage. Ce champ est vide s’il n’est pas utilisé. | \$GeneralJournalView\_FR/\$deDateLet |
| 16     | ValidDate     | Date           | La date de validation de l’écriture comptable | Date de validation de l’entrée comptable. | \$GeneralJournalView\_FR/GeneralJournalEntryAccountingDate |
| 17     | Montantdevise | Numérique      | Le montant en devise (à blanc si non utilisé) | Montant en devise. Ce champ est vide s’il n’est pas utilisé. | \$GeneralJournalView\_FR/GeneralJournalAccountEntryTransactionCurrencyAmount |
| 18     | Idevise       | Alphanumérique | L’identifiant de la devise (à blanc si non utilisé) | L’identifiant de la devise. Ce champ est vide s’il n’est pas utilisé. | \$GeneralJournalView\_FR/GeneralJournalAccountEntryTransactionCurrencyCode |

## <a name="customers-fiscal-year-opening-balances-annex"></a><a id="customers-balances"></a>Annexe des soldes d’ouverture de l’exercice pour les clients 

Les transactions d’ouverture de l’exercice des clients sont enregistrées en tant que transactions récapitulatives dans le compte général. Afin de fournir des informations détaillées sur les opérations d’ouverture de l’exercice par les clients, l’**Annexe sur les soldes d’ouverture de l’exercice des clients** est implémentée. Cette annexe recueille les montants des soldes d’ouverture des clients au début de l’exercice et fournit ces informations avec le bon de transaction d’ouverture du compte général.

Le tableau suivant montre les définitions de structure de données **Annexe sur les soldes d’ouverture de l’exercice des clients** (\$CustLedgerBalance).

| Nombre | Nom          | Type           | Description (FR) | Description (EN) | Source de données ER |
|--------|---------------|----------------|------------------|------------------|----------------|
| 1      | JournalCode   | Alphanumérique | Le code journal de l’écriture comptable | Le code journal de l’écriture comptable. | CustTransGroupedByLedgerAccount/\$JournalCodeText |
| 2      | JournalLib    | Alphanumérique | Le libellé journal de l’écriture comptable | La légende du journal de l’écriture comptable. | CustTransGroupedByLedgerAccount/\$JournalLibText |
| 3      | EcritureNum   | Alphanumérique | Le numéro sur une séquence continue de l’écriture comptable | Le numéro dans une séquence continue pour l’écriture comptable. | CustTransGroupedByLedgerAccount/\$Voucher |
| 4      | EcritureDate  | Date           | La date de comptabilisation de l’écriture comptable | Date de validation de l’entrée comptable. | CustTransGroupedByLedgerAccount/\$Date |
| 5      | CompteNum     | Alphanumérique | Le numéro de compte, dont les trois premiers caractères doivent correspondre à des chiffres respectant les normes du plan comptable français | Le numéro de compte dont les trois premiers caractères doivent correspondre à des chiffres respectant les normes du plan comptable français. | CustTransGroupedByLedgerAccount/grouped/\$LedgerAccount |
| 6      | CompteLib     | Alphanumérique | Le libellé de compte, conformément à la nomenclature du plan comptable français | Le nom du compte selon la nomenclature du plan comptable français. | CustTransGroupedByLedgerAccount/\$LedgerAccountName |
| 7      | CompAuxNum    | Alphanumérique | Le numéro de compte auxiliaire (à blanc si non utilisé) | Numéro de compte auxiliaire. Ce champ est vide s’il n’est pas utilisé. | CustTransGroupedByLedgerAccount/grouped/AccountNum |
| 8      | CompAuxLib    | Alphanumérique | Le libellé du compte auxiliaire (à blanc si non utilisé) | Description du compte auxiliaire. Ce champ est vide s’il n’est pas utilisé. | CustTransGroupedByLedgerAccount/\$PartyName |
| 9      | PieceRef      | Alphanumérique | La référence de la pièce justificative | La référence de la pièce justificative. | CustTransGroupedByLedgerAccount/\$PieceNum |
| 10     | PieceDate     | Date           | La date de la pièce justificative | La date de la pièce justificative. | CustTransGroupedByLedgerAccount/\$PieceDate |
| 11     | EcritureLib   | Alphanumérique | Le libellé de l’écriture comptable | La formulation de l’écriture comptable. | CustTransGroupedByLedgerAccount/\$EcritureLib |
| 12     | Montant       | Numérique      | Le montant au débit/au crédit | Le montant de débit/crédit. | CustTransGroupedByLedgerAccount/\$AbsAmount |
| 13     | Sens          | Numérique      | Le sens : "D" au débit ; "C" au crédit | Le sens : **D** = débit, **C** = crédit | CustTransGroupedByLedgerAccount/\$Direction |
| 14     | EcritureLet   | Alphanumérique | Le lettrage de l’écriture comptable (à blanc si non utilisé) | Le lettrage de l’écriture comptable. Ce champ est vide s’il n’est pas utilisé. | \$deEmpty |
| 15     | DateLet       | Date           | La date de lettrage (à blanc si non utilisé) | La date du lettrage. Ce champ est vide s’il n’est pas utilisé. | \$deDateNull |
| 16     | ValidDate     | Date           | La date de validation de l’écriture comptable | Date de validation de l’entrée comptable. | CustTransGroupedByLedgerAccount/\$ValidDate |
| 17     | Montantdevise | Numérique      | Le montant en devise (à blanc si non utilisé) | Montant en devise. Ce champ est vide s’il n’est pas utilisé. | CustTransGroupedByLedgerAccount/aggregated/AmountCur |
| 18     | Idevise       | Alphanumérique | L’identifiant de la devise (à blanc si non utilisé) | L’identifiant de la devise. Ce champ est vide s’il n’est pas utilisé. | CustTransGroupedByLedgerAccount/grouped/CurrencyCode |

## <a name="vendors-fiscal-year-opening-balances-annex"></a><a id="vendors-balances"></a>Annexe des soldes d’ouverture de l’exercice pour les fournisseurs 

Les transactions d’ouverture de l’exercice des fournisseurs sont enregistrées en tant que transactions récapitulatives dans le compte général. Afin de fournir des informations détaillées sur les opérations d’ouverture de l’exercice par les fournisseurs, l’**Annexe sur les soldes d’ouverture de l’exercice des fournisseurs** est implémentée. Cette annexe recueille les montants des soldes d’ouverture des fournisseurs au début de l’exercice et représente ces informations conjointement avec le bon de transaction d’ouverture du compte général.

Le tableau suivant montre les définitions de structure de données **Annexe sur les soldes d’ouverture de l’exercice des fournisseurs**.

| Nombre | Nom          | Type           | Description (FR) | Description (EN) | Source de données ER |
|--------|---------------|----------------|------------------|------------------|----------------|
| 1      | JournalCode   | Alphanumérique | Le code journal de l’écriture comptable | Le code journal de l’écriture comptable. | Non inclus |
| 2      | JournalLib    | Alphanumérique | Le libellé journal de l’écriture comptable | La légende du journal de l’écriture comptable. | VendTransGroupedByLedgerAccount/\$JournalLibText |
| 3      | EcritureNum   | Alphanumérique | Le numéro sur une séquence continue de l’écriture comptable | Le numéro dans une séquence continue pour l’écriture comptable. | VendTransGroupedByLedgerAccount/\$Voucher |
| 4      | EcritureDate  | Date           | La date de comptabilisation de l’écriture comptable | Date de validation de l’entrée comptable. | VendTransGroupedByLedgerAccount/\$Date |
| 5      | CompteNum     | Alphanumérique | Le numéro de compte, dont les trois premiers caractères doivent correspondre à des chiffres respectant les normes du plan comptable français | Le numéro de compte dont les trois premiers caractères doivent correspondre à des chiffres respectant les normes du plan comptable français. | VendTransGroupedByLedgerAccount/grouped/\$LedgerAccount |
| 6      | CompteLib     | Alphanumérique | Le libellé de compte, conformément à la nomenclature du plan comptable français | Le nom du compte selon la nomenclature du plan comptable français. | VendTransGroupedByLedgerAccount/\$LedgerAccountName |
| 7      | CompAuxNum    | Alphanumérique | Le numéro de compte auxiliaire (à blanc si non utilisé) | Numéro de compte auxiliaire. Ce champ est vide s’il n’est pas utilisé. | VendTransGroupedByLedgerAccount/grouped/AccountNum |
| 8      | CompAuxLib    | Alphanumérique | Le libellé du compte auxiliaire (à blanc si non utilisé) | Description du compte auxiliaire. Ce champ est vide s’il n’est pas utilisé. | VendTransGroupedByLedgerAccount/\$PartyName |
| 9      | PieceRef      | Alphanumérique | La référence de la pièce justificative | La référence de la pièce justificative. | VendTransGroupedByLedgerAccount/\$PieceNum |
| 10     | PieceDate     | Date           | La date de la pièce justificative | La date de la pièce justificative. | VendTransGroupedByLedgerAccount/\$PieceDate |
| 11     | EcritureLib   | Alphanumérique | Le libellé de l’écriture comptable | La formulation de l’écriture comptable. | VendTransGroupedByLedgerAccount/\$EcritureLib |
| 12     | Montant       | Numérique      | Le montant au débit/au crédit | Le montant de débit/crédit. | VendTransGroupedByLedgerAccount/\$AbsAmount |
| 13     | Sens          | Numérique      | Le sens : "D" au débit ; "C" au crédit | Le sens : **D** = débit, **C** = crédit | VendTransGroupedByLedgerAccount/\$Direction |
| 14     | EcritureLet   | Alphanumérique | Le lettrage de l’écriture comptable (à blanc si non utilisé) | Le lettrage de l’écriture comptable. Ce champ est vide s’il n’est pas utilisé. | \$deEmpty |
| 15     | DateLet       | Date           | La date de lettrage (à blanc si non utilisé) | La date du lettrage. Ce champ est vide s’il n’est pas utilisé. | \$deDateNull |
| 16     | ValidDate     | Date           | La date de validation de l’écriture comptable | Date de validation de l’entrée comptable. | VendTransGroupedByLedgerAccount/\$ValidDate |
| 17     | Montantdevise | Numérique      | Le montant en devise (à blanc si non utilisé) | Montant en devise. Ce champ est vide s’il n’est pas utilisé. | VendTransGroupedByLedgerAccount/aggregated/AmountCur |
| 18     | Idevise       | Alphanumérique | L’identifiant de la devise (à blanc si non utilisé) | L’identifiant de la devise. Ce champ est vide s’il n’est pas utilisé. | VendTransGroupedByLedgerAccount/grouped/CurrencyCode |

## <a name="customers-transactions-annex-for-the-period-specified"></a><a id="customers-transactions"></a>Annexe des transactions de clients pour la période spécifiée

**Annexe des transactions clients pour la période spécifiée** Une annexe peut être demandée pour fournir des détails supplémentaires sur les transactions des clients. Par exemple, dans le cas où une entreprise utilise le paramètre [Autoriser plusieurs transactions dans un seul bon](../../finance/general-ledger/one-voucher.md) sur l’onglet **Général** de la page **Paramètres de Comptabilité**, un justificatif peut être attribué à plusieurs transactions clients. Pour fournir des informations détaillées par les comptes clients pour un tel scénario, l’**Annexe des transactions clients pour la période spécifiée** est mise en œuvre. 

Le tableau suivant montre les définitions de structure de données **Annexe des transactions clients pour la période spécifiée**.

| Nombre | Nom          | Type           | Description (FR) | Description (EN) | Source de données ER |
|--------|---------------|----------------|------------------|------------------|----------------|
| 1      | JournalCode   | Alphanumérique | Le code journal de l’écriture comptable | Le code journal de l’écriture comptable. | \$CustTrans/\$JournalCodeText |
| 2      | JournalLib    | Alphanumérique | Le libellé journal de l’écriture comptable | La légende du journal de l’écriture comptable. | \$CustTrans/\$JournalLibText |
| 3      | EcritureNum   | Alphanumérique | Le numéro sur une séquence continue de l’écriture comptable | Le numéro dans une séquence continue pour l’écriture comptable. | \$CustTrans/Voucher |
| 4      | EcritureDate  | Date           | La date de comptabilisation de l’écriture comptable | Date de validation de l’entrée comptable. | \$CustTrans/TransDate |
| 5      | CompteNum     | Alphanumérique | Le numéro de compte, dont les trois premiers caractères doivent correspondre à des chiffres respectant les normes du plan comptable français | Le numéro de compte dont les trois premiers caractères doivent correspondre à des chiffres respectant les normes du plan comptable français. | \$CustTrans/deLedgerAccount\_FR() |
| 6      | CompteLib     | Alphanumérique | Le libellé de compte, conformément à la nomenclature du plan comptable français | Le nom du compte selon la nomenclature du plan comptable français. | \$CustTrans/deLedgerAccountName\_FR() |
| 7      | CompAuxNum    | Alphanumérique | Le numéro de compte auxiliaire (à blanc si non utilisé) | Numéro de compte auxiliaire. Ce champ est vide s’il n’est pas utilisé. | \$CustTrans/AccountNum |
| 8      | CompAuxLib    | Alphanumérique | Le libellé du compte auxiliaire (à blanc si non utilisé) | Description du compte auxiliaire. Ce champ est vide s’il n’est pas utilisé. | \$CustTrans/custTableName() |
| 9      | PieceRef      | Alphanumérique | La référence de la pièce justificative | La référence de la pièce justificative. | \$CustTrans/\$PieceNum |
| 10     | PieceDate     | Date           | La date de la pièce justificative | La date de la pièce justificative. | \$CustTrans/\$PieceDate |
| 11     | EcritureLib   | Alphanumérique | Le libellé de l’écriture comptable | La formulation de l’écriture comptable. | \$CustTrans/deEcritureLib\_FR() |
| 12     | Montant       | Numérique      | Le montant au débit/au crédit | Le montant de débit/crédit. | \$CustTrans/\$AbsAmount |
| 13     | Sens          | Numérique      | Le sens : "D" au débit ; "C" au crédit | Le sens : **D** = débit, **C** = crédit | \$CustTrans/\$Direction |
| 14     | EcritureLet   | Alphanumérique | Le lettrage de l’écriture comptable (à blanc si non utilisé) | Le lettrage de l’écriture comptable. Ce champ est vide s’il n’est pas utilisé. | \$CustTrans/LastSettleVoucher |
| 15     | DateLet       | Date           | La date de lettrage (à blanc si non utilisé) | La date du lettrage. Ce champ est vide s’il n’est pas utilisé. | \$CustTrans/LastSettleDate |
| 16     | ValidDate     | Date           | La date de validation de l’écriture comptable | Date de validation de l’entrée comptable. | \$CustTrans/createdDateTime |
| 17     | Montantdevise | Numérique      | Le montant en devise (à blanc si non utilisé) | Montant en devise. Ce champ est vide s’il n’est pas utilisé. | \$CustTrans/AmountCur|
| 18     | Idevise       | Alphanumérique | L’identifiant de la devise (à blanc si non utilisé) | L’identifiant de la devise. Ce champ est vide s’il n’est pas utilisé. | \$CustTrans/CurrencyCode |

## <a name="vendors-transactions-annex-for-the-period-specified"></a><a id="vendors-transactions"></a>Annexe des transactions de fournisseurs pour la période spécifiée

**Annexe des transactions fournisseurs pour la période spécifiée** Une annexe peut être demandée pour fournir des détails supplémentaires sur les transactions des fournisseurs. Par exemple, dans le cas où une entreprise utilise le paramètre [Autoriser plusieurs transactions dans un seul bon](../../finance/general-ledger/one-voucher.md) sur l’onglet **Général** de la page **Paramètres de Comptabilité**, un justificatif peut être attribué à plusieurs transactions fournisseurs. Pour fournir des informations détaillées par comptes fournisseur pour un tel scénario, l’**annexe des transactions fournisseur pour la période spécifiée** est mise en œuvre. 

Le tableau suivant montre les définitions de structure de données **Annexe des transactions fournisseurs pour la période spécifiée**.

| Nombre | Nom          | Type           | Description (FR) | Description (EN) | Source de données ER |
|--------|---------------|----------------|------------------|------------------|----------------|
| 1      | JournalCode   | Alphanumérique | Le code journal de l’écriture comptable | Le code journal de l’écriture comptable. | \$VendTrans/\$JournalCodeText |
| 2      | JournalLib    | Alphanumérique | Le libellé journal de l’écriture comptable | La légende du journal de l’écriture comptable. | \$VendTrans/\$JournalLibText |
| 3      | EcritureNum   | Alphanumérique | Le numéro sur une séquence continue de l’écriture comptable | Le numéro dans une séquence continue pour l’écriture comptable. | \$VendTrans/Voucher |
| 4      | EcritureDate  | Date           | La date de comptabilisation de l’écriture comptable | Date de validation de l’entrée comptable. | \$VendTrans/TransDate |
| 5      | CompteNum     | Alphanumérique | Le numéro de compte, dont les trois premiers caractères doivent correspondre à des chiffres respectant les normes du plan comptable français | Le numéro de compte dont les trois premiers caractères doivent correspondre à des chiffres respectant les normes du plan comptable français. | \$VendTrans/deLedgerAccount\_FR() |
| 6      | CompteLib     | Alphanumérique | Le libellé de compte, conformément à la nomenclature du plan comptable français | Le nom du compte selon la nomenclature du plan comptable français. | \$VendTrans/deLedgerAccountName\_FR() |
| 7      | CompAuxNum    | Alphanumérique | Le numéro de compte auxiliaire (à blanc si non utilisé) | Numéro de compte auxiliaire. Ce champ est vide s’il n’est pas utilisé. | \$VendTrans/AccountNum |
| 8      | CompAuxLib    | Alphanumérique | Le libellé du compte auxiliaire (à blanc si non utilisé) | Description du compte auxiliaire. Ce champ est vide s’il n’est pas utilisé. | \$VendTrans/custTableName() |
| 9      | PieceRef      | Alphanumérique | La référence de la pièce justificative | La référence de la pièce justificative. | \$VendTrans/\$PieceNum |
| 10     | PieceDate     | Date           | La date de la pièce justificative | La date de la pièce justificative. | \$VendTrans/\$PieceDate |
| 11     | EcritureLib   | Alphanumérique | Le libellé de l’écriture comptable | La formulation de l’écriture comptable. | \$VendTrans/deEcritureLib\_FR() |
| 12     | Montant       | Numérique      | Le montant au débit/au crédit | Le montant de débit/crédit. | \$VendTrans/\$AbsAmount |
| 13     | Sens          | Numérique      | Le sens : "D" au débit ; "C" au crédit | Le sens : **D** = débit, **C** = crédit | \$VendTrans/\$Direction |
| 14     | EcritureLet   | Alphanumérique | Le lettrage de l’écriture comptable (à blanc si non utilisé) | Le lettrage de l’écriture comptable. Ce champ est vide s’il n’est pas utilisé. | \$VendTrans/LastSettleVoucher |
| 15     | DateLet       | Date           | La date de lettrage (à blanc si non utilisé) | La date du lettrage. Ce champ est vide s’il n’est pas utilisé. | \$VendTrans/LastSettleDate |
| 16     | ValidDate     | Date           | La date de validation de l’écriture comptable | Date de validation de l’entrée comptable. | \$VendTrans/createdDateTime |
| 17     | Montantdevise | Numérique      | Le montant en devise (à blanc si non utilisé) | Montant en devise. Ce champ est vide s’il n’est pas utilisé. | \$VendTrans/AmountCur |
| 18     | Idevise       | Alphanumérique | L’identifiant de la devise (à blanc si non utilisé) | L’identifiant de la devise. Ce champ est vide s’il n’est pas utilisé. | \$VendTrans/CurrencyCode |

## <a name="fec-main-file-including-fiscal-year-opening-balances-details-for-customers-and-vendors"></a><a id="fec-main-extended"></a>Fichier FEC principal incluant les détails des soldes d’ouverture de l’exercice pour les clients et les fournisseurs

Le tableau suivant montre les définitions de structure de données du **Fichier principal du FEC comprenant les détails des soldes d’ouverture de l’exercice pour les clients et les fournisseurs**.

| Nombre | Nom          | Type           | Description (FR) | Description (EN) | Source de données ER |
|--------|---------------|----------------|------------------|------------------|----------------|
| 1      | JournalCode   | Alphanumérique | Le code journal de l’écriture comptable | Le code journal de l’écriture comptable. | \$FECExtendedAggregation/\$JournalCodeText |
| 2      | JournalLib    | Alphanumérique | Le libellé journal de l’écriture comptable | La légende du journal de l’écriture comptable. | \$FECExtendedAggregation/\$JournalLibText |
| 3      | EcritureNum   | Alphanumérique | Le numéro sur une séquence continue de l’écriture comptable | Le numéro dans une séquence continue pour l’écriture comptable. | \$FECExtendedAggregation/\$Voucher |
| 4      | EcritureDate  | Date           | La date de comptabilisation de l’écriture comptable | Date de validation de l’entrée comptable. | \$FECExtendedAggregation/\$Date |
| 5      | CompteNum     | Alphanumérique | Le numéro de compte, dont les trois premiers caractères doivent correspondre à des chiffres respectant les normes du plan comptable français | Le numéro de compte dont les trois premiers caractères doivent correspondre à des chiffres respectant les normes du plan comptable français. Des informations sur les transactions de plusieurs clients ou fournisseurs se trouvent dans les annexes respectives. | \$FECExtendedAggregation/\$LedgerAccount |
| 6      | CompteLib     | Alphanumérique | Le libellé de compte, conformément à la nomenclature du plan comptable français | Le nom du compte selon la nomenclature du plan comptable français. | \$FECExtendedAggregation/\$LedgerAccountName |
| 7      | CompAuxNum    | Alphanumérique | Le numéro de compte auxiliaire (à blanc si non utilisé) | Numéro de compte auxiliaire. Ce champ est vide s’il n’est pas utilisé. | \$FECExtendedAggregation/\$AccountNum |
| 8      | CompAuxLib    | Alphanumérique | Le libellé du compte auxiliaire (à blanc si non utilisé) | Description du compte auxiliaire. Ce champ est vide s’il n’est pas utilisé. | \$FECExtendedAggregation/\$PartyName |
| 9      | PieceRef      | Alphanumérique | La référence de la pièce justificative | La référence de la pièce justificative. Si la référence du document de support est introuvable, ce champ est rempli avec EcritureNum. | \$FECExtendedAggregation/\$PieceNum |
| 10     | PieceDate     | Date           | La date de la pièce justificative | La date de la pièce justificative. | \$FECExtendedAggregation/\$PieceDate |
| 11     | EcritureLib   | Alphanumérique | Le libellé de l’écriture comptable | La formulation de l’écriture comptable. | \$FECExtendedAggregation/\$EcritureLib |
| 12     | Montant       | Numérique      | Le montant au débit/au crédit | Le montant de débit/crédit. | \$FECExtendedAggregation/\$AbsAmount |
| 13     | Sens          | Numérique      | Le sens : "D" au débit ; "C" au crédit | Le sens : **D** = débit, **C** = crédit | \$FECExtendedAggregation/\$Direction |
| 14     | EcritureLet   | Alphanumérique | Le lettrage de l’écriture comptable (à blanc si non utilisé) | Le lettrage de l’écriture comptable. Ce champ est vide s’il n’est pas utilisé. | \$FECExtendedAggregation/\$LastSettleVoucher |
| 15     | DateLet       | Date           | La date de lettrage (à blanc si non utilisé) | La date du lettrage. Ce champ est vide s’il n’est pas utilisé. | \$FECExtendedAggregation/\$LastSettleDate |
| 16     | ValidDate     | Date           | La date de validation de l’écriture comptable | Date de validation de l’entrée comptable. | \$FECExtendedAggregation/\$ValidDate |
| 17     | Montantdevise | Numérique      | Le montant en devise (à blanc si non utilisé) | Montant en devise. Ce champ est vide s’il n’est pas utilisé. | \$FECExtendedAggregation/\$AmountCur |
| 18     | Idevise       | Alphanumérique | L’identifiant de la devise (à blanc si non utilisé) | L’identifiant de la devise. Ce champ est vide s’il n’est pas utilisé. | $FECExtendedAggregation/$CurrencyCode |

## <a name="missing-numbers-justification-annex"></a><a id="missing-numbers-justification"></a>Annexe Justification pour les numéros manquants

À partir de la version 10.0.23 de Finance, l’annexe **Justification pour les numéros manquants** représente les données collectées auprès de Finance pour les scénarios suivants où la cohérence de la souche de numéros pour les écritures du compte général (document) peut être interrompue dans le fichier FEC principal :

- **Scénario 1 :** Une écriture du compte général est créée dans la comptabilité, mais n’est pas indiquée dans le fichier FEC lorsque le montant est de 0,00.
- **Scénario 2** : Un numéro de document est utilisé pour une transaction de stock ayant un montant nul qui n’est pas reflété dans le tableau des écritures du compte général.
- **Scénario 3** : Un écart dans la souche de numéros pour les écritures de compte général se produit en raison d’un problème technique.

Utilisez l’annexe [Justification pour les numéros manquants](#missing-numbers-justification) pour déclarer les transactions du compte général manquantes dans le fichier FEC principal pour les raisons qui précèdent.

Le tableau suivant montre les définitions de structure de données du **Fichier principal du FEC comprenant les détails des soldes d’ouverture de l’exercice pour les clients et les fournisseurs**.

| Nombre | Nom          | Type           | Description (FR) | Description (EN) | Source de données ER |
|--------|---------------|----------------|------------------|------------------|----------------|
| 1      | JournalCode   | Alphanumérique | Le code journal de l’écriture comptable | Le code journal de l’écriture comptable. | <p>\$VouchersOmissions/\$JournalCodeText</p><ul><li>**Scénario 1 :** GeneralJournalView_FR.GeneralJournalEntrySubledgerVoucher</li><li>**Scénario 2 :** InventTrans.VoucherPhysical</li><li>**Scénario 3 :** Numéro de document manquant généré automatiquement</li></ul> |
| 2      | JournalLib    | Alphanumérique | Le libellé journal de l’écriture comptable | La légende du journal de l’écriture comptable. | <p>$VouchersOmissions/$JournalLib</p><ul><li>**Scénario 1 :** GeneralJournalView_FR.\'getGeneralJournalEntry()\'.\'deJournalLib_FR()\'</li><li>**Scénario 2 :** \"Stock\"</li><li>**Scénario 3 :** Valeur vide</li></ul> |
| 3      | EcritureNum   | Alphanumérique | Le numéro sur une séquence continue de l’écriture comptable | Le numéro dans une séquence continue pour l’écriture comptable. | $VouchersOmissions/$Voucher |
| 4      | EcritureDate  | Date           | La date de comptabilisation de l’écriture comptable | Date de validation de l’entrée comptable. | <p>$VouchersOmissions/$Date</p><ul><li>**Scénario 1 :** GeneralJournalView_FR.GeneralJournalEntryAccountingDate</li><li>**Scénario 2 :** InventTrans.DatePhysical</li><li>**Scénario 3 :** Valeur vide</li></ul> |
| 5      | CompteNum     | Alphanumérique | Le numéro de compte, dont les trois premiers caractères doivent correspondre à des chiffres respectant les normes du plan comptable français | Le numéro de compte dont les trois premiers caractères doivent correspondre à des chiffres respectant les normes du plan comptable français. Des informations sur les transactions de plusieurs clients ou fournisseurs se trouvent dans les annexes respectives. | <p>$VouchersOmissions/$AccountNum</p><ul><li>**Scénario 1 :** GeneralJournalView_FR.GeneralJournalAccountEntryMainAccount</li><li>**Scénario 2 :** Valeur vide</li><li>**Scénario 3 :** Valeur vide</li></ul> |
| 6      | CompteLib     | Alphanumérique | Le libellé de compte, conformément à la nomenclature du plan comptable français | Le nom du compte selon la nomenclature du plan comptable français. | <p>$VouchersOmissions/$AccountName</p><ul><li>**Scénario 1 :** GeneralJournalView_FR.\'getGeneralJournalAccountEntry()\'.getMainAccountName()</li><li>**Scénario 2 :** Valeur vide</li><li>**Scénario 3 :** Valeur vide</li></ul> |
| 7      | CompAuxNum    | Alphanumérique | Le numéro de compte auxiliaire (à blanc si non utilisé) | Numéro de compte auxiliaire. Ce champ est vide s’il n’est pas utilisé. | <p>$VouchersOmissions/$CompteAuxNum</p><ul><li>**Scénario 1 :** GeneralJournalView_FR.\'getGeneralJournalAccountEntry()\'.\'deCompteAuxNum_FR()\'</li><li>**Scénario 2 :** Non applicable</li><li>**Scénario 3 :** Non applicable</li></ul> |
| 8      | CompAuxLib    | Alphanumérique | Le libellé du compte auxiliaire (à blanc si non utilisé) | Description du compte auxiliaire. Ce champ est vide s’il n’est pas utilisé. | <p>$VouchersOmissions/$CompteAuxLib</p><ul><li>**Scénario 1 :** GeneralJournalView_FR.\'getGeneralJournalAccountEntry()\'.\'deCompteAuxLib_FR()\'</li><li>**Scénario 2 :** Non applicable</li><li>**Scénario 3 :** Non applicable</li></ul> |
| 9      | PieceRef      | Alphanumérique | La référence de la pièce justificative | La référence de la pièce justificative. Si la référence du document de support est introuvable, ce champ est rempli avec EcritureNum. | <p>$VouchersOmissions/$PieceRef</p><ul><li>**Scénario 1 :** GeneralJournalView_FR.\'getGeneralJournalEntry()\'.\'dePieceNum_FR()\'</li><li>**Scénario 2 :** InventTrans.VoucherPhysical</li><li>**Scénario 3 :** Valeur vide</li></ul> |
| 10     | PieceDate     | Date           | La date de la pièce justificative | La date de la pièce justificative. | <p>$VouchersOmissions/$PieceDate</p><ul><li>**Scénario 1 :** GeneralJournalView_FR.\'getGeneralJournalEntry()\'.\'dePieceDate_FR()\'</li><li>**Scénario 2 :** InventTrans.DatePhysical</li><li>**Scénario 3 :** Valeur vide</li></ul> |
| 11     | EcritureLib   | Alphanumérique | Le libellé de l’écriture comptable | La formulation de l’écriture comptable. | <p>$VouchersOmissions/$EcritureLib</p><ul><li>**Scénario 1 :** GeneralJournalView_FR.\'getGeneralJournalAccountEntry()\'</li><li>**Scénario 2 :** \'InventTrans_\' et InventTrans.RecID</li><li>**Scénario 3 :** Valeur vide</li></ul> |
| 12     | Montant       | Numérique      | Le montant au débit/au crédit | Le montant de débit/crédit. | <p>$VouchersOmissions/$AbsAmount</p><ul><li>**Scénario 1 :** GeneralJournalView_FR.GeneralJournalAccountEntryAccountingCurrencyAmount</li><li>**Scénario 2 :** InventTrans.CostAmountPhysical</li><li>**Scénario 3 :** \'0.00\'</li></ul> |
| 13     | Sens          | Numérique      | Le sens : "D" au débit ; "C" au crédit | Le sens : **D** = débit, **C** = crédit | <p>$VouchersOmissions/$Direction</p><ul><li>**Scenario 1 :** Indicateur Débit\/crédit du document financier (GeneralJournalView_FR.GeneralJournalAccountEntryAccountingCurrencyAmount)</li><li>**Scénario 2 :** Indicateur Débit\/crédit du document physique (InventTrans.CostAmountPhysical)</li><li>**Scénario 3 :** Valeur vide</li></ul> |
| 14     | EcritureLet   | Alphanumérique | Le lettrage de l’écriture comptable (à blanc si non utilisé) | Le lettrage de l’écriture comptable. Ce champ est vide s’il n’est pas utilisé. | <p>$VouchersOmissions\/$EcritureLet</p><ul><li>**Scénario 1 :** GeneralJournalAccountEntry_Extension.deEcritureLet_FR(GeneralJournalView_FR.\'getGeneralJournalAccountEntry()\',\'$Period_DateFrom’, \'$Period_DateTo\')</li><li>**Scénario 2 :** Non applicable</li><li>**Scénario 3 :** Non applicable</li></ul> |
| 15     | DateLet       | Date           | La date de lettrage (à blanc si non utilisé) | La date du lettrage. Ce champ est vide s’il n’est pas utilisé. | <p>$VouchersOmissions/$DateLet</p><ul><li>**Scénario 1 :** GeneralJournalAccountEntry_Extension.deDateLet_FR(GeneralJournalView_FR.\'getGeneralJournalAccountEntry()\',\'$Period_DateFrom’,\'$Period_DateTo\')</li><li>**Scénario 2 :** Non applicable</li><li>**Scénario 3 :** Non applicable</li></ul> |
| 16     | ValidDate     | Date           | La date de validation de l’écriture comptable | Date de validation de l’entrée comptable. | <p>$VouchersOmissions/$Date</p><ul><li>**Scénario 1 :** GeneralJournalView_FR.GeneralJournalEntryAccountingDate</li><li>**Scénario 2 :** InventTrans.DatePhysical</li><li>**Scénario 3 :** Valeur vide</li></ul> |
| 17     | Montantdevise | Numérique      | Le montant en devise (à blanc si non utilisé) | Montant en devise. Ce champ est vide s’il n’est pas utilisé. | <p>$VouchersOmissions/$AmountCur</p><ul><li>**Scénario 1 :** GeneralJournalView_FR.GeneralJournalAccountEntryTransactionCurrencyAmount</li><li>**Scénario 2 :** InventTrans.CostAmountPhysical</li><li>**Scénario 3 :** \'0.00\'</li></ul> |
| 18     | Idevise       | Alphanumérique | L’identifiant de la devise (à blanc si non utilisé) | L’identifiant de la devise. Ce champ est vide s’il n’est pas utilisé. | <p>$VouchersOmissions/$Currency</p><ul><li>**Scénario 1 :** GeneralJournalView_FR.GeneralJournalAccountEntryTransactionCurrencyCode</li><li>**Scénario 2 :** InventTrans.CurrencyCode</li><li>**Scénario 3 :** Non applicable</li></ul> |

## <a name="detailed-data-source-descriptions"></a><a id="fec-detailed-datasources"></a>Descriptions des sources des données détaillées

Cette section explique les sources de données des champs dans FEC de type "Principal" en termes de tables et de champs Finance.

### <a name="journalcode--journal-code-of-the-accounting-entry"></a>JournalCode - Le code journal de l’écriture comptable

La valeur du champ `JournalCode` représente la partie texte du préfixe qui est spécifié pour la souche de numéros du document comptable utilisé par la transaction comptable lors de sa validation. L’algorithme d’extraction du préfixe est basé sur la règle qui doit être appliquée lors de la configuration des souches de numéros, comme décrit dans [Prérequis pour générer un fichier d’audit FEC](emea-fra-fec-audit-file-pre-requisites.md). Par exemple, si la souche de N° de justificatif pour les journaux de facture fournisseur est définie sous la forme **FRSIFACF-\#\#\#\#\#\#\#\#**, la valeur **FRSIFACF** est reportée dans le champ `JournalCode` au sein du FEC.

### <a name="journallib--journal-caption-of-the-accounting-entry"></a>JournalLib - Légende du journal de l’écriture comptable

La valeur du champ `JournalLib` est collectée à partir de plusieurs sources de données dans Finance :

1. Si la transaction provient d’une transaction de journal comptable, la valeur est collectée à partir du champ `Name` de la table `LedgerJournalName`.
2. Si la transaction ne provient pas d’une transaction de journal comptable, la valeur est collectée à partir de l’étiquette dans la langue française de l’énumération (enum) `LedgerTransType` du champ `JournalCategory` au sein de la table `GeneralJournalEntry`.
3. Si la valeur enum `LedgerTransType` n’est pas définie, Finance renvoie la description de `TransactionLog` à partir de `TransactionLog.Type` dans la langue française qui est liée à `generalJournalEntry.CreatedTransactionId`.

### <a name="ecriturenum--number-in-a-continuous-sequence-for-the-accounting-entry"></a>EcritureNum – Numéro dans une séquence continue pour l’écriture comptable

Le champ `EcritureNum` représente la valeur du champ `SubledgerVoucher` de l’enregistrement de table `GeneralJournalEntry` lié à chaque transaction des états. Dans l’interface utilisateur (IU) de Finance, cette valeur de champ peut être affichée dans le champ **Pièce justificative** des transactions de comptabilité.

### <a name="ecrituredate--posting-date-of-the-accounting-entry"></a>EcritureDate – Date de validation de l’entrée comptable

Le champ `EcritureDate` représente la valeur du champ `AccountingDate` de l’enregistrement de table `GeneralJournalEntry` lié à chaque transaction des états. Dans l’interface utilisateur (IU) de Finance, cette valeur de champ peut être affichée dans le champ **Date** des transactions de comptabilité.

### <a name="comptenum--account-number-the-first-three-characters-of-which-must-correspond-to-figures-that-respect-the-standards-of-the-french-chart-of-accounts"></a>CompteNum – Le numéro de compte dont les trois premiers caractères doivent correspondre à des chiffres respectant les normes du plan comptable français

Le champ `CompteNum` représente la valeur du champ `MainAccountID` de l’enregistrement de table `MainAccount` lié au champ `MainAccount` de la table `GeneralJournalAccountEntry` qui est lié à chaque transaction des états. Dans l’interface utilisateur (IU) de Finance, cette valeur de champ peut être affichée dans le champ **Compte principal** des transactions de comptabilité.

### <a name="comptelib--account-name-in-accordance-with-the-nomenclature-of-the-french-chart-of-accounts"></a>CompteLib – Nom du compte selon la nomenclature du plan comptable français

Le champ `CompteLib` représente la valeur en français du champ `Name` de l’enregistrement de table `MainAccount` lié au champ `MainAccount` de la table `GeneralJournalAccountEntry` qui est lié à chaque transaction des états. La traduction française est extraite de l’enregistrement `MainAccountTranslation` de table lié à l’enregistrement de la table `MainAccount`. Si aucune traduction n’est stockée pour un enregistrement de table `MainAccount`, la valeur du champ `Name` de la table `MainAccount` est signalée. Dans l’interface utilisateur (IU) de Finance, cette valeur de champ peut être affichée dans le champ **Nom du compte** des transactions de comptabilité.

### <a name="compauxnum--auxiliary-account-number"></a>CompAuxNum – Numéro de compte auxiliaire

La valeur du champ `CompAuxNum` est collectée à partir de plusieurs sources de données dans Finance :

1. Pour les transactions des états du type de validation *Solde client*, *Règlement client* ou *Remboursement client*, ce champ représente le champ `AccountNum` de l’enregistrement de table `CustTable` lié par la valeur `AccountNum` à l’enregistrement de table `CustTrans` lié par la valeur des champs `subledgerVoucher` et `AccountingDate` à l’enregistrement de la table `GeneralJournalEntry`, ou liés par la valeur des champs `Voucher` et `AccountingDate` de la table `GeneralJournalEntry` à l’enregistrement de la table `subledgerVoucherGeneralJournalEntry`, où l’enregistrement de table `subledgerVoucherGeneralJournalEntry` est connecté avec l’enregistrement de table `GeneralJournalEntry` par la valeur `generalJournalEntry.RecId`. Dans l’interface utilisateur (IU) de Finance, cette valeur de champ peut être affichée dans le champ **Compte** des données principales du client
2. Pour déclarer les opérations du type de validation *Solde fournisseur* ou *Règlement client*, ce champ représente le champ `AccountNum` de l’enregistrement de table `VendTable` lié par la valeur `AccountNum` à l’enregistrement de table `VendTrans` lié par la valeur des champs `subledgerVoucher` et `AccountingDate` à l’enregistrement de la table `GeneralJournalEntry`, ou liés par la valeur des champs `Voucher` et `AccountingDate` de la table `GeneralJournalEntry` à l’enregistrement de la table `subledgerVoucherGeneralJournalEntry`, où l’enregistrement de table `subledgerVoucherGeneralJournalEntry` est connecté avec l’enregistrement de table `GeneralJournalEntry` par la valeur `generalJournalEntry.RecId`. Dans l’interface utilisateur (IU) de Finance, cette valeur de champ peut être affichée dans le champ **Compte** des données principales du fournisseur.
3. Pour les transactions des états d’autres types de comptabilisation, cette valeur de champ est vide.

### <a name="compauxlib--auxiliary-account-description"></a>CompAuxLib – Description du compte auxiliaire

Le champ `CompAuxLib` représente le champ `Name` de l’enregistrement de table `dirPartyTable` lié à la valeur définie pour le champ `CompAuxNum` du rapport, où la table `dirPartyTable` est connectée à `CustTable` et `VendTable` via le champ `Party`. Dans l’interface utilisateur (IU) de Finance, cette valeur de champ peut être visualisée dans le champ **Nom** des données de base client ou fournisseur.

### <a name="pieceref--reference-of-the-supporting-document"></a>PieceRef – Référence de la pièce justificative

La valeur du champ `PieceRef` est collectée à partir de plusieurs sources de données dans Finance :

1. Le champ `Invoice` représente la valeur de champ de la table `VendorTrans` liée à l’enregistrement de table `GeneralJournalEntry` par les champs `subledgerVoucher` et `AccountingDate` de la table `GeneralJournalEntry`. Dans l’interface utilisateur Finance, cette valeur de champ peut être affichée dans le champ **Facture d’achat** du journal des factures dans le module **Comptabilité fournisseur**.
2. Le champ `Invoice` représente la valeur de champ de la table `CustTrans` liée à l’enregistrement de table `GeneralJournalEntry` par les champs `subledgerVoucher` et `AccountingDate` de la table `GeneralJournalEntry`. Dans l’interface utilisateur Finance, cette valeur de champ peut être affichée dans le champ **Facture d’achat** du journal des factures dans le module **Comptabilité client**.
3. Le champ `DocumentNumber` ou, si le champ `DocumentNumber` est vide, le champ `subledgerVoucher` de la table `GeneralJournalEntry`. Dans l’interface utilisateur Finance, cette valeur de champ peut être affichée dans le champ **Document** ou, si le champ **Document** est vide, le champ **Pièce justificative** des transactions de comptabilité.

### <a name="piecedate--date-of-the-supporting-document"></a>PieceDate – Date de la pièce justificative

La valeur du champ `PieceDate` est collectée à partir du champ `DocumentDate` ou `AccountingDate` de la table `GeneralJournalEntry` dans Finances. Dans l’interface utilisateur (IU) de Finance, cette valeur de champ peut être affichée dans le champ **Date du document** ou **Date** des transactions de comptabilité.

### <a name="ecriturelib--wording-of-the-accounting-entry"></a>EcritureLib – Formulation de l’écriture comptable

La valeur du champ `EcritureLib` est collectée à partir de plusieurs sources de données dans Finance :

1. Le champ `Text` de l’enregistrement de table `GeneralJournalAccountEntry` lié à chaque transaction des états.
2. Si le champ `Text` de la table `GeneralJournalAccountEntry` est vide, l’application de finances collecte la valeur de champ `Text` de la table `TransactionLogTable` liée par le champ `createdTransactionId` de la table `GeneralJournalAccountEntry`.
3. Si les deux champs `Text` sont vides, la valeur de ce champ est "N/A".

Si char(10) ou char(32) est inclus dans la valeur `Text` dans Finance, elle est exclue de la valeur dans les rapports.

Dans l’interface utilisateur (IU) de Finance, cette valeur de champ peut être affichée dans le champ **Description** des transactions de comptabilité.

### <a name="montant--debit-or-credit-amount"></a>Montant – Montant de débit ou de crédit

La valeur du champ `Montant` représente la valeur absolue du champ `AccountingCurrencyAmount` de l’enregistrement de table `GeneralJournalAccountEntry` lié à chaque transaction des états. Dans l’interface utilisateur (IU) de Finance, cette valeur de champ peut être affichée dans le champ **Montant** des transactions de comptabilité.

### <a name="sens--direction-d--debit-c--credit"></a>Sens – Direction (D = débit, C = crédit)

La valeur du `Sens` est calculée de la manière suivante :

1. Le `AccountingCurrencyAmount` = **0** dans l’enregistrement qui est lié à la transaction des états, ce champ représente la valeur du champ `IsCredit` de `GeneralJournalAccountEntry`.
2. Si `AccountingCurrencyAmount` \< 0 et `IsCorrection` = **No**, ce champ représente "C".
3. Si `AccountingCurrencyAmount` \> 0 et `IsCorrection` = **Yes**, ce champ représente "C".
4. Dans d’autres cas où `IsCredit` = **Yes** et `IsCorrection` = **Yes**, ce champ représente "D".
5. Dans d’autres cas où `IsCredit` = **No** et `IsCorrection` = **No**, ce champ représente "D".
6. Dans tous les autres cas, ce champ représente "C".

### <a name="ecriturelet--lettering-of-the-accounting-entry"></a>EcritureLet – Lettrage de l’écriture comptable

La valeur du champ `EcritureLet` est signalée pour les transactions de comptabilité du type de validation *Solde client* ou *Solde fournisseur*. Il est collecté à partir de plusieurs sources de données dans Finance :

1. Si la valeur du champ `JournalCategory` de l’enregistrment de la table `GeneralJournalEntry` est **Paiement**, le titre de paiement est représenté dans le champ `EcritureLet` par la même valeur que celle utilisée dans le champ `EcritureNum` du rapport.
2. Pour les autres valeurs du champ `JournalCategory` de l’enregistrement de table `GeneralJournalEntry`, Finance représente la valeur du champ `OffsetTransVoucher` de la table `VendSettlement` ou la table `CustSettlement` par les champs `RecId`, `AccountNum` et `DataAreaID` à la table `VendTrans` ou `CustTrans` s’il y a un enregistrement dans la table `VendSettlement` ou la table `CustSettlement` au cours de la période de reporting. Dans l’interface utilisateur Finance, cette valeur de champ peut être affichée dans le champ **Pièce justificative** des transactions comptables qui ont été validées pour le dernier paiement réglé au cours de la période de reporting. Si plusieurs pièces justificatives sont incluses dans le décompte, ils sont séparés par une virgule.

### <a name="datelet--lettering-date"></a>DateLet – Date du lettrage

La valeur du champ `DateLet` est signalée pour les transactions de comptabilité du type de validation *Solde client* ou *Solde fournisseur*. Il est collecté à partir de plusieurs sources de données dans Finance :

1. Si la valeur du champ `JournalCategory` de l’enregistrement de table `GeneralJournalEntry` est **Paiement**, le champ représente la même valeur que le champ de l’état `EcritureDate`.
2. Pour les autres valeurs du champ `JournalCategory` de l’enregistrement de table `GeneralJournalEntry`, Finance représente la dernière valeur au cours de la période de rapport du champ `TransDate` du champ `CustSettlement.TransDate`, `VendSettlement.TransDate` (date comptable de décompte) à partir de la table `VendSettlement` ou `CustSettlement` qui est liée à l’enregistrement de la table `VendSettlement` ou `CustSettlement` liée par les champs `RecId`, `AccountNum` et `DataAreaID` à la table `VendTrans` ou `CustTrans` s’il y a un enregistrement dans la table `VendSettlement` ou la table `CustSettlement` au cours de la période de reporting. Dans l’interface utilisateur Finance, cette valeur de champ peut être affichée dans le champ **Date** du dernier paiement réglé au cours de la période de reporting.

### <a name="validdate--validation-date-of-the-accounting-entry"></a>ValidDate – Validation de l’entrée comptable

Le champ `ValidDate` représente la valeur du champ `CreatedDateTime` de l’enregistrement de table `GeneralJournalEntry` lié à chaque transaction des états. Les transactions comptables sont classées à cette date dans le rapport des types d’exploitation. Dans l’interface utilisateur (IU) de Finance, cette valeur de champ peut être affichée dans le champ **Date et heure de création** des transactions de comptabilité.

### <a name="montantdevise--amount-in-currency"></a>Montantdevise – Montant retenu en devise de base

Le champ `Montantdevise` représente la valeur du champ `TransactionCurrencyAmount` de l’enregistrement de table `GeneralJournalAccountEntry` lié à chaque transaction des états. Dans l’interface utilisateur (IU) de Finance, cette valeur de champ peut être affichée dans le champ **Montant dans la devise de transaction** des transactions de comptabilité.

### <a name="idevise--currency-identifier"></a>Idevise – Identifiant de la devise

Le champ `Idevise` représente la valeur du champ `TransactionCurrencyCode` de l’enregistrement de table `GeneralJournalAccountEntry` lié à chaque transaction des états. Dans l’interface utilisateur (IU) de Finance, cette valeur de champ peut être affichée dans le champ **Devise** des transactions de comptabilité.
