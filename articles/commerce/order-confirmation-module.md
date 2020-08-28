---
title: Module des détails de la commande
description: Cette rubrique aborde les modules des détails de la commande et explique comment les utiliser dans Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 06/18/2020
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
ms.openlocfilehash: 5876b953a3b3d960c106acf37731fde13b93f8e7
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661170"
---
# <a name="order-details-module"></a><span data-ttu-id="eb1fd-103">Module des détails de la commande</span><span class="sxs-lookup"><span data-stu-id="eb1fd-103">Order details module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="eb1fd-104">Cette rubrique aborde les modules des détails de la commande et explique comment les utiliser dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-104">This topic covers order details modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="eb1fd-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="eb1fd-105">Overview</span></span>

<span data-ttu-id="eb1fd-106">Le module des détails de la commande permet d’afficher les détails de confirmation de commande une fois la commande passée.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-106">The order details module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="eb1fd-107">Il indique l’ID de confirmation de la commande, les coordonnées de contact de la commande et d’autres détails de commande comme les articles achetés, les informations de paiement et le mode d’expédition.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, and the shipping method.</span></span>

## <a name="order-details-module-properties"></a><span data-ttu-id="eb1fd-108">Propriétés du module de détails de commande</span><span class="sxs-lookup"><span data-stu-id="eb1fd-108">Order details module properties</span></span>

| <span data-ttu-id="eb1fd-109">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="eb1fd-109">Property name</span></span>  | <span data-ttu-id="eb1fd-110">Valeurs</span><span class="sxs-lookup"><span data-stu-id="eb1fd-110">Values</span></span> | <span data-ttu-id="eb1fd-111">Description</span><span class="sxs-lookup"><span data-stu-id="eb1fd-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="eb1fd-112">Titre</span><span class="sxs-lookup"><span data-stu-id="eb1fd-112">Heading</span></span>        | <span data-ttu-id="eb1fd-113">Texte d’en-tête et balise d’en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="eb1fd-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="eb1fd-114">Le module de détails de commande peut avoir un en-tête.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-114">The order details module can have a heading.</span></span> <span data-ttu-id="eb1fd-115">Par défaut, la balise d’en-tête **H2** sert pour l’en-tête.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="eb1fd-116">Toutefois, la balise peut être modifiée pour satisfaire aux exigences d’accessibilité.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="eb1fd-117">Numéro du contact</span><span class="sxs-lookup"><span data-stu-id="eb1fd-117">Contact number</span></span> | <span data-ttu-id="eb1fd-118">Texte</span><span class="sxs-lookup"><span data-stu-id="eb1fd-118">Text</span></span> | <span data-ttu-id="eb1fd-119">Un numéro de contact peut être fourni pour les questions liées à la commande.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-119">A contact number can be provided for order-related questions.</span></span> |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a><span data-ttu-id="eb1fd-120">Modules pouvant être utilisés dans une page de détails de la commande</span><span class="sxs-lookup"><span data-stu-id="eb1fd-120">Modules that can be used on an order details page</span></span>

<span data-ttu-id="eb1fd-121">Lorsque vous créez une page de détails de la commande, vous pouvez ajouter d’autres modules pertinents au module de détails de la commande existant.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-121">When you create an order details page, you can add other relevant modules in addition to the order details module.</span></span> <span data-ttu-id="eb1fd-122">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="eb1fd-122">Here are some examples:</span></span>

- <span data-ttu-id="eb1fd-123">**Module de recommandations** : il peut être ajouté à la page de détails de la commande pour suggérer d’autres produits au client.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-123">**Recommendations module** – The recommendations module can be added to the order details page to suggest other products to the customer.</span></span>
- <span data-ttu-id="eb1fd-124">**Modules de marketing** : tout module de marketing peut être ajouté à la page de détails de la commande pour afficher le contenu marketing.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-124">**Marketing modules** – Any marketing module can be added to the order details page to show marketing content.</span></span>

## <a name="add-an-order-details-module-to-a-page"></a><span data-ttu-id="eb1fd-125">Ajouter un module de détails de commande à une page</span><span class="sxs-lookup"><span data-stu-id="eb1fd-125">Add an order details module to a page</span></span>

<span data-ttu-id="eb1fd-126">Pour ajouter un module de détails de commande à une nouvelle page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-126">To add an order details module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="eb1fd-127">Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-127">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="eb1fd-128">Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez un nom pour le **modèle de détails de commande**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-128">In the **New Template** dialog box, under **Template name**, enter the name **Order details template**, and then select **OK**.</span></span>
1. <span data-ttu-id="eb1fd-129">Dans l’emplacement **Corps**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-129">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="eb1fd-130">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Page par défaut**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-130">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="eb1fd-131">Dans l’emplacement **Principal** du module **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-131">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="eb1fd-132">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Détails de commande**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-132">In the **Add Module** dialog box, select the **Order details** module, and then select **OK**.</span></span>
1. <span data-ttu-id="eb1fd-133">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher le modèle.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-133">Select **Save**, and then select **Preview** to preview the template.</span></span> <span data-ttu-id="eb1fd-134">Le module de détails de la commande ne s’affiche pas car il a besoin du contexte du numéro de confirmation de commande.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-134">The order details module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="eb1fd-135">Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-135">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="eb1fd-136">Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-136">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="eb1fd-137">Dans la boîte de dialogue **Choisir un modèle**, sélectionnez le modèle **Modèle de détails de commande**.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-137">In the **Choose a template** dialog box, select **Order details template**.</span></span> <span data-ttu-id="eb1fd-138">Sous **Nom de la page**, entrez **Page de détails de la commande**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-138">Under **Page name**, enter **Order details page**, and then select **OK**.</span></span>
1. <span data-ttu-id="eb1fd-139">Dans l’emplacement **Principal** du module **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-139">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="eb1fd-140">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Détails de commande**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-140">In the **Add Module** dialog box, select the **Order details** module, and then select **OK**.</span></span>
1. <span data-ttu-id="eb1fd-141">Dans le volet des propriétés du module de détails de commande, sélectionnez **En-tête** à côté du symbole du crayon.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-141">In the properties pane for the order details module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="eb1fd-142">Dans le champ **Texte d’en-tête** de la boîte de dialogue **Titre**, entrez le texte de l’en-tête **Détails de la commande**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-142">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order details**, and then select **OK**.</span></span>
1. <span data-ttu-id="eb1fd-143">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-143">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="eb1fd-144">Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-144">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="eb1fd-145">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="eb1fd-145">Additional resources</span></span>

[<span data-ttu-id="eb1fd-146">Module Panier</span><span class="sxs-lookup"><span data-stu-id="eb1fd-146">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="eb1fd-147">Module Icône de panier</span><span class="sxs-lookup"><span data-stu-id="eb1fd-147">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="eb1fd-148">Module Validation</span><span class="sxs-lookup"><span data-stu-id="eb1fd-148">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="eb1fd-149">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="eb1fd-149">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="eb1fd-150">Module Adresse d’expédition</span><span class="sxs-lookup"><span data-stu-id="eb1fd-150">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="eb1fd-151">Module Options de livraison</span><span class="sxs-lookup"><span data-stu-id="eb1fd-151">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="eb1fd-152">Module Carte cadeau</span><span class="sxs-lookup"><span data-stu-id="eb1fd-152">Gift card module</span></span>](add-giftcard.md)
