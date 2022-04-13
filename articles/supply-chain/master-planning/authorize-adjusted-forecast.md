---
title: Autoriser une prévision ajustée
description: Certaines données de prévision ne doivent pas être autorisées immédiatement. Cet article explique comment spécifier la période pour laquelle une prévision est autorisée. Elle décrit également comment autoriser la prévision pour des sociétés spécifiques et des modèles de prévision.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b5523fe993955b4a9c0b0e639509530f298da7a
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468664"
---
# <a name="authorize-an-adjusted-forecast"></a>Autoriser une prévision ajustée

[!include [banner](../includes/banner.md)]

Certaines données de prévision ne doivent pas être autorisées immédiatement. Cet article explique comment spécifier la période pour laquelle une prévision est autorisée. Elle décrit également comment autoriser la prévision pour des sociétés spécifiques et des modèles de prévision.

Certaines données de prévision ne doivent pas être autorisées immédiatement. Vous pouvez spécifier les dates de début et de fin de la période à laquelle la prévision est autorisée. Cette fonction permet de figer des intervalles spécifiques. 

Les dates de début et de fin spécifiées doivent correspondre aux dates de début et de fin de l’intervalle dans lequel la prévision est générée. Le système applique cette restriction et ajuste automatiquement les dates, si l’ajustement est requis. 

Sous l’onglet **Détails** de la page **Autorisation**, vous pouvez afficher les détails de la prévision qui a été récemment générée. 

Vous pouvez sélectionner les sociétés et les modèles de prévision pour autoriser l’utilisation de la prévision. Par défaut, la grille inclut toutes les sociétés pour lesquelles la demande de prévision a été créée. Pour chaque société, le modèle de prévision qui correspond au plan prévisionnel actuel qui est paramétré dans les paramètres de planification est prérempli. Toutefois, vous pouvez remplacer ce modèle de prévision par n’importe quel modèle de prévision qui appartient à cette société. Si aucune donnée de demande de prévision n’a été générée pour une société sélectionnée, vous recevez un message d’avertissement au moment de l’importation. 

Il est très important que vous compreniez comment fonctionne la case à cocher **Enregistrer les ajustements manuels apportés à la prévision de la demande de base**. Si vous avez effectué des ajustements manuels sur les prévisions de base statistiques, les valeurs ajustées sont autorisées à être utilisées, même si cette case à cocher est désactivée. Toutefois, les modifications sont ignorées après l’autorisation. Par conséquent, la prochaine fois que la prévision est générée, cette prévision n’est qu’une prévision statistique et n’a aucun remplacement manuel, même si **Transfert des ajustements manuels dans la prévision de la demande** est sélectionné. Par conséquent, vous pouvez considérer la case à cocher **Enregistrer les ajustements manuels apportés à la prévision de la demande de base** comme un mécanisme qui vous permet de conserver ou d’ignorer les modifications manuelles.

## <a name="additional-resources"></a>Ressources supplémentaires

[Effectuer des ajustements manuels sur la prévision de base](manual-adjustments-baseline-forecast.md)

[Contrôler la précision de la prévision](monitor-forecast-accuracy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]