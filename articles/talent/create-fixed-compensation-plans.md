---
title: Créer des régimes de rémunération fixe
description: La rémunération fixe fait référence au salaire brut normal des employés. Cet article décrit les composants qui doivent être définis avant de créer un régime de rémunération fixe et y inscrire des employés.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompRefPointSetup, HRMCompEligibility, HRMCompEvent, HRMFixedCompPlanTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 15991
ms.assetid: ef8cf992-176c-4c98-9dff-6510e1eb9f1c
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: 0a31ea7d1df33d3f42e95d5e1152f00687954b04
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "858051"
---
# <a name="create-fixed-compensation-plans"></a>Créer des régimes de rémunération fixe

[!include [banner](includes/banner.md)]

La rémunération fixe fait référence au salaire brut normal des employés. Cette rubrique décrit les composants qui doivent être définis avant de créer un régime de rémunération fixe et y inscrire des employés.

Les montants de rémunération fixe peuvent être calculés pour vos employés en fonction de facteurs tels que les performances, la zone et les augmentations de budget. Microsoft Talent prend en charge les types de rémunération par échelon, niveau et structure.

## <a name="fixed-compensation-components"></a>Composants de rémunération fixe
### <a name="compensation-levels"></a>Niveaux de rémunération

Vous pouvez utiliser des **niveaux de rémunération** pour définir la rémunération pour diverses tâches, pour garantir que les employés qui exécutent ces tâches sont payés suffisamment. Sur la page **Niveaux de rémunération**, vous pouvez paramétrer les niveaux de rémunération requis pour chaque régime par échelon, niveau et structure. Utilisez les boutons **Haut** et **Bas** pour mettre les niveaux dans l'ordre correct, en fonction de leur type. En définissant des niveaux de rémunération sur une tâche, vous garantissez que tous les employés occupant un poste pour cette tâche sont payés au même niveau.

### <a name="reference-points"></a>Points de référence

Les **Points de référence** sont les colonnes dans la grille qui définissent les plages de rémunération pour chaque niveau. Le niveau de rémunération est la ligne dans la grille. Les points de référence habituels pour un régime de type niveau sont un minimum, une valeur médiane et un maximum. Vous créez des points de référence dans la page **Paramétrages de point de référence**.

### <a name="compensation-grids"></a>Grilles de rémunération

Après avoir paramétré les niveaux et les points de référence, vous pouvez les combiner pour créer une **grille de rémunération** Dans la page **Grilles de rémunération**, définissez les informations concernant la grille. Par exemple, spécifiez à quoi la grille est destinée à être utilisée, avec quel type de régime elle sera utilisée et quels points ou colonnes de référence sont requis dans la grille. Après avoir terminé d'entrer ces informations, cliquez sur **Structure de rémunération** pour ajouter des niveaux et des montants à votre grille. 

**Conseil :** utilisez la fonction **Modifications en masse** dans la structure de rémunération pour définir des montants initiaux, puis incrémentez par des pourcentages ou des montants dans tous vos niveaux ou points de référence.

### <a name="pay-frequencies"></a>Fréquences de paiement

Les **Fréquences de paiement** permettent de définir la manière dont le salaire de l'employé est spécifié (par exemple 10 € par heure/50 000 € par an), et la conversion entre les taux horaires, hebdomadaires, mensuels (12 mois) et annuels. Par exemple, une société qui utilise une semaine de travail de 38 heures pour ses employés horaires paramètre une fréquence de paiement associée à un taux horaire de 1, un taux hebdomadaire de 38, un taux mensuel de 164,6666666667, et un taux annuel de 1 976. Ces conversions permettent de calculer les différents taux de salaire qui apparaissent dans l'enregistrement de la rémunération fixe de l'employé.

## <a name="fixed-compensation-plans"></a>Régimes de rémunération fixe
Vous pouvez concevoir le régime de rémunération fixe pour combiner les composants que vous avez configurés. Pour créer un régime de rémunération fixe, ouvrez la page **Régimes de rémunération fixe**. Ici, vous pouvez attribuer à votre régime un nom et une description, sélectionner le type de régime dont il s'agit (échelon, niveau ou structure), sélectionner la fréquence de paiement que vous utiliserez pour le taux de salaire d'un employé (montant par heure, montant par an, etc.), puis définir certaines options qui contrôlent le mode de traitement de la rémunération. 

Le paramètre **Tolérance des valeurs hors limite** permet de spécifier avec quelle rigueur vous voulez assurer les montants de rémunération entre le nombre minimal et les montants maximaux. Une tolérance **Absolue** requiert que la rémunération soit dans la marge définie pour un niveau donné. Une tolérance **Souple** vous alerte lorsque le montant de rémunération n'est pas compris dans la plage, mais vous permet de continuer. Si vous définissez la tolérance sur **Aucune**, vous pouvez entrer tout montant de rémunération pour un employé sans recevoir d'avertissement ou de messages d'erreur. 

