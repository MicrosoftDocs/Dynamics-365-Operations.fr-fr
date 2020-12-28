---
title: Nouveautés ou modifications dans Dynamics 365 for Talent (10 septembre 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 9/10/2019
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
ms.search.validFrom: 2019-09-10
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 0aadecd5b37759492f7895ccfda1a777793a08b3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461155"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-september-10-2019"></a>Nouveautés ou modifications dans Dynamics 365 for Talent (10 septembre 2019)

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

### <a name="candidate-e-mail-login"></a>Identifiant de connexion par e-mail du candidat

Les candidats sont désormais en mesure d'utiliser n'importe quelle adresse électronique afin de créer un compte et un identifiant pour un site de carrière Talent dans le but de postuler à des emplois et de rechercher le statut de leur candidature. Cela vient en complément de la connexion au site de carrière Talent avec leurs comptes des réseaux sociaux ou leurs identifiants d'organisation.

### <a name="job-activation-and-posting"></a>Activation et validation des missions

Nous avons apporté quelques modifications à l'activation et à la validation des missions. Vous devez activer les missions avant de les valider vers le site de carrière Talent ou vers tout tableau de bord de missions externe, notamment LinkedIn ou Broadbean.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2482. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).

### <a name="you-can-enable-preview-features-in-sandbox-and-trial-environments"></a>Vous pouvez activer les fonctions d'aperçu dans les environnements de bac à sable et d'essai.

Lorsque vous provisionnez une nouvelle instance de Talent, vous pouvez indiquer si le type d'instance est Production ou Bac à sable. Les instances du type Bac à sable permettent de tester les nouvelles fonctions en avant-première. Si vous souhaitez que l'une de vos instances existantes soit mise à jour avec le type d'instance Bac à sable (sandbox), contactez le Support pour initier la demande de modification.

Pour plus d'informations sur la manière dont les modifications sont publiées, voir [Mettre en service Talent](./provisioning-talent.md).

### <a name="platform-update-29"></a>Update 29 de la plateforme

Pour des informations complémentaires sur Platform Update 29, voir [Fonctionnalités en version préliminaire dans Dynamics 365 for Finance and Operations Platform Update 29 (octobre 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-29).

### <a name="new-job-base-entity-available-in-data-management-framework-347202"></a>Nouvelle entité Mission de base disponible dans le cadre de la gestion des données (347202)

Avec cette version, une nouvelle entité Mission de base est disponible pour l'importation et l'exportation des données. 

### <a name="worker-advanced-security-policy-incorrectly-displays-positions-in-position-hierarchy-354868"></a>La politique de sécurité avancée des collaborateurs affiche des postes dans Hiérarchie des postes (354868)

Avec cette version, les postes ne s'affichent plus comme ouverts avec un collaborateur « vide » lorsque les utilisateurs ont un accès limité.

### <a name="job-form-close-box-wont-close-form-in-certain-situations-342467"></a>La zone de clôture de l'écran Mission ne se fermera pas dans certains cas (342467)

Cette version inclut une modification qui permet à l'écran Mission de se fermer dans tous les scénarios.

### <a name="new-case-on-employee-record-is-locked-for-human-resources-manager-role-337111"></a>Le nouveau dossier sur l'enregistrement de l'employé est verrouillé pour le rôle de responsable des Ressources humaines (337111)

Avec cette modification, l'écran de gestion des incidents n'est plus verrouillé en accédant depuis l'écran de l'employé.

### <a name="employment-end-date-always-defaults-to-235959-351492"></a>La date de fin d'emploi par défaut est toujours 23:59:59 (351492)

Avec cette modification, vous pouvez changer la date d'emploi à une heure autre que 23:59:59 lors de la fin manuelle d'un emploi.

### <a name="unable-to-set-up-expiration-date-on-an-earning-code-through-data-management-336604"></a>Impossible de définir la date d'expiration du code de rémunération par le biais de la gestion des données (336604)

Dans cette version, vous pouvez paramétrer des codes de rémunération qui expirent via l'entité **PayrollWorkerPositionEarningCodeEntity**.

### <a name="employee-development-analytic-report-doesnt-display-data-348737"></a>L'état analytique du développement des employés n'affiche pas de données (348737)

Dans la version de cette semaine, les analyses pour les compétences des employés ont été mises à jour pour offrir une analyse précise.

### <a name="terms-of-employment-datetime-dont-default-to-beginning-of-day-349101"></a>Les conditions de date/d'heure d'emploi ne sont pas définies par défaut au début du jour (349101)

Avec cette modification, la date/l'heure de début par défaut est désormais le début du jour et la date/l'heure de fin est définie par défaut à la fin de la journée.

### <a name="changing-the-employment-end-date-on-worker-action-form-displays-an-error-354092"></a>La modification de la date de fin d'emploi sur l'écran Action du collaborateur affiche une erreur (354092) 

Cette modification corrige une sortie en modifiant la date de fin d'emploi dans le cadre de l'action du collaborateur.

### <a name="applying-onboarding-checklists-across-companies-338433"></a>Application des listes de contrôle d'intégration entre les sociétés (338433)

Cette version permet maintenant d'appliquer des listes de contrôle pour les collaborateurs qui sont employés dans des entités juridiques autres que l'entité juridique connectée.

## <a name="in-preview"></a>En mode aperçu

### <a name="streamlined-employee-entry-and-navigation"></a>Navigation et entrée d'employé simplifiées

Cette fonctionnalité est désormais disponible dans les environnements de bac à sable. Pour activer cette fonctionnalité, naviguez jusqu'à **Administration du système > Liens > Paramétrage > Paramètres système > Fonctionnalités en version préliminaire**. Sélectionnez **Formulaire Collaborateur et navigation améliorés**. Ces modifications seront activées pour tous les utilisateurs. Vous pouvez désactiver cette option à tout moment.

Pour plus d'informations, voir [Navigation et entrée d'employé simplifiées](./streamlined-employee-entry.md).
