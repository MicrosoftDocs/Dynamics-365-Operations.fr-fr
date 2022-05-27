---
title: Les performances du calcul de la taxe affectent les transactions
description: Cette rubrique fournit des informations sur la résolution des problèmes liés aux performances du calcul de la taxe et à son effet sur les transactions.
author: shtao
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 1902017a7a00d4cc068f17e23aa21cd1d2b547a7
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695216"
---
# <a name="tax-calculation-performance-affects-transactions"></a>Les performances du calcul de la taxe affectent les transactions

[!include [banner](../includes/banner.md)]

Parfois, une transaction est affectée par des problèmes de performance liés au calcul de la taxe. Pour résoudre ce problème, suivez les étapes des sections suivantes selon les besoins.

## <a name="review-the-transaction-line-count"></a>Examiner le nombre de lignes de transaction

Déterminez si la transaction comporte un grand nombre de lignes (par exemple plusieurs centaines). Si ce n’est pas le cas, passez à la section suivante. Si la transaction comporte plusieurs centaines de lignes, retardez le calcul de la taxe. Pour plus d’informations, consultez [Activer un calcul de taxe différé sur les journaux](enable-delayed-tax-calculation.md). 

Ensuite, vous pouvez déterminer si l’une des conditions suivantes est remplie :

- Il existe des transactions d’importation à partir de fichiers volumineux.
- Plusieurs sessions traitent le même calcul de taxe sur des transactions en même temps.
- La transaction comporte plusieurs lignes et les vues sont mises à jour en temps réel. Par exemple, le champ **Montant de taxe calculé** sur la page **Journal des opérations diverses** est mis à jour en temps réel lorsque les champs d’une ligne sont modifiés.

   [![Champ Montant de taxe calculé sur la page Justificatif de journal.](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)

Si l’une de ces conditions est remplie, retardez le calcul de la taxe.

## <a name="review-the-call-stack"></a>Examiner la pile d’appels

Examinez la pile d’appels pour déterminer si le calcul de la taxe est appelé plusieurs fois. Si ce n’est pas le cas, passez à la section suivante. Si la pile d’appels est appelée plusieurs fois, procédez comme suit pour réduire les temps de calcul de la taxe.

1. Si le journal a pris en compte la transaction, retardez le calcul de la taxe. Pour plus d’informations, consultez [Activer un calcul de taxe différé sur les journaux](enable-delayed-tax-calculation.md).
2. Si la transaction est un bon de commande et que la version de l’application est postérieure à 10.0.15, vous pouvez retarder le calcul de la taxe jusqu’au calcul final en activant le mode Flighting pour **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.

## <a name="review-the-call-stack-timeline"></a>Examiner la chronologie de la pile d’appels

Consultez la chronologie de la pile d’appels pour déterminer si les problèmes suivants existent. Si tel est le cas, activez le mode Flighting pour **TaxUncommittedDoIsolateScopeFlighting** pour résoudre le problème.

- La transaction fait que le système cesse de répondre jusqu’à ce que la session se termine. Par conséquent, la transaction ne peut pas calculer le résultat fiscal. L’illustration suivante montre la boîte de message « Session terminée » que vous recevez.

    [![Message Session terminée.](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)

- Les méthodes **TaxUncommitted** prennent plus de temps que les autres. Par exemple, dans l’illustration suivante, la méthode **TaxUncommitted::updateTaxUncommitted()** prend 43 347,42 secondes, mais les autres méthodes prennent 0,09 seconde.

    [![Durée des méthodes.](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)

## <a name="customizing-and-calling-tax-calculation"></a>Personnalisation et appel du calcul de la taxe

Lorsque vous personnalisez, n’appelez pas le calcul de la taxe pour la méthode **insérer()** ou **mettre à jour()** pour chaque ligne. Le calcul de la taxe doit être appelé au niveau de la transaction.

## <a name="determine-whether-customization-exists"></a>Déterminer si la personnalisation existe

Si vous avez terminé les étapes des sections précédentes mais que vous n’avez trouvé aucun problème, déterminez s’il existe une personnalisation. Si aucune personnalisation n’existe, créez une demande de service Microsoft pour une assistance supplémentaire.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
