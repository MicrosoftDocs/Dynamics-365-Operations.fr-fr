---
title: Supprimer une instance
description: Cet article décrit le processus de suppression d’une version d’évaluation ou d’un environnement de production pour Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/11/2021
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
ms.openlocfilehash: 0ce676c93e133cc04ad9c49417ed2ca0d6791e93
ms.sourcegitcommit: 1401d66b6b64c590ca1f8f339d622e922920cf15
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/20/2022
ms.locfileid: "9178470"
---
# <a name="remove-an-instance"></a>Supprimer une instance

_**S’applique à :** Human Resources dans l’infrastructure autonome_ 

> [!NOTE]
> À partir de juillet 2022, les nouveaux environnements de Human Resources ne peuvent plus être approvisionnés sur l’infrastructure autonome de Human Resources, et les nouveaux projets Microsoft Dynamics Lifecycle Services (LCS) ne peuvent pas y être créés. Les clients peuvent déployer des environnements Human Resources sur l’infrastructure des applications de finances et d’opérations. Pour en savoir plus, voir [Mettre en service Human Resources dans l’infrastructure des applications de finances et d’opérations](/hr-admin-setup-provision-fo.md).

> [!IMPORTANT]
> L’infrastructure de l’application de finances et d’opérations prend en charge la suppression d’un environnement. Pour plus d’informations sur la suppression d’un environnement, voir [Supprimer un environnement](../fin-ops-core/dev-itpro/deployment/deployenvironment-newinfrastructure.md#delete-an-environment).

Cet article explique le processus de suppression d’une version d’évaluation ou d’un environnement de production pour Microsoft Dynamics 365 Human Resources.

## <a name="remove-a-test-drive-environment"></a>Suppression d’un environnement de test

Les tests Human Resources sont provisionnés avec une stratégie d’expiration de 60 jours. Toutefois, les propriétaires des environnements de test ont l’option de mettre fin à leur période d’essai en suivant les étapes suivantes. 

1. Accédez au [centre d’administration Power Apps](https://admin.businessplatform.microsoft.com/).
2. Sélectionner **Environnements**.
3. Sélectionnez l’environnement de test, avec un modèle de dénomination similaire à ceci : TestDrive – alias@domain
4. Sélectionnez **Supprimer** et confirmez la décision. 

L’environnement de test existant est supprimé. Une fois supprimé, vous pouvez vous inscrire à un nouvel environnement de test. 

## <a name="remove-a-production-environment"></a>Suppression d’un environnement de production

Cet article suppose que vous avez acheté Human Resources par l’intermédiaire d’un fournisseur de solutions Cloud (CSP) ou dans le cadre d’un contrat d’architecture d’entreprise (EA). 

Comme un seul environnement Human Resources est contenu dans un seul environnement Power Apps, il existe deux options à prendre en compte lorsque vous supprimez un environnement : 
- **Supprimer l’intégralité de l’environnement Power Apps.** La première option est recommandée lorsque vous avez créé un environnement Power Apps expressément pour l’approvisionnement de Human Resources, et que vous venez de commencer l’implémentation, ou que vous n’avez pas établi d’intégration.  
- **Supprimer uniquement Human Resources.** L’option est utile lorsque vous avez établi un environnement Power Apps rempli avec des données enrichies qui sont exploitées dans Microsoft Power Apps et Power Automate.


> [!Important]
> Avant de supprimer l’environnement Power Apps, vérifiez qu’il n’est pas utilisé pour des intégrations de données enrichies en dehors de la portée de Human Resources. Notez également que les environnements Power Apps par défaut ne peuvent pas être supprimés. 

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
7. Sélectionnez l’instance à supprimer, qui doit être marquée avec un statut de déploiement **Supprimé**.
8. Sélectionnez **Supprimer l’instance** et confirmez votre décision. 

## <a name="recover-a-soft-deleted-environment"></a>Récupérer un environnement supprimé de manière temporaire

Si vous supprimez l’environnement Power Apps auquel votre environnement Human Resources est connecté, le statut de l’environnement Human Resources dans LCS est **Suppression temporaire**. Dans ce cas, les utilisateurs ne peuvent pas se connecter à Human Resources.

Pour restaurer l’environnement :

1. Suivez les instructions dans [Récupérer l’environnement Power Apps](/power-platform/admin/recover-environment).

2. Contactez le support pour restaurer l’environnement Human Resources. Pour plus d’informations, voir [Obtenir de l’aide](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

> [!Warning]
> Les environnements Power Apps ne sont enregistrés que pendant sept jours après la suppression. Vous devez récupérer l’environnement dans le délai de sept jours.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
