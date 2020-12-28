---
title: Synchroniser les informations sur le niveau de stock depuis Supply Chain Management vers Field Service
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les informations au niveau du stock depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 05/07/2019
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
ms.openlocfilehash: 1228339c12d26f7b91875d15f0daa8da2869cba0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427771"
---
# <a name="synchronize-inventory-level-information-from-supply-chain-management-to-field-service"></a><span data-ttu-id="c4815-103">Synchroniser les informations sur le niveau de stock depuis Supply Chain Management vers Field Service</span><span class="sxs-lookup"><span data-stu-id="c4815-103">Synchronize inventory level information from Supply Chain Management to Field Service</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c4815-104">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les informations au niveau du stock depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="c4815-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory-level information from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="c4815-105">[![Synchronisation des processus d'entreprise entre Supply Chain Management et Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span><span class="sxs-lookup"><span data-stu-id="c4815-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="c4815-106">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="c4815-106">Templates and tasks</span></span>
<span data-ttu-id="c4815-107">Le modèle et les tâches sous-jacentes suivants sont utilisés pour synchroniser les niveaux disponibles en stock et les transferts depuis Supply Chain Management vers Field Service.</span><span class="sxs-lookup"><span data-stu-id="c4815-107">The following template and underlying tasks are used to synchronize inventory on-hand levels from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="c4815-108">**Modèle dans l'intégration de données**</span><span class="sxs-lookup"><span data-stu-id="c4815-108">**Template in Data integration**</span></span>
- <span data-ttu-id="c4815-109">Stock de produit (Supply Chain Management vers Field Service)</span><span class="sxs-lookup"><span data-stu-id="c4815-109">Product Inventory (Supply Chain Management to Field Service)</span></span>
  
<span data-ttu-id="c4815-110">**Tâche du projet d'intégration des données**</span><span class="sxs-lookup"><span data-stu-id="c4815-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="c4815-111">Produit de stock</span><span class="sxs-lookup"><span data-stu-id="c4815-111">Product inventory</span></span>

<span data-ttu-id="c4815-112">Les tâches de synchronisation suivantes sont requises avant que la synchronisation des niveaux de stock puisse avoir lieu :</span><span class="sxs-lookup"><span data-stu-id="c4815-112">The following synchronization tasks are required before synchronization of inventory levels can occur:</span></span>
- <span data-ttu-id="c4815-113">Entrepôts (Supply Chain Management vers Field Service)</span><span class="sxs-lookup"><span data-stu-id="c4815-113">Warehouses (Supply Chain Management to Field Service)</span></span> 
- <span data-ttu-id="c4815-114">Produits Field Service avec unité de stock (Supply Chain Management vers Sales)</span><span class="sxs-lookup"><span data-stu-id="c4815-114">Field Service products with Inventory unit (Supply Chain Management to Sales)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="c4815-115">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="c4815-115">Entity set</span></span>

| <span data-ttu-id="c4815-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="c4815-116">Field Service</span></span>                      | <span data-ttu-id="c4815-117">Gestion de la chaîne d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="c4815-117">Supply Chain Management</span></span>                |
|------------------------------------|----------------------------------------|
| <span data-ttu-id="c4815-118">msdynce_externalproductinventories</span><span class="sxs-lookup"><span data-stu-id="c4815-118">msdynce_externalproductinventories</span></span> | <span data-ttu-id="c4815-119">Stock CDS disponible par entrepôt</span><span class="sxs-lookup"><span data-stu-id="c4815-119">CDS inventory on-hand by warehouse</span></span>     |

