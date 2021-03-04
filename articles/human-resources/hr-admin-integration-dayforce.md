---
title: Configuration de l'intégration avec Dayforce
description: L'intégration entre Microsoft Dynamics 365 Human Resources et Ceridian Dayforce repose sur plusieurs étapes de configuration décrites dans cet article. Vous devez configurer l'intégration dans Human Resources et Dayforce avant de pouvoir traiter un cycle de paie.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: PersonnelIntegrationConfiguration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c66ec772ea66732e042f50081f04a6569852f211
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418425"
---
# <a name="configure-integration-with-dayforce"></a>Configuration de l'intégration avec Dayforce

L'intégration entre Microsoft Dynamics 365 Human Resources et Ceridian Dayforce repose sur plusieurs étapes de configuration décrites dans cet article. Vous devez configurer l'intégration dans Human Resources et Dayforce avant de pouvoir traiter un cycle de paie.

Lorsque vous utilisez un service comme Dayforce pour compléter des cycles de paie, vous devez activer l'intégration dans Human Resources. L'intégration nécessite des données spécifiques de Human Resources. Par conséquent, vous devez vérifier que les données mises en correspondance avec Dayforce sont configurées dans Human Resources d'une manière prenant en charge l'intégration. L'intégration utilise les larges catégories de données suivantes :

- Données de ressources humaines
- Données de rémunération
- Données salariales, telles que des cycles de paie, des périodes de rémunération, et des codes de rémunération
- Données sur les collaborateurs

Cet article décrit la procédure à suivre pour activer l'intégration. Elle décrit également les types de données et les détails de configuration que l'intégration nécessite.

## <a name="enable-the-integration"></a>Activer l'intégration

Dans Human Resources, vous devez activer l'intégration et entrer des informations de configuration pour vous connecter Dayforce. Si vous souhaitez que l'écriture comptable produite soit importée dans Microsoft Dynamics 365 Finance, vous devez également configurer un compte de stockage Microsoft Azure et entrer la chaîne de connexion de stockage Azure dans Finance.

Pour l'activer l'intégration dans Human Resources, procédez comme suit.

1. Sur la page **Administration du système**, sélectionnez **Configuration de l'intégration**.
2. Entrez le point de terminaison FTP (File Transfer Protocol) sécurisé et le chemin d'accès de dossier FTP sécurisé.
3. Entrez le nom d'utilisateur et le mot de passe de l'utilisateur qui accèdera au point de terminaison FTP et au chemin d'accès du dossier sécurisés.
4. Testez la connexion, au besoin, puis définissez l'option **Activation de l'intégration de la paie** sur **Oui**.

Lorsque l'intégration est activée, le package et les fichiers d'exportation de données sont créés, et la fréquence est définie. Vous pouvez modifier la fréquence selon vos besoins.

Pour plus d'informations sur les comptes de stockage Azure et les chaînes de connexion de stockage Azure, consultez les articles Azure suivants :

