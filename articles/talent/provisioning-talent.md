---
title: Mettre en service Microsoft Dynamics 365 for Talent
description: "Cette rubrique décrit le processus de mise en service d'un nouvel environnement pour Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 1be4b41f63dd03a1d853d344fcde05e8962424e2
ms.openlocfilehash: e6266ef5890b5caaf33db76eeccfc8a7a6888a11
ms.contentlocale: fr-fr
ms.lasthandoff: 03/17/2018

---
# <a name="provision-microsoft-dynamics-365-for-talent"></a>Mettre en service Microsoft Dynamics 365 for Talent

[!include[banner](includes/banner.md)]

Cette rubrique décrit le processus de mise en service d'un nouvel environnement de production pour Microsoft Dynamics 365 for Talent. Cette rubrique suppose que vous avez acheté Talent par l'intermédiaire d'un fournisseur de solutions Cloud (CSP) ou dans le cadre d'un contrat d'architecture d'entreprise (EA). Si vous disposez d'une licence Microsoft Dynamics 365 existante qui inclut déjà le plan de service Talent et que vous ne pouvez pas effectuer les étapes décrites dans cette rubrique, contactez le support technique.

Pour commencer, l'administrateur global doit se connecter à [Microsoft Dynamics Lifecycle Services](http://lcs.dynamics.com) (LCS) et créer un projet Talent. Il n'est pas nécessaire de contacter le support technique ou les représentants de Dynamics Service Engineering (DSE) sauf si un problème de licence vous empêche de mettre en service Talent.

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
2. Talent est toujours mis en service dans un environnement Microsoft PowerApps pour permettre l'intégration et l'extensibilité des applications PowerApps. Si vous ne disposez pas déjà d'un environnement PowerApps, suivez les étapes décrites dans la section « Créer un environnement PowerApps (si nécessaire) » de cette rubrique avant de continuer.

    > [!NOTE]
    > Pour afficher les environnements existants ou en créer de nouveaux, la licence P2 PowerApps doit être affectée à l'administrateur qui met en service Talent. Si votre organisation ne dispose pas d'une licence P2 PowerApps, vous pouvez en obtenir une auprès de votre fournisseur CSP ou à partir de la [Page de tarification PowerApps](https://powerapps.microsoft.com/en-us/pricing/).

3. Sélectionnez **Ajouter**, puis sélectionnez l'environnement dans lequel mettre en service Talent.
4. Sélectionnez **Oui** pour accepter les termes et commencer le déploiement.

    Votre nouvel environnement apparaît dans la liste des environnements dans le volet de navigation à gauche. Toutefois, vous ne pouvez pas commencer à utiliser l'environnement jusqu'à ce que le statut de déploiement soit mis jour sur **Déployé**. Ce processus ne prend généralement que quelques minutes. Si le processus d'approvisionnement est infructueux, vous devez contacter le support technique.

6. Sélectionnez **Se connecter à Talent** pour utiliser votre nouvel environnement.

> [!NOTE]
> Si vous ne vous êtes pas encore déconnecté, vous pouvez déployer une instance de test de Talent dans le projet. Vous pouvez ensuite utiliser cette instance pour tester votre solution jusqu'à ce que vous vous déconnectiez. Si vous utilisez votre nouvel environnement pour les tests, vous devez répéter cette procédure pour créer un environnement de production.

> [!NOTE]
> Les environnements Talent qui sont mis en service via LCS ne contiennent pas de données de démonstration configurées pour les tâches liées aux Ressources humaines (RH) ou spécifiques à Talent. Si vous exigez un environnement qui contient les données de démonstration, nous vous recommandons de vous inscrire gratuitement pour une période de 60 jours [Environnement d'évaluation Talent](https://dynamics.microsoft.com/en-us/talent/overview/). Bien qu'un environnement d'évaluation soit la propriété de l'utilisateur qui l'a demandé, d'autres utilisateurs peuvent être invités via l'expérience d'administration système pour Core RH. Les environnements d'évaluation contiennent des données fictives qui peuvent être utilisées pour explorer le programme de manière sûre. Ils ne sont pas destinés à être utilisés comme environnements de production. Notez que lorsque l'environnement d'évaluation expire après 60 jours, toutes les données qu'il contient sont supprimées et ne peuvent pas être récupérées. Vous pouvez vous inscrire à un nouvel environnement d'évaluation après expiration de l'environnement existant.

## <a name="create-a-new-powerapps-environment-if-required"></a>Créer un environnement PowerApps (si nécessaire)
L'intégration entre les environnements Talent et PowerApps permet d'intégrer et d'étendre l'utilisation des données Talent à l'aide des outils PowerApps. Comprendre le but des environnements PowerApps vous aidera à créer des applications qui répondent aux besoins que vous avez en matière d'extension de Talent. Pour plus d'informations sur les environnements PowerApps, notamment la portée de l'environnement, l'accès à l'environnement ainsi que la création et le choix d'un environnement, voir [Annonce des environnements PowerApps](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/). Chaque locataire met automatiquement en service un environnement PowerApps par défaut, qui n'est peut-être pas le meilleur environnement à utiliser pour votre déploiement Talent. Les stratégies d'intégration des données et de test doivent être prises en compte au cours de cette étape, il est donc recommandé de tenir compte des différentes implications pour votre déploiement, car tout changement ultérieur ne sera pas aisé. 

Bien que chaque locataire soit automatiquement configuré dans un environnement PowerApps par défaut, cet environnement n'est peut-être pas le meilleur environnement à utiliser pour votre déploiement Talent. Les stratégies d'intégration et de test des données devraient être prises en compte lors de cette étape. Par conséquent, nous vous recommandons de définir les différentes implications pour le déploiement, car il sera difficile de modifier l'environnement PowerApps par la suite.

1. Dans LCS, sélectionnez **Gérer les environnements**. Vous êtes redirigé vers le [Centre d'administration PowerApps](https://preview.admin.powerapps.com/environments), où vous pouvez afficher les environnements existants et en créer de nouveaux.
2. Sélectionnez **Nouvel environnement**.
3. Entrez un nom unique pour l'environnement, puis sélectionnez l'emplacement de déploiement.

    > [!NOTE]
    > Talent n'est pas disponible dans toutes les régions. Par conséquent, pensez à vérifier la disponibilité avant de sélectionner l'emplacement de votre environnement.

4. Lorsque le système vous demande si vous souhaitez créer une base de données, sélectionnez **Créer une base de données** pour créer la base de données Common Data Service (CDS) qui doit héberger une partie de vos données Talent. En créant une base de données, vous pouvez également intégrer des applications PowerApps à Talent.
5. Le système vous demande le niveau d'accès à utiliser pour la base de données. Nous vous recommandons de sélectionner **Restriction de l'accès**, car cette option empêche les utilisateurs Talent d'accéder directement aux données confidentielles à l'aide d'une application PowerApps.
6. La base de données CDS qui est créée contient les données de démonstration ajoutant des employés inactifs et des adresses fictives, entre autres informations, à votre environnement de production. Pour supprimer les données de démonstration, suivez les étapes ci-après une fois que vous avez terminé de créer la base de données CDS :

    > [!IMPORTANT]
    > Si vous avez déjà créé une base de données CDS et saisi les données de production de votre société, notez que ces étapes suppriment **toutes** les données de la base de données sélectionnée, même les données de production de votre société.

    1. Se connecter à [PowerApps](https://preview.web.powerapps.com/home).
    2. Dans la liste déroulante en haut à droite, sélectionnez l'environnement que vous avez créé à l'étape 2.
    3. Dans le volet de navigation gauche, développez le **Common Data Service**, puis sélectionnez **Entités**.
    4. Sur le côté droit de la page, sélectionnez le bouton (**…**), puis sélectionnez **Effacer toutes les données**.
    5. Sélectionnez **Supprimer les données** pour confirmer la suppression des données. Cette action supprime par défaut toutes les données de démonstration contenues dans la base de données CDS. Elle supprime également les autres données saisies dans la base de données sélectionnée.

Vous pouvez maintenant utiliser votre nouvel environnement.

## <a name="grant-access-to-the-environment"></a>Autoriser l'accès à l'environnement
Par défaut, l'administrateur global ayant créé l'environnement y a accès. Cependant, les autres utilisateurs d'application doivent avoir un accès explicitement autorisé. Pour accorder l'accès, [ajoutez des utilisateurs](../dev-itpro/sysadmin/tasks/create-new-users.md) et [affectez-leurs les rôles appropriés](../dev-itpro/sysadmin/tasks/assign-users-security-roles.md) dans Core RH. Vous devez également ajouter ces utilisateurs à l'environnement PowerApps, afin qu'ils puissent accéder aux applications Attract et Onboard. La procédure est décrite ici. Si vous avez besoin d'aide pour effectuer les étapes, voir le billet de blog [Présentation du centre d'administration PowerApps](https://powerapps.microsoft.com/en-us/blog/introducing-admin-center-for-powerapps/).

Cette procédure est effectuée par l'administrateur global qui a déployé l'environnement Talent.

1. Ouvrez le [Centre d'administration PowerApps](https://preview.admin.powerapps.com/environments).
2. Sélectionnez les environnements appropriés.
3. Sous l'onglet **Sécurité**, ajoutez les utilisateurs requis au rôle **Créateur d'environnement**.

Notez que cette dernière étape, dans laquelle vous ajoutez manuellement des utilisateurs à l'environnement PowerApps, est temporaire. Par la suite, elle sera effectuée automatiquement lorsque les utilisateurs sont ajoutés à Core RH.

