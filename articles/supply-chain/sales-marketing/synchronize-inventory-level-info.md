---
title: Synchroniser les informations sur le niveau de stock entre Finance and Operations et Field Service
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les informations au niveau du stock depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
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
ms.openlocfilehash: 6b2bdf1ca6f6ae43cd85c8a1353ee8305052761d
ms.sourcegitcommit: a6d385db6636ef2b7fb6b24d37a2160c8d5a3c0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/14/2019
ms.locfileid: "842554"
---
# <a name="synchronize-inventory-level-information-from-finance-and-operations-to-field-service"></a><span data-ttu-id="4982b-103">Synchroniser les informations sur le niveau de stock entre Finance and Operations et Field Service</span><span class="sxs-lookup"><span data-stu-id="4982b-103">Synchronize inventory level information from Finance and Operations to Field Service</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="4982b-104">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les informations au niveau du stock depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="4982b-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory-level information from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="4982b-105">[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span><span class="sxs-lookup"><span data-stu-id="4982b-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="4982b-106">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="4982b-106">Templates and tasks</span></span>
<span data-ttu-id="4982b-107">Le modèle suivant et les tâches sous-jacentes sont utilisées pour exécuter la synchronisation aux niveaux du stock disponible de Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="4982b-107">The following template and underlying tasks are used to synchronize inventory on-hand levels from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="4982b-108">**Modèle dans l'intégration de données**</span><span class="sxs-lookup"><span data-stu-id="4982b-108">**Template in Data integration**</span></span>
- <span data-ttu-id="4982b-109">Stock produit (Fin and Ops vers Field Service)</span><span class="sxs-lookup"><span data-stu-id="4982b-109">Product Inventory (Fin and Ops to Field Service)</span></span>
  
<span data-ttu-id="4982b-110">**Tâche du projet d'intégration des données**</span><span class="sxs-lookup"><span data-stu-id="4982b-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="4982b-111">Produit de stock</span><span class="sxs-lookup"><span data-stu-id="4982b-111">Product inventory</span></span>

<span data-ttu-id="4982b-112">Les tâches de synchronisation suivantes sont requises avant que la synchronisation des niveaux de stock puisse avoir lieu :</span><span class="sxs-lookup"><span data-stu-id="4982b-112">The following synchronization tasks are required before synchronization of inventory levels can occur:</span></span>
- <span data-ttu-id="4982b-113">Entrepôts (Fin and Ops vers Field Service)</span><span class="sxs-lookup"><span data-stu-id="4982b-113">Warehouses (Fin and Ops to Field Service)</span></span> 
- <span data-ttu-id="4982b-114">Produits Field Service avec unité de stock (Fin and Ops vers Sales)</span><span class="sxs-lookup"><span data-stu-id="4982b-114">Field Service products with Inventory unit (Fin and Ops to Sales)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="4982b-115">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="4982b-115">Entity set</span></span>

| <span data-ttu-id="4982b-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="4982b-116">Field Service</span></span>                      | <span data-ttu-id="4982b-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4982b-117">Finance and Operations</span></span>                 |
|------------------------------------|----------------------------------------|
| <span data-ttu-id="4982b-118">msdynce_externalproductinventories</span><span class="sxs-lookup"><span data-stu-id="4982b-118">msdynce_externalproductinventories</span></span> | <span data-ttu-id="4982b-119">Stock CDS disponible par entrepôt</span><span class="sxs-lookup"><span data-stu-id="4982b-119">CDS inventory on-hand by warehouse</span></span>     |

