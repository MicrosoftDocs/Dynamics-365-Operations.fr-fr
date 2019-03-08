---
title: Objets de coût
description: Cet article fournit des informations sur les objets de coûts, et explique comment les coûts et les quantités sont accumulés. Un objet de coût est une entité pour laquelle des coûts et des quantités sont accumulés. Une entité d'objet de coûts peut être un produit ou des variantes de produit, telles que des variantes de style et de couleur.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 275855f2fb4d32df91449d7ebb9ad9ba2bd3f36b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "338427"
---
# <a name="cost-objects"></a>Objets de coût

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur les objets de coûts, et explique comment les coûts et les quantités sont accumulés. Un objet de coût est une entité pour laquelle des coûts et des quantités sont accumulés. Une entité d'objet de coûts peut être un produit ou des variantes de produit, telles que des variantes de style et de couleur.  

## <a name="cost-objects"></a>Objets de coût

La page **Objets de coût** répertorie tous les objets de coût qui sont enregistrés sur un produit. Les objets de coût sont définis par les données issues des sources suivantes :

-   Produit
-   Groupe de dimensions de produit
-   Groupe de dimension de stockage
-   Groupe de dimension de suivi

**Remarque :** un objet de coût représente un élément de coût du type **Matières directes** uniquement. Un objet de coût et un objet de stock diffèrent en ce qu'un objet de coût est défini par les dimensions de stock sélectionnées pour le stock physique. Par exemple, un article a la configuration suivante :

-   **Site :** Stock physique = oui, Stock financier = oui
-   **Entrepôt :** Stock physique = oui, Stock financier = non
-   **N° de lot :** Stock physique = oui, Stock financier = non

Le tableau suivant présente ce qui est un objet de coût et ce qui est un objet de stock.

| Type d'objet      | Numéro d'article | site ; | Entrepôt | N° de lot |
|------------------|-------------|------|-----------|-----------|
| Objet de coût      | x           | x    |           |           |
| Objet de stock | x           | x    |  x        | x         |

## <a name="accumulation-of-costs-and-quantities"></a>Cumul des coûts et des quantités
-   La valeur dans le champ **Valeur** est une somme des valeurs suivantes :
    -   Montant du coût physique
    -   Montant du coût financier
    -   Ajustements
-   La valeur dans le champ **Quantité** est une somme des valeurs suivantes :
    -   Reçue
    -   Déduit
    -   Quantité validée
-   Le champ **Coût unitaire moyen** est un champ calculé. La valeur est calculée en divisant la valeur **Valeur** par la valeur **Quantité**.

**Remarque :** Le paramètre **Inclure la valeur physique** n'a aucun effet sur les calculs précédents.

<a name="additional-resources"></a>Ressources supplémentaires
--------

[Groupe de dimensions de produit](https://technet.microsoft.com/en-us/library/aa499382.aspx)

[Groupe de dimension de stockage](https://technet.microsoft.com/en-us/library/hh209317.aspx)

[Groupe de dimensions de suivi](https://technet.microsoft.com/en-us/library/hh209465.aspx)

[Nouveautés ou changements](../../fin-and-ops/get-started/whats-new-changed.md)

[Écritures de coût](cost-entries.md)



