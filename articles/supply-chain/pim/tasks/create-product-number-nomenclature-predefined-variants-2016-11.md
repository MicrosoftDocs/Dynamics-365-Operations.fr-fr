---
title: Créer une nomenclature de numéro de produit pour les variantes de produit prédéfinies
description: Ce guide décrit comment paramétrer une nomenclature de numéros de produit pour des variantes de produit prédéfinies et comment l'affecter au groupe de dimensions de produit approprié.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6a2e61fd99cb80a1a9cc3d8e985fb0f14e3c2fc2
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844679"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Créer une nomenclature de numéro de produit pour les variantes de produit prédéfinies

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

