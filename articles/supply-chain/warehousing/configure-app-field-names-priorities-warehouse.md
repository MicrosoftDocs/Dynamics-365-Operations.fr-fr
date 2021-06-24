---
title: Configurer les champs pour l’application mobile Gestion des entrepôts
description: Cette rubrique décrit comment définir et configurer les noms et les priorités de champ présentés dans l’application mobile Gestion des entrepôts.
author: MarkusFogelberg
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: bc224d3fd6cf5b111f61066202090f10ba4a7e8a
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189248"
---
# <a name="configure-fields-for-the-warehouse-management-mobile-app"></a><span data-ttu-id="6484a-103">Configurer les champs pour l’application mobile Gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="6484a-103">Configure fields for the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6484a-104">Cette rubrique décrit comment définir et configurer les noms et les priorités de champ présentés dans l’application mobile Gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="6484a-104">This topic describes how to define and configure names and priorities of fields shown in the Warehouse Management mobile app.</span></span>

> [!NOTE]
> <span data-ttu-id="6484a-105">Cette rubrique s’applique aux fonctionnalités du module Gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="6484a-105">This topic applies to features in Warehouse management.</span></span> <span data-ttu-id="6484a-106">Elle ne s’applique pas aux fonctionnalités du module Gestion des stocks.</span><span class="sxs-lookup"><span data-stu-id="6484a-106">It doesn’t apply to features in Inventory management.</span></span> <span data-ttu-id="6484a-107">L’application mobile Gestion des entrepôts est une application que vous pouvez utiliser pour effectuer des tâches d’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="6484a-107">The Warehouse Management mobile app is an application that you can use to perform warehouse tasks.</span></span> <span data-ttu-id="6484a-108">Vous pouvez définir et configurer les noms de champ utilisés dans l’application, et aussi configurer la priorité d’affectation des noms de champ.</span><span class="sxs-lookup"><span data-stu-id="6484a-108">You can define and configure the field names that are used in the app, as well as configure the priority to which the field names should be assigned.</span></span> <span data-ttu-id="6484a-109">Cette rubrique explique comment définir et configurer ces noms et priorités de champ de l’application mobile Gestion des entrepôts, et comment les utiliser.</span><span class="sxs-lookup"><span data-stu-id="6484a-109">This topic explains how to define and configure these Warehouse Management mobile app field names and priorities, and how they are used.</span></span>

## <a name="configure-warehouse-app-field-names"></a><span data-ttu-id="6484a-110">Configurer les noms de champ d’application d’entrepôt</span><span class="sxs-lookup"><span data-stu-id="6484a-110">Configure warehouse app field names</span></span>

