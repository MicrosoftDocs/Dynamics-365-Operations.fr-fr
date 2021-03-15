---
title: Créer une nomenclature de numéro de produit pour les variantes de produit prédéfinies
description: Cette rubrique explique comment paramétrer une nomenclature de numéros de produit pour des variantes de produit prédéfinies et comment l'affecter au groupe de dimensions de produit approprié.
author: ShylaThompson
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3a15d1f4ecbf85e22bfadc1dd680d24bc56d807f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007539"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Créer une nomenclature de numéro de produit pour les variantes de produit prédéfinies

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment paramétrer une nomenclature de numéros de produit pour des variantes de produit prédéfinies et comment l'affecter au groupe de dimensions de produit approprié. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. La nouvelle nomenclature de numéros de produit est affectée au groupe de dimensions de produit Couleur et Taille. Cette tâche est généralement effectuée par un concepteur de produit.


## <a name="create-a-product-number-nomenclature"></a>Créer une nomenclature de numéros de produit
1. Sélectionnez **Définition du modèle de variante de produit**.
2. Sélectionnez **Nomenclature produit**.
3. Sélectionnez **Nouveau**.
4. Dans le champ **Nom**, entrez un nom de nomenclature qui permet d'identifier le groupe de dimensions de produit cible, par exemple, `ColorSize`.
5. Tapez une valeur dans le champ **Description**.
6. Sélectionnez **Ajouter**.
7. Sélectionnez **Numéro du produit générique**.
8. Sélectionnez **Ajouter**.
9. Sélectionnez **Texte constant**.
10. Tapez une valeur dans le champ **Texte**.
11. Sélectionnez **Ajouter**.
12. Sélectionnez **Couleur**.
13. Sélectionnez **Ajouter**.
14. Sélectionnez **Texte constant**.
15. Tapez une valeur dans le champ **Texte**.
16. Sélectionnez **Ajouter**.
17. Sélectionnez **Taille**.
18. Fermez la page.

## <a name="assign-the-nomenclature-to-a-product-master"></a>Affecter la nomenclature à un produit générique
1. Sélectionnez **Groupes de dimensions de produit**.
2. Sélectionnez le groupe de **dimensions de produit SizeCol**.
3. Sélectionnez **Modifier**.
4. Sélectionnez **Oui** dans le champ **Utiliser la nomenclature**.
5. Entrez ou sélectionnez une valeur dans le champ **Nomenclature de numéros de variante de produit**.
6. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]