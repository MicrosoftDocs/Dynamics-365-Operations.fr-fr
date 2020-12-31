---
title: Recalculer les coûts de remplacement et les valeurs assurées pour des groupes d’immobilisations
description: Cet article décrit le processus pour mettre à jour les coûts de remplacement et les valeurs assurées pour des immobilisations.
author: ShylaThompson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3261
ms.assetid: b8876f83-8772-4f2a-b277-12724e2a0c44
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a9dd04072b4845fe5df2a918b64ba1835ea584dd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443230"
---
# <a name="recalculate-replacement-costs-and-insured-values-for-fixed-asset-groups"></a>Recalculer les coûts de remplacement et les valeurs assurées pour des groupes d’immobilisations

[!include [banner](../includes/banner.md)]

Cet article décrit le processus pour mettre à jour les coûts de remplacement et les valeurs assurées pour des immobilisations.

Il est possible que vous soyez régulièrement averti que le coût de remplacement ou d’assurance des immobilisations spécifiques a été modifié. Par exemple, votre gestionnaire peut vous indiquer que l’inflation a été de 3 pour cent l’année passée et que vous devez augmenter le coût de remplacement de toutes les immobilisations de 3 pour cent. 

Bien que vous puissiez modifier le coût de remplacement et la valeur assurée des immobilisations individuelles dans la page **Immobilisations**, vous pouvez utiliser la page **Mettre à jour les coûts de remplacement et les valeurs assurées** pour mettre à jour ces valeurs pour un groupe d’immobilisations en une fois. Les informations suivantes décrivent la mise à jour des valeurs pour les groupes d’immobilisations ou des immobilisations spécifiques au sein des groupes.

## <a name="how-values-are-updated"></a>Procédure de mise à jour des valeurs
Pour recalculer les coûts de remplacement et les valeurs assurées des groupes d’immobilisations, vous devez tout d’abord spécifier le pourcentage de modification des valeurs assurées et des coûts de remplacement existants, puis procéder à la mise à jour périodique pour effectivement recalculer les valeurs. Spécifiez le pourcentage dans les champs **Facteur Coût de remplacement** et **Facteur Valeur assurée** de la page **Groupes d’immobilisations**. Bien que vous puissiez utiliser ces facteurs pour le groupe d’immobilisations, lorsque vous utilisez la page **Mettre à jour les coûts de remplacement et les valeurs assurées**, vous pouvez choisir de recalculer le coût de remplacement et la valeur assurée uniquement pour les immobilisations spécifiques d’un groupe. 

Lorsque vous utilisez la page **Mettre à jour les coûts de remplacement et les valeurs assurées** pour recalculer le coût de remplacement et la valeur assurée pour les immobilisations, les formules suivantes sont utilisées :

-   \[(Facteur de coût de remplacement du groupe d’immobilisations / 100) + 1\] \* Coût de remplacement existant des immobilisations
-   \[(Facteur de valeur assurée du groupe d’immobilisations / 100) + 1\] \* Valeur assurée existante des immobilisations

> [!NOTE] 
> Lorsque vous utilisez la page **Mettre à jour les coûts de remplacement et les valeurs assurées**, le coût de remplacement et la valeur assurée sont mis à jour pour les immobilisations sélectionnées ; vous ne pouvez pas spécifier qu’une seule valeur doit être mise à jour. Pour laisser une valeur inchangée et en mettre une autre à jour, entrez 0 (zéro) comme facteur dans la page **Groupes d’immobilisations**. Si le facteur est nul ou non défini, le calcul est ignoré dans la mise à jour. La valeur comptable et la valeur comptable nette des immobilisations ne sont pas affectées par la mise à jour périodique. 

## <a name="how-to-use-a-date-to-select-which-items-to-update"></a>Utilisation d’une date pour sélectionner les articles à mettre à jour
Par défaut, le processus met à jour les immobilisations sélectionnées qui n’ont pas été mises à jour à la date actuelle, mais qui ont peut-être été mises à jour les jours précédents. Par exemple, &lt; la date actuelle signifie « avant aujourd’hui ». Vous pouvez modifier la date dans la page **Mettre à jour les coûts de remplacement et les valeurs assurées** en cliquant sur le bouton **Sélection**. Le critère de la date que vous spécifiez est comparé à la date de la dernière mise à jour périodique pour l’immobilisation (champ **Dernière mise à jour de la valeur périodique/des coûts** de la page **Immobilisations**). Chaque fois que vous mettez à jour le coût de remplacement ou la valeur assurée d’une immobilisation, le champ **Dernière mise à jour de la valeur périodique/des coûts** est automatiquement mis à jour avec la date actuelle. 

