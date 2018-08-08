---
title: Configurer les noms de champ d'application dans l'application Entreposage
description: "Cette rubrique décrit comment définir et configurer les noms et les priorités de champ d'application d'entrepôt dans Finance and Operations."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 0162014189ed6bffb17e6718a67eecfd55c334a5
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---

# <a name="configure-app-field-names-in-warehousing-app"></a><span data-ttu-id="00ff1-103">Configurer les noms de champ d'application dans l'application Entreposage</span><span class="sxs-lookup"><span data-stu-id="00ff1-103">Configure app field names in Warehousing app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="00ff1-104">Cette rubrique décrit comment définir et configurer les noms et les priorités de champ d'application d'entrepôt dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="00ff1-104">This topic describes how to define and configure warehouse app field names and priorities in Finance and Operations.</span></span> 

<span data-ttu-id="00ff1-105">**Remarque :** cette rubrique s'applique aux fonctionnalités du module Gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="00ff1-105">**Note:** This topic applies to features in Warehouse management.</span></span> <span data-ttu-id="00ff1-106">Elle ne s'applique pas aux fonctionnalités du module Gestion des stocks.</span><span class="sxs-lookup"><span data-stu-id="00ff1-106">It doesn’t apply to features in Inventory management.</span></span> <span data-ttu-id="00ff1-107">Finance and Operations - Entreposage est une application que vous pouvez utiliser pour effectuer des tâches d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="00ff1-107">Finance and Operations - Warehousing is an application that you can use to perform warehouse tasks.</span></span> <span data-ttu-id="00ff1-108">Vous pouvez définir et configurer les noms de champ utilisés dans l'application, et aussi configurer la priorité d'affectation des noms de champ.</span><span class="sxs-lookup"><span data-stu-id="00ff1-108">You can define and configure the field names that are used in the app, as well as configure the priority to which the field names should be assigned.</span></span> <span data-ttu-id="00ff1-109">Cette rubrique explique comment définir et configurer ces noms et priorités de champ d'application d'entrepôt, et comment les utiliser dans Finance and Operations - Entreposage.</span><span class="sxs-lookup"><span data-stu-id="00ff1-109">This topic explains how to define and configure these warehouse app field names and priorities, and how they are used in Finance and Operations - Warehousing.</span></span> <span data-ttu-id="00ff1-110">Pour des informations détaillées sur la configuration de la connexion à Finance and Operations - Entreposage, reportez-vous au didacticiel [Installation et configuration de Finance and Operations - Entreposage](install-configure-warehousing-app.md)</span><span class="sxs-lookup"><span data-stu-id="00ff1-110">For detailed information about how to configure the connection to Finance and Operations  - Warehousing, refer to the tutorial [Install and configure Finance and Operations - Warehousing](install-configure-warehousing-app.md).</span></span>

## <a name="configure-warehouse-app-field-names"></a><span data-ttu-id="00ff1-111">Configurer les noms de champ d'application d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="00ff1-111">Configure warehouse app field names</span></span>

