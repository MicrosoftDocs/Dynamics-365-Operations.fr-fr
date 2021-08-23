---
title: Mettre en service Human Resources
description: Cette rubrique décrit le processus de mise en service d’un nouvel environnement de production pour Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 58ffce072c8b73f4907b18c6c60b022f9a3b55f26cb785238367254021afdc28
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756146"
---
# <a name="provision-human-resources"></a>Mettre en service Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit le processus de mise en service d’un nouvel environnement de production pour Microsoft Dynamics 365 Human Resources. Cette rubrique suppose que vous avez acheté Human Resources par l’intermédiaire d’un fournisseur de solutions Cloud (CSP) ou dans le cadre d’un contrat d’architecture d’entreprise (EA). Si vous disposez d’une licence Microsoft Dynamics 365 existante qui inclut déjà le plan de service Human Resources et que vous ne pouvez pas effectuer les étapes décrites dans cet article, contactez le support technique.

Pour commencer, l’administrateur global doit se connecter à [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) et créer un projet Human Resources. Il n’est pas nécessaire de contacter le support technique ou les représentants de Dynamics Service Engineering (DSE) sauf si un problème de licence vous empêche de mettre en service Human Resources.

## <a name="provision-a-human-resources-trial-environment"></a>Configuration d’un environnement d’essai Human Resources

Avant de provisionner votre premier environnement bac à sable ou de production, vous souhaiterez peut-être provisionner un [Environnement d’essai Human Resources](https://go.microsoft.com/fwlink/p/?LinkId=2115962) pour valider la fonctionnalité Human Resources. Les environnements d’évaluation contiennent des données fictives qui peuvent être utilisées pour explorer le programme de manière sûre. Bien qu’un environnement d’évaluation soit la propriété de l’utilisateur qui l’a demandé, d’autres utilisateurs peuvent être invités par l’expérience d’administration système pour Ressources humaines. 

Les environnements d’essai ne sont pas destinés à être utilisés comme environnements de production. Ils sont limités à une période d’essai de 60 jours. À l’expiration de la période d’essai, l’environnement et toutes les données qu’il contient sont supprimés et ne peuvent pas être récupérés. L’environnement ne peut pas être converti en environnement bac à sable ou de production. Vous pouvez vous inscrire à un nouvel environnement d’évaluation après expiration de l’environnement existant.

## <a name="plan-human-resources-environments"></a>Planifier les environnements Human Resources

Avant de créer votre premier environnement Human Resources, vous devez planifier soigneusement les besoins en environnement de votre projet. Un abonnement de base à l’application Human Resources comprend deux environnements : un environnement de production et un environnement sandbox. Selon la complexité de votre projet, vous devrez peut-être acheter des environnements sandbox supplémentaires pour prendre en charge les activités du projet. 

Les considérations relatives aux environnements supplémentaires incluent, mais sans s’y limiter, les éléments suivants :

- **Migration de données** : Vous devrez peut-être envisager un environnement supplémentaire pour les activités de migration de données afin de permettre à votre environnement sandbox d’être utilisé à des fins de test tout au long du projet. Le fait de disposer d’un environnement supplémentaire permet aux activités de migration de données de se poursuivre tandis que les activités de test et de configuration se produisent simultanément dans un environnement différent.
- **Intégration** : Vous devrez peut-être envisager un environnement supplémentaire pour configurer et tester les intégrations. Cela peut inclure des intégrations natives telles que les intégrations Ceridian Dayforce LinkedIn Talent Hub, ou des intégrations personnalisées telles que celles pour la paie, les systèmes de suivi des candidatures ou les régimes et les fournisseurs de prestations.
- **Formation** : Vous pouvez avoir besoin d’un environnement distinct configuré avec un ensemble de données de formation afin de former vos employés à l’utilisation du nouveau système. 
- **Projet en plusieurs phases** : Vous pouvez avoir besoin d’un environnement supplémentaire pour prendre en charge la configuration, la migration des données, les tests ou d’autres activités dans une phase de projet qui est planifiée après la mise en service initiale du projet.

 > [!IMPORTANT]
 > Nous vous recommandons d’utiliser votre environnement de production tout au long de votre projet comme environnement de configuration GOLD. Ceci est important, car vous ne pouvez pas copier un environnement sandbox dans un environnement de production. Par conséquent, lors de la mise en service, votre environnement GOLD est votre environnement de production et c’est là que vous allez effectuer vos activités de basculement.</br></br>
 > Nous vous recommandons d’utiliser votre environnement sandbox ou un autre environnement pour effectuer une simulation de basculement avant votre mise en service. Vous pouvez le faire en actualisant l’environnement de production avec votre configuration GOLD dans votre environnement sandbox.</br></br>
 > Nous vous recommandons de conserver une liste de contrôle de basculement détaillée qui inclut chacun des packages de données requis pour migrer les données finales dans l’environnement de production lors de la mise en service.</br></br>
 > Nous recommandons aussi d’utiliser votre environnement sandbox tout au long de votre projet comme environnement de configuration TEST. Si vous avez besoin d’environnements supplémentaires, votre organisation peut les acheter moyennant un coût supplémentaire.</br></br>

## <a name="create-an-lcs-project"></a>Créer un projet LCS

Pour utiliser LCS pour gérer vos environnements Human Resources, vous devez d’abord créer un projet LCS.

1. Connectez-vous à [LCS](https://lcs.dynamics.com/Logon/Index) à l’aide du compte utilisé pour vous abonner à Human Resources.

   > [!NOTE]
   > Pour garantir un provisionnement réussi, le compte que vous utilisez pour provisionner l’environnement Human Resources doit être affecté au rôle **Administrateur système** ou au rôle **Personnalisateur système** dans l’environnement Power Apps associé à l’environnement Human Resources. Voir [Configurer la sécurité des utilisateurs dans Human Resources](/power-platform/admin/database-security) pour plus d’informations sur l’attribution de rôles de sécurité aux utilisateurs dans la Power Platform.

2. Sélectionnez le signe plus (**+**) pour créer un projet.

3. Sélectionnez **Microsoft Dynamics 365 Human Resources** comme nom et version du produit.

4. Sélectionner la méthodologie **Dynamics 365 Human Resources**.

5. Sélectionnez **Créer**.

Pour plus d’informations sur la mise en route de Human Resources, consultez la méthodologie **Human Resources** que vous avez créée dans votre nouveau projet. Une fois que vous avez terminé de créer le projet, exécutez la procédure suivante pour mettre en service votre environnement Human Resources.

## <a name="provision-a-human-resources-project"></a>Mise à disposition d’un projet Human Resources

Une fois que vous avez créé un projet LCS, vous pouvez mettre en service Human Resources dans un environnement.

1. Dans votre projet LCS, sélectionnez la vignette **Gestion de l’application Human Resources**.

2. Indiquez s’il s’agit d’un environnement de bac à sable ou de production de Human Resources. Des fonctionnalité d’aperçu anticipées peuvent être disponibles dans les instances de Sandbox pour permettre des commentaire et des test anticipés.
   
    > [!NOTE]
    > Le type d’instance Human Resources ne peut plus être modifié une fois défini. Vérifiez que le type d’instance correct est sélectionné avant de continuer.</br></br>
    > Le type d’instance Human Resources est distinct du type d’instance de l’environnement Microsoft Power Apps, que vous définissez dans le Centre d’administration Power Apps.
    
3. Sélectionnez l’option **Inclure les données de démonstration** si vous souhaitez que votre environnement inclut le même ensemble de données de démonstration que celui utilisé dans l’environnement de test de Human Resources. Les données de démonstration sont utiles pour les environnements de démonstration ou de formation à long terme, et ne doivent jamais être utilisées pour les environnements de production. Vous devez sélectionner cette option lors du déploiement initial. Vous ne pouvez pas mettre un déploiement à jour ultérieurement.

4. Human Resources est toujours mis en service dans un environnement Microsoft Power Apps pour permettre l’intégration et l’extensibilité des applications Power Apps. Lisez la section « Sélectionnant d’un environnement Power Apps » de cet article avant de continuer. Si vous n’avez pas déjà un environnement Power Apps, sélectionnez Gérer les environnements dans LCS ou accédez au centre d’administration de Power Apps. Puis suivez les étapes pour [Créer un environnement Power Apps](/powerapps/administrator/create-environment).

5. Sélectionnez l’environnement dans lequel mettre en œuvre Human Resources.

6. Sélectionnez **Oui** pour accepter les termes et commencer le déploiement.

   Votre nouvel environnement apparaît dans la liste des environnements dans le volet de navigation à gauche. Toutefois, vous ne pouvez pas commencer à utiliser l’environnement jusqu’à ce que le statut de déploiement soit mis jour sur **Déployé**. Ce processus prend généralement quelques minutes. Si le processus d’approvisionnement est infructueux, vous devez contacter le support technique.

7. Sélectionnez **Se connecter à Human Resources** pour utiliser votre nouvel environnement.

    > [!NOTE]
    > Si vous ne vous êtes pas encore déconnecté, vous pouvez déployer une instance de test de Human Resources dans le projet. Vous pouvez ensuite utiliser cette instance pour tester votre solution jusqu’à ce que vous vous déconnectiez. Si vous utilisez votre nouvel environnement pour les tests, vous devez répéter cette procédure pour créer un environnement de production.

## <a name="select-a-power-apps-environment"></a>Sélectionner un environnement Power Apps

Vous pouvez intégrer et étendre l’utilisation des données de Human Resources à l’aide des outils Power Apps. Pour plus d’informations sur les environnements Power Apps, notamment la portée de l’environnement, l’accès à l’environnement ainsi que la création et le choix d’un environnement, voir [Annonce des environnements Power Apps](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Utilisez les consignes suivantes pour déterminer dans quel environnement Power Apps déployer Human Resources : 

1. Dans LCS, sélectionnez **Gérer les environnements**. Vous pouvez également accéder directement au Centre d’administration Power Apps, où vous pouvez afficher les environnements existants et en créer de nouveaux.

2. Un seul environnement Human Resources est mappé à un seul environnement Power Apps.

3. Un environnement Power Apps « contient » l’application Human Resources, ainsi que les applications Power Apps, Power Automate et Dataverse. Si l’environnement Power Apps est supprimé, les applications qu’il contient le sont aussi. Lors de la mise en service d’un environnement Human Resources, vous pouvez mettre en service un environnement **d’évaluation** ou **de production**. Choisissez le type d’environnement selon la façon dont l’environnement sera utilisé. 

4. Des stratégies d’intégration de données et de test doivent être envisagées, par exemple : bac à sable (Sandbox), UAT ou Production. Prenez en compte avec précaution les implications de votre déploiement, car il sera difficile de modifier l’environnement Human Resources mappé à un environnement Power Apps par la suite.

5. Vous ne pouvez pas utiliser les environnements Power Apps suivants pour Human Resources. Ils sont filtrés à partir de la liste de sélection dans LCS :
 
    - **Environnements Power Apps par défaut** – Alors que chaque client est automatiquement provisionné avec une valeur d’environnement Power Apps par défaut, nous ne recommandons pas de les utiliser avec les Human Resources. Tous les utilisateurs clients peuvent accéder à l’environnement Power Apps et pourraient involontairement corrompre les données de production lors des tests et de l’exploration avec les intégrations Power Apps ou Power Automate.
   
    - **Environnements d’essai** – Ces environnements sont créés avec une date d’expiration. À l’expiration, votre environnement et toutes les instances de Human Resources qu’il contient seront supprimés automatiquement.
   
    - **Zones géographiques non prises en charge** – L’environnement doit être dans une zone géographique prise en charge. Pour plus d’informations, consultez [Zones géographiques prises en charge](hr-admin-setup-provision.md#supported-geographies).

6. Après avoir déterminé l’environnement à utiliser, vous pouvez poursuivre le processus d’approvisionnement. 

### <a name="supported-geographies"></a>Zones géographiques prises en charge

Human Resources prend actuellement en charge les zones géographiques suivantes :

- Etats-Unis
- Europe
- Royaume-Uni
- Australie
- Canada
- Asie 

Lorsque vous créez un environnement Human Resources, vous sélectionnez un environnement Power Apps à associer à l’environnement Human Resources. L’environnement Human Resources est ensuite provisionné dans la même zone géographique Azure que l’environnement Power Apps. Vous pouvez sélectionner l’emplacement physique de l’environnement Human Resources et de la base de données en sélectionnant la zone géographique lors de la création de l’environnement Power Apps qui sera associé à l’environnement Human Resources.

Vous pouvez sélectionner la *zone géographique* Azure dans lequel l’environnement est provisionné, mais vous ne pouvez pas sélectionner la *région* spécifique à Azure. L’automatisation détermine la région spécifique de la zone géographique dans laquelle l’environnement est créé pour optimiser l’équilibrage de charge et les performances. Vous trouverez des informations sur les zones géographiques et les régions Azure dans la documentation sur les [Zones géographiques Azure](https://azure.microsoft.com/global-infrastructure/geographies).

Les données de l’environnement Human Resources seront toujours contenues dans la zone géographique Azure dans laquelle elles sont créées. Cependant, elles ne seront pas toujours contenues dans la même région Azure. À des fins de reprise après sinistre, les données seront répliquées à la fois dans la région Azure principale et dans une région de basculement secondaire au sein de la zone géographique.

 > [!NOTE]
 > La migration d’un environnement Human Resources d’une région Azure vers une autre région n’est pas prise en charge.

## <a name="grant-access-to-the-environment"></a>Autoriser l’accès à l’environnement

Par défaut, l’administrateur global ayant créé l’environnement y a accès. Vous devez explicitement autoriser l’accès à d’autres utilisateurs d’application. Vous devez ajouter des utilisateurs et leur affecter les rôles appropriés dans l’environnement Human Resources. L’administrateur global qui a déployé Human Resources doit également lancer Attract et Onboard pour terminer l’initialisation et activer l’accès pour les autres utilisateurs. Sinon, les autres utilisateurs ne pourront pas accéder à Attract et Onboard et recevront des erreurs de violation de l’accès. Pour plus d’informations, voir [Création de nouveaux utilisateurs](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) et [Affecter des utilisateurs à des rôles de sécurité](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
