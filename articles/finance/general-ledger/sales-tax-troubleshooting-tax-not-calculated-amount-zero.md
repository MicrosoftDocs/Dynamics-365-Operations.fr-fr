---
title: La taxe n'est pas calculée ou le montant de la taxe est égal à zéro
description: Cette rubrique fournit des informations sur la résolution des problèmes qui peuvent vous aider lorsque le montant de la taxe est égal à 0 (zéro) ou lorsque la taxe n'est pas calculée.
author: shtao
ms.date: 04/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: ead979081692d4dcee9812c89f5f10c7879d3f7e
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947638"
---
# <a name="tax-isnt-calculated-or-the-tax-amount-is-zero"></a>La taxe n'est pas calculée ou le montant de la taxe est égal à zéro

[!include [banner](../includes/banner.md)]

Une transaction peut avoir un montant de ligne différent de 0 (zéro), mais la taxe n'est pas calculée ou le montant de la taxe calculé est de 0. Pour résoudre ce problème, suivez les étapes des sections suivantes selon les besoins.

## <a name="verify-that-tax-codes-are-correctly-selected-by-the-transaction"></a>Vérifiez que les codes de taxe sont correctement sélectionnés par la transaction

Si la transaction ne sélectionne pas les bons codes de taxe, ou si elle ne sélectionne aucun code de taxe, les taxes ne seront pas calculées dessus. Pour vérifier que les codes de taxe sont correctement sélectionnés par la transaction, procédez comme suit : 

1. Sur la ligne de transaction, sur le raccourci **Détails de ligne** de l'onglet **Paramétrage**, dans la section **Taxe**, vérifiez que les groupes de taxes corrects sont sélectionnés dans les champs **Groupe de taxes d’article** et **Groupe de taxes**. Si les groupes de taxes corrects ne sont pas sélectionnés, sélectionnez-les.

    [![Champs Groupe de taxes d’article et Groupe de taxes](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)

2. Accédez à **Taxe** \> **Taxes indirectes** \> **Taxe** \> **Groupes de taxes**.
3. Sélectionnez le groupe de taxes de vente approprié, puis sur le raccourci **Paramétrage**, notez le code de taxe dans le champ **Code taxe**.

    [![Page Groupes de taxes](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)

4. Accédez à **Taxe** \> **Taxes indirectes** \> **Taxe** \> **Groupes de taxes d’article**.
5. Sélectionnez le groupe de taxes sur les articles approprié, puis sur le raccourci **Paramétrage**, vérifiez que le code de taxe dans le champ **Code taxe** correspond à celui du groupe de taxes de vente.

    [![Page Groupes de taxes d’article](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)

6. Si les codes de taxe ne correspondent pas, mettez à jour le code de taxe de vente pour l'un des groupes.

## <a name="verify-that-the-selected-tax-codes-arent-exempt-and-that-they-have-the-correct-tax-rate-value"></a>Vérifiez que les codes de taxe sélectionnés ne sont pas exonérés et qu'ils ont la valeur de taux de taxe correcte

Si les codes de taxe sont exonérés ou si le taux de taxe est 0 (zéro), le résultat du calcul de la taxe sera 0. Suivez ces étapes pour déterminer si les codes de taxe sélectionnés sont exonérés et pour vérifier que le taux de taxe correct leur est appliqué.

1. Accédez à **Taxe** \> **Taxes indirectes** \> **Taxe** \> **Groupes de taxes**.
2. Sélectionnez le groupe de taxes approprié, puis sur le raccourci **Paramétrage**, vérifiez que la case à cocher **Exonéré** est désactivée. Si elle est cochée, décochez-la.

    [![Case à cocher Exonéré sur la page Groupes de taxes](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)

3. Accédez à **Taxe** \> **Taxes indirectes** \> **Taxe** \> **Codes taxe**.
4. Sélectionnez le code de taxe approprié, puis vérifiez que la valeur du taux de taxe dans le champ **Valeur** n'est pas 0 (zéro). S'il est égal à 0, mettez à jour le champ afin qu'il soit défini sur le taux de taxe correct.

    [![Champ Valeur sur la page Valeurs de code taxe](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)

## <a name="determine-whether-zero-is-the-correct-tax-amount"></a>Déterminer si zéro est le montant de taxe correct

Dans certains scénarios, un montant de taxe de 0 (zéro) est correct. Suivez ces étapes pour déterminer si 0 est le montant de taxe correct pour votre transaction.

1. Accédez à **Comptabilité** \> **Paramétrage de la comptabilité** \> **Paramètres de comptabilité**.
2. Sur l'onglet **Taxe**, dans le champ **Méthode de calcul**, vérifiez que **Total** est sélectionné.

    [![Champ Méthode de calcul sur la page Paramètres de Comptabilité](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)

3. Accédez à **Taxe** \> **Taxes indirectes** \> **Taxe** \> **Codes taxe**.
4. Sélectionnez le code de taxe approprié, sélectionnez **Calcul** \> **Base marginale**, et vérifiez que la base marginale est définie sur **Montant HT du solde de la facture** ou **Facture totale, autres taxe incluses**. Pour plus d'informations, consultez [Facture totale, autres taxe incluses](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).
5. Si les valeurs correctes sont définies aux étapes 2 et 4, déterminez si le montant total de la transaction est 0 (zéro). Si le montant total est de 0, un montant de taxe de 0 est le résultat attendu. Étant donné que le calcul de la taxe est basé sur le montant total du solde de la facture et que ce montant n'est pas ligne par ligne, le montant de la taxe de 0 sera attribué à chaque ligne après le calcul de la taxe.

## <a name="determine-whether-customization-exists"></a>Déterminer si la personnalisation existe

Si vous avez terminé les étapes des sections précédentes mais que vous n'avez trouvé aucun problème, déterminez s'il existe une personnalisation. Si aucune personnalisation n'existe, créez une demande de service Microsoft pour une assistance supplémentaire.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
