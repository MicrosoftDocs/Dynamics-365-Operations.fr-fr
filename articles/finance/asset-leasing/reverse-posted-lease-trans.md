---
title: Contrepasser les transactions de bail validées
description: Cette rubrique explique comment Contrepasser une transaction de location validée. Toute transaction créée via la location d’actifs peut être annulée.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseLeaseTransactions
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 55eb7c5f2419bf1cb2ac0a33a82ab931a3ef380f
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881540"
---
# <a name="reverse-posted-lease-transactions"></a>Contrepasser les transactions de bail validées

[!include [banner](../includes/banner.md)]

Toute transaction créée via la location d’actifs peut être annulée. Les transactions annulées via la location d’actifs mettent à jour vos données de location. Par conséquent, elles mettent également à jour les valeurs comptables du passif locatif et du droit d’utilisation de l’actif.

Pour créer une transaction de contrepassation pour une location, procédez comme suit.

1. Sur la page **Transactions d’actifs** ou la page **Transactions de passif**, sélectionnez la transaction, puis sélectionnez **Contrepasser la transaction**.
2. Dans la boîte de dialogue qui apparaît, vous pouvez modifier la date à laquelle l’écriture de contrepassation sera validée. Par défaut, le champ **Date** est défini sur la date comptable de la transaction que vous avez sélectionnée. L’écriture de contrepassation ne peut pas être validée avant la date comptable d’origine de la transaction sélectionnée.
3. Cliquez sur **OK**. Une entrée de journal est validée qui annule l’écriture que vous avez sélectionnée. La Contrepassation est indiquée sur la page **Transactions d’actifs** ou **Transactions de passif** et le total net du solde actuel affiché sur la page est mis à jour.

Lorsque vous sélectionnez **Suivi de la Contrepassation**, une boîte de dialogue apparaît et affiche à la fois les transactions d’origine et les transactions annulées, ainsi qu’un numéro lié appelé *Numéro de trace*. Pour faciliter la compréhension des annulations et améliorer la visibilité, vous pouvez également suivre les annulations à l’aide des échéanciers de location.

Le champ **Dernier numéro de journal** sur la page **Échéancier** affiche les numéros de journal des transactions. Lorsqu’une transaction est annulée, ce champ est mis à jour avec le numéro de journal d’une transaction d’annulation. De plus, la case **Contrepassé** est cochée pour indiquer que la transaction est annulée et le champ **Validé** est sélectionné.

## <a name="revoke-a-reversed-transaction"></a>Annuler une transaction contrepassée

Pour révoquer une transaction Contrepassée, procédez comme suit.

1. Sur la page **Échéancier** ou la page **Transactions**, sélectionnez la transaction d’origine.
2. Utilisez l’une des procédures suivantes :

    - Si vous avez sélectionné la transaction sur la page **Échéancier**, suivez les étapes de création d’un journal dans [Créer des entrées de journal mensuelles dans un lot](create-monthly-journals-batch.md). Vous devez valider manuellement le journal.
    - Si vous avez sélectionné la transaction sur la page **Transactions**, sélectionnez **Contrepasser la transaction**. Vous recevez un message indiquant que cette révocation est une révocation d’une contrepassation antérieure et que vous pouvez modifier la date comptable de cette révocation. Cependant, les validations commerciales générales affectent les dates qui peuvent être saisies dans le champ **Date**. 

3. Cliquez sur **OK**. Une entrée de journal est validée qui annule l’écriture que vous avez sélectionnée. La Contrepassation est indiquée sur la page **Transactions**, et le solde courant total net est rétabli à ce qu’il était avant la première Contrepassation. Par conséquent, l’impact de la contrepassation sur les soldes est annulé.

Lorsque vous sélectionnez **Suivi de la Contrepassation**, une boîte de dialogue apparaît et affiche à la fois les transactions d’origine et les transactions annulées, ainsi qu’un numéro de trace.

Vous pouvez également suivre les révocations en utilisant la page **Échéanciers**. Le champ **Contrepasser** est effacé, alors que le champ **Journal validé** est sélectionné. De plus, le champ **Dernier numéro de journal** est mis à jour avec le numéro de journal de la transaction de révocation et le champ **Numéro de journal** est mis à jour avec le numéro de journal de contrepassation.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
