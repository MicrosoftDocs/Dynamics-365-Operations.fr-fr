---
title: Importer les données d’historique pour les prévisions de la demande
description: Pour obtenir des prévisions de la demande précises, les données de demande d’historique par article ou par clé de répartition par article sont requises. Cette rubrique explique comment utiliser les entités de données pour importer les données de demande d’historique à partir de n’importe quel système, afin de disposer d’un historique plus long des données de prévision de la demande.
author: roxanadiaconu
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: de380113fe951f75c15f9e5526ad2f1f5cc84334
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908878"
---
# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="57eca-104">Importer les données d’historique pour les prévisions de la demande</span><span class="sxs-lookup"><span data-stu-id="57eca-104">Import historical data for demand forecasts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57eca-105">Pour garantir la précision des prévisions de la demande, vous devez disposer d’autant de données de demande d’historique que possible par article ou par clé de répartition par article.</span><span class="sxs-lookup"><span data-stu-id="57eca-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="57eca-106">Si les données de demande d’historique ne sont pas déjà importées, utilisez l’entité de données **Demande externe d’historique** (ReqDemPlanHistoricalExternalDemandEntity) dans Dynamics 365 Supply Chain Management pour les importer.</span><span class="sxs-lookup"><span data-stu-id="57eca-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Dynamics 365 Supply Chain Management to import it.</span></span>

<span data-ttu-id="57eca-107">L’espace de travail **Gestion des données** donne une vue d’ensemble de tous les champs de l’entité.</span><span class="sxs-lookup"><span data-stu-id="57eca-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="57eca-108">Ouvrez l’espace de travail **Gestion des données**.</span><span class="sxs-lookup"><span data-stu-id="57eca-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="57eca-109">Sélectionnez la vignette **Entités de données**.</span><span class="sxs-lookup"><span data-stu-id="57eca-109">Select the **Data entities** tile.</span></span>
3. <span data-ttu-id="57eca-110">Recherchez **Demande externe d’historique** dans la liste d’entités.</span><span class="sxs-lookup"><span data-stu-id="57eca-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="57eca-111">Sélectionnez **Champs cibles**.</span><span class="sxs-lookup"><span data-stu-id="57eca-111">Select **Target fields**.</span></span> <span data-ttu-id="57eca-112">Les champs d’entité suivants sont obligatoires : site (**DeliveringSiteId**), date (**DemandDate**), quantité (**DemandQuantity**) et numéro d’article (**ItemNumber**) ou clé de répartition par article (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="57eca-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="57eca-113">Pour utiliser l’entité de données, vous devez disposer d’un fichier Microsoft Excel ou d’un fichier de valeurs séparées par des virgules (CSV) contenant les données de demande d’historique.</span><span class="sxs-lookup"><span data-stu-id="57eca-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="57eca-114">L’exemple suivant montre comment importer les données à partir d’un fichier CSV.</span><span class="sxs-lookup"><span data-stu-id="57eca-114">The following example shows how to import the data from a CSV file.</span></span>

<span data-ttu-id="57eca-115">Pour plus d’informations sur l’importation de données, notamment le nettoyage des données après une importation, voir [Vue d’ensemble des tâches d’importation et d’exportation de données](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) et ses rubriques associées.</span><span class="sxs-lookup"><span data-stu-id="57eca-115">For more information about how to import data, including how to clean up data after an import, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) and its related topics.</span></span>

## <a name="example"></a><span data-ttu-id="57eca-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="57eca-116">Example</span></span>

