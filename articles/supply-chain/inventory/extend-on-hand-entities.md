---
title: Étendre le stock des entités de données disponibles
description: Cette rubrique fournit un exemple qui montre comment ajouter des champs étendus aux vues INVENTORSITEONHANDENTITY et INVENTWAREHOUSEONHANDENTITY, afin que les fonctionnalités des entités de données de stock disponible puissent fonctionner avec les extensions.
author: sherry-zheng
manager: tfehr
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-27
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: e3bf3a7d48b0aa3e48845882be0ee86da17ed040
ms.sourcegitcommit: e276348a63bfdb9e712c0ea86e6c2a68c50872c0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "3665402"
---
# <a name="extend-inventory-on-hand-data-entities"></a><span data-ttu-id="1dfde-103">Étendre le stock des entités de données disponibles</span><span class="sxs-lookup"><span data-stu-id="1dfde-103">Extend inventory on-hand data entities</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1dfde-104">Microsoft Dynamics 365 Supply Chain Management fournit des fonctionnalités [d’extensibilité](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) qui vous permettent [d’ajouter des champs aux tables via l’extension](../../fin-ops-core/dev-itpro/extensibility/add-field-extension).</span><span class="sxs-lookup"><span data-stu-id="1dfde-104">Microsoft Dynamics 365 Supply Chain Management provides [extensibility](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) features that let you [add fields to tables through extension](../../fin-ops-core/dev-itpro/extensibility/add-field-extension).</span></span> <span data-ttu-id="1dfde-105">Cette rubrique fournit un exemple qui montre comment ajouter des champs étendus aux vues `INVENTORSITEONHANDENTITY` et `INVENTWAREHOUSEONHANDENTITY`, afin que les fonctionnalités des entités de données de stock disponible puissent fonctionner avec les extensions.</span><span class="sxs-lookup"><span data-stu-id="1dfde-105">This topic provides an example that shows how to add extended fields to the `INVENTORSITEONHANDENTITY` and `INVENTWAREHOUSEONHANDENTITY` views, so that the capabilities of the inventory on-hand data entities can work with the extensions.</span></span> <span data-ttu-id="1dfde-106">Pour plus d’informations sur les entités de données, consultez [Vue d’ensemble de la gestion des données](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).</span><span class="sxs-lookup"><span data-stu-id="1dfde-106">For more information about data entities, see [Data management overview](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1dfde-107">Voici une liste de certaines des entités de données de stock disponible :</span><span class="sxs-lookup"><span data-stu-id="1dfde-107">Here is a list of some of the inventory on-hand data entities:</span></span>
>
> - <span data-ttu-id="1dfde-108">Stock disponible par site</span><span class="sxs-lookup"><span data-stu-id="1dfde-108">Inventory on-hand by site</span></span>
> - <span data-ttu-id="1dfde-109">Stock disponible par site V2</span><span class="sxs-lookup"><span data-stu-id="1dfde-109">Inventory on-hand by site V2</span></span>
> - <span data-ttu-id="1dfde-110">Stock disponible par entrepôt</span><span class="sxs-lookup"><span data-stu-id="1dfde-110">Inventory on-hand by warehouse</span></span>
> - <span data-ttu-id="1dfde-111">Stock disponible par entrepôt v2</span><span class="sxs-lookup"><span data-stu-id="1dfde-111">Inventory on-hand by warehouse v2</span></span>

<span data-ttu-id="1dfde-112">Après avoir ajouté des champs aux tables utilisées par la vue `inventSiteOnHandView`, vous devez synchroniser le moteur pour que les extensions soient correctement reconnues.</span><span class="sxs-lookup"><span data-stu-id="1dfde-112">After you add fields to tables that are used by the `inventSiteOnHandView` view, you must sync the engine so that the extensions are correctly recognized.</span></span>

1. <span data-ttu-id="1dfde-113">Étendez la vue `InventSiteOnHandView` en ajoutant le champ d’extension.</span><span class="sxs-lookup"><span data-stu-id="1dfde-113">Extend the `InventSiteOnHandView` view by adding the extension field.</span></span>
1. <span data-ttu-id="1dfde-114">Étendez la vue `InventSiteOnHandAggregatedView` avec les champs d’extension.</span><span class="sxs-lookup"><span data-stu-id="1dfde-114">Extend the `InventSiteOnHandAggregatedView` view with the extension fields.</span></span>
1. <span data-ttu-id="1dfde-115">Étendez la classe viewBuilder `InventSiteOnHandAggregatedViewBuilder` en modifiant la méthode `getExtensionFields()`.</span><span class="sxs-lookup"><span data-stu-id="1dfde-115">Extend the `InventSiteOnHandAggregatedViewBuilder` viewBuilder class by modifying the `getExtensionFields()` method.</span></span> <span data-ttu-id="1dfde-116">De cette manière, vous mappez les anciens champs de vue aux nouveaux champs de vue lorsque la synchronisation viewBuilder est exécutée.</span><span class="sxs-lookup"><span data-stu-id="1dfde-116">In this way, you map old view fields to new view fields when viewBuilder synchronization is run.</span></span>

<span data-ttu-id="1dfde-117">Par exemple, vous avez ajouté les quatre champs suivants à la table `InventTable` par le biais de l’extension :</span><span class="sxs-lookup"><span data-stu-id="1dfde-117">For example, you've added the following four fields to the `InventTable` table through extension:</span></span>

- <span data-ttu-id="1dfde-118">Champ personnalisé 1</span><span class="sxs-lookup"><span data-stu-id="1dfde-118">Custom field 1</span></span>
- <span data-ttu-id="1dfde-119">Champ personnalisé 2</span><span class="sxs-lookup"><span data-stu-id="1dfde-119">Custom field 2</span></span>
- <span data-ttu-id="1dfde-120">Champ personnalisé 3</span><span class="sxs-lookup"><span data-stu-id="1dfde-120">Custom field 3</span></span>
- <span data-ttu-id="1dfde-121">Champ personnalisé 4</span><span class="sxs-lookup"><span data-stu-id="1dfde-121">Custom field 4</span></span>

<span data-ttu-id="1dfde-122">Dans ce cas, vous devez modifier la méthode `getExtensionFields()` de la manière suivante.</span><span class="sxs-lookup"><span data-stu-id="1dfde-122">In the case, you must modify the `getExtensionFields()` method in the following way.</span></span>

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

<span data-ttu-id="1dfde-123">Une fois ces étapes terminées, vous pouvez étendre le stock disponible par site et le stock disponible par entités de données d’entrepôt en ajoutant les nouveaux champs.</span><span class="sxs-lookup"><span data-stu-id="1dfde-123">After you complete these steps, you can extend the inventory on-hand by site and inventory on-hand by warehouse data entities by adding the new fields.</span></span> <span data-ttu-id="1dfde-124">De cette manière, vous vous assurez que les champs étendus sont reconnus et inclus lors de la migration de données qui utilise ces entités de données.</span><span class="sxs-lookup"><span data-stu-id="1dfde-124">In this way, you ensure that the extended fields are recognized and included during data migration that uses those data entities.</span></span>