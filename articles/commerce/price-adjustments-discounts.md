---
title: Ajustements de prix et remises
description: Cet article offre des informations relatives aux ajustements de prix et aux rabais dans Dynamics 365 Commerce.
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
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
ms.openlocfilehash: dfaacfa7681258e3b2273083017c0c398d566651
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022568"
---
# <a name="price-adjustments-and-discounts"></a>Ajustements de prix et remises

[!include [banner](includes/banner.md)]

Cet article offre des informations relatives aux ajustements de prix et aux rabais dans Dynamics 365 Commerce.

Dans Commerce, procédez des ajustements de prix sur les produits et paramétrez des remises appliquées à une ligne ou une transaction au point de vente (PDV), au niveau d'une commande client enregistrée par un centre d'appels ou au niveau d'une commande en ligne. Tant les ajustements de prix que les remises peuvent être liés à des groupes de prix. Pour les ajustements de prix et les remises, vous pouvez spécifier une date de début et une date de fin uniques ou une période récurrente, un code remise et quelques attributs supplémentaires. 

Les ajustements de prix et les remises peuvent être appliqués aux produits, variantes ou catégories. Si plusieurs remises s'appliquent à un produit, un client peut recevoir une des remises ou une remise combinée, selon la configuration de la remise. Commerce applique automatiquement la remise ou une combinaison de remises qui fournit le meilleur prix au client. Lorsque vous paramétrez un ajustement de prix ou une remise, veillez à confirmer que les groupes de prix sont affectés aux canaux, catalogues, affiliations ou programmes de fidélité appropriés auxquels vous souhaitez appliquer la remise. En outre, si vous souhaitez générer automatiquement l'ID de remise, configurez les souches de numéros dans la page **Paramètres de commerce** avant de définir un nouvel ajustement de prix ou une nouvelle remise.

> [!NOTE]
> Vous pouvez supprimer un ajustement de prix ou une remise. Toutefois, les informations statistiques sont perdues.

## <a name="types-of-discounts"></a>Types de remises

Il existe 4 types de remise :

- **Remise simple** – Un pourcentage ou montant individuel.
- **Remise sur quantité** – Une remise est appliquée lorsqu'au moins deux produits sont achetés.
- **Remise mix and match** – Une remise est appliquée lorsqu'une combinaison spécifique de produits est achetée.
- **Remise seuil** – Une remise est appliquée lorsque le total de la transaction est supérieur à un montant spécifié.

Tant les ajustements de prix que les remises peuvent être associés à des groupes de prix. Les groupes de prix peuvent ensuite être associés à des canaux, catalogues, affiliations et programmes de fidélité.