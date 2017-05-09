---
title: Aligner les qualifications du personnel sur les besoins de l&quot;entreprise
description: "Vous pouvez suivre les qualifications que les travailleurs, les candidats ou les personnes à contacter ont ou doivent avoir pour assumer efficacement leurs rôles. Vous pouvez également spécifier les qualifications requises pour une tâche spécifique."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 720a1f272948eb310dc3cd02588aeec40b556d20
ms.openlocfilehash: 31dda85ff2e4a4e5380401b031b2dd74acff394b
ms.lasthandoff: 03/31/2017


---

# <a name="align-workforce-skills-with-business-needs"></a>Aligner les qualifications du personnel sur les besoins de l'entreprise

Vous pouvez suivre les qualifications que les travailleurs, les candidats ou les personnes à contacter ont ou doivent avoir pour assumer efficacement leurs rôles. Vous pouvez également spécifier les qualifications requises pour une tâche spécifique.

Les exemples de qualifications que vous pouvez suivre sont les suivants :
-   Supervision – Capacité de superviser le travail des autres.
-   Leadership – Capacité de diriger des employés et des secteurs d'entreprise.
-   Planification – Capacité de réfléchir à l'avenir, de formuler des visions et de les mener à bien.
-   HTML – Capacité d'écrire du code HTML.

Avant d'affecter une qualification à une personne ou une tâche, de créer une recherche de mise en correspondance des qualifications ou de créer un profil de qualification, vous devez entrer des informations sur les qualifications dans la page **Qualifications**. Pour chaque qualification, vous pouvez sélectionner un type de qualification et un modèle de classement.

## <a name="rating-models"></a>Modèles de classement
Le fait de classer les modèles permet d'évaluer le niveau de qualification réel d'une personne, le niveau qu'ils doivent atteindre, ou le niveau de la qualification nécessaire pour une tâche. Vous pouvez entrer jusqu'à 10 niveaux pour un modèle de classement.  Un facteur est affecté à chaque niveau dans un modèle de classement.  La valeur de facteur sera utilisée pour normaliser les scores de compétences qui utilisent différents modèles de classement.  Le facteur doit être un numéro compris entre 0 et 9 et chaque niveau doit avoir un facteur unique.  Les niveaux avec des valeurs de facteur plus élevées ont plus de poids dans un modèle de classement.

## <a name="specify-job-skills"></a>Spécification des qualifications requises pour une tâche
Lorsque vous entrez des informations sur une tâche, vous pouvez spécifier les qualifications qu'une personne doit avoir pour exécuter le travail requis par la tâche.  En outre, vous pouvez spécifier le niveau désiré pour chaque qualification, ainsi que le niveau d'importance de la qualification. Différents postes peuvent nécessiter différents niveaux d'importance d'une même qualification.

## <a name="enter-skills-for-workers-applicants-or-contacts"></a>Saisie de qualifications pour les travailleurs, les candidats, ou les contacts
Vous pouvez entrer des qualifications cibles ou des qualifications réelles pour les travailleurs, les candidats, ou les contacts. Une qualification cible est une qualification que la personne envisage d'acquérir. Une qualification réelle est une qualification qu'une personne possède actuellement.

## <a name="skill-mapping-and-skill-mapping-profiles"></a> Mise en correspondance des qualifications et profils de mise en correspondance des qualifications
Vous pouvez créer une recherche de mise en correspondance des qualifications pour rechercher un collaborateur, un candidat, ou une personne à contacter qui est qualifiée pour effectuer un type de tâche spécifique de tâche. Le recherche de mise en correspondance des qualifications étudie les compétences, la formation, les certificats, les postes de confiance et l'expérience sur le projet et renvoie des résultats qui correspondent aux critères entrés.  Par exemple, il peut être utile de savoir quels collaborateurs de votre organisation ont un diplôme de comptabilité.

Les profils de mise en correspondance des qualifications vous permettent de rechercher les employés actuels ou les candidats dont les qualifications correspondent directement aux besoins de votre entreprise.  Par exemple, vous pouvez créer un profil de mise en correspondance des qualifications pour un poste vacant de votre organisation. En créant un profil pour une tâche spécifique et en copiant les qualifications, les formations et les certificats de cette tâche dans le profil, vous pouvez rechercher rapidement des travailleurs, des candidats et des personnes à contacter qui correspondent à un ou plusieurs des critères entrés dans le profil et afficher la liste des candidats dont les qualifications correspondent le mieux aux qualifications requises pour la tâche.

<table>
<thead>
<tr class="header">
<th><strong>Remarque </strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Seuls les travailleurs, les candidats, les personnes à contacter sélectionnés pour être inclus dans les recherches de mise en correspondance des qualifications peuvent être affichés dans la liste des résultats de la mise en correspondance des qualifications ou être inclus dans un profil de qualification. Pour inclure un travailleur, un candidat ou une personne à contacter dans les recherches de mise en correspondance des qualifications, définissez l'option <strong>Inclure dans la mise en correspondance des qualifications</strong> sur Oui dans les pages suivantes :
<ul>
<li>Collaborateur</li>
<li>Employé</li>
<li>Candidat</li>
<li>contacts ;</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a>Analyse des écarts de qualification et analyse des profils de qualification
Vous pouvez créer une analyse des profils de qualification pour afficher la liste des compétences d'un travailleur, d'un candidat ou d'une personne à contacter à une date spécifique. Vous pouvez créer une analyse des écarts de qualification pour comparer les qualifications d'une personne aux qualifications requises pour une tâche donnée.  



<a name="see-also"></a>Voir également :
--------

[Ressources humaines](index.md)


