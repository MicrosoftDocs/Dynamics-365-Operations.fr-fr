---
title: Migration vers l’Optimisation de la planification pour la planification
description: Cette rubrique fournit des informations sur le nouveau moteur de planification, l’Optimisation de la planification et sur la migration à partir du moteur existant.
author: ChristianRytt
manager: tfehr
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: crytt
ms.search.validFrom: 2020-11-05
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5fdbe472f24e1140f0af63da8a1fc4eafe4767a2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238036"
---
# <a name="migration-to-planning-optimization-for-master-planning"></a>Migration vers l’Optimisation de la planification pour la planification

[!include [banner](../includes/banner.md)]

Il est prévu que le moteur de planification intégré devienne obsolète (déconseillé). Il est remplacé par le complément Optimisation de la planification pour Microsoft Dynamics 365 Supply Chain Management. Cette rubrique fournit des informations sur l’impact sur les déploiements nouveaux et existants. Il comprend des informations sur les actions requises.

L’Optimisation de la planification permet le calcul de planification en dehors de Supply Chain Management et sa base de données Azure SQL. Les avantages associés à la fonctionnalité Optimisation de la planification incluent des performances améliorées et un impact minimisé sur la base de données SQL pendant l’exécution de la planification. Du fait que des exécutions rapides de la planification peuvent être effectuées même pendant les heures de bureau, les planificateurs peuvent réagir immédiatement aux modifications de la demande ou des paramètres.

Pour plus d’informations sur l’Optimisation de la planification, voir [Vue d’ensemble de l’Optimisation de la planification](planning-optimization/planning-optimization-overview.md).

## <a name="obsolescence-of-the-existing-master-planning-engine"></a>Obsolescence du moteur de planification existant

Microsoft est en train de rendre obsolète le moteur de planification intégré au profit de l’optimisation de la planification. Ce changement affecte tous les environnements cloud. Les installations sur site ne sont pas affectées. Dans les versions 10.0.16 et ultérieures, vous recevrez un message d’erreur si vous exécutez la planification intégrée sans générer d’ordres de fabrication planifiés. Cependant, l’exécution de la planification se terminera avec succès malgré le message d’erreur.

Pour plus d’informations sur l’obsolescence du moteur de planification intégré, consultez les annonces dans [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](../get-started/removed-deprecated-features-scm-updates.md).

## <a name="migration-messages-and-exceptions"></a>Migration, messages et exceptions

Les propriétaires d’environnements existants exécutant le moteur de planification intégré sans générer d’ordres de fabrication planifiés recevront un e-mail contenant des détails sur le processus d’exception. Nous vous recommandons de travailler avec un partenaire pour évaluer et planifier la migration vers l’optimisation de la planification.

Comme indiqué, vous recevrez un message d’erreur dans la version 10.0.16 et versions ultérieures si vous exécutez la planification intégrée sans générer d’ordres de fabrication planifiés. Ce message d’erreur comprend des conseils sur la migration et des instructions pour demander une exception.

### <a name="new-deployments"></a>Nouveaux déploiements

L’optimisation de la planification doit être considérée comme le moteur de planification par défaut pour tous les nouveaux déploiements dans le cloud. En général, l’optimisation de la planification doit être utilisée pour tous les nouveaux déploiements qui ne génèrent pas d’ordres de fabrication planifiés lors de la planification générale. Si un nouveau déploiement dépend de fonctionnalités que l’Optimisation de la planification ne prend actuellement pas en charge, vous pouvez demander une exception afin de pouvoir continuer à utiliser le moteur de planification intégré.

### <a name="existing-deployments"></a>Déploiements existants

Les propriétaires de déploiements cloud existants qui dépendent de la planification doivent prévoir de migrer vers l’Optimisation de la planification. Si votre mise en œuvre dépend de fonctionnalités que l’Optimisation de la planification ne prend actuellement pas en charge, vous pouvez demander une exception afin de pouvoir continuer à utiliser le moteur de planification intégré.

Pour les environnements qui utilisent actuellement des processus de planification devenus obsolètes, Microsoft enverra un e-mail à l’administrateur de l’environnement. Cet e-mail fournira des informations sur les actions requises pour migrer ou demander une exception.

## <a name="the-exception-process"></a>Processus d’exception

Vous pouvez demander une exception si vous devez continuer à utiliser le moteur de planification intégré car vos processus d’entreprise dépendent fortement d’au moins une fonctionnalité qui n’est pas actuellement mise en œuvre dans l’Optimisation de la planification. Pour une liste des fonctionnalités disponibles, voir [Analyse de l’ajustement de l’optimisation de la planification](planning-optimization/planning-optimization-fit-analysis.md).

Actuellement, les exceptions pour la migration vers l’optimisation de la planification ne sont pertinentes que si votre processus de planification n’inclut pas la fabrication (planification des ordres de fabrication planifiés générés par la planification) et si vous avez besoin du moteur de planification principal intégré au-delà de la version 10.0.15.

