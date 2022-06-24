---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (03 septembre 2020)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 3 septembre 2020.
author: andreabichsel
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7d558f4b0ddb3e8fe3479567483e2c2349a40774
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891348"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-3-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (3 septembre 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s’appliquent au numéro de version 8.1.3504. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support Lifecycle Services (LCS) pour référence.

Pour plus d’informations sur les fonctionnalités à venir dans Human Resources, voir [Vue d’ensemble de la 2e partie du lancement 2019 de Dynamics 365 Human Resources](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/). Pour plus d’informations sur le processus de mise à jour de Human Resources, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

## <a name="in-this-release"></a>Dans cette version

### <a name="new-default-financial-dimensions-grid-and-dialog-pattern-throughout-human-resources-469495"></a>Nouvelle grille de dimensions financières par défaut et nouveau modèle de dialogue dans Human Resources (469495)

Le nouveau modèle des dimensions financières est désormais disponible dans les domaines suivants :

- Actions liées au postes (formulaire : **HcmPositionActionDetail**)
- Codes de rémunération de la paie (formulaire : **PayrollEarningCode**)

### <a name="entries-dont-appear-in-company-leave-calendar-if-leave-and-absence-calendar-enhancements-arent-enabled-484406"></a>Les écritures n’apparaissent pas dans le calendrier des congés de l’entreprise si les améliorations du calendrier des congés et des absences ne sont pas activées (484406)

Cette version corrige un problème où les écritures de congé ne sont pas affichées dans le calendrier des congés de l’entreprise. Ce problème se produit uniquement lorsque l’option de gestion des fonctionnalités **Améliorations du calendrier des congés et des absences** n’est pas activé.

### <a name="benefitplanemployeeentity-issue-467597"></a>Problème avec BenefitPlanEmployeeEntity (467597)

Cette version corrige un problème avec l’entité **BenefitsPlanEmployee**. Lors de l’importation des inscriptions de collaborateurs, le **Code de couverture** et le **Code de type de régime** sont désormais correctement définis. Ce problème entraînait l’affichage incorrect des régimes d’avantages sociaux des employés dans les formulaires **Régime d’avantages sociaux des collaborateurs** et **Ouvrir l’inscription** dans le libre service des employés.

### <a name="electronic-file-1094-c-output-missing-letter-in-xml-435190"></a>Lettre manquante de sortie du fichier électronique 1094-C au format XML (435190)

Cette modification corrige un problème avec le fichier de sortie 1094-C manquant un caractère nécessaire lors de la soumission à l’IRS.

### <a name="employee-variable-compensation-table-mapped-to-fixed-compensation-form-476117"></a>Tableau de rémunération variable des employés mappé sur le formulaire de rémunération fixe (476117)

Cette modification aligne les champs de rémunération fixe avec le formulaire de rémunération fixe. Les champs de rémunération variable ne sont désormais disponibles qu’avec le formulaire de rémunération variable.

### <a name="leave-requests-allowed-before-enrollment-if-that-leave-type-has-a-negative-minimum-balance-469917"></a>Demandes de congé autorisées avant l’inscription si ce type de congé a un solde minimum négatif (469917)

Ce changement interdit de saisir des demandes de congé avant d’être inscrit au plan, même si l’inscription a un solde minimum négatif. Vous ne pouvez saisir ou soumettre des demandes que lorsque le plan est actif.

### <a name="document-templates-dont-download-457279"></a>Les modèles de documents ne se téléchargent pas (457279)

Avec cette modification, vous pouvez désormais télécharger tous les modèles de documents. 

### <a name="data-displays-as-column-headers-instead-of-rows-for-the-pay-rate-field-in-the-compensation-plan-report-476077"></a>Les données s’affichent sous forme d’en-têtes de colonne au lieu de lignes pour le champ Taux de rémunération dans le rapport sur le plan de rémunération (476077)

Le rapport d’analyse affiche désormais les informations correctes pour **Taux de rémunération**.

## <a name="in-preview"></a>En mode aperçu

### <a name="human-resources-application-in-teams"></a>Application Human Resources de Teams

