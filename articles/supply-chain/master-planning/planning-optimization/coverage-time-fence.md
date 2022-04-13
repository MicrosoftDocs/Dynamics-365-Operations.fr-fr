---
title: Plages de gestion de la couverture
description: Cette rubrique décrit comment configurer des plages de gestion de la couverture lorsque vous utilisez le complément Optimisation de la planification. Une plage de gestion de la couverture indique votre horizon de planification et votre limite.
author: t-benebo
ms.date: 01/18/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2021-01-18
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 12deca22fd6ff3cb4556e0525ab831e1aea0ee33
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468914"
---
# <a name="coverage-time-fences"></a>Plages de gestion de la couverture

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment configurer des *plages de gestion de la couverture* lorsque vous utilisez le complément Optimisation de la planification. Les planificateurs peuvent définir l’horizon de planification (la période de couverture en jours) et exclure l’offre et la demande qui se situent au-delà de cet horizon. Par conséquent, les délais de couverture aident à prévenir le « bruit » causé par des suggestions d’approvisionnement auxquelles vous n’avez pas à réagir depuis des mois. Les exemples incluent les prévisions de l’année prochaine et les commandes des clients qui sont passées bien au-delà du délai normal.

Une plage de gestion de la couverture correspond au nombre de jours après la date du jour (ou, plus précisément, la date à laquelle vous effectuez la planification) pendant lesquels l’offre et la demande sont exclues. Pour éviter les retards, vous devez vous assurer que la plage de gestion de la couverture est plus longue que le délai total. La valeur système par défaut est de 100 jours.

Vous pouvez spécifier une plage de gestion de la couverture à chacun des niveaux suivants :

- **Groupe de couverture** : vous pouvez définir une plage de gestion de la couverture par défaut pour chaque groupe de couverture.
- **Couverture d’article** : vous pouvez remplacer la plage de gestion de la couverture héritée du groupe de couverture affecté à un élément.
- **Plan général** : vous pouvez remplacer les plages de gestion de la couverture héritées du groupe de couverture et des paramètres de couverture d’article.

Les sections suivantes expliquent comment spécifier un groupe de couverture à chaque niveau.

## <a name="set-a-coverage-time-fence-for-a-coverage-group"></a>Définir une plage de gestion des demandes approuvées pour un groupe de couverture

Lorsque vous spécifiez une plage de gestion de la couverture pour un groupe de couverture, le paramètre s’applique à tous les articles (produits) appartenant à ce groupe. Cependant, vous pouvez remplacer le paramètre pour des éléments spécifiques ou des plans généraux spécifiques.

Pour spécifier une plage de gestion de la couverture pour un groupe de couverture, procédez comme suit.

1. Accédez à **Planification \> Paramétrage \> Couverture \> Groupes de couverture**.
1. Sélectionnez un groupe de couverture existant dans la liste ou créez un groupe de couverture.
1. Sur l’organisateur **Général**, définissez le champ **Plage de gestion de la couverture (jours)** sur le nombre de jours que vous souhaitez utiliser comme plage de gestion de la couverture pour le groupe de couverture.

## <a name="set-a-coverage-time-fence-for-a-specific-item"></a>Définir une plage de gestion de la couverture pour un article spécifique

Chaque article (produit) appartient à un groupe de couverture. Si aucun groupe de couverture n’est explicitement affecté à un élément, un groupe de couverture par défaut s’applique. Chaque élément hérite d’une plage de gestion de la couverture de son groupe de couverture. Cependant, vous pouvez remplacer cette plage de gestion pour des éléments spécifiques selon vos besoins.

Pour spécifier une plage de gestion de la couverture pour un article spécifique, procédez comme suit.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Sélectionnez un produit dans la grille.
1. Dans le volet Actions, sous l’onglet **Planifier**, dans le groupe **Couverture**, sélectionnez **Couverture de l’article**.
1. Sur la page **Couverture de l’article**, sur l’onglet **Aperçu**, sélectionnez ou créez une ligne pour le site sur lequel vous souhaitez définir une plage de gestion de la couverture.
1. Sélectionnez l’onglet **Général** pour ouvrir les paramètres du site sélectionné.
1. Cochez la case **Remplacer les paramètres du groupe de couverture**.
1. Définissez le champ **Plage de gestion de la couverture (jours)** sur le nombre de jours que vous souhaitez utiliser comme plage de gestion de la couverture pour l’article.

