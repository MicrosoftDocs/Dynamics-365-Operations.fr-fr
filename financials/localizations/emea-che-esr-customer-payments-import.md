---
title: Importation de paiements client ESR
description: Cette rubrique fournit des informations sur l&quot;importation de paiements client au format ESR.
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustPaymMode, LedgerJournalTransCustPaym
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264584
ms.assetid: 60c429b5-1d88-4fef-be6b-b8585e0e9ee7
ms.search.region: Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f7fd20ef0c78bc781f0ef9f17fc612723906ac78
ms.openlocfilehash: 87643da8ef213f72740370a52d500d9f6fb2fcf2
ms.lasthandoff: 03/31/2017


---

# <a name="esr-customer-payments-import"></a>Importation de paiements client ESR

Cette rubrique fournit des informations sur l'importation de paiements client au format ESR.

L'ESR est un service électronique de débit qui utilise les bordereaux de paiement pour collecter espèces. Il s'agit du système standard de paiement électronique créé par le valider suisse. Vous pouvez recevoir des fichiers de paiement client au format ESR, qui peut inclure des transactions et des frais bancaires. Cette fonctionnalité est prévue pour les références de paiement importées de transactions client selon qui ont été générées dans Microsoft Dynamics 365 pour les opérations et imprimées sur le bordereau de paiement.

## <a name="generate-payment-references"></a>Générer les références de paiement
Les références de paiement doivent être imprimées sur le bordereau de paiement après validation. Vous pouvez également vérifier les références de paiement sur ** journal des factures ** la page de la commande client sélectionnée. Pour générer des références de paiement, les paramètres suivants doivent être spécifiées.

1.  Les paramètres définissez compte bancaire ** ESR **, ** ID BESR, ** et ** numéro d'acheminement **.
2.  Définissez ** nombre de caractères pour le compte de virement ** le champ sous ** des paramètres de ventes ** la page sur ** comptabilité et taxe ** l'onglet. Celui-ci définit le nombre de symboles du compte client doivent être inclus dans la référence de paiement.
3.  La souche de numéros de facture client doit être au format approprié (elle ne doit pas avoir des symboles autres que des chiffres et elle ne doit pas contenir des zéros non significatifs).
4.  ** Orange ** le format doit être spécifié pour le compte client dans ** Dans une facture client ** le champ sous ** facture et livraison ** l'onglet.

Pour plus d'informations, voir [état de bordereau de paiement (Bank Giro)](emea-eur-payment-slip-report-giro.md).

## <a name="import-a-payment-file"></a>Importez un fichier de paiement
1.  Allez ** journal des paiements ** à la page
2.  Cliquez sur **Lignes**.
3.  Cliquez sur ** fonctions ** &gt; ** paiements d'importation **.
4.  Dans la boîte de dialogue, sélectionnez le mode de paiement, puis naviguez jusqu'à l'emplacement du fichier vers l'importation. 
  > [!NOTE]
  >  Avant de pouvoir effectuer cette étape, vous devez avoir déjà importé ** ESR (ch) ** les configurations des Lifecycle Services (LCS) et paramétrer le mode de paiement ESR. Pour plus d'informations, voir [des formats de fichiers pour le mode de paiement] (emea-select-file-formats-for-the-method-of-payments.md).

Après avoir importé le fichier de paiement, des lignes de journal des paiements sont créées et marquées pour règlement avec des factures client selon la référence de paiement. Si des frais spécifiés pour le compte bancaire qui sont représentés dans le fichier, tel que des transactions entre le compte principal et le compte de frais, ces frais sont ajoutés au journal.


