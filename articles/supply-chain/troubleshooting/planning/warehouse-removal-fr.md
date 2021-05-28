---
title: Vous ne pouvez pas supprimer la dimension de prévision de la demande d'entrepôt des lignes de prévision
description: Vous ne pouvez pas supprimer la dimension de prévision de la demande d'entrepôt des lignes de prévision.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6b643c4fe51ae6ce73b34ab81d4e458dcd5032df
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026510"
---
# <a name="you-cant-remove-the-warehouse-demand-forecast-dimension-from-forecast-lines"></a><span data-ttu-id="6709b-103">Vous ne pouvez pas supprimer la dimension de prévision de la demande d'entrepôt des lignes de prévision</span><span class="sxs-lookup"><span data-stu-id="6709b-103">You can't remove the Warehouse demand forecast dimension from forecast lines</span></span>

<span data-ttu-id="6709b-104">Numéro de la base de connaissances : 4614408</span><span class="sxs-lookup"><span data-stu-id="6709b-104">KB number: 4614408</span></span>

## <a name="symptoms"></a><span data-ttu-id="6709b-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="6709b-105">Symptoms</span></span>

<span data-ttu-id="6709b-106">Ce problème se produit lorsque la dimension **Entrepôt** n'est pas attribuée sur l'onglet **Dimensions de prévision** de la page **Paramètre de prévision de la demande**.</span><span class="sxs-lookup"><span data-stu-id="6709b-106">This issue occurs when the **Warehouse** dimension isn't assigned on the **Forecast dimensions** tab of the **Demand forecasting parameter** page.</span></span> <span data-ttu-id="6709b-107">Néanmoins, la colonne **Entrepôt** est affichée sur la page **Prévision de la demande** (**Planification générale \> Prévision \> Entité de prévision manuelle \> Lignes de prévision de la demande**).</span><span class="sxs-lookup"><span data-stu-id="6709b-107">Nevertheless, the **Warehouse** column is shown on the **Demand forecast** page (**Master planning \> Forecasting \> Manual forecast entity \> Demand forecast lines**).</span></span>

## <a name="resolution"></a><span data-ttu-id="6709b-108">Résolution</span><span class="sxs-lookup"><span data-stu-id="6709b-108">Resolution</span></span>

<span data-ttu-id="6709b-109">Les paramètres sur l'onglet **Dimensions de prévision** de la page **Paramètre de prévision de la demande** n'affecte pas la page **Prévision de la demande**.</span><span class="sxs-lookup"><span data-stu-id="6709b-109">The settings on the **Forecast dimensions** tab of the **Demand forecasting parameter** page don't affect the **Demand forecast** page.</span></span> <span data-ttu-id="6709b-110">Ils contrôlent la prévision de base qui est générée et affichée dans la prévision de demande ajustée.</span><span class="sxs-lookup"><span data-stu-id="6709b-110">They control the baseline forecast that is generated and shown in the adjusted demand forecast.</span></span> <span data-ttu-id="6709b-111">Cependant, ils ne contrôlent pas les dimensions requises pour la prévision de la demande "réelle".</span><span class="sxs-lookup"><span data-stu-id="6709b-111">However, they don't control the dimensions that are required for the "real" demand forecast.</span></span> <span data-ttu-id="6709b-112">En autorisant les enregistrements affichés sur la page **Prévision de la demande ajustée**, vous pouvez les convertir en entrées de prévision "réelles" pour un modèle de prévision.</span><span class="sxs-lookup"><span data-stu-id="6709b-112">By authorizing the records that are shown on the **Adjusted demand forecast** page, you can convert them to "real" forecast entries for a forecast model.</span></span> <span data-ttu-id="6709b-113">Ce modèle peut ensuite être utilisé pour la planification générale.</span><span class="sxs-lookup"><span data-stu-id="6709b-113">That model can then be used for master planning.</span></span>

<span data-ttu-id="6709b-114">Sur la page **Prévision de la demande**, les dimensions de la prévision "réelle" qui sont affichées sur les lignes de prévision de la demande font partie des dimensions du stock.</span><span class="sxs-lookup"><span data-stu-id="6709b-114">On the **Demand forecast** page, the dimensions for the "real" forecast that are shown on the demand forecast lines are part of the inventory dimensions.</span></span> <span data-ttu-id="6709b-115">(Ce comportement ressemble au comportement des lignes de commande client.) Si votre système n'est pas configuré pour utiliser **Entrepôt** en tant que dimension de stock obligatoire, vous pouvez personnaliser la page pour masquer la colonne.</span><span class="sxs-lookup"><span data-stu-id="6709b-115">(This behavior resembles the behavior for sales order lines.) If your system isn't set up to use **Warehouse** as a mandatory inventory dimension, you can customize the page to hide the column.</span></span>
