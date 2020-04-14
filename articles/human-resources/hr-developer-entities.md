---
title: Entités Common Data Service
description: Microsoft Dynamics 365 Human Resources utilise Common Data Service pour permettre des scénarios d'extensibilité et d'intégration.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c8e0288da16829c04a9b97c0a52caa8bd27cddf8
ms.sourcegitcommit: fde8045ea49d0cf26d5e7ac5a0da5c0d3d69d5bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/26/2020
ms.locfileid: "3166496"
---
# <a name="common-data-service-entities"></a>Entités Common Data Service

Microsoft Dynamics 365 Human Resources utilise Common Data Service pour permettre des scénarios d'extensibilité et d'intégration.

Pour plus d'informations sur Common Data Service, voir [Qu'est-ce que Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

Les entités Human Resources suivantes sont disponibles dans Common Data Service.

## <a name="benefit-entities"></a>Entités Avantage

| Nom | Entité |
| --- | --- |
| Fréquence de calcul des avantages | cdm_benefitcalculationfrequency |
| Fréquence de calcul des avantages de la période de rémunération | cdm_benefitcalculationfrequencypayperiod |
| Taux de calcul des avantages | cdm_benefitcalculationrate |
| Détails du taux de calcul des avantages | cdm_benefitcalculationratedetail |
| Option d'avantage | cdm_benefitoption |
| Plan d'avantages | cdm_benefitplan (Non activé pour la prise en charge des champs personnalisés) |
| Type d'avantage | cdm_benefittype |

## <a name="business-process-tasks-entities"></a>Entités de tâches de processus d'entreprise

| Nom | Entité |
| --- | --- |
| Calendrier pour le processus d'entreprise | cdm_businessprocesscalendar |
| Affectation du groupe de processus d'entreprise | cdm_businessprocessgroupassignment |
| Groupe de tâches de la bibliothèque de processus d'entreprise | cdm_businessprocesslibrarytaskgroup |
| Phase du processus d'entreprise | cdm_businessprocessstage |
| En-tête de modèle de liste de contrôle | cdm_businessprocesstemplateheader |
| Tâche du modèle de liste de contrôle | cdm_businessprocesstemplatetask |

## <a name="compensation-entities"></a>Entités de rémunération

| Nom | Entité |
| --- | --- |
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
| Événement de rémunération fixe | cdm_fixedcompensationevent |
| Règle d'acquisition | cdm_vestingrule |
| Rémunération fixe du collaborateur | cdm_workerfixedcompensation |

## <a name="organization-entities"></a>Entités Organisation

| Nom | Entité |
| --- | --- |
| Département | cdm_department |
| Emploi | cdm_employment |
| Société | cdm_company |
| Mission | cdm_job |
| Fonction de tâche | cdm_jobfunction |
| Poste | cdm_jobposition |
| Type de poste | cdm_positiontype |
| Affectation du collaborateur au poste | cdm_positionworkerassignmentmap |
| Dimension du poste | cdm_jobpositiondimension|
| Type de poste | cdm_jobtype |
| Langue | cdm_language |
| Titre | cdm_title |

> [!NOTE]
> Les dimensions financières pour **Type de poste**, **Affectation du collaborateur au poste** et **Emploi** fournissent une intégration unidirectionnelle vers Common Data Service. Les mises à jour des dimensions financières ne peuvent actuellement pas se synchroniser de Common Data Service vers Human Resources. 

## <a name="leave-and-absence-entities"></a>Entités liées aux congés et absences

| Nom | Entité |
| --- | --- |
| Transaction bancaire de congé | cdm_leavebanktransaction |
| Inscription aux congés | cdm_leaveenrollment |
| Plan de congé | cdm_leaveplan |
| Demande de congé | cdm_leaverequest |
| Détails de la demande de congés | cdm_leaverequestdetail |
| Type de congé | cdm_leavetype |
| Code motif du type de congé | cdm_leavetypereasoncode |

## <a name="payroll-entities"></a>Entités de paie

| Nom | Entité |
| --- | --- |
| Cycle de paie | cdm_paycycle |
| Période de rémunération | cdm_payperiod |
| Code de rémunération de la paie | cdm_payrollearningcode |
| Décaissements du compte en banque | cdm_bankaccountdisbursement |
| Zone fiscale | cdm_taxregion |

## <a name="worker-entities"></a>Entités de collaborateurs

| Nom | Entité |
| --- | --- |
| Collaborateur | cdm_worker |
| Adresse du collaborateur | cdm_workeraddress |
| Détails personnels du collaborateur | cdm_workerpersonaldetail |
| Numéro d'identification personnel du collaborateur | cdm_workerpersonidentificationnumber |
| Type d'identification personnel du collaborateur | cdm_workerpersonidentificationtype |
| Calendrier de travail | cdm_workcalendar |
| Jours de calendrier de travail | cdm_workcalendarday |
| Congé du calendrier de travail |cdm_workcalendarholiday |
| Ligne de congé du calendrier de travail | cdm_workcalendarholidayline |
| Intervalle de temps du calendrier de travail | cdm_workcalendartimeinterval (Non activé pour la prise en charge des champs personnalisés) |
| Compte bancaire du collaborateur | cdm_workerbankaccount |

## <a name="worker-setup-entities"></a>Entités de configuration des collaborateurs

| Nom | Entité |
| --- | --- |
| Statut d'ancien combattant | cdm_veteranstatus |
| Origine ethnique | cdm_ethnicorigin |
| Code motif | cdm_reasoncode |
| Administration émettrice de l'identification des personnes | cdm_personidentificationissuingagency |

## <a name="competency-entities"></a>Entités de compétence

| Nom | Entité |
| --- | --- |
| Type de qualification | cdm_skilltype |

## <a name="entity-relationship-models"></a>Modèles de relation d'entité

### <a name="worker"></a>Collaborateur

![Collaborateur](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>Emploi et poste

![Emploi et poste](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Avantages

![Avantages](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Rémunération

![Rémunération](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Quitter

![Quitter](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Calendrier de travail

![Calendrier de travail](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a>Voir également :

[Choisir une technologie d'intégration de données](hr-admin-integration-choose-technology.md)</br>
[Configuration de l'intégration Common Data Service](hr-admin-integration-common-data-service.md)
