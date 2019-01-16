---
title: "Synchroniser les entrepôts entre Finance and Operations et Field Service"
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les entrepôts entre Microsoft Dynamics 365 for Finance and Operations et Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 10/10/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: eb8ba6051777e27bd44504a8160118e8096b1435
ms.contentlocale: fr-fr
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a><span data-ttu-id="dca05-103">Synchroniser les entrepôts entre Finance and Operations et Field Service</span><span class="sxs-lookup"><span data-stu-id="dca05-103">Synchronize warehouses from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="dca05-104">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les entrepôts entre Microsoft Dynamics 365 for Finance and Operations et Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="dca05-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="dca05-105">[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="dca05-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="dca05-106">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="dca05-106">Templates and tasks</span></span>
<span data-ttu-id="dca05-107">Les modèle et les tâches sous-jacentes suivants sont utilisés pour exécuter la synchronisation des entrepôts de Microsoft Dynamics 365 for Finance and Operations vers Microsoft Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="dca05-107">The following template and underlying tasks are used to run synchronization of warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="dca05-108">**Nom du modèle dans l'intégration des données :**</span><span class="sxs-lookup"><span data-stu-id="dca05-108">**Name of the template in Data integration:**</span></span>
- <span data-ttu-id="dca05-109">Entrepôts (Finance and Operations vers Field Service)</span><span class="sxs-lookup"><span data-stu-id="dca05-109">Warehouses (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="dca05-110">**Noms des tâches dans le projet d'intégration de données :**</span><span class="sxs-lookup"><span data-stu-id="dca05-110">**Names of the tasks in the Data integration project:**</span></span>
- <span data-ttu-id="dca05-111">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="dca05-111">Warehouse</span></span>

## <a name="entity-set"></a><span data-ttu-id="dca05-112">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="dca05-112">Entity set</span></span>
| <span data-ttu-id="dca05-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="dca05-113">Field Service</span></span>    | <span data-ttu-id="dca05-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="dca05-114">Finance and Operations</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="dca05-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="dca05-115">msdyn_warehouses</span></span> | <span data-ttu-id="dca05-116">Entrepôts</span><span class="sxs-lookup"><span data-stu-id="dca05-116">Warehouses</span></span>                             |

## <a name="entity-flow"></a><span data-ttu-id="dca05-117">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="dca05-117">Entity flow</span></span>
<span data-ttu-id="dca05-118">Les entrepôts qui sont créés et tenus à jour dans Finance and Operations peuvent être synchronisées sur Field Service via un projet d'intégration de données Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="dca05-118">Warehouses that are created and maintained in Finance and Operations can be synchronized to Field Service via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="dca05-119">Les entrepôts souhaités qui se synchronisent sur Field Service peuvent être contrôlés avec la fonctionnalité de requête et de filtrage avancée sur le projet.</span><span class="sxs-lookup"><span data-stu-id="dca05-119">The desired warehouses that synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="dca05-120">Les entrepôts qui se synchronisent sur Finance and Operations sont créés dans Field Service avec le champ Est géré en externe défini sur Oui et l'enregistrement est rendu en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="dca05-120">Warehouses that synchronize from Finance and Operations are created in Field Service with the field Is maintained externally set to Yes and the record is made read only.</span></span>
<span data-ttu-id="dca05-121">Solution Field Service CRM Pour permettre l'intégration entre Field Service et Finance and Operations, des fonctionnalités supplémentaires de la solution Field Service CRM sont requises.</span><span class="sxs-lookup"><span data-stu-id="dca05-121">Field Service CRM solution To support the integration between Field Service and Finance and Operations, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="dca05-122">La solution inclut les modifications suivantes.</span><span class="sxs-lookup"><span data-stu-id="dca05-122">The solution includes the following changes.</span></span>
<span data-ttu-id="dca05-123">Le champ **Est géré en externe** a été ajouté à l'entité **Entrepôt (msdyn_warehouses)**.</span><span class="sxs-lookup"><span data-stu-id="dca05-123">The field **Is Maintained Externally** has been added to the **Warehouse (msdyn_warehouses)** entity.</span></span> <span data-ttu-id="dca05-124">Ce champ permet d'identifier si l'entrepôt est géré depuis Operations ou s'il existe uniquement dans Field Service.</span><span class="sxs-lookup"><span data-stu-id="dca05-124">This field helps to identify If the Warehouse is handled from Operations or if It only exists in Field Service.</span></span>
- <span data-ttu-id="dca05-125">Oui – L'entrepôt provient de Finance and Operations et n'est pas modifiable dans Sales.</span><span class="sxs-lookup"><span data-stu-id="dca05-125">Yes – The warehouse originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="dca05-126">Non - l'entrepôt a été entré directement dans Field Service et y est géré.</span><span class="sxs-lookup"><span data-stu-id="dca05-126">No – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="dca05-127">Le champ **Est géré en externe** permet de contrôler la synchronisation des niveaux de stock, des ajustements, des transferts et de l'utilisation sur les ordres d'exécution.</span><span class="sxs-lookup"><span data-stu-id="dca05-127">The **Is Externally Maintained** field helps control the synchronization of inventory levels, adjustments, transfers and usage on work orders.</span></span> <span data-ttu-id="dca05-128">Seuls les entrepôts avec **Est géré en externe** = Oui peuvent être utilisés pour se synchroniser directement sur l'entrepôt de l'autre système.</span><span class="sxs-lookup"><span data-stu-id="dca05-128">Only warehouses with **Is Externally Maintained** = Yes can be used to synchronize directly to the same warehouse in the other system.</span></span> 

<span data-ttu-id="dca05-129">Remarque : vous pouvez créer plusieurs entrepôts dans Field Service (avec **Géré en externe** = Non), puis les mapper à un seul entrepôt dans Finance and Operations, avec la fonctionnalité de requête et de filtrage avancée.</span><span class="sxs-lookup"><span data-stu-id="dca05-129">Note: It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained** = No) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="dca05-130">Cela est utile dans les situations où vous souhaitez que Field Service serve de base au niveau de stock détaillé et n'envoyer que des mises à jour à Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dca05-130">This is used in situations where you want Field service to master the detailed inventory level and just send updates to Finance and Operations.</span></span> <span data-ttu-id="dca05-131">Dans ce cas, Field Service ne reçoit pas les mises à jour de niveau de stock de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dca05-131">In this case Field service will not receive inventory level updates from Finance and Operations.</span></span> <span data-ttu-id="dca05-132">Voir les informations supplémentaires dans Synchroniser les ajustements de stock entre Field Service et Finance and Operations et Synchroniser des bons de travail de Field Service sur des commandes client de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dca05-132">See additional information in Synchronize inventory adjustments from Field Service to Finance and Operations and Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="dca05-133">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="dca05-133">Prerequisites and mapping setup</span></span>
### <a name="in-the-data-integration-project"></a><span data-ttu-id="dca05-134">Dans le projet d'intégration des données</span><span class="sxs-lookup"><span data-stu-id="dca05-134">In the Data Integration project</span></span>
<span data-ttu-id="dca05-135">Avant la synchronisation des entrepôts, vérifiez de mettre à jour la fonctionnalité de requête et de filtrage avancée sur le projet pour inclure uniquement les entrepôts à transférer de Finance and Operations vers Field Service.</span><span class="sxs-lookup"><span data-stu-id="dca05-135">Before synchronization of the warehouses make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Finance and Operations to Field Service.</span></span> <span data-ttu-id="dca05-136">Notez que vous avez besoin de l'entrepôt dans Field Service pour l'appliquer aux ordres d'exécution, ajustements et transferts.</span><span class="sxs-lookup"><span data-stu-id="dca05-136">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments and transfers.</span></span>  

