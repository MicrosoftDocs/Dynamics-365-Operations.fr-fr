---
title: "Paramétrer les cours de formation"
description: "Les administrateurs des ressources humaines et les responsables peuvent utiliser les fonctionnalités du cours pour tenir à jour des informations sur la formation qui est offerte aux employés."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 095f41c35641834a1ed8ac2527c7014826921376
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-training-courses"></a>Paramétrer les cours de formation

[!include[banner](includes/banner.md)]


Les administrateurs des ressources humaines et les responsables peuvent utiliser les fonctionnalités du cours pour tenir à jour des informations sur la formation qui est offerte aux employés.

 <a name="set-up-prerequisites"></a>Paramétrage des conditions préalables
---------------------

Les informations suivantes sont requises et doivent être définies avant de créer des cours.
-   **Types de cours**

Les informations suivantes sont des informations facultatives que vous pouvez spécifier pour les cours. Si vous savez que vous allez entrer ces informations pour les cours, vous devez paramétrer ces informations avant de créer des enregistrements de cours.
-   **Groupes de classes**
-   **Groupes de cours**
-   **Lieux de cours**
-   **Classes**
-   **Instructeurs**

## <a name="course-types"></a>Types de cours
Ceux-ci servent à classer les cours en fonction de leur structure ou de leur contenu. Vous pouvez créer des types de cours dans la page **Types de cours**. Vous devez sélectionner un type de cours lorsque vous créez un enregistrement de cours.

## <a name="course-setup-type"></a>Type de paramétrage de cours
Le tableau suivant répertorie les trois types de paramétrage pour les cours. Les types de paramétrage déterminent la structure du cours.

<table>
<thead>
<tr class="header">
<th>Type de paramétrage</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Standard</strong></td>
<td>Sélectionnez ce type pour les cours qui n'ont pas un emploi du temps quotidien. Il s'agit du type de paramétrage par défaut lors de la création d'un cours.</td>
</tr>
<tr class="even">
<td><strong>Emploi du temps</strong></td>
<td>Sélectionnez ce type pour organiser les détails de chaque journée de cours qui se déroule sur plusieurs jours.</td>
</tr>
<tr class="odd">
<td><strong>Emploi du temps + session</strong></td>
<td>Sélectionnez ce type pour les cours plus complexes. Par exemple, vous pouvez diviser l'emploi du temps du cours en suivis et sessions.
<ul>
<li><strong>Suivi</strong> : Les suivis sont les domaines d'intérêt spécifiques d'un cours.</li>
<li><strong>Sessions</strong> : Les sessions permettent de diviser les suivis et aident à identifier les processus ou les techniques spécifiques adaptés au suivi concerné.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="course-tasks"></a>Tâches de cours
Pour chaque cours, vous pouvez effectuer les tâches suivantes.
-   Enregistrer les participants
-   Spécifier une date limite d'inscription
-   Définir le nombre minimal et le nombre maximal de participants
-   Affecter un lieu de cours et une classe
-   Recommander des hôtels aux participants
-   Créer une description du cours, que vous pouvez ensuite annoncer sur le libre-service pour employés

  >**Remarque** : vous pouvez supprimer un cours uniquement si personne n'y est inscrit. 
    
## <a name="course-statuses"></a>Statuts de cours
Le tableau suivant répertorie les statuts de cours possibles et les actions que vous pouvez effectuer lorsque le cours a un statut spécifique.

<table>
<thead>
<tr class="header">
<th>Statut</th>
<th>Actions</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Créé</strong></td>
<td><ul>
<li>Permet d'entrer et de modifier les informations sur le cours.</li>
<li>Permet d'attribuer le statut <strong>Ouvert</strong> au cours afin que les employés puissent s'inscrire.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Ouverte</strong></td>
<td><ul>
<li>Permet d'inscrire les participants au cours.</li>
<li>Permet de supprimer des participants d'un cours.</li>
<li>Permet de confirmer l'inscription des participants au cours.</li>
<li>Remplacez le statut de cours par<strong> Clôturé</strong> ou <strong>Annulé</strong>.</li>
<li>Prévoyez des questionnaires pour les participants dont le statut est <strong>Confirmé</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Clôturé(e)</strong></td>
<td>Vous pouvez rouvrir le cours.</td>
</tr>
<tr class="even">
<td><strong>Annulé</strong></td>
<td>Vous pouvez rouvrir le cours.</td>
</tr>
</tbody>
</table>

## <a name="course-participants"></a>Participants du cours
Les participants du cours sont des employés, des candidats ou des personnes à contacter qui prennent part à un cours de formation ou un événement. Vous pouvez inscrire des participants aux cours actifs. Le nombre minimal et maximal de participants que vous pouvez inscrire à un cours est défini dans l'organisateur **General** de la page **Cours**.

<a name="workflow"></a>Workflow
--------

Les employés qui s'inscrivent à un cours via la page **Libre service employé** peuvent faire suivre leur inscription via le workflow pour approbation.  Un workflow peut être affecté à un cours dans l'organisateur **Général** de la page **Cours**.






