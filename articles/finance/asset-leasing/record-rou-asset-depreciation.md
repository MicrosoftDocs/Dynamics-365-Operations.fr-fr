---
title: Enregistrer l’amortissement des droits d’utilisation de l’actif (version préliminaire)
description: Cette rubrique explique comment créer l’écriture de journal pour l’amortissement requis pour les contrats de location comptabilisés dans le bilan d’une organisation.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1c42eba0c4bc18e643202020a5bbb7335a73af86
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978987"
---
# <a name="record-right-of-use-asset-depreciation-preview"></a>Enregistrer l’amortissement des droits d’utilisation de l’actif (version préliminaire)

[!include [banner](../includes/banner.md)]

Pour les contrats de location comptabilisés au bilan d’une organisation, le droit d’utilisation de l’actif est amorti sur une base mensuelle. Cette rubrique explique comment créer l’écriture de journal pour l’amortissement. L’amortissement débite le compte général des dépenses et crédite le compte général des amortissements cumulés, en fonction de la configuration de votre profil comptable et du type de bail. Ces entrées peuvent être créées pour chaque bail ou pour plusieurs baux à l’aide de la fonctionnalité de journal par lots.

## <a name="asset-depreciation-schedule"></a>Tableau de dépréciation des actifs

1. Sur la page **Résumé du bail**, sélectionnez un bail. Puis sélectionnez **Registres \> Plan d’amortissement des actifs** pour ouvrir la page **Plan d’amortissement des actifs**.

    L’écriture de journal des dépenses d’amortissement du droit d’utilisation de l’actif est basée sur le montant de la colonne **Frais d’amortissement**. Pour un exemple des directives relatives à la conformité aux normes comptables, consultez la section [Calcul des dépenses d’amortissement du droit d’utilisation de l’actif pour les contrats de location-financement](#calculation-of-rou-asset-amortization-expense-for-finance-leases) plus loin dans cette rubrique.

2. Sélectionnez la période d’amortissement, puis sélectionnez **Créer un journal**. Vous recevez un message indiquant que le journal qui sera utilisé pour enregistrer l’amortissement a été créé.
3. Sélectionnez **Journaux \> Journaux de location d’actifs** pour ouvrir la page **Journal de location d’actifs**, où vous pouvez afficher l’écriture de journal des dépenses d’amortissement qui a été créée.
4. Sélectionnez l’entrée de journal, puis sélectionnez **Publier** pour enregistrer l’écriture d’amortissement dans la comptabilité.

## <a name="calculation-of-rou-asset-amortization-expense-for-operating-leases"></a>Calcul des frais d’amortissement du droit d’utilisation de l’actif pour les locations simples

La charge d’amortissement d’une location simple est calculée comme la différence entre la charge mensuelle de location linéaire et la charge d’intérêt mensuelle sur le passif locatif, conformément à la codification des normes comptables 842 (ASC 842), qui est la norme dans les principes comptables généralement reconnus aux États-Unis (US GAAP). Les frais de location linéaires correspondent à la somme de tous les paiements de location divisée par la durée du bail en mois. (La somme des paiements de location comprend les remboursements anticipés, les coûts directs initiaux, les coûts de démantèlement et les incitatifs à la location.) Le tableau suivant montre un exemple de la charge d’amortissement d’une location simple.

### <a name="example-of-rou-asset-amortization-expense-for-operating-leases"></a>Exemple de frais d’amortissement du droit d’utilisation de l’actif pour les locations simples

| Champ                                          | Valeur       |
|------------------------------------------------|-------------|
| Montant du paiement                                 | 1 000       |
| Fréquence de paiement                              | Tous les mois     |
| Durée du bail (mois)                            | 24          |
| Total des paiements de location                           | 24,000      |
| Taux d’emprunt marginal                     | 5 %          |
| Type d’annuité                                   | Annuité exigible |
| Intervalle de composition                           | Tous les mois     |
| Valeur actuelle des futurs paiements minimaux de location | 22,888.87   |

Comme mentionné précédemment, les frais de location linéaires correspondent à la somme de tous les paiements divisée par la durée du bail. Le système calcule automatiquement les frais d’intérêts mensuels sur le calendrier d’amortissement du passif. Les charges d’intérêts sont calculées selon la méthode du taux d’intérêt effectif. Le système utilisera le coût de location linéaire pour soustraire les charges d’intérêts pour chaque mois. La valeur est utilisée pour réduire le droit d’utilisation de l’actif.

| Mois | Coût de location linéaire | Dépenses d’intérêts                        | Calcul de la charge d’amortissement du droit d’utilisation de l’actif |
|-------|--------------------------|-----------------------------------------|-----------------------------------------------|
| 1     | (24 000 ÷ 24) = 1 000,00 | (22 888,87 – 1 000) × (5 % ÷ 12) = 91,20 | 1 000 – 91,20 = 908,80                        |
| 2     | (24 000 ÷ 24) = 1 000,00 | (21 980,08 – 1 000) × (5 % ÷ 12) = 87,42 | 1 000 – 87,42 = 912,58                        |
| 3     | (24 000 ÷ 24) = 1 000,00 | (21 067,49 – 1 000) × (5 % ÷ 12) = 83,62 | 1 000 – 83,62 = 916,39                        |

> [!NOTE]
> Selon l’ASC 842, l’amortissement du droit d’utilisation de l’actif pour une location simple est classé comme une charge de location dans le compte de résultat. Pour la visibilité, la location d’actifs décrit l’écriture comme l’amortissement du droit d’utilisation de l’actif. Cependant, l’écriture de débit doit être affectée à un compte de charges de location simple et l’écriture de crédit doit être affectée directement au droit d’utilisation de l’actif pour la location simple. Néanmoins, dans les paramètres de location, vous pouvez spécifier que les écritures de crédit doivent être effectuées sur un compte d’amortissement cumulé pour les droits d’utilisation de l’actif opérationnels.

## <a name="calculation-of-rou-asset-amortization-expense-for-finance-leases"></a>Calcul des frais d’amortissement du droit d’utilisation de l’actif pour les contrats de location-financement

Pour les location qui ont une classification financière, le système calcule l’amortissement du droit d’utilisation de l’actif sur une base linéaire. Par conséquent, la charge d’amortissement sera la même pour chaque mois.

Conformément aux normes internationales d’information financière 16 (IFRS 16) et ASC 842, l’actif sera amorti sur la durée du contrat de location ou sur la durée de vie utile de l’actif, selon la moindre des deux. De plus, si le paramètre **Transfert de propriété** est activé pour le bail, le bail sera automatiquement amorti sur la durée d’utilité de l’actif.

### <a name="example-of-rou-asset-amortization-expense-for-finance-leases"></a>Exemple de frais d’amortissement du droit d’utilisation de l’actif pour les contrats de location-financement

| Champ                                | Valeur                                   |
|--------------------------------------|-----------------------------------------|
| Début du solde du droit d’utilisation de l’actif | 22,889.87                               |
| Durée du bail (mois)                  | 24                                      |
| Durée de vie utile de l’actif (mois)           | 36                                      |
| Mois                                | Dépense d’amortissement du droit d’utilisation de l’actif |
| 1                                    | 22 889,87 ÷ 24 = 953,74                 |
| 2                                    | 22 889,87 ÷ 24 = 953,74                 |
| 3                                    | 22 889,87 ÷ 24 = 953,74                 |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]