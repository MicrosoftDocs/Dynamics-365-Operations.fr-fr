---
title: Fonds dans le secteur public
description: Cet article explique comment les entités du secteur public peuvent se servir des fonds pour attester de leur responsabilité financière. Un fonds est un ensemble de registres financiers en équilibre qui permet de contrôler et de surveiller l’utilisation planifiée de ressources, souvent pour se conformer aux exigences légales et administratives.
author: v-kiarnd
ms.date: 08/07/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerFund, LedgerFundType
audience: Application User
ms.reviewer: twheeloc
ms.custom: 19571
ms.assetid: c746c09f-dc9e-4381-ae92-e1af484064b6
ms.search.region: Global
ms.search.industry: Public sector
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4623e751cc4b72937a93b3e11dadd53551a5d432
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897943"
---
# <a name="funds-in-the-public-sector"></a>Fonds dans le secteur public

[!include [banner](../includes/banner.md)]

Un fonds est un ensemble de registres financiers en équilibre qui permet de contrôler et de surveiller l’utilisation planifiée de ressources, souvent pour se conformer aux exigences légales et administratives. Les organisations du secteur public se servent des fonds pour attester de leur responsabilité financière.

## <a name="what-general-ledger-parameters-should-be-set-for-funds"></a>Quels paramètres de comptabilité doivent être définis pour les fonds ?

Pour en savoir plus sur les paramètres de comptabilité requis pour les fonds, voir [Comptabilité dans le secteur public](general-ledger-public-sector.md).

## <a name="what-fund-classes-and-fund-types-do-i-need-to-set-up"></a>Quels classes et types de fonds dois-je paramétrer ?
Le Governmental Accounting Standards Board (GASB) recommande un ensemble de principes comptables généralement reconnus (GAAP) pour la comptabilité gouvernementale et locale. GAAP identifie huit types de fonds catégorisés en trois classes de fonds :

-   Fonds gouvernementaux
    -   Fonds général
    -   Fonds de financement particulier
    -   Fonds de projets d’immobilisations
    -   Fonds de service de la dette
-   Fonds propriétaires ou de type commercial
    -   Fonds d’entreprise
    -   Fonds de service interne
-   Fonds fiduciaires
    -   Fonds d’affectation spéciale
    -   Fonds en fidéicommis

Les trois classes de fonds GAAP, plus une classe **Mémo**, sont des options prédéfinies dans Dynamics 365 Finance. 

Les types de fonds sont définis en fonction des besoins de l’organisation. Dans la plupart des cas, vous paramètrerez les huit types de fonds GAAP. Les types de fonds regroupent les fonds à des fins de suivi et de génération d’états fiscaux détaillés. Si de nombreux fonds peuvent être inclus dans un seul état de niveau supérieur, chaque fonds reste toutefois une entité fiscale et comptable distincte disposant d’une comptabilité, de comptes de résultats et de bilans qui lui sont propres. 

Chaque fonds doit disposer d’un numéro de fonds unique. Les numéros de fonds servent de valeurs de dimension dans les numéros de compte financier, dans la mesure où une dimension a été mise en correspondance avec un fonds. Lorsqu’un numéro de compte est lié à un fonds spécifique, il fait partie de l’ensemble de registres financiers contenu dans ce fonds.

### <a name="example"></a>Exemple

Voici une liste de certains fonds qui peuvent être utilisés par une municipalité :

-   Fonds général
-   École de technologie
-   Technologies de l’information
-   Marché de producteurs
-   Commission de services publics
-   Service de messagerie
-   Fonds de rémunération des travailleurs
-   Régime de santé complet
-   Rémunération différée
-   Perceptions de taxes locales
-   Greffier

Le tableau suivant présente affiche ces fonds regroupés par classe et type de fonds.

| Classe de fonds | Type de fonds          | Numéro de fonds | Nom du fonds                    |
|----------------|------------------------|-----------------|----------------------------------|
| Gouvernemental   | Fonds général           | 1103            | Fonds général                     |
|                | Fonds de financement particulier  | 1343            | École de technologie             |
|                |                        | 1372            | Technologies de l’information           |
| Propriétaire    | Fonds d’entreprise       | 2501            | Marché de producteurs                   |
|                |                        | 2541            | Commission de services publics             |
|                | Fonds de service interne | 2723            | Service de messagerie                  |
|                |                        | 2738            | Fonds de rémunération des travailleurs       |
| Fiduciaire      | Caisses de retraite en fiducie    | 3320            | Régime de santé complet |
|                |                        | 3324            | Rémunération différée            |
|                | Fonds en fidéicommis           | 3912            | Perceptions de taxes locales      |
|                |                        | 3914            | Greffier                  |

## <a name="how-are-financial-dimensions-used-with-funds"></a>Comment les dimensions financières sont-elles utilisées avec les fonds ?
Chaque fonds doit disposer d’un numéro de fonds unique. Les numéros de fonds servent de valeurs de dimension dans les numéros de compte financier, dans la mesure où une dimension a été mise en correspondance avec un fonds. Lorsqu’un numéro de compte est lié à un fonds spécifique, il fait partie de l’ensemble de registres financiers contenu dans ce fonds. 

Les organisations du secteur public ont généralement besoin des écritures équilibrées pour les dimensions financières associées aux fonds. Lorsqu’une dimension financière ou une combinaison de dimensions est marquée pour exiger des écritures équilibrées, le système ne valide pas une transaction si les débits ne sont pas égaux aux crédits pour la dimension financière.

## <a name="how-do-i-set-a-fund-balance-to-carry-over-to-the-new-year"></a>Comment paramétrer un solde de fonds de sorte qu’il soit reporté sur la nouvelle année ?
Pour en savoir plus sur le traitement de fin d’exercice pour les fonds, voir [Traitement de fin d’exercice dans le secteur public](year-end-processing-public-sector.md).


Pour plus d’informations, voir les rubriques suivantes :

[Création d’un type de fonds](tasks/create-fund-type-public-sector.md)

[Paramétrer un fonds](tasks/set-up-fund-public-sector.md)






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
