---
title: "Précision de prévision de surveiller"
description: "Cet article décrit les types de précision prévue à Microsoft Dynamics 365 pour les opérations, calcule et explique comment vous pouvez afficher les valeurs de précision."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d3f88a4fa54217cea909c54955de05e2175db0cd
ms.lasthandoff: 03/29/2017


---

# <a name="monitor-forecast-accuracy"></a>Précision de prévision de surveiller

Cet article décrit les types de précision prévue à Microsoft Dynamics 365 pour les opérations, calcule et explique comment vous pouvez afficher les valeurs de précision.

Dynamics 365 pour les opérations calcule les types suivants de précision prévue :

-   Précision de prévision historique, en comparant la prévision historique que la planification utilise à la demande historique. Pour afficher les valeurs (à la fois les valeurs absolues et les valeurs de pourcentage) pour la précision de prévision historique, cliquez sur **Afficher la précision** dans la page **Détails de prévision de la demande**.
-   La précision estimée du modèle de prévision utilisé pour générer les prévisions. Vous pouvez afficher le pourcentage de précision sous **Détails du modèle - MAPE** dans la page **Détails de prévision de la demande**. 

** Remarque : ** Si vous utilisez Dynamics 365 pour le service azuré de Machine Learning Microsoft de prévision de la demande d'opérations, le calcul de la précision modèle interne est basé sur l'ensemble de données de test. Pour spécifier la taille de l'ensemble de données de test, définissez ** POURCENTAGE RÉGLÉ\_de TAILLE\_\_de TEST ** le paramètre sous ** des paramètres de prévision de la demande ** la page. Par exemple, si vous définissez la valeur sur **20**, les derniers 20 % des données historiques seront utilisés pour calculer la précision du modèle interne.


<a name="see-also"></a>Voir également :
--------

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)

[Remove outliers from historical transaction data when calculating a demand forecast](remove-historical-outliers-calculating-demand-forecast.md)


