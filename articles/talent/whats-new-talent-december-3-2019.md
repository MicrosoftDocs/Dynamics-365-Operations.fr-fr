---
title: Nouveautés ou modifications dans Dynamics 365 Talent (3 décembre 2019)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 12/03/2019
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
ms.author: dkrame
ms.search.validFrom: 2019-12-03
ms.dyn365.ops.version: Talent
ms.openlocfilehash: bf1ad4ca2e0ab18aaa35a7410d80a54e7a2160ce
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528691"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-december-3-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (3 décembre 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2646. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).

### <a name="feature-management-workspace"></a>Espace de travail Gestion des fonctionnalités

L'espace de travail **Gestion des fonctions** fournit une liste des fonctions fournies dans chaque lancement. Par défaut, les nouvelles fonctionnalités sont désactivées. Vous pouvez utiliser l'espace de travail pour les activer et consulter la documentation les concernant. Pour plus d'informations sur la gestion des fonctions, voir [Présentation de la gestion des fonctions](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Toutes les nouvelles fonctionnalités restent dans la version préliminaire pendant au moins 30 jours, et généralement entre 30 et 60 jours. Les fonctionnalités principales sont généralement disponibles en octobre et en avril chaque année suivant la période de version préliminaire. Dès que vous voyez de nouvelles fonctionnalités dans l'espace de travail **Gestion des fonctions**, vous pouvez les activer. Certaines fonctionnalités peuvent être activées par défaut.
 
