---
title: Synchroniser les produits avec l'unité de stock entre Finance and Operations et Field Service
description: Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits avec l'unité de stock depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 5d3767c1a499f3d888d8fc2ce06c2837442e39f0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "359242"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a><span data-ttu-id="a8226-103">Synchroniser les produits avec l'unité de stock entre Finance and Operations et Field Service</span><span class="sxs-lookup"><span data-stu-id="a8226-103">Synchronize products with inventory unit from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a8226-104">Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits avec l'unité de stock depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="a8226-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="a8226-105">[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="a8226-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="a8226-106">Le modèle **Produits Field Service (Finance and Operations vers Field Service)** utilisé est basé sur le modèle **Produits (Finance and Operations vers Sales) – Direct** de Prospect en disponibilités.</span><span class="sxs-lookup"><span data-stu-id="a8226-106">The used **Field Service Products (Finance and Operations to Field Service)** template is based on the **Products (Finance and Operations to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="a8226-107">Pour plus d'informations, voir [Produits (entre Finance and Operations et Sales) - Direct](products-template-mapping-direct.md).</span><span class="sxs-lookup"><span data-stu-id="a8226-107">For more information, see [Products (Finance and Operations to Sales) – Direct](products-template-mapping-direct.md).</span></span>

<span data-ttu-id="a8226-108">Cette rubrique décrit les différences entre les modèles **Produits Field Service (Finance and Operations vers Field Service)** et **Produits Field Service (Finance and Operations vers Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="a8226-108">This topic only describes the differences between the **Field Service Products (Finance and Operations to Field Service)** and **Field Service Products (Finance and Operations to Field Service)** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="a8226-109">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="a8226-109">Templates and tasks</span></span>

<span data-ttu-id="a8226-110">**Nom du modèle dans l'intégration des données :**</span><span class="sxs-lookup"><span data-stu-id="a8226-110">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="a8226-111">Produits Field Service avec l'unité de stock (Finance and Operations vers Sales)</span><span class="sxs-lookup"><span data-stu-id="a8226-111">Field Service Products with Inventory unit (Finance and Operations to Sales)</span></span>

<span data-ttu-id="a8226-112">**Nom de la tâche dans le projet d'intégration de données :**</span><span class="sxs-lookup"><span data-stu-id="a8226-112">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="a8226-113">Produits</span><span class="sxs-lookup"><span data-stu-id="a8226-113">Products</span></span>

<span data-ttu-id="a8226-114">Le modèle **Produits Field Service avec unité de stock (Finance and Operations vers Field Service)** comprend une mise en correspondance qui n'est pas incluse dans le modèle **Produits Field Service (Finance and Operations vers Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="a8226-114">The **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="a8226-115">Cette mise en correspondance garantit que l'unité de stock nécessaire pour la synchronisation de niveau de stock est incluse.</span><span class="sxs-lookup"><span data-stu-id="a8226-115">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="a8226-116">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="a8226-116">Template mapping in Data integration</span></span>

<span data-ttu-id="a8226-117">Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="a8226-117">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a><span data-ttu-id="a8226-118">Produits Field Service avec unité de stock (Finance and Operations vers Field Service) : Produits</span><span class="sxs-lookup"><span data-stu-id="a8226-118">Field Service Products with Inventory unit (Finance and Operations to Field Service): Products</span></span>

<span data-ttu-id="a8226-119">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="a8226-119">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
