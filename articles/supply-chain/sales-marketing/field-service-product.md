---
title: Synchroniser directement les produits provenant du module Supply Chain Management sur les produits dans Field Service
description: Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 04/09/2018
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 1efa4e403f5cf2cdc5fb797f05781f6d42245ed5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210012"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a><span data-ttu-id="e06f2-103">Synchroniser directement les produits provenant du module Supply Chain Management sur les produits dans Field Service</span><span class="sxs-lookup"><span data-stu-id="e06f2-103">Synchronize products in Supply Chain Management to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e06f2-104">Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="e06f2-104">This topic discusses the templates and underlying task that are used to synchronize products from Dynamics 365 Supply Chain Management to Dynamics 365  Field Service.</span></span>

<span data-ttu-id="e06f2-105">Le modèle **Produits Field Service (Supply Chain Management vers Field Service)** utilisé est basé sur le modèle **Produits (Supply Chain Management vers Sales) – Direct** de Prospect en disponibilités.</span><span class="sxs-lookup"><span data-stu-id="e06f2-105">The used **Field Service Products (Supply Chain Management to Field Service)** template is based on the **Products (Supply Chain Management to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="e06f2-106">Pour plus d'informations, voir [Produits (entre Supply Chain Management et Sales) - Direct](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="e06f2-106">For more information, see [Products (Supply Chain Management to Sales) – Direct](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="e06f2-107">Cette rubrique décrit les différences entre les modèles **Produits Field Service (Supply Chain Management vers Field Service)** et **Produits (Supply Chain Management vers Sales) – Direct**.</span><span class="sxs-lookup"><span data-stu-id="e06f2-107">This topic only describes the differences between the **Field Service Products (Supply Chain Management to Field Service)** and **Products (Supply Chain Management to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="e06f2-108">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="e06f2-108">Templates and tasks</span></span>

<span data-ttu-id="e06f2-109">**Nom du modèle dans l'intégration des données**</span><span class="sxs-lookup"><span data-stu-id="e06f2-109">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="e06f2-110">Produits Field Service (Supply Chain Management vers Field Service)</span><span class="sxs-lookup"><span data-stu-id="e06f2-110">Field Service Products (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="e06f2-111">**Nom de la tâche dans le projet d'intégration de données**</span><span class="sxs-lookup"><span data-stu-id="e06f2-111">**Name of the task in the Data integration project**</span></span>

- <span data-ttu-id="e06f2-112">Produits - Produits</span><span class="sxs-lookup"><span data-stu-id="e06f2-112">Products - Products</span></span>

<span data-ttu-id="e06f2-113">Le modèle **Produits Field Service (Supply Chain Management vers Field Service)** utilisé inclut un mappage qui n'est pas inclus dans le modèle **Produits (Supply Chain Management vers Sales) – Direct**.</span><span class="sxs-lookup"><span data-stu-id="e06f2-113">The **Field Service Products (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Products (Supply Chain Management to Sales) – Direct** template.</span></span> <span data-ttu-id="e06f2-114">Cette mise en correspondance garantit que le champ spécifique à Field Service **Type de produit de service** obligatoire est défini correctement.</span><span class="sxs-lookup"><span data-stu-id="e06f2-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```Text
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="e06f2-115">La mise en correspondance des valeurs suivante est utilisée.</span><span class="sxs-lookup"><span data-stu-id="e06f2-115">The following value mapping is used.</span></span>

```Text
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="e06f2-116">Dans Supply Chain Management, la valeur **Type de produit Field Service** dans l'entité de données **Produits lancés vendables** est calculée comme suit :</span><span class="sxs-lookup"><span data-stu-id="e06f2-116">In Supply Chain Management, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="e06f2-117">**Inventory :** Type de produit = Groupe de modèles Produit et Article, Produit stocké = True</span><span class="sxs-lookup"><span data-stu-id="e06f2-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="e06f2-118">**NonInventory :** Type de produit = Groupe de modèles Produit et Article, Produit stocké = False</span><span class="sxs-lookup"><span data-stu-id="e06f2-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="e06f2-119">**Service :** Type de produit = Service</span><span class="sxs-lookup"><span data-stu-id="e06f2-119">**Service:** Product type = Service</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="e06f2-120">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="e06f2-120">Template mapping in Data integration</span></span>

<span data-ttu-id="e06f2-121">Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="e06f2-121">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a><span data-ttu-id="e06f2-122">Produits Field Service (Supply Chain Management vers Field Service) : Produits - Produits</span><span class="sxs-lookup"><span data-stu-id="e06f2-122">Field Service Products (Supply Chain Management to Field Service): Products - Products</span></span>

<span data-ttu-id="e06f2-123">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSProduct.png)](./media/FSProduct.png)</span><span class="sxs-lookup"><span data-stu-id="e06f2-123">[![Template mapping in Data integration](./media/FSProduct.png)](./media/FSProduct.png)</span></span>
