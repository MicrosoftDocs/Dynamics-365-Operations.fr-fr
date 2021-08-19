---
title: Créer une nomenclature de numéro de produit pour les variantes de produit configurées
description: Cette procédure décrit comment paramétrer une nomenclature de numéros de produit pour des variantes de produit configurées, et comment elle peut être associée à un produit générique configurable.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: da52385f60b2522cf358e0ceb70448479a1e5dc714ef15ba361611ed404ed852
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726823"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a>Créer une nomenclature de numéro de produit pour les variantes de produit configurées

[!include [banner](../../includes/banner.md)]

Cette procédure décrit comment paramétrer une nomenclature de numéros de produit pour des variantes de produit configurées, et comment elle peut être associée à un produit générique configurable. Cette procédure illustre également comment générer une nomenclature de configuration pour un composant du modèle de configuration de produit. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. La nouvelle nomenclature de numéros de produit est affectée au produit générique D0004. Cette tâche est généralement effectuée par un concepteur de produit.

## <a name="create-a-product-number-nomenclature"></a>Créer une nomenclature de numéros de produit

1. Accédez à **Gestion des informations sur les produits \> Configuration \> Nomenclature produit**.
1. Sélectionnez **Nouveau**.
1. Tapez une valeur dans le champ **Nom**.
1. Tapez une valeur dans le champ **Description**.
1. Sélectionnez **Ajouter**.
1. Sélectionnez **Numéro du produit générique**.
1. Sélectionnez **Ajouter**.
1. Sélectionnez **Texte constant**.
1. Dans la liste, marquer la ligne sélectionnée.
1. Tapez une valeur dans le champ **Texte**.
1. Sélectionnez **Ajouter**.
1. Sélectionnez **Configuration**.
1. Fermez la page.

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a>Affecter la nomenclature de numéros de produit à un produit générique

1. Allez dans **Gestion des informations sur les produits \> Produits \> Produits génériques**.
1. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, appliquez un filtre sur le champ **Numéro de produit** avec la valeur « D ».
1. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
1. Sélectionnez **Modifier**.
1. Sélectionnez *Oui* dans le champ **Utiliser la nomenclature**.
1. Entrez ou sélectionnez une valeur dans le champ **Nomenclature de numéros de variante de produit**.
1. Fermez la page.
1. Fermez la page.

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a>Créer une nomenclature pour un composant du modèle de configuration de produit

1. Accédez à **Gestion des informations sur les produits \> Produits \> Modèles de configuration de produit**.
1. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
1. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
1. Sélectionnez **Modifier**.
1. Sélectionnez *Oui* dans le champ **Utiliser la nomenclature de configuration**.
1. Sélectionnez **Ajouter**.
1. Sélectionnez **Valeur d’attribut**.
1. Dans la liste, marquer la ligne sélectionnée.
1. Dans le champ **Attribut**, entrez ou sélectionnez une valeur.
1. Sélectionnez **Ajouter**.
1. Sélectionnez **Texte constant**.
1. Dans la liste, marquer la ligne sélectionnée.
1. Tapez une valeur dans le champ **Texte**.
1. Sélectionnez **Ajouter**.
1. Sélectionnez **Valeur d’attribut**.
1. Dans la liste, marquer la ligne sélectionnée.
1. Dans le champ **Attribut**, entrez ou sélectionnez une valeur.
1. Sélectionnez **Ajouter**.
1. Sélectionnez **Texte constant**.
1. Dans la liste, marquer la ligne sélectionnée.
1. Tapez une valeur dans le champ **Texte**.
1. Sélectionnez **Ajouter**.
1. Sélectionnez **Valeur d’attribut**.
1. Dans la liste, marquer la ligne sélectionnée.
1. Dans le champ **Attribut**, entrez ou sélectionnez une valeur.
1. Sélectionnez **Ajouter**.
1. Sélectionnez **Texte constant**.
1. Dans la liste, marquer la ligne sélectionnée.
1. Tapez une valeur dans le champ **Texte**.
1. Sélectionnez **Ajouter**.
1. Sélectionnez **Valeur d’attribut**.
1. Dans la liste, marquer la ligne sélectionnée.
1. Dans le champ **Attribut**, entrez ou sélectionnez une valeur.
1. Sélectionnez **Ajouter**.
1. Sélectionnez **Texte constant**.
1. Dans la liste, marquer la ligne sélectionnée.
1. Tapez une valeur dans le champ **Texte**.
1. Sélectionnez **Ajouter**.
1. Sélectionnez **Valeur de souche de numéros**.
1. Dans la liste, marquer la ligne sélectionnée.
1. Dans le champ **Souche de numéros**, entrez ou sélectionnez une valeur.
1. Fermez la page.
1. Fermez la page.
1. Fermez la page.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]