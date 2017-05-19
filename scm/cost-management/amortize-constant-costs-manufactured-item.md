---
title: "Amortissement des coûts constants pour un article fabriqué"
description: "Les coûts constants d&quot;un article fabriqué reflètent les temps de réglage de l&quot;opération et les composants pour lesquels la quantité est constante ou la quantité de rebut est constante."
author: YuyuScheller
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcTable, BOMCalcTrans
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 274503
ms.assetid: 535ab25d-a031-4e8c-84ec-478f2987a1ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 1f849e05a6d68cbfb95849ad6e8b34c599716c50
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="amortize-constant-costs-for-a-manufactured-item"></a>Amortissement des coûts constants pour un article fabriqué

[!include[banner](../includes/banner.md)]


Les coûts constants d'un article fabriqué reflètent les temps de réglage de l'opération et les composants pour lesquels la quantité est constante ou la quantité de rebut est constante. 

Le concept de taille du lot d'évaluation des coûts permet d'amortir ces coûts constants dans le coût calculé d'un article fabriqué. Ce concept a plusieurs synonymes, notamment celui de taille de lot comptable. Le concept d'amortissement des coûts constants a également plusieurs synonymes, notamment celui de coûts constants proportionnels.
La quantité d'une taille de lot d'évaluation des coûts pour un article fabriqué est utilisée dans un calcul de nomenclature. La quantité dépend de la méthode d'initiation et d'exécution du calcul de nomenclature, comme illustré ci-après :
-   Quantité de calcul par défaut dans le calcul de nomenclature d'un article : la quantité de commande standard de l'article pour le stock fait office de taille du lot d'évaluation des coûts, mais la valeur par défaut peut être égale à une quantité supérieure afin de refléter la quantité multiple de commande de l'article. La quantité commandée standard de l'article et la quantité multiple peuvent être définies dans les paramètres de commande par défaut ou dans les paramètres de commande spécifiques au site.
-   Quantité de calcul spécifiée dans le calcul de nomenclature d'un article : la quantité de calcul spécifiée fait office de taille du lot d'évaluation des coûts pour l'article. Au départ, la quantité de calcul utilise la quantité de commande standard de l'article, mais la valeur par défaut peut être remplacée manuellement. La quantité de commande spécifiée représente la taille du lot d'évaluation des coûts pour l'article spécifié ainsi que pour les composants fabriqués dont la ligne de nomenclature est du type production. Cela est dû au fait que le composant est censé être produit en quantité exacte. La taille du lot d'évaluation des coûts pour les autres composants fabriqués dont la ligne de nomenclature est du type article reflètera leur quantité de commande standard.
-   Quantité de calcul de fabrication à la commande spécifiée dans le calcul de nomenclature d'un article : la quantité de calcul spécifiée fait office de taille du lot d'évaluation des coûts pour l'article et ses composants fabriqués lorsque les calculs de nomenclature utilisent un mode d'éclatement de fabrication à la commande. Les composants fabriqués sont censés être produits en quantité exacte, comme un composant fabriqué dont la ligne de nomenclature est du type production.
-   Quantité de calcul spécifiée dans un calcul de nomenclature spécifique à une commande : un calcul de nomenclature spécifique à une commande peut être réalisé pour une ligne d'une commande client, d'un devis de vente ou d'une commande de service. Par défaut, la quantité de calcul spécifiée utilise la quantité de la ligne d'origine, mais la quantité par défaut peut être remplacée. Vous pouvez décider que le calcul de nomenclature spécifique à une commande utilise un mode d'éclatement de fabrication à la commande ou à plusieurs niveaux.

Le montant calculé des coûts constants amortis d'un article fabriqué est appelé frais.






