---
title: Mettre en service Human Resources dans l’infrastructure des applications de finances et d’opérations
description: Cet article explique le processus de provisionnement d’un nouvel environnement de production pour Microsoft Dynamics 365 Human Resources dans l’infrastructure des finances et des opérations.
author: twheeloc
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 15060d8bdd598476081c22d7280319da3db0cb31
ms.sourcegitcommit: 1401d66b6b64c590ca1f8f339d622e922920cf15
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/20/2022
ms.locfileid: "9178408"
---
# <a name="provision-human-resources-in-the-finance-and-operations-infrastructure"></a>Mettre en service Human Resources dans l’infrastructure des applications de finances et d’opérations

_**S’applique à :** Human Resources dans l’infrastructure des applications de finances et d’opérations_ 

> [!NOTE]
> À partir de juillet 2022, les nouveaux environnements de Human Resources ne peuvent plus être approvisionnés sur l’infrastructure autonome de Human Resources, et les nouveaux projets Microsoft Dynamics Lifecycle Services (LCS) ne peuvent pas y être créés. Les clients peuvent déployer des environnements Human Resources sur l’infrastructure des applications de finances et d’opérations.

Cet article explique le processus de provisionnement d’un nouvel environnement de production pour Microsoft Dynamics 365 Human Resources dans l’infrastructure des finances et des opérations.

## <a name="prerequisites"></a>Conditions préalables

Avant de commencer à approvisionner un nouvel environnement, les conditions préalables suivantes doivent être en place :

- Vous avez acheté Human Resources par l’intermédiaire d’un fournisseur de solutions Cloud (CSP) ou dans le cadre d’un contrat d’architecture d’entreprise (EA). Si vous disposez d’une licence Dynamics 365 existante qui inclut déjà le plan de service Human Resources et que vous ne pouvez pas effectuer les étapes décrites dans cet article, contactez le support technique.
- L’administrateur global s’est connecté à [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com) et a créé un projet de finances et d’opérations.

## <a name="provision-a-human-resources-trial-environment"></a>Configuration d’un environnement d’essai Human Resources