<span data-ttu-id="00ff1-112">Lorsque vous utilisez Finance and Operations - Entreposage sur votre appareil mobile, vous pouvez configurer l'affichage des métadonnées sur votre appareil dans la page **Noms de champ d'application d'entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="00ff1-112">When you use Finance and Operations - Warehousing on your mobile device, you can configure how metadata should be displayed on your device on the **Warehouse app field names** page.</span></span> <span data-ttu-id="00ff1-113">Dans une nouvelle société de Finance and Operations, sélectionnez **Créer un paramétrage par défaut** pour générer tous les noms de champ qui seront utilisés dans les workflows d'appareil mobile d'entrepôt, puis affectez-leur un mode et un type de saisie favoris.</span><span class="sxs-lookup"><span data-stu-id="00ff1-113">In a new company in Finance and Operations, select **Create default setup** to generate all field names that will be used in the warehouse mobile device workflows, and then assign a preferred input mode and input type to them.</span></span> <span data-ttu-id="00ff1-114">Après avoir généré tous les noms de champ, vous pouvez sélectionner les options de saisie suivantes.</span><span class="sxs-lookup"><span data-stu-id="00ff1-114">After you have generated all field names, you can select the following input options.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00ff1-115">Option</span><span class="sxs-lookup"><span data-stu-id="00ff1-115">Option</span></span></th>
<th><span data-ttu-id="00ff1-116">description ;</span><span class="sxs-lookup"><span data-stu-id="00ff1-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="00ff1-117">Mode de saisie favori</span><span class="sxs-lookup"><span data-stu-id="00ff1-117">Preferred input mode</span></span></td>
<td><span data-ttu-id="00ff1-118">Cette option définit si un champ de lecture ou un champ de saisie manuelle doit être affiché pour le nom de champ sélectionné.</span><span class="sxs-lookup"><span data-stu-id="00ff1-118">This option defines whether a scanning field or a manual entry input field should be shown for the selected field name.</span></span> <span data-ttu-id="00ff1-119">Cela est utile pour distinguer les champs selon que des codes-barres sont utilisés pour le champ.</span><span class="sxs-lookup"><span data-stu-id="00ff1-119">This is useful to distinguish fields depending on if barcodes are used for the field.</span></span> <span data-ttu-id="00ff1-120"><strong>Remarque :</strong> pour les noms de champ dont le mode de saisie favori est défini sur <strong>Lecture</strong>, vous pouvez entrer les informations manuellement si le code-barres est illisible ou endommagé.</span><span class="sxs-lookup"><span data-stu-id="00ff1-120"><strong>Note:</strong> For field names with preferred input mode set to <strong>Scanning</strong>, you can enter information manually if the barcode is unreadable or damaged.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="00ff1-121">Type de saisie</span><span class="sxs-lookup"><span data-stu-id="00ff1-121">Input type</span></span></td>
<td><span data-ttu-id="00ff1-122">Cette option définit le type de saisie à utiliser pour le nom de champ sélectionné.</span><span class="sxs-lookup"><span data-stu-id="00ff1-122">This option defines what input type should be used for the selected field name.</span></span> <span data-ttu-id="00ff1-123">Quatre options sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="00ff1-123">Four options are available:</span></span>
<ul>
<li><span data-ttu-id="00ff1-124"><strong>Sélection</strong> - Contient une liste d'options parmi lesquelles choisir.</span><span class="sxs-lookup"><span data-stu-id="00ff1-124"><strong>Selection</strong> - Contains a list of options to choose from.</span></span> <span data-ttu-id="00ff1-125">Les noms de champ avec cette option ne sont pas modifiables.</span><span class="sxs-lookup"><span data-stu-id="00ff1-125">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="00ff1-126"><strong>Date</strong> - Les noms de champs spécifiés comme date affichent un format de date avec l'étiquette.</span><span class="sxs-lookup"><span data-stu-id="00ff1-126"><strong>Date</strong> - Field names specified as date will show a date format with the label.</span></span> <span data-ttu-id="00ff1-127">Cela permet aux magasiniers de déterminer le format de saisie de la date.</span><span class="sxs-lookup"><span data-stu-id="00ff1-127">This helps warehouse workers see in which format to enter the date.</span></span> <span data-ttu-id="00ff1-128">Les noms de champ avec cette option ne sont pas modifiables.</span><span class="sxs-lookup"><span data-stu-id="00ff1-128">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="00ff1-129"><strong>Alpha</strong> - Si cette option est sélectionnée, le clavier du périphérique est utilisé lors de la saisie manuelle d'informations dans l'application.</span><span class="sxs-lookup"><span data-stu-id="00ff1-129"><strong>Alpha</strong> - If selected, the device keyboard will be used when entering information manually in the app.</span></span> <span data-ttu-id="00ff1-130">L'expérience au clavier peut être modifiée selon le périphérique utilisé.</span><span class="sxs-lookup"><span data-stu-id="00ff1-130">The keyboard experience can be changed depending on which device is used.</span></span></li>
<li><span data-ttu-id="00ff1-131"><strong>Numérique</strong> - Pour les noms de champ qui utilisent la saisie numérique uniquement, vous pouvez sélectionner cette option pour afficher un pavé numérique personnalisé avec le champ de saisie au lieu du clavier du périphérique.</span><span class="sxs-lookup"><span data-stu-id="00ff1-131"><strong>Numeric</strong> - For field names that use numeric input only, you can select this option to display a custom numeric keypad with the input field instead of the device keyboard.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a><span data-ttu-id="00ff1-132">Configurer la priorité du champ d'application d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="00ff1-132">Configure warehouse app field priority</span></span>

