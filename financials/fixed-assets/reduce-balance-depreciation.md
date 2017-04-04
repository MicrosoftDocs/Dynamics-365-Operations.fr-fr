---
title: "Réduire l&quot;amortissement de solde"
description: "Cet article donne une vue d&quot;ensemble de la méthode d&quot;amortissement dégressif."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3281
ms.assetid: 1b86763d-d47c-4a6a-a9a6-d97a736750da
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b41901d573e977a89fcd1a7c1ebf7185e162c654
ms.openlocfilehash: 0dede1cabccf672475ea242f05d5de06dc8e78c5
ms.lasthandoff: 03/31/2017


---

# <a name="reduce-balance-depreciation"></a>Réduire l'amortissement de solde

Cet article donne une vue d'ensemble de la méthode d'amortissement dégressif.

Si vous définissez un profil d'amortissement d'immobilisation, puis sélectionnez Dégressif dans le champ Méthode de la page Profils d'amortissement, les immobilisations auxquelles ce profil d'amortissement a été affecté sont amorties par le même pourcentage pour chaque période d'amortissement.

Pour paramétrer l'amortissement dégressif, vous devez également effectuer des sélections dans l'organisateur Général de la page Profils d'amortissement. Commencez par sélectionner une année dans le champ Année d'amortissement. En fonction de la sélection, différentes options s'affichent dans le champ Période fréquence, comme expliqué dans les sections ci-dessous. 

Vous devez également entrer une valeur dans le champ Pourcentage du profil d'amortissement. Si vous sélectionnez l'option Amortissement complet, la base d'amortissement restante est prise dans la dernière période d'amortissement et peut représenter un montant important. Certains pays/régions n'utilisent pas de basculement vers une méthode linéaire. Un basculement se produit lorsque le montant de la méthode alternative d'amortissement est supérieur ou égal au montant du profil d'amortissement principal, et que le montant d'amortissement pris en compte est le montant alternatif. 

Puisqu'une immobilisation ne sera jamais totalement amortie sur la base d'un calcul de pourcentage, vous devez sélectionner l'option Amortissement complet pour amortir complètement une immobilisation.

## <a name="select-a-depreciation-year"></a>Sélection d'une année d'amortissement
Vous pouvez sélectionner soit Calendrier soit Exercice dans le champ Année d'amortissement de la page Profils d'amortissement. La sélection effectuée détermine les options disponibles dans le champ Période fréquence. L'option par défaut est Calendrier.

### <a name="calendar"></a>Calendrier

L'option Calendrier met à jour la base d'amortissement (généralement la valeur comptable nette moins la valeur de mise au rebut) le premier janvier de chaque année. Dans l'exemple d'amortissement dégressif donné plus loin dans cette rubrique, la base d'amortissement est le numérateur de la première expression des calculs de la colonne de calcul. 

Si vous sélectionnez Calendrier, les options suivantes sont disponibles dans le champ Période fréquence qui définit les dates et les montants de validation de régularisation des amortissements au cours de l'année civile :

-   L'option Annuel valide annuellement le 31 décembre.
-   L'option Mensuellement valide un montant mensuel à la fin de chaque mois du calendrier.
-   L'option Trimestriel valide un montant trimestriel à la fin de chaque trimestre du calendrier (31 mars, 30 juin, 30 septembre et 31 décembre).
-   L'option Semestriel valide un montant semestriel à la fin de chaque semestre du calendrier (30 juin et 31 décembre).
-   L'option Quotidien valide le montant d'amortissement pour la méthode d'amortissement quotidien à l'aide d'une transaction par jour.

Par exemple, si vous sélectionnez Annuel, l'amortissement annuel n'est validé qu'une seule fois, le 31 décembre de chaque année. Si vous sélectionnez Mensuellement, l'amortissement mensuel est validé chaque mois comme 1/12 du montant d'amortissement annuel.

### <a name="fiscal"></a>Exercice

Si vous sélectionnez Exercice dans le champ Année d'amortissement, la méthode d'amortissement linéaire est utilisée. Elle est calculée en fonction de l'exercice, qui est paramétré dans la page Calendriers fiscaux pour le calendrier fiscal sélectionné dans la page Comptabilité . Par exemple, pour l'exercice allant du 1er juillet au 30 juin, le calcul de l'amortissement commence le 1er juillet. L'exercice peut avoir une longueur supérieure ou inférieure à 12 mois. L'amortissement est ajusté en fonction de chaque période fiscale. La longueur de l'exercice suivant est basée sur les périodes fiscales paramétrées lors de la création d'un exercice dans la page Calendriers fiscaux.


Si vous sélectionnez Fiscal, les options suivantes sont disponibles dans le champ Période fréquence :

-   Annuel valide le montant total de l'amortissement calculé pour l'exercice comme montant unique le dernier jour de l'exercice.
-   Période fiscale valide le montant total de l'amortissement calculé pour l'exercice, qui est provisionné dans les périodes fiscales définies pour le calendrier fiscal sélectionné dans la page Comptabilité, ou pour le calendrier fiscal sélectionné pour le registre pour une immobilisation.

## <a name="example-of-reducing-balance-depreciation"></a>Exemple d'amortissement dégressif

Supposons que le prix d'acquisition d'immobilisation soit 11 000, la valeur de mise au rebut 1 000 et le pourcentage d'amortissement 30. 

En utilisant la méthode d'amortissement dégressif, les 30 % de la base d'amortissement (valeur nette moins valeur de mise au rebut) sont calculés à la fin de la période d'amortissement précédente. L'amortissement pour les trois premières années est indiqué dans le tableau suivant.

| Période | Calcul du montant d'amortissement annuel | Valeur comptable nette à la fin de l'exercice |
|--------|-------------------------------------------|---------------------------------------|
| Année 1 | (11,000 - 1,000) \* 30% = 3,000           | (11 000 - 1 000) - 3 000 = 7 000      |
| Année 2 | (7,000 - 1,000) \* 30% = 1,800            | (7 000 -1 800) = 5 200                |
| Année 3 | (5,200 - 1,000) \* 30% = 1,260            | (5 200 - 1 260) = 3 940               |

 
-




