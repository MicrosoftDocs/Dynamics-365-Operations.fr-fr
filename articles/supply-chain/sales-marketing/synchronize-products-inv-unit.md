---
title: Synchroniser les produits avec l'unité de stock entre Supply Chain Management et Field Service
description: Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits avec l'unité de stock depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 911c5cc79ae359bbb77d31f366ccfeabf282a33e
ms.sourcegitcommit: 4a32634690a741535f3f4babfd753f7c227ad6fe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/05/2020
ms.locfileid: "3958691"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a><span data-ttu-id="91928-103">Synchroniser les produits avec l'unité de stock entre Supply Chain Management et Field Service</span><span class="sxs-lookup"><span data-stu-id="91928-103">Synchronize products with inventory unit from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="91928-104">Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits avec l'unité de stock depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="91928-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="91928-105">[![Synchronisation des processus d'entreprise entre Supply Chain Management et Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="91928-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="91928-106">Le modèle **Produits Field Service avec unité de stock (Supply Chain Management vers Field Service)** est basé sur le modèle **Produits Field Service (Supply Chain Management vers Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="91928-106">The used **Field Service Products with Inventory unit (Supply Chain Management to Field Service)** template is based on the **Field Service Products (Supply Chain Management to Field Service)** template.</span></span> <span data-ttu-id="91928-107">Pour en savoir plus, voir [Synchroniser les produits dans Supply Chain Management vers les produits dans Field Service](field-service-product.md).</span><span class="sxs-lookup"><span data-stu-id="91928-107">For more information, see [Synchronize products in Supply Chain Management to products in Field Service](field-service-product.md).</span></span>

<span data-ttu-id="91928-108">Cette rubrique décrit uniquement les différences entre les deux modèles :</span><span class="sxs-lookup"><span data-stu-id="91928-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="91928-109">**Produits Field Service avec unité de stock (Supply Chain Management vers Sales)**</span><span class="sxs-lookup"><span data-stu-id="91928-109">**Field Service Products with Inventory unit (Supply Chain Management to Sales)**</span></span>
- <span data-ttu-id="91928-110">**Produits Field Service (Supply Chain Management vers Field Service)**</span><span class="sxs-lookup"><span data-stu-id="91928-110">**Field Service Products (Supply Chain Management to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="91928-111">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="91928-111">Templates and tasks</span></span>

<span data-ttu-id="91928-112">**Nom du modèle dans l'intégration des données :**</span><span class="sxs-lookup"><span data-stu-id="91928-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="91928-113">Produits Field Service avec unité de stock (Supply Chain Management vers Sales)</span><span class="sxs-lookup"><span data-stu-id="91928-113">Field Service Products with Inventory unit (Supply Chain Management to Sales)</span></span>

<span data-ttu-id="91928-114">**Nom de la tâche dans le projet d'intégration de données :**</span><span class="sxs-lookup"><span data-stu-id="91928-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="91928-115">Produits</span><span class="sxs-lookup"><span data-stu-id="91928-115">Products</span></span>

<span data-ttu-id="91928-116">Le modèle **Produits Field Service avec unité de stock (Supply Chain Management vers Field Service)** inclut une mise en correspondance qui n'est pas incluse dans le modèle **Produits Field Service (Supply Chain Management vers Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="91928-116">The **Field Service Products with Inventory unit (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Supply Chain Management to Field Service)** template.</span></span> <span data-ttu-id="91928-117">Cette mise en correspondance garantit que l'unité de stock nécessaire pour la synchronisation de niveau de stock est incluse.</span><span class="sxs-lookup"><span data-stu-id="91928-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```plaintext
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="91928-118">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="91928-118">Template mapping in Data integration</span></span>

<span data-ttu-id="91928-119">Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="91928-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a><span data-ttu-id="91928-120">Produits Field Service avec unité de stock (Supply Chain Management vers Field Service) : Produits</span><span class="sxs-lookup"><span data-stu-id="91928-120">Field Service Products with Inventory unit (Supply Chain Management to Field Service): Products</span></span>

<span data-ttu-id="91928-121">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="91928-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
