---
title: Synchroniser les transferts et les ajustements de stock depuis Field Service vers Supply Chain Management
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les ajustements de stock et les transferts depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 04/30/2019
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
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: d76adf10b9df48f5a7a5196e0469bb7cb1dbb34f
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2552231"
---
# <a name="synchronize-inventory-transfers-and-adjustments-from-field-service-to-supply-chain-management"></a><span data-ttu-id="878c3-103">Synchroniser les transferts et les ajustements de stock depuis Field Service vers Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="878c3-103">Synchronize inventory transfers and adjustments from Field Service to Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="878c3-104">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les ajustements de stock et les transferts depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="878c3-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="878c3-105">[![Synchronisation des processus d'entreprise entre Supply Chain Management et Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="878c3-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="878c3-106">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="878c3-106">Templates and tasks</span></span>
<span data-ttu-id="878c3-107">Le modèle et les tâches sous-jacentes suivants sont utilisés pour synchroniser les ajustements de stock et les transferts depuis Field Service vers Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="878c3-107">The following template and underlying tasks are used to synchronize inventory adjustments and transfers from Field Service to Supply Chain Management.</span></span>

<span data-ttu-id="878c3-108">**Modèles dans l'intégration de données**</span><span class="sxs-lookup"><span data-stu-id="878c3-108">**Templates in Data integration**</span></span>
- <span data-ttu-id="878c3-109">Ajustement de stock (Field Service vers Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="878c3-109">Inventory Adjustment (Field Service to Supply Chain Management)</span></span>
- <span data-ttu-id="878c3-110">Transferts de stock (Field Service vers Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="878c3-110">Inventory Transfers (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="878c3-111">**Tâches des projets d'intégration des données**</span><span class="sxs-lookup"><span data-stu-id="878c3-111">**Tasks in the Data integration projects**</span></span>
- <span data-ttu-id="878c3-112">Ajustements de stock</span><span class="sxs-lookup"><span data-stu-id="878c3-112">Inventory Adjustments</span></span>
- <span data-ttu-id="878c3-113">Transferts de stock</span><span class="sxs-lookup"><span data-stu-id="878c3-113">Inventory Transfers</span></span>

## <a name="entity-set"></a><span data-ttu-id="878c3-114">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="878c3-114">Entity set</span></span>
| <span data-ttu-id="878c3-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="878c3-115">Field Service</span></span>                     | <span data-ttu-id="878c3-116">Gestion de la chaîne d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="878c3-116">Supply Chain Management</span></span>                          |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="878c3-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="878c3-117">msdyn_inventoryadjustmentproducts</span></span> |   <span data-ttu-id="878c3-118">En-têtes et lignes du journal d'ajustement de stock CDS</span><span class="sxs-lookup"><span data-stu-id="878c3-118">CDS Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="878c3-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="878c3-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="878c3-120">En-têtes et lignes du journal de transfert de stock CDS</span><span class="sxs-lookup"><span data-stu-id="878c3-120">CDS inventory transfer journal headers and lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="878c3-121">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="878c3-121">Entity flow</span></span>
<span data-ttu-id="878c3-122">Les ajustements et les transferts de stock effectués dans Field Service se synchronisent sur Supply Chain Management, une fois que le **Statut de validation** passe de **Créé** à **Validé**.</span><span class="sxs-lookup"><span data-stu-id="878c3-122">Inventory adjustments and transfers made in Field Service will synchronize to Supply Chain Management after the **Post status** changes from **Created** to **Posted**.</span></span> <span data-ttu-id="878c3-123">Dans ce cas, l'ajustement ou l'ordre de transfert est verrouillé et passe en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="878c3-123">When this occurs, the adjustment or the transfer order will be locked and become read only.</span></span> <span data-ttu-id="878c3-124">Cela signifie que les ajustements et les transferts peuvent être validés dans Supply Chain Management, mais ne peuvent pas être modifiés.</span><span class="sxs-lookup"><span data-stu-id="878c3-124">This means that adjustments and transfers can be posted in Supply Chain Management, but cannot be modified.</span></span> <span data-ttu-id="878c3-125">Dans Supply Chain Management, vous pouvez paramétrer un traitement par lots pour valider automatiquement les journaux d'ajustements et de transferts de stock générés par l'intégration.</span><span class="sxs-lookup"><span data-stu-id="878c3-125">In Supply Chain Management, you can set up a batch job to automatically post the adjustments and transfer inventory journals that have been generated during the integration.</span></span> <span data-ttu-id="878c3-126">Voir les prérequis ci-dessous pour plus d'informations sur la procédure d'activation du traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="878c3-126">See the following prerequisites for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="878c3-127">Solution Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="878c3-127">Field Service CRM solution</span></span> 
<span data-ttu-id="878c3-128">Le champ **Unité de stock** a été ajouté à l'entité **Produit**.</span><span class="sxs-lookup"><span data-stu-id="878c3-128">The **Inventory unit** field has been added to the **Product** entity.</span></span> <span data-ttu-id="878c3-129">Ce champ est nécessaire, car unité de vente et l'unité de stock ne sont pas toujours les mêmes dans Supply Chain Management, et l'unité de stock est requise pour le stock de l'entrepôt dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="878c3-129">This field is needed because the Sales and Inventory unit is not always the same in Supply Chain Management, and the Inventory Unit is needed for the Warehouse Inventory in Supply Chain Management.</span></span>
<span data-ttu-id="878c3-130">Lorsque vous définissez le produit sur un produit d'ajustement de stock pour les ajustements de stock et les transferts de stock, l'unité est extraite de la valeur du produit de stock.</span><span class="sxs-lookup"><span data-stu-id="878c3-130">When you set the product on an Inventory adjustment product for both Inventory adjustments and Inventory transfers, the unit will be fetched from the inventory product value.</span></span> <span data-ttu-id="878c3-131">Si une valeur est trouvée, le champ **Unité** est verrouillé sur le produit d'ajustement de stock</span><span class="sxs-lookup"><span data-stu-id="878c3-131">If a value is found, the **Unit** field will be locked on the Inventory adjustment product.</span></span>

<span data-ttu-id="878c3-132">Le champ **Statut de validation** a été ajouté à l'entité **Ajustement de stock** et à l'entité **Transfert de stock**.</span><span class="sxs-lookup"><span data-stu-id="878c3-132">The **Post status** field has been added to both the **Inventory adjustment** entity and the **Inventory transfer** entity.</span></span> <span data-ttu-id="878c3-133">Ce champ est utilisé comme filtre lorsqu'un ajustement ou un transfert est envoyé à Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="878c3-133">This field is used as a filter when an adjustment or transfer is sent to Supply Chain Management.</span></span> <span data-ttu-id="878c3-134">La valeur par défaut pour ce champ est créée (1), mais elle n'est pas envoyée à Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="878c3-134">The default for this field is Created (1), however it is not sent to Supply Chain Management.</span></span> <span data-ttu-id="878c3-135">Lorsque vous mettez à jour la valeur sur Validé (2), il est envoyé à Supply Chain Management, mais vous ne pourrez ensuite plus rien modifier dans Ajustement ou Transfert, ni ajouter aucune ligne à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="878c3-135">When you update the value to Posted (2), it is sent to Supply Chain Management, but after that you will no longer be able to change the adjustment or transfer or add new lines.</span></span>

<span data-ttu-id="878c3-136">Le champ **Souche de numéros** a été ajouté à l'entité **Produit d'ajustement de stock**.</span><span class="sxs-lookup"><span data-stu-id="878c3-136">The **Number sequence** field has been added to the **Inventory adjustment product** entity.</span></span> <span data-ttu-id="878c3-137">Ce champ garantit que l'intégration a un numéro unique, et que l'intégration peut créer et mettre à jour l'ajustement.</span><span class="sxs-lookup"><span data-stu-id="878c3-137">This field ensures that the integration has a unique number, so the integration can create and update the adjustment.</span></span> <span data-ttu-id="878c3-138">Lorsque vous créez votre premier produit d'ajustement de stock, cela entraîne la création d'un enregistrement dans l'entité **P2C AutoNumber** afin de tenir à jour la souche de numéros et le préfixe utilisé.</span><span class="sxs-lookup"><span data-stu-id="878c3-138">When you create your first inventory adjustment product, it will create a new record in the **P2C AutoNumber** entity to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="878c3-139">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="878c3-139">Prerequisites and mapping setup</span></span>

### <a name="supply-chain-management"></a><span data-ttu-id="878c3-140">Gestion de la chaîne d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="878c3-140">Supply Chain Management</span></span>
<span data-ttu-id="878c3-141">Les journaux de stock d'intégration générés par l'intégration peuvent être automatiquement validés avec un traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="878c3-141">The integration inventory journals generated by the integration can automatically be posted using a batch job.</span></span> <span data-ttu-id="878c3-142">Pour cela, accédez à : **Gestion des stocks > Tâches périodiques > Intégration CDS > Valider les journaux de stock pour l'intégration**.</span><span class="sxs-lookup"><span data-stu-id="878c3-142">This is enabled from **Inventory management > Periodic tasks > CDS integration > Post integration inventory journals**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="878c3-143">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="878c3-143">Template mapping in Data integration</span></span>

<span data-ttu-id="878c3-144">Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="878c3-144">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a><span data-ttu-id="878c3-145">Ajustement de stock (Field Service vers Supply Chain Management) : ajustement de stock</span><span class="sxs-lookup"><span data-stu-id="878c3-145">Inventory adjustment (Field Service to Supply Chain Management): Inventory adjustment</span></span>

<span data-ttu-id="878c3-146">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="878c3-146">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a><span data-ttu-id="878c3-147">Transfert de stock (Field Service vers Supply Chain Management) : transfert de stock</span><span class="sxs-lookup"><span data-stu-id="878c3-147">Inventory transfer (Field Service to Supply Chain Management): Inventory transfer</span></span>

<span data-ttu-id="878c3-148">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="878c3-148">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>
