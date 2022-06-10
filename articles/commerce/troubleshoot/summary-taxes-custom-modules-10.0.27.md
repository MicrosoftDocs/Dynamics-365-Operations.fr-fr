---
title: Le sous-total du récapitulatif de commande n’inclut pas les taxes sur les frais lors de l’utilisation de modules de récapitulatif de commande personnalisés
description: Cette rubrique fournit des conseils de dépannage qui peuvent vous aider lorsque vous utilisez des modules de récapitulatif de commande personnalisés et que le sous-total du récapitulatif de commande n’inclut pas les taxes sur les frais dans le scénario "le prix inclut la taxe de vente".
author: gvrmohanreddy
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-04-22
ms.openlocfilehash: 1a47561a3ac984bc554b5b93546592237c16cf18
ms.sourcegitcommit: 48d094d083c1bd45c3d72f8b666926b48ec7ae35
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2022
ms.locfileid: "8767966"
---
# <a name="order-summary-subtotal-doesnt-include-taxes-on-charges-when-using-customized-order-summary-modules"></a>Le sous-total du récapitulatif de commande n’inclut pas les taxes sur les frais lors de l’utilisation de modules de récapitulatif de commande personnalisés

Cette rubrique fournit des conseils de dépannage qui peuvent vous aider lorsque vous utilisez des modules de récapitulatif de commande personnalisés et que le sous-total du récapitulatif de commande n’inclut pas les taxes sur les frais dans le scénario "le prix inclut la taxe de vente".

## <a name="description"></a>Description

Dès la version Microsoft Dynamics 365 Commerce 10.0.27, les modifications suivantes ont été apportées au scénario "le prix inclut la taxe de vente" pour fournir une expérience cohérente dans les modules de récapitulatif des commandes sur les pages du site de commerce électronique.

- Deux nouveaux champs ont été ajoutés : **TaxOnShippingCharge** et **TaxOnNonShippingCharges**.
- Les interfaces de programmation d’application (API) **GetSalesOrderBySalesId** et **GetSalesOrderByTransactionId** ont des valeurs précises pour les champs suivants dans le scénario "le prix inclut la taxe de vente" :

    - SubtotalSalesAmount
    - SubtotalAmountWithoutTax
    - SubtotalAmount
    - ShippingChargeAmount
    - OtherChargeAmount

Toutefois, si vous utilisez des modules de récapitulatif de commande personnalisés, ces modifications peuvent affecter les valeurs du sous-total du récapitulatif de commande en n’incluant pas les taxes sur les frais.

## <a name="resolution"></a>Résolution

Si vous utilisez des modules récapitulatifs de commande personnalisés et que vous ne souhaitez pas hériter des modifications apportées au scénario "le prix inclut la taxe de vente" dans Commerce version 10.0.27 et ultérieure, suivez les instructions de cette section.

En revenant au comportement de résumé de commande précédent (avant la version 10.0.27) des champs **salesTransaction.SubtotalAmount** et **salesTransaction.SubtotalAmountWithoutTax**, vous rétablissez la prise en compte du montant total de la taxe facturée (**TaxOnShippingCharge** et **TaxOnNonShippingCharges**) dans les montants des sous-totaux (**SubtotalAmount** et **SubtotalAmountWithoutTax**).

Pour revenir au comportement de résumé de commande précédent, procédez comme suit.

1. Dans Commerce Headquarters, ouvrez la page des paramètres Commerce (**Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres Commerce**).
1. Dans le volet de navigation de gauche, sélectionnez **Paramètres de configuration**.
1. Ajoutez les paramètres de configuration suivants et définissez la valeur de chacun sur **true** :

    - IsLegacyTaxOnChargeInSubtotalAmountIncludedInTaxIncusiveEnabled
    - IsLegacyOrderSummaryHydrationEnabled

> [!NOTE]
> Si vous avez déjà utilisé le paramètre de configuration **IsUpdatedPriceIncludesTaxSubtotalCalculationEnabled** et que vous souhaitez conserver le même comportement pour la propriété **order.NetAmountWithoutTax**, vous devez également ajouter le paramètre de configuration **IsLegacyPriceIncludesTaxNetAmountWithoutTaxCalculationEnabled** et définissez sa valeur sur **true**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Masquer les informations de répartition fiscale dans les résumés de commande](../hide-taxes-breakup.md)
