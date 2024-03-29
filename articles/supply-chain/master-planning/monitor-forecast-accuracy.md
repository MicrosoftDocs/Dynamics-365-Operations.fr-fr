---
title: Surveiller la précision de la prévision
description: Cet article décrit les types de précision de prévision que Dynamics 365 Supply Chain Management calcule, et explique comment vous pouvez afficher les valeurs de précision.
author: t-benebo
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76248d87533fd233b255060aa278c76e13719700
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740737"
---
# <a name="monitor-forecast-accuracy"></a>Surveiller la précision de la prévision

[!include [banner](../includes/banner.md)]

Cet article décrit les types de précision de prévision que Microsoft Dynamics 365 Supply Chain Management calcule, et explique comment vous pouvez afficher les valeurs de précision.

Supply Chain Management calcule les types de précision de prévision suivants :

-   Précision de prévision historique, en comparant la prévision historique que la planification utilise à la demande historique. Pour afficher les valeurs (à la fois les valeurs absolues et les valeurs de pourcentage) pour la précision de prévision historique, cliquez sur **Afficher la précision** dans la page **Détails de prévision de la demande**.
-   La précision estimée du modèle de prévision utilisé pour générer les prévisions. Vous pouvez afficher le pourcentage de précision sous **Détails du modèle - MAPE** dans la page **Détails de prévision de la demande**. 

> [!NOTE]
> Si vous utilisez Microsoft Azure Machine Learning pour la prévision de la demande, le calcul de la précision du modèle interne est basé sur l’ensemble de données de test. Pour spécifier la taille de l’ensemble de données de test, définissez le paramètre **TEST\_SET\_SIZE\_PERCENT** dans la page **Paramètres de prévision de la demande**. Par exemple, si vous définissez la valeur sur **20**, les derniers 20 % des données historiques seront utilisés pour calculer la précision du modèle interne.


## <a name="additional-resources"></a>Ressources supplémentaires

- [Autoriser un ajustement de la prévision de demande](authorize-adjusted-forecast.md)
- [Supprimer les valeurs hors norme des données de transaction historiques lors du calcul d’une prévision de la demande](remove-historical-outliers-calculating-demand-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]