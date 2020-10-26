---
title: Importer les données d'historique pour les prévisions de la demande
description: Pour obtenir des prévisions de la demande précises, les données de demande d'historique par article ou par clé de répartition par article sont requises. Cette rubrique explique comment utiliser les entités de données pour importer les données de demande d'historique à partir de n'importe quel système, afin de disposer d'un historique plus long des données de prévision de la demande.
author: roxanadiaconu
manager: tfehr
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c66481b1dd8650960cad2947425c1e6c7450afcb
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982819"
---
# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="603ab-104">Importer les données d'historique pour les prévisions de la demande</span><span class="sxs-lookup"><span data-stu-id="603ab-104">Import historical data for demand forecasts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="603ab-105">Pour garantir la précision des prévisions de la demande, vous devez disposer d'autant de données de demande d'historique que possible par article ou par clé de répartition par article.</span><span class="sxs-lookup"><span data-stu-id="603ab-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="603ab-106">Si les données de demande d'historique ne sont pas déjà importées, utilisez l'entité de données **Demande externe d'historique** (ReqDemPlanHistoricalExternalDemandEntity) dans Dynamics 365 Supply Chain Management pour les importer.</span><span class="sxs-lookup"><span data-stu-id="603ab-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Dynamics 365 Supply Chain Management to import it.</span></span>

<span data-ttu-id="603ab-107">L'espace de travail **Gestion des données** donne une vue d'ensemble de tous les champs de l'entité.</span><span class="sxs-lookup"><span data-stu-id="603ab-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="603ab-108">Ouvrez l'espace de travail **Gestion des données**.</span><span class="sxs-lookup"><span data-stu-id="603ab-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="603ab-109">Cliquez sur la vignette **Entités de données**.</span><span class="sxs-lookup"><span data-stu-id="603ab-109">Click the **Data entities** tile.</span></span>
3. <span data-ttu-id="603ab-110">Recherchez **Demande externe d'historique** dans la liste d'entités.</span><span class="sxs-lookup"><span data-stu-id="603ab-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="603ab-111">Cliquez sur **Champs cibles**.</span><span class="sxs-lookup"><span data-stu-id="603ab-111">Click **Target fields**.</span></span> <span data-ttu-id="603ab-112">Les champs d'entité suivants sont obligatoires : site (**DeliveringSiteId**), date (**DemandDate**), quantité (**DemandQuantity**) et numéro d'article (**ItemNumber**) ou clé de répartition par article (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="603ab-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="603ab-113">Pour utiliser l'entité de données, vous devez disposer d'un fichier Microsoft Excel ou d'un fichier de valeurs séparées par des virgules (CSV) contenant les données de demande d'historique.</span><span class="sxs-lookup"><span data-stu-id="603ab-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="603ab-114">L'exemple suivant montre comment importer les données à partir d'un fichier CSV.</span><span class="sxs-lookup"><span data-stu-id="603ab-114">The following example shows how to import the data from a CSV file.</span></span>

## <a name="example"></a><span data-ttu-id="603ab-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="603ab-115">Example</span></span>

<span data-ttu-id="603ab-116">Vous pouvez utiliser le fichier suivant comme exemple.</span><span class="sxs-lookup"><span data-stu-id="603ab-116">You can use the following file as an example.</span></span> <span data-ttu-id="603ab-117">Téléchargez le fichier [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast).</span><span class="sxs-lookup"><span data-stu-id="603ab-117">Download the [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast).</span></span> <span data-ttu-id="603ab-118">Ce fichier contient les données de demande d'historique pour l'article D0001.</span><span class="sxs-lookup"><span data-stu-id="603ab-118">This file contains the historical demand data for item D0001.</span></span> <span data-ttu-id="603ab-119">Il contient uniquement les champs obligatoires suivants : site, quantité et date de la demande.</span><span class="sxs-lookup"><span data-stu-id="603ab-119">It contains only the following mandatory fields: site, quantity, and the demand date.</span></span>

1. <span data-ttu-id="603ab-120">Sélectionnez la société dans laquelle importer les données de demande d'historique.</span><span class="sxs-lookup"><span data-stu-id="603ab-120">Select the company to import the historical demand data into.</span></span>
2. <span data-ttu-id="603ab-121">Ouvrez l'espace de travail **Gestion des données**.</span><span class="sxs-lookup"><span data-stu-id="603ab-121">Open the **Data management** workspace.</span></span>
3. <span data-ttu-id="603ab-122">Cliquez sur la vignette **Importer**.</span><span class="sxs-lookup"><span data-stu-id="603ab-122">Click the **Import** tile.</span></span>
4. <span data-ttu-id="603ab-123">Entrez un nom pour le projet d'importation, par exemple **Importer la demande d'historique pour l'article D0001**.</span><span class="sxs-lookup"><span data-stu-id="603ab-123">Enter a name for the import project, such as **Import historical demand for item D0001**.</span></span>
5. <span data-ttu-id="603ab-124">Dans le champ **Format des données source**, sélectionnez le format du fichier que vous importez.</span><span class="sxs-lookup"><span data-stu-id="603ab-124">In the **Source data format** field, select the file format of the file that you're importing.</span></span> <span data-ttu-id="603ab-125">Pour importer le fichier HistoricalDemandData pour cet exemple, sélectionnez **CSV**.</span><span class="sxs-lookup"><span data-stu-id="603ab-125">To import the HistoricalDemandData file for this example, select **CSV**.</span></span>
6. <span data-ttu-id="603ab-126">Dans le champ **Nom d'entité**, sélectionnez **Demande externe d'historique**.</span><span class="sxs-lookup"><span data-stu-id="603ab-126">In the **Entity name** field, select **Historical external demand**.</span></span>
7. <span data-ttu-id="603ab-127">Enregistrez le fichier sur votre ordinateur, puis téléchargez-le.</span><span class="sxs-lookup"><span data-stu-id="603ab-127">Save the file to your computer, and then upload it.</span></span>
8. <span data-ttu-id="603ab-128">Cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="603ab-128">Click **Import**.</span></span>
9. <span data-ttu-id="603ab-129">La page **Synthèse de l'exécution** s'ouvre automatiquement.</span><span class="sxs-lookup"><span data-stu-id="603ab-129">The **Execution summary** page is opened automatically.</span></span> <span data-ttu-id="603ab-130">Vérifiez les données importées dans la page.</span><span class="sxs-lookup"><span data-stu-id="603ab-130">Verify the imported data on the page.</span></span>

<span data-ttu-id="603ab-131">Après avoir importé les données de demande d'historique, vous pouvez générer une prévision de la demande.</span><span class="sxs-lookup"><span data-stu-id="603ab-131">After you've imported the historical demand data, you can generate a demand forecast.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="603ab-132">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="603ab-132">Additional resources</span></span>

[<span data-ttu-id="603ab-133">Générer des prévisions de base statistiques</span><span class="sxs-lookup"><span data-stu-id="603ab-133">Generate a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)
