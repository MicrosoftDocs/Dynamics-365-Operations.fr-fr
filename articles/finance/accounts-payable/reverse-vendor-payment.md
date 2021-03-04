---
title: Contrepasser un paiement fournisseur
description: Cet article décrit les différences entre contrepasser, supprimer, annuler et rejeter un paiement. En outre, il détaille les deux méthodes pour contrepasser une vérification fournisseur.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankChequeTable, LedgerJournalTransBankChequeReversal, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14361
ms.assetid: 9f0a1883-cbe0-4cc7-b9f3-dd12fb85ebe8
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: db9208c8e76d963d5b8f6bee6b7c73268af68734
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443122"
---
# <a name="reverse-a-vendor-payment"></a>Contrepasser un paiement fournisseur

[!include [banner](../includes/banner.md)]

Cet article décrit les différences entre contrepasser, supprimer, annuler et rejeter un paiement. En outre, il détaille les deux méthodes pour contrepasser une vérification fournisseur. 

Parfois, après la validation d’un paiement fournisseur, le paiement doit être contrepassé. La contrepassation est différente de la suppression, de l’annulation ou du rejet d’un paiement. Vous pouvez supprimer un paiement uniquement si son statut est **Créé**. Ce statut indique que le paiement a été créé mais n’a pas encore été généré. Cette limitation s’applique toujours, indépendamment du mode de paiement. Vous pouvez annuler les chèques non validés après qu’ils ont été générés mais avant qu’ils n’aient été validés. Si le paiement généré est effectué comme transfert électronique de fonds(TEF), vous pouvez rejeter le paiement avant de l’avoir validé. Pour rejeter un paiement, modifiez la valeur du **Statut du paiement**. Un paiement annulé ou rejeté peut être régénéré après que la valeur **Statut du paiement** a été rétablie à **Aucun**. 

Une fois le paiement validé, les contrepassations sont utilisées. Les paiements effectués par voie électronique ne peuvent pas être contrepassés une fois qu’ils ont été validés. À la place, une nouvelle transaction doit être créée pour le montant du paiement pour redéfinir le passif sur le compte du fournisseur. Il existe deux méthodes pour contrepasser des chèques validés. Dans la première méthode, les contrepassations sont validées immédiatement lorsque vous cliquez sur **Contrepassation de paiement** dans la page **Chèque**. Dans la deuxième méthode, lorsque vous cliquez sur **Contrepassation de paiement** dans la page **Chèque**, la contrepassation est envoyée au journal de contrepassation des chèques du module Gestion des fonds et des banques, dans lequel un réviseur peut valider ou rejeter la contrepassation. 

Pour connaître la méthode utilisée par votre organisation, affichez la page **Paramètres de gestion des disponibilités et des banques**. Si l’option **Utiliser le processus de révision pour les contrepassations de paiement** est définie sur **Oui**, les contrepassations sont envoyées au journal de contrepassation des chèques pour révision. Le tableau suivant décrit les différences entre les méthodes de contrepassation de chèques.

| Si votre organisation ne révise pas les contrepassations de chèques avant la validation                                                                                                                                  | Si votre organisation révise les contrepassations de chèques avant la validation                                                                                                                                                                                                                                                                                                                                                                     |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Le chèque est contrepassé immédiatement lorsque que cliquez sur **OK** dans la page **Chèque**.                                                                                                                      | Le chèque n’est pas immédiatement contrepassé. Un journal de contrepassation des chèques est créé pour révision. Si le journal de contrepassation des chèques est supprimé, le chèque peut être contrepassé de nouveau.                                                                                                                                                                                                                                                                |
| Les écritures comptables pour le chèque original sont contrepassées.                                                                                                                                         | Il se peut que le compte général de l’écriture comptable du chèque d’origine ne soit pas validé. Les dimensions financières du journal du chèque d’origine sont utilisées comme dimensions financières par défaut dans le journal de contrepassation des chèques. Vous pouvez modifier ces valeurs par défaut. Lorsque le journal de contrepassation des chèques est validé, les comptes principaux pour la comptabilité fournisseur sont entrées automatiquement à partir des profils de validation, qui ont peut-être été modifiés. |
| Les structures de compte qui ont été utilisées lorsque le chèque d’origine a été validé sont utilisées pour contrepasser le chèque, même si la structure de compte a été modifiée. La combinaison du compte n’est pas validée. | Si une structure de compte est modifiée une fois le chèque d’origine validé, une nouvelle dimension financière peut être requise pour la contrepassation du chèque. Il se peut que cette dimension financière ne soit pas entrée automatiquement à partir du journal du paiement d’origine. La combinaison du compte est validée lorsque la contrepassation du chèque est validée.                                                                                                        |
| Les dimensions fixes ne sont pas appliquées à la contrepassation, pour garantir que les mêmes comptes généraux sont contrepassés.                                                                                      | Les dimensions fixes sont appliquées au journal de contrepassation des chèques lors de la validation. La valeur de dimension financière peut ne pas exister dans l’écriture comptable pour le chèque d’origine, selon le moment où la dimension fixe a été définie.                                                                                                                                                                                                     |