Exemple 

Vous avez mis à jour le coût de remplacement pour les groupes Véhicules, Mobilier de bureau et Bâtiments de 5 pour cent hier et vous considérez à présent que ces immobilisations sont précisément mises à jour. Pour exclure ces immobilisations lors de la mise à jour de toutes les immobilisations du jour, vous entrez une date dans le champ **Dernière mise à jour de la valeur périodique/des coûts** antérieur à hier (&lt; date d’hier), car la dernière mise à jour pour les groupes **Véhicules**, **Mobiliers de bureau** et **Bâtiments** est survenue en dehors des critères de dates que vous avez entrés.

## <a name="cumulative-effect-of-each-update"></a>Effet cumulatif pour chaque mise à jour
Chaque mise à jour a un effet cumulatif. Vous devez donc soigneusement planifier vos mises à jour. Par exemple, si vous augmentez toutes les immobilisations de 3 pour cent le mardi et si vous augmentez le mobilier de bureau de 4 pour cent le vendredi, assurez-vous que vous augmentez le mobilier de bureau d’un total de 7,12 pour cent.

## <a name="scenario"></a>Scénario
Votre gestionnaire vous signale les modifications suivantes dans les immobilisations :
-   Une augmentation du coût de remplacement de toutes les immobilisations, excepté les ordinateurs, de 3,25 pour cent.
-   Une augmentation du coût de remplacement de toutes les fournitures de bureau d’1 pour cent supplémentaire.
-   Une diminution du coût de remplacement et de la valeur assurée de tous les ordinateurs de 10 pour cent.

Vous apportez les modifications suivantes :
1.  Dans la page **Groupes d’immobilisations**, pour tous les groupes d’immobilisations excepté le groupe **Mobiliers de bureau** et le groupe **Ordinateurs**, entrez 3,25 dans le champ **Facteur Coût de remplacement** et 0 dans le champ **Facteur Valeur assurée**.
2.  Pour le groupe **Mobiliers de bureau**, entrez 4,25 dans le champ **Facteur Coût de remplacement** et 0 dans le champ **Facteur Valeur assurée**.
3.  Pour le groupe **Ordinateurs**, entrez -10 dans le champ **Facteur Coût de remplacement** et -10 dans le champ **Facteur Valeur assurée**.
4.  Dans la page **Mettre à jour les coûts de remplacement et les valeurs assurées**, cliquez sur **OK** pour effectuer le recalcul pour toutes les immobilisations.

Le jour suivant, votre gestionnaire vous signale que les ordinateurs ont diminué de 8 pour cent au lieu de 10 pour cent. Vous devez donc corriger les coûts de remplacement et les valeurs assurées. Pour corriger l’erreur, utilisez l’une des deux méthodes suivantes :
-   Modifiez manuellement les champs **Valeur assurée** et **Coût de remplacement** dans la page **Immobilisations** pour chaque immobilisation dans le groupe d’immobilisations **Ordinateurs**. Calculez et entrez manuellement les valeurs comme si vous aviez diminué le compte initial de 8 pour cent. Cette méthode ne nécessite pas l’utilisation de la page **Mettre à jour les coûts de remplacement et les valeurs assurées**.
-   Entrez les facteurs de coût de remplacement et de valeur assurée pour le groupe **Ordinateurs** dans les champs **Facteur Coût de remplacement** et **Facteur Valeur assurée** dans la page **Groupes d’immobilisations**. Cela permet de réinitialiser les immobilisations à leur valeur initiale (avant la diminution de 10 pour cent) et d’appliquer la diminution de 8 pour cent à la valeur initiale. La page **Mettre à jour les coûts de remplacement et les valeurs assurées** permet ensuite de recalculer les valeurs sur la base des facteurs que vous avez entrés.

> [!NOTE]  
> Vous ne pouvez pas contrepasser le facteur –10 en entrant un facteur positif 10 (ou un facteur 2, la différence entre –10 et –8) car les montants ne seront pas calculés comme vous le souhaitez. 





