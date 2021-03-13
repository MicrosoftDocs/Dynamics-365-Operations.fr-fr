---
title: Synchroniser les entrepôts depuis Supply Chain Management vers Field Service
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les entrepôts depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 0c0c1bafb5b36bb9ddc00061e0040a199c8c033d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010845"
---
# <a name="synchronize-warehouses-from-supply-chain-management-to-field-service"></a><span data-ttu-id="826e6-103">Synchroniser les entrepôts depuis Supply Chain Management vers Field Service</span><span class="sxs-lookup"><span data-stu-id="826e6-103">Synchronize warehouses from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="826e6-104">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les entrepôts depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="826e6-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="826e6-105">[![Synchronisation des processus d'entreprise entre Supply Chain Management et Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="826e6-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="826e6-106">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="826e6-106">Templates and tasks</span></span>
<span data-ttu-id="826e6-107">Le modèle et les tâches sous-jacentes suivants sont utilisés pour synchroniser les entrepôts depuis Supply Chain Management vers Field Service.</span><span class="sxs-lookup"><span data-stu-id="826e6-107">The following template and underlying tasks are used to run synchronization of warehouses from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="826e6-108">**Modèle dans l'intégration de données**</span><span class="sxs-lookup"><span data-stu-id="826e6-108">**Template in Data integration**</span></span>
- <span data-ttu-id="826e6-109">Entrepôts (Supply Chain Management vers Field Service)</span><span class="sxs-lookup"><span data-stu-id="826e6-109">Warehouses (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="826e6-110">**Tâche du projet d'intégration des données**</span><span class="sxs-lookup"><span data-stu-id="826e6-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="826e6-111">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="826e6-111">Warehouse</span></span>

## <a name="table-set"></a><span data-ttu-id="826e6-112">Ensemble de tables</span><span class="sxs-lookup"><span data-stu-id="826e6-112">Table set</span></span>
| <span data-ttu-id="826e6-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="826e6-113">Field Service</span></span>    | <span data-ttu-id="826e6-114">Gestion de la chaîne d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="826e6-114">Supply Chain Management</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="826e6-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="826e6-115">msdyn_warehouses</span></span> | <span data-ttu-id="826e6-116">Entrepôts</span><span class="sxs-lookup"><span data-stu-id="826e6-116">Warehouses</span></span>                             |

## <a name="table-flow"></a><span data-ttu-id="826e6-117">Flux de table</span><span class="sxs-lookup"><span data-stu-id="826e6-117">Table flow</span></span>
<span data-ttu-id="826e6-118">Les entrepôts créés et tenus à jour dans Supply Chain Management peuvent être synchronisés avec Field Service via un projet d'intégration de données de Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="826e6-118">Warehouses that are created and maintained in Supply Chain Management can be synchronized to Field Service via a Microsoft Dataverse Data integration project.</span></span> <span data-ttu-id="826e6-119">Les entrepôts souhaités qui se synchronisent sur Field Service peuvent être contrôlés avec la fonctionnalité de requête et de filtrage avancée sur le projet.</span><span class="sxs-lookup"><span data-stu-id="826e6-119">The warehouses that you want to synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="826e6-120">Les entrepôts synchronisés depuis Supply Chain Management sont créés dans Field Service avec la colonne **Est géré en externe** définie sur **Oui** et l'enregistrement est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="826e6-120">Warehouses that synchronize from Supply Chain Management are created in Field Service with the **Is maintained externally** column set to **Yes** and the record is read only.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="826e6-121">Solution Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="826e6-121">Field Service CRM solution</span></span>
<span data-ttu-id="826e6-122">Pour permettre l'intégration entre Field Service et Supply Chain Management, des fonctionnalités supplémentaires de la solution Field Service CRM sont requises.</span><span class="sxs-lookup"><span data-stu-id="826e6-122">To support the integration between Field Service and Supply Chain Management, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="826e6-123">Dans la solution, la colonne **Est géré en externe** a été ajoutée à la table **Entrepôt (msdyn_warehouses)**.</span><span class="sxs-lookup"><span data-stu-id="826e6-123">In the solution, the **Is Maintained Externally** column has been added to the **Warehouse (msdyn_warehouses)** table.</span></span> <span data-ttu-id="826e6-124">Cette colonne aide à identifier si l'entrepôt est géré depuis Supply Chain Management ou s'il existe uniquement dans Field Service.</span><span class="sxs-lookup"><span data-stu-id="826e6-124">This column helps to identify if the warehouse is handled from Supply Chain Management or if it only exists in Field Service.</span></span> <span data-ttu-id="826e6-125">Les paramètres de cette colonne sont :</span><span class="sxs-lookup"><span data-stu-id="826e6-125">The settings for this column include:</span></span>
- <span data-ttu-id="826e6-126">**Oui** – L'entrepôt provient de Supply Chain Management et n'est pas modifiable dans Sales.</span><span class="sxs-lookup"><span data-stu-id="826e6-126">**Yes** – The warehouse originated from Supply Chain Management and won't be editable in Sales.</span></span>
- <span data-ttu-id="826e6-127">**Non** - l'entrepôt a été entré directement dans Field Service et y est géré.</span><span class="sxs-lookup"><span data-stu-id="826e6-127">**No** – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="826e6-128">La colonne **Est géré en externe** aide à contrôler la synchronisation des niveaux de stock, les ajustements, les transferts et l'utilisation sur les ordres d'exécution.</span><span class="sxs-lookup"><span data-stu-id="826e6-128">The **Is Externally Maintained** column helps control the synchronization of inventory levels, adjustments, transfers, and usage on work orders.</span></span> <span data-ttu-id="826e6-129">Seuls les entrepôts avec **Est géré en externe** définis sur **Oui** peuvent être utilisés pour se synchroniser directement sur l'entrepôt de l'autre système.</span><span class="sxs-lookup"><span data-stu-id="826e6-129">Only warehouses with **Is Externally Maintained** set to **Yes** can be used to synchronize directly to the same warehouse in the other system.</span></span> 

> [!NOTE]
> <span data-ttu-id="826e6-130">Vous pouvez créer plusieurs entrepôts dans Field Service (avec **Géré en externe** = Non), puis les mapper à un seul entrepôt, avec la fonctionnalité de requête et de filtrage avancée.</span><span class="sxs-lookup"><span data-stu-id="826e6-130">It is possible to create multiple warehouses in Field Service (with **Is Externally Maintained** = No) and then map them to a single warehouse, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="826e6-131">Cela est utile dans les situations où vous souhaitez que Field Service serve de base au niveau de stock détaillé et d'envoyer uniquement des mises à jour à Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="826e6-131">This is used in situations where you want Field Service to master the detailed inventory level and just send updates to Supply Chain Management.</span></span> <span data-ttu-id="826e6-132">Dans ce cas, Field Service ne reçoit pas les mises à jour de niveau de stock de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="826e6-132">In this case, Field Service will not receive inventory-level updates from Supply Chain Management.</span></span> <span data-ttu-id="826e6-133">Pour en savoir plus, voir [Synchroniser les ajustements de stock entre Field Service et Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) et [Synchroniser des ordres de travail de Field Service sur des commandes client de  Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="826e6-133">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="826e6-134">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="826e6-134">Prerequisites and mapping setup</span></span>
### <a name="data-integration-project"></a><span data-ttu-id="826e6-135">Projet d'intégration des données</span><span class="sxs-lookup"><span data-stu-id="826e6-135">Data Integration project</span></span>
<span data-ttu-id="826e6-136">Avant la synchronisation des entrepôts, vérifiez de mettre à jour la fonctionnalité de requête et de filtrage avancée sur le projet pour inclure uniquement les entrepôts à transférer de Supply Chain Management vers Field Service.</span><span class="sxs-lookup"><span data-stu-id="826e6-136">Before synchronizing the warehouses, make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Supply Chain Management to Field Service.</span></span> <span data-ttu-id="826e6-137">Notez que vous avez besoin de l'entrepôt dans Field Service pour l'appliquer aux ordres d'exécution, ajustements et transferts.</span><span class="sxs-lookup"><span data-stu-id="826e6-137">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments, and transfers.</span></span>  

<span data-ttu-id="826e6-138">Pour s'assurer que la **Clé d'intégration** existe pour **msdyn_warehouses** :</span><span class="sxs-lookup"><span data-stu-id="826e6-138">To ensure that the **Integration key** exists for **msdyn_warehouses**:</span></span>
1. <span data-ttu-id="826e6-139">Accédez au module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="826e6-139">Go to Data Integration.</span></span>
2. <span data-ttu-id="826e6-140">Sélectionnez l'onglet **Ensemble de connexions**.</span><span class="sxs-lookup"><span data-stu-id="826e6-140">Select the **Connection Set** tab.</span></span>
3. <span data-ttu-id="826e6-141">Sélectionnez l'ensemble de connexions utilisé pour la synchronisation des ordres d'exécution.</span><span class="sxs-lookup"><span data-stu-id="826e6-141">Select the connection set used for work order synchronization.</span></span>
4. <span data-ttu-id="826e6-142">Sélectionnez l'onglet **Clé d'intégration**.</span><span class="sxs-lookup"><span data-stu-id="826e6-142">Select the **Integration key** tab.</span></span>
5. <span data-ttu-id="826e6-143">Recherchez msdyn_warehouses et confirmez que la clé **msdyn_name (nom)** est ajoutée.</span><span class="sxs-lookup"><span data-stu-id="826e6-143">Find msdyn_warehouses and confirm that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="826e6-144">Si elle n'est pas affichée, ajoutez-la en cliquant sur **Ajouter une clé**, puis sur **Enregistrer** en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="826e6-144">If it is not shown, add it by clicking **Add key** and then click **Save** at the top of the page.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="826e6-145">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="826e6-145">Template mapping in Data integration</span></span>

<span data-ttu-id="826e6-146">Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="826e6-146">The following illustration shows the template mapping in Data integration.</span></span>

### <a name="warehouses-supply-chain-management-to-field-service-warehouse"></a><span data-ttu-id="826e6-147">Entrepôts (Supply Chain Management vers Field Service) : Entrepôt</span><span class="sxs-lookup"><span data-stu-id="826e6-147">Warehouses (Supply Chain Management to Field Service): Warehouse</span></span>

<span data-ttu-id="826e6-148">[![Mise en correspondance de modèles dans l'intégration de données](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="826e6-148">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>
