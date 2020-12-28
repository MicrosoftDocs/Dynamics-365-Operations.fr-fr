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
ms.openlocfilehash: d96d1cd91bad4f950868074d9558cb403821d73f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428050"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a><span data-ttu-id="29a50-103">Synchroniser directement les produits provenant du module Supply Chain Management sur les produits dans Field Service</span><span class="sxs-lookup"><span data-stu-id="29a50-103">Synchronize products in Supply Chain Management to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="29a50-104">Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="29a50-104">This topic discusses the templates and underlying task that are used to synchronize products from Dynamics 365 Supply Chain Management to Dynamics 365  Field Service.</span></span>

<span data-ttu-id="29a50-105">Le modèle **Produits Field Service (Supply Chain Management vers Field Service)** utilisé est basé sur le modèle **Produits (Supply Chain Management vers Sales) – Direct** de Prospect en disponibilités.</span><span class="sxs-lookup"><span data-stu-id="29a50-105">The used **Field Service Products (Supply Chain Management to Field Service)** template is based on the **Products (Supply Chain Management to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="29a50-106">Pour plus d'informations, voir [Produits (entre Supply Chain Management et Sales) - Direct](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="29a50-106">For more information, see [Products (Supply Chain Management to Sales) – Direct](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="29a50-107">Cette rubrique décrit les différences entre les modèles **Produits Field Service (Supply Chain Management vers Field Service)** et **Produits (Supply Chain Management vers Sales) – Direct**.</span><span class="sxs-lookup"><span data-stu-id="29a50-107">This topic only describes the differences between the **Field Service Products (Supply Chain Management to Field Service)** and **Products (Supply Chain Management to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="29a50-108">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="29a50-108">Templates and tasks</span></span>

<span data-ttu-id="29a50-109">**Nom du modèle dans l'intégration des données**</span><span class="sxs-lookup"><span data-stu-id="29a50-109">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="29a50-110">Produits Field Service (Supply Chain Management vers Field Service)</span><span class="sxs-lookup"><span data-stu-id="29a50-110">Field Service Products (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="29a50-111">**Nom de la tâche dans le projet d'intégration de données**</span><span class="sxs-lookup"><span data-stu-id="29a50-111">**Name of the task in the Data integration project**</span></span>

- <span data-ttu-id="29a50-112">Produits - Produits</span><span class="sxs-lookup"><span data-stu-id="29a50-112">Products - Products</span></span>

<span data-ttu-id="29a50-113">Le modèle **Produits Field Service (Supply Chain Management vers Field Service)** utilisé inclut un mappage qui n'est pas inclus dans le modèle **Produits (Supply Chain Management vers Sales) – Direct**.</span><span class="sxs-lookup"><span data-stu-id="29a50-113">The **Field Service Products (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Products (Supply Chain Management to Sales) – Direct** template.</span></span> <span data-ttu-id="29a50-114">Cette mise en correspondance garantit que le champ spécifique à Field Service **Type de produit de service** obligatoire est défini correctement.</span><span class="sxs-lookup"><span data-stu-id="29a50-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```plaintext
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="29a50-115">La mise en correspondance des valeurs suivante est utilisée.</span><span class="sxs-lookup"><span data-stu-id="29a50-115">The following value mapping is used.</span></span>

```plaintext
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="29a50-116">Dans Supply Chain Management, la valeur **Type de produit Field Service** dans l'entité de données **Produits lancés vendables** est calculée comme suit :</span><span class="sxs-lookup"><span data-stu-id="29a50-116">In Supply Chain Management, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="29a50-117">**Inventory :** Type de produit = Groupe de modèles Produit et Article, Produit stocké = True</span><span class="sxs-lookup"><span data-stu-id="29a50-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="29a50-118">**NonInventory :** Type de produit = Groupe de modèles Produit et Article, Produit stocké = False</span><span class="sxs-lookup"><span data-stu-id="29a50-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="29a50-119">**Service :** Type de produit = Service</span><span class="sxs-lookup"><span data-stu-id="29a50-119">**Service:** Product type = Service</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="29a50-120">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="29a50-120">Template mapping in Data integration</span></span>

<span data-ttu-id="29a50-121">Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="29a50-121">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a><span data-ttu-id="29a50-122">Produits Field Service (Supply Chain Management vers Field Service) : Produits - Produits</span><span class="sxs-lookup"><span data-stu-id="29a50-122">Field Service Products (Supply Chain Management to Field Service): Products - Products</span></span>

<span data-ttu-id="29a50-123">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSProduct.png)](./media/FSProduct.png)</span><span class="sxs-lookup"><span data-stu-id="29a50-123">[![Template mapping in Data integration](./media/FSProduct.png)](./media/FSProduct.png)</span></span>
