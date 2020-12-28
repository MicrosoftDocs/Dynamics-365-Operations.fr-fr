---
title: Module Confirmation de commande
description: Cette rubrique couvre les modules de confirmation de commande et décrit leur utilisation dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: bf33ebf9c0c5136f40fcd7e1012988d186c4169b
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/07/2020
ms.locfileid: "4412431"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="d3738-103">Module de confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="d3738-103">Order confirmation module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d3738-104">Cette rubrique couvre les modules de confirmation de commande et décrit leur utilisation dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d3738-104">This topic covers order confirmation modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d3738-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="d3738-105">Overview</span></span>

<span data-ttu-id="d3738-106">Le module de confirmation de la commande permet d’afficher les détails de confirmation de commande une fois la commande passée.</span><span class="sxs-lookup"><span data-stu-id="d3738-106">The order confirmation module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="d3738-107">Il indique l’ID de confirmation de la commande, les coordonnées de contact de la commande et d’autres détails de commande comme les articles achetés, les informations de paiement, les options de retrait et le mode d’expédition.</span><span class="sxs-lookup"><span data-stu-id="d3738-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, pickup options, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="d3738-108">Propriétés du module de confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="d3738-108">Order confirmation module properties</span></span>

| <span data-ttu-id="d3738-109">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="d3738-109">Property name</span></span>  | <span data-ttu-id="d3738-110">Valeurs</span><span class="sxs-lookup"><span data-stu-id="d3738-110">Values</span></span> | <span data-ttu-id="d3738-111">Description</span><span class="sxs-lookup"><span data-stu-id="d3738-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="d3738-112">En-tête</span><span class="sxs-lookup"><span data-stu-id="d3738-112">Heading</span></span>        | <span data-ttu-id="d3738-113">Texte d'en-tête et balise d'en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="d3738-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="d3738-114">Le module de confirmation de commande peut avoir un en-tête.</span><span class="sxs-lookup"><span data-stu-id="d3738-114">The order confirmation module can have a heading.</span></span> <span data-ttu-id="d3738-115">Par défaut, la balise d'en-tête **H2** sert pour l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="d3738-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="d3738-116">Toutefois, la balise peut être modifiée pour satisfaire aux exigences d’accessibilité.</span><span class="sxs-lookup"><span data-stu-id="d3738-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="d3738-117">Numéro du contact</span><span class="sxs-lookup"><span data-stu-id="d3738-117">Contact number</span></span> | <span data-ttu-id="d3738-118">Texte</span><span class="sxs-lookup"><span data-stu-id="d3738-118">Text</span></span> | <span data-ttu-id="d3738-119">Un numéro de contact peut être fourni pour les questions liées à la commande.</span><span class="sxs-lookup"><span data-stu-id="d3738-119">A contact number can be provided for order-related questions.</span></span> |
| <span data-ttu-id="d3738-120">Afficher les informations sur le créneau horaire de retrait</span><span class="sxs-lookup"><span data-stu-id="d3738-120">Show pickup timeslot information</span></span> | <span data-ttu-id="d3738-121">Vrai ou Faux</span><span class="sxs-lookup"><span data-stu-id="d3738-121">True or False</span></span> | <span data-ttu-id="d3738-122">Cette propriété est disponible dans Dynamics 365 Commerce 10.0.15 et plus.</span><span class="sxs-lookup"><span data-stu-id="d3738-122">This property is available in Dynamics 365 Commerce 10.0.15 and higher.</span></span> <span data-ttu-id="d3738-123">Lorsqu'elle est vraie, elle affiche les informations sur la plage horaire de retrait si elles sont fournies pour un article de retrait</span><span class="sxs-lookup"><span data-stu-id="d3738-123">When true, it displays the pickup timeslot information if provided for a pickup item</span></span>|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a><span data-ttu-id="d3738-124">Modules pouvant être utilisés dans une page de confirmation de la commande</span><span class="sxs-lookup"><span data-stu-id="d3738-124">Modules that can be used on an order confirmation page</span></span>

<span data-ttu-id="d3738-125">Lorsque vous créez une page de confirmation de la commande, vous pouvez ajouter d’autres modules pertinents au module de confirmation de la commande existant.</span><span class="sxs-lookup"><span data-stu-id="d3738-125">When you create an order confirmation page, you can add other relevant modules in addition to the order confirmation module.</span></span> <span data-ttu-id="d3738-126">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="d3738-126">Here are some examples:</span></span>