<span data-ttu-id="57eca-117">Vous pouvez utiliser le fichier suivant comme exemple.</span><span class="sxs-lookup"><span data-stu-id="57eca-117">You can use the following file as an example.</span></span> <span data-ttu-id="57eca-118">Téléchargez le fichier [HistoricalDemandData](/dynamics/s-e/).</span><span class="sxs-lookup"><span data-stu-id="57eca-118">Download the [HistoricalDemandData](/dynamics/s-e/).</span></span> <span data-ttu-id="57eca-119">Ce fichier contient les données de demande d’historique pour l’article D0001.</span><span class="sxs-lookup"><span data-stu-id="57eca-119">This file contains the historical demand data for item D0001.</span></span> <span data-ttu-id="57eca-120">Il contient uniquement les champs obligatoires suivants : site, quantité et date de la demande.</span><span class="sxs-lookup"><span data-stu-id="57eca-120">It contains only the following mandatory fields: site, quantity, and the demand date.</span></span>

1. <span data-ttu-id="57eca-121">Sélectionnez la société dans laquelle importer les données de demande d’historique.</span><span class="sxs-lookup"><span data-stu-id="57eca-121">Select the company to import the historical demand data into.</span></span>
2. <span data-ttu-id="57eca-122">Ouvrez l’espace de travail **Gestion des données**.</span><span class="sxs-lookup"><span data-stu-id="57eca-122">Open the **Data management** workspace.</span></span>
3. <span data-ttu-id="57eca-123">Sélectionnez la vignette **Importer**.</span><span class="sxs-lookup"><span data-stu-id="57eca-123">Select the **Import** tile.</span></span>
4. <span data-ttu-id="57eca-124">Entrez un nom pour le projet d’importation, par exemple **Importer la demande d’historique pour l’article D0001**.</span><span class="sxs-lookup"><span data-stu-id="57eca-124">Enter a name for the import project, such as **Import historical demand for item D0001**.</span></span>
5. <span data-ttu-id="57eca-125">Dans le champ **Format des données source**, sélectionnez le format du fichier que vous importez.</span><span class="sxs-lookup"><span data-stu-id="57eca-125">In the **Source data format** field, select the file format of the file that you're importing.</span></span> <span data-ttu-id="57eca-126">Pour importer le fichier HistoricalDemandData pour cet exemple, sélectionnez **CSV**.</span><span class="sxs-lookup"><span data-stu-id="57eca-126">To import the HistoricalDemandData file for this example, select **CSV**.</span></span>
6. <span data-ttu-id="57eca-127">Dans le champ **Nom d’entité**, sélectionnez **Demande externe d’historique**.</span><span class="sxs-lookup"><span data-stu-id="57eca-127">In the **Entity name** field, select **Historical external demand**.</span></span>
7. <span data-ttu-id="57eca-128">Enregistrez le fichier sur votre ordinateur, puis téléchargez-le.</span><span class="sxs-lookup"><span data-stu-id="57eca-128">Save the file to your computer, and then upload it.</span></span>
8. <span data-ttu-id="57eca-129">Sélectionnez **Importer**.</span><span class="sxs-lookup"><span data-stu-id="57eca-129">Select **Import**.</span></span>
9. <span data-ttu-id="57eca-130">La page **Synthèse de l’exécution** s’ouvre automatiquement.</span><span class="sxs-lookup"><span data-stu-id="57eca-130">The **Execution summary** page is opened automatically.</span></span> <span data-ttu-id="57eca-131">Vérifiez les données importées dans la page.</span><span class="sxs-lookup"><span data-stu-id="57eca-131">Verify the imported data on the page.</span></span>

<span data-ttu-id="57eca-132">Après avoir importé les données de demande d’historique, vous pouvez générer une prévision de la demande.</span><span class="sxs-lookup"><span data-stu-id="57eca-132">After you've imported the historical demand data, you can generate a demand forecast.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="57eca-133">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="57eca-133">Additional resources</span></span>

[<span data-ttu-id="57eca-134">Générer des prévisions de base statistiques</span><span class="sxs-lookup"><span data-stu-id="57eca-134">Generate a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)  
[<span data-ttu-id="57eca-135">Vue d’ensemble de tâches d’importation et d’exportation de données</span><span class="sxs-lookup"><span data-stu-id="57eca-135">Data import and export jobs overview</span></span>](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]