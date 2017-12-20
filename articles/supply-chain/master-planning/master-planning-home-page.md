---
title: Page d'accueil de la planification
description: "La planification permet aux sociétés de déterminer et d'équilibrer les futurs besoins en matières premières et en capacités afin d'atteindre leurs objectifs."
author: YuyuScheller
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: roxanadiaconu
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a24f75bf7e27702505d8a61ae3db83d03fe4a933
ms.openlocfilehash: a2e91cd2b72ffed78669fe3cc83b141db6f26aa2
ms.contentlocale: fr-fr
ms.lasthandoff: 11/29/2017

---

# <a name="master-planning-home-page"></a>Page d'accueil de la planification

[!include[banner](../includes/banner.md)]


La planification permet essentiellement aux sociétés de déterminer et d'équilibrer les futurs besoins en matières premières et en capacités afin d'atteindre leurs objectifs. La planification évalue les éléments suivants : 

-  Quelles matières premières et capacités sont actuellement disponibles ? 
-  Quelles matières premières et capacités sont nécessaires pour réaliser la production ? Par exemple, ce qui doit être fabriqué, acheté, transféré ou mis de côté en tant que stock de sécurité avant de réaliser la production.

La planification utilise les informations pour calculer les besoins et générer des ordres prévisionnels.

Les trois principaux processus de planification sont :

-  **Planification** - Le plan général calcule les besoins nets. Il est basé sur les commandes actuelles réelles et permet aux sociétés de contrôler le réapprovisionnement quotidien du stock à court terme. Un autre terme pour le décrire est *Plan des besoins nets*. Pour plus d'informations, voir [Planification](master-plans.md). 

-  **Planification prévisionnelle** - Le calendrier des prévisions calcule les besoins bruts. Il est basé sur les futures projections (ou prévisions), et permet aux sociétés d'effectuer la planification à long terme des matières et des capacités. Pour plus d'informations, voir [Planification prévisionnelle](introduction-demand-forecasting.md). 

-  **Planification intersociétés** - Le plan général intersociétés calcule les besoins nets dans les entités juridiques. Il relie la demande et l'approvisionnement entre les sociétés non seulement pour la demande et l'approvisionnement fermes à court terme, mais aussi pour la demande et l'approvisionnement planifiés (qui ne sont pas encore confirmés) à long terme. Pour plus d'informations, voir [Planification intersociétés](https://mbspartner.microsoft.com/AX/CourseOverview/1276) (eLearning) (nécessite un compte CustomerSource). 

Les sociétés peuvent modifier la sortie du plan. Ils peuvent exécuter les plans de régénération, les plans de modification nette, ou les deux. Les plans de régénération mettent à jour l'ensemble des besoins, tandis que les plans de modification nette ne mettent à jour que le plan des articles présentant de nouveaux besoins depuis la dernière exécution de la planification.

Les plans de calcul PDP/MRP impliquent généralement le court terme, qui peut aller d'une semaine à six mois. Le module Planification détermine les besoins en approvisionnement (matières) et en capacité (ressources) qui répondent à la demande actuelle (besoins nets). Dans la plupart des sociétés il est étendu pour inclure le délai cumulé le plus long entre les produits à recevoir.

## <a name="learning-map"></a>Programme de formation

Le programme de formation suivant montre les principaux concepts et tâches qui constituent la structure du module Planification. Cliquez sur les liens dans la section [Liens rapides](#quick-links) pour savoir comment utiliser le module.

[![Programme de formation pour la planification](./media/master-planning-learning-map.png)](./media/master-planning-learning-map.png)

## <a name="quick-links"></a>Liens rapides
|      |   |
|------|---|
|        [Plans généraux](master-plans.md)       |     [Générer un plan avec contrainte](./tasks/constrained-plan.md)  |
| [Créer un plan matières pour des coproduits](./tasks/create-material-plan-co-products.md)   |  [Planification et fonctionnalité multisite](master-plan-multisite-functionality.md)  |
| [Créer un plan intersociétés](./tasks/create-intercompany-plan.md) | [Vue d'ensemble de la prévision de la demande](introduction-demand-forecasting.md)  | 
|[Clés de réduction](reduction-keys.md)| [Notions de base de la planification](https://mbspartner.microsoft.com/AX/CourseOverview/1275) (eLearning) (nécessite un compte CustomerSource)     |
|  [Planification pour la conception de processus](https://mbspartner.microsoft.com/D365E/CourseOverview/1514) (eLearning) (nécessite un compte CustomerSource) | [Planification intersociétés](https://mbspartner.microsoft.com/AX/CourseOverview/1276) (eLearning) (nécessite un compte CustomerSource)|
                                  
## <a name="additional-resources"></a>Ressources supplémentaires

### <a name="roadmaps"></a>Calendriers de lancement
Accédez au [Calendrier de lancement de Microsoft Dynamics 365](https://roadmap.dynamics.com/) pour découvrir les nouvelles fonctions qui ont été lancées ou qui sont en développement.

### <a name="blogs"></a>Blogs
Vous trouverez des avis, des actualités et d'autres informations concernant la planification et d'autres solutions sur le [Blog de l'équipe R&D de Dynamics AX chargée de la fabrication](https://blogs.msdn.microsoft.com/axmfg) et sur le [Blog de l'équipe R&D de Dynamics AX chargée de la gestion de la chaîne d'approvisionnement](https://blogs.msdn.microsoft.com/dynamicsaxscm).

### <a name="task-guides"></a>Guides de tâches
Une aide supplémentaire est disponible sous forme de guides de tâche dans Finance and Operations. Pour accéder aux guides de tâche, cliquez sur le bouton **Aide** de n'importe quelle page.

### <a name="webinars"></a>Webinaires
[Utiliser Azure Machine Learning pour la prévision de la demande](https://www.youtube.com/watch?v=4nQsccdFFDA&feature=youtu.be)





