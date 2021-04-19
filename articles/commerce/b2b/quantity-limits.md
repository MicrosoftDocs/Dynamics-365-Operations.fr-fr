---
title: Définir des limites de quantité de produits pour les sites de commerce électronique B2B
description: Cette rubrique décrit comment définir des limites de quantité de produits pour les sites de commerce électronique B2B.
author: josaw1
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e9f14bc9aa6586e87f3e8ccb82e63d0ec2e46534
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799779"
---
# <a name="set-product-quantity-limits-for-b2b-e-commerce-sites"></a><span data-ttu-id="d3f07-103">Définir des limites de quantité de produits pour les sites de commerce électronique B2B</span><span class="sxs-lookup"><span data-stu-id="d3f07-103">Set product quantity limits for B2B e-commerce sites</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d3f07-104">Cette rubrique décrit comment définir des limites de quantité de produits pour les sites de commerce électronique B2B.</span><span class="sxs-lookup"><span data-stu-id="d3f07-104">This topic describes how to set product quantity limits for business-to-business (B2B) e-commerce sites.</span></span>

<span data-ttu-id="d3f07-105">La plupart des produits ont une unité de mesure qui définit leur regroupement.</span><span class="sxs-lookup"><span data-stu-id="d3f07-105">Most products have a unit of measure that defines their grouping.</span></span> <span data-ttu-id="d3f07-106">Le regroupement affecte la manière dont les produits peuvent être vendus.</span><span class="sxs-lookup"><span data-stu-id="d3f07-106">The grouping affects how the products can be sold.</span></span> <span data-ttu-id="d3f07-107">Certains produits peuvent avoir un regroupement supplémentaire pour les quantités.</span><span class="sxs-lookup"><span data-stu-id="d3f07-107">Some products might have an additional grouping for quantities.</span></span> <span data-ttu-id="d3f07-108">Ce regroupement détermine si les produits peuvent être vendus sous forme d’unités individuelles ou multiples, et s’il existe une limite de quantité de commande minimale ou maximale à respecter.</span><span class="sxs-lookup"><span data-stu-id="d3f07-108">This grouping determines whether the products can be sold as individual units or multiples, and whether there is a minimum or maximum order quantity limit that must be followed.</span></span>

<span data-ttu-id="d3f07-109">La fonctionnalité de limitation de quantité garantit que les quantités minimales, maximales, multiples et standard configurées dans Microsoft Dynamics 365 Commerce (dans les paramètres de commande par défaut ou dans les paramètres du site de création de site Commerce) sont appliqués aux commandes des clients passées sur un site d’e-commerce.</span><span class="sxs-lookup"><span data-stu-id="d3f07-109">The quantity limiting feature ensures that the minimum, maximum, multiple, and standard quantities that are configured in Microsoft Dynamics 365 Commerce (in the default order settings or the Commerce site builder site settings) are applied to customer orders that are placed on an e-commerce site.</span></span> <span data-ttu-id="d3f07-110">Les limites de quantité de produits ne sont actuellement pas prises en charge pour le point de vente (PDV) et les centres d’appels.</span><span class="sxs-lookup"><span data-stu-id="d3f07-110">Product quantity limits aren't currently supported for the point of sale (POS) and call centers.</span></span>

<span data-ttu-id="d3f07-111">De nombreux détaillants offrent la possibilité que les commandes client (également appelées commandes spéciales) répondent à diverses exigences de produit et de traitement.</span><span class="sxs-lookup"><span data-stu-id="d3f07-111">Many retailers provide the option of customer orders (also known as special orders) to meet various product and fulfillment requirements.</span></span> <span data-ttu-id="d3f07-112">Voici quelques scénarios classiques :</span><span class="sxs-lookup"><span data-stu-id="d3f07-112">Here are some typical scenarios:</span></span>