<span data-ttu-id="00ff1-133">Sur la page **Priorité du champ d'application d'entrepôt**, vous pouvez classer les noms de champ dans différents groupes de priorité.</span><span class="sxs-lookup"><span data-stu-id="00ff1-133">On the **Warehouse app field priority** page, you can put field names into different priority groups.</span></span> <span data-ttu-id="00ff1-134">Cela permet de déterminer quelles informations doivent être affichées sur la page de tâches principale lorsque les magasiniers effectuent des tâches via l'application.</span><span class="sxs-lookup"><span data-stu-id="00ff1-134">This makes it possible to decide what information should be displayed on the main task page when warehouse workers perform tasks using the app.</span></span> <span data-ttu-id="00ff1-135">Si vous cliquez sur **Créer un paramétrage par défaut**, un ensemble de groupes de priorité par défaut est généré.</span><span class="sxs-lookup"><span data-stu-id="00ff1-135">If you click **Create default setup**, a default set of priority groups will be generated.</span></span> <span data-ttu-id="00ff1-136">Vous pouvez créer autant de groupes de priorité que nécessaire, mais seuls trois groupes de priorité seront affichés sur la page de tâches.</span><span class="sxs-lookup"><span data-stu-id="00ff1-136">It is possible to create as many priority groups as needed, but only three priority groups will be shown on the task page.</span></span> <span data-ttu-id="00ff1-137">Lorsque Finance and Operations envoie des métadonnées à l'application, il affecte à chaque champ une priorité relative selon son groupe de priorité, et l'application affiche les trois premiers groupes de priorité contenus dans les métadonnées de la page de tâches.</span><span class="sxs-lookup"><span data-stu-id="00ff1-137">When Finance and Operations sends metadata to the app, it will assign each field a relative priority depending on its priority group, and the app will display the first three priority groups contained in the metadata on the task page.</span></span> <span data-ttu-id="00ff1-138">Les métadonnées restantes seront affichées sur une page de détails secondaire.</span><span class="sxs-lookup"><span data-stu-id="00ff1-138">The rest of the overflowing metadata will be displayed on a secondary details page.</span></span> <span data-ttu-id="00ff1-139">Le tableau ci-dessous présente un exemple de cinq groupes de priorité.</span><span class="sxs-lookup"><span data-stu-id="00ff1-139">The following table shows an example of five priority groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00ff1-140">Groupe de priorité</span><span class="sxs-lookup"><span data-stu-id="00ff1-140">Priority group</span></span></th>
<th><span data-ttu-id="00ff1-141">Champs affectés</span><span class="sxs-lookup"><span data-stu-id="00ff1-141">Assigned fields</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> <span data-ttu-id="00ff1-142">Priorité 10</span><span class="sxs-lookup"><span data-stu-id="00ff1-142">Priority 10</span></span></td>
<td><ul>
<li><span data-ttu-id="00ff1-143">Article</span><span class="sxs-lookup"><span data-stu-id="00ff1-143">Item</span></span></li>
<li><span data-ttu-id="00ff1-144">Quantité</span><span class="sxs-lookup"><span data-stu-id="00ff1-144">Quantity</span></span></li>
<li><span data-ttu-id="00ff1-145">Unité de mesure</span><span class="sxs-lookup"><span data-stu-id="00ff1-145">Unit of measure</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="00ff1-146">Priorité 20</span><span class="sxs-lookup"><span data-stu-id="00ff1-146">Priority 20</span></span></td>
<td><ul>
<li><span data-ttu-id="00ff1-147">Poste de groupement</span><span class="sxs-lookup"><span data-stu-id="00ff1-147">Cluster position</span></span></li>
<li><span data-ttu-id="00ff1-148">Groupement</span><span class="sxs-lookup"><span data-stu-id="00ff1-148">Cluster</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="00ff1-149">Priorité 30</span><span class="sxs-lookup"><span data-stu-id="00ff1-149">Priority 30</span></span></td>
<td><ul>
<li><span data-ttu-id="00ff1-150">Description de l'article</span><span class="sxs-lookup"><span data-stu-id="00ff1-150">Item description</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="00ff1-151">Priorité 40</span><span class="sxs-lookup"><span data-stu-id="00ff1-151">Priority 40</span></span></td>
<td><ul>
<li><span data-ttu-id="00ff1-152">Configuration</span><span class="sxs-lookup"><span data-stu-id="00ff1-152">Configuration</span></span></li>
<li><span data-ttu-id="00ff1-153">Couleur</span><span class="sxs-lookup"><span data-stu-id="00ff1-153">Color</span></span></li>
<li><span data-ttu-id="00ff1-154">Taille</span><span class="sxs-lookup"><span data-stu-id="00ff1-154">Size</span></span></li>
<li><span data-ttu-id="00ff1-155">Style</span><span class="sxs-lookup"><span data-stu-id="00ff1-155">Style</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="00ff1-156">Priorité 50</span><span class="sxs-lookup"><span data-stu-id="00ff1-156">Priority 50</span></span></td>
<td><ul>
<li><span data-ttu-id="00ff1-157">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="00ff1-157">Location</span></span></li>
<li><span data-ttu-id="00ff1-158">Contenant</span><span class="sxs-lookup"><span data-stu-id="00ff1-158">License plate</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="00ff1-159">Par exemple, lorsqu'un magasinier effectue une tâche sur un appareil mobile, si les métadonnées qui seront affichées dans l'application comprennent les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="00ff1-159">For example, when a warehouse worker is performing a task on a mobile device, if the metadata that will be displayed in the app consists of the following fields:</span></span>

