---
title: Appliquer les paramètres de stock
description: Cette rubrique couvre les paramètres de stock et décrit leur application dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 5d3737ee1534dd973a35e2ef64f1d58d5a74d5b3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211347"
---
# <a name="apply-inventory-settings"></a><span data-ttu-id="0d1b5-103">Appliquer les paramètres de stock</span><span class="sxs-lookup"><span data-stu-id="0d1b5-103">Apply inventory settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0d1b5-104">Cette rubrique couvre les paramètres de stock et décrit leur application dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-104">This topic covers inventory settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0d1b5-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="0d1b5-105">Overview</span></span>

<span data-ttu-id="0d1b5-106">Les paramètres de stock spécifient si le stock doit être vérifié avant que des produits ne soient ajoutés au panier.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-106">Inventory settings specify whether inventory should be checked before products are added to the cart.</span></span> <span data-ttu-id="0d1b5-107">Ils définissent également les messages de marchandisage liés au stock, tels que « En stock » et « Plus que quelques-uns ».</span><span class="sxs-lookup"><span data-stu-id="0d1b5-107">They also define inventory-related merchandising messages, such as "In stock" and "Only a few left."</span></span> <span data-ttu-id="0d1b5-108">Ces paramètres garantissent qu’un produit ne peut pas être acheté s’il est en rupture de stock.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-108">These settings ensure that a product can't be purchased if it's out of stock.</span></span>

<span data-ttu-id="0d1b5-109">Dynamics 365 Commerce fournit des estimations de la disponibilité des produits.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-109">Dynamics 365 Commerce provides estimates of on-hand availability for products.</span></span> <span data-ttu-id="0d1b5-110">Pour plus d’informations sur le calcul de la disponibilité estimée des produits, voir [Calculer la disponibilité des stocks pour les canaux de vente au détail](calculated-inventory-retail-channels.md).</span><span class="sxs-lookup"><span data-stu-id="0d1b5-110">For information about how estimated on-hand availability is calculated, see [Calculate inventory availability for retail channels](calculated-inventory-retail-channels.md).</span></span>