<span data-ttu-id="6484a-111">Lorsque vous utilisez Entreposage sur votre appareil mobile, vous pouvez configurer l’affichage des métadonnées sur votre appareil dans la page **Noms de champ d’application d’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="6484a-111">When you use Warehousing on your mobile device, you can configure how metadata should be displayed on your device on the **Warehouse app field names** page.</span></span> <span data-ttu-id="6484a-112">Dans une nouvelle société, sélectionnez **Créer un paramétrage par défaut** pour générer tous les noms de champ qui seront utilisés dans les workflows d’appareil mobile d’entrepôt, puis affectez-leur un mode et un type de saisie favoris.</span><span class="sxs-lookup"><span data-stu-id="6484a-112">In a new company, select **Create default setup** to generate all field names that will be used in the warehouse mobile device workflows, and then assign a preferred input mode and input type to them.</span></span> <span data-ttu-id="6484a-113">Après avoir généré tous les noms de champ, vous pouvez sélectionner les options de saisie suivantes.</span><span class="sxs-lookup"><span data-stu-id="6484a-113">After you have generated all field names, you can select the following input options.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6484a-114">Option</span><span class="sxs-lookup"><span data-stu-id="6484a-114">Option</span></span></th>
<th><span data-ttu-id="6484a-115">description ;</span><span class="sxs-lookup"><span data-stu-id="6484a-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6484a-116">Mode de saisie favori</span><span class="sxs-lookup"><span data-stu-id="6484a-116">Preferred input mode</span></span></td>
<td><span data-ttu-id="6484a-117">Cette option définit si un champ de lecture ou un champ de saisie manuelle doit être affiché pour le nom de champ sélectionné.</span><span class="sxs-lookup"><span data-stu-id="6484a-117">This option defines whether a scanning field or a manual entry input field should be shown for the selected field name.</span></span> <span data-ttu-id="6484a-118">Cela est utile pour distinguer les champs selon que des codes-barres sont utilisés pour le champ.</span><span class="sxs-lookup"><span data-stu-id="6484a-118">This is useful to distinguish fields depending on if barcodes are used for the field.</span></span> <span data-ttu-id="6484a-119"><strong>Remarque :</strong> pour les noms de champ dont le mode de saisie favori est défini sur <strong>Lecture</strong>, vous pouvez entrer les informations manuellement si le code-barres est illisible ou endommagé.</span><span class="sxs-lookup"><span data-stu-id="6484a-119"><strong>Note:</strong> For field names with preferred input mode set to <strong>Scanning</strong>, you can enter information manually if the barcode is unreadable or damaged.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6484a-120">Type de saisie</span><span class="sxs-lookup"><span data-stu-id="6484a-120">Input type</span></span></td>
<td><span data-ttu-id="6484a-121">Cette option définit le type de saisie à utiliser pour le nom de champ sélectionné.</span><span class="sxs-lookup"><span data-stu-id="6484a-121">This option defines what input type should be used for the selected field name.</span></span> <span data-ttu-id="6484a-122">Quatre options sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="6484a-122">Four options are available:</span></span>
<ul>
<li><span data-ttu-id="6484a-123"><strong>Sélection</strong> - Contient une liste d’options parmi lesquelles choisir.</span><span class="sxs-lookup"><span data-stu-id="6484a-123"><strong>Selection</strong> - Contains a list of options to choose from.</span></span> <span data-ttu-id="6484a-124">Les noms de champ avec cette option ne sont pas modifiables.</span><span class="sxs-lookup"><span data-stu-id="6484a-124">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="6484a-125"><strong>Date</strong> - Les noms de champs spécifiés comme date affichent un format de date avec l’étiquette.</span><span class="sxs-lookup"><span data-stu-id="6484a-125"><strong>Date</strong> - Field names specified as date will show a date format with the label.</span></span> <span data-ttu-id="6484a-126">Cela permet aux magasiniers de déterminer le format de saisie de la date.</span><span class="sxs-lookup"><span data-stu-id="6484a-126">This helps warehouse workers see in which format to enter the date.</span></span> <span data-ttu-id="6484a-127">Les noms de champ avec cette option ne sont pas modifiables.</span><span class="sxs-lookup"><span data-stu-id="6484a-127">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="6484a-128"><strong>Alpha</strong> - Si cette option est sélectionnée, le clavier du périphérique est utilisé lors de la saisie manuelle d’informations dans l’application.</span><span class="sxs-lookup"><span data-stu-id="6484a-128"><strong>Alpha</strong> - If selected, the device keyboard will be used when entering information manually in the app.</span></span> <span data-ttu-id="6484a-129">L’expérience au clavier peut être modifiée selon le périphérique utilisé.</span><span class="sxs-lookup"><span data-stu-id="6484a-129">The keyboard experience can be changed depending on which device is used.</span></span></li>
<li><span data-ttu-id="6484a-130"><strong>Numérique</strong> - Pour les noms de champ qui utilisent la saisie numérique uniquement, vous pouvez sélectionner cette option pour afficher un pavé numérique personnalisé avec le champ de saisie au lieu du clavier du périphérique.</span><span class="sxs-lookup"><span data-stu-id="6484a-130"><strong>Numeric</strong> - For field names that use numeric input only, you can select this option to display a custom numeric keypad with the input field instead of the device keyboard.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a><span data-ttu-id="6484a-131">Configurer la priorité du champ d’application d’entrepôt</span><span class="sxs-lookup"><span data-stu-id="6484a-131">Configure warehouse app field priority</span></span>

