---
title: Simulation de prix
description: Cet article fournit des informations sur la simulation de prix pour les devis. La simulation de prix vous permet d'évaluer l'effet des déductions sur le futur prix de vente au cours du processus de devis, avant de s'engager à un prix spécifique.
author: omulvad
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationPriceSimulation
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 12254
ms.assetid: 92be7c85-73cf-4f77-833c-d37ce779a031
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0369c1a4bbc893a86cf14bd59a2d28a7bbca15c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1554642"
---
# <a name="price-simulation"></a>Simulation de prix

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur la simulation de prix pour les devis. La simulation de prix vous permet d'évaluer l'effet des déductions sur le futur prix de vente au cours du processus de devis, avant de s'engager à un prix spécifique.

Une simulation de prix pour un devis affiche un nouveau montant total basé sur un nouveau prix proposé. Une simulation de prix peut également afficher un nouveau montant associé à une ligne spécifique créée dans un devis existant. Vous pouvez entrer une simulation de prix et l'appliquer ultérieurement. Vous pouvez autrement utiliser le devis original sans simulation de prix et effectuer d'autres modifications à mesure que vous avancez avec votre client dans le processus de vente.  

Lors d'une simulation de prix, le prix du devis n'est pas modifié. Si la simulation de prix est appliquée à l'ensemble du devis, elle est considérée comme une remise spéciale sur l'en-tête du devis. Si la simulation de prix est appliquée à des articles spécifiques, elle est considérée comme une remise spéciale sur les lignes du devis. Le prix de vente unitaire sur une ligne de devis créée ne change pas lorsqu'une simulation de prix est appliquée. À la place, un pourcentage de remise qui correspond à la réduction de prix du devis est appliqué. Lorsqu'une simulation de prix est appliquée, le prix de vente unitaire et le pourcentage de remise sont transférés vers la ligne de devis ou l'en-tête du devis.  

>[Remarque!] Lorsque vous exécutez une simulation de prix, seule la devise de vente actuelle est utilisée pour créer la simulation. Toutefois, lorsque vous affichez les totaux du devis, vous découvrez une combinaison de la devise de la société et de la devise de vente.  

Les articles supplémentaires ajoutés à des lignes de devis peuvent engendrer des remises sur une ou plusieurs lignes. Ils peuvent également déclencher des remises totales modifiant l'état des marges contributives et des taux de contribution des lignes de devis et de la remise complète.  

Vous pouvez exécuter plusieurs simulations de prix pour suivre les effets des ajustements de prix sur les cibles d'un devis. L'exécution de ces simulations vous permet d'ajuster le prix total du devis ou le prix d'une ou plusieurs lignes spécifiques du devis et ensuite d'appliquer la simulation de prix la plus susceptible de vous aider à conclure la vente.  

Vous pouvez paramétrer une alerte lorsque vous créez un devis. Voici certaines façons d'utiliser les alertes :

-   Elles vous permettent de rester informé du statut des devis au sein de l'organisation.
-   Elles permettent de déclencher une révision d'un devis spécifique ou de vous informer lorsque les limites de remise sont dépassées.

## <a name="price-simulation-and-discounts"></a>Simulation et remises de prix
Afin de garantir un calcul correct des remises et des prix, l'exécution de simulations de prix sur des devis avec remises requiert une attention particulière. Étant donné que toutes les simulations de prix sont traitées comme des remises spéciales dans la ligne de devis active ou dans l'ensemble du devis, vous devez repérer les différences entre les remises.

### <a name="types-of-discounts-in-trade-agreements"></a>Types de remises dans le cadre d'accords commerciaux

Dans Microsoft Dynamics 365 for Finance and Operations, les accords commerciaux peuvent comprendre quatre types de remises. Vous pouvez paramétrer ces remises pour différents articles, clients ou groupes de prix, et les limiter par date. Afin d'éviter toute erreur de calcul, les accords commerciaux doivent être pris en compte lors des simulations de prix. Voici les quatre types de remises inclus dans les accords commerciaux :

