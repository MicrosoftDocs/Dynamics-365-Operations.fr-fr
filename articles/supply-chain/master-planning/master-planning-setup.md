---
title: Paramétrer une planification
description: Cette rubrique décrit les différentes stratégies et les paramètres importants utilisés pour paramétrer la planification.
author: t-benebo
ms.date: 07/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: e30b02a6f98f638954adc7ec335babd518b92bf4
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5909401"
---
# <a name="set-up-master-planning"></a>Paramétrer une planification

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les différentes stratégies et les paramètres importants utilisés pour paramétrer la planification. Elle inclut une vue d’ensemble des types de plans qui sont utilisés par la planification et explique quelle stratégie de plan utiliser en fonction des besoins de l’entreprise. Elle décrit également les paramètres principaux qui affectent le plan et explique comment ces paramètres influencent les ordres prévisionnels qui sont suggérés.

## <a name="types-of-master-plans"></a>Types de planification

Une planification comporte deux types de plans : statique et dynamique. Chaque type est conçu pour un usage différent. Pour les meilleures performances, nous vous recommandons d’utiliser le plan approprié à votre scénario.

### <a name="static-plan"></a>Plan statique

Le plan statique n’est pas modifié, indépendamment des modifications de l’offre et de la demande, jusqu’à la prochaine mise en exécution de la planification.

Le plan statique est utilisé pour approuver et confirmer les ordres qui sont suggérées. Il s’agit d’un plan opérationnel sur lequel différents types d’employés de l’entreprise (tels qu’un acheteur ou un gestionnaire de production) peuvent baser leurs décisions et qu’ils peuvent utiliser pour effectuer leurs tâches et activités quotidiennes.

Le plan statique prend également en charge la régénération. Un plan amélioré totalement nouveau est calculé à chaque fois que la planification est exécutée, et les ordres existants qui n’ont pas encore été approuvés sont supprimés.

### <a name="dynamic-plan"></a>Plan dynamique

Le plan dynamique commence généralement comme une copie du plan statique, mais il peut être mis à jour chaque fois que les données principales sont modifiées. Par exemple, si les données sont modifiées, une nouvelle commande client est créée.

Le plan dynamique est utilisé pour la planification ad-hoc. Il permet à l’entreprise de surveiller le réseau de commandes et la disponibilité des articles changeants sans déranger le plan statique que d’autres personnes utilisent pour leurs processus. Il est particulièrement utilisé pour le système CTP (capable to promise). Le plan dynamique est le plan par défaut lorsque les besoins nets sont ouverts à partir des pages de commandes (telles que les pages commandes client, commandes fournisseur, ou ordres de fabrication).

Le plan dynamique utilise la modification nette. Par conséquent, il permet de garantie un délai d’exécution plus rapide.

## <a name="strategies-for-using-master-plans"></a>Stratégies d’utilisation des planifications

Vous pouvez utiliser un plan ou deux plans dans la planification. La stratégie que vous utilisez dépend de vos exigences métier.

### <a name="one-plan-strategy"></a>Stratégie à un plan

Pour la stratégie à un plan, vous utilisez la même planification pour le plan statique et le plan dynamique. Cette stratégie est utilisée pour les scénarios de création de stock, dans lesquels vous ne devez généralement pas simuler de plan qui satisfait une commande.

La stratégie à un plan est généralement utilisée dans des secteurs de vente au détail et de distribution, ou lorsque les dates de livraison sont confirmées sur la base de contrats de niveau de service (SLA) ou de délais. Pour le plan, le contrôle de date de livraison peut être utilisé sans système CTP.

Si vous devez effectuer une simulation, le plan peut être réexécuté pour les articles nécessitant une simulation. Les ordres prévisionnels que produisent les simulations de commande sont généralement confirmés.

### <a name="two-plan-strategy"></a>Stratégie à deux plans

Pour la stratégie à deux plans, vous utilisez un plan statique et un plan dynamique différent. La stratégie à deux plans est généralement utilisée pour les scénarios de configuration sur commande et de création de stock, dans lesquels vous devez effectuer des simulations de commande client et calculer les dates de livraison précises pour les commandes client, mais les calculs ne doivent pas affecter les opérations quotidiennes. Ces simulations sont toujours effectuées dans le plan dynamique. La stratégie à deux plans est utile dans les secteurs automobile et équipementier (OEM), par exemple.

