---
title: Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (6 décembre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 12/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-12-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6fae56d2feeec8e5c26fc86bdf89b8ab4c282144
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "304438"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-december-6-2018"></a>Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (6 décembre 2018)

[!include [banner](includes/banner.md)]

**Version 8.1.2071**

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.


## <a name="platform-update-22"></a>Update 22 de la plateforme

### <a name="export-up-to-1-million-rows-to-excel"></a>Exportation jusqu'à 1 millions de lignes vers Excel

La fonctionnalité Exporter vers Excel peut désormais être configurée pour autoriser les utilisateurs à exporter jusqu'à 1 millions de lignes d'une grille dans Talent, une augmentation substantielle de la limite précédente de 10 000 lignes. 

### <a name="restyled-personalization-toolbar"></a>Barre d'outils de personnalisation remaniée

La barre d'outils de personnalisation a été remaniée dans Platform update 22 pour aider les utilisateurs à personnaliser plus facilement leurs propres expériences dans Talent. Les modifications suivantes ont été apportées : 

-  Le nom de chaque outil de personnalisation est désormais affiché avec une icône, ce qui aide les utilisateurs rapidement à identifier l'outil qu'ils souhaitent utiliser.
-  La description de l'utilisation de l'outil actuel est également affichée, ce qui aide les utilisateurs à comprendre comment effectuer les personnalisations nécessaires.  
-  La barre de personnalisation complète peut être déplacée entre l'écran en faisant glisser-déplacer dans une zone spécifique à l'extrême gauche de la barre d'outils. Cela permet aux utilisateurs de personnaliser les éléments précédemment masqués par la barre d'outils.   

### <a name="optimized-is-one-of-filtering-experience"></a>Optimisation de l'expérience de filtrage « est l'un de »

L'opérateur de filtrage « est l'un de » est disponible pour la plupart des champs à l'aide du volet de filtres et des listes déroulantes d'en-tête de la grille. Cet opérateur permet à l'utilisateur de filtrer un champ selon plusieurs valeurs. Une nouvelle expérience améliorée de l'opérateur « est l'un de » est disponible dans Platform update 22. Pour en savoir plus, voir [Optimisation de l'expérience de filtrage « est l'un de »](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/improved-isoneof-filtering).

### <a name="paste-lists-from-excel-into-filter-fields-with-the-is-one-of-operator"></a>Collage des listes d'Excel dans des champs de filtre avec l'opérateur « est l'un de »

Pour certaines tâches, les utilisateurs peuvent avoir une liste de valeurs dans Excel qu'ils voudraient utiliser pour filtrer des données dans Talent. Par exemple, un utilisateur des Ressources humaines peut avoir identifié un ensemble d'employés dans un état qui ont besoin de recherche supplémentaire dans le système, et il serait idéal que l'utilisateur puisse copier la liste directement à partir d'Excel dans un champ de filtre dans Talent.

Avec Platform update 22, l'opérateur « est l'un de » du volet de filtre et le filtrage de la colonne de la grille identifie désormais les listes copiées depuis Excel afin qu'elles puissent être collées directement dans un champ de filtre. Cela inclut un ensemble de valeurs copiées de différentes lignes et colonnes dans Excel. Pour en savoir plus sur cette fonctionnalité, voir [Collage des listes d'Excel dans des champs de filtre avec l'opérateur « est l'un de »](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/paste-filter-lists-from-excel).

## <a name="in-preview"></a>En mode aperçu

### <a name="configure-uk-payroll-integration-between-talent-and-dayforce"></a>Configuration de l'intégration de la paie R.-U. entre Talent et Dayforce

L'intégration entre Microsoft Dynamics 365 for Talent et Ceridian Dayforce est disponible dans l'aperçu pour le R.-U. Voir la rubrique suivante pour plus d'informations, [Configurer l'intégration de la paie entre Talent et Dayforce](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/configure-payroll-integration), voir.

## <a name="coming-soon"></a>Prochainement

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a>Congés et absences : Futurs soldes et prévisions de congés

Les modifications apportées pour autoriser les employés à prévoir des congés et à faire de futures demandes de congés sans répercussion sur leur solde actuel de congés modifient également la façon dont les soldes de congés sont affichés. 

Le solde disponible affiché actuellement correspond à la quantité de congés disponible pour les demandes, y compris les régularisations à ce jour et toutes les demandes de congés approuvées à la fin du temps. 

