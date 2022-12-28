---
title: Configurer l’intégration avec les tables Dataverse
description: Cet article décrit l’intégration entre les applications Microsoft Dynamics 365 Human Resources et Dataverse.
author: anschmidt
ms.date: 12/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2022-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63c25020b7026a76ecc6e2c3563f8299627ec8a8
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838624"
---
# <a name="configure-integration-with-dataverse-tables"></a>Configurer l’intégration avec les tables Dataverse

>[!Important]
>La fonctionnalité indiquée dans cet article est actuellement disponible pour les clients dans Dynamics 365 Human Resources sur l’infrastructure de finances et d’opérations. 


Pour intégrer Microsoft Dynamics 365 Human Resources avec Dataverse, vous pouvez utiliser [l’intégrateur de données](/powerapps/administrator/data-integrator). Le modèle Human Resources vers Dataverse permet aux données pour les emplois, les postes, les travailleurs et autres de passer de Human Resources vers Dataverse, et de Dataverse vers Human Resources, créant une écriture dans les deux systèmes.

## <a name="system-requirements-for-human-resources"></a>Configuration requise pour Human Resources

La solution d’intégration nécessite les versions suivantes de Human Resources et de Dynamics 365 Finance : 

- Dynamics 365 Finance versions 7.2 et ultérieures
- Environnement Dynamics CRM dans lequel une base de données a été créée et les applications Dynamics 365 sont autorisées

## <a name="template-and-tasks"></a>Modèle et tâches

Pour accéder au modèle Human Resources à Finance, procédez comme suit.

