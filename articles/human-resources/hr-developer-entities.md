---
title: Tables Dataverse
description: Microsoft Dynamics 365 Human Resources utilise Dataverse pour permettre des scénarios d’extensibilité et d’intégration.
author: twheeloc
ms.date: 12/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 51be30f10c8e5f5e962f54f720f66c712a785835
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838580"
---
# <a name="dataverse-tables"></a>Tables Dataverse


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources utilise Dataverse pour permettre des scénarios d’extensibilité et d’intégration.

> [!NOTE]
> Les entités Human Resources correspondent aux tables Dataverse. Pour plus d’informations sur Dataverse (auparavant Common Data Service) et les mises à jour terminologiques, voir [Qu’est-ce que Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)

Les tables Dataverse suivantes sont disponibles dans les entités Human Resources.

Pour plus d’informations sur les problèmes connus, voir [Recherche d’incidents dans Lifecycle Services (LCS)](/dev-itpro/lifecycle-services/issue-search-lcs).

## <a name="benefit-tables"></a>Tables des avantages

| Name | Tableau | Problèmes connus  | Status |
| --- | --- |    --------|----------  |
| Fréquence de calcul des avantages | cdm_benefitcalculationfrequency |     |     |
| Fréquence de calcul des avantages de la période de rémunération | cdm_benefitcalculationfrequencypayperiod |     |     |
| Taux de calcul des avantages | cdm_benefitcalculationrate |    |     |
| Détails du taux de calcul des avantages | cdm_benefitcalculationratedetail |753225 | Résolu  |
| Option d’avantage | cdm_benefitoption |    |     |
| Plan d’avantages | cdm_benefitplan (Non activé pour la prise en charge des champs personnalisés) |    |     |
| Type d’avantage | cdm_benefittype |    |     |

## <a name="business-process-tasks-tables"></a>Tables des tâches de processus d’entreprise

| Name | Tableau |Problèmes connus  | Status |
| --- | --- |   --------|----------   |
| Calendrier pour le processus d’entreprise | cdm_businessprocesscalendar | 751867 | Résolu |
| Affectation du groupe de processus d’entreprise | cdm_businessprocessgroupassignment | 751869  751863 | Actif|
| Groupe de tâches de la bibliothèque de processus d’entreprise | cdm_businessprocesslibrarytaskgroup |751866 | Clôturée |
| Phase du processus d’entreprise | cdm_businessprocessstage |      |     |
| En-tête de modèle de liste de contrôle | cdm_businessprocesstemplateheader |     |     |
| Tâche du modèle de liste de contrôle | cdm_businessprocesstemplatetask |      |     |

## <a name="compensation-tables"></a>Tables de rémunération

| Name | Tableau |Problèmes connus  | Status |
| --- | --- | ----------      | -------    |
| Régime fixe de rémunération | cdm_compensationfixedplan |754453 | Clôturée |
| Grille de rémunération | cdm_compensationgrid |             |     |
| Niveau de rémunération | cdm_compensationlevel |           |     |
| Fréquence de paiement de la rémunération | cdm_compensationpayfrequency |                  |     |
| Paramétrage des points de référence de rémunération | cdm_compensationreferencepointsetup |               |     |
| Ligne de paramétrage des points de référence de rémunération | cdm_compensationreferencepointsetupline |             |     |
| Région de rémunération | cdm_compensationregion |                   |     |
| Structure des rémunérations | cdm_compensationstructure |    754456        | Clôturée    |
| Régime de rémunération variable | cdm_compensationvariableplan |               |     |
| Niveau du régime de rémunération variable | cdm_compensationvariableplanlevel |                |     |
| Type du régime rémunération variable | cdm_compensationvariableplantype |               |     |
| Événement de rémunération fixe | cdm_fixedcompensationevent |               |     |
| Règle d’acquisition | cdm_vestingrule |              |     |
| Rémunération fixe du collaborateur | cdm_workerfixedcompensation |              |     |

## <a name="organization-tables"></a>Tables d’organisation

