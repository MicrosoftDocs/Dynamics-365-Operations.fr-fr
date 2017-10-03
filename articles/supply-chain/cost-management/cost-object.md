---
title: "Objets de coût"
description: "Cet article fournit des informations sur les objets de coûts, et explique comment les coûts et les quantités sont accumulés. Un objet de coût est une entité pour laquelle des coûts et des quantités sont accumulés. Une entité d'objet de coûts peut être un produit ou des variantes de produit, telles que des variantes de style et de couleur."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 9262dcaa3b326d8c31b7d7416b102920795da94b
ms.openlocfilehash: 823d3edd106925339607d01fbf5f1921b85ff244
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017

---

# <a name="cost-objects"></a>Objets de coût

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur les objets de coûts, et explique comment les coûts et les quantités sont accumulés. Un objet de coût est une entité pour laquelle des coûts et des quantités sont accumulés. Une entité d'objet de coûts peut être un produit ou des variantes de produit, telles que des variantes de style et de couleur.  

<a name="cost-objects"></a>Objets de coût
------------

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

<a name="see-also"></a>Voir également :
--------

[Groupe de dimensions de produit](https://technet.microsoft.com/en-us/library/aa499382.aspx)

[Groupe de dimension de stockage](https://technet.microsoft.com/en-us/library/hh209317.aspx)

[Groupe de dimensions de suivi](https://technet.microsoft.com/en-us/library/hh209465.aspx)

[Nouveautés ou changements](/dynamics365/unified-operations/dev-itpro/get-started/whats-new-changed)

[Écritures de coût](cost-entries.md)



