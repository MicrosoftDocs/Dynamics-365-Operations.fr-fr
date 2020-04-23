---
title: Stock - Balance âgée
description: Cette rubrique décrit les fonctionnalités qui vous permettent d'exécuter un état de la balance âgée et de mettre le résultat à disposition sous la forme d'un formulaire et d'un graphique.
author: AndersGirke
manager: tfehr
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 790c8fe3a52bce652227f1cef97eff6496476100
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201617"
---
# <a name="inventory-aging-report"></a><span data-ttu-id="5a57e-103">Stock - Balance âgée</span><span class="sxs-lookup"><span data-stu-id="5a57e-103">Inventory aging report</span></span>


[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="5a57e-104">Dans Microsoft Dynamics 365 Supply Chain Management, vous pouvez exécuter un état **Balance âgée** et le mettre à disposition sous la forme d'un formulaire et d'un graphique.</span><span class="sxs-lookup"><span data-stu-id="5a57e-104">In Microsoft Dynamics 365 Supply Chain Management, you can run an **Inventory aging** report and make the output available as a form and a chart.</span></span> <span data-ttu-id="5a57e-105">Dans le formulaire, des colonnes et des soldes globaux sont ajustés de façon dynamique, selon la disposition configurée.</span><span class="sxs-lookup"><span data-stu-id="5a57e-105">In the form, columns and aggregate balances are dynamically adjusted, depending on the layout that is configured.</span></span> <span data-ttu-id="5a57e-106">Le graphique offre une vue d'ensemble qui prend en charge les filtres et vous permet de parcourir des informations détaillées.</span><span class="sxs-lookup"><span data-stu-id="5a57e-106">The chart provides a visual overview that supports filtering and lets you drill down into details.</span></span> <span data-ttu-id="5a57e-107">En outre, une entité de données intitulée **État - Balance âgée** vous permet d'exporter les résultats d'un état **Balance âgée** à un format tel qu'un fichier Microsoft Excel ou un fichier PDF.</span><span class="sxs-lookup"><span data-stu-id="5a57e-107">Additionally, a data entity that is named **Inventory aging report** lets you export the results of an **Inventory aging** report run to a format such as a Microsoft Excel file or a PDF file.</span></span>

<span data-ttu-id="5a57e-108">Ce mode d'exécution d'un état **Balance âgée** est utile lorsque le résultat contient plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="5a57e-108">This method of running an **Inventory aging** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="5a57e-109">Par exemple, le résultat contient plusieurs lignes si vous avez 50 000 articles et 300 magasins créés comme entrepôts, et si vous demandez la balance âgée par article, site et entrepôt.</span><span class="sxs-lookup"><span data-stu-id="5a57e-109">For example, the output will contain many lines if you have 50,000 items and 300 stores that are created as warehouses, and you request inventory aging by item, site, and warehouse.</span></span>

## <a name="run-an-inventory-aging-report"></a><span data-ttu-id="5a57e-110">Exécuter un état - Balance âgée</span><span class="sxs-lookup"><span data-stu-id="5a57e-110">Run an Inventory aging report</span></span>

1. <span data-ttu-id="5a57e-111">Accédez à **Gestion des coûts \> Recherches et états \> Stockage des états de balance âgée**.</span><span class="sxs-lookup"><span data-stu-id="5a57e-111">Go to **Cost management \> Inquiries and reports \> Inventory aging report storage**.</span></span>
1. <span data-ttu-id="5a57e-112">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="5a57e-112">Select **New**.</span></span>
1. <span data-ttu-id="5a57e-113">Dans le champ **Identificateur de processus - Nom**, entrez un nom unique pour l'état.</span><span class="sxs-lookup"><span data-stu-id="5a57e-113">In the **Process Identifier – Name** field, enter a unique name for the report.</span></span>
1. <span data-ttu-id="5a57e-114">Sélectionnez l'état **Identification – ID**, et filtrez-le comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="5a57e-114">Select the **Identification – ID** report, and filter it as you require.</span></span>

    <span data-ttu-id="5a57e-115">L'exécution de l'état est toujours effectuée dans un traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="5a57e-115">Report execution is always done in a batch job.</span></span>

1. <span data-ttu-id="5a57e-116">Lorsque le traitement par lots est terminé, le résultat est affiché sur la page **Stockage des états de la balance âgée**.</span><span class="sxs-lookup"><span data-stu-id="5a57e-116">After the batch job is completed, the output is shown on the **Inventory aging report storage** page.</span></span>
1. <span data-ttu-id="5a57e-117">Pour afficher le résultat sous la forme d'un formulaire avec une disposition de grille traditionnelle, sélectionnez **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="5a57e-117">To view the output as a form that has a traditional grid layout, select **View details**.</span></span> <span data-ttu-id="5a57e-118">Pour afficher le résultat comme graphique regroupé, sélectionnez **Afficher le graphique**.</span><span class="sxs-lookup"><span data-stu-id="5a57e-118">To view the output as an aggregated chart, select **View chart**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a57e-119">Le formulaire n'inclut pas les sous-totaux définis dans la disposition de l'état.</span><span class="sxs-lookup"><span data-stu-id="5a57e-119">The form won't include subtotals that are defined in the report layout.</span></span>

<span data-ttu-id="5a57e-120">L'entité de données **État de la balance âgée** vous permet d'exporter le résultat d'un état **Balance âgée** en appliquant un filtre pour le champ **Identificateur de processus – Nom** à n'importe quel format pris en charge par la gestion des données.</span><span class="sxs-lookup"><span data-stu-id="5a57e-120">The **Inventory aging report** data entity lets you export the output of an **Inventory aging** report by applying a filter for the **Process Identifier – Name** field to any format that Data management supports.</span></span>
