---
title: Analyse budgétaire dans le secteur public
description: Cet article décrit l’utilisation de la page d’analyse de budget pour afficher les produits et les dépenses par dimension financière, puis elle répond aux questions posées fréquemment, notamment les différences entre la page d’analyse de budget et la page de statistiques de contrôle budgétaire.
author: v-kiarnd
ms.date: 01/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 19641
ms.assetid: a1055712-0a20-425d-939d-de8564c358b8
ms.search.industry: Public sector
ms.search.form: BudgetAnalysisInquiry_PSN, BudgetControlStatistics, DimensionDetails, LedgerPeriodCode, LedgerTrialBalanceListPage
ms.openlocfilehash: e02e592b29c77a8c5c78377ec126993b0002da3d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273717"
---
# <a name="budget-analysis-in-the-public-sector"></a>Analyse budgétaire dans le secteur public

[!include [banner](../includes/banner.md)]

Cet article décrit l’utilisation de la page d’analyse de budget pour afficher les produits et les dépenses publiés par dimension financière, puis elle répond aux questions posées fréquemment, notamment les différences entre la page d’analyse de budget et la page de statistiques de contrôle budgétaire. 

Cet article décrit la fonctionnalité d’analyse budgétaire pour le secteur public. 

Avant de lire cet article, vous devez également lire [Vue d’ensemble de budgétisation dans le secteur public](budgeting-public-sector.md). 

Il est possible que vous deviez paramétrer les fonctionnalités de budgétisation suivantes pour le secteur public : La page **Analyse budgétaire** permet d’afficher les produits et les dépenses publiés par dimension financière, à l’aide d’une combinaison de données comptables et de contrôle budgétaire. Vous pouvez afficher les montants et les détails de transaction récapitulés pour les budgets révisés, les dépenses réelles, les engagements et les engagements préalables. 

Les produits et les dépenses peuvent être récapitulés par les différents niveaux des dimensions financières. Par exemple, si les dimensions de budget sont les fonds, l’organisation et le compte principal, vous pouvez sélectionner **Fonds**, **Organisation** ou **Compte principal** pour voir l’activité financière récapitulative à ce niveau. 

La page **Analyse budgétaire** permet également de sélectionner un ensemble de dimensions financières et un ensemble de colonnes. Sélectionnez ou spécifiez les éléments suivants, puis cliquez sur **Mettre à jour les totaux :**

-   Paramètres
-   Informations sur la date
-   Dimensions financières

> [!NOTE] 
> Vous créez des dimensions financières sur la page **Dimensions financières**. Vous spécifiez l’intervalle de dates pour les transactions incluses sur la page **Intervalles de dates** de la comptabilité.

## <a name="what-transaction-details-are-available-on-the-budget-analysis-page"></a>Quels détails de la transaction sont-ils disponibles sur la page Analyse budgétaire ?
Vous pouvez sélectionner un article dans la grille et effectuer un zoom avant pour afficher les détails de transaction suivants :

-   **Budget révisé** montants (somme des montants du budget d’origine, de la révision, du transfert, et des montants reportés)
-   **Dépenses réelles** (la somme des débits et des crédits validés pour les valeurs de dimension financière)
-   **Engagements** et **Engagements préalables** (y compris les transactions d’origine et d’exonération)

### <a name="tips"></a>Conseils

-   Vous pouvez afficher les écritures de registre budgétaire révisées pour la recherche d’analyse budgétaire en cliquant sur **Budget révisé** dans le volet Actions. Les types de budget pour les écritures de registre budgétaires révisées comprennent le budget d’origine, le report, le transfert et la révision. Ces montants proviennent des tableaux d’entrées de registre budgétaire.
-   Pour afficher les dépenses réelles pour la recherche d’analyse budgétaire, cliquez sur **Réel**. La page affecte la page d’origine du document, par exemple une écriture comptable avancée. Ces montants proviennent des tables d’entrée de compte général, sauf si l’option **Dépense avec report** est sélectionnée. Lorsque cette option est sélectionnée, les tables source budgétaire sont utilisées.
-   Pour afficher les engagements et les transactions référencées pour la recherche d’analyse budgétaire, cliquez sur **Engagement**. La page affecte la réservation budgétaire générale (si implémentée) ou la commande fournisseur pour la transaction sélectionnée. Ces montants proviennent des tableaux de suivi de la source budgétaire.
-   Pour afficher les engagements préalables et les transactions référencées pour la recherche d’analyse budgétaire, cliquez sur **Engagement préalable**. La page affecte la demande d’achat pour la transaction sélectionnée. Ces montants proviennent des tableaux de suivi de la source budgétaire.

## <a name="should-i-use-the-budget-control-statistics-page-or-the-budget-analysis-page"></a>Dois-je utiliser la page Statistiques de contrôle budgétaire ou la page Analyse budgétaire ?
La page **Statistiques de contrôle budgétaire** est l’outil à utiliser lorsque vous souhaitez analyser un compte budgétaire unique, ou une combinaison ou un groupe de comptes par période et dimension de contrôle budgétaire. La page **Analyse budgétaire** est plus flexible. Vous pouvez l’utiliser pour réaliser une recherche dans n’importe quel ordre de dimension du plan de comptes ou pour rechercher un sous-ensemble d’un compte. Par exemple, vous pouvez afficher une liste des totaux de fonds de l’année en cours, accéder à un fonds spécifiques pour afficher les totaux du service, puis accéder à un département spécifique pour afficher les totaux des comptes.