> [!NOTE]
> À partir d’avril 2022, les environnements de test de Human Resources ne sont plus disponibles sur l’application autonome. Les clients potentiels qui souhaitent évaluer les capacités de Human Resources dans les applications de finances et d’opérations peuvent le faire en utilisant l’essai gratuit de 30 jours avec les données de démonstration. Dynamics 365 Finance inclura les fonctionnalités de Human Resources intégrées dans l’infrastructure de Finance grâce à la fusion de l’application autonome. Pour plus d’informations, voir [La fusion des offres RH rassemble les capacités des clients](https://cloudblogs.microsoft.com/dynamics365/it/2021/09/15/merging-of-hr-offerings-brings-capabilities-together-for-customers). Pour en savoir plus sur les évaluations Dynamics 365 Finance, consultez le [guide étape par étape](../fin-ops-core/fin-ops/get-started/before-you-buy.md).

## <a name="plan-human-resources-environments"></a>Planifier les environnements Human Resources

Avant de créer votre premier environnement Human Resources, vous devez planifier soigneusement les besoins en environnement de votre projet. Un abonnement de base à l’application Human Resources comprend deux environnements : un environnement de production et un environnement de test de validation standard (sandbox). Selon la complexité de votre projet, vous devrez peut-être acheter des environnements sandbox supplémentaires pour prendre en charge les activités du projet.

Voici quelques considérations aux environnements facultatifs supplémentaires :

- **Migration de données** : pour les activités de migration de données afin de permettre à votre environnement sandbox d’être utilisé à des fins de test tout au long du projet. Le fait de disposer d’un environnement supplémentaire permet aux activités de migration de données de se poursuivre tandis que les activités de test et de configuration se produisent simultanément dans un environnement différent.
- **Intégration** : configurer et tester les intégrations, ce qui peut inclure des intégrations natives telles que les intégrations natives, ou des intégrations personnalisées telles que celles pour la paie, les systèmes de suivi des candidatures ou les régimes et les fournisseurs de prestations.
- **Formation** : vous pouvez avoir besoin d’un environnement distinct configuré avec un ensemble de données de formation afin de former vos employés à l’utilisation du nouveau système. 
- **Projet en plusieurs phases** : vous pouvez avoir besoin d’un environnement supplémentaire pour prendre en charge la configuration, la migration des données, les tests ou d’autres activités dans une phase de projet qui est planifiée après la mise en service initiale du projet.
- **Développement** : dans l’infrastructure des finances et des opérations, vous pouvez désormais étendre la solution et développer vos propres personnalisations. Chaque développeur doit utiliser son propre environnement de développement. Pour en savoir plus, voir [Déployer des environnements de développement et y accéder](/fin-ops-core/dev-itpro/dev-tools/access-instances).
- **GOLD** : pour les nouveaux déploiements, une pratique courante consiste à utiliser un environnement GOLD distinct qui reste vierge pour la configuration et la migration des données. Cet environnement peut être utilisé tout au long de l’implémentation pour actualiser d’autres environnements. Il sera utilisé pour créer l’environnement de production qui a la configuration de base et la migration des données. Vous ne pouvez pas déployer un environnement de production sur l’infrastructure de finances et d’opérations tant que vous n’avez pas terminé le processus de préparation à la mise en service. Pour plus d’informations, voir [Préparation au lancement](/fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live).

<!--NOTE: Need to come back and verify Tier-1 can be used and if a customer cannot purchase tier 3-5 need specific documentation about this.-->

> [!IMPORTANT]
> En tenant compte de vos environnements, nous vous recommandons l’approche suivante :
>
> - Utilisez votre environnement de test d’acceptation standard par défaut (anciennement Sandbox) ou un autre environnement pour effectuer une simulation de basculement avant votre mise en service.
> - Conservez une liste de contrôle de basculement détaillée qui inclut chacun des packages de données requis pour migrer les données finales dans l’environnement de production au moment de la mise en service. Cette recommandation est particulièrement importante si vous ne disposez pas d’un environnement GOLD distinct pour stocker vos configurations.
> - Utilisez votre environnement de test d’acceptation standard par défaut (anciennement Sandbox) ou un autre environnement de niveau 2 ou supérieur comme environnement de TEST tout au long de votre projet. Si vous avez besoin d’environnements supplémentaires, votre organisation peut les acheter moyennant un coût supplémentaire.

## <a name="create-an-lcs-project"></a>Créer un projet LCS

Pour utiliser LCS pour gérer vos environnements Human Resources, vous devez d’abord créer un projet LCS. Si vous migrez votre environnement de Human Resources vers l’infrastructure des finances et des opérations, vous devez créer un projet LCS pour les applications de finances et d’opérations. Pour plus d’informations, voir [Migrer votre environnement Human Resources](hr-admin-migrate-overview). Si vous avez déjà un projet LCS pour d’autres applications de finances et d’opérations, vous pouvez activer les fonctionnalités de Human Resources dans l’espace de travail **Gestion des fonctionnalités**. Pour plus d’informations, voir [Vue d’ensemble de la gestion des fonctionnalités](/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Lorsqu’un nouveau client s’inscrit à Human Resources, l’abonnement inclut un espace de travail de projet de mise en œuvre. Une fois que le client a activé le service, l’administrateur du client doit se connecter à <https://lcs.dynamics.com> en utilisant le compte client. L’espace de travail du projet est automatiquement créé pour l’organisation. Pour plus d’informations, voir [Lifecycle Services (LCS) pour les clients des applications de finances et d’opérations](/fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs).

> [!NOTE]
> Pour garantir un provisionnement réussi, le compte que vous utilisez pour provisionner l’environnement Human Resources doit être affecté au rôle **Administrateur système** ou au rôle **Personnalisateur du système** dans l’environnement Power Apps associé à l’environnement Human Resources. Pour plus d’informations sur l’affectation de rôles de sécurité aux utilisateurs dans Microsoft Power Platform, voir [Configurer la sécurité utilisateur sur les ressources](/power-platform/admin/database-security).

Vous devez terminer le processus d’intégration du projet LCS avant de pouvoir commencer à déployer des environnements. Pour plus d’informations, voir [Intégration du projet](/fin-ops-core/dev-itpro/lifecycle-services/project-onboarding). Pour plus d’informations sur l’utilisation de LCS, voir [Guide de l’utilisateur de Lifecycle Services (LCS)](/fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide).

## <a name="deploy-human-resources-environments"></a>Déployer les environnements Human Resources

Le déploiement d’applications de finances et d’opérations, y compris Human Resources, dans le cloud nécessite que vous compreniez l’environnement et l’abonnement que vous déployez, qui peut effectuer quelles tâches, et quelles données et personnalisations vous devez gérer. Nous vous recommandons d’utiliser un compte de service au lieu d’un utilisateur nommé lorsque vous déployez de nouveaux environnements. Pour plus d’informations sur le déploiement d’environnements sur l’infrastructure de finances et d’opérations, voir [Vue d’ensemble du déploiement cloud](/fin-ops-core/dev-itpro/deployment/cloud-deployment-overview).

Pour déployer un environnement de production pour Human Resources sur l’infrastructure de finances et d’opérations, vous devez terminer processus de préparation à la mise en service. Pour plus d’informations, voir [Préparation au lancement](/fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live). Ce processus inclut l’estimateur d’abonnement dans LCS. Pour plus d’informations, voir [Estimateur d’abonnement](/fin-ops-core/dev-itpro/lifecycle-services/subscription-estimator).

## <a name="integrate-microsoft-power-platform-with-human-resources"></a>Intégrer Microsoft Power Platform à Human Resources

Microsoft Power Platform fournit une suite de fonctionnalités pour les applications Dynamics 365 via le centre d’administration Power Platform. Vous pouvez intégrer et étendre l’utilisation des données de Human Resources à l’aide de Microsoft Power Platform. Pour plus d’informations sur l’intégration de Human Resources à Microsoft Power Platform, voir [Intégration de Microsoft Power Platform aux applications de finances et d’opérations](/fin-ops-core/dev-itpro/power-platform/overview).

## <a name="supported-geographies"></a>Zones géographiques prises en charge

Pour plus d’informations sur les langues et les zones géographiques prises en charge pour Human Resources, voir [Conçu pour le monde entier : découvrez les pays et les langues pris en charge](https://dynamics.microsoft.com/availability-reports/).

## <a name="grant-access-to-the-environment"></a>Autoriser l’accès à l’environnement

Par défaut, l’administrateur global ayant créé l’environnement y a accès. Vous devez explicitement autoriser l’accès à d’autres utilisateurs d’application. Vous devez ajouter des utilisateurs et leur affecter les rôles appropriés dans l’environnement Human Resources. Pour plus d’informations, voir [Création de nouveaux utilisateurs](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) et [Affecter des utilisateurs à des rôles de sécurité](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles).

## <a name="additional-resources"></a>Ressources supplémentaires
Vous pouvez en savoir plus sur l’utilisation et la gestion de projets dans LCS sur l’infrastructure des applications de finances et d’opérations en utilisant les ressources suivantes :

- [Ressources Lifecycle Services](/fin-ops-core/dev-itpro/lifecycle-services/lcs.md)
- [Guide de l’utilisateur de Lifecycle Services (LCS)](/fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md)
- [Vue d’ensemble de Déploiement libre-service](../fin-ops-core/dev-itpro/deployment/infrastructure-stack.md)
- [Page d’accueil des opérations de mouvement de base de données](../fin-ops-core/dev-itpro/database/dbmovement-operations.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
