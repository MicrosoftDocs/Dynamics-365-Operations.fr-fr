---
title: Recherche de stock dans le point de vente (PDV)
description: Cette rubrique décrit les options disponibles pour afficher les informations de stock dans le point de vente (PDV).
author: ashishmsft
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.openlocfilehash: 26bbbeee7ed6c228b3c84dc07576bccb8e1aebd8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231006"
---
# <a name="inventory-lookup-in-the-point-of-sale-pos"></a><span data-ttu-id="9027d-103">Recherche de stock dans le point de vente (PDV)</span><span class="sxs-lookup"><span data-stu-id="9027d-103">Inventory lookup in the point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9027d-104">La recherche de stock dans le point de vente (PDV) permet aux détaillants d'atteindre l'excellence opérationnelle en temps réel et d'acquérir des connaissances en connectant les magasins, le PDV, et les services administratifs.</span><span class="sxs-lookup"><span data-stu-id="9027d-104">Inventory lookup in the point of sale (POS) helps retailers achieve real-time operational excellence and gain insights by connecting stores, the POS, and the back office.</span></span> <span data-ttu-id="9027d-105">Cette fonctionnalité fournit une vue en temps réel précise du stock de produits entre les magasins et les centres de distribution.</span><span class="sxs-lookup"><span data-stu-id="9027d-105">This functionality provides an accurate real-time view of product inventory across stores and distribution centers.</span></span> <span data-ttu-id="9027d-106">Elle permet également aux détaillants d'acquérir de l'efficacité supplémentaire et de réaliser des économies en améliorant la planification de stock en temps réel.</span><span class="sxs-lookup"><span data-stu-id="9027d-106">It also helps retailers drive additional efficiencies and cost savings by improving inventory planning in real time.</span></span>

<span data-ttu-id="9027d-107">Une vue en temps réel précise du stock d'une organisation aide les collaborateurs du magasin à fournir un service client opportun et supérieur.</span><span class="sxs-lookup"><span data-stu-id="9027d-107">An accurate real-time view of inventory across an organization helps store associates provide timely, superior customer service.</span></span> <span data-ttu-id="9027d-108">Le moment qui importe est plus celui où le client est prêt à prendre une décision d'achat.</span><span class="sxs-lookup"><span data-stu-id="9027d-108">The moment that matters most is the moment when the customer is ready to make a purchase decision.</span></span> <span data-ttu-id="9027d-109">Il est important que les caissiers du magasin aient des informations en temps réel sur le stock au bout des doigts, de sorte qu'ils puissent promettre avec certitude la livraison et le prélèvement de produit.</span><span class="sxs-lookup"><span data-stu-id="9027d-109">It's important that cashiers in the store have real-time inventory information at their fingertips, so that they can accurately promise product delivery and pickup.</span></span>

<span data-ttu-id="9027d-110">Vous pouvez ouvrir la page **Recherche de stock** dans l'espace de travail **Retail Modern POS** ou l'espace de travail **Retail Cloud POS**.</span><span class="sxs-lookup"><span data-stu-id="9027d-110">You can open the **Inventory lookup** page from the **Retail Modern POS** workspace or the **Retail Cloud POS** workspace.</span></span>

