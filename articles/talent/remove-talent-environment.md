---
title: Supprimer un environnement Talent
description: "Cette rubrique décrit le processus de suppression d'un environnement de test ou de production pour Microsoft Dynamics 365 for Talent."
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
ms.sourcegitcommit: d1870c84d4d5e7402bae44d192ce7587c2f67fe7
ms.openlocfilehash: 0e7748b079b1cd5c069917d46e05cd281ea6aa01
ms.contentlocale: fr-fr
ms.lasthandoff: 04/05/2018

---
# <a name="remove-a-talent-environment"></a>Supprimer un environnement Talent

Cette rubrique décrit le processus de suppression d'un environnement de test ou de production pour Microsoft Dynamics 365 for Talent.

## <a name="removing-a-test-drive-environment"></a>Suppression d'un environnement de test

Les tests Talent sont provisionnés avec une stratégie d'expiration de 60 jours. Toutefois, les propriétaires des environnements de test ont l'option de mettre fin à leur période d'essai en suivant les étapes suivantes. 

1. Accédez au [Centre d'administration PowerApps](https://admin.businessplatform.microsoft.com/).
2. Sélectionner **Environnements**.
3. Sélectionnez l'environnement de test, avec un modèle de dénomination similaire à ceci : TestDrive - alias@domain
4. Sélectionnez **Supprimer** et confirmez la décision. 

L'environnement de test existant est supprimé. Une fois supprimé, vous pouvez vous inscrire à un nouvel environnement de test. 

## <a name="removing-a-production-environment"></a>Suppression d'un environnement de production

Cette rubrique suppose que vous avez acheté Talent par l'intermédiaire d'un fournisseur de solutions Cloud (CSP) ou dans le cadre d'un contrat d'architecture d'entreprise (EA). 

Comme un seul environnement Talent est « contenu » dans un seul environnement PowerApps, il existe deux options à prendre en compte. La première option implique de supprimer l'ensemble de l'environnement PowerApps ; puis supprimer uniquement Talent. La première option est recommandée lorsque vous avez créé un environnement PowerApps expressément pour le provisionnement de Talent, et que vous venez de commencer l'implémentation, ou que vous n'avez pas établi d'intégration. La deuxième option est utile lorsque vous avez établi un environnement PowerApps rempli avec des données enrichies qui sont exploitées dans PowerApps et Flow.

> [!Important]
> Avant de supprimer l'environnement PowerApps, vérifiez qu'il n'est pas utilisé pour des intégrations de données enrichies en dehors de la portée de Talent. Notez également que les environnements PowerApps par défaut ne peuvent pas être supprimés. 

Pour supprimer l'ensemble de l'environnement PowerApps, notamment Talent et les applications et flux associés :

1. Accédez au [Centre d'administration PowerApps](https://admin.businessplatform.microsoft.com/).
2. Sélectionner **Environnements**.
3. Sélectionnez l'environnement à supprimer.
4. Sélectionnez **Supprimer** et confirmez la décision. 
5. Attendez que la suppression soit terminée.
6. Connectez-vous à [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (CS) à l'aide du compte utilisé pour vous abonner à Talent. 
7. Sélectionnez le projet Talent qui contient l'environnement. 
8. Dans votre projet LCS, sélectionnez la vignette **Gestion de l'application Talent**. 
9. Sélectionnez l'instance à supprimer. 
10. Sélectionnez **Supprimer l'instance** et confirmez votre décision.  

Pour supprimer un environnement Talent d'un environnement PowerApps existant, procédez comme suit. Notez que la nécessité d'inclure le support et de contacter l'équipe DevOps de Talent est temporaire tant que cette fonction est activée directement dans LCS.

1. Contactez le support pour lancer une demande de suppression.
2. L'équipe de support initialisera une demande de suppression avec l'équipe DevOps de Talent. 
3. Continuez après la réception du message indiquant que l'environnement a été supprimé.
4.  Connectez-vous à LCS à l'aide du compte utilisé pour vous abonner à Talent. 
5. Sélectionnez le projet Talent qui contient l'environnement. 
6. Dans votre projet LCS, sélectionnez la vignette **Gestion de l'application Talent**. 
7. Sélectionnez l'instance à supprimer, qui doit être marquée avec un statut de déploiement **Échec**.
8. Sélectionnez **Supprimer l'instance** et confirmez votre décision. 

