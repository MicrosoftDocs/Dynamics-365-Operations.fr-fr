---
title: Accorder des congés sur la base des heures travaillées
description: Cette rubrique décrit comment les plans de congés peuvent être configurés pour accorder des congés sur la base des heures travaillées.
author: andreabichsel
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-09-17
ms.dyn365.ops.version: ''
ms.openlocfilehash: 229ae14b9e2dedcd0ade094a772f16c0524d32a7
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006076"
---
# <a name="accrue-time-off-based-on-hours-worked"></a>Accorder des congés sur la base des heures travaillées

## <a name="overview"></a>Vue d'ensemble

Les organisations qui ont des employés rémunérés à l'heure peuvent accorder des congés sur la base des heures travaillées au lieu de l'ancienneté dans l'organisation. Les données sur les heures travaillées sont généralement stockées dans un système de pointage. 

## <a name="leave-plans"></a>Plans de congés

Dans le plan de congés, le type de régularisation peut être Mois de service ou Heures travaillées. Lorsque l'option Heures travaillées est sélectionnée, deux types d'heures peuvent être utilisés pour la régularisation : Normal et Heures supplémentaires.

Pour paramétrer un plan de congés pour utiliser les heures travaillées, procédez comme suit :

1. Dans la page **Plans de congé et d'absence**, cliquez sur **Créer un plan**.
2. Entrez un nom pour votre plan de congés.
3. Sélectionnez la fréquence de régularisation du plan.
5. Sélectionnez la date de début du plan.
6. Choisissez la base de la période de régularisation et sélectionnez la date spécifique à l'employé, le cas échéant.
7. Pour le programme de régularisation, sélectionnez **Heures travaillées** pour le type de régularisation.
8. Sélectionnez le type d'heures à utiliser pour la régularisation.
9. Entrez le nombre d'heures travaillées et le montant de régularisation associé, le solde minimal et le montant de report ou de subvention maximal.

Le processus de régularisation pour les plans d'heures travaillées utilise la fréquence de régularisation, ainsi que la base de la période de régularisation, pour déterminer les heures à régulariser.

## <a name="annual-accrual-frequency"></a>Fréquence de régularisation annuelle

| Date de régularisation    | Niveau d'heures travaillées    | Montant de régularisation        | Dates des heures travaillées   | Heures réelles travaillées| Prime               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 31/12/2018            | 2080                 | 144                   | 1/1/2018-31/12/2018  | 2085                | 144                 |        
| 31/12/2018            | 2080                 | 144                   | 1/1/2018-31/12/2018  | 2 000                | 0                 |


## <a name="monthly-accrual-frequency"></a>Fréquence de régularisation mensuelle

| Date de régularisation    | Niveau d'heures travaillées    | Montant de régularisation        | Dates des heures travaillées   | Heures réelles travaillées| Prime               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 31/8/2018             | 160                  | 12                    | 1/8/2018-31/8/2018   | 184                 | 12                  |        
| 31/8/2018             | 160                  | 3                     | 1/8/2018-31/8/2018   | 184                 | 3                   |

## <a name="semi-monthly-accrual-frequency"></a>Fréquence de régularisation bimensuelle

| Date de régularisation    | Niveau d'heures travaillées    | Montant de régularisation        | Dates des heures travaillées   | Heures réelles travaillées| Prime               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 31/8/2018             | 80                   | 6                     | 16/8/2018-31/8/2018  | 81                  | 6                  |        
| 31/8/2018             | 80                   | 6                     | 16/8/2018-31/8/2018  | 75                  | 0                   |

## <a name="weekly-accrual-frequency"></a>Fréquence de régularisation hebdomadaire

| Date de régularisation    | Niveau d'heures travaillées    | Montant de régularisation        | Dates des heures travaillées   | Heures réelles travaillées| Prime               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 31/8/2018             | 40                   | 3                     | 27/8/2018-31/8/2018  | 42                  | 3                  |        
| 31/8/2018             | 40                   | 3                     | 27/8/2018-31/8/2018  | 35                  | 0                   |

## <a name="employee-assigned-leave-plans"></a>Plans de congés affectés à l'employé

Dans les plans de congés de l'employé, la base de niveau et le type d'heures sont affichés pour les plans dans lesquels les heures travaillées sont définies comme type de régularisation. Pour les plans actifs, les heures réelles travaillées pour les périodes de régularisation à la date actuelle sont également affichées pour référence. 

## <a name="loading-data"></a>Chargement des données

Les heures réelles peuvent être importées à l'aide de l'entité Heures de congé et d'absence travaillées dans la gestion des données. Si vous utilisez des calendriers de temps de travail, l'importation valide que les heures normales travaillées ne dépassent pas les heures planifiées dans un jour défini par le calendrier. L'importation valide également que les heures travaillées pour un jour donné ne dépassent pas 24 heures. 

Les informations suivantes sont nécessaires pour importer les heures réelles à utiliser dans le processus de régularisation des congés :

+ Numéro personnel 
+ Date travaillée
+ Type
+ Heures

Un seul type peut être associé à une date.

| NUMÉRO PERSONNEL       | DATE TRAVAILLÉE           | TYPE                  | HEURES                |
| --------------------- | -------------------- | --------------------- | -------------------- |
| 000337                | 6/8/2018             | Normal               | 8                    |       
| 000337                | 7/8/2018             | Normal               | 8                    |
| 000337                | 7/8/2018             | Heures supplémentaires              | 3                    |
| 000337                | 8/8/2018             | Normal               | 8                    |
| 000337                | 7/8/2018             | Normal               | 8                    |
| 000337                | 9/8/2018             | Normal               | 8                    |