Parfois, une fonctionnalité intégrale sera activée par défaut et ne pourra pas être désactivée (par exemple, l'espace de travail **Gestion des fonctions**).
 
Une fois qu’une fonction est généralement disponible, elle peut être activée ou désactivée dans les environnements de production. L'espace de travail **Gestion des fonctions** indique quand une fonction d'aperçu devient obligatoire. Cette date est généralement le 1er octobre ou le 1er avril pour s’aligner avec les plans de lancement semi-annuels. Vous ne pouvez pas désactiver les fonctions obligatoires. Tant qu'elle n'est pas obligatoire, vous pouvez activer et désactiver une fonction dans tous les environnements.

### <a name="add-automatic-scheduling-of-batch-job-history-cleanup-332528"></a>Ajout d'une planification automatique du nettoyage de l'historique des traitements par lots (332528)

Avec ce changement, l'**Historique des traitements par lots** s'exécute chaque nuit et supprime les éléments de l'historique des traitements par lots de plus de 30 jours.

### <a name="talent-doesnt-respond-in-worker-actions-when-identification-number-length-doesnt-match-the-identification-type-390971"></a>Talent ne répond pas aux actions du collaborateur lorsque la longueur du numéro d'identification ne correspond pas au type d'identification (390971)

Cette version corrige le problème apparu lorsque la longueur du numéro d'identification ne correspond pas à la définition du type d'identification. 

### <a name="fixed-compensation-doesnt-update-level-with-changes-to-position-details--348085"></a>La rémunération fixe ne met pas à jour le niveau avec les modifications apportées aux détails du poste (348085)

Dans la version de cette semaine, **Date de début de la rémunération** détermine la tâche associée au poste au moment de la création d'un enregistrement de rémunération fixe pour un employé.

### <a name="workers-employees-and-contractors-lists-show-worker-type-as-both-when-they-should-only-be-worker-or-contractor-384473"></a>Les listes des collaborateurs, des employés et des fournisseurs indiquent le type de collaborateur comme étant Les deux alors qu'elles ne devraient être que des collaborateurs ou des fournisseurs (384473)

Ce changement reflète avec précision le type de collaborateur entré (fournisseur ou employé).

### <a name="email-notifications-for-new-hire-actions-dont-contain-name-information-due-to-security-policies-383402"></a>Les notifications par e-mail pour les actions de nouvelle embauche ne contiennent pas d'informations de nom en raison des stratégies de sécurité (383402)

Cette modification corrige les informations affichées dans les champs Prénom ou Nom dans les espaces réservés pour le workflow lorsque la sécurité avancée est activée.

### <a name="system-allows-two-full-day-leave-requests-for-the-same-day-379284"></a>Le système permet deux demandes de congé d'une journée entière pour la même journée (379284)

Avec cette modification, vous ne pouvez pas émettre deux demandes de congé le même jour. 

### <a name="address-changes-list-should-be-sorted-by-effective-date-352798"></a>La liste des changements d'adresse doit être triée par date d'effet (352798)

Avec ce changement, la liste de changement d'adresse est maintenant triée par **Date d'effet**.

### <a name="leave-requests-should-allow-deletes-from-common-data-service-to-talent-376999"></a>Les demandes de congé doivent autoriser les suppressions de Common Data Service vers Talent (376999)

Avec cette modification, les demandes de congés provisoires et annulées peuvent être supprimées de Common Data Service puis de Talent.

### <a name="delete-earning-codes-is-allowed-when-the-same-earning-code-is-assigned-to-an-employee-371792"></a>La suppression des codes de rémunération est autorisée lorsque le même code de rémunération est attribué à un employé (371792)

Dans cette version, vous devez d'abord supprimer le code de rémunération de l'employé avant de supprimer le code de rémunération du système.

### <a name="leave-and-absence-workflow-with-two-approval-stages-fails-to-complete--391116"></a>Le workflow des congés et des absences avec deux étapes d'approbation ne se termine pas (391116)

Avec cette modification, le workflow des congés et des absences se poursuit à travers toutes les étapes lorsque plusieurs étapes d'approbation sont configurées pour la demande.

### <a name="issue-date-doesnt-sync-to-common-data-service-when-updated-or-entered-in-talent-397361"></a>La date d'émission n'est pas synchronisée avec Common Data Service une fois mise à jour ou entrée dans Talent (397361)

Cette modification corrige un problème où la date d'émission des enregistrements **Identification de la personne** n'a pas été synchronisée avec Common Data Service dans Talent.

### <a name="hierarchy-circular-reference-error-issued-when-assigning-a-manager-to-a-position-386659"></a>Erreur de référence circulaire de hiérarchie émise lors de l'affectation d'un gestionnaire à un poste (386659)

Cette modification corrige un scénario unique dans lequel une erreur de référence circulaire apparaît lors de l'affectation d'un nouveau responsable à un poste.

### <a name="common-data-service-entities-that-now-support-custom-fields"></a>Entités Common Data Service prenant maintenant en charge les champs personnalisés

Les entités Common Data Service suivantes prennent désormais en charge les champs personnalisés :

| Nom | Entité |
| --- | --- |
| Décaissements du compte en banque | cdm_bankaccountdisbursement |
| Fréquence de calcul des avantages | cdm_benefitcalculationfrequency |
| Fréquence de calcul des avantages de la période de rémunération | cdm_benefitcalculationfrequencypayperiod |
| Taux de calcul des avantages | cdm_benefitcalculationrate |
| Détails du taux de calcul des avantages | cdm_benefitcalculationratedetail |
| Option d'avantage | cdm_benefitoption |
| Plan d'avantages | cdm_benefitplan (Non activé pour la prise en charge des champs personnalisés) |
| Type d'avantage | cdm_benefittype |
| Calendrier pour le processus d'entreprise | cdm_businessprocesscalendar |
| Affectation du groupe de processus d'entreprise | cdm_businessprocessgroupassignment |
| Groupe de tâches de la bibliothèque de processus d'entreprise | cdm_businessprocesslibrarytaskgroup |
| Phase du processus d'entreprise | cdm_businessprocessstage |
| En-tête de modèle de liste de contrôle | cdm_businessprocesstemplateheader |
| Tâche du modèle de liste de contrôle | cdm_businessprocesstemplatetask |
| Société | cdm_company |
| Régime de rémunération fixe | cdm_compensationfixedplan |
| Grille de rémunération | cdm_compensationgrid |
| Niveau de rémunération | cdm_compensationlevel |
| Fréquence de paiement de la rémunération | cdm_compensationpayfrequency |
| Paramétrage des points de référence de rémunération | cdm_compensationreferencepointsetup |
| Ligne de paramétrage des points de référence de rémunération | cdm_compensationreferencepointsetupline |
| Région de rémunération | cdm_compensationregion |
| Structure des rémunérations | cdm_compensationstructure |
| Régime de rémunération variable | cdm_compensationvariableplan |
| Niveau du régime de rémunération variable | cdm_compensationvariableplanlevel |
| Type du régime rémunération variable | cdm_compensationvariableplantype |
| Département | cdm_department |
| Emploi | cdm_employment |
| Origine ethnique | cdm_ethnicorigin |
| Événement de rémunération fixe | cdm_fixedcompensationevent |
| Mission | cdm_job |
| Fonction de tâche | cdm_jobfunction |
| Poste | cdm_jobposition |
| Type de tâche | cdm_jobtype |
| Langue | cdm_language |
| Transaction bancaire de congé | cdm_leavebanktransaction |
| Inscription aux congés | cdm_leaveenrollment |
| Plan de congé | cdm_leaveplan |
| Demande de congé | cdm_leaverequest |
| Détails de la demande de congés | cdm_leaverequestdetail |
| Type de congé | cdm_leavetype |
| Code motif du type de congé | cdm_leavetypereasoncode |
| Cycle de paie | cdm_paycycle |
| Période de rémunération | cdm_payperiod |
| Code de rémunération de la paie | cdm_payrollearningcode |
| Administration émettrice de l'identification des personnes | cdm_personidentificationissuingagency |
| Type de poste | cdm_positiontype |
| Affectation du collaborateur au poste | cdm_positionworkerassignmentmap |
| Code motif | cdm_reasoncode |
| Type de qualification | cdm_skilltype |
| Zone fiscale | cdm_taxregion |
| Règle d'acquisition | cdm_vestingrule |
| Statut d'ancien combattant | cdm_veteranstatus |
| Calendrier de travail | cdm_workcalendar |
| Jours de calendrier de travail | cdm_workcalendarday |
| Congé du calendrier de travail |cdm_workcalendarholiday |
| Ligne de congé du calendrier de travail | cdm_workcalendarholidayline |
| Intervalle de temps du calendrier de travail | cdm_workcalendartimeinterval (Non activé pour la prise en charge des champs personnalisés) |
| Collaborateur | cdm_worker |
| Adresse du collaborateur | cdm_workeraddress |
| Compte bancaire du collaborateur | cdm_workerbankaccount |
| Rémunération fixe du collaborateur | cdm_workerfixedcompensation |
| Détails personnels du collaborateur | cdm_workerpersonaldetail |
| Numéro d'identification personnel du collaborateur | cdm_workerpersonidentificationnumber |
| Type d'identification personnel du collaborateur | cdm_workerpersonidentificationtype |

## <a name="in-preview"></a>En mode aperçu

Les fonctions d'aperçu sont disponibles uniquement dans des environnements de **bac à sable**.

### <a name="print-performance-reviews"></a>Imprimer les évaluations des performances

Voir [Imprimer les examens des performances](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) dans Dynamics 365 : 2e partie du lancement 2019.


[!INCLUDE[footer-include](../includes/footer-banner.md)]