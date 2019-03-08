---
title: Amortissement linéaire sur la durée de vie restante
description: Cet article propose une vue d'ensemble de la méthode d'amortissement linéaire sur la durée de vie restante.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13851
ms.assetid: 0fa2f71a-596c-414c-a6e6-8f7405a0bf81
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 720a7c581dc0f68b14b769e9c9af0df791d0c273
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "329664"
---
# <a name="straight-line-life-remaining-depreciation"></a>Amortissement linéaire sur la durée de vie restante

[!include [banner](../includes/banner.md)]

Cet article propose une vue d'ensemble de la méthode d'amortissement linéaire sur la durée de vie restante.

Lorsque vous définissez un profil d'amortissement de l'immobilisation et sélectionnez **Durée de vie linéaire restante** dans le champ **Méthode** sur la page **Profils d'amortissement**, l'amortissement des immobilisations affectées au profil d'amortissement est basé sur la durée de vie restante de l'immobilisation. Le montant d'amortissement est généralement identique dans chaque période d'amortissement. Pour paramétrer l'amortissement linéaire restant, vous devez également sélectionner les options dans les champs  **Année d'amortissement** et **Fréquence** sur la page **Profils d'amortissement**. Les options disponibles dans le champ **Fréquence** varient en fonction de la valeur sélectionnée dans le champ **Année d'amortissement**.

## <a name="select-a-depreciation-year"></a>Sélectionner une année d'amortissement
Vous pouvez sélectionner soit **Calendrier** soit **Exercice** dans le champ **Année d'amortissement** de la page **Profils d'amortissement**. La valeur par défaut est **Calendrier**. Votre sélection détermine les options disponibles dans le champ **Fréquence**. Ce champ définit les dates et les montants de validation de régularisation des amortissements au cours de l'année civile.

### <a name="calendar"></a>Calendrier

Si vous sélectionnez **Calendrier** dans le champ ***Année d'amortissement***, l'exercice supposé s'étend sur la période du 1er janvier au 31 décembre, même si vous avez défini le calendrier fiscal différemment. L'option **Calendrier** met à jour la base d'amortissement le 1er janvier de chaque année. Généralement, la base d'amortissement est la valeur nette moins la valeur résiduelle. Dans l'exemple plus loin dans cette rubrique, la base d'amortissement est le numérateur de la première expression de la colonne Calcul. Si vous sélectionnez **Calendrier** comme année d'amortissement, les options suivantes sont disponibles dans le champ **Fréquence** :

-   **Annuel** valide un montant le 31 décembre.
-   **Mensuel** valide un montant mensuel à la fin de chaque mois du calendrier.
-   **Trimestriel** valide un montant trimestriel à la fin de chaque trimestre du calendrier (31 mars, 30 juin, 30 septembre et 31 décembre).
-   **Semestriel** valide un montant semestriel à la fin de chaque semestre du calendrier (30 juin et 31 décembre).
-   **Quotidien** valide le montant d'amortissement pour la méthode d'amortissement quotidien en utilisant une transaction par jour.

Par exemple, si vous sélectionnez **Annuel**, l'amortissement annuel n'est validé qu'une seule fois, le 31 décembre de chaque année. Si vous sélectionnez **Mensuel**, l'amortissement mensuel est validé chaque mois comme 1/12 du montant d'amortissement annuel.

### <a name="fiscal"></a>Exercice

Si vous sélectionnez **Fiscal** dans le champ **Année d'amortissement**, l'amortissement restant linéaire est utilisé. L'amortissement est calculé sur la base des exercices restants. Par exemple, pour l'exercice allant du 1er juillet 2015 au 30 juin 2016 , le calcul de l'amortissement commence le 1er juillet. L'exercice peut avoir une longueur supérieure ou inférieure à 12 mois. L'amortissement est ajusté en fonction de chaque période fiscale. La longueur de l'exercice suivant découle de la définition des périodes fiscales sur la page **Calendriers fiscaux**. Si vous sélectionnez **Exercice** comme année d'amortissement, les options suivantes sont disponibles dans le champ **Fréquence** :

-   **Annuel** valide le montant total de l'amortissement calculé pour l'exercice comme montant unique, le dernier jour de l'exercice.
-   **Période fiscale**calcule le montant total de l'amortissement pour l'exercice. Ce montant est ensuite à recevoir dans les périodes fiscales définies sur la page **Calendriers fiscaux** pour le calendrier fiscal spécifié pour le registre.

## <a name="example-of-straight-line-depreciation-of-an-unchanged-fixed-asset"></a>Exemple d'amortissement linéaire d'une immobilisation inchangée
Une immobilisation possède les caractéristiques suivantes :

|                     |        |
|---------------------|--------|
| Coût d'acquisition    | 11 000 |
| Valeur résiduelle       | 1 000  |
| Base d'amortissement   | 10 000 |
| Années de durée de vie  | 5      |
| Amortissement annuel | 2 000  |

Le montant d'amortissement est le même chaque année : (Coût d'acquisition – Valeur résiduelle) ÷ Années de durée de vie

| Période | Calcul du montant d'amortissement annuel | Valeur comptable nette à la fin de l'exercice |
|--------|-----------------------------------------------|---------------------------------------|
| Année 1 | (11 000 – 1 000) ÷ 5 = 2 000                  | 9 000                                 |
| Année 2 | (9 000 – 1 000) ÷ 4 = 2 000                   | 7 000                                 |
| Année 3 | (7 000 – 1 000) ÷ 3 = 2 000                   | 5 000                                 |
| Année 4 | (5 000 – 1 000) ÷ 2 = 2 000                   | 3 000                                 |
| Année 5 | (3 000 – 1 000) ÷ 1 = 2 000                   | 1 000                                 |





