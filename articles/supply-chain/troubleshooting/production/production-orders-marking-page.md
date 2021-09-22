---
title: Les ordres de fabrication ne sont pas affichés sur la page de marquage
description: Certains ordres de fabrication ne sont pas affichés sur la page de marquage. Cette rubrique explique les trois configurations de produit qui ne sont pas disponibles pour le marquage.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 87507e91d3feb2557e7ba771b8e34ff7ca105749
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476282"
---
# <a name="production-orders-arent-shown-on-the-marking-page"></a>Les ordres de fabrication ne sont pas affichés sur la page de marquage

## <a name="symptoms"></a>Symptômes

Lorsque vous utilisez la fabrication discrète, certains ordres de fabrication ne sont pas affichés sur la page **Marquage**.

## <a name="resolution"></a>Résolution

Les produits ayant les configurations suivantes ne sont pas disponibles pour le marquage. Par conséquent, ils ne seront pas affichés sur la page de **marquage** :

- Les produits sont définis comme des produits du type *Poids variable*.
- Ils sont activés pour les processus d’entrepôt avancés.
- Ils sont configurés pour être contrôlés par le principe *Coût standard*.
