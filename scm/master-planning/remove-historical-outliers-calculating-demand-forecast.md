---
title: "Supprimer les valeurs hors norme des données de transaction historiques lors du calcul d'une prévision de la demande"
description: "Cette article décrit la procédure d'exclusion des valeurs hors norme des données historiques utilisées pour calculer une prévision de la demande. En excluant des les valeurs hors normes, vous pouvez améliorer la précision de prévision."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: ea3f08b20e25af6ebb738c2373b65532d74a0c80
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---

# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a><span data-ttu-id="bc4b9-104">Supprimer les valeurs hors norme des données de transaction historiques lors du calcul d'une prévision de la demande</span><span class="sxs-lookup"><span data-stu-id="bc4b9-104">Remove outliers from historical transaction data when calculating a demand forecast</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="bc4b9-105">Cette article décrit la procédure d'exclusion des valeurs hors norme des données historiques utilisées pour calculer une prévision de la demande.</span><span class="sxs-lookup"><span data-stu-id="bc4b9-105">This article describes how to exclude outliers from the historical data that is used to calculate a demand forecast.</span></span> <span data-ttu-id="bc4b9-106">En excluant des les valeurs hors normes, vous pouvez améliorer la précision de prévision.</span><span class="sxs-lookup"><span data-stu-id="bc4b9-106">By excluding outliers, you can improve forecast accuracy.</span></span>

<span data-ttu-id="bc4b9-107">Vous pouvez exclure les valeurs hors normes pour améliorer la précision de prévision.</span><span class="sxs-lookup"><span data-stu-id="bc4b9-107">You can exclude outliers to improve forecast accuracy.</span></span> <span data-ttu-id="bc4b9-108">Cette tâche est facultative.</span><span class="sxs-lookup"><span data-stu-id="bc4b9-108">This is an optional task.</span></span> <span data-ttu-id="bc4b9-109">Vue d'ensemble du processus :</span><span class="sxs-lookup"><span data-stu-id="bc4b9-109">Here is an overview of the process:</span></span>

1.  <span data-ttu-id="bc4b9-110">Cliquez sur **Planification** &gt; **Paramétrage** &gt; **Prévision de la demande** &gt; **Suppression des valeurs hors norme** pour ouvrir la page **Suppression des valeurs hors norme**, dans laquelle vous pouvez utiliser une requête pour sélectionner les transactions à exclure.</span><span class="sxs-lookup"><span data-stu-id="bc4b9-110">Click **Master planning** &gt; **Setup** &gt; **Demand forecasting** &gt; **Outlier removal** to open the **Outlier removal** page, where you can use a query to select the transactions to exclude.</span></span>
2.  <span data-ttu-id="bc4b9-111">Sélectionnez la société à laquelle la requête s'applique, puis entrez un nom et une description.</span><span class="sxs-lookup"><span data-stu-id="bc4b9-111">Select the company that the query applies to, and then enter a name and description.</span></span> <span data-ttu-id="bc4b9-112">Le champ **Date de la requête** est automatiquement défini sur la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="bc4b9-112">The **Query date** field is automatically set to the current date.</span></span>
3.  <span data-ttu-id="bc4b9-113">Cochez la case **Actif** pour exclure les transactions trouvées par la requête dans les données historiques.</span><span class="sxs-lookup"><span data-stu-id="bc4b9-113">Select the **Active** check box to exclude the transactions that the query finds from the historical data.</span></span> <span data-ttu-id="bc4b9-114">Ce paramètre entrera en effet lorsque vous créerez une prévision de base.</span><span class="sxs-lookup"><span data-stu-id="bc4b9-114">This setting will take effect when you create a baseline forecast.</span></span>
4.  <span data-ttu-id="bc4b9-115">Sur la page **Requête de suppression des valeurs hors norme**, vous pouvez ajouter, supprimer et sélectionner les critères qui définissent les transactions exclues lorsque la prévision de base est calculée.</span><span class="sxs-lookup"><span data-stu-id="bc4b9-115">On the **Outlier removal query** page, you can add, remove, and select the criteria that define which transactions will be excluded when the baseline forecast is calculated.</span></span> <span data-ttu-id="bc4b9-116">Par exemple, sélectionnez un article ou une transaction de commande spécifique à exclure.</span><span class="sxs-lookup"><span data-stu-id="bc4b9-116">For example, select a specific item or order transaction to exclude.</span></span>
5.  <span data-ttu-id="bc4b9-117">Cliquez sur **Afficher les transactions**.</span><span class="sxs-lookup"><span data-stu-id="bc4b9-117">Click **Display transactions**.</span></span> <span data-ttu-id="bc4b9-118">La page **Transactions de valeurs hors norme** répertorie les transactions qui correspondent aux critères que vous avez définis dans la requête et qui seront exclues des données historiques lors du calcul de la prévision de la demande.</span><span class="sxs-lookup"><span data-stu-id="bc4b9-118">The **Outlier transactions** page lists the transactions that meet the criteria that you defined in the query, and that will be excluded from the historical data when the demand forecast is calculated.</span></span>

<span data-ttu-id="bc4b9-119">**Remarque :** vous pouvez également créer une requête basée sur une requête existante.</span><span class="sxs-lookup"><span data-stu-id="bc4b9-119">**Note:** You can also create a query that is based on an existing query.</span></span> <span data-ttu-id="bc4b9-120">Sélectionnez la requête à copier, puis cliquez sur **Dupliquer**.</span><span class="sxs-lookup"><span data-stu-id="bc4b9-120">Select the query to copy, and then click **Duplicate**.</span></span> <span data-ttu-id="bc4b9-121">Le champ **Date de la requête** identifie la version.</span><span class="sxs-lookup"><span data-stu-id="bc4b9-121">The **Query date** field identifies the version.</span></span> <span data-ttu-id="bc4b9-122">Vous pouvez utiliser la requête telle qu'elle est, ou vous pouvez cliquer sur **Modifier la requête** pour modifier les critères.</span><span class="sxs-lookup"><span data-stu-id="bc4b9-122">You can use the query as it is, or you can click **Edit query** to modify the criteria.</span></span> <span data-ttu-id="bc4b9-123">Vous pouvez également, si vous le souhaitez, modifier le nom et la description de la nouvelle requête.</span><span class="sxs-lookup"><span data-stu-id="bc4b9-123">You can optionally modify the name and description of the new query.</span></span>

<a name="see-also"></a><span data-ttu-id="bc4b9-124">Voir également :</span><span class="sxs-lookup"><span data-stu-id="bc4b9-124">See also</span></span>
--------

[<span data-ttu-id="bc4b9-125">Présentation de la prévision de la demande</span><span class="sxs-lookup"><span data-stu-id="bc4b9-125">Introduction to demand forecasting</span></span>](introduction-demand-forecasting.md)

[<span data-ttu-id="bc4b9-126">Surveillance de la précision de la prévision</span><span class="sxs-lookup"><span data-stu-id="bc4b9-126">Monitoring forecast accuracy</span></span>](monitor-forecast-accuracy.md)




