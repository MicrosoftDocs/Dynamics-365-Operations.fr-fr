---
title: "Amortissement linéaire sur la durée de vie"
description: "Cet article donne une vue d&quot;ensemble de la méthode d&quot;amortissement linéaire sur la durée de vie restante."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3341
ms.assetid: ae5ceaeb-aeb7-45cd-b835-23cf9c5cf95a
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: b210a69ee8675127f6799e0531c024c7b48f4e32
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="straight-line-service-life-depreciation"></a>Amortissement linéaire sur la durée de vie

[!include[banner](../includes/banner.md)]


Cet article donne une vue d'ensemble de la méthode d'amortissement linéaire sur la durée de vie restante.

Lorsque vous paramétrez un profil d'amortissement des immobilisations et sélectionnez Durée de vie linéaire dans le champ Méthode de la page Profils d'amortissement, l'amortissement des immobilisations affectées à ce profil d'amortissement est basé sur la durée de vie totale de l'immobilisation. Le montant d'amortissement est généralement identique dans chaque période d'amortissement. 

La différence dans le montant d'amortissement calculé entre la durée de vie linéaire restante et la durée de vie linéaire est quand un ajustement est validé dans l'immobilisation. 

Pour paramétrer l'amortissement linéaire sur la durée de vie, vous devez également sélectionner des options dans les champs Année d'amortissement et Fréquence de la page Profils d'amortissement.

## <a name="select-a-depreciation-year"></a>Sélection d'une année d'amortissement
Vous pouvez sélectionner soit Calendrier soit Exercice dans le champ Année d'amortissement de la page Profils d'amortissement. La sélection effectuée détermine les options disponibles dans le champ Période fréquence. L'option par défaut est Calendrier.

### <a name="calendar"></a>Calendrier

Si vous sélectionnez Calendrier, l'exercice supposé s'étend sur la période du 1er janvier au 31 décembre, même si vous avez défini le calendrier fiscal différemment. 

L'option Calendrier met à jour la base d'amortissement (généralement la valeur comptable nette moins la valeur résiduelle) le premier janvier de chaque année. Dans les exemples plus loin dans cette rubrique, la base d'amortissement est le numérateur de la première expression de la colonne Calcul. 

Si vous sélectionnez Calendrier, les options suivantes sont disponibles dans le champ Période fréquence qui définit les dates et les montants de validation de régularisation des amortissements au cours de l'année civile :
-   Annuel valide un montant le 31 décembre.
-   L'option Mensuellement valide un montant mensuel à la fin de chaque mois du calendrier.
-   L'option Trimestriel valide un montant trimestriel à la fin de chaque trimestre du calendrier (31 mars, 30 juin, 30 septembre et 31 décembre).
-   Semestriel valide un montant semestriel à la fin de chaque semestre du calendrier (30 juin et 31 décembre).
-   L'option Quotidien valide le montant d'amortissement pour la méthode d'amortissement quotidien à l'aide d'une transaction par jour.

Par exemple, si vous sélectionnez Annuel, l'amortissement annuel n'est validé qu'une seule fois, le 31 décembre de chaque année. Si vous sélectionnez Mensuellement, l'amortissement mensuel est validé chaque mois comme 1/12 du montant d'amortissement annuel.

### <a name="fiscal"></a>Exercice

Si vous sélectionnez Fiscal dans le champ Année d'amortissement, l'amortissement linéaire sur la durée de vie est utilisé. Il est calculé sur la base de l'exercice, qui est défini par le calendrier fiscal spécifié pour le registre, ou par le calendrier fiscal sélectionné sur la page Comptabilité. Les calendriers fiscaux sont paramétrés dans la page Calendriers fiscaux.

Par exemple, pour l'exercice allant du 1er juillet au 30 juin, le calcul de l'amortissement commence le 1er juillet. L'exercice peut avoir une longueur supérieure ou inférieure à 12 mois. L'amortissement est ajusté automatiquement en fonction de chaque période fiscale. La longueur de l'exercice suivant est basée sur les périodes fiscales paramétrées lors de la création d'un exercice dans l'écran Calendriers fiscaux. 

Si vous sélectionnez Fiscal, les options suivantes sont disponibles dans le champ Période fréquence :
-   Annuel valide le montant total de l'amortissement calculé pour l'exercice comme montant unique le dernier jour de l'exercice.
-   Période fiscale calcule le montant total de l'amortissement pour l'exercice, qui est à recevoir dans les périodes définies dans l'écran Calendriers fiscaux pour le calendrier fiscal.

## <a name="example-straight-line-depreciation-of-an-unchanged-fixed-asset"></a>Exemple : amortissement linéaire d'une immobilisation inchangée
Supposons que l'immobilisation présente les caractéristiques suivantes :

|                     |        |
|---------------------|--------|
| Coût d'acquisition    | 11 000 |
| Valeur résiduelle       | 1 000  |
| Base d'amortissement   | 10 000 |
| Années de durée de vie  | 5      |
| Amortissement annuel | 2 000  |

Vous obtenez le même montant d'amortissement chaque année. (coûts d'acquisition - valeur résiduelle) / années de durée de vie

| Période | Calcul du montant d'amortissement annuel | Valeur nette à la fin de l'exercice |
|--------|-------------------------------------------|---------------------------------------|
| Année 1 | (11 000 - 1 000) / 5 = 2 000              | 9 000                                 |
| Année 2 | (11 000 - 1 000) / 5 = 2 000              | 7 000                                 |
| Année 3 | (11 000 - 1 000) / 5 = 2 000              | 5 000                                 |
| Année 4 | (11 000 - 1 000) / 5 = 2 000              | 3 000                                 |
| Année 5 | (11 000 - 1 000) / 5 = 2 000              | 1 000                                 |

## <a name="example-straight-line-depreciation-of-a-modified-fixed-asset"></a>Exemple : amortissement linéaire d'une immobilisation modifiée

Supposons que vous ajoutez un ajustement d'acquisition de 4 000 pour l'année 2 à la même immobilisation. 

La durée de vie de l'ajustement d'acquisition est identique à celle de l'immobilisation et commence au moment de l'acquisition. Une valeur comptable nette reste à la fin de l'année 5, qui correspond à la valeur comptable nette de l'ajustement d'acquisition. L'amortissement par période est calculé comme dans le tableau suivant.

| Période | Calcul du montant d'amortissement annuel | Valeur comptable nette à la fin de l'exercice |
|--------|-------------------------------------------|---------------------------------------|
| Année 1 | 10 000 / 5 = 2 000                        | 11 000 - 2 000 = 9 000                |
| Année 2 | 4 000 (ajustement d'acquisition)            | 9 000 + 4 000 =13 000                 |
| Année 2 | 14 000 / 5 = 2 800                        | 13 000 - 2 800 = 10 200               |
| Année 3 | 14 000 / 5 = 2 800                        | 10 200 - 2 800 = 7 400                |
| Année 4 | 14 000 / 5 = 2 800                        | 7 400 - 2 800 = 4 600                 |
| Année 5 | 14 000 / 5 = 2 800                        | 4 600 - 2 800 = 1 800                 |
| Année 6 | 800 restants\*                           | 1 800 – 800 = 1 000                   |

\*Comme le montant restant est inférieur au montant d'amortissement, seul le montant restant moins la valeur résiduelle est pris.






