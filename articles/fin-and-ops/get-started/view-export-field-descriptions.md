---
title: Afficher et exporter les descriptions de champ
description: "Cet article décrit comment afficher les descriptions des champs et comment utiliser la page Descriptions de champ pour exporter des descriptions."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: d1ee87dbe9dab089a893d9c69d2573a4c4b11b58
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---

# <a name="view-and-export-field-descriptions"></a><span data-ttu-id="b11a6-103">Afficher et exporter les descriptions de champ</span><span class="sxs-lookup"><span data-stu-id="b11a6-103">View and export field descriptions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b11a6-104">Cet article décrit comment afficher les descriptions des champs et comment utiliser la page Descriptions de champ pour exporter des descriptions.</span><span class="sxs-lookup"><span data-stu-id="b11a6-104">This article describes how to view field descriptions and how to use the Field descriptions page to export descriptions.</span></span>

<span data-ttu-id="b11a6-105">Microsoft Dynamics 365 for Finance and Operations offre des descriptions pour les champs les plus complexes.</span><span class="sxs-lookup"><span data-stu-id="b11a6-105">Microsoft Dynamics 365 for Finance and Operations has descriptions for some of the more complex fields.</span></span> <span data-ttu-id="b11a6-106">Ces descriptions s’affichent lorsque vous survolez un champ.</span><span class="sxs-lookup"><span data-stu-id="b11a6-106">These descriptions appear when you hover over a field.</span></span> <span data-ttu-id="b11a6-107">Vous pouvez également afficher et exporter des descriptions sur la page **Descriptions de champ**.</span><span class="sxs-lookup"><span data-stu-id="b11a6-107">You can also view and export descriptions on the **Field descriptions** page.</span></span> 

<span data-ttu-id="b11a6-108">Toutes les pages n'ont pas des descriptions de champ.</span><span class="sxs-lookup"><span data-stu-id="b11a6-108">Not all pages have field descriptions.</span></span> <span data-ttu-id="b11a6-109">Nous souhaitons uniquement fournir des descriptions pour les champs plus complexes, et non ceux dont l'utilisation du champ est évidente.</span><span class="sxs-lookup"><span data-stu-id="b11a6-109">We want to provide descriptions only for the more complex fields, not where the use of the field is obvious.</span></span> <span data-ttu-id="b11a6-110">Par conséquent, certaines pages n’ont pas de descriptions de champ, certaines pages comportent quelques descriptions et certaines des pages plus complexes, comme la plupart des pages de paramètres, comportent de nombreuses descriptions.</span><span class="sxs-lookup"><span data-stu-id="b11a6-110">Therefore, some pages don't have any field descriptions, some pages have a few descriptions, and some of the more complex pages, such as many of the parameters pages, have many descriptions.</span></span> 

