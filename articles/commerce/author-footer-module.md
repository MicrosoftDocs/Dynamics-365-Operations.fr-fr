---
title: Module Pied de page
description: Cette rubrique couvre les modules de pied de page et leur création dans Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: 87ffc0204019f2f7122c40dc21bdb5de012929d6
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411199"
---
# <a name="footer-module"></a><span data-ttu-id="51445-103">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="51445-103">Footer module</span></span>  

[!include [banner](includes/banner.md)]

<span data-ttu-id="51445-104">Cette rubrique couvre les modules de pied de page et décrit leur création dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="51445-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="51445-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="51445-105">Overview</span></span>

<span data-ttu-id="51445-106">Le module de pied de page est un conteneur spécial utilisé pour héberger les modules qui figurent dans le pied de page de la page.</span><span class="sxs-lookup"><span data-stu-id="51445-106">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="51445-107">Par exemple, il peut inclure des liens vers des pages du site, telles que les pages **Nous contacter** et **Stocker des stratégies**.</span><span class="sxs-lookup"><span data-stu-id="51445-107">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

<span data-ttu-id="51445-108">L'image suivante montre un exemple de module de pied de page sur une page de site.</span><span class="sxs-lookup"><span data-stu-id="51445-108">The following image shows an example of a footer module on a site page.</span></span>

![Exemple de module de pied de page](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a><span data-ttu-id="51445-110">Propriétés du module de pied de page</span><span class="sxs-lookup"><span data-stu-id="51445-110">Footer module properties</span></span> 

<span data-ttu-id="51445-111">Comme la plupart des conteneurs, un module de pied de page prend en charge les propriétés pour l'en-tête et la largeur.</span><span class="sxs-lookup"><span data-stu-id="51445-111">Like most containers, a footer module supports properties for the heading and the width.</span></span> <span data-ttu-id="51445-112">Il prend également en charge l'addition de plusieurs modules de catégories de pieds de page.</span><span class="sxs-lookup"><span data-stu-id="51445-112">It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id="51445-113">Chaque module de catégorie de pied de page qui est ajouté est affiché dans une colonne dans le module de pied de page.</span><span class="sxs-lookup"><span data-stu-id="51445-113">Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name="modules-available-in-a-footer-module"></a><span data-ttu-id="51445-114">Modules disponibles dans un module de pied de page</span><span class="sxs-lookup"><span data-stu-id="51445-114">Modules available in a footer module</span></span>

<span data-ttu-id="51445-115">**Articles de pied de page** – Un module d'articles de pied de page peut contenir un en-tête, une image, et un lien.</span><span class="sxs-lookup"><span data-stu-id="51445-115">**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id="51445-116">L'en-tête peut être utilisé seul ou en combinaison avec une image et un lien.</span><span class="sxs-lookup"><span data-stu-id="51445-116">The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id="51445-117">Chaque lien dans le pied de page peut être configuré de sorte qu'il s'agisse juste de texte (par exemple, « Contactez-nous » et « Confidentialité »), ou afin qu'il comporte à la fois du texte et une image (par exemple, des liens vers des réseaux sociaux).</span><span class="sxs-lookup"><span data-stu-id="51445-117">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="51445-118">**Retour vers le haut** – A module Retour vers le haut fournit un lien de navigation rapide vers le haut de la page.</span><span class="sxs-lookup"><span data-stu-id="51445-118">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="51445-119">Une destination est requise.</span><span class="sxs-lookup"><span data-stu-id="51445-119">A destination is required.</span></span> <span data-ttu-id="51445-120">La valeur par défaut de destination est \#, qui dirige l'utilisateur vers le haut de la page.</span><span class="sxs-lookup"><span data-stu-id="51445-120">The default destination value is \#, which takes the user to the top of the page.</span></span>

## <a name="create-a-footer-module"></a><span data-ttu-id="51445-121">Créer un module de pied de page</span><span class="sxs-lookup"><span data-stu-id="51445-121">Create a footer module</span></span>

1. <span data-ttu-id="51445-122">Accédez à **Fragments de page**, puis cliquez sur **Nouveau** pour créer un fragment.</span><span class="sxs-lookup"><span data-stu-id="51445-122">Go to **Page Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="51445-123">Dans la boîte de dialogue **Nouveau fragment de page**, sélectionnez le module **Conteneur**, entrez un nom pour le fragment de page, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="51445-123">In the **New Page Fragment** dialog box, select the **Container** module, enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="51445-124">Dans l'emplacement **Conteneur par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="51445-124">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="51445-125">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Catégorie de pied de page**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="51445-125">In the **Add Module** dialog box, select the **Footer category** module, and then select **OK**.</span></span>
1. <span data-ttu-id="51445-126">Dans l'emplacement **Catégorie de pied de page**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="51445-126">In the **Footer category** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="51445-127">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Élément de pied de page**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="51445-127">In the **Add Module** dialog box, select the **Footer item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="51445-128">Sélectionnez l'emplacement **Élément de pied de page** puis, dans le volet de propriétés de droite, configurez l'en-tête, le lien et le texte du lien, et une image au besoin.</span><span class="sxs-lookup"><span data-stu-id="51445-128">Select the **Footer item** slot, and then, in the properties pane on the right, configure the heading, link and link text, and image as needed.</span></span>
1. <span data-ttu-id="51445-129">Pour ajouter d'autres éléments de pied de page, répétez les étapes 5 à 7 pour chacun.</span><span class="sxs-lookup"><span data-stu-id="51445-129">To add more footer items, repeat steps 5 through 7 for each.</span></span>
1. <span data-ttu-id="51445-130">Pour ajouter un lien « Retour vers le haut » à votre pied de page, sélectionnez le bouton représentant des points de suspension (**...**) dans l'emplacement **Catégorie de pied de page**, puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="51445-130">To add a "back to top" link to your footer, select the ellipsis (**...**) in the **Footer category** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="51445-131">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Retour vers le haut**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="51445-131">In the **Add Module** dialog box, select the **Back to top** module, and then select **OK**.</span></span>
1. <span data-ttu-id="51445-132">Sélectionnez l'emplacement **Retour vers le haut** puis, dans le volet de propriétés de droite, configurez le texte et les autres propriétés du module selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="51445-132">Select the **Back to top** slot, and then, in the properties pane on the right, configure the text and other module properties as needed.</span></span>
1. <span data-ttu-id="51445-133">Sélectionnez **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="51445-133">Select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="51445-134">Pour vous assurer qu'un en-tête apparaît sur chaque page, suivez ces étapes pour chaque modèle de page créé pour le site.</span><span class="sxs-lookup"><span data-stu-id="51445-134">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="51445-135">Dans l'emplacement **Pied de page** du module **Page par défaut**, ajoutez le fragment de pied de page que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="51445-135">In the **Footer** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="51445-136">Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="51445-136">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="51445-137">En ajoutant le fragment de page aux modèles de page, vous vous assurez que le pied de page s'affiche sur chaque page.</span><span class="sxs-lookup"><span data-stu-id="51445-137">By adding the page fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="51445-138">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="51445-138">Additional resources</span></span>

[<span data-ttu-id="51445-139">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="51445-139">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="51445-140">Module Container</span><span class="sxs-lookup"><span data-stu-id="51445-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="51445-141">Module Zone d'achat</span><span class="sxs-lookup"><span data-stu-id="51445-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="51445-142">Module Panier</span><span class="sxs-lookup"><span data-stu-id="51445-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="51445-143">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="51445-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="51445-144">Module Confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="51445-144">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="51445-145">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="51445-145">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="51445-146">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="51445-146">Footer module</span></span>](author-footer-module.md)
