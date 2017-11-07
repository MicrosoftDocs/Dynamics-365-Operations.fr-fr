---
title: "Surveiller la précision de la prévision"
description: "Cet article décrit les types de précision de prévision que Microsoft Dynamics 365 for Finance and Operations calcule, et explique comment vous pouvez afficher les valeurs de précision."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c2f9482a9906ad6c607d275769ac06b29b22c25d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="monitor-forecast-accuracy"></a>Surveiller la précision de la prévision

[!include[banner](../includes/banner.md)]


Cet article décrit les types de précision de prévision que Microsoft Dynamics 365 for Finance and Operations calcule, et explique comment vous pouvez afficher les valeurs de précision.

Finance and Operations calcule les types de précision de prévision suivants :

-   Précision de prévision historique, en comparant la prévision historique que la planification utilise à la demande historique. Pour afficher les valeurs (à la fois les valeurs absolues et les valeurs de pourcentage) pour la précision de prévision historique, cliquez sur **Afficher la précision** dans la page **Détails de prévision de la demande**.
-   La précision estimée du modèle de prévision utilisé pour générer les prévisions. Vous pouvez afficher le pourcentage de précision sous **Détails du modèle - MAPE** dans la page **Détails de prévision de la demande**. 

**Remarque :** si vous utilisez le service Microsoft Azure Machine Learning de prévision de la demande de Finance and Operations, le calcul de la précision du modèle interne est basé sur l'ensemble de données de test. Pour spécifier la taille de l'ensemble de données de test, définissez le paramètre **TEST\_SET\_SIZE\_PERCENT** dans la page **Paramètres de prévision de la demande**. Par exemple, si vous définissez la valeur sur **20**, les derniers 20 % des données historiques seront utilisés pour calculer la précision du modèle interne.


<a name="see-also"></a>Voir également :
--------

[Autorisation de la prévision ajustée](authorize-adjusted-forecast.md)

[Supprimer les valeurs hors norme des données de transaction historiques lors du calcul d'une prévision de la demande](remove-historical-outliers-calculating-demand-forecast.md)