Pour la stratégie à deux plans, un CTP de contrôle de date de livraison peut être utilisé. Lorsque le système CTP est utilisé, il déclenche automatiquement l’exécution dans le plan dynamique.

### <a name="setting-up-the-plans"></a>Paramétrage des plans

Vous pouvez créer des plans dans la page **Plans généraux** (**Planification \> Paramétrage \> Plans \> Plans généraux**).

Vous pouvez spécifier les plans à utiliser pour le plan statique et le plan dynamique en définissant les champs **Plan général statique actuel** et **Plan général dynamique actuel** sur la page **Paramètres de planification** (**Planification \> Paramétrage \> Paramètres de Planification**). Pour utiliser une stratégie à un plan, sélectionnez le même plan dans les champs **Plan général statique actuel** et **Plan général dynamique actuel**.

## <a name="types-of-planning-methods"></a>Types de méthodes de planification

Trois méthodes de calcul peuvent être utilisées pour exécuter la planification : régénération et modification nette Chaque méthode produit un plan différent lorsqu’elle est exécutée.

Vous spécifiez la méthode de planification dans la boîte de dialogue **Exécution de planification**. Pour ouvrir cette boîte de dialogue, accédez à **Planification \> Planification \> Exécution \> Planification**, ou sélectionnez **Exécuter** dans l’espace de travail **Planification**.

### <a name="regeneration"></a>Régénération

La méthode de planification par régénération supprime les ordres prévisionnels existants, à moins qu’ils ne soient confirmés. Elle génère de nouveaux ordres prévisionnels, en fonction de tous les besoins. La régénération est la seule méthode de planification disponible pour les plans statiques.

- Les modifications de l’approvisionnement sont prises en compte. Ces modifications incluent les modifications des prévisions.
- Cette méthode respecte le code couverture **Période**.
- Cette méthode prend en charge la fonctionnalité de substitution de produit (PI).

### <a name="net-change"></a>Modification nette

La méthode de planification par modification nette génère des ordres prévisionnels pour couvrir les demandes créées ou modifiées depuis la dernière exécution de la planification. Les modifications de l’approvisionnement ne sont pas prises en compte lorsque cette méthode est exécutée. Le système ne prend pas en compte les nouveaux approvisionnements, et ordres prévisionnels créés précédemment ne sont pas supprimés s’ils ne sont plus nécessaires. La méthode de planification par modification nette s’exécute plus rapidement que la méthode de régénération. Elle n’est disponible que pour les plans dynamique.

- Les dates d’action et les dates de début au plus tôt sont mises à jour pour toutes les demandes.
- Cette méthode ne respecte pas le code couverture **Période**.
- Cette méthode ne satisfait pas la prévision, même si elle est sélectionnée dans le plan.
- Cette méthode ne prend pas en charge la fonctionnalité de substitution de produit (PI).

### <a name="net-change-minimized"></a>Modification nette réduite

La méthode de planification par modification nette minimisée génère des ordres prévisionnels pour couvrir uniquement les demandes créées ou modifiées depuis la dernière exécution de l’ordonnancement de la planification. Pour cette méthode, contrairement à la méthode par modification nette, les dates d’action et les dates de début au plus tôt ne sont mises à jour que pour les demandes nouvelles ou modifiées. Cette méthode de planification n’est disponible que pour les plans dynamiques.

## <a name="types-of-scheduling-methods"></a>Types de méthodes d’ordonnancement

Pour chaque plan, sous l’organisateur **Général** de la page **Plans généraux** (**Planification \> Paramétrage \> Plans \> Plans généraux**), vous devez sélectionner la méthode d’ordonnancement utilisée pour les ordres de fabrication. Vous pouvez planifier la production au niveau des opérations et des tâches.

### <a name="operations-scheduling"></a>Ordonnancement

