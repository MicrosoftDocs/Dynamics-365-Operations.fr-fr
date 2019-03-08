---
title: Générer et exécuter les états prêts à l'emploi
description: Utilisez ce guide de tâche pour exécuter des états prêts à l'emploi dans le siège à partir de différents espaces de travail et des états Recherches et ventes situés sous Commerce et vente au détail.
author: ashishmsft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailCategoryAndProductWorkspace, RetailOrgHierarchyTreeLookup, SrsReportViewerForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b42f86fc243312d18654b1a048f9dffb29afd187
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "365245"
---
# <a name="generate-and-run-out-of-box-reports"></a><span data-ttu-id="00578-103">Générer et exécuter les états prêts à l'emploi</span><span class="sxs-lookup"><span data-stu-id="00578-103">Generate and run out of box reports</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="00578-104">Utilisez ce guide de tâche pour exécuter des états prêts à l'emploi dans le siège à partir de différents espaces de travail et des états Recherches et ventes situés sous Commerce et vente au détail.</span><span class="sxs-lookup"><span data-stu-id="00578-104">Use this task guide to run out of box reports in headquarters from different workspaces and Inquiries & Sales reports located under Retail & Commerce.</span></span>



<span data-ttu-id="00578-105">La société fictive utilisée pour créer cet enregistrement est USRT.</span><span class="sxs-lookup"><span data-stu-id="00578-105">The demo data company used to create this recording is USRT.</span></span> <span data-ttu-id="00578-106">Cet enregistrement est destiné au rôle Administrateur système.</span><span class="sxs-lookup"><span data-stu-id="00578-106">This recording is intended for the System administrator role.</span></span>


## <a name="launch-reports-from-workspaces"></a><span data-ttu-id="00578-107">Lancer des états à partir des espaces de travail</span><span class="sxs-lookup"><span data-stu-id="00578-107">Launch reports from workspaces</span></span>
1. <span data-ttu-id="00578-108">Accédez à Commerce et vente au détail > Produits et catégories > Gestion des catégories et des produits.</span><span class="sxs-lookup"><span data-stu-id="00578-108">Go to Retail and commerce > Products and categories > Category and product management.</span></span>
2. <span data-ttu-id="00578-109">Cliquez sur la flèche pour développer ou réduire la section États.</span><span class="sxs-lookup"><span data-stu-id="00578-109">Click the arrow to expand or collapse the Reports section.</span></span>
3. <span data-ttu-id="00578-110">Cliquez sur État Principaux produits.</span><span class="sxs-lookup"><span data-stu-id="00578-110">Click Top products report.</span></span>
4. <span data-ttu-id="00578-111">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="00578-111">In the From date field, enter a date.</span></span>
5. <span data-ttu-id="00578-112">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="00578-112">In the To date field, enter a date.</span></span>
6. <span data-ttu-id="00578-113">Dans le champ Canal, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="00578-113">In the Channel field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="00578-114">Dans l'arborescence, sélectionnez « Contoso Retail\Contoso Retail USA\Central\Houston ».</span><span class="sxs-lookup"><span data-stu-id="00578-114">In the tree, select 'Contoso Retail\Contoso Retail USA\Central\Houston'.</span></span>
    * <span data-ttu-id="00578-115">La hiérarchie d'organisation de la vente au détail par défaut s'affiche aux fins de génération d'états sur la vente au détail.</span><span class="sxs-lookup"><span data-stu-id="00578-115">This shows the default retail organization hierarchy for Retail reporting purpose.</span></span>   <span data-ttu-id="00578-116">Accédez à Administration d'organisation >Organisations > Objectifs de la hiérarchie d'organisation et choisissez Génération d'états sur les ventes au détail, et sous Hiérarchies affectées, vérifiez le nom de hiérarchie pour lequel la colonne Valeur par défaut est cochée.</span><span class="sxs-lookup"><span data-stu-id="00578-116">Go to Organization administration >Organizations >Organization hierarchy purposes and choose Retail reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span>      <span data-ttu-id="00578-117">Dans le cadre des données de démonstration (utilisées pour cet enregistrement de tâche), vous remarquez que Magasins de vente au détail par région est la hiérarchie d'organisation par défaut pour les besoins de génération d'états sur la vente au détail.</span><span class="sxs-lookup"><span data-stu-id="00578-117">As part of demo data (used for this task recording) you would notice, Retail Stores by Region, is the default organization hierarchy for the Retail reporting purpose.</span></span>     
