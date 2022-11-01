---
title: Factures d’acompte et acomptes
description: Cet article décrit et compare les deux méthodes que les organisations peuvent utiliser pour les paiements en avance (acomptes).
author: abruer
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, PurchTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: 15871
ms.assetid: a0bb5220-73d4-48ae-84d0-46a171c224fa
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62f828b93075c134778da280243c0875edf99300
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/25/2022
ms.locfileid: "9715827"
---
# <a name="prepayment-invoices-vs-prepayments"></a>Factures d’acompte et acomptes

[!include [banner](../includes/banner.md)]

Cet article décrit et compare les deux méthodes que les organisations peuvent utiliser pour les paiements en avance (acomptes). Une méthode crée une facture d’acompte qui est associée à une commande fournisseur. L’autre méthode crée des N° document du journal des acomptes en créant des entrées de journal et en les marquant comme des N° document du journal des acomptes.

Les organisations peuvent verser des acomptes (paiements en avance) aux fournisseurs pour des biens ou services avant que ceux-ci ne soient livrés. Deux méthodes permettent de verser des acomptes aux fournisseurs. Pour minimiser les risques, vous pouvez suivre les acomptes en définissant l’acompte sur une commande fournisseur. Pour cette méthode, vous devez créer une facture d’acompte associée à une commande fournisseur. Cette méthode est appelée facturation d’acompte. Les organisations qui ne souhaitent pas suivre les acomptes aussi étroitement ou qui ne reçoivent pas une facture d’acompte de leur fournisseur peuvent utiliser les N° documents du journal des acomptes au lieu de la méthode de facturation d’acompte. Vous pouvez créer des N° documents du journal des acomptes en créant des entrées de journal et en les marquant comme N° documents du journal des acomptes. Pour cette méthode, vous ne pouvez pas suivre les acomptes versés à un fournisseur, ni les commandes fournisseur concernées. Toutefois, vous pouvez marquer un acompte validé pour règlement pour une commande fournisseur.

## <a name="when-to-use-prepayment-invoicing-vs-prepayments"></a>Utilisation de la facturation d’acompte et des acomptes

| Facturation d’acompte                                                                | Acomptes                                                              |
|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| Définissez une valeur d’acompte sur la commande fournisseur.                                    | Aucune valeur d’acompte n’est définie sur la commande fournisseur.                    |
| Une facture d’acompte et une facture finale doivent être validées.                       | Aucune facture d’acompte ne doit être validée.                                    |
| Le passif de l’acompte est conservé dans le compte d’acompte, et non le compte d’achats. | Le passif de l’acompte est conservé dans le compte d’achats.                  |
| Le solde fournisseur ne reflète pas la valeur d’acompte tout au long du processus.     | Le solde fournisseur reflète la valeur d’acompte tout au long du processus. |
| La facturation d’acompte est disponible dans la Comptabilité fournisseur uniquement.                         | Les acomptes sont disponibles dans la Comptabilité fournisseur et la Comptabilité client.    |

## <a name="overview-of-the-prepayment-process"></a>Vue d’ensemble du processus d’acompte
Les pratiques comptables dans plusieurs pays/régions requièrent que les acomptes d’un client ou à un fournisseur ne soient pas imputés dans les comptes collectifs habituels pour le client ou le fournisseur. Au lieu de cela, ces acomptes sont validés dans des comptes généraux spéciaux pour les acomptes. Lorsqu’une commande client ou fournisseur est créée, une facture est émise pour le client ou par le fournisseur. Lorsque la facture est payée, l’acompte et le N° document d’acompte de taxe dans les comptes généraux des acomptes sont contrepassés et les montants de facture sont automatiquement validés dans les comptes collectifs habituels. Pour créer un acompte, procédez comme suit :

1.  Paramétrez un profil de validation pour les acomptes.
2.  Dans les paramètres de la comptabilité client et de la comptabilité fournisseur, sous **Comptabilité et taxe**, sélectionnez le nouveau profil de validation à l’aide du paramètre **Profil de validation du journal des paiements avec acompte**.
3.  Créez un journal des paiements, puis créez le paiement.
4.  Vous pouvez marquer le paiement comme acompte. Si un paiement est marqué comme acompte, il est validé dans les comptes généraux définis dans le profil de validation que vous paramétrez dans les étapes 1 et 2. En outre, si le paiement est marqué comme acompte, les taxes sont calculées. Certains gouvernements exigent le paiement de taxes lorsqu’un acompte est enregistré, même s’il n’y a pas de facture.
5.  Validez l’acompte.
6.  Facultatif : vous pouvez régler l’acompte pour la commande fournisseur ou la commande client avant de créer la facture. Dans la page Commande client ou Commande fournisseur, dans le volet Actions, utilisez **Régler les transactions**.
7.  Une fois que le fournisseur livre les biens ou services, enregistrez la facture. Si vous avez réglé l’acompte pour la commande fournisseur ou la commande client à l’étape 6, l’acompte est réglé automatiquement pour la facture créée. Si vous n’avez pas réglé l’acompte pour la commande fournisseur ou la commande client, vous pouvez le faire manuellement pour la facture à l’aide de l’option **Régler les transactions** dans la page du client ou du fournisseur. Le montant de l’acompte est ensuite contrepassé du compte créditeur/débiteur temporaire. En outre, si les taxes ont été calculées, elles sont contrepassés, car la facture indique les taxes réelles.

