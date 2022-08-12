---
title: FAQ sur la migration client Human Resources
description: Cet article répond aux questions fréquemment posées sur la migration de Microsoft Dynamics 365 Human Resources vers l’infrastructure fusionnée des applications de finances et d’opérations.
author: twheeloc
ms.date: 07/06/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8a6f883da07bd1d3a6b0379f1582dc8556e166ff
ms.sourcegitcommit: 9310c943ac76896663e5604209034da9f8d6139c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151080"
---
# <a name="human-resources-customer-migration"></a>Migration client Human Resources

## <a name="how-should-dynamics-365-human-resources-customers-plan-to-move-to-the-finance-and-operations-infrastructure"></a>Comment les clients Dynamics 365 Human Resources doivent-ils envisager la transition vers l’infrastructure de finances et d’opérations ?

Deux catégories de clients Microsoft Dynamics 365 Human Resources seront affectés et devront apporter des modifications pour s’assurer qu’ils utilisent la dernière infrastructure de finances et d’opérations :

- Les clients qui utilisent Dynamics 365 Human Resources et n’ont pas d’autres applications d’opérations de Dynamics 365
- Les clients qui utilisent Dynamics 365 Human Resources et Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce ou Dynamics 365 Project Operations

Quelle que soit la catégorie à laquelle ils appartiennent, les clients devront déplacer les données dans un environnement nouvellement créé sur l’infrastructure de finances et d’opérations et valider que la fusion a été effectuée avec succès.

À l’avenir, l’application Dynamics 365 Human Resources disposera de son propre environnement de finances et d’opérations, distinct des autres applications d’exploitation. De cette façon, les clients pourront profiter des options d’extensibilité sans avoir à fusionner leurs données actuelles. Microsoft fournira des outils et un environnement sandbox que les clients pourront utiliser pour tester et valider la migration des données avant de passer à un environnement de production. L’outillage permettra un processus quasi automatisé et sera disponible entre août et novembre 2022.

Les clients qui utilisent d’autres applications sur l’infrastructure de finances et d’opérations auront la possibilité de fusionner leurs données de ressources humaines avec un environnement existant. 

## <a name="when-will-customers-be-moved-to-the-finance-and-operations-infrastructure"></a>Quand la transition des clients vers l’infrastructure de finances et d’opérations sera-t-elle effective ?

La migration de chaque entreprise dépendra de sa configuration actuelle et de sa capacité à migrer vers la nouvelle infrastructure de finances et d’opérations. Nous recommandons aux clients de travailler avec leur partenaire Microsoft pour déterminer la meilleure voie à suivre.

- Les organisations qui utilisent le module **Human Resources** dans Dynamics 365 Finance pourront activer de nouvelles fonctionnalités à partir de Dynamics 365 Human Resources dans le cadre du processus de mise à jour régulier de One Version. De nouvelles fonctionnalités sont prévues en disponibilité générale à partir de janvier 2022.
- Les organisations qui utilisent Dynamics 365 Human Resources auront accès à des outils qu’ils pourront utiliser pour réaliser la fusion de l’infrastructure. Microsoft travaillera avec les clients sur la transition, pour aider à prévenir toute interruption de service. Les clients disposeront de 12 à 18 mois pour effectuer la transition, à partir du moment où l’outil de migration sera disponible.
- Les organisations qui utilisent Dynamics 365 Human Resources et le module **Human Resources** peuvent migrer leur infrastructure Human Resources autonome vers l’infrastructure de finances et d’opérations. Une autre option consiste à utiliser l’outil de fusion pour regrouper les environnements dans un environnement unique. Il n’y a aucune exigence ou délai pour fusionner les deux environnements.

Pour des informations à jour, consultez régulièrement les [Programmes de lancement](/dynamics365/release-plans/).

## <a name="will-customers-still-need-custom-integrations-between-dynamics-365-human-resources-and-the-human-resources-module"></a>Les clients auront-ils encore besoin d’intégrations personnalisées entre Dynamics 365 Human Resources et le module Human Resources ?