![Mosaïque Recherche de stock dans la page d'accueil du PDV](media/POSHomepage.png)

<span data-ttu-id="9027d-112">Sur la page **Recherche de stock**, vous pouvez utiliser le clavier numérique pour entrer un numéro de produit.</span><span class="sxs-lookup"><span data-stu-id="9027d-112">On the **Inventory lookup** page, you can use the numeric keyboard to enter a product number.</span></span> <span data-ttu-id="9027d-113">Vous pouvez ensuite afficher la quantité disponible pour plusieurs magasins et entrepôts.</span><span class="sxs-lookup"><span data-stu-id="9027d-113">You can then view the on-hand quantity for multiple stores and warehouses.</span></span>

![Page Recherche de stock standard](media/InventoryLookUp.png)

<span data-ttu-id="9027d-115">Les quantités **Réservé** et **Commandé** sont également affichées pour chaque emplacement.</span><span class="sxs-lookup"><span data-stu-id="9027d-115">**Reserved** and **Ordered** quantities are also shown for each location.</span></span>

- <span data-ttu-id="9027d-116">**Réservé** – Cette quantité fait référence à la valeur **Physique réservé** des services administratifs pour le numéro de produit spécifié à l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="9027d-116">**Reserved** – This quantity refers to the **Physical reserved** value from the back office for the specified product number at the location.</span></span>
- <span data-ttu-id="9027d-117">**Commandé** – Cette quantité fait référence à la valeur **Total commandé** des services administratifs pour le numéro de produit spécifié à l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="9027d-117">**Ordered** – This quantity refers to the **Ordered in total** value from the back office for the specified product number at the location.</span></span>

## <a name="locations-that-inventory-availability-information-is-shown-for"></a><span data-ttu-id="9027d-118">Emplacements pour lesquels les informations de disponibilité de stock sont affichés</span><span class="sxs-lookup"><span data-stu-id="9027d-118">Locations that inventory availability information is shown for</span></span>

<span data-ttu-id="9027d-119">La liste des emplacements inclut deux types d'entités :</span><span class="sxs-lookup"><span data-stu-id="9027d-119">The list of locations includes two types of entities:</span></span>

- <span data-ttu-id="9027d-120">**Magasins** : la liste affiche les magasins configurés à l'aide du groupe de localisateurs de magasin pour le magasin actuel dans Headquarters.</span><span class="sxs-lookup"><span data-stu-id="9027d-120">**Stores** – The list shows stores that are configured by using the store locator group for the current store in the Headquarters.</span></span>
- <span data-ttu-id="9027d-121">**Centres de distribution** : différents types de centres de distribution (comme les entrepôts) peuvent être configurés dans Commerce.</span><span class="sxs-lookup"><span data-stu-id="9027d-121">**Distribution centers** – Various types of distribution centers (such as warehouses) can be configured in Commerce.</span></span> <span data-ttu-id="9027d-122">Toutefois, la liste affiche les informations de stock disponible uniquement pour les centres de distribution de type par défaut **Standard**.</span><span class="sxs-lookup"><span data-stu-id="9027d-122">However, the list shows inventory availability information only for distribution centers of the **Standard** default type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9027d-123">Les informations de stock disponible ne sont pas affichées pour les entrepôts de type **Transit**, **Contrôle**, et **Marchandises en route** du PDV.</span><span class="sxs-lookup"><span data-stu-id="9027d-123">Inventory availability information isn't shown for warehouses of the **Transit**, **Quarantine**, and **Goods in Route** types for the POS.</span></span>

<span data-ttu-id="9027d-124">Sur la page **Recherche de stock**, vous pouvez afficher les quantités disponibles à la vente (DAV) de chaque magasin, en plus des quantités disponibles actuelles, des quantités réservées, et des quantités commandées.</span><span class="sxs-lookup"><span data-stu-id="9027d-124">On the **Inventory lookup** page, you can view available to promise (ATP) quantities for each store, in addition to the current on-hand quantities, reserved quantities, and ordered quantities.</span></span> <span data-ttu-id="9027d-125">Sélectionnez le magasin pour afficher les informations DAV, puis sélectionnez **Afficher la disponibilité du magasin**.</span><span class="sxs-lookup"><span data-stu-id="9027d-125">Select the store to view the ATP information for, and then select **Show store availability**.</span></span>

![Quantités ATP](media/ATP.png)

## <a name="opening-the-dimension-based-matrix-view-to-show-all-variants"></a><span data-ttu-id="9027d-127">Ouverture de la vue Matrice basée sur les dimensions pour afficher toutes les variantes</span><span class="sxs-lookup"><span data-stu-id="9027d-127">Opening the Dimension based matrix view to show all variants</span></span>

<span data-ttu-id="9027d-128">Sur la page **Détails du produit** d'un produit générique, ou sur la page **Recherche de stock**, sélectionnez **Afficher toutes les variantes** sur la barre d'application en bas de la page.</span><span class="sxs-lookup"><span data-stu-id="9027d-128">On the **Product details** page of a product master, or on the **Inventory lookup** page, select **View all variants** from the app-bar at bottom of the page.</span></span> <span data-ttu-id="9027d-129">La vue **Matrice basée sur les dimensions** pour le lancement initial de ces pages affiche les informations de stock disponible pour toutes les variantes d'un produit pour le magasin actuel.</span><span class="sxs-lookup"><span data-stu-id="9027d-129">The **Dimension based matrix** view for the initial launch from these pages shows the inventory availability information for all variants of a product for the current store.</span></span>

> [!NOTE]
> <span data-ttu-id="9027d-130">Le bouton **Afficher toutes les variantes** est disponible uniquement pour les produits génériques d'article ayant des variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="9027d-130">The **View all variants** button is available only for item product masters that have product variants.</span></span> <span data-ttu-id="9027d-131">Il n'est pas disponible pour les produits ou les kits autonomes.</span><span class="sxs-lookup"><span data-stu-id="9027d-131">It isn't available for standalone products or kits.</span></span>

![Afficher tous les boutons de variantes sur la page Recherche de stock](media/StandardToMatrix.png)

<span data-ttu-id="9027d-133">Sélectionnez **Afficher toutes les variantes** sur la page **Détails du produit** d'un produit générique, ou sur la page **Recherche de stock**, sans sélectionner d'emplacement, pour accéder à la vue **Matrice basée sur les dimensions** pour afficher les informations de stock disponible de toutes les variantes d'un produit pour le magasin actuel.</span><span class="sxs-lookup"><span data-stu-id="9027d-133">Select **View all variants** on the **Product details** page of a product master, or on the **Inventory lookup** page, without selecting a location, to go to the **Dimension based matrix** view to view the inventory availability information for all variants of a product for the current store.</span></span>

![Vue de matrice basée sur les dimensions pour la page de recherche de stock](media/Matrix.png)

> [!NOTE]
> <span data-ttu-id="9027d-135">Dans l'illustration précédente, l'ordre d'affichage des dimensions était alphabétique, car l'ordre d'affichage des dimensions n'avait pas été configuré pour le produit sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9027d-135">In the preceding illustration, the display order of the dimensions is alphabetic, because the display order of dimensions wasn't configured for the selected product.</span></span>

<span data-ttu-id="9027d-136">Dans la vue **Matrice basée sur les dimensions**, les cellules des variantes de produit comprennent une valeur disponible dans le coin inférieur droit.</span><span class="sxs-lookup"><span data-stu-id="9027d-136">In the **Dimension based matrix** view, the cells for the product variants include an on-hand value in the lower-right corner.</span></span> <span data-ttu-id="9027d-137">Le tableau suivant explique la signification des différentes valeurs.</span><span class="sxs-lookup"><span data-stu-id="9027d-137">The following table explains the meaning of the various values.</span></span>

| <span data-ttu-id="9027d-138">Valeur disponible</span><span class="sxs-lookup"><span data-stu-id="9027d-138">On-hand value</span></span>                            | <span data-ttu-id="9027d-139">Description</span><span class="sxs-lookup"><span data-stu-id="9027d-139">Description</span></span> |
|------------------------------------------|-------------|
| <span data-ttu-id="9027d-140">Valeur numérique supérieure à 0 (zéro)</span><span class="sxs-lookup"><span data-stu-id="9027d-140">Numeric value that is more than 0 (zero)</span></span> | <span data-ttu-id="9027d-141">Une variante a été lancée à l'emplacement sélectionné, et vous pouvez exécuter des actions supplémentaires dans la cellule.</span><span class="sxs-lookup"><span data-stu-id="9027d-141">A variant has been released to the selected location, and you can perform additional actions in the cell.</span></span> <span data-ttu-id="9027d-142">(Ces actions sont décrites en détail plus loin dans cette rubrique.)</span><span class="sxs-lookup"><span data-stu-id="9027d-142">(These actions are described in more detail later in this topic.)</span></span> |
| <span data-ttu-id="9027d-143">**0** (zéro)</span><span class="sxs-lookup"><span data-stu-id="9027d-143">**0** (zero)</span></span>                             | <span data-ttu-id="9027d-144">Une variante a été lancée à l'emplacement sélectionné, mais l'article n'est pas disponible à l'emplacement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9027d-144">A variant has been released to the selected location, but the item isn't available in selected location.</span></span> <span data-ttu-id="9027d-145">Toutefois, vous pouvez exécuter des actions supplémentaires dans la cellule.</span><span class="sxs-lookup"><span data-stu-id="9027d-145">However, you can perform additional actions in the cell.</span></span> <span data-ttu-id="9027d-146">(Ces actions sont décrites en détail plus loin dans cette rubrique.)</span><span class="sxs-lookup"><span data-stu-id="9027d-146">(These actions are described in more detail later in this topic.)</span></span> |
| <span data-ttu-id="9027d-147">**s/o** ou une cellule inactive</span><span class="sxs-lookup"><span data-stu-id="9027d-147">**n/a** or an inactive cell</span></span>              | <span data-ttu-id="9027d-148">Aucune variante n'a été lancée à l'emplacement sélectionné, et vous ne pouvez pas exécuter des actions supplémentaires dans la cellule.</span><span class="sxs-lookup"><span data-stu-id="9027d-148">A variant hasn't been released to the selected location, and you can't perform additional actions in the cell.</span></span> |

<span data-ttu-id="9027d-149">Vous pouvez également modifier le tableau croisé dynamique pour les dimensions en sélectionnant la nouvelle dimension à utiliser.</span><span class="sxs-lookup"><span data-stu-id="9027d-149">You can also change the pivot for dimensions by selecting the new dimension to use.</span></span>

![Modification du tableau croisé dynamique](media/ChangePivot.png)

![Tableau croisé dynamique modifié](media/PivotChanged.png)

> [!NOTE]
> <span data-ttu-id="9027d-152">Dans les illustrations précédentes, l'ordre d'affichage des dimensions du produit sélectionné était personnalisé (non alphabétique).</span><span class="sxs-lookup"><span data-stu-id="9027d-152">In the preceding illustrations, the display order of the dimensions for the selected product is custom (non-alphabetic).</span></span> <span data-ttu-id="9027d-153">Il était basé sur l'ordre d'affichage des dimensions défini dans les services administratifs.</span><span class="sxs-lookup"><span data-stu-id="9027d-153">It's based on the dimension display order that is set in the back office.</span></span>

<span data-ttu-id="9027d-154">En outre, dans la vue **Matrice basée sur les dimensions**, d'autres actions peut être exécutées pour aider à amplifier la productivité d'un collaborateur du magasin.</span><span class="sxs-lookup"><span data-stu-id="9027d-154">Additionally, in the **Dimension based matrix** view, more actions can be performed to help boost a store associate's productivity.</span></span> <span data-ttu-id="9027d-155">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="9027d-155">Here are some examples:</span></span>

- <span data-ttu-id="9027d-156">Modifiez l'emplacement du magasin pour rechercher le stock disponible pour toutes les variantes de produit à d'autres emplacements.</span><span class="sxs-lookup"><span data-stu-id="9027d-156">Change the store location to look up the inventory availability of all product variants at other locations.</span></span> <span data-ttu-id="9027d-157">Ces emplacements incluent d'autres magasins du groupe de localisateurs de magasin et des centres de distribution de type par défaut **Standard**.</span><span class="sxs-lookup"><span data-stu-id="9027d-157">These locations include other stores in the store locator group and distribution centers of the **Standard** default type.</span></span>
- <span data-ttu-id="9027d-158">Vendez une variante de produit individuelle à un client à l'aide du paiement comptant sans livraison, du prélèvement en magasin, ou de l'expédition à une adresse.</span><span class="sxs-lookup"><span data-stu-id="9027d-158">Sell an individual product variant to a customer by using cash and carry, in-store pickup, or shipment to an address.</span></span>
- <span data-ttu-id="9027d-159">Fournissez au client des informations DAV pour une variante de produit individuelle à un emplacement spécifique.</span><span class="sxs-lookup"><span data-stu-id="9027d-159">Provide the customer with ATP information for an individual product variant at a specific location.</span></span>

![Actions supplémentaires sur les vignettes des variantes](media/VariantActions.png)

> [!NOTE]
> <span data-ttu-id="9027d-161">Dans l'illustration précédente, l'ordre d'affichage des dimensions était alphabétique, car l'ordre d'affichage des dimensions n'avait pas été configuré pour le produit sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9027d-161">In the preceding illustration, the display order of the dimensions is alphabetic, because the display order of dimensions wasn't configured for the selected product.</span></span>

<span data-ttu-id="9027d-162">Le tableau suivant fournit d'autres informations sur les actions supplémentaires disponibles.</span><span class="sxs-lookup"><span data-stu-id="9027d-162">The following table provides more information about the additional actions that are available.</span></span>

| <span data-ttu-id="9027d-163">Action</span><span class="sxs-lookup"><span data-stu-id="9027d-163">Action</span></span>               | <span data-ttu-id="9027d-164">Description</span><span class="sxs-lookup"><span data-stu-id="9027d-164">Description</span></span> |
|----------------------|-------------|
| <span data-ttu-id="9027d-165">Vendre maintenant</span><span class="sxs-lookup"><span data-stu-id="9027d-165">Sell now</span></span>             | <span data-ttu-id="9027d-166">Ajoutez la variante d'article sélectionnée à la transaction, et redirigez l'utilisateur vers l'écran de transaction.</span><span class="sxs-lookup"><span data-stu-id="9027d-166">Add the selected item variant to the transaction, and redirect the user to the transaction screen.</span></span> <span data-ttu-id="9027d-167">(Cette action n'est pas disponible lorsque l'emplacement sélectionné est un centre de distribution.)</span><span class="sxs-lookup"><span data-stu-id="9027d-167">(This action isn't available when the selected location is a distribution center.)</span></span> |
| <span data-ttu-id="9027d-168">Prélever dans un magasin</span><span class="sxs-lookup"><span data-stu-id="9027d-168">Pick up in store</span></span>     | <span data-ttu-id="9027d-169">Créez une commande client pour la variante de produit qui sera prélevée à l'emplacement sélectionné, et redirigez l'utilisateur vers l'écran de transaction.</span><span class="sxs-lookup"><span data-stu-id="9027d-169">Create a customer order for the product variant that will be picked up from the selected location, and redirect the user to the transaction screen.</span></span> <span data-ttu-id="9027d-170">(Cette action n'est pas disponible lorsque l'emplacement sélectionné est un centre de distribution.)</span><span class="sxs-lookup"><span data-stu-id="9027d-170">(This action isn't available when the selected location is a distribution center.)</span></span> |
| <span data-ttu-id="9027d-171">Expédier le produit</span><span class="sxs-lookup"><span data-stu-id="9027d-171">Ship product</span></span>         | <span data-ttu-id="9027d-172">Créez une commande client pour la variante de produit qui sera expédiée depuis l'emplacement sélectionné, et redirigez l'utilisateur vers l'écran de transaction.</span><span class="sxs-lookup"><span data-stu-id="9027d-172">Create a customer order for the product variant that will be shipped from the selected location, and redirect the user to the transaction screen.</span></span> |
| <span data-ttu-id="9027d-173">Disponibilité</span><span class="sxs-lookup"><span data-stu-id="9027d-173">Availability</span></span>         | <span data-ttu-id="9027d-174">Affichez des informations DAV pour la combinaison de variables sélectionnée pour l'emplacement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9027d-174">Show the ATP information for the selected variant combination for the selected location.</span></span> |
| <span data-ttu-id="9027d-175">Afficher tous les emplacements</span><span class="sxs-lookup"><span data-stu-id="9027d-175">Show all locations</span></span>   | <span data-ttu-id="9027d-176">Passez à la vue de recherche de stock standard, et mettez en surbrillance les informations de stock disponible pour la variante d'article dans tous les magasins du groupe de localisateurs de magasin, ainsi que dans les centres de distribution de type **Standard/Par défaut**.</span><span class="sxs-lookup"><span data-stu-id="9027d-176">Switch to the standard inventory lookup view, and highlight inventory availability information for the item variant across all stores in the store locator group, and also in distribution centers of the **Standard/Default** type.</span></span> |
| <span data-ttu-id="9027d-177">Afficher les détails du produit</span><span class="sxs-lookup"><span data-stu-id="9027d-177">View product details</span></span> | <span data-ttu-id="9027d-178">Redirigez l'utilisateur vers la page **Détails du produit** du produit générique associé.</span><span class="sxs-lookup"><span data-stu-id="9027d-178">Redirect the user to the **Product details** page of the associated product master.</span></span> |


[!INCLUDE[footer-include](../includes/footer-banner.md)]