---
title: "Exécution par lots des alertes"
description: "Cette rubrique donne des informations sur le traitement par lots des alertes dans Microsoft Dynamics 365 for Finance and Operations."
author: tjvass
manager: AnnBe
ms.date: 03/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.translationtype: HT
ms.sourcegitcommit: 454368ab5a467002ebf973db97fd98e31885dfe0
ms.openlocfilehash: f4c874c148dc10ac658f659896009981962a5802
ms.contentlocale: fr-fr
ms.lasthandoff: 03/23/2018

---

# <a name="batch-processing-for-alerts"></a>Traitement par lots des alertes
[!INCLUDE [banner](../includes/banner.md)]

[!INCLUDE [banner](../includes/pre-release.md)]

Les alertes sont traitées par la fonctionnalité de traitement par lots dans Microsoft Dynamics 365 for Finance and Operations. Vous devez paramétrer le traitement par lots avant que les alertes puissent être remises.

Finance and Operations prend en charge deux types d'événements :

- Événements déclenchés par des événements basés sur des modifications. Ces événements sont également connus sous le nom d'événements de création/suppression et de mise à jour.
- Événements déclenchés par les dates d'échéance.

Vous pouvez paramétrer les traitements par lots pour chaque type d'événement.
        
## <a name="batch-processing-for-change-based-events"></a>Traitement par lots des événements basés sur des modifications
Finance and Operations lit tous les événements basés sur des modifications qui se sont produits depuis la dernière exécution du traitement par lots. Les événements basés sur des modifications incluent les mises à jour des champs, la suppression des enregistrements et la création des enregistrements. Ces événements sont comparés avec les conditions définies dans les règles d'alerte. Lorsqu'un événement correspond aux conditions d'une règle, le traitement par lots génère une alerte.

### <a name="frequency-for-change-based-events"></a>Fréquence des événements basés sur des modifications
Pour les événements basés sur des modifications, vous pouvez paramétrer une tâche de traitement par lots qui déclenche le traitement d'un événement peu de temps après que celui-ci soit consigné par le système. Si vous paramétrez le traitement par lots de manière à ce qu'il ait lieu plus souvent, les utilisateurs reçoivent leurs alertes plus rapidement après des modifications. Toutefois, une fréquence élevée du traitement par lots peut compromettre les performances du système.

Par contre, un traitement par lots qui se reproduit moins souvent, et qui est prévu à des heures où la charge système est faible, peut améliorer les performances du système. Toutefois, une faible fréquence du traitement par lots ne peut pas répondre aux demandes des utilisateurs qui souhaitent recevoir des alertes en temps opportun.

Par conséquent, lors de la définition de la fréquence du traitement par lots pour les événements basés sur des modifications, vous devez tenir compte de l'équilibre entre la rapidité des alertes et les performances de l'ensemble du système. Plus le nombre d'utilisateurs créant des règles d'alerte est important, plus ces aspects sont pertinents. La fréquence n'affecte pas le nombre d'événements qui doivent être traités. Toutefois, si plus d'utilisateurs créent des règles, plus de vérifications doivent être effectuées. Ce type d'échange de données peut affecter les performances du système.

#### <a name="the-risks-of-low-batch-frequency"></a>Risques d'une fréquence de traitement par lots faible
Si vous paramétrez une faible fréquence du traitement par lots des événements basés sur des modifications, les données appropriées aux conditions de la règle d'alerte peuvent être modifiées avant l'exécution du traitement par lots. Par conséquent, vous risquez de perdre des alertes.

Par exemple, une règle d'alerte est définie pour déclencher une alerte lorsque l'événement est **modifications du contact client** et que la condition est **client = BB**. Autrement dit, lorsque le contact du client BB est modifié, l'événement est consigné. Toutefois, le système de traitement par lots est paramétré afin que le traitement par lots se produise moins souvent que la saisie de données. Si le nom du client passe de **BB** à **AA** avant que l'événement soit traité, les données de la base de données ne correspondent plus à la condition de la règle, **client = BB**. Donc, lorsque l'événement est finalement traité, aucune alerte n'est générée.