- Les clients qui utilisent Dynamics 365 Human Resources et d’autres environnements d’infrastructure de finances et d’opérations actuellement intégrés devront continuer à intégrer les deux environnements après la fusion.
- Les clients qui choisissent de conserver leur environnement Dynamics 365 Human Resources à part de leur environnement d’application de finances et d’opérations existant devront continuer à intégrer les environnements pour rendre les données disponibles dans les deux environnements.
- Les clients peuvent continuer à utiliser l’intégrateur de données pour copier des données entre les deux environnements. Les clients qui fusionnent des données dans un environnement unique après la migration n’auront plus à intégrer les données, car toutes les données seront dans une seule base de données.

## <a name="will-customer-isv-solutions-automatically-be-migrated"></a>Nos solutions ISV client seront-elles migrées automatiquement ?

L’expérience de migration pour chaque solution d’éditeur de logiciels indépendant (ISV) variera en fonction de la méthode d’intégration de la solution. Microsoft travaillera en étroite collaboration avec les ISV pour assurer une transition fluide vers la nouvelle infrastructure de finances et d’opérations. De nombreuses solutions ISV reposent sur Dataverse en utilisant les fonctionnalités de Microsoft Power Platform. Ces solutions dépendent de l’intégration Dataverse entre l’environnement Dynamics 365 Human Resources et l’environnement Dataverse. L’intégration Dataverse est obsolète dans le cadre de la fusion de l’infrastructure. Dans l’infrastructure de finances et d’opérations, de nouvelles cartes en double écriture devraient remplacer la fonctionnalité de l’intégration Dataverse.

## <a name="how-will-the-data-integrator-that-moves-data-between-dynamics-365-human-resources-and-other-dynamics-365-apps-be-affected"></a>Comment l’intégrateur de données qui migre les données entre Dynamics 365 Human Resources et d’autres applications Dynamics 365 est-il impacté ?

Une fois que les clients sont passés à l’infrastructure de finances et d’opérations, ils devront continuer à intégrer les données entre les deux environnements. Les clients peuvent continuer à utiliser l’intégrateur de données pour effectuer ces tâches de migration de données. Les clients qui prévoient de conserver leur environnement Dynamics 365 Human Resources à part de leur environnement d’application de finances et d’opérations existant devront continuer à intégrer les données dans les deux environnements. Pour les clients qui fusionnent les deux environnements en un seul, l’intégration entre les deux environnements ne sera plus nécessaire.

## <a name="how-will-data-be-moved-between-dynamics-365-human-resources-on-the-finance-and-operations-infrastructure-and-dataverse-after-the-migration"></a>Comment les données passeront-elles entre Dynamics 365 Human Resources sur l’infrastructure de finances et d’opérations et Dataverse après la migration ?

L’intégration Dataverse actuelle entre Dynamics 365 Human Resources et Dataverse est en cours d’abandon dans le cadre de l’infrastructure de finances et d’opérations. Des cartes en double écriture devraient mapper les entités de finances et d’opérations vers les tables Dataverse. Les clients devront décider quelles cartes en double écriture sont nécessaires pour leur mise en œuvre. Nous recommandons d’utiliser des tables virtuelles pour les intégrations et les solutions ISV, à moins qu’il n’y ait un besoin commercial spécifique pour que les données soient dupliquées dans Dataverse pour exécuter la logique métier.

## <a name="how-does-the-migration-affect-dataverse-extensions-for-dynamics-365-human-resources"></a>Comment la migration affecte-t-elle les extensions Dataverse pour Dynamics 365 Human Resources ?

Les clients devront migrer vers un environnement sandbox avant de migrer leur environnement de production. Lorsque les clients migrent leur environnement sandbox, ils doivent créer une copie de leur environnement Dataverse pour se connecter au nouvel environnement migré de finances et d’opérations. Nous recommandons à un client de copier à la fois les données et les solutions pour l’environnement, afin qu’elles correspondent à l’environnement de production actuel du client.

Lorsque les clients sont prêts à migrer leur environnement de production Dynamics 365 Human Resources, Microsoft migrera automatiquement la base de données et le stockage Azure Blob. La base de données et le stockage ayant fait l’objet de la migration désigneront le nouvel environnement sur l’infrastructure de finances et d’opérations vers le même environnement de production Dataverse. Avant que les données puissent continuer à être copiées vers Dataverse, les clients devront activer toutes les cartes en double écriture requises pour leurs intégrations, extensions et solutions ISV basées sur Dataverse.