1. Ouvrez le [centre d’administration Power Apps](https://admin.powerapps.com/). 
2. Sous votre environnement, sélectionnez **Applications Dynamics 365**, puis **Source de l’application** dans la barre d’outils.
3. Pour installer le modèle, recherchez « Human Resources en double écriture » ou rendez-vous directement à l’adresse suivante : <https://appsource.microsoft.com/product/dynamics-365/mscrm.hcm_dualwrite>.
3. Une fois l’installation terminée, ouvrez Dynamics 365 Finance.
4. Ouvrez l’espace de travail **Gestion des données**. 
5. Sélectionnez **Double écriture**. 
6. Suivez le processus de liaison de votre environnement pour au moins une entreprise de votre organisation. 
7. Quand vous avez terminé de configurer un lien vers votre environnement Dataverse, sélectionnez **Appliquer la solution**. La solution est appliquée et les mappages sont installés dans l’application d’intégration.

## <a name="template-mappings"></a>Mises en correspondance des modèles

Dans les tableaux de mappage de modèles suivants, le nom de la tâche indique les entités utilisées dans chaque application. Finance est à gauche et Dataverse est à droite.

### <a name="bank-account-disbursements-dual-write-to-bank-account-disbursement"></a>Décaissements du compte bancaire (double écriture) vers le décaissement du compte bancaire

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACCOUNTIDENTIFICATIONID        | cdm\_bankaccountid.cdm\_accountidentification        |
| MONTANT                         | cdm\_amount                                         |
| PRIORITÉ                       | cdm\_disbursementpriority                           |
| NUMÉRO PERSONNEL                | cdm\_bankaccountid.cdm\_workerid.cdm\_workernumber    |
| SOLDE                      | cdm\_isremainder                                    |

### <a name="benefit-calculation-rate-detail-dual-write-to-benefit-calculation-rate-detail"></a>Détails du taux de calcul des avantages (double écriture) en détail du taux de calcul des avantages

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| MÉTHODEDECONTRIBUTION             | cdm\_contributionmethod                             |
| EFFECTIF                      | cdm\_effective                                      |
| CONTRIBUTIONDEL’EMPLOYEUR           | cdm\_employercontribution                           |
| EXPIRATION                     | cdm\_expiration                                     |
| RETENUEDESCOLLABORATEURS                | cdm\_workerdeduction                                |
| NAME                           | cdm\_calculationrateid.cdm\_name                     |

### <a name="benefit-calculation-rate-header-to-benefit-calculation-rate"></a>En-tête Taux de calcul des avantages pour le taux de calcul des avantages

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| NAME                           | cdm\_name                                           |
| TYPEDENIVEAU                       | cdm\_tiertype                                       |

### <a name="benefit-option-to-benefit-option"></a>Option d’avantage à Option d’avantage

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| AUTORISERLESDÉSIGNATIONSDESBÉNÉFICIAIRES   | cdm\_allowbeneficiarydesignations                   |
| AUTORISERLACOUVERTUREDESPERSONNESÀCHARGE         | cdm\_allowdependentcoverage                         |
| IDOPTIONDAVANTAGE                | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| ESTANNULÉ                        | cdm\_iswaived                                       |

### <a name="benefit-type-to-benefit-type"></a>Type d’avantage à type d’avantage

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IDTYPEAVANTAGE                  | cdm\_name                                           |
| INSCRIPTIONSIMULTANÉE           | cdm\_concurrentenrollment                           |
| DESCRIPTION                    | cdm\_description                                    |
| CATÉGORIEDESALAIRE                | cdm\_payrollcategory                                |

### <a name="business-calendar-to-business-process-calendar"></a>Calendrier métier vers calendrier des processus métier

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALENDARID                     | cdm\_name                                           |
| NAME                           | cdm\_calendarname                                   |
| STARTDATE                      | cdm\_startdate                                      |
| ENDDATE                        | cdm\_enddate                                        |
| ESTOUVERTLELUNDI                   | cdm\_ismondayopen                                   |
| ESTOUVERTLEMARDI                  | cdm\_istuesdayopen                                  |
| ESTOUVERTLEMERCREDI                | cdm\_iswednesdayopen                                |
| ESTOUVERTLEJEUDI                 | cdm\_isthursdayopen                                 |
| ESTOUVERTLEVENDREDI                   | cdm\_isfridayopen                                   |
| ESTOUVERTLESAMEDI                 | cdm\_issaturdayopen                                 |
| ESTOUVERTLEDIMANCHE                   | cdm\_issundayopen                                   |

### <a name="business-process-to-business-process-header"></a>Processus métier à en-tête de processus métier

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IDDEPROCESSUS                      | cdm\_processid                                      |
| TYPEDEPROCESSUS                    | cdm\_processtype                                    |
| SOUSTYPEGÉNÉRIQUE                 | cdm\_genericsubtype                                 |
| NAME                           | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| STATUT                         | cdm\_status                                         |
| DATECIBLE                     | cdm\_targetdate                                     |
| DATEETHEUREDEDÉBUT                  | cdm\_startdatetime                                  |
| DATEETHEUREDEFIN                    | cdm\_enddatetime                                    |
| RÉSOLUPARNUMÉRODUPERSONNEL      | cdm\_resolvedbyid.cdm\_workernumber                  |
| NUMÉRODEPERSONNELDUPROPRIÉTAIREDUPROCESSUS    | cdm\_processownerid.cdm\_workernumber                |
| NOMDUMODÈLESOURCE             | cdm\_sourcetemplateid.cdm\_name                      |
| TYPEDEMODÈLEDEPROCESSUSSOURCE      | cdm\_sourcetemplateid.cdm\_businessprocesstype       |
| SOUSTYPEDEMODÈLEGÉNÉRIQUESOURCE   | cdm\_sourcetemplateid.cdm\_genericsubtype            |

### <a name="business-process-library-task-group-to-business-process-library-task-group"></a>Groupe de tâches de la bibliothèque de processus métier vers groupe de tâches de la bibliothèque de processus métier

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| TYPEDEPROCESSUS                    | cdm\_processtype                                    |
| NAME                           | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |

### <a name="business-process-stage-to-business-process-stage"></a>Phase du processus métier à phase de processus métier

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| TYPEDEPROCESSUS                    | cdm\_businessprocesstype                            |
| NAME                           | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| NUMÉRODESOUCHE                 | cdm\_sequencenumber                                 |

### <a name="business-process-task-to-business-process-task"></a>Tâche de processus métier à tâche de processus métier

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| DATEDÉCHÉANCE                        | cdm\_duedate                                        |
| IDDETÂCHE                         | cdm\_taskid                                         |
| INSTRUCTIONS                   | cdm\_instructions                                   |
| DATEETHEUREDEFIN             | cdm\_completiondatetime                             |
| TYPED’AFFECTATION                 | cdm\_assignmenttype                                 |
| ESTFACULTATIF                     | cdm\_isoptional                                     |
| NAME                           | cdm\_name                                           |
| STATUT                         | cdm\_status                                         |
| RÉSOLUPAR\_NUMÉRODUPERSONNEL     | cdm\_resolvedbyid.cdm\_workernumber                  |
| IDMODÈLETÂCHE                 | cdm\_templatetaskid.cdm\_taskid                      |
| COLLABORATEURATTRIBUÉ\_NUMÉRODEPERSONNEL | cdm\_assignedworkerid.cdm\_workernumber              |
| IDDEPROCESSUS                      | cdm\_processheaderid.cdm\_processid                  |
| GROUPEAFFECTÉ\_NOM             | cdm\_assignedgroupid.cdm\_name                       |
| POSTEAFFECTÉ\_IDDEPOSTE    | cdm\_assignedposition.cdm\_jobpositionnumber         |

### <a name="business-process-template-to-checklist-template-header"></a>Modèle de processus métier vers l’en-tête du modèle de liste de contrôle

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| TYPEDEPROCESSUS                    | cdm\_businessprocesstype                            |
| SOUSTYPEGÉNÉRIQUE                 | cdm\_genericsubtype                                 |
| NAME                           | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| CALENDARID                     | cdm\_businessprocesscalendarid.cdm\_name             |
| NUMÉRO PERSONNEL                | cdm\_processownerid.cdm\_workernumber                |
| ISACTIVE                       | cdm\_isactive                                       |

### <a name="business-process-template-task-to-checklist-template-task"></a>Modèle de tâche de processus métier vers tâche du modèle de liste de contrôle

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IDDETÂCHE                         | cdm\_taskid                                         |
| NAME                           | cdm\_name                                           |
| MODÈLEDENTÊTE\_TYPEDEPROCESSUS     | cdm\_businessprocesstemplateheaderid.cdm\_businessprocesstype |
| MODÈLEDENTÊTE\_SOUSTYPEGÉNÉRIQUE  | cdm\_businessprocesstemplateheaderid.cdm\_genericsubtype |
| MODÈLEDENTÊTE\_NOM            | cdm\_businessprocesstemplateheaderid.cdm\_name       |
| DESCRIPTION                    | cdm\_description                                    |
| DATEDÉCHÉANCEJOURSDÉCALÉS              | cdm\_duedateoffsetdays                              |
| TYPEDOPTIONDEMENU                   | cdm\_tasklinktype                                   |
| OPTIONDEMENU                       | cdm\_tasklink                                       |
| PERSONNEDECONTACT\_NUMÉROPERSONNEL  | cdm\_contactpersonid.cdm\_workernumber               |
| TYPED’AFFECTATION                 | cdm\_assignmenttype                                 |
| COLLABORATEURATTRIBUÉ\_NUMÉRODEPERSONNEL | cdm\_assignedworkerid.cdm\_workernumber              |
| POSTEAFFECTÉ\_IDDEPOSTE    | cdm\_assignedpositionid.cdm\_jobpositionnumber       |
| GROUPEAFFECTÉ\_NOM             | cdm\_assignedgroupid.cdm\_name                       |
| ESTFACULTATIF                     | cdm\_isoptional                                     |
| INSTRUCTIONS                   | cdm\_instructions                                   |

### <a name="calculation-frequency-to-benefit-calculation-frequency"></a>Fréquence de calcul à fréquence de calcul des avantages

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| FREQUENCY                      | cdm\_name                                           |
| CONTRÔLEDELAFRÉQUENCE               | cdm\_frequencycontrol                               |
| ESTINALTÉRABLE                    | cdm\_isimmutable                                    |

### <a name="calculation-frequency-pay-period-to-benefit-calculation-frequency-pay-period"></a>Fréquence de calcul de la période de rémunération en fréquence de calcul des avantages sociaux de la période de rémunération

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IDFRÉQUENCEDECALCUL         | cdm\_benefitcalculationfrequencyid.cdm\_name         |
| DATEDEDÉBUTDELAPÉRIODE                | cdm\_payperiodid.cdm\_periodstartdate                |
| IDDUCYCLEDEPAIE                     | cdm\_payperiodid.cdm\_paycycleid.cdm\_name            |

### <a name="calendar-to-work-calendar"></a>Calendrier en calendrier de travail

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALENDARID                     | cdm\_name                                           |
| NOMDUCALENDRIER                   | cdm\_description                                    |
| IDCONGÉSDUCALENDRIERDETRAVAIL          | cdm\_workcalendarholidayid.cdm\_name                 |

### <a name="compensation-fixed-action-table-to-fixed-compensation-event"></a>Table d’action fixe de rémunération à événement de rémunération fixe

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACTION                         | cdm\_name                                           |
| ACTIF                         | cdm\_isactive                                       |
| DESCRIPTION                    | cdm\_description                                    |
| TYPE                           | cdm\_eventtype                                      |

### <a name="compensation-fixed-plan-to-compensation-fixed-plan"></a>Régime fixe de rémunération à Régime fixe de rémunération

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| RÉGIME                           | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| TYPE                           | cdm\_type                                           |
| DATEDEFFET                  | cdm\_effectivedate                                  |
| DATEEXPIRATION                 | cdm\_expirationdate                                 |
| DEVISE                       | cdm\_transactioncurrencyid.isocurrencycode          |
| FRÉQUENCEPAIE                   | cdm\_payfrequency.cdm\_name                          |
| RÈGLEDEMBAUCHE                       | cdm\_hirerule                                       |
| TOLÉRANCEDESVALEURSHORSLIMITE            | cdm\_outofrangetolerance                            |
| RECOMMANDATIONAUTORISÉE          | cdm\_recommendationallowed                          |
| STRUCTUREDESRÉMUNÉRATIONS          | cdm\_compensationgrid.cdm\_name                      |
| IDPARAMÉTRAGEDEPOINTSDERÉFÉRENCE                | cdm\_referencepointsetupline.cdm\_referencepointsetupid.cdm\_name |
| POINTDECONTRÔLE                   | cdm\_referencepointsetupline.cdm\_name               |

### <a name="compensation-grids-to-compensation-grid"></a>Grilles de rémunération à Grille de rémunération

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IDGRILLE                         | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| DATEDEFFET                  | cdm\_effectivedate                                  |
| DATEEXPIRATION                 | cdm\_expirationdate                                 |
| PARAMÉTRAGEDERÉFÉRENCE                 | cdm\_referencepointsetupid.cdm\_name                 |
| TYPE                           | cdm\_type                                           |
| DEVISE                       | cdm\_transactioncurrencyid.isocurrencycode          |

### <a name="compensation-job-function-to-job-function"></a>Fonction du poste à Fonction du poste de rémunération

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IDFONCTIONDUPOSTE                  | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |

### <a name="compensation-job-type-to-job-type"></a>Type de tâche de rémunération à Type de tâche

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IDTYPEDEPOSTE                      | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| STATUTDELEXEMPTION                   | cdm\_exemptstatus                                   |

### <a name="compensation-pay-frequency-to-compensation-pay-frequency"></a>Fréquence de paiement de la rémunération à Fréquence de paiement de la rémunération

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| FRÉQUENCEDEPAIEMENT              | cdm\_name                                           |
| PÉRIODE                         | cdm\_period                                         |
| DESCRIPTION                    | cdm\_description                                    |
| FACTEURDECONVERSIONANNUEL         | cdm\_annualconversionfactor                         |
| FACTEURDECONVERSIONHORAIRE         | cdm\_hourlyconversionfactor                         |
| FACTEURDECONVERSIONMENSUEL        | cdm\_monthlyconversionfactor                        |
| FACTEURDECONVERSIONHEBDOMADAIRE         | cdm\_weeklyconversionfactor                         |

### <a name="compensation-regions-to-compensation-region"></a>Régions de rémunération à région de rémunération

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| EMPLACEMENT                       | cdm\_name                                           |

### <a name="compensation-variable-plan-v2-to-compensation-variable-plan"></a>Régime variable de rémunération V2 à Régime variable de rémunération

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| BASEDELAPRIMEVARIABLE             | cdm\_awardbasis                                     |
| CALCULDEBASEDELAPRIME          | cdm\_awardbasiscalculation                          |
| TYPEDECALCUL                | cdm\_calculationtype                                |
| DESCRIPTION                    | cdm\_description                                    |
| ACTIVERLINSCRIPTION               | cdm\_enableenrollment                               |
| ACTIVERLESNIVEAUX                   | cdm\_enablelevels                                   |
| ACTIVERLARECOMMANDATION           | cdm\_enablerecommendation                           |
| RÈGLEDEMBAUCHE                       | cdm\_hirerule                                       |
| VALEUR100POURCENT             | cdm\_leverage100percent                             |
| VALEURMAXIMALE                | cdm\_leveragemaximum                                |
| VALEURMINIMALE                | cdm\_leverageminimum                                |
| VALEURAUDELÀDELOBJECTIF          | cdm\_leverageoverobjective                          |
| VALEURENDEÇÀDELOBJECTIF         | cdm\_leverageunderobjective                         |
| POURCENTAGEDEBASE                 | cdm\_percentofbasis                                 |
| IDRÉGIME                         | cdm\_name                                           |
| TYPEDERÉMUNÉRATIONVARIABLE       | cdm\_variablecompensationtypeid.cdm\_name            |
| CODEDEVISEUNITAIRE               | transactioncurrencyid.isocurrencycode              |
| RELATIONUNITAIRE               | cdm\_unitrelationship                               |
| VALEURUNITAIRE                      | cdm\_unitvalue                                      |
| NOMBREDUNITÉSRÉEL              | cdm\_numberofunits                                  |
| DATEDEFFET                  | cdm\_effectivedate                                  |
| DATEEXPIRATION                 | cdm\_expirationdate                                 |
| RÈGLEDACQUISITION                    | cdm\_vestingruleid.cdm\_name                         |
| TOLÉRANCEDELAVALEURMAXIMALE           | cdm\_leveragetolerancemax                           |
| TOLÉRANCEDELAVALEURMINIMALE           | cdm\_leveragetolerancemin                           |

### <a name="compensation-variable-type-to-compensation-variable-plan-type"></a>Type de variable de rémunération à type de régime variable de rémunération

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| TYPE                           | cdm\_awardtype                                      |
| TYPEDERÉMUNÉRATIONVARIABLE       | cdm\_name                                           |

### <a name="compensation-vesting-rules-to-vesting-rule"></a>Règles d’acquisition de la rémunération à la règle d’acquisition

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| NOTE                           | cdm\_notes                                          |
| RÈGLEDACQUISITION                    | cdm\_name                                           |

### <a name="department-v2-to-department"></a>Département V2 en département

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| OPERATINGUNITNUMBER            | cdm\_departmentnumber                               |
| NAME                           | cdm\_name                                           |
| NOMDERECHERCHE                     | cdm\_description                                    |
| PARTYTYPE                      | cdm\_partytype                                      |

### <a name="dual-write-tax-region-to-tax-region"></a>Zone fiscale en double écriture en zone fiscale

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| VILLE                           | cdm\_city                                           |
| PAYSOURÉGION                | cdm\_countryorregion                                |
| DÉPARTEMENT                         | cdm\_county                                         |
| ÉTAT                          | cdm\_stateorprovince                                |
| NOMDELAZONEFISCALE                  | cdm\_name                                           |

### <a name="dual-write-worker-identification-to-worker-person-identification-number"></a>Identification du collaborateur en double écriture en numéro d’identification personnel du collaborateur

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| TYPEDESAISIE                      | cdm\_entrytype                                      |
| DATEEXPIRATION                 | cdm\_expirationdate                                 |
| IDENTIFICATIONNUMBER           | cdm\_identificationnumber                           |
| IDTYPEDIDENTIFICATION           | cdm\_identificationtypeid.cdm\_name                  |
| ESTPRINCIPAL                      | cdm\_isprimary                                      |
| DATEDÉMISSION                      | cdm\_issuedate                                      |
| IDAGENCEÉMETTRICE                | cdm\_issuingagencyid.cdm\_name                       |
| MATRICULEDUCOLLABORATEUR                   | cdm\_workerid.cdm\_workernumber                      |

### <a name="compensation-structure-to-compensation-structure"></a>Structure de rémunération en structure de rémunération

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| MONTANT                         | cdm\_amount                                         |
| GRILLE                           | cdm\_compensationgridid.cdm\_name                    |
| IDNIVEAU                        | cdm\_compensationlevelid.cdm\_name                   |
| NUMÉRODELIGNEDEPOINTDERÉFÉRENCE       | cdm\_referencepointid.cdm\_linenumber                |
| PARAMÉTRAGEDERÉFÉRENCE                 | cdm\_referencepointid.cdm\_referencepointsetupid.cdm\_name |
| POINTDERÉFÉRENCE                 | cdm\_referencepointid.cdm\_name                      |

### <a name="earning-code-to-payroll-earning-code"></a>Code de gain en code de gain de la paie

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CODEDERÉMUNÉRATION                    | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| INCLUREDANSTYPEDEPAIEMENT           | cdm\_includeinpaymenttype                           |
| UNITÉDEQUANTITÉ                   | cdm\_quantityunit                                   |
| SUIVRELESHEURESFMLA                 | cdm\_trackfmlahours                                 |
| ESTPRODUCTIF                   | cdm\_isproductive                                   |

### <a name="employee-fixed-compensation-to-worker-fixed-compensation"></a>Rémunération fixe de l’employé à Rémunération fixe du collaborateur

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IDNIVEAURÉMUNÉRATION            | cdm\_compensationlevelid.cdm\_name                   |
| TYPE                           | cdm\_compensationtype                               |
| DATEDEFFET                  | cdm\_effectivedate                                  |
| DATEEXPIRATION                 | cdm\_expirationdate                                 |
| LINENUMBER                     | cdm\_linenumber                                     |
| FRÉQUENCEPAIE                   | cdm\_payfrequencyid.cdm\_name                        |
| TAUXDERÉMUNÉRATION                        | cdm\_payrate                                        |
| RÉGIME                           | cdm\_planid.cdm\_name                                |
| IDPOSTE                     | cdm\_positionid.cdm\_jobpositionnumber               |
| TYPEDEPROCESSUS                    | cdm\_processtype                                    |
| NUMÉRO PERSONNEL                | cdm\_workerid.cdm\_workernumber                      |
| ACTION                         | cdm\_eventid.cdm\_name                               |
| ÉTAPE                           | cdm\_referencepointsetuplineid.cdm\_name             |
| IDPARAMÉTRAGEDEPOINTSDERÉFÉRENCE                | cdm\_referencepointsetuplineid.cdm\_referencepointsetupid.cdm\_name |

### <a name="employment-per-company-to-employment"></a>Emploi par entreprise en Emploi

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DATEDEFINDELEMPLOI              | cdm\_employmentenddate                              |
| NUMÉRO PERSONNEL                | cdm\_workerid.cdm\_workernumber                      |
| DATEDEDÉBUTDELEMPLOI            | cdm\_employmentstartdate                            |
| TYPEDECOLLABORATEUR                     | cdm\_workertype                                     |
| VALEURDAFFICHAGEDELADIMENSION          | cdm\_dimensiondisplayvalue                          |
| DATEDEDÉBUTAJUSTÉEDUCOLLABORATEUR        | cdm\_adjustedworkerstartdate                        |
| MONTANTDUPRÉAVISDELEMPLOYEUR           | cdm\_employernoticeamount                           |
| UNITÉDEPRÉAVISDELEMPLOYEUR           | cdm\_employerunitofnotice                           |
| UNITÉDEPRÉAVISDUCOLLABORATEUR             | cdm\_workerunitofnotice                             |
| MONTANTDEPRÉAVISDUCOLLABORATEUR             | cdm\_workernoticeamount                             |
| DERNIERJOURDETRAVAIL                 | cdm\_lastdateworked                                 |
| DATEDEFINDEPÉRIODEDESSAI               | cdm\_probationenddate                               |
| DATEDETRANSITION                 | cdm\_transitiondate                                 |
| NOMDECODERAISONDELATRANSITION       | cdm\_transitionreasoncode.cdm\_name                  |
| DATEDEDÉBUTDUCOLLABORATEUR                | cdm\_workerstartdate                                |
| VALIDTO                        | cdm\_validto                                        |
| VALIDFROM                      | cdm\_validfrom                                      |

### <a name="ethnic-origins-to-ethnic-origin"></a>Origine ethnique à origine ethnique

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ETHNICORIGINID                 | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |

### <a name="group-assignment-to-business-process-group-assignment"></a>Affectation de groupe à Affectation de groupe de processus d’entreprise

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| NAME                           | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| ISACTIVE                       | cdm\_isactive                                       |

### <a name="identification-type-to-worker-person-identification-type"></a>Type d’identification en type d’identification du collaborateur

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| IDTYPEDIDENTIFICATION           | cdm\_name                                           |
| VALEURSAUTORISÉES                  | cdm\_allowedvalues                                  |
| LONGUEURFIXE                    | cdm\_fixedlength                                    |
| FORMATDUNUMÉRODIDENTIFICATION     | cdm\_identificationnumberformat                     |

### <a name="issuing-agency-to-person-identification-issuing-agency"></a>Agence émettrice en Agence émettrice de l’identification de la personne

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| E-MAIL                          | cdm\_email                                          |
| POSTE                      | cdm\_extension                                      |
| TÉLÉCOPIE                            | cdm\_fax                                            |
| AGENCEÉMETTRICE                  | cdm\_name                                           |
| TÉLÉPHONEPORTABLE                    | cdm\_mobilephone                                    |
| ADRESSEINTERNET                | cdm\_websiteurl                                     |
| NAME                           | cdm\_description                                    |
| RécepteurDeRadiomessagerie                          | cdm\_pager                                          |
| SMS                            | cdm\_sms                                            |
| TÉLÉPHONE                      | cdm\_telephone                                      |
| NUMÉRODETÉLEX                    | cdm\_telex                                          |
| ADDRESSCITY                    | cdm\_city                                           |
| ADDRESSCOUNTY                  | cdm\_county                                         |
| ADDRESSDESCRIPTION             | cdm\_addressdescription                             |
| ADDRESSSTATE                   | cdm\_stateorprovince                                |
| ADDRESSSTREET                  | cdm\_street                                         |
| ADDRESSZIPCODE                 | cdm\_postalcode                                     |
| ADDRESSCOUNTRYREGIONISOCODE    | cdm\_countryregion                                  |

### <a name="job-positions-dual-write-to-job-position"></a>Postes en double écriture à poste

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IDPOSTE                     | cdm\_jobpositionnumber                              |
| ACTIVATION                     | cdm\_activation                                     |
| DISPONIBLEPOURAFFECTATION         | cdm\_availableforassignment                         |
| IDRÉGIONDERÉMUNÉRATION           | cdm\_compensationregionid.cdm\_name                  |
| IDDÉPARTMENT                   | cdm\_departmentid.cdm\_departmentnumber              |
| DESCRIPTION                    | cdm\_description                                    |
| ÉQUIVALENTTEMPSPLEIN             | cdm\_fulltimeequivalent                             |
| IDTÂCHE                          | cdm\_jobid.cdm\_name                                 |
| IDPOSITIONPARENT               | cdm\_parentjobpositionid.cdm\_jobpositionnumber      |
| IDTYPEPOSITION                 | cdm\_positiontypeid.cdm\_name                        |
| RETIREMENT                     | cdm\_retirement                                     |
| IDTITRE                        | cdm\_titleid.cdm\_name                               |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |

### <a name="jobs-dual-write-to-job"></a>Tâches en double écriture à tâche

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IDTÂCHE                          | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| DESCRIPTIONDUPOSTE                 | cdm\_jobdescription                                 |
| AUTORISERDESPOSTESILLIMITÉS        | cdm\_allowunlimitedpositions                        |
| NOMBREMAXIMALDEPOSTES       | cdm\_maximumnumberofpositions                       |
| IDFONCTIONDUPOSTE                  | cdm\_jobfunctionid.cdm\_name                         |
| IDTYPEDEPOSTE                      | cdm\_jobtypeid.cdm\_name                             |
| IDTITRE                        | cdm\_titleid.cdm\_name                               |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |
| ÉQUIVALENCETEMPSPLEINPARDÉFAUT     | cdm\_defaultfulltimeequivalent                      |

### <a name="language-codes-to-language"></a>Codes langues à langue

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IDCODELANGUE                 | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |

### <a name="leave-and-absence-bank-transaction-v2-to-leave-bank-transaction"></a>Transaction bancaire congés et absences V2 vers Transaction bancaire congés

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| MONTANT                         | cdm\_amount                                         |
| IDTYPECONGÉS                    | cdm\_leavetypeid.cdm\_type                           |
| IDRÉGIMECONGÉS                    | cdm\_leaveplanid.cdm\_name                           |
| TRANSACTIONDATE                | cdm\_transactiondate                                |
| TRANSACTIONNUMBER              | cdm\_transactionnumber                              |
| NUMÉRO PERSONNEL                | cdm\_workerid.cdm\_workernumber                      |
| TRANSACTIONTYPE                | cdm\_transactiontype                                |

### <a name="leave-and-absence-enrollment-v2-to-leave-enrollment"></a>Inscription aux congés et absences V2 en inscription aux congés

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| STARTDATE                      | cdm\_startdate                                      |
| ENDDATE                        | cdm\_enddate                                        |
| DATEPERSONNALISÉE                     | cdm\_customdate                                     |
| DATEDEDÉBUTDERÉGULARISATION               | cdm\_accrualstartdate                               |
| BASEPOURLADATEDERÉGULARISATION               | cdm\_accrualdatebasis                               |
| ESTUNERÉGULARISATIONSUSPENDUE             | cdm\_isaccrualsuspended                             |
| IDRÉGIMECONGÉS                    | cdm\_leaveplanid.cdm\_name                           |
| BASEDENIVEAU                      | cdm\_tierbasis                                      |
| NUMÉRO PERSONNEL                | cdm\_workerid.cdm\_workernumber                      |

### <a name="leave-and-absence-plan-v2-to-leave-plan"></a>Régime de congés et absences V2 en régime de congés

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| FRÉQUENCEDERÉGULARISATION               | cdm\_accrualfrequency                               |
| NAME                           | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| STARTDATE                      | cdm\_startdate                                      |
| IDTYPECONGÉS                    | cdm\_leavetypeid.cdm\_type                           |

### <a name="leave-and-absence-type-to-leave-type"></a>Type de congés et d’absences à type de congés

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| TYPE                           | cdm\_type                                           |
| IDCODEDERÉMUNÉRATION                  | cdm\_earningcodeid.cdm\_name                         |

### <a name="leave-and-absence-type-reason-code-to-leave-type-reason-code"></a>Code motif du type de congés et d’absences à Code motif du type de congés

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| TYPEDECONGÉ                      | cdm\_typeid.cdm\_type                                |
| IDCODEMOTIF                   | cdm\_reasoncodeid.cdm\_name                          |

### <a name="leave-time-off-request-detail-to-leave-request-detail"></a>Détail de la demande de départ en congé en détail de la demande de congé

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| MONTANT                         | cdm\_amount                                         |
| DATEDECONGÉ                      | cdm\_leavedate                                      |
| IDDEMANDE                      | cdm\_leaverequestid.cdm\_leaverequestnumber          |
| TYPE                           | cdm\_leavetypeid.cdm\_type                           |

### <a name="leave-time-off-request-header-to-leave-request"></a>En-tête de la demande de départ en congé en demande de congé

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IDDEMANDE                      | cdm\_leaverequestnumber                             |
| Datedelademande                    | cdm\_requestdate                                    |
| STATUT                         | cdm\_status                                         |
| COMMENTAIRE                        | cdm\_comment                                        |
| NUMÉRO PERSONNEL                | cdm\_workerid.cdm\_workernumber                      |

### <a name="levels-to-compensation-level"></a>Niveaux en niveau de rémunération

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| TYPE                           | cdm\_type                                           |
| DESCRIPTION                    | cdm\_description                                    |
| NIVEAU                          | cdm\_name                                           |

### <a name="onboarding-process-header-to-onboard-process-header"></a>En-tête de processus d’intégration en en-tête de processus d’intégration

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IDDEPROCESSUS                      | cdm\_processheaderid.cdm\_processid                  |
| MATRICULEDELEMPLOYÉINTÉGRÉ | cdm\_onboardedemployeeid.cdm\_workernumber           |
| NUMÉRODEPERSONNELDELEMPLOI      | cdm\_employmentid.cdm\_workerid.cdm\_workernumber     |
| LEGALENTITYID                  | cdm\_employmentid.cdm\_companyid.cdm\_companycode     |
| DATEDEDÉBUTDELEMPLOI            | cdm\_employmentid.cdm\_employmentstartdate           |

### <a name="pay-cycle-to-pay-cycle"></a>Cycle de paie à cycle de paie

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IDDUCYCLEDEPAIE                     | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| FRÉQUENCEDUCYCLEDEPAIE              | cdm\_frequency                                      |

### <a name="pay-period-to-pay-period"></a>Période de paie à période de paie

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| COMMENTS                       | cdm\_description                                    |
| DATEDEPAIEMENTPARDÉFAUT             | cdm\_defaultpaymentdate                             |
| IDDUCYCLEDEPAIE                     | cdm\_paycycleid.cdm\_name                            |
| DATEDEFINDEPÉRIODE                  | cdm\_periodenddate                                  |
| DATEDEDÉBUTDELAPÉRIODE                | cdm\_periodstartdate                                |
| STATUT                         | cdm\_status                                         |

### <a name="payroll-details-for-positions-to-payroll-position-detail"></a>Détails de paie pour les postes à détail du poste de paie

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IDDUCYCLEDEPAIE                     | cdm\_paycycle.cdm\_name                              |
| IDPOSTE                     | cdm\_position.cdm\_jobpositionnumber                 |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |
| DURÉEANNUELLENORMALE             | cdm\_annualregularhours                             |
| PAYÉPARLENTITÉJURIDIQUE              | cdm\_paidby.cdm\_companycode                         |

### <a name="position-default-dimensions-dual-write-to-job-position-dimension"></a>Double écriture des dimensions par défaut de la position en dimension de la position de la tâche

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| VALEURDAFFICHAGEDELADIMENSION          | cdm\_dimensiondisplayvalue                          |
| IDPOSTE                     | cdm\_jobpositionid.cdm\_jobpositionnumber            |

### <a name="position-type-to-position-type"></a>Type de poste à Type de poste

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IDTYPEPOSITION                 | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| CLASSIFICATION                 | cdm\_classification                                 |

### <a name="position-worker-assignments-v2-to-position-worker-assignment"></a>Affectations du collaborateur V2 au poste à Affectation du collaborateur au poste

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| NUMÉRO PERSONNEL                | cdm\_workerid.cdm\_workernumber                      |
| IDPOSTE                     | cdm\_jobpositionid.cdm\_jobpositionnumber            |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |
| IsPrimaryPosition              | cdm\_isprimaryposition                              |

### <a name="reason-codes-to-reason-code"></a>Codes de motif vers Code de motif

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IDCODEMOTIF                   | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| ISABSENCEAPPLICABLE            | cdm\_isabsenceapplicable                            |
| ISAPPLICATIONAPPLICABLE        | cdm\_isapplicationapplicable                        |
| ISCOMPENSATIONAPPLICABLE       | cdm\_iscompensationapplicable                       |
| ISCREATENEWPOSITIONAPPLICABLE  | cdm\_iscreatenewpositionapplicable                  |
| ISEDITPOSITIONAPPLICABLE       | cdm\_iseditpositionapplicable                       |
| ISHIREAPPLICABLE               | cdm\_ishireapplicable                               |
| ISSKILLMAPPINGAPPLICABLE       | cdm\_isskillmappingapplicable                       |
| ISTERMINATIONAPPLICABLE        | cdm\_isterminationapplicable                        |
| ISTRANSFERAPPLICABLE           | cdm\_istransferapplicable                           |

### <a name="reference-point-setup-line-dual-write-to-compensation-reference-point-setup-line"></a>Ligne de configuration du point de référence (double écriture) vers la ligne de configuration du point de référence de rémunération

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| LINENUM                        | cdm\_linenumber                                     |
| REFPOINTID                     | cdm\_name                                           |
| IDPARAMÉTRAGEDEPOINTSDERÉFÉRENCE                | cdm\_referencepointsetupid.cdm\_name                 |

### <a name="reference-point-setups-to-compensation-reference-point-setup"></a>Paramètres du point de référence en paramètre du point de référence de rémunération

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PARAMÉTRAGEDERÉFÉRENCE                 | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| TYPE                           | cdm\_compensationtype                               |

### <a name="skill-types-to-skill-type"></a>Types de compétence vers Type de compétence

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| SKILLTYPE                      | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |

### <a name="titles-to-title"></a>Titres à titre

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IDTITRE                        | cdm\_name                                           |

### <a name="variable-compensation-level-v2-to-compensation-variable-plan-level"></a>Niveau de rémunération variable V2 à niveau de régime variable de rémunération

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| AWARDAMOUNT                    | cdm\_awardamount                                    |
| AWARDPERCENT                   | cdm\_awardpercent                                   |
| AWARDUNITSREAL                 | cdm\_awardunits                                     |
| COMPENSATIONLEVELID            | cdm\_compensationlevelid.cdm\_name                   |
| IDRÉGIME                         | cdm\_compensationvariableplanid.cdm\_name            |

### <a name="veteran-status-to-veteran-status"></a>Statut d’ancien combattant en statut d’ancien combattant

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| VETERANSTATUSID                | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| ISPROTECTEDVETERAN             | cdm\_isprotectedveteran                             |

### <a name="work-calendar-enrollments-to-work-calendar-enrollment"></a>Inscriptions au calendrier de travail en inscription au calendrier de travail

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| STARTDATE                      | cdm\_employmentid.cdm\_employmentstartdate           |
| NUMÉRO PERSONNEL                | cdm\_employmentid.cdm\_workerid.cdm\_workernumber     |
| CALENDARID                     | cdm\_workcalendarid.cdm\_name                        |
| COMPANYID                      | cdm\_employmentid.cdm\_companyid.cdm\_companycode     |

### <a name="work-calendar-holiday-to-work-calendar-holiday"></a>Congé du calendrier de travail à Congé du calendrier de travail

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| lD                             | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |

### <a name="work-calendar-holiday-line-to-work-calendar-holiday-line"></a>Ligne de congé du calendrier de travail à ligne de congé du calendrier de travail

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| HOLIDAYID                      | cdm\_workcalendarholidayid.cdm\_name                 |
| NAME                           | cdm\_name                                           |
| HOLIDAYDATE                    | cdm\_holidaydate                                    |

### <a name="worker-to-worker"></a>Collaborateur à Collaborateur

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| NUMÉRO PERSONNEL                | cdm\_workernumber                                   |
| FIRSTNAME                      | cdm\_firstname                                      |
| MIDDLENAME                     | cdm\_middlename                                     |
| LASTNAME                       | cdm\_lastname                                       |
| WORKERTYPE                     | cdm\_type                                           |
| WORKERSTATUS                   | cdm\_status                                         |
| PRIMARYCONTACTEMAIL            | cdm\_primaryemailaddress                            |
| PRIMARYCONTACTPHONE            | cdm\_primarytelephone                               |
| PRIMARYCONTACTFACEBOOK         | cdm\_facebookidentity                               |
| PRIMARYCONTACTTWITTER          | cdm\_twitteridentity                                |
| PRIMARYCONTACTLINKEDIN         | cdm\_linkedinidentity                               |
| PRIMARYCONTACTURL              | cdm\_websiteurl                                     |
| GENDER                         | cdm\_gender                                         |
| BIRTHDATE                      | cdm\_birthdate                                      |
| NAME                           | cdm\_fullname                                       |

### <a name="worker-bank-accounts-to-worker-bank-account"></a>Comptes bancaires des collaborateurs en compte bancaire de collaborateur

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACCOUNTIDENTIFICATION          | cdm\_accountidentification                          |
| ADDRESSCITY                    | cdm\_city                                           |
| ADDRESSCOUNTRYREGIONID         | cdm\_countryorregion                                |
| ADDRESSCOUNTY                  | cdm\_county                                         |
| ADDRESSDESCRIPTION             | cdm\_addressdescription                             |
| ADDRESSDISTRICTNAME            | cdm\_districtname                                   |
| ADDRESSPOSTBOX                 | cdm\_postofficebox                                  |
| ADDRESSSTATE                   | cdm\_stateorprovince                                |
| ADDRESSZIPCODE                 | cdm\_postalcode                                     |
| NUMÉRO PERSONNEL                | cdm\_workerid.cdm\_workernumber                      |
| BANKACCOUNTNUMBER              | cdm\_bankaccountnumber                              |
| BANKACCOUNTTYPE                | cdm\_bankaccounttype                                |
| E-MAIL                          | cdm\_email                                          |
| EXTENSION                      | cdm\_extension                                      |
| FAX                            | cdm\_fax                                            |
| INTERNETADDRESS                | cdm\_websiteurl                                     |
| MOBILEPHONE                    | cdm\_mobilephone                                    |
| ROUTINGNUMBER                  | cdm\_routingnumber                                  |
| TELEPHONE                      | cdm\_telephone                                      |
| NUMÉRODETÉLEX                    | cdm\_telexnumber                                    |
| BANKIBAN                       | cdm\_iban                                           |
| SWIFTNO                        | cdm\_swiftcode                                      |
| BANKLOCATIONCODE               | cdm\_banklocationcode                               |
| BRANCHNAME                     | cdm\_branchname                                     |
| BRANCHNUMBER                   | cdm\_branchnumber                                   |
| ROUTINGNUMBERTYPE              | cdm\_routingnumbertype                              |
| ACCOUNTHOLDER                  | cdm\_accountholder                                  |
| NAMEOFPERSON                   | cdm\_nameofperson                                   |
| NAME                           | cdm\_description                                    |
| ADDRESSSTREET                  | cdm\_line1                                          |
| ADDRESSSTREETNUMBER            | cdm\_line2                                          |

### <a name="worker-personal-details-to-worker-personal-detail"></a>Données personnelles du travailleur vers Données personnelles du travailleur

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| NUMÉRO PERSONNEL                | cdm\_workerid.cdm\_workernumber                      |
| BIRTHDATE                      | cdm\_birthdate                                      |
| PERSONBIRTHCITY                | cdm\_birthcity                                      |
| GENDER                         | cdm\_gender                                         |
| EXPATRIATEENDDATE              | cdm\_expatriateenddate                              |
| EXPATRIATESTARTDATE            | cdm\_expatriatestartdate                            |
| DISABLEDVETERAN                | cdm\_isdisabledveteran                              |
| DECEASEDDATE                   | cdm\_deceaseddate                                   |
| DISABLEDVERIFICATIONDATE       | cdm\_disabledveteranverificationdate                |
| EDUCATION                      | cdm\_education                                      |
| ETHNICORIGINID                 | cdm\_ethnicoriginid.cdm\_name                        |
| ISDISABLED                     | cdm\_isdisabled                                     |
| ISFULLTIMESTUDENT              | cdm\_isfulltimestudent                              |
| ISEXPATRIATERULINGAPPLICABLE   | cdm\_isexpatriaterulingapplicable                   |
| MARITALSTATUS                  | cdm\_maritalstatus                                  |
| MILITARYSERVICESTARTDATE       | cdm\_militaryservicestartdate                       |
| MILITARYSERVICEENDDATE         | cdm\_militaryserviceenddate                         |
| NUMBEROFDEPENDENTS             | cdm\_numberofdependents                             |
| NATIVELANGUAGEID               | cdm\_nativelanguageidid.cdm\_name                    |
| NATIONALITYCOUNTRYREGION       | cdm\_nationalitycountryregion                       |
| PERSONBIRTHCOUNTRYREGION       | cdm\_birthcountryregion                             |
| FATHERBIRTHCOUNTRYREGION       | cdm\_fatherbirthcountryregion                       |
| MOTHERBIRTHCOUNTRYREGION       | cdm\_motherbirthcountryregion                       |
| CITIZENSHIPCOUNTRYREGION       | cdm\_citizenshipcountryregion                       |
| VETERANSTATUSID                | cdm\_veteranstatusid.cdm\_name                       |

### <a name="worker-postal-addresses-dual-write-to-worker-address"></a>Adresses postales des collaborateurs en double écriture à Adresse postale du collaborateur

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| NUMÉRO PERSONNEL                | cdm\_workerid.cdm\_workernumber                      |
| ADDRESSLOCATIONID              | cdm\_addressnumber                                  |
| ADDRESSLOCATIONROLES           | cdm\_addresstype                                    |
| EFFECTIF                      | cdm\_effectivedate                                  |
| EXPIRATION                     | cdm\_expirationdate                                 |
| ADDRESSSTREET                  | cdm\_street                                         |
| ADDRESSSTREETNUMBER            | cdm\_streetnumber                                   |
| ADDRESSCITY                    | cdm\_city                                           |
| ADDRESSCOUNTRYREGIONISOCODE    | cdm\_countryregion                                  |
| ADDRESSSTATE                   | cdm\_stateorprovince                                |
| ADDRESSCOUNTYID                | cdm\_county                                         |
| ADDRESSDESCRIPTION             | cdm\_description                                    |
| ADDRESSLATITUDE                | cdm\_latitude                                       |
| ADDRESSLONGITUDE               | cdm\_longitude                                      |
| ADDRESSZIPCODE                 | cdm\_postalcode                                     |
| ADDRESSPOSTBOX                 | cdm\_postofficebox                                  |
| ESTPRINCIPAL                      | cdm\_ispreferred                                    |

### <a name="working-time-to-work-calendar-time-interval"></a>Temps de travail en intervalle de temps pour le calendrier de travail

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ENDTIME                        | cdm\_endtime                                        |
| STARTTIME                      | cdm\_starttime                                      |
| WORKCALENDARDATE               | cdm\_workcalendardayid.cdm\_calendardate             |
| WORKCALENDARID                 | cdm\_workcalendarid.cdm\_name                        |
| WORKCALENDARID                 | cdm\_workcalendardayid.cdm\_workcalendarid.cdm\_name  |

### <a name="working-times-to-work-calendar-day"></a>Temps de travail en jour calendaire ouvert

| Entité financière                 | Table Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALENDARDATE                   | cdm\_calendardate                                   |
| WORKCALENDARID                 | cdm\_workcalendarid.cdm\_name                        |
| WORKINGDAYDEFINITION           | cdm\_status                                         |

## <a name="integration-considerations"></a>Considérations sur l’intégration

- Toutes les modifications apportées aux données dans l’un ou l’autre système seront soumises à la validation de l’autre système. En cas d’échec, les données ne seront écrites dans aucun des deux systèmes. 
- Toutes les écritures sont soumises à la valeur par défaut des données (si une logique personnalisée se produit dans Finance).
- L’application d’intégration à double écriture utilise des clés d’intégration pour mapper entre les deux systèmes. Parfois, il est difficile de choisir la bonne clé d’intégration, surtout si plusieurs clés d’intégration répondent aux besoins. Pour vous aider dans ce choix, le tableau suivant répertorie les clés d’intégration suggérées pour vos mappages.

| Table Dataverse                          | Clés d’intégration |
|------------------------------------------|------------------|
| Décaissements du compte en banque                | cdm\_bankaccountid.cdm\_accountidentification, cdm\_bankaccountid.cdm\_workerid.cdm\_workernumber, cdm\_companyid.cdm\_companycode |
| Fréquence de calcul des avantages            | cdm\_name |
| Fréquence de calcul des avantages de la période de rémunération | cdm\_payperiodid.cdm\_periodstartdate, cdm\_payperiodid.cdm\_paycycleid.cdm\_name, cdm\_benefitcalculationfrequencyid.cdm\_name |
| Taux de calcul des avantages                 | cdm\_name |
| Détails du taux de calcul des avantages          | cdm\_workerdeduction, cdm\_effective, cdm\_calculationrateid.cdm\_name |
| Option d’avantage                           | cdm\_name |
| Type d’avantage                             | cdm\_name |
| Calendrier pour le processus d’entreprise                | cdm\_name |
| Affectation du groupe de processus d’entreprise        | cdm\_name |
| En-tête de processus d’entreprise                  | cdm\_processid |
| Groupe de tâches de la bibliothèque de processus d’entreprise      | cdm\_processtype, cdm\_name |
| Phase du processus d’entreprise                   | cdm\_name, cdm\_businessprocesstype, cdm\_companyid.cdm\_companycode |
| Tâche de processus d’entreprise                    | cdm\_taskid |
| Unité commerciale                            | |
| En-tête de modèle de liste de contrôle                | cdm\_businessprocesstype, cdm\_name, cdm\_genericsubtype |
| Tâche du modèle de liste de contrôle                  | cdm\_taskid |
| Société                                  | cdm\_companycode |
| Régime fixe de rémunération                  | cdm\_name, cdm\_company.cdm\_companycode |
| Grille de rémunération                        | cdm\_name, cdm\_companyid.cdm\_companycode |
| Niveau de rémunération                       | cdm\_name |
| Fréquence de paiement de la rémunération               | cdm\_name, cdm\_companyid.cdm\_companycode |
| Paramétrage des points de référence de rémunération       | cdm\_name, cdm\_companyid.cdm\_companycode |
| Ligne de paramétrage des points de référence de rémunération  | cdm\_name, cdm\_referencepointsetupid.cdm\_name, cdm\_referencepointsetupid.cdm\_companyid.cdm\_companycode |
| Région de rémunération                      | cdm\_name |
| Structure des rémunérations                   | cdm\_compensationlevelid.cdm\_nom, cdm\_referencepointid.cdm\_nom, cdm\_referencepointid. cdm\_referencepointsetupid.cdm\_name, cdm\_referencepointid.cdm\_referencepointsetupid.cdm\_companyid. cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_compensationgridid.cdm\_name, cdm\_compensationgridid.cdm\_companyid.cdm\_companycode |
| Régime de rémunération variable               | cdm\_name, cdm\_companyid.cdm\_companycode |
| Niveau du régime de rémunération variable         | cdm\_companyid.cdm\_companycode, cdm\_compensationvariableplanid.cdm\_name, cdm\_compensationvariableplanid. cdm\_companyid.cdm\_companycode, cdm\_compensationlevelid.cdm\_name |
| Type du régime rémunération variable          | cdm\_name, cdm\_companyid.cdm\_companycode |
| Devise                                 | isocurrencycode |
| Département                               | cdm\_departmentnumber |
| Emploi                               | cdm\_employmentstartdate, cdm\_workerid.cdm\_workernumber, cdm\_companyid.cdm\_companycode |
| Origine ethnique                            | cdm\_name |
| Événement de rémunération fixe                 | cdm\_name, cdm\_companyid.cdm\_companycode |
| Poste                                      | cdm\_name |
| Fonction de tâche                             | cdm\_name |
| Poste                             | cdm\_jobpositionnumber |
| Dimension du poste                   | cdm\_jobpositionid.cdm\_jobpositionnumber, cdm\_companyid.cdm\_companycode |
| Type de poste                                 | cdm\_name |
| Langue                                 | cdm\_name |
| Transaction bancaire de congé                   | cdm\_transactiondate, cdm\_transactiontype, cdm\_transactionnumber, cdm\_leavetypeid.cdm\_type, cdm\_leavetypeid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_workerid.cdm\_workernumber |
| Inscription à un congé                         | cdm\_startdate, cdm\_leaveplanid.cdm\_name, cdm\_leaveplanid.cdm\_companyid. cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_workerid.cdm\_workernumber |
| Plan de congé                               | cdm\_name, cdm\_companyid.cdm\_companycode |
| Demande de congé                            | cdm\_leaverequestnumber, cdm\_companyid.cdm\_companycode |
| Détails de la demande de congés                     | cdm\_leavedate, cdm\_leavetypeid.cdm\_type, cdm\_leavetypeid.cdm\_companyid. cdm\_codeentreprise, cdm\_leaverequestid.cdm\_leaverequestnumber, cdm\_leaverequestid.cdm\_identreprise. cdm\_codeentreprise |
| Type de congé                               | cdm\_type, cdm\_companyid.cdm\_companycode |
| Code motif du type de congé                   | cdm\_reasoncodeid.cdm\_name, cdm\_typeid.cdm\_type, cdm\_typeid. cdm\_companyid.cdm\_companycode |
| En-tête de processus d’intégration                   | cdm\_processheaderid.cdm\_processid |
| Organisation                             | |
| Cycle de paie                                | cdm\_name |
| Période de rémunération                               | cdm\_periodstartdate, cdm\_paycycleid.cdm\_name, cdm\_periodenddate |
| Code de rémunération des salaires                     | cdm\_name |
| Détails du poste de paie                  | cdm\_validfrom, cdm\_validto, cdm\_position.cdm\_jobpositionnumber |
| Agence émettrice de l’identification de la personne     | cdm\_name |
| Type de poste                            | cdm\_name |
| Affectation du collaborateur au poste               | cdm\_validfrom, cdm\_jobpositionid.cdm\_jobpositionnumber |
| Code motif                              | cdm\_name |
| Type de qualification                               | cdm\_name |
| Zone fiscale                               | cdm\_stateorprovince, cdm\_name, cdm\_countryorregion, cdm\_county, cdm\_city |
| Équipe                                     | azureactivedirectoryobjectid, membershiptype |
| Titre                                    | cdm\_name |
| User                                     | azureactivedirectoryobjectid |
| Règle d’acquisition                             | cdm\_name, cdm\_companyid.cdm\_companycode |
| Statut de vétéran                           | cdm\_name |
| Calendrier de travail                            | cdm\_name, cdm\_companyid.cdm\_companycode |
| Jours de calendrier de travail                        | cdm\_calendardate, cdm\_companyid.cdm\_companycode, cdm\_workcalendarid.cdm\_name, cdm\_workcalendarid.cdm\_companyid.cdm\_companycode |
| Inscription dans le calendrier de travail                 | cdm\_employmentid.cdm\_employmentstartdate, cdm\_employmentid.cdm\_workerid.cdm\_workernumber, cdm\_employmentid.cdm\_companyid.cdm\_companycode |
| Congé du calendrier de travail                    | cdm\_name |
| Ligne de congé du calendrier de travail               | cdm\_holidaydate, cdm\_workcalendarholidayid.cdm\_name |
| Intervalle de temps du calendrier de travail              | cdm\_starttime, cdm\_workcalendardayid.cdm\_calendardate, cdm\_workcalendardayid.cdm\_companyid.cdm\_companycode, cdm\_workcalendardayid.cdm\_workcalendarid.cdm\_name, cdm\_workcalendardayid.cdm\_workcalendarid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_workcalendarid.cdm\_name, cdm\_workcalendarid.cdm\_companyid.cdm\_companycode |
| Travailleur                                   | cdm\_workernumber |
| Adresse du collaborateur                           | cdm\_addressnumber, cdm\_addresstype, cdm\_workerid.cdm\_workernumber |
| Compte bancaire du collaborateur                      | cdm\_accountidentification, cdm\_workerid.cdm\_workernumber |
| Rémunération fixe du collaborateur                | cdm\_linenumber, cdm\_effectivedate, cdm\_companyid.cdm\_companycode, cdm\_positionid.cdm\_jobpositionnumber, cdm\_workerid.cdm\_workernumber, cdm\_eventid.cdm\_name, cdm\_eventid.cdm\_companyid.cdm\_companycode, cdm\_planid.cdm\_name, cdm\_planid.cdm\_company.cdm\_companycode |
| Numéro d’identification personnel du collaborateur      | cdm\_identificationnumber, cdm\_workerid.cdm\_workernumber, cdm\_identificationtypeid.cdm\_name |
| Type d’identification personnel du collaborateur        | cdm\_name |
| Détails personnels du collaborateur                   | cdm\_workerid.cdm\_workernumber |