<span data-ttu-id="dca05-137">Vérifiez que la **Clé d'intégration** existe pour **msdyn_warehouses**</span><span class="sxs-lookup"><span data-stu-id="dca05-137">Ensure the **Integration key** exist for **msdyn_warehouses**</span></span>
1. <span data-ttu-id="dca05-138">Accédez au module Intégration des données</span><span class="sxs-lookup"><span data-stu-id="dca05-138">Go to Data Integration</span></span>
2. <span data-ttu-id="dca05-139">Sélectionnez l'onglet **Ensemble de connexions**</span><span class="sxs-lookup"><span data-stu-id="dca05-139">Select **Connection Set** tab</span></span>
3. <span data-ttu-id="dca05-140">Sélectionnez l'ensemble de connexions utilisé pour la synchronisation des ordres d'exécution</span><span class="sxs-lookup"><span data-stu-id="dca05-140">Select the Connection set used for Work order synchronization</span></span>
4. <span data-ttu-id="dca05-141">Sélectionnez l'onglet **Clé d'intégration**</span><span class="sxs-lookup"><span data-stu-id="dca05-141">Select **Integration key** tab</span></span>
5. <span data-ttu-id="dca05-142">Recherchez msdyn_warehouses et vérifiez que la clé **msdyn_name (nom)** est ajoutée.</span><span class="sxs-lookup"><span data-stu-id="dca05-142">Find msdyn_warehouses and check that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="dca05-143">Si elle n'est pas affichée, ajoutez-la en cliquant sur **Ajouter une clé**, puis sur **Enregistrer** en haut de la page</span><span class="sxs-lookup"><span data-stu-id="dca05-143">If it is not shown, add it by click **Add key** and click **Save** in the top of the page</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="dca05-144">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="dca05-144">Template mapping in Data integration</span></span>

<span data-ttu-id="dca05-145">Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="dca05-145">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="warehouses-finance-and-operations-to-field-service-warehouse"></a><span data-ttu-id="dca05-146">Entrepôts (Finance and Operations vers Field Service): Entrepôt</span><span class="sxs-lookup"><span data-stu-id="dca05-146">Warehouses (Finance and Operations to Field Service): Warehouse</span></span>

<span data-ttu-id="dca05-147">[![Mise en correspondance de modèles dans l'intégration de données](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="dca05-147">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>

