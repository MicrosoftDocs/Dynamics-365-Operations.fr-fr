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
ms.search.form: Talent
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
ms.sourcegitcommit: 6ffb97b53f522cfe8ccd8e89df854cbc557e4f1f
ms.openlocfilehash: fadc373b2c1c06987f22d4d9c20a9ab07b0c85d5
ms.contentlocale: fr-fr
ms.lasthandoff: 11/20/2017

---
# <a name="provision-microsoft-dynamics-365-for-talent"></a>Mettre en service Microsoft Dynamics 365 for Talent
Cette rubrique décrit le processus de mise en service d'un nouvel environnement pour Microsoft Dynamics 365 for Talent. Cette rubrique suppose que vous avez acheté Talent par l'intermédiaire d'un fournisseur de solutions Cloud (CSP) ou dans le cadre d'un contrat d'architecture d'entreprise (EA). Si vous disposez d'une licence Microsoft Dynamics 365 existante qui inclut déjà le plan de service Talent et que vous ne pouvez pas effectuer les étapes décrites dans cette rubrique, contactez le support technique.

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

    Votre nouvel environnement apparaît dans la liste des environnements dans le volet de navigation à gauche. Toutefois, vous ne pouvez pas commencer à utiliser l'environnement jusqu'à ce que le statut de déploiement soit mis jour sur **Déployé**. Ce processus ne prend généralement que quelques minutes. Si la mise en service échoue, vous devez contacter le support technique.

6. Sélectionnez **Se connecter à Talent** pour utiliser votre nouvel environnement.

> [!NOTE]
> Si vous ne vous êtes pas encore déconnecté, vous pouvez déployer une instance de test de Talent dans le projet. Vous pouvez ensuite utiliser cette instance pour tester votre solution jusqu'à ce que vous vous déconnectiez. Si vous utilisez votre nouvel environnement pour les tests, vous devez répéter cette procédure pour créer un environnement de production.

## <a name="create-a-new-powerapps-environment-if-required"></a>Créer un environnement PowerApps (si nécessaire)
1. Sélectionnez **Gérer les environnements** dans LCS. Vous êtes redirigé vers le [Centre d'administration PowerApps](https://preview.admin.powerapps.com/environments), où vous pouvez afficher les environnements existants et en créer de nouveaux.
2. Sélectionnez le bouton (**+**) **Nouvel environnement**.
3. Entrez un nom unique pour l'environnement, puis sélectionnez l'emplacement de déploiement.

    > [!NOTE]
    > Talent n'est pas disponible dans toutes les régions. Par conséquent, pensez à vérifier la disponibilité avant de sélectionner l'emplacement de votre environnement.

4. Lorsque le système vous demande si vous souhaitez créer une base de données, sélectionnez **Créer une base de données** pour créer la base de données Common Data Service (CDS) qui doit héberger une partie de vos données Talent. En créant une base de données, vous pouvez également intégrer des applications PowerApps à Talent.
5. Le système vous demande le niveau d'accès que vous souhaitez utiliser pour la base de données. Nous vous recommandons de sélectionner **Restriction de l'accès**, car cette option empêche les utilisateurs Talent d'accéder directement aux données confidentielles à l'aide d'une application PowerApps.
6. La base de données CDS créée contient des données de démonstration. Ces données de démonstration sont utiles, car vous pouvez utiliser la société fictive pour les tests, ou pour créer des enregistrements de tâches ou des guides de tâches. Toutefois, les données de démonstration ajoutent des employés inactifs et des adresses fictives, entre autres informations, à votre environnement de production. Pour supprimer les données de démonstration, suivez les étapes ci-après une fois que vous avez terminé de créer la base de données CDS :

    > [!IMPORTANT]
    > Si vous avez déjà créé une base de données CDS et saisi les données de production de votre société, notez que ces étapes suppriment **toutes** les données de la base de données sélectionnée, même les données de production de votre société.

    1. Connectez-vous à [PowerApps](https://preview.web.powerapps.com/home), puis accédez à l'environnement créé à l'étape 2.
    2. Sélectionnez **Entités**. Sur le côté droit de la page, sélectionnez le bouton (**…**), puis sélectionnez **Effacer toutes les données**.
    3. Sélectionnez **Supprimer les données** pour confirmer la suppression des données. Cette action supprime par défaut toutes les données de démonstration contenues dans la base de données CDS. Elle supprime également les autres données saisies dans la base de données sélectionnée.

Vous pouvez maintenant utiliser votre nouvel environnement.

