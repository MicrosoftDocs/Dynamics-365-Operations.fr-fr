---
title: Paramètres de date et d’heure utilisés par l’optimisation de la planification
description: Cet article fournit des informations sur les paramètres de date et d’heure que l’optimisation de la planification utilise pendant son fonctionnement.
author: t-benebo
ms.date: 09/21/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-09-21
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2ef78c73a1c7033735f9586229ff7ba21daaa5ef
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740902"
---
# <a name="date-and-time-parameters-used-by-planning-optimization"></a>Paramètres de date et d’heure utilisés par l’optimisation de la planification

[!include [banner](../../includes/banner.md)]

Cet article fournit des informations sur les paramètres de date et d’heure que l’optimisation de la planification utilise pendant son fonctionnement.

Alors que le moteur de planification générale déprécié utilise des dates de transaction dans tous les calculs, l’optimisation de la planification fonctionne avec des valeurs de date et d’heure qui sont converties en dates. Cette différence de comportement peut conduire à des situations dans lesquelles, par exemple, les transactions de prévision créées à minuit le jour de l’exécution de la planification principale ne sont pas incluses, car l’optimisation de la planification considère qu’elles ont été créées avant la date actuelle.

## <a name="parameters-for-issue-and-demand-transactions"></a>Paramètres pour les transactions de sortie et de demande

Le tableau suivant répertorie les paramètres utilisés par l’optimisation de la planification lorsqu’elle traite les transactions de sortie et de demande.

| Paramètre | Nom du paramètre dans l’optimisation de la planification | Description | Champ équivalent dans Microsoft Dynamics 365 Supply Chain Management (dans la table ReqTrans) |
|---|---|---|---|
| Heure de sortie prévue | `PlannedIssueTime` | Date à laquelle la sortie est actuellement prévue. | **Jusqu’à ce jour** (`FuturesDate`) et **Retardé** (`FuturesTime`) |
| Heure de sortie demandée | `RequestedIssueTime` | Date de sortie demandée par l’utilisateur et définie dans Supply Chain Management. Ce paramètre s’applique uniquement aux ordres planifiés lancés ou approuvés. Pour les ordres planifiés, ce paramètre est vide par défaut. | **Date demandée** (`ReqDateDlvOrig`) |
| Heure de sortie requise | `RequiredIssueTime` | Date de sortie requise qui est ajustée par l’optimisation de la planification. Si l’heure de sortie demandée est passée lors de l’exécution de l’optimisation de la planification, l’heure de sortie requise sera ajustée au premier jour ouvrable qui n’est pas antérieur à la date d’aujourd’hui. Si l’heure de sortie demandée est marquée comme bloquée dans le calendrier, l’heure de sortie requise sera ajustée au premier jour ouvrable avant cette date. | **Date de besoin** (`ReqDate`) et **Heure de besoin** (`ReqTime`) |
| Retard de l’heure de sortie | `IssueTimeDelay` | Décalage entre l’heure de sortie planifiée et l’heure de sortie demandée pour les commandes approuvées et validées, ou l’heure de sortie requise. | **Retard (en jours)** (`FuturesDays`) |

## <a name="parameters-for-receipt-and-supply-transactions"></a>Paramètres pour les transactions de réception et d’approvisionnement

Le tableau suivant répertorie les paramètres utilisés par l’optimisation de la planification lorsqu’elle traite les transactions de réception et d’approvisionnement.

| Paramètre | Nom du paramètre dans l’optimisation de la planification | Description | Champ équivalent dans Supply Chain Management (dans la table ReqTrans ou ReqPO) |
|---|---|---|---|
| Heure de disponibilité prévue | `PlannedAvailabilityTime` | Date à laquelle la disponibilité de la réception est prévue. | **Date de besoin** (`ReqDate`) et **Heure de besoin** (`ReqTime`) |
| Heure de réception prévue | `PlannedReceiptTime` | Date à laquelle la réception arrivera à l’emplacement. | **À ce jour** (`FuturesDate`), **Retardé** (`FuturesTime`), et **Date de livraison** (`ReqDateDlv`) ou **Date demandée** (`ReqDateDlvOrig`) si la commande n’est pas encore validée. |
| Heure de disponibilité requise | `RequiredAvailabilityTime` | Date de disponibilité requise qui est ajustée par l’optimisation de la planification. | **Date de besoin** (`ReqDate`) et **Heure de besoin** (`ReqTime`) |
| Heure de réception prévue | `ExpectedReceiptTime` | Date de réception prévue pour une réception validée. La valeur est définie par l’utilisateur dans Supply Chain Management et n’est pas ajustée par l’optimisation de la planification. Ce paramètre s’applique uniquement aux réceptions validées. | **Date demandée** (`ReqDateDlvOrig`) |
| Heure de réception requise | `RequiredReceiptTime` | Date de réception requise qui est ajustée par l’optimisation de la planification. | **Date de besoin** (`ReqDate`) et **Heure de besoin** (`ReqTime`) |
| Heure de commande prévue | `PlannedOrderingTime` | Date de commande qui est calculée par l’optimisation de la planification. | **Date de commande** (`ReqDateOrder`) et **Heure de commande** (`ReqTimeOrder`) |
| Heure de début de l’activité prévue | `PlannedActivityStartTime` | Date à laquelle l’activité pour cette réception doit commencer. | **Date de début** (`SchedFromDate`) |
| Retard de réception | `ReceiptTimeDelay` | Décalage entre l’heure de réception prévue et l’heure de réception requise. | **Retard (jours)** (`FuturesDays`) et **Retardé** (`FuturesTime`) |

