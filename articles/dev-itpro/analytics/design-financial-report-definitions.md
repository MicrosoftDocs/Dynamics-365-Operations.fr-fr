---
title: Définitions d'états dans le générateur d'états financiers
description: Cet article fournit des informations sur les définitions d'état. Une définition d'état est un composant d'état (ou bloc élémentaire) qui utilise une définition de ligne, de colonne et d'organigramme d'entreprise facultatif pour créer un état. Une définition d'état fournit également les paramètres et les options pour la personnalisation d’un état.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 322f1cca32053224e1cd6dbaf29c098b983b5e1f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547052"
---
# <a name="report-definitions-in-financial-report-designer"></a><span data-ttu-id="9b705-105">Définitions d'états dans le générateur d'états financiers</span><span class="sxs-lookup"><span data-stu-id="9b705-105">Report definitions in financial report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9b705-106">Cet article fournit des informations sur les définitions d'état.</span><span class="sxs-lookup"><span data-stu-id="9b705-106">This article provides information about report definitions.</span></span> <span data-ttu-id="9b705-107">Une définition d'état est un composant d'état (ou bloc élémentaire) qui utilise une définition de ligne, de colonne et d'organigramme d'entreprise facultatif pour créer un état.</span><span class="sxs-lookup"><span data-stu-id="9b705-107">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="9b705-108">Une définition d'état fournit également les paramètres et les options pour la personnalisation d’un état.</span><span class="sxs-lookup"><span data-stu-id="9b705-108">A report definition also provides options and settings that for customizing a report.</span></span> 

<span data-ttu-id="9b705-109">Une définition d'état est un composant d'état (ou bloc élémentaire) qui utilise une définition de ligne, de colonne et d'organigramme d'entreprise facultatif pour créer un état.</span><span class="sxs-lookup"><span data-stu-id="9b705-109">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="9b705-110">De plus, la définition de rapport comporte un grand nombre d'options et de paramètres pour personnaliser un rapport.</span><span class="sxs-lookup"><span data-stu-id="9b705-110">A report definition also provides options and settings that you can use to customize a report.</span></span> <span data-ttu-id="9b705-111">Après avoir défini des définitions de ligne et des définitions de colonne, vous devez les combiner dans une définition d'état.</span><span class="sxs-lookup"><span data-stu-id="9b705-111">After you define row definitions and column definitions, you must combine them in a report definition.</span></span> <span data-ttu-id="9b705-112">À ce stade, vous définissez également d'autres aspects des définitions, comme le niveau de détail et la date de l'état.</span><span class="sxs-lookup"><span data-stu-id="9b705-112">At this point, you also define other aspects of the definitions, such as the detail level and report date.</span></span> <span data-ttu-id="9b705-113">Vous pouvez ensuite enregistrer et générer l'état.</span><span class="sxs-lookup"><span data-stu-id="9b705-113">You can then save and generate a report.</span></span> <span data-ttu-id="9b705-114">Les états financiers offrent les niveaux de détail suivants :</span><span class="sxs-lookup"><span data-stu-id="9b705-114">Financial reporting offers the following levels of detail:</span></span>

- <span data-ttu-id="9b705-115">Financier</span><span class="sxs-lookup"><span data-stu-id="9b705-115">Financial</span></span>
- <span data-ttu-id="9b705-116">Financier et Compte</span><span class="sxs-lookup"><span data-stu-id="9b705-116">Financial and Account</span></span>
- <span data-ttu-id="9b705-117">Financier, Compte et Transaction</span><span class="sxs-lookup"><span data-stu-id="9b705-117">Financial, Account, and Transaction</span></span>

<span data-ttu-id="9b705-118">Toutefois, en fonction de la manière dont les données sont stockées dans le système Microsoft Dynamics ERP, il se peut que les détails de la transaction ne soient pas disponibles dans les rapports.</span><span class="sxs-lookup"><span data-stu-id="9b705-118">However, depending on how data is stored in the Microsoft Dynamics ERP system, transaction details might not be available in reports.</span></span>

## <a name="create-a-report-definition"></a><span data-ttu-id="9b705-119">Créer une définition d'état</span><span class="sxs-lookup"><span data-stu-id="9b705-119">Create a report definition</span></span>
1. <span data-ttu-id="9b705-120">Dans le générateur d'état, dans le menu **Fichier**, cliquez sur **Nouveau**, puis sélectionnez **Définition d'état**.</span><span class="sxs-lookup"><span data-stu-id="9b705-120">In Report Designer, on the **File** menu, click **New**, and then select **Report Definition**.</span></span>
2. <span data-ttu-id="9b705-121">Spécifiez les informations appropriées dans les onglets **État**, **Sortie et distribution**, **En-têtes et pieds de page** et **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="9b705-121">Specify the appropriate information on the **Report**, **Output and Distribution**, **Headers and Footers**, and **Settings** tabs.</span></span>

