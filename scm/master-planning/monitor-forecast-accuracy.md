---
title: "Surveiller la précision de la prévision"
description: "Cet article décrit les types de précision de prévision que Microsoft Dynamics 365 for Operations calcule, et explique comment vous pouvez afficher les valeurs de précision."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 580b45263b45e6ef730b0fac32575fcdd9c358b6
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="monitor-forecast-accuracy"></a>Surveiller la précision de la prévision

[!include[banner](../includes/banner.md)]


Cet article décrit les types de précision de prévision que Microsoft Dynamics 365 for Operations calcule, et explique comment vous pouvez afficher les valeurs de précision.

Dynamics 365 for Operations calcule les types de précision de prévision suivants :

-   Précision de prévision historique, en comparant la prévision historique que la planification utilise à la demande historique. Pour afficher les valeurs (à la fois les valeurs absolues et les valeurs de pourcentage) pour la précision de prévision historique, cliquez sur **Afficher la précision** dans la page **Détails de prévision de la demande**.
-   La précision estimée du modèle de prévision utilisé pour générer les prévisions. Vous pouvez afficher le pourcentage de précision sous **Détails du modèle - MAPE** dans la page **Détails de prévision de la demande**. 

**Remarque :** si vous utilisez le service Microsoft Azure Machine Learning de prévision de la demande de Dynamics 365 for Operations, le calcul de la précision du modèle interne est basé sur l'ensemble de données de test. Pour spécifier la taille de l'ensemble de données de test, définissez le paramètre **TEST\_SET\_SIZE\_PERCENT** dans la page **Paramètres de prévision de la demande**. Par exemple, si vous définissez la valeur sur **20**, les derniers 20 % des données historiques seront utilisés pour calculer la précision du modèle interne.


<a name="see-also"></a>Voir également :
--------

[Autorisation de la prévision ajustée](authorize-adjusted-forecast.md)

[Supprimer les valeurs hors norme des données de transaction historiques lors du calcul d'une prévision de la demande](remove-historical-outliers-calculating-demand-forecast.md)




