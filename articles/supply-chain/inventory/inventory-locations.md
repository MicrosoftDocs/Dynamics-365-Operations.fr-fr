---
title: Emplacement de stockage
description: Les emplacements de stockage sont utilisés avec l’entreposage de base (WMS I) pour déterminer où les articles sont enregistrés et où les articles sont prélevés dans un entrepôt WMS I.
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSLocation, WMSBlockingCause, WHSLocation
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8d5459e37b5827b6a2ff07c892c2ff25b76ecd6
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187480"
---
# <a name="inventory-locations"></a>Emplacement de stockage

[!include [banner](../includes/banner.md)]

Les emplacements de stockage sont utilisés avec l’entreposage de base (WMS I) pour déterminer où les articles sont enregistrés et où les articles sont prélevés dans un entrepôt WMS I.

Cette rubrique s’applique aux fonctionnalités du module Gestion des stocks. Elle ne s’applique pas aux fonctionnalités du module Gestion des entrepôts.

Le terme emplacement fait référence au lieu de stockage et d’extraction des articles.

Pour chaque emplacement, vous pouvez également spécifier le lieu d’insertion de l’article. Par défaut, ces lieux sont identiques. Généralement, les articles sont insérés et extraits du même côté d’un emplacement mais ce n’est pas toujours le cas. Par exemple, les articles stockés dans des casiers à accumulation dynamique sont insérés depuis une allée et extraits depuis une autre. La donnée principale est le nom de l’emplacement qui est généralement déterminé par ses coordonnées : entrepôt, allée, rayon, étagère et casier. Ce nom ou cet ID peut être entré manuellement ou généré à partir des coordonnées de l’emplacement (par exemple, 01-02-03-4 pour allée 1, rayon 2, étagère 3, casier 4) dans la page Emplacements de stockage.
Propriétés de l’emplacement

Un emplacement possède les caractéristiques suivantes :
-   Taille (hauteur, largeur, profondeur et, par conséquent, volume)
-   Position de l’entrepôt, de l’allée, du rayon, de l’étagère et du casier.
-   Type d’emplacement (emplacement de stockage en gros, emplacement de prélèvement, quai d’embarquement, quai de débarquement, emplacement d’entrée en production, emplacement d’inspection ou supermarché kanban)

Un libellé de contrôle peut être utilisé dans les systèmes en ligne pour vérifier que l’opérateur a bien sélectionné le bon emplacement pour un article spécifique. Ce libellé de contrôle peut être créé manuellement ou par défaut.

## <a name="sort-codes"></a>Priorités
Les priorités permettent d’optimiser la gestion des lignes de prélèvement, qui décrivent les informations requises pour le prélèvement des articles du stock, notamment l’ordre de prélèvement. Les priorités peuvent être spécifiées par l’aile ou d’autres coordonnées ou attribuées manuellement pour l’emplacement.

## <a name="blocked-locations"></a>Emplacements bloqués
Vous souhaitez parfois indiquer qu’un emplacement est bloqué pour une période donnée, par exemple, pour permettre des réparations. Ou bien, vous pouvez indiquer que seule l’entrée ou la sortie est bloquée.

## <a name="tree-structure"></a>Structure arborescente

Dans la page Emplacements de stockage, vous pouvez afficher la disposition d’entrepôt dans une structure arborescente basée sur les coordonnées des emplacements de stockage, dans un format d’affichage défini.

## <a name="maintain-inventory-locations-via-the-warehouse-form"></a>Tenir à jour les emplacements de stockage via l’écran Entrepôt

Il est possible de copier des emplacements d’un entrepôt à un autre et de créer des emplacements via un assistant. Avant d’exécuter l’assistant, vous devez veiller à définir les noms d’emplacement par défaut dans la page Entrepôt.



## <a name="additional-resources"></a>Ressources supplémentaires

[Créer une structure d’entrepôt](tasks/create-new-warehouse-layout.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]