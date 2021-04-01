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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 407fc2724d4b589ef5f611974f9358e879dba7ed
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257145"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="38037-103">Module de confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="38037-103">Order confirmation module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="38037-104">Cette rubrique couvre les modules de confirmation de commande et décrit leur utilisation dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="38037-104">This topic covers order confirmation modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="38037-105">Le module de confirmation de la commande permet d’afficher les détails de confirmation de commande une fois la commande passée.</span><span class="sxs-lookup"><span data-stu-id="38037-105">The order confirmation module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="38037-106">Il indique l’ID de confirmation de la commande, les coordonnées de contact de la commande et d’autres détails de commande comme les articles achetés, les informations de paiement, les options de retrait et le mode d’expédition.</span><span class="sxs-lookup"><span data-stu-id="38037-106">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, pickup options, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="38037-107">Propriétés du module de confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="38037-107">Order confirmation module properties</span></span>

| <span data-ttu-id="38037-108">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="38037-108">Property name</span></span>  | <span data-ttu-id="38037-109">Valeurs</span><span class="sxs-lookup"><span data-stu-id="38037-109">Values</span></span> | <span data-ttu-id="38037-110">Description</span><span class="sxs-lookup"><span data-stu-id="38037-110">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="38037-111">En-tête</span><span class="sxs-lookup"><span data-stu-id="38037-111">Heading</span></span>        | <span data-ttu-id="38037-112">Texte d'en-tête et balise d'en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="38037-112">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="38037-113">Le module de confirmation de commande peut avoir un en-tête.</span><span class="sxs-lookup"><span data-stu-id="38037-113">The order confirmation module can have a heading.</span></span> <span data-ttu-id="38037-114">Par défaut, la balise d'en-tête **H2** sert pour l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="38037-114">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="38037-115">Toutefois, la balise peut être modifiée pour satisfaire aux exigences d’accessibilité.</span><span class="sxs-lookup"><span data-stu-id="38037-115">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="38037-116">Numéro du contact</span><span class="sxs-lookup"><span data-stu-id="38037-116">Contact number</span></span> | <span data-ttu-id="38037-117">Texte</span><span class="sxs-lookup"><span data-stu-id="38037-117">Text</span></span> | <span data-ttu-id="38037-118">Un numéro de contact peut être fourni pour les questions liées à la commande.</span><span class="sxs-lookup"><span data-stu-id="38037-118">A contact number can be provided for order-related questions.</span></span> |
| <span data-ttu-id="38037-119">Afficher les informations sur le créneau horaire de retrait</span><span class="sxs-lookup"><span data-stu-id="38037-119">Show pickup timeslot information</span></span> | <span data-ttu-id="38037-120">Vrai ou Faux</span><span class="sxs-lookup"><span data-stu-id="38037-120">True or False</span></span> | <span data-ttu-id="38037-121">Cette propriété est disponible dans Dynamics 365 Commerce 10.0.15 et plus.</span><span class="sxs-lookup"><span data-stu-id="38037-121">This property is available in Dynamics 365 Commerce 10.0.15 and higher.</span></span> <span data-ttu-id="38037-122">Lorsqu'elle est vraie, elle affiche les informations sur la plage horaire de retrait si elles sont fournies pour un article de retrait</span><span class="sxs-lookup"><span data-stu-id="38037-122">When true, it displays the pickup timeslot information if provided for a pickup item</span></span>|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a><span data-ttu-id="38037-123">Modules pouvant être utilisés dans une page de confirmation de la commande</span><span class="sxs-lookup"><span data-stu-id="38037-123">Modules that can be used on an order confirmation page</span></span>

<span data-ttu-id="38037-124">Lorsque vous créez une page de confirmation de la commande, vous pouvez ajouter d’autres modules pertinents au module de confirmation de la commande existant.</span><span class="sxs-lookup"><span data-stu-id="38037-124">When you create an order confirmation page, you can add other relevant modules in addition to the order confirmation module.</span></span> <span data-ttu-id="38037-125">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="38037-125">Here are some examples:</span></span>