## <a name="overview-of-the-prepayment-invoicing-process"></a>Vue d’ensemble du processus de facturation d’acompte
Les factures d’acompte sont une procédure commerciale courante. Un fournisseur émet des factures d’acompte pour demander un dépôt sur l’achat avant l’exécution de la commande fournisseur. Par exemple, certains fournisseurs peuvent demander un acompte pour des biens ou services personnalisés. Si un fournisseur émet une facture qui demande un acompte, vous pouvez utiliser la fonctionnalité de facturation d’acompte. Une valeur d’acompte peut être définie sur la commande fournisseur, une facture d’acompte est enregistrée et payée, puis la facture d’acompte est appliquée à la facture finale. Pour créer un acompte, procédez comme suit :

1.  L’acheteur crée, confirme et envoie une commande fournisseur pour laquelle le fournisseur a demandé un acompte. La valeur d’acompte est définie sur la commande fournisseur dans le cadre de l’accord.
2.  Le fournisseur soumet une facture d’acompte.
3.  Le coordinateur de la comptabilité fournisseur enregistre la facture d’acompte pour la commande fournisseur, puis la facture d’acompte est payée.
4.  Le fournisseur envoie une demande de paiement, appelée facture fournisseur standard. Une fois les biens ou services livrés par le fournisseur et les factures fournisseur standard associées reçues, le coordinateur de la comptabilité fournisseur applique le montant d’acompte déjà payé pour la facture standard.
5.  Le coordinateur de la comptabilité fournisseur paie et règle le montant restant de la facture standard.

## <a name="set-up-parameters-to-enable-the-prepayment-invoicing-process"></a>Configurer les paramètres pour activer le processus de facturation d’acompte
Un compte d’acompte doit être défini sur l’onglet **Commande fournisseur** de la page **Validation du stock** (**Gestion du stock \> Paramétrage \> Validation \> Validation**). Le compte d’acompte sera mis à jour, généralement débité, lors de la validation de la facture d’acompte. Le solde du compte d’acompte sera contrepassé lorsque la facture standard appliquée à la facture d’acompte sera validée. Si vous ne réglez pas la facture d’acompte sur un paiement avant d’appliquer la facture d’acompte à la facture standard, les écritures comptables de la facture d’acompte validée seront contrepassées lors de la validation de la facture standard.

Le compte de synthèse de contrepartie de la comptabilité fournisseur est défini sur le profil **Validation fournisseur**. Pour définir le profil de validation par défaut, cliquez sur **Comptabilité fournisseur \> Paramétrage \> Paramètres de la comptabilité fournisseur \> Onglet Comptabilité et taxe \> Profil de validation avec facture d’acompte fournisseur**.

La **Stratégie d’application des acomptes** indique si le système appliquera automatiquement les factures d’acompte réglées à la facture finale qui a été créée manuellement. Les factures créées à l’aide d’une entité de données ne font pas référence à la **Stratégie d’application des acomptes**. Vous devrez appliquer manuellement les factures d’acompte réglées aux factures créées à l’aide d’une entité de données. Pour définir la stratégie, accédez à **Comptabilité fournisseur \> Paramétrage \> Paramètres de la comptabilité fournisseur \> Onglet Comptabilité et taxe \> Stratégie d’application des acomptes**. Si le champ **Stratégie d’application des acomptes** est défini sur **Automatique**, la facture d’acompte sera automatiquement marquée pour règlement avec la facture finale. Si le champ est défini sur **Notification**, une indication visuelle qu’une facture d’acompte est disponible pour l’application s’affichera lors de la création de la facture finale.

## <a name="create-a-purchase-order-that-contains-prepayment-invoice-information"></a>Créer une commande fournisseur contenant des informations sur la facture d’acompte
Lorsqu’un fournisseur vous dit qu’il a besoin d’un acompte pour les biens et services contenus dans une commande fournisseur, vous devez définir la valeur d’acompte pour la commande fournisseur concernée. Accédez à **Comptabilité fournisseur \> Commun \> Commandes fournisseur \> Toutes les commandes fournisseur** et recherchez la commande fournisseur du fournisseur. Dans le volet Actions, sélectionnez l’onglet **Achat**, puis sélectionnez **Acompte**. Entrez les informations relatives à l’acompte, notamment une description, la valeur de l’acompte, si l’acompte est un montant fixe ou un pourcentage, et un ID de catégorie d’acompte. 