Le tableau suivant décrit les différences entre ces pages.

| Page Statistiques de contrôle budgétaire | Analyse budgétaire                        |
|---|---|
| Affiche les soldes budgétaires pour un cycle budgétaire et un modèle de budget pour une seule valeur de dimension financière ou un groupe budgétaire. | Affiche les montants budgétaires combinés pour plusieurs valeurs de dimension financière simultanément. |
| Inclut les données des engagements confirmés et non confirmés.                                                         | Inclut les données des engagements confirmés uniquement.                                             |
| Inclut les données des comptes de dépenses uniquement.                                                                               | Inclut les données des comptes de produit et de dépenses.                                       |

> [!NOTE] 
> Si vous souhaitez que les montants budgétaires disponibles ou restants comprennent des transactions provisoires, utilisez la page **Statistiques de contrôle budgétaire**. La page **Analyse budgétaire** affiche uniquement les transactions validées.

## <a name="can-i-export-the-budget-analysis-results-to-microsoft-excel"></a>Puis-je exporter les résultats de l’analyse budgétaire vers Microsoft Excel ?
Oui, vous pouvez exporter les résultats de l’analyse budgétaire. Sur la page **Analyse budgétaire**, appuyez sur Ctrl+Maj+E.

## <a name="how-do-i-display-information-for-a-specific-closing-period"></a>Comment puis-je afficher les informations pour une période de clôture spécifique ?
Pour afficher les soldes et les informations pour une période de clôture spécifique, utilisez la page **Balance comptable**. La page **Analyse budgétaire** ne distingue pas les périodes d’exploitation et les périodes de clôture.

## <a name="can-i-analyze-the-budget-in-a-dimension-order-thats-different-from-the-expense-account-structure"></a>Puis-je analyser le budget dans un ordre de dimension différent de la structure de compte de dépenses ?
Oui. Par exemple, vous pouvez souhaiter afficher certains comptes principaux sur plusieurs programmes ou d’autres dimensions. Vous pouvez créer des ensembles de dimensions financières qui reflètent la manière dont vous souhaitez analyser vos données. Pour ce faire, utilisez la page **Ensembles de dimensions financières** du module Comptabilité. Pour afficher les comptes principaux sur les programmes, par exemple, créez un ensemble de dimensions Programmes, puis ajoutez des dimensions à par l’intermédiaire du paramètre **MainAccount**. Lorsque vous revenez sur la page **Analyse budgétaire** et que vous sélectionnez cet ensemble de dimensions, le budget apparaît comme une liste des comptes principaux. Vous pouvez ensuite accéder à n’importe quel compte principal pour inclure le niveau de programme de l’ensemble de dimensions, qui décompose tous les totaux par programme dans ce compte principal.

## <a name="what-if-the-financial-dimension-set-that-i-want-to-use-isnt-included-on-the-page"></a>Que faire si l’ensemble de dimensions financières que je souhaite utiliser n’est pas inclus sur la page ?
Tous les ensembles de dimensions financières existants sont affichés sur la page **Analyse budgétaire**. Si vous ne voyez pas celui que vous souhaitez, vous pouvez le créer dans le module Comptabilité.

## <a name="what-is-the-carry-forwards-column-set-used-for"></a>À quoi sera la colonne Reports ?
Utilisez l’ensemble de colonnes **Budget de dépenses avec report** si vous reportez le budget pour des commandes fournisseur en cours en fin d’exercice. Cet ensemble de colonnes affiche des totaux distincts pour les transactions qui utilisent le budget actif de l’exercice précédent et pour les transactions qui utilisent le budget du nouvel exercice. Cela facilite la surveillance des montants budgétés, engagés et dépensés relatifs à des transactions de l’année précédente.

## <a name="what-should-i-do-if-the-grids-are-empty-even-when-ive-selected-all-the-values"></a>Que dois-je faire si les grilles sont vides alors que j’ai sélectionné toutes les valeurs ?
Si les grilles sont vides sur la page **Analyse budgétaire**, tentez les actions suivantes pour résoudre le problème :

-   Cliquez sur **Mettre à jour les totaux** après avoir défini les valeurs en haut de la page.
-   Vérifiez que l’ensemble de dimensions sélectionné comprend la valeur de dimension que vous recherchez.
-   Vérifiez que la couche de validation et les dates sont correctes pour les valeurs que vous recherchez.
-   Vérifiez que le document de transaction que vous recherchez a été validé ou confirmé. Seules les transactions validées sont affichées sur la page **Analyse budgétaire**.

## <a name="how-do-i-see-updated-numbers-in-the-columns-when-i-change-the-dimension-set-dates-posting-layers-and-other-settings"></a>Comment afficher les numéros mis à jour dans les colonnes lorsque je modifie l’ensemble de dimensions, les dates, les couches de validation, et d’autres paramètres ?
Après avoir modifié les paramètres en haut de la page, cliquez sur **Mettre à jour les totaux** pour afficher les résultats de votre requête.

## <a name="feature-budget-control-statistics-date-range-enhancements"></a>Fonctionnalité : Améliorations de la plage de dates des statistiques de contrôle budgétaire
Cette fonctionnalité offre une nouvelle vue où afficher uniquement les montants réels à l’intérieur de la plage de dates indiquée sur l’enquête **Statistiques de contrôle budgétaire**. Cette fonctionnalité est activée par défaut dans la 2ème vague de lancement 2022. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
