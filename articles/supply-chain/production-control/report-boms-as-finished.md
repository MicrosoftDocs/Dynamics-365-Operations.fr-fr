---
title: Déclarer la fin des nomenclatures
description: Cet article fournit des informations sur les nomenclatures déclarées terminées
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMReportFinish, BOMReportFinishMax, BOMSetupReportFinish
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53251
ms.assetid: 510d05a3-0073-438d-b0c4-b6a6df1882ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ff88622c2cbbdcff6130fb8c500ea12a1e454ecb5f33834bc0a69718038c9e89
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766581"
---
# <a name="report-boms-as-finished"></a>Déclarer la fin des nomenclatures

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur les nomenclatures déclarées terminées

Les pages **Déclarer comme terminé** et **Déclaration et contrôle sans OF** permettent de déclarer des nomenclatures (BOM) comme terminées. Conceptuellement, le processus de déclaration d’une nomenclature comme terminée est identique au processus de déclaration d’un ordre de fabrication comme terminé. Ce processus peut être utilisé par exemple dans des processus de kitting et d’assemblage simples où les capacités les plus avancées en matière d’ordres de fabrication ne sont pas requises. La page **Déclarer comme terminé** vous permet de déclarer plusieurs nomenclatures comme terminées dans un traitement par lots. La page **Déclaration et contrôle sans OF** vous permet de déclarer une seule nomenclature comme terminée à la fois. La page **Déclarer comme terminé** est disponible à partir d’une option de menu du module Gestion des stocks, et les deux pages sont disponibles en tant qu’options de menu sur la page **Produits lancés**.

## <a name="report-as-finished-page"></a>Page Déclarer comme terminé
Si vous ouvrez la page **Déclarer comme terminé** d’un produit lancé, la page vous suggère de déclarer la quantité par défaut de stock standard comme terminée. Par défaut, la version de nomenclature active est affichée, mais vous pouvez modifier la version de nomenclature s’il existe d’autres versions approuvées. Cette page vous permet également de supprimer des enregistrements et de créer des enregistrements pour les produits qui doivent être déclarés comme terminés. Pour utiliser une requête pour sélectionner les produits, cliquez sur l’option de menu **Sélectionner**. Vous pouvez confirmer manuellement que la déclaration est terminée pour les produits sélectionnés en cliquant sur **OK**. Vous pouvez également paramétrer le processus pour qu’il s’exécute par lots. Lorsque la réussite du processus de déclaration de fin est confirmée, le système génère un journal de nomenclature dans lequel la validation du stock est traitée. Ce journal comporte une ligne pour le produit fini et une ligne pour chaque ligne de nomenclature. Vous pouvez contrôler si le journal est validé automatiquement ou s’il est laissé ouvert pour des ajustements supplémentaires.

## <a name="max-report-as-finished-page"></a>Page Déclaration et contrôle sans OF
Sur la page **Déclaration et contrôle sans OF**, chaque ligne de nomenclature indique le nombre de pièces du produit pouvant être déclarées comme terminées. Ce calcul est basé sur le stock physique disponible de chaque ligne du matériel. Dans l’exemple suivant, une pièce du numéro d’article FG consomme deux pièces de la matière première RM10 et une pièce de la matière première RM20. Comme il n’y a que 10 pièces de RM10 disponibles, la quantité maximale de FG pouvant être déclarée comme terminée est de cinq pièces. Cette valeur est affichée dans le champ **Déclaration et contrôle sans OF**.

| Niveau | Numéro d’article | Quantité | Disponible | Page Déclaration de fin |
|-------|-------------|----------|---------|-------------------------|
| 0     | FG          |  1       | 0       | 5                       |
| 1     | RM10        | -2       | 10      | 5                       |
| 1     | RM20        | -1       |  8      | 8                       |

## <a name="boms-that-have-multiple-levels"></a>Nomenclatures qui ont plusieurs niveaux
Lorsqu’une nomenclature possède plusieurs niveaux, vous pouvez contrôler la manière dont les matières sont prises en compte à tous les niveaux à l’aide du champ  **Éclatement**. Ce champ est disponible sur la page **Déclarer comme terminé** et la page **Déclaration et contrôle sans OF**. Les options suivantes sont disponibles :

-   **Jamais** : Les nomenclatures sous-jacentes ne sont jamais éclatées en cas de pénurie de matières.
-   **Toujours** : Toutes les nomenclatures sous-jacentes sont entièrement éclatées. Ainsi, le stock disponible de composants semi-finis n’est pas utilisé.
-   **En cas de pénurie** : Les nomenclatures sous-jacentes sont éclatées uniquement si la quantité souhaitée de matières n’est pas disponible.

### <a name="example"></a>Exemple

Dans cet exemple, trois pièces du produit fini (numéro d’article FG) sont prêtes à être déclarées comme terminées. Il existe une nomenclature à deux niveaux, comme indiqué ici.

| Niveau | Numéro d’article | Quantité de la ligne de nomenclature | Disponible |
|-------|-------------|-------------------|---------|
| 0     | FG          |                   |         |
| 1     | COMP        | 1                 | 2       |
| 1     | RM          | 1                 |         |

Les tableaux suivants indiquent comment le paramètre du champ **Éclatement** affecte la manière dont les lignes de journal de nomenclature sont générées. **Éclatement : Jamais**

| Niveau | Numéro d’article | Quantité |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | COMP        | -3       |

Comme indiqué dans le tableau précédent, seul le numéro d’article COMP est considéré comme déduit dans le journal. Le numéro d’article RM, qui fait partie de COMP, n’est pas éclaté dans la ligne de journal, et les deux pièces de COMP disponibles ne sont pas prises en compte. **Éclatement : Toujours**

| Niveau | Numéro d’article | Quantité |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | RM          | -3       |

Dans ce cas, le numéro d’article COMP est éclaté dans ses matières premières, le numéro d’article RM. Les deux pièces de CPM disponibles ne sont pas prises en compte dans la quantité de RM à consommer. **Éclatement : Pénurie**

| Niveau | Numéro d’article | Quantité |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | COMP        | -2       |
| 1     | RM          | -1       |

Dans ce cas, les deux pièces du numéro d’article COMP disponibles sont prises en compte. Toutefois, comme trois pièces du numéro d’article FG sont requises, une pièce du numéro d’article RM est également requise afin de compléter la pièce de COMP supplémentaire.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]