## <a name="contents-of-a-report-definition"></a><span data-ttu-id="9b705-122">Contenu d'une définition d'état</span><span class="sxs-lookup"><span data-stu-id="9b705-122">Contents of a report definition</span></span>
<span data-ttu-id="9b705-123">Le tableau suivant décrit les onglets dans une définition d'état, ainsi que la manière dont les informations sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="9b705-123">The following table describes the tabs in a report definition and how the information is used.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9b705-124">Onglet</span><span class="sxs-lookup"><span data-stu-id="9b705-124">Tab</span></span></th>
<th><span data-ttu-id="9b705-125">Description</span><span class="sxs-lookup"><span data-stu-id="9b705-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9b705-126">Etat</span><span class="sxs-lookup"><span data-stu-id="9b705-126">Report</span></span></td>
<td><span data-ttu-id="9b705-127">Créer un état, configurer un état, ou modifier un état existant.</span><span class="sxs-lookup"><span data-stu-id="9b705-127">Create a report, configure a report, or modify an existing report.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b705-128">Sortie et distribution</span><span class="sxs-lookup"><span data-stu-id="9b705-128">Output and Distribution</span></span></td>
<td><span data-ttu-id="9b705-129">Modifier le type de sortie et la destination de l'état.</span><span class="sxs-lookup"><span data-stu-id="9b705-129">Change the output type and destination of the report.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b705-130">En-têtes et pieds de page</span><span class="sxs-lookup"><span data-stu-id="9b705-130">Headers and Footers</span></span></td>
<td><span data-ttu-id="9b705-131">Définir et mettre en forme les en-têtes et les pieds de page de l'état.</span><span class="sxs-lookup"><span data-stu-id="9b705-131">Define and format the headers and footers for the report.</span></span> <span data-ttu-id="9b705-132">Par exemple, vous pouvez ajouter du texte ou des images à l'en-tête ou au pied de page.</span><span class="sxs-lookup"><span data-stu-id="9b705-132">For example, you can add text or images to the header or footer.</span></span> <span data-ttu-id="9b705-133">Les états financiers prennent en charge les fichiers image .bmp, .jpg, et .png.</span><span class="sxs-lookup"><span data-stu-id="9b705-133">Financial reporting supports .bmp, .jpg, and .png files for images.</span></span> <span data-ttu-id="9b705-134">Vous pouvez également ajouter des codes d'insertion automatique pour insérer d'autres informations, telles que le nom de la société, un nom d'état, ou un numéro de page.</span><span class="sxs-lookup"><span data-stu-id="9b705-134">You can also add autotext codes to insert other information, such as a company name, report name, or page number.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b705-135">Paramètres</span><span class="sxs-lookup"><span data-stu-id="9b705-135">Settings</span></span></td>
<td><span data-ttu-id="9b705-136">Spécifier des paramètres de définition d'état, tels que les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="9b705-136">Specify report definition settings, such as the following settings:</span></span>
<ul>
<li><span data-ttu-id="9b705-137">Mise en forme et arrondi des montants</span><span class="sxs-lookup"><span data-stu-id="9b705-137">Formatting and rounding amounts</span></span></li>
<li><span data-ttu-id="9b705-138">Mise en forme des états détaillés</span><span class="sxs-lookup"><span data-stu-id="9b705-138">Format detail reports</span></span></li>
<li><span data-ttu-id="9b705-139">Mise en forme des arborescences de génération d'états</span><span class="sxs-lookup"><span data-stu-id="9b705-139">Format reporting trees</span></span></li>
<li><span data-ttu-id="9b705-140">Générer un état sur les exceptions</span><span class="sxs-lookup"><span data-stu-id="9b705-140">Generate an exception report</span></span></li>
<li><span data-ttu-id="9b705-141">Spécifier la conversion de devises</span><span class="sxs-lookup"><span data-stu-id="9b705-141">Specify currency conversion</span></span></li>
<li><span data-ttu-id="9b705-142">Sous-total et filtrage des détails du compte</span><span class="sxs-lookup"><span data-stu-id="9b705-142">Subtotal and filter account details</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="9b705-143">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="9b705-143">Additional resources</span></span>

[<span data-ttu-id="9b705-144">États financiers</span><span class="sxs-lookup"><span data-stu-id="9b705-144">Financial reporting</span></span>](financial-reporting-intro.md)