Lorsque la capacité à prévoir sera activée, le solde affiché deviendra le solde actuel de congés, y compris les régularisations à ce jour et les demandes à ce jour. Les employés et les responsables verront ces soldes mis à jour dans le libre-service employé et responsable sur la fiche **Congés** et la fenêtre **Soldes des congés**. Les responsables des RH auront accès à ces soldes mis à jour dans l'espace de travail **Personnes** et dans la fenêtre **Plans de congés affectés** de l'employé.

## <a name="other-changes"></a>Autres modifications 

### <a name="termination-code-is-not-populated-to-the-worker-position-assignment-record"></a>Le code de fin de contrat n'est pas renseigné dans l'enregistrement d'affectation de poste du collaborateur

Une modification a été mise en œuvre qui remplit le code motif dans l'enregistrement d'affectation de poste lors du processus de fin de contrat.

### <a name="validation-for-personnel-number-being-in-use-needs-additional-details"></a>La validation du numéro personnel en cours d'utilisation nécessite des informations supplémentaires

Les informations supplémentaires sont affichées lorsque les souches de numéros sont en cours d'utilisation, afin de mieux comprendre les problèmes lorsqu'un nouveau numéro ne peut être généré.
 
### <a name="attachments-buttons-not-available-for-workers"></a>Boutons de pièces jointes non disponibles pour les collaborateurs

Des modifications ont été apportées pour corriger les pièces jointes. Lors de l'ajout d'une nouvelle pièce jointe à un collaborateur, les boutons **Nouveau** et **Modifier** sont désormais disponibles lorsque les récapitulatifs sont en cours dans la fenêtre du collaborateur. 

## <a name="known-issues"></a>Problèmes connus

### <a name="mapping-errors-in-the-integration-with-finance-and-operations"></a>Erreurs de mise en correspondance dans l'intégration à Finance and Operations

Les problèmes suivants ont été identifiés dans le modèle actuel d'intégration de Talent à Finance and Operations. Un nouveau modèle sera publié prochainement et appliqué à tous les nouveaux projets d'intégration qui seront créés. Pour les projets d'intégration existants, les mises en correspondance de tâches peuvent être mises à jour. Pour plus d'informations sur les mises en correspondance mises à jour, voir le tableau suivant. 

>[!NOTE]
> La tâche Attribution de postes d'une mission au poste parent des missions n'intègre pas les données. Il s'agit d'un problème qui fait actuellement l'objet de recherches. Il n'existe aucune solution dans la mise en correspondance actuelle. 

La tâche Départements à unité opérationnelle nécessite que les mises en correspondance suivantes soient mises à jour.

| Champ source existant          | Nouveau champ source |
| -------------------------------|------------------|
| cdm_description (Description)  | cdm_name (Nom)  |

Une mise en correspondance supplémentaire doit également être ajoutée. Sélectionnez le dernier champ **Aucun** pour ajouter la mise en correspondance suivante.

| Champ source                   | Champ de destination    |
| -------------------------------|----------------------|
| cdm_description (Description)  | NAMEALIAS (NAMEALIAS)|

Les mises en correspondance mises à jour doivent ressembler à ce qui suit.

![Tâche Départements à unités opérationnelles](./media/DepartmentMapping.png)


La tâche Missions à Détail de la mission nécessite que les mises en correspondance suivantes soient mises à jour.

| Champ source existant          | Nouveau champ source                   |
| -------------------------------|------------------------------------|
| cdm_name (Nom)                | cdm_description (Description)      |
| cdm_name (Description)         | cdm_jobdescription(Description de la mission)|


Les mises en correspondance mises à jour doivent ressembler à ce qui suit.

![Tâches Mission à Détails de la mission](./media/JobMapping.png)

La tâche Collaborateurs à Travail nécessite que les mises en correspondance suivantes soient mises à jour.

| Champ source existant                 | Nouveau champ source                               |
| --------------------------------------|------------------------------------------------|
| cdm_emailaddress1 (Adresse e-mail 1)   | cdm_primaryemailaddress (Adresse e-mail principale) |
| cdm_telephone1 (Téléphone 1)          | cdm_primarytelephone (Téléphone principal)       |

La transformation du champ Sexe doit également être mise à jour. Sélectionnez le type de mise en correspondance **fn** (fonction) pour Sexe et mettez à jour les mises en correspondance de valeurs suivantes.

| Valeur CDS   | Valeur Finance and Operations | | ------------|------------------ -----------| | 75440000    | Masculin                         | | 75440001    | Féminin                       | | 75440002    | Aucun                         | | 75440003    | NonSpecific                  |

Les mises en correspondance mises à jour doivent ressembler à ce qui suit.

![Tâche Collaborateurs à Collaborateurs](./media/WorkerMapping.png)

![Transformation du champ Sexe](./media/WorkerTransform.png)

