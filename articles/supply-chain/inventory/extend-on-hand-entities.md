---
title: Étendre le stock des entités de données disponibles
description: Cet article fournit un exemple qui montre comment ajouter des champs étendus aux vues INVENTORSITEONHANDENTITY et INVENTWAREHOUSEONHANDENTITY, afin que les fonctionnalités des entités de données de stock disponible puissent fonctionner avec les extensions.
author: yufeihuang
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-07-27
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 352b466a185bcd0778ea17e598129864c1547987
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906035"
---
# <a name="extend-inventory-on-hand-data-entities"></a>Étendre le stock des entités de données disponibles

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management fournit des fonctionnalités [d’extensibilité](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) qui vous permettent [d’ajouter des champs aux tables via l’extension](../../fin-ops-core/dev-itpro/extensibility/add-field-extension.md). Cet article fournit un exemple qui montre comment ajouter des champs étendus aux vues `INVENTORSITEONHANDENTITY` et `INVENTWAREHOUSEONHANDENTITY`, afin que les fonctionnalités des entités de données de stock disponible puissent fonctionner avec les extensions. Pour plus d’informations sur les entités de données, consultez [Vue d’ensemble de la gestion des données](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

> [!NOTE]
> Voici une liste de certaines des entités de données de stock disponible :
>
> - Stock disponible par site
> - Stock disponible par site V2
> - Stock disponible par entrepôt
> - Stock disponible par entrepôt v2

Après avoir ajouté des champs aux tables utilisées par la vue `inventSiteOnHandView`, vous devez synchroniser le moteur pour que les extensions soient correctement reconnues.

1. Étendez la vue `InventSiteOnHandView` en ajoutant le champ d’extension.
1. Étendez la vue `InventSiteOnHandAggregatedView` avec les champs d’extension.
1. Étendez la classe viewBuilder `InventSiteOnHandAggregatedViewBuilder` en modifiant la méthode `getExtensionFields()`. De cette manière, vous mappez les anciens champs de vue aux nouveaux champs de vue lorsque la synchronisation viewBuilder est exécutée.

Par exemple, vous avez ajouté les quatre champs suivants à la table `InventTable` par le biais de l’extension :

- Champ personnalisé 1
- Champ personnalisé 2
- Champ personnalisé 3
- Champ personnalisé 4

Dans ce cas, vous devez modifier la méthode `getExtensionFields()` de la manière suivante.

```xpp
[ExtensionOf(classStr(InventSiteOnHandAggregatedViewBuilder))]
public final class InventOnHandAggregatedViewBuilder\_Extension
{
    protected Map getExtensionFields()
    {
        next getExtensionFields();
        Map extensionFields = new Map(Types::Int64, Types::Int64);
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 1), fieldNum(InventSiteOnHandAggregatedView, Custom field 1));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 2), fieldNum(InventSiteOnHandAggregatedView, Custom field 2));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 3), fieldNum(InventSiteOnHandAggregatedView, Custom field 3));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 4), fieldNum(InventSiteOnHandAggregatedView, Custom field 4));
        return extensionFields;
    }
}
```

Une fois ces étapes terminées, vous pouvez étendre le stock disponible par site et le stock disponible par entités de données d’entrepôt en ajoutant les nouveaux champs. De cette manière, vous vous assurez que les champs étendus sont reconnus et inclus lors de la migration de données qui utilise ces entités de données.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]