---
title: Mise en service de Talent
description: "Cette rubrique décrit le processus de mise en service d'un nouvel environnement pour Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 09/27/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: c5d4fb53939d88fcb1bd83d70bc361ed9879f298
ms.openlocfilehash: d28ca1f9cf2bef73dc687a85592056cccc767da5
ms.contentlocale: fr-fr
ms.lasthandoff: 10/01/2018

---
# <a name="provision-talent"></a>Mise en service de Talent

[!include [banner](includes/banner.md)]

Cette rubrique décrit le processus de mise en service d'un nouvel environnement de production pour Microsoft Dynamics 365 for Talent. Cette rubrique suppose que vous avez acheté Talent par l'intermédiaire d'un fournisseur de solutions Cloud (CSP) ou dans le cadre d'un contrat d'architecture d'entreprise (EA). Si vous disposez d'une licence Microsoft Dynamics 365 existante qui inclut déjà le plan de service Talent et que vous ne pouvez pas effectuer les étapes décrites dans cette rubrique, contactez le support technique.

Pour commencer, l'administrateur global doit se connecter à [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) et créer un projet Talent. Il n'est pas nécessaire de contacter le support technique ou les représentants de Dynamics Service Engineering (DSE) sauf si un problème de licence vous empêche de mettre en service Talent.

## <a name="create-an-lcs-project"></a>Créer un projet LCS
Pour utiliser LCS pour gérer vos environnements Talent, vous devez d'abord créer un projet LCS.