## <a name="examples-of-date-parameter-use-by-planning-optimization"></a>Exemple de paramètres de date utilisés par l’optimisation de la planification

Les plans des illustrations suivantes sont indiqués au niveau quotidien, mais l’optimisation de la planification est exécutée à un niveau plus détaillé. Par exemple, étant donné que les marges peuvent être exprimées en heures, l’heure de planification de la commande peut être le 22 janvier 2021, à 11h35, et ainsi de suite.

### <a name="example-1-simple-scenario"></a>Exemple 1 : Scénario simple

Une commande client dont l’heure de sortie est demandée le 22 janvier est couverte par une commande fournisseur. Les paramètres suivants sont utilisés :

- Pas de délai
- Pas de calendrier (Tous les jours sont ouverts.)
- Pas de marge

L’illustration suivante présente ce scénario. (Sélectionnez l’illustration pour ouvrir une version plus grande.)

[![Scénario simple.](media/planning-service-dates-1-small.png)](media/planning-service-dates-1.png)

### <a name="example-2-lead-time-scenario"></a>Exemple 2 : Scénario avec délai

Une commande client dont l’heure de sortie est demandée le 22 janvier est couverte par une commande fournisseur. Les paramètres suivants sont utilisés :

- Trois jours de délai
- Pas de calendrier (Tous les jours sont ouverts.)
- Pas de marge

L’illustration suivante présente ce scénario. (Sélectionnez l’illustration pour ouvrir une version plus grande.)

[![Scénario avec délai.](media/planning-service-dates-2-small.png)](media/planning-service-dates-2.png)

### <a name="example-3-margin-scenario"></a>Exemple 3 : Scénario avec marge

Une commande client dont l’heure de sortie est demandée le 22 janvier est couverte par une commande fournisseur. Les paramètres suivants sont utilisés :

- Trois jours de délai
- Marge de commande de quatre jours
- Marge de disponibilité de cinq jours
- Pas de calendrier (Tous les jours sont ouverts.)

L’illustration suivante présente ce scénario. (Sélectionnez l’illustration pour ouvrir une version plus grande.)

[![Scénario avec marge.](media/planning-service-dates-3-small.png)](media/planning-service-dates-3.png)

### <a name="example-4-delay-scenario"></a>Exemple 4 : Scénario avec retard

Une commande client dont l’heure de sortie est demandée le 22 janvier est couverte par une commande fournisseur. Cet exemple utilise les mêmes paramètres que l’exemple 3, mais la date de planification a été déplacée au 15 janvier. La planification en arrière (marqueurs rouges) échoue car l’heure de commande planifiée devrait être antérieure à la date d’aujourd’hui. Par conséquent, la planification principale doit planifier à l’avance et des retards se produisent.

L’illustration suivante présente ce scénario. (Sélectionnez l’illustration pour ouvrir une version plus grande.)

[![Scénario avec retard.](media/planning-service-dates-4-small.png)](media/planning-service-dates-4.png)

### <a name="example-5-transfer-scenario"></a>Exemple 5 : Scénario avec transfert

Une commande client depuis l’entrepôt 1 dont l’heure de sortie est demandée le 22 janvier est couverte par un ordre de transfert de l’entrepôt 2 qui est couvert par une commande fournisseur prévisionnelle. Les paramètres suivants sont utilisés :

- Délai de transfert de trois jours (entrepôt 1)
- Délai d’achat de deux jours (entrepôt 2)
- Pas de calendrier (Tous les jours sont ouverts.)

L’illustration suivante présente ce scénario. (Sélectionnez l’illustration pour ouvrir une version plus grande.)

[![Scénario avec transfert.](media/planning-service-dates-5-small.png)](media/planning-service-dates-5.png)

### <a name="example-6-lead-time-with-calendars-scenario"></a>Exemple 6 : Scénario avec délai et calendriers

Une commande client dont l’heure de sortie est demandée le 22 janvier est couverte par une commande fournisseur. Les paramètres suivants sont utilisés :

- Trois jours de délai
- Calendrier des sorties (fermeture le vendredi)
- Calendrier des disponibilités (fermeture le jeudi et le vendredi)
- Calendrier des réceptions (fermeture le mardi, le mercredi et le dimanche)
- Calendrier des délais (fermeture le jeudi et le vendredi)
- Calendrier des commandes (ouverture le lundi et le samedi)

L’illustration suivante présente ce scénario. (Sélectionnez l’illustration pour ouvrir une version plus grande.)

[![Scénario avec délai et calendriers.](media/planning-service-dates-6-small.png)](media/planning-service-dates-6.png)

### <a name="example-7-delay-with-calendars-scenario"></a>Exemple 7 : Scénario avec retard et calendriers

Une commande client dont l’heure de sortie est demandée le 22 janvier est couverte par une commande fournisseur. Cet exemple utilise les mêmes paramètres que l’exemple 6, mais la date de planification a été déplacée au 13 janvier. La planification en arrière (marqueurs rouges) échoue car l’heure de commande planifiée devrait être antérieure à la date d’aujourd’hui. Par conséquent, la planification principale doit planifier à l’avance et des retards se produisent.

L’illustration suivante présente ce scénario. (Sélectionnez l’illustration pour ouvrir une version plus grande.)

[![Scénario avec retard et calendriers.](media/planning-service-dates-7-small.png)](media/planning-service-dates-7.png)
