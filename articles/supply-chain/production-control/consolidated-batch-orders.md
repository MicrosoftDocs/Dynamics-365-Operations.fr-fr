---
title: Lots de production consolidés
description: Cet article décrit le concept des lots de production consolidés.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: faeb90aa3366a58b746c0b397dd950bfb8c9024f
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3979473"
---
# <a name="consolidated-batch-orders"></a>Lots de production consolidés

[!include [banner](../includes/banner.md)]

Cet article décrit le concept des lots de production consolidés.

Un consommable produit est considéré comme un article parent, tandis qu'un article emballé est considéré comme un article enfant. La relation entre le consommable et l'article emballé est exprimé par une conversion de consommables. Cette conversion de consommables est définie sur le consommable lui-même.  

Les articles emballés peuvent être emballés dans des conteneurs d'une seule et même taille ou de tailles différentes, eux-mêmes considérés comme une unité. En consolidant les commandes pour un consommable, vous pouvez voir tous les lots de commandes associés sur un seul et même écran, ce qui vous permet de déterminer le travail restant à effectuer.  

Un lot de production consolidé peut contenir toute combinaison des commandes suivantes :

-   Une commande en vrac simple et plusieurs commandes emballées
-   Plusieurs commandes en vrac et plusieurs commandes emballées
-   Plusieurs commandes en vrac et une seule commande emballée
-   Les commandes emballées seules




