---
title: Synchroniser les produits avec l'unité de stock entre Supply Chain Management et Field Service
description: Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits avec l'unité de stock depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 8b65e9640106c5d351270074e39c121e70917228
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251222"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a><span data-ttu-id="4173a-103">Synchroniser les produits avec l'unité de stock entre Supply Chain Management et Field Service</span><span class="sxs-lookup"><span data-stu-id="4173a-103">Synchronize products with inventory unit from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="4173a-104">Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits avec l'unité de stock depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="4173a-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="4173a-105">[![Synchronisation des processus d'entreprise entre Supply Chain Management et Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="4173a-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="4173a-106">Le modèle **Produits Field Service avec unité de stock (Supply Chain Management vers Field Service)** est basé sur le modèle **Produits Field Service (Supply Chain Management vers Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="4173a-106">The used **Field Service Products with Inventory unit (Supply Chain Management to Field Service)** template is based on the **Field Service Products (Supply Chain Management to Field Service)** template.</span></span> <span data-ttu-id="4173a-107">Pour plus d'informations, voir [Produits Field Service (Supply Chain Management vers Field Service)](field-service-product.md).</span><span class="sxs-lookup"><span data-stu-id="4173a-107">For more information, see [Field Service Products (Supply Chain Management to Field Service)](field-service-product.md).</span></span>

<span data-ttu-id="4173a-108">Cette rubrique décrit uniquement les différences entre les deux modèles :</span><span class="sxs-lookup"><span data-stu-id="4173a-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="4173a-109">**Produits Field Service avec unité de stock (Supply Chain Management vers Sales)**</span><span class="sxs-lookup"><span data-stu-id="4173a-109">**Field Service Products with Inventory unit (Supply Chain Management to Sales)**</span></span>
- <span data-ttu-id="4173a-110">**Produits Field Service (Supply Chain Management vers Field Service)**</span><span class="sxs-lookup"><span data-stu-id="4173a-110">**Field Service Products (Supply Chain Management to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="4173a-111">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="4173a-111">Templates and tasks</span></span>

<span data-ttu-id="4173a-112">**Nom du modèle dans l'intégration des données :**</span><span class="sxs-lookup"><span data-stu-id="4173a-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="4173a-113">Produits Field Service avec unité de stock (Supply Chain Management vers Sales)</span><span class="sxs-lookup"><span data-stu-id="4173a-113">Field Service Products with Inventory unit (Supply Chain Management to Sales)</span></span>

<span data-ttu-id="4173a-114">**Nom de la tâche dans le projet d'intégration de données :**</span><span class="sxs-lookup"><span data-stu-id="4173a-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="4173a-115">Produits</span><span class="sxs-lookup"><span data-stu-id="4173a-115">Products</span></span>

<span data-ttu-id="4173a-116">Le modèle **Produits Field Service avec unité de stock (Supply Chain Management vers Field Service)** inclut une mise en correspondance qui n'est pas incluse dans le modèle **Produits Field Service (Supply Chain Management vers Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="4173a-116">The **Field Service Products with Inventory unit (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Supply Chain Managementto Field Service)** template.</span></span> <span data-ttu-id="4173a-117">Cette mise en correspondance garantit que l'unité de stock nécessaire pour la synchronisation de niveau de stock est incluse.</span><span class="sxs-lookup"><span data-stu-id="4173a-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="4173a-118">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="4173a-118">Template mapping in Data integration</span></span>

<span data-ttu-id="4173a-119">Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="4173a-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a><span data-ttu-id="4173a-120">Produits Field Service avec unité de stock (Supply Chain Management vers Field Service) : Produits</span><span class="sxs-lookup"><span data-stu-id="4173a-120">Field Service Products with Inventory unit (Supply Chain Management to Field Service): Products</span></span>

<span data-ttu-id="4173a-121">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="4173a-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