<span data-ttu-id="0d1b5-111">Dans le générateur de site Commerce, il est possible de définir des seuils et des plages de stocks pour un produit ou une catégorie.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-111">In Commerce site builder, inventory thresholds and ranges can be defined for a product or a category.</span></span> <span data-ttu-id="0d1b5-112">Ils déterminent si l’inventaire peut être classé comme en stock, en stock faible ou en rupture de stock.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-112">They determine whether inventory can be classified as in stock, low stock, or out of stock.</span></span> <span data-ttu-id="0d1b5-113">Pour plus de détails, voir [Configurer les marges de stock et les niveaux de stock](inventory-buffers-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0d1b5-113">For details, see [Configure inventory buffers and inventory levels](inventory-buffers-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0d1b5-114">La prise en charge des seuils et des plages de stock est disponible dans Dynamics 365 Commerce version 10.0.12.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-114">Support for inventory thresholds and ranges is available in the Dynamics 365 Commerce 10.0.12 release.</span></span>

## <a name="inventory-settings"></a><span data-ttu-id="0d1b5-115">Paramètres de stock</span><span class="sxs-lookup"><span data-stu-id="0d1b5-115">Inventory settings</span></span>

<span data-ttu-id="0d1b5-116">Dans Commerce, les paramètres de stock sont définis dans **Paramètres du site \> Extensions \> Gestion du stock** dans le générateur de site.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-116">In Commerce, inventory settings are defined at **Site Settings \> Extensions \> Inventory Management** in site builder.</span></span> <span data-ttu-id="0d1b5-117">Il existe quatre paramètres de stock, dont l’un est obsolète (déconseillé) :</span><span class="sxs-lookup"><span data-stu-id="0d1b5-117">There are four inventory settings, one of which is obsolete (deprecated):</span></span>

- <span data-ttu-id="0d1b5-118">**Activer la vérification du stock dans l’application** – Ce paramètre active une vérification du stock des produits.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-118">**Enable stock check in app** – This setting turns on a product inventory check.</span></span> <span data-ttu-id="0d1b5-119">Les modules de zone d’achat, de panier et de prélèvement en magasin vérifieront alors le stock des produits et ne permettront d’ajouter un produit au panier que si le stock est disponible.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-119">Buy box, cart, and pick up in store modules will then check product inventory, and will allow a product to be added to the cart only if inventory is available.</span></span>
- <span data-ttu-id="0d1b5-120">**Niveau de stock basé sur** – Ce paramètre définit la façon dont les niveaux de stock sont calculés.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-120">**Inventory level based on** – This setting defines how inventory levels are calculated.</span></span> <span data-ttu-id="0d1b5-121">Les valeurs disponibles sont **Total disponible**, **Disponible physique**, et **Seuil de rupture de stock**.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-121">The available values are **Total Available**, **Physical Available**, and **Out of stock threshold**.</span></span> <span data-ttu-id="0d1b5-122">Dans Commerce, il est possible de définir des seuils et des plages de stocks pour chaque produit et catégorie.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-122">In Commerce, inventory threshold and ranges can be defined for each product and category.</span></span> <span data-ttu-id="0d1b5-123">Les API de stock renvoient des informations sur l’inventaire des produits pour les deux propriétés **Total disponible** et **Disponible physique**.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-123">The inventory APIs return product inventory information for both the **Total Available** property and the **Physical Available** property.</span></span> <span data-ttu-id="0d1b5-124">Le distributeur décide si la valeur **Total disponible** ou **Disponible physique** doit être utilisée pour déterminer le nombre en stock et les plages correspondantes pour les statuts « en stock » et « en rupture de stock ».</span><span class="sxs-lookup"><span data-stu-id="0d1b5-124">The retailer decides whether the **Total Available** or **Physical Available** value should be used to determine the inventory count and the corresponding ranges for in-stock and out-of-stock statuses.</span></span>

    <span data-ttu-id="0d1b5-125">La valeur **Seuil de rupture de stock** du paramètre **Niveau de stock basé sur** est une valeur ancienne (héritée) et obsolète.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-125">The **Out of stock threshold** value of the **Inventory level based on** setting is an old (legacy), obsolete value.</span></span> <span data-ttu-id="0d1b5-126">Lorsqu’il est sélectionné, le nombre en stock est déterminé à partir des résultats de la valeur **Total disponible**, mais le seuil est défini par le paramètre numérique **Seuil de rupture de stock** décrit plus loin.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-126">When it's selected, the inventory count is determined from the results of the **Total Available** value, but the threshold is defined by the **Out of stock threshold** numeric setting that is described later.</span></span> <span data-ttu-id="0d1b5-127">Ce paramètre de seuil s’applique à tous les produits d’un site d'e-commerce.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-127">This threshold setting applies to all products across an e-commerce site.</span></span> <span data-ttu-id="0d1b5-128">Si le stock est inférieur au seuil, un produit est considéré comme en rupture de stock.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-128">If inventory is below the threshold number, a product is considered out of stock.</span></span> <span data-ttu-id="0d1b5-129">Sinon, il est considéré comme en stock.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-129">Otherwise, it's considered in stock.</span></span> <span data-ttu-id="0d1b5-130">Les fonctionnalités de la valeur **Seuil de rupture de stock** sont limitées et nous vous déconseillons de l’utiliser dans la version 10.0.12 et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-130">The capabilities of the **Out of stock threshold** value are limited, and we don't recommend that you use it in version 10.0.12 and later.</span></span>

- <span data-ttu-id="0d1b5-131">**Plages de stock** – Ce paramètre définit les plages de stock pour lesquelles des messages sont affichés sur les modules du site.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-131">**Inventory ranges** – This setting defines the inventory ranges that message are shown for on site modules.</span></span> <span data-ttu-id="0d1b5-132">Il est applicable uniquement si la valeur **Total disponible** ou la valeur **Disponible physique** est sélectionnée pour le paramètre **Niveau de stock basé sur**.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-132">It's applicable only if either the **Total Available** value or the **Physical Available** value is selected for the **Inventory level based on** setting.</span></span> <span data-ttu-id="0d1b5-133">Les valeurs disponibles sont **Tout**, **Stock faible et rupture de stock** et **En rupture de stock**.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-133">The available values are **All**, **Low and out of stock**, and **Out of stock**.</span></span>

    - <span data-ttu-id="0d1b5-134">Quand **Tout** est sélectionné, les messages pour toutes les plages de stock, depuis en stock (message « Disponible ») jusqu’à rupture de stock (message « Épuisé »), seront affichés.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-134">When **All** is selected, messages for all inventory ranges, from in stock ("Available" message) to out of stock ("Out of stock" message), will be shown.</span></span>
    - <span data-ttu-id="0d1b5-135">Quand **Stock faible et rupture de stock** est sélectionné, les messages pour toutes les plages de stock, sauf en stock (message « Disponible »), seront affichés.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-135">When **Low and out of stock** is selected, messages for all inventory ranges except in stock ("Available" message) will be shown.</span></span>
    - <span data-ttu-id="0d1b5-136">Quand **En rupture de stock** est sélectionné, seul le message « Épuisé » sera affiché.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-136">When **Out of stock** is selected, only the "Out of stock" message will be shown.</span></span>

- <span data-ttu-id="0d1b5-137">**Seuil de rupture de stock** – Cet ancien paramètre numérique ne prendra effet que si la valeur **Seuil de rupture de stock** est sélectionnée pour le paramètre **Niveau de stock basé sur**.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-137">**Out of stock threshold** – This old numeric setting will take effect only if the **Out of stock threshold** value is selected for the **Inventory level based on** setting.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="0d1b5-138">Ces paramètres sont disponibles dans la version 10.0.12 de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-138">These settings are available in the Dynamics 365 Commerce 10.0.12 release.</span></span> <span data-ttu-id="0d1b5-139">Si vous effectuez une mise à jour à partir d'une ancienne version de Dynamics 365 Commerce, vous devez mettre à jour manuellement le fichier appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-139">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="0d1b5-140">Pour obtenir des instructions de mise à jour du fichier appsettings.json, consultez [Mise à jour du kit de développement logiciel et de la bibliothèque de modules](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="0d1b5-140">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="modules-that-use-inventory-settings"></a><span data-ttu-id="0d1b5-141">Modules qui utilisent les paramètres de stock</span><span class="sxs-lookup"><span data-stu-id="0d1b5-141">Modules that use inventory settings</span></span>

<span data-ttu-id="0d1b5-142">Les modules Zone d’achat, Liste de souhaits, Sélecteur de magasin, Panier et Icône de panier utilisent les paramètres de stock pour afficher les plages et les messages de stock.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-142">Buy box, wishlist, store selector, cart, and cart icon modules use inventory settings to show the inventory ranges and messages.</span></span>

<span data-ttu-id="0d1b5-143">L’image suivante montre un exemple de page de détails du produit (PDP) qui affiche un message en stock (« Disponible »).</span><span class="sxs-lookup"><span data-stu-id="0d1b5-143">The following image shows an example of a product details page (PDP) that is showing an in-stock ("Available") message.</span></span>

![Exemple d’un module PDP qui affiche un message en stock](./media/pdp-InStock.png)

<span data-ttu-id="0d1b5-145">L’image suivante montre un exemple de page PDP qui affiche un message de rupture de stock (« Épuisé »).</span><span class="sxs-lookup"><span data-stu-id="0d1b5-145">The following image shows an example of a PDP that is showing an "Out of stock" message.</span></span>

![Exemple d’un module PDP qui affiche un message de rupture de stock](./media/pdp-outofstock.png)

<span data-ttu-id="0d1b5-147">L’image suivante montre un exemple de panier qui affiche un message de stock (« Disponible »).</span><span class="sxs-lookup"><span data-stu-id="0d1b5-147">The following image shows an example of a cart that is showing an in-stock ("Available") message.</span></span>

![Exemple d’un module de panier qui affiche un message en stock](./media/cart-instock.png)

## <a name="additional-resources"></a><span data-ttu-id="0d1b5-149">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0d1b5-149">Additional resources</span></span>

[<span data-ttu-id="0d1b5-150">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="0d1b5-150">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="0d1b5-151">Configurer des marges de stock et des niveaux de stock</span><span class="sxs-lookup"><span data-stu-id="0d1b5-151">Configure inventory buffers and inventory levels</span></span>](inventory-buffers-levels.md)

[<span data-ttu-id="0d1b5-152">Module de panier</span><span class="sxs-lookup"><span data-stu-id="0d1b5-152">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="0d1b5-153">Module de zone d’achat</span><span class="sxs-lookup"><span data-stu-id="0d1b5-153">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="0d1b5-154">Pages et modules Gestion des comptes</span><span class="sxs-lookup"><span data-stu-id="0d1b5-154">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="0d1b5-155">Module Sélection de magasin</span><span class="sxs-lookup"><span data-stu-id="0d1b5-155">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="0d1b5-156">Mise à jour du kit de développement logiciel et de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="0d1b5-156">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]