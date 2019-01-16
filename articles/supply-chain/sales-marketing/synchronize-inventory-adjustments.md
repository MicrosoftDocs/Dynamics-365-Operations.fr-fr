---
title: Synchroniser les transferts et les ajustements de stock entre Field Service et Finance and Operations
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les ajustements et transferts de stock de Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
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
ms.openlocfilehash: 79a1cfac3fa94223cc9af73e758ce95fd47065c9
ms.contentlocale: fr-fr
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a><span data-ttu-id="815ee-103">Synchroniser les ajustements de stock entre Field Service et Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="815ee-103">Synchronize inventory adjustments from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="815ee-104">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les ajustements et transferts de stock de Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="815ee-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="815ee-105">[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="815ee-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="815ee-106">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="815ee-106">Templates and tasks</span></span>
<span data-ttu-id="815ee-107">Les modèle et les tâches sous-jacentes suivants sont utilisés pour exécuter la synchronisation des ajustements et transferts de stock de Microsoft Dynamics 365 for Field Service vers Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="815ee-107">The following template and underlying tasks are used to run synchronization of inventory adjustments and transfers from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="815ee-108">**Nom des modèles dans l'intégration des données :**</span><span class="sxs-lookup"><span data-stu-id="815ee-108">**Name of the templates in Data integration:**</span></span>
- <span data-ttu-id="815ee-109">Ajustement de stock (Field Service vers Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="815ee-109">Inventory Adjustment (Field Service to Finance and Operations)</span></span>
- <span data-ttu-id="815ee-110">Transferts de stock (Field Service vers Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="815ee-110">Inventory Transfers (Field Service to Finance and Operations)</span></span>

<span data-ttu-id="815ee-111">**Noms des tâches dans les projets d'intégration de données :**</span><span class="sxs-lookup"><span data-stu-id="815ee-111">**Names of the tasks in the Data integration projects:**</span></span>
- <span data-ttu-id="815ee-112">Ajustements de stock</span><span class="sxs-lookup"><span data-stu-id="815ee-112">Inventory Adjustments</span></span>
- <span data-ttu-id="815ee-113">Transferts de stock</span><span class="sxs-lookup"><span data-stu-id="815ee-113">Inventory Transfers</span></span>

## <a name="entity-set"></a><span data-ttu-id="815ee-114">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="815ee-114">Entity set</span></span>
| <span data-ttu-id="815ee-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="815ee-115">Field Service</span></span>                     | <span data-ttu-id="815ee-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="815ee-116">Finance and Operations</span></span>                             |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="815ee-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="815ee-117">msdyn_inventoryadjustmentproducts</span></span> |   <span data-ttu-id="815ee-118">En-têtes et lignes du journal d'ajustement de stock CDS</span><span class="sxs-lookup"><span data-stu-id="815ee-118">CDS Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="815ee-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="815ee-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="815ee-120">En-têtes et lignes du journal de transfert de stock CDS</span><span class="sxs-lookup"><span data-stu-id="815ee-120">CDS inventory transfer journal headers and lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="815ee-121">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="815ee-121">Entity flow</span></span>
<span data-ttu-id="815ee-122">Les ajustements et les transferts de stock effectués dans Field Service se synchronisent sur Finance and Operations, une fois que le **Statut de validation** passe de Créé à Validé.</span><span class="sxs-lookup"><span data-stu-id="815ee-122">Inventory adjustments and transfers made in Field Service will synchronize to Finance and Operations, once the **Post status** is changed from Created to Posted.</span></span> <span data-ttu-id="815ee-123">Dans ce cas, l'ordre d'ajustement ou de transfert est verrouillé et passe en lecture seule, car les ajustements et les transferts peuvent être validés dans Finance and Operations, et par conséquent ne peuvent pas être modifiés.</span><span class="sxs-lookup"><span data-stu-id="815ee-123">When this happen the adjustment or transfer order will be locked and become read-only, as adjustments and transfers might be posted in Finance and Operations and therefor can't be modified.</span></span>
<span data-ttu-id="815ee-124">Dans Finance and Operations, vous pouvez paramétrer un traitement par lots pour valider automatiquement les journaux d'ajustements et de transferts de stock générés par l'intégration.</span><span class="sxs-lookup"><span data-stu-id="815ee-124">In Finance and Operations you can setup a batch job to automatically post the adjustments and transfer inventory journals generated with the integration.</span></span> <span data-ttu-id="815ee-125">Voir les prérequis ci-dessous pour plus d'informations sur la procédure d'activation du traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="815ee-125">See prerequisite below for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="815ee-126">Solution Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="815ee-126">Field Service CRM solution</span></span> 
<span data-ttu-id="815ee-127">Le champ Unité de stock a été ajouté à l'entité Produit.</span><span class="sxs-lookup"><span data-stu-id="815ee-127">The Inventory Unit field has been added to the Product entity.</span></span> <span data-ttu-id="815ee-128">Ce champ est nécessaire, car unité de vente et l'unité de stock ne sont pas toujours les mêmes dans Operations, et pour le stock de l'entrepôt dans les opérations nous avons besoin de l'unité de stock.</span><span class="sxs-lookup"><span data-stu-id="815ee-128">This field is needed since the Sales and Inventory Unit is not always the same in Operations, and for the Warehouse Inventory in operations we need the Inventory Unit.</span></span>
<span data-ttu-id="815ee-129">Lorsque vous définissez le produit sur un produit d'ajustement de stock pour les ajustements de stock et les transferts de stock, l'unité est extraite de la valeur du produit de stock de produits.</span><span class="sxs-lookup"><span data-stu-id="815ee-129">When you set the Product on an Inventory Adjustment Product for both Inventory Adjustments and Inventory Transfers the Unit will be fetched from the Products Inventory Product value.</span></span> <span data-ttu-id="815ee-130">Si une valeur est trouvée, le champ Unité est verrouillé sur le produit d'ajustement de stock</span><span class="sxs-lookup"><span data-stu-id="815ee-130">If a value is found the Unit field will be locked on the Inventory Adjustment Product</span></span>

<span data-ttu-id="815ee-131">Le champ Statut de validation a été ajouté à l'entité Ajustement de stock et à l'entité Transfert de stock.</span><span class="sxs-lookup"><span data-stu-id="815ee-131">The Post Status field has been added to both the Inventory Adjustment entity and the Inventory Transfer entity.</span></span> <span data-ttu-id="815ee-132">Ce champ est utilisé comme filtre lorsqu'un ajustement ou un transfert est envoyé à Operations.</span><span class="sxs-lookup"><span data-stu-id="815ee-132">This field is used as a filter for when a adjustment or transfer is sent to Operations.</span></span> <span data-ttu-id="815ee-133">La valeur par défaut du champ est Créé (1) et n'est ensuite pas envoyé à Operations.</span><span class="sxs-lookup"><span data-stu-id="815ee-133">The field is defaulted to Created (1) and its then not sent over to Operations.</span></span> <span data-ttu-id="815ee-134">Une fois que vous le modifiez avec Validé (2), il est envoyé à Operations, mais vous ne pourrez ensuite plus rien modifier dans Ajustement ou Transfert, ni ajouter aucune ligne à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="815ee-134">Ones you change is to Posted (2) It is sent over to operations, but you will then no longer be able to change anything in the Adjustment or Transfer or add any new lines to it.</span></span>
<span data-ttu-id="815ee-135">Le champ Souche de numéros a été ajouté à l'entité Produit d'ajustement de stock.</span><span class="sxs-lookup"><span data-stu-id="815ee-135">The Number Sequence field has been added to the Inventory Adjustment Product entity.</span></span> <span data-ttu-id="815ee-136">Ce champ permet à l'intégration de disposer d'un numéro unique, afin qu'elle sache quand effectuer des créations et quand effectuer des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="815ee-136">This field helps the integration to have a Unique number, so the integration knows when to do creates and when to do updates.</span></span> <span data-ttu-id="815ee-137">Lorsque vous créez votre premier produit d'ajustement de stock, cela entraîne la création d'un enregistrement dans l'entité P2C AutoNumber afin de tenir à jour la souche de numéros et le préfixe utilisé.</span><span class="sxs-lookup"><span data-stu-id="815ee-137">When you create your first Inventory Adjustment Product it will create a new record in the P2C AutoNumber entity to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="815ee-138">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="815ee-138">Prerequisites and mapping setup</span></span>

### <a name="in-finance-and-operations"></a><span data-ttu-id="815ee-139">Dans Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="815ee-139">In Finance and Operations</span></span>
<span data-ttu-id="815ee-140">Les journaux de stock d'intégration générés par l'intégration peuvent être automatiquement validés avec un traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="815ee-140">The integration inventory journals generated by the integration can automatically be posted with a batch job.</span></span> <span data-ttu-id="815ee-141">Pour cela, accédez à : Gestion des stocks > Tâches périodiques > Intégration CDS > Valider les journaux de stock pour l'intégration</span><span class="sxs-lookup"><span data-stu-id="815ee-141">This is enabled from: Inventory management > Periodic tasks > CDS integration > Post integration inventory journals</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="815ee-142">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="815ee-142">Template mapping in Data integration</span></span>

<span data-ttu-id="815ee-143">Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="815ee-143">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-finance-and-operations-inventory-adjustment"></a><span data-ttu-id="815ee-144">Ajustement de stock (Field Service vers Finance and Operations) : Ajustement de stock</span><span class="sxs-lookup"><span data-stu-id="815ee-144">Inventory Adjustment (Field Service to Finance and Operations): Inventory Adjustment</span></span>

<span data-ttu-id="815ee-145">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="815ee-145">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-finance-and-operations-inventory-transfer"></a><span data-ttu-id="815ee-146">Transfert de stock (Field Service vers Finance and Operations) : Transfert de stock</span><span class="sxs-lookup"><span data-stu-id="815ee-146">Inventory Transfer (Field Service to Finance and Operations): Inventory Transfer</span></span>

<span data-ttu-id="815ee-147">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="815ee-147">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>

