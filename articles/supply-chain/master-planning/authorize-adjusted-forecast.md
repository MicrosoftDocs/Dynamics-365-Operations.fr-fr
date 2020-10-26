---
title: Autoriser une prévision ajustée
description: Certaines données de prévision ne doivent pas être autorisées immédiatement. Cet article explique comment spécifier la période pour laquelle une prévision est autorisée. Elle décrit également comment autoriser la prévision pour des sociétés spécifiques et des modèles de prévision.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b599385f4bc79707ac7b6b814dd106813cbf3c9
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982742"
---
# <a name="authorize-an-adjusted-forecast"></a><span data-ttu-id="de083-105">Autoriser une prévision ajustée</span><span class="sxs-lookup"><span data-stu-id="de083-105">Authorize an adjusted forecast</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="de083-106">Certaines données de prévision ne doivent pas être autorisées immédiatement.</span><span class="sxs-lookup"><span data-stu-id="de083-106">Not all forecast data must be authorized immediately.</span></span> <span data-ttu-id="de083-107">Cet article explique comment spécifier la période pour laquelle une prévision est autorisée.</span><span class="sxs-lookup"><span data-stu-id="de083-107">This article explains how you can specify the period that a forecast is authorized for.</span></span> <span data-ttu-id="de083-108">Elle décrit également comment autoriser la prévision pour des sociétés spécifiques et des modèles de prévision.</span><span class="sxs-lookup"><span data-stu-id="de083-108">It also explains how you can authorize the forecast for specific companies and forecast models.</span></span>

<span data-ttu-id="de083-109">Certaines données de prévision ne doivent pas être autorisées immédiatement.</span><span class="sxs-lookup"><span data-stu-id="de083-109">Not all forecast data must be authorized immediately.</span></span> <span data-ttu-id="de083-110">Vous pouvez spécifier les dates de début et de fin de la période à laquelle la prévision est autorisée.</span><span class="sxs-lookup"><span data-stu-id="de083-110">You can specify the start and end dates of the period that the forecast is authorized for.</span></span> <span data-ttu-id="de083-111">Cette fonction permet de figer des intervalles spécifiques.</span><span class="sxs-lookup"><span data-stu-id="de083-111">This functionality lets you freeze specific buckets.</span></span> 

<span data-ttu-id="de083-112">Les dates de début et de fin spécifiées doivent correspondre aux dates de début et de fin de l'intervalle dans lequel la prévision est générée.</span><span class="sxs-lookup"><span data-stu-id="de083-112">The start and end dates that you specify must correspond to the start and end dates of the bucket that the forecast is generated in.</span></span> <span data-ttu-id="de083-113">Le système applique cette restriction et ajuste automatiquement les dates, si l'ajustement est requis.</span><span class="sxs-lookup"><span data-stu-id="de083-113">The system enforces this restriction and automatically adjusts the dates, if adjustment is required.</span></span> 

<span data-ttu-id="de083-114">Sous l'onglet **Détails** de la page **Autorisation**, vous pouvez afficher les détails de la prévision qui a été récemment générée.</span><span class="sxs-lookup"><span data-stu-id="de083-114">On the **Details** tab of the **Authorization** page, you can view details about the forecast that was most recently generated.</span></span> 

<span data-ttu-id="de083-115">Vous pouvez sélectionner les sociétés et les modèles de prévision pour autoriser l'utilisation de la prévision.</span><span class="sxs-lookup"><span data-stu-id="de083-115">You can select the companies and the forecast models to authorize the forecast for use.</span></span> <span data-ttu-id="de083-116">Par défaut, la grille inclut toutes les sociétés pour lesquelles la demande de prévision a été créée.</span><span class="sxs-lookup"><span data-stu-id="de083-116">By default, the grid includes all the companies that forecast demand has been created for.</span></span> <span data-ttu-id="de083-117">Pour chaque société, le modèle de prévision qui correspond au plan prévisionnel actuel qui est paramétré dans les paramètres de planification est prérempli.</span><span class="sxs-lookup"><span data-stu-id="de083-117">For each company, the forecast model that corresponds to the current forecast plan that is set up in the master planning parameters is prefilled.</span></span> <span data-ttu-id="de083-118">Toutefois, vous pouvez remplacer ce modèle de prévision par n'importe quel modèle de prévision qui appartient à cette société.</span><span class="sxs-lookup"><span data-stu-id="de083-118">However, you can change this forecast model to any forecast model that belongs to that company.</span></span> <span data-ttu-id="de083-119">Si aucune donnée de demande de prévision n'a été générée pour une société sélectionnée, vous recevez un message d'avertissement au moment de l'importation.</span><span class="sxs-lookup"><span data-stu-id="de083-119">If no forecast demand data has been generated for a selected company, you receive a warning message at import time.</span></span> 

<span data-ttu-id="de083-120">Il est très important que vous compreniez comment fonctionne la case à cocher **Enregistrer les ajustements manuels apportés à la prévision de la demande de base**.</span><span class="sxs-lookup"><span data-stu-id="de083-120">It's very important that you understand how the **Save the manual adjustments made to the baseline demand forecast** check box works.</span></span> <span data-ttu-id="de083-121">Si vous avez effectué des ajustements manuels sur les prévisions de base statistiques, les valeurs ajustées sont autorisées à être utilisées, même si cette case à cocher est désactivée.</span><span class="sxs-lookup"><span data-stu-id="de083-121">If you've made manual adjustments to the statistical baseline forecast, the adjusted values are authorized for use, even if this check box is cleared.</span></span> <span data-ttu-id="de083-122">Toutefois, les modifications sont ignorées après l'autorisation.</span><span class="sxs-lookup"><span data-stu-id="de083-122">However, the changes are discarded after the authorization.</span></span> <span data-ttu-id="de083-123">Par conséquent, la prochaine fois que la prévision est générée, cette prévision n'est qu'une prévision statistique et n'a aucun remplacement manuel, même si **Transfert des ajustements manuels dans la prévision de la demande** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="de083-123">Therefore, the next time that a forecast is generated, that forecast is only a statistical forecast and doesn't have any manual overrides, even if **Transfer manual adjustments to the demand forecast** is selected.</span></span> <span data-ttu-id="de083-124">Par conséquent, vous pouvez considérer la case à cocher **Enregistrer les ajustements manuels apportés à la prévision de la demande de base** comme un mécanisme qui vous permet de conserver ou d'ignorer les modifications manuelles.</span><span class="sxs-lookup"><span data-stu-id="de083-124">Therefore, you can consider the **Save the manual adjustments made to the baseline demand forecast** check box a mechanism that lets you keep or discard all manual changes.</span></span>

<a name="additional-resources"></a><span data-ttu-id="de083-125">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="de083-125">Additional resources</span></span>
--------

[<span data-ttu-id="de083-126">Effectuer des ajustements manuels sur la prévision de base</span><span class="sxs-lookup"><span data-stu-id="de083-126">Make manual adjustments to the baseline forecast</span></span>](manual-adjustments-baseline-forecast.md)

[<span data-ttu-id="de083-127">Contrôler la précision de la prévision</span><span class="sxs-lookup"><span data-stu-id="de083-127">Monitor forecast accuracy</span></span>](monitor-forecast-accuracy.md)



