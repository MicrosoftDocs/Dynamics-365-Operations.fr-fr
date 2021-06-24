---
title: Vue d’ensemble des plans généraux
description: Utilisez différents plans généraux pour prendre en charge les opérations de travail quotidiennes de votre entreprise, simuler différentes stratégies de planification que vous souhaitez surveiller et mettre en œuvre une politique d’entreprise, par exemple en ce qui concerne les performances internes ou la satisfaction des clients.
author: roxanadiaconu
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqParameters, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.custom: 7911
ms.assetid: a116b7de-3d6d-4321-87ba-5a5d99c2f64e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3da1e7d4f6fb709f5ed849022b199a367dbafbee
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187504"
---
# <a name="master-plans-overview"></a>Vue d’ensemble des plans généraux

[!include [banner](../includes/banner.md)]

Utilisez différents plans généraux pour prendre en charge les opérations de travail quotidiennes de votre entreprise, simuler différentes stratégies de planification que vous souhaitez surveiller et mettre en œuvre une politique d’entreprise, par exemple en ce qui concerne les performances internes ou la satisfaction des clients. 

Vous pouvez configurer des plans généraux dans la page **Plans généraux**.

Il existe deux types de plans :
-   **Plan statique** – Le calcul de planification utilise les données actuelles pour générer un plan de besoins nets. Ce plan n’est pas modifié jusqu’à la prochaine exécution de la planification ou de la modification manuelle du plan. Il s’agit d’un plan opérationnel sur lequel différents types d’employés de l’entreprise, tels qu’un acheteur ou un gestionnaire de production, peuvent baser leurs décisions et qu’ils peuvent utiliser pour effectuer leurs tâches et activités quotidiennes.
-   **Plan dynamique** – Ce plan démarre avec le plan de besoins nets qui a été généré par la planification. Cependant, vous pouvez mettre à jour le plan dynamique chaque fois que les données générales changent. Cela peut être le cas lorsque vous créez une commande client, par exemple. Cela vous permet de surveiller le réseau de commandes et la disponibilité d’articles changeants sans déranger le plan statique que d’autres utilisent pour leurs processus de travail.

Une entreprise peut choisir de travailler uniquement avec un plan dynamique ou d’utiliser à la fois un plan statique et un plan dynamique. De plus, vous pouvez configurer un plan général pour refléter une stratégie particulière ou résoudre un problème. Voici quelques exemples :
-   définition de niveaux de stock supérieurs pour s’assurer contre les ruptures de stock ;
-   définition de marges de sécurité plus longues pour se protéger contre les fournisseurs peu fiables.

Vous pouvez également définir le plan dynamique de démarrage de manière à ce qu’il soit mis à jour avec le nouveau plan de besoins à chaque fois que vous exécutez la planification. Vous pouvez spécifier ces paramètres dans la page **Paramètres de planification**.



## <a name="additional-resources"></a>Ressources supplémentaires

[Paramètres de couverture](coverage-settings.md)

[Division des planifications tactique et opérationnelle pour le calcul PDP/MRP](https://blogs.msdn.com/b/axmfg/archive/2012/10/12/separating-tactical-and-operative-planning-for-master-scheduling.aspx)

[Planification : Utilisez un plan général statique et dynamique ou utilisez un plan ?](https://community.dynamics.com/ax/b/msdynaxlessonslearned/archive/2014/01/16/master-planning-use-a-static-and-dynamic-master-plan-or-use-one-plan)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]