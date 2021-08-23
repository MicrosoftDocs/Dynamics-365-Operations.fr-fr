---
title: Prise en charge de la double devise pour la taxe
description: Cette rubrique explique comment étendre la fonctionnalité comptable Double devise dans le domaine fiscal, ainsi que l’impact sur le calcul de la taxe et la validation
author: EricWang
ms.date: 12/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 449ebe55b8be7ee7ea22b4be7c44162d83fc3c2affbd4d20f4cad235ddb0f772
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742202"
---
# <a name="dual-currency-support-for-sales-tax"></a>Prise en charge de la double devise pour la taxe
[!include [banner](../includes/banner.md)]

Cette rubrique explique comment étendre la fonctionnalité comptable Double devise pour les taxes, ainsi que l’impact sur les calculs de la taxe, la validation et les règlements.

La fonctionnalité Double devise pour Dynamics 365 Finance a été introduite dans la version 8.1 (octobre 2018). Elle modifie la façon dont les écritures comptables dans la devise de déclaration sont calculées.

Dans les versions antérieures, les transactions étaient converties dans la devise de déclaration dans l’ordre suivant : 

- Le total de la transaction était calculé dans la devise de la transaction > Le montant de la transaction était converti dans la devise comptable > Le montant en devise comptable était converti en devise de déclaration

Après activation de la fonctionnalité Double devise, les transactions étaient converties dans la devise de déclaration dans l’ordre suivant :

- Montant dans la devise de la transaction > Montant en devise de déclaration

Pour plus d’informations sur la double devise, reportez-vous à [Double devise](dual-currency.md).

En raison de la prise en charge des doubles devises, deux nouvelles fonctionnalités sont disponibles dans la gestion des fonctionnalités : 

- Conversion de la taxe (nouveauté de la version 10.0.13)
- Saisissez les dimensions financières dans les comptes de profits/pertes d’ajustement de devise réalisés pour le règlement de la taxe (nouveau dans la version 10.0.17)

La prise en charge de la double devise pour les taxes permet de calculer avec précision les taxes dans la devise de la taxe et de calculer avec précision le solde du règlement de la taxe à la fois dans la devise comptable et la devise de déclaration.

## <a name="sales-tax-conversion"></a>Conversion de la taxe

Le paramètre **Conversion de la taxe** offre deux options pour convertir le montant de la taxe depuis la devise de la transaction vers la devise de la taxe. 

- Devise comptable : le chemin d’accès sera « Montant dans la devise de la transaction > Montant dans la devise comptable > Montant dans la devise de la taxe ». Le type de taux de change de la devise comptable (configuré dans les paramètres de comptabilité) sera utilisé pour la conversion de devise.
- Devise de déclaration : le chemin d’accès sera « Montant dans la devise de la transaction > Montant dans la devise de déclaration > Montant dans la devise de la taxe ». Le type de taux de change de la devise de déclaration (configuré dans les paramètres de comptabilité) sera utilisé pour la conversion de devise.

### <a name="example"></a>Exemple

Voici un exemple simple pour démontrer cette fonctionnalité :

Configuration de la devise pour la comptabilité et la taxe

| Devise de la transaction | Devise comptable | Devise de déclaration | Devise de la taxe |
| -------------------- | ------------------- | ------------------ | ------------ |
| EUR                  | USD                 | GBP                | GBP          |

Taux de change

| Devise de départ | Devise d’arrivée | Facteur | Taux de change |
| ------------- | ----------- | ------ | ------------- |
| EUR           | USD         | 1      | 1,11          |
| EUR           | GBP         | 1      | 0,83          |
| USD           | GBP         | 1      | 0,75          |

Calcul du montant de la taxe dans différentes options de paramètre

Montant de la taxe = 100 EUR

| Paramètres de conversion de la taxe | Devise de la transaction (EUR) | Devise comptable (USD) | Devise de déclaration (GBP) | Devise de la taxe (GBP) |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| Devise comptable             | 100                        | 111                       | 83                       | **83,25**          |
| Devise de déclaration              | 100                        | 111                       | 83                       | **83**             |

Ce paramètre peut être configuré en fonction des exigences de conformité de l’administration fiscale.


### <a name="upgrade-consideration"></a>Remarques importantes relatives à la mise à niveau

Cette fonctionnalité ne s’appliquera qu’aux nouvelles transactions. Pour la transaction de taxe déjà enregistrée dans la table TAXTRANS mais pas encore réglée, le système ne recalculera pas le montant de la taxe dans la devise de la taxe car le taux de change au moment de la validation de la taxe est déjà manquant.

Pour éviter le scénario précédent, nous vous recommandons de modifier cette valeur de paramètre dans une nouvelle période de règlement de la taxe qui ne contient aucune transaction de taxe non réglée. Pour modifier cette valeur au cours d’une période de règlement de la taxe, exécutez le programme « Régler et valider la taxe » pour la période de règlement de la taxe actuelle avant de modifier cette valeur de paramètre.

