---
title: Créer une nomenclature de numéro de produit pour les variantes de produit prédéfinies
description: Cet article explique comment paramétrer une nomenclature de numéros de produit pour des variantes de produit prédéfinies et comment l’affecter au groupe de dimensions de produit approprié.
author: t-benebo
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e77c8eabe1657f7fbfef71747627207dccff3b60
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887310"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Créer une nomenclature de numéro de produit pour les variantes de produit prédéfinies

[!include [banner](../../includes/banner.md)]

Cet article explique comment paramétrer une nomenclature de numéros de produit pour des variantes de produit prédéfinies et comment l’affecter au groupe de dimensions de produit approprié. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. La nouvelle nomenclature de numéros de produit est affectée au groupe de dimensions de produit Couleur et Taille. Cette tâche est généralement effectuée par un concepteur de produit.


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