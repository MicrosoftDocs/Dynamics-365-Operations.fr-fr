---
title: Module Panier
description: Cette rubrique couvre les modules de panier et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1ec8e89ed82bcdffdc21e62d24ad8c8a7d939cdf
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797861"
---
# <a name="cart-module"></a><span data-ttu-id="ac324-103">Module Panier</span><span class="sxs-lookup"><span data-stu-id="ac324-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ac324-104">Cette rubrique couvre les modules de panier et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ac324-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="ac324-105">Un module de panier affiche les articles qui ont été ajoutés au panier avant que le client ne passe à la caisse.</span><span class="sxs-lookup"><span data-stu-id="ac324-105">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="ac324-106">Le module montre également un résumé de la commande et permet au client d’appliquer ou de supprimer des codes promotionnels.</span><span class="sxs-lookup"><span data-stu-id="ac324-106">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="ac324-107">Le module de panier prend en charge la caisse connectée et la caisse d’invité.</span><span class="sxs-lookup"><span data-stu-id="ac324-107">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="ac324-108">Il prend également en charge un lien **Revenir aux achats**.</span><span class="sxs-lookup"><span data-stu-id="ac324-108">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="ac324-109">Vous pouvez configurer l’itinéraire pour ce lien sous **Paramètres du site \> Extensions \> Itinéraires**.</span><span class="sxs-lookup"><span data-stu-id="ac324-109">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="ac324-110">Le module de panier affiche les données selon l’ID du panier, qui est un cookie de navigateur disponible sur tout le site.</span><span class="sxs-lookup"><span data-stu-id="ac324-110">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span> 

<span data-ttu-id="ac324-111">L’image suivante montre un exemple de page de panier sur le site Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="ac324-111">The following image shows an example of a cart page on the Fabrikam site.</span></span>

![Exemple de module de panier sur le site Fabrikam](./media/cart2.PNG)

<span data-ttu-id="ac324-113">L’image suivante montre un exemple de page de panier sur le site Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="ac324-113">The following image shows an example of a cart page on the Fabrikam site.</span></span> <span data-ttu-id="ac324-114">Dans cet exemple, des frais de traitement s’appliquent à un élément de ligne.</span><span class="sxs-lookup"><span data-stu-id="ac324-114">In this example, there is a handling fee for a line item.</span></span>

![Exemple de module de panier avec frais de traitement pour un élément de ligne](./media/ecommerce-handling-fee.png)

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="ac324-116">Propriétés et emplacements du module de panier</span><span class="sxs-lookup"><span data-stu-id="ac324-116">Cart module properties and slots</span></span>

