---
title: "Planifier des charges à l’aide de la consolidation de point de transbordement"
description: "Cet article décrit la fonctionnalité de consolidation des expéditions dans un point de transbordement lorsque vous livrez des marchandises provenant d’entrepôts différents pour le même client, ou lorsque vous recevez des marchandises à partir de plusieurs fournisseurs dans le même entrepôt."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLoadPlanningWorkbench
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 92273
ms.assetid: d27b0926-a534-4caf-a2a3-acbc7c440bca
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: e0bd837a441a17e53982d5c5a7a7983f40e471c5
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="plan-loads-using-hub-consolidation"></a>Planifier des charges à l’aide de la consolidation de point de transbordement

[!include[banner](../includes/banner.md)]


Cet article décrit la fonctionnalité de consolidation des expéditions dans un point de transbordement lorsque vous livrez des marchandises provenant d’entrepôts différents pour le même client, ou lorsque vous recevez des marchandises à partir de plusieurs fournisseurs dans le même entrepôt.

Il peut être utile de consolider les expéditions dans un point de transbordement lorsque vous livrez des marchandises provenant d’entrepôts différents pour le même client, ou lorsque les marchandises sont livrées à partir de plusieurs fournisseurs à l’entrepôt.

## <a name="building-loads"></a>Création de chargements
Avant de pouvoir utiliser consolidation d epoint de transbordement, vous devez activer l'option **Planification en transit**sur la page **Paramètres de gestion du transport**. Vous devez également créer les points de transbordement où la consolidation aura lieu. Le diagramme suivant illustre un exemple de consolidation de point de transbordement. Dans ce cas, les commandes client provenant de différents entrepôts vont au même client. Les chargements de base sont créés en fonction des commandes client de la façon habituelle, à l’aide de la page **Atelier de planification des chargements**. Pour consolider les deux chargements dans un point de transbordement avant de les livrer au client, sur la page **Atelier de planification des chargements**, dans le champ **Transport**, sélectionnez **Consolidation de point de transbordement**. Lorsque vous sélectionnez le point de transbordement correct pour chaque chargement, les chargements auront le point de transbordement comme destination de « remise ». Vous aurez également deux « lignes de demande de transport » dans la section **Offre et demande** de la page **Atelier de planification des chargements**. Vous pouvez ensuite ajouter ces deux lignes à un nouveau chargement. Ce nouveau chargement aura les deux lignes de commande client et sera également le point de transbordement comme adresse d'« enlèvement » et le client A comme destination de « remise ». Les trois chargements sont ensuite prêts à être évalués et acheminés comme tout autre chargement. Vous pouvez sélectionner n'importe quel transporteur proposé par le système pour chaque chargement. [![Consolidation de point de transbordement](./media/hubconsol.jpg)](./media/hubconsol.jpg) Vous pouvez également utiliser la même méthode pour consolider les chargements de plusieurs ordres de transfert. Dans ce cas, le client A dans le diagramme précédent est un entrepôt. Sinon, vous pouvez consolider les chargements de plusieurs commandes fournisseur, où les chargements en provenance de différents fournisseurs sont remis à l’entrepôt. Vous pouvez avoir plusieurs points de transbordement de consolidation et pouvez consolider plusieurs points de transbordement pour plusieurs chargements provenant de différents entrepôts. Une fois que vous générez vos chargements de base et que vous utilisez l’option de consolidation du point de transbordement, vous créez les nouveaux chargements à l'aide des lignes de demande de transport consolidées. Ensuite, vous évaluez et acheminer vos chargements.




