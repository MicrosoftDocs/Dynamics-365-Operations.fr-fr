---
title: Synchroniser les transferts et les ajustements de stock depuis Field Service vers Supply Chain Management
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les ajustements de stock et les transferts depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 04/30/2019
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
ms.openlocfilehash: fce407a66c339f2ece4bbc37b30243a2ed172d0a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251887"
---
# <a name="synchronize-inventory-transfers-and-adjustments-from-field-service-to-supply-chain-management"></a><span data-ttu-id="404eb-103">Synchroniser les transferts et les ajustements de stock depuis Field Service vers Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="404eb-103">Synchronize inventory transfers and adjustments from Field Service to Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="404eb-104">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les ajustements de stock et les transferts depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="404eb-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="404eb-105">[![Synchronisation des processus d’entreprise entre Supply Chain Management et Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="404eb-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="404eb-106">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="404eb-106">Templates and tasks</span></span>
<span data-ttu-id="404eb-107">Le modèle et les tâches sous-jacentes suivants sont utilisés pour synchroniser les ajustements de stock et les transferts depuis Field Service vers Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="404eb-107">The following template and underlying tasks are used to synchronize inventory adjustments and transfers from Field Service to Supply Chain Management.</span></span>

<span data-ttu-id="404eb-108">**Modèles dans l’intégration de données**</span><span class="sxs-lookup"><span data-stu-id="404eb-108">**Templates in Data integration**</span></span>
- <span data-ttu-id="404eb-109">Ajustement de stock (Field Service vers Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="404eb-109">Inventory Adjustment (Field Service to Supply Chain Management)</span></span>
- <span data-ttu-id="404eb-110">Transferts de stock (Field Service vers Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="404eb-110">Inventory Transfers (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="404eb-111">**Tâches des projets d’intégration des données**</span><span class="sxs-lookup"><span data-stu-id="404eb-111">**Tasks in the Data integration projects**</span></span>
- <span data-ttu-id="404eb-112">Ajustements de stock</span><span class="sxs-lookup"><span data-stu-id="404eb-112">Inventory Adjustments</span></span>
- <span data-ttu-id="404eb-113">Transferts de stock</span><span class="sxs-lookup"><span data-stu-id="404eb-113">Inventory Transfers</span></span>

## <a name="table-set"></a><span data-ttu-id="404eb-114">Ensemble de tables</span><span class="sxs-lookup"><span data-stu-id="404eb-114">Table set</span></span>
| <span data-ttu-id="404eb-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="404eb-115">Field Service</span></span>                     | <span data-ttu-id="404eb-116">Gestion de la chaîne d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="404eb-116">Supply Chain Management</span></span>                          |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="404eb-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="404eb-117">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="404eb-118">En-têtes et lignes du journal d’ajustement de stock de Dataverse</span><span class="sxs-lookup"><span data-stu-id="404eb-118">Dataverse Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="404eb-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="404eb-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="404eb-120">En-têtes et lignes du journal de transfert de stock de Dataverse</span><span class="sxs-lookup"><span data-stu-id="404eb-120">Dataverse inventory transfer journal headers and lines</span></span>   |

## <a name="table-flow"></a><span data-ttu-id="404eb-121">Flux de table</span><span class="sxs-lookup"><span data-stu-id="404eb-121">Table flow</span></span>
<span data-ttu-id="404eb-122">Les ajustements et les transferts de stock effectués dans Field Service se synchronisent sur Supply Chain Management, une fois que le **Statut de validation** passe de **Créé** à **Validé**.</span><span class="sxs-lookup"><span data-stu-id="404eb-122">Inventory adjustments and transfers made in Field Service will synchronize to Supply Chain Management after the **Post status** changes from **Created** to **Posted**.</span></span> <span data-ttu-id="404eb-123">Dans ce cas, l’ajustement ou l’ordre de transfert est verrouillé et passe en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="404eb-123">When this occurs, the adjustment or the transfer order will be locked and become read only.</span></span> <span data-ttu-id="404eb-124">Cela signifie que les ajustements et les transferts peuvent être validés dans Supply Chain Management, mais ne peuvent pas être modifiés.</span><span class="sxs-lookup"><span data-stu-id="404eb-124">This means that adjustments and transfers can be posted in Supply Chain Management, but cannot be modified.</span></span> <span data-ttu-id="404eb-125">Dans Supply Chain Management, vous pouvez paramétrer un traitement par lots pour valider automatiquement les journaux d’ajustements et de transferts de stock générés par l’intégration.</span><span class="sxs-lookup"><span data-stu-id="404eb-125">In Supply Chain Management, you can set up a batch job to automatically post the adjustments and transfer inventory journals that have been generated during the integration.</span></span> <span data-ttu-id="404eb-126">Voir les prérequis ci-dessous pour plus d’informations sur la procédure d’activation du traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="404eb-126">See the following prerequisites for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="404eb-127">Solution Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="404eb-127">Field Service CRM solution</span></span> 
<span data-ttu-id="404eb-128">La colonne **Unité de stock** a été ajoutée à la table **Produit**.</span><span class="sxs-lookup"><span data-stu-id="404eb-128">The **Inventory unit** column has been added to the **Product** table.</span></span> <span data-ttu-id="404eb-129">Cette colonne est nécessaire, car l’unité de vente et de stock n’est pas toujours la même dans Supply Chain Management, et l’unité de stock est nécessaire pour le stock de l’entrepôt dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="404eb-129">This column is needed because the Sales and Inventory unit is not always the same in Supply Chain Management, and the Inventory Unit is needed for the Warehouse Inventory in Supply Chain Management.</span></span>
<span data-ttu-id="404eb-130">Lorsque vous définissez le produit sur un produit d’ajustement de stock pour les ajustements de stock et les transferts de stock, l’unité est extraite de la valeur du produit de stock.</span><span class="sxs-lookup"><span data-stu-id="404eb-130">When you set the product on an Inventory adjustment product for both Inventory adjustments and Inventory transfers, the unit will be fetched from the inventory product value.</span></span> <span data-ttu-id="404eb-131">Si une valeur est trouvée, la colonne **Unité** est verrouillée sur le produit d’ajustement de stock.</span><span class="sxs-lookup"><span data-stu-id="404eb-131">If a value is found, the **Unit** column will be locked on the Inventory adjustment product.</span></span>

<span data-ttu-id="404eb-132">La colonne **Statut de validation** a été ajoutée à la table **Ajustement de stock** et à la table **Transfert de stock**.</span><span class="sxs-lookup"><span data-stu-id="404eb-132">The **Post status** column has been added to both the **Inventory adjustment** table and the **Inventory transfer** table.</span></span> <span data-ttu-id="404eb-133">Cette colonne est utilisée comme filtre lorsqu’un ajustement ou un transfert est envoyé à Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="404eb-133">This column is used as a filter when an adjustment or transfer is sent to Supply Chain Management.</span></span> <span data-ttu-id="404eb-134">La valeur par défaut pour cette colonne est Créé (1), mais elle n’est pas envoyée à Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="404eb-134">The default for this column is Created (1), however it is not sent to Supply Chain Management.</span></span> <span data-ttu-id="404eb-135">Lorsque vous mettez à jour la valeur sur Validé (2), il est envoyé à Supply Chain Management, mais vous ne pourrez ensuite plus rien modifier dans Ajustement ou Transfert, ni ajouter aucune ligne à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="404eb-135">When you update the value to Posted (2), it is sent to Supply Chain Management, but after that you will no longer be able to change the adjustment or transfer or add new lines.</span></span>

<span data-ttu-id="404eb-136">La colonne **Souche de numéros** a été ajoutée à la table **Produit d’ajustement de stock**.</span><span class="sxs-lookup"><span data-stu-id="404eb-136">The **Number sequence** column has been added to the **Inventory adjustment product** table.</span></span> <span data-ttu-id="404eb-137">Cette colonne garantit que l’intégration a un numéro unique, et que l’intégration peut créer et mettre à jour l’ajustement.</span><span class="sxs-lookup"><span data-stu-id="404eb-137">This column ensures that the integration has a unique number, so the integration can create and update the adjustment.</span></span> <span data-ttu-id="404eb-138">Lorsque vous créez votre premier produit d’ajustement de stock, un enregistrement sera créé dans la table **P2C AutoNumber** pour tenir à jour la souche de numéros et le préfixe utilisé.</span><span class="sxs-lookup"><span data-stu-id="404eb-138">When you create your first inventory adjustment product, it will create a new record in the **P2C AutoNumber** table to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="404eb-139">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="404eb-139">Prerequisites and mapping setup</span></span>

### <a name="supply-chain-management"></a><span data-ttu-id="404eb-140">Gestion de la chaîne d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="404eb-140">Supply Chain Management</span></span>
<span data-ttu-id="404eb-141">Les journaux de stock d’intégration générés par l’intégration peuvent être automatiquement validés avec un traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="404eb-141">The integration inventory journals generated by the integration can automatically be posted using a batch job.</span></span> <span data-ttu-id="404eb-142">Pour cela, accédez à : **Gestion des stocks > Tâches périodiques > Intégration de Dataverse > Valider les journaux de stock pour l’intégration**.</span><span class="sxs-lookup"><span data-stu-id="404eb-142">This is enabled from **Inventory management > Periodic tasks > Dataverse integration > Post integration inventory journals**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="404eb-143">Mise en correspondance de modèles dans l’intégration de données</span><span class="sxs-lookup"><span data-stu-id="404eb-143">Template mapping in Data integration</span></span>

<span data-ttu-id="404eb-144">Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="404eb-144">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a><span data-ttu-id="404eb-145">Ajustement de stock (Field Service vers Supply Chain Management) : ajustement de stock</span><span class="sxs-lookup"><span data-stu-id="404eb-145">Inventory adjustment (Field Service to Supply Chain Management): Inventory adjustment</span></span>

<span data-ttu-id="404eb-146">[![Mise en correspondance de modèles dans l’intégration de données](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="404eb-146">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a><span data-ttu-id="404eb-147">Transfert de stock (Field Service vers Supply Chain Management) : transfert de stock</span><span class="sxs-lookup"><span data-stu-id="404eb-147">Inventory transfer (Field Service to Supply Chain Management): Inventory transfer</span></span>

<span data-ttu-id="404eb-148">[![Mise en correspondance de modèles dans l’intégration de données](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="404eb-148">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]