<span data-ttu-id="b11a6-111">Si vous avez accès à l'environnement de développement Finance and Operations, vous pouvez ajouter de nouvelles descriptions de champ et personnaliser les descriptions existantes.</span><span class="sxs-lookup"><span data-stu-id="b11a6-111">If you have access to the Finance and Operations development environment, you can add new field descriptions and customize existing descriptions.</span></span> <span data-ttu-id="b11a6-112">Par exemple, vous pouvez ajouter des informations spécifiques à la société dans une description de champ.</span><span class="sxs-lookup"><span data-stu-id="b11a6-112">For example, you can add company-specific information to a field description.</span></span> <span data-ttu-id="b11a6-113">Pour plus d'informations, voir [Personnaliser le champ d'aide](../../dev-itpro/user-interface/customize-field-help.md).</span><span class="sxs-lookup"><span data-stu-id="b11a6-113">For more information, see [Customize field help](../../dev-itpro/user-interface/customize-field-help.md).</span></span>

## <a name="see-field-descriptions-in-the-user-interface"></a><span data-ttu-id="b11a6-114">Voir les descriptions des champs dans l'interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="b11a6-114">See field descriptions in the user interface</span></span>
<span data-ttu-id="b11a6-115">Vous pouvez afficher les descriptions de champ en plaçant le curseur sur un champ.</span><span class="sxs-lookup"><span data-stu-id="b11a6-115">You can view field descriptions by hovering over a field.</span></span> <span data-ttu-id="b11a6-116">Si aucune description n’est disponible, vous voyez le nom du champ lorsque vous placez le pointeur sur le champ.</span><span class="sxs-lookup"><span data-stu-id="b11a6-116">If no description is available, you see the field name when you hover over the field.</span></span> <span data-ttu-id="b11a6-117">(Remarque : dans Dynamics AX 7.0 (février 2016), les descriptions des champs ne s'affichent que dans la page **Descriptions des champs**.) L'illustration suivante présente la description du champ qui s'affiche lorsque vous survolez le champ **Verrouiller les articles lors du comptage**.</span><span class="sxs-lookup"><span data-stu-id="b11a6-117">(Note: In Dynamics AX 7.0 (February 2016), field descriptions can be viewed only on the **Field descriptions** page.) The following illustration shows the field description that appears when you hover over the **Lock items during count** field.</span></span> 

<span data-ttu-id="b11a6-118">[![Exemple de description de champ](./media/field-description.png)](./media/field-description.png)</span><span class="sxs-lookup"><span data-stu-id="b11a6-118">[![Example of a field description](./media/field-description.png)](./media/field-description.png)</span></span>

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a><span data-ttu-id="b11a6-119">Utilisez la page Descriptions de champs pour afficher et exporter l'aide du champ</span><span class="sxs-lookup"><span data-stu-id="b11a6-119">Use the Field descriptions page to view and export field help</span></span>
<span data-ttu-id="b11a6-120">La page **Descriptions de champ** vous permet d'afficher et exporter des descriptions de champ.</span><span class="sxs-lookup"><span data-stu-id="b11a6-120">The **Field descriptions** page lets you view and export field descriptions.</span></span> <span data-ttu-id="b11a6-121">Vous pouvez afficher les descriptions disponibles pour une page à la fois.</span><span class="sxs-lookup"><span data-stu-id="b11a6-121">You can see the descriptions that are available for one page at a time.</span></span>

### <a name="view-the-descriptions-for-a-page"></a><span data-ttu-id="b11a6-122">Afficher les descriptions pour une page</span><span class="sxs-lookup"><span data-stu-id="b11a6-122">View the descriptions for a page</span></span>

<span data-ttu-id="b11a6-123">Pour afficher les descriptions pour une page, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b11a6-123">To view the descriptions for a page, follow this step.</span></span>

-   <span data-ttu-id="b11a6-124">Dans le champ **Sélectionner une page**, tapez le nom de la page.</span><span class="sxs-lookup"><span data-stu-id="b11a6-124">In the **Select a page** field, type the name of the page.</span></span> <span data-ttu-id="b11a6-125">Sinon, cliquez sur la flèche pour ouvrir une liste de toutes les pages, puis parcourez ou filtrer la liste.</span><span class="sxs-lookup"><span data-stu-id="b11a6-125">Alternatively, click the arrow to open a list of all the pages, and then browse or filter the list.</span></span>

<span data-ttu-id="b11a6-126">Vous pouvez utiliser le nom de la page qui s'affiche dans l'interface utilisateur (IU) (par exemple : **Clients**), ou le nom de code (nom AOA) disponible en cliquant avec le bouton droit sur la page (par exemple : **CustTable**).</span><span class="sxs-lookup"><span data-stu-id="b11a6-126">You can use either the name of the page that is shown in the user interface (UI) (for example, **Customers**) or the code name (AOT name) that's available when you right-click a page (for example, **CustTable**).</span></span> 

<span data-ttu-id="b11a6-127">Pour plus d’informations sur les différentes façons de filtrer la liste des pages, consultez la section « Recherche d’une page » plus loin dans cet article.</span><span class="sxs-lookup"><span data-stu-id="b11a6-127">For information about the various ways to filter the list of pages, see the "Searching for a page" section later in this article.</span></span> 

<span data-ttu-id="b11a6-128">Si vous définissez l'option **Inclure les champs sans description** sur **Oui**, tous les champs de la page s'afficheront, même s'ils n'ont pas de description du champ.</span><span class="sxs-lookup"><span data-stu-id="b11a6-128">If you set the **Include fields without a description** option to **Yes**, all the fields on the page are shown, even if they don't have a field description.</span></span>

### <a name="export-the-descriptions-for-a-page"></a><span data-ttu-id="b11a6-129">Exporter les descriptions pour une page</span><span class="sxs-lookup"><span data-stu-id="b11a6-129">Export the descriptions for a page</span></span>

<span data-ttu-id="b11a6-130">Pour exporter les descriptions pour une page, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b11a6-130">To export the descriptions for a page, follow these steps.</span></span>

1.  <span data-ttu-id="b11a6-131">Dans le champ **Sélectionner une page**, sélectionnez une page.</span><span class="sxs-lookup"><span data-stu-id="b11a6-131">In the **Select a page** field, select a page.</span></span>
2.  <span data-ttu-id="b11a6-132">Cliquez sur le bouton **Ouvrir dans Microsoft Office** dans le coin supérieur droit, puis cliquez sur **FieldDescriptionTmp**.</span><span class="sxs-lookup"><span data-stu-id="b11a6-132">Click the **Open in Microsoft Office** button in the upper-right corner, and then click **FieldDescriptionTmp**.</span></span>

### <a name="searching-for-a-page"></a><span data-ttu-id="b11a6-133">Rechercher une page</span><span class="sxs-lookup"><span data-stu-id="b11a6-133">Searching for a page</span></span>

<span data-ttu-id="b11a6-134">Il existe plusieurs manières de rechercher une page dans le champ **Sélectionner une page**.</span><span class="sxs-lookup"><span data-stu-id="b11a6-134">There are several ways to search for a page in the **Select a page** field.</span></span> <span data-ttu-id="b11a6-135">Dans de nombreux cas, vous devrez cliquer sur la flèche dans le champ **Sélectionner une page** pour ouvrir le menu déroulant et sélectionner une page dans une liste de pages filtrées.</span><span class="sxs-lookup"><span data-stu-id="b11a6-135">In many cases, you must click the arrow in the **Select a page** field to open the drop-down list, and then select from a filtered list of pages.</span></span>

-   <span data-ttu-id="b11a6-136">Entrez une partie du nom, puis ouvrez la liste déroulante pour sélectionner la page dans une liste de pages filtrées.</span><span class="sxs-lookup"><span data-stu-id="b11a6-136">Type part of the name, and then open the drop-down list to select from a filtered list of pages.</span></span>
-   <span data-ttu-id="b11a6-137">Ouvrez la liste déroulante puis cliquez sur l'en-tête **Nom de la page** en haut de la liste, ou sur l'en-tête **Nom de page AOA**.</span><span class="sxs-lookup"><span data-stu-id="b11a6-137">Open the drop-down list, and then click either the **Page name** heading at the top of the list or the **Page AOT name** heading.</span></span> <span data-ttu-id="b11a6-138">Une boîte de dialogue s'affiche où vous pouvez utiliser les options de filtrage avancé, telles que **Nom de page commençant par**.</span><span class="sxs-lookup"><span data-stu-id="b11a6-138">A dialog box appears, where you can use advanced filtering options, such as **Page name begins with**.</span></span>
-   <span data-ttu-id="b11a6-139">Entrez le nom complet de la page.</span><span class="sxs-lookup"><span data-stu-id="b11a6-139">Type the full name of the page.</span></span> <span data-ttu-id="b11a6-140">Lorsque vous utilisez cette option, il est recommandé d'ouvrir la liste déroulante et de consulter les autres options de la liste, même si les descriptions de champ sont affichées.</span><span class="sxs-lookup"><span data-stu-id="b11a6-140">When you use this option, it's best to open the drop-down list and see what else is in the list, even if field descriptions are shown.</span></span>
    -   <span data-ttu-id="b11a6-141">S'il n'y a qu'une seule correspondance exacte pour le nom, les descriptions de champ de cette page s'affichent.</span><span class="sxs-lookup"><span data-stu-id="b11a6-141">If there is a single exact match to the name, the field descriptions for that page are shown.</span></span>
    -   <span data-ttu-id="b11a6-142">S’il existe plus d’une correspondance exacte, aucune description n’est affichées.</span><span class="sxs-lookup"><span data-stu-id="b11a6-142">If there is more than one exact match, no descriptions are shown.</span></span> <span data-ttu-id="b11a6-143">Vous devez ouvrir la liste déroulante et sélectionner la page que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="b11a6-143">You must open the drop-down list and select the page that you want.</span></span>
    -   <span data-ttu-id="b11a6-144">Si le nom que vous avez tapé est la partie du nom d’une autre page, vous voyez les descriptions de votre page.</span><span class="sxs-lookup"><span data-stu-id="b11a6-144">If the name that you typed is part of the name of another page, you see the descriptions for your page.</span></span> <span data-ttu-id="b11a6-145">Cependant, si vous ouvrez la liste déroulante, vous voyez des pages supplémentaires qui contiennent ce nom.</span><span class="sxs-lookup"><span data-stu-id="b11a6-145">However, if you open the drop-down list, you see additional pages that contain that name.</span></span>

<span data-ttu-id="b11a6-146">Par exemple, aucune description n’est affichée lorsque vous tapez <strong>Comptage</strong> dans le champ *<strong><em>Sélectionner une page</em></strong>*.</span><span class="sxs-lookup"><span data-stu-id="b11a6-146">For example, no descriptions are shown when you type <strong>Counting</strong> in the *<strong><em>Select a page</em></strong>* field.</span></span> <span data-ttu-id="b11a6-147">Vous ouvrez la liste déroulante et vous voyez qu'il existe deux pages avec le nom <strong>Comptage</strong>, ainsi que plusieurs pages qui contiennent le mot « Comptage » dans leur nom.</span><span class="sxs-lookup"><span data-stu-id="b11a6-147">You open the drop-down list, and see that there are two pages that have the name <strong>Counting</strong> and several pages that contain the word "Counting" in the name.</span></span> <span data-ttu-id="b11a6-148">Si vous choisissez la page qui a le nom AOA <strong>InventJournalCount</strong> », des descriptions de champ s'affichent pour cette page.</span><span class="sxs-lookup"><span data-stu-id="b11a6-148">If you select the page that has the AOT name <strong>InventJournalCount</strong>, the field descriptions are shown for that page.</span></span> <span data-ttu-id="b11a6-149">Toutefois, si vous ouvrez de nouveau la liste déroulante, vous verrez que la liste contient désormais toutes les pages dont le nom de page AOA contient « InventJournalCount ».</span><span class="sxs-lookup"><span data-stu-id="b11a6-149">However, if you open the drop-down list again, you will see that the list now contains all pages that have "InventJournalCount" as part of their AOT name.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b11a6-150">Dépannage</span><span class="sxs-lookup"><span data-stu-id="b11a6-150">Troubleshooting</span></span>
<span data-ttu-id="b11a6-151">Cette section fournit des informations pour vous aider à résoudre les problèmes que vous pouvez rencontrer lorsque vous utilisez les descriptions de champ.</span><span class="sxs-lookup"><span data-stu-id="b11a6-151">This section provides information to help you troubleshoot issues that you might encounter when you use field descriptions.</span></span>

### <a name="i-cant-find-a-field-description"></a><span data-ttu-id="b11a6-152">Je ne trouve pas de description du champ</span><span class="sxs-lookup"><span data-stu-id="b11a6-152">I can't find a field description</span></span>

<span data-ttu-id="b11a6-153">Nous en sommes en train d'ajouter des descriptions pour les champs plus complexes.</span><span class="sxs-lookup"><span data-stu-id="b11a6-153">We’re in the process of adding descriptions for the more complex fields.</span></span> <span data-ttu-id="b11a6-154">Si vous avez besoin d'aide pour un champ spécifique, merci de nous le faire savoir en ajoutant un commentaire à cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="b11a6-154">If you require help for a particular field, let us know by adding a comment for this topic.</span></span>

### <a name="the-field-description-isnt-helpful"></a><span data-ttu-id="b11a6-155">La description du champ n'est pas utile</span><span class="sxs-lookup"><span data-stu-id="b11a6-155">The field description isn't helpful</span></span>

<span data-ttu-id="b11a6-156">Merci de nous le faire savoir en ajoutant un commentaire à cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="b11a6-156">Let us know by adding a comment for this topic.</span></span> <span data-ttu-id="b11a6-157">Si vous le pouvez, décrivez les informations supplémentaires dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="b11a6-157">If you can, describe the additional information that you require.</span></span>

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a><span data-ttu-id="b11a6-158">Impossible de trouver un champ sur la page Descriptions de champ</span><span class="sxs-lookup"><span data-stu-id="b11a6-158">I can't find a field on the Field descriptions page</span></span>

<span data-ttu-id="b11a6-159">Pour afficher tous les champs d'une page, définissez l'option **Inclure les champs sans description** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b11a6-159">To show all the fields on a page, set the **Include fields without a description** option to **Yes**.</span></span> <span data-ttu-id="b11a6-160">Cliquez sur le champ **Sélectionner une page** pour vérifier que vous avez sélectionné la bonne page.</span><span class="sxs-lookup"><span data-stu-id="b11a6-160">Click the **Select a page** field to verify that you've selected the correct page.</span></span> <span data-ttu-id="b11a6-161">Si le nom que vous avez tapé fait partie d’un autre nom de champ, vous avez peut-être sélectionné la page qui porte le nom plus long.</span><span class="sxs-lookup"><span data-stu-id="b11a6-161">If the name that you typed is part of another field name, you might have selected the page that has the longer name.</span></span>

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a><span data-ttu-id="b11a6-162">Impossible de trouver une page sur la page Descriptions de champ</span><span class="sxs-lookup"><span data-stu-id="b11a6-162">I can't find a page on the Field descriptions page</span></span>

<span data-ttu-id="b11a6-163">Pour plus d’informations sur les différentes façons de trouver une page, consultez la section « Recherche de pages » plus tôt dans cet article.</span><span class="sxs-lookup"><span data-stu-id="b11a6-163">For information about the various way to find pages, see the "Searching for pages" section earlier in this article.</span></span> <span data-ttu-id="b11a6-164">Si vous avez tapé le nom exact de la page, il est possible que les descriptions de champ ne s'affichent pas s'il existe plusieurs pages avec le même nom.</span><span class="sxs-lookup"><span data-stu-id="b11a6-164">If you've typed the exact name of the page, the field descriptions might not be shown if more than one page has the same name.</span></span> <span data-ttu-id="b11a6-165">Cliquez sur la flèche dans le champ **Sélectionner une page** pour ouvrir une liste filtrée des pages disponibles.</span><span class="sxs-lookup"><span data-stu-id="b11a6-165">Click the arrow in the **Select a page** field to open a filtered list of the pages that are available.</span></span>

<a name="additional-resources"></a><span data-ttu-id="b11a6-166">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b11a6-166">Additional resources</span></span>
--------

[<span data-ttu-id="b11a6-167">Personnaliser l'aide du champ</span><span class="sxs-lookup"><span data-stu-id="b11a6-167">Customize field help</span></span>](../../dev-itpro/user-interface/customize-field-help.md)