-   **Prix de vente** : un prix de vente distinct peut être spécifié pour chaque article. Lors de la création de lignes de devis, le programme recherche le prix de vente approprié d'un article et le transfère vers les lignes de devis. Par conséquent, un accord commercial comportant ce type de remise n'a aucune incidence sur la simulation de prix. Le prix de vente utilisé dans la ligne de devis reflète l'accord commercial.
-   **Remise ligne** : des remises spéciales sont spécifiées pour les articles, en fonction de la quantité commandée. La valeur de la remise ligne est généralement soustraite des montants des lignes avant l'exécution d'une simulation de prix. Par conséquent, un accord commercial associé à ce type de remise a une incidence sur la simulation de prix.
-   **Remise multiligne** : si les quantités combinées dépassent la limite que vous avez définie, les combinaisons prédéfinies d'articles commandés déclenchent une remise sur l'ensemble de la commande. La valeur de la remise ligne est généralement soustraite des montants des lignes avant l'exécution d'une simulation de prix. Par conséquent, un accord commercial associé à ce type de remise a une incidence sur la simulation de prix.
-   **Remise totale** : si les montants combinés dépassent la limite que vous avez définie, les articles commandés prédéfinis déclenchent une remise sur l'ensemble de la commande. La remise totale est générée par les lignes de devis. Toutefois, étant donné que la remise totale est appliquée au total du devis sous forme de remise, le montant total du devis est réduit. Par conséquent, un accord commercial associé à ce type de remise a une incidence sur la simulation de prix.

### <a name="quotation-lines-and-trade-agreements"></a>Lignes de devis et accords commerciaux

Lorsque vous créez ou ajustez une ligne de devis, les remises ligne sont automatiquement calculées. Le prix de vente correspondant est repéré pour l'article, en fonction de l'accord commercial.

## <a name="price-simulation-examples"></a>Exemples de simulation de prix
Les exemples suivants utilisent une simulation de prix pour les en-têtes de devis et les lignes uniques.

### <a name="price-simulation-for-quotation-headers"></a>Simulation de prix pour des en-têtes de devis

Vous créez un devis contenant les lignes suivantes :

-   10 unités de l'article BR-12 (prix de revient par unité : 9,52 EUR, prix de vente par unité : 15,32 EUR)
-   12 unités de l'article BR-14 (prix de revient par unité : 7,48 EUR, prix de vente par unité : 13,75 EUR)

Le tableau suivant présente les lignes du devis.

|                            | Calcul                          | Résultat   |
|----------------------------|--------------------------------------|----------|
| Quantité vendue             | 10 unités + 12 unités                  | 22 unités |
| Prix de vente (USD)         | (10 × 15,32) + (12 × 13,75)          | 318,20   |
| Prix de revient (USD)          | (10 × 9,52) + (12 × 7,48)            | 184,96   |
| Marge contributive (USD) | 318,20 – 184,96                      | 133,24   |
| Taux de contribution         | (\[318.20 – 184.96\] ÷ 318.20) × 100 | 41,87 %   |

Vous exécutez une simulation de prix avec une remise totale de 15 % sur l'ensemble du devis ou l'en-tête de devis. Le tableau suivant affiche les nouveaux totaux du devis une fois la simulation de prix exécutée.

|                                                      | Calcul                               | Résultat   |
|------------------------------------------------------|-------------------------------------------|----------|
| Quantité vendue                                       | 10 unités + 12 unités                       | 22 unités |
| Ancien prix de vente (USD)                               | (10 × 15,32) + (12 × 13,75)               | 318,20   |
| Ancien prix de revient (USD)                                | (10 × 9,52) + (12 × 7,48)                 | 184,96   |
| Ancienne marge contributive (USD)                       | 318,20 – 184,96                           | 133,24   |
| Ancien taux de contribution                               | (\[318.20 – (10 × 9.52)\] ÷ 318.20) × 100 | 41,87 %   |
| Simulation de prix avec remise totale de 15 % (EUR) | (15 × 318,2) ÷ 100                        | 47,73    |
| Nouveau prix de vente (USD)                               | 318,20 – 47,73                            | 270,47   |
| Nouvelle marge contributive (USD)                       | 270,47 – 184,96                           | 85,51    |
| Nouveau taux de contribution                               | \[(270.47 – 184.96) ÷ 270.47\] × 100      | 31,61 %   |