## <a name="entity-flow"></a><span data-ttu-id="c4815-120">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="c4815-120">Entity flow</span></span>
<span data-ttu-id="c4815-121">Les informations sur le niveau de stock sont envoyées de Finance and Operations vers Field Service pour certains produits.</span><span class="sxs-lookup"><span data-stu-id="c4815-121">Inventory-level information from Finance and Operation is sent to Field Service for selected products.</span></span> <span data-ttu-id="c4815-122">Les informations de niveau de stock comprennent :</span><span class="sxs-lookup"><span data-stu-id="c4815-122">The inventory-level information includes:</span></span> 
- <span data-ttu-id="c4815-123">La quantité disponible (quantité physique actuelle enregistrée dans l'entrepôt)</span><span class="sxs-lookup"><span data-stu-id="c4815-123">On hand quantity (current recorded physical quantity located in the warehouse)</span></span>
- <span data-ttu-id="c4815-124">Quantité en commande (quantité totale en commande enregistrée - c'est-à-dire commandes client)</span><span class="sxs-lookup"><span data-stu-id="c4815-124">On order quantity (total recorded quantity on order, such as sales orders)</span></span>
- <span data-ttu-id="c4815-125">Quantité commandée (quantité totale commandée enregistrée - c'est-à-dire commandes fournisseur)</span><span class="sxs-lookup"><span data-stu-id="c4815-125">Ordered quantity (total recorded ordered quantity, such as purchase orders)</span></span>

<span data-ttu-id="c4815-126">Ces informations sont capturées par produit lancé pour chaque entrepôt et synchronisées selon le suivi des modifications, lorsque le niveau de stock change.</span><span class="sxs-lookup"><span data-stu-id="c4815-126">This information is captured per released product for each warehouse and synchronized based on change tracking, when the inventory level changes.</span></span>

<span data-ttu-id="c4815-127">Dans Field Service, la solution d'intégration crée des journaux de stock pour le delta, pour obtenir les niveaux dans Field Service pour faire correspondre les niveaux dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c4815-127">In Field Service, the integration solution creates inventory journals for the delta, so that the levels in Field Service match the levels in Supply Chain Management.</span></span>

<span data-ttu-id="c4815-128">Supply Chain Management agira comme base pour les niveaux de stock.</span><span class="sxs-lookup"><span data-stu-id="c4815-128">Supply Chain Management will act as the master for inventory levels.</span></span> <span data-ttu-id="c4815-129">Il est donc important de paramétrer l'intégration pour les ordres d'exécution, les transferts et les ajustements entre Field Service et Supply Chain Management si cette fonctionnalité est utilisée dans Field Service, ainsi qu'avec la synchronisation des niveaux de stock de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c4815-129">Therefore it is important to set up integration for work orders, transfers, and adjustments from Field Service to Supply Chain Management if this functionality is used in Field Service, together with synchronization of inventory levels from Supply Chain Management.</span></span>

<span data-ttu-id="c4815-130">Les produits et les entrepôts dans lesquels les niveaux de stock sont basés sur Supply Chain Management peuvent être contrôlés avec Requête et filtrage avancés (Power Query).</span><span class="sxs-lookup"><span data-stu-id="c4815-130">The products and warehouses where inventory levels are mastered from Supply Chain Management can be controlled with the Advanced Query and Filtering (Power Query).</span></span>

> [!NOTE]
> <span data-ttu-id="c4815-131">Vous pouvez créer plusieurs entrepôts dans Field Service (avec **Géré en externe = Non**), puis les mapper à un seul entrepôt dans Supply Chain Management, avec la fonctionnalité de requête et de filtrage avancée.</span><span class="sxs-lookup"><span data-stu-id="c4815-131">It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained = No**) and then map them to a single warehouse in Supply Chain Management, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="c4815-132">Cela est utile dans les situations où vous souhaitez que Field Service serve de base au niveau de stock détaillé et n'envoyer que des mises à jour à Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c4815-132">This is used in situations where you want Field Service to master the detailed inventory level and only send updates to Supply Chain Management.</span></span> <span data-ttu-id="c4815-133">Dans ce cas, Field Service ne reçoit pas les mises à jour de niveau de stock de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c4815-133">In this case, Field Service will not receive inventory-level updates from Supply Chain Management.</span></span> <span data-ttu-id="c4815-134">Pour en savoir plus, voir [Synchroniser les ajustements de stock entre Field Service et Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) et [Synchroniser des bons de travail de Field Service sur des commandes client de Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="c4815-134">For additional information, see [Synchronize inventory adjustments from Field Service to Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="c4815-135">Solution Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="c4815-135">Field Service CRM solution</span></span>
<span data-ttu-id="c4815-136">L'entité **Stock de produits externe** est une nouvelle entité utilisée uniquement pour la partie principale dans l'intégration.</span><span class="sxs-lookup"><span data-stu-id="c4815-136">The **External product inventory** entity is only used for back end in to the integration.</span></span> <span data-ttu-id="c4815-137">Elle reçoit les valeurs de niveau de stock de Supply Chain Management dans l'intégration puis les transforme en journaux de stock manuel, qui modifie ensuite les produits de stock dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="c4815-137">This entity receives the inventory level values from Supply Chain Management in the integration and then transforms those values to Manual inventory journals, which then changes the Inventory products in the Warehouse.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="c4815-138">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="c4815-138">Prerequisites and mapping setup</span></span>

### <a name="data-integration"></a><span data-ttu-id="c4815-139">Intégration de données</span><span class="sxs-lookup"><span data-stu-id="c4815-139">Data integration</span></span>
<span data-ttu-id="c4815-140">Pour que le projet fonctionne, vous devez vous assurer que la Clé d'intégration est mise à jour pour msdynce_externalproductinventories.</span><span class="sxs-lookup"><span data-stu-id="c4815-140">For the project to work, you need to ensure that the Integration key is updated for msdynce_externalproductinventories.</span></span>
1.  <span data-ttu-id="c4815-141">Accédez à **Intégration de données > Ensembles de connexions**.</span><span class="sxs-lookup"><span data-stu-id="c4815-141">Go to **Data integration > Connection sets**.</span></span>
2.  <span data-ttu-id="c4815-142">Sélectionnez l'Ensemble de connexions utilisé.</span><span class="sxs-lookup"><span data-stu-id="c4815-142">Select the used Connection set.</span></span>
3.  <span data-ttu-id="c4815-143">Dans l'onglet **Clé d'intégration**, assurez-vous que les clés suivantes sont ajoutées à msdynce_externalproductinventories :</span><span class="sxs-lookup"><span data-stu-id="c4815-143">On the **Integration key** tab, ensure that the following keys are added to msdynce_externalproductinventories:</span></span>
      - <span data-ttu-id="c4815-144">msdynce_productnumber (numéro de produit)</span><span class="sxs-lookup"><span data-stu-id="c4815-144">msdynce_productnumber (Product Number)</span></span>
      - <span data-ttu-id="c4815-145">msdynce_warehouseid (ID entrepôt)</span><span class="sxs-lookup"><span data-stu-id="c4815-145">msdynce_warehouseid (Warehouse ID)</span></span>
      
### <a name="data-integration-project"></a><span data-ttu-id="c4815-146">Projet d'intégration des données</span><span class="sxs-lookup"><span data-stu-id="c4815-146">Data integration project</span></span>
<span data-ttu-id="c4815-147">Vous pouvez appliquer des filtres avec Requête et filtrage avancés afin de contrôler que seuls les produits et entrepôts souhaités envoient des informations de niveau de stock de Supply Chain Management vers Field Service.</span><span class="sxs-lookup"><span data-stu-id="c4815-147">You can apply filters with Advanced Query and Filtering so that only certain products and warehouses send inventory-level information from Supply Chain Management to Field Service.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="c4815-148">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="c4815-148">Template mapping in Data integration</span></span>

### <a name="product-inventory-supply-chain-management-to-field-service-product-inventory"></a><span data-ttu-id="c4815-149">Stock de produit (Supply Chain Management vers Field Service) : stock de produit</span><span class="sxs-lookup"><span data-stu-id="c4815-149">Product inventory (Supply Chain Management to Field Service): Product inventory</span></span>

<span data-ttu-id="c4815-150">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span><span class="sxs-lookup"><span data-stu-id="c4815-150">[![Template mapping in Data integration](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span></span>
