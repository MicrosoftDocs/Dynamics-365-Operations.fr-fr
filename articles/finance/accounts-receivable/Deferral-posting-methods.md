---
title: Méthodes de validation des reports
description: Cet article décrit les différences entre les méthodes de report de report pour les reports de revenus et de dépenses dans la facturation des abonnements.
author: JodiChristiansen
ms.date: 6/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: c66ed1c38251140dd798c39797873ceb5f7121a4
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9019095"
---
# <a name="deferral-posting-methods"></a>Méthodes de validation des reports

Cet article décrit les différences entre les méthodes de report de report pour les reports de revenus et de dépenses dans la facturation des abonnements.

Sur la page **Paramètres de report des revenus et des dépenses**, les options de méthode de report sont **Bilan** et **Compte de résultat**. L’exemple de cet article vous aidera à expliquer les différences entre les deux méthodes et les raisons pour lesquelles vous pourriez utiliser l’une ou l’autre méthode.

La méthode **Bilan** utilise seulement deux comptes. Par conséquent, moins de configuration est impliquée. La méthode **Compte de résultat** a deux comptes supplémentaires, **Comptabilisation initiale** et **Décalage de reconnaissance**, pour les revenus, les remises et les coûts, selon le type de transaction. Ces comptes sont établis sur la page **Valeurs par défaut de report** (**Facturation de l’abonnement \> Reports de revenus et de dépenses \> Configurer**). Bien que l’exemple se concentre sur les revenus reportés, le même concept peut être appliqué aux remises reportées et aux coûts reportés.

## <a name="example"></a>Exemple

La facture de vente 1 a un total de 3 000 USD et a des revenus différés. Les tableaux suivants montrent les répartitions lorsque cette facture client est validée.

**Méthode Bilan**

| Type | Compte | Débit | Crédit|
|---|---|---|---|
| Débit | Module Comptabilité client | 3,000.00 | |
| Crédit | Produit différé | | 3,000.00 |

**Méthode Compte de résultat**

| Type | Compte | Débit | Crédit |
|---|---|---|---|
| Débit | Module Comptabilité client | 3,000.00 | |
| Débit | Contrepartie de constatation des revenus | 3,000.00 | |
| Crédit | Produit différé | | 3,000.00 |
| Crédit | Constatation initiale des revenus | | 3,000.00 |

La facture de vente 2 a un total de 2 000 USD et a des revenus différés.

| Type | Compte | Montant |
|---|---|---|
| Débit | Module Comptabilité client | 3,000.00 |
| Crédit | Recettes | 3,000.00 |

**Totaux selon la méthode du bilan pour les factures de vente 1 et 2 combinées**

| Compte | Débit | Crédit |
|---|---|---|
| Module Comptabilité client | 5,000.00 | |
| Recettes | | 2,000.00 |
| Produit différé | | 3,000.00 |

Quand la méthode **Bilan** est utilisée, il n’est pas aussi facile de voir le revenu brut pour une période. Certains revenus sont validés dans le compte **Produit différé**. Gardez à l’esprit que, comme les revenus sont comptabilisés à chaque période, il y a plusieurs débits et crédits dans le compte **Revenus reportés**. Les revenus bruts pour une période donnée seront mélangés avec les entrées / sorties de la reconnaissance des revenus.

**La méthode Compte de résultat pour les factures de vente 1 et 2 combinées**

| Compte | Débit | Crédit |
|---|---|---|
| Module Comptabilité client | 5,000.00 | |
| Recettes | | 5,000.00 |
| Compensation des revenus | 3,000.00 | |
| Produit différé | | 3,000.00 |

Tous les revenus vont sur le compte de résultat **Revenus**. Ensuite, les revenus différés sont transférés du compte de résultat au bilan. Vous pouvez facilement voir les revenus bruts, car tout est affiché sur le compte **Revenus**. Cependant, une partie de ces revenus bruts est différée. Par conséquent, il est déplacé vers le compte **Revenus reportés** et reconnu plus tard.

Dans la méthode **Compte de résultat**, vous pouvez consulter le compte **Revenus** et le compte **Compensation des revenus** pour voir les revenus bruts de 5 000 USD et les revenus nets (nets des différés) de 2 000 USD. Bien que la méthode **Compte de résultat** peut faciliter la création de rapports, il y a plus de comptes à configurer.