- <span data-ttu-id="38037-126">**Module de recommandations** : il peut être ajouté à la page de confirmation de la commande pour suggérer d’autres produits au client.</span><span class="sxs-lookup"><span data-stu-id="38037-126">**Recommendations module** – The recommendations module can be added to the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="38037-127">**Modules de marketing** : tout module de marketing peut être ajouté à la page de confirmation de la commande pour afficher le contenu marketing.</span><span class="sxs-lookup"><span data-stu-id="38037-127">**Marketing modules** – Any marketing module can be added to the order confirmation page to show marketing content.</span></span>

## <a name="add-an-order-confirmation-module-to-a-page"></a><span data-ttu-id="38037-128">Ajouter un module confirmation de commande à une page</span><span class="sxs-lookup"><span data-stu-id="38037-128">Add an order confirmation module to a page</span></span>

<span data-ttu-id="38037-129">Pour ajouter un module de confirmation de commande à une nouvelle page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="38037-129">To add an order confirmation module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="38037-130">Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="38037-130">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="38037-131">Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez un nom pour le **modèle de confirmation de commande**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="38037-131">In the **New Template** dialog box, under **Template name**, enter the name **Order confirmation template**, and then select **OK**.</span></span>
1. <span data-ttu-id="38037-132">Dans l’emplacement **Corps**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="38037-132">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="38037-133">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Page par défaut**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="38037-133">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="38037-134">Dans l’emplacement **Principal** du module **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="38037-134">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="38037-135">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Confirmation de commande**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="38037-135">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="38037-136">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher le modèle.</span><span class="sxs-lookup"><span data-stu-id="38037-136">Select **Save**, and then select **Preview** to preview the template.</span></span> <span data-ttu-id="38037-137">Le module de confirmation de commande ne sera pas affiché, car il nécessite le contexte du numéro de confirmation de commande.</span><span class="sxs-lookup"><span data-stu-id="38037-137">The order confirmation module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="38037-138">Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="38037-138">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="38037-139">Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.</span><span class="sxs-lookup"><span data-stu-id="38037-139">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="38037-140">Dans la boîte de dialogue **Choisir un modèle**, sélectionnez le modèle **Modèle de confirmation de commande**.</span><span class="sxs-lookup"><span data-stu-id="38037-140">In the **Choose a template** dialog box, select **Order confirmation template**.</span></span> <span data-ttu-id="38037-141">Sous **Nom de la page**, entrez **Page de confirmation de la commande**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="38037-141">Under **Page name**, enter **Order confirmation page**, and then select **OK**.</span></span>
1. <span data-ttu-id="38037-142">Dans l’emplacement **Principal** du module **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="38037-142">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="38037-143">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Confirmation de commande**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="38037-143">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="38037-144">Dans le volet des propriétés du module de confirmation de commande, sélectionnez **En-tête** à côté du symbole du crayon.</span><span class="sxs-lookup"><span data-stu-id="38037-144">In the properties pane for the order confirmation module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="38037-145">Dans le champ **Texte d’en-tête** de la boîte de dialogue **Titre**, entrez le texte de l’en-tête **Confirmation de la commande**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="38037-145">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order confirmation**, and then select **OK**.</span></span>
1. <span data-ttu-id="38037-146">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="38037-146">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="38037-147">Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="38037-147">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="38037-148">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="38037-148">Additional resources</span></span>

[<span data-ttu-id="38037-149">Module Panier</span><span class="sxs-lookup"><span data-stu-id="38037-149">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="38037-150">Module Icône de panier</span><span class="sxs-lookup"><span data-stu-id="38037-150">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="38037-151">Module Validation</span><span class="sxs-lookup"><span data-stu-id="38037-151">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="38037-152">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="38037-152">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="38037-153">Module Adresse d’expédition</span><span class="sxs-lookup"><span data-stu-id="38037-153">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="38037-154">Module Options de livraison</span><span class="sxs-lookup"><span data-stu-id="38037-154">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="38037-155">Module d'information sur le retrait</span><span class="sxs-lookup"><span data-stu-id="38037-155">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="38037-156">Module Carte cadeau</span><span class="sxs-lookup"><span data-stu-id="38037-156">Gift card module</span></span>](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]