---
title: Module Panier
description: Cette rubrique couvre les modules de panier et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f21268ed4cffed1d5c789f722796cdf05e965819
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621034"
---
# <a name="cart-module"></a><span data-ttu-id="831df-103">Module Panier</span><span class="sxs-lookup"><span data-stu-id="831df-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="831df-104">Cette rubrique couvre les modules de panier et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="831df-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="831df-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="831df-105">Overview</span></span>

<span data-ttu-id="831df-106">Un module de panier affiche les articles qui ont été ajoutés au panier avant que le client ne passe à la caisse.</span><span class="sxs-lookup"><span data-stu-id="831df-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="831df-107">Le module montre également un résumé de la commande et permet au client d’appliquer ou de supprimer des codes promotionnels.</span><span class="sxs-lookup"><span data-stu-id="831df-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="831df-108">Le module de panier prend en charge la caisse connectée et la caisse d’invité.</span><span class="sxs-lookup"><span data-stu-id="831df-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="831df-109">Il prend également en charge un lien **Revenir aux achats**.</span><span class="sxs-lookup"><span data-stu-id="831df-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="831df-110">Vous pouvez configurer l’itinéraire pour ce lien sous **Paramètres du site \> Extensions \> Itinéraires**.</span><span class="sxs-lookup"><span data-stu-id="831df-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="831df-111">Le module de panier affiche les données selon l’ID du panier, qui est un cookie de navigateur disponible sur tout le site.</span><span class="sxs-lookup"><span data-stu-id="831df-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span> 

<span data-ttu-id="831df-112">L’image suivante montre un exemple de page de panier sur le site Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="831df-112">The following image shows an example of a cart page on the Fabrikam site.</span></span>

![Exemple d’un module de panier](./media/cart2.PNG)

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="831df-114">Propriétés et emplacements du module de panier</span><span class="sxs-lookup"><span data-stu-id="831df-114">Cart module properties and slots</span></span>