## <a name="entity-flow"></a><span data-ttu-id="4982b-120">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="4982b-120">Entity flow</span></span>
<span data-ttu-id="4982b-121">Les informations sur le niveau de stock sont envoyées de Finance and Operations vers Field Service pour certains produits.</span><span class="sxs-lookup"><span data-stu-id="4982b-121">Inventory-level information from Finance and Operation is sent to Field Service for selected products.</span></span> <span data-ttu-id="4982b-122">Les informations de niveau de stock comprennent :</span><span class="sxs-lookup"><span data-stu-id="4982b-122">The inventory-level information includes:</span></span> 
- <span data-ttu-id="4982b-123">La quantité disponible (quantité physique actuelle enregistrée dans l'entrepôt)</span><span class="sxs-lookup"><span data-stu-id="4982b-123">On hand quantity (current recorded physical quantity located in the warehouse)</span></span>
- <span data-ttu-id="4982b-124">Quantité en commande (quantité totale en commande enregistrée - c'est-à-dire commandes client)</span><span class="sxs-lookup"><span data-stu-id="4982b-124">On order quantity (total recorded quantity on order, such as sales orders)</span></span>
- <span data-ttu-id="4982b-125">Quantité commandée (quantité totale commandée enregistrée - c'est-à-dire commandes fournisseur)</span><span class="sxs-lookup"><span data-stu-id="4982b-125">Ordered quantity (total recorded ordered quantity, such as purchase orders)</span></span>

<span data-ttu-id="4982b-126">Ces informations sont capturées par produit lancé pour chaque entrepôt et synchronisées selon le suivi des modifications, lorsque le niveau de stock change.</span><span class="sxs-lookup"><span data-stu-id="4982b-126">This information is captured per released product for each warehouse and synchronized based on change tracking, when the inventory level changes.</span></span>

<span data-ttu-id="4982b-127">Dans Field Service, la solution d'intégration crée des journaux de stock pour le delta, pour obtenir les niveaux dans Field Service pour faire correspondre les niveaux dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4982b-127">In Field Service, the integration solution creates inventory journals for the delta, so that the levels in Field Service match the levels in Finance and Operations.</span></span>

<span data-ttu-id="4982b-128">Finance and Operations agira comme base pour les niveaux de stock.</span><span class="sxs-lookup"><span data-stu-id="4982b-128">Finance and Operations will act as the master for inventory levels.</span></span> <span data-ttu-id="4982b-129">Il est donc important de paramétrer l'intégration pour les ordres d'exécution, les transferts et les ajustements entre Field Service et Finance and Operations si cette fonctionnalité est utilisée dans Field Service, ainsi qu'avec la synchronisation des niveaux de stock de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4982b-129">Therefore it is important to set up integration for work orders, transfers, and adjustments from Field Service to Finance and Operations if this functionality is used in Field Service, together with synchronization of inventory levels from Finance and Operations.</span></span>

<span data-ttu-id="4982b-130">Les produits et les entrepôts dans lesquels les niveaux de stock sont basés sur Finance and Operations peuvent être contrôlés avec Requête et filtrage avancés (Power Query).</span><span class="sxs-lookup"><span data-stu-id="4982b-130">The products and warehouses where inventory levels are mastered from Finance and Operations can be controlled with the Advanced Query and Filtering (Power Query).</span></span>

> [!NOTE]
> <span data-ttu-id="4982b-131">Vous pouvez créer plusieurs entrepôts dans Field Service (avec **Géré en externe = Non**), puis les mapper à un seul entrepôt dans Finance and Operations, avec la fonctionnalité de requête et de filtrage avancée.</span><span class="sxs-lookup"><span data-stu-id="4982b-131">It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained = No**) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="4982b-132">Cela est utile dans les situations où vous souhaitez que Field Service serve de base au niveau de stock détaillé et n'envoyer que des mises à jour à Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4982b-132">This is used in situations where you want Field Service to master the detailed inventory level and only send updates to Finance and Operations.</span></span> <span data-ttu-id="4982b-133">Dans ce cas, Field Service ne reçoit pas les mises à jour de niveau de stock de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4982b-133">In this case, Field Service will not receive inventory-level updates from Finance and Operations.</span></span> <span data-ttu-id="4982b-134">Pour en savoir plus, voir [Synchroniser les ajustements de stock entre Field Service et Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) et [Synchroniser des bons de travail de Field Service sur des commandes client de Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="4982b-134">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="4982b-135">Solution Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="4982b-135">Field Service CRM solution</span></span>
<span data-ttu-id="4982b-136">L'entité **Stock de produits externe** est une nouvelle entité utilisée uniquement pour la partie principale dans l'intégration.</span><span class="sxs-lookup"><span data-stu-id="4982b-136">The **External product inventory** entity is only used for back end in to the integration.</span></span> <span data-ttu-id="4982b-137">Elle reçoit les valeurs de niveau de stock de Finance and Operations dans l'intégration puis les transforme en journaux de stock manuel, qui modifie ensuite les produits de stock dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="4982b-137">This entity receives the inventory level values from Finance and Operations in the integration and then transforms those values to Manual inventory journals, which then changes the Inventory products in the Warehouse.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="4982b-138">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="4982b-138">Prerequisites and mapping setup</span></span>

### <a name="data-integration-project"></a><span data-ttu-id="4982b-139">Projet d'intégration des données</span><span class="sxs-lookup"><span data-stu-id="4982b-139">Data integration project</span></span>
<span data-ttu-id="4982b-140">Vous pouvez appliquer des filtres avec Requête et filtrage avancés afin de contrôler que seuls les produits et entrepôts souhaités envoient des informations de niveau de stock de Finance and Operations vers Field Service.</span><span class="sxs-lookup"><span data-stu-id="4982b-140">You can apply filters with Advanced Query and Filtering so that only certain products and warehouses send inventory-level information from Finance and Operations to Field Service.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="4982b-141">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="4982b-141">Template mapping in Data integration</span></span>

### <a name="product-inventory-fin-and-ops-to-field-service-product-inventory"></a><span data-ttu-id="4982b-142">Stock produit (Fin and Ops vers Field Service) : Stock produit</span><span class="sxs-lookup"><span data-stu-id="4982b-142">Product inventory (Fin and Ops to Field Service): Product inventory</span></span>

<span data-ttu-id="4982b-143">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span><span class="sxs-lookup"><span data-stu-id="4982b-143">[![Template mapping in Data integration](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span></span>