| <span data-ttu-id="ac324-117">Propriété</span><span class="sxs-lookup"><span data-stu-id="ac324-117">Property</span></span> | <span data-ttu-id="ac324-118">Valeurs</span><span class="sxs-lookup"><span data-stu-id="ac324-118">Values</span></span> | <span data-ttu-id="ac324-119">Description</span><span class="sxs-lookup"><span data-stu-id="ac324-119">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="ac324-120">Titre</span><span class="sxs-lookup"><span data-stu-id="ac324-120">Heading</span></span> | <span data-ttu-id="ac324-121">Texte d’en-tête et balise d’en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="ac324-121">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="ac324-122">Un en-tête pour le panier, tel que « Panier d’achat » ou « Articles dans votre panier ».</span><span class="sxs-lookup"><span data-stu-id="ac324-122">A heading for the cart, such as "Shopping bag" or "Items in your cart."</span></span> |
| <span data-ttu-id="ac324-123">Afficher les erreurs de rupture de stock</span><span class="sxs-lookup"><span data-stu-id="ac324-123">Show out of stock errors</span></span> | <span data-ttu-id="ac324-124">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="ac324-124">**True** or **False**</span></span> | <span data-ttu-id="ac324-125">Si cette propriété est définie sur **True**, la page du panier affichera les erreurs liées au stock.</span><span class="sxs-lookup"><span data-stu-id="ac324-125">If this property is set to **True**, the cart page will show stock-related errors.</span></span> <span data-ttu-id="ac324-126">Nous vous recommandons de définir cette propriété sur **True** si des contrôles de stock sont appliqués sur le site.</span><span class="sxs-lookup"><span data-stu-id="ac324-126">We recommend that you set this property to **True** if inventory checks are applied on the site.</span></span> |
| <span data-ttu-id="ac324-127">Afficher les frais d’expédition pour les lignes</span><span class="sxs-lookup"><span data-stu-id="ac324-127">Show shipping charges for line items</span></span> | <span data-ttu-id="ac324-128">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="ac324-128">**True** or **False**</span></span> | <span data-ttu-id="ac324-129">Si cette propriété est définie sur **True**, les articles de ligne de panier afficheront les frais d’expédition, si ces informations sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="ac324-129">If this property is set to **True**, cart line items will show the shipping charges, if this information is available.</span></span> <span data-ttu-id="ac324-130">Cette fonctionnalité n’est pas prise en charge dans le thème Fabrikam, car les utilisateurs sélectionnent la livraison uniquement dans le processus de paiement.</span><span class="sxs-lookup"><span data-stu-id="ac324-130">This feature isn't supported in the Fabrikam theme, because users select shipping only in the checkout flow.</span></span> <span data-ttu-id="ac324-131">Cependant, cette fonctionnalité peut être activée dans d’autres workflows si elle est applicable.</span><span class="sxs-lookup"><span data-stu-id="ac324-131">However, this feature can be turned on in other workflows if it's applicable.</span></span> |
| <span data-ttu-id="ac324-132">Afficher les promotions disponibles</span><span class="sxs-lookup"><span data-stu-id="ac324-132">Show available promotions</span></span>| <span data-ttu-id="ac324-133">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="ac324-133">**True** or **False**</span></span> | <span data-ttu-id="ac324-134">Si cette propriété est définie sur **True**, le panier affiche les promotions disponibles, en fonction des articles du panier.</span><span class="sxs-lookup"><span data-stu-id="ac324-134">If this property is set to **True**, the cart shows available promotions, based on items in the cart.</span></span> <span data-ttu-id="ac324-135">Cette fonctionnalité est disponible dans Dynamics 365 Commerce version 10.0.16.</span><span class="sxs-lookup"><span data-stu-id="ac324-135">This capability is available in the Dynamics 365 Commerce 10.0.16 release.</span></span> |

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="ac324-136">Modules qui peuvent être utilisés dans un module de panier</span><span class="sxs-lookup"><span data-stu-id="ac324-136">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="ac324-137">**Bloc de texte** – Ce module prend en charge la messagerie personnalisée dans le module de panier.</span><span class="sxs-lookup"><span data-stu-id="ac324-137">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="ac324-138">Les messages sont pilotés par le système de gestion de contenu (CMS).</span><span class="sxs-lookup"><span data-stu-id="ac324-138">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="ac324-139">Tous les messages peuvent être ajoutés, tels que « Pour tout problème avec votre commande, contactez le 1-800-Fabrikam ».</span><span class="sxs-lookup"><span data-stu-id="ac324-139">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="ac324-140">**Sélecteur de magasins** – Ce module affiche une liste de magasins voisins où un article est disponible pour le prélèvement.</span><span class="sxs-lookup"><span data-stu-id="ac324-140">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="ac324-141">Il permet aux utilisateurs d’entrer un emplacement pour trouver des magasins à proximité.</span><span class="sxs-lookup"><span data-stu-id="ac324-141">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="ac324-142">Pour plus d’informations sur ce module, voir [Module du sélecteur de magasins](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="ac324-142">For more information on this module, see [Store selector module](store-selector.md).</span></span>

## <a name="module-properties"></a><span data-ttu-id="ac324-143">Propriétés du module</span><span class="sxs-lookup"><span data-stu-id="ac324-143">Module properties</span></span>

<span data-ttu-id="ac324-144">Les paramètres de module de panier suivants peuvent être configurés sur **Paramètres du site \> Extensions** :</span><span class="sxs-lookup"><span data-stu-id="ac324-144">The following cart module settings can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="ac324-145">**Quantité maximale** – Cette propriété est utilisé pour spécifier le nombre maximal de chaque article qui peut être ajouté au panier.</span><span class="sxs-lookup"><span data-stu-id="ac324-145">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="ac324-146">Par exemple, un détaillant peut décider que seuls 10 % de chaque produit peuvent être vendus en une seule transaction.</span><span class="sxs-lookup"><span data-stu-id="ac324-146">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="ac324-147">**Stock** – Pour plus d’informations sur l’application des paramètres de stock, voir [Appliquer les paramètres de stock](inventory-settings.md).</span><span class="sxs-lookup"><span data-stu-id="ac324-147">**Inventory** – For information about how to apply inventory settings, see [Apply inventory settings](inventory-settings.md).</span></span>
- <span data-ttu-id="ac324-148">**Revenir aux achats** - Cette propriété est utilisée pour spécifier l’itinéraire pour le lien **Revenir aux achats**.</span><span class="sxs-lookup"><span data-stu-id="ac324-148">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="ac324-149">L’itinéraire peut être configuré au niveau du site, permettant aux détaillants de ramener le client à la page d’accueil ou vers toute autre page du site.</span><span class="sxs-lookup"><span data-stu-id="ac324-149">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac324-150">Dans Dynamics 365 Commerce version 10.0.14 et versions ultérieures, les articles du panier sont agrégés en fonction des paramètres définis dans le profil de fonctionnalité en ligne de la boutique en ligne dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="ac324-150">In the Dynamics 365 Commerce 10.0.14 release and later, items in the cart are aggregated based on the settings that are defined in the online functionality profile for the online store in Commerce headquarters.</span></span> <span data-ttu-id="ac324-151">Pour plus d’informations sur la création d’un profil de fonctionnalité en ligne et la définition des propriétés requises pour l’agrégation, voir [Créer un profil de fonctionnalité en ligne](online-functionality-profile.md).</span><span class="sxs-lookup"><span data-stu-id="ac324-151">For more information about how to create an online functionality profile and set the properties that are required for aggregation, see [Create an online functionality profile](online-functionality-profile.md).</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="ac324-152">Interaction avec Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="ac324-152">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="ac324-153">Le module de panier extrait les informations sur le produit à l’aide des API d’unité d’échelle commerciale.</span><span class="sxs-lookup"><span data-stu-id="ac324-153">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="ac324-154">L’ID panier du cookie du navigateur permet de récupérer toutes les informations sur le produit auprès de l’unité d’échelle commerciale.</span><span class="sxs-lookup"><span data-stu-id="ac324-154">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="ac324-155">Ajouter un module de panier à une page</span><span class="sxs-lookup"><span data-stu-id="ac324-155">Add a cart module to a page</span></span>

<span data-ttu-id="ac324-156">Pour ajouter un module de panier à une nouvelle page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ac324-156">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="ac324-157">Accédez à **Fragments**, puis cliquez sur **Nouveau** pour créer un fragment.</span><span class="sxs-lookup"><span data-stu-id="ac324-157">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="ac324-158">Dans la boîte de dialogue **Nouveau fragment**, sélectionnez le module **Panier**.</span><span class="sxs-lookup"><span data-stu-id="ac324-158">In the **New fragment** dialog box, select the **Cart** module.</span></span>
1. <span data-ttu-id="ac324-159">Sous **Nom du fragment**, entrez le nom **Fragment de panier**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac324-159">Under **Fragment name**, enter the name **Cart fragment**, and then select **OK**.</span></span>
1. <span data-ttu-id="ac324-160">Sélectionnez l’emplacement **Panier**.</span><span class="sxs-lookup"><span data-stu-id="ac324-160">Select the **Cart** slot.</span></span>
1. <span data-ttu-id="ac324-161">Dans le volet des propriétés à droite, sélectionnez le symbole du crayon, entrez le texte de l’en-tête dans le champ, puis sélectionnez le symbole de coche.</span><span class="sxs-lookup"><span data-stu-id="ac324-161">In the properties pane on the right, select the pencil symbol, enter heading text in the field, and then select the check mark symbol.</span></span>
1. <span data-ttu-id="ac324-162">Dans l’emplacement **Panier**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="ac324-162">In the **Cart** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="ac324-163">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Sélecteur de magasin**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac324-163">In the **Add Module** dialog box, select the **Store selector** module, and then select **OK**.</span></span>
1. <span data-ttu-id="ac324-164">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="ac324-164">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="ac324-165">Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="ac324-165">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="ac324-166">Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez un nom pour le nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="ac324-166">In the **New Template** dialog box, under **Template name**, enter a name for the template.</span></span>
1. <span data-ttu-id="ac324-167">Dans l’arborescence de contour, sélectionnez l’emplacement **Corps**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un fragment**.</span><span class="sxs-lookup"><span data-stu-id="ac324-167">In the outline tree, select the **Body** slot, select the ellipsis (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="ac324-168">Dans la boîte de dialogue **Sélectionner un fragment**, sélectionnez le fragment **Panier**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac324-168">In the **Select fragment** dialog box, select the **Cart fragment** fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="ac324-169">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="ac324-169">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="ac324-170">Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.</span><span class="sxs-lookup"><span data-stu-id="ac324-170">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="ac324-171">Dans la boîte de dialogue **Choisir un modèle**, sélectionnez le modèle que vous avez créé, entrez un nom de page, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac324-171">In the **Choose a template** dialog box, select the template that you created, enter a page name, and then select **OK**.</span></span>
1. <span data-ttu-id="ac324-172">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="ac324-172">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="ac324-173">Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="ac324-173">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ac324-174">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ac324-174">Additional resources</span></span>

[<span data-ttu-id="ac324-175">Module Icône de panier</span><span class="sxs-lookup"><span data-stu-id="ac324-175">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="ac324-176">Module Validation</span><span class="sxs-lookup"><span data-stu-id="ac324-176">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="ac324-177">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="ac324-177">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="ac324-178">Module Adresse d’expédition</span><span class="sxs-lookup"><span data-stu-id="ac324-178">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="ac324-179">Module Options de livraison</span><span class="sxs-lookup"><span data-stu-id="ac324-179">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="ac324-180">Module d’information sur le retrait</span><span class="sxs-lookup"><span data-stu-id="ac324-180">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="ac324-181">Module Détails de la commande</span><span class="sxs-lookup"><span data-stu-id="ac324-181">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="ac324-182">Module Carte cadeau</span><span class="sxs-lookup"><span data-stu-id="ac324-182">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="ac324-183">Calculer la disponibilité des stocks pour les canaux de vente au détail</span><span class="sxs-lookup"><span data-stu-id="ac324-183">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)

[<span data-ttu-id="ac324-184">Créer un profil de fonctionnalité en ligne</span><span class="sxs-lookup"><span data-stu-id="ac324-184">Create an online functionality profile</span></span>](online-functionality-profile.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]