---
title: Synchroniser les produits avec l'unité de stock entre Finance and Operations et Field Service
description: Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits avec l'unité de stock depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
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
ms.openlocfilehash: 8e421be79fde6103be6344040b6ae6cda0626c5a
ms.sourcegitcommit: d9ed934a142b88340d268fd2bd3753475a3712b0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2019
ms.locfileid: "836300"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a><span data-ttu-id="c98e9-103">Synchroniser les produits avec l'unité de stock entre Finance and Operations et Field Service</span><span class="sxs-lookup"><span data-stu-id="c98e9-103">Synchronize products with inventory unit from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c98e9-104">Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits avec l'unité de stock depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="c98e9-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="c98e9-105">[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="c98e9-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="c98e9-106">Le modèle **Produits Field Service avec unité de stock (Finance and Operations vers Field Service)** est basé sur le modèle **Produits Field Service (Finance and Operations vers Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="c98e9-106">The used **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template is based on the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="c98e9-107">Pour plus d'informations, voir [Produits Field Service (Finance and Operations vers Field Service)](field-service-product.md).</span><span class="sxs-lookup"><span data-stu-id="c98e9-107">For more information, see [Field Service Products (Finance and Operations to Field Service)](field-service-product.md).</span></span>

<span data-ttu-id="c98e9-108">Cette rubrique décrit uniquement les différences entre les deux modèles :</span><span class="sxs-lookup"><span data-stu-id="c98e9-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="c98e9-109">**Produits Field Service avec l'unité de stock (Finance and Operations vers Sales)**</span><span class="sxs-lookup"><span data-stu-id="c98e9-109">**Field Service Products with Inventory unit (Finance and Operations to Sales)**</span></span>
- <span data-ttu-id="c98e9-110">**Produits Field Service (Finance and Operations vers Field Service)**</span><span class="sxs-lookup"><span data-stu-id="c98e9-110">**Field Service Products (Finance and Operations to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="c98e9-111">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="c98e9-111">Templates and tasks</span></span>

<span data-ttu-id="c98e9-112">**Nom du modèle dans l'intégration des données :**</span><span class="sxs-lookup"><span data-stu-id="c98e9-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="c98e9-113">Produits Field Service avec l'unité de stock (Finance and Operations vers Sales)</span><span class="sxs-lookup"><span data-stu-id="c98e9-113">Field Service Products with Inventory unit (Finance and Operations to Sales)</span></span>

<span data-ttu-id="c98e9-114">**Nom de la tâche dans le projet d'intégration de données :**</span><span class="sxs-lookup"><span data-stu-id="c98e9-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="c98e9-115">Produits</span><span class="sxs-lookup"><span data-stu-id="c98e9-115">Products</span></span>

<span data-ttu-id="c98e9-116">Le modèle **Produits Field Service avec unité de stock (Finance and Operations vers Field Service)** comprend une mise en correspondance qui n'est pas incluse dans le modèle **Produits Field Service (Finance and Operations vers Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="c98e9-116">The **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="c98e9-117">Cette mise en correspondance garantit que l'unité de stock nécessaire pour la synchronisation de niveau de stock est incluse.</span><span class="sxs-lookup"><span data-stu-id="c98e9-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="c98e9-118">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="c98e9-118">Template mapping in Data integration</span></span>

<span data-ttu-id="c98e9-119">Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="c98e9-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a><span data-ttu-id="c98e9-120">Produits Field Service avec unité de stock (Finance and Operations vers Field Service) : Produits</span><span class="sxs-lookup"><span data-stu-id="c98e9-120">Field Service Products with Inventory unit (Finance and Operations to Field Service): Products</span></span>

<span data-ttu-id="c98e9-121">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="c98e9-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
