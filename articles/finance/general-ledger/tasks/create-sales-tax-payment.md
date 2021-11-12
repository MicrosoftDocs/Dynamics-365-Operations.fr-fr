---
title: Créer un paiement de taxe
description: La procédure de la tâche Régler et valider la taxe permet de régler les soldes de taxe dans les comptes de taxe et de les compenser dans le compte de règlement de la taxe pour une période donnée.
author: twheeloc
ms.date: 10/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 54132ca4775482b4a06ff7e73125e804aff40cb4
ms.sourcegitcommit: f8b597b09157d934b62bd5fb9a4d05b8f82b5a0e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/26/2021
ms.locfileid: "7700111"
---
# <a name="create-a-sales-tax-payment"></a>Créer un paiement de taxe

[!include [banner](../../includes/banner.md)]

La procédure de la tâche Régler et valider la taxe permet de régler les soldes de taxe dans les comptes de taxe, et de les compenser dans le compte de règlement de la taxe pour une période donnée.

1. Allez dans **Taxe > Déclarations > Taxe > Régler et valider la taxe**.
2. Dans le champ **Période de règlement**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Entrez une date dans le champ **Date de début**.
    - Si vous ne sélectionnez pas m’option **Inclure les corrections** sur la page **Paramètres de comptabilité**, le règlement peut être traité pour différentes versions. L’original est le premier règlement pour un intervalle de périodes et peut uniquement être traité une fois pour un intervalle de périodes. Les corrections les plus récentes permettent de régler les transactions de taxe validées après la création de la version d’origine.
5. Entrez une date dans le champ **Date de transaction**.
6. Cliquez sur **OK**.

## <a name="performance-consideration"></a>Considération relative aux performances

La procédure de paiement de la taxe peut être longue. Les principaux facteurs qui affectent le niveau de performance de la procédure sont le nombre de factures dans la période de règlement et le nombre d’écritures qui doivent être enregistrées dans le document de règlement de la taxe. Pour aider à améliorer les performances, vous pouvez choisir de contourner certaines fonctionnalités qui ne sont pas requises dans votre processus.

### <a name="enable-the-sales-tax-payment-performance-improvement-feature"></a>Activer la fonctionnalité Amélioration des performances de paiement de la taxe

La fonctionnalité **Amélioration des performances de paiement de la taxe** peut aider à améliorer les performances de la procédure de paiement de la taxe en agrégeant, sur une seule ligne, le montant en devise comptable et le montant en devise de déclaration sur les lignes de document de paiement de la taxe qui ont le même compte principal, la même dimension comptable et la même devise.

1. Accédez à **Administration système** \> **Espaces de travail** \> **Gestion des fonctionnalités**.
2. Dans l’onglet **Tous**, recherchez et sélectionnez **Amélioration des performances de paiement de la taxe**.
3. Sélectionnez **Activer**.

### <a name="prevent-generation-of-offset-tax-transactions"></a>Empêcher la génération de transactions de taxe de contrepartie

Par défaut, le document de paiement de la taxe comptabilise les transactions de taxe de contrepartie par rapport à chaque transaction de taxe réglée dans la procédure de paiement de la taxe. Ces transactions de taxe de contrepartie sont incluses dans le rapport **Taxe/Rapprochement taxe**. Elles montrent le solde impayé des transactions de taxe de vente qui ne sont pas réglées au cours de la période.

Cependant, les transactions de taxe de contrepartie peuvent augmenter la charge sur la procédure de paiement de la taxe. Par conséquent, une version d’évaluation nommée **TaxReportGenOffsetTaxTransPerRecordSetFlighting** peut être activée à la demande. Cette version d’évaluation peut aider à améliorer les performances de génération de transactions de taxe de contrepartie pour les pays et régions à l’exception de la Thaïlande, la Pologne, la Hongrie, la Lituanie, la Malaisie, l’Inde, l’Italie, la Russie, la République tchèque, l’Estonie et la Lettonie.

> [!NOTE]
> S’il existe des champs personnalisés dans le tableau des transactions fiscales, la version d’évaluation ne peut pas être activée.

Étant donné que le rapport **Taxe/Rapprochement taxe** est généralement utilisé uniquement à des fins de contrôle interne et n’est pas requis dans de nombreux régimes fiscaux, vous pouvez choisir de ne pas générer de transactions de taxe de vente de contrepartie sur le document de paiement de la taxe.

1. Accédez à **Taxes** \> **Taxes indirectes** \> **Taxe** \> **Périodes de règlement fiscal**.
2. Sélectionnez une période de règlement.
3. Sur le raccourci **Général**, définissez l’option **Empêcher la génération des transactions de taxe de contrepartie** sur **Oui**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
