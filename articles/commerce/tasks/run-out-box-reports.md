---
title: Générer et exécuter les états prêts à l’emploi
description: Utilisez ce guide de tâche pour exécuter des états prêts à l’emploi dans Headquarters à partir de différents espaces de travail et des états Recherches et ventes situés dans Commerce.
author: ashishmsft
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailCategoryAndProductWorkspace, RetailOrgHierarchyTreeLookup, SrsReportViewerForm
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db75b09f1ae1f83a88a5e5eaef0c8c1b8eab5901
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804135"
---
# <a name="generate-and-run-out-of-box-reports"></a><span data-ttu-id="7b59b-103">Générer et exécuter les états prêts à l’emploi</span><span class="sxs-lookup"><span data-stu-id="7b59b-103">Generate and run out of box reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7b59b-104">Utilisez ce guide de tâche pour exécuter des états prêts à l’emploi dans Headquarters à partir de différents espaces de travail et des états Recherches et ventes situés dans Commerce.</span><span class="sxs-lookup"><span data-stu-id="7b59b-104">Use this task guide to run out of box reports in Headquarters from different workspaces and Inquiries & Sales reports located in Commerce.</span></span>

<span data-ttu-id="7b59b-105">La société fictive utilisée pour créer cet enregistrement est USRT.</span><span class="sxs-lookup"><span data-stu-id="7b59b-105">The demo data company used to create this recording is USRT.</span></span> <span data-ttu-id="7b59b-106">Cet enregistrement est destiné au rôle Administrateur système.</span><span class="sxs-lookup"><span data-stu-id="7b59b-106">This recording is intended for the System administrator role.</span></span>

## <a name="launch-reports-from-workspaces"></a><span data-ttu-id="7b59b-107">Lancer des états à partir des espaces de travail</span><span class="sxs-lookup"><span data-stu-id="7b59b-107">Launch reports from workspaces</span></span>
1. <span data-ttu-id="7b59b-108">Accédez à Retail et Commerce > Produits et catégories > Gestion des catégories et des produits.</span><span class="sxs-lookup"><span data-stu-id="7b59b-108">Go to Retail and Commerce > Products and categories > Category and product management.</span></span>
2. <span data-ttu-id="7b59b-109">Cliquez sur la flèche pour développer ou réduire la section États.</span><span class="sxs-lookup"><span data-stu-id="7b59b-109">Click the arrow to expand or collapse the Reports section.</span></span>
3. <span data-ttu-id="7b59b-110">Cliquez sur État Principaux produits.</span><span class="sxs-lookup"><span data-stu-id="7b59b-110">Click Top products report.</span></span>
4. <span data-ttu-id="7b59b-111">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="7b59b-111">In the From date field, enter a date.</span></span>
5. <span data-ttu-id="7b59b-112">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="7b59b-112">In the To date field, enter a date.</span></span>
6. <span data-ttu-id="7b59b-113">Dans le champ Canal, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="7b59b-113">In the Channel field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="7b59b-114">Dans l’arborescence, sélectionnez « Contoso Retail\Contoso Retail USA\Central\Houston ».</span><span class="sxs-lookup"><span data-stu-id="7b59b-114">In the tree, select 'Contoso Retail\Contoso Retail USA\Central\Houston'.</span></span>
    * <span data-ttu-id="7b59b-115">La hiérarchie d’organisation par défaut pour Commerce s’affiche pour la génération d’états.</span><span class="sxs-lookup"><span data-stu-id="7b59b-115">This shows the default organization hierarchy for Commerce reporting purpose.</span></span>   <span data-ttu-id="7b59b-116">Accédez à Administration d’organisation > Organisations > Objectifs de la hiérarchie d’organisation et choisissez Génération d’états de Commerce et, sous Hiérarchies affectées, vérifiez le nom de la hiérarchie pour lequel la colonne Valeur par défaut est cochée.</span><span class="sxs-lookup"><span data-stu-id="7b59b-116">Go to Organization administration > Organizations > Organization hierarchy purposes and choose Commerce reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span> <span data-ttu-id="7b59b-117">Dans le cadre des données de démonstration (utilisées pour cet enregistrement de tâche), vous remarquez que Magasins par région est la hiérarchie d’organisation par défaut pour la génération d’états.</span><span class="sxs-lookup"><span data-stu-id="7b59b-117">As part of demo data (used for this task recording) you would notice, Stores by Region, is the default organization hierarchy for the reporting purpose.</span></span>     
