---
title: Traitement du stock de sécurité pour les articles
description: Cette rubrique décrit le traitement du stock de sécurité et le paramétrage de la quantité de stock de sécurité pour les articles.
author: roxanadiaconu
manager: tfehr
ms.date: 11/27/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqSafetyKey, ReqItemTableSetup, ReqItemJournalName, ReqItemTable, EcoResProductDetailsExtended, ReqSafetyKeyDefaultDataWizard
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: kamaybac
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: ee5775826c4f7f499d015145a5e8f0f6c7a42903
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3987387"
---
# <a name="safety-stock-fulfillment-for-items"></a>Traitement du stock de sécurité pour les articles

[!include [banner](../includes/banner.md)]

Le stock de sécurité est une quantité supplémentaire d'un article détenu en stock afin de réduire le risque de rupture de stock de l'article. Le stock de sécurité est utilisé comme stock tampon dans le cas où des commandes client arrivent et que le fournisseur ne peut pas livrer les articles supplémentaires pour respecter la date d'expédition demandée par le client. Si le stock de sécurité est utilisé pour exécuter une commande client, il est réduit. Vous pouvez utiliser le module Planification pour ramener automatiquement le stock au niveau de sécurité.    

## <a name="set-up-safety-stock-levels-for-items"></a>Paramétrer les niveaux de stock de sécurité pour les articles

Le stock de sécurité est paramétré dans le cadre de la couverture de l'article sur la page **Couverture de l'article** sous **Produits lancés** > **Plan** > **Couverture**.

Dans le champ **Minimum**, entrez le niveau de stock de sécurité que vous souhaitez maintenir pour l'article. La valeur est exprimée en unités de stock. Si vous laissez ce champ vide, la valeur par défaut est zéro. Ce champ est disponible lorsque vous sélectionnez **Période**, **Besoin** ou **Min/max** dans la liste **Code couverture**. La limite du niveau de stock s'applique au stock disponible, ce qui signifie que les réservations et les marquages peuvent déclencher le réapprovisionnement du stock de sécurité avant que la quantité physique passe en dessous du niveau minimum spécifié.

> [!NOTE]
> Vous devez définir toutes les autres dimensions de couverture prévues avant de définir le champ **Minimum**. Cela évite d'utiliser un enregistrement non valide lors de la planification. Cette situation peut survenir, par exemple, si un groupe de dimensions est étendu avec une dimension de couverture prévue supplémentaire pour laquelle les quantités en stock minimales et maximales ne sont pas encore définies.

Les clés minimum vous permettent de gérer les fluctuations saisonnières de la demande. Par exemple, vous pouvez réduire le niveau de stock minimum d'un article hors saison, puis augmenter graduellement le niveau pendant les autres mois. Pour créer une clé minimum, accédez à **Planification** > **Paramétrage** > **Couverture** > **Clés minimum/maximum**. Vous spécifiez la clé minimum pour ajuster le niveau du stock de sécurité par saisonnalité dans le champ **Clé minimum** de la page **Couverture de l'article**. 

## <a name="example-minimum-key"></a>Exemple : clé minimum
Si vous voulez paramétrer une clé minimum qui tient compte de la demande saisonnière accrue au cours des mois du printemps et de l'été, accédez à **Planification** > **Paramétrage** > **Couverture** > **Clés minimum/maximum** et suivez les étapes ci-après.

1. Créez 12 lignes et affectez un numéro allant de 1 à 12 aux lignes dans le champ **Modifier**.
2. Dans le champ **Unité**, sélectionnez **Mois**.
3. Dans le champ **Facteur**, entrez les valeurs décrites dans le tableau suivant.

|Ligne|Entrez cette valeur|Résultat|
|---|---|---|
|1 à 3|1|Le stock minimal est basé sur le paramètre dans la page **Couverture de l'article** pour janvier jusqu'à mars.|
|4-5|2|Le stock minimal est multiplié par un facteur de 2 pour avril jusqu'à mai.|
|6-8|2,5|Le stock minimal est multiplié par un facteur de 2,5 pour juin jusqu'à août.|
|9-12|1|Le stock minimal rétablit le paramètre dans la page **Couverture de l'article** pour septembre jusqu'à décembre.|