### <a name="price-simulation-for-single-line-items"></a>Simulation de prix pour des lignes uniques

Vous créez un devis contenant les lignes suivantes :

-   10 unités de l'article BR-12 (prix de revient par unité : 9,52 EUR, prix de vente par unité : 15,32 EUR)
-   12 unités de l'article BR-14 (prix de revient par unité : 7,48 EUR, prix de vente par unité : 13,75 EUR)

Le tableau suivant présente les lignes du devis.

|                                      | Calcul                          | Résultat   |
|--------------------------------------|--------------------------------------|----------|
| Quantité vendue                       | 10 unités + 12 unités                  | 22 unités |
| Prix de vente (USD) pour BR-12         | 10 × 15,32                           | 153,20   |
| Prix de vente (USD) pour BR-14         | 12 × 13,75                           | 165,00   |
| Prix de revient (USD) pour BR-12          | 10 × 9,52                            | 95,20    |
| Prix de revient (USD) pour BR-14          | 12 × 7,48                            | 89,76    |
| Marge contributive (USD) pour BR-12 | 153,20 – 95,20                       | 58,00    |
| Marge contributive (USD) pour BR-14 | 165,00 – 89,76                       | 75,24    |
| Taux de contribution (USD) pour BR-12  | \[(153.20 – 95.20) ÷ 153.20\] × 100  | 37,86    |
| Taux de contribution (USD) pour BR-14  | \[(165.00 – 89.76) ÷ 165.00\] × 100  | 45,60    |
| Prix de vente total (USD)             | (10 × 15,32) + (12 × 13,75)          | 318,20   |
| Prix de revient total (USD)              | (10 × 9,52) + (12 × 7,48)            | 184,96   |
| Marge contributive totale (USD)     | 318,20 – 184,96                      | 133,24   |
| Taux de contribution total             | \[(318.20 – 184.96) ÷ 318.20\] × 100 | 41,87 %   |

Vous exécutez une simulation de prix avec une remise totale de 10 % sur les unités de l'article BR-12. Le tableau suivant présente les nouveaux totaux du devis une fois la simulation de prix exécutée pour la ligne unique.

|                                                   | Calcul                             | Résultat   |
|---------------------------------------------------|-----------------------------------------|----------|
| Quantité vendue                                    | 10 unités + 12 unités                     | 22 unités |
| Ancien prix de vente (USD) pour BR-12                  | 10 × 15,32                              | 153,20   |
| Simulation de prix avec remise de 10 % pour BR-12 | (10 × 153,2) ÷ 100                      | 15,32    |
| Nouveau prix de vente (USD) pour BR-12                  | (10 × 15,32) – 15,32                    | 137,88   |
| Prix de vente (USD) pour BR-14                      | 12 × 13,75                              | 165,00   |
| Prix de revient (USD) pour BR-12                       | 10 × 9,52                               | 95,20    |
| Prix de revient (USD) pour BR-14                       | 12 × 7,48                               | 89,76    |
| Nouvelle marge contributive (USD) pour BR-12          | 137,88 – 95,20                          | 42,68    |
| Marge contributive (USD) pour BR-14              | 165,00 – 89,76                          | 75,24    |
| Nouveau taux de contribution (USD) pour BR-12           | \[(137.88 – 95.20) ÷ 137.88\] × 100     | 30,95    |
| Taux de contribution (USD) pour BR-14               | \[(165.00 – 89.76) ÷ 165.00\] × 100     | 45,60    |
| Nouveau prix de vente total (USD)                      | \[(10 × 15.32) – 15.32\] + (12 × 13.75) | 302,88   |
| Prix de revient total (USD)                           | (10 × 9,52) + (12 × 7,48)               | 184,96   |
| Nouvelle marge contributive totale (USD)              | 302,88 – 184,96                         | 117,92   |
| Nouveau taux de contribution total                      | \[(302.88 – 184.96) ÷ 302.88\] × 100    | 38,93 %   |

La simulation de prix affecte uniquement la ligne à laquelle elle est appliquée et réduit le total de cette ligne.



