---
title: Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (14 décembre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 12/14/2018
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
ms.search.validFrom: 2018-12-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 7d2866923efd7f115ad5290f35ed4fcac5e47573
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "304294"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-december-14-2018"></a>Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (14 décembre 2018)

[!include [banner](includes/banner.md)]

**Version 8.1.2085**

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.

## <a name="changes"></a>Modifications

### <a name="us---aca-affordable-care-act-support-for-tax-year-2018-1095-b-and-1095-c-forms"></a>États-Unis - Prise en charge de la Loi sur les soins abordables (ACA) pour les formulaires 1095-B et 1095-C de l'exercice fiscal 2018

Chaque année, les ALE (Grands employeurs applicables) doivent fournir à chaque employé à temps plein un formulaire 1095-C. De plus, si l'employeur fournit une couverture personnelle, il doit fournir le formulaire 1095-C (s'il s'agit d'un ALE) et un formulaire 1095-B (s'il s'agit d'une petite société) à tous les employés, à temps plein ou à temps partiel, couvert par l'un leurs plans de santé. Cette fonctionnalité fournit des écrans imprimables pour les formulaires 1095-C et 1095-B.

### <a name="during-import-submittedbypersonid-field-on-hcmperfjournalentity-is-ignored"></a>Pendant l'importation, le champ SubmittedByPersonId sur HcmPerfJournalEntity est ignoré

Lors de l'importation/exportation des entrées du journal de performances, le champ **Soumis par** est ignoré. Avec cette modification, la valeur **importé/exporté** reflète la valeur dans le tableau pendant l'exportation, lorsque l'importation du système est mis à jour avec la valeur fournie dans le fichier d'importation.

### <a name="analytics-tab-on-leave-and-absence-workspace-displays-openconnectionerror-error-for-non-system-admin-roles"></a>L'onglet Analyses de l'espace de travail « Congés et absences » affiche l'erreur « OpenConnectionError » pour les rôles d'administrateur non système

Avec cette mise à jour, aucune erreur n'est émise lorsque vous ouvrez l'onglet **Analyses** de l'espace de travail **Congés et absences**.

### <a name="employee-self-service-position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a>L'exploration de Libre-service employé, Hiérarchie des postes, depuis la vignette échoue à obtenir un nœud parent

Une modification a été apportée pour corriger l'erreur « L'obtention du nœud parent a échoué » lorsque la hiérarchie des postes a été personnalisée pour s'afficher sur un espace de travail existant et qu'un poste est sélectionné dans la hiérarchie.  

### <a name="must-be-system-admin-to-see-the-payroll-tab-in-the-position-page"></a>Doit être administrateur système pour afficher l'onglet Paie sur la page Poste

Une modification a été apportée pour inclure les éléments de sécurité corrects dans le privilège existant : « Tenir à jour les détails sur les collaborateurs et les postes de la paie ». Avec cette modification, par défaut, l'administrateur de paie a accès aux champs Paie de la page Poste.

### <a name="error-when-submitting-performance-review-to-manager-and-the-reviewsperfperiod-placeholder-is-used-in-the-submission-instructions"></a>Erreur lors de la soumission de l'évaluation des performances au responsable et l'espace réservé %Reviews.PerfPeriod% est utilisé dans les instructions de soumission

Une modification a été apportée pour corriger l'erreur « Référence null » lors de l'utilisation de l'espace réservé %Reviews.PerfPeriod% dans les instructions de soumission.

### <a name="workforce-power-bi-report-shows-error-when-worker-seniority-date-is-a-leap-day"></a>L'état Power BI sur la main-d'œuvre affiche une erreur lorsque la date d'ancienneté du collaborateur est un jour intercalaire

Avec cette modification, les jours intercalaires sont maintenant pris en charge dans Power BI.

### <a name="integration-between-core-hr-and-attract"></a>Intégration entre Core HR et Attract

Une modification a été apportée pour mettre à jour l'intégration entre Core HR et Attract concernant les candidats à embaucher. Pour que les candidats à embaucher soient visibles dans l'espace de travail **Gestion du personnel**, les entités CDS pour les applications (CDS 2.0) suivantes sont utilisés :

Candidature
- La raison du statut doit être définie sur Offre acceptée
-   Fournit le candidat et l'offre d'emploi

Candidat
-   Fournit des informations sur le candidat

Offre d'emploi
-   Fournit l'ID de l'offre d'emploi et les participants à l'offre d'emploi

Participants à l'offre d'emploi
-   Fournit le responsable de l'embauche

Lorsqu'un candidat est ajouté à Gestion du personnel, le candidat peuvent être désormais également ignoré à l'aide d'une nouvelle option disponible sur la fiche du candidat.

## <a name="coming-soon"></a>Prochainement

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a>Congés et absences : Futurs soldes et prévisions de congés

Les modifications apportées pour autoriser les employés à prévoir des congés et à faire de futures demandes de congés sans répercussion sur leur solde actuel de congés modifient également la façon dont les soldes de congés sont affichés. 

Le solde disponible affiché actuellement correspond à la quantité de congés disponible pour les demandes, y compris les régularisations à ce jour et toutes les demandes de congés approuvées à la fin du temps. 

Lorsque la capacité à prévoir sera activée, le solde affiché deviendra le solde actuel de congés, y compris les régularisations à ce jour et les demandes à ce jour. Les employés et les responsables verront ces soldes mis à jour dans le libre-service employé et responsable sur la fiche **Congés** et la fenêtre **Soldes des congés**. Les responsables des RH auront accès à ces soldes mis à jour dans l'espace de travail **Personnes** et dans la fenêtre **Plans de congés affectés** de l'employé.

## <a name="known-issue"></a>Problème connu

### <a name="mapping-errors-in-the-integration-with-finance-and-operations"></a>Erreurs de mise en correspondance dans l'intégration à Finance and Operations

Les problèmes suivants ont été identifiés dans le modèle actuel d'intégration de Talent à Dynamics 365 for Finance and Operations. Un nouveau modèle sera publié prochainement et appliqué à tous les nouveaux projets d'intégration qui seront créés. Pour les projets d'intégration existants, les mises en correspondance de tâches peuvent être mises à jour. Pour plus d'informations sur les mises en correspondance mises à jour, voir le tableau suivant. 

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

Les mises en correspondance mises à jour doivent ressembler à l'illustration suivante.

![Tâche Départements à unités opérationnelles](./media/DepartmentMapping.png)


La tâche Missions à Détail de la mission nécessite que les mises en correspondance suivantes soient mises à jour.

| Champ source existant          | Nouveau champ source                   |
| -------------------------------|------------------------------------|
| cdm_name (Nom)                | cdm_description (Description)      |
| cdm_name (Description)         | cdm_jobdescription(Description de la mission)|


Les mises en correspondance mises à jour doivent ressembler à l'illustration ci-dessous.

![Tâches Mission à Détails de la mission](./media/JobMapping.png)

La tâche Collaborateurs à Travail nécessite que les mises en correspondance suivantes soient mises à jour.

| Champ source existant                 | Nouveau champ source                               |
| --------------------------------------|------------------------------------------------|
| cdm_emailaddress1 (Adresse e-mail 1)   | cdm_primaryemailaddress (Adresse e-mail principale) |
| cdm_telephone1 (Téléphone 1)          | cdm_primarytelephone (Téléphone principal)       |

La transformation du champ Sexe doit également être mise à jour. Sélectionnez le type de mise en correspondance **fn** (fonction) pour Sexe et mettez à jour les mises en correspondance de valeurs suivantes.

| Valeur CDS                   | Valeur Finance and Operations                     |
| ----------------------------|--------------------------------------------------|
| 75440000                    | Masculin                                             |
| 75440001                    | Féminin                                           |
| 75440002                    | Aucune                                             | 
| 75440003                    | NonSpecific                                      |

Les mises en correspondance mises à jour doivent ressembler aux illustrations suivantes.

![Tâche Collaborateurs à Collaborateurs](./media/WorkerMapping.png)

![Transformation du champ Sexe](./media/WorkerTransform.png)