| Name | Tableau |Problèmes connus  | Status |
| --- | --- | ----------      | -------    |
| Département | cdm_department |  752194    | Clôturée    |
| Emploi | cdm_employment | 762414  |  Clôturée  |
| Société | cdm_company |  |     |
| Poste | cdm_job |  |     |
| Fonction de tâche | cdm_jobfunction |        |     |
| Poste | cdm_jobposition | 752214      | Clôturée    |
| Type de poste | cdm_positiontype |            |     |
| Affectation du collaborateur au poste | cdm_positionworkerassignmentmap | 752224    |  Clôturée   |
| Dimension du poste | cdm_jobpositiondimension|       |     |
| Type de poste | cdm_jobtype |      |     |
| Langue | cdm_language |        |     |
| Titre | cdm_title |       |     |

> [!NOTE]
> Les dimensions financières pour **Type de poste**, **Affectation du collaborateur au poste** et **Emploi** fournissent une intégration unidirectionnelle vers Dataverse. Les mises à jour des dimensions financières ne peuvent actuellement pas se synchroniser de Dataverse vers Human Resources. 

## <a name="leave-and-absence-tables"></a>Tables de congés et d’absences

| Name | Tableau | Problèmes connus  | Status |
| --- | --- |   ----------      | -------    |
| Transaction bancaire de congé | cdm_leavebanktransaction |  752252    |    Résolu |
| Inscription à un congé | cdm_leaveenrollment |  752934    |Clôturée     |
| Plan de congé | cdm_leaveplan |   752232   |   Clôturée  |
| Demande de congé | cdm_leaverequest | 753207     | Clôturée    |
| Détails de la demande de congés | cdm_leaverequestdetail | 753207     |   Clôturée  |
| Type de congé | cdm_leavetype |      |     |
| Code motif du type de congé | cdm_leavetypereasoncode |         |     |

>[!NOTE]
>L’intégration à double écriture à l’aide de tables Dataverse pour les congés et les absences n’est disponible que lorsque la fonctionnalité **Configurer plusieurs types de congés sur un seul plan de congé** est activée dans Microsoft Dynamics 365 Finance en utilisant **la gestion des fonctionnalités**. 

## <a name="payroll-tables"></a>Tables des salaires

| Name | Tableau |Problèmes connus  | Status |
| --- | --- |  ----------      | -------    |
| Cycle de paie | cdm_paycycle |    |     |
| Période de rémunération | cdm_payperiod |          |     |
| Code de rémunération des salaires | cdm_payrollearningcode |   754458        |   Clôturée  |
| Décaissements du compte en banque | cdm_bankaccountdisbursement |    751904     |   Clôturée  |
| Zone fiscale | cdm_taxregion |          |     |

## <a name="worker-tables"></a>Tables des collaborateurs

| Name | Tableau |Problèmes connus  | Status |
| --- | --- |----------      | -------    |
| Travailleur | cdm_worker |    751906    |    Clôturée |
| Adresse du collaborateur | cdm_workeraddress |   754465     |Clôturée     |
| Détails personnels du collaborateur | cdm_workerpersonaldetail |   751906     |   Clôturée  |
| Numéro d’identification personnel du collaborateur | cdm_workerpersonidentificationnumber |  766704      |   Clôturée  |
| Type d’identification personnel du collaborateur | cdm_workerpersonidentificationtype |        |     |
| Calendrier de travail | cdm_workcalendar |        |     |
| Jours de calendrier de travail | cdm_workcalendarday |        |     |
| Congé du calendrier de travail |cdm_workcalendarholiday |        |     |
| Ligne de congé du calendrier de travail | cdm_workcalendarholidayline |        |     |
| Intervalle de temps du calendrier de travail | cdm_workcalendartimeinterval (Non activé pour la prise en charge des champs personnalisés) |        |     |
| Compte bancaire du collaborateur | cdm_workerbankaccount |        |     |

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

![Collaborateur.](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>Emploi et poste

![Emploi et poste.](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Avantages

![Avantages.](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Rémunération

![Rémunération.](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Congés

![Congés.](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Calendrier de travail

![Calendrier de travail.](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a>Voir également :

[Choisir une technologie d’intégration de données](hr-admin-integration-choose-technology.md)<br>
[Configuration de l’intégration Dataverse](hr-admin-integration-common-data-service.md)<br>
[Configurer des tables virtuelles Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[FAQ sur les tables virtuelles Human Resources](hr-admin-virtual-entity-faq.md)<br>
[Qu’est-ce que Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Mises à jour de la terminologie](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