## <a name="reverse-posted-checks-without-reviewing-them"></a>Contrepasser des chèques validés sans les réviser
Si votre organisation souhaite valider les contrepassations de chèque immédiatement lorsque vous cliquez sur **Contrepassation de paiement** dans la page **Chèques**, procédez comme suit. Dans la page **Paramètres de gestion des disponibilités et des banques**, définissez l’option **Utiliser le processus de révision pour les contrepassations de paiement** sur **Non**. Dans la page **Chèques**, vous pouvez sélectionner le chèque à contrepasser, puis sélectionner **Contrepassation de paiement**. Vous pouvez ensuite entrer la date et sélectionner un motif de contrepassation.

## <a name="reverse-posted-checks-after-they-are-reviewed-in-the-check-reversal-journal"></a>Contrepasser des chèques validés après leur révision dans le journal de contrepassation des chèques
Si votre organisation souhaite réviser les contrepassations de chèque avant leur validation, créez un journal de contrepassation des chèques pour révision. Ensuite, dans la page **Paramètres de gestion des disponibilités et des banques**, définissez l’option **Utiliser le processus de révision pour les contrepassations de paiement** sur **Oui**. Dans la page **Chèques**, vous pouvez sélectionner le chèque à contrepasser, puis sélectionner **Contrepassation de paiement**. Vous pouvez ensuite entrer la date et sélectionner un motif de contrepassation. Le motif financier doit être défini pour le type Banque comme pour le type Fournisseur. Vous devez également sélectionner un nom de journal pour créer un journal dans le journal de contrepassation des chèques.

### <a name="review-a-reversal"></a>Révision d’une contrepassation

Si vous êtes un utilisateur qui doit réviser les contrepassations, vous pouvez approuver et valider le journal ou rejeter la contrepassation en supprimant le journal. Dans la page **Journal de contrepassation des chèques**, vous pouvez sélectionner le journal de contrepassation à réviser, puis cliquer sur **Lignes**. Vous pouvez réviser le chèque contrepassé, puis sélectionner l’une des options d’approbation suivantes :

-   Pour approuver et valider le journal de contrepassation, cliquez sur **Valider** ou **Valider et transférer**.
-   Pour rejeter la contrepassation, supprimez le journal de contrepassation des chèques.

> [!NOTE]
> Si vous supprimez le journal, la contrepassation est supprimée du système, mais le chèque d’origine figure toujours dans la page **Chèque**. Le statut du chèque n’est plus **Annulation en attente**.

## <a name="results-of-posting-a-reversal"></a>Résultats de la validation d’une contrepassation
Lorsque vous validez la contrepassation d’un chèque, les événements suivants se produisent :

-   Le statut du chèque est mis à jour sur **Annulation**.
-   Si l’option **Rapprocher** est sélectionnée dans la page de contrepassation lors de la contrepassation, le chèque est rapproché (l’option **Rapproché** est sélectionnée) et n’apparaît pas dans la page **Rapprochement de compte**.
-   Le n° document de la contrepassation est validé sur le compte bancaire d’où le chèque a été émis, ce qui augmente le solde du compte bancaire.
-   Le N° document est validé dans la comptabilité.
-   Les détails de la modification sont mis à jour dans le groupe de champs **Historique** de la page **Chèque**.

> [!NOTE] 
> Lors de la contrepassation d’un chèque émis pour une transaction commerciale intersociétés, les entrées de contrepartie proviennent du paramétrage comptable pour le commerce intersociétés, et non de la transaction d’origine. Si le chèque contrepassé était émis pour un paiement fournisseur, les événements suivants se produisent également :

-   Le paiement d’origine de la facture pour laquelle le paiement était réglé n’est pas lettré (le règlement est contrepassé).
-   Une transaction est validée pour le compte fournisseur pour la contrepassation du paiement et le paiement contrepassé est réglé avec le paiement d’origine. Le champ **N° document dernier règlement** dans la page **Transactions fournisseur** pour le paiement d’origine du fournisseur est mis à jour pour refléter le n° document de la transaction contrepassée.

Si le chèque contrepassé était émis pour un remboursement client, les événements suivants se produisent également :

-   Une transaction est validée pour le compte client pour la contrepassation du paiement et le règlement entre le paiement d’origine et le document pour lequel le paiement était réglé à l’origine est contrepassé (un paiement négatif est créé).
-   Une contrepassation de paiement est réglée avec le paiement d’origine. Le champ **N° document dernier règlement** dans la page **Transactions client** pour le paiement d’origine du client est mis à jour pour refléter le n° document de la transaction contrepassée.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]