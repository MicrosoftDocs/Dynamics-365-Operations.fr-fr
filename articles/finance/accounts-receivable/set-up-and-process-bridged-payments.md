---
title: Configuration et traitement des paiements en transition
description: Cet article explique comment paramétrer et traiter les paiements clients en transition. Un paiement en transition est un paiement qui est validé dans la comptabilité en deux étapes.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode, VendPaymMode, LedgerJournalTable, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, LedgerJournalTransDaily
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f0609e333fb16ba189b6a971f88fbb5bf900fec
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887975"
---
# <a name="set-up-and-process-bridged-payments"></a>Configurer et traiter les paiements en transition

[!include [banner](../includes/banner.md)]

Un paiement en transition est un paiement qui est validé dans la comptabilité en deux étapes. Généralement, cette approche est utilisée lorsque le mode de paiement est défini sur **Banque**, et que vous ne devez valider les transactions sur le compte bancaire que lorsque la transaction a été compensée par la banque. Cependant, vous pouvez également l’utiliser pour un compte général. Dans ce cas, le système transfère le montant d’un compte principal à un autre compte principal lors du traitement de l’écriture de transition.

Vous pouvez créer des paiements en transition à partir de la Comptabilité fournisseur ou de la Comptabilité client. Bien que cet article explique comment configurer la validation en transition pour la comptabilité client, les étapes pour les transactions de la comptabilité fournisseur sont similaires.

## <a name="set-up-bridging-posting"></a>Configuration de la validation en transition

Pour utiliser la validation en transition, vous devez configurer un ou plusieurs modes de paiement afin qu’ils utilisent la méthode **Validation en transition**. Vous devez ensuite sélectionner un compte de transition.

1. Accédez à **Comptabilité client &gt; Paramétrage des paiements &gt; Modes de paiement**.
2. Sélectionnez un mode de paiement existant pour lequel activer la validation en transition. Sinon, créez un mode de paiement.
3. Cochez la case **Validation en transition**.
4. Dans le champ **Compte de transition**, sélectionnez le compte principal sur lequel les paiements doivent être imputés avant qu’ils ne soient compensés sur le compte bancaire.
5. Fermez la page.

## <a name="process-and-transfer-bridging-posting"></a>Traiter et transférer une validation en transition

Pour créer et traiter une validation en transition, procédez comme suit.

1. Accédez à **Comptabilité client &gt; Paiements &gt; Journal des paiements client**.
2. Sélectionnez **Nouveau** pour créer un journal.
3. Dans le champ **Nom**, sélectionnez un nom.
4. Ajoutez des lignes au journal des paiements client et sélectionnez le mode de paiement configuré pour la validation en transition.
5. Valider le journal. Les transactions seront comptabilisées sur le compte principal que vous avez sélectionné dans le champ **Compte de transition** dans la procédure précédente.

Lorsque les transactions ont été compensées par la banque et que vous souhaitez transférer le paiement du compte de transition vers le compte de paiement spécifié pour le mode de paiement, procédez comme suit.

1. Allez dans **Comptabilité &gt; Entrées de journal &gt; Journaux des opérations diverses**.
2. Sélectionnez **Nouveau** pour créer un journal.
3. Dans le champ **Nom**, sélectionnez un nom.
4. Sélectionnez **Lignes** pour ouvrir les détails du journal.
5. Sélectionnez **Fonctions &gt; Sélectionner les transactions en transition**.
6. Marquez chaque paiement qui a été compensé, puis sélectionnez **Accepter**.
7. Valider le journal.