Les collaborateurs peuvent consulter et demander des absences dans Microsoft Teams. Ils peuvent interagir avec un bot pour créer des demandes de congé. Pour plus d’informations, voir :

- [Expérience des employés en congé et absence Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) dans la 1ère partie du lancement 2020 de Dynamics 365
- [Application Human Resources dans Teams](./hr-admin-teams-leave-app.md) dans la documentation Human Resources

### <a name="human-resources-app-in-teams-preview-features"></a>Application Human Resources dans les fonctionnalités d’évaluation Teams
 
-  **Notifications** : Les demandeurs et les approbateurs des demandes de congés seront informés dans l’application Human Resources de Teams. Les approbateurs pourront approuver ou refuser les demandes de congé. Les demandeurs seront informés si la demande a été approuvée ou refusée. Pour plus d’informations, voir :
   - [Expérience de congé et d’absence des employés dans Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) dans la 2e partie du lancement 2020 de Dynamics 365
   - [Activer les notifications de l’application Human Resources dans Teams](./hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) dans la documentation Human Resources
   - [Activer ou désactiver les notifications Teams pour les utilisateurs individuels](./hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users) dans la documentation Human Resources
   - [Notifications Teams](./hr-teams-leave-app.md#respond-to-teams-notifications) dans la documentation Human Resources
   - [Afficher le calendrier des congés de votre équipe](./hr-teams-leave-app.md#view-your-teams-leave-calendar) dans la documentation Human Resources
 
- **Calendrier des congés du responsable** : Les responsables pourront afficher les congés approuvés et en attente pour leurs subordonnés directs dans une vue du calendrier. Cette vue permet de comprendre facilement quand les membres de leur équipe sont absents du travail. Pour plus d’informations, voir :
   - [Expérience de congé et d’absence des employés dans Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) dans la 2e partie du lancement 2020 de Dynamics 365
   - [Afficher le calendrier des congés de votre équipe](./hr-teams-leave-app.md#view-your-teams-leave-calendar) dans la documentation Human Resources

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a>Option de configuration pour positionner la liste des éléments de travail qui m’ont été assignés (477004)

Une nouvelle option est désormais disponible pour positionner la liste **Éléments de travail qui m’ont été attribués** dans la colonne de droite du tableau de bord. Avec cette modification, tous les éléments de travail et les listes de tâches s’affichent dans la même zone. Activez cette fonctionnalité en activant **Aperçu – Améliorations de l’expérience de workflow** dans la gestion des fonctionnalités. Pour plus d’informations sur l’activation des fonctionnalités d’évaluation, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

Cette fonctionnalité favorise également les options de workflow qui apparaissent dans les formulaires d’actions du personnel. Les options de workflow apparaissent également au-dessus de l’onglet Action rapide pour un accès rapide. Pour plus d’informations, voir : 

- [Améliorations de l’expérience du workflow de gestion de l’organisation et du personnel](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) dans la 2e partie du lancement2020 de Dynamics 365

![Éléments de travail qui me sont affectés.](./media/hr-workflow-work-items-assigned-to-me.png)

![Accès rapide aux éléments du workflow.](./media/hr-workflow-quick-access.png)

## <a name="coming-soon"></a>Prochainement

### <a name="checklist-entities-included-in-dataverse"></a>Entités de liste de contrôle incluses dans Dataverse

Les entités de liste de contrôle pour les processus d’intégration, de départ, de transfert et d’entreprise seront bientôt disponibles dans Dataverse.

### <a name="benefits-management-reason-codes"></a>Codes de motif de la gestion des avantages

Les codes de motif de gestion des avantages seront bientôt combinés aux codes de motif existants dans Human Resources. Si vous avez créé des codes raison dans la gestion des avantages de plus de 15 caractères, vous devez modifier le nom du code motif dans le formulaire **Codes motif** de la gestion des avantages sur 15 caractères ou moins. Une fois le nom mis à jour, le code motif apparaîtra sous le formulaire de code motif existant dans la gestion du personnel. Ce changement sera disponible à l’avenir et n’affectera pas les fonctionnalités existantes.

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de la 2e partie du lancement 2019 de Dynamics 365 Human Resources](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
