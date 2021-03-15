---
title: Jours négatifs et jours négatifs dynamiques
description: Cette rubrique fournit des informations sur les jours négatifs et les jours négatifs dynamiques, et la manière de les mettre à profit pour votre activité.
author: t-benebo
manager: tfehr
ms.date: 06/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2019-06-07
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c098c04e8804187f5111fd10cb858a0c63289e3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983617"
---
# <a name="negative-days-and-dynamic-negative-days"></a>Jours négatifs et jours négatifs dynamiques

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur les jours négatifs et les jours négatifs dynamiques, et la manière de les mettre à profit pour votre activité. La *plage de gestion des jours négatifs* représente le nombre de jours que vous pouvez attendre avant de commander un nouveau réapprovisionnement, si vous avez un stock négatif.

Les informations suivantes sont indiquées dans cette rubrique :

- La manière de créer les ordres prévisionnels.
- La corrélation entre la plage de gestion des jours négatifs et le délai d'exécution l'article
- La procédure de calcul de la plage de gestion des jours négatifs dynamiques, et la prise en compte du délai d'exécution de l'article dans le calcul
- La manière d'interpréter les [suggestions d'amélioration du délai d'exécution pour la planification des besoins matériels (planfication, MRP)](https://blogs.msdn.com/b/axmfg/archive/2015/01/02/checklist-for-improving-mrp-performance-part-2-how-to-setup-planning-parameters.aspx) qui sont associées aux jours négatifs

Cette rubrique utilise trois scénarios hypothétiques pour vous aider à comprendre ces informations. La différence entre ces scénarios est le moment où vous recevez la demande : avant, pendant ou après le délai d'exécution de l'article.

## <a name="scenario-1-you-get-demand-before-the-items-lead-time-period"></a>Scénario 1 : vous recevez la demande avant le délai d'exécution de l'article

Vous pouvez recevoir la demande relativement tôt dans le délai d'exécution de l'article ou juste avant le début de cette période. Voici un exemple de ce cas :

- L'article DemoProduct a un cycle d'approvisionnement de six jours.
- Au jour zéro (1er janvier), le niveau de stock de l'article DemoProduct est 0 (zéro).
- Au jour zéro (1er janvier), vous recevez une commande client pour une quantité de 10 de l'article DemoProduct.
- Au jour sept (7 janvier), il existe une commande fournisseur pour une quantité de 10 de l'article DemoProduct.

La figure suivante présente une vue graphique de ce scénario.

![Vue graphique du scénario 1](./media/negative-days-1.jpg)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>Cas A : les jours négatifs sont inférieurs au délai d'exécution de l'article

Si vous avez défini les jours négatifs à un nombre inférieur au délai d'exécution de l'article, la MRP recherche des réceptions de l'article DemoProduct dans la plage de gestion des jours négatifs. Comme elle ne trouve aucune réception, la MRP crée une nouvelle commande fournisseur prévisionnelle. Cet ordre prévisionnel est immédiatement retardé de six jours (le délai d'exécution). Par conséquent, il arrivera le 7 janvier. La commande fournisseur existante reçoit un message d'action **Annuler**, car la création de la nouvelle commande fournisseur prévisionnelle l'a rendue redondante.

La figure suivante présente une capture d'écran de ce cas.

