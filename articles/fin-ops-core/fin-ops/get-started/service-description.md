---
title: Description du service pour les applications de finances et d’opérations
description: Cet article fournit la description du service pour les applications de finances et d’opérations.
author: tomhig
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: whigginb
ms.search.validFrom: 2021-09-03
ms.openlocfilehash: 756895ab0ccdbd2bc42f0a750ad9895ee7b284a4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847158"
---
# <a name="service-description-for-finance-and-operations-apps"></a>Description du service pour les applications de finances et d’opérations

[!include[banner](../includes/banner.md)]

Les applications de finances et d’opérations sont des offres SaaS (software as a service) de planification des ressources d’entreprise (ERP) conçues pour et intégrées dans [Microsoft Azure](https://azure.microsoft.com/overview/what-is-azure/). Le service de finances et d’opérations propose aux organisations des fonctionnalités ERP qui prennent en charge leurs besoins uniques et les aident à s’adapter à des environnements commerciaux en constante évolution, sans avoir besoin de gérer l’infrastructure. Les applications de finances et d’opérations peuvent inclure un ou plusieurs des domaines de solution suivants :

- [Dynamics 365 Finance](/dynamics365/finance/)
- [Dynamics 365 Human Resources](/dynamics365/human-resources/)
- [Dynamics 365 Supply Chain Management](/dynamics365/supply-chain/)
- [Dynamics 365 Commerce](/dynamics365/commerce/)
- [Dynamics 365 Project Operations](/dynamics365/project-operations/)

Combinées avec les outils [Business Intelligence](/power-bi/fundamentals/power-bi-service-overview), d’[infrastructure](https://azure.microsoft.com/global-infrastructure/), de [calcul](/azure/service-fabric/service-fabric-overview) et les [services de base de données](https://devblogs.microsoft.com/azure-sql/running-1m-databases-on-azure-sql-for-a-large-saas-provider-microsoft-dynamics-365-and-power-platform/), ces applications permettent aux organisations d’exécuter des processus métiers opérationnels et propres à l’industrie. Soutenus par leur partenaire d’implémentation, les clients déterminent la configuration de la logique d’application métier qui convient le mieux à leurs processus métier uniques. Les fonctionnalités et les processus métier peuvent être augmentés ou étendus via une des solutions suivantes ou une association d’entre elles :

- [Expérience de personnalisation](personalize-user-experience.md) intégrée
- Outils [Microsoft Power Platform](../../dev-itpro/power-platform/overview.md)
- [Kit de développement logiciel (SDK) de développement logiciel de finances et d’opérations](../../dev-itpro/dev-tools/developer-home-page.md) basé sur [Visual Studio](https://visualstudio.microsoft.com) et [automatisation intégrée à Azure DevOps](../../dev-itpro/dev-tools/developer-home-page.md#build-automation-using-azure)
- Solutions d’éditeurs de logiciels indépendants (ISV) de [AppSource](https://appsource.microsoft.com/partners)

En fonction des besoins, les clients choisissent leur approche de solution. Ils collaborent avec leur partenaire de mise en œuvre pour définir, développer et tester leur solution en utilisant des outils et les bonnes pratiques fournis dans[Microsoft Dynamics Lifecycle Services (LCS)](../../dev-itpro/lifecycle-services/lcs.md). Il existe quatre scénarios courants :

- Configuration standard des applications de finances et d’opérations "prêtes à l’emploi" (pas d’extensions)
- Configuration des applications de finances et d’opérations qui inclut une ou plusieurs solutions de fournisseur de logiciel indépendant
- Configuration des applications de finances et d’opérations incluant une ou plusieurs extensions spécifiques au client
- Configuration des applications de finances et d’opérations incluant une combinaison d’extensions spécifiques au client et une ou plusieurs solutions ISV

Les organisations peuvent accompagner la croissance de leur activité en ajoutant facilement des utilisateurs et des processus métier via un modèle d’abonnement simple et transparent. Pour plus d’informations, voir [Guide de gestion des licences Dynamics 365](https://www.microsoft.com/licensing/docs/view/Microsoft-Dynamics-365).

## <a name="operating-model"></a>Modèle de fonctionnement

Le modèle de fonctionnement des applications de finances et d’opérations définit des rôles et des responsabilités spécifiques au client, au partenaire de mise en œuvre et à Microsoft tout au long du cycle de vie du service. Pour plus d’informations, voir [Opérations et maintenance du cloud](../../dev-itpro/lifecycle-services/cloud-operations-servicing.md).

### <a name="customer-activities"></a>Activités client

Les clients collaborent avec leur partenaire et [Microsoft FastTrack](/dynamics365/fasttrack/) et suivent le [Guide de mise en œuvre pour Dynamics 365](https://community.dynamics.com/365/dynamics-365-fasttrack/p/dynamics365implementationguide), le guide [Success by Design](/dynamics365/fasttrack/success-by-design-overview), ainsi que les outils et les modèles de pratiques recommandées de [Lifecycle Services](../../dev-itpro/lifecycle-services/lcs.md) pour mettre en œuvre leur solution. Les activités courantes comprennent :

- Gestion de l’identité et de la sécurité des utilisateurs
- Définir, développer et exploiter les processus métier
- Définir, développer, tester et exploiter des extensions
- Surveiller et gérer les déploiements hors production
- Gérer les mises à jour des applications et valider les extensions
- Gérer les solutions ISV et les intégrations tierces

### <a name="microsoft-responsibilities"></a>Responsabilités de Microsoft

Microsoft gère le service de finances et d’opérations en déployant, en surveillant activement et en assurant la maintenance des environnements de type bac à sable et de production des clients dans l’abonnement SaaS de Microsoft. Cette gestion comprend l’allocation de l’infrastructure système requise pour exécuter le service et communiquer de manière proactive avec les clients sur la santé du service. Les responsabilités comprennent :

**Gestion des infrastructures**
- Sécurité et isolement
- Systèmes d’exploitation et virtualisation
- Serveurs, stockage et mise en réseau
- Alimentation, mise en réseau, refroidissement du centre de données

**Gestion de la plateforme de l’application**
- Surveillance des applications et notifications 24h/24 et 7j/7
- Diagnostics, mises à jour de plate-forme, correctifs, mises à jour de service
- Acheminement des applications, équilibrage de charge, réplication de site
- Approvisionnement et gestion de l’environnement
- Gestion de base de données, haute disponibilité (HA)/récupération d’urgence (DR), évolutivité, opérations
- Déploiement de calcul, montée en charge, réduction

## <a name="system-configuration"></a>Configuration du système

Les applications de finances et d’opérations évoluent en fonction du volume de transactions et de la charge utilisateur. Chaque implémentation client produit une solution unique qui se compose des éléments suivants :

- **Composition des données** : ensemble unique de paramètres qui contrôlent le comportement, la configuration de l’organisation, la structure des données de base (telles que les dimensions financières et d’inventaire) et la granularité du suivi des transactions.
- **Extension et configuration** : mécanismes d’extension qui utilisent des extensions de code, des solutions ISV et des configurations uniques qui incluent des workflows, des intégrations et des configurations de rapport.
- **Modèles d’utilisation** : une combinaison unique d’utilisation en ligne et par lots, ainsi que la possibilité d’intégrer des systèmes en amont et en aval pour un flux de données unifié et la possibilité de se différencier en fonction des vues d’informations que les clients utilisent dans leurs processus métier.

Microsoft configure des environnements de production client dimensionnés pour gérer les volumes de transactions et la simultanéité des utilisateurs. Microsoft est responsable des tâches suivantes :

- Allouer correctement les ressources des environnements de production, en fonction des informations de profilage du client dans l’[estimateur d’abonnement LCS](../../dev-itpro/lifecycle-services/subscription-estimator.md)
- Surveiller et diagnostiquer en permanence la disponibilité des services des environnements de production
- Analyser et résoudre les problèmes de performance système avec les applications de finances et d’opérations

Pour veiller à ce qu’une implémentation soit configurée pour de hautes performances, les clients doivent effectuer ces tâches :

- Fournir des informations d’utilisation précises sur la mise en œuvre de finances et d’opérations dans [l’estimateur d’abonnement LCS](../../dev-itpro/lifecycle-services/subscription-estimator.md).
- Créez et testez des extensions pour les performances et l’évolutivité.
- Testez de manière appropriée les configurations de données pour les performances.
- Assurer l’évolutivité en faisant des [tests de performance](https://community.dynamics.com/365/b/techtalks/posts/performance-testing-approach-april-30-2018) avant la mise en service.

## <a name="onboarding-and-implementation"></a>Intégration et mise en œuvre

Le tableau suivant présente les événements d’intégration et de mise en œuvre typiques.

| Demande | Action Microsoft attendue | Action attendue du client/partenaire de mise en œuvre |
|---|---|---|
| Offre initiale d’achat | Un projet LCS est créé après l’achat de l’offre, sur la base d’un événement déclenché par le client. | Passez en revue le contrat entreprise (EA) ou le fournisseur de solutions cloud (CSP) [processus commercial](before-you-buy.md). Le partenaire crée un locataire pour le client, le cas échéant. |
| Achat complémentaire | Accordez au client l’accès au module complémentaire sélectionné au moment de la mise en œuvre. | Non applicable |
| Planification et analyse de la mise en œuvre | Fournissez des outils pertinents dans LCS, tels que le [Concepteur de processus d’entreprise (BPM)](../../dev-itpro/lifecycle-services/bpm-overview.md) et l’[interopérabilité avec Azure DevOps](../../dev-itpro/lifecycle-services/synchronize-bpm-vsts.md). | Faites la planification du projet, mettez en place Azure DevOps, exécutez l’intégration système et configurez les comptes d’administrateur. |

Pour plus d’informations, consultez [Intégration d’un projet de mise en œuvre](../imp-lifecycle/onboard.md).

## <a name="globalization"></a>Globalisation

Les applications de finances et d’opérations sont servies à partir de plusieurs régions Azure à travers le monde. Les applications de finances et d’opérations fournissent des fonctionnalités pour prendre en charge différents pays/régions et langues maternelles. Pour plus d’informations, voir [Localisation et fonctionnalités réglementaires](../../dev-itpro/lcs-solutions/country-region.md#localization-and-regulatory-features).

### <a name="countryregion-specific-considerations"></a>Considérations spécifiques à un pays/une région

- Les clients des secteurs réglementés ou des organisations commerciales qui travaillent avec des entités en France nécessitant la résidence des données locale doivent passer en revue les [finances et opérations en France](../../dev-itpro/deployment/france-local-deployment.md).
- Les clients qui ont des opérations en Chine devraient examiner [Playbook Azure Chine](/azure/china/) et [Finances et opérations exploitées par 21Vianet en Chine](../../dev-itpro/deployment/china-local-deployment.md).
- Les clients qui ont des opérations en Russie doivent passer en revue la [loi russe sur la localisation des données personnelles](/business-applications-release-notes/october18/dynamics365-finance-operations/russian-regulations-on-prem#when-will-the-cloud-deployment-option-of-dynamics-365-for-finance-and-operations-be-generally-available-for-russia).

### <a name="general-data-protection-regulation-gdpr"></a>Règlement général sur la protection des données (RGPD)

Pour les applications de finances et d’opérations, Microsoft agit en tant que sous-traitant. En tant que traitement des données, les finances et les opérations fournissent des processus et des fonctionnalités qui aident les clients à se conformer aux obligations en matière de RGPD en tant que contrôleur de données. Pour plus d’informations, reportez-vous à la section [Vue d’ensemble RGPD](../../dev-itpro/gdpr/gdpr-guide.md).

## <a name="environment-and-data-management"></a>Environnement et gestion des données

Cette section décrit certains événements typiques d’environnement et de gestion des données qui se produisent dans le service.

### <a name="environment-and-data-management-events-for-production-instances"></a>Événements de gestion de l’environnement et des données pour les instances de production

LCS fournit des [outils en libre-service](../../dev-itpro/deployment/infrastructure-stack.md) et [opérations de déplacement de base de données](../../dev-itpro/database/dbmovement-operations.md) qui sont utilisés pour effectuer des tâches de gestion de l’environnement et des données. Voici quelques exemples :

**Événement :** [Demander une instance de production](../imp-lifecycle/go-live-faq.md#when-can-i-configure-and-request-my-production-environment)

- Complétez le [Processus d’évaluation de la mise en service](../imp-lifecycle/prepare-go-live.md) et soumettez-la à l’équipe [Microsoft FastTrack](/dynamics365/fasttrack/).
- Exécutez l’[estimateur d’abonnement LCS](../../dev-itpro/lifecycle-services/subscription-estimator.md) avant de demander une instance de production.
- Effectuez toutes les tâches de mise en œuvre spécifiées dans la [méthodologie LCS](../../dev-itpro/lifecycle-services/create-methodology.md).

**Événement :**[Copier une base de données sandbox vers une instance de production](../../dev-itpro/database/dbmovement-scenario-goldenconfig.md)

- Exécuté pour une simulation de lancement ou une transition de lancement.

**Événement :** [Mode Maintenance](../../dev-itpro/sysadmin/maintenance-mode.md)

1. Activez le mode Maintenance dans LCS.
2. Effectuez la maintenance requise.
3. Désactivez le mode Maintenance dans LCS.

### <a name="environment-and-data-management-events-for-non-production-instances"></a>Événements de gestion de l’environnement et des données pour les instances hors production

LCS fournit l’[approvisionnement en libre-service](../../dev-itpro/deployment/infrastructure-stack.md) et des [opérations de déplacement de base de données](../../dev-itpro/database/dbmovement-operations.md) qui sont utilisés pour effectuer des tâches de gestion de l’environnement et des données. Voici quelques exemples :

**Événement :** [Déployer une nouvelle instance sandbox](../../dev-itpro/deployment/deployenvironment-newinfrastructure.md)

- Assurez-vous que toutes les instances requises ont été [prévues](../imp-lifecycle/environment-planning.md), et que les offres complémentaires applicables ont été achetées.
- Exécutez le processus de déploiement dans LCS.
- Effectuez toutes les tâches de mise en œuvre spécifiées dans les listes de contrôle LCS.
    
>[!NOTE]
>Un environnement sandbox de développement est une machine virtuelle (VM) qui est [déployée sur l’abonnement Azure du client](../../dev-itpro/dev-tools/access-instances.md) et gérée par le client.

**Événement :**[Copier une base de données de configuration Golden du bac à sable vers la production](../../dev-itpro/database/dbmovement-scenario-goldenconfig.md)

- Exécuté pour une simulation de lancement ou une transition de lancement.

**Événement :** [Restauration d’une sauvegarde ponctuelle de production sur une instance hors production](../../dev-itpro/database/database-pitr-prod-sandbox.md)

- Exécutez l’option [Actualiser la base de données](../../dev-itpro/database/database-refresh.md) dans LCS.
- Afficher une copie : supprimez ou masquez les données sensibles via des scripts, ajustez les configurations d’application spécifiques à l’environnement (telles que les points de terminaison d’intégration) et activez ou ajoutez des utilisateurs. Notez que ces changements sont effectués en appliquant un [paquet de données](../../dev-itpro/data-entities/data-entities-data-packages.md#import-a-data-package).

**Événement :** [Restauration à un instant donné de la base de données d’instance hors production](../../dev-itpro/database/database-point-in-time-restore.md)

- Acceptez que le processus ne puisse pas être annulé.
- Exécutez l’opération de restauration ponctuelle dans LCS.

**Événement :** copie d’une base de données sandbox de niveau 2 vers un sandbox de développement pour la résolution des problèmes et le [débogage](../../dev-itpro/database/dbmovement-scenario-debugdiag.md)

- Exécutez l’opération d’exportation de la base de données dans LCS sur l’environnement sandbox de niveau 2.
- Importez et mettez à jour la base de données dans l’environnement de développement.

## <a name="data-backup-and-retention"></a>Sauvegarde et conservation des données

Les bases de données pour les environnements de finances et d’opérations dans l’abonnement SaaS sont protégées par des sauvegardes automatiques. Pour les environnements de production, les sauvegardes automatiques sont conservées pendant 28 jours, à moins que Microsoft ne procède à une restauration. Pour les environnements sandbox (Tier 2+), ils sont conservés pendant sept jours. Une restauration de l’environnement de production peut être effectuée si une défaillance se produit au moment d’une mise à jour de maintenance planifiée.

Pour plus d’informations sur les sauvegardes automatiques, voir [Sauvegardes automatisées - Azure SQL Database et SQL Managed Instance](/azure/azure-sql/database/automated-backups-overview?tabs=single-database).

## <a name="service-activity-responsibilities"></a>Responsabilités d’activités de service

Le tableau suivant décrit certains scénarios et activités types pour le service. Il indique également si Microsoft, le client ou à la fois Microsoft et le client sont responsables des activités.

| Activité | Responsabilité de Microsoft | Responsabilité du client |
|---|---|---|
| **Approvisionnement des clients initiaux** | | |
| Dimensionnez la charge projetée dans LCS à l’aide de l’outil d’estimation d’abonnement et demandez le provisionnement d’environnements spécifiques. | | O |
| Provisionnez toutes les instances de production et les instances hors production. | O | |
| Validez les instances de production déployées et les instances hors production. | | O |
| **Mises à jour de service** | |
| Appliquez les mises à jour de service aux instances hors production et de production désignées. | O | |
| Appliquez manuellement les mises à jour de service de LCS aux instances sandbox. Définissez, développez, testez la mise à jour et fournissez le package de mise à jour du code à LCS. | | O |
| Demandez et planifiez que les mises à jour d’extension soient appliquées à l’instance de production. | | O |
| Créez une sauvegarde du code et des données pour l’instance de production avant l’application des mises à jour. | O | |
| En cas d’échec, restaurez l’instance de production vers la sauvegarde du code et des données. | O | |
| **Gestion des données (sauvegarde, restauration et mise à jour)** | | |
| Sauvegardez la base de données. | O | |
| Déterminez la haute disponibilité et un plan de récupération d’urgence. | O | |
| Surveillez les performances de la base de données de l’instance de production. | O | |
| Ajustez la base de données de l’instance de production pour les performances. | O | |
| Effectuez une actualisation ponctuelle de la base de données de l’instance de production sur une instance de non-production. | | O |
| **Mise à jour des infrastructures** | | |
| Planifiez des mises à jour régulières de l’infrastructure. | O | |
| **Mise à l’échelle vers le haut et vers le bas (utilisateurs, stockage et instances)** | | |
| Achetez des utilisateurs supplémentaires et des modules complémentaires hors production. | | O |
| Mettez à jour les modifications d’utilisation dans l’outil d’estimation d’abonnement LCS. | | O |
| Signalez tout problème de performance important qui affecte l’utilisation du service. | | O |
| Gérez de manière proactive les ressources requises pour le service applicable. | O | |
| Enquêtez et résolvez les incidents. | O | |
| **Sécurité (accès utilisateur)** | | |
| Fournissez un accès utilisateur au service. | | O |
| Fournissez un accès au projet LCS pour la gestion et l’exploitation des instances qui ont été déployées via LCS. | | O |
| **Suivi des instances de production** | | |
| Surveillez les instances de production 24h/24, 7j/7. | O | |
| Informez le client de manière proactive des incidents impliquant l’instance de production. | O | |
| **Gestion et suivi des instances hors production** | | |
| Gérez les instances hors production à l’aide de LCS. | | O |
| Surveillez les instances hors production. | | O |

## <a name="service-update-strategy"></a>Stratégie de mise à jour de service

Conformément à la [stratégie de cycle de vie du logiciel](../../dev-itpro/migration-upgrade/versions-update-policy.md), les applications de finances et d’opérations suivent la [stratégie du cycle de vie moderne](../../dev-itpro/migration-upgrade/versions-update-policy.md#modern-lifecycle-policy) de Microsoft, ce qui couvre les produits maintenus et pris en charge en continu. 

Microsoft publie huit mises à jour de service pour les applications de finances et d’opérations chaque année les mois suivants :

- Janvier
- Février
- Avril
- mai
- Juillet
- Août
- Octobre
- Novembre

>[!NOTE]
>Avril et octobre sont des vagues de sortie de fonctionnalités majeures. Les clients peuvent suspendre une mise à jour de service individuelle jusqu’à trois cycles de mise à jour consécutifs.

Pour plus d’informations, passez en revue les rubriques suivantes :

- [Vue d’ensemble des mises à jour de service à une version](../../dev-itpro/lifecycle-services/oneversion-overview.md)
- [Configurer les mises à jour de service via LCS](../../dev-itpro/lifecycle-services/configure-service-updates.md)
- [Suspendre les mises à jour de service via LCS](../../dev-itpro/lifecycle-services/pause-service-updates.md)
- [Être informé sur les mises à jour de service via LCS](../../dev-itpro/lifecycle-services/notifications-service-updates.md)
- [Outils de test de régression pour valider les mises à jour de service](../../dev-itpro/perf-test/rsat/rsat-overview.md)
- [Feuille de route et vagues de lancement de Dynamics 365](https://dynamics.microsoft.com/roadmap/overview/)

## <a name="security-and-administrative-access"></a>Accès administratif et sécurité

L’accès administratif à un environnement de production de finances et d’opérations est strictement contrôlé et enregistré. Les données des clients sont traitées conformément aux [Conditions des services en ligne Microsoft](https://www.microsoft.com/licensing/terms/productoffering). 

### <a name="customer-administrative-access"></a>Accès administratif client

L’administrateur du locataire du client peut accéder aux instances de production ou aux instances hors production, comme décrit dans le tableau suivant :

| Type d’environnement | Objectif | Niveau d’accès client |
|---|---|---|
| **Hors production**<br>Bac à sable de niveau 1 | Environnement hors production que les clients déploient à des fins de développement, de démonstration ou de formation. | Le bac à sable de niveau 1 (également appelé environnement hébergé dans le cloud) est une machine virtuelle gérée par le client qui est déployée sur l’abonnement Azure du client à partir de LCS. Étant donné qu’il s’agit d’une machine virtuelle dans l’abonnement Azure du client, le client dispose d’un accès administratif complet à l’environnement via Remote Desktop. |
| **Hors production**<br>Bac à sable de niveau 2 (ou supérieur) | Un environnement hors production que les clients déploient pour les tests d’acceptation des utilisateurs, les tests d’intégration, la formation, la préparation ou tout autre scénario de pré-production. | Les bacs à sable de niveau 2 et supérieurs sont déployés sur l’abonnement SaaS de finances et d’opérations. L’accès aux bases de données Azure SQL associées à l’environnement hors production est accordé via [l’accès juste-à-temps](../../dev-itpro/database/database-just-in-time-jit-access.md). L’accès à Remote Desktop n’est pas disponible. |
| **Production** | Un environnement de production est déployé quand le projet est [prêt pour la mise en service initiale](../imp-lifecycle/environment-planning.md#production-system-readiness). | Les environnements de production sont déployés sur l’abonnement SaaS. Tous les accès se font via le navigateur, les points de terminaison de service ou LCS. |

### <a name="microsoft-administrative-access"></a>Accès administratif Microsoft

Le tableau suivant présente les différents niveaux d’accès pour différents administrateurs Microsoft :

| Administrator | Données client |
|---|---|
| Équipe d’intervention des opérations<br>(Limité au personnel clé uniquement) | L’accès est accordé via un ticket de support. L’accès est audité et limité à la durée de l’activité de support. |
| Services de support client Microsoft (CSS) | Aucun accès direct. Le client peut utiliser le partage d’écran pour collaborer avec le personnel d’assistance afin de déboguer les problèmes. |
| Ingénierie | Aucun accès direct. L’équipe d’intervention des opérations peut utiliser le partage d’écran pour travailler avec l’ingénierie afin de déboguer les problèmes. |
| Autres dans Microsoft | Aucun accès. |

## <a name="monitoring"></a>Surveillance

Microsoft a investi dans un ensemble d’outils complet pour surveiller et diagnostiquer les instances de production des clients. Microsoft surveille les environnements de production des clients 24h/24, 7j/7. Pour plus d’informations, voir [Accompagnement et suivi de production](../imp-lifecycle/production-support-monitoring.md).

| Responsabilités de Microsoft | Responsabilités du client |
|---|---|
| <ul><li>Surveillez la disponibilité du service.</li><li>Surveillez et alertez en permanence via des métriques de santé et des « chiens de garde » pour les composants critiques tels que Application Object Server (AOS), Batch, Data Import/Export Framework (DIXF), Commerce et Management Reporter.</li><li>Surveillez la dégradation des performances causée par les services d’infrastructure (tels que Azure Active Directory \[Azure AD\] et Azure SQL).</li><li>Si Microsoft détermine qu’un seul processus ou tâche par lots provoque des aberrations, ce processus ou cette tâche sera interrompu après la communication avec le client.</li></ul> | <ul><li>Surveillez les modifications apportées aux configurations et aux extensions des applications qui peuvent entraîner des problèmes fonctionnels et de performances.</li><li>Les erreurs d’application doivent être diagnostiquées à l’aide des outils de surveillance. Utilisez ces outils pour diagnostiquer les aberrations de performances signalées par les utilisateurs.</li><li>Informez Microsoft s’il y a une charge prévue sur le système au-delà de l’utilisation maximale prévue.</li><li>Si le service applicable n’est pas disponible dans l’instance de production, le client peut utiliser LCS pour signaler un [arrêt de production](../../dev-itpro/lifecycle-services/report-production-outage.md).</li></ul> |

En soumettant des demandes de support en ligne, via LCS, les clients permettent à Microsoft de fournir une expertise technique rapide et approfondie de la manière la plus efficace et la plus efficiente. Bien qu’une option téléphonique soit disponible, elle ne doit être utilisée que si l’option en ligne n’est pas disponible. Pour plus d’informations, voir la rubrique [Options de support téléphonique](/power-platform/admin/support-overview?toc=%2Fdynamics365%2Ffin-ops-core%2Fdev-itpro%2Ftoc.json&bc=%2Fdynamics365%2Fbreadcrumb%2Ftoc.json#is-there-a-phone-number-i-can-call-to-contact-support).

## <a name="incident-management"></a>Gestion des incidents

Microsoft répond et corrige les incidents en fonction des niveaux de gravité. Les niveaux de gravité des incidents de Microsoft peuvent être modifiés au moment de l’évaluation initiale de l’incident et à mesure que de plus amples informations sur l’impact et la portée deviennent disponibles. Si l’incident est atténué, la gravité de l’incident reste inchangée.

Pour plus d’informations sur les niveaux de gravité, voir [ce tableau de gravité](/power-platform/admin/support-overview#what-is-initial-response-time-and-how-quickly-can-i-expect-to-hear-back-from-someone-after-submitting-my-support-request).

## <a name="business-continuity-through-high-availability-and-disaster-recovery"></a>Continuité des activités grâce à la haute disponibilité et à la récupération d’urgence 

Microsoft assure la continuité des activités et la récupération d’urgence pour les instances de production des applications de finances et d’opérations en cas de pannes à l’échelle de la région Azure. Pour plus d’informations, y compris l’objectif de temps de récupération (RTO) et l’objectif de point de récupération (RPO), voir [continuité d’activité et reprise d’activité](../../dev-itpro/sysadmin/business-continuity-disaster-recovery.md).

- **Haute disponibilité** : la fonctionnalité HA fournit des moyens d’éviter les temps d’arrêt causés par la défaillance d’un seul nœud dans un centre de données Azure. L’architecture cloud de chaque service utilise des ensembles de disponibilité Azure pour le niveau de calcul afin d’éviter les événements de point de défaillance unique. La haute disponibilité pour les bases de données est fournie via les [Fonctionnalités HA Azure SQL](/azure/azure-sql/database/high-availability-sla).
- **Récupération d’urgence** : les [fonctionnalités de récupération d’urgence Azure](/azure/best-practices-availability-paired-regions) protègent chaque service contre les pannes qui affectent largement l’ensemble d’un centre de données Azure. Voici quelques unes de ces fonctionnalités :

    - Réplication géoactive Azure SQL pour la base de données principale (base de données métier).
    - Copies géo-redondantes d’Azure Blob Storage (qui contient des pièces jointes de documents) dans d’autres régions Azure.
    - Région secondaire pour les réplications Azure SQL et Azure Blob Storage.

Si la récupération d’urgence est utilisée pour récupérer l’instance de production du client, Microsoft et le client respecteront leurs responsabilités de [gestion des incidents](service-description.md#incident-management).

Les plans et procédures de récupération d’urgence de Microsoft sont examinés régulièrement par le biais d’audits de contrôle du système et de l’organisation (SOC). Ces audits de conformité attestent du processus technique et procédural du DR de Microsoft, y compris les applications de finances et d’opérations Dynamics 365. Les rapports d’audit [Conformité SOC](/compliance/regulatory/offering-soc-2) et tous les autres rapports de conformité sont disponibles sur [Offres du Centre de gestion de la confidentialité Microsoft](/compliance/regulatory/offering-home).

## <a name="finance-and-operations-support-offerings"></a>Support pour les offres de finances et d’opérations

Le support technique est disponible sur les marchés où les services de finances et d’opérations sont proposés. Les [expériences d’assistance](../../dev-itpro/lifecycle-services/lcs-support.md) sont fournies dans LCS ou les applications de finances et d’opérations. Voici quelques exemples :

- [Recherche d’incidents](../../dev-itpro/lifecycle-services/issue-search-lcs.md) dans LCS
- [Support technique intégré](../../dev-itpro/lifecycle-services/support-experience.md) dans les applications de finances et d’opérations
- [Prise en charge sur le cloud](../../dev-itpro/lifecycle-services/cloud-powered-support-lcs.md) dans LCS

Microsoft offre aux clients de finances et d’opérations trois plans de support : Premier, Professional Direct et le support inclus dans l’abonnement. Le niveau de soutien diffère selon le plan. Le tableau suivant présente une comparaison des trois plans.

| Fonctionnalité de support | Premier | Support technique direct professionnel | Abonnement |
|---|---|---|---|
| Soumission illimitée d’incidents de rupture/réparation | Oui | Oui | Oui |
| Accès 24h/24 et 7j/7 via LCS | Oui | Oui | Oui |
| Temps de réponse aux incidents | Moins d’une heure | Moins d’une heure | Jour ouvrable suivant |
| Heures de conseil | Les regroupements sont acquis par contrat. | Non | Non |
| Responsable de compte support dédié | Oui | Non | Non |
| Ingénieur support dédié | Engagé dans le cadre d’un contrat distinct | Non | Non |

Pour plus d’informations, voir [Vue d’ensemble du support](/power-platform/admin/support-overview).

### <a name="process-to-engage-support"></a>Processus pour engager le support

En cas d’incident impliquant les applications de finances et d’opérations, les clients envoient des tickets de support à Microsoft via LCS. CSS gère les incidents, en fonction du plan de support du client et de la gravité de l’incident tel que désigné par CSS.

### <a name="service-level-agreement"></a>Contrat SLA

Microsoft s’engage à un taux de disponibilité de 99,9 % par mois de service. Si Microsoft n’atteint pas et ne maintient pas le niveau de service pour le service applicable tel que décrit dans le contrat de niveau de service (SLA), le client peut être éligible à un crédit pour une partie de ses frais de service mensuels pour ce service. Pour plus d’informations sur la façon d’initier un crédit de service, consulter la section « Réclamations » du [SLA](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services).

## <a name="important-resources"></a>Ressources importantes

- **[Centre de gestion de la confidentialité](https://www.microsoft.com/trust-center)** – Obtenez des informations sur l’endroit où vos données de finances et d’opérations sont stockées, ainsi que des informations supplémentaires sur les procédures de confidentialité, de conformité et de sécurité.
- **[Conditions de licence et documentation](https://www.microsoftvolumelicensing.com/)**  : accédez rapidement aux termes, conditions et informations supplémentaires des licences relatives à l’utilisation des produits et services concédés sous licence via les programmes de licence en volume Microsoft.
- **[Conditions de licence](https://www.microsoft.com/licensing/product-licensing/)**  : les ressources de cette page définissent les termes et conditions des logiciels et des produits de services en ligne que vous achetez via les programmes de licence commerciale Microsoft.
- **[Stratégie du cycle de vie Microsoft](/lifecycle/)**  : cette page fournit des directives cohérentes et prévisibles pour la disponibilité du support tout au long de la vie d’un produit.
- **[Guide de licence](https://www.microsoft.com/licensing/docs/view/Microsoft-Dynamics-365)**  : utilisez ce guide pour en savoir plus sur l’octroi de licence Dynamics 365.
- **[Service client](https://dynamics.microsoft.com/support/)**  : bénéficiez d’un support de pointe pour vos applications Dynamics 365.
- **[Dynamics Lifecycle Services](https://lcs.dynamics.com/)**  : gérez le cycle de vie de votre application et évoluez vers des implémentations prévisibles, reproductibles et de haute qualité.
- **[Guide de mise en œuvre de Dynamics 365](https://aka.ms/D365ImplementationGuideFlip)** – Les documents du Guide de mise en œuvre de Dynamics 365 ont fait leurs preuves les principes Success by Design et fournissent des conseils normatifs pour concevoir, créer, tester et déployer des solutions Dynamics 365.

## <a name="definitions"></a>Définitions

### <a name="azure-region"></a>[Région Azure](/azure/availability-zones/az-overview#regions)

Région géographique où existent un ou plusieurs centres de données Azure. Les exemples incluent les États-Unis et l’Europe.

### <a name="business-process-modeler-bpm"></a>[Concepteur de processus d’entreprise (BPM)](../../dev-itpro/lifecycle-services/bpm-overview.md)

Un outil dans LCS qui aide à effectuer une analyse d’ajustement pour une implémentation donnée en utilisant les définitions de processus métier de l’American Productivity et Quality Center (APQC) qui sont pris en charge dans les applications de finances et d’opérations.

### <a name="cloud-solution-provider"></a>Fournisseur de solutions cloud

Un partenaire qui fait partie du programme Microsoft Cloud Solution Provider (CSP) et qui fournit aux clients des services cloud à valeur ajoutée, une assistance, une facture et une gestion des clients à grande échelle.

### <a name="customer"></a>Client

Une entité commerciale qui utilise les applications de finances et d’opérations et est représenté par un locataire dans Office 365.

### <a name="development-environment"></a>Environnement de développement

Environnement sandbox hors production utilisé pour développer des extensions. Les clients déploient cet environnement sur leur propre abonnement Azure à partir de LCS. Cet environnement peut également être utilisé pour des démonstrations, des formations ou d’autres tâches de test. On le désigne aussi comme [bac à sable de niveau 1](../imp-lifecycle/environment-planning.md#tier-1-vs-tier-2-and-higher).

### <a name="downtime"></a>Temps d’arrêt

Toute période pendant laquelle les utilisateurs ne peuvent pas se connecter ou accéder à leur locataire actif en raison d’une défaillance de la plate-forme non expirée ou de l’infrastructure de service, comme le détermine Microsoft à partir de la surveillance automatisée de l’intégrité et des journaux système. Les temps d’arrêt n’incluent pas les temps d’arrêt programmés, l’indisponibilité des fonctionnalités complémentaires du service, l’impossibilité d’accéder au service en raison de vos modifications apportées au service ou les périodes où la capacité de l’unité d’échelle est dépassée.

### <a name="implementation-partner"></a>Partenaire d’implémentation

Le partenaire que le client choisit pour personnaliser, configurer, mettre en œuvre et gérer ses solutions de finances et d’opérations.

### <a name="incident"></a>Incident

Un problème que les clients rencontrent quand ils utilisent le service de finances et d’opérations, et qu’ils soumettent un ticket via LCS.

### <a name="microsoft-customer-support-services-css"></a>Services de support client Microsoft (CSS)

Équipe de support mondial de Microsoft qui se consacre à fournir un service de qualité pour les applications de finances et d’opérations.

### <a name="microsoft-dynamics-lifecycle-services-lcs"></a>Microsoft Dynamics Lifecycle Services (LCS)

Le portail administratif pour la gestion du cycle de vie des applications de finances et d’opérations de l’évaluation à la mise en œuvre, en passant par la gestion et le support post-production. Pour plus d’informations, voir [Ressources Lifecycle Services](../../dev-itpro/lifecycle-services/lcs.md).

### <a name="non-production-instance"></a>Instance hors production

Une des instances suivantes d’un service que le client utilise pour valider les extensions et effectuer d’autres tâches de développement :

- **Bac à sable de niveau 1** : instance de développeur (hébergée par le client)
- **Bac à sable de niveau 2** : instance de test d’acceptation standard
- **Bac à sable des niveaux 3 à 5** : bacs à sable complémentaires

Pour plus d’informations sur les niveaux 2 à 5, voir [Sélection du bon environnement de niveau 2 ou supérieur](../imp-lifecycle/environment-planning.md#selecting-the-correct-tier-2-or-higher-environment).

### <a name="production-instance"></a>Instance de production

Un environnement de finances et d’opérations que le client utilise pour gérer ses transactions quotidiennes « en direct » et ses processus commerciaux.

### <a name="sandbox-environment"></a>Environnement de bac à sable

Environnement hors production que le client utilise pour la démonstration, la formation, les tests d’acceptation des utilisateurs, la validation des extensions et d’autres tâches de test.

### <a name="service"></a>Service

Tout service de base inclus dans les applications de finances et d’opérations.

### <a name="service-level-agreement-sla-for-microsoft-online-services"></a>Contrat de niveau de service (SLA) pour les services en ligne Microsoft

Le SLA s’applique aux services en ligne Microsoft. Pour plus d’informations, voir [Contrats de niveau de service](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services).

### <a name="service-update"></a>Mise à jour de service

Microsoft met en place les environnements de finances et d’opérations sur une base cohérente grâce à des mises à jour de service. Les clients définissent leur propre calendrier de mise à jour des services, en fonction de leurs besoins commerciaux. Pour plus d’informations, voir [Mises à jour de service One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="success-by-design"></a>[Success by Design](/dynamics365/fasttrack/success-by-design-overview)

Le cadre qui guide systématiquement une implémentation à travers une série d’évaluations à des étapes critiques pour garantir une architecture, une sécurité, des performances et une expérience utilisateur optimales pour une solution Dynamics 365.

### <a name="user"></a>Utilisateur

Personne seule qui utilise les environnements de finances et d’opérations et associée au locataire d’un client.
