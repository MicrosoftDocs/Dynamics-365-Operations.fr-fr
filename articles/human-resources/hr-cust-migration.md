---
title: Migration client de Dynamics 365 Human Resources vers l’infrastructure des finances et des opérations
description: Cet article décrit la migration par le client de Microsoft Dynamics 365 Human Resources vers l’infrastructure des finances et des opérations.
author: twheeloc
ms.date: 10/25/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4df9a68ea0128378224bf77bd66423fd2e13fa55
ms.sourcegitcommit: e5b290bac7e8f468167caa1a5607aac6eac9aaea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2022
ms.locfileid: "9760360"
---
# <a name="dynamics-365-human-resources-customer-migration"></a>Migration par le client de Dynamics 365 Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

La migration client est une migration « lift-and-shift » (déplacement) d’une base de données client vers l’infrastructure des finances et des opérations. Des outils de migration automatisés sont utilisés pour cela. Le résultat est un nouvel environnement de finances et d’opérations qui utilise la base de données Human Resources du client.

## <a name="prerequisites"></a>Conditions préalables

### <a name="user-access-and-permissions"></a>Accès et autorisations utilisateur

- L’utilisateur de Microsoft Dynamics Lifecycle Services doit avoir le rôle **Administrateur d’organisation**.
- L’utilisateur doit pouvoir [créer des projets Azure DevOps](/azure/devops/organizations/projects/create-project) ou utiliser un projet Azure DevOps existant.
- L’utilisateur doit avoir l’accès nécessaire pour [créer un Jeton de sécurité d’accès personnel Azure DevOps](/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate), ou doit avoir un jeton disponible à utiliser.

### <a name="dataverse-environment-backup-sandbox"></a>Sauvegarde d’un environnement Dataverse (bac à sable)

 - Facultatif mais recommandé : actualisez l’environnement bac à sable Human Resources existant à l’aide d’une copie de l’environnement de production Human Resources.
 - Créez un nouvel environnement Dataverse à l’aide du centre d’administration Power Platform.
 - Copiez l’environnement Dataverse existant, qui est lié à l’application autonome Human Resources, vers l’environnement que vous avez créé à l’étape précédente.

