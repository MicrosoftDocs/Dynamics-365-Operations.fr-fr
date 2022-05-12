---
title: FAQ sur la fusion d’infrastructure de Dynamics 365 Human Resources
description: Cette rubrique répond aux questions fréquemment posées sur la fusion d’infrastructure pour les applications Microsoft Dynamics 365 Human Resources et Finances et Opérations.
author: twheeloc
ms.date: 08/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e43aaad2f5b80996eb0fc10f550f073aec67fe5d
ms.sourcegitcommit: 26c726bd0b00935e3d2c31fdc5a3b2ae03a8a2b0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2022
ms.locfileid: "8661456"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-faq"></a>FAQ sur la fusion d’infrastructure de Dynamics 365 Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Cette rubrique répond aux questions fréquemment posées sur la fusion d’infrastructure pour les applications Microsoft Dynamics 365 Human Resources et Finances et Opérations.

## <a name="what-is-the-dynamics-365-human-resources-infrastructure-merge"></a>Qu’est-ce que la fusion d’infrastructure pour Dynamics 365 Human Resources ?

Dynamics 365 Human Resources est une application autonome qui utilise une infrastructure différente des autres applications de finances et d’opérations, telles que Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce et Dynamics 365 Project Operations. La fusion des infrastructures permet d’intégrer Dynamics 365 Human Resources dans la même infrastructure que les autres applications Finances et Opérations.

## <a name="value-and-benefits-of-the-infrastructure-merge"></a>Valeur ajoutée et avantages de la fusion des infrastructures

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-what-benefits-will-we-see-from-these-changes"></a>Mon organisation utilise Dynamics 365 Human Resources pour gérer ses opérations RH. Quels bénéfices tirerons-nous de ces changements ?

- Ces modifications évitent la confusion engendrée par plusieurs ensembles de fonctionnalités de ressources humaines (RH) dans Dynamics 365.
- Elles offrent à la fois l’extensibilité de Microsoft Power Platform et un moyen d’étendre les options de logique métier et de fonctionnalité.
- Elles apportent de la cohérence entre Dynamics 365 Human Resources et les autres applications Finances et Opérations en termes de gestion du cycle de vie des applications (ALM), de Microsoft Dynamics Lifecycle Services (LCS), de disponibilité géographique, d’extensibilité, etc.
- Elles vous permettent de profiter de services et d’outils partagés et contribuent à réduire les coûts.

### <a name="my-organization-uses-the-human-resources-module-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-benefits-will-we-see-from-these-changes"></a>Mon organisation utilise le module Human Resources dans Dynamics 365 Finance, Supply Chain Management, Commerce ou Project Operations. Quels bénéfices tirerons-nous de ces changements ?

Les efforts de fonctionnalité et les investissements consacrés à Dynamics 365 Human Resources seront désormais à la disposition des clients qui utilisent le module HR dans Dynamics 365 Finance. Certaines de ces fonctionnalités incluent la gestion des congés et des absences, la gestion des avantages et la gestion des tâches.

### <a name="will-i-lose-any-features-or-capabilities-that-i-currently-use"></a>Vais-je perdre des fonctions ou fonctionnalités que j’utilise actuellement ?

