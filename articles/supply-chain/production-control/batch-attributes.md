---
title: Attributs de lot
description: "Cette rubrique fournit des informations sur les attributs de lot. Les attributs de lot sont des caractéristiques de matières premières et de produits finis qui constituent des lots de stock. La rubrique décrit également les manières d'affecter des attributs de lot et d'y effectuer une recherche lorsque vous réservez des traitements par lots."
author: YuyuScheller
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PdsBatchAttrib, PdsBatchAttribAssociate, PdsBatchAttribByAttribGroup, PdsBatchAttribByItem, PdsBatchAttribByitemCustomer, PdsBatchAttribGroup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19271
ms.assetid: 41de0250-4a96-412e-a412-aa06615b6b1d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6c18b007a72686b1ede69b750e930d72e86f0aba
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="batch-attributes"></a>Attributs de lot

[!include[banner](../includes/banner.md)]


Cette rubrique fournit des informations sur les attributs de lot. Les attributs de lot sont des caractéristiques de matières premières et de produits finis qui constituent des lots de stock. La rubrique décrit également les manières d'affecter des attributs de lot et d'y effectuer une recherche lorsque vous réservez des traitements par lots.

Les attributs de lot sont des caractéristiques de matières premières et de produits finis qui constituent des lots de stock. Les attributs de lot peuvent varier en fonction de plusieurs facteurs, comme les conditions environnementales, la qualité des matières premières utilisées pour produire le lot ou le résultat du produit fini. Le nombre et les types d'attributs de lot utilisés peuvent fortement varier d'un secteur à l'autre. Voici deux exemples d'utilisation d'attributs de lot :

-   Dans l'industrie fromagère, le lait, une des matières premières utilisées dans la production de fromage, peut disposer d'attributs tels que la teneur en matière grasse et le pourcentage en masse. D'autres attributs, comme l'humidité et la maturité, peuvent s'ajouter au fromage fabriqué à partir du lait.
-   Dans l'industrie sidérurgique, les attributs du fer produit peuvent correspondre aux pourcentages de contenu en magnésium, argent et zinc.

Pour mieux gérer le nombre et les types d'attributs, vous pouvez utiliser des groupes d'attributs de lot. Ainsi, il n'est pas nécessaire d'ajouter chaque attribut individuellement.

## <a name="assign-batch-attributes"></a>Affecter des attributs de lot
Vous pouvez affecter des attributs de lot à différents produits dans des lots de stock ou à des produits liés à des clients spécifiques. Pour pouvoir affecter un attribut de lot au niveau du client, vous devez d'abord l'affecter au niveau du produit. La dimension de lot du produit doit être définie sur **Actif** dans le groupe de dimensions de suivi. Pour affecter un attribut de lot à un produit individuel, utilisez la page spécifique au produit. Si l'attribut est spécifique à un produit pour un client, utilisez la page spécifique au client. Lorsque vous ajoutez un attribut à un produit, vous définissez également d'autres paramètres. Voici quelques exemples :

-   Les plages Minimum et Maximum d'un attribut de type **Entier** ou **Fraction**.
-   Les actions de tolérance d'un attribut du type **Entier** ou **Fraction**. Si la valeur de l'attribut n'est pas comprise dans la plage Minimum et Maximum, l'action peut être un message d'avertissement ou un message d'erreur.
-   La valeur cible de l'attribut. Cette valeur est la valeur optimale de l'attribut et s'applique à tous les types d'attributs.

Vous pouvez accéder aux pages des produits que vous sélectionnez dans la page **Produits lancés** dans Gestion des informations sur les produits. Après avoir affecté des attributs de lot à un produit, vous pouvez ajouter des valeurs spécifiques aux attributs dans la page **Attributs de lot de stock**.

## <a name="reserve-batches"></a>Réservation de lots
Vous pouvez effectuer une recherche dans les attributs de lot lorsque vous effectuez des réservations de lot pour une commande client pour honorer la commande d'un client, ou lorsque vous prélevez et réservez des lots pour un ordre de fabrication. La recherche permet de trouver un lot de stock qui contient le produit présentant l'attribut de lot souhaité. Une fois le ou les lots trouvés, vous pouvez réserver le produit dans la ligne de mouvement de stock d'origine.




