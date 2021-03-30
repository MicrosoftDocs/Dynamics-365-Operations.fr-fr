---
title: Module d’accordéon
description: Cette rubrique couvre les modules accordéon et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: a08441f5dffa9c2c65b304d0265dd107a838a685
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206605"
---
# <a name="accordion-module"></a><span data-ttu-id="bbf62-103">Module Accordéon</span><span class="sxs-lookup"><span data-stu-id="bbf62-103">Accordion module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bbf62-104">Cette rubrique couvre les modules accordéon et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bbf62-104">This topic covers accordion modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="bbf62-105">Les modules accordéon sont des modules de type conteneur qui sont utilisés pour organiser les informations ou les modules d’une page en fournissant une fonctionnalité de réduction de type tiroir.</span><span class="sxs-lookup"><span data-stu-id="bbf62-105">Accordion modules are container-like modules that are used to organize the information or modules on a page by providing a collapsible drawer-like capability.</span></span> <span data-ttu-id="bbf62-106">Un module d’accordéon peut être utilisé sur n’importe quelle page.</span><span class="sxs-lookup"><span data-stu-id="bbf62-106">An accordion module can be used on any page.</span></span>

<span data-ttu-id="bbf62-107">À l’intérieur de chaque module d’accordéon, un ou plusieurs modules d’élément d’accordéon peuvent être ajoutés.</span><span class="sxs-lookup"><span data-stu-id="bbf62-107">Inside every accordion module, one or more accordion item modules can be added.</span></span> <span data-ttu-id="bbf62-108">Chaque module d’élément d’accordéon représente un tiroir réductible.</span><span class="sxs-lookup"><span data-stu-id="bbf62-108">Each accordion item module represents a collapsible drawer.</span></span> <span data-ttu-id="bbf62-109">À l’intérieur de chaque module d’élément d’accordéon, un ou plusieurs modules peuvent être ajoutés.</span><span class="sxs-lookup"><span data-stu-id="bbf62-109">Inside every accordion item module, one or more modules can be added.</span></span> <span data-ttu-id="bbf62-110">Il n’y a aucune restriction quant aux types de modules qui peuvent être ajoutés à un module d’élément d’accordéon.</span><span class="sxs-lookup"><span data-stu-id="bbf62-110">There are no restrictions on the types of modules that can be added to an accordion item module.</span></span>

<span data-ttu-id="bbf62-111">L’image suivante montre un exemple de module d’accordéon utilisé pour organiser les informations sur la page des questions fréquemment posées (FAQ) d’un magasin.</span><span class="sxs-lookup"><span data-stu-id="bbf62-111">The following image shows an example of an accordion module that is used to organize information on a store's frequently asked questions (FAQ) page.</span></span>

![Exemple d’un module d’accordéon](./media/ecommerce-accordion.PNG)

## <a name="accordion-module-properties"></a><span data-ttu-id="bbf62-113">Propriétés du module d’accordéon</span><span class="sxs-lookup"><span data-stu-id="bbf62-113">Accordion module properties</span></span>