- <span data-ttu-id="d3738-127">**Module de recommandations** : il peut être ajouté à la page de confirmation de la commande pour suggérer d’autres produits au client.</span><span class="sxs-lookup"><span data-stu-id="d3738-127">**Recommendations module** – The recommendations module can be added to the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="d3738-128">**Modules de marketing** : tout module de marketing peut être ajouté à la page de confirmation de la commande pour afficher le contenu marketing.</span><span class="sxs-lookup"><span data-stu-id="d3738-128">**Marketing modules** – Any marketing module can be added to the order confirmation page to show marketing content.</span></span>

## <a name="add-an-order-confirmation-module-to-a-page"></a><span data-ttu-id="d3738-129">Ajouter un module confirmation de commande à une page</span><span class="sxs-lookup"><span data-stu-id="d3738-129">Add an order confirmation module to a page</span></span>

<span data-ttu-id="d3738-130">Pour ajouter un module de confirmation de commande à une nouvelle page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d3738-130">To add an order confirmation module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="d3738-131">Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="d3738-131">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="d3738-132">Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez un nom pour le **modèle de confirmation de commande**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3738-132">In the **New Template** dialog box, under **Template name**, enter the name **Order confirmation template**, and then select **OK**.</span></span>
1. <span data-ttu-id="d3738-133">Dans l’emplacement **Corps**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="d3738-133">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="d3738-134">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Page par défaut**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3738-134">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="d3738-135">Dans l’emplacement **Principal** du module **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="d3738-135">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="d3738-136">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Confirmation de commande**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3738-136">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="d3738-137">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher le modèle.</span><span class="sxs-lookup"><span data-stu-id="d3738-137">Select **Save**, and then select **Preview** to preview the template.</span></span> <span data-ttu-id="d3738-138">Le module de confirmation de commande ne sera pas affiché, car il nécessite le contexte du numéro de confirmation de commande.</span><span class="sxs-lookup"><span data-stu-id="d3738-138">The order confirmation module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="d3738-139">Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="d3738-139">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="d3738-140">Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.</span><span class="sxs-lookup"><span data-stu-id="d3738-140">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="d3738-141">Dans la boîte de dialogue **Choisir un modèle**, sélectionnez le modèle **Modèle de confirmation de commande**.</span><span class="sxs-lookup"><span data-stu-id="d3738-141">In the **Choose a template** dialog box, select **Order confirmation template**.</span></span> <span data-ttu-id="d3738-142">Sous **Nom de la page**, entrez **Page de confirmation de la commande**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3738-142">Under **Page name**, enter **Order confirmation page**, and then select **OK**.</span></span>
1. <span data-ttu-id="d3738-143">Dans l’emplacement **Principal** du module **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="d3738-143">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="d3738-144">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Confirmation de commande**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3738-144">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="d3738-145">Dans le volet des propriétés du module de confirmation de commande, sélectionnez **En-tête** à côté du symbole du crayon.</span><span class="sxs-lookup"><span data-stu-id="d3738-145">In the properties pane for the order confirmation module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="d3738-146">Dans le champ **Texte d’en-tête** de la boîte de dialogue **Titre**, entrez le texte de l’en-tête **Confirmation de la commande**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3738-146">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order confirmation**, and then select **OK**.</span></span>
1. <span data-ttu-id="d3738-147">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="d3738-147">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="d3738-148">Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="d3738-148">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d3738-149">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d3738-149">Additional resources</span></span>

[<span data-ttu-id="d3738-150">Module Panier</span><span class="sxs-lookup"><span data-stu-id="d3738-150">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="d3738-151">Module Icône de panier</span><span class="sxs-lookup"><span data-stu-id="d3738-151">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="d3738-152">Module Validation</span><span class="sxs-lookup"><span data-stu-id="d3738-152">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="d3738-153">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="d3738-153">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="d3738-154">Module Adresse d’expédition</span><span class="sxs-lookup"><span data-stu-id="d3738-154">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="d3738-155">Module Options de livraison</span><span class="sxs-lookup"><span data-stu-id="d3738-155">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="d3738-156">Module d'information sur le retrait</span><span class="sxs-lookup"><span data-stu-id="d3738-156">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="d3738-157">Module Carte cadeau</span><span class="sxs-lookup"><span data-stu-id="d3738-157">Gift card module</span></span>](add-giftcard.md)
