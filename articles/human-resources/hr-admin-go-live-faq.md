---
title: FAQ sur le lancement
description: Cette rubrique répertorie les questions fréquemment posées sur le lancement d’un projet de mise en œuvre de Dynamics 365 Human Resources.
author: rachel-profitt
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c449ae6eb84fb4150072c386d02b100ca3cca219
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067224"
---
# <a name="go-live-faq"></a>FAQ sur le lancement 


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Cette rubrique répertorie les questions fréquemment posées sur le lancement d’un projet de mise en œuvre de Dynamics 365 Human Resources. 

## <a name="when-can-i-configure-and-request-my-production-environment"></a>Quand puis-je configurer et demander mon environnement de production ? 

En règle générale, un environnement de production est déployé après avoir satisfait aux critères suivants :

- Toutes les personnalisations sont entièrement codées.
- Le test d’acceptation par l’utilisateur (UAT) est terminé.
- Le client a approuvé la solution.
- Il n’y a pas de problèmes bloquant le lancement. 

Lorsque les clients qualifiés en sont à ce stade, l’équipe Microsoft FastTrack travaillera avec l’équipe de projet pour effectuer une évaluation du lancement. 

## <a name="what-are-the-prerequisites-to-deploying-a-production-environment"></a>Quelles sont les conditions préalables au déploiement d’un environnement de production ? 

Pour obtenir la liste des prérequis, voir [Préparer le lancement](hr-admin-go-live-prepare.md). 

## <a name="what-is-a-go-live-assessment"></a>Qu’est-ce qu’une évaluation du lancement ?  

L’évaluation du lancement fait partie du [Programme Microsoft FastTrack](/dynamics365/fasttrack/). Au cours de cet examen, un architecte de solution évalue si un projet de mise en œuvre est prêt pour une transition et un lancement réussis. Cet examen est obligatoire pour chaque projet d’implémentation avant de pouvoir demander à être lancé dans un environnement de production. 

## <a name="our-sandbox-environments-are-deployed-in-the-central-us-datacenter-we-want-our-production-environments-to-be-deployed-in-the-west-us-datacenter-can-i-select-west-us-as-the-datacenter-in-my-production-configuration"></a>Nos environnements Sandbox sont déployés dans le centre de données USA Centre. Nous voulons que nos environnements de production soient déployés dans le centre de données USA Ouest. Puis-je sélectionner USA Ouest comme centre de données dans ma configuration de production ? 

LCS ne vous empêche pas de sélectionner un centre de données différent lorsque vous déployez un environnement Human Resources, mais nous vous recommandons vivement de ne pas sélectionner un centre de données différent.  

Si vous souhaitez que votre environnement de production se trouve dans le centre de données de l’ouest des États-Unis, vous devez d’abord redéployer vos environnements Sandbox dans le centre de données de l’ouest des États-Unis, les tester et vous déconnecter. 

Pour plus d’informations sur la sélection du centre de données approprié, voir [Configuration réseau requise](../fin-ops-core/fin-ops/get-started/system-requirements.md#network-requirements). 

## <a name="what-level-of-access-do-i-have-to-the-azure-resources-for-my-human-resources-environments"></a>Quel niveau d’accès ai-je aux ressources Azure pour mes environnements Human Resources ?  

L’accès aux environnements Human Resources est limité. Vous ne pouvez pas accéder à la machine virtuelle (VM) ou à Microsoft Internet Information Services (IIS). Vous ne pouvez pas non plus accéder à la base de données via Microsoft SQL Server Management Studio. 

Bien que vous ne puissiez pas accéder à vos ressources Azure ou à l’environnement Dynamics 365 Human Resources directement, il existe des fonctionnalités supplémentaires que vous pouvez utiliser pour accéder à vos données :

- Vous pouvez déployer une base de données Azure SQL dans votre propre client Azure et utiliser la fonctionnalité Bring Your Own Database (BYOD) pour synchroniser les données. Pour plus d’informations, consultez [Apporter votre propre base de données (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md).

- Vous pouvez utiliser l’intégration de Dataverse pour synchroniser les entités sélectionnées dans la base de données Dataverse. Pour plus d’informations, consultez les [tables Dataverse](hr-developer-entities.md). 

## <a name="how-often-is-my-production-database-backed-up"></a>À quelle fréquence ma base de données de production est-elle sauvegardée ? 

Les bases de données sont protégées par des sauvegardes automatiques aux fréquences suivantes :

| Type de sauvegarde | Fréquence |
| --- | --- |
| Sauvegarde complète de base de données | Toutes les semaines |
| Sauvegarde différentielle de base de données | Toutes les 12 à 24 heures |
| Sauvegarde du journal des transactions | Toutes les 5 à 10 minutes |

Microsoft conserve suffisamment de sauvegardes pour permettre la restauration à un moment donné (PITR) au cours des 14 derniers jours. 

Pour plus d’informations, voir [En savoir plus sur les sauvegardes de base de données SQL](/azure/azure-sql/database/automated-backups-overview?tabs=single-database). 

## <a name="can-i-request-a-copy-of-the-backup-of-my-production-database"></a>Puis-je demander une copie de la sauvegarde de ma base de données de production ? 

Non. Cependant, vous pouvez soumettre une demande de service d’actualisation de la base de données pour copier votre environnement de production dans votre environnement Sandbox. Vous pouvez déployer une base de données Azure SQL dans votre propre client Azure et utiliser la fonctionnalité BYOD pour synchroniser les données de votre environnement de production. Pour plus d’informations, consultez [Apporter votre propre base de données (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md). 

## <a name="how-do-i-move-my-sandbox-environment-to-production-for-go-live"></a>Comment déplacer mon environnement Sandbox vers un environnement de production pour le lancement ? 

Étant donné qu’aucune fonction de copie n’est disponible pour déplacer votre environnement d’un environnement Sandbox vers un environnement de production, vous devez utiliser des packages de données pour déplacer des données dans votre environnement de production.  

Nous vous recommandons de conserver une liste claire des entités configurées dans votre bac à sable tout au long du projet. Testez ensuite le processus de basculement et de migration de tous les packages de données nécessaires à votre lancement. Vous devez déplacer manuellement tous les packages de données dans l’environnement de production lorsque vous êtes prêt pour le lancement. 

## <a name="what-should-i-do-if-my-production-environment-is-down"></a>Que dois-je faire si mon environnement de production est en panne ? 

Pour signaler une interruption de l’environnement de production, suivez le processus décrit dans [Signaler une panne de production](../fin-ops-core/dev-itpro/lifecycle-services/report-production-outage.md). 

 ## <a name="see-also"></a>Voir également :

 [Préparation au lancement](hr-admin-go-live-prepare.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
