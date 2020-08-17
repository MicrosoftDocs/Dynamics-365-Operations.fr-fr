---
title: Supprimer une instance
description: Cet article décrit le processus de suppression d’un pilote test ou d’un environnement de production pour Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a384801060b2b684f7908daaac2311edd27c773a
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621378"
---
# <a name="remove-an-instance"></a>Supprimer une instance

Cet article décrit le processus de suppression d’un pilote test ou d’un environnement de production pour Microsoft Dynamics 365 Human Resources.

## <a name="remove-a-test-drive-environment"></a>Suppression d’un environnement de test

Les tests Human Resources sont provisionnés avec une stratégie d’expiration de 60 jours. Toutefois, les propriétaires des environnements de test ont l’option de mettre fin à leur période d’essai en suivant les étapes suivantes. 

1. Accédez au [centre d’administration Power Apps](https://admin.businessplatform.microsoft.com/).
2. Sélectionner **Environnements**.
3. Sélectionnez l’environnement de test, avec un modèle de dénomination similaire à ceci : TestDrive - alias@domain
4. Sélectionnez **Supprimer** et confirmez la décision. 

L’environnement de test existant est supprimé. Une fois supprimé, vous pouvez vous inscrire à un nouvel environnement de test. 

## <a name="remove-a-production-environment"></a>Suppression d’un environnement de production

Cet article suppose que vous avez acheté Human Resources par l’intermédiaire d’un fournisseur de solutions Cloud (CSP) ou dans le cadre d’un contrat d’architecture d’entreprise (EA). 

Comme un seul environnement Human Resources est « contenu » dans un seul environnement Power Apps, il existe deux options à prendre en compte. La première option implique de supprimer l’ensemble de l’environnement Power Apps ; puis supprimer uniquement Human Resources. La première option est recommandée lorsque vous avez créé un environnement Power Apps expressément pour le provisionnement de Human Resources, et que vous venez de commencer l’implémentation, ou que vous n’avez pas établi d’intégration. La deuxième option est utile lorsque vous avez établi un environnement Power Apps rempli avec des données enrichies qui sont exploitées dans Power Apps et Power Automate.

> [!Important]
> Avant de supprimer l’environnement Power Apps, vérifiez qu’il n’est pas utilisé pour des intégrations de données enrichies en dehors de la portée de Human Resources. Notez également que les environnements Power Apps par défaut ne peuvent pas être supprimés. 

Pour supprimer l’ensemble de l’environnement Power Apps, notamment Human Resources et les applications et flux associés :

1. Accédez au [centre d’administration Power Apps](https://admin.businessplatform.microsoft.com/).
2. Sélectionner **Environnements**.
3. Sélectionnez l’environnement à supprimer.
4. Sélectionnez **Supprimer** et confirmez la décision. 
5. Attendez que la suppression soit terminée.
6. Connectez-vous à [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (CS) à l’aide du compte utilisé pour vous abonner à Human Resources. 
7. Sélectionnez le projet Human Resources qui contient l’environnement. 
8. Dans votre projet LCS, sélectionnez la vignette **Gestion de l’application Human Resources**. 
9. Sélectionnez l’instance à supprimer. 
10. Sélectionnez **Supprimer l’instance** et confirmez votre décision.  

Pour supprimer un environnement Human Resources d’un environnement Power Apps existant, procédez comme suit. Notez que la nécessité d’inclure le support et de contacter l’équipe DevOps de Human Resources est temporaire tant que cette fonction est activée directement dans LCS.

1. Contactez le support pour lancer une demande de suppression.
2. L’équipe de support initialisera une demande de suppression avec l’équipe DevOps de Human Resources. 
3. Continuez après la réception du message indiquant que l’environnement a été supprimé.
4. Connectez-vous à LCS à l’aide du compte utilisé pour vous abonner à Human Resources. 
5. Sélectionnez le projet Human Resources qui contient l’environnement. 
6. Dans votre projet LCS, sélectionnez la vignette **Gestion de l’application Human Resources**. 
7. Sélectionnez l’instance à supprimer, qui doit être marquée avec un statut de déploiement **Échec**.
8. Sélectionnez **Supprimer l’instance** et confirmez votre décision. 

## <a name="recover-a-soft-deleted-environment"></a>Récupérer un environnement supprimé de manière temporaire

Si vous supprimez l’environnement Power Apps auquel votre environnement Human Resources est connecté, le statut de l’environnement Human Resources dans Lifecycle Services est **Suppression temporaire**. Dans ce cas, les utilisateurs ne peuvent pas se connecter à Human Resources.

Pour restaurer l’environnement :

1. Suivez les instructions dans [Récupérer l’environnement Power Apps](/power-platform/admin/recover-environment.md).

2. Contactez le support pour restaurer l’environnement Human Resources. Pour plus d’informations, voir [Obtenir de l’aide](hr-admin-troubleshooting-support.md).

> [!Warning]
> Les environnements Power Apps ne sont enregistrés que pendant sept jours après la suppression. Vous devez récupérer l’environnement dans le délai de sept jours.
