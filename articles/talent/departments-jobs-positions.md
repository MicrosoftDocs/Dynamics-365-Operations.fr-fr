---
title: "Organiser le personnel à l'aide des départements, tâches et postes"
description: "Les départements, les tâches et les postes sont des éléments d'organisation qui sont tenus à jour au sein des Ressources humaines. Cette rubrique décrit des informations conceptuelles sur ces éléments."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmJob, HcmPosition, OMOperatingUnit
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent, Retail
ms.custom: 87933
ms.assetid: eb5dcacb-a5fe-451d-b30a-7ef14da65d81
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 5799db0354e0e2bb766284ef2d87e8da9a956958
ms.contentlocale: fr-fr
ms.lasthandoff: 02/07/2018

---

# <a name="organize-your-workforce-using-departments-jobs-and-positions"></a>Organiser le personnel à l'aide des départements, tâches et postes

[!INCLUDE [banner](includes/banner.md)]

[!INCLUDE [retail name](includes/retail-name.md)]

Les départements, les tâches et les postes sont des éléments d'organisation qui sont tenus à jour au sein des Ressources humaines. Cette rubrique décrit des informations conceptuelles sur ces éléments. 

L'exemple suivant est utilisé pour illustrer les concepts décrits dans cette rubrique.

|**Département**|**Poste**|**Tâche**|
|---|---|---|
|**Ventes**|Responsable des ventes (est)|Responsable des ventes|
|**Ventes**|Responsable des ventes (ouest)|Responsable des ventes|
|**Ventes**|Responsable des ventes (centre)|Responsable des ventes|
|**Comptabilité**|Chef comptable|Responsable comptabilité|
|**Comptabilité**|Comptabilité-A|Comptable|
|**Ressources humaines**|Directeur RH (est)|Directeur RH|
|**Ressources humaines**|Directeur RH (ouest)|Directeur RH|
|**Ressources humaines**|Directeur RH (centre)|Directeur RH|


 <a name="departments"></a>Départements
------------

Un département est une unité opérationnelle représentant une catégorie ou une zone fonctionnelle d'une organisation, et responsable d'une région spécifique de l'organisation ; par exemple les ventes ou la comptabilité. Un département est chargé de fournir des états sur les zones fonctionnelles et peut être responsable des résultats. En outre, un département peut inclure un groupe de centres de coût. Les ventes, la comptabilité et les ressources humaines sont des exemples de départements d'une organisation.

## <a name="jobs-and-positions"></a>Les tâches et les postes
Une tâche est un ensemble de tâches et de responsabilités attribuées à la personne affectée à la tâche. Un poste est une instance individuelle de tâche. Les domaines de responsabilité, les tâches, les fonctions de tâche, les qualifications, les informations de formation et les certificats requis pour une tâche sont également nécessaires pour les postes associés à la tâche.
### <a name="job-tasks"></a>Tâches

Vous pouvez créer des descriptifs de tâches qui décrivent les tâches de base devant être accomplies par un travailleur occupant un poste pour cette tâche. Le même descriptif peut être ajouté à plusieurs tâches, et les postes associés à ces tâches hériteront de ces descriptifs. Des exemples de tâches sont répertoriés dans le tableau suivant.

<table>
<thead>
<tr class="header">
<th>Mission</th>
<th>Tâche</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Responsable des ventes</td>
<td><ul>
<li><span class="input">Examen des performances</span> – examen du rendement au travail de chaque commercial.</li>
<li><span class="input">Examen des absences</span> – approbation ou rejet des demandes ou enregistrement d'absence de chaque commercial.</li>
</ul></td>
</tr>
<tr class="even">
<td>Comptable</td>
<td><span class="input">États financiers</span> – présentation d'états financiers hebdomadaires au directeur financier.</td>
</tr>
</tbody>
</table>

### <a name="job-functions"></a>Fonctions

Les fonctions de tâche sont comme des descriptifs de tâches. Une fonction de tâche décrit une ou plusieurs tâches, devoirs ou responsabilités affectés à une tâche. Les fonctions de tâche peuvent être affectées aux tâches et servir à paramétrer et mettre en œuvre des règles d'admissibilité pour les régimes de rémunération. Des exemples de fonctions de tâche sont répertoriés dans le tableau suivant.

| Tâche           | Fonction de tâche                                                |
|---------------|-------------------------------------------------------------|
| Responsable des ventes | Gestion de personnes – gérer les personnes placés sous votre autorité.               |
| Comptable    | Examen des états financiers – tenue à jour des données financières pour un ensemble de comptes. |

### <a name="job-types"></a>Types de tâche

Utilisez les types de tâches pour classer les tâches similaires en catégories. Les types de tâches, tout comme les fonctions de tâche peuvent être affectées aux tâches et servir à paramétrer et mettre en œuvre des règles d'admissibilité pour les régimes de rémunération. La liste suivante fournit quelques exemples de types de tâches :
-   Temps plein
-   Temps partiel
-   Salaire
-   Salaire horaire

### <a name="areas-of-responsibility"></a>Domaines de responsabilité

Utilisez les domaines de responsabilité pour indiquer les rôles, les processus et les produits dont un travailleur occupant un poste pour cette tâche est responsable. Un exemple de domaine de responsabilité pour une tâche intitulée « Comptable » peut être « Génération d'états financiers pour le produit A ».