1. Connectez-vous à [LCS](https://lcs.dynamics.com/Logon/Index) à l'aide du compte utilisé pour vous abonner à Talent.
2. Sélectionnez le signe plus (**+**) pour créer un projet.
3. Sélectionnez **Microsoft Dynamics 365 for Talent** comme nom et version du produit.
4. Sélectionnez la méthodologie **Dynamics 365 for Talent**.
5. Sélectionnez **Créer**.

Pour plus d'informations sur la mise en route de Talent, consultez la méthodologie **Talent** que vous avez créée dans votre nouveau projet. Une fois que vous avez terminé de créer le projet, exécutez la procédure suivante pour mettre en service votre environnement Talent.

## <a name="provision-a-talent-project"></a>Mettre en service un projet Talent
Une fois que vous avez créé un projet LCS, vous pouvez mettre en service Talent dans un environnement.

1. Dans votre projet LCS, sélectionnez la vignette **Gestion de l'application Talent**.
2. Talent est toujours mis en service dans un environnement Microsoft PowerApps pour permettre l'intégration et l'extensibilité des applications PowerApps. Lisez la section « Sélectionnant d'un environnement PowerApps » de cette rubrique avant de continuer. 

    > [!NOTE]
    > Pour afficher les environnements existants ou en créer de nouveaux, la licence P2 PowerApps doit être affectée à l'administrateur qui met en service Talent. Si votre organisation ne dispose pas d'une licence P2 PowerApps, vous pouvez en obtenir une auprès de votre fournisseur CSP ou à partir de la [Page de tarification PowerApps](https://powerapps.microsoft.com/en-us/pricing/).

4. Sélectionnez **Ajouter**, puis sélectionnez l'environnement dans lequel mettre en service Talent.
5. Sélectionnez l'option « Inclure les données de démonstration » si vous souhaitez que votre environnement inclut le même ensemble de données de démonstration que celui utilisé dans l'environnement de test de Talent.  Cette option est utile pour les environnements de démonstration ou de formation à long terme, et ne doit jamais être utilisée pour les environnements de production.  Notez que vous devez sélectionner cette option lors du déploiement initial et vous ne pouvez pas mettre à jour un déploiement existant ultérieurement.
6. Sélectionnez **Oui** pour accepter les termes et commencer le déploiement.

    Votre nouvel environnement apparaît dans la liste des environnements dans le volet de navigation à gauche. Toutefois, vous ne pouvez pas commencer à utiliser l'environnement jusqu'à ce que le statut de déploiement soit mis jour sur **Déployé**. Ce processus ne prend généralement que quelques minutes. Si le processus d'approvisionnement est infructueux, vous devez contacter le support technique.

7. Sélectionnez **Se connecter à Talent** pour utiliser votre nouvel environnement.

> [!NOTE]
> Si vous ne vous êtes pas encore déconnecté, vous pouvez déployer une instance de test de Talent dans le projet. Vous pouvez ensuite utiliser cette instance pour tester votre solution jusqu'à ce que vous vous déconnectiez. Si vous utilisez votre nouvel environnement pour les tests, vous devez répéter cette procédure pour créer un environnement de production.

> [!NOTE]
> Comme seuls deux environnements LCS sont autorisés dans le cadre de l'abonnement Talent, vous pouvez également envisager d'utiliser un [environnement d'évaluation Talent](https://dynamics.microsoft.com/en-us/talent/overview/) gratuit pendant 60 jours. Bien qu'un environnement d'évaluation soit la propriété de l'utilisateur qui l'a demandé, d'autres utilisateurs peuvent être invités via l'expérience d'administration système pour Core RH. Les environnements d'évaluation contiennent des données fictives qui peuvent être utilisées pour explorer le programme de manière sûre. Ils ne sont pas destinés à être utilisés comme environnements de production. Notez que lorsqu'un environnement d'évaluation expire après 60 jours, toutes les données qu'il contient sont supprimées et ne peuvent pas être récupérées. Vous pouvez vous inscrire à un nouvel environnement d'évaluation après expiration de l'environnement existant.

## <a name="select-a-powerapps-environment"></a>Sélectionner un environnement PowerApps

L'intégration entre les environnements Talent et PowerApps permet d'intégrer et d'étendre l'utilisation des données Talent à l'aide des outils PowerApps. La compréhension de l'objectif des environnements PowerApps vous aidera non seulement à créer des applications pour étendre Talent, mais aussi à sélectionner l'environnement approprié lorsque du provisionnement de Talent. Pour plus d'informations sur les environnements PowerApps, notamment la portée de l'environnement, l'accès à l'environnement ainsi que la création et le choix d'un environnement, voir [Annonce des environnements PowerApps](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/). 

Utilisez les consignes suivantes pour déterminer dans quel environnement PowerApps déployer Talent : 
1. Dans LCS, sélectionnez Gérer les environnements, ou accédez directement au Centre d'administration de PowerApps, dans lequel vous pouvez afficher les environnements existants et créer des environnements.
2. Un seul environnement Talent est mappé à un seul environnement PowerApps.
3. Un environnement PowerApps « contient » l'application Talent, ainsi que les applications PowerApps, Flow et CDS correspondantes. Si l'environnement PowerApps est supprimé, les applications qu'il contient le sont aussi.
4. Des stratégies d'intégration de données et de test doivent être envisagées, par exemple : Bac à sable (Sandbox), UAT, Production. Par conséquent, nous vous recommandons de définir les différentes implications pour le déploiement, car il sera difficile de modifier l'environnement Talent mappé à un environnement PowerApps par la suite.
5. Les environnements PowerApps suivants ne peuvent pas être utilisés pour Talent et seront filtrés de la liste de sélection dans LCS :
 
   **Environnements PowerApps par défaut** Bien que chaque locataire soit automatiquement provisionné avec un environnement PowerApps par défaut, nous ne vous recommandons pas de l'utiliser avec Talent, car tous les utilisateurs d'un locataire ont accès à l'environnement PowerApps et peuvent involontairement endommager des données de production lors de tests et en explorant avec les intégrations PowerApps ou Flow.
   
   <strong>Environnements de test</strong> Les environnements avec un nom comme « TestDrive – alias@domain » sont créés avec une période d'expiration de 60 jours et expirent après ce délai, entraînant la suppression automatique de votre environnement.
   
   **Zones non prises en charge** Actuellement, Talent n'est pris en charge que dans les zones suivantes : États-Unis, Europe ou Australie.
  
6. Il n'existe aucune action spécifique à effectuer une fois que vous avez déterminé l'environnement correct à utiliser. Poursuivez le processus de provisionnement. 
 
## <a name="grant-access-to-the-environment"></a>Autoriser l'accès à l'environnement
Par défaut, l'administrateur global ayant créé l'environnement y a accès. Cependant, les autres utilisateurs d'application doivent avoir un accès explicitement autorisé. Pour accorder l'accès, [ajoutez des utilisateurs](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) et [affectez-leurs les rôles appropriés](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles) dans Core RH. L'administrateur global qui a déployé Talent doit également lancer les applications Attract et Onboard pour terminer l'initialisation et activer l'accès pour les autres utilisateurs.  Sinon, les autres utilisateurs ne pourront pas accéder aux applications Attract et Onboard et recevront des erreurs de violation de l'accès.