<span data-ttu-id="831df-115">Le module panier a une propriété **En-tête** qui peut être définie sur des valeurs telles que **Panier d’achat** et **Articles dans votre panier**.</span><span class="sxs-lookup"><span data-stu-id="831df-115">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="831df-116">Modules qui peuvent être utilisés dans un module de panier</span><span class="sxs-lookup"><span data-stu-id="831df-116">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="831df-117">**Bloc de texte** – Ce module prend en charge la messagerie personnalisée dans le module de panier.</span><span class="sxs-lookup"><span data-stu-id="831df-117">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="831df-118">Les messages sont pilotés par le système de gestion de contenu (CMS).</span><span class="sxs-lookup"><span data-stu-id="831df-118">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="831df-119">Tous les messages peuvent être ajoutés, tels que « Pour tout problème avec votre commande, contactez le 1-800-Fabrikam ».</span><span class="sxs-lookup"><span data-stu-id="831df-119">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="831df-120">**Sélecteur de magasins** – Ce module affiche une liste de magasins voisins où un article est disponible pour le prélèvement.</span><span class="sxs-lookup"><span data-stu-id="831df-120">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="831df-121">Il permet aux utilisateurs d’entrer un emplacement pour trouver des magasins à proximité.</span><span class="sxs-lookup"><span data-stu-id="831df-121">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="831df-122">Pour plus d’informations sur ce module, voir [Module du sélecteur de magasins](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="831df-122">For more information on this module, see [Store selector module](store-selector.md).</span></span>

## <a name="module-properties"></a><span data-ttu-id="831df-123">Propriétés du module</span><span class="sxs-lookup"><span data-stu-id="831df-123">Module properties</span></span>

<span data-ttu-id="831df-124">Les paramètres de module de panier suivants peuvent être configurés sur **Paramètres du site \> Extensions** :</span><span class="sxs-lookup"><span data-stu-id="831df-124">The following cart module settings can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="831df-125">**Quantité maximale** – Cette propriété est utilisé pour spécifier le nombre maximal de chaque article qui peut être ajouté au panier.</span><span class="sxs-lookup"><span data-stu-id="831df-125">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="831df-126">Par exemple, un détaillant peut décider que seuls 10 % de chaque produit peuvent être vendus en une seule transaction.</span><span class="sxs-lookup"><span data-stu-id="831df-126">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="831df-127">**Stock** – Pour plus d’informations sur l’application des paramètres de stock, voir [Appliquer les paramètres de stock](inventory-settings.md).</span><span class="sxs-lookup"><span data-stu-id="831df-127">**Inventory** – For information about how to apply inventory settings, see [Apply inventory settings](inventory-settings.md).</span></span>
- <span data-ttu-id="831df-128">**Revenir aux achats** - Cette propriété est utilisée pour spécifier l’itinéraire pour le lien **Revenir aux achats**.</span><span class="sxs-lookup"><span data-stu-id="831df-128">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="831df-129">L’itinéraire peut être configuré au niveau du site, permettant aux détaillants de ramener le client à la page d’accueil ou vers toute autre page du site.</span><span class="sxs-lookup"><span data-stu-id="831df-129">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="831df-130">Interaction avec l’unité d’échelle commerciale</span><span class="sxs-lookup"><span data-stu-id="831df-130">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="831df-131">Le module de panier extrait les informations sur le produit à l’aide des API d’unité d’échelle commerciale.</span><span class="sxs-lookup"><span data-stu-id="831df-131">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="831df-132">L’ID panier du cookie du navigateur permet de récupérer toutes les informations sur le produit auprès de l’unité d’échelle commerciale.</span><span class="sxs-lookup"><span data-stu-id="831df-132">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="831df-133">Ajouter un module de panier à une page</span><span class="sxs-lookup"><span data-stu-id="831df-133">Add a cart module to a page</span></span>

<span data-ttu-id="831df-134">Pour ajouter un module de panier à une nouvelle page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="831df-134">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="831df-135">Accédez à **Fragments de page**, puis cliquez sur **Nouveau** pour créer un fragment.</span><span class="sxs-lookup"><span data-stu-id="831df-135">Go to **Page Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="831df-136">Dans la boîte de dialogue **Nouveau fragment de page**, sélectionnez le module **Panier**.</span><span class="sxs-lookup"><span data-stu-id="831df-136">In the **New Page Fragment** dialog box, select the **Cart** module.</span></span>
1. <span data-ttu-id="831df-137">Sous **Nom du fragment de page**, entrez le nom **Fragment de panier**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="831df-137">Under **Page Fragment Name**, enter the name **Cart fragment**, and then select **OK**.</span></span>
1. <span data-ttu-id="831df-138">Sélectionnez l’emplacement **Panier**.</span><span class="sxs-lookup"><span data-stu-id="831df-138">Select the **Cart** slot.</span></span>
1. <span data-ttu-id="831df-139">Dans le volet des propriétés à droite, sélectionnez le symbole du crayon, entrez le texte de l’en-tête dans le champ, puis sélectionnez le symbole de coche.</span><span class="sxs-lookup"><span data-stu-id="831df-139">In the properties pane on the right, select the pencil symbol, enter heading text in the field, and then select the check mark symbol.</span></span>
1. <span data-ttu-id="831df-140">Dans l’emplacement **Panier**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="831df-140">In the **Cart** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="831df-141">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Sélecteur de magasin**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="831df-141">In the **Add Module** dialog box, select the **Store selector** module, and then select **OK**.</span></span>
1. <span data-ttu-id="831df-142">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="831df-142">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="831df-143">Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="831df-143">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="831df-144">Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez un nom pour le nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="831df-144">In the **New Template** dialog box, under **Template name**, enter a name for the template.</span></span>
1. <span data-ttu-id="831df-145">Dans l’arborescence de contour, sélectionnez l’emplacement **Corps**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un fragment**.</span><span class="sxs-lookup"><span data-stu-id="831df-145">In the outline tree, select the **Body** slot, select the ellipsis (**...**), and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="831df-146">Dans la boîte de dialogue **Sélectionner un fragment de page**, sélectionnez le fragment **Panier**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="831df-146">In the **Select Page Fragment** dialog box, select the **Cart fragment** fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="831df-147">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="831df-147">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="831df-148">Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.</span><span class="sxs-lookup"><span data-stu-id="831df-148">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="831df-149">Dans la boîte de dialogue **Choisir un modèle**, sélectionnez le modèle que vous avez créé, entrez un nom de page, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="831df-149">In the **Choose a template** dialog box, select the template that you created, enter a page name, and then select **OK**.</span></span>
1. <span data-ttu-id="831df-150">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="831df-150">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="831df-151">Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="831df-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="831df-152">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="831df-152">Additional resources</span></span>

[<span data-ttu-id="831df-153">Vue d’ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="831df-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="831df-154">Module Conteneur</span><span class="sxs-lookup"><span data-stu-id="831df-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="831df-155">Module de sélection de magasin</span><span class="sxs-lookup"><span data-stu-id="831df-155">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="831df-156">Module de zone d’achat</span><span class="sxs-lookup"><span data-stu-id="831df-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="831df-157">Module icône de panier</span><span class="sxs-lookup"><span data-stu-id="831df-157">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="831df-158">Module de validation</span><span class="sxs-lookup"><span data-stu-id="831df-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="831df-159">Module de confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="831df-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="831df-160">Module d’en-tête</span><span class="sxs-lookup"><span data-stu-id="831df-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="831df-161">Module de pied de page</span><span class="sxs-lookup"><span data-stu-id="831df-161">Footer module</span></span>](author-footer-module.md)

[<span data-ttu-id="831df-162">Calculer la disponibilité des stocks pour les canaux de vente au détail</span><span class="sxs-lookup"><span data-stu-id="831df-162">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)