Cette fonctionnalité ajoutera des écritures comptables qui clarifient les gains et les pertes des changes. Les écritures seront créées dans les comptes de profits et pertes d’ajustement de devise réalisés lorsque la réévaluation est effectuée pendant le règlement de la taxe. Pour plus d’informations, consultez la section [Équilibrage automatique du règlement de la taxe dans la devise de déclaration](#tax-settlement-auto-balance-in-reporting-currency) plus loin dans cette rubrique.

> [!NOTE]
> Lors du règlement, les informations des dimensions financières sont extraites des comptes de taxe, qui sont des comptes de bilan, et saisies dans les comptes de profits et pertes d’ajustement de devise, qui sont des comptes de relevé de profits et pertes. Étant donné que les restrictions sur la valeur des dimensions financières diffèrent entre les comptes de bilan et les comptes de relevé de profits et pertes, une erreur peut se produire pendant le processus Régler et valider la taxe. Pour éviter de devoir modifier les structures du compte, vous pouvez activer la fonctionnalité « Renseigner les dimensions financières des comptes de profits/pertes d’ajustement de devise réalisés pour le règlement de la taxe ». Cette fonctionnalité forcera la dérivation des dimensions financières vers les comptes de profits/pertes d’ajustement de devise. 

## <a name="track-reporting-currency-tax-amount"></a>Suivre le montant de la taxe dans la devise de déclaration

Trois nouveaux champs ont été ajoutés aux tables de taxe pour suivre les montants dans la devise de déclaration. Ces champs se trouvent dans les tables TAXUNCOMMITTED et TAXTRANS :

- TaxAmountRep : montant de la taxe dans la devise de déclaration
- TaxBaseAmountRep : montant de base dans la devise de déclaration
- TaxInCostPriceRep : montant non déductible dans la devise de déclaration

Pour la taxe uniquement enregistrée dans la table TAXUNCOMMITTED mais pas encore validée, le système recalculera le montant de la taxe dans la devise de déclaration au moment de la validation et de l’enregistrement dans la table TAXTRANS.

Cette version n’inclura pas les modifications des rapports et des formulaires qui affichent le montant de la taxe dans la devise de déclaration. Les modifications des rapports et des formulaires seront disponibles dans la prochaine version.



## <a name="tax-settlement-auto-balance-in-reporting-currency"></a>Équilibrage automatique du règlement de la taxe dans la devise de déclaration

Si le règlement de la taxe n’est pas équilibré dans la devise de déclaration pour une raison quelconque, par exemple le chemin de conversion de la taxe est « Devise comptable » ou le taux de change est modifié dans une période de règlement de la taxe, le système générera automatiquement des écritures comptables pour ajuster l’écart du montant de la taxe et le déduire du compte de profit/perte réalisé, qui est configuré dans les paramètres de comptabilité.

En utilisant l’exemple précédent pour démontrer cette fonctionnalité, supposons que les données de la table TAXTRANS au moment de la validation se présentent comme suit.

| Paramètres de conversion de la taxe | Devise de la transaction (EUR) | Devise comptable (USD) | Devise de déclaration (GBP) | Devise de la taxe (GBP) |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| Devise comptable             | 100                        | 111                       | 83                       | **83,25**          |
| Devise de déclaration              | 100                        | 111                       | 83                       | **83**             |

Lorsque vous exécutez le programme de règlement de la taxe en fin de mois, l’écriture comptable se présentera comme suit.
#### <a name="scenario-sales-tax-conversion--accounting-currency"></a>Scénario : conversion de la taxe = « Devise comptable »

| Compte principal           | Devise de la transaction (GBP) | Devise comptable (USD) | Devise de déclaration (GBP) |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| Taxe collectée/déductible | -83,25                     | -111                      | -83,25                   |
| Règlement de la taxe         | 83,25                      | 111                       | 83,25                    |
| Profit/perte réalisé     | 0                          | 0                         | -0,25                    |
| Taxe collectée/déductible | 0                          | 0                         | 0,25                     |

#### <a name="scenario-sales-tax-conversion--reporting-currency"></a>Scénario : conversion de la taxe = « Devise de déclaration »


| Compte principal           | Devise de la transaction (GBP) | Devise comptable (USD) | Devise de déclaration (GBP) |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| Taxe collectée/déductible | -83                        | -110,67                   | -83                      |
| Règlement de la taxe         | 83                         | 110,67                    | 83                       |
| Profit/perte réalisé     | 0                          | 0,33                      | 0                        |
| Taxe collectée/déductible | 0                          | -0,33                     | 0                        |



Pour plus d’informations, voir les rubriques suivantes :

- [Devise double](dual-currency.md)
- [Vue d’ensemble des taxes](indirect-taxes-overview.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