Si le code couverture est **Min/Max**, vous pouvez également spécifier la quantité en stock **Maximum** que vous souhaitez maintenir pour l'article. La valeur est également exprimée en unités de stock. Si le stock disponible à date passe en dessous de la quantité minimale, la planification génère un ordre prévisionnel pour honorer toutes les demandes en cours, puis rétablit la quantité maximale indiquée pour le stock disponible. De la même manière que vous paramétrez **Minimum**, vous devez définir toutes les dimensions de couverture prévues avant de définir le champ **Maximum**.

## <a name="example-minmax-coverage-code"></a>Exemple : code couverture minimum/maximum
La quantité minimale est 10 et la quantité maximale est 15. Le stock disponible actuel est de 4. Cela donne une quantité minimale requise de 6. Toutefois, la quantité maximale étant 15, la planification génère un ordre prévisionnel pour 11 articles.

Pour les articles qui suivent les demandes saisonnières, vous devrez maintenir différents niveaux maximum. Pour ce faire, vous devez définir **Clés maximum** en accédant à **Planification** > **Paramétrage** > **Couverture** > **Clés minimum/maximum**. Renseignez le champ **Clé maximum** sur la page **Couverture de l'article**. Vous pouvez afficher les informations sur les niveaux de stock de sécurité définis à l'aide des clés minimum sous l'onglet **Min/Max** de la page **Couverture de l'article**. Vous devez vous assurer que, pour une période donnée, les valeurs minimum et maximum sont synchronisées.

## <a name="safety-stock-fulfillment"></a>Traitement du stock de sécurité 

Le paramètre **Exécuter le minimum** vous permet de sélectionner la date ou la période pendant laquelle le niveau de stock doit atteindre la quantité indiquée dans le champ **Minimum**. Ce champ est disponible lorsque vous sélectionnez **Période**, **Besoin** ou **Min/max** dans la liste **Code couverture**.

Si les **Clés minimum** sont utilisées, activez la case à cocher **Périodes minimum** pour honorer le niveau de stock minimum pour toutes les périodes paramétrées pour la clé minimum. Si vous désactivez la case à cocher, le stock minimum est honoré pour la période actuelle uniquement.

Le scénario suivant décrit comment ce paramètre fonctionne et quelles sont les différences entre ses valeurs.

> [!NOTE]
> Pour toutes les illustrations contenues dans cette rubrique, l'axe X représente le stock, l'axe Y représente les jours, les codes-barres représentent le niveau de stock, les flèches représentent les transactions, telles que les lignes de commande client, les lignes de commande fournisseur ou les ordres prévisionnels.

