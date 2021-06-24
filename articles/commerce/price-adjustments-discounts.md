---
title: Ajustements de prix et remises
description: Cet article offre des informations relatives aux ajustements de prix et aux rabais dans Dynamics 365 Commerce.
author: scott-tucker
ms.date: 06/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 44c03ae0a04d648e788a72d8f6dcc3671c5736c7
ms.sourcegitcommit: 7c9d6be464db058511df9cb6ba162d21dc0554e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/11/2021
ms.locfileid: "6240940"
---
# <a name="price-adjustments-and-discounts"></a>Ajustements de prix et remises

[!include [banner](includes/banner.md)]

Cet article offre des informations relatives aux ajustements de prix et aux rabais dans Dynamics 365 Commerce.

Dans Commerce, procédez des ajustements de prix sur les produits et paramétrez des remises appliquées à une ligne ou une transaction au point de vente (PDV), au niveau d’une commande client enregistrée par un centre d’appels ou au niveau d’une commande en ligne. Tant les ajustements de prix que les remises peuvent être liés à des groupes de prix. Pour les ajustements de prix et les remises, vous pouvez spécifier une date de début et une date de fin uniques ou une période récurrente, un code remise et quelques attributs supplémentaires. 

Les ajustements de prix et les remises peuvent être appliqués aux produits, variantes ou catégories. Si plusieurs remises s’appliquent à un produit, un client peut recevoir une des remises ou une remise combinée, selon la configuration de la remise. Commerce applique automatiquement la remise ou une combinaison de remises qui fournit le meilleur prix au client. Lorsque vous paramétrez un ajustement de prix ou une remise, veillez à confirmer que les groupes de prix sont affectés aux canaux, catalogues, affiliations ou programmes de fidélité appropriés auxquels vous souhaitez appliquer la remise. En outre, si vous souhaitez générer automatiquement l’ID de remise, configurez les souches de numéros dans la page **Paramètres de commerce** avant de définir un nouvel ajustement de prix ou une nouvelle remise.

> [!NOTE]
> Vous pouvez supprimer un ajustement de prix ou une remise. Toutefois, les informations statistiques sont perdues.

## <a name="types-of-discounts"></a>Types de remises

Il existe plusieurs types de remise :

- **Remise simple** – Un pourcentage ou montant individuel.
- **Remise sur quantité** – Une remise est appliquée lorsqu’au moins deux produits sont achetés.
- **Remise mix and match** – Une remise est appliquée lorsqu’une combinaison spécifique de produits est achetée.
- **Remise seuil** – Une remise est appliquée lorsque le total de la transaction est supérieur à un montant spécifié.
- **Remise sur appel d’offres** – Remise appliquée lorsque le total de la transaction est supérieur à un montant spécifié et qu’un type de paiement spécifique (par exemple, espèces, carte de crédit ou de débit) est utilisé pour le paiement.
- **Remise sur l’expédition** – Une remise qui est appliquée lorsque le total de la transaction est supérieur à un montant spécifié et qu’un mode de livraison spécifique (par exemple, expédition sous deux jours ou livraison le lendemain) est utilisé sur la commande.

Tant les ajustements de prix que les remises peuvent être associés à des groupes de prix. Les groupes de prix peuvent ensuite être associés à des canaux, catalogues, affiliations et programmes de fidélité.

> [!NOTE]
> La remise mix and match et la remise seuil ont des propriétés nommées respectivement « Compter les produits non sujets à remise » et « Compter les produits non sujets à remise dans le seuil ». Si ces propriétés sont activées, un article qui n’est éligible à aucune remise peut toujours aider à qualifier une transaction pour la remise, mais l’article non éligible ne bénéficiera pas de la remise. 
> 
> Par exemple, si vous créez une remise mix and match avec deux lignes, A et B, où un client devrait bénéficier d’une remise de 10 % sur les deux articles, mais que la configuration « Empêcher toutes les remises » est cochée pour l’article A, cela empêchera généralement l’article A d’être inclus dans la remise. Cependant, si la propriété « Compter les produits non sujets à remise » est activée, l’article A peut être utilisé pour bénéficier de la remise mix and match, mais la remise de 10 % ne sera appliquée qu’à l’article B. Une logique similaire s’applique à la remise seuil. 
>
> Cependant, la propriété « Compter les produits non sujets à remise dans le seuil » présente une possibilité supplémentaire par rapport à la propriété « Compter les produits non sujets à remise » des remises mix and match. Si la remise seuil est activée et s’il existe un article qui a une remise existante qui empêcherait l’article de bénéficier d’autres remises, alors le prix payé pour cet article permettrait d’atteindre le seuil, mais cet article n’obtiendra pas la remise supplémentaire.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
