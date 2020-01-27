---
title: Régimes de rémunération
description: Les gestionnaires de rémunération et avantages peuvent utiliser la gestion des rémunérations pour tenir à jour et traiter les régimes de rémunération fixes et variables des employés de l'organisation.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCompensationLevel, HRCCompGrid, HRMCompFixedAction, HRMCompFixedBudget, HRMCompFixedPlanTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: 8e7e41756c3be73937ef62523ff6bf41536405b0
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898848"
---
# <a name="compensation-plans"></a>Régimes de rémunération

Les gestionnaires de rémunération et avantages peuvent utiliser la gestion des rémunérations pour tenir à jour et traiter les régimes de rémunération fixes et variables des employés de l'organisation.

### <a name="introduction"></a>Introduction

La gestion des rémunérations est utilisée pour contrôler la rémunération de base et les primes. Le salaire de base fixe et les augmentations pour mérite d'un employé sont contrôlés via les régimes de rémunération fixe. Le paiement des primes (primes liées aux résultats, options d'achat d'actions et octrois d'actions), ainsi que les primes exceptionnelles, est contrôlé via les régimes de rémunération variable. 

Vous pouvez associer les employés à un ou plusieurs de ces régimes. Pour prétendre à l'enregistrement dans un régime de rémunération, l'employé doit remplir les conditions suivantes :
-   L'employé doit avoir une affectation de poste active.
-   L'employé doit satisfaire aux exigences définies dans les règles d'admissibilité à un régime de rémunération.

## <a name="compensation-setup"></a>Paramétrage de la rémunération
Le tableau suivant répertorie les composants du processus de rémunération pouvant être intégrés au paramétrage des régimes de rémunération de votre société.

