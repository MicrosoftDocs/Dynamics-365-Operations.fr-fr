---
title: Synchroniser des produits de Finance and Operations sur des produits de Field Service
description: Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 06d7ff272ecb79abded3c3d3ade1f6bc0ef1f095
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742353"
---
# <a name="synchronize-products-in-finance-and-operations-to-products-in-field-service"></a><span data-ttu-id="23cf3-103">Synchroniser des produits de Finance and Operations sur des produits de Field Service</span><span class="sxs-lookup"><span data-stu-id="23cf3-103">Synchronize products in Finance and Operations to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="23cf3-104">Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="23cf3-104">This topic discusses the templates and underlying task that are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="23cf3-105">Le modèle **Produits Field Service (Fin and Ops vers Field Service)** utilisé est basé sur le modèle **Produits (Fin and Ops vers Sales) – Direct** de Prospect en disponibilités.</span><span class="sxs-lookup"><span data-stu-id="23cf3-105">The used **Field Service Products (Fin and Ops to Field Service)** template is based on the **Products (Fin and Ops to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="23cf3-106">Pour plus d'informations, voir [Produits (entre Fin and Ops et Sales) - Direct](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="23cf3-106">For more information, see [Products (Fin and Ops to Sales) – Direct](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="23cf3-107">Cette rubrique décrit les différences entre les modèles **Produits Field Service (Fin and Ops vers Field Service)** et **Produits (Fin and Ops vers Sales) – Direct**.</span><span class="sxs-lookup"><span data-stu-id="23cf3-107">This topic only describes the differences between the **Field Service Products (Fin and Ops to Field Service)** and **Products (Fin and Ops to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="23cf3-108">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="23cf3-108">Templates and tasks</span></span>

<span data-ttu-id="23cf3-109">**Nom du modèle dans l'intégration des données :**</span><span class="sxs-lookup"><span data-stu-id="23cf3-109">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="23cf3-110">Produits Field Service (Fin and Ops vers Field Service)</span><span class="sxs-lookup"><span data-stu-id="23cf3-110">Field Service Products (Fin and Ops to Field Service)</span></span>

<span data-ttu-id="23cf3-111">**Nom de la tâche dans le projet d'intégration de données :**</span><span class="sxs-lookup"><span data-stu-id="23cf3-111">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="23cf3-112">Produits - Produits</span><span class="sxs-lookup"><span data-stu-id="23cf3-112">Products - Products</span></span>

<span data-ttu-id="23cf3-113">Le modèle **Produits Field Service (Fin and Ops vers Field Service)** inclut une mise en correspondance qui n'est pas incluse dans le modèle **Produits (Fin and Ops vers Sales) – Direct**.</span><span class="sxs-lookup"><span data-stu-id="23cf3-113">The **Field Service Products (Fin and Ops to Field Service)** template includes one mapping that isn't included in the **Products (Fin and Ops to Sales) – Direct** template.</span></span> <span data-ttu-id="23cf3-114">Cette mise en correspondance garantit que le champ spécifique à Field Service **Type de produit de service** obligatoire est défini correctement.</span><span class="sxs-lookup"><span data-stu-id="23cf3-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="23cf3-115">La mise en correspondance des valeurs suivante est utilisée.</span><span class="sxs-lookup"><span data-stu-id="23cf3-115">The following value mapping is used.</span></span>

```
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="23cf3-116">Dans Finance and Operations, la valeur **Type de produit Field Service** dans l'entité de données **Produits lancés vendables** est calculée comme suit :</span><span class="sxs-lookup"><span data-stu-id="23cf3-116">In Finance and Operations, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="23cf3-117">**Inventory :** Type de produit = Groupe de modèles Produit et Article, Produit stocké = True</span><span class="sxs-lookup"><span data-stu-id="23cf3-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="23cf3-118">**NonInventory :** Type de produit = Groupe de modèles Produit et Article, Produit stocké = False</span><span class="sxs-lookup"><span data-stu-id="23cf3-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="23cf3-119">**Service :** Type de produit = Service</span><span class="sxs-lookup"><span data-stu-id="23cf3-119">**Service:** Product type = Service</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="23cf3-120">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="23cf3-120">Template mapping in Data integration</span></span>

<span data-ttu-id="23cf3-121">Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="23cf3-121">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-fin-and-ops-to-field-service-products---products"></a><span data-ttu-id="23cf3-122">Produits Field Service (Fin and Ops vers Field Service) : Produits - produits</span><span class="sxs-lookup"><span data-stu-id="23cf3-122">Field Service Products (Fin and Ops to Field Service): Products - Products</span></span>

<span data-ttu-id="23cf3-123">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSProduct.png)](./media/FSProduct.png)</span><span class="sxs-lookup"><span data-stu-id="23cf3-123">[![Template mapping in Data integration](./media/FSProduct.png)](./media/FSProduct.png)</span></span>
