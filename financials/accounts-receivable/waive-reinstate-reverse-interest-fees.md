---
title: "Exonération, rétablissement ou contrepassation de commissions d&quot;intérêt"
description: "Cet article explique comment exonérer, rétablir, et contrepasser les frais pour les intérêts et les frais."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 59461
ms.assetid: 25ec29f3-e3ea-4abb-bf6b-f6240873b315
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e25a7657c2b859ffd57313ed7eb8da6583e7130d
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="waive-reinstate-or-reverse-interest-fees"></a>Exonération, rétablissement ou contrepassation de commissions d'intérêt

[!include[banner](../includes/banner.md)]


Cet article explique comment exonérer, rétablir, et contrepasser les frais pour les intérêts et les frais.

Les boutons de l'onglet **Collecter** de la page de liste **Tous les clients** vous permettent d'exonérer, de contrepasser ou de rétablir des frais :

-   Les frais exonérés sont effacés. Vous pouvez par exemple exonérer des frais si un client refuse de les payer et que vous souhaitez conserver de bonnes relations commerciales avec ce client.
-   Les frais rétablis sont de nouveau dus. Vous pouvez rétablir des frais précédemment exonérés. Vous devrez peut-être rétablir des frais si vous déterminez qu'ils ont été exonérés par erreur.
-   Les frais contrepassés sont supprimés du compte client et ne sont plus dus. Vous pouvez par exemple contrepasser des frais si un taux d'intérêt erroné a été sélectionné pour calculer le montant dû par un client. Vous pouvez utiliser une procédure distincte pour recalculer les intérêts et créer une note d'intérêt comportant de nouveaux frais pour le client.

Toutes ces actions modifient une note d'intérêt. Une note d'intérêt est un document commercial qui informe les clients que des frais ou des intérêts ont été facturés sur leur compte. Lorsque vous exonérez ou contrepassez des intérêts ou des frais, un avoir ou une facture d'ajustement est créé automatiquement pour régler les frais. Si vous rétablissez des frais exonérés, une facture ayant un montant débiteur est automatiquement créée pour rétablir les frais dus par le client. Le tableau suivant décrit les résultats de chaque action.

| Action                                                                                                                                                                                                            | Résultat pour le client                                                                                             | Traiter                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Exonérez des notes d'intérêt complètes ainsi l'ensemble des intérêts et des frais qu'elles incluent. –ou– Sélectionnez et exonérez les frais ou les transactions d'intérêt faisant partie des notes d'intérêt.                                        | Les frais sont effacés.                                                                                           | Un avoir ou une facture d'ajustement est créé pour le client. L'avoir permet de régler automatiquement la note d'intérêt ou les transactions d'intérêt ou frais que vous avez sélectionnés. Le montant réglé est égal au montant total des frais, moins les paiements précédents effectués par le client, moins les montants précédemment exonérés ou annulés. Si le montant de l'avoir dépasse le montant dû par le client, vous pouvez convertir l'avoir en facture fournisseur. Vous pouvez ensuite rembourser le client.                                                       |
| Rétablissez des notes d'intérêt complètes avec l'ensemble des intérêts et des frais qu'elles incluent. –ou– Sélectionnez et rétablissez les frais ou les transactions d'intérêt faisant partie des notes d'intérêt.                                | Le montant exonéré est de nouveau dû.                                                                                     | Une facture avec un montant débiteur est créée et le montant est réglé automatiquement en tenant compte des frais précédemment exonérés. Les notes d'intérêt réelles ne sont pas rétablies. Au lieu de cela, une facture est créée. Elle affiche le montant dû par le client. Les avoirs ou les factures d'ajustement créés pour régler des notes d'intérêt exonérées peuvent toujours exister s'ils n'ont pas été utilisés dans le cadre du règlement des notes d'intérêt. Dans ce cas, les avoirs restants sont annulés. Ils sont généralement réglés automatiquement lors de l'exonération des notes d'intérêt. Toutefois, un avoir restant peut exister si un client a payé une note d'intérêt après avoir refusé de payer les charges. |
| Contrepassez des notes d'intérêt complètes. –or– Contrepassez les transactions d'intérêt sélectionnées qui font partie des notes d'intérêt. **Remarque :** Vous ne pouvez pas contrepasser des frais. Toutefois, vous pouvez contrepasser une note d'intérêt complète qui inclut des frais. | Les frais ne sont plus dus par le client. Toutefois, les frais sont de nouveau dus si vous recalculez les intérêts. | La procédure est identique à l'exonération des notes d'intérêt ou des transactions d'intérêt sélectionnées. Un avoir ou une facture d'ajustement est créé pour le client. Cet avoir permet de régler automatiquement la note d'intérêt. Vous pouvez utiliser une procédure distincte pour recalculer les intérêts et créer une note d'intérêt.                                                                                                                                                                                                                                                                                                                                                                                              |

> [!NOTE] 
> Vous pouvez également utiliser une procédure distincte pour annuler les créances irrécouvrables. Ce processus marque toutes les transactions client pour règlement, plutôt que d'exonérer uniquement les frais faisant partie des notes d'intérêt.

