---
title: Ajustements de prix et remises
description: "Cet articles associées des informations sur les ajustements de prix et des remises dans la vente au détail et le commerce dans Microsoft Dynamics 365 pour les opérations."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 01f249cbdabc6febf23dcd7103d4587cecdaad08
ms.lasthandoff: 03/31/2017


---

# <a name="price-adjustments-and-discounts"></a>Ajustements de prix et remises

Cet articles associées des informations sur les ajustements de prix et des remises dans la vente au détail et le commerce dans Microsoft Dynamics 365 pour les opérations.

Dans Dynamics 365 pour les opérations - au détail, vous pouvez effectuer des ajustements de prix des produits, et pouvez également paramétrer des remises appliquées à une ligne ou une transaction au point de vente (POS), dans une commande client de centre d'appels, ou dans un ordre en ligne. Tant les ajustements de prix que les remises peuvent être liés à des groupes de prix. Pour les ajustements de prix et les remises, vous pouvez spécifier une date de début et une date de fin uniques ou une période récurrente, un code remise et quelques attributs supplémentaires. Les ajustements de prix et les remises peuvent être appliqués aux produits, variantes ou catégories. Si plusieurs remises s'appliquent à un produit, un client peut recevoir une des remises ou une remise combinée, selon la configuration de la remise. Dynamics 365 pour les opérations applique automatiquement l'escompte ou une combinaison de remises qui fournissent le meilleur prix au client. Lorsque vous paramétrez un ajustement de prix ou une remise, veillez à confirmer que les groupes de prix sont affectés aux canaux, catalogues, affiliations ou programmes de fidélité appropriés auxquels vous souhaitez appliquer la remise. En outre, si vous souhaitez générer automatiquement l'ID remise, définissez des souches de numéros dans la page **Paramètres des ventes au détail** avant de définir un nouvel ajustement de prix ou une nouvelle remise. **Remarque :** vous pouvez supprimer un ajustement de prix ou une remise. Toutefois, les informations statistiques sont perdues.

### <a name="types-of-discounts"></a>Types de remises

Il existe quatre types de remises de vente au détail :

-   **Remise simple** – Un pourcentage ou montant individuel.
-   **Remise sur quantité** – Une remise est appliquée lorsqu'au moins deux produits sont achetés.
-   **Remise mix and match** – Une remise est appliquée lorsqu'une combinaison spécifique de produits est achetée.
-   **Remise seuil** – Une remise est appliquée lorsque le total de la transaction est supérieur à un montant spécifié.

Tant les ajustements de prix que les remises peuvent être associés à des groupes de prix. Les groupes de prix peuvent ensuite être associés à des canaux, catalogues, affiliations et programmes de fidélité.


