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
ms.openlocfilehash: 0b04ee246d4c28e934407ccb92d792692cc4347d
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301648"
---
# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="6fb7e-104">Importer les données d’historique pour les prévisions de la demande</span><span class="sxs-lookup"><span data-stu-id="6fb7e-104">Import historical data for demand forecasts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6fb7e-105">Pour garantir la précision des prévisions de la demande, vous devez disposer d’autant de données de demande d’historique que possible par article ou par clé de répartition par article.</span><span class="sxs-lookup"><span data-stu-id="6fb7e-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="6fb7e-106">Si les données de demande d’historique ne sont pas déjà importées, utilisez l’entité de données **Demande externe d’historique** (ReqDemPlanHistoricalExternalDemandEntity) dans Dynamics 365 Supply Chain Management pour les importer.</span><span class="sxs-lookup"><span data-stu-id="6fb7e-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Dynamics 365 Supply Chain Management to import it.</span></span>

<span data-ttu-id="6fb7e-107">L’espace de travail **Gestion des données** donne une vue d’ensemble de tous les champs de l’entité.</span><span class="sxs-lookup"><span data-stu-id="6fb7e-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="6fb7e-108">Ouvrez l’espace de travail **Gestion des données**.</span><span class="sxs-lookup"><span data-stu-id="6fb7e-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="6fb7e-109">Sélectionnez la vignette **Entités de données**.</span><span class="sxs-lookup"><span data-stu-id="6fb7e-109">Select the **Data entities** tile.</span></span>
3. <span data-ttu-id="6fb7e-110">Recherchez **Demande externe d’historique** dans la liste d’entités.</span><span class="sxs-lookup"><span data-stu-id="6fb7e-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="6fb7e-111">Sélectionnez **Champs cibles**.</span><span class="sxs-lookup"><span data-stu-id="6fb7e-111">Select **Target fields**.</span></span> <span data-ttu-id="6fb7e-112">Les champs d’entité suivants sont obligatoires : site (**DeliveringSiteId**), date (**DemandDate**), quantité (**DemandQuantity**) et numéro d’article (**ItemNumber**) ou clé de répartition par article (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="6fb7e-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="6fb7e-113">Pour utiliser l’entité de données, vous devez disposer d’un fichier Microsoft Excel ou d’un fichier de valeurs séparées par des virgules (CSV) contenant les données de demande d’historique.</span><span class="sxs-lookup"><span data-stu-id="6fb7e-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="6fb7e-114">L’exemple suivant montre comment importer les données à partir d’un fichier CSV.</span><span class="sxs-lookup"><span data-stu-id="6fb7e-114">The following example shows how to import the data from a CSV file.</span></span>

<span data-ttu-id="6fb7e-115">Pour plus d’informations sur l’importation de données, notamment le nettoyage des données après une importation, voir [Vue d’ensemble des tâches d’importation et d’exportation de données](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) et ses rubriques associées.</span><span class="sxs-lookup"><span data-stu-id="6fb7e-115">For more information about how to import data, including how to clean up data after an import, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) and its related topics.</span></span>

<span data-ttu-id="6fb7e-116">Voir aussi [Générer des prévisions de base statistiques](generate-statistical-baseline-forecast.md).</span><span class="sxs-lookup"><span data-stu-id="6fb7e-116">See also [Generate a statistical baseline forecast](generate-statistical-baseline-forecast.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]