- <span data-ttu-id="d3f07-113">Un client souhaite que des variantes spécifiques de produits soient vendues par multiples.</span><span class="sxs-lookup"><span data-stu-id="d3f07-113">A customer wants products of specific variants to be sold in multiples of a few.</span></span>
- <span data-ttu-id="d3f07-114">Un client souhaite prélever les produits dans un magasin ou un emplacement qui diffère du magasin ou de l’emplacement où il a acheté ces produits.</span><span class="sxs-lookup"><span data-stu-id="d3f07-114">A customer wants to pick up products from a store or location that differs from the store or location where the customer purchased those products.</span></span> <span data-ttu-id="d3f07-115">Cependant, les normes d’emballage pour les magasins diffèrent de celles pour la distribution des ventes en ligne.</span><span class="sxs-lookup"><span data-stu-id="d3f07-115">However, the packing standards for the stores differ from the packing standards for online sales distribution.</span></span>
- <span data-ttu-id="d3f07-116">Un client souhaite acheter un produit en édition limitée dont la quantité maximale pouvant être achetée est limitée.</span><span class="sxs-lookup"><span data-stu-id="d3f07-116">A customer wants to buy a limited-edition product that has a maximum quantity limit for items that can be purchased.</span></span>

## <a name="turn-on-the-default-order-settings-feature-in-commerce-headquarters"></a><span data-ttu-id="d3f07-117">Activez la fonction des paramètres de commande par défaut dans Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="d3f07-117">Turn on the default order settings feature in Commerce headquarters</span></span>

<span data-ttu-id="d3f07-118">Avant de pouvoir définir des limites de quantité de produits, la fonction des paramètres de commande par défaut doit être activée dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="d3f07-118">Before you can set product quantity limits, the default order settings feature must be turned on in Commerce headquarters.</span></span>

<span data-ttu-id="d3f07-119">Pour activer la fonction des paramètres de commande par défaut, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d3f07-119">To turn on the default order settings feature, follow these steps.</span></span>

1. <span data-ttu-id="d3f07-120">Accédez à **Administration système \> Espaces de travail \> Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="d3f07-120">Go to **System administration \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="d3f07-121">Recherchez et sélectionnez la fonction **Prise en charge du site et des paramètres de commande par défaut dans la commande client**.</span><span class="sxs-lookup"><span data-stu-id="d3f07-121">Find and select the **Support the Site and Default order settings in the customer order** feature.</span></span>
1. <span data-ttu-id="d3f07-122">En bas du volet droit, sélectionnez **Activer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="d3f07-122">At the bottom of the right pane, select **Enable now**.</span></span> 

## <a name="define-quantity-settings"></a><span data-ttu-id="d3f07-123">Définir des paramètres de quantité</span><span class="sxs-lookup"><span data-stu-id="d3f07-123">Define quantity settings</span></span> 

<span data-ttu-id="d3f07-124">Vous pouvez définir les paramètres de quantité sur la page **Paramètres de commande par défaut**.</span><span class="sxs-lookup"><span data-stu-id="d3f07-124">You can define the quantity settings on the **Default order settings** page.</span></span>

<span data-ttu-id="d3f07-125">Pour définir les paramètres de quantité, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d3f07-125">To define the quantity settings, follow these steps.</span></span> 