<table>
<thead>
<tr class="header">
<th>Composant</th>
<th>Plus d'informations...</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Actions de rémunération fixe</td>
<td>Les actions de rémunération fixe ont deux objectifs :
<ul>
<li>Les actions peuvent spécifier le type d'informations qui doivent être enregistrées lorsque la rémunération d'un employé change. Par exemple, vous pouvez exiger que le motif d'une modification, telle qu'une promotion ou une rétrogradation, soit enregistré.</li>
<li>Les actions permettent de garantir qu'un calcul est appliqué lorsque les régimes de rémunération fixe sont traités.  Par exemple, les actions de type Capitaux propres compareront le salaire des employés au point de référence minimal par rapport au niveau de l'employé et garantiront que l'employé est rémunéré au moins au niveau minimal.</li>
</ul></td>
</tr>
<tr class="even">
<td>Niveaux</td>
<td>Les niveaux sont associés aux tâches et aux postes liés à la référence d'une tâche. Vous pouvez créer des niveaux distincts pour les trois types de régimes de rémunération : Niveau, Structure et Échelon.</td>
</tr>
<tr class="odd">
<td>Matrice d'utilisation de tranche</td>
<td>Une matrice de plage d'utilisation vous permet de faire passer les employés au point de contrôle pour leurs tâches. Vous pouvez également vous servir de la plage d'utilisation pour contrôler l'équité des niveaux de rémunération au sein de la société sans tenir compte des performances individuelles de l'employé ou des performances globales de la société. Par exemple, les employés qui ont les salaires les plus bas de leur plage bénéficient d'augmentations supérieures en termes de pourcentage que les employés de la même plage qui sont payés davantage. De cette manière, il est possible d'atténuer les différences de manière systématique. La plage d'utilisation est calculée comme suit : (taux de salaire fixe - plage minimale) ÷ (plage maximale - plage minimale).</td>
</tr>
<tr class="even">
<td>Paramétrages de point de référence</td>
<td>Un paramétrage de points de référence inclut un ensemble de points de référence représentant des plages dans une matrice. Chaque plage peut être associée à un taux de salaire. Par exemple, les plans de niveau ont souvent des points de référence Minimal, Point moyen et Maximal.</td>
</tr>
<tr class="odd">
<td>Matrice de rémunération</td>
<td>Une matrice de rémunération est l'ensemble de points de référence et de niveaux utilisés pour créer une structure de rémunération.</td>
</tr>
<tr class="even">
<td>Structure des rémunérations</td>
<td>Une structure de rémunération est une matrice de rémunération dotée de taux de salaire associés aux points de référence pour chaque niveau.</td>
</tr>
<tr class="odd">
<td>Règles d'admissibilité</td>
<td>Des règles d'admissibilité permettent d'identifier les employés rattachés à certains types de tâches, tâches, fonctions de tâche, départements, syndicats ou régions de rémunération qui sont concernés par les régimes de rémunération spécifiques. Vous devez créer des règles d'admissibilité pour les régimes de rémunération variables et fixes afin d'inscrire les employés dans le régime. Une fois les règles d'admissibilité d'un régime de rémunération paramétrées, vous pouvez définir les niveaux devant s'appliquer aux tâches qu'il englobe.</td>
</tr>
<tr class="even">
<td>Fréquences de paiement</td>
<td>Les fréquences de paiement permettent de définir la période pour laquelle la rémunération est spécifiée.  Par exemple, les fréquences de paiement vous aident à comprendre si le montant de rémunération est spécifié comme un salaire annuel ou comme un taux de salaire horaire. Les fréquences de paiement permettent également de paramétrer des facteurs de conversion pour convertir les montants de rémunération mensuelle, hebdomadaire, bi-hebdomadaire et horaire en paiement annuel.</td>
</tr>
<tr class="odd">
<td>Régions de rémunération</td>
<td>Les régions de rémunération permettent de spécifier la rémunération de l'employé en fonction de l'emplacement du lieu de travail.</td>
</tr>
<tr class="even">
<td>Point de contrôle</td>
<td>Le point de contrôle définit ce que vous considérez comme le taux de salaire idéal pour tous les employés appartenant à un niveau de rémunération. Pour les structures de régime de niveau, les points de contrôle correspondent généralement au centre de la plage. Les structures utilisent rarement les points de contrôle. Vous pouvez spécifier le point de contrôle pour un régime de rémunération fixe dans l'écran Régimes de rémunération fixe.</td>
</tr>
<tr class="odd">
<td>Fonctions</td>
<td>Les fonctions de tâche permettent de classer et de filtrer les régimes de rémunération par rapport à des tâches spécifiques.</td>
</tr>
<tr class="even">
<td>Types de missions</td>
<td>Les types de tâche permettent de classer et de filtrer les régimes de rémunération par rapport à des tâches spécifiques.</td>
</tr>
<tr class="odd">
<td>Types de rémunérations variables</td>
<td>Les types de rémunérations variables, tels que les primes sous forme d'actions ou les primes en espèces, sont paramétrés dans les régimes de rémunération variable.</td>
</tr>
<tr class="even">
<td>Grilles de rémunération</td>
<td>Les grilles de rémunération contiennent la structure de rémunération.  Elles peuvent être utilisées par un ou plusieurs régimes de rémunération.</td>
</tr>
<tr class="odd">
<td>Régime basé sur les résultats</td>
<td>Les régimes basés sur les résultats permettent d'associer les performances à une matrice de répartition, de manière à utiliser le régime dans une stratégie de rémunération en fonction des résultats.</td>
</tr>
<tr class="even">
<td>Classements de résultats</td>
<td>Les classements de résultats sont utilisés dans les régimes basés sur les résultats afin de déterminer le montant d'une prime au mérite ou d'une prime liée aux résultats.</td>
</tr>
</tbody>
</table>

## <a name="process-events"></a>Événements de processus
Un événement des traitements de données calcule les informations de rémunération d'une période spécifique pour tous les employés inscrits à un ou plusieurs régimes de rémunération fixe ou variable. Vous pouvez exécuter un événement des traitements de données à plusieurs reprises pour tester ou mettre à jour les résultats de la rémunération.

<a name="compensation-events"></a>Événements de rémunération
-------------------

Chaque fois qu'un événement de processus est exécuté, un événement de rémunération est créé.  Les événements de rémunération contiennent les résultats du processus de rémunération pour chaque employé inclus dans cet événement de processus.  Lorsque les calculs sont corrects, vous pouvez charger l'événement de rémunération pour mettre à jour les enregistrements de rémunération pour les employés affectés par l'événement de processus.

## <a name="recommendations"></a>Recommandations
Après avoir exécuté un événement des traitements de données, vous pouvez recommander des ajustements au montant de la prime et à l'augmentation pour mérite d'un employé, sur la base des résultats du calcul de l'événement des traitements de données. Pour être en mesure d'émettre des recommandations pour les employés, vous devez autoriser les recommandations lorsque vous paramétrez les régimes de rémunération ou l'événement des traitements de données.



