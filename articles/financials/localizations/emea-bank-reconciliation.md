---
title: Rapprochement des relevés bancaires et des paiements pour l'UE
description: Cette rubrique donne une vue d'ensemble de la fonctionnalité permettant de rapprocher les informations de paiement des banques dans les formats utilisés par les pays européens.
author: neserovleo
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, CustPaymMode, VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 267994
ms.search.region: Belgium, Norway, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c6a6e4bfe40f2ced5e9200e963b432c1a5334ef4
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852131"
---
# <a name="bank-statement-and-payment-reconciliation-for-the-eu"></a>Rapprochement des relevés bancaires et des paiements pour l'UE

[!include [banner](../includes/banner.md)]

Cette rubrique donne une vue d'ensemble de la fonctionnalité permettant de rapprocher les informations de paiement des banques dans les formats utilisés par les pays européens.

Dans Microsoft Dynamics 365 for Finance and Operations, vous pouvez importer des transactions bancaires et régler ces transactions avec les transactions existantes. En Europe, vous pouvez le faire pour les scénarios suivants :

-   Importation des relevés bancaires
-   Importation des paiements
-   Importation des fichiers de retour

## <a name="bank-statements"></a>Relevés bancaires
Un *relevé bancaire* ou *relevé de compte* est une synthèse des transactions financières effectuées sur une période donnée sur un compte bancaire détenu par une société avec une institution financière. Dans Finance and Operations, vous pouvez importer un relevé bancaire. Il est important de régler les transactions importées avec les transactions existantes et de vérifier le solde d'ouverture et de fin des comptes bancaires. La liste suivante présente les formats européens pris en charge.

-   Formats du fichier européen de rapprochement bancaire avancé. Pour plus d'informations, voir [Vue d'ensemble du rapprochement bancaire avancé](../cash-bank-management/advanced-bank-reconciliation-overview.md).
-   Format du fichier de message de relevé bancaire ISO 20022 camt.053
-   Format du fichier de relevé bancaire CODA. Pour plus d'informations, voir [Relevé bancaire CODA](emea-bel-coda-bank-statement-import.md).

## <a name="customer-and-vendor-payments-import-and-return-messages"></a>Messages d'importation et de retour des paiements client et fournisseur
Outre un relevé bancaire, les banques peuvent fournir des messages spécifiques, contenant des informations sur les paiements client ou fournisseur, qui peuvent être importés dans Finance and Operations et rapprochés avec les transactions client et fournisseur. Lorsqu'une société doit recevoir des informations sur les transactions de paiements client entrants de la banque, les formats d'importation peuvent être utilisés. Pour les sociétés qui utilisent le transfert de débit et de crédit direct, les messages de retour peuvent être reçus pour mettre à jour le statut des paiements qui ont été précédemment exportés. La différence entre les formats d'importation et les formats de retour est que les retours visent principalement à mettre à jour les lignes de journal des paiements déjà créées (elles peuvent être créées lors du lancement du transfert de débit ou de crédit direct) au lieu de créer de nouvelles lignes. Certains formats d'importation complexes peuvent également inclure des scénarios de retour. L'exemple suivant montre comment cette division doit être implémentée.

### <a name="import-formats"></a>Formats d'importation

-   Message de notification bancaire ISO 20022 [camt.054](emea-ISO20022-file-formats.md)
-   [Format d'importation Nets](emea-nor-nets-import-format.md) - Fonction complexe pour les formats de paiement norvégiens
-   Paiements d'importation client [ESR](emea-che-esr-customer-payments-import.md)
-   Formats de paiement d'importation pour la Suède - Formats OCR BankGirot Max et BankGirot

### <a name="return-formats"></a>Formats de retour

-   État du statut de paiement ISO 20022 [pain.002](emea-ISO20022-file-formats.md)
-   (DNK) BetalingsserviceBasis-returformat – Format de retour pour le format d'exportation Betalingsservice client
-   [Formats de paiement d'importation pour la Suède](emea-swe-payment-formats-import.md) - Retours Bankgirot Autogiro
-   (SWE) Retour BankGirot – Format de retour des paiements fournisseur, qui correspond au format d'exportation Bankgirot