Le paramètre **Règle d'embauche** permet de spécifier si tous les employés doivent recevoir la même augmentation, indépendamment de la date à laquelle ils ont été engagés (**Règle d'embauche** = **Aucune**), ou si les employés doivent recevoir un pourcentage de la prime, selon la durée pendant laquelle ils ont été employés au cours du cycle (**Règle d'embauche** = **Pourcentage**). 

Une **matrice de l'utilisation de tranche** est utile si vous souhaitez réduire le temps requis pour que les employés atteignent la valeur médiane de leur tranche, ou augmenter le temps requis pour que les employés atteignent le point de référence maximal de la tranche. Par exemple, vous souhaitez donner aux employés qui sont dans les derniers 25 % de leur tranche 110 % de leur prime cible, mais vous souhaitez donner aux employés qui sont dans les premiers 25 % de leur tranche seulement 80 % de leur prime cible, pour les empêcher d'atteindre le maximum aussi rapidement. 

Après avoir défini les bases du régime de rémunération fixe, vous pouvez paramétrer la structure de rémunération du régime. Cliquez sur **Paramétrer la rémunération**. Une boîte de dialogue curseur s'ouvre et affiche les trois options suivantes :

-   Créer une grille de rémunération en sélectionnant un paramétrage de point de référence et en donnant à la grille un nom.
-   Créer une grille de rémunération en faisant une copie d'une grille existante que vous pouvez utiliser comme point de départ.
-   Utiliser une grille de rémunération existante déjà définie. Tous les régimes de rémunération qui utilisent la même grille reçoivent des mises à jour si cette grille est modifiée.

Après avoir sélectionné une option, la page **Structure de rémunération** s'ouvre et vous pouvez modifier la nouvelle grille de rémunération ou la grille de rémunération existante.

## <a name="fixed-compensation-enrollment"></a>Inscription à la rémunération fixe
### <a name="determine-who-is-eligible-for-the-plan"></a>Déterminez qui peut prétendre au régime

La première étape en inscrivant des employés dans un régime de rémunération fixe est de déterminer qui peut prétendre à la rémunération définie dans le régime. Tant que vous n'avez pas déterminé l'admissibilité, vous ne pouvez affecter le régime à aucun employé. Pour paramétrer l'admissibilité, ouvrez la page **Règles d'admissibilité**. Ici, vous créez une règle d'admissibilité pour votre régime de rémunération et définissez les critères qu'un employé doit remplir pour pouvoir prétendre à un régime. Vous pouvez limiter l'admissibilité selon un département, un syndicat, une région de rémunération (emplacement), une tâche, une fonction, un type de tâche ou un niveau de rémunération. Les employés peuvent être inscrits dans un régime de rémunération uniquement s'ils répondent à toutes les conditions définies sur la règle d'admissibilité. 

**Remarque :** les règles d'admissibilité s'appliquent pour déterminer l'admissibilité aux régimes de rémunération fixe et variable. 

La règle d'admissibilité prend en compte la valeur des champs spécifiques dans les enregistrements de la tâche, du poste, et de l'employé pour déterminer si un employé peut prétendre à un régime de rémunération.

-   Dans la page **Tâche**, la règle d'admissibilité prend en compte les champs suivants :
    -   le champ **Tâche**
    -   Sous l'onglet **Classification des tâches**, les champs **Fonction** et **Tâche**
    -   Sous l'onglet **Rémunération**, le champ **Niveau**
-   Dans la page **Postes**, la règle d'admissibilité prend en compte les champs **Département** et **Région de rémunération**.

La règle d'admissibilité considère également les syndicats associés à l'employé (dans la page **Employés**, sous l'onglet **Collaborateur**, cliquez sur **Informations personnelles** &gt; **Syndicats**).

### <a name="define-fixed-compensation-actions"></a>Définir les actions de rémunération fixe

Les **actions de rémunération fixe** sont utilisées quand vous paramétrez ou modifiez la rémunération fixe d'un employé. Les actions de rémunération fixe permettent de fournir des noms descriptifs pour les types d'actions qu'un responsable de la rémunération et des avantages peut effectuer. Les différents types d'action obéissent à une logique spéciale, de sorte qu'elles peuvent être utilisées à des moments spécifiques. 

Par exemple, lorsque la rémunération fixe est paramétrée pour un employé, seules les actions de type **Embaucher/Réembaucher** peuvent être utilisées. Dans ce cas, vous souhaitez peut-être créer trois actions différentes du type **Embaucher/Réembaucher**, et les nommer **Embaucher**, **Réembaucher** et **Transfert**. Vous obtenez ainsi une explication plus descriptive de la raison pour laquelle la rémunération fixe a été donnée à un employé ou modifiée.

### <a name="enroll-the-employee"></a>Inscrire l'employé

Vous pouvez désormais affecter un employé à un régime de rémunération fixe. Ouvrez la page **Employés**, puis sélectionnez l'employé à inscrire dans le régime de rémunération. Dans le volet Actions, cliquez sur **Rémunération** &gt; **Régime fixe**. Vous pouvez désormais créer une action de rémunération fixe pour cet employé. 

**Remarque :** le champ régime de rémunération affiche seulement les régimes auxquels un employé peut prétendre selon les règles d'admissibilité paramétrées pour chaque régime. Si aucune règle d'admissibilité n'est définie pour un régime, aucun employé ne pourra y prétendre. 

Le système vérifie que le montant de rémunération spécifié pour un régime de rémunération du type niveau ou structure est compris dans les points de référence minimum et maximum pour le niveau de rémunération donné dans la tâche de l'employé. Si le montant de rémunération est en dehors de la plage autorisée, un avertissement ou un message d'erreur s'affiche, selon le niveau de tolérance défini dans le régime de rémunération fixe.

<a name="additional-resources"></a>Ressources supplémentaires
--------

[Régimes de rémunération](compensation-plans.md)



