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
ms.openlocfilehash: c9d3e7af95dffddfddc34059d93a2a5a350d08e5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "346063"
---
# <a name="options-for-preventing-discounts-for-retail-products"></a>Options pour empêcher les remises pour les produits vendus au détail

[!include [banner](includes/banner.md)]

Il existe plusieurs raisons pour lesquelles les détaillants ne souhaitent pas appliquer une remise à certains produits, à partir d'une promotion ou pendant la vente dans le PDV.

Les options suivantes, disponibles dans l'onglet **Vente au détail** des produits lancés, permettent de configurer le produit pour empêcher l'ensemble des remises ou les remises manuelles. Les paramètres peuvent également être spécifiés au niveau de la catégorie à partir de la hiérarchie des catégories de vente au détail.

- **Empêcher toutes les remises** : sélectionnez cette option pour empêcher tous les types de remises d'être appliqués à ce produit. Cela inclut les promotions telles que les remises mix and match, les remises sur quantité et les remises seuil, ainsi que les remises de ligne et de transaction manuelles qui sont appliquées pendant une vente par un utilisateur du PDV.
- **Empêcher les remises manuelles** : sélectionnez cette option pour empêcher uniquement les remises de ligne ou de transaction manuelles qui sont appliquées pendant une vente par un utilisateur du PDV. Les produits pour lesquels cette option est sélectionnée peuvent toujours bénéficier de promotions, comme les remises mix and match, les remises sur quantité et les remises seuil.

> [!NOTE]
> Ces paramètres ne limitent pas l'opération de remplacement de prix, car elle définit le prix de base et n'est pas considérée comme une remise.

[![champ Empêcher les remises](./media/prevent-discounts.png)](./media/prevent-discounts.png)
