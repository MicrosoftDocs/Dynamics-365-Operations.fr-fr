---
title: "Paramétrage des composants d&quot;une tâche"
description: "Cette rubrique décrit les éléments conceptuels qu&quot;une tâche peut comprendre et fournit des exemples de la manière dont vous pouvez utiliser ces éléments dans votre organisation."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: d96b1f01a5cb4370436888deae8fd4835a0dbb80
ms.openlocfilehash: b8143db5b133337603a7f2f46028d91bb81cd947
ms.lasthandoff: 03/31/2017


---

# <a name="setting-up-the-components-of-a-job"></a>Paramétrage des composants d'une tâche

Cette rubrique décrit les éléments conceptuels qu'une tâche peut comprendre et fournit des exemples de la manière dont vous pouvez utiliser ces éléments dans votre organisation. 

Avant de créer des tâches, vous devez paramétrer certaines informations de référence. Vous pouvez créer une tâche avec uniquement un nom. Toutefois, en incluant des informations supplémentaires, telles qu'une fonction, vous livrez des valeurs par défaut des postes affectés à la tâche. En outre, certaines informations que vous entrez peut être utilisée pour filtrer les régimes de rémunération pour des tâches spécifiques. Si vous souhaitez paramétrer l'admissibilité que vous pouvez utiliser pour filtrer les régimes de rémunération à une tâche spécifique, vous devez paramétrer les fonctions et les types de tâches avant de configurer des tâches. En avec ces valeurs par défaut disponibles, vous épargnerez du temps lorsque vous ajoutez des postes de la tâche. 

Certains détails des tâches, tels que la fonction, type, et fonction, sont dates effectives. Si vous créez une tâche aujourd'hui mais n'ajoutez pas ces détails jusqu'à une date ultérieure, et vous examinez la tâche à partir de la date de création, ces détails ne figurent pas. Par conséquent, vous devez créer certaines de ces informations de référence avant d'avoir besoin de celui-ci. De cette manière, vous pouvez ajouter des informations à des tâches lors de leur création.

## <a name="job-titles"></a>Fonctions
Avant de créer des tâches, vous devez paramétrer des titres pour celles-ci. Les postes héritent des titres des tâches auxquelles ils sont associés. 

Mise à jour des fonctions à l'aide de ** des titres ** la page, que vous pouvez ouvrir à l'aide de la fonction de recherche. Sous ** des titres ** la page, entrez les titres que vous prévoyez d'utiliser pour vos tâches.

## <a name="job-types"></a>Types de missions
Vous utilisez les types de tâches pour regrouper des tâches similaires en catégories. Les types de tâches ne sont pas nécessaires. si vous envisagez de les utiliser lors du paramétrage des règles d'admissibilité pour la gestion des rémunérations, vous devez les paramétrer avant de configurer des tâches. Certains exemples de types de tâches sont à temps plein et à temps partiel, ou rémunération et salaire horaire. Vous gérez des types de tâches à l'aide ** les types de tâches ** de la page. Sous ** les types de tâches ** la page, entrez un nom et une brève description du type de tâche. Dans ** statut de l'exemption ** le champ, sélectionnez l'une des options suivantes pour indiquer le statut de l'exemption de (FLSA) destinée FLSA juste de standard de travail des tâches avec ce type de tâche :

-   ** ** – Les tâches sans sont exonérées des heures supplémentaires le FLSA.
-   ** ** – Les tâches non-exemptes ne sont pas exonérées des heures supplémentaires le FLSA.
-   ** La applique pas ** – couverture de FLSA ne s'applique pas.

## <a name="job-functions"></a>Fonctions
Les jonctions de tâche décrivent les catégories fonctionnelles de haut niveau et associent des fonctions de niveau supérieur. Les fonctions ne sont pas requises. Vous pouvez utiliser les fonctions, avec les types de tâches, pour filtrer les régimes de rémunération pour des tâches spécifiques. Vous associez les fonctions et les types de tâches avec des régimes de rémunération en paramétrant des règles d'admissibilité dans ** des règles d'admissibilité ** la page. Vous pouvez ensuite joindre un ensemble de niveaux au régime de rémunération qui s'applique à la combinaison spécifique d'un type de tâche et une fonction que vous avez définis à l'aide d'une règle d'admissibilité. (Ces fonctions s'appliquent aux régimes de rémunération fixe et aux régimes de rémunération variable.) Toutefois, si vous comptez utiliser des fonctions de tâche lorsque vous paramétrez des règles d'admissibilité pour la gestion des rémunérations, vous devez paramétrer des fonctions de tâche avant de configurer des tâches. Le tableau suivant présente certains exemples les fonctions.

| Mission           | Fonction de tâche         |
|---------------|----------------------|
| Responsable des ventes | Responsable à mi-niveau    |
| Comptable    | Professionnels        |

Vous gérez des fonctions de tâche à l'aide ** des fonctions de tâche ** de la page. Sous ** des fonctions de tâche ** la page, entrez un code d'identification et une brève description de la fonction.

## <a name="job-tasks"></a>Tâches
Les tâches décrivent les tâches de base qu'un travailleur occupant un poste pour une tâche doit exécuter. La même tâche peut être ajoutée à plusieurs tâches, et aux postes pour les tâches qui utilisent ces tâches. Le tableau suivant présente certains exemples des tâches.

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
<li><strong>Perforation-révision</strong> – Permet d'examiner les performances de la tâche de chaque commercial.</li>
<li><strong>ABS-révision</strong> – Permet d'approuver ou de rejeter les demandes d'absence et les enregistrements de chaque commercial.</li>
</ul></td>
</tr>
<tr class="even">
<td>Comptable</td>
<td><strong>FIN-état</strong> – États financiers hebdomadaires actuels à directeur financier.</td>
</tr>
</tbody>
</table>

Vous gérez des tâches à l'aide ** des tâches ** de la page. Sous ** des tâches ** la page, entrez un nom et une description de la tâche. Dans ** note ** le champ, vous pouvez entrer des informations supplémentaires. Les notes peuvent être mises à jour pour une tâche spécifique sans modifier les notes que vous avez entrées ici.

## <a name="areas-of-responsibility"></a>Domaines de responsabilité
Vous utilisez des domaines de responsabilité pour indiquer les rôles, les processus, les produits et qu'un travailleur occupant un poste pour une tâche est responsable. Par exemple, pour une tâche qui est appelée « comptable, » un domaine de responsabilité peuvent être des « états financiers pour les produits A ». Vous gérez des domaines de responsabilité à l'aide ** des domaines de responsabilité ** de la page, que vous pouvez trouver à l'aide de la fonction de recherche. Sous ** des domaines de responsabilité ** la page, entrez le nom et la description de la responsabilité. Dans ** note ** le champ, vous pouvez entrer des informations supplémentaires. Les notes peuvent être mises à jour pour une tâche spécifique sans modifier les notes que vous avez entrées ici.


