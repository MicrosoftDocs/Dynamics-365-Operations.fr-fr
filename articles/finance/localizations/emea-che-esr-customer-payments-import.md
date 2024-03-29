---
title: Importation des paiements client ESR
description: Cet article fournit des informations sur l’importation de paiements client au format ESR.
author: AdamTrukawka
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Switzerland
ms.author: atrukawk
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 264584
ms.search.form: CustPaymMode, LedgerJournalTransCustPaym
ms.openlocfilehash: eadaff19f28232673bf26b0b3993af7e20528bef
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278266"
---
# <a name="esr-customer-payments-import"></a>Importation des paiements client ESR

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur l’importation de paiements client au format ESR.

ESR est un service de débit électronique qui utilise des bordereaux de paiement pour collecter de l’argent. Il s’agit du système standard de paiement électronique créé par la Poste suisse. Vous pouvez recevoir les fichiers de paiement client au format ESR, qui peuvent inclure les transactions et les frais bancaires. Cette fonctionnalité est destinée aux transactions client importées basées sur les références de paiement initialement générées dans Dynamics 365 Finance et imprimées sur le bordereau de paiement.

## <a name="generate-payment-references"></a>Générer les références de paiement
Les références de paiement doivent être imprimées sur le bordereau de paiement après validation. Vous pouvez également vérifier les références de paiement dans la page **Journal des factures** pour la commande client sélectionnée. Pour générer les références de paiement, les paramètres suivants doivent être spécifiés.

1.  Définissez les paramètres de compte bancaire sur **ESR**, **ID BESR** et **Numéro d’acheminement**.
2.  Définissez le champ **Nombre de caractères du compte de virement** sur la page **Paramètres de la comptabilité client** sur l’onglet **Comptabilité et taxe**. Cela définit combien de symboles du compte client doivent être inclus dans la référence de paiement.
3.  La souche de numéros de la facture client doit être au format approprié (elle ne doit pas comporter des symboles autres que des chiffres et elle ne doit pas contenir des zéros non significatifs).
4.  Le format **Orange** doit être spécifié pour le compte client dans le champ **Sur une facture client** de l’onglet **Facture et livraison**.

Pour plus d’informations, voir [État du bordereau de paiement pour l’Europe](emea-eur-payment-slip-report-giro.md).

## <a name="import-a-payment-file"></a>Importer un fichier de paiement
1. Accédez à la page **Journal des paiements**.
2. Cliquez sur **Lignes**.
3. Cliquez sur **Fonctions** &gt; **Importer les paiements**.
4. Dans la boîte de dialogue, sélectionnez le mode de paiement, puis accédez à l’emplacement du fichier à importer. 
   > [!NOTE]
   >  Avant de pouvoir effectuer cette étape, vous devez avoir déjà importé les configurations **ESR (CH)** à partir de Lifecycle Services (LCS) et paramétré le mode de paiement ESR. Pour plus d’informations, voir [Formats de fichier des modes de paiement](emea-select-file-formats-for-the-method-of-payments.md).

Après avoir importé le fichier de paiement, les lignes du journal des paiements sont créées et marquées pour règlement avec les factures client basées sur la référence de paiement. Si des frais spécifiés pour le compte bancaire sont représentés dans le fichier, par exemple les transactions entre le compte principal et le compte de frais, ces frais seront ajoutés au journal.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