| <span data-ttu-id="bbf62-114">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="bbf62-114">Property name</span></span> | <span data-ttu-id="bbf62-115">Valeurs</span><span class="sxs-lookup"><span data-stu-id="bbf62-115">Values</span></span> | <span data-ttu-id="bbf62-116">Description</span><span class="sxs-lookup"><span data-stu-id="bbf62-116">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="bbf62-117">En-tête</span><span class="sxs-lookup"><span data-stu-id="bbf62-117">Heading</span></span> | <span data-ttu-id="bbf62-118">Détails</span><span class="sxs-lookup"><span data-stu-id="bbf62-118">Text</span></span> | <span data-ttu-id="bbf62-119">Cette propriété spécifie un en-tête de texte facultatif pour le module d’accordéon.</span><span class="sxs-lookup"><span data-stu-id="bbf62-119">This property specifies an optional text heading for the accordion module.</span></span> |
| <span data-ttu-id="bbf62-120">Développer tout</span><span class="sxs-lookup"><span data-stu-id="bbf62-120">Expand All</span></span> | <span data-ttu-id="bbf62-121">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="bbf62-121">**True** or **False**</span></span> | <span data-ttu-id="bbf62-122">Si la valeur est définie sur **Vrai**, la fonctionnalité de développement/réduction est activée, de sorte que tous les éléments du module d’accordéon peuvent être développés et réduits.</span><span class="sxs-lookup"><span data-stu-id="bbf62-122">If the value is set to **True**, expand/collapse functionality is turned on, so that all items in the accordion module can be expanded and collapsed.</span></span> |
| <span data-ttu-id="bbf62-123">Style d’interaction</span><span class="sxs-lookup"><span data-stu-id="bbf62-123">Interaction Style</span></span> | <span data-ttu-id="bbf62-124">**Indépendant** ou **Développer un seul élément**</span><span class="sxs-lookup"><span data-stu-id="bbf62-124">**Independent** or **Expand one item only**</span></span> | <span data-ttu-id="bbf62-125">Cette propriété définit le style d’interaction des éléments d’accordéon.</span><span class="sxs-lookup"><span data-stu-id="bbf62-125">This property defines the style of interaction for accordion items.</span></span> <span data-ttu-id="bbf62-126">Si la valeur est définie sur **Indépendant**, chaque élément d’accordéon peut être développé ou réduit indépendamment.</span><span class="sxs-lookup"><span data-stu-id="bbf62-126">If the value is set to **Independent**, each accordion item can be expanded or collapsed independently.</span></span> <span data-ttu-id="bbf62-127">Si la valeur est définie sur **Développer un seul élément**, un seul élément peut être développé à la fois.</span><span class="sxs-lookup"><span data-stu-id="bbf62-127">If the value is set to **Expand one item only**, only one item can be expanded at a time.</span></span> <span data-ttu-id="bbf62-128">À mesure que les éléments sont développés, les éléments précédemment développés sont réduits.</span><span class="sxs-lookup"><span data-stu-id="bbf62-128">As items are expanded, previously expanded items are collapsed.</span></span> |

## <a name="accordion-item-module-properties"></a><span data-ttu-id="bbf62-129">Propriétés du module d’élément d’accordéon</span><span class="sxs-lookup"><span data-stu-id="bbf62-129">Accordion item module properties</span></span>

| <span data-ttu-id="bbf62-130">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="bbf62-130">Property name</span></span> | <span data-ttu-id="bbf62-131">Valeurs</span><span class="sxs-lookup"><span data-stu-id="bbf62-131">Values</span></span> | <span data-ttu-id="bbf62-132">Description</span><span class="sxs-lookup"><span data-stu-id="bbf62-132">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="bbf62-133">Titre</span><span class="sxs-lookup"><span data-stu-id="bbf62-133">Title</span></span> | <span data-ttu-id="bbf62-134">Détails</span><span class="sxs-lookup"><span data-stu-id="bbf62-134">Text</span></span> | <span data-ttu-id="bbf62-135">Cette propriété spécifie le texte du titre du module d’élément d’accordéon.</span><span class="sxs-lookup"><span data-stu-id="bbf62-135">This property specifies the title text for the accordion item module.</span></span> <span data-ttu-id="bbf62-136">En sélectionnant la région du titre, les utilisateurs peuvent développer ou réduire la section.</span><span class="sxs-lookup"><span data-stu-id="bbf62-136">By selecting the title region, users can expand or collapse the section.</span></span> |
| <span data-ttu-id="bbf62-137">Développer par défaut</span><span class="sxs-lookup"><span data-stu-id="bbf62-137">Expand by default</span></span> | <span data-ttu-id="bbf62-138">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="bbf62-138">**True** or **False**</span></span> | <span data-ttu-id="bbf62-139">Si la valeur est définie sur **Vrai**, l’élément d’accordéon est développé par défaut lors du chargement de la page.</span><span class="sxs-lookup"><span data-stu-id="bbf62-139">If the value is set to **True**, the accordion item is expanded by default when the page is loaded.</span></span> |

## <a name="add-an-accordion-module-to-a-faq-page"></a><span data-ttu-id="bbf62-140">Ajouter un module d’accordéon à une page de FAQ</span><span class="sxs-lookup"><span data-stu-id="bbf62-140">Add an accordion module to a FAQ page</span></span>

<span data-ttu-id="bbf62-141">Pour ajouter un module d’accordéon à une page de FAQ et définir ses propriétés dans le générateur de site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="bbf62-141">To add an accordion module to a FAQ page and set its properties in site builder, follow these steps.</span></span>

