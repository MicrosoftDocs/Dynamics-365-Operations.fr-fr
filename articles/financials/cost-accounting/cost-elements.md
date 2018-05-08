---
title: "Dimensions d'éléments de coût"
description: "En tant que l'un des piliers de base du contrôle de gestion, les dimensions d'éléments de coût sont utilisées pour catégoriser et suivre le flux des coûts."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 223204
ms.assetid: 1eda0e62-760b-4737-9dfd-3c3c38d80c1a
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 00a09120116183785d96ed1e18c577d5430fa16b
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="cost-element-dimensions"></a>Dimensions d'éléments de coût

[!include [banner](../includes/banner.md)]

En tant que l'un des piliers de base du contrôle de gestion, les dimensions d'éléments de coût sont utilisées pour catégoriser et suivre le flux des coûts. 

Un élément de coût correspond à un article dont le coût est pertinent dans le plan de comptes. Fondamentalement, il peut s'agir de n'importe quel type d'élément au niveau le plus bas d'une société vers lequel les coûts peuvent se diriger. Les éléments de coûts comme plage de concept des comptes généraux à toutes les ressources dont le coût est pertinent. Actuellement, le contrôle de gestion prend en charge les comptes généraux.

## <a name="two-types-of-cost-elements"></a>Deux types d'éléments de coût
Il existe deux types d'éléments de coût : les éléments de coût principaux et les éléments de coût secondaires. Le tableau suivant décrit les différences entre les deux types.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Éléments de coût principaux</strong></td>
<td><strong>Éléments de coût secondaires</strong></td>
</tr>
<tr class="even">
<td>Les éléments de coûts principaux représentent le flux des coûts entre la comptabilité financière et le contrôle de gestion. La structure d'élément de coût correspond à la structure de compte de résultat dans la comptabilité, dans laquelle un élément de coût peut correspondre à un compte principal. Tous les comptes principaux ne doivent pas nécessairement être représentés en tant qu'éléments de coûts, en fonction des besoins de l'entreprise. Voici quelques exemples d'éléments de coût principaux :
<ul>
<li>Coûts des marchandises vendues</li>
<li>Coûts indirects liés aux matières</li>
<li>Coûts de personnel</li>
<li>Coûts énergétiques</li>
</ul></td>
<td>Les éléments des coûts secondaires représentent le flux interne des coûts, car ces coûts sont créés et utilisées uniquement dans le contrôle de gestion. Ils sont utilisés pour s'assurer que la source de coûts peut être retracée. Ces éléments de coût sont utilisés dans les répartitions de coûts et les calculs des frais généraux. Voici quelques exemples d'éléments de coût secondaires :
<ul>
<li>Coûts de production</li>
<li>Production, matières, et frais généraux de marketing</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="cost-element-dimensions-and-cost-element-dimension-members"></a>Dimensions d'éléments de coût et membres de la dimension d'élément de coût
Les éléments de coût sont appelés des *dimensions d'éléments de coût*. Les valeurs de dimension individuelle sont appelées *membres de la dimension d'élément de coût*. Par exemple, vous disposez d'une structure de plan de comptes américain qui est la base de la génération d'états statutaires. Cette structure de plan de comptes est utilisée comme dimension d'élément de coût. Les comptes, qui sont des éléments de coût principaux, sont représentées comme les membres de la dimension d'élément de coût dans le contrôle de gestion. La capture d'écran suivante illustre un exemple de comptes principaux comme dimension d'élément de coût avec ses comptes principaux réels comme membres de la dimension d'élément de coût. 

[![cost-element-dimensions](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)

## <a name="import-cost-element-dimension-members-through-data-connectors"></a>Importer les membres de la dimension d'élément de coût à l'aide de connecteurs de données
Pour faciliter le paramétrage des membres de la dimension d'élément de coût dans le contrôle de gestion, vous pouvez utiliser des connecteurs de données qui sont préconçus ou personnalisés pour récupérer les éléments de coût principaux d'un ou plusieurs systèmes sources.

## <a name="implementation-considerations"></a>Considérations d'implémentation
Puisque les éléments de coûts représentent le niveau le plus bas des détails de coût, vous devez vous assurer que tous les éléments de coût requis pour la génération d'états de gestionnaire sont inclus lorsque vous implémentez la structure d'éléments de coût. Cela peut être un défi de rechercher un numéro d'éléments de coût approprié pour le contrôle des coûts. Avoir des milliers d'éléments de coût peut rendre difficile le contrôle de chaque élément de coût. À la place, vous pouvez regrouper des éléments de coût et gérer le contrôle des coûts à un niveau agrégé.




