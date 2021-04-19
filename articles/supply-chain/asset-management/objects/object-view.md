---
title: Vue des actifs
description: Cette rubrique décrit la vue des actifs dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectTree, EntAssetFunctionalLocationTree
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4a7bf1cf07178f570f32e3fa4c4c1e5a2106b10d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837847"
---
# <a name="asset-view"></a><span data-ttu-id="bafa3-103">Vue des actifs</span><span class="sxs-lookup"><span data-stu-id="bafa3-103">Asset view</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="bafa3-104">Cette rubrique décrit la vue des actifs dans le module Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="bafa3-104">This topic describes the asset view in Asset Management.</span></span> <span data-ttu-id="bafa3-105">La page **Vue des actifs** affiche les actifs actifs et les postes techniques dans une arborescence.</span><span class="sxs-lookup"><span data-stu-id="bafa3-105">The **Asset view** page shows active assets and functional locations in a tree view.</span></span> <span data-ttu-id="bafa3-106">Par conséquent, vous pouvez facilement avoir une vue d’ensemble des relations entre les actifs et les postes techniques.</span><span class="sxs-lookup"><span data-stu-id="bafa3-106">Therefore, you can easily get an overview of asset relations to functional locations.</span></span> <span data-ttu-id="bafa3-107">En outre, vous pouvez afficher des informations détaillées sur les postes techniques, les actifs et les nomenclatures correspondantes.</span><span class="sxs-lookup"><span data-stu-id="bafa3-107">Additionally, you can view detailed information about functional locations, assets, and related bills of materials (BOMs).</span></span> <span data-ttu-id="bafa3-108">Vous pouvez également avoir une vue d’ensemble rapide des demandes de maintenance et des ordres de travail actifs qui sont associés à un actif.</span><span class="sxs-lookup"><span data-stu-id="bafa3-108">You can also get a quick overview of active maintenance requests and work orders that are related to an asset.</span></span>

1. <span data-ttu-id="bafa3-109">Sélectionnez **Gestion des actifs** \> **Commun** \> **Actifs** \> **Vue des actifs**.</span><span class="sxs-lookup"><span data-stu-id="bafa3-109">Select **Asset management** \> **Common** \> **Assets** \> **Asset view**.</span></span>
2. <span data-ttu-id="bafa3-110">Pour modifier la vue qui s’affiche sur la page, sélectionnez une nouvelle valeur dans le champ **Vue**.</span><span class="sxs-lookup"><span data-stu-id="bafa3-110">To change the view that is shown on the page, select a new value in the **View** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bafa3-111">La vue par défaut qui s’affiche lorsque vous ouvrez la page **Vue des actifs** dépend de la valeur sélectionnée dans le champ **Vue** de l’onglet **Actifs** de la page **Paramètres de gestion des actifs** (**Gestion des actifs** \> **Paramétrage** \> **Paramètres de gestion des actifs**).</span><span class="sxs-lookup"><span data-stu-id="bafa3-111">The default view that is shown when you open the **Asset view** page depends on the value that is selected in the **View** field on the **Assets** tab of the **Asset management parameters** page (**Asset management** \> **Setup** \> **Asset management parameters**).</span></span>

<span data-ttu-id="bafa3-112">À droite de la page, les raccourcis affichent les détails de la vue sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bafa3-112">On the right side of the page, FastTabs shows details of the selected view.</span></span>

<span data-ttu-id="bafa3-113">La piste de navigation qui apparaît au-dessus de l’arborescence affiche la sélection actuelle dans l’arborescence.</span><span class="sxs-lookup"><span data-stu-id="bafa3-113">The breadcrumb trail that appears above the tree view shows the current selection in the tree view.</span></span> <span data-ttu-id="bafa3-114">Cette piste de navigation utilise le format suivant :</span><span class="sxs-lookup"><span data-stu-id="bafa3-114">This breadcrumb trail uses the following format:</span></span>

<span data-ttu-id="bafa3-115">ID poste technique / ID poste technique (s’il existe plusieurs postes techniques) \> ID actif / ID actif(s’il existe plusieurs actifs) - Numéro d’article.</span><span class="sxs-lookup"><span data-stu-id="bafa3-115">Functional location ID / Functional location ID (if there is more than one functional location) \> Asset ID / Asset ID (if there is more than one asset) - Item number.</span></span>

<span data-ttu-id="bafa3-116">Si vous avez sélectionné un actif dans l’arborescence, vous pouvez sélectionner **Demandes actives** ou **Ordres de travail actifs** pour afficher les demandes de maintenance ou les ordres de travail associés à l’actif.</span><span class="sxs-lookup"><span data-stu-id="bafa3-116">If you've selected an asset in the tree view, you can select **Active requests** or **Active work orders** to view the maintenance requests or work orders that are related to the asset.</span></span> <span data-ttu-id="bafa3-117">Vous pouvez également sélectionner **Ouvrir** \>, **Poste technique**, **Actif** ou **Nomenclature des actifs** pour ouvrir la vue associée.</span><span class="sxs-lookup"><span data-stu-id="bafa3-117">You can also select **Open** \> **Functional location**, **Asset**, or **Asset BOM** to open the related view.</span></span>

<span data-ttu-id="bafa3-118">L’option **Postes techniques des actifs** que vous pouvez sélectionner dans le champ **Vue** est également disponible dans toute recherche d’actif où vous pouvez sélectionner un actif.</span><span class="sxs-lookup"><span data-stu-id="bafa3-118">The **Asset functional locations** option that you can select in the **View** field is also available in any asset lookup where you can select an asset.</span></span> <span data-ttu-id="bafa3-119">L’arborescence s’affiche sous un onglet **Vue des actifs**, par exemple, où vous [créez un actif](../objects/create-an-object.md), créez une demande de maintenance ou créez un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="bafa3-119">The tree view is shown on an **Asset view** tab, for example, where you [create an asset](../objects/create-an-object.md), create a maintenance request, or create a work order.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]