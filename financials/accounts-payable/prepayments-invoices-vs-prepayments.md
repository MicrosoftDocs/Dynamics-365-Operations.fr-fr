---
title: Factures d&quot;acompte et acomptes
description: "Cet article décrit et contraste les deux méthodes que les organisations peuvent utiliser pour les paiements en avance (acomptes). Dans la première, vous créez une facture d&quot;acompte qui est associée à une commande fournisseur. Dans l&quot;autre méthode, vous créez des N° document du journal des acomptes en créant des entrées de journal et en les marquant comme des N° document du journal des acomptes."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, PurchTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15871
ms.assetid: a0bb5220-73d4-48ae-84d0-46a171c224fa
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 44d51807cd6bb64ae2c4bef58d8a445417ffa3a9
ms.openlocfilehash: 770a6fba8a27e9403235929b7e8cd547cc522486
ms.lasthandoff: 03/31/2017


---

# <a name="prepayment-invoices-vs-prepayments"></a>Factures d'acompte et acomptes

Cet article décrit et contraste les deux méthodes que les organisations peuvent utiliser pour les paiements en avance (acomptes). Dans la première, vous créez une facture d'acompte qui est associée à une commande fournisseur. Dans l'autre méthode, vous créez des N° document du journal des acomptes en créant des entrées de journal et en les marquant comme des N° document du journal des acomptes.

Les organisations peuvent verser des acomptes (paiements en avance) aux fournisseurs pour des biens ou services avant que ceux-ci ne soient livrés. Deux méthodes permettent de verser des acomptes aux fournisseurs. Pour minimiser les risques, vous pouvez suivre les acomptes en définissant l'acompte sur une commande fournisseur. Pour cette méthode, vous devez créer une facture d'acompte associée à une commande fournisseur. Cette méthode est appelée facturation d'acompte. Les organisations qui ne souhaitent pas suivre les acomptes aussi étroitement ou qui ne reçoivent pas une facture d'acompte de leur fournisseur peuvent utiliser les N° documents du journal des acomptes au lieu de la méthode de facturation d'acompte. Vous pouvez créer des N° documents du journal des acomptes en créant des entrées de journal et en les marquant comme N° documents du journal des acomptes. Pour cette méthode, vous ne pouvez pas suivre les acomptes versés à un fournisseur, ni les commandes fournisseur concernées. Toutefois, vous pouvez marquer un acompte validé pour règlement pour une commande fournisseur.

## <a name="when-to-use-prepayment-invoicing-vs-prepayments"></a>Utilisation de la facturation d'acompte et des acomptes
| Facturation d'acompte                                                                | Acomptes                                                              |
|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| Définissez une valeur d'acompte sur la commande fournisseur.                                    | Aucune valeur d'acompte n'est définie sur la commande fournisseur.                    |
| Une facture d'acompte et une facture finale doivent être validées.                       | Aucune facture d'acompte ne doit être validée.                                    |
| Le passif de l'acompte est conservé dans le compte d'acompte, et non le compte d'achats. | Le passif de l'acompte est conservé dans le compte d'achats.                  |
| Le solde fournisseur ne reflète pas la valeur d'acompte tout au long du processus.     | Le solde fournisseur reflète la valeur d'acompte tout au long du processus. |
| La facturation d'acompte est disponible dans la Comptabilité fournisseur uniquement.                         | Les acomptes sont disponibles dans la Comptabilité fournisseur et la Comptabilité client.    |

## <a name="overview-of-the-prepayment-process"></a>Vue d'ensemble du processus d'acompte
Les pratiques comptables dans plusieurs pays/régions requièrent que les acomptes d'un client ou à un fournisseur ne soient pas validés dans les comptes collectifs habituels pour le client ou le fournisseur. Au lieu de cela, ces acomptes sont validés dans des comptes généraux spéciaux pour les acomptes. Lorsqu'une commande client ou fournisseur est créée, une facture est émise pour le client ou par le fournisseur. Lorsque la facture est payée, l'acompte et le N° document d'acompte de taxe dans les comptes généraux des acomptes sont contrepassés et les montants de facture sont automatiquement validés dans les comptes collectifs habituels. Pour créer un acompte, procédez comme suit :

1.  Paramétrez un profil de validation pour les acomptes.
2.  Dans les paramètres de la comptabilité client et de la comptabilité fournisseur, sous **Comptabilité et taxe**, sélectionnez le nouveau profil de validation à l'aide du paramètre **Profil de validation du journal des paiements avec acompte**.
3.  Créez un journal des paiements, puis créez le paiement.
4.  Vous pouvez marquer le paiement comme acompte. Si un paiement est marqué comme acompte, le paiement est validé dans les comptes généraux définis dans le profil de validation que vous paramétrez dans les étapes 1 et 2. En outre, si le paiement est marqué comme acompte, les taxes sont calculées. Certains gouvernements exigent le paiement de taxes lorsqu'un acompte est enregistré, même s'il n'y a pas de facture.
5.  Validez l'acompte.
6.  Facultatif : Vous pouvez régler l'acompte pour la commande fournisseur ou la commande client avant de créer la facture. Dans la page de commande client ou de commande fournisseur, dans le volet Actions, utilisation ** transactions de règlement **.
7.  Une fois que le fournisseur livre les biens ou services, enregistrez la facture. Si vous avez réglé l'acompte pour la commande fournisseur ou la commande client à l'étape 6, l'acompte est réglé automatiquement pour la facture créée. Si vous n'avez pas réglé l'acompte pour la commande fournisseur ou la commande client, vous pouvez le faire manuellement pour la facture à l'aide de l'option **Régler les transactions** dans la page du client ou du fournisseur. Le montant de l'acompte est ensuite contrepassé du compte créditeur/débiteur temporaire. En outre, si les taxes ont été calculées, elles sont contrepassés, car la facture indique les taxes réelles.

## <a name="overview-of-the-prepayment-invoicing-process"></a>Vue d'ensemble du processus de facturation d'acompte
Les factures d'acompte sont une procédure commerciale courante. Un fournisseur émet des factures d'acompte pour demander un dépôt sur l'achat avant l'exécution de la commande fournisseur. Par exemple, certains fournisseurs peuvent demander un acompte pour des biens ou services personnalisés. Si un fournisseur émet une facture qui demande un acompte, vous pouvez utiliser la fonctionnalité de facturation d'acompte. Une valeur d'acompte peut être définie sur la commande fournisseur, une facture d'acompte est enregistrée et payée, puis la facture d'acompte est appliquée à la facture finale. Pour créer un acompte, procédez comme suit :

1.  L'acheteur crée, confirme et envoie une commande fournisseur pour laquelle le fournisseur a demandé un acompte. La valeur d'acompte est définie sur la commande fournisseur dans le cadre de l'accord.
2.  Le fournisseur soumet une facture d'acompte.
3.  Le coordinateur de la comptabilité fournisseur enregistre la facture d'acompte pour la commande fournisseur, puis la facture d'acompte est payée.
4.  Une fois les biens ou services livrés par le fournisseur et les factures fournisseur associées reçues, le coordinateur de la comptabilité fournisseur applique le montant d'acompte déjà payé pour la facture.
5.  Le coordinateur de la comptabilité fournisseur paie et règle le montant restant de la facture.