8. <span data-ttu-id="7b59b-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7b59b-118">Click OK.</span></span>
9. <span data-ttu-id="7b59b-119">Dans le champ Afficher, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="7b59b-119">In the View field, select an option.</span></span>
10. <span data-ttu-id="7b59b-120">Dans le champ Par, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="7b59b-120">In the By field, select an option.</span></span>
11. <span data-ttu-id="7b59b-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7b59b-121">Click OK.</span></span>

## <a name="launch-reports-from-the-inquiries-and-sales-reports"></a><span data-ttu-id="7b59b-122">Lancer des rapports à partir des états Recherches et ventes</span><span class="sxs-lookup"><span data-stu-id="7b59b-122">Launch reports from the inquiries and sales reports</span></span>
1. <span data-ttu-id="7b59b-123">Accédez à Retail et Commerce > Recherches et états > États des ventes > État des ventes par catégorie.</span><span class="sxs-lookup"><span data-stu-id="7b59b-123">Go to Retail and Commerce > Inquiries and reports > Sales reports > Category sales report.</span></span>
2. <span data-ttu-id="7b59b-124">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="7b59b-124">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="7b59b-125">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="7b59b-125">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="7b59b-126">Dans le champ Canal, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="7b59b-126">In the Channel field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="7b59b-127">Dans l’arborescence, sélectionnez « Contoso Retail\Contoso Retail USA\West\Seattle ».</span><span class="sxs-lookup"><span data-stu-id="7b59b-127">In the tree, select 'Contoso Retail\Contoso Retail USA\West\Seattle'.</span></span>
    * <span data-ttu-id="7b59b-128">La hiérarchie d’organisation par défaut pour Commerce s’affiche pour la génération d’états.</span><span class="sxs-lookup"><span data-stu-id="7b59b-128">This shows the default organization hierarchy for Commerce reporting purpose.</span></span> <span data-ttu-id="7b59b-129">Accédez à Administration d’organisation > Organisations > Objectifs de la hiérarchie d’organisation et choisissez Génération d’états de Commerce et, sous Hiérarchies affectées, vérifiez le nom de la hiérarchie pour lequel la colonne Valeur par défaut est cochée.</span><span class="sxs-lookup"><span data-stu-id="7b59b-129">Go to Organization administration > Organizations > Organization hierarchy purposes and choose Commerce reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span> <span data-ttu-id="7b59b-130">Dans le cadre des données de démonstration (utilisées pour cet enregistrement de tâche), vous remarquez que Magasins par région est la hiérarchie d’organisation par défaut pour la génération d’états.</span><span class="sxs-lookup"><span data-stu-id="7b59b-130">As part of demo data (used for this task recording) you would notice, Stores by Region, is the default organization hierarchy for the reporting purpose.</span></span>     
6. <span data-ttu-id="7b59b-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7b59b-131">Click OK.</span></span>
7. <span data-ttu-id="7b59b-132">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7b59b-132">Click OK.</span></span>

## <a name="export-an-hq-reports"></a><span data-ttu-id="7b59b-133">Exporter un état HQ</span><span class="sxs-lookup"><span data-stu-id="7b59b-133">Export an HQ reports</span></span>
1. <span data-ttu-id="7b59b-134">Accédez à Retail et Commerce > Recherches et états > États des ventes > État des ventes d’organisation.</span><span class="sxs-lookup"><span data-stu-id="7b59b-134">Go to Retail and Commerce > Inquiries and reports > Sales reports > Organization sales report.</span></span>
2. <span data-ttu-id="7b59b-135">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="7b59b-135">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="7b59b-136">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="7b59b-136">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="7b59b-137">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7b59b-137">Click OK.</span></span>
5. <span data-ttu-id="7b59b-138">Cliquez sur Exporter.</span><span class="sxs-lookup"><span data-stu-id="7b59b-138">Click Export.</span></span>
6. <span data-ttu-id="7b59b-139">Cliquez sur PDF.</span><span class="sxs-lookup"><span data-stu-id="7b59b-139">Click PDF.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]