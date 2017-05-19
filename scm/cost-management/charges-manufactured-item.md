---
title: "Affichage des frais pour un article fabriqué"
description: "Les coûts constants d&quot;un article fabriqué reflètent les temps de réglage de l&quot;opération et les composants pour lesquels la quantité est constante ou la quantité de rebut est constante."
author: YuyuScheller
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 274483
ms.assetid: 6f5b851b-c5a7-43ef-b380-0d316667c1ef
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 119f49d9456c49b1e010da1e0b2c52e369164344
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="display-charges-for-a-manufactured-item"></a>Affichage des frais pour un article fabriqué

[!include[banner](../includes/banner.md)]


Les coûts constants d'un article fabriqué reflètent les temps de réglage de l'opération et les composants pour lesquels la quantité est constante ou la quantité de rebut est constante.

Le montant calculé des frais d'un article peut être affiché avec les coûts unitaires de l'article. Toutefois, les frais s'affichent parfois dans des champs distincts et ne sont pas inclus dans les coûts unitaires de l'article. Lorsque les frais s'affichent dans des champs distincts, un premier champ affiche le montant total des frais et un second champ affiche la taille du lot d'évaluation des coûts utilisée pour amortir le montant. Par exemple, la page Prix de l'article affiche les frais dans deux champs séparés. En revanche, la page Complet affiche le coût total de l'article par unité, et les coûts amortis sont inclus dans les coûts unitaires.
Les frais d'un article fabriqué sont toujours inclus dans le coût unitaire à des fins de coûts standard. Ils peuvent éventuellement être inclus à des fins de coûts planifiés. Une stratégie dans la version d'évaluation des coûts applique l'inclusion des frais dans le coût d'un article fabriqué. Lorsque vous activez l'enregistrement des coûts d'un article, les frais pour les informations de coût de base de l'article sont mis à jour, comme affiché dans la page Prix de l'article. Les frais s'affichent dans deux champs distincts et ne sont pas inclus dans le coût unitaire de l'article. Chaque activation met à jour les informations de coût de base de l'article, même si l'activation reflète différents sites. Vous devez donc considérer les informations de coût de base comme des informations de référence.






