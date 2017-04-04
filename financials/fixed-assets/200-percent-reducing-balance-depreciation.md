---
title: "Amortissements dégressifs de 200 %"
description: "Cet article propose une vue d&quot;ensemble de la méthode d&quot;amortissement dégressif de 200 %."
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
ms.custom: 13951
ms.assetid: 69b4e010-7683-4dc2-8a06-6d572f37e903
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 8e89a57dda8f2d392483ed13c686ea97b74926b0
ms.openlocfilehash: 617d643517f4c40d6e870d1e7e676b0be28092dd
ms.lasthandoff: 03/31/2017


---

# <a name="200-percent-reducing-balance-depreciation"></a>Amortissements dégressifs de 200 %

Cet article propose une vue d'ensemble de la méthode d'amortissement dégressif de 200 %.

Si vous définissez un profil d'amortissement d'immobilisation, puis sélectionnez **Amortissement dégressif de 200 %** dans le champ **Méthode** de la page **Profils d'amortissement**, les immobilisations qui sont affectées à ce profil d'amortissement sont amorties par le même pourcentage pour chaque période d'amortissement. Le pourcentage est calculé sur la base de la durée de vie de l'immobilisation. Par exemple, si une immobilisation a une durée de vie de cinq ans, la valeur de pourcentage calculée est de 40 pourcent (200 % ÷ 5). 

Cette méthode est également appelée amortissement dégressif à taux double.

Pour paramétrer un amortissement dégressif de 200 %, vous devez également sélectionner des options dans les champs **Année d'amortissement** et **Fréquence** sur la page **Profils d'amortissement**. Les options disponibles dans le champ **Fréquence** varient en fonction de la valeur sélectionnée dans le champ **Année d'amortissement**.

## <a name="select-a-depreciation-year"></a>Sélectionner une année d'amortissement
Vous pouvez sélectionner soit **Calendrier** soit **Exercice** dans le champ **Année d'amortissement** de la page **Profils d'amortissement**. La valeur par défaut est **Calendrier**. 

Votre sélection détermine les options disponibles dans le champ **Fréquence**. Ce champ définit les dates et les montants de validation de régularisation des amortissements au cours de l'année civile.

### <a name="calendar"></a>Calendrier

Vous pouvez décider de conserver la valeur par défaut du champ **Année d'amortissement**, **Calendrier**. 

L'option **Calendrier** met à jour la base d'amortissement le 1er janvier de chaque année. Généralement, l'amortissement est la valeur nette moins la valeur de mise au rebut. Dans les exemples plus loin dans cette rubrique, la base d'amortissement est le numérateur de la première expression de la colonne Calcul. 

Si vous sélectionnez **Calendrier** comme année d'amortissement, les options suivantes sont disponibles dans le champ **Fréquence** :

-   **Annuel** valide un montant le 31 décembre.
-   **Mensuel** valide un montant mensuel à la fin de chaque mois du calendrier.
-   **Trimestriel** valide un montant trimestriel à la fin de chaque trimestre du calendrier (31 mars, 30 juin, 30 septembre et 31 décembre).
-   **Semestriel** valide un montant semestriel à la fin de chaque semestre du calendrier (30 juin et 31 décembre).
-   **Quotidien** valide le montant d'amortissement pour la méthode d'amortissement quotidien en utilisant une transaction par jour.

### <a name="fiscal"></a>Exercice

Si vous sélectionnez **Exercice** dans le champ **Année d'amortissement**, l'amortissement dégressif de 200 % est calculé sur la base de l'exercice du calendrier fiscal spécifié pour le registre, ou pour le calendrier fiscal sélectionné sur la page **Comptabilité**. Les calendriers fiscaux sont paramétrés sur la page **Calendriers fiscaux**. 

Par exemple, pour l'exercice allant du 1er juillet au 30 juin, le calcul de l'amortissement commence le le 1er juillet. L'exercice peut avoir une longueur supérieure ou inférieure à 12 mois. L'amortissement est ajusté en fonction de chaque période. La longueur de l'exercice suivant découle de la définition des périodes fiscales sur la page **Calendriers fiscaux**. 

Si vous sélectionnez **Fiscal** comme année d'amortissement, les options suivantes sont disponibles dans le champ **Fréquence** :

-   **Annuel** valide le montant total de l'amortissement calculé pour l'exercice comme montant unique, le dernier jour de l'exercice.
-   **Période fiscale **valide le montant total de l'amortissement calculé pour l'exercice. Ce montant est régularisé dans les périodes fiscales définies sur la page **Calendriers fiscaux**.

## <a name="example-of-200-reducing-balance-depreciation"></a>Exemple d'amortissement dégressif de 200 %
|                                |        |
|--------------------------------|--------|
| Prix d'acquisition               | 11 000 |
| Valeur résiduelle                  | 1 000 |
| Base d'amortissement              | 10 000 |
| Années de durée de vie             | 5      |
| Pourcentage d'amortissement annuel | 40 %    |

La méthode d'amortissement dégressif de 200 % divise 200 % par le nombre d'années de durée de vie. Le pourcentage ainsi obtenu est multiplié par la valeur comptable nette de l'actif afin de déterminer le montant d'amortissement pour chaque année.

| Période | Calcul du montant d'amortissement annuel | Valeur comptable             | Valeur comptable nette à la fin de l'exercice |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| Année 1 | (11 000 - 1 000) × 40 % = 4 000                | 11 000 - 4 000 = 7 000 | 11 000 - 1 000 - 4 000 = 6 000        |
| Année 2 | 6 000 × 40 % = 2 400                           | 7 000 - 2 400 = 4 600  | 6 000 - 2 400 = 3 600                 |
| Année 3 | 3 600 × 40 % = 1 440                           | 4 600 - 1 440 = 3 160  | 3 600 - 1 440 = 2 160                 |

> [!NOTE] 
> Généralement, lorsque le montant calculé à l'aide de la méthode d'amortissement dégressif de 200% devient inférieur au montant qui aurait calculé à l'aide de la méthode linéaire, une conversion en méthode linéaire pour la durée de vie restante.