## <a name="adjust-interest-for-invoices"></a>Ajustement des intérêts figurant sur les factures
Outre l'ajustement des notes d'intérêt, vous pouvez supprimer les frais d'intérêts des factures par l'intermédiaire de l'une des procédures suivantes Les deux procédures appliquent également des ajustements aux notes d'intérêt associées.

### <a name="correct-an-invoice-that-has-associated-interest"></a>Correction d'une facture à laquelle des intérêts sont associés

Vous pouvez corriger une facture validée incluse dans une note d'intérêt. Cette procédure permet de copier les informations de la facture existante vers une nouvelle facture de manière à apporter uniquement les corrections souhaitées. La facture est annulée et une autre facture est créée. Les intérêts de la transaction sont également contrepassés sur la note d'intérêt, si celle-ci a été validée. 

Vous pouvez apporter la correction par l'intermédiaire du bouton **Corriger la facture** dans le volet Actions de la facture financière. Cet bouton est uniquement disponible si la clé de configuration **Correction de la facture financière** est sélectionnée.

### <a name="reverse-a-customer-transaction-that-has-associated-interest"></a>Contrepassation d'une transaction client à laquelle des intérêts sont associés

Vous pouvez contrepasser une transaction client sur une facture si cette dernière a été créée de manière incorrecte. Si la transaction client contrepassée est associée à des intérêts faisant partie d'une note d'intérêt et que cette dernière a été validée, les intérêts de la transaction sont également contrepassés sur la note d'intérêt. La note d'intérêt est annulée si elle n'a pas été validée. 

Vous pouvez contrepasser des transactions client par l'intermédiaire du bouton **Contrepasser**sur la page **Transactions client**.

## <a name="waive-or-reinstate-interest-notes"></a>Exonération ou rétablissement des notes d'intérêt
Vous pouvez exonérer ou rétablir l'intégralité des frais des notes d'intérêt sélectionnées. Lorsque vous exonérez des frais, le montant total à exonérer ne peut pas dépasser les limites que vous avez définies. Vous pouvez rétablir une note d'intérêt uniquement si celle-ci a été précédemment exonérée. 

Vous pouvez exonérer ou rétablir les notes d'intérêt par l'intermédiaire du bouton **Note d'intérêts** sous l'onglet **Collecter** de la page **Client**.

## <a name="waive-or-reinstate-interest-transactions"></a>Exonération ou rétablissement des transactions d'intérêt
Vous pouvez exonérer ou rétablir des transactions d'intérêt sur une note d'intérêt, plutôt que d'ajuster l'ensemble des frais de cette note d'intérêt. Lorsque vous exonérez des frais, le montant total à exonérer ne peut pas dépasser les limites que vous avez définies. Vous pouvez rétablir une transaction d'intérêt uniquement si celle-ci a été précédemment exonérée. 

Vous pouvez exonérer ou rétablir les notes d'intérêt par l'intermédiaire du bouton **Intérêt de la transaction** sous l'onglet **Collecter** de la page **Client**.

## <a name="waive-or-reinstate-fees"></a>Exonération ou rétablissement des frais
Vous pouvez exonérer ou rétablir des frais spécifiques sur une note d'intérêt, plutôt que d'ajuster l'ensemble des frais de celle-ci. Lorsque vous exonérez des frais, le montant total à exonérer ne peut pas dépasser les limites que vous avez définies. Vous pouvez rétablir des frais uniquement si ceux-ci ont été précédemment exonérés. 

Vous pouvez exonérer ou rétablir les notes d'intérêt par l'intermédiaire du bouton **Frais** sous l'onglet **Collecter** de la page **Client**.

## <a name="reverse-interest-notes"></a>Contrepasser les notes d'intérêt
Vous pouvez contrepasser l'intégralité des frais des notes d'intérêt sélectionnées. Les frais contrepassés sont supprimés du compte client et ne sont plus dus. Une fois la note d'intérêt contrepassée, vous pouvez recalculer les intérêts et créer une note d'intérêt. 

Vous pouvez contrepasser les notes d'intérêt par l'intermédiaire du bouton **Note d'intérêts**sous l'onglet **Collecter** de la page **Client**.

## <a name="reverse-interest-transactions"></a>Contrepassation des transactions d'intérêt
Vous pouvez contrepasser l'intégralité des transactions d'intérêt sélectionnées. Les frais contrepassés sont supprimés du compte client et ne sont plus dus. Une fois les transactions contrepassée, vous pouvez recalculer les intérêts et créer une note d'intérêt.

Vous pouvez contrepasser les transactions d'intérêt par l'intermédiaire du bouton **Intérêt de la transaction** sous l'onglet **Collecter** de la page **Client**.

## <a name="view-the-history-of-adjustments-for-charges-that-were-waived-reinstated-or-reversed"></a>Affichage de l'historique des ajustements pour les frais exonérés, rétablis ou contrepassés
Vous pouvez afficher un historique détaillé des ajustements effectués pour les notes d'intérêt (utilisateur ayant entré l'ajustement, type d'ajustement, montant et date de saisie de l'ajustement). Par exemple, vous pouvez afficher les ajustements précédemment entrés pour une note d'intérêt avant d'en créer une. 

Vous pouvez contrepasser les transactions d'intérêt par l'intermédiaire du bouton **Historique**sous l'onglet **Collecter** de la page **Client**.




