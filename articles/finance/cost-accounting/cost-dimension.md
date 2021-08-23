---
title: Créer des dimensions et importer des membres de la dimension
description: Le Contrôle de gestion est un module indépendant qui nécessite les données principales d’autres modules.
author: ShylaThompson
ms.date: 09/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: roschlom
ms.custom: 256254
ms.assetid: e1b0a6e3-0c72-4a7d-90e1-20f870c6dbad
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6febb8a48cf6496fb7f4c2ee9f5281d47aa1ccae1a8ecc51c908b3810302e11c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6775120"
---
# <a name="create-dimensions-and-import-dimension-members"></a>Créer des dimensions et importer des membres de la dimension

[!include [banner](../includes/banner.md)]

Le Contrôle de gestion est un module indépendant qui nécessite les données d’autres modules. Ces données sont classées par catégorie comme suit :

-  Éléments de coût
-  Objets de coût
-  Dimensions statistiques

Un **élément de coût** correspond à un article dont le coût est pertinent dans le plan de comptes. Un **objet de coût** correspond à tout type de dimension financière, comme les produits, les centres de coût et les projets que vous voulez estimer, auxquels vous voulez affecter des coûts, ou que vous voulez mesurer directement. Une **dimension statistique** et ses membres permettent d’enregistrer les entrées non monétaires. Les membres de la dimension statistique peuvent être utilisés comme base de répartition pour la distribution et la répartition des coûts 

Le diagramme suivant illustre les dimensions utilisées dans le Contrôle de gestion.

[![Dimensions de Contrôle de gestion.](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)

Une fois que les données sont importées dans le Contrôle de gestion, vous pouvez l’utiliser pour créer les différentes perspectives qui fournissent des analyses aux responsables à tous les niveaux de l’organisation. Les rubriques suivantes fournissent des informations sur la création des dimensions et l’importation des membres de la dimension. 

-  [Dimensions d’éléments de coût](cost-elements.md)
-  [Créer des éléments de coût](./tasks/create-cost-elements.md)
-  [Dimensions d’objets de coût](cost-objects.md)
-  [Mappage de membres de dimension d’élément de coût à un ensemble commun de membres de dimension](map-cost-elements-dimension-members.md)
-  [Mapper une dimension d’élément de coût](./tasks/map-cost-element-dimension.md)
-  [Membres de la dimension statistique et modèles de fournisseur de mesures statistiques](statistical-measure-provider-template.md)








[!INCLUDE[footer-include](../../includes/footer-banner.md)]