Vous pouvez utiliser l’ordonnancement pour fournir une estimation globale du processus de production dans le temps. L’ordonnancement n’éclate pas les opérations de la gamme de production en tâches. Pour plus d’informations sur l’ordonnancement des opérations, voir [Ordonnancement](/dynamics365/unified-operations/supply-chain/production-control/operations-scheduling).

### <a name="job-scheduling"></a>Planification de tâche

L’ordonnancement des tâches est une méthode d’ordonnancement plus détaillée, où chaque opération est divisée en ses tâches individuelles. L’ordonnancement des tâches fournit des informations sur la capacité. Il concerne généralement l’ordonnancement de tâches individuelles dans l’atelier et se déroule normalement immédiatement ou à court terme. Pour plus d’informations sur l’ordonnancement des tâches, voir [Ordonnancement des tâches](/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="time-fences-in-days"></a>Plages de gestion en jours

Pour chaque plan, vous pouvez sélectionner la durée dans l’avenir du calcul par la planification des divers besoins et autres éléments. Cette période est appelée *plage de gestion*. Pour les meilleures performances de la planification, il est recommandé d’ajuster les différentes plages de gestion pour répondre aux besoins de l’activité. Pour chaque plan, vous trouverez les plages de gestion dans l’organisateur **Plage de gestion en jours** de la page **Plans généraux** (**Planification \> Paramétrage \> Plans \> Plans généraux**).

> [!NOTE]
> La plage de gestion indique la durée dans l’avenir du calcul par la planification des divers besoins et autres éléments. Les plages de gestion sélectionnées dans cette page annulent et remplacent les plages de gestion définies dans le groupe de couverture. Cela signifie que le fait de définir l’option de plage de gestion sur Oui et de définir les jours a pour effet de remplacer la plage de gestion définie dans le groupe de couverture. Lorsqu’elle est définie sur Non, la plage de gestion est définie dans le groupe de couverture. Enfin, si vous ne souhaitez pas ou n’avez pas besoin d’utiliser une option (par exemple vous ne voulez pas utiliser de messages d’action), définissez-la sur **Oui**, et définissez la plage de gestion sur **0** (zéro) jours.

### <a name="coverage"></a>Couverture

La plage de gestion de couverture représente la période d’ordonnancement, soit la durée d’inclusion de la demande. En d’autres termes, elle indique votre horizon de planification.

En définissant l’option **Couverture** sur **Oui**, vous pouvez remplacer la plage de gestion de couverture définie pour l’article lors du calcul PDP/MRP. Dans ce cas, entrez le nombre de jours durant lesquels le calcul PDP/MRP doit couvrir les besoins. La plage de gestion de la couverture est calculée en avant à partir de la date actuelle. Les besoins apparaissant avant la date actuelle sont toujours traités.

> [!NOTE]
> Pour les meilleures performances de la planification, il est recommandé d’ajuster la plage de gestion de couverture à l’horizon de la planification.

### <a name="freeze"></a>Geler

La plage de gestion de gel représente la période où les ordres prévisionnels existants ne sont pas modifiés lorsqu’un nouveau programme directeur est exécuté. Les ordres prévisionnels sont gelés et aucun nouvel ordre prévisionnel n’est suggéré.

En définissant l’option **Geler** sur **Oui**, vous pouvez remplacer la plage de gestion de gel définie pour l’article lors du calcul PDP/MRP. Dans ce cas, entrez le nombre de jours pendant lesquels l’activité de planification doit être gelée. Souvenez-vous que, pendant cette période, aucun nouvel ordre prévisionnel n’est généré et que les ordres prévisionnels existants ne peuvent pas être modifiés.

### <a name="firming"></a>Confirmation

La plage de gestion de confirmation indique l’horizon auquel les ordres prévisionnels sont automatiquement convertis en ordres de fabrication et en commandes fournisseur. Ce processus est également appelée *confirmation automatique des ordres prévisionnels*.

En définissant l’option **Confirmation** sur **Oui**, vous pouvez remplacer la plage de gestion de confirmation définie pour l’article lors du calcul PDP/MRP. Dans ce cas, entrez le nombre de jours pendant lesquels les commandes fournisseur prévisionnelles et les ordres de fabrication prévisionnels doivent être confirmés automatiquement. La plage de gestion de confirmation est calculée en avant à partir de la date d’établissement du calcul PDP/MRP. La confirmation automatique d’une commande fournisseur prévisionnelle n’est possible que si l’article est associé à un fournisseur.

### <a name="forecast-plan"></a>Programme prévisionnel

La plage de gestion du programme prévisionnel indique la durée dans l’avenir pendant laquelle la planification crée des ordres prévisionnels pour les articles ayant la demande prévue.

En définissant l’option **Programme prévisionnel** sur **Oui**, vous pouvez remplacer la plage de gestion du programme prévisionnel définie pour l’article lors du calcul PDP/MRP. Dans ce cas, entrez le nombre de jours pendant lesquels les prévisions de vente du programme prévisionnel doivent être incluses dans la planification.

### <a name="capacity"></a>Capacité

La plage de gestion de capacité indique la durée dans l’avenir pendant laquelle le système prend en compte la capacité maximale de vos ressources lorsqu’il planifie des commandes. En d’autres termes, le plan programme les ordres de fabrication en utilisant la gamme de production des articles, et il prend en compte les ressources et la capacité maximale de la gamme de production pour chaque ressource.

En définissant l’option **Capacité** sur **Oui**, vous pouvez remplacer la plage de gestion de capacité définie pour l’article lors du calcul PDP/MRP. Dans ce cas, entrez le nombre de jours pendant lesquels la capacité doit être prévue pour les ordres de fabrication prévisionnels. L’établissement du calcul PDP/MRP utilise la gamme de production active pour l’article et planifie en arrière à partir de la date de besoin. Si la date de besoin relative à un ordre de fabrication prévisionnel se situe hors de la plage de capacité, le délai est déterminé par le délai de livraison de l’article. La plage de gestion de capacité est calculée en avant à partir de la date actuelle.

### <a name="action-message"></a>Message d’action

Les messages d’action suggèrent les modifications qui peuvent être apportées à l’ordre d’approvisionnement existant pour optimiser le plan d’approvisionnement. Par exemple, ils peuvent vous recommander d’avancer ou de reporter certains ordres, ou d’augmenter ou diminuer les quantités des commandes.

En définissant l’option **Message d’action** sur **Oui**, vous pouvez remplacer la plage de gestion des messages d’action définie pour l’article lors du calcul PDP/MRP. Dans ce cas, entrez le nombre de jours pendant lesquels l’établissement du calcul PDP/MRP doit générer des messages d’action pour les besoins. La plage de gestion de message d’action est calculée en avant à partir de la date actuelle.

Pour plus d’informations sur les messages d’action, voir [Messages d’action](/dynamics365/unified-operations/supply-chain/master-planning/action-messages).

> [!NOTE]
> Le calcul des messages d’action entraîne un temps d’exécution de la planification plus long. Si les messages d’action ne sont pas régulièrement analysés et mis en application (chaque jour, chaque semaine), songez à désactiver leur calcul lors de l’exécution de la planification. Pour désactiver le calcul, dans la page **Plans généraux**, définissez la plage de gestion **Message d’action** sur **0** (zéro) pour le plan général que vous exécutez. Assurez-vous également que le paramètre **Message d’action** est désactivé pour tous les groupes de couverture.

### <a name="calculated-delays"></a>Retards calculés

Vous pouvez indiquer la durée dans l’avenir pendant laquelle les éventuels retards sont détectés et déclarés. De cette manière, vous pouvez planifier les dates de livraison (retardées) possibles.

Si un ordre prévisionnel ne peut pas être honoré pour la date demandée, il est prévu pour la date d’exécution la plus proche pour une transaction, en fonction des délais et de la disponibilité des matières et de la capacité.

### <a name="approved-requisitions-time-fence"></a>Plage de gestion des demandes approuvées

Vous pouvez paramétrer la planification pour créer des ordres prévisionnels pour les commandes de réapprovisionnement. Définissez l’option **Inclure les demandes** sur **Oui** sous l’organisateur **Général** de la page **Plans généraux**. Puis, lorsque l’objectif d’une commande est approuvée est le réapprovisionnement, la planification crée automatiquement un ordre prévisionnel correspondant pour le réaliser. La méthode de réapprovisionnement est déterminée par les stratégies de fourniture paramétrées pour les articles de votre organisation. Une fois la demande de réapprovisionnement créée et approuvée, aucune autre action n’est nécessaire de la part de l’utilisateur.

En définissant l’option **Plage de gestion des demandes approuvées** sur **Oui** sous l’organisateur **Plage de gestion en jours**, vous pouvez remplacer la plage de gestion des demandes approuvées qui est définie pour l’article lors du calcul PDP/MRP. Dans ce cas, entrez le nombre de jours dans le passé pendant lesquels les besoins provenant des demandes approuvées de type Réapprovisionnement doivent être inclus dans le calcul PDP/MRP. Par exemple, vous pouvez spécifier que seules les commandes en retard et non satisfaites des bons de commande approuvés qui ont été créés au cours des 10 derniers jours doivent être prises en compte et planifiées.

### <a name="sequencing"></a>Séquençage

Le classement permet d’organiser les ordres prévisionnels sur la base d’attributs de classement associés au produit fini. Il est souvent utilisé pour préparer les ordres de fabrication pour l’emballage. Par exemple, il peut être utilisé pour emballer des boîtes dans un ordre spécifique, selon la couleur et la taille.

En définissant l’option **Classement** sur **Oui**, vous pouvez spécifier la durée dans l’avenir pendant laquelle il convient de classer les opérations ou les tâches. Gardez à l’esprit que plus la plage de gestion est longue, plus l’exécution de la planification prend du temps.

### <a name="calculated-delays"></a>Retards calculés

Les options de retard permettent de garantir que les commandes ont des dates prévues réalistes. Les options suivantes sont disponibles dans l’organisateur **Retards calculés** de la page **Plans généraux** :

- **Vérifier que les ordres prévisionnels ne sont pas créés avant la date d’exécution de la planification** – Définissez cette option sur **Oui** pour garantir que les commandes ne peuvent pas être planifiées pour des dates dans le passé.
- **Ajouter le retard calculé à la date de besoin** (sous **Commandes fournisseur prévisionnelles**) – Définissez cette option sur **Oui** pour ajouter le retard calculé aux besoins.
- **Ajouter le retard calculé à la date de besoin** (sous **Ordres de fabrication prévisionnels**) – Définissez cette option sur **Oui** pour ajouter le retard calculé aux besoins.
- **Ajouter le retard calculé à la date de besoin** (sous **Transfert prévisionnel**) – Définissez cette option sur **Oui** pour ajouter le retard calculé aux besoins.
- **Ajouter le retard calculé à la date de besoin** (sous **Kanban prévisionnel**) – Définissez cette option sur **Oui** pour ajouter le retard calculé aux besoins.

Lorsque vous définissez les options **Ajouter le retard calculé à la date de besoin** sur **Oui** pour ajouter les retards aux dates de besoin, le système prend en compte la capacité des ressources et crée des ordres prévisionnels faisables. Le recalcul des dates d’ordre prévisionnel augmente le temps d’exécution de la planification. Par conséquent, si vous n’avez pas besoin d’utiliser de retards, définissez les options sur **Non**.

## <a name="positive-and-negative-days"></a>Jours positifs et négatifs

Les jours positifs et négatifs affectent la façon dont la planification suggère les ordres prévisionnels et les actions. Les jours positifs et négatifs sont définis dans le groupe de couverture d’article de l’article. Vous pouvez définir les différents groupes de couverture et définir leurs paramètres sur la page **Groupes de couverture** (**Planification \> Paramétrage \> Couverture \> Groupes de couverture**).

### <a name="positive-days"></a>Jours positifs

Les jours positifs indiquent la durée dans l’avenir pendant laquelle la planification tient compte du stock actuel ou des réceptions pour honorer la demande future. Par exemple, si les jours positifs sont définis sur **100**, le stock actuel peut être utilisée pour honorer la demande dans les 100 prochains jours. S’il existe une commande 150 jours à compter de la date actuelle, la planification génère un ordre prévisionnel pour satisfaire la demande, même si le stock disponible pour l’article peut satisfaire la commande. Pour les articles rapides dont le délai est court, vous ne pouvez pas utiliser le stock disponible pour un ordre qui est loin dans l’avenir. Dans ce cas, le stock disponible actuel sera rapidement épuisé, et il conviendra de passer d’autres commandes dans l’avenir pour satisfaire une demande future à temps, ce qui sera possible en raison du bref délai d’exécution de l’article.

Les jours positifs affectent également les messages d’action. Par exemple, le système peut vous recommander d’augmenter une commande fournisseur prévisionnelle pour qu’elle tienne compte d’une demande comprise dans le nombre de jours positifs dans le futur. Si les jours positifs sont définis sur **100**, et s’il existe demande pour un article dans 30 jours à compter de la date actuelle, le système crée un ordre prévisionnel pour satisfaire cette demande. S’il existe une demande pour le même article dans les 90 jours à compter de la date actuelle, le système recommandera que vous augmentiez la quantité de la commande dans 30 jours à compter de la date actuelle, afin que la commande couvre également la demande sous 90 jours. Toutefois, s’il existe une demande pour l’article dans 150 jours à compter de la date actuelle, le système ne recommandera pas que vous augmentiez la quantité de la commande qui a déjà été planifiée. Au lieu de cela, un nouvel ordre prévisionnel sera créé.

En règle générale, les jours positifs sont définis à un nombre qui est compris entre le plus long délai d’exécution des articles et la plage de gestion de couverture. Il est recommandé d’affecter des articles qui sont régulièrement obtenus ou produits à un groupe de couverture où le nombre de jours positifs est égal au délai d’exécution des articles.

### <a name="negative-days"></a>Jours négatifs

Les jours négatifs indiquent le retard acceptable de réception des articles. Ils représentent le nombre de jours que vous pouvez attendre avant de commander un nouveau réapprovisionnement, si vous avez un stock négatif ou pas assez de stock. Les jours négatifs répondent à la question : devons-nous créer une commande fournisseur pour l’article ou, devons-nous utiliser un achat existant, même en sachant que l’article sera en retard ?

Par exemple, vous avez une commande client pour un article pour dans 15 jours à compter de la date actuelle. Vous avez également une commande fournisseur pour le même article. Cette commande fournisseur sera réceptionné dans 20 jours à compter de la date actuelle. Souhaitez-vous que le système crée une commande fournisseur pour la commande client, ou souhaitez-vous utiliser la commande existante, même si vous ne pouvez pas honorer la commande client en temps voulu ? Si les jours négatifs sont définis sur un nombre inférieur à **5** pour indiquer que l’article peut avoir un retard maximal de cinq jours, le système crée une nouvelle commande fournisseur prévisionnelle pour satisfaire la commande client. Si les jours négatifs sont définis à un nombre supérieur à **5**, le système utilise la commande existante pour l’article.

Les jours négatifs affectent également les performances de la planification. Si les jours négatifs sont définis sur un nombre élevé, de nombreux messages d’action seront générés.

Nous vous recommandons de définir les jours négatifs à une valeur inférieure au délai d’exécution de l’article.

### <a name="dynamic-negative-days"></a>Jours négatifs dynamiques

Les jours négatifs dynamiques prennent en compte le délai d’exécution de l’article et les jours négatifs que vous avez spécifiés. Le système crée une nouvelle commande fournisseur prévisionnelle, selon la plage de gestion des jours négatifs qui est calculée suivant la formule ci-après :

Délai d’exécution + jours négatifs + date du jour – date de besoin

Le système utilise uniquement les ordres prévisionnels d’approvisionnement compris dans cette plage de gestion, et il crée un nouvel ordre prévisionnel en dehors de celle-ci. L’avantage des jours négatifs dynamiques est qu’ils incluent le délai d’exécution du produit individuel pour réutiliser les commandes existantes et éviter de créer de nouveaux ordres prévisionnels qui finiront par des jours de retard en raison des délais d’exécution. 

Pour plus d’informations, voir [Jours négatifs et jours négatifs dynamiques](/dynamics365/unified-operations/supply-chain/master-planning/more-about-dynamic-negative-days).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]