---
title: "Vue d&quot;ensemble du rapprochement de relevé de compte bancaire et le paiement de l&quot;UE"
description: "Cette rubrique fournit une vue d&quot;ensemble de la fonctionnalité que vous pouvez utiliser pour rapprocher les informations de paiement des banques dans les formats utilisés par les pays européens."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankAccountTable, CustPaymMode, VendPaymMode
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267994
ms.assetid: 2bfb8ecc-e850-43cb-9a96-deb11716a391
ms.search.region: Belgium, Norway, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 22d93d7b3618d4f5931c6a7e39d681173734b0b9
ms.lasthandoff: 03/31/2017


---

# <a name="bank-statement-and-payment-reconciliation-overview-for-the-eu"></a>Vue d'ensemble du rapprochement de relevé de compte bancaire et le paiement de l'UE

Cette rubrique fournit une vue d'ensemble de la fonctionnalité que vous pouvez utiliser pour rapprocher les informations de paiement des banques dans les formats utilisés par les pays européens.

Dans Microsoft Dynamics 365 pour les opérations, vous pouvez importer des transactions des banques et régler ces transactions par rapport à les transactions existantes. En Europe, vous pouvez le faire pour les scénarios suivants :

-   Importer des relevés bancaires
-   Importer des paiements.
-   Importation des fichiers de retour.

## <a name="bank-statements"></a>Relevés bancaires
Un statement* de *bank ou le statement* de *account est une synthèse des transactions financières qui ont eu lieu au cours d'une période donnée sur un compte bancaire effectué par une société à une institution financière. Dans Dynamics 365 pour les opérations vous pouvez importer un relevé bancaire. Il est essentielle à des transactions importées par règlement avec les transactions existantes ainsi que vérifie le solde d'ouverture et de fin des comptes bancaires. La liste suivante récapitule les formats européens pris en charge.

-   Formats avancés de dossier de l'Europe de rapprochement bancaire. Pour plus d'informations, voir [vue d'ensemble avancée de rapprochement bancaire (]. /cash-bank-management/advanced-bank-reconciliation-overview.md).
-   Format de fichier de message du relevé bancaire camt.053 ISO 20022
-   Format de fichier de relevé bancaire CODA. Pour plus d'informations, voir [relevés bancaires CODA] (emea-bel-coda-bank-statement-import.md).

## <a name="customer-and-vendor-payments-import-and-return-messages"></a>Client et paiements fournisseur importation et messages retournés
Outre d'un relevé bancaire, les banques peuvent fournir les messages spécifiques, contenant des informations sur les paiements client ou fournisseur, qui peuvent être importés dans Dynamics 365 pour les opérations et être rapprochés avec les transactions client et fournisseur. Lorsqu'une société doit recevoir des informations sur les transactions entrantes de paiements client de la banque, les formats d'importation peuvent être utilisés. Pour les sociétés qui utilisent le transfert de débit et de crédit, les messages retournés peuvent être reçus pour mettre à jour le statut de paiements qui ont été précédemment exportés. Différence entre les formats d'importation et les formats de retour est que les retours sont auxquels la plupart pour mettre à jour les lignes déjà créées de journal des paiements (peuvent être créés lorsque le transfert de débit ou de crédit ont été créés) au lieu de créer des lignes. Certains formats d'importation complexes peuvent également inclure les scénarios de retour. L'exemple suivant montre comment cette division doit être implémentées.

##### <a name="import-formats"></a>Formats d'importation

-   Message de notification de la banque camt.054 ISO 20022
-   [Format d'importation de réseaux] () - emea-nor-nets-import-format.md fonction complexe pour les formats de paiement norvégiens
-   Importation de paiements client ESR
-   Importez les formats de paiement pour la Suède - Le BankGirot des formats maximal et de BankGirot ROC

##### <a name="return-formats"></a>Retour les formats

-   État du statut de paiement pain.002 ISO 20022
-   (DNK) BetalingsserviceBasis-returformat – format de retour pour le format d'exportation de Betalingsservice client
-   [Formats de paiement d'importation pour la Suède] () - emea-swe-payment-formats-import.md Bankgirot Autogiro revient
-   (SWE) retour de BankGirot – format retourné paiements fournisseur, qui correspond au format d'exportation Bankgirot

