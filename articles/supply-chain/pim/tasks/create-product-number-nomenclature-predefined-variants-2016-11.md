---
title: Créer une nomenclature de numéro de produit pour les variantes de produit prédéfinies
description: Cette rubrique explique comment paramétrer une nomenclature de numéros de produit pour des variantes de produit prédéfinies et comment l’affecter au groupe de dimensions de produit approprié.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fada426b03aa8a908c3351932a288c911cb8c60fa13ccbfbfd0ceed232759a88
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736038"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Créer une nomenclature de numéro de produit pour les variantes de produit prédéfinies

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment paramétrer une nomenclature de numéros de produit pour des variantes de produit prédéfinies et comment l’affecter au groupe de dimensions de produit approprié. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. La nouvelle nomenclature de numéros de produit est affectée au groupe de dimensions de produit Couleur et Taille. Cette tâche est généralement effectuée par un concepteur de produit.


## <a name="create-a-product-number-nomenclature"></a>Créer une nomenclature de numéros de produit

1. Accédez à **Gestion des informations sur les produits \> Configuration \> Nomenclature produit**.
1. Sélectionnez **Nouveau**.
1. Dans le champ **Nom**, entrez un nom de nomenclature qui permet d’identifier le groupe de dimensions de produit cible, par exemple, `ColorSize`.
1. Tapez une valeur dans le champ **Description**.
1. Sélectionnez **Ajouter**.
1. Sélectionnez **Numéro du produit générique**.
1. Sélectionnez **Ajouter**.
1. Sélectionnez **Texte constant**.
1. Tapez une valeur dans le champ **Texte**.
1. Sélectionnez **Ajouter**.
1. Sélectionnez **Couleur**.
1. Sélectionnez **Ajouter**.
1. Sélectionnez **Texte constant**.
1. Tapez une valeur dans le champ **Texte**.
1. Sélectionnez **Ajouter**.
1. Sélectionnez **Taille**.
1. Fermez la page.

## <a name="assign-the-nomenclature-to-a-product-master"></a>Affecter la nomenclature à un produit générique

1. Sélectionnez **Groupes de dimensions de produit**.
2. Sélectionnez le groupe de **dimensions de produit SizeCol**.
3. Sélectionnez **Modifier**.
4. Sélectionnez **Oui** dans le champ **Utiliser la nomenclature**.
5. Entrez ou sélectionnez une valeur dans le champ **Nomenclature de numéros de variante de produit**.
6. Fermez la page.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]