<a name="positions"></a>Postes
----------

Les postes sont un élément important du niveau inférieur d'une hiérarchie d'organisation. Un poste est une instance individuelle de tâche. Par exemple, le poste « Responsable des ventes (est) » est l'un des postes associé à la tâche « Responsable des ventes ». Les postes existent dans un département et sont affectées aux travailleurs.
### <a name="position-creation-and-maintenance"></a>Création et mise à jour de poste

-   Vous pouvez afficher un historique des modifications relatives aux postes du système dans une page de liste facile d'accès.
-   Vous pouvez créer des codes motif que les utilisateurs peuvent sélectionner lorsqu'ils créent ou modifient des postes.
-   Vous pouvez créer des types d'action d'un membre du personnel et affecter une souche de numéros aux actions d'un membre du personnel.
-   Vous pouvez paramétrer le workflow de telle sorte que les ajouts et modifications de poste nécessitent une approbation.

### <a name="position-duration"></a>Durée du poste

Chaque poste a une période durant laquelle le poste est effectif. Cette période est également appelée durée. Par exemple, les postes d'été peuvent avoir une durée qui s'étend du 1er mai 2015 au 31 août 2015.

### <a name="worker-assignments"></a>Affectations du collaborateur

Lorsque vous affectez un travailleur à un poste, vous occupez ce poste. Vous pouvez affecter des travailleurs à plusieurs postes, mais un seul travailleur à la fois peut être affecté au poste.

### <a name="reporting-relationships"></a>Relations de génération d'états

Les postes sont des éléments importants du niveau inférieur d'une hiérarchie d'organisation. Dans l'écran Poste, vous pouvez spécifier le poste dont un poste dépend. Lorsque vous affectez un travailleur à un poste qui dépend d'un autre poste, vous créez une relation hiérarchique entre les travailleurs affectés aux deux postes. Par exemple, le poste « Comptable A » est sous l'autorité de « Chef comptable ». Pierre Lopez est affecté au poste « Chef comptable » et Sanjay Patel est affecté au poste « Comptable A ». Cela signifie que Sanjay Patel est sous l'autorité de Pierre Lopez. 

Si votre organisation utilise une hiérarchie matricielle ou une autre hiérarchie personnalisée, vous pouvez paramétrer des types de hiérarchies des postes et ensuite ajouter des relations hiérarchiques aux postes pour chaque type de hiérarchie défini. Par exemple, Lori Penor est directeur général chez Adventure Works et est affecté au poste de « Directeur général ». Lori gère le développement d'un produit utilisé pour nettoyer les widgets. Lori a besoin d'un comptable pour l'aider à gérer l'aspect financier du développement du produit. Par conséquent, elle a recruté Sanjay Patel comme comptable. Sanjay est sous l'autorité directe de Pierre Lopez, mais il travaille également avec Lori Penor sur l'aspect financier du développement du nettoyeur de widget. 

Dans l'exemple précédent, vous effectueriez les tâches suivantes pour paramétrer la relation de travail entre Sanjay Patel et Lori Penor :
1.  Création d'un type de hiérarchie de poste personnalisé appelé « Widget » pour créer une hiérarchie qui inclut les postes responsables du travail sur le produit de nettoyage de widget.
2.  Affectation du poste de Directeur général comme poste dont dépend le Comptable A dans la hiérarchie de Widget.

Utilisez la hiérarchie des postes pour afficher la structure hiérarchique des postes. Si plusieurs hiérarchies des postes, vous pouvez afficher la hiérarchie de chaque type de hiérarchie de la hiérarchie des postes. En outre, vous pouvez rechercher un poste à l'aide de l'ID du poste ou du nom du travailleur affecté au poste. La hiérarchie des postes est une hiérarchie d'organisation.

## <a name="date-effective-records"></a>Date des enregistrements effectifs
Pour certains enregistrements, vous pouvez spécifier des modifications futures apportées à l'enregistrement. Les informations suivantes ont une date d'effet.

<table>
<thead>
<tr class="header">
<th>Enregistrements</th>
<th>Informations à date d'effet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Tâches</td>
<td><ul>
<li>Informations détaillées relatives à la tâche</li>
<li>Informations de classification des tâches</li>
<li>Informations de rémunération</li>
</ul></td>
</tr>
<tr class="even">
<td>Postes</td>
<td><ul>
<li>Informations détaillées relatives au poste</li>
<li>Affectations du travailleur</li>
<li>Durées du poste</li>
<li>Hiérarchies des postes</li>
</ul></td>
</tr>
</tbody>
</table>

Vous pouvez modifier les informations mentionnées dans le tableau précédent pour un poste ou une tâche et spécifier une date à laquelle les modifications apportées au poste ou à la tâche doivent prendre effet. Par exemple, un poste peut uniquement être affecté à un travailleur, mais Sanjay Patel, affecté au poste de Comptable A, partira dans deux semaines. Olivier Renaud remplacera Sanjay Patel à son départ. Même si Sanjay est affecté au poste, vous pouvez y affecter Olivier Renaud afin que l'affectation soit effective seulement après le dernier jour de Sanjay.






