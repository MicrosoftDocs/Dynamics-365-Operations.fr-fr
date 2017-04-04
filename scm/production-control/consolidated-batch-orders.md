---
title: "Lots de production consolidés"
description: "Cet article décrit le concept des lots de production consolidés."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 3359f1cd5c3f1ecf25c3f28a366c022826cf895e
ms.lasthandoff: 03/31/2017


---

# <a name="consolidated-batch-orders"></a>Lots de production consolidés

Cet article décrit le concept des lots de production consolidés.

Un consommable produit est considéré comme un article parent, tandis qu'un article emballé est considéré comme un article enfant. La relation entre le consommable et l'article emballé est exprimé par une conversion de consommables. Cette conversion de consommables est définie sur le consommable lui-même.  

Les articles emballés peuvent être emballés dans des conteneurs d'une seule et même taille ou de tailles différentes, eux-mêmes considérés comme une unité. En consolidant les commandes pour un consommable, vous pouvez voir tous les lots de commandes associés sur un seul et même écran, ce qui vous permet de déterminer le travail restant à effectuer.  

Un lot de production consolidé peut contenir toute combinaison des commandes suivantes :

-   Une commande en vrac simple et plusieurs commandes emballées
-   Plusieurs commandes en vrac et plusieurs commandes emballées
-   Plusieurs commandes en vrac et une seule commande emballée
-   Les commandes emballées seules



