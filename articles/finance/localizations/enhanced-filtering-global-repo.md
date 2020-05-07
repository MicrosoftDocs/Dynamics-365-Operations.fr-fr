---
title: Filtrage amélioré par RCS dans le référentiel RCS/Global
description: Cette rubrique décrit les capacités de filtrage améliorées pour le référentiel RCS Global, qui ont été améliorées pour inclure les filtres supplémentaires.
author: JaneA07
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 1913b661c46af5e34da1a2939cb2a5d5b4e46411
ms.sourcegitcommit: 7df49a85de484d013518217ba8ada6c61da4b6e4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/24/2020
ms.locfileid: "3287937"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a><span data-ttu-id="5940a-103">Options de filtrage améliorées RCS pour trouver des configurations dans le référentiel global/RCS</span><span class="sxs-lookup"><span data-stu-id="5940a-103">RCS enhanced filtering options for finding configurations in the RCS/Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5940a-104">Cette rubrique décrit les capacités de filtrage améliorées pour le référentiel Regulatory Configuration Services (RCS) Global, qui ont été améliorées pour inclure les la capacité de filtrer avec les critères suivants :</span><span class="sxs-lookup"><span data-stu-id="5940a-104">This topic describes enhanced filtering capabilities for Regulatory Configuration Services (RCS) Global repository, which have been improved to include the ability to filter with the following criteria:</span></span> 
- <span data-ttu-id="5940a-105">**Pays/région** : basé sur les codes pays ISO</span><span class="sxs-lookup"><span data-stu-id="5940a-105">**Country/region** - Based on ISO country codes</span></span>  
- <span data-ttu-id="5940a-106">Types de **Balises** pour :</span><span class="sxs-lookup"><span data-stu-id="5940a-106">**Tags** types for:</span></span>
  - <span data-ttu-id="5940a-107">Zone fonctionnelle</span><span class="sxs-lookup"><span data-stu-id="5940a-107">Functional area</span></span>
  - <span data-ttu-id="5940a-108">Fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="5940a-108">Feature area</span></span>
  - <span data-ttu-id="5940a-109">Secteur</span><span class="sxs-lookup"><span data-stu-id="5940a-109">Industry</span></span> 
  - <span data-ttu-id="5940a-110">Document commercial</span><span class="sxs-lookup"><span data-stu-id="5940a-110">Business document</span></span> 

<span data-ttu-id="5940a-111">Pour faciliter la recherche des configurations spécifiques ou connexes, vous pouvez appliquer des filtres, individuellement ou en groupe.</span><span class="sxs-lookup"><span data-stu-id="5940a-111">To make it easier to discover specific or related configurations you can apply filters, either individually or as a group.</span></span> <span data-ttu-id="5940a-112">Par exemple, pour rechercher un seul type de documents commerciaux configurables liés aux factures fournisseur, vous pouvez appliquer un filtre **Type de document commercial** pour rechercher ce type de document.</span><span class="sxs-lookup"><span data-stu-id="5940a-112">For example, to find a single type of 'configurable business documents that are related to vendor invoices, you could apply a **Business document type** filter to search for that type of document.</span></span> 

<span data-ttu-id="5940a-113">[![Section Filtre pour le référentiel Global](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG)</span><span class="sxs-lookup"><span data-stu-id="5940a-113">[![Filter section for Global repository](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG)</span></span> 

<span data-ttu-id="5940a-114">Vous pouvez affiner la recherche en sélectionnant le type de document, par exemple « facture fournisseur » et en cliquant sur **Appliquer le filtre**.</span><span class="sxs-lookup"><span data-stu-id="5940a-114">You can further refine the search by selecting document type, for example 'vendor invoice' and clicking **Apply filter**.</span></span> <span data-ttu-id="5940a-115">L'exemple suivant montre les résultats lors du filtrage sur **Type de document commercial** avec le type de document ajouté.</span><span class="sxs-lookup"><span data-stu-id="5940a-115">The following example shows the results when filtering on **Business document type** with the document type added.</span></span> 

<span data-ttu-id="5940a-116">[![Filtre appliqué et Importer pour le type de document commercial](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG)</span><span class="sxs-lookup"><span data-stu-id="5940a-116">[![Applied filter and Import for business document type](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG)</span></span> 

<span data-ttu-id="5940a-117">Les résultats filtrés peuvent être importés dans un référentiel RCS d'utilisateurs ou un environnement Dynamics 365 Finance, individuellement ou en tant qu'ensemble.</span><span class="sxs-lookup"><span data-stu-id="5940a-117">Filtered results can be imported into a users RCS repository or a Dynamics 365 Finance environment, either individually or as a set.</span></span> <span data-ttu-id="5940a-118">Pour ce faire, sélectionnez le groupe de configurations et cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="5940a-118">To do this, select the group of configurations, and click **Import**.</span></span>
