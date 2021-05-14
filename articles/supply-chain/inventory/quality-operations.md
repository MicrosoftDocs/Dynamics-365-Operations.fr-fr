---
title: Opérations pour les non-conformités
description: Cette rubrique décrit comment créer et utiliser des opérations pour les non-conformités.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestOperations, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6454a56323ea66369696dd6e3310a41b4eb9ee58
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956660"
---
# <a name="operations-for-nonconformances"></a><span data-ttu-id="581b5-103">Opérations pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="581b5-103">Operations for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="581b5-104">Cette rubrique décrit comment créer et utiliser des opérations pour les non-conformités.</span><span class="sxs-lookup"><span data-stu-id="581b5-104">This topic describes how to create and use operations for nonconformances.</span></span>

<span data-ttu-id="581b5-105">Vous pouvez utiliser la page **Opérations** pour définir les classifications des tâches pouvant être exécutées pour une non-conformité approuvée.</span><span class="sxs-lookup"><span data-stu-id="581b5-105">You can use the **Operations** page to define classifications of the work that can be performed for an approved nonconformance.</span></span> <span data-ttu-id="581b5-106">Lorsque vous affectez une opération associée à une non-conformité, vous pouvez fournir des informations détaillées, notamment sur la matière, les heures travaillées et les charges associées requises pour l’exécution de l’opération.</span><span class="sxs-lookup"><span data-stu-id="581b5-106">When you assign a related operation to a nonconformance, you can provide details such as the associated material, labor hours, and charges that are required to do the operation.</span></span> <span data-ttu-id="581b5-107">Le système utilise ces informations pour calculer le coût estimé de l’opération.</span><span class="sxs-lookup"><span data-stu-id="581b5-107">The system uses this information to calculate an estimated cost for the operation.</span></span> <span data-ttu-id="581b5-108">Les informations détaillées et les coûts estimés sont fournis à titre de référence.</span><span class="sxs-lookup"><span data-stu-id="581b5-108">The detailed information and estimated costs are for reference.</span></span> <span data-ttu-id="581b5-109">Les opérations associées pour la qualité diffèrent des opérations pouvant être définies pour une gamme de production.</span><span class="sxs-lookup"><span data-stu-id="581b5-109">The related operations for quality differ from the operations that can be defined for a production route.</span></span>

> [!NOTE]
> <span data-ttu-id="581b5-110">Bien que vous puissiez suivre les coûts, le temps et les éléments utilisés dans une opération liée à une non-conformité, les données que vous saisissez sont uniquement informatives.</span><span class="sxs-lookup"><span data-stu-id="581b5-110">Although you can track costs, time, and the items that are used in an operation that is related to a nonconformance, the data that you enter is only informational.</span></span> <span data-ttu-id="581b5-111">Elles ne sont pas automatiquement intégrées à la comptabilité, à la comptabilité auxiliaire du stock ou au module **Pointage**.</span><span class="sxs-lookup"><span data-stu-id="581b5-111">It isn't automatically integrated with the general ledger, inventory subledger, or the **Time and attendance** module.</span></span>

## <a name="examples-of-operations"></a><span data-ttu-id="581b5-112">Exemples d'opérations</span><span class="sxs-lookup"><span data-stu-id="581b5-112">Examples of operations</span></span>

<span data-ttu-id="581b5-113">Vous travaillez pour une entreprise de fabrication.</span><span class="sxs-lookup"><span data-stu-id="581b5-113">You work for a manufacturing company.</span></span> <span data-ttu-id="581b5-114">Une non-conformité a été créée et approuvée pour les éléments qui ont échoué à un test de qualité.</span><span class="sxs-lookup"><span data-stu-id="581b5-114">A nonconformance was created and approved for items that failed a quality test.</span></span> <span data-ttu-id="581b5-115">Une correction a été créée pour indiquer que le problème était lié à un mauvais roulement sur une machine.</span><span class="sxs-lookup"><span data-stu-id="581b5-115">A correction was created to indicate that the problem was related to a bad bearing on a machine.</span></span> <span data-ttu-id="581b5-116">Plusieurs étapes sont nécessaires pour remplacer le roulement et la responsabilité de chaque opération fait l'objet d'un suivi.</span><span class="sxs-lookup"><span data-stu-id="581b5-116">Several steps are required to replace the bearing, and the responsibility for each operation is tracked.</span></span> <span data-ttu-id="581b5-117">Par exemple, les étapes suivantes peuvent être requises :</span><span class="sxs-lookup"><span data-stu-id="581b5-117">For example, the following steps might be required:</span></span>