> [!NOTE]
> Lorsque vous ajoutez une base de données, assurez-vous que l’option **Activer les applications Dynamics 365** est définie sur **Oui**. Pour des informations détaillées, voir [Préparer un environnement Power Platform](hr-cust-migration.md#prepare-a-power-platform-environment)

### <a name="dataverse-capacity"></a>Capacité Dataverse

1. Utilisez la page **Résumé** dans le centre d’administration Power Platform pour vérifier que le [stockage Dataverse](/power-platform/admin/finance-operations-storage-capacity) a suffisamment de capacité disponible pour la copie de l’environnement.
2. S’il n’y a pas assez de capacité disponible, suivez les [conseils pour libérer de l’espace de stockage](/power-platform/admin/free-storage-space) pour réduire la consommation globale. Les clients peuvent également [ajouter une capacité de stockage supplémentaire](/power-platform/admin/add-storage).

## <a name="customer-migration-process"></a>Processus de migration client

### <a name="create-a-lifecycle-services-project-for-human-resources-migration"></a>Créer un projet Lifecycle Services pour la migration de Human Resources

La première étape consiste à créer un nouveau projet Implémentation des finances et des opérations dans Lifecycle Services. Le client aura un projet Lifecycle Services Human Resources existant. Les environnements Human Resources existants seront migrés vers le nouveau projet Implémentation des finances et des opérations.

Pour créer un projet, procédez comme suit.

1. Connectez-vous à Lifecycle Services en tant qu’administrateur général ou utilisateur du compte de service désigné.
2. Sur la page d’accueil de Lifecycle Services, sélectionnez **Créer/Nouveau (+)**.
3. Sélectionnez les applications de finances et d’opérations comme produit.
4. Dans le champ **Objectif du projet**, sélectionnez **Implémentation**.
5. Entrez un nom et une description pour le projet.
6. Dans le champ **Type de projet personnalisé**, sélectionnez **Migration de Microsoft Dynamics 365 Human Resources**.
7. Cochez la case pour accepter les conditions générales.
8. Cliquez sur **Créer**.

Une fois que vous avez créé un nouveau projet Lifecycle Services, procédez comme suit pour le configurer.

1. Sélectionnez **Intégration de projet** pour terminer l’intégration du projet. Pour plus d’informations, voir [Intégration du projet](../fin-ops-core/dev-itpro/lifecycle-services/project-onboarding.md).

    - Sélectionnez la même région que vos environnements actuels. Cette sélection n’affectera pas la migration.
    - Pour les anciens systèmes, sélectionnez **Autre**.

2. Renseignez les paramètres du projet. Dans le cadre de cette étape, vous devez configurer la Bibliothèque SharePoint Online, Azure DevOps, et les connexions Azure si elles sont nécessaires. Pour plus d’informations, voir [Guide d’utilisation de Lifecycle Services (LCS)](../dev-itpro/lifecycle-services/lcs-user-guide.md).

> [!NOTE]
> Les clients peuvent utiliser un projet Azure DevOps existant et le jeton de sécurité d’accès personnel associé. Si un projet existant est utilisé, les configurations liées au projet sont automatiquement disponibles et il est possible d’examiner leur exactitude.

### <a name="migrate-a-human-resources-sandbox-environment"></a>Migration d’un environnement Human Resources bac à sable

#### <a name="prepare-to-migrate-the-sandbox-environment"></a>Préparer la migration de l’environnement bac à sable

Une fois qu’un nouveau projet Lifecycle Services a été créé et que le processus d’intégration du projet est terminé, vous êtes prêt à migrer votre premier environnement. Avant de commencer ce processus, nous vous recommandons d’actualiser l’environnement bac à sable que vous souhaitez migrer depuis votre environnement de production vers l’infrastructure autonome.

#### <a name="prepare-a-power-platform-environment"></a>Préparation d’un environnement Power Platform

> [!NOTE]
> Cette étape ne s’applique qu’à la migration des environnements bac à sable. Lorsque vous migrez l’environnement de production, l’environnement du centre d’administration Power Platform existant qui est attaché à l’environnement de production sera transféré. Lorsque vous ajoutez une base de données, vérifiez que le bouton **Activer les applications Dynamics 365** est défini sur **Oui**. 

- Dans le centre d’administration Power Platform, [créez un environnement avec une base de données](/power-platform/admin/create-environment#create-an-environment-with-a-database) à utiliser pour la migration de bac à sable ou sélectionnez un environnement existant.
- [Copiez un environnement](/power-platform/admin/copy-environment) pour actualiser l’environnement Power Platform utilisé pour le mappage.

#### <a name="migrate-the-sandbox-environment"></a>Migration de l’environnement bac à sable

1. Connectez-vous à Lifecycle Services en tant qu’administrateur général ou utilisateur du compte de service désigné.

    > [!NOTE]
    > Nous vous recommandons d’utiliser un compte utilisateur nommé. L’utilisateur connecté doit disposer du rôle de sécurité **Propriétaire du projet** ou **Gestionnaire d’environnement** dans le projet autonome Lifecycle Services de Human Resources.

2. Ouvrez le projet de migration Human Resources nouvellement créé.
3. Examinez et terminer les phases appropriées de la méthodologie de migration et de l’intégration du projet.
4. Sur le tableau de bord du projet, dans le volet **Par défaut : test d’acceptation standard**, sélectionnez **Migrer HR**.
5. Dans le volet **Sélectionnez l’environnement à migrer**, sélectionnez le projet Lifecycle Services approprié et l’environnement Human Resources d’origine (à partir de votre application Human Resources autonome source).
6. Activez **Mapper sur le nouvel environnement Power Platform** et sélectionnez l’environnement Power Platform approprié. Cliquez ensuite sur **Suivant**.
7. Suivez l’assistant **Paramètres de déploiement (finances et opérations – bac à sable)** pour confirmer les détails et la signature du client, puis sélectionnez **Déployer**.

L’état de l’environnement montrera la progression. L’état passera de **Chargement en cours** à **Déploiement en cours** à **Déployé**.

> [!NOTE]
> Le volet de production ne sera pas disponible tant que la liste de contrôle de préparation du projet de mise en service ne sera pas terminée. Pour plus d’informations, voir [Préparation au lancement](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md).

#### <a name="considerations-and-assumptions"></a>Observations et hypothèses

Un environnement bac à sable Human Resources existe dans un projet Lifecycle Services sur le locataire qui présente les caractéristiques suivantes :

- L’environnement bac à sable Human Resources n’est pas lié à un environnement fusionné existant. Une seule migration peut être en cours à la fois pour un environnement Human Resources donné.
- Le nombre d’environnements bac à sable autorisés à la fois dépend de la licence Human Resources. Si suffisamment de licences ont été achetées pour le locataire, des environnements bac à sable supplémentaires seront répertoriés dans le volet **Environnements** du projet.
- Les migrations doivent être effectuées vers des environnements du même type. En d’autres termes, seules les migrations de bac à sable à bac à sable ou de production à production peuvent être effectuées.

    > [!NOTE]
    > Seuls les types d’environnement Human Resources sont pris en compte au moment de déterminer le statut Production ou Bac à sable de l’environnement. Si les environnements ne sont pas classés correctement (c’est-à-dire, un environnement de production est marqué comme environnement bac à sable, ou un environnement bac à sable est marqué comme environnement de production), contactez le support.

- Si la migration échoue, un message d’erreur s’affiche et un bouton **Supprimer** devient disponible. Utilisez ce bouton pour supprimer la migration ayant échoué. Vous pouvez ensuite migrer à nouveau l’environnement.

#### <a name="validate-the-sandbox-migration"></a>Valider la migration du bac à sable

Une fois le processus de migration du bac à sable terminé avec succès, créez un plan de test détaillé pour vérifier et approuver tous les processus métier.

Avant de commencer les tests, vérifiez les détails suivants :

- Confirmez que l’environnement migré est accessible à l’URL qui est générée.
- Confirmez que les utilisateurs peuvent accéder à l’environnement bac à sable migré.
- Confirmez que l’environnement Dataverse associé à l’environnement bac à sable migré est accessible.
- Vérifiez ponctuellement différentes données pour confirmer que les données les plus récentes sont disponibles.
- Menez à bien la validation des processus métier critiques.
- Confirmez que vos stratégies de sécurité sont applicables.
- Confirmez que les tâches par lots sont déclenchées comme prévu.

Vous n’aurez pas l’accès Bureau à distance au bac à sable migré. Vous pouvez utiliser les fonctionnalités et les outils en libre service pour effectuer les actions suivantes pour vos environnements bac à sable de niveau 2 et + :

- Accédez à la [Base de données Azure SQL](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-the-azure-sql-database).
- Accédez aux [fichiers journaux](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-log-files).
- Utilisez [l’outil perfmon](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#use-perfmon-tools).
- Activez ou désactivez le [Mode de Maintenance](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-self-service-logs).
- Redémarrez les [services](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#restart-services).
- Configurez l’outil [Regression Suite Automation Tool](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#configure-the-regression-suite-automation-tool).

Pour plus d’informations, voir [FAQ sur le déploiement en libre service](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md).

### <a name="migrate-a-human-resources-production-environment"></a>Migration d’un environnement Human Resources de production

Une fois que vous avez terminé la migration et la validation d’un environnement bac à sable, procédez comme suit pour migrer l’environnement de production.

#### <a name="prerequisites"></a>Conditions préalables

- Vous devez avoir exécuté l’Estimateur d’abonnement.
- Vois devez avoir terminé [l’évaluation de l’état de préparation](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md) pour la mise en service.

#### <a name="migrate-the-production-environment"></a>Migration de l’environnement de production

1. Connectez-vous à Lifecycle Services en tant qu’administrateur général ou utilisateur du compte de service désigné.

    > [!NOTE]
    > Nous vous recommandons d’utiliser un compte utilisateur nommé. L’utilisateur connecté doit disposer du rôle de sécurité **Propriétaire du projet** ou **Gestionnaire d’environnement** dans le projet Lifecycle Services.

2. Ouvrez le nouveau projet de migration Human Resources.
3. Examinez et terminer les phases appropriées de la méthodologie de migration et de l’intégration du projet.
4. Sur le tableau de bord du projet, dans le volet **Production**, sélectionnez **Migrer HR**.
5. Dans le volet **Sélectionnez l’environnement à migrer**, sélectionnez le projet Lifecycle Services approprié et l’environnement Human Resources d’origine (à partir de votre application Human Resources autonome source). Cliquez ensuite sur **Suivant**.
6. Suivez l’assistant **Paramètres de déploiement (finances et opérations – bac à sable)** pour confirmer les détails et la signature du client, puis sélectionnez **Déployer**.

L’état de l’environnement montrera la progression du déploiement. L’état passera de **Chargement en cours** à **Déploiement en cours** à **Déployé**.

#### <a name="post-migration-considerations"></a>Observations après la migration

- Appliquez les dernières [mises à jour de qualité](/fin-ops-core/fin-ops/get-started/quality-updates) à vos environnements.
- Si vous utilisez des [tables virtuelles](hr-admin-integration-common-data-service-virtual-entities.md), reconfigurez les points de terminaison.
- Reconfigurez l’intégration de la double écriture. Évaluez les entités qui doivent être activées.
- Envisagez d’utiliser des tables virtuelles pour remplacer la double écriture pour l’intégration.

#### <a name="dual-write-integration"></a>Intégration en double écriture

##### <a name="set-up-microsoft-power-platform-dual-write-integration"></a>Configurer l’intégration de la double écriture dans Microsoft Power Platform

1. Accédez au centre d’administration Power Platform, puis sélectionnez **Environnements** dans la navigation de gauche.
2. Sélectionnez l’environnement précédemment copié/actualisé et confirmez que l’état est **Prêt**.
3. Accédez à Lifecycle Services et confirmez que le statut du projet de migration est **Déployé**.
4. Sous l’environnement migré, sélectionnez **Détails complets** pour examiner des détails supplémentaires et [configurer une application à double écriture](../fin-ops-core/dev-itpro/data-entities/dual-write/lcs-setup.md#set-up-dual-write-for-new-or-existing-dataverse-environments).
5. Dans le volet **Configuration d’application à double écriture**, cochez la case pour accepter de mapper et de synchroniser les données entre les bases de données, puis sélectionnez **Configurer**.
6. Lorsqu’une boîte de message vous informe de la réussite de la configuration de la double écriture, sélectionnez **OK**.
7. Vous pouvez surveiller la progression de la configuration dans les détails.
8. Lorsque la configuration est terminée, sélectionnez **Associer à un environnement Power Platform** pour synchroniser les entités de données disponibles.
9. Lorsque le statut indique que les environnements ont été associés avec succès, accédez au centre d’administration Power Platform pour examiner et sélectionner les entités de données appropriées.
10. Dans le volet de gauche, sélectionnez **Applications Dynamics 365 \>Ressources**.
11. Vérifiez que le statut de l’application Human Resources à double écriture est **Activé**.
12. Sélectionnez l’application Human Resources à double écriture, puis sélectionnez **Installer**.
13. Dans le volet **Installer une application Dynamics 365 Human Resources à double écriture**, sélectionnez l’environnement approprié pour y installer le package.
14. Cochez la case pour accepter les conditions d’utilisation du service, puis sélectionnez **Installer**.
15. Dans l’environnement de l’application Dynamics 365, le statut sera **Installation en cours** pendant que l’installation est en cours. Il passera à **installé** lorsque l’installation sera terminée.

##### <a name="review-and-apply-a-dual-write-solution"></a>Examiner et appliquer une solution à double écriture

1. Dans le nouvel environnement de finances et d’opérations, accédez à **Gestion des données \> Double écriture**.
2. Sélectionnez **Appliquer la solution**.
3. Dans le volet, sélectionnez **Solutions Dynamics installées**, **Mappages d’entités principales dans les applications à double écriture**, et **Mappages Dynamics 365 Human Resources**. Sélectionnez ensuite **Appliquer**. Un message confirme que la solution est en cours d’application. Une fois la solution appliquée avec succès, tous les mappages de table disponibles seront affichés.
4. Passez en revue les mappages de table disponibles pour sélectionner et exécuter l’intégration à l’aide de la double écriture.
5. Lorsque vous exécutez l’intégration de la double écriture pour la première fois pour les mappages de table, sélectionnez la case à cocher **Synchronisation initiale**. S’il existe une intégration à partir de l’environnement Human Resources source, vous n’avez pas à cocher la case **Synchronisation initiale** lorsque vous exécutez l’intégration pour les mappages de table.

#### <a name="recommended-practices"></a>Pratiques recommandées

Cette section présente des recommandations pour la migration de l’infrastructure autonome vers l’infrastructure des finances et des opérations.

- Nous vous recommandons vivement de travailler avec votre partenaire Microsoft Dynamics pour obtenir de l’aide pour la migration de votre environnement Human Resources.
- Prévoyez le temps nécessaire pour effectuer des tests d’acceptation utilisateur complets (UAT) sur l’environnement bac à sable migré.
- Planifiez et documentez les étapes détaillées pour migrer les intégrations vers l’environnement migré.
- Créez une liste de contrôle détaillée pour décrire le processus de transition pour votre migration.
- Planifiez une durée d’indisponibilité appropriée pour votre entreprise pendant la migration.
- Nous recommandons vivement aux clients éligibles au programme FastTrack de travailler avec leur architecte de solution FastTrack pour superviser le processus de migration.
- Nous vous recommandons vivement d’actualiser votre environnement bac à sable dans l’infrastructure autonome avant d’effectuer la première migration. Cette actualisation doit inclure votre environnement Dataverse connecté à l’environnement bac à sable vers lequel vous prévoyez de migrer.
- Nous vous recommandons vivement d’utiliser un compte de service lorsque vous déployez, migrez et créez votre projet Lifecycle Services.
- Prévoyez de mettre à niveau l’environnement bac à sable pour la validation UAT sur la dernière version en disponibilité générale (GA). Pour plus d’informations, voir [Observations](hr-infrastructure-merge.md#considerations).
