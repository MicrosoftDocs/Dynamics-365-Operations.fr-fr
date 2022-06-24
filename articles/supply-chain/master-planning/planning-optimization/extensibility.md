---
title: Extensibilité de l’optimisation de la planification
description: Cet article décrit les scénarios d’extensibilité pris en charge dans l’optimisation de la planification.
author: t-benebo
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-07-07
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 7d649110959e6bcfdaeb32dd53c55dbc446ed1be
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857542"
---
# <a name="planning-optimization-extensibility"></a>Extensibilité de l’optimisation de la planification

[!include [banner](../../includes/banner.md)]

Cet article décrit les scénarios d’extensibilité liés à la planification générale et pris en charge dans l’optimisation de la planification. Ces fonctionnalités de recherche dans le cloud sont disponibles à partir de Microsoft Dynamics 365 Supply Chain Management version 10.0.13.

## <a name="custom-processing-when-master-planning-is-completed"></a>Traitement personnalisé lorsque la planification générale est terminée

Dans le scénario d’extensibilité le plus courant dans l’optimisation de la planification, le traitement personnalisé est effectué après la mise à jour du plan. Par exemple, vous pouvez ajouter une colonne à la table des ordres planifiés (`ReqPO`) ou vous souhaitez extraire des informations statistiques du plan généré. Le principal point d’extensibilité qui permet ces scénarios est la méthode `jobCompletedSuccessfully` dans la classe `MpsMasterPlanningEvents`.

```X++
public static void jobCompletedSuccessfully(MpsMasterPlanningJobCompletedSuccessfullyEventArgs _args)
```

Voici un exemple d’extension qui définit un champ `CstmOrderPriority` sur l’ordre planifié.

```X++
[ExtensionOf(classStr(MpsMasterPlanningEvents))]
public static final class MpsMasterPlanningEvents_Cstm_Extension
{
    public static void jobCompletedSuccessfully(MpsMasterPlanningJobCompletedSuccessfullyEventArgs _args)
    {
        ttsbegin;

        var affectedPlannedOrdersQuery = _args.parmPostProcessingQueryBuilder().buildAffectedPlannedOrdersQuery();
        var affectedPlannedOrdersQueryRun = new QueryRun(affectedPlannedOrdersQuery);

        while (affectedPlannedOrdersQueryRun.next())
        {
            ReqPO reqPO = affectedPlannedOrdersQueryRun.get(tableNum(ReqPO));
            reqPO.selectForUpdate(true);
            reqPO.CstmOrderPriority = reqPO.ReqDate - systemDateGet() < 7 ? CstmPlannedOrderPriority::Urgent : CstmPlannedOrderPriority::Regular;
            reqPO.doUpdate();
        }

        ttscommit;

        next jobCompletedSuccessfully(_args);
    }

}
```

Lorsque vous ajoutez une logique personnalisée, tenez compte des contraintes et bonnes pratiques suivantes :

- La méthode `jobCompletedSuccessfully` est appelée en dehors de la portée de la transaction. Par conséquent, le plan est déjà visible pour l’utilisateur lorsque la logique personnalisée commence à s’exécuter. Si votre personnalisation définit des champs supplémentaires sur les ordres planifiés, il est important que vous informiez les utilisateurs que les valeurs de ces champs peuvent être cohérentes (en d’autres termes, elles peuvent être obsolètes immédiatement après la fin d’une tâche de planification).
- Une autre tâche de planification principale peut démarrer lorsque la méthode `jobCompletedSuccessfully` est appelée. La nouvelle tâche peut affecter le plan complet ou une partie du plan. La nouvelle tâche peut mettre à jour ou supprimer les ordres planifiés ou les transactions de demande qui ont été créés ou mis à jour dans le cadre de la tâche de planification qui a été traitée dans `jobCompletedSuccessfully`. Les exceptions de conflit de mise à jour doivent être gérées lorsque cet événement est étendu.
- Évitez d’utiliser une portée de transaction unique lorsque vous étendez cette méthode. Un seul cycle de planification principale peut produire des millions de transactions de demande et des centaines de milliers d’ordres planifiés. Si toutes ces transactions et ordres planifiés sont traités dans le cadre d’une transaction unique, de nombreux verrous SQL se produiront et bloqueront d’autres processus de planification. De plus, si la transaction est suspendue pendant une longue période, des « enregistrements fantômes » seront créés dans la base de données SQL. Les enregistrements fantômes affecteront négativement chaque processus du système.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]