### <a name="set-up-processing-for-change-based-alerts"></a>Paramétrage du traitement des alertes basées sur des modifications
1. Accédez à **Administration du système** &gt; **Tâches périodiques** &gt; **Alertes** &gt; **Modifier les alertes de base**.
2. Dans la boîte de dialogue **Modifier les alertes de base**, entrez les informations appropriées.

## <a name="batch-processing-for-due-date-events"></a>Traitement par lots des événements de date d'échéance
Finance and Operations détecte tous les événements qui sont provoqués par les dates d'échéance, et ceux-ci sont comparés avec les conditions définies dans les règles d'alerte. Le traitement par lots génère une alerte lorsqu'un événement correspond aux conditions d'une règle.

### <a name="frequency-for-due-date-events"></a>Fréquence des événements de date d'échéance
Pour les événements de date d'échéance, vous pouvez paramétrer des traitements par lots qui sont exécutés pendant la nuit ou à des heures spécifiques de la journée, afin d'équilibrer la charge du système. Nous vous recommandons de paramétrer le traitement par lots de manière à ce qu'il s'exécute au moins une fois par jour. Si les alertes doivent être envoyées aussi tôt que possible, paramétrez le traitement par lots de manière à ce qu'il soit effectué immédiatement après la modification de la date du système. Si vous souhaitez générer des alertes pour les événements de date d'échéance se produisant après qu'un traitement par lots a généré des alertes, vous pouvez réexécuter le traitement par lots dans la même journée.

Par exemple, un traitement par lots a été exécuté un jour spécifique. Vous créez ensuite une commande fournisseur dont la date d'échéance doit déclencher une alerte ce même jour. Pour recevoir l'alerte ce jour, vous devez réexécuter le traitement par lots une fois la commande fournisseur créée. Toutefois, si vous ne réexécutez pas le traitement par lots ce même jour, le traitement par lots du jour suivant détecte les événements de date d'échéance non traités les jours précédents.

> [!NOTE]
> Même lorsque le traitement par lots est exécuté plusieurs fois par jour, les alertes ne sont pas dupliquées pour le même événement de date d'échéance et les mêmes conditions. Les alertes ne sont générées que pour les dates arrivant à échéance en raison de modifications dans le système se produisant après l'exécution du dernier traitement par lots.

### <a name="batch-processing-window"></a>Fenêtre de traitement par lots
Le traitement des règles d'alerte d'une société peut être arrêté pour plusieurs raisons. Il s'agit notamment des congés, des erreurs système ou d'autres problèmes qui empêchent l'exécution des traitements par lots pendant un certain temps.

Pour empêcher les alertes de date d'échéance de devenir obsolètes car le traitement par lots n'a pas été exécuté pendant plusieurs jours, vous pouvez paramétrer une fenêtre de traitement par lots. Une fenêtre de traitement par lots permet d'empêcher l'exécution d'un traitement par lots pendant un certain nombre de jours.

Si vous paramétrez une fenêtre de traitement par lots, une alerte est envoyée lorsque la règle d'alerte est traitée, même si l'alerte dépasse le délai défini dans les critères de date d'échéance. Une alerte continue à être envoyée tant que la période définie par ce délai et la fenêtre de traitement par lots n'est pas dépassée. Toutefois, si la période définie par le délai et la fenêtre de traitement par lots est dépassée, l'alerte n'est plus envoyée.

### <a name="set-up-processing-for-due-date-alerts"></a>Paramétrage du traitement des alertes de date d'échéance
1. Accédez à **Administration du système** &gt; **Tâches périodiques** &gt; **Alertes** &gt; **Alertes de date d'échéance**.
2. Dans la boîte de dialogue **Alertes de date d'échéance**, entrez les informations appropriées.

