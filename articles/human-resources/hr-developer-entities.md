---
title: Tables Dataverse
description: Microsoft Dynamics 365 Human Resources utilise Dataverse pour permettre des scénarios d’extensibilité et d’intégration.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: e316cda9b9c5361c0a2837e7ed6c050e76cc39b9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793607"
---
# <a name="dataverse-tables"></a>Tables Dataverse

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources utilise Dataverse pour permettre des scénarios d’extensibilité et d’intégration.

> [!NOTE]
> Les entités Human Resources correspondent aux tables Dataverse. Pour plus d’informations sur Dataverse (auparavant Common Data Service) et les mises à jour terminologiques, voir [Qu’est-ce que Microsoft Dataverse ?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)

Les tables Dataverse suivantes sont disponibles dans les entités Human Resources.

## <a name="benefit-tables"></a>Tables des avantages

| Nom | Table |
| --- | --- |
| Fréquence de calcul des avantages | cdm_benefitcalculationfrequency |
| Fréquence de calcul des avantages de la période de rémunération | cdm_benefitcalculationfrequencypayperiod |
| Taux de calcul des avantages | cdm_benefitcalculationrate |
| Détails du taux de calcul des avantages | cdm_benefitcalculationratedetail |
| Option d’avantage | cdm_benefitoption |
| Plan d’avantages | cdm_benefitplan (Non activé pour la prise en charge des champs personnalisés) |
| Type d’avantage | cdm_benefittype |

## <a name="business-process-tasks-tables"></a>Tables des tâches de processus d’entreprise

| Nom | Enregistrement |
| --- | --- |
| Calendrier pour le processus d’entreprise | cdm_businessprocesscalendar |
| Affectation du groupe de processus d’entreprise | cdm_businessprocessgroupassignment |
| Groupe de tâches de la bibliothèque de processus d’entreprise | cdm_businessprocesslibrarytaskgroup |
| Phase du processus d’entreprise | cdm_businessprocessstage |
| En-tête de modèle de liste de contrôle | cdm_businessprocesstemplateheader |
| Tâche du modèle de liste de contrôle | cdm_businessprocesstemplatetask |

## <a name="compensation-tables"></a>Tables de rémunération

| Nom | Table |
| --- | --- |
| Régime fixe de rémunération | cdm_compensationfixedplan |
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
| Règle d’acquisition | cdm_vestingrule |
| Rémunération fixe du collaborateur | cdm_workerfixedcompensation |

## <a name="organization-tables"></a>Tables d’organisation

| Nom | Enregistrement |
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
> Les dimensions financières pour **Type de poste**, **Affectation du collaborateur au poste** et **Emploi** fournissent une intégration unidirectionnelle vers Dataverse. Les mises à jour des dimensions financières ne peuvent actuellement pas se synchroniser de Dataverse vers Human Resources. 

## <a name="leave-and-absence-tables"></a>Tables de congés et d’absences

| Nom | Enregistrement |
| --- | --- |
| Transaction bancaire de congé | cdm_leavebanktransaction |
| Inscription à un congé | cdm_leaveenrollment |
| Plan de congé | cdm_leaveplan |
| Demande de congé | cdm_leaverequest |
| Détails de la demande de congés | cdm_leaverequestdetail |
| Type de congé | cdm_leavetype |
| Code motif du type de congé | cdm_leavetypereasoncode |

## <a name="payroll-tables"></a>Tables des salaires

| Nom | Enregistrement |
| --- | --- |
| Cycle de paie | cdm_paycycle |
| Période de rémunération | cdm_payperiod |
| Code de rémunération des salaires | cdm_payrollearningcode |
| Décaissements du compte en banque | cdm_bankaccountdisbursement |
| Zone fiscale | cdm_taxregion |

## <a name="worker-tables"></a>Tables des collaborateurs

| Nom | Enregistrement |
| --- | --- |
| Collaborateur | cdm_worker |
| Adresse du collaborateur | cdm_workeraddress |
| Détails personnels du collaborateur | cdm_workerpersonaldetail |
| Numéro d’identification personnel du collaborateur | cdm_workerpersonidentificationnumber |
| Type d’identification personnel du collaborateur | cdm_workerpersonidentificationtype |
| Calendrier de travail | cdm_workcalendar |
| Jours de calendrier de travail | cdm_workcalendarday |
| Congé du calendrier de travail |cdm_workcalendarholiday |
| Ligne de congé du calendrier de travail | cdm_workcalendarholidayline |
| Intervalle de temps du calendrier de travail | cdm_workcalendartimeinterval (Non activé pour la prise en charge des champs personnalisés) |
| Compte bancaire du collaborateur | cdm_workerbankaccount |

## <a name="worker-setup-tables"></a>Tables de configuration des collaborateurs

| Nom | Enregistrement |
| --- | --- |
| Statut de vétéran | cdm_veteranstatus |
| Origine ethnique | cdm_ethnicorigin |
| Code motif | cdm_reasoncode |
| Agence émettrice de l’identification de la personne | cdm_personidentificationissuingagency |

## <a name="competency-tables"></a>Tables des compétences

| Nom | Enregistrement |
| --- | --- |
| Type de qualification | cdm_skilltype |

## <a name="table-relationship-models"></a>Modèles de relations de table

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

[Choisir une technologie d’intégration de données](hr-admin-integration-choose-technology.md)<br>
[Configuration de l’intégration Dataverse](hr-admin-integration-common-data-service.md)<br>
[Configurer des tables virtuelles Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[FAQ sur les tables virtuelles Human Resources](hr-admin-virtual-entity-faq.md)<br>
[Qu’est-ce que Microsoft Dataverse ?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[Mises à jour de la terminologie](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]