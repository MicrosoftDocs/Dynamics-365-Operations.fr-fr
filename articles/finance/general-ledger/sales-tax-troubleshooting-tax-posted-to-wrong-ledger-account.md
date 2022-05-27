---
title: La taxe est imputée sur le mauvais compte du grand livre dans le justificatif
description: Cette rubrique fournit des informations sur la résolution des problèmes qui peuvent aider lorsque la taxe est imputée sur le mauvais compte du grand livre dans le justificatif.
author: qire
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 9c9f3fc63374b185a795977566cf73c8c29ee5d3
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686433"
---
# <a name="tax-is-posted-to-the-wrong-ledger-account-in-the-voucher"></a>La taxe est imputée sur le mauvais compte du grand livre dans le justificatif

[!include [banner](../includes/banner.md)]

Lors de la validation, il est possible que la taxe soit imputée sur le mauvais compte du grand livre dans le justificatif. Pour résoudre ce problème, suivez les étapes des sections suivantes selon les besoins. Les exemples de cette rubrique utilisent une commande client comme document commercial.

## <a name="find-the-tax-code-of-the-incorrectly-posted-tax-transaction"></a>Rechercher le code taxe de la transaction fiscale incorrectement validée

1. Sur la page **Justificatif de transaction**, sélectionnez la transaction avec laquelle vous souhaitez travailler, puis sélectionnez **Taxe validée**.

    [![Bouton Taxe validée sur la page Justificatif de transaction.](./media/tax-posted-to-wrong-ledger-account-Picture1.png)](./media/tax-posted-to-wrong-ledger-account-Picture1.png)

2. Vérifiez la valeur du champ **Code taxe**. Dans cet exemple, c’est **TVA 19**.

    [![Champ Code taxe de la page Taxe validée.](./media/tax-posted-to-wrong-ledger-account-Picture2.png)](./media/tax-posted-to-wrong-ledger-account-Picture2.png)

## <a name="check-the-ledger-posting-group-of-the-tax-code"></a>Vérifiez le groupe d’écriture comptable du code taxe

1. Accédez à **Taxe** \> **Taxes indirectes** \> **Taxe** \> **Codes taxe**.
2. Recherchez et sélectionnez le code taxe, puis examinez la valeur dans le champ **Groupe de validations dans la comptabilité**. Dans cet exemple, c’est **TVA**.

    [![Champ Groupe de validations dans la comptabilité de la page Codes taxe.](./media/tax-posted-to-wrong-ledger-account-Picture3.png)](./media/tax-posted-to-wrong-ledger-account-Picture3.png)

3. La valeur du champ **Groupe de validations dans la comptabilité** est un lien. Pour afficher les détails de la configuration du groupe, sélectionnez le lien. Sinon, sélectionnez et maintenez sélectionné (ou cliquez avec le bouton droit) dans le champ, puis sélectionnez **Afficher les détails**.

    [![Commande Afficher les détails.](./media/tax-posted-to-wrong-ledger-account-Picture4.png)](./media/tax-posted-to-wrong-ledger-account-Picture4.png)

4. Dans le champ **Taxe collectée**, vérifiez que le numéro de compte est correct, selon le type de transaction. Si ce n’est pas le cas, sélectionnez le bon compte pour lequel effectuer la validation. Dans cet exemple, la taxe de la commande client doit être imputée au compte de collecte de taxe 222200.

    [![Champ Taxe collectée de la page Groupes de validations dans la comptabilité.](./media/tax-posted-to-wrong-ledger-account-Picture5.png)](./media/tax-posted-to-wrong-ledger-account-Picture5.png)

    Le tableau suivant fournit des informations sur chaque champ de la page **Groupes de validations dans la comptabilité**.

    | Champ                  | Description |
    |------------------------|-------------|
    | Taxe collectée      | Le compte principal pour les taxes sortantes collectées par l’administration fiscale. |
    | Taxe déductible   | Le compte principal pour les taxes entrantes transmises par l’administration fiscale. |
    | Dépenses de taxe d’utilisation        | Le compte principal utilisé pour valider les taxes d’utilisation déductibles qui ne sont pas réclamées ou signalées à l’administration fiscale par les fournisseurs dans le cadre de la taxe GST/HST au preneur de l’UE. L’option **Taxe d’utilisation** doit être sélectionnée pour le code taxe dans le groupe de taxes utilisé dans la transaction. Ce champ n’est pas disponible si l’option **Appliquer les règles de taxe** est sélectionnée dans la page **Paramètres de comptabilité**. |
    | Taxe d’utilisation due        | Compte principal utilisé pour valider les taxes d’utilisation sortantes collectées par l’administration fiscale. |
    | Compte de règlement     | Le compte principal utilisé pour valider le solde net des comptes généraux spécifiés dans les champs **Taxe d’utilisation due** et **Taxe déductible**. |
    | Fournisseur - Escompte de règlement   | Compte principal utilisé pour valider l’escompte de règlement pour les codes taxe associés à ce groupe de validation dans la comptabilité. |
    | Client – Escompte de règlement | Compte principal utilisé pour valider l’escompte de règlement pour les codes taxe associés à ce groupe de validation dans la comptabilité. |

    Pour plus d’informations, voir [Paramétrer des groupes de validation dans la comptabilité de la taxe](tasks/set-up-ledger-posting-groups-sales-tax.md)

## <a name="debug-in-code-to-check-ledger-dimensions"></a>Déboguer dans le code pour vérifier les dimensions comptables

Dans le code, le compte de validation est déterminé par la dimension comptable. La dimension comptable enregistre l’ID d’enregistrement d’un compte dans la base de données.

1. Pour une commande client, ajoutez un point d’arrêt aux méthodes **Tax::saveAndPost()** et **Tax::post()**. Faites attention à la valeur **\_ledgerDimension**.

    [![Exemple de code de commande client ayant un point d’arrêt.](./media/tax-posted-to-wrong-ledger-account-Picture6.png)](./media/tax-posted-to-wrong-ledger-account-Picture6.png)

    Pour un bon de commande, ajoutez un point d’arrêt aux méthodes **TaxPost::saveAndPost()** et **TaxPost::postToTaxTrans()**. Faites attention à la valeur **\_ledgerDimension**.

    [![Exemple de code de commande fournisseur ayant un point d’arrêt.](./media/tax-posted-to-wrong-ledger-account-Picture7.png)](./media/tax-posted-to-wrong-ledger-account-Picture7.png)

2. Exécutez la requête SQL suivante pour rechercher la valeur d’affichage du compte dans la base de données, en fonction de l’ID d’enregistrement enregistré par la dimension comptable.

    ```sql
    select * from DIMENSIONATTRIBUTEVALUECOMBINATION where recid={the value of _ledgerDimension}
    ```

    [![Afficher la valeur de l’ID d’enregistrement.](./media/tax-posted-to-wrong-ledger-account-Picture8.png)](./media/tax-posted-to-wrong-ledger-account-Picture8.png)

3. Examinez la pile d’appels pour trouver où la valeur **_ledgerDimension** est attribuée. Habituellement, la valeur provient de **TmpTaxWorkTrans**. Dans ce cas, vous devez ajouter un point d’arrêt à **TmpTaxWorkTrans::insert()** et **TmpTaxWorkTrans::update()** pour trouver où la valeur est attribuée.

## <a name="determine-whether-customization-exists"></a>Déterminer si la personnalisation existe

Si vous avez terminé les étapes des sections précédentes mais que vous n’avez trouvé aucun problème, déterminez s’il existe une personnalisation. Si aucune personnalisation n’existe, créez une demande de service Microsoft pour une assistance supplémentaire.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
