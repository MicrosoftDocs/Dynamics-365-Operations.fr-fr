---
title: Supprimer des environnements Talent
description: Cette rubrique décrit le processus de suppression d'un pilote test ou d'un environnement de production pour Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 11/20/2017
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
ms.openlocfilehash: bbc65a77b7c3df6545dfd7aa2109aba5c4e1b57b
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773032"
---
# <a name="remove-talent-environments"></a>Supprimer des environnements Talent

[!include [banner](includes/banner.md)]

Cette rubrique décrit le processus de suppression d'un pilote test ou d'un environnement de production pour Microsoft Dynamics 365 Talent.

## <a name="removing-a-test-drive-environment"></a>Suppression d'un environnement de test

Les tests Talent sont provisionnés avec une stratégie d'expiration de 60 jours. Toutefois, les propriétaires des environnements de test ont l'option de mettre fin à leur période d'essai en suivant les étapes suivantes. 

1. Accédez au [centre d'administration Power Apps](https://admin.businessplatform.microsoft.com/).
2. Sélectionner **Environnements**.
3. Sélectionnez l'environnement de test, avec un modèle de dénomination similaire à ceci : TestDrive - alias@domain
4. Sélectionnez **Supprimer** et confirmez la décision. 

L'environnement de test existant est supprimé. Une fois supprimé, vous pouvez vous inscrire à un nouvel environnement de test. 

## <a name="removing-a-production-environment"></a>Suppression d'un environnement de production

Cette rubrique suppose que vous avez acheté Talent par l'intermédiaire d'un fournisseur de solutions Cloud (CSP) ou dans le cadre d'un contrat d'architecture d'entreprise (EA). 

Comme un seul environnement Talent est « contenu » dans un seul environnement Power Apps, il existe deux options à prendre en compte. La première option implique de supprimer l'ensemble de l'environnement Power Apps ; puis supprimer uniquement Talent. La première option est recommandée lorsque vous avez créé un environnement Power Apps expressément pour le provisionnement de Talent, et que vous venez de commencer l'implémentation, ou que vous n'avez pas établi d'intégration. La deuxième option est utile lorsque vous avez établi un environnement Power Apps rempli avec des données enrichies qui sont exploitées dans Power Apps et Power Automate.

> [!Important]
> Avant de supprimer l'environnement Power Apps, vérifiez qu'il n'est pas utilisé pour des intégrations de données enrichies en dehors de la portée de Talent. Notez également que les environnements Power Apps par défaut ne peuvent pas être supprimés. 

Pour supprimer l'ensemble de l'environnement Power Apps, notamment Talent et les applications et flux associés :

1. Accédez au [centre d'administration Power Apps](https://admin.businessplatform.microsoft.com/).
2. Sélectionner **Environnements**.
3. Sélectionnez l'environnement à supprimer.
4. Sélectionnez **Supprimer** et confirmez la décision. 
5. Attendez que la suppression soit terminée.
6. Connectez-vous à [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (CS) à l'aide du compte utilisé pour vous abonner à Talent. 
7. Sélectionnez le projet Talent qui contient l'environnement. 
8. Dans votre projet LCS, sélectionnez la vignette **Gestion de l'application Talent**. 
9. Sélectionnez l'instance à supprimer. 
10. Sélectionnez **Supprimer l'instance** et confirmez votre décision.  

Pour supprimer un environnement Talent d'un environnement Power Apps existant, procédez comme suit. Notez que la nécessité d'inclure le support et de contacter l'équipe DevOps de Talent est temporaire tant que cette fonction est activée directement dans LCS.

1. Contactez le support pour lancer une demande de suppression.
2. L'équipe de support initialisera une demande de suppression avec l'équipe DevOps de Talent. 
3. Continuez après la réception du message indiquant que l'environnement a été supprimé.
4.  Connectez-vous à LCS à l'aide du compte utilisé pour vous abonner à Talent. 
5. Sélectionnez le projet Talent qui contient l'environnement. 
6. Dans votre projet LCS, sélectionnez la vignette **Gestion de l'application Talent**. 
7. Sélectionnez l'instance à supprimer, qui doit être marquée avec un statut de déploiement **Échec**.
8. Sélectionnez **Supprimer l'instance** et confirmez votre décision. 