1. <span data-ttu-id="581b5-118">La ligne de production est arrêtée et la routine de nettoyage est exécutée.</span><span class="sxs-lookup"><span data-stu-id="581b5-118">The production line is stopped, and the clean-out routine is performed.</span></span>
1. <span data-ttu-id="581b5-119">Le personnel de maintenance remplace le roulement.</span><span class="sxs-lookup"><span data-stu-id="581b5-119">Maintenance personnel replace the bearing.</span></span>
1. <span data-ttu-id="581b5-120">Le personnel d'assurance qualité inspecte la machine avant de la rallumer.</span><span class="sxs-lookup"><span data-stu-id="581b5-120">Quality assurance personnel inspect the machine before it's turned back on.</span></span>

<span data-ttu-id="581b5-121">Pour cet exemple, les opérations suivantes peuvent être créées pour représenter le travail à effectuer :</span><span class="sxs-lookup"><span data-stu-id="581b5-121">For this example, the following operations can be created to represent the work that must be done:</span></span>

- <span data-ttu-id="581b5-122">Arrêter la ligne de production.</span><span class="sxs-lookup"><span data-stu-id="581b5-122">Stop the production line.</span></span>
- <span data-ttu-id="581b5-123">Nettoyer la ligne de production.</span><span class="sxs-lookup"><span data-stu-id="581b5-123">Clean out the production line.</span></span>
- <span data-ttu-id="581b5-124">Exécuter la maintenance de la machine.</span><span class="sxs-lookup"><span data-stu-id="581b5-124">Perform machine maintenance.</span></span>
- <span data-ttu-id="581b5-125">Inspecter la machine.</span><span class="sxs-lookup"><span data-stu-id="581b5-125">Inspect the machine.</span></span>

## <a name="create-an-operation"></a><span data-ttu-id="581b5-126">Créer une opération</span><span class="sxs-lookup"><span data-stu-id="581b5-126">Create an operation</span></span>

1. <span data-ttu-id="581b5-127">Accédez à **Gestion des stocks \> Paramétrage \> Gestion de la qualité \> Opérations**.</span><span class="sxs-lookup"><span data-stu-id="581b5-127">Go to **Inventory management \> Setup \> Quality management \> Operations**.</span></span>
1. <span data-ttu-id="581b5-128">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="581b5-128">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="581b5-129">Définissez ensuite les champs suivants pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="581b5-129">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="581b5-130">**Opération** - Entrez un ID ou un nom unique pour l'opération.</span><span class="sxs-lookup"><span data-stu-id="581b5-130">**Operation** – Enter a unique ID or name for the operation.</span></span>
    - <span data-ttu-id="581b5-131">**Description** – Entrez une description détaillée de l'opération.</span><span class="sxs-lookup"><span data-stu-id="581b5-131">**Description** – Enter a detailed description of the operation.</span></span>
    - <span data-ttu-id="581b5-132">**Taper** - Si l'opération ne peut être utilisée qu'avec des non-conformités liées à un type de commande spécifique, sélectionnez le type de commande (*Bon de commande* ou *Commande client*).</span><span class="sxs-lookup"><span data-stu-id="581b5-132">**Type** – If the operation can be used only with nonconformances that are related to a specific type of order, select the order type (*Purchase order* or *Sales order*).</span></span>

1. <span data-ttu-id="581b5-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="581b5-133">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="581b5-134">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="581b5-134">Additional resources</span></span>

- [<span data-ttu-id="581b5-135">Vue d’ensemble de la gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="581b5-135">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="581b5-136">Activer la gestion de la qualité et de la non-conformité</span><span class="sxs-lookup"><span data-stu-id="581b5-136">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="581b5-137">Créer et traiter les non-conformités</span><span class="sxs-lookup"><span data-stu-id="581b5-137">Create and process nonconformances</span></span>](tasks/create-process-non-conformance.md)
- [<span data-ttu-id="581b5-138">Collaborateurs chargés d'approuver les non-conformités</span><span class="sxs-lookup"><span data-stu-id="581b5-138">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="581b5-139">Zones de contrôle pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="581b5-139">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="581b5-140">Types de diagnostic pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="581b5-140">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="581b5-141">Frais de qualité pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="581b5-141">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="581b5-142">Types de problème pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="581b5-142">Problem types for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="581b5-143">Gestion de la qualité pour les processus d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="581b5-143">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