- [À propos des comptes de stockage Azure](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [Configurer les chaînes de connexion de stockage Azure](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a>Détails techniques lorsque l'intégration de la paie est activée

Activer l'intégration de la paie a deux principaux effets :

- Un projet d'exportation de données nommé « Exportation de l'intégration de la paie » est créé. Ce projet contient les entités et les champs nécessaires pour l'intégration de la paie. Pour examiner le projet, accédez à **Administration système**, sélectionnez la vignette **Gestion des données**, puis ouvrez le projet à partir de la liste de projets.
- Ce traitement par lots exécute le projet d'exportation de données, chiffre le package de données obtenues, et transfère le fichier de package de données au point de terminaison SFTP configuré dans l'écran **Configuration de l'intégration**.

> [!NOTE]
> Le package de données transféré au point de terminaison SFTP est chiffré à l'aide d'une clé unique dans le module. Cette clé est dans un coffre Azure Key Vault qui n'est accessible que par Ceridian. Il est impossible de déchiffrer et examiner le contenu du package de données. Si vous devez examiner le contenu du package de données, vous devez exporter le projet de données « Exportation de l'intégration de la paie » manuellement, le télécharger, puis l'ouvrir. L'exportation manuelle n'appliquera pas de chiffrement ou de transfert au package.

## <a name="configure-your-data"></a>Configurer vos données 

Pour traiter les paies, vous devez configurer les données des ressources humaines dans Human Resources. Vous devez configurer les données organisationnelles, telles que les tâches et les postes, ainsi que les avantages et les informations de rémunération. Ces informations fournissent des informations sur l'emploi, le salaire et les déductions nécessaires pour générer le salaire de l'employé.

### <a name="human-resource-data"></a>Données des ressources humaines

#### <a name="benefits"></a>Avantages 

Les ressources humaines proposent des outils de paramétrage et de mise à jour des avantages, des déductions et des plans de compensation des collaborateurs qu'une organisation offre ou gère pour ses collaborateurs.

Lorsque vous créez des avantages, n'oubliez pas les données et les configurations suivantes utilisées dans Dayforce.

##### <a name="benefit-plans"></a>Plans d'avantages

- Plan (obligatoire)
- Type (obligatoire)
- Impact sur la paie (obligatoire)
- Recouvrer les arriérés
- Méthode de déduction
- Priorité de la déduction
- Période limite
- Montant limite

##### <a name="benefits"></a>Avantages

- Plan (obligatoire)
- Type (obligatoire)
- Option (obligatoire)
- ID avantage (obligatoire)
- Fréquence
- Base
- Montant ou taux
- Code de rémunération

##### <a name="supported-frequencies"></a>Fréquences prises en charge 

- Hebdomadairement
- Bimensuelle
- Bimensuel
- Mensuellement

##### <a name="supported-bases"></a>Bases pris en charge 

- Montant fixe
- Pourcentage des rémunérations
- Heures productives

Dayforce crée les déductions suivantes, selon l'impact sur la paie défini dans le plan d'avantages.

| Sélection dans Human Resources        | Résultat dans Dayforce                            |
|----------------------------|-----------------------------------------------|
| Aucune                       | Aucune retenue n'est créée.                      |
| Déduction uniquement             | Une retenue employé est créée.             |
| Contribution uniquement          | Une retenue employeur est créée.             |
| Déduction et contribution | Des retenues employé et employeur sont créées. |

Pour plus d'informations sur la définition et la gestion des programmes d'avantages, consultez les articles suivants :

- [Communiquer le programme d'avantages à un employé](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [Créer un avantage](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [Définir les règles d'admissibilité et les stratégies relatives aux avantages](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [Inscrire et annuler l'inscription des travailleurs à des avantages](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a>Rémunération 

La gestion des rémunérations est utilisée pour contrôler la rémunération de base et les primes. Le salaire de base fixe et les augmentations pour mérite d'un employé sont contrôlés via les régimes de rémunération fixe. Le paiement des primes (primes liées aux résultats, options d'achat d'actions et octrois d'actions), ainsi que les primes exceptionnelles, est contrôlé via les régimes de rémunération variable.

Dayforce utilise les informations de rémunération pour calculer le taux horaire ou annuel d'un employé. Des plans de rémunération fixe et des conversions de taux de salaire sont requis. Les employés doivent être associés à un plan de rémunération fixe.

Pour plus d'informations sur les plans de rémunération, voir les articles suivants :

- [Créer des régimes de rémunération fixe](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [Créer des régimes de rémunération variable](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [Développer les plans et la structure du salaire/de la rémunération](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [Traiter la rémunération](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [Définir le processus de rémunération et calculer les résultats](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [Inscrire un employé à un régime de rémunération fixe](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [Inscrire un employé à un régime de rémunération variable](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a>Postes 

Une tâche est un ensemble de tâches et de responsabilités attribuées à la personne affectée à la tâche. Pour plus d'informations, voir l'article suivant :

- [Paramétrage des composants d'une tâche](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [Définir les nouvelles tâches](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a>Postes

Un poste est une instance individuelle d'une tâche. Par exemple, le poste « Responsable des ventes (est) » est l'un des postes associés à la tâche « Responsable des ventes ». Un poste existe dans un département. Seul un collaborateur peut être associé à chaque poste.

Gardez à l'esprit les données et la configuration suivantes lorsque vous paramétrez des postes :

- Poste (obligatoire)
- Description (obligatoire)
- Tâche (obligatoire)
- Département (obligatoire)
- Type de poste (obligatoire)
- Équivalent temps plein
- Durée annuelle normale (obligatoire)
- Rémunéré par l'entité juridique (obligatoire)
- Cycle de paie (obligatoire)
- Dimension financière par défaut – Centre de coût (obligatoire)
- Affectation du collaborateur – Collaborateur, début de l'affectation, fin de l'affectation, code motif

Si plusieurs postes dans un même département sont associés à la même tâche, ils sont consolidés un seul poste dans Dayforce.

Pour plus d'informations, voir l'article suivant :

- [Organisation du personnel à l'aide des départements, tâches et postes](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [Paramétrer les postes](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a>Départements

Un département est une unité opérationnelle qui représente une catégorie ou un domaine fonctionnel d'une organisation. Un département est responsable d'un domaine spécifique de l'organisation, par exemple les ventes, la comptabilité ou les ressources humaines. Les départements vous permettent de générer des états sur les domaines fonctionnels. Les départements peuvent avoir la responsabilité des résultats.

Pour plus d'informations, voir l'article suivant :

- [Créer un département et l'associer à la hiérarchie des départements](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [Définir les nouveaux départements](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a>Cycles de paie et périodes de rémunération

Un cycle de paie détermine la fréquence d'exécution de la paie et les jours spécifiques où les collaborateurs sont payés. Par exemple, un cycle de paie peut être mensuel, et les employés peuvent être payés le dernier jour du mois. Sinon, un cycle de paie peut être hebdomadaire, et les employés peuvent être payés le mardi après la fin de la période de rémunération. Les cycles de paie sont affectés aux postes afin de contrôler à quel moment les collaborateurs à ces postes sont payés.

Après avoir créé des cycles de paie, vous pouvez générer des périodes de rémunération pour chaque cycle. Chaque période de rémunération comprend une date de paiement par défaut basée sur les informations que vous fournissez. Toutefois, vous pouvez modifier la date de paiement par défaut d'une période de rémunération pour permettre des exceptions, par exemple lorsque la date de paiement a lieu un jour férié.

Les informations suivantes sont utilisée dans Dayforce :

- Cycle de paie (obligatoire)
- Fréquence du cycle de paie (obligatoire)
- Date de début de la période (première période de rémunération obligatoire)
- Date de rémunération par défaut (première période de rémunération obligatoire)

Ces informations sont intégrées à Dayforce en tant que des groupes de paie, et sont séparées par pays ou par région pour chaque cycle de paie. Au moins une période de rémunération doit être générée avant l'intégration. Dayforce génère des calendriers de groupe de paie et des dates de rémunération, selon la date de début de la première période de rémunération et la date de rémunération par défaut paramétrées dans Human Resources.

#### <a name="earning-codes"></a>Codes de rémunérations

Les codes de rémunérations identifient de manière unique chaque type de revenus que les collaborateurs reçoivent. Les codes ont différents paramètres associés aux revenus, tels que des règles comptables, des lois fiscales, des conditions de génération d'états, et la capacité de montant brut.

Les informations suivantes sont utilisée dans Dayforce :

- Code de rémunération (obligatoire)
- Description
- Unité de mesure
- Productif

### <a name="worker-data"></a>Données sur les collaborateurs

Les enregistrements pour les différents types d'employés dont vous disposez sont importants pour vos systèmes de ressources humaines et de paie. Les informations que vous entrez peuvent servir à suivre les informations des collaborateurs et les informations personnelles.

Vous pouvez tenir à jour les informations suivantes pour les travailleurs :

- **Base** – Permet de tenir à jour les informations de base sur un collaborateur, telles que les informations de contact, les informations démographiques, les informations d'identification, les informations sur la famille, le statut de service militaire, les informations d'expatriation, et les contacts personnels et les personnes à prévenir en cas d'urgence.
- **Emploi** – Permet de tenir à jour les informations relatives à l'emploi des collaborateurs, telles que l'affiliation de la société ou de l'organisation, l'affectation de poste, les dates de début et de fin, l'éligibilité à un emploi, les conditions d'emploi, la retraite, les congés, et les informations de mutation.
- **Congé et absence** – Permet de tenir à jour les informations sur les absences des collaborateurs, telles que les calendriers de travail, les transactions d'absence et le paramétrage d'absence.
- **Rémunération et paie** – Permet de tenir à jour les informations sur les régimes de rémunération des collaborateurs et les informations de paie, telles que l'inscription à un régime, les primes, les performances, la commission, les informations fiscales, la retraite et les déductions de salaire.

Lorsque vous entrez des informations sur le collaborateur, n'oubliez pas les données et les configurations suivantes utilisées dans Dayforce.

#### <a name="general-information"></a>Informations générales

- Matricule (obligatoire)
- Prénom (obligatoire)
- Nom (obligatoire)
- Autres prénoms
- Date d'ancienneté
- Connu sous

#### <a name="personal-information"></a>Informations personnelles

- État civil (obligatoire)
- Date de naissance (obligatoire)
- Sexe (obligatoire)
- Personne handicapée
- Région/pays de nationalité (uniquement au Mexique)

#### <a name="address-information"></a>Informations d'adresse

- Adresse principale (obligatoire)
- Pays/région (obligatoire)
- Code postal (obligatoire)
- Numéro de la rue (obligatoire) (uniquement au Mexique)
- Info complémentaire sur le bâtiment (uniquement au Mexique)
- Ville (obligatoire)
- État (obligatoire)
- Pays (obligatoire)

#### <a name="contact-information"></a>Informations de contact 

- Contact principal (obligatoire)
- Numéro du contact (obligatoire)
- Poste

#### <a name="payroll-information-and-earning-codes"></a>Informations sur les salaires et codes de rémunération

Les employés peuvent bénéficier de revenus spécifiques à une fréquence de paiement donnée et avoir un mode de paiement préféré. Les champs suivants sont utilisés dans Dayforce pour garantir que ces préférences et paramètres soient utilisés.

##### <a name="earning-codes"></a>Codes de rémunérations

- Poste (obligatoire)
- Code de rémunération (obligatoire)
- Fréquence (obligatoire)
- Montant (obligatoire)

##### <a name="payroll-information"></a>Informations sur les salaires

- Mode de paiement
- Région économique (obligatoire)
- ID avantages employé
- Numéro d'ID national (obligatoire)
- Numéro de service militaire
- ID d'équipe (obligatoire)
- Numéro de taxe (obligatoire)
- ID syndicat (obligatoire)
- ID de la journée de travail (obligatoire)
- Numéro de permis de travail

> [!NOTE]
> Pour le mode de paiement, le Mexique prend en charge les **Espèces**, les **Chèques** (chèque physique de la société) et le **Paiement électronique**. Si aucun mode de paiement n'est spécifié, le **Chèque** est utilisé par défaut.

#### <a name="employment-details"></a>Détails de l'emploi

L'historique des détails de l'emploi est utilisé comme information clé pour en dériver le statut d'embauche, de fin du contrat, et de réembauche d'un employé dans Dayforce. Dayforce prend en charge un seul enregistrement d'emploi actif à la fois.

- Date de début de l'emploi (obligatoire)
- Date de fin de l'emploi
- Date de début
- Date de début de contrat ajustée
- Date de fin de contrat (obligatoire à la fin du contrat)
- Motif de la fin du contrat (obligatoire à la fin du contrat)

Les dates clés d'un employé sont dérivées à l'aide des informations suivantes.

| Ressources humaines                | Dayforce                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| Date d'embauche la plus récente | Début de l'emploi de l'enregistrement d'historique d'emploi avec contrat en cours                                 |
| Date de fin de contrat      | Date de fin de contrat de l'enregistrement d'historique d'emploi avec contrat en cours                                 |
| Date de début            | Date de début ajustée, date de début, ou début de l'emploi de l'enregistrement d'historique d'emploi inactif actuel |
| Date d'embauche d'origine    | Début d'emploi de l'enregistrement d'historique d'emploi le plus proche                                               |

#### <a name="compensation"></a>Rémunération

Un plan de rémunération fixe doit être associé au poste principal de chaque employé tout au long d'une période d'emploi. Cette période démarre à la date à laquelle l'employé a été embauché (ou à la date de début de l'emploi) et se poursuit jusqu'à la fin de contrat.

- Date d'effet (obligatoire)
- Date d'expiration
- Taux de salaire (obligatoire)
- Conversions de taux de salaire (obligatoire)
- Équivalent annuel (obligatoire)
- Équivalent horaire (obligatoire)

Si un employé horaire a plusieurs postes, la rémunération fixe du poste principal est importée dans Dayforce comme taux de base/salaire de niveau d'employé. Pour les postes non principaux, le taux horaire est enregistré au poste correspondant dans Dayforce.

Si un employé salarié occupe plusieurs postes, le taux horaire cumulé et le salaire annuel entre tous les postes actifs sont dérivés et utilisés comme taux de base/salaire au niveau de l'employé.

#### <a name="identification-numbers"></a>Numéros d'identifications

##### <a name="social-security-identifier"></a>Numéro de Sécurité sociale 

Chaque employé doit avoir un numéro principal. Cet numéro doit être de type d'identification **N° S.S.**. Dans Dayforce, il est automatiquement dérivé du numéro de Sécurité sociale de l'employé qui est obligatoire pour l'embaucher.

- Numéro principal (obligatoire)
- Type d'identification = « N° S.S. »
- Date d'émission
- Date d'expiration

Les employés peuvent déclarer plusieurs numéros d'identification de type d'identification **N° S.S.**. Toutefois, seul l'enregistrement marqué comme **Principal** est intégré à Dayforce, que le numéro soit active ou arrivé à expiration.

#### <a name="bank-accounts-and-disbursements"></a>Comptes en banque et décaissements

Des informations de compte bancaire valides doivent être entrées pour tous les employés qui choisissent d'être payés à l'aide de virements bancaires.

| Ressources humaines                         | Dayforce                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| Numéro de compte bancaire (obligatoire) |                                                                                                             |
| Code SWIFT (obligatoire)          | Le champ **ID banque** utilisé lors du traitement du salaire au Mexique.                                                             |
| Numéro d'agence (obligatoire)       |                                                                                                             |
| Type de compte bancaire (obligatoire)   | Le champ **Type de compte** utilisé lors du traitement du salaire au Mexique. Les valeurs prises en charge sont **Chèque** et **Paie**. |

> [!NOTE]
> Les employés qui choisissent d'être payés par des virements bancaires doivent fournir un lien vers un compte de solde qui se trouve sous une entité juridique avec son adresse principale au Mexique, et associée à un compte bancaire valide dans une banque mexicaine. Tous les autres comptes non-solde sont ignorés.

#### <a name="address-information"></a>Informations d'adresse

Chaque employé doit avoir un lieu principal. Dans Dayforce, ce lieu est utilisé pour déterminer la résidence principale de l'employé à des fins fiscales.

- Lieu principal (obligatoire)
- Pays/région (obligatoire)
- Code postal (obligatoire)
- Rue (obligatoire)
- Numéro de rue (obligatoire)
- Info complémentaire sur le bâtiment
- Ville (obligatoire)
- État (obligatoire)
- Pays (obligatoire)

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a>Configurer vos données pour générer un salaire aux États-Unis et au Canada

Si vous générez un salaire pour des employés aux États-Unis et au Canada, les éléments suivants doivent être configurés :

- Les départements sont obligatoires sur les postes.
- Les centres de coût doivent être définis comme des dimensions financières et doivent être le premier élément de la chaîne de dimension financière par défaut.

> [!NOTE] 
> Vous pouvez configurer Human Resources pour demander que les postes spécifient un service. Pour ce faire, accédez à **Postes partagés par les ressources humaines > Postes > Demander le service des postes**. Nous vous recommandons d'appliquer ce paramètre pour l'intégration.

### <a name="job-types"></a>Types de missions

Les types de tâches sont utilisés pour regrouper les tâches similaires en catégories. Les types de tâches sont nécessaires pour traiter la paie aux États-Unis et au Canada. Les exemples de types de tâches incluent le temps plein et le temps partiel, ou le salaire et le paiement à l'heure. Les types de tâches sont mis en correspondance dans Dayforce comme types de paies qui indiquent si un employé est payé à l'heure ou salarié.

Les types de tâches et les descriptions suivants sont obligatoires.

| Type de mission   | Description |
|------------|-------------|
| Horaire     | Horaire      |
| Salarié   | Salarié    |

### <a name="position-types"></a>Types de poste 

Vous utilisez les types de postes pour indiquer si le poste est à temps plein, à temps partiel, ou autre chose. Les types de postes sont mis en correspondance dans Dayforce comme classes de paiements qui indiquent si un employé est à temps plein ou à temps partiel.

Les types de postes et les descriptions suivants sont obligatoires.

| Type de poste   | Description        |
|-----------------|--------------------|
| Temps plein       | Employé à temps plein |
| Temps partiel       | Employé à temps partiel |

### <a name="reason-codes"></a>Codes motif

Les codes motif fournissent des informations sur le statut d'un employé. Les codes motif sont mis en correspondance avec Dayforce comme motifs du statut, indiquant le motif des modifications apportées au poste ou au statut d'emploi d'un employé.

Les codes motif et les descriptions suivants sont obligatoires.

| Code motif    | Description      | Scénarios applicables |
|----------------|------------------|----------------------|
| RESIGNATION    | Démission      | Mettre un terme au contrat du collaborateur     |
| TERMINATION    | Fin du contrat      | Mettre un terme au contrat du collaborateur     |
| RETIREMENT     | Retraite       | Mettre un terme au contrat du collaborateur     |
| OTHER          | Autres motifs    | Mettre un terme au contrat du collaborateur     |
| DEATH          | Décès            | Mettre un terme au contrat du collaborateur     |
| LEAVEOFABSENCE | Congé | Mettre un terme au contrat du collaborateur     |
| CONTRACTEND    | Fin du contrat  | Mettre un terme au contrat du collaborateur     |
| SALARYCHANGE   | Modification du salaire | Rémunération         |

### <a name="marital-status"></a>Situation de famille

Les valeurs de situation de famille sont mises en correspondance avec Dayforce et traduite, au besoin, dans les valeurs acceptées lors de l'intégration.

Le tableau suivant montre comment les valeurs de situation de famille sont mises en correspondance avec Dayforce.

| Ressources humaines                 | Dayforce             |
|------------------------|----------------------|
| Marié                | Marié              |
| Unique                 | Unique               |
| Veuf                | Veuf              |
| Divorcé               | Divorcé             |
| Partenariat enregistré | Partenariat local |
| None                   | None                 |
| Concubinage             | Concubinage           |

### <a name="gender"></a>Sexe

Le sexe est mis en correspondance avec Dayforce et traduit, au besoin, dans les valeurs acceptées lors de l'intégration.

Le tableau suivant montre comment le sexe est mis en correspondance avec Dayforce.

| Ressources humaines       | Dayforce        |
|--------------|-----------------|
| Masculin         | Masculin            |
| Féminin       | Féminin          |
| Non spécifique | *Non pris en charge* |

### <a name="earning-codes"></a>Codes de rémunérations

Les codes de rémunérations identifient de manière unique chaque type de revenus que les collaborateurs reçoivent. Les codes couvrent différents paramètres associés aux revenus, tels que des règles comptables, des lois fiscales, des conditions de génération d'états, et la capacité de montant brut. Si une fréquence non prise en charge est utilisée, la fréquence **Chaque paie** est utilisée par défaut pour le calcul.

#### <a name="supported-frequencies"></a>Fréquences prises en charge

- Tous
- EVERYPAY
- EACHPAYPERIOD
- EVRYOTHRPAYODD
- EVRYOTHRPAYEVN
- 1OFMTH
- LASTOFMTH
- 2OFMTH
- 3OFMTH
- 4OFMTH
- 5OFMTH
- 1N2OFMTH
- 3N4OFMTH
- 1N3OFMTH
- 1N4OFMTH
- 2N3OFMTH
- 2N4OFMTH
- 1N2N3OFMTH
- 1N2N4OFMTH
- 1N3N4OFMTH
- 2N3N4OFMTH
- 1N2N3N4OFMTH - 1N2N3N4OFMTH
- 2N3N4N5OFMth - 2N3N4N5OFMth
- 1OFQTR - 1OFQTR
- LASTOFQTR – LASTOFQTR
- LASTMTHOFQTR – LASTMTHOFQTR
- 1OFYEAR - 1OFYEAR
- LASTOFYEAR – LASTOFYEAR
- NOVNDECOFYEAR - NOVNDECOFYEAR

### <a name="addresses"></a>Adresses

L'identification d'un pays ou d'une région, d'un état, et des codes département (municipalité) spécifiques nécessite des formats spécifiques que les fournisseurs Dayforce et dans le pays/la région peuvent identifier. Bien que le format pour les villes soit flexible, chaque ville doit être associée à un état.

| Ressources humaines          | Dayforce              |
|-----------------|-----------------------|
| Pays/région  | Code pays          |
| Code postal | Code postal           |
| État           | Code région            |
| Ville            | Ville                  |
| Commune          | Département (municipalité) |
| Rue          | Ligne d'adresse 1        |

### <a name="tax-regions"></a>Zones fiscales

Les régions fiscales permettent de déterminer la taxe appropriée qui doit être appliquée lors de la génération des salaires. Les régions fiscales sont mises en correspondance avec Dayforce comme adresses de lieu. La région fiscale par défaut doit être associée au poste actif du collaborateur. 

- Région fiscale (obligatoire)
- Pays/région (obligatoire)
- État (obligatoire)
- Commune 
- Ville (obligatoire)

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a>Configurez vos données pour générer un salaire au Mexique

Si vous générez un salaire pour des employés au Mexique, les éléments suivants doivent être configurés :

- Les départements sont obligatoires sur les postes.
- Les centres de coût doivent être définis comme des dimensions financières et doivent être le premier élément de la chaîne de dimension financière par défaut.

### <a name="job-types"></a>Types de missions

Les types de tâches sont utilisés pour regrouper les tâches similaires en catégories. Les types de tâches sont nécessaires afin de traiter le salaire au Mexique. Les exemples de types de tâches incluent le temps plein et le temps partiel, ou le salaire et le paiement à l'heure. Les types de tâches sont mis en correspondance dans Dayforce comme types de paies qui indiquent si un employé est payé à l'heure ou salarié.

Les types de tâches et les descriptions suivants sont obligatoires.

| Type de mission   | Description |
|------------|-------------|
| Horaire     | Horaire MX   |
| Salarié   | Salarié MX |

### <a name="position-types"></a>Types de poste 

Vous utilisez les types de postes pour indiquer si le poste est à temps plein, à temps partiel, ou autre chose. Les types de postes sont mis en correspondance dans Dayforce comme classes de paiements qui indiquent si un employé est à temps plein ou à temps partiel.

Les types de postes et les descriptions suivants sont obligatoires.

| Type de poste   | Description        |
|-----------------|--------------------|
| Temps plein       | Employé à temps plein |
| Temps partiel       | Employé à temps partiel |

### <a name="reason-codes"></a>Codes motif

Les codes motif fournissent des informations sur le statut d'un employé. Les codes motif sont mis en correspondance avec Dayforce comme motifs du statut, indiquant le motif des modifications apportées au poste ou au statut d'emploi d'un employé.

Les codes motif et les descriptions suivants sont obligatoires.

| Code motif            | Description                    | Scénarios applicables |
|------------------------|--------------------------------|----------------------|
| DEPARTUREBEFOREPAYMENT | Départ avant le premier salaire | Mettre un terme au contrat du collaborateur     |
| RESIGNATION            | Démission                    | Mettre un terme au contrat du collaborateur     |
| PENSION                | Retraite                        | Mettre un terme au contrat du collaborateur     |
| TERMINATION            | Fin du contrat                    | Mettre un terme au contrat du collaborateur     |
| RETIREMENT             | Retraite                     | Mettre un terme au contrat du collaborateur     |
| ABSENTEE               | Absent                       | Mettre un terme au contrat du collaborateur     |
| OTHER                  | Autres motifs                  | Mettre un terme au contrat du collaborateur     |
| CLOSURE                | Fermeture de l'entreprise               | Mettre un terme au contrat du collaborateur     |
| DEATH                  | Décès                          | Mettre un terme au contrat du collaborateur     |
| LEAVEOFABSENCE         | Congé               | Mettre un terme au contrat du collaborateur     |
| CONTRACTEND            | Fin du contrat                | Mettre un terme au contrat du collaborateur     |
| SALARYCHANGE           | Modification du salaire               | Rémunération         |

### <a name="terms-of-employment"></a>Conditions d'emploi

Les conditions d'emploi sont utilisées pour créer des catégories de conditions d'emploi. Les conditions sont mises en correspondance avec Dayforce en tant que valeurs d'indicateur d'emploi.

Les conditions d'emploi et descriptions suivantes sont obligatoires.

| Conditions d'emploi   | Description |
|-----------------------|-------------|
| Régulier               | Régulier     |
| Direct                | Direct      |
| Stage            | Stage  |
| Permanent             | Permanent   |

### <a name="marital-status"></a>Situation de famille

Les valeurs de situation de famille sont mises en correspondance avec Dayforce et traduite, au besoin, dans les valeurs acceptées lors de l'intégration.

Le tableau suivant montre comment les valeurs de situation de famille sont mises en correspondance avec Dayforce.

| Ressources humaines                 | Dayforce                  |
|------------------------|---------------------------|
| Marié                | Marié                   |
| Unique                 | Unique                    |
| Veuf                | Veuf                   |
| Divorcé               | Divorcé                  |
| Partenariat enregistré | Partenariat local      |
| None                   | *Non pris en charge par le Mexique* |
| Concubinage             | *Non pris en charge par le Mexique* |

### <a name="gender"></a>Sexe

Le sexe est mis en correspondance avec Dayforce et traduit, au besoin, dans les valeurs acceptées lors de l'intégration.

Le tableau suivant montre comment le sexe est mis en correspondance avec Dayforce.

| Ressources humaines       | Dayforce                  |
|--------------|---------------------------|
| Masculin         | Masculin                      |
| Féminin       | Féminin                    |
| Non spécifique | *Non pris en charge par le Mexique* |

### <a name="payment-method"></a>Mode de paiement

Les modes de paiement fournissent à l'employé et à la société une manière de décrire la façon dont les employés sont payés. Les modes de paiement sont mis en correspondance avec Dayforce et traduit, au besoin, dans les valeurs acceptées lors de l'intégration.

Le tableau suivant montre comment les modes de paiement sont mis en correspondance avec Dayforce.

| Ressources humaines             | Dayforce                  |
|--------------------|---------------------------|
| Argent comptant               | Argent comptant                      |
| Paiement électronique | Transférer                  |
| Vérification              | Chèque                    |
| Traites bancaires         | *Non pris en charge par le Mexique* |
| Autre/s              | *Non pris en charge par le Mexique* |

### <a name="bank-account-type"></a>Type de compte bancaire

Les types de comptes bancaires sont utilisés pour les paiements électroniques aux employés. Les types de comptes bancaires sont mis en correspondance avec Dayforce tant qu'informations de compte de transfert. Les types de comptes bancaires sont traduits, au besoin, dans des valeurs acceptées lors de l'intégration.

| Ressources humaines            | Dayforce                  |
|-------------------|---------------------------|
| Compte courant  | CheckingAccount           |
| Compte de paie   | PayrollAccount            |
| Compte d'épargne   | *Non pris en charge par le Mexique* |
| Compte BankGirot | *Non pris en charge par le Mexique* |
| Compte PlusGirot | *Non pris en charge par le Mexique* |

### <a name="earning-codes"></a>Codes de rémunérations

Les codes de rémunérations identifient de manière unique chaque type de revenus que les collaborateurs reçoivent. Les codes couvrent différents paramètres associés aux revenus, tels que des règles comptables, des lois fiscales, des conditions de génération d'états, et la capacité de montant brut. Si une fréquence non prise en charge est utilisée, la fréquence **Chaque paie** est utilisée par défaut pour le calcul.

#### <a name="supported-frequencies"></a>Fréquences prises en charge

- Tous
- EVERYPAY
- EACHPAYPERIOD
- EVRYOTHRPAYODD
- EVRYOTHRPAYEVN
- 1OFMTH
- LASTOFMTH
- 2OFMTH
- 3OFMTH
- 4OFMTH
- 5OFMTH
- 1N2OFMTH
- 3N4OFMTH
- 1N3OFMTH
- 1N4OFMTH
- 2N3OFMTH
- 2N4OFMTH
- 1N2N3OFMTH
- 1N2N4OFMTH
- 1N3N4OFMTH
- 2N3N4OFMTH
- 1N2N3N4OFMTH - 1N2N3N4OFMTH
- 2N3N4N5OFMth - 2N3N4N5OFMth
- 1OFQTR - 1OFQTR
- LASTOFQTR – LASTOFQTR
- LASTMTHOFQTR – LASTMTHOFQTR
- 1OFYEAR - 1OFYEAR
- LASTOFYEAR – LASTOFYEAR
- NOVNDECOFYEAR - NOVNDECOFYEAR

### <a name="addresses"></a>Adresses

L'identification d'un pays ou d'une région, d'un état, et des codes département (municipalité) spécifiques nécessite des formats spécifiques que les fournisseurs Dayforce et dans le pays/la région peuvent identifier. Bien que le format pour les villes soit flexible, chaque ville doit être associée à un état.

| Ressources humaines              | Dayforce              |
|---------------------|-----------------------|
| Pays/région      | Code pays          |
| Code postal     | Code postal           |
| État               | Code région            |
| Ville                | Ville                  |
| Commune              | Département (municipalité) |
| Rue              | Ligne d'adresse 1        |
| Numéro de la rue       | Ligne d'adresse 2        |
| Info complémentaire sur le bâtiment | Ligne d'adresse 5        |

### <a name="passport-number"></a>Numéro de passeport

Les employés peuvent déclarer des informations de passeport. Ces informations sont de type d'identification **Passeport** et sont intégrées à Dayforce dans le cadre des informations spécifique au Mexique d'un employé.

- Type d'identification = « Passeport »
- Date d'émission
- Date d'expiration

Les employés peuvent déclarer plusieurs numéros d'identification de type d'identification **Passeport**. Toutefois, seule la saisie de passeport actif actuel est intégrée à Dayforce. Si toutes les entrées de passeport sont arrivées à expiration, le passeport émis le plus récemment est intégré dans Dayforce.



[!INCLUDE[footer-include](../includes/footer-banner.md)]