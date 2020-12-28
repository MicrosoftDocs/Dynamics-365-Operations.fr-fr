---
title: Inventaire tournant de l’emplacement partiel
description: Les plans d’inventaire tournant guident les opérations tournantes réelles. Vous pouvez demander que seuls des produits et des variantes de produit spécifiques soient comptabilisés au lieu de tout le stock disponible à un emplacement.
author: perlynne
manager: tfehr
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable, WHSRFMenuItemCycleCount, WHSCycleCountPlanListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a541818a72f5c24db8784071f447c83a2aa4edfd
ms.sourcegitcommit: 95f90ac3f248716abdab16d5de6ccbf059616e4b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4666744"
---
# <a name="partial-location-cycle-counting"></a>Inventaire tournant de l’emplacement partiel

[!include [banner](../includes/banner.md)]

Les plans d’inventaire tournant guident les opérations tournantes réelles. Vous pouvez demander que seuls des produits et des variantes de produit spécifiques soient comptabilisés au lieu de tout le stock disponible à un emplacement.

En utilisant des plans d’inventaire tournant pour créer un travail d’inventaire, vous pouvez guider les opérations d’inventaire réelles. Vous pouvez demander que seuls des produits et des variantes de produit spécifiques soient comptabilisés au lieu de tout le stock disponible à un emplacement. Lorsque vous appliquez un filtre sur les produits spécifiques, le gestionnaire d’entrepôt peut réduire les frais généraux de révision, éviter toute erreur de consolidation et gagner du temps.

## <a name="how-to-configure-partial-location-cycle-counting"></a>Procédure de configuration d’un inventaire tournant partiel

Lorsque vous utilisez le processus de travail de l’entrepôt pour les opérations d’inventaire, l’en-tête de travail est créé pour chaque emplacement. Lorsque vous définissez le plan d’inventaire tournant, vous pouvez utiliser la requête **Sélectionner des emplacements** pour limiter le travail d’inventaire qui est créé. Lorsque vous sélectionnez des produits pour le plan d’inventaire tournant, vous pouvez sélectionner des requêtes de produits et de variantes de produit pour affiner l’inventaire.

Vous pouvez associer un **modèle de travail** à un plan d’inventaire tournant afin de définir la manière dont le travail d’inventaire tournant doit être créé. Le modèle de travail pour les opérations d’inventaire est directement référencé à partir du plan d’inventaire tournant.

Lorsque vous définissez les détails du modèle de travail, vous pouvez utiliser l’option **Pauses de ligne de travail** pour spécifier si les lignes de comptage traitées doivent être regroupées par numéro d’article ou de variante de produit. Ce paramétrage est nécessaire si vous voulez compter le stock disponible uniquement pour les produits spécifiques d’un emplacement. Les lignes de travail d’inventaire tournant qui sont créées disposeront du niveau d’information que vous définissez ici, et l’opération de comptage guidée sera gérée en fonction de ce niveau.

Si vous associez des plans de comptage d’inventaire tournant à des modèles de travail à l’aide de l’option **Pauses de ligne de travail**, le champ **Inventaire tournant partiel** est sélectionné pour le travail d’inventaire tournant créé, et plusieurs lignes de travail d’inventaire tournant sont créées en fonction de la définition du modèle de travail.

Avant que le travail d’inventaire tournant partiel puisse être traité, vous devez, au moins, sélectionner **Afficher le numéro d’article** pour l’option de menu de l’appareil mobile dans le cadre du paramétrage de l’inventaire tournant. L’opérateur d’entrepôt est invité à enregistrer uniquement les informations d’inventaire liées aux lignes de comptage (numéros d’article et dimensions de produit). Tout autre stock disponible est ignoré pour ce processus de comptage.

Pour le processus d’inventaire tournant partiel, la date et l’heure du **Dernier inventaire tournant** ne seront pas mises à jour pour l’emplacement, même si tous les articles disponibles à un emplacement donné sont comptés. L’inventaire tournant partiel ne prend pas en compte le paramètre **Jours entre l’inventaire tournant** sur la page **Plans d’inventaire tournant**. L’inventaire tournant partiel ne prend pas en charge l’inventaire simultané de plusieurs articles au même endroit. La fonctionnalité d’inventaire tournant partiel peut entraîner l’inventaire du même emplacement plusieurs fois pour un article lorsque **Traiter le plan d’inventaire tournant** est exécuté. Pour éviter ce scénario, spécifiez des filtres dans le champ **Sélectionnez des emplacements**.

> [!NOTE]
> L'application d'entrepôt ne fournit pas le bouton **Ajouter un LP ou un article** lorsque vous utilisez le processus de comptage partiel du cycle.

## <a name="example"></a>Exemple

Pour cet exemple, seul le numéro d’article A0001 doit être compté dans l’entrepôt 61.

1. Un modèle de travail pour l’inventaire tournant est créé. L’option **Pauses de ligne de travail** permet de regrouper des lignes de comptage traitées par numéro d’article. Par conséquent, le travail d’inventaire tournant créé aura des lignes par numéro d’article. Vous pouvez aussi regrouper les lignes par numéro de variante de produit.
1. Un nouveau plan d’inventaire tournant est créé qui référence le nouveau modèle de travail créé. Le plan d’inventaire tournant inclut tous les emplacements de l’entrepôt 61 (requête **Sélectionner des emplacements**) renfermant le numéro d’article A0001. La sélection de produits spécifiques est définie dans la section **Sélections de produits du plan d’inventaire tournant**.
1. Vous pouvez sélectionner des produits pour les plans d’inventaire tournant en définissant le champ **Emplacements vides** sur **Vides exclus**. Une fois le plan d’inventaire tournant traité, le travail d’inventaire tournant partiel du numéro d’article A0001 est créé. Le processus de comptage réel peut être exécuté à l’aide d’une option de menu du périphérique mobile pour l’inventaire tournant guidé.

## <a name="additional-resources"></a>Ressources supplémentaires

[Inventaire tournant](cycle-counting.md)