## <a name="will-microsoft-power-platform-components-that-were-built-for-dynamics-365-human-resources-automatically-work-after-the-infrastructure-migration-is-completed"></a>Est-ce que ces composants Microsoft Power Platform conçus pour Dynamics 365 Human Resources fonctionneront-ils automatiquement une fois la migration de l’infrastructure terminée ?

Les applications créées dans Power Apps, les flux créés dans Power Automate et autres personnalisations Microsoft Power Platform sont similaires aux extensions Dataverse. Lors de la migration des environnements de production des clients, il n’y a aucun impact sur les environnements Dataverse, y compris les extensions. Les applications, les flux et autres personnalisations de Power Microsoft Platform doivent continuer à fonctionner sans nécessiter de configuration supplémentaire.

## <a name="what-will-happen-to-dataverse-virtual-table-entities-for-dynamics-365-human-resources-during-the-migration"></a>Qu’adviendra-t-il de ces entités de table virtuelle Dataverse pour Dynamics 365 Human Resources au moment de la migration ?

Lorsque les clients migrent leur environnement Dynamics 365 Human Resources vers l’infrastructure de finances et d’opérations, l’environnement restera connecté à l’environnement Dataverse actuellement connecté à Dynamics 365 Human Resources. Les tables virtuelles Dataverse qui ont été générées dans l’environnement continueront de fonctionner sans nécessiter de configuration supplémentaire. Les tables virtuelles devront peut-être être régénérées dans l’environnement Dataverse qui est connecté à un environnement de finances et d’opérations existant d’un client.

## <a name="how-will-an-integration-that-uses-the-applicant-tracking-system-ats-api-payroll-api-dataverse-virtual-tables-for-dynamics-365-human-resources-or-other-entities-in-the-dataverse-web-api-work-after-the-infrastructure-merge-is-completed"></a>Comment une intégration qui utilise l’API du système de suivi des candidats (ATS), l’API de la paie, les tables virtuelles Dataverse pour Dynamics 365 Human Resources, ou d’autres entités de l’API web Dataverse fonctionne-t-elle une fois la fusion de l’infrastructure terminée ?

Lorsque les clients migrent leur environnement Dynamics 365 Human Resources vers l’infrastructure de finances et d’opérations, l’environnement restera connecté à l’environnement Dataverse actuellement connecté à Dynamics 365 Human Resources. Toutes les intégrations qui ont été développées par rapport à l’API web Dataverse continuera de fonctionner une fois la migration terminée.

## <a name="our-organization-has-configured-custom-security-in-dynamics-365-human-resources-will-it-still-be-applied-after-the-infrastructure-migration-is-completed"></a>Notre organisation a configuré une sécurité personnalisée dans Dynamics 365 Human Resources. Sera-t-elle toujours appliquée une fois la migration d’infrastructure terminé ?

Oui, les configurations de sécurité personnalisées seront incluses dans la migration des données.

## <a name="will-workflows-in-dynamics-365-human-resources-automatically-be-migrated"></a>Ces workflows dans Dynamics 365 Human Resources seront-ils migrés automatiquement ?

Oui, les configurations de workflow, l’historique des workflows et les workflows en cours seront migrés vers l’infrastructure fusionnée.

## <a name="will-saved-views-in-dynamics-365-human-resources-automatically-be-migrated"></a>Ces vues enregistrées seront-elles migrées automatiquement dans Dynamics 365 Human Resources ?

Oui, les vues enregistrées seront migrées vers l’infrastructure fusionnée.

## <a name="will-features-that-are-enabled-in-dynamics-365-human-resources-automatically-be-available-after-the-infrastructure-merge"></a>Les fonctionnalités activées dans Dynamics 365 Human Resources seront-elles disponibles après la fusion de l’infrastructure ?

