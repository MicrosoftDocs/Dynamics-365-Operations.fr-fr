---
title: Paramétrage de lettres de change
description: Cet article décrit la procédure de paramétrage des lettres de change.
author: ShivamPandey-msft
ms.date: 09/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustBillOfExchangeJour
audience: Application User
ms.reviewer: kfend
ms.custom: 269964
ms.assetid: f2077165-da90-4359-ab12-e05717728dc7
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 91821b10afe7cdbabd0a58b61219ce29d686c5c9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874723"
---
# <a name="set-up-bills-of-exchange"></a>Paramétrage de lettres de change

[!include [banner](../includes/banner.md)]

Cet article décrit la procédure de paramétrage des lettres de change.

Une lettre de change est un ordre écrit ou électronique d’un client spécifiant qu’un tiers, généralement une banque, doit payer un montant défini à la société. Lorsque vous utilisez une lettre de change pour payer une facture de commande client ou une facture financière, vous créditez le compte client. Ce crédit est sécurisé par la lettre de change jusqu’à ce que le client paie cette dernière à la banque. En général, vous réglez la facture avec une lettre de change à la date d’échéance. Lorsque vous recevez une notification de la banque vous informant que la lettre de change a été honorée, vous pouvez la clôturer. Vous pouvez créer une lettre de change via votre banque à l’un des moments suivants :

-   à la date d’échéance. Cette procédure est appelée remise à l’encaissement.
-   avant la date d’échéance, en général à la date de remise spécifiée dans les conditions de paiement paramétrées pour le client. Lorsque vous validez la transaction, le montant de remise est validé dans un compte de dépense. Le montant restant constitue un passif pour vous, jusqu’à ce que la banque reçoive le paiement du client. Cette procédure est appelée remise à l’escompte.

## <a name="set-up-posting-profiles-for-bills-of-exchange"></a>Paramétrer les profils de validation des lettres de change

La page **Profils de validation client** permet de paramétrer des profils de validation à utiliser avec les lettres de change, les lettres de change impayées, les remises à l’encaissement et les remises à l’escompte : Dans le champ **Compte collectif**, sélectionnez le compte collectif sur lequel valider les montants des lettres de change. Ce compte est débité ou crédité, selon du type de transaction de lettre de change :
-   Pour les lettres de change, ce compte est débité lorsqu’une lettre de change est validée et il est crédité lorsqu’une remise à l’escompte ou une remise à l’encaissement est validée.
-   Pour les lettres de change impayées, ce compte est débité lorsqu’une lettre de change impayée est validée.
-   Pour les remises à l’encaissement, ce compte est débité lorsqu’une remise à l’encaissement est validée.
-   Pour les remises à l’escompte, ce compte est débité lorsqu’une remise à l’escompte est validée.

Dans le champ **Compte de règlement**, sélectionnez le compte de disponibilités sur lequel valider les montants des lettres de change. Ce compte est débité lorsqu’une lettre de change est réglée. Dans le champ **Acomptes de taxe**, sélectionnez le compte collectif sur lequel valider les montants des taxes lorsque les lettres de change sont utilisées pour les acomptes. Dans le champ **Compte d’engagements de remise**, sélectionnez le compte sur lequel valider le montant de la remise pour les remises à l’escompte. Ce compte est crédité lorsqu’une remise à l’escompte est validée.

## <a name="set-up-accounts-receivable-parameters-for-bills-of-exchange"></a>Définition des paramètres de la comptabilité client pour les lettres de change

Dans la page **Paramètres de la comptabilité client**, les profils de validation par défaut pour les lettres de change sont entrés dans l’onglet **Comptabilité et taxe**. Les souches de numéros sont définies dans l’onglet **Souches de numéros**.

## <a name="set-up-journal-names-for-bills-of-exchange"></a>Paramétrage du nom des journaux des lettres de change


Dans la page **Noms de journal**, créez au moins cinq noms de journal à utiliser pour les lettres de change. Les types de journaux sont les suivants :
-   **Création de lettre de change client** – Crée un nom de journal pour le journal de création des lettres de change.
-   **Contestation de lettre de change client** – Crée un nom de journal pour le journal de contestation des lettres de change.
-   **Renouvellement de lettre de change client** – Crée un nom de journal pour le journal de renouvellement des lettres de change.
-   **Remise en banque client** – Crée un nom de journal pour le journal des remises.
-   **Règlement de lettre de change client** – Crée un nom de journal pour le journal de règlement des lettres de change.

Sur la page N° document de journal pour chaque journal des lettres de change, saisissez les informations relatives à la lettre de change dans l’onglet **Lettre de change**. Après la publication des lignes de journal des lettres de change, vous pouvez les consulter sur la page **Recherche dans le journal de lettres de change** et la page **Statistiques des lettres de change**.

## <a name="set-up-methods-of-payment-for-bills-of-exchange"></a>Paramétrage de modes de paiement pour les lettres de change

Dans la page **Modes de paiement**, paramétrez au moins un mode de paiement pour les lettres de change. Si vous faites affaires avec plusieurs banques, paramétrez un mode de paiement qui correspond au format de remise de lettre de change demandé par chaque banque.

## <a name="set-up-payment-fees-for-bills-of-exchange"></a>Paramétrage des frais de paiement des lettres de change

Les frais de paiement sont les frais associés au processus de collecte des paiements réalisé auprès des clients. Il est possible d’associer plusieurs lignes de paramétrage de frais de paiement à chaque frais de paiement. Les lignes de paramétrage permettent de contrôler la procédure de calcul des montants par défaut pour les frais de paiement. Par exemple, vous pouvez créer des lignes de paramétrage pour les modes de paiement, les spécifications de paiement, les devises et les périodes. Vous pouvez également créer des lignes de paramétrage pour un pourcentage ou un montant basé sur des intervalles en jours. Par exemple, vous pouvez paramétrer un pourcentage d’intérêt basé sur la longueur d’un retard de paiement. Si la banque facture des frais différents pour les différents types de remises, tels que **Relance** ou **Remise**, paramétrez une ligne de frais de paiement séparée pour chaque type de remise.

## <a name="set-up-remittance-fees-for-bank-remittance-files"></a>Paramétrage des frais de remise pour les fichiers de remise en banque

Dans la page **Comptes bancaires**, vous pouvez paramétrer les frais de remise facturés par une banque pour chaque fichier de remise généré. Les frais de remise sont validés lorsque la remise a été confirmée et que les montants des frais réalisés sont connus. Les frais de remise diffèrent des frais de paiement, lesquels sont collectés auprès des clients et associés aux lignes de journal.

## <a name="set-up-document-layouts-for-bills-of-exchange"></a>Paramétrage des modèles de document des lettres de change

Dans la page **Comptes bancaires**, cliquez sur **Paramétrer**, puis spécifiez le modèle de document requis pour chaque compte bancaire pour lequel vous allez générer des documents de lettre de change imprimés.

## <a name="set-up-customers-for-bills-of-exchange"></a>Paramétrage des clients pour les lettres de change

Dans la page **Clients**, pour chaque client qui a accepté de payer à l’aide d’une lettre de change, vous pouvez paramétrer un mode de paiement par défaut pour les lettres de change sous l’onglet **Valeurs par défaut de paiement**.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
