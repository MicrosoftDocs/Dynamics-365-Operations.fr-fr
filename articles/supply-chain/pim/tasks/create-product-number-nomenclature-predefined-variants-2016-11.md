--- 
title: "Créer un numéro de produit pour les variantes de produit prédéfinies"
description: "Ce guide décrit comment paramétrer une nomenclature de numéros de produit pour des variantes de produit prédéfinies et comment l'affecter au groupe de dimensions de produit approprié."
author: BibiSp
manager: AnnBe
ms.date: 09/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: f14ee57564ad70bb7f28cd9274fc97d07974ec32
ms.contentlocale: fr-fr
ms.lasthandoff: 07/28/2017

---
# <a name="create-a-product-number-for-predefined-product-variants"></a>Créer un numéro de produit pour les variantes de produit prédéfinies

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ce guide décrit comment paramétrer une nomenclature de numéros de produit pour des variantes de produit prédéfinies et comment l'affecter au groupe de dimensions de produit approprié. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. La nouvelle nomenclature de numéros de produit est affectée au groupe de dimensions de produit Couleur et Taille. Cette tâche est généralement effectuée par un concepteur de produit.


## <a name="create-a-product-number-nomenclature"></a>Créer une nomenclature de numéros de produit
1. Cliquez sur Définition du modèle de variante de produit.
2. Cliquez sur Nomenclature produit.
3. Cliquez sur Nouveau.
4. Dans le champ Nom, entrez un nom de nomenclature qui permet d'identifier le groupe de dimensions de produit cible, par exemple, ColorSize.
5. Dans le champ Description, entrez une valeur.
6. Cliquez sur Ajouter.
7. Cliquez sur Numéro du produit générique.
8. Cliquez sur Ajouter.
9. Cliquez sur Constante de texte.
10. Tapez une valeur dans le champ Texte.
11. Cliquez sur Ajouter.
12. Cliquez sur Couleur.
13. Cliquez sur Ajouter.
14. Cliquez sur Constante de texte.
15. Tapez une valeur dans le champ Texte.
16. Cliquez sur Ajouter.
17. Cliquez sur Taille.
18. Fermez la page.

## <a name="assign-the-nomenclature-to-a-product-master"></a>Affecter la nomenclature à un produit générique
1. Cliquez sur Groupes de dimensions de produit.
2. Sélectionnez le groupe de dimensions de produit SizeCol.
3. Cliquez sur Modifier.
4. Sélectionnez Oui dans le champ Utiliser la nomenclature.
5. Dans le champ Nomenclature de numéros de variante de produit, entrez ou sélectionnez une valeur.
6. Fermez la page.