[![Scénario courant pour le traitement du stock de sécurité](./media/Scenario1.png)](./media/Scenario1.png) Le paramètre **Exécuter le minimum** peut avoir les valeurs suivantes :
### <a name="todays-date"></a>Date du jour 
La quantité minimale indiquée est atteinte à la date d'exécution de la planification. Le système tente d'atteindre la limite de stock de sécurité dès que possible, même si cela peut s'avérer irréaliste en raison du délai. 
[![Demande à la date du jour](./media/TodayReq.png)](./media/TodayReq.png) L'ordre prévisionnel P1 est créé à la date du jour pour faire passer le stock disponible au-dessus du niveau de stock de sécurité à cette date. Les lignes de commande client S1 à S3 continuent à diminuer le niveau de stock. Les ordres prévisionnels P2 à P4 sont générés par la planification afin que le niveau de stock soit ramené à la limite de sécurité après chaque demande de commande client.
Lorsque le code couverture **Demande** est utilisé, plusieurs ordres prévisionnels sont créés. Il est toujours recommandé d'utiliser la couverture **Période** ou **Min/Max** pour les articles et les matières en demande fréquente pour regrouper les réapprovisionnements. L'illustration suivante présente un exemple pour le code couverture **Période**.
[![Période. Date du jour](./media/TodayPeriod.png)](./media/TodayPeriod.png) L'illustration suivante présente un exemple pour le code couverture **Min/Max**.
[![MinMax. Date du jour](./media/TodayMinMax.png)](./media/TodayMinMax.png)
### <a name="todays-date--procurement-time"></a>Date du jour + délai d'approvisionnement 
La quantité minimale indiquée est atteinte à la date d'exécution de la planification, plus le délai d'achat ou de production. Cette date inclut toutes les marges de sécurité. Si l'article est assorti d'un accord commercial et que la case à cocher **Rechercher des accords commerciaux** est activée sur la page **Paramètres de planification**, le délai de livraison de l'accord commercial n'est pas pris en compte. Les délais sont calculés à partir des paramètres de couverture de l'article ou à partir de l'article.
Ce mode d'exécution crée des plans avec moins de retards et d'ordres prévisionnels, quel que soit le groupe de couverture paramétré pour l'article. L'illustration suivante présente le résultat du plan si le code couverture est **Demande** ou **Période**.  
[![Demande. Période. Date du jour et délai](./media/TodayPLTReq.png)](./media/TodayPLTReq.png) L'illustration suivante présente le résultat du plan si le code couverture est **Min/Max**.  
[![MinMax. Date du jour et délai](./media/TodayPLTMinMax.png)](./media/TodayPLTMinMax.png)
### <a name="first-issue"></a>Première sortie 
La quantité minimum indiquée est atteinte à la date à laquelle le stock disponible passe en dessous du niveau minimum, comme le montre l'illustration suivante. Même si le stock disponible est en dessous du niveau minimum à la date d'exécution de la planification, l'option **Première sortie** ne tente pas de le couvrir jusqu'à la demande suivante.
L'illustration suivante présente un exemple pour le code couverture **Demande**.
[![Planification d'un article avec le code couverture **Demande** et l'option **Première sortie**](./media/FirstIssueReq.png)](./media/FirstIssueReq.png) L'illustration suivante présente un exemple pour le code couverture **Période**.
[![Planification d'un article avec le code couverture **Période** et l'option **Première sortie**](./media/FirstIssuePeriod.png)](./media/FirstIssuePeriod.png) L'illustration suivante présente un exemple pour le code couverture **Min/Max**.
[![Planification d'un article avec le code couverture **MinMax** et l'option **Première sortie**](./media/FirstIssueMinMax.png)](./media/FirstIssueMinMax.png) À la date d'exécution de la planification, si le stock disponible est déjà en dessous de la limite du stock de sécurité, les options **Date du jour** et **Date du jour + délai d'approvisionnement** déclenchent immédiatement le réapprovisionnement. L'option **Première sortie** attend jusqu'à ce qu'une autre transaction de sortie soit disponible, par exemple une demande de ligne de commande client ou de nomenclature pour l'article, puis il déclenche le réapprovisionnement à la date de cette transaction. À la date d'exécution de la planification, si le stock disponible n'est pas en dessous de la limite du stock de sécurité, les options **Date du jour** et **Première sortie** génèrent exactement le même résultat, comme le montre l'illustration ci-dessous. 

