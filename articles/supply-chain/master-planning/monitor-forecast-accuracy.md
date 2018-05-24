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
ms.search.form: ReqDemPlanForecastDetails
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 1f54251b6f6937c59293bd44a0fc27272ffd3d55
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="monitor-forecast-accuracy"></a><span data-ttu-id="02542-103">Surveiller la précision de la prévision</span><span class="sxs-lookup"><span data-stu-id="02542-103">Monitor forecast accuracy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="02542-104">Cet article décrit les types de précision de prévision que Microsoft Dynamics 365 for Finance and Operations calcule, et explique comment vous pouvez afficher les valeurs de précision.</span><span class="sxs-lookup"><span data-stu-id="02542-104">This article describes the types of forecast accuracy that Microsoft Dynamics 365 for Finance and Operations calculates, and explains how you can view the accuracy values.</span></span>

<span data-ttu-id="02542-105">Finance and Operations calcule les types de précision de prévision suivants :</span><span class="sxs-lookup"><span data-stu-id="02542-105">Finance and Operations calculates the following types of forecast accuracy:</span></span>

-   <span data-ttu-id="02542-106">Précision de prévision historique, en comparant la prévision historique que la planification utilise à la demande historique.</span><span class="sxs-lookup"><span data-stu-id="02542-106">Historical forecast accuracy, by comparing the historical forecast that Master Planning uses with the historical demand.</span></span> <span data-ttu-id="02542-107">Pour afficher les valeurs (à la fois les valeurs absolues et les valeurs de pourcentage) pour la précision de prévision historique, cliquez sur **Afficher la précision** dans la page **Détails de prévision de la demande**.</span><span class="sxs-lookup"><span data-stu-id="02542-107">To view the values (both absolute values and percentage values) for historical forecast accuracy, click **Show accuracy** on the **Demand forecast details** page.</span></span>
-   <span data-ttu-id="02542-108">La précision estimée du modèle de prévision utilisé pour générer les prévisions.</span><span class="sxs-lookup"><span data-stu-id="02542-108">The estimated accuracy of the forecasting model that is used to generate the predictions.</span></span> <span data-ttu-id="02542-109">Vous pouvez afficher le pourcentage de précision sous **Détails du modèle - MAPE** dans la page **Détails de prévision de la demande**.</span><span class="sxs-lookup"><span data-stu-id="02542-109">You can view the accuracy percentage under **Model details - MAPE** on the **Demand forecast details** page.</span></span> 

<span data-ttu-id="02542-110">**Remarque :** si vous utilisez le service Microsoft Azure Machine Learning de prévision de la demande de Finance and Operations, le calcul de la précision du modèle interne est basé sur l'ensemble de données de test.</span><span class="sxs-lookup"><span data-stu-id="02542-110">**Note:** If you use the Finance and Operations Demand forecasting Microsoft Azure Machine Learning service, the calculation of internal model accuracy is based on the test data set.</span></span> <span data-ttu-id="02542-111">Pour spécifier la taille de l'ensemble de données de test, définissez le paramètre **TEST\_SET\_SIZE\_PERCENT** dans la page **Paramètres de prévision de la demande**.</span><span class="sxs-lookup"><span data-stu-id="02542-111">To specify the size of the test data set, set the **TEST\_SET\_SIZE\_PERCENT** parameter on the **Demand forecasting parameters** page.</span></span> <span data-ttu-id="02542-112">Par exemple, si vous définissez la valeur sur **20**, les derniers 20 % des données historiques seront utilisés pour calculer la précision du modèle interne.</span><span class="sxs-lookup"><span data-stu-id="02542-112">For example, if you set the value to **20**, the last 20 percent of the historical data will be used to calculate the internal model accuracy.</span></span>


<a name="additional-resources"></a><span data-ttu-id="02542-113">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="02542-113">Additional resources</span></span>
--------

[<span data-ttu-id="02542-114">Autorisation de la prévision ajustée</span><span class="sxs-lookup"><span data-stu-id="02542-114">Authorizing the adjusted forecast</span></span>](authorize-adjusted-forecast.md)

[<span data-ttu-id="02542-115">Supprimer les valeurs hors norme des données de transaction historiques lors du calcul d'une prévision de la demande</span><span class="sxs-lookup"><span data-stu-id="02542-115">Remove outliers from historical transaction data when calculating a demand forecast</span></span>](remove-historical-outliers-calculating-demand-forecast.md)




