---
title: Module Pied de page
description: Cette rubrique couvre les modules de pied de page et leur création dans Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 51f8d26d6223dcd1f6961058cd9d772a67c69670
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269634"
---
# <a name="footer-module"></a><span data-ttu-id="1369e-103">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="1369e-103">Footer module</span></span>  


[!include [banner](includes/banner.md)]

<span data-ttu-id="1369e-104">Cette rubrique couvre les modules de pied de page et décrit leur création dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1369e-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="1369e-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="1369e-105">Overview</span></span>

<span data-ttu-id="1369e-106">Le module de pied de page est un conteneur spécial utilisé pour héberger les modules qui figurent dans le pied de page de la page.</span><span class="sxs-lookup"><span data-stu-id="1369e-106">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="1369e-107">Par exemple, il peut inclure des liens vers des pages du site, telles que les pages **Nous contacter** et **Stocker des stratégies**.</span><span class="sxs-lookup"><span data-stu-id="1369e-107">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

## <a name="footer-module-properties"></a><span data-ttu-id="1369e-108">Propriétés du module de pied de page</span><span class="sxs-lookup"><span data-stu-id="1369e-108">Footer module properties</span></span> 

<span data-ttu-id="1369e-109">Comme la plupart des conteneurs, un module de pied de page prend en charge les propriétés pour l'en-tête et la largeur.</span><span class="sxs-lookup"><span data-stu-id="1369e-109">Like most containers, a footer module supports properties for the heading and the width.</span></span> <span data-ttu-id="1369e-110">Il prend également en charge l'addition de plusieurs modules de catégories de pieds de page.</span><span class="sxs-lookup"><span data-stu-id="1369e-110">It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id="1369e-111">Chaque module de catégorie de pied de page qui est ajouté est affiché dans une colonne dans le module de pied de page.</span><span class="sxs-lookup"><span data-stu-id="1369e-111">Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name="modules-available-in-a-footer-module"></a><span data-ttu-id="1369e-112">Modules disponibles dans un module de pied de page</span><span class="sxs-lookup"><span data-stu-id="1369e-112">Modules available in a footer module</span></span>

<span data-ttu-id="1369e-113">**Articles de pied de page** – Un module d'articles de pied de page peut contenir un en-tête, une image, et un lien.</span><span class="sxs-lookup"><span data-stu-id="1369e-113">**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id="1369e-114">L'en-tête peut être utilisé seul ou en combinaison avec une image et un lien.</span><span class="sxs-lookup"><span data-stu-id="1369e-114">The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id="1369e-115">Chaque lien dans le pied de page peut être configuré de sorte qu'il s'agisse juste de texte (par exemple, « Contactez-nous » et « Confidentialité »), ou afin qu'il comporte à la fois du texte et une image (par exemple, des liens vers des réseaux sociaux).</span><span class="sxs-lookup"><span data-stu-id="1369e-115">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="1369e-116">**Retour vers le haut** – A module Retour vers le haut fournit un lien de navigation rapide vers le haut de la page.</span><span class="sxs-lookup"><span data-stu-id="1369e-116">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="1369e-117">Une destination est requise.</span><span class="sxs-lookup"><span data-stu-id="1369e-117">A destination is required.</span></span> <span data-ttu-id="1369e-118">La valeur par défaut de destination est #, qui dirige l'utilisateur vers le haut de la page.</span><span class="sxs-lookup"><span data-stu-id="1369e-118">The default destination value is #, which takes the user to the top of the page.</span></span>

## <a name="author-a-footer-module"></a><span data-ttu-id="1369e-119">Créer un module de pied de page</span><span class="sxs-lookup"><span data-stu-id="1369e-119">Author a footer module</span></span>

