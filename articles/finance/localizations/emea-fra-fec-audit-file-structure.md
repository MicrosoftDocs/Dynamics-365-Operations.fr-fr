---
title: Structure des sources de données Dynamics 365 Finance pour le fichier FEC
description: Cette rubrique décrit la structure des sources de données Microsoft Dynamics 365 Finance pour le Fichier des écritures comptables (FEC).
author: liza-golub
ms.date: 10/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.author: elgolu
ms.reviewer: kfend
ms.search.region: France
ms.openlocfilehash: 3574214bd09a351d44dcbeb2e5e75e0983062ad2
ms.sourcegitcommit: 4946b7f250f8b5cd3d09098b08e74bc5763d1c86
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2021
ms.locfileid: "7792596"
---
# <a name="structure-of-dynamics-365-finance-data-sources-for-the-fec"></a>Structure des sources de données Dynamics 365 Finance pour le fichier FEC

Dans Microsoft Dynamics 365 Finance, vous pouvez générer le fichier [FEC principal](#fec-main) (Fichier des écritures comptables) et les annexes suivantes :

- **[Solde client](#customers-balances) :** Annexe sur les soldes d’ouverture de l’exercice des clients
- **[Solde fournisseur](#vendors-balances) :** Annexe sur les soldes d’ouverture de l’exercice des fournisseurs
- **[Transactions client](#customers-transactions) :** Annexe des transactions client pour une période déterminée
- **[Transactions fournisseur](#vendors-transactions) :** Annexe des transactions fournisseur pour une période déterminée

Vous pouvez également générer un fichier FEC qui inclut les soldes d’ouverture des exercices client et fournisseur ([FEC principal étendu](#fec-main-extended)). Utilisez cette option pour les entreprises qui n’ont que quelques enregistrements au cours de la période de reporting. La période de déclaration doit inclure le début de l’exercice financier.

Les sections suivantes répertorient les sources de données utilisées dans le fichier principal et les annexes FEC.

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
