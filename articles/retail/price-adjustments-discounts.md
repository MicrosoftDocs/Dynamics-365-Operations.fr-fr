---
title: Ajustements de prix et remises
description: Cet article fournit des informations sur les ajustements de prix et les remises dans Microsoft Dynamics 365 for Retail.
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 61ac8e5fbdc4d91bb5bc5372a7fb96633043473a
ms.contentlocale: fr-fr
ms.lasthandoff: 01/04/2019

---

# <a name="price-adjustments-and-discounts"></a>Ajustements de prix et remises

[!include [banner](includes/banner.md)]

Cet article fournit des informations sur les ajustements de prix et les remises dans Microsoft Dynamics 365 for Retail.

Dans Dynamics 365 for Retail, vous pouvez procéder à des ajustements de prix des produits, et aussi définir des remises à appliquer à une ligne ou une transaction au point de vente, dans une commande client du centre d'appels ou dans une commande en ligne. Tant les ajustements de prix que les remises peuvent être liés à des groupes de prix. Pour les ajustements de prix et les remises, vous pouvez spécifier une date de début et une date de fin uniques ou une période récurrente, un code remise et quelques attributs supplémentaires. Les ajustements de prix et les remises peuvent être appliqués aux produits, variantes ou catégories. Si plusieurs remises s'appliquent à un produit, un client peut recevoir une des remises ou une remise combinée, selon la configuration de la remise. Dynamics 365 for Retail applique automatiquement la remise ou une combinaison de remises qui fournit le meilleur prix au client. Lorsque vous paramétrez un ajustement de prix ou une remise, veillez à confirmer que les groupes de prix sont affectés aux canaux, catalogues, affiliations ou programmes de fidélité appropriés auxquels vous souhaitez appliquer la remise. En outre, si vous souhaitez générer automatiquement l'ID remise, définissez des souches de numéros dans la page **Paramètres des ventes au détail** avant de définir un nouvel ajustement de prix ou une nouvelle remise.

> [!NOTE]
> Vous pouvez supprimer un ajustement de prix ou une remise. Toutefois, les informations statistiques sont perdues.

## <a name="types-of-discounts"></a>Types de remises

Il existe quatre types de remises de vente au détail :

- **Remise simple** – Un pourcentage ou montant individuel.
- **Remise sur quantité** – Une remise est appliquée lorsqu'au moins deux produits sont achetés.
- **Remise mix and match** – Une remise est appliquée lorsqu'une combinaison spécifique de produits est achetée.
- **Remise seuil** – Une remise est appliquée lorsque le total de la transaction est supérieur à un montant spécifié.

Tant les ajustements de prix que les remises peuvent être associés à des groupes de prix. Les groupes de prix peuvent ensuite être associés à des canaux, catalogues, affiliations et programmes de fidélité.

