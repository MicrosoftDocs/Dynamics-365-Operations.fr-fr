---
title: Configuration de l'intégration avec Finance
description: Cet article décrit les fonctionnalités disponibles pour l'intégration à partir de Dynamics 365 Human Resources et Dynamics 365 Finance.
author: andreabichsel
manager: AnnBe
ms.date: 03/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3b4d6369ab567879e23e1f132265aaff45c8ce47
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527911"
---
# <a name="configure-integration-with-finance"></a>Configurer l'intégration avec Finance

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Pour intégrer Dynamics 365 Human Resources avec Dynamics 365 Finance, vous pouvez utiliser le modèle Human Resources à Finance dans [Intégrateur de données](https://docs.microsoft.com/powerapps/administrator/data-integrator). Le modèle Human Resources à Finance active le flux de données pour les emplois, les postes et les collaborateurs. Le modèle permet aux données de passer de Human Resources à Finance, mais ne permet pas aux données de passer de Finance à Human Resources.

![Flux d'intégration de Human Resources à Finance](./media/hr-admin-integration-finance-flow.png)

La solution Human Resources à Finance fournit les types de synchronisation de données suivants :

- Mettre à jour les tâches dans Human Resources et les synchroniser depuis Human Resources vers Finance.
- Mettre à jour les postes et les affectations de poste dans Human Resources et les synchroniser depuis Human Resources vers Finance.
- Mettre à jour les emplois dans Human Resources et les synchroniser depuis Human Resources vers Finance.
- Mettre à jour les collaborateurs et les adresses des collaborateurs dans Human Resources et les synchroniser depuis Human Resources vers Finance.

## <a name="system-requirements-for-human-resources"></a>Configuration requise pour Human Resources

La solution d'intégration nécessite les versions suivantes de Human Resources et de Finance : 

- Dynamics 365 Human Resources sur Common Data Service
- Dynamics 365 Finance version 7.2 et versions ultérieures

## <a name="template-and-tasks"></a>Modèle et tâches

Pour accéder au modèle Human Resources à Finance.

1. Ouvrez [Centre d'administration Power Apps](https://admin.powerapps.com/). 

2. Sélectionnez **Projets**, puis sélectionnez **Nouveau projet** dans l'angle supérieur droit. Créez un projet pour chaque entité juridique que vous souhaitez intégrer dans Finance.

3. Sélectionnez **Human Resources (Human Resources Common Data Service vers Finance)** pour synchroniser les enregistrements de Human Resources vers Finance.

Le modèle utilise les tâches sous-jacentes suivantes pour synchroniser les enregistrements de Human Resources vers Finance :

- **Fonctions de tâche à Fonction de tâche de compensation**
- **Départements à Unité opérationnelle**
- **Types de tâche vers Type de tâche de compensation**
- **Tâches à Tâches**
- **Tâches à Détails de tâche**
- **Types de poste à Type de poste**
- **Postes de mission à Poste de base**
- **Postes de mission à Détails du poste**
- **Postes de mission à Durées du poste**
- **Postes de mission à Hiérarchies du poste**
- **Collaborateurs à Collaborateurs**
- **Emplois à Emploi**
- **Emplois à Détails d'emploi**
- **Affectation du collaborateur au poste à Affectations des collaborateurs aux postes**
- **Adresses des collaborateurs à Adresse postale du collaborateur V2**

## <a name="template-mappings"></a>Mises en correspondance des modèles

Dans les tableaux de mappage de modèles suivants, le nom de la tâche contient les entités utilisées dans chaque application. La source (Human Resources) est à gauche et la destination (Finance) est à droite.

### <a name="job-functions-to-compensation-job-function"></a>Fonctions de tâche à Fonction de tâche de compensation

| Entité Common Data Service (source) | Entité Finance (destination) |
|-------------------------------------|---------------------------------------------|
| cdm_name (nom de fonction cdm_Job)  | JOBFUNCTIONID (JOBFUNCTIONID)            |
| cdm_description (cdm_description) | DESCRIPTION (DESCRIPTION)                 |

### <a name="departments-to-operating-unit"></a>Départements à Unité opérationnelle

| Entité Common Data Service (source)           | Entité Finance (destination) |
|-----------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                           | NAME (NAME)                                 |
| cdm_departmentnumber (cdm_departmentnumber) | OPERATINGUNITNUMBER (OPERATINGUNITNUMBER) |
|                                               | OPERATINGUNITTYPE (OPERATINGUNITTYPE)     |
| cdm_description (cdm_description)           | NAMEALIAS (NAMEALIAS)                     |

### <a name="job-types-to-compensation-job-type"></a>Types de tâche vers Type de tâche de compensation

| Entité Common Data Service (source)   | Entité Finance (destination) |
|---------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                   | JOBTYPEID (JOBTYPEID)                     |
| cdm_description (cdm_description)   | DESCRIPTION (DESCRIPTION)                 |
| cdm_exemptstatus (cdm_exemptstatus) | EXEMPTSTATUS (EXEMPTSTATUS)               |

### <a name="jobs-to-jobs"></a>Tâches à Tâches

| Entité Common Data Service (source)                           | Entité Finance (destination)           |
|---------------------------------------------------------------|-------------------------------------------------------|
| cdm_name (cdm_name)                                           | JOBID (JOBID)                                         |
| cdm_maximumnumberofpositions (cdm_maximumnumberofpositions) | MAXIMUMNUMBEROFPOSITIONS (MAXIMUMNUMBEROFPOSITIONS) |
| cdm_allowedunlimitedpositions (cdm_allowunlimitedpositions) | ALLOWUNLIMITEDPOSITIONS (ALLOWUNLIMITEDPOSITIONS)   |
| cdm_description (cdm_description)                           | DESCRIPTION (DESCRIPTION)                           |
| cdm_jobdescription (cdm_jobdescription)                     | JOBDESCRIPTION (JOBDESCRIPTIONS)                    |

### <a name="jobs-to-job-detail"></a>Tâches à Détails de tâche

| Entité Common Data Service (source)                             | Entité Finance (destination) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                                             | JOBID (JOBID)                               |
| cdm_jobtypeid.cdm_name (type de tâche (nom du type de tâche))             | JOBTYPEID (JOBTYPEID)                     |
| cdm_jobfunctionid.cdm_name (fonction de tâche (nom de la fonction de tâche)) | FUNCTIONID (FUCNTIONID)                   |
| cdm_validfrom (valide à partir de)                                    | VALIDFROM (VALIDFROM)                     |
| cdm_validto (valide jusqu'à)                                        | VALIDTO (VALIDTO)                           |
| cdm_defaultfulltimeequivalent (équivalent plein temps par défaut)   | FULLTIMEEQUIVALENT (FULLTIMEEQUIVALENT)   |

### <a name="position-types-to-position-type"></a>Types de poste à Type de poste

| Entité Common Data Service (source)       | Entité Finance (destination) |
|-------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                       | POSITIONTYPEID (POSITIONTYPEID)           |
| cdm_description (cdm_description)       | DESCRIPTION (DESCRIPTION)                 |
| cdm_classification (cdm_classification) | CLASSIFICATION (CLASSIFICATION)           |

### <a name="job-positions-to-base-position"></a>Postes de mission à Poste de base

| Entité Common Data Service (source)           | Entité Finance (destination) |
|-----------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber (numéro de poste) | POSITIONID (POSITIONID)                      |

### <a name="job-positions-to-position-details"></a>Postes de mission à Détails du poste

| Entité Common Data Service (source)              | Entité Finance (destination)       |
|--------------------------------------------------------------------------|---------------------------------------------------|
| cdm_jobpositionnumber (numéro de poste)                            | POSITIONID (POSITIONID)                             |
| cdm_jobid.cdm_name (Tâche (Nom))                                        | JOBID (JOBID)                                    |
| cdm_description (cdm_description)                                        | DESCRIPTION (DESCRIPTION)                       |
| cdm_departmentid.cdm_departmentnumber (Départment (Numéro de département)) | DEPARTMENTNUMBER (DEPARTMENTNUMBER)             |
| cdm_positiontypeid.cdm_name (type de poste (nom))                     | POSITIONTYPEID (POSITIONTYPEID)                 |
| cdm_avaialableforassignment (disponible pour affectation)                 | AVAILABLEFORASSIGNMENT (AVAILABLEFORASSIGNMENT) |
| cdm_validfrom (valide à partir de)                                            | VALIDFROM (VALIDFROM)                           |
| cdm_validto (valide jusqu'à)                                                 | VALIDTO (VALIDTO)                               |
| cdm_fulltimeequivalent (équivalent temps plein)                           | FULLTIMEEQUIVALENT (FULLTIMEEQUIVALENT)         |

### <a name="job-positions-to-position-durations"></a>Postes de mission à Durées du poste

| Entité Common Data Service (source)             | Entité Finance (destination) |
|-------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber (numéro de poste)   | POSITIONID (POSITIONID)                      |
| Activation calculée (activation calculée) | VALIDFROM (VALIDFROM)                        |
| Retraite calculée (retraite calculée) | VALIDTO (VALIDTO)                         |

### <a name="job-positions-to-position-hierarchies"></a>Postes de mission à Hiérarchies du poste

| Entité Common Data Service (source)        | Entité Finance (destination) |
|-----------------------------------------------------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber (numéro de poste)                                                 | POSITIONID(POSITIONID)                      |
| cdm_parentjobpositionid.cdmjobpositionnumber (cdm_parentjobpositionid.cdmjobpositionnumber) | PARENTPOSITIONID (PARENTPOSITIONID)         |
| cdm_validfrom (valide à partir de)                                                                  | VALIDFROM (VALIDFROM)                     |
| cdm_validto (valide jusqu'à)                                                                      | VALIDTO (VALIDTO)                           |
| HIERARCHYTYPENAME (HIERARCHYTYPENAME)                                                       | HIERARCHYTYPENAME (HIERARCHYTYPENAME)     |


### <a name="workers-to-worker"></a>Collaborateurs à Collaborateurs
| Entité Common Data Service (source)           | Entité Finance (destination)       |
|-----------------------------------------------|---------------------------------------------------|
| cdm_birthdate (cdm_birthdate)               | BIRTHDATE (BIRTHDATE)                           |
| cdm_gender (cdm_gender)                     | GENDER (GENDER)                                   |
| cdm_primaryaddress (cdm_primaryaddress)     | PRIMARYCONTACTEMAIL (PRIMARYCONTACTEMAIL)      |
| cdm_primarytelephone (cdm_primarytelephone) | PRIMARYCONTACTPHONE (PRIMARYCONTACTPHONE)       |
| cdm_facebookidentity (cdm_facebookidentity) | PRIMARYCONTACTFACEBOOK (PRIMARYCONTACTFACEBOOK) |
| cdm_twitteridentity (cdm_twitteridentity)   | PRIMARYCONTACTTWITTER (PRIMARYCONTACTTWITTER)   |
| cdm_linkedinIdentity (cdm_linkedinIdentity) | PRIMARYCONTACTLINKEDIN (PRIMARYCONTACTLINKEDIN) |
| cdm_websiteurl (cdm_websiteurl)             | PRIMARYCONTACTURL (PRIMARYCONTACTURL)           |
| cdm_firstname (cdm_firstname)               | FIRSTNAME (FIRSTNAME)                           |
| cdm_middlename (cdm_middlename)             | MIDDLENAME (MIDDLENAME)                         |
| cdm_lastname (cdm_lastname)                 | LASTNAME (LASTNAME)                               |
| cdm_workernumber (cdm_workernumber)         | PERSONNELNUMBER (PERSONNELNUMBER)               |
| cdm_type (cdm_type)                           | WORKERTYPE (WORKERTYPE)                         |
| cdm_state (cdm_state)                       | WORKSTATUS (WORKERSTATUS)                       |

### <a name="employments-to-employment"></a>Emplois à Emploi

| Entité Common Data Service (source)                             | Entité Finance (destination) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_employmentstartdate (cdm_employmentstartdate)             | EMPLOYMENTSTARTDATE (EMPLOYMENTSTARTDATE) |
| cdm_employmentenddate (cdm_employmentenddate)                 | EMPLOYMENTENDDATE (EMPLOYMENTENDDATE)     |
| cdm_workertype (cdm_workertype)                               | WORKERTYPE (WORKERTYPE)                   |
| cdm_workerid.cdm_workernumber (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER (PERSONNELNUMBER)         |
| cdm_companyid.cdm_companycode (cdm_companyid.cdm_companycode) | LEGALENTITYID (LEGALENTITYID)             |

### <a name="employments-to-employment-detail"></a>Emplois à Détails d'emploi

| Entité Common Data Service (source)                             | Entité Finance (destination)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_employmentstartdate (cdm_employmentstartdate)             | EMPLOYMENTSTARTDATE (EMPLOYMENTSTARTDATE)   |
| cdm_employmentenddate (cdm_employmentenddate)                 | EMPLOYMENTENDDATE (EMPLOYMENTENDDATE)       |
| cdm_validfrom (valide à partir de)                                    | VALIDFROM (VALIDFROM)                       |
| cdm_validto (valide jusqu'à)                                        | VALIDTO (VALIDTO)                             |
| cdm_workerstartdate (cdm_workerstartdate)                     | WORKERSTARTDATE (WORKERSTARTDATE)           |
| cdm_lastdateworked (cdm_lastdateworked)                       | LASTDATEWORKED (LASTDATEWORKED)             |
| cdm_transitiondate (cdm_transitiondate)                       | TRANSITIONDATE (TRANSITIONDATE)             |
| cdm_employerunitofnotice (cdm_employerunitofnotice)           | EMPLOYERUNITOFNOTICE (EMPLOYERUNITOFNOTICE) |
| cdm_workerunitofnotice (cdm_workerunitofnotice)               | WORKERUNITOFNOTICE (WORKERUNITOFNOTICE)     |
| cdm_workerid.cdm_workernumber (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER (PERSONNELNUMBER)           |
| cdm_companyid.cdm_companycode (cdm_companyid.cdm_companycode) | LEGALENTITYID (LEGALENTITYID)               |
| cdm_employernoticeamount (cdm_employernoticeamount)           | EMPLOYERNOTICEAMOUNT (EMPLOYERNOTICEAMOUNT) |
| cdm_workernoticeamount (cdm_workernoticeamount )              | WORKERNOTICEAMOUNT (WORKERNOTICEAMOUNT)     |

### <a name="position-worker-assignment-to-position-worker-assignments"></a>Affectation du collaborateur au poste à Affectations des collaborateurs aux postes

| Entité Common Data Service (source)                             | Entité Finance (destination)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER (PERSONNELNUMBER)           |
| cdm_jobpositionnumber (numéro de poste)                   | POSITIONID(POSITIONID)                        |
| cdm_validfrom (valide à partir de)                                    | VALIDFROM (VALIDFROM)                       |
| cdm_validto (valide jusqu'à)                                        | VALIDTO (VALIDTO)                             |

### <a name="worker-addresses-to-worker-postal-address-v2"></a>Adresses des collaborateurs à Adresse postale du collaborateur V2

| Entité Common Data Service (source)                             | Entité Finance (destination)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER (PERSONNELNUMBER)           |
| cdm_addresstype (cdm_addresstype)                             | ADDRESSLOCATIONROLES (ADDRESSLOCATIONROLES) |
| cdm_line1 (cdm_line1)                                         | ADDRESSSTREET (ADDRESSSTREET)               |
| cdm_city (cdm_city)                                             | ADDRESSCITY (ADDRESSCITY)                   |
| cdm_stateorprovince (cdm_stateorprovince)                     | ADDRESSSTATE (ADDRESSSTATE)                 |
| cdm_postalcode (cdm_postalcode)                               | ADDRESSZIPCODE(ADDRESSZIPCODE)                |
| cdm_countryregion (cdm_countryregion)                         | ADDRESSCOUNTRYREGION(ADDRESSCOUNTRYREGION)    |
| cdm_addressnumber (cdm_addressnumber)                         | ADDRESSLOCATIONID(ADDRESSLOCATIONID)          |
| cdm_ispreferred (cdm_ispreferred)                             | ISPRIMARY (ISPRIMARY)                       |
| cdm_county (cdm_county)                                       | ADDRESSCOUNTYID(ADDRESSCOUNTYID)              |
| cdm_addresstype (cdm_addresstype)                             | ADDRESSDESCRIPTION(ADDRESSDESCRIPTION)        |

## <a name="integration-considerations"></a>Considérations sur l'intégration

L'intégration des données des Human Resources à Finance tente de faire correspondre les enregistrements en fonction de l'ID. Si les enregistrements correspondent, l'intégrateur de données remplace les données dans Finance avec les valeurs dans Human Resources. Cependant, un problème peut se produire si, logiquement, ces enregistrements sont différents et que le même ID a été généré dans Human Resources ou Finance en fonction de la séquence de numéros respective.

Les domaines dans lesquels cela peut se produire sont **Collaborateur**, qui utilise le **Numéro personnel** pour établir la correspondance, et **Postes**. Les tâches n'utilisent pas de séquences de nombres. Par conséquent, si le même ID de tâche est présent à la fois dans Human Resources et Finance, les informations des Human Resources remplaceront les informations Dynamics 365 Finance. 

Pour éviter les problèmes d'ID en double, vous pouvez soit ajouter un préfixe à la [souche de numéros](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/number-sequence-overview?toc=/dynamics365/unified-operations/talent/toc.json) ou définir un numéro de début sur la souche de numéros qui dépasse la plage de l'autre système. 

L'ID d'emplacement utilisé pour l'adresse du collaborateur ne fait pas partie d'une souche de numéros. Lors de l'intégration d'une adresse de collaborateur des Human Resources à Finance, si l'adresse du collaborateur existe déjà dans Finance, un enregistrement d'adresse en double peut être créé. 

L'illustration suivante présente un exemple de modèle de mise en correspondance dans l'Intégrateur de données. 

![Mise en correspondance des modèles](./media/IntegrationMapping.png)