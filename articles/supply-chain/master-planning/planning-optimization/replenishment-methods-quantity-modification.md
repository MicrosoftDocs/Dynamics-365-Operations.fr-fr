---
title: Méthodes de réapprovisionnement et modification des quantités
description: Cette rubrique fournit des informations sur les méthodes de réapprovisionnement dans l’optimisation de la planification. Elle explique également comment la quantité de commandes multiples pour un produit affecte le résultat.
author: crytt
ms.date: 6/1/2021
ms.topic: article
ms.search.form: ReqGroup, ReqItemTable, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d5e0e671e624de2646a47647ef08d3567599b884
ms.sourcegitcommit: 4cbd83e21a78459e4711a2dedba0f5a7acc3c841
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261694"
---
# <a name="replenishment-methods-and-quantity-modification"></a>Méthodes de réapprovisionnement et modification des quantités

[!include [banner](../../includes/banner.md)]

Cette rubrique fournit des informations sur les méthodes de réapprovisionnement dans l’optimisation de la planification. Elle explique également comment la quantité de commandes multiples pour un produit affecte le résultat.

Les méthodes de réapprovisionnement sont également appelées méthodes de couverture et méthodes de calibrage.

## <a name="coverage-codes"></a>Codes de couverture

L’optimisation de la planification peut être configurée pour utiliser plusieurs méthodes de réapprovisionnement. Les méthodes de réapprovisionnement sont les techniques utilisées par le système pour calculer les besoins d’un produit. Les méthodes de réapprovisionnement sont définies par des codes de couverture que vous pouvez paramétrer sur le groupe de couverture ou sur le produit.

Les codes de couverture suivants peuvent être utilisés dans l’optimisation de la planification :

- **Période** : méthode de réapprovisionnement qui associe toutes les demandes pour une période en une commande du produit. La commande sera planifiée pour le premier jour de la période et sa quantité répondra aux besoins nets pendant la période définie. La période commence avec la première demande du produit et couvre la plage de temps définie. La période suivante commencera avec les prochains besoins du produit. Le code de couverture *Période* est souvent utilisé pour les épuisements de stock non prévisibles, les produits influencés par la saison ou les produits à coût élevé. L’illustration suivante présente un exemple.

    ![Exemple d’utilisation du code de couverture Période](./media/coverage-code-period.png "Exemple d’utilisation du code de couverture Période")

- **Besoin** : méthode de réapprovisionnement dans laquelle le système crée un ordre de fabrication, de transfert ou d’achat planifié selon les besoins du produit. Cette méthode est utilisée pour les produits coûteux qui ont une demande intermittente. Le code de couverture *Besoin* est souvent utilisé pour les produits configurables ou les scénarios de fabrication sur commande. L’illustration suivante présente un exemple.

    ![Exemple d’utilisation du code de couverture Besoin](./media/coverage-code-requirement.png "Exemple d’utilisation du code de couverture Besoin")

- **Min./max.**  : La méthode de réapprovisionnement est basée sur le niveau des stocks. Elle définit le réapprovisionnement du stock jusqu’à un niveau spécifique lorsque le niveau de stock disponible prévu est inférieur à un seuil spécifique. La quantité de réapprovisionnement sera la différence entre le niveau maximum et le niveau disponible prévisionnel. Le code de couverture *Min./Max.* est souvent utilisé pour les épuisements de stock prévisibles, les produits les plus demandés ou les produits moins coûteux. L’illustration suivante présente un exemple.

    ![Exemple d’utilisation du code de couverture Min./Max.](./media/coverage-code-min-max.png "Exemple d’utilisation du code de couverture Min./Max.")

- **Manuel** : dans la méthode de réapprovisionnement, le système ne suggère pas d’ordres de fabrication, de transfert ou d’achat pour le produit. Au lieu de cela, le planificateur du produit est responsable de la création des commandes requises pour le réapprovisionnement du produit. Le code de couverture *Manuel* est souvent utilisé pour les produits pour lesquels les ordres planifiés générés par le système ne sont pas souhaitables.

## <a name="impact-of-the-order-quantity-from-default-order-settings"></a>Impact de la quantité de commande à partir des paramètres de commande par défaut

