---
title: "Autorisez une prévision ajustée"
description: "Certaines données de prévision ne doivent pas être autorisées immédiatement. Cet article explique comment spécifier la période pour laquelle une prévision est autorisée. Elle décrit également comment autoriser la prévision pour des sociétés spécifiques et des modèles de prévision."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: f151f4b4290df0b2bf1b5d1159654bd248a439b1
ms.lasthandoff: 03/31/2017


---

# <a name="authorize-an-adjusted-forecast"></a>Autorisez une prévision ajustée

Certaines données de prévision ne doivent pas être autorisées immédiatement. Cet article explique comment spécifier la période pour laquelle une prévision est autorisée. Elle décrit également comment autoriser la prévision pour des sociétés spécifiques et des modèles de prévision.

Certaines données de prévision ne doivent pas être autorisées immédiatement. Vous pouvez spécifier les dates de début et de fin de la période à laquelle la prévision est autorisée. Cette fonction permet de figer des intervalles spécifiques. 

Les dates de début et de fin spécifiées doivent correspondre au début et les dates de fin de la plage que la prévision est générée. Le système met cette restriction et ajuste effet automatiquement les dates, si l'ajustement est requis. 

Sous l'onglet **Détails** de la page **Autorisation**, vous pouvez afficher les détails de la prévision qui a été récemment générée. 

Vous pouvez sélectionner les sociétés et les modèles de prévision pour autoriser l'utilisation de la prévision. Par défaut, la grille inclut toutes les sociétés pour lesquelles la demande de prévision a été créée. Pour chaque société, le modèle de prévision qui correspond au plan prévisionnel actuel qui est paramétré dans les paramètres de planification est prérempli. Toutefois, vous pouvez remplacer ce modèle de prévision par n'importe quel modèle de prévision qui appartient à cette société. Si aucune donnée de demande de prévision n'a été générée pour une société sélectionnée, vous recevez un message d'avertissement au moment de l'importation. 

Il est très important que vous compreniez comment fonctionne la case à cocher **Enregistrer les ajustements manuels apportés à la prévision de la demande de base**. Si vous avez effectué les ajustements manuels aux prévisions de base statistiques, les valeurs ajustées sont autorisées pour l'utilisation, même si cette case à cocher est désactivée. Toutefois, les modifications sont ignorées après l'autorisation. Par conséquent, la prochaine fois que la prévision est générée, cette prévision n'est qu'une prévision statistique et n'a aucun remplacement manuel, même si **Transfert des ajustements manuels dans la prévision de la demande** est sélectionné. Par conséquent, vous pouvez considérer la case à cocher **Enregistrer les ajustements manuels apportés à la prévision de la demande de base** comme un mécanisme qui vous permet de conserver ou d'ignorer les modifications manuelles.

<a name="see-also"></a>Voir également :
--------

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)

[Monitoring forecast accuracy](monitor-forecast-accuracy.md)


