---
title: Synchroniser les entrepôts entre Finance and Operations et Field Service
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les entrepôts depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 01/14/2019
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
ms.openlocfilehash: 34cd18a18715d12d4002e6dbeee047467ed2a5ad
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "340313"
---
# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a><span data-ttu-id="eaa37-103">Synchroniser les entrepôts entre Finance and Operations et Field Service</span><span class="sxs-lookup"><span data-stu-id="eaa37-103">Synchronize warehouses from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="eaa37-104">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les entrepôts depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="eaa37-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="eaa37-105">[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="eaa37-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="eaa37-106">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="eaa37-106">Templates and tasks</span></span>
<span data-ttu-id="eaa37-107">Le modèle suivant et les tâches sous-jacentes sont utilisées pour exécuter la synchronisation des entrepôts de Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="eaa37-107">The following template and underlying tasks are used to run synchronization of warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="eaa37-108">**Modèle dans l'intégration de données**</span><span class="sxs-lookup"><span data-stu-id="eaa37-108">**Template in Data integration**</span></span>
- <span data-ttu-id="eaa37-109">Entrepôts (Finance and Operations vers Field Service)</span><span class="sxs-lookup"><span data-stu-id="eaa37-109">Warehouses (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="eaa37-110">**Tâche du projet d'intégration des données**</span><span class="sxs-lookup"><span data-stu-id="eaa37-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="eaa37-111">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="eaa37-111">Warehouse</span></span>

## <a name="entity-set"></a><span data-ttu-id="eaa37-112">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="eaa37-112">Entity set</span></span>
| <span data-ttu-id="eaa37-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="eaa37-113">Field Service</span></span>    | <span data-ttu-id="eaa37-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="eaa37-114">Finance and Operations</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="eaa37-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="eaa37-115">msdyn_warehouses</span></span> | <span data-ttu-id="eaa37-116">Entrepôts</span><span class="sxs-lookup"><span data-stu-id="eaa37-116">Warehouses</span></span>                             |

## <a name="entity-flow"></a><span data-ttu-id="eaa37-117">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="eaa37-117">Entity flow</span></span>
<span data-ttu-id="eaa37-118">Les entrepôts qui sont créés et tenus à jour dans Finance and Operations peuvent être synchronisées sur Field Service via un projet d'intégration de données Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="eaa37-118">Warehouses that are created and maintained in Finance and Operations can be synchronized to Field Service via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="eaa37-119">Les entrepôts souhaités qui se synchronisent sur Field Service peuvent être contrôlés avec la fonctionnalité de requête et de filtrage avancée sur le projet.</span><span class="sxs-lookup"><span data-stu-id="eaa37-119">The warehouses that you want to synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="eaa37-120">Les entrepôts qui se synchronisent sur Finance and Operations sont créés dans Field Service avec le champ **Est géré en externe** défini sur **Oui** et l'enregistrement est rendu en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="eaa37-120">Warehouses that synchronize from Finance and Operations are created in Field Service with the **Is maintained externally** field set to **Yes** and the record is read only.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="eaa37-121">Solution Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="eaa37-121">Field Service CRM solution</span></span>
<span data-ttu-id="eaa37-122">Pour permettre l'intégration entre Field Service et Finance and Operations, des fonctionnalités supplémentaires de la solution Field Service CRM sont requises.</span><span class="sxs-lookup"><span data-stu-id="eaa37-122">To support the integration between Field Service and Finance and Operations, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="eaa37-123">Dans la solution, le champ **Est géré en externe** a été ajouté à l'entité **Entrepôt (msdyn_warehouses)**.</span><span class="sxs-lookup"><span data-stu-id="eaa37-123">In the solution, the **Is Maintained Externally** field has been added to the **Warehouse (msdyn_warehouses)** entity.</span></span> <span data-ttu-id="eaa37-124">Ce champ permet d'identifier si l'entrepôt est géré depuis Finance and Operations ou s'il existe uniquement dans Field Service.</span><span class="sxs-lookup"><span data-stu-id="eaa37-124">This field helps to identify if the warehouse is handled from Finance and Operations or if it only exists in Field Service.</span></span> <span data-ttu-id="eaa37-125">Les paramètres de ce champ sont :</span><span class="sxs-lookup"><span data-stu-id="eaa37-125">The settings for this field include:</span></span>
- <span data-ttu-id="eaa37-126">**Oui** – L'entrepôt provient de Finance and Operations et n'est pas modifiable dans Sales.</span><span class="sxs-lookup"><span data-stu-id="eaa37-126">**Yes** – The warehouse originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="eaa37-127">**Non** - l'entrepôt a été entré directement dans Field Service et y est géré.</span><span class="sxs-lookup"><span data-stu-id="eaa37-127">**No** – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="eaa37-128">Le champ **Est géré en externe** permet de contrôler la synchronisation des niveaux de stock, des ajustements, des transferts et de l'utilisation sur les ordres d'exécution.</span><span class="sxs-lookup"><span data-stu-id="eaa37-128">The **Is Externally Maintained** field helps control the synchronization of inventory levels, adjustments, transfers, and usage on work orders.</span></span> <span data-ttu-id="eaa37-129">Seuls les entrepôts avec **Est géré en externe**définis sur **Oui** peuvent être utilisés pour se synchroniser directement sur l'entrepôt de l'autre système.</span><span class="sxs-lookup"><span data-stu-id="eaa37-129">Only warehouses with **Is Externally Maintained** set to **Yes** can be used to synchronize directly to the same warehouse in the other system.</span></span> 

> [!NOTE]
> <span data-ttu-id="eaa37-130">Vous pouvez créer plusieurs entrepôts dans Field Service (avec **Géré en externe** = Non), puis les mapper à un seul entrepôt dans Finance and Operations, avec la fonctionnalité de requête et de filtrage avancée.</span><span class="sxs-lookup"><span data-stu-id="eaa37-130">It is possible to create multiple warehouses in Field Service (with **Is Externally Maintained** = No) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="eaa37-131">Cela est utile dans les situations où vous souhaitez que Field Service serve de base au niveau de stock détaillé et n'envoyer que des mises à jour à Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="eaa37-131">This is used in situations where you want Field Service to master the detailed inventory level and just send updates to Finance and Operations.</span></span> <span data-ttu-id="eaa37-132">Dans ce cas, Field Service ne reçoit pas les mises à jour de niveau de stock de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="eaa37-132">In this case, Field Service will not receive inventory-level updates from Finance and Operations.</span></span> <span data-ttu-id="eaa37-133">Pour en savoir plus, voir [Synchroniser les ajustements de stock entre Field Service et Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) et [Synchroniser des bons de travail de Field Service sur des commandes client de Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="eaa37-133">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="eaa37-134">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="eaa37-134">Prerequisites and mapping setup</span></span>
### <a name="data-integration-project"></a><span data-ttu-id="eaa37-135">Projet d'intégration des données</span><span class="sxs-lookup"><span data-stu-id="eaa37-135">Data Integration project</span></span>
<span data-ttu-id="eaa37-136">Avant la synchronisation des entrepôts, vérifiez de mettre à jour la fonctionnalité de requête et de filtrage avancée sur le projet pour inclure uniquement les entrepôts à transférer de Finance and Operations vers Field Service.</span><span class="sxs-lookup"><span data-stu-id="eaa37-136">Before synchronizing the warehouses, make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Finance and Operations to Field Service.</span></span> <span data-ttu-id="eaa37-137">Notez que vous avez besoin de l'entrepôt dans Field Service pour l'appliquer aux ordres d'exécution, ajustements et transferts.</span><span class="sxs-lookup"><span data-stu-id="eaa37-137">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments, and transfers.</span></span>  

<span data-ttu-id="eaa37-138">Pour s'assurer que la **Clé d'intégration** existe pour **msdyn_warehouses** :</span><span class="sxs-lookup"><span data-stu-id="eaa37-138">To ensure that the **Integration key** exists for **msdyn_warehouses**:</span></span>
1. <span data-ttu-id="eaa37-139">Accédez au module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="eaa37-139">Go to Data Integration.</span></span>
2. <span data-ttu-id="eaa37-140">Sélectionnez l'onglet **Ensemble de connexions**.</span><span class="sxs-lookup"><span data-stu-id="eaa37-140">Select the **Connection Set** tab.</span></span>
3. <span data-ttu-id="eaa37-141">Sélectionnez l'ensemble de connexions utilisé pour la synchronisation des ordres d'exécution.</span><span class="sxs-lookup"><span data-stu-id="eaa37-141">Select the connection set used for work order synchronization.</span></span>
4. <span data-ttu-id="eaa37-142">Sélectionnez l'onglet **Clé d'intégration**.</span><span class="sxs-lookup"><span data-stu-id="eaa37-142">Select the **Integration key** tab.</span></span>
5. <span data-ttu-id="eaa37-143">Recherchez msdyn_warehouses et confirmez que la clé **msdyn_name (nom)** est ajoutée.</span><span class="sxs-lookup"><span data-stu-id="eaa37-143">Find msdyn_warehouses and confirm that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="eaa37-144">Si elle n'est pas affichée, ajoutez-la en cliquant sur **Ajouter une clé**, puis sur **Enregistrer** en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="eaa37-144">If it is not shown, add it by clicking **Add key** and then click **Save** at the top of the page.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="eaa37-145">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="eaa37-145">Template mapping in Data integration</span></span>

<span data-ttu-id="eaa37-146">Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="eaa37-146">The following illustration shows the template mapping in Data integration.</span></span>

### <a name="warehouses-finance-and-operations-to-field-service-warehouse"></a><span data-ttu-id="eaa37-147">Entrepôts (Finance and Operations vers Field Service): Entrepôt</span><span class="sxs-lookup"><span data-stu-id="eaa37-147">Warehouses (Finance and Operations to Field Service): Warehouse</span></span>

<span data-ttu-id="eaa37-148">[![Mise en correspondance de modèles dans l'intégration de données](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="eaa37-148">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>