<span data-ttu-id="6484a-132">Sur la page **Priorité du champ d’application d’entrepôt**, vous pouvez classer les noms de champ dans différents groupes de priorité.</span><span class="sxs-lookup"><span data-stu-id="6484a-132">On the **Warehouse app field priority** page, you can put field names into different priority groups.</span></span> <span data-ttu-id="6484a-133">Cela permet de déterminer quelles informations doivent être affichées sur la page de tâches principale lorsque les magasiniers effectuent des tâches via l’application.</span><span class="sxs-lookup"><span data-stu-id="6484a-133">This makes it possible to decide what information should be displayed on the main task page when warehouse workers perform tasks using the app.</span></span> <span data-ttu-id="6484a-134">Si vous cliquez sur **Créer un paramétrage par défaut**, un ensemble de groupes de priorité par défaut est généré.</span><span class="sxs-lookup"><span data-stu-id="6484a-134">If you click **Create default setup**, a default set of priority groups will be generated.</span></span> <span data-ttu-id="6484a-135">Vous pouvez créer autant de groupes de priorité que nécessaire, mais seuls trois groupes de priorité seront affichés sur la page de tâches.</span><span class="sxs-lookup"><span data-stu-id="6484a-135">It is possible to create as many priority groups as needed, but only three priority groups will be shown on the task page.</span></span> <span data-ttu-id="6484a-136">Lorsque le système envoie des métadonnées à l’application, il affecte à chaque champ une priorité relative selon son groupe de priorité, et l’application affiche les trois premiers groupes de priorité contenus dans les métadonnées de la page de tâches.</span><span class="sxs-lookup"><span data-stu-id="6484a-136">When the system sends metadata to the app, it will assign each field a relative priority depending on its priority group, and the app will display the first three priority groups contained in the metadata on the task page.</span></span> <span data-ttu-id="6484a-137">Les métadonnées restantes seront affichées sur une page de détails secondaire.</span><span class="sxs-lookup"><span data-stu-id="6484a-137">The rest of the overflowing metadata will be displayed on a secondary details page.</span></span> <span data-ttu-id="6484a-138">Le tableau ci-dessous présente un exemple de cinq groupes de priorité.</span><span class="sxs-lookup"><span data-stu-id="6484a-138">The following table shows an example of five priority groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6484a-139">Groupe de priorité</span><span class="sxs-lookup"><span data-stu-id="6484a-139">Priority group</span></span></th>
<th><span data-ttu-id="6484a-140">Champs affectés</span><span class="sxs-lookup"><span data-stu-id="6484a-140">Assigned fields</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> <span data-ttu-id="6484a-141">Priorité 10</span><span class="sxs-lookup"><span data-stu-id="6484a-141">Priority 10</span></span></td>
<td><ul>
<li><span data-ttu-id="6484a-142">Article</span><span class="sxs-lookup"><span data-stu-id="6484a-142">Item</span></span></li>
<li><span data-ttu-id="6484a-143">Quantité</span><span class="sxs-lookup"><span data-stu-id="6484a-143">Quantity</span></span></li>
<li><span data-ttu-id="6484a-144">Unité de mesure</span><span class="sxs-lookup"><span data-stu-id="6484a-144">Unit of measure</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="6484a-145">Priorité 20</span><span class="sxs-lookup"><span data-stu-id="6484a-145">Priority 20</span></span></td>
<td><ul>
<li><span data-ttu-id="6484a-146">Poste de groupement</span><span class="sxs-lookup"><span data-stu-id="6484a-146">Cluster position</span></span></li>
<li><span data-ttu-id="6484a-147">Groupement</span><span class="sxs-lookup"><span data-stu-id="6484a-147">Cluster</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="6484a-148">Priorité 30</span><span class="sxs-lookup"><span data-stu-id="6484a-148">Priority 30</span></span></td>
<td><ul>
<li><span data-ttu-id="6484a-149">Description de l’article</span><span class="sxs-lookup"><span data-stu-id="6484a-149">Item description</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="6484a-150">Priorité 40</span><span class="sxs-lookup"><span data-stu-id="6484a-150">Priority 40</span></span></td>
<td><ul>
<li><span data-ttu-id="6484a-151">Configuration</span><span class="sxs-lookup"><span data-stu-id="6484a-151">Configuration</span></span></li>
<li><span data-ttu-id="6484a-152">Couleur</span><span class="sxs-lookup"><span data-stu-id="6484a-152">Color</span></span></li>
<li><span data-ttu-id="6484a-153">Taille</span><span class="sxs-lookup"><span data-stu-id="6484a-153">Size</span></span></li>
<li><span data-ttu-id="6484a-154">Style</span><span class="sxs-lookup"><span data-stu-id="6484a-154">Style</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="6484a-155">Priorité 50</span><span class="sxs-lookup"><span data-stu-id="6484a-155">Priority 50</span></span></td>
<td><ul>
<li><span data-ttu-id="6484a-156">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="6484a-156">Location</span></span></li>
<li><span data-ttu-id="6484a-157">Contenant</span><span class="sxs-lookup"><span data-stu-id="6484a-157">License plate</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6484a-158">Par exemple, lorsqu’un magasinier effectue une tâche sur un appareil mobile, si les métadonnées qui seront affichées dans l’application comprennent les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="6484a-158">For example, when a warehouse worker is performing a task on a mobile device, if the metadata that will be displayed in the app consists of the following fields:</span></span>