1. <span data-ttu-id="d3f07-126">Accédez à Produit **Retail et Commerce \> Produits et catégories \> Produits lancés par catégorie**.</span><span class="sxs-lookup"><span data-stu-id="d3f07-126">Go to Product **Retail and Commerce \> Products and categories \> Released products by category**.</span></span>
1. <span data-ttu-id="d3f07-127">Sélectionnez un produit lancé.</span><span class="sxs-lookup"><span data-stu-id="d3f07-127">Select a released product.</span></span>
1. <span data-ttu-id="d3f07-128">Dans le volet Actions, sur l’onglet **Gérer le stock**, dans le groupe **Paramètres de commande**, sélectionnez **Paramètres de commande par défaut**.</span><span class="sxs-lookup"><span data-stu-id="d3f07-128">On the Action Pane, on the **Manage inventory** tab, in the **Order settings** group, select **Default order settings**.</span></span> 
1. <span data-ttu-id="d3f07-129">Sur la page **Paramètres de commande par défaut**, sur le raccourci **Commande client**, dans la section **Quantité vendue**, définissez les quantités de produit vendues :</span><span class="sxs-lookup"><span data-stu-id="d3f07-129">On the **Default order settings** page, on the **Sales order** FastTab, in the **Sales quantity** section, set the product sales quantities:</span></span>

    - <span data-ttu-id="d3f07-130">**Multiple** - Multiples dans lesquels le produit peut être acheté.</span><span class="sxs-lookup"><span data-stu-id="d3f07-130">**Multiple** – The quantity that the product can be bought in multiples of.</span></span>
    - <span data-ttu-id="d3f07-131">**Quantité minimale de commande** - Le nombre minimum de produits devant être achetés.</span><span class="sxs-lookup"><span data-stu-id="d3f07-131">**Minimum Order Quantity** – The minimum number of products that must be purchased.</span></span>
    - <span data-ttu-id="d3f07-132">**Quantité maximale de commande** - Le nombre maximal de produits pouvant être achetés.</span><span class="sxs-lookup"><span data-stu-id="d3f07-132">**Maximum Order Quantity** – The maximum number of products that can be purchased.</span></span>
    - <span data-ttu-id="d3f07-133">**Quantité de commande standard** - La quantité par défaut qui est automatiquement saisie lorsque le produit est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d3f07-133">**Standard Order Quantity** – The default quantity that is automatically entered when the product is selected.</span></span>

## <a name="turn-on-the-b2b-order-quantity-limits-feature-in-commerce-site-builder"></a><span data-ttu-id="d3f07-134">Activer la fonctionnalité de limites de quantité de commande B2B dans le générateur de site Commerce</span><span class="sxs-lookup"><span data-stu-id="d3f07-134">Turn on the B2B order quantity limits feature in Commerce site builder</span></span>

<span data-ttu-id="d3f07-135">Pour activer la fonctionnalité de limites de quantité de commande B2B dans le générateur de site Commerce, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d3f07-135">To turn on the B2B order quantity limits feature in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="d3f07-136">Accédez à **Paramètres du site \> Extensions**</span><span class="sxs-lookup"><span data-stu-id="d3f07-136">Go to **Site settings \> Extensions**</span></span>
1. <span data-ttu-id="d3f07-137">Sous **Activer les limites de quantité de commande**, sélectionnez **Activé pour les clients B2B** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="d3f07-137">Under **Enable Order Quantity Limits**, select **Enabled for B2B customers** in the drop-down menu.</span></span> 

> [!NOTE] 
> <span data-ttu-id="d3f07-138">Les paramètres de création de site mis à jour ne prennent effet qu’après la mise à jour du fichier app.settings.json.</span><span class="sxs-lookup"><span data-stu-id="d3f07-138">Updated site builder settings take effect only after the app.settings.json file has been updated.</span></span> <span data-ttu-id="d3f07-139">Pour plus d’informations, voir [Mise à jour des kits de développement logiciel (SDK) et des bibliothèques de modules](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="d3f07-139">For more information, see [SDK and Module library updates](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d3f07-140">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d3f07-140">Additional resources</span></span>

[<span data-ttu-id="d3f07-141">Configurer un site d’e-commerce B2B</span><span class="sxs-lookup"><span data-stu-id="d3f07-141">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="d3f07-142">Créer des hiérarchies de modélisation organisationnelle pour les organisations B2B</span><span class="sxs-lookup"><span data-stu-id="d3f07-142">Create org modeling hierarchies for B2B organizations</span></span>](org-model.md)

[<span data-ttu-id="d3f07-143">Gérer les utilisateurs des partenaires commerciaux sur les sites e-commerce B2B</span><span class="sxs-lookup"><span data-stu-id="d3f07-143">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="d3f07-144">Configurer le mode de paiement du compte client pour les sites de commerce électronique B2B</span><span class="sxs-lookup"><span data-stu-id="d3f07-144">Configure the customer account payment method for B2B e-commerce sites</span></span>](payment-method.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]