-   <span data-ttu-id="00ff1-160">Article</span><span class="sxs-lookup"><span data-stu-id="00ff1-160">Item</span></span>
-   <span data-ttu-id="00ff1-161">Quantité</span><span class="sxs-lookup"><span data-stu-id="00ff1-161">Quantity</span></span>
-   <span data-ttu-id="00ff1-162">Unité de mesure</span><span class="sxs-lookup"><span data-stu-id="00ff1-162">Unit of measure</span></span>
-   <span data-ttu-id="00ff1-163">Description de l'article</span><span class="sxs-lookup"><span data-stu-id="00ff1-163">Item description</span></span>
-   <span data-ttu-id="00ff1-164">Taille et emplacement</span><span class="sxs-lookup"><span data-stu-id="00ff1-164">Size and Location</span></span>

<span data-ttu-id="00ff1-165">Selon la priorité du champ d'application d'entrepôt paramétrée dans le tableau ci-dessus, les 3 lignes d'informations ci-après seront affichées sur la page de tâches :</span><span class="sxs-lookup"><span data-stu-id="00ff1-165">Based on the warehouse app field priority set up in the table above, the following 3 rows of information will be displayed on the task page:</span></span>

-   <span data-ttu-id="00ff1-166">Ligne 1 : Article, Quantité, Unité de mesure</span><span class="sxs-lookup"><span data-stu-id="00ff1-166">Row 1: Item, Quantity, Unit of measure</span></span>
-   <span data-ttu-id="00ff1-167">Ligne 2 : Description de l'article</span><span class="sxs-lookup"><span data-stu-id="00ff1-167">Row 2: Item description</span></span>
-   <span data-ttu-id="00ff1-168">Ligne 3 : Taille</span><span class="sxs-lookup"><span data-stu-id="00ff1-168">Row 3: Size</span></span>

<span data-ttu-id="00ff1-169">Les métadonnées restantes, par exemple, Emplacement, ne seront pas affichées sur la page de tâches, mais sur une page de détails.</span><span class="sxs-lookup"><span data-stu-id="00ff1-169">The remaining metadata, for example, Location, will not be displayed on the task page, but will be displayed on a details page.</span></span> <span data-ttu-id="00ff1-170">Pour en savoir plus et pour consulter des exemples de l'interface utilisateur, reportez-vous à la publication de blog [Annonce de Finance and Operations - Entreposage](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span><span class="sxs-lookup"><span data-stu-id="00ff1-170">To learn more and see examples of the user interface, refer to the blog post [Announcing Finance and Operations - Warehousing](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span></span>

<a name="additional-resources"></a><span data-ttu-id="00ff1-171">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="00ff1-171">Additional resources</span></span>
--------

[<span data-ttu-id="00ff1-172">Installation et configuration de Microsoft Dynamics 365 for Finance and Operations – Entreposage</span><span class="sxs-lookup"><span data-stu-id="00ff1-172">Install and configure Microsoft Dynamics 365 for Finance and Operations – Warehousing</span></span>](install-configure-warehousing-app.md)