Notez qu’il n’est pas possible de mettre plusieurs définitions d’acompte sur une commande fournisseur. Si vous devez autoriser plusieurs acomptes sur une commande fournisseur, validez les paiements à l’aide du journal des paiements au lieu d’une facture d’acompte.

L’acompte peut être supprimé de la commande fournisseur, sauf si vous avez déjà réglé un paiement sur la facture d’acompte validée ou validé la facture standard. Pour supprimer une information d’acompte de la commande fournisseur, sélectionnez **Comptabilité fournisseur \> Commun \> Commandes fournisseur \> Toutes les commandes fournisseur** et recherchez la commande fournisseur du fournisseur. Dans le volet Actions, sélectionnez l’onglet **Achat**, puis sélectionnez **Supprimer l’acompte**.

## <a name="create-and-post-a-prepayment-invoice"></a>Créer et valider une facture d’acompte
Pour enregistrer la facture d’acompte du fournisseur, accédez à la page **Facture fournisseur** en sélectionnant l’option **Facture d’acompte** sur la page **Commandes fournisseur** (**Comptabilité fournisseur \> Commun \> Commandes fournisseur \> Toutes les commandes fournisseur \> Onglet Facture \> Facture d’acompte**). Entrez les informations relatives à la facture d’acompte, notamment le numéro de facture. Vous ne pouvez pas modifier les quantités d’une facture d’acompte. Si le fournisseur a facturé un montant partiel de la valeur d’acompte définie sur la commande fournisseur, vous pouvez mettre à jour le prix unitaire pour refléter la valeur partielle.

Lors de la validation de la facture d’acompte, le solde fournisseur et le compte d’acompte sont mis à jour. La valeur **Application de l’acompte** de la définition d’acompte contenue dans la commande fournisseur est également mise à jour. Les entrées de dimension financière par défaut pour le N° document d’acompte validé seront extraites des informations d’en-tête de la commande fournisseur.

Si la fonction **Verrouiller les dimensions financières sur les lignes de facture sur la facture d’acompte fournisseur** sur la page **Gestion des fonctionnalités** est activée, les dimensions de l’en-tête ou des lignes d’acompte ne peuvent pas être mises à jour. 

## <a name="post-and-settle-payments-for-the-prepayment-invoice"></a>Valider et régler les paiements pour la facture d’acompte
Ensuite, la facture d’acompte sera payée à partir de la page **Journal des paiements**. Pour accéder aux journaux de paiement, cliquez sur **Comptabilité fournisseur \> Journaux \> Paiement s\> Journal des paiements**. Après avoir validé le règlement du paiement sur la facture d’acompte, la valeur **Demandes d’avance restantes** de la commande fournisseur est mise à jour.

Avant de valider la facture standard pour la facture d’acompte, vous pouvez contrepasser le règlement du paiement à partir de la facture d’acompte. Toutefois, après qu’une facture standard a été appliquée à la facture d’acompte, il n’est pas possible de contrepasser le règlement du paiement à partir de la facture d’acompte.

## <a name="post-the-standard-vendor-invoice-for-the-purchase-order-and-apply-the-prepayment-invoice-to-the-standard-invoice"></a>Valider la facture fournisseur standard pour la commande fournisseur et appliquer la facture d’acompte à la facture standard
Enregistrez la facture standard reçue du fournisseur. Dans le cadre de ce processus, vous pouvez appliquer la facture d’acompte réglée à la facture fournisseur afin que la valeur de la facture soit réduite du montant déjà payé. Le fait d’appliquer la facture d’acompte à la facture fournisseur garantira que les écritures comptables de la facture d’acompte seront contrepassées.

## <a name="application-of-the-prepayment-invoice-after-posting-the-standard-invoice"></a>Application de la facture d’acompte après validation de la facture standard
Si vous oubliez d’appliquer l’acompte à la facture fournisseur standard au moment de la validation de la facture fournisseur, l’acompte réglé pourra être appliqué à d’autres factures de ce fournisseur à partir de la page **Fournisseurs** (**Comptabilité fournisseur \> Commun \> Fournisseurs \> Tous les fournisseurs \> Onglet Facture \> Appliquer**).

## <a name="reversal-of-the-prepayment-application-process"></a>Contrepassation du processus d’application de l’acompte
Si vous devez annuler ou contrepasser l’application d’une facture d’acompte à partir d’une facture standard, sélectionnez l’action **Contrepasser** à partir de la page **Fournisseurs** (**Comptabilité fournisseur \> Commun \> Fournisseurs \> Tous les fournisseurs \> Onglet Facture \> Contrepasser**). Une fois l’application de l’acompte contrepassée, vous pouvez appliquer l’acompte à une autre facture standard. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