8. <span data-ttu-id="00578-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="00578-118">Click OK.</span></span>
9. <span data-ttu-id="00578-119">Dans le champ Afficher, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="00578-119">In the View field, select an option.</span></span>
10. <span data-ttu-id="00578-120">Dans le champ Par, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="00578-120">In the By field, select an option.</span></span>
11. <span data-ttu-id="00578-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="00578-121">Click OK.</span></span>

## <a name="launch-reports-from-the-inquiries-and-sales-reports-located-under-retail--commerce-app-link"></a><span data-ttu-id="00578-122">Lancez des états à partir des états de recherches et de ventes situés sous le lien de l'application Commerce et vente au détail.</span><span class="sxs-lookup"><span data-stu-id="00578-122">Launch reports from the inquiries and sales reports located under Retail & Commerce app link.</span></span>
1. <span data-ttu-id="00578-123">Accédez à Commerce et vente au détail > Recherches et états > États des ventes > État des ventes par catégorie.</span><span class="sxs-lookup"><span data-stu-id="00578-123">Go to Retail and commerce > Inquiries and reports > Sales reports > Category sales report.</span></span>
2. <span data-ttu-id="00578-124">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="00578-124">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="00578-125">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="00578-125">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="00578-126">Dans le champ Canal, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="00578-126">In the Channel field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="00578-127">Dans l'arborescence, sélectionnez « Contoso Retail\Contoso Retail USA\West\Seattle ».</span><span class="sxs-lookup"><span data-stu-id="00578-127">In the tree, select 'Contoso Retail\Contoso Retail USA\West\Seattle'.</span></span>
    * <span data-ttu-id="00578-128">La hiérarchie d'organisation de la vente au détail par défaut s'affiche aux fins de génération d'états sur la vente au détail.</span><span class="sxs-lookup"><span data-stu-id="00578-128">This shows the default retail organization hierarchy for Retail reporting purpose.</span></span>   <span data-ttu-id="00578-129">Accédez à Administration d'organisation >Organisations > Objectifs de la hiérarchie d'organisation et choisissez Génération d'états sur les ventes au détail, et sous Hiérarchies affectées, vérifiez le nom de hiérarchie pour lequel la colonne Valeur par défaut est cochée.</span><span class="sxs-lookup"><span data-stu-id="00578-129">Go to Organization administration >Organizations >Organization hierarchy purposes and choose Retail reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span>      <span data-ttu-id="00578-130">Dans le cadre des données de démonstration (utilisées pour cet enregistrement de tâche), vous remarquez que Magasins de vente au détail par région est la hiérarchie d'organisation par défaut pour les besoins de génération d'états sur la vente au détail.</span><span class="sxs-lookup"><span data-stu-id="00578-130">As part of demo data (used for this task recording) you would notice, Retail Stores by Region, is the default organization hierarchy for the Retail reporting purpose.</span></span>     
6. <span data-ttu-id="00578-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="00578-131">Click OK.</span></span>
7. <span data-ttu-id="00578-132">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="00578-132">Click OK.</span></span>

## <a name="export-an-hq-reports"></a><span data-ttu-id="00578-133">Exporter un état HQ</span><span class="sxs-lookup"><span data-stu-id="00578-133">Export an HQ reports</span></span>
1. <span data-ttu-id="00578-134">Accédez à Commerce et vente au détail > Recherches et états > États des ventes > État des ventes d'organisation.</span><span class="sxs-lookup"><span data-stu-id="00578-134">Go to Retail and commerce > Inquiries and reports > Sales reports > Organization sales report.</span></span>
2. <span data-ttu-id="00578-135">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="00578-135">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="00578-136">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="00578-136">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="00578-137">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="00578-137">Click OK.</span></span>
5. <span data-ttu-id="00578-138">Cliquez sur Exporter.</span><span class="sxs-lookup"><span data-stu-id="00578-138">Click Export.</span></span>
6. <span data-ttu-id="00578-139">Cliquez sur PDF.</span><span class="sxs-lookup"><span data-stu-id="00578-139">Click PDF.</span></span>

