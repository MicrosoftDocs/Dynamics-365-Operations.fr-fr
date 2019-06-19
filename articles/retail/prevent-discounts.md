---
title: Options pour empêcher les remises pour les produits vendus au détail
description: Il existe plusieurs raisons pour lesquelles les détaillants ne souhaitent pas appliquer une remise à certains produits, à partir d'une promotion ou pendant la vente dans le PDV.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85183
ms.assetid: e8c5a24f-7edd-4fd6-af80-5e0ac9f03127
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 64f54c1a63706ccd9225d47df96ffc3f88cf3332
ms.sourcegitcommit: e2fb0846fcc6298050a0ec82c302e5eb5254e0b5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2019
ms.locfileid: "1606916"
---
# <a name="options-for-preventing-discounts-for-retail-products"></a><span data-ttu-id="57c8a-103">Options pour empêcher les remises pour les produits vendus au détail</span><span class="sxs-lookup"><span data-stu-id="57c8a-103">Options for preventing discounts for retail products</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="57c8a-104">Il existe plusieurs raisons pour lesquelles les détaillants ne souhaitent pas appliquer une remise à certains produits, à partir d'une promotion ou pendant la vente dans le PDV.</span><span class="sxs-lookup"><span data-stu-id="57c8a-104">There are various reasons why retailers may want to prevent some products from being discounted, either from a promotion or during the sale at the POS.</span></span>

<span data-ttu-id="57c8a-105">Les options suivantes, disponibles dans l'onglet **Vente au détail** des produits lancés, permettent de configurer le produit pour empêcher l'ensemble des remises ou les remises manuelles.</span><span class="sxs-lookup"><span data-stu-id="57c8a-105">The following options, which can be found on the **Retail** tab of released products, will allow the product to be configured to prevent all or manual discounts.</span></span> <span data-ttu-id="57c8a-106">Les paramètres peuvent également être spécifiés au niveau de la catégorie à partir de la hiérarchie des catégories de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="57c8a-106">The settings can also be specified at the category level from the retail category hierarchy.</span></span>

- <span data-ttu-id="57c8a-107">**Empêcher toutes les remises** : sélectionnez cette option pour empêcher tous les types de remises d'être appliqués à ce produit.</span><span class="sxs-lookup"><span data-stu-id="57c8a-107">**Prevent all discounts** – Select this option to prevent all types of discounts from being applied to this product.</span></span> <span data-ttu-id="57c8a-108">Cela inclut les promotions telles que les remises mix and match, les remises sur quantité et les remises seuil, ainsi que les remises de ligne et de transaction manuelles qui sont appliquées pendant une vente par un utilisateur du PDV.</span><span class="sxs-lookup"><span data-stu-id="57c8a-108">This includes promotions such as mix and match, quantity and threshold discounts, as well as manual line and transaction discounts that are applied during a sale by a POS user.</span></span>
- <span data-ttu-id="57c8a-109">**Empêcher les remises manuelles** : sélectionnez cette option pour empêcher uniquement les remises de ligne ou de transaction manuelles qui sont appliquées pendant une vente par un utilisateur du PDV.</span><span class="sxs-lookup"><span data-stu-id="57c8a-109">**Prevent manual discounts** – Select this option to only prevent the manual line or transaction discounts that are applied during a sale by a POS user.</span></span> <span data-ttu-id="57c8a-110">Les produits pour lesquels cette option est sélectionnée peuvent toujours bénéficier de promotions, comme les remises mix and match, les remises sur quantité et les remises seuil.</span><span class="sxs-lookup"><span data-stu-id="57c8a-110">Products with this option selected are still eligible for promotions, such as mix and match and quantity and threshold discounts.</span></span>

> [!NOTE]
> <span data-ttu-id="57c8a-111">Ces paramètres ne limitent pas l'opération de remplacement de prix, car elle définit le prix de base et n'est pas considérée comme une remise.</span><span class="sxs-lookup"><span data-stu-id="57c8a-111">These settings do not restrict the price override operation, because that sets the base price and is not treated as a discount.</span></span>

<span data-ttu-id="57c8a-112">[![Champ Empêcher les remises](./media/prevent-discounts.png)](./media/prevent-discounts.png)</span><span class="sxs-lookup"><span data-stu-id="57c8a-112">[![Prevent discounts field](./media/prevent-discounts.png)](./media/prevent-discounts.png)</span></span>
