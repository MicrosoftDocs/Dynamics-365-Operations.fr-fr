---
title: Articles fantôme
description: Cette rubrique décrit, en détail, la manière dont le type de ligne Fantôme peut être utilisé pour les lignes d’une nomenclature et d’une formule dans Dynamics 365 Supply Chain Management.
author: ShylaThompson
ms.date: 06/15/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.search.region: Global
ms.author: kamaybac
ms.search.validfrom: ''
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 1118d7334602e450e5d503632895f73ba19066a1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814776"
---
# <a name="phantom-items"></a>Articles fantôme

[!include [banner](../includes/banner.md)]

Cette rubrique décrit, en détail, la manière dont le type de ligne Fantôme peut être utilisé pour les lignes d’une nomenclature et d’une formule. Dans l’illustration suivante, (a) est la nomenclature du produit H et des pièces F et G, et (b) est la feuille de gamme des produits H et de la pièce F.

![Produit H et pièce F](media/product-H-part-F.png)


Cette illustration présente un exemple de structure de nomenclature à deux niveaux. Le produit fini H représente un produit pour un assemblage de machine. L’assemblage de la machine se compose de deux parties, une unité électrique (F) qui a deux matériaux (A et B) et un groupe de matériaux d’emballage (G) qui a également deux matériaux (C et D). Un autre matériau (E) est utilisé pendant l’assemblage général de la machine.

![Produit H et pièce F](media/product-H-part-B.png)

L’illustration précédente représente la nomenclature d’ingénierie du produit H. Cette structure donne une bonne vue d’ensemble des pièces et des composants de l’assemblage général de la machine. Toutefois, bien que les concepteurs du produit préfèrent que la nomenclature soit représentée de cette manière, cette structure peut ne pas représenter correctement la manière dont la machine est construite dans l’atelier. 

Par exemple, la nomenclature d’ingénierie dans l’illustration précédente indique que l’unité électrique F est assemblée comme une partie distincte d’un ordre d’exécution distinct. Toutefois, dans l’atelier, il peut s’avérer plus efficace d’assembler l’unité électrique dans le cadre de l’assemblage général de la machine, et non comme un ordre d’exécution distinct.

Cette nomenclature d’ingénierie indique également que la pièce G est une pièce distincte. Toutefois, dans cette structure, la pièce G ne représente pas une pièce physique mais un ensemble de matériaux d’emballage. 

Par conséquent, bien qu’une nomenclature d’ingénierie soit importante pour la conception d’un produit et la maintenance de cette conception, elle ne représente peut-être pas la manière la plus logique de prendre en charge le processus de contrôle et suivi de la production du produit. En revanche, une nomenclature de fabrication représente la meilleure façon de créer un produit.

L’illustration ci-dessous indique comment la nomenclature d’ingénierie précédente est convertie en nomenclature de fabrication. Dans cette illustration, (a) est la nomenclature du produit H, et b est la feuille de gamme du produit H.

Dans cette structure, vous pouvez voir que la notion de pièces F et G n’existe pas, et les matériaux de ces pièces ont été élevés au niveau suivant de la nomenclature. 

Contrairement à la nomenclature d’ingénierie, qui a deux feuilles d’opérations, la nomenclature de fabrication n’en a qu’une seule. L’opération d’emballage associée à la pièce G a également été élevée et fait désormais partie de la feuille d’opérations du produit H. L’assemblage de l’unité électrique est la première opération. Cet ordre est logique, car cette unité est utilisée dans l’opération suivante, c’est-à-dire l’assemblage de la machine. La dernière opération est l’opération d’emballage, qui utilise deux matériaux d’emballage (C et D).

La transition entre la nomenclature d’ingénierie et la nomenclature de fabrication est activée via le type de ligne de nomenclature Fantôme. Comme le terme » fantôme » l’indique, les pièces F et G ont disparu pendant la transition entre les deux types de nomenclature. Dans cet exemple, le type de ligne Fantôme est appliqué aux lignes de nomenclature pour les pièces F et G de la nomenclature d’ingénierie. Lorsqu’un ordre de fabrication ou un ordre de traitement par lots est créé, la nomenclature d’ingénierie est copiée dans l’ordre de fabrication ou de traitement par lots. Ensuite, lorsque l’ordre d’exécution est estimé, la transition de la nomenclature d’ingénierie à la nomenclature de fabrication a lieu, comme indiqué dans les illustrations précédentes. Dans la feuille d’opérations de la deuxième illustration, les matériaux d’emballage C et D sont des entrées pour l’opération. 

## <a name="multilevel-phantom-bom-structures"></a>Structures de nomenclature fantôme à plusieurs niveaux
Le type de ligne Fantôme peut être utilisé dans les structures de nomenclature à plusieurs niveaux, comme le montre l’illustration suivante. Dans cette illustration, (a) est la nomenclature du produit G, et (b) est la feuille de gamme des pièces E et F et du produit G. 

![Produit G et pièce F avec feuilles de gamme](media/product-G-route-sheet-G.png)


L’illustration suivante présente la nomenclature d’ingénierie et la feuille de gamme obtenues si les lignes de nomenclature des pièces E et F sont configurées pour que le type de ligne soit Fantôme. Dans cette illustration, (a) est la nomenclature du produit G, et (b) est la feuille de gamme du produit G.

![Produit G](media/product-G.png)


## <a name="phantom-and-route-network"></a>Nomenclature fantôme et réseau de gammes
Les nomenclatures fantômes peuvent également être utilisées pour une nomenclature doté d’un réseau de gammes. Dans un réseau de gammes, une ou plusieurs opérations s’exécutent en parallèle. L’illustration suivante présente un exemple de réseau de gammes utilisé dans une nomenclature à plusieurs niveaux. Dans cette illustration, (a) est la nomenclature du produit G et de la pièce F, et (b) est la feuille de gamme du produit G et de la pièce F, qui a un réseau de gammes.

![Produit G et pièce F](media/product-G-part-F.png)


Dans l’illustration suivante, (a) est la nomenclature du produit G et de la pièce F, et (b) est la feuille de gamme du produit G et de la pièce F.

![Produit G et pièce F avec feuilles de gamme](media/product-G-part-F-with-route-sheet.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]