[![NotUnderLimit](./media/ReqFirstIssue.png)](./media/ReqFirstIssue.png) À la date d'exécution de la planification, si le stock disponible n'est pas en dessous de la limite de stock de sécurité, l'option **Date du jour + délai d'approvisionnement** génère le résultat suivant, car elle reporte l'exécution jusqu'à la fin du délai d'approvisionnement.
![Planification d'un article avec le code couverture **Demande** et l'option **Première sortie**](./media/ReqTodayLT.png)
### <a name="coverage-time-fence"></a>Plage de gestion de la couverture
La quantité minimale indiquée est atteinte pendant la période indiquée dans le champ **Plage de gestion de la couverture**. Cette option est utile lorsque la planification n'autorise pas l'utilisation du stock disponible pour les commandes réelles, telles que les ventes ou les transferts, lors de la tentative de maintien du niveau de sécurité. Toutefois, dans une prochaine version, ce mode de réapprovisionnement ne sera plus nécessaire, et cette option sera déconseillée.
## <a name="plan-safety-stock-replenishment-for-first-expired-first-out-fefo-items"></a>Planifier le réapprovisionnement du stock de sécurité pour les articles FEFO (Premier arrivé à expiration, premier sorti)
À tout moment, la réception du stock avec la dernière date d'expiration est utilisée pour le stock de sécurité pour permettre l'exécution de la demande réelle, comme les lignes de vente ou de nomenclature, dans l'ordre FEFO (premier arrivé à expiration, premier sorti).
Pour montrer comment cela fonctionne, utilisez le scénario suivant.
[![FEFOScenario](./media/FEFOScenario.png)](./media/FEFOScenario.png) Lorsque la planification s'exécute, elle doit couvrir la première commande client pour le stock disponible existant et une commande fournisseur supplémentaire pour la quantité restante.
[![FEFO1](./media/FEFO1.png)](./media/FEFO1.png) Un ordre prévisionnel est créé pour s'assurer que le stock disponible est ramené à la limite de sécurité.
[![FEFO2](./media/FEFO2.png)](./media/FEFO2.png) Lorsque la deuxième commande client est planifiée, l'ordre prévisionnel précédemment créé qui couvre le stock de sécurité est utilisé pour couvrir cette quantité. Par conséquent, le stock de sécurité change constamment.
[![FEFO3](./media/FEFO3.png)](./media/FEFO3.png) Enfin, un autre ordre prévisionnel est créé pour couvrir le stock de sécurité.
[![FEFO4](./media/FEFO4.png)](./media/FEFO4.png) Tous les traitements par lots expirent en conséquence, et des ordres prévisionnels sont créés pour recharger le stock de sécurité après son expiration.

## <a name="how-master-planning-handles-the-safety-stock-constraint"></a>Procédure de gestion de la contrainte de stock de sécurité par la planification

Le stock de sécurité est suivi dans le système en tant que type de demande, à l'instar des lignes de vente ou des demandes de nomenclature. Vous pouvez afficher la ligne de demande de stock de sécurité sur la page **Besoins nets** si vous supprimez le filtre par défaut dans la colonne **Type de demande**.

La transaction de demande de stock de sécurité n'est pas traitée en priorité si le système détermine que cela crée des retards dans l'exécution de la demande réelle, par exemple les lignes de vente, les lignes de nomenclature, les demandes de transfert ou les lignes de prévision de la demande. Sinon, s'assurer que le stock disponible est au-dessus de la quantité de stock de sécurité a la même priorité que les autres types de demande. Ainsi, aucun retard n'est enregistré pour les transactions réelles et cela permet d'éviter tout réapprovisionnement excessif ou anticipé du stock de sécurité.

Pendant la phase de couverture de la planification, le réapprovisionnement du stock de sécurité n'est plus dépriorisé. Le stock disponible peut être utilisé avant les autres types de demande. Lors du calcul du retard, une nouvelle logique est ajoutée pour parcourir les lignes de vente retardées, les demandes de ligne de nomenclature et tous les autres types de demande, pour déterminer si la livraison peut être effectuée à temps, à condition que le stock de sécurité soit utilisé. Si le système détermine qu'il peut réduire les retards à l'aide du stock de sécurité, les lignes de vente ou de nomenclature remplacent leur couverture d'origine par le stock de sécurité, et le système déclenche à la place le réapprovisionnement du stock de sécurité.

Si le plan ou l'article n'est pas paramétré pour le calcul du retard, la contrainte du stock de sécurité a la même priorité que les autres types de demande. Cela signifie qu'il existe une réserve de stock disponible avant les autres types de demande.