- Pour les clients qui utilisent le module **Human Resources**, les fonctionnalités disponibles uniquement dans Dynamics 365 Human Resources seront gérées via la gestion des fonctionnalités. Habituellement, ces fonctionnalités ne seront pas activées par défaut. Toutes les fonctionnalités qui doivent être activées par défaut seront documentées.
- Pour les clients qui utilisent Dynamics 365 Human Resources, les fonctionnalités seront disponibles dans l’infrastructure. Toutes les fonctionnalités qui ne sont pas disponibles seront documentées. Chaque clé de gestion des fonctionnalités activée dans l’environnement Dynamics 365 Human Resources actuel sera activée dans l’infrastructure fusionnée. Pour plus d’informations, voir [Vue d’ensemble de la gestion des fonctionnalités](/fin-ops/get-started/feature-management-overview.md).

## <a name="what-happens-to-byod-databases-during-the-migration"></a>Qu’adviendra-t-il de mes bases de données BYOD pendant la migration ?

Les configurations d’importation et d’exportation pour votre propre base de données (BYOD) seront migrées vers l’infrastructure de finances et d’opérations.

## <a name="is-there-an-impact-on-the-azure-region-when-the-customer-environment-is-migrated"></a>La migration de l’environnement client a-t-elle un impact sur la région Azure ?

L’environnement Dynamics 365 Human Resources restera dans la même région Azure pour la migration. S’il est nécessaire de déplacer un environnement vers une autre région Azure, les clients devront suivre les étapes standard pour migrer vers une nouvelle région une fois la migration terminée.

## <a name="what-happens-to-azure-data-lakes-during-the-migration"></a>Qu’adviendra-t-il des lacs de données Azure pendant la migration ?

Toute exportation actuellement configurée pour Azure Data Lake dans les applications de finances et d’opérations conserveront la même configuration après la migration.

> [!NOTE]
> Les cartes en double écriture devront être activées pour continuer à écrire des données de l’environnement Human Resources dans Dataverse.

Les clients qui souhaitent exporter des données Human Resources vers le lac de données peuvent activer cette fonctionnalité une fois la migration vers l’infrastructure des finances et des opérations terminée. Pour plus d’informations, voir [Lacs de données – Centre des architectures Azure](/azure/architecture/data-guide/scenarios/data-lake).

Les clients peuvent relier plusieurs environnements de finances et d’opérations au même lac de données. Cependant, chaque environnement pointera vers un dossier et un conteneur différents. Les clients qui envisagent de fusionner des environnements ultérieurement doivent soigneusement planifier leur approche.
 
## <a name="what-migration-will-be-required-if-a-customer-is-currently-using-the-human-resources-module"></a>Quelle migration sera nécessaire si un client utilise actuellement le module Human Resources ?

Les clients qui utilisent le module **Human Resources** auront la nouvelle fonctionnalité de fonction de Dynamics 365 Human Resources appliquée à leur environnement via le processus de mise à jour standard One Version. Les clients peuvent s’attendre à voir les nouvelles fonctionnalités dans leur environnement dès leur disponibilité dans les mises à jour. Les clients peuvent utiliser la gestion des fonctionnalités pour activer les fonctionnalités. Les clients doivent planifier la validation de ces nouvelles fonctionnalités à l’aide des processus qu’ils ont déjà mis en place et utiliser pour valider d’autres mises à jour de leur environnement.

## <a name="what-will-happen-to-custom-integrations-to-external-systems"></a>Qu’adviendra-t-il des intégrations personnalisées à des systèmes externes ?

Les clients devront migrer leurs intégrations vers l’environnement de finances et d’opérations. Étant donné que le point de terminaison de cet environnement est différent, les clients peuvent être amenés à mettre à jour ou à modifier les intégrations afin qu’elles pointent vers le nouvel environnement. Cette tâche sera principalement un processus manuel et les modifications requises dépendront de l’architecture de l’intégration. Les clients doivent travailler avec leur partenaire Microsoft pour déterminer la meilleure approche pour déplacer les intégrations.

## <a name="what-will-happen-to-microsoft-power-platform-dataverse-extensions-if-customers-merge-a-dynamics-365-human-resources-environment-with-an-existing-finance-and-operations-environment"></a>Qu’adviendra-t-il des extensions Microsoft Power Platform (Dataverse) si les clients fusionnent un environnement Dynamics 365 Human Resources avec un environnement de finances et d’opérations existant ?

Si les clients décident de fusionner un environnement Dynamics 365 Human Resources et un environnement de finances et d’opérations existant en une seule instance Dataverse après la migration, leurs environnements Dataverse doivent être combinés dans le cadre du processus de fusion. Cette tâche exigera que toutes les applications créées avec Power Apps et autres personnalisations soient redéployées dans le nouvel environnement.

