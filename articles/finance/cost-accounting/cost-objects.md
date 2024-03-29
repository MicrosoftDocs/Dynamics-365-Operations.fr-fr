---
title: Dimensions d’objets de coût
description: Lorsque vous analysez les coûts, vous utilisez des dimensions d’élément de coût pour déterminer le flux des coûts. Vous utilisez les dimensions d’objet de coût pour déterminer où vous devez affecter des coûts. Cet article fournit des informations sur les dimensions d’objet de coût.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimensionMember, CAMCostObject
audience: Application User
ms.reviewer: twheeloc
ms.custom: 223174
ms.assetid: 2a1cdd35-30cb-41e7-9506-67fd04a537c5
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: twheeloc
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3ee481b9dafe202e0a850a31b6ab036d52a20547
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874636"
---
# <a name="cost-object-dimensions"></a>Dimensions d’objets de coût

[!include [banner](../includes/banner.md)]

Lorsque vous analysez les coûts, vous utilisez des dimensions d’élément de coût pour déterminer le flux des coûts. Vous utilisez les dimensions d’objet de coût pour déterminer où vous devez affecter des coûts. Cet article fournit des informations sur les dimensions d’objet de coût.

Un objet de coût peut être n’importe quel type d’objet que vous voulez estimer, affecter des coûts, ou mesurer directement. Les objets de coût comprennent les produits, les projets, les ressources, les services, les centres de coût, et les zones géographiques. La gestion utilise les objets de coût pour mesurer les coûts, mais aussi pour réaliser l’analyse de rentabilité.

## <a name="cost-object-dimensions-and-cost-object-dimension-members"></a>Dimensions d’objet de coût, et membres de la dimension d’objet de coût
Les objets de coût sont appelés *dimensions d’objet de coût*. Une fois que vous avez décidé à quelle l’entité la dimension d’objets de coût doit faire référence, vous devez spécifier les valeurs de dimension individuelle ou les importer dans le contrôle de gestion depuis d’autres systèmes sources. Ces valeurs de dimension individuelle sont appelées *membres de la dimension d’objet de coût*. Par exemple, vous souhaitez utiliser la dimension financière qui est nommée Centre de coût comme dimension d’objet de coût. Pour voir comment le flux des coûts vers les différents centres de coût, vous devez importer les membres de la dimension d’objet de coût. Dans ce cas, les membres de la dimension d’objet de coût sont les centres de coût réels, tels que les Ventes, la Production, l’Administration, et les Emplacements géographiques. La capture d’écran suivante illustre un exemple de Centres de coûts comme dimension d’objet de coût avec ses centres de coûts réels comme membres de la dimension d’objet de coût. 

[![Capture d’écran présentant les centres de coût comme dimension d’objet de coût.](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)

## <a name="import-cost-object-dimension-members-through-data-connectors"></a>Importer les membres de la dimension d’objet de coût à l’aide de connecteurs de données
Pour faciliter l’importation de membres de dimension d’objet de coût, vous utilisez des connecteurs de données pour récupérer les valeurs des entités à utiliser en tant que dimensions de coût d’objet. Vous pouvez utiliser des connecteurs de données préconçus ou des personnalisés que vous créez.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
