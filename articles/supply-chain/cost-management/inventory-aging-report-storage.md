---
title: Stockage des états de balance âgée
description: Cette rubrique décrit les fonctionnalités qui vous permettent d’exécuter un état de la balance âgée et de mettre le résultat à disposition sous la forme d’un formulaire et d’un graphique.
author: AndersGirke
manager: tfehr
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
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
ms.openlocfilehash: c4a1480cf96a4ba753b436c04eb8f7b01379da48
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759662"
---
# <a name="inventory-aging-report-storage"></a><span data-ttu-id="b99bf-103">Stockage des états de balance âgée</span><span class="sxs-lookup"><span data-stu-id="b99bf-103">Inventory aging report storage</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b99bf-104">Dans Microsoft Dynamics 365 Supply Chain Management, vous pouvez exécuter un état **Stockage des états de balance âgée** et le mettre à disposition sous la forme d’un formulaire et d’un graphique.</span><span class="sxs-lookup"><span data-stu-id="b99bf-104">In Microsoft Dynamics 365 Supply Chain Management, you can run an **Inventory aging report storage** report and make the output available as a form and a chart.</span></span> <span data-ttu-id="b99bf-105">Dans le formulaire, des colonnes et des soldes globaux sont ajustés de façon dynamique, selon la disposition configurée.</span><span class="sxs-lookup"><span data-stu-id="b99bf-105">In the form, columns and aggregate balances are dynamically adjusted, depending on the layout that is configured.</span></span> <span data-ttu-id="b99bf-106">Le graphique offre une vue d’ensemble qui prend en charge les filtres et vous permet de parcourir des informations détaillées.</span><span class="sxs-lookup"><span data-stu-id="b99bf-106">The chart provides a visual overview that supports filtering and lets you drill down into details.</span></span> <span data-ttu-id="b99bf-107">En outre, une entité de données intitulée **État - Balance âgée** vous permet d’exporter les résultats d’un état **Stockage des états de balance âgée** à un format tel qu’un fichier Microsoft Excel ou un fichier PDF.</span><span class="sxs-lookup"><span data-stu-id="b99bf-107">Additionally, a data entity that is named **Inventory aging report** lets you export the results of an **Inventory aging report storage** report run to a format such as a Microsoft Excel file or a PDF file.</span></span>

<span data-ttu-id="b99bf-108">Ce mode d’exécution d’un état **Stockage des états de balance âgée** est utile lorsque le résultat contient plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="b99bf-108">This method of running an **Inventory aging report storage** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="b99bf-109">Par exemple, le résultat contient plusieurs lignes si vous avez 50 000 articles et 300 magasins créés comme entrepôts, et si vous demandez la balance âgée par article, site et entrepôt.</span><span class="sxs-lookup"><span data-stu-id="b99bf-109">For example, the output will contain many lines if you have 50,000 items and 300 stores that are created as warehouses, and you request inventory aging by item, site, and warehouse.</span></span>

## <a name="enable-the-inventory-value-storage-report-feature"></a><span data-ttu-id="b99bf-110">Activer la fonctionnalité d’état de stockage des valeur de stock</span><span class="sxs-lookup"><span data-stu-id="b99bf-110">Enable the Inventory value storage report feature</span></span>

<span data-ttu-id="b99bf-111">Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="b99bf-111">Before you can use this feature, you must enable it on your system.</span></span> <span data-ttu-id="b99bf-112">Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="b99bf-112">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the feature status and enable it if needed.</span></span> <span data-ttu-id="b99bf-113">La fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="b99bf-113">Here, the feature is listed as:</span></span>

- <span data-ttu-id="b99bf-114">**Module** : Gestion des coûts</span><span class="sxs-lookup"><span data-stu-id="b99bf-114">**Module** - Cost management</span></span>
- <span data-ttu-id="b99bf-115">**Nom de la fonctionnalité** - Stockage des états de balance âgée</span><span class="sxs-lookup"><span data-stu-id="b99bf-115">**Feature name** - Inventory aging report storage</span></span>

## <a name="run-an-inventory-aging-report-storage"></a><span data-ttu-id="b99bf-116">Exécuter un stockage des états de balance âgée</span><span class="sxs-lookup"><span data-stu-id="b99bf-116">Run an Inventory aging report storage</span></span>

1. <span data-ttu-id="b99bf-117">Accédez à **Gestion des coûts \> Recherches et états \> Stockage des états de balance âgée**.</span><span class="sxs-lookup"><span data-stu-id="b99bf-117">Go to **Cost management \> Inquiries and reports \> Inventory aging report storage**.</span></span>
1. <span data-ttu-id="b99bf-118">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b99bf-118">Select **New**.</span></span>
1. <span data-ttu-id="b99bf-119">Dans le champ **Identificateur de processus - Nom**, entrez un nom unique pour l’état.</span><span class="sxs-lookup"><span data-stu-id="b99bf-119">In the **Process Identifier – Name** field, enter a unique name for the report.</span></span>
1. <span data-ttu-id="b99bf-120">Sélectionnez l’état **Identification – ID**, et filtrez-le comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="b99bf-120">Select the **Identification – ID** report, and filter it as you require.</span></span>

    <span data-ttu-id="b99bf-121">L’exécution de l’état est toujours effectuée dans un traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="b99bf-121">Report execution is always done in a batch job.</span></span>

1. <span data-ttu-id="b99bf-122">Lorsque le traitement par lots est terminé, le résultat est affiché sur la page **Stockage des états de la balance âgée**.</span><span class="sxs-lookup"><span data-stu-id="b99bf-122">After the batch job is completed, the output is shown on the **Inventory aging report storage** page.</span></span>
1. <span data-ttu-id="b99bf-123">Pour afficher le résultat sous la forme d’un formulaire avec une disposition de grille traditionnelle, sélectionnez **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="b99bf-123">To view the output as a form that has a traditional grid layout, select **View details**.</span></span> <span data-ttu-id="b99bf-124">Pour afficher le résultat comme graphique regroupé, sélectionnez **Afficher le graphique**.</span><span class="sxs-lookup"><span data-stu-id="b99bf-124">To view the output as an aggregated chart, select **View chart**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b99bf-125">Le formulaire n’inclut pas les sous-totaux définis dans la disposition de l’état.</span><span class="sxs-lookup"><span data-stu-id="b99bf-125">The form won't include subtotals that are defined in the report layout.</span></span>

<span data-ttu-id="b99bf-126">L’entité de données **État de la balance âgée** vous permet d’exporter le résultat d’un état **Stockage des états de balance âgée** en appliquant un filtre pour le champ **Identificateur de processus – Nom** à n’importe quel format pris en charge par la gestion des données.</span><span class="sxs-lookup"><span data-stu-id="b99bf-126">The **Inventory aging report** data entity lets you export the output of an **Inventory aging report storage** report by applying a filter for the **Process Identifier – Name** field to any format that Data management supports.</span></span>