Sur la page **Paramètre de commande par défaut** pour un produit lancé, vous pouvez spécifier chacun des paramètres de quantité suivants sur les raccourcis **Commande fournisseur**, **Stock** et **Commande client**. (Le raccourci **Stock** sert à la fois pour les ordres de transfert et les ordres de fabrication.)

- **Multiple** : les commandes planifiées seront un multiple de cette quantité.

    Par exemple, si le champ **Multiple** est défini sur *5*, une commande peut concerner une quantité de 5, 10, 15, 20, et ainsi de suite.

- **Quantité de commande min.**  : les commandes planifiées ne seront pas inférieures à la valeur spécifiée.

    Par exemple, si le champ **Quantité de commande min.** est défini sur *10*, une commande planifié pour une quantité de 10 sera créée, même s’il ne faut que quatre articles pour satisfaire la demande.

- **Quantité de commande max.**  : les commandes planifiées ne seront pas supérieures à la valeur spécifiée. Si la demande est supérieure à la valeur **Quantité de commande max.**, plusieurs commandes planifiées seront créées pour la couvrir.

    Par exemple, si le champ **Quantité de commande max.** est défini sur *100* et que la demande est de 450, quatre commandes planifiées pour une quantité de 100 et une commande planifiée pour une quantité de 50 seront créées.

## <a name="examples-of-replenishment-that-use-the-minmax-coverage-code"></a>Exemples de réapprovisionnement utilisant le code de couverture Min./Max.

Si vous ne spécifiez pas de valeur dans le champ **Multiple** d’un produit sur la page **Paramètre de commande par défaut**, et si vous utilisez la méthode de réapprovisionnement *Min./Max.* l’optimisation de la planification réapprovisionnera le stock jusqu’à un niveau spécifique lorsque le niveau de stock disponible prévu est inférieur à un seuil spécifique.

Si vous définissez une quantité multiple pour un produit, la méthode de réapprovisionnement *Min./Max.* modifiera son comportement et prendra en compte la valeur **Multiple**.

En d’autres termes, l’optimisation de la planification réapprovisionnera toujours le stock jusqu’au niveau maximum défini lorsque le niveau de stock prévu est inférieur au niveau minimum défini. Cependant, la quantité de réapprovisionnement doit être un multiple de la valeur **Multiple**.

Si la quantité de réapprovisionnement (la différence entre le niveau maximum et le niveau de stock prévu) n’est pas un multiple de la quantité multiple définie, l’optimisation de la planification utilisera la première valeur possible qui, avec le niveau de stock prévu, sera inférieure au niveau maximal. Si la somme est inférieure au niveau minimum, l’optimisation de la planification utilisera la première valeur qui, avec le stock prévu, sera supérieure au niveau maximum.

Les sous-sections suivantes fournissent quelques exemples qui montrent comment la quantité de commande multiple d’un produit affecte le résultat de la méthode de réapprovisionnement *Min./Max.*.

### <a name="example-1"></a>Exemple 1

Un produit a la configuration suivante :

- **Code de couverture :** *Min./Max.*
- **Minimum :** *15*
- **Maximum :** *22*
- **Multiple :** *0*

Il y a 10 pièces en stock pour le produit, et il n’y a pas d’autre demande ou offre.

Lors de l’exécution de la planification générale, une commande planifiée de 12 pièces est créée pour réapprovisionner le stock à la quantité maximale.

### <a name="example-2"></a>Exemple 2

Un produit a la configuration suivante :

- **Code de couverture :** *Min./Max.*
- **Minimum :** *15*
- **Maximum :** *22*
- **Multiple :** *5*

Il y a 10 pièces en stock pour le produit, et il n’y a pas d’autre demande ou offre.

Lors de l’exécution de la planification générale, une commande planifiée de 10 pièces est créée (car 15 pièces de réapprovisionnement plus 10 pièces de stock disponible dépasseront la quantité maximale).

### <a name="example-3"></a>Exemple 3

Un produit a la configuration suivante :

- **Code de couverture :** *Min./Max.*
- **Minimum :** *21*
- **Maximum :** *24*
- **Multiple :** *5*

Il y a 10 pièces en stock pour le produit, et il n’y a pas d’autre demande ou offre.

Lors de l’exécution de la planification générale, une commande planifiée de 15 pièces est créée (car 10 pièces de réapprovisionnement plus 10 pièces de stock disponible seront inférieures à la quantité minimale).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