1. <span data-ttu-id="1369e-120">Dans le volet de navigation, sélectionnez **Fragments**, puis sélectionnez **Nouveau fragment de page**.</span><span class="sxs-lookup"><span data-stu-id="1369e-120">In the navigation pane, select **Fragments**, and then select **New Page Fragment**.</span></span>
1. <span data-ttu-id="1369e-121">Dans la boîte de dialogue **Nouveau fragment de page**, sélectionnez le module de pied de page, entrez un nom pour le fragment de page, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="1369e-121">In the **New Page Fragment** dialog box, select the footer module, enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="1369e-122">Dans l'arborescence du contour à gauche, sélectionnez le bouton représentant des points de suspension (**...**) pour le module de pied de page, puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="1369e-122">In the outline tree on the left, select the ellipsis button (**...**) for the footer module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="1369e-123">Dans la boîte de dialogue **Ajouter le module**, sélectionnez le module de catégorie de pied de page, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="1369e-123">In the **Add Module** dialog box, select the footer category module, and then select **OK**.</span></span>
1. <span data-ttu-id="1369e-124">Dans l'arborescence du contour, sélectionnez le bouton représentant des points de suspension pour le module de catégorie de pied de page, puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="1369e-124">In the outline tree, select the ellipsis button for the footer category module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="1369e-125">Dans la boîte de dialogue **Ajouter le module**, sélectionnez le module d'article de pied de page, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="1369e-125">In the **Add Module** dialog box, select the footer item module, and then select **OK**.</span></span>
1. <span data-ttu-id="1369e-126">Dans l'arborescence de contour, sélectionnez le module d'article de pied de page.</span><span class="sxs-lookup"><span data-stu-id="1369e-126">In the outline tree, select the footer item module.</span></span> <span data-ttu-id="1369e-127">Puis, dans le volet de propriétés de droite, configurez l'en-tête, le lien et le texte du lien, et une image au besoin.</span><span class="sxs-lookup"><span data-stu-id="1369e-127">Then, in the properties pane on the right, configure the heading, link and link text, and image as you require.</span></span>
1. <span data-ttu-id="1369e-128">Pour ajouter d'autres articles de pied de page, répétez les étapes 5 à 7.</span><span class="sxs-lookup"><span data-stu-id="1369e-128">To add more footer items, repeat steps 5 through 7.</span></span>
1. <span data-ttu-id="1369e-129">Pour ajouter un lien « Retour vers le haut » à votre pied de page, sélectionnez le bouton représentant des points de suspension pour le module de catégorie de pied de page, puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="1369e-129">To add a "back to top" link to your footer, select the ellipsis button for the footer category module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="1369e-130">Dans la boîte de dialogue **Ajouter le module**, sélectionnez le module de retour vers le haut, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="1369e-130">In the **Add Module** dialog box, select the back to top module, and then select **OK**.</span></span>
1. <span data-ttu-id="1369e-131">Dans l'arborescence de contour, sélectionnez le module de retour vers le haut.</span><span class="sxs-lookup"><span data-stu-id="1369e-131">In the outline tree, select the back to top module.</span></span> <span data-ttu-id="1369e-132">Puis, dans le volet des propriétés de droite, configurez le module de retour vers le haut comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="1369e-132">Then, in the properties pane on the right, configure the back to top module as you require.</span></span>
1. <span data-ttu-id="1369e-133">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment de page, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="1369e-133">Select **Save**, select **Finish editing** to check in the page fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="1369e-134">Sur chaque modèle de page créé pour le site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1369e-134">On every page template that has been created for the site, follow these steps.</span></span>

1. <span data-ttu-id="1369e-135">À l'emplacement **Principal** de la page par défaut, dans le module de pied de page, ajoutez le fragment de pied de page que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="1369e-135">In the **Main** slot of the default page, in the footer module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="1369e-136">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="1369e-136">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="1369e-137">En ajoutant le fragment de page aux modèles de page, vous vous assurez que le pied de page s'affiche sur chaque page.</span><span class="sxs-lookup"><span data-stu-id="1369e-137">By adding the page fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1369e-138">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="1369e-138">Additional resources</span></span>

[<span data-ttu-id="1369e-139">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="1369e-139">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="1369e-140">Module Container</span><span class="sxs-lookup"><span data-stu-id="1369e-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="1369e-141">Module Zone d'achat</span><span class="sxs-lookup"><span data-stu-id="1369e-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="1369e-142">Module Panier</span><span class="sxs-lookup"><span data-stu-id="1369e-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="1369e-143">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="1369e-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="1369e-144">Module Confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="1369e-144">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="1369e-145">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="1369e-145">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="1369e-146">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="1369e-146">Footer module</span></span>](author-footer-module.md)