-   <span data-ttu-id="6484a-159">Article</span><span class="sxs-lookup"><span data-stu-id="6484a-159">Item</span></span>
-   <span data-ttu-id="6484a-160">Quantité</span><span class="sxs-lookup"><span data-stu-id="6484a-160">Quantity</span></span>
-   <span data-ttu-id="6484a-161">Unité de mesure</span><span class="sxs-lookup"><span data-stu-id="6484a-161">Unit of measure</span></span>
-   <span data-ttu-id="6484a-162">Description de l’article</span><span class="sxs-lookup"><span data-stu-id="6484a-162">Item description</span></span>
-   <span data-ttu-id="6484a-163">Taille et emplacement</span><span class="sxs-lookup"><span data-stu-id="6484a-163">Size and Location</span></span>

<span data-ttu-id="6484a-164">Selon la priorité du champ d’application d’entrepôt paramétrée dans le tableau ci-dessus, les 3 lignes d’informations ci-après seront affichées sur la page de tâches :</span><span class="sxs-lookup"><span data-stu-id="6484a-164">Based on the warehouse app field priority set up in the table above, the following 3 rows of information will be displayed on the task page:</span></span>

-   <span data-ttu-id="6484a-165">Ligne 1 : Article, Quantité, Unité de mesure</span><span class="sxs-lookup"><span data-stu-id="6484a-165">Row 1: Item, Quantity, Unit of measure</span></span>
-   <span data-ttu-id="6484a-166">Ligne 2 : Description de l’article</span><span class="sxs-lookup"><span data-stu-id="6484a-166">Row 2: Item description</span></span>
-   <span data-ttu-id="6484a-167">Ligne 3 : Taille</span><span class="sxs-lookup"><span data-stu-id="6484a-167">Row 3: Size</span></span>

<span data-ttu-id="6484a-168">Les métadonnées restantes, par exemple, Emplacement, ne seront pas affichées sur la page de tâches, mais sur une page de détails.</span><span class="sxs-lookup"><span data-stu-id="6484a-168">The remaining metadata, for example, Location, will not be displayed on the task page, but will be displayed on a details page.</span></span> <span data-ttu-id="6484a-169">Pour en savoir plus et pour consulter des exemples de l’interface utilisateur, reportez-vous à la publication de blog [Annonce de Finance and Operations - Entreposage](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span><span class="sxs-lookup"><span data-stu-id="6484a-169">To learn more and see examples of the user interface, refer to the blog post [Announcing Finance and Operations - Warehousing](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6484a-170">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6484a-170">Additional resources</span></span>

[<span data-ttu-id="6484a-171">Installer et connecter l’application mobile Gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="6484a-171">Install and connect the Warehouse Management mobile app</span></span>](../warehousing/install-configure-warehouse-management-app.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]