---
title: Paramétrer les composants d’une tâche
description: Cet article décrit les éléments conceptuels pouvant être inclus dans une tâche et fournit des exemples d’utilisation de ces éléments dans votre organisation.
author: andreabichsel
ms.date: 06/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle, HcmPersonnelManagementWorkspace, HCMJobFamily
audience: Application User
ms.author: anbichse
ms.search.scope: Human Resources
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d4e24e64f3fece0807df8fbf4fb206c4588c9332
ms.sourcegitcommit: 43962e6fedaf55aab2f28f53bc38a69d2ff58403
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2021
ms.locfileid: "6333091"
---
# <a name="set-up-the-components-of-a-job"></a>Paramétrer les composants d’une tâche

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit les éléments conceptuels pouvant être inclus dans une tâche et fournit des exemples d’utilisation de ces éléments dans votre organisation. 

Avant de créer des tâches, vous devez paramétrer certaines informations de référence. Vous pouvez créer une tâche qui a uniquement un nom. Toutefois, en incluant des informations supplémentaires, telles qu’un titre, vous fournissez des valeurs par défaut pour les postes affectés à la tâche. En outre, certaines informations saisies peuvent être utilisées pour filtrer les régimes de rémunération pour des tâches spécifiques. Si vous souhaitez paramétrer l’admissibilité pour filtrer les régimes de rémunération pour une tâche spécifique, vous devez paramétrer les fonctions et les types de tâche avant de paramétrer les tâches. Lorsque ces valeurs par défaut sont disponibles, vous gagnez du temps lorsque vous ajoutez des postes à la tâche. 

Certains détails de la tâche, tels que le titre, le type et la fonction ont une date d’effet. Si vous créez une tâche aujourd’hui mais ajoutez ces détails ultérieurement, et consultez la tâche à partir de la date de création, ces détails ne s’affichent pas. Par conséquent, vous devez créer certaines de ces informations de référence avant que cela soit requis. Ainsi, vous pouvez ajouter les informations aux nouvelles tâches lors de leur création.

## <a name="job-titles"></a>Titres de tâche
Avant de créer des tâches, vous devez paramétrer des titres pour celles-ci. Les postes héritent des titres des tâches auxquelles ils sont associés. 

Tenez à jour les titres de tâche à l’aide de la page **Titres**, que vous pouvez ouvrir en utilisant la fonction de recherche. Sur la page **Titres**, entrez les titres que vous prévoyez d’utiliser pour vos tâches.

## <a name="job-types"></a>Types de tâches
Utilisez les types de tâches pour regrouper les tâches similaires en catégories. Les types de tâches sont facultatifs. si vous envisagez de les utiliser lors du paramétrage des règles d’admissibilité pour la gestion des rémunérations, vous devez les paramétrer avant de configurer des tâches. Certains exemples de types de tâches sont à temps plein et à temps partiel, ou payés à l’heure. Tenez à jour les types de tâches à l’aide de la page **Types de tâches**. Sur la page **Types de tâches**, entrez un nom et une brève description du type de tâche. Dans le champ **Statut de l’exemption**, sélectionnez l’une des options suivantes pour indiquer le statut d’exemption FLSA (Fair Labor Standards Act) des tâches de ce type :

-   **Exonéré** – Les tâches sont exonérées des heures supplémentaires effectuées dans le cadre du FLSA.
-   **Non dispensé** – Les tâches ne sont pas exonérées des heures supplémentaires effectuées dans le cadre du FLSA.
-   **Ne s’applique pas** – La couverture FLSA ne s’applique pas.

## <a name="job-family"></a>Famille de tâches
Une famille de tâches est un groupe de tâches qui impliquent un travail similaire et qui nécessitent une formation, des compétences, des connaissances et une expertise similaires. Une famille de tâches peut être liée à une tâche sur le raccourci **Classification des tâches** de la page **Tâches** et sur la tâche **Général** de la page **Tous les postes**. Les familles de tâches peuvent être larges ou spécifiques, selon votre entreprise et vos exigences en matière de rapports. Quelques exemples de grandes familles de tâches sont **Main-d’œuvre qualifiée** et **Main-d’œuvre non qualifiée**. Quelques exemples de familles de tâches spécifiques sont **Comptabilité**, **Fabrication** et **Ventes**.

Tenez à jour les familles de tâches à l’aide de la page **Famille de tâches**, que vous pouvez ouvrir en utilisant la fonction de recherche. Sur la page **Famille de tâches**, entrez un nom unique pour la famille et entrez une description détaillée que vous prévoyez d’utiliser pour vos tâches.

## <a name="job-functions"></a>Fonctions de la tâche
Les fonctions de tâche décrivent les catégories fonctionnelles de haut niveau et les responsabilités de haut niveau associées. Les fonctions de tâche sont facultatives. Vous pouvez utiliser les fonctions de tâche avec les types de tâche pour filtrer les régimes de rémunération pour des tâches spécifiques. Vous associez les fonctions de tâche et les types de tâche avec les régimes de rémunération en paramétrant des règles d’admissibilité dans la page **Règles d’admissibilité**. Vous pouvez ensuite lier un ensemble de niveaux à un régime de rémunération qui s’applique à la combinaison spécifique d’un type de tâche et d’une fonction de tâche que vous avez définie à l’aide d’une règle d’admissibilité. (Ces fonctions s’appliquent aux régimes de rémunération fixe et variable). Toutefois, si vous envisagez d’utiliser les fonctions de tâche lors du paramétrage des règles d’admissibilité pour la gestion des rémunérations, vous devez les paramétrer avant de configurer des tâches. Le tableau suivant donne des exemples de fonctions de tâche.