## <a name="what-will-happen-to-documents-during-the-migration"></a>Qu’adviendra-t-il de ces documents au moment de la migration ?

Lorsque les clients migrent leur environnement Dynamics 365 Human Resources vers l’infrastructure de finances et d’opérations, les documents resteront dans le stockage de documents existant et seront automatiquement mappés au nouvel environnement dans l’infrastructure de finances et d’opérations.

Dans une version ultérieure, de nouvelles entités de données seront fournies. Une fois ce changement effectué, les clients qui choisissent de fusionner leur environnement Dynamics 365 Human Resources avec un environnement de finances et d’opérations existant sera alors en mesure d’exporter des documents et de les déplacer dans l’environnement existant.

## <a name="after-the-migration-what-happens-to-the-batch-jobs-that-were-configured-in-dynamics-365-human-resources"></a>Après la migration, qu’advient-il des tâches de traitement par lots qui ont été configurées dans Dynamics 365 Human Resources ?

Les tâches par lots devront être reconfigurées dans l’environnement de finances et d’opérations. Les clients devront évaluer chaque tâche par lots et la comparer à la liste actuelle des tâches par lots dans l’environnement de finances et d’opérations. Les clients doivent également analyser la planification globale des lots lorsqu’ils fusionnent les deux ensembles de tâches par lots, afin de déterminer si des modifications doivent être apportées à la planification des lots, aux priorités ou aux groupes de lots.

## <a name="how-will-the-migration-affect-the-lcs-project-for-dynamics-365-human-resources"></a>Comment la migration affectera-t-elle le projet LCS pour Dynamics 365 Human Resources ?

Les clients devront créer un nouveau projet Microsoft Dynamics Lifecycle Service (LCS), et ils devront sélectionner des applications de finances et d’opérations comme produit et **Implémentation** comme type de projet. De plus, un nouveau champ pour le type de sous-projet est disponible lorsqu’un projet LCS est créé. Les clients devront sélectionner l’option pour la migration Dynamics 365 Human Resources pour migrer un projet LCS Human Resources existant vers l’infrastructure de finances et d’opérations.

Les caractéristiques des projets LCS de finances et d’opérations diffèrent des caractéristiques des projets LCS Human Resources.

Pour être mis en ligne, les nouveaux clients devront effectuer les tâches suivantes :

- Terminer l’intégration du projet.
- Compléter la méthodologie.
- Remplir un estimateur d’abonnement.
- Terminer le processus de préparation à la mise en service.

## <a name="how-will-the-business-process-modeler-be-migrated"></a>Comment le concepteur de processus d’entreprise sera-t-il migré ?

Les clients devront exporter leur bibliothèque de concepteur de processus d’entreprise à partir du projet LCS Human Resources et l’importer dans le projet LCS de finances et d’opérations. De plus, les clients devront mettre à jour les paramètres d’aide dans l’application afin qu’ils pointent vers le nouveau projet LCS.

## <a name="how-will-the-service-update-process-be-affected-by-the-migration"></a>Comment le processus de mise à jour du service sera-t-il affecté par la migration ?

Après la migration, les clients auront beaucoup plus de flexibilité pour Application Lifecycle Management (ALM) et les mises à jour des services. Les mises à jour de service ne seront plus appliquées automatiquement aux environnements Human Resources. Au lieu de cela, le service suivra les processus et fonctionnalités de mise à jour du service One Version, et les options de configuration pour les mises à jour via LCS seront activées.

## <a name="will-customers-be-eligible-for-fasttrack-assistance-with-the-infrastructure-merge"></a>Les clients seront-ils éligibles à l’assistance FastTrack avec la fusion de l’infrastructure ?

Microsoft est toujours en train de définir quels outils et ressources seront disponibles auprès de FastTrack pour aider à la fusion.

## <a name="licensing-impact"></a>Impact sur la gestion des licences

Pour plus d’informations sur la façon dont les licences sont impactées, voir [FAQ sur la fusion de l’infrastructure Dynamics 365 Human Resources](hr-infrastructure-merge-faq.md#licensing-impact).