1. <span data-ttu-id="bbf62-142">Accédez à **Pages** et utilisez le modèle de marketing Fabrikam (ou tout modèle dénué de restriction) pour créer une nouvelle page nommée **FAQ du magasin**.</span><span class="sxs-lookup"><span data-stu-id="bbf62-142">Go to **Pages**, and use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store FAQ**.</span></span>
1. <span data-ttu-id="bbf62-143">Dans l’emplacement **Principal** de la **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="bbf62-143">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="bbf62-144">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="bbf62-144">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="bbf62-145">Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="bbf62-145">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="bbf62-146">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Accordéon**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="bbf62-146">In the **Add Module** dialog box, select the **Accordion** module, and then select **OK**.</span></span>
1. <span data-ttu-id="bbf62-147">Dans le volet des propriétés du module d’accordéon, sélectionnez **En-tête** à côté du symbole du crayon.</span><span class="sxs-lookup"><span data-stu-id="bbf62-147">In the property pane of the accordion module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="bbf62-148">Dans la boîte de dialogue **En-tête**, sous **Texte d’en-tête**, entrez **Questions fréquemment posées**.</span><span class="sxs-lookup"><span data-stu-id="bbf62-148">In the **Heading** dialog box, under **Heading Text**, enter **Frequently asked questions**.</span></span> <span data-ttu-id="bbf62-149">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="bbf62-149">Then select **OK**.</span></span>
1. <span data-ttu-id="bbf62-150">Dans le volet des propriétés du module d’accordéon, cochez la case **Afficher Tout développer** puis, dans le champ **Style d’interaction**, sélectionnez **Indépendant**.</span><span class="sxs-lookup"><span data-stu-id="bbf62-150">In the property pane of the accordion module, select the **Show expand all** check box, and then, in the **Interaction style** field, select **Independent**.</span></span>
1. <span data-ttu-id="bbf62-151">Dans l’emplacement **Accordéon**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="bbf62-151">In the **Accordion** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="bbf62-152">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Élément d’accordéon**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="bbf62-152">In the **Add Module** dialog box, select the **Accordion item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="bbf62-153">Dans le volet des propriétés du module d’élément d’accordéon, sous **Titre**, saisissez le texte du titre (par exemple, **Comment fonctionnent les retours ?**).</span><span class="sxs-lookup"><span data-stu-id="bbf62-153">In the property pane of the accordion item module, under **Title**, enter title text (for example, **How do returns work?**).</span></span>
1. <span data-ttu-id="bbf62-154">Dans l’emplacement **Élément d’accordéon**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="bbf62-154">In the **Accordion item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="bbf62-155">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Bloc de texte**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="bbf62-155">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="bbf62-156">Dans le volet des propriétés du module de bloc de texte, entrez un paragraphe de texte (par exemple, **Les retours doivent être traités par le centre d’appels. Contactez le 1-800-FABRIKAM pour les retours. Les produits sont soumis à une politique de retour de 30 jours. Les retours doivent être initiés dans ce délai.**).</span><span class="sxs-lookup"><span data-stu-id="bbf62-156">In the property pane of the text block module, enter a paragraph of text (for example, **Returns must be processed via the call center. Contact 1-800-FABRIKAM for returns. Products have a 30-day return policy. Returns must be initiated within this time frame.**).</span></span>
1. <span data-ttu-id="bbf62-157">Dans l’emplacement **Accordéon**, ajoutez quelques autres modules d’élément d’accordéon.</span><span class="sxs-lookup"><span data-stu-id="bbf62-157">In the **Accordion** slot, add a few more accordion item modules.</span></span> <span data-ttu-id="bbf62-158">Dans chaque module d’élément d’accordéon, ajoutez un module de bloc de texte portant du contenu.</span><span class="sxs-lookup"><span data-stu-id="bbf62-158">In each accordion item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="bbf62-159">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="bbf62-159">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="bbf62-160">La page affichera un module d’accordéon portant le contenu que vous avez ajouté.</span><span class="sxs-lookup"><span data-stu-id="bbf62-160">The page will show an accordion module that has the content that you added.</span></span>
1. <span data-ttu-id="bbf62-161">Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="bbf62-161">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bbf62-162">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="bbf62-162">Additional resources</span></span>

[<span data-ttu-id="bbf62-163">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="bbf62-163">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="bbf62-164">Module Conteneur</span><span class="sxs-lookup"><span data-stu-id="bbf62-164">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="bbf62-165">Module Onglet</span><span class="sxs-lookup"><span data-stu-id="bbf62-165">Tab module</span></span>](add-tab.md)

[<span data-ttu-id="bbf62-166">Module de bloc de texte</span><span class="sxs-lookup"><span data-stu-id="bbf62-166">Text block module</span></span>](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]