| Mission           | Fonction de tâche         |
|---------------|----------------------|
| Responsable des ventes | Responsable de niveau intermédiaire    |
| Comptable    | Professionnels        |

Tenez à jour les fonctions de tâche à l’aide de la page **Fonctions de tâche**. Sur la page **Fonctions de tâche**, entrez un code d’identification et une brève description de la fonction de tâche.

## <a name="compensation"></a>Rémunération
Pour affecter un régime de rémunération fixe à un employé qui occupe un poste pour une tâche, vous devez définir des niveaux de rémunération sur la tâche. Le niveau de rémunération est utilisé lorsque les montants minimum, médian et maximum sont définis dans une structure de rémunération (grille de rémunération). Lorsqu’un régime de rémunération fixe est créé, la structure de rémunération est sélectionnée. La structure de rémunération comprend également le niveau de rémunération. Lorsque vous sélectionnez un plan de rémunération fixe pour un employé, les niveaux de rémunération disponibles pour la sélection dépendent de la tâche auquel le poste de l’employé est associé. Pour plus d’informations sur la configuration des régimes de rémunération, voir [Régimes de rémunération](hr-compensation-overview.md).

## <a name="job-skills"></a>Compétences de tâche
Les compétences de tâche décrivent les compétences requises pour effectuer une tâche. Un niveau de compétence doit être associé à chaque compétence de tâche. Les niveaux de compétence sont définis par l’utilisateur. Ils indiquent le niveau de connaissance ou d’aptitude requis pour la compétence. Par exemple, les entreprises peuvent définir des niveaux numériques, tels que 1 à 5, où **1** indique un débutant et **5** indique un expert. Alternativement, les entreprises peuvent établir des niveaux qui sont étiquetés **Débutant**, **Intermédiaire** ou **Expert**. Une fois le niveau de compétence défini, l’importance de la compétence peut également être définie. Par exemple, si un comptable doit avoir une solide connaissance de Microsoft Excel, une compétence qui s’appelle **Connaissances Excel** peut être créée. Le niveau de compétence peut alors être défini sur **Intermédiaire** et l’importance peut être définie sur **Plus**.

Les compétences qui sont sur une tâche peuvent être utilisées dans la cartographie des compétences. La cartographie des compétences peut comparer l’ensemble des compétences requises pour un travail et les compétences associées à un employé. Elle peut ensuite déterminer un pourcentage de correspondance, en fonction des compétences qui se chevauchent. Pour en savoir plus sur la cartographie des compétences, consultez [Configurer les compétences](hr-develop-skills.md). 

## <a name="job-tasks"></a>Tâches
Les descriptifs de tâche décrivent les tâches de base devant être accomplies par un travailleur occupant un poste pour une tâche. Le même descriptif peut être ajouté à plusieurs tâches, et aux postes associés aux tâches qui utilisent ces descriptifs. Le tableau suivant donne des exemples de descriptifs de tâche.

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
<li><strong>Examen des performances</strong> – examen du rendement au travail de chaque commercial.</li>
<li><strong>Examen des absences</strong> – approbation ou rejet des demandes ou enregistrement d’absence de chaque commercial.</li>
</ul></td>
</tr>
<tr class="even">
<td>Comptable</td>
<td><strong>États financiers</strong> – présentation d’états financiers hebdomadaires au directeur financier.</td>
</tr>
</tbody>
</table>

Tenez à jour les tâches à l’aide de la page **Tâches**. Sur la page **Tâches**, entrez un nom et une brève description de la tâche. Dans le champ **Remarque**, vous pouvez éventuellement entrer des informations supplémentaires. Les notes peuvent être mises à jour pour une tâche spécifique sans modifier les notes que vous avez entrées ici.

## <a name="areas-of-responsibility"></a>Domaines de responsabilité
Utilisez les domaines de responsabilité pour indiquer les rôles, les processus et les produits dont un travailleur occupant un poste pour une tâche est responsable. Par exemple, pour une tâche intitulée « Comptable », un domaine de responsabilité peut être « Génération d’états financiers pour le produit A ». Tenez à jour les domaines de responsabilité à l’aide de la page **Domaines de responsabilité**, que vous pouvez rechercher à l’aide de la fonction de recherche. Sur la page **Domaines de responsabilité**, entrez un nom et une description pour la responsabilité. Dans le champ **Remarque**, vous pouvez éventuellement entrer des informations supplémentaires. Les notes peuvent être mises à jour pour une tâche spécifique sans modifier les notes que vous avez entrées ici.

## <a name="steps-for-creating-a-job"></a>Étapes pour créer une tâche
Reportez-vous à l’article [Définir les nouvelles tâches](./hr-personnel-define-jobs.md) pour connaître la procédure pas à pas pour créer une tâche. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
