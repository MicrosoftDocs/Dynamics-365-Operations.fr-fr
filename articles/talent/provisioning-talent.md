---
title: Mise en service de Talent
description: Cette rubrique décrit le processus de mise en service d'un nouvel environnement pour Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.openlocfilehash: d7c4a8174007384370ae320b3874e104c04b71a5
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124702"
---
# <a name="provision-talent"></a>Mettre en service Talent

Cette rubrique décrit le processus de mise en service d'un nouvel environnement de production pour Microsoft Dynamics 365 Talent. Cette rubrique suppose que vous avez acheté Talent par l'intermédiaire d'un fournisseur de solutions Cloud (CSP) ou dans le cadre d'un contrat d'architecture d'entreprise (EA). Si vous disposez d'une licence Microsoft Dynamics 365 existante qui inclut déjà le plan de service Talent et que vous ne pouvez pas effectuer les étapes décrites dans cette rubrique, contactez le support technique.

Pour commencer, l'administrateur global doit se connecter à [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) et créer un projet Talent. Il n'est pas nécessaire de contacter le support technique ou les représentants de Dynamics Service Engineering (DSE) sauf si un problème de licence vous empêche de mettre en service Talent.

## <a name="create-an-lcs-project"></a>Créer un projet LCS
Pour utiliser LCS pour gérer vos environnements Talent, vous devez d'abord créer un projet LCS.