![Capture d'écran du cas A pour le scénario 1](./media/negative-days-2.png)

La figure suivante présente une vue graphique de ce qui se produit dans ce cas.

![Vue graphique du cas A pour le scénario 1](./media/negative-days-3.png)

Si vous envisagez les performances de la MRP et êtes inquiet, ce cas n'est pas très performant. La MRP doit créer un ordre prévisionnel et doit calculer les retards et les actions. Ces tâches demandent du temps. Ce cas ajoute également deux transactions supplémentaires à votre plan. D'autre part, la commande client est retardée de seulement six jours, et non sept jours.

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>Cas B : les jours négatifs sont supérieurs au délai d'exécution de l'article

Pour améliorer les performances de la MRP, vous pouvez définir les jours négatifs à un nombre supérieur au délai d'exécution de l'article. Comme dans ce scénario vous ne pouvez pas obtenir l'approvisionnement dans le délai d'exécution, vous pouvez rechercher des réceptions pour autant que cette recherche soit raisonnable. Bien que le temps d'exécution de la MRP soit plus court, vous devez faire attention aux retards supplémentaires des commandes.

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>Cas C : corréler automatiquement le délai d'exécution l'article et la plage de gestion des jours négatifs

Pour corréler automatiquement le délai d'exécution l'article et la plage de gestion des jours négatifs, utilisez des jours négatifs dynamiques. Pour utiliser les jours négatifs dynamiques, accédez à **Planification \> Paramétrage \> Paramètres de planification**, puis, dans l'onglet **Général**, dans la section **Couverture**, définissez l'option **Utiliser des jours négatifs dynamiques** sur **Oui**. La MRP recherche alors des réceptions dans la plage de gestion des jours négatifs dynamiques. La plage de gestion est calculée selon la formule suivante :

Plage de gestion des jours négatifs dynamiques = délai d'achat + plage de gestion des jours négatifs + (date actuelle – date de besoin)

(Si le type de commande par défaut de l'article DemoProduct est **Production** ou **Transfert**, le délai d'exécution est celui du **stock** .)

Lorsque des jours négatifs dynamiques sont utilisés, la plage de gestion utilisée par la MRP pour rechercher des réceptions est à présent 6 + 2 + 0 = 8 jours. La MRP trouve la commande fournisseur existante et y associe la commande client. Aucun ordre prévisionnel n'est créé. Par conséquent, le temps d'exécution de la MRP est plus court. L'illustration suivante présente les besoins nets pour l'article DemoProduct.

![Besoins nets pour le cas C du scénario 1](./media/negative-days-4.png)

La figure suivante présente une vue graphique de ce qui se produit dans ce cas.

![Vue graphique du cas C pour le scénario 1](./media/negative-days-5.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>Cas D : utiliser uniquement des jours négatifs dynamiques

Si vous définissez les jours négatifs sur **0** (zéro) et utilisez seulement la plage de gestion des jours négatifs dynamiques, celle-ci est 6 + 0 + 0 = 6 jours. Dans ce cas, le résultat est identique au résultat du cas A pour ce scénario. La MRP doit créer un ordre prévisionnel et doit calculer les retards et les actions. Ces tâches prennent du temps et peuvent être laborieuses. Vous devez également traiter deux transactions supplémentaires. Étant donné que la demande ne peut pas être satisfaite à temps pour que l'article arrive, ce cas ajoute des complications inutiles à votre plan.

La figure suivante présente une capture d'écran de ce cas.

![Capture d'écran du cas D pour le scénario 1](./media/negative-days-6.png)

La figure suivante présente une vue graphique de ce qui se produit dans ce cas.

![Vue graphique du cas D pour le scénario 1](./media/negative-days-7.png)

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>Cas E : utiliser des jours négatifs supérieurs au délai d'exécution de l'article et la plage de gestion des jours négatifs dynamiques

Si vous définissez les jours négatifs à un nombre supérieur au délai d'exécution de l'article, et si vous utilisez également la plage de gestion des jours négatifs dynamiques, celle-ci est 6 + 6 + 0 = 12 jours. Cette approche peut produire une plage de gestion très longue dans laquelle la MRP doit rechercher les résultats. Pour plus d'informations sur la manière dont le cas E est lié à une situation où vous attribuez aux jours négatifs une longue plage de gestion, voir la section [Conclusion](#conclusion) de cette rubrique.

## <a name="scenario-2-you-get-demand-during-the-items-lead-time-period"></a>Scénario 2 : vous recevez la demande pendant le délai d'exécution de l'article

Vous pouvez recevoir la demande à un moment quelconque du délai d'exécution de l'article. Voici un exemple de ce cas :

- L'article DemoProduct a un cycle d'approvisionnement de six jours. 
- Au jour zéro (1er janvier), le niveau de stock de l'article DemoProduct est 0 (zéro).
- Au jour quatre (5 janvier), qui se situe à l'intérieur du délai d'exécution de l'article, vous recevez une commande client pour une quantité de 10 de l'article DemoProduct.
- Au jour sept (8 janvier), il existe une commande fournisseur pour une quantité de 10 de l'article DemoProduct.

La figure suivante présente une vue graphique de ce scénario.

![Vue graphique du scénario 1](./media/negative-days-8.png)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>Cas A : les jours négatifs sont inférieurs au délai d'exécution de l'article

Si vous avez défini les jours négatifs à un nombre inférieur au délai d'exécution de l'article, la MRP recherche des réceptions de l'article DemoProduct dans la plage de gestion des jours négatifs. Comme elle ne trouve aucune réception, la MRP crée une nouvelle commande fournisseur prévisionnelle qui utilise la date actuelle comme date de commande. Cet ordre prévisionnel est immédiatement retardé de six jours (le délai d'exécution). Par conséquent, il arrivera le 7 janvier. La commande fournisseur existante reçoit un message d'action **Annuler**, car la création de la nouvelle commande fournisseur prévisionnelle l'a rendue redondante.

La figure suivante présente une capture d'écran de ce cas.

![Capture d'écran du cas A pour le scénario 2](./media/negative-days-9.png)

La figure suivante présente une vue graphique de ce qui se produit dans ce cas.

![Vue graphique du cas A pour le scénario 2](./media/negative-days-10.png)

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>Cas B : les jours négatifs sont supérieurs au délai d'exécution de l'article

Ce cas ressemble au cas B du scénario 1. Si vous définissez les jours négatifs à un nombre supérieur au délai d'exécution de l'article, vous ne recevez pas de nouvel ordre prévisionnel. La commande client est associée à la commande fournisseur existante.

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>Cas C : corréler automatiquement le délai d'exécution l'article et la plage de gestion des jours négatifs

Ce cas ressemble au cas C pour le scénario 1, car les jours négatifs dynamiques y fonctionnent exactement de la même manière. La plage de gestion des jours négatifs dynamiques est désormais 6 + 2 – 4 = 4 jours. Si vous utilisez cette approche, la MRP recherche la commande fournisseur existante et y joint la commande client. Comme aucune nouvel ordre prévisionnel n'est créé, le temps d'exécution de la MRP est plus court.

La figure suivante présente une capture d'écran de ce cas.

![Capture d'écran du cas C pour le scénario 2](./media/negative-days-11.png)

La figure suivante présente une vue graphique de ce qui se produit dans ce cas.

![Vue graphique du cas C pour le scénario 2](./media/negative-days-12.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>Cas D : utiliser uniquement des jours négatifs dynamiques

Si vous définissez les jours négatifs sur **0** (zéro) et utilisez seulement la plage de gestion des jours négatifs dynamiques, celle-ci est désormais 6 + 0 - 4 = 2 jours. Dans ce cas, le résultat est identique au résultat du cas A pour ce scénario. Pour une vue graphique de ce qui se produit, voir le cas A pour ce scénario.

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>Cas E : utiliser des jours négatifs supérieurs au délai d'exécution de l'article et la plage de gestion des jours négatifs dynamiques

Si vous définissez les jours négatifs à un nombre supérieur au délai d'exécution de l'article, et si vous utilisez également la plage de gestion des jours négatifs dynamiques, celle-ci est 6 + 6 - 4 = 8 jours. Cette approche peut produire une plage de gestion très longue dans laquelle la MRP doit rechercher les résultats. Pour plus d'informations sur la manière dont le cas E est lié à une situation où vous attribuez aux jours négatifs une longue plage de gestion, voir la section [Conclusion](#conclusion) de cette rubrique.

## <a name="scenario-3-you-get-demand-after-the-items-lead-time-period"></a>Scénario 3 : vous recevez la demande après le délai d'exécution de l'article

Vous pouvez recevoir la demande après le délai d'exécution de l'article. Voici un exemple de ce cas :

- L'article DemoProduct a un cycle d'approvisionnement de six jours.
- Au jour zéro (1er janvier), le stock de l'article DemoProduct est 0 (zéro).
- Au jour sept (8 janvier), qui se situe à l'extérieur du délai d'exécution de l'article, vous recevez une commande client pour une quantité de 10 de l'article DemoProduct.
- Au jour 10 (11 janvier), il existe une commande fournisseur pour une quantité de 10 de l'article DemoProduct.

La figure suivante présente une vue graphique de ce scénario.

![Vue graphique du scénario 3](./media/negative-days-13.png)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>Cas A : les jours négatifs sont inférieurs au délai d'exécution de l'article

Si vous avez défini les jours négatifs à un nombre inférieur au délai d'exécution de l'article, la MRP recherche deux jours après la date de besoin de la commande client. Comme elle ne trouve rien, la MRP crée une nouvelle commande fournisseur prévisionnelle le 2 janvier. Cette commande fournisseur prévisionnelle est expédiée juste à temps pour honorer la demande de la commande client. La commande fournisseur existante reçoit un message d'action **Annuler**, car elle n'est pas nécessaire.

La figure suivante présente une capture d'écran de ce cas.

![Capture d'écran du cas A pour le scénario 3](./media/negative-days-14.png)

La figure suivante présente une vue graphique de ce qui se produit dans ce cas.

![Vue graphique du cas A pour le scénario 3](./media/negative-days-15.png)

> [!NOTE]
> Dans le capture d'écran précédente, la date de besoin de la commande fournisseur est le 12 janvier. Comme cette capture d'écran a été pris en 2015, alors que le 11 janvier était un dimanche, la MRP a déplacé la date de besoin au jour ouvrable suivant, qui est le lundi 12 janvier. Néanmoins, la commande fournisseur a la date de livraison du 11 janvier.

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>Cas B : les jours négatifs sont supérieurs au délai d'exécution de l'article

Si vous définissez les jours négatifs à un nombre supérieur au délai d'exécution de l'article, vous ne recevez pas de nouvel ordre prévisionnel. La commande client est associée à la commande fournisseur existante. Par conséquent, la commande client est retardée. Si vous créez un ordre prévisionnel, vous pouvez expédier la commande client à temps.

La figure suivante présente une capture d'écran de ce cas.

![Capture d'écran du cas B pour le scénario 3](./media/negative-days-16.png)

La figure suivante présente une vue graphique de ce qui se produit dans ce cas.

![Vue graphique du cas B pour le scénario 3](./media/negative-days-17.png)

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>Cas C : corréler automatiquement le délai d'exécution l'article et la plage de gestion des jours négatifs

Ce cas ressemble au cas C pour le scénario 1, car les jours négatifs dynamiques y fonctionnent exactement de la même manière, sinon mieux, que dans le cas B de ce scénario.

La plage de gestion des jours négatifs dynamiques est désormais 6 + 2 – 7 = 1 jour. Toutefois, dans ce cas, le système prend en considération toujours le délai d'exécution des jours négatifs (2), car la MRP considère la valeur maximale entre le délai d'exécution des jours négatifs et le délai d'exécution des jours négatifs dynamiques. Par conséquent, le résultat de ce cas est identique au résultat du cas A pour ce scénario.

La figure suivante présente une vue graphique de ce qui se produit dans ce cas.

![Vue graphique du cas C pour le scénario 3](./media/negative-days-18.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>Cas D : utiliser uniquement des jours négatifs dynamiques

Si vous définissez les jours négatifs sur **0** (zéro) et utilisez seulement la plage de gestion des jours négatifs dynamiques, celle-ci est désormais 6 + 0 - 7 = -1 jours. Dans ce cas, le système prend en considération toujours le délai d'exécution des jours négatifs (2). Par conséquent, le résultat de ce cas est identique au résultat du cas A pour ce scénario et présente les mêmes inconvénients. Pour une vue graphique de ce qui se produit, voir le cas A pour le scénario 2.

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>Cas E : utiliser des jours négatifs supérieurs au délai d'exécution de l'article et la plage de gestion des jours négatifs dynamiques

Ce cas est identique au cas E des scénarios 1 et 2. Il a fondamentalement les mêmes avantages et inconvénients.

## <a name="conclusion"></a>Conclusion

Comme le montrent les trois scénarios de cette rubrique, il est conseillé de définir les jours négatifs à un nombre qui est supérieur au délai d'exécution des articles dans le groupe de couverture. Il est également judicieux d'utiliser uniquement des jours négatifs dynamiques, et de définir les jours négatifs au nombre de jours que vous souhaitez attendre avant de commander un nouveau réapprovisionnement si vous avez un stock négatif (autrement dit, le nombre de jours dont vous souhaitez repousser la demande). En outre, les articles du même groupe de couverture doivent avoir des délais d'exécution similaires.

Si vous avez défini les jours négatifs sur **0** (zéro) et n'utilisez pas de jours négatifs dynamiques, la MRP crée toujours un nouvel ordre prévisionnel pour honorer la demande. Dans ce cas, il est important que vous utilisiez les messages d'action pour vous assurer de ne pas empiler de stock.

Vous pouvez définir les jours négatifs à une longue plage de gestion, puis utiliser les messages d'action. Cette approche produit de bons résultats de planification, mais est également un peu plus lente. L'analyse peut également être plus difficile, car vous devez analyser et appliquer les messages d'action. Voici un exemple :

- L'article DemoProduct a un cycle d'approvisionnement de six jours.
- Au jour zéro (1er janvier), le stock de l'article DemoProduct est 0 (zéro).
- Au jour zéro (1er janvier), vous recevez une commande client pour une quantité de 10 de l'article DemoProduct.
- Au jour 10 (10 janvier), vous recevez une commande client pour une quantité de 10 de l'article DemoProduct.
- Au jour 12 (12 janvier), il existe une commande fournisseur pour une quantité de 10 de l'article DemoProduct.
- Les jours négatifs sont définis sur **20**, ce qui est beaucoup plus que le délai d'exécution de l'article.

La figure suivante présente une vue graphique de ce qui se produit.

![Vue graphique de l'exemple](./media/negative-days-19.png)

La MRP produit les résultats suivants :

![Résultats](./media/negative-days-20.png)

Dans le capture d'écran précédente, la date de besoin de la commande client est le 9 janvier au lieu du 10 janvier. Comme cette capture d'écran a été pris en 2015, alors que le 10 janvier était un samedi, la date de besoin de la commande aurait du être le jour ouvrable précédent, qui est le vendredi 9 janvier.

La MRP crée une commande fournisseur prévisionnelle pour honorer la demande requise par la première commande client,mais elle recommande également que vous annuliez l'ordre prévisionnel, car vous pouvez avancer la commande fournisseur existante et en augmenter la quantité.

Les résultats ne sont pas erronés, mais le temps d'exécution de la MRP peut être plus long, car elle doit créer tous les retards et toutes les suggestions. En outre, il peut falloir plus de temps au planificateur pour comprendre les résultats de la MRP. Avant tout, dans ce cas, il est vital que le planificateur comprenne et utilise les messages d'action.

Si vous réduisez les jours négatifs à un nombre plus proche du délai d'exécution de l'article, et que vous utilisez des jours négatifs dynamiques, la MRP produit les résultats suivants.

![Résultats](./media/negative-days-21.png)

La MRP crée un ordre prévisionnel associé à la première commande client. Ensuite, comme prévu, la deuxième commande client est liée à la commande fournisseur existante, sur la base des jours négatifs. Ce résultat de planification est également correct, et le temps d'exécution de la MRP peut être plus court. Dans ce cas, il n'est pas vital de comprendre et savoir utiliser les messages d'action.

Pour assurer que les valeurs adéquates sont entrées pour votre entreprise, vous devez réfléchir à la fois en termes de fonctionnalité et de temps d'exécution de la MRP. Par conséquent, il peut falloir quelques essais-erreurs pour déterminer les valeurs optimales.

## <a name="see-also"></a>Voir également :

Pour plus de discussion, voir le billet de blog original [Plus d'informations sur les jours négatifs (dynamiques)](https://blogs.msdn.microsoft.com/axmfg/2015/02/19/more-about-dynamic-negative-days/).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]