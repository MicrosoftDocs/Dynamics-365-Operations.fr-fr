---
title: Module Pied de page
description: Cette rubrique couvre les modules de pied de page et leur création dans Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 16c9ca145aff97f0af242da4cf662367f1f4ca3d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211446"
---
# <a name="footer-module"></a><span data-ttu-id="945cc-103">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="945cc-103">Footer module</span></span>  

[!include [banner](includes/banner.md)]

<span data-ttu-id="945cc-104">Cette rubrique couvre les modules de pied de page et décrit leur création dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="945cc-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="945cc-105">Le module de pied de page est un conteneur spécial utilisé pour héberger les modules qui figurent dans le pied de page de la page.</span><span class="sxs-lookup"><span data-stu-id="945cc-105">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="945cc-106">Par exemple, il peut inclure des liens vers des pages du site, telles que les pages **Nous contacter** et **Stocker des stratégies**.</span><span class="sxs-lookup"><span data-stu-id="945cc-106">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

<span data-ttu-id="945cc-107">L’image suivante montre un exemple de module de pied de page sur une page de site.</span><span class="sxs-lookup"><span data-stu-id="945cc-107">The following image shows an example of a footer module on a site page.</span></span>

![Exemple de module de pied de page](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a><span data-ttu-id="945cc-109">Propriétés du module de pied de page</span><span class="sxs-lookup"><span data-stu-id="945cc-109">Footer module properties</span></span> 

<span data-ttu-id="945cc-110">Comme la plupart des conteneurs, un module de pied de page prend en charge les propriétés pour l’en-tête et la largeur.</span><span class="sxs-lookup"><span data-stu-id="945cc-110">Like most containers, a footer module supports properties for the heading and the width.</span></span> <span data-ttu-id="945cc-111">Il prend également en charge l’addition de plusieurs modules de catégories de pieds de page.</span><span class="sxs-lookup"><span data-stu-id="945cc-111">It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id="945cc-112">Chaque module de catégorie de pied de page qui est ajouté est affiché dans une colonne dans le module de pied de page.</span><span class="sxs-lookup"><span data-stu-id="945cc-112">Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name="modules-available-in-a-footer-module"></a><span data-ttu-id="945cc-113">Modules disponibles dans un module de pied de page</span><span class="sxs-lookup"><span data-stu-id="945cc-113">Modules available in a footer module</span></span>

<span data-ttu-id="945cc-114">**Articles de pied de page** – Un module d’articles de pied de page peut contenir un en-tête, une image, et un lien.</span><span class="sxs-lookup"><span data-stu-id="945cc-114">**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id="945cc-115">L’en-tête peut être utilisé seul ou en combinaison avec une image et un lien.</span><span class="sxs-lookup"><span data-stu-id="945cc-115">The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id="945cc-116">Chaque lien dans le pied de page peut être configuré de sorte qu’il s’agisse juste de texte (par exemple, « Contactez-nous » et « Confidentialité »), ou afin qu’il comporte à la fois du texte et une image (par exemple, des liens vers des réseaux sociaux).</span><span class="sxs-lookup"><span data-stu-id="945cc-116">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="945cc-117">**Retour vers le haut** – A module Retour vers le haut fournit un lien de navigation rapide vers le haut de la page.</span><span class="sxs-lookup"><span data-stu-id="945cc-117">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="945cc-118">Une destination est requise.</span><span class="sxs-lookup"><span data-stu-id="945cc-118">A destination is required.</span></span> <span data-ttu-id="945cc-119">La valeur par défaut de destination est \#, qui dirige l’utilisateur vers le haut de la page.</span><span class="sxs-lookup"><span data-stu-id="945cc-119">The default destination value is \#, which takes the user to the top of the page.</span></span>

## <a name="create-a-footer-module"></a><span data-ttu-id="945cc-120">Créer un module de pied de page</span><span class="sxs-lookup"><span data-stu-id="945cc-120">Create a footer module</span></span>

1. <span data-ttu-id="945cc-121">Accédez à **Fragments**, puis cliquez sur **Nouveau** pour créer un fragment.</span><span class="sxs-lookup"><span data-stu-id="945cc-121">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="945cc-122">Dans la boîte de dialogue **Nouveau fragment**, sélectionnez le module **Conteneur**, entrez un nom pour le fragment, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="945cc-122">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="945cc-123">Dans l’emplacement **Conteneur par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="945cc-123">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="945cc-124">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Catégorie de pied de page**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="945cc-124">In the **Add Module** dialog box, select the **Footer category** module, and then select **OK**.</span></span>
1. <span data-ttu-id="945cc-125">Dans l’emplacement **Catégorie de pied de page**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="945cc-125">In the **Footer category** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="945cc-126">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Élément de pied de page**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="945cc-126">In the **Add Module** dialog box, select the **Footer item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="945cc-127">Sélectionnez l’emplacement **Élément de pied de page** puis, dans le volet de propriétés de droite, configurez l’en-tête, le lien et le texte du lien, et une image au besoin.</span><span class="sxs-lookup"><span data-stu-id="945cc-127">Select the **Footer item** slot, and then, in the properties pane on the right, configure the heading, link and link text, and image as needed.</span></span>
1. <span data-ttu-id="945cc-128">Pour ajouter d’autres éléments de pied de page, répétez les étapes 5 à 7 pour chacun.</span><span class="sxs-lookup"><span data-stu-id="945cc-128">To add more footer items, repeat steps 5 through 7 for each.</span></span>
1. <span data-ttu-id="945cc-129">Pour ajouter un lien « Retour vers le haut » à votre pied de page, sélectionnez le bouton représentant des points de suspension (**...**) dans l’emplacement **Catégorie de pied de page**, puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="945cc-129">To add a "back to top" link to your footer, select the ellipsis (**...**) in the **Footer category** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="945cc-130">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Retour vers le haut**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="945cc-130">In the **Add Module** dialog box, select the **Back to top** module, and then select **OK**.</span></span>
1. <span data-ttu-id="945cc-131">Sélectionnez l’emplacement **Retour vers le haut** puis, dans le volet de propriétés de droite, configurez le texte et les autres propriétés du module selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="945cc-131">Select the **Back to top** slot, and then, in the properties pane on the right, configure the text and other module properties as needed.</span></span>
1. <span data-ttu-id="945cc-132">Sélectionnez **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="945cc-132">Select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="945cc-133">Pour vous assurer qu’un en-tête apparaît sur chaque page, suivez ces étapes pour chaque modèle de page créé pour le site.</span><span class="sxs-lookup"><span data-stu-id="945cc-133">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="945cc-134">Dans l’emplacement **Pied de page** du module **Page par défaut**, ajoutez le fragment de pied de page que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="945cc-134">In the **Footer** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="945cc-135">Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="945cc-135">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="945cc-136">En ajoutant le fragment aux modèles de page, vous vous assurez que le pied de page s’affiche sur chaque page.</span><span class="sxs-lookup"><span data-stu-id="945cc-136">By adding the fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="945cc-137">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="945cc-137">Additional resources</span></span>

[<span data-ttu-id="945cc-138">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="945cc-138">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="945cc-139">Module Conteneur</span><span class="sxs-lookup"><span data-stu-id="945cc-139">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="945cc-140">Module Zone d’achat</span><span class="sxs-lookup"><span data-stu-id="945cc-140">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="945cc-141">Module Panier</span><span class="sxs-lookup"><span data-stu-id="945cc-141">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="945cc-142">Module Validation</span><span class="sxs-lookup"><span data-stu-id="945cc-142">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="945cc-143">Module Confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="945cc-143">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="945cc-144">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="945cc-144">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="945cc-145">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="945cc-145">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]