1. Connectez-vous à [LCS](https://lcs.dynamics.com/Logon/Index) à l'aide du compte utilisé pour vous abonner à Talent.

2. Sélectionnez le signe plus (**+**) pour créer un projet.

3. Sélectionnez **Microsoft Dynamics 365 Talent** comme nom et version du produit.

4. Sélectionner la méthodologie **Dynamics 365 Talent**.

5. Sélectionnez **Créer**. 

Pour plus d'informations sur la mise en route de Talent, consultez la méthodologie **Talent** que vous avez créée dans votre nouveau projet. Une fois que vous avez terminé de créer le projet, exécutez la procédure suivante pour mettre en service votre environnement Talent.

## <a name="provision-a-talent-project"></a>Mettre en service un projet Talent

Une fois que vous avez créé un projet LCS, vous pouvez mettre en service Talent dans un environnement.

1. Dans votre projet LCS, sélectionnez la vignette **Gestion de l'application Talent**.

2. Indiquez s'il s'agit d'une instance de bac à sable ou de production de Talent. Des fonctionnalité d'aperçu anticipées peuvent être disponibles dans les instances de Sandbox pour permettre des commentaire et des test anticipés. 

    > [!NOTE]
    > Le type d'instance Talent ne peut plus être modifié une fois défini. Vérifiez que le type d'instance correct est sélectionné avant de continuer.

    > [!NOTE]
    > Le type d'instance Talent est distincte du type d'instance de l'environnement Microsoft Power Apps, que vous définissez dans le Centre d'administration Power Apps.

3. Sélectionnez l'option **Inclure les données de démonstration** si vous souhaitez que votre environnement inclut le même ensemble de données de démonstration que celui utilisé dans l'environnement de test de Talent. Cette option est utile pour les environnements de démonstration ou de formation à long terme, et ne doit jamais être utilisée pour les environnements de production.  Notez que vous devez sélectionner cette option lors du déploiement initial. Vous ne pouvez pas mettre un déploiement à jour ultérieurement.

4. Talent est toujours mis en service dans un environnement Microsoft Power Apps pour permettre l'intégration et l'extensibilité des applications Power Apps. Lisez la section « Sélectionnant d'un environnement Power Apps » de cette rubrique avant de continuer. Si vous n'avez pas déjà un environnement Power Apps, sélectionnez Gérer les environnements dans LCS ou accédez au centre d'administration de Power Apps. Puis suivez les étapes pour [Créer un environnement Power Apps](https://docs.microsoft.com/powerapps/administrator/create-environment).

5. Sélectionnez l'environnement dans lequel mettre en œuvre Talent.

6. Sélectionnez **Oui** pour accepter les termes et commencer le déploiement.

    Votre nouvel environnement apparaît dans la liste des environnements dans le volet de navigation à gauche. Toutefois, vous ne pouvez pas commencer à utiliser l'environnement jusqu'à ce que le statut de déploiement soit mis jour sur **Déployé**. Ce processus prend généralement quelques minutes. Si le processus d'approvisionnement est infructueux, vous devez contacter le support technique.

7. Sélectionnez **Se connecter à Talent** pour utiliser votre nouvel environnement.

    > [!NOTE]
    > Si vous ne vous êtes pas encore déconnecté, vous pouvez déployer une instance de test de Talent dans le projet. Vous pouvez ensuite utiliser cette instance pour tester votre solution jusqu'à ce que vous vous déconnectiez. Si vous utilisez votre nouvel environnement pour les tests, vous devez répéter cette procédure pour créer un environnement de production.

    > Comme seuls deux environnements LCS sont autorisés dans le cadre de l'abonnement Talent, vous pouvez également envisager d'utiliser un [environnement d'évaluation Talent](https://dynamics.microsoft.com/talent/overview/) gratuit pendant 60 jours. Bien qu'un environnement d'évaluation soit la propriété de l'utilisateur qui l'a demandé, d'autres utilisateurs peuvent être invités par l'expérience d'administration système pour Ressources humaines. Les environnements d'évaluation contiennent des données fictives qui peuvent être utilisées pour explorer le programme de manière sûre. Ils ne sont pas destinés à être utilisés comme environnements de production. Notez que lorsqu'un environnement d'évaluation expire après 60 jours, toutes les données qu'il contient sont supprimées et ne peuvent pas être récupérées. Vous pouvez vous inscrire à un nouvel environnement d'évaluation après expiration de l'environnement existant.

## <a name="select-a-power-apps-environment"></a>Sélectionner un environnement Power Apps

L'intégration entre les environnements Talent et Power Apps permet d'intégrer et d'étendre l'utilisation des données Talent à l'aide des outils Power Apps. La compréhension de l'objectif des environnements Power Apps vous aidera non seulement à créer des applications pour étendre Talent, mais aussi à sélectionner l'environnement approprié lorsque du provisionnement de Talent. Pour plus d'informations sur les environnements Power Apps, notamment la portée de l'environnement, l'accès à l'environnement ainsi que la création et le choix d'un environnement, voir [Annonce des environnements Power Apps](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Utilisez les consignes suivantes pour déterminer dans quel environnement Power Apps déployer Talent : 

1. Dans LCS, sélectionnez **Gérer les environnements**, ou accédez directement au Centre d'administration de Power Apps, dans lequel vous pouvez afficher les environnements existants et créer des environnements.

2. Un seul environnement Talent est mappé à un seul environnement Power Apps.

3. Un environnement Power Apps « contient » l'application Talent, ainsi que les applications Power Apps, Power Automate et Common Data Service. Si l'environnement Power Apps est supprimé, les applications qu'il contient le sont aussi. Lors de la mise en service d'un environnement Talent, vous pouvez mettre en service un environnement **d'évaluation** ou **de production**. Choisissez le type d'environnement selon la façon dont l'environnement sera utilisé. 

4. Des stratégies d'intégration de données et de test doivent être envisagées, par exemple : bac à sable (Sandbox), UAT ou Production. Nous vous recommandons de prendre en compte les différentes implications de votre déploiement, car il sera difficile de modifier l'environnement Talent mappé à un environnement Power Apps par la suite.

5. Les environnements Power Apps suivants ne peuvent pas être utilisés pour Talent et seront filtrés de la liste de sélection dans LCS :
 
    - **Environnements Power Apps par défaut** : bien que chaque client soit automatiquement provisionné avec un environnement Power Apps par défaut, nous ne vous recommandons pas de l'utiliser avec Talent, car tous les utilisateurs d'un client ont accès à l'environnement Power Apps et peuvent involontairement endommager des données de production lors de tests et des explorations des intégrations Power Apps ou Power Automate.
   
    - **Environnements de test** : ces environnements sont créés avec une date d'expiration et expirent après ce délai, entraînant la suppression automatique de votre environnement et de toutes les instances Talent qu'il contient.
   
    - **Zones non prises en charge** : actuellement, Talent n'est pris en charge que dans les zones suivantes : États-Unis, Europe, Royaume-Uni, Australie, Canada et Asie.
  
6. Après avoir déterminé l'environnement à utiliser, vous pouvez poursuivre le processus d'approvisionnement. 
 
## <a name="grant-access-to-the-environment"></a>Autoriser l'accès à l'environnement

Par défaut, l'administrateur global ayant créé l'environnement y a accès. Cependant, les autres utilisateurs d'application doivent avoir un accès explicitement autorisé. Pour accorder l'accès, vous devez ajouter des utilisateurs et leur affecter les rôles appropriés dans l'environnement Ressources humaines. L'administrateur global qui a déployé Talent doit également lancer Attract et Onboard pour terminer l'initialisation et activer l'accès pour les autres utilisateurs.  Sinon, les autres utilisateurs ne pourront pas accéder à Attract et Onboard et recevront des erreurs de violation de l'accès. Pour plus d'informations, voir [Création de nouveaux utilisateurs](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) et [Affecter des utilisateurs à des rôles de sécurité](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 
