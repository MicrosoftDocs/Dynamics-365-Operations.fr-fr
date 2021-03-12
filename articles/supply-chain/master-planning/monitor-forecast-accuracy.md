---
title: Contrôler la précision de la prévision
description: Cette rubrique décrit les types de précision de prévision que Dynamics 365 Supply Chain Management calcule, et explique comment vous pouvez afficher les valeurs de précision.
author: roxanadiaconu
manager: tfehr
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a21e9d6199229438b73bfdf8307030eed60c21bb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977936"
---
# <a name="monitor-forecast-accuracy"></a><span data-ttu-id="61ef8-103">Contrôler la précision de la prévision</span><span class="sxs-lookup"><span data-stu-id="61ef8-103">Monitor forecast accuracy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="61ef8-104">Cette rubrique décrit les types de précision de prévision que Microsoft Dynamics 365 Supply Chain Management calcule, et explique comment vous pouvez afficher les valeurs de précision.</span><span class="sxs-lookup"><span data-stu-id="61ef8-104">This topic describes the types of forecast accuracy that Microsoft Dynamics 365 Supply Chain Management calculates, and explains how you can view the accuracy values.</span></span>

<span data-ttu-id="61ef8-105">Supply Chain Management calcule les types de précision de prévision suivants :</span><span class="sxs-lookup"><span data-stu-id="61ef8-105">Supply Chain Management calculates the following types of forecast accuracy:</span></span>

-   <span data-ttu-id="61ef8-106">Précision de prévision historique, en comparant la prévision historique que la planification utilise à la demande historique.</span><span class="sxs-lookup"><span data-stu-id="61ef8-106">Historical forecast accuracy, by comparing the historical forecast that Master Planning uses with the historical demand.</span></span> <span data-ttu-id="61ef8-107">Pour afficher les valeurs (à la fois les valeurs absolues et les valeurs de pourcentage) pour la précision de prévision historique, cliquez sur **Afficher la précision** dans la page **Détails de prévision de la demande**.</span><span class="sxs-lookup"><span data-stu-id="61ef8-107">To view the values (both absolute values and percentage values) for historical forecast accuracy, click **Show accuracy** on the **Demand forecast details** page.</span></span>
-   <span data-ttu-id="61ef8-108">La précision estimée du modèle de prévision utilisé pour générer les prévisions.</span><span class="sxs-lookup"><span data-stu-id="61ef8-108">The estimated accuracy of the forecasting model that is used to generate the predictions.</span></span> <span data-ttu-id="61ef8-109">Vous pouvez afficher le pourcentage de précision sous **Détails du modèle - MAPE** dans la page **Détails de prévision de la demande**.</span><span class="sxs-lookup"><span data-stu-id="61ef8-109">You can view the accuracy percentage under **Model details - MAPE** on the **Demand forecast details** page.</span></span> 

> [!NOTE]
> <span data-ttu-id="61ef8-110">Si vous utilisez Microsoft Azure Machine Learning pour la prévision de la demande, le calcul de la précision du modèle interne est basé sur l'ensemble de données de test.</span><span class="sxs-lookup"><span data-stu-id="61ef8-110">If you use the Demand forecasting Microsoft Azure Machine Learning, the calculation of internal model accuracy is based on the test data set.</span></span> <span data-ttu-id="61ef8-111">Pour spécifier la taille de l'ensemble de données de test, définissez le paramètre **TEST\_SET\_SIZE\_PERCENT** dans la page **Paramètres de prévision de la demande**.</span><span class="sxs-lookup"><span data-stu-id="61ef8-111">To specify the size of the test data set, set the **TEST\_SET\_SIZE\_PERCENT** parameter on the **Demand forecasting parameters** page.</span></span> <span data-ttu-id="61ef8-112">Par exemple, si vous définissez la valeur sur **20**, les derniers 20 % des données historiques seront utilisés pour calculer la précision du modèle interne.</span><span class="sxs-lookup"><span data-stu-id="61ef8-112">For example, if you set the value to **20**, the last 20 percent of the historical data will be used to calculate the internal model accuracy.</span></span>


<a name="additional-resources"></a><span data-ttu-id="61ef8-113">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="61ef8-113">Additional resources</span></span>
--------

[<span data-ttu-id="61ef8-114">Autoriser un ajustement de la prévision de demande</span><span class="sxs-lookup"><span data-stu-id="61ef8-114">Authorize an adjusted forecast</span></span>](authorize-adjusted-forecast.md)

[<span data-ttu-id="61ef8-115">Supprimer les valeurs hors norme des données de transaction historiques lors du calcul d'une prévision de la demande</span><span class="sxs-lookup"><span data-stu-id="61ef8-115">Remove outliers from historical transaction data when calculating a demand forecast</span></span>](remove-historical-outliers-calculating-demand-forecast.md)