Il y aura une parité fonctionnelle entre Dynamics 365 Human Resources et le module HR des applications Finances et Opérations. Pour les fonctionnalités similaires, Dynamics 365 Human Resources prendra la priorité. Pour plus d’informations, voir [Vue d’ensemble de la gestion des fonctionnalités](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="will-the-experience-change-for-my-users"></a>L’expérience changera-t-elle pour mes utilisateurs ?

Les nouvelles capacités RH seront gérées via la Gestion des fonctionnalités. Les clients décideront s’ils veulent les adopter. Dans certains cas, les fonctionnalités sont susceptibles d’être modifiées. Dans ces cas, une documentation sera fournie.

### <a name="how-does-this-change-affect-me-if-i-am-an-existing-customer-and-i-use-both-the-hr-module-on-the-finance-and-operations-infrastructure-and-dynamics-365-human-resources-through-custom-integrations"></a>Comment ce changement m’affecte-t-il si je suis un client existant et que j’utilise à la fois le module HR dans l’infrastructure Finances et Opérations et Dynamics 365 Human Resources via des intégrations personnalisées ?

Les intégrations personnalisées entre Dynamics 365 Human Resources et le module HR de Dynamics 365 Finance ne seront plus nécessaires. Toutes les données HR résideront dans la même base de données que les autres applications Finances et Opérations.

## <a name="migration-from-dynamics-365-human-resources-to-finance-and-operations-apps"></a>Migration des données des applications Dynamics 365 Human Resources vers Finances et Opérations

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-hr-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>Mon organisation utilise Dynamics 365 Human Resources pour gérer ses opérations RH. Que devons-nous prévoir pour migrer vers la nouvelle expérience ?

Si votre organisation utilise Dynamics 365 Human Resources, mais n’utilise pas d’autres applications Finances et Opérations, votre environnement Human Resources sera migré vers la nouvelle infrastructure. Une grande partie de ce processus de migration sera automatisée. Des processus seront implémentés pour migrer votre base de données et la synchroniser avec la nouvelle infrastructure.

De plus, des outils seront en place pour que vous puissiez tester le processus de migration et valider vos données et votre expérience avant de migrer votre environnement de production.

Si votre organisation utilise à la fois Dynamics 365 Human Resources et d’autres applications Finances et Opérations, vous devez prévoir plus de temps pour la validation afin de vous assurer que vos données sont correctement migrées vers le nouvel environnement. La migration vers la nouvelle infrastructure fusionnera les données de votre environnement Human Resources avec votre environnement Finances et Opérations. Les données conflictuelles nécessiteront l’intervention de l’utilisateur pour déterminer le mode de résolution du conflit. Les utilisateurs et les administrateurs devront gérer les mappages de données en cas de conflits, et tester la migration dans des environnements bac à sable avant la migration des environnements de production.

### <a name="my-organization-uses-the-human-resources-module-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>Mon organisation utilise le module Human Resources dans Dynamics 365 Finance, Supply Chain Management, Commerce ou Project Operations. Que devons-nous prévoir pour migrer vers la nouvelle expérience ?

Pour les organisations qui utilisent le module HR dans les applications Finances et Opérations, la nouvelle fonctionnalité de fonction de Dynamics 365 Human Resources sera appliquée à votre environnement via le processus de mise à jour standard One Version. Vous pouvez vous attendre à voir les nouvelles fonctionnalités dans votre environnement dès leur disponibilité dans les mises à jour. Vous pouvez utiliser la gestion des fonctionnalités pour activer de nouvelles fonctionnalités, mais vous devez prévoir de valider ces fonctionnalités. Suivez les processus que vous avez mis en place pour valider les autres mises à jour de votre environnement. Pour plus d’informations sur la façon dont les mises à jour sont appliquées aux applications Finances et Opérations, reportez-vous à la [Présentation de One Version](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="when-will-my-organization-be-migrated"></a>Quand mon organisation sera-t-elle migrée ?

La migration de chaque organisation dépendra de sa configuration actuelle et de sa capacité à migrer vers la nouvelle infrastructure. Ces dates sont sujettes à modification.

- Les organisations qui utilisent actuellement le module HR dans les applications Finances et Opérations recevront la fonctionnalité HR pour Dynamics 365 Human Resources dans le cadre du processus régulier de mise à jour de One Version. De nouvelles fonctionnalités sont prévues en disponibilité générale à partir de janvier 2022.
- Les organisations qui utilisent uniquement Dynamics 365 Human Resources auront accès à des outils de migration afin de pouvoir commencer les tests et démarrer la migration à partir de mi-2022. La date à laquelle la migration vers la nouvelle infrastructure doit être terminée n’a pas encore été déterminée. Cependant, il se sera écoulé au moins un an après que les outils de migration auront été rendus disponibles.
- Les organisations qui utilisent actuellement à la fois Dynamics 365 Human Resources et d’autres applications Finances et Opérations auront accès à des outils de migration afin de pouvoir commencer les tests et démarrer la migration à partir de la fin 2022. La date à laquelle la migration vers la nouvelle infrastructure doit être terminée n’a pas encore été déterminée. Cependant, il se sera écoulé au moins un an après que les outils de migration auront été rendus disponibles.

Pour plus d’informations sur les nouvelles fonctionnalités de Dynamics 365 Human Resources, consultez [Nouveautés ou modifications dans Human Resources](./hr-admin-whats-new.md).

### <a name="my-organization-has-not-yet-gone-live-on-dynamics-365-human-resources-should-we-go-live-with-the-human-resources-module-in-the-finance-and-operations-apps-or-with-the-dynamics-365-human-resources-app-on-the-legacy-infrastructure"></a>Mon organisation n’est pas encore en service sur Dynamics 365 Human Resources. Devons-nous procéder à la mise en service avec le module Human Resources dans les applications Finances et Opérations ou avec l’application Dynamics 365 Human Resources sur l’infrastructure existante ?

Les éléments importants à considérer sont la fonctionnalité RH nécessaire et le moment où cette fonctionnalité sera disponible sur la nouvelle infrastructure. Si l’organisation a besoin de la fonctionnalité de base pour la gestion du personnel, celle-ci est actuellement disponible dans le module RH des applications Finances et Opérations sur la nouvelle infrastructure. La parité des fonctionnalités entre le module RH des applications Finances et Opérations et l’application Dynamics 365 Human Resources est attendue dans la version 10.0.25, dont la disponibilité générale est prévue en mars 2022. Les fonctionnalités d’intégration telles que l’application Teams et les intégrations d’entités Dataverse seront disponibles dans des versions ultérieures.

Si les fonctionnalités RH requises par l’organisation seront disponibles sur la nouvelle infrastructure dans le délai de mise en service de l’organisation, il peut être plus facile d’effectuer la mise en service sur le module Human Resources dans les applications Finances et Opérations. Cela se traduira par une migration plus facile car il s’agira d’une mise à niveau d’application standard vers l’application Dynamics 365 Human Resources et le client sera déjà sur la nouvelle infrastructure. Si l’organisation décide une mise en service sur l’application Dynamics 365 Human Resources sur l’infrastructure existante, une migration de l’environnement sera nécessaire pour passer à la nouvelle infrastructure. Cela peut être évité en effectuant la mise en service sur la nouvelle infrastructure.

### <a name="i-am-using-new-capabilities-that-are-available-only-in-dynamics-365-human-resources-such-as-leave-and-absence-and-benefits-management-will-these-capabilities-now-be-available-in-the-human-resources-module-on-the-finance-and-operations-infrastructure-too"></a>J’utilise de nouvelles fonctionnalités disponibles uniquement dans Dynamics 365 Human Resources (telles que **Congés et absences** et **Gestion des avantages**). Ces fonctionnalités seront-elles désormais également disponibles dans le module Human Resources de l’infratsructure Finances et Opérations ?

Oui, tous les modules de Dynamics 365 Human Resources fonctionneront en l’état dans les applications Finances et Opérations, et il y aura une parité des fonctionnalités de 100 %. Dans le cadre de la stratégie globale de migration pour les clients qui utilisent actuellement ces fonctionnalités dans HR, les données client seront migrées de manière à ce qu’elles continuent à fonctionner dans l’infrastructure Finances et Opérations.

### <a name="i-use-the-new-dynamics-365-human-resources-benefits-management-capabilities-ive-built-custom-integrations-with-the-hr-module-on-the-finance-and-operations-infrastructure-so-that-i-can-take-advantage-of-the-payroll-capabilities-by-using-benefits-data-will-these-custom-integrations-be-required-going-forward"></a>J’utilise les nouvelles fonctionnalités de gestion des avantages de Dynamics 365 Human Resources. J’ai créé des intégrations personnalisées avec le module HR dans l’infrastructure Finances et Opérations de manière à pouvoir tirer parti des capacités de paie en utilisant les données des avantages. Ces intégrations personnalisées seront-elles nécessaires à l’avenir ?

Dans le cadre de la fusion des infrastructures, les données HR sont intégrées dans la même base de données que les autres applications Finances et Opérations. L’intégration entre modules dans les applications Finances et Opérations ne sera plus nécessaires.

### <a name="my-organization-uses-one-or-more-isv-solutions-with-dynamics-365-human-resources-will-our-isv-solutions-be-migrated-automatically"></a>Mon organisation utilise une ou plusieurs solutions d’ISV avec Dynamics 365 Human Resources. Nos solutions ISV seront-elles migrées automatiquement ?

L’expérience de migration pour chaque solution d’éditeur de logiciels indépendant (ISV) variera en fonction de la méthode d’intégration de la solution. Microsoft travaillera en étroite collaboration avec les ISV pour assurer une transition fluide vers la nouvelle infrastructure.

### <a name="my-organization-uses-linkedin-talent-hub-integration-with-dynamics-365-human-resources-will-this-integration-continue-to-work-after-the-infrastructure-change-is-completed"></a>Mon organisation utilise l’intégration de LinkedIn Talent Hub avec Dynamics 365 Human Resources. Cette intégration continuera-t-elle à fonctionner une fois le changement d’infrastructure terminé ?

Non, l’intégration de LinkedIn Talent Hub ne fonctionnera pas après la migration vers la nouvelle infrastructure. Le service d’intégration de LinkedIn Talent Hub sera désactivé avec l’infrastructure Dynamics 365 Human Resources existante.

### <a name="my-organization-uses-the-human-resources-app-for-teams-will-the-app-continue-to-work-after-the-infrastructure-change-is-completed"></a>Mon organisation utilise l’application Human Resources pour Teams. L’application continuera-t-elle à fonctionner une fois le changement d’infrastructure terminé ?

Oui, l’intégration de l’application Human Resources pour Teams continuera de fonctionner après la migration vers la nouvelle infrastructure.

### <a name="my-organization-has-configured-custom-security-in-dynamics-365-human-resources-will-our-custom-security-still-be-applied-after-the-infrastructure-change-is-completed"></a>Mon organisation a configuré une sécurité personnalisée dans Dynamics 365 Human Resources. Notre sécurité personnalisée sera-t-elle toujours appliquée une fois le changement d’infrastructure terminé ?

Oui, les configurations de sécurité personnalisées seront incluses dans la migration des données vers la nouvelle infrastructure.

### <a name="we-are-using-data-integrator-to-move-data-between-dynamics-365-human-resources-and-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected"></a>Nous utilisons l’intégrateur de données pour déplacer les données entre Dynamics 365 Human Resources et les applications Finances et Opérations. Comment les données en cours d’intégration seront-elles affectées ?

Les données HR actuellement dans Dynamics 365 Human Resources sont synchronisées avec Dataverse. L’intégrateur de données peut alors être utilisé pour une synchronisation unidirectionnelle avec les applications Finances et Opérations. Après la migration vers la nouvelle infrastructure, les données HR seront natives des applications Finances et Opérations. L’intégrateur de données ne sera plus nécessaire pour synchroniser les données entre les applications Finances et Opérations et Human Resources.

Les tables de données actuelles, natives de Dataverse pour Human Resources, continueront de synchroniser les données de l’environnement avec la nouvelle infrastructure. Les entités seront converties pour prendre en charge la double écriture. Toutes les autres intégrations de données configurées via l’intégrateur de données par rapport à ces tables pour d’autres applications Dynamics 365 continueront de fonctionner telles qu’elles sont actuellement configurées.

### <a name="we-are-using-dual-write-to-move-hr-data-between-dataverse-and-other-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected-by-the-migration-to-the-new-infrastructure"></a>Nous utilisons la double écriture pour déplacer les données HR entre Dataverse et les autres applications Finances et Opérations. Comment les données en cours d’intégration seront-elles affectées par la migration vers la nouvelle infrastructure ?

Les données HR seront natives des applications Finances et Opérations dans l’environnement de la nouvelle infrastructure. La double écriture sera utilisée pour déplacer les données HR entre le nouvel environnement et l’environnement Dataverse.

### <a name="we-have-built-custom-integrations-from-dynamics-365-human-resources-to-one-or-more-external-systems-will-we-have-to-develop-new-integrations-after-the-infrastructure-change-is-completed"></a>Nous avons créé des intégrations personnalisées entre Dynamics 365 Human Resources et un ou plusieurs systèmes externes. Devrons-nous développer de nouvelles intégrations une fois le changement d’infrastructure terminé ?

Cela dépend du point de terminaison d’intégration. Pour plus d’informations sur les technologies d’intégration disponibles dans les applications Finances et Opérations, et sur le choix de la technologie d’intégration la plus adaptée, consultez [Vue d’ensemble de l’intégration](../fin-ops-core/dev-itpro/data-entities/integration-overview.md).

### <a name="we-have-extended-dataverse-for-dynamics-365-human-resources-will-these-extensions-be-migrated-automatically"></a>Nous avons étendu Dataverse pour Dynamics 365 Human Resources. Ces extensions seront-elles migrées automatiquement ?

Si les environnements Dynamics 365 Human Resources et Finances et Opérations qui seront joints à l’environnement dans la nouvelle infrastructure sont connectés au même environnement Dataverse, les deux applications resteront connectées au même environnement Dataverse après la migration. Aucune migration ne sera requise pour aucune extension Dataverse.

Toutefois, si les environnements Dynamics 365 Human Resources et Finances et Opérations sont actuellement connectés à des environnements Dataverse distincts, les deux environnements Dataverse devront être combinés de manière à être connectés à un seul environnement de la nouvelle infrastructure. Pour cette migration de Dataverse, les tables Dataverse qui sont standard dans les solutions Human Resources peuvent être connectées et resynchronisées avec le nouvel environnement Dataverse. Aucune extension de l’environnement Dataverse ne sera migrée automatiquement, mais devra être redéployée dans le nouvel environnement. Nous vous recommandons d’utiliser des solutions gérées pour gérer vos extensions Dataverse. Pour plus d’informations, consultez [Présentation des solutions](/powerapps/developer/data-platform/introduction-solutions).

### <a name="we-have-configured-microsoft-power-automate-flows-andor-microsoft-power-apps-to-work-with-dynamics-365-human-resources-will-these-microsoft-power-platform-components-be-migrated-and-work-automatically-after-the-infrastructure-change-is-completed"></a>Nous avons configuré les flux Microsoft Power Automate et/ou Microsoft Power Apps pour qu’ils fonctionnent avec Dynamics 365 Human Resources. Est-ce que ces composants Microsoft Power Platform seront migrés et fonctionneront-ils automatiquement une fois le changement d’infrastructure terminé ?

Power Apps, les flux Power Automate et les autres personnalisations Microsoft Power Platform sont similaires aux extensions Dataverse. Leur fonctionnement automatique après la migration vers la nouvelle infrastructure dépend du fait que l’application Human Resources et les applications Finances et Opérations sont connectées au même environnement Power Apps avant la migration.

Si les applications sont actuellement connectées au même environnement Power Apps, elles continueront d’être connectées à cet environnement Power Apps après la migration vers la nouvelle infrastructure. Dans ce cas, Power Apps, les flux Power Automate et les autres personnalisations Microsoft Power Platform continueront de fonctionner sans aucune configuration supplémentaire. Nous vous recommandons d’utiliser des solutions gérées pour gérer vos extensions d’applications sur Dataverse. Pour plus d’informations, consultez [Présentation des solutions](/powerapps/developer/data-platform/introduction-solutions).

Cependant, si l’application Human Resources et les applications Finances et Opérations sont connectées à des environnements Power Apps distincts elles devront être combinées dans le cadre de la migration. Cette tâche exigera que toutes les personnalisations Power Apps et autres soient redéployées dans le nouvel environnement.

### <a name="we-have-enabled-dataverse-virtual-tables-for-dynamics-365-human-resources-what-will-happen-to-these-tables-during-the-migration"></a>Nous avons activé les tables virtuelles Dataverse pour Dynamics 365 Human Resources. Qu’adviendra-t-il de ces tables au moment de la migration ?

Après la migration, si l’environnement de la nouvelle infrastructure demeure connecté à l’environnement Dataverse actuellement connecté à Dynamics 365 Human Resources, les tables virtuelles Dataverse qui ont été générées dans cet environnement continueront de fonctionner sans aucune configuration supplémentaire.

Cependant, si l’environnement de la nouvelle infrastructure est connecté à un autre environnement Dataverse après la migration, les tables virtuelles devront être régénérées dans le nouvel environnement Dataverse.

### <a name="we-have-developed-an-integration-by-using-the-applicant-tracking-system-ats-api-payroll-api-dataverse-virtual-tables-for-dynamics-365-human-resources-or-other-entities-in-the-dataverse-web-api-will-these-integrations-continue-to-work-after-the-infrastructure-change-is-completed"></a>Nous avons développé une intégration en utilisant l’API ATS (Applicant Tracking System), l’API de paie, les tables virtuelles Dataverse pour Dynamics 365 Human Resources, ou d’autres entités dans l’APi web Dataverse. Ces intégrations continueront-elles à fonctionner une fois le changement d’infrastructure terminé ?

Après la migration, si l’environnement de la nouvelle infrastructure demeure connecté à l’environnement Dataverse actuellement connecté à Dynamics 365 Human Resources, toutes les intégrations qui auront été développées par rapport à l’API web Dataverse continueront à fonctionner une fois la migration terminée.

Toutefois, si l’environnement de la nouvelle infrastructure demeure connecté à un autre environnement Dataverse après la migration, toutes les intégrations qui auront été développées par rapport à l’API web Dataverse devront être reconfigurées de manière à pouvoir se connecter au nouvel environnement Dataverse.

### <a name="is-there-an-impact-on-the-azure-region-when-my-environment-is-migrated"></a>La migration de mon environnement a-t-elle un impact sur la région Azure ?

Il est prévu que votre environnement Human Resources demeure généralement dans la même région Azure pendant la migration. La seule exception est si l’environnement Human Resources doit être fusionné avec un environnement Finances et Opérations qui se trouve dans une région différente. Dans ce cas, l’environnement Human Resources sera migré vers la région Azure de l’environnement Finances et Opérations.

### <a name="my-organization-depends-on-workflows-in-dynamics-365-human-resources-for-one-or-more-business-processes-will-the-workflows-be-migrated-automatically"></a>Mon organisation dépend de workflows de Dynamics 365 Human Resources pour un ou plusieurs processus métier. Ces workflows seront-ils migrés automatiquement ?

Oui, les configurations de workflow, l’historique des workflows et les workflows en cours seront migrés.

### <a name="what-training-and-resources-will-be-available-to-help-with-the-migration-process"></a>Quelles formations et ressources seront disponibles pour faciliter le processus de migration ?

Une documentation complète sera fournie pour décrire en détail chaque étape du processus de migration. Des ressources de formation supplémentaires, telles que des vidéos et des ateliers, peuvent également être disponibles, en fonction des besoins.

### <a name="my-organization-has-created-saved-views-in-dynamics-365-human-resources-to-improve-the-usability-of-the-interface-will-the-saved-views-be-migrated-automatically"></a>Mon organisation a créé des Vues enregistrées dans Dynamics 365 Human Resources pour améliorer la convivialité de l’interface. Ces vues enregistrées seront-elles migrées automatiquement ?

Oui, les vues enregistrées seront migrées vers la nouvelle infrastructure.

### <a name="we-are-using-ceridian-with-dynamics-365-human-resources-will-the-ceridian-integration-be-available-after-the-infrastructure-change-is-completed"></a>Nous utilisons Ceridian avec Dynamics 365 Human Resources. L’intégration Ceridian sera-t-elle toujours disponible une fois le changement d’infrastructure terminé ? 

L’intégration avec Ceridian sera migrée vers l’intégration basée sur l’API de paie. L’intégration basée sur des fichiers qui existe actuellement dans Dynamics 365 Human Resources ne sera pas migrée vers l’infrastructure Finances et Opérations. Pour plus d’informations, voir [Vue d’ensemble de l’API de paie](./hr-admin-integration-payroll-api-introduction.md).

### <a name="how-will-the-migration-affect-the-service-update-process"></a>Comment la migration affectera-t-elle le processus de mise à jour du service ?

Après la migration, les clients auront beaucoup plus de flexibilité en termes de gestion du cycle de vie des applications (ALM) et de mises à jour des services. Les mises à jour de service ne seront plus appliquées automatiquement aux environnements Human Resources. Au lieu de cela, le service suivra les processus et fonctionnalités de mise à jour de service One Version. Par conséquent, les options de configuration pour les mises à jour seront disponibles via LCS. Pour plus d’informations, voir [Vue d’ensemble de One Version](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="how-will-the-migration-affect-my-lcs-project-for-dynamics-365-human-resources"></a>Comment la migration affectera-t-elle mon projet LCS pour Dynamics 365 Human Resources ?

La migration vers la nouvelle infrastructure déplacera la gestion de vos environnements Dynamics 365 Human Resources vers un projet d’implémentation Finances et Opérations dans LCS. Si la migration fusionne Dynamics 365 Human Resources avec un environnement Finances et Opérations existant, votre projet LCS Human Resources sera fusionné dans le projet d’implémentation LCS pour l’application Finances et Opérations. Si vous utilisez actuellement uniquement Dynamics 365 Human Resources, un nouveau projet d’implémentation LCS sera créé et votre projet LCS Human Resources existant sera migré vers le nouveau projet.

Le nouveau projet sera du même type que celui qu’utilisent les applications Finances et Opérations. Il aura les mêmes caractéristiques et fonctionnalités pour la gestion d’environnement. Pour plus d’informations, voir [Ressources Lifecycle Services](../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

### <a name="we-have-linked-our-task-recordings-to-the-business-process-modeler-in-human-resources-how-will-the-business-process-modeler-be-migrated-and-merged-into-lcs"></a>Nous avons lié nos enregistrements de tâches au Concepteur de processus d’entreprise dans Human Resources. Comment le Concepteur de processus d’entreprise sera-t-il migré et fusionné dans LCS ?

Les bibliothèques de processus métier pour le projet LCS seront migrées vers le nouveau projet LCS pour Human Resources.

### <a name="my-organization-currently-uses-only-dynamics-365-human-resources-what-resources-are-available-so-that-we-can-learn-more-about-the-development-capabilities-after-the-infrastructure-change-is-completed"></a>Mon organisation utilise actuellement uniquement Dynamics 365 Human Resources. Quelles ressources sont disponibles pour que nous puissions en savoir plus sur les possibilités de développement une fois le changement d’infrastructure terminé ?

Les options d’extensibilité de Microsoft Power Platform les options d’extensibilité de Finances et Opérations seront disponibles et pourront être utilisées pour le développement. Pour plus d’informations, consultez [Développer et personnaliser la page d’accueil](../fin-ops-core/dev-itpro/dev-tools/developer-home-page.md).

### <a name="we-have-enabled-features-in-dynamics-365-human-resources-will-these-features-be-enabled-automatically-during-the-migration"></a>Nous avons activé des fonctionnalités dans Dynamics 365 Human Resources. Ces fonctionnalités seront-elles activées automatiquement au moment de la migration ?

L’activation automatique d’une fonctionnalité dans la nouvelle infrastructure sera déterminée individuellement pour chaque fonctionnalité. Ces informations seront incluses dans la documentation des fonctionnalités.

### <a name="what-happens-to-my-byod-database-during-the-migration"></a>Qu’adviendra-t-il de ma base de données BYOD pendant la migration ?

Les configurations d’importation et d’exportation pour votre propre base de données (BYOD) seront migrées vers la nouvelle infrastructure.

### <a name="what-happens-to-my-azure-data-lake-during-the-migration"></a>Qu’adviendra-t-il de mon Azure Data Lake pendant la migration ?

Toute exportation actuellement configurée pour Azure Data Lake Storage dans les applications Finances et Opérations conserveront la même configuration après la migration.

### <a name="we-are-currently-using-dynamics-ax-2012-will-the-upgrade-tools-that-are-currently-available-be-used-to-upgrade-the-hr-module-in-ax-2012-to-dynamics-365-human-resources"></a>Nous utilisons actuellement Dynamics AX 2012. Les outils de mise à niveau actuellement disponibles seront-ils utilisés pour mettre à niveau le module HR de AX 2012 vers Dynamics 365 Human Resources ?

Oui. Dynamics 365 Human Resources sera inclus dans la base de code et l’infrastructure fusionnés pour les applications Finances et Opérations. Une mise à niveau de Dynamics AX 2012 vers Dynamics 365 Human Resources utilisera le même chemin de mise à niveau et les mêmes outils que ceux utilisés pour la mise à niveau vers la dernière version des applications Finances et Opérations.

### <a name="we-use-document-handling-with-dynamics-365-human-resources-what-will-happen-to-the-documents-during-the-migration"></a>Nous utilisons la Gestion des documents avec Dynamics 365 Human Resources. Qu’adviendra-t-il de ces documents au moment de la migration ?

Les documents resteront dans le stockage de documents existant. Ils seront remappés sur l’environnement dans la nouvelle infrastructure.

### <a name="what-happens-to-the-batch-jobs-that-we-have-configured-in-dynamics-365-human-resources-after-the-migration"></a>Qu’adviendra-t-il des tâches de traitement par lots que nous avons configurées dans Dynamics 365 Human Resources après la migration ?

Les tâches de traitement par lots applicables seront migrées automatiquement vers la nouvelle infrastructure.

## <a name="licensing-impact"></a>Impact sur la gestion des licences

Cette documentation n’annule ni ne remplace aucune des documentations légales qui couvrent les droits d’utilisation.

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-does-our-licensing-or-cost-change"></a>Mon organisation utilise Dynamics 365 Human Resources pour gérer ses opérations RH. Nos droits ou nos coûts de licence sont-ils modifiés ?

Les clients qui ont acheté des licences Dynamics 365 Human Resources ne seront pas affectés. Il n’y a pas de migration de licence pour ces clients. L’unité de gestion de stock (SKU) bac à sable supplémentaire qui était spécifique à Human Resources humaines ne sera plus applicable. Au lieu de cela, les clients peuvent choisir d’acheter un bac à sable d’applications Finances et Opérations de niveau 2 à un coût légèrement inférieur. Les clients existants qui ont acheté une unité Human Resources bac à sable seront migrés vers un bac à sable d’application Finances et Opérations de niveau 2 sans frais supplémentaires.

### <a name="my-organization-uses-the-human-resources-module-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-does-my-licensing-or-cost-change"></a>Mon organisation utilise le module Human Resources dans Dynamics 365 Finance, Supply Chain Management, Commerce ou Project Operations. Mes droits ou mes coûts de licence sont-ils modifiés ?

Les utilisateurs existants d’applications Dynamics 365 et les utilisateurs d’applications autonomes Dynamics 365 Finance, Supply Chain Management, Commerce et Project Operations peuvent accéder à Human Resources dans le cadre de ces licences jusqu’en février 2025, ou jusqu’à l’expiration du contrat de licence actuel, selon la première éventualité. Vous pouvez choisir de passer plus tôt à des licences Human Resources si cela vous permet de réaliser de meilleures économies. À partir de février 2025, tous les clients CSP et EA existants doivent abandonner le module HR et acheter des licences Human Resources pour tirer parti des nouvelles fonctionnalités qui sont apportées aux applications Finances et Opérations.

### <a name="my-organization-is-live-with-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-will-we-be-required-to-purchase-an-additional-environment-to-support-the-infrastructure-merge"></a>Mon organisation utilise Dynamics 365 Finance, Supply Chain Management, Commerce ou Project Operations. Serons-nous obligés d’acheter un environnement supplémentaire pour prendre en charge la fusion de l’infrastructure ?

Des environnements supplémentaires ne sont pas nécessaires pour prendre en charge le changement d’infrastructure.

