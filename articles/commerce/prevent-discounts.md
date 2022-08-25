---
title: Options pour empêcher les remises pour les produits vendus au détail
description: Il existe plusieurs raisons pour lesquelles les détaillants ne souhaitent pas appliquer une remise à certains produits, à partir d’une promotion ou pendant la vente dans le PDV.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 85183
ms.assetid: e8c5a24f-7edd-4fd6-af80-5e0ac9f03127
ms.search.industry: Retail
ms.search.form: RetailPeriodicDiscount
ms.openlocfilehash: 803279282e98b926ae70351ced39157fa95792d9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269052"
---
# <a name="options-for-preventing-discounts-for-retail-products"></a>Options pour empêcher les remises pour les produits vendus au détail

[!include [banner](includes/banner.md)]

Il existe plusieurs raisons pour lesquelles les détaillants ne souhaitent pas appliquer une remise à certains produits, à partir d’une promotion ou pendant la vente dans le PDV.

Les options suivantes, disponibles dans l’onglet **Commerce** des produits lancés, permettent de configurer le produit pour empêcher l’ensemble des remises ou les remises manuelles. Les paramètres peuvent également être spécifiés au niveau de la catégorie à partir de la hiérarchie de catégorie.

- **Empêcher toutes les remises** : sélectionnez cette option pour empêcher tous les types de remises d’être appliqués à ce produit. Cela inclut les promotions telles que les remises mix and match, les remises sur quantité et les remises seuil, ainsi que les remises de ligne et de transaction manuelles qui sont appliquées pendant une vente par un utilisateur du PDV.
- **Empêcher les remises manuelles** : sélectionnez cette option pour empêcher uniquement les remises de ligne ou de transaction manuelles qui sont appliquées pendant une vente par un utilisateur du PDV. Les produits pour lesquels cette option est sélectionnée peuvent toujours bénéficier de promotions, comme les remises mix and match, les remises sur quantité et les remises seuil.

> [!NOTE]
> Ces paramètres ne limitent pas l’opération de remplacement de prix, car elle définit le prix de base et n’est pas considérée comme une remise.

[![Champ Empêcher les remises.](./media/prevent-discounts.png)](./media/prevent-discounts.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