Une fois que les fonctionnalités requises seront disponibles, Microsoft fournira une période de grâce jusqu’à l’expiration de l’exception. L’administrateur de l’environnement sera informé lorsque les fonctionnalités requises seront disponibles et que la période de grâce aura commencé.

> [!NOTE]
> Vous ne pouvez demander une exception que pour les environnements de production, pas pour les environnements sandbox. Si vous devez désactiver l’erreur d’exception de l’optimisation de la planification sur un environnement sandbox d’infrastructure en tant que service (IaaS), exécutez la requête SQL fournie dans [l’environnements sandbox](#faq-sandbox).

## <a name="frequently-asked-questions"></a>Forum aux questions

### <a name="sandbox-environments"></a><a name="faq-sandbox"></a>Environnements de bac à sable

Puis-je utiliser la planification intégrée sur mon environnement sandbox ? Ai-je besoin d’une exception ?

**Réponse :** Les exceptions ne sont normalement pas pertinentes pour les environnements sandbox, car l’erreur d’exception de l’optimisation de la planification n’empêche pas le moteur de planification intégré de fonctionner correctement. Cependant, si le message d’erreur vous dérange, vous pouvez le désactiver sur un environnement sandbox IaaS (et non Service Fabric) en exécutant la requête suivante sur votre base de données :

```sql
-- Insert or update an enabled flight:
DECLARE @flightName NVARCHAR(100) = 'ReqPlanningOptimizationExceptionToggle';
IF NOT EXISTS (SELECT TOP 1 1 FROM SysFlighting WHERE flightName = @flightName)
    INSERT INTO SYSFLIGHTING(FLIGHTNAME,ENABLED, FLIGHTSERVICEID,PARTITION)
    SELECT @flightName, 1, 12719367,RECID FROM DBO.[PARTITIONS];
ELSE
    UPDATE SysFlighting SET enabled = 1, flightServiceId = 12719367 WHERE flightName = @flightName;
```

### <a name="on-premises-environments"></a>Environnements locaux

Mon environnements est local. Ai-je besoin d’une exception ?

**Réponse :** Non. Une exception n’est pas requise pour les environnements locaux. Vous pouvez continuer à utiliser la planification intégrée. L’administrateur de votre environnement sera informé si une action est requise.

### <a name="production-scenarios"></a>Scénarios de production

Nous utilisons des ordres de fabrication planifiés, mais je suis préoccupé par ce qui se passera lorsque nous passerons à la version 10.0.16. Dois-je prendre des mesures ?

**Réponse :** Vous ne devriez pas vous inquiéter. Vous pourrez continuer à utiliser la planification intégrée dans la version 10.0.16. Cependant, nous vous recommandons d’évaluer si la migration vers l’Optimisation de la planification peut démarrer avec la fonctionnalité actuelle. Nous vous recommandons également de rester informé des nouvelles fonctionnalités.

### <a name="email-from-microsoft"></a>E-mail de Microsoft

Notre administrateur d’environnement a reçu un e-mail de Microsoft. Cet e-mail indique que nous devons migrer vers l’Optimisation de la planification ou demander une exception. Dois-je prendre des mesures ?

**Réponse :** Oui. Votre environnement sera affecté à moins que vous ne suiviez les instructions de l’e-mail. Vous pouvez migrer vers l’Optimisation de la planification à la date spécifiée ou demander une exception en utilisant le lien dans l’e-mail. Ce lien ouvre un questionnaire. Après avoir rempli et envoyé ce questionnaire, vous recevrez une réponse par e-mail. Bien que ce processus soit manuel, Microsoft essaie de répondre dans un délai d’une semaine après l’envoi du questionnaire.

### <a name="error-messages"></a>Messages d’erreur

J’utilise la version 10.0.16 ou une version ultérieure et je reçois le message d’erreur suivant lorsque j’exécute la planification principale. La planification est-elle bloquée ?

> Vous recevez ce message d’erreur car le moteur de planification intégré a été utilisé pour les scénarios pris en charge par l’Optimisation de la planification. Vous devez migrer vers l’Optimisation de la planification maintenant, car la planification intégrée actuelle sera obsolète. Notez que ce cycle de planification s’est terminé avec succès.
>
> Si votre migration a de fortes dépendances sur les fonctionnalités en attente, une exception à l’utilisation continue du moteur de planification intégré peut être demandée.
>
> Remplissez le questionnaire suivant pour commencer et, le cas échéant, demander une exception pour la migration vers l’Optimisation de la planification.

**Réponse :** Non, la planification n’est pas bloquée. Votre cycle de planification principale s’est terminé avec succès et vous pouvez utiliser le résultat de la manière habituelle. Toutefois, pour éviter de recevoir ce message d’erreur lors des futures exécutions de planification générale, vous devez soit migrer immédiatement vers l’Optimisation de la planification, soit demander une exception à l’aide du lien dans le message d’erreur.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]