## <a name="set-a-coverage-time-fence-for-a-specific-master-plan"></a>Définir une plage de gestion de la couverture pour un plan général

Vous pouvez spécifier une plage de gestion de la couverture au niveau du plan général. De cette manière, vous définissez le nombre de jours que couvre le calcul de la planification générale pour un plan général. Ce paramètre remplace tous les paramètres de gestion de la couverture qui ont été définis pour chaque élément et groupe de couverture pertinents.

Pour spécifier une plage de gestion de la couverture pour un plan général spécifique, procédez comme suit.

1. Accédez à **Planification \> Paramétrage \> Plans \> Plans généraux**.
1. Sélectionnez un plan général existant dans la liste ou créez un plan général.
1. Sur l’organisateur **Plages de gestion en jours**, définissez l’option **Couverture** sur *Oui*. Puis, dans le champ sous l’option, saisissez le nombre de jours que vous souhaitez utiliser comme plage de gestion de la couverture pour le plan général.

## <a name="considerations-for-coverage-time-fences"></a>Considérations relatives aux plages de gestion de la couverture

Lorsque vous configurez des plages de gestion de la couverture, tenez compte des points suivants :

- Les plages de gestion de la couverture affectent uniquement les données d’entrée pour la planification générale. En cas de retard, les ordres prévisionnels résultants peuvent avoir une date postérieure à la date du jour plus la plage de gestion de la couverture.
- Les délais de gestion de la couverture sont spécifiés en jours civils. Les calendriers qui utilisent des jours ouvrés n’affecteront pas le calcul de la plage de gestion. Par exemple, une semaine est toujours considérée comme sept jours, même si les week-ends sont définis comme des jours fermés dans le calendrier du temps de travail.
- Les transactions obligatoires ne seront pas générées pour toute offre et demande hors de la période de gestion de la couverture.
- Si une offre et une demande approuvées sortent de la plage de gestion de la couverture, elles ne seront pas chargées dans le moteur. Par conséquent, cela ne déclenchera aucun réapprovisionnement et les retards ne seront pas calculés. Néanmoins, cette offre et cette demande ne doivent pas être effacées du système.
- Les variations des quantités de stock de sécurité (par rapport aux clés minimales) seront ignorées si elles sortent de la plage de gestion de la couverture.
- La demande intersociétés sera ignorée si la date d’expédition demandée qui est calculée n’est pas comprise dans la plage de gestion de la couverture. Notez que, pour la planification générale intégrée, la demande intersociétés n’est pas limitée par la plage de gestion de la couverture.
- Les prévisions de la demande seront ignorées si la date du budget n’est pas comprise dans la plage de gestion de la couverture. Notez que, pour la planification générale intégrée, les demandes intersociétés ne sont pas limitées par la plage de gestion de la couverture.
- Le complément Optimisation de la planification tient compte du fuseau horaire. Elle tient compte du fuseau horaire sur les sites d’approvisionnement et de demande, ainsi que de l’heure de l’exécution de la planification. Par exemple, la planification principale est déclenchée à 11 heures le 15 octobre à partir d’un site au Danemark (fuseau horaire GMT + 1) et une plage de gestion de la couverture de dix jours est utilisée. Dans ce cas, l’offre et la demande d’un site à Seattle (fuseau horaire GMT-8) sont incluses jusqu’à 2 heures du matin le 25 octobre (= dix jours de 24 heures après le déclenchement du plan général, moins la différence de fuseau horaire de neuf heures). Notez que le moteur de planification générale intégré ne tient pas compte de la date de la plage horaire. Par conséquent, le résultat peut différer.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]