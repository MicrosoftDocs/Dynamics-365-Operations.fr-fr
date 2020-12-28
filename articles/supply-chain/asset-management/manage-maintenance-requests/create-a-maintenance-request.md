---
title: Créer des demandes de maintenance
description: Cette rubrique explique comment créer une demande de maintenance dans Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetRequestTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 22d5e371c386abc71946bf64ed8792647f78cf1b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427950"
---
# <a name="create-maintenance-requests"></a><span data-ttu-id="9e221-103">Créer des demandes de maintenance</span><span class="sxs-lookup"><span data-stu-id="9e221-103">Create maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="9e221-104">Les demandes de maintenance peuvent être utilisées si les agents de maintenance ou de production découvrent que l'équipement doit être réparé, mais que la réparation ne peut pas être effectuée immédiatement.</span><span class="sxs-lookup"><span data-stu-id="9e221-104">Maintenance requests can be used if maintenance workers or production workers discover that equipment requires repair, but the repair job can't be done right away.</span></span>

<span data-ttu-id="9e221-105">**Exemple :** Pendant qu'un agent de maintenance effectue une réparation, il découvre qu'un autre actif situé au même endroit doit être réparé.</span><span class="sxs-lookup"><span data-stu-id="9e221-105">**Example:** While a maintenance worker is making a repair, she discovers that another asset at the same location must be serviced.</span></span> <span data-ttu-id="9e221-106">Cependant, l'agent de maintenance n'a pas le temps ni les pièces de rechange nécessaires pour effectuer le travail de réparation.</span><span class="sxs-lookup"><span data-stu-id="9e221-106">However, the maintenance worker doesn't have the time or the required spare parts to do the repair job.</span></span> <span data-ttu-id="9e221-107">Par conséquent, il crée une demande de maintenance pour l'actif et entre une brève description du problème.</span><span class="sxs-lookup"><span data-stu-id="9e221-107">Therefore, she creates a maintenance request on the asset and enters a short description of the issue.</span></span>

<span data-ttu-id="9e221-108">La section **Demandes de maintenance actives** du volet **Informations associées** à droite de la page **Tous les actifs** ou **Actifs actifs** (**Gestion d'actifs** \> **Commun** \> **Actifs** \> **Tous les actifs** ou **Actifs actifs**) affiche les demandes de maintenance actives attachées à l'actif sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9e221-108">The **Active maintenance requests** section of the **Related information** pane on the right side of the **All assets** or **Active assets** page (**Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**) shows the active maintenance requests that are attached to the selected asset.</span></span>

1. <span data-ttu-id="9e221-109">Sélectionnez **Gestion des actifs** \> **Commun** \> **Demandes de maintenance** \> **Toutes les demandes de maintenance** ou **Demandes de maintenance actives**.</span><span class="sxs-lookup"><span data-stu-id="9e221-109">Select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests** or **Active maintenance requests**.</span></span>
2. <span data-ttu-id="9e221-110">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9e221-110">Select **New**.</span></span>
3. <span data-ttu-id="9e221-111">Dans la boîte de dialogue **Créer une demande**, dans le champ **Type de demande de maintenance**, sélectionnez le type de demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="9e221-111">In the **Create request** dialog box, in the **Maintenance request type** field, select the type of maintenance request.</span></span> <span data-ttu-id="9e221-112">Un type par défaut est proposé.</span><span class="sxs-lookup"><span data-stu-id="9e221-112">A default type is suggested.</span></span>
4. <span data-ttu-id="9e221-113">Dans le champ **Description**, entrez un nom ou un titre décrivant brièvement la demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="9e221-113">In the **Description** field, enter a name or title that briefly describes the maintenance request.</span></span>
5. <span data-ttu-id="9e221-114">Dans les champs **Poste technique** et **Actif**, sélectionnez un poste technique ou un actif, ou la combinaison d'un poste technique et d'un actif, comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="9e221-114">In the **Functional location** and **Asset** fields, select a functional location or an asset, or a combination of a functional location and an asset, as you require.</span></span> <span data-ttu-id="9e221-115">Vous pouvez créer une demande de maintenance sans activer d'actif, et l'actif pourra être ajouté à la demande de maintenance ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="9e221-115">You can create a maintenance request without selecting an asset, and the asset can be added to the maintenance request later.</span></span> <span data-ttu-id="9e221-116">Si l'agent de maintenance qui est connecté est lié à une ressource associée à un actif, le champ **Actif** est automatiquement défini.</span><span class="sxs-lookup"><span data-stu-id="9e221-116">If the maintenance worker who is signed in is related to a resource that is related to an asset, the **Asset** field is automatically set.</span></span>

    <span data-ttu-id="9e221-117">Si une demande de maintenance est déjà jointe à l’actif sélectionné, une barre de message apparaît en haut de la boîte de dialogue **Créer une demande** pour vous indiquer l'ID de la demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="9e221-117">If a maintenance request is already attached to the selected asset, a message bar appears at the top of the **Create request** dialog box to notify you about the ID of the existing maintenance request.</span></span> <span data-ttu-id="9e221-118">Une barre de message vous informe également si l'actif est couvert par un accord de garantie.</span><span class="sxs-lookup"><span data-stu-id="9e221-118">A message bar also notifies you if the asset is covered by a warranty agreement.</span></span>

6. <span data-ttu-id="9e221-119">Dans le champ **Niveau de service**, sélectionnez un niveau de service qui indique l'urgence de la demande.</span><span class="sxs-lookup"><span data-stu-id="9e221-119">In the **Service level** field, select a service level that indicates the urgency of the request.</span></span>
7. <span data-ttu-id="9e221-120">Si vous avez sélectionné un actif à l'étape 5, vous pouvez utiliser les champs **Symptôme de défaut**, **Zone de défaut** et **Type de défaut** pour créer un enregistrement de défaut.</span><span class="sxs-lookup"><span data-stu-id="9e221-120">If you selected an asset in step 5, you can use the **Fault symptom**, **Fault area**, and **Fault type** fields to create a fault registration.</span></span>
8. <span data-ttu-id="9e221-121">Si la demande de maintenance a entraîné un temps d'arrêt pour maintenance, entrez la date et l'heure de début du temps d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="9e221-121">If the maintenance request has caused maintenance downtime, enter the start date and time of the downtime.</span></span>

    <span data-ttu-id="9e221-122">Le champ **Lancé par** est automatiquement défini pour votre nom.</span><span class="sxs-lookup"><span data-stu-id="9e221-122">The **Started by** field is automatically set to your name.</span></span>

10. <span data-ttu-id="9e221-123">Le champ **Début réel** est automatiquement défini sur la date et l'heure actuelles.</span><span class="sxs-lookup"><span data-stu-id="9e221-123">The **Actual start** field is automatically set to the current date and time.</span></span> <span data-ttu-id="9e221-124">Vous pouvez néanmoins modifier la valeur comme vous le voulez.</span><span class="sxs-lookup"><span data-stu-id="9e221-124">However, you can change the value as you require.</span></span>
11. <span data-ttu-id="9e221-125">Dans le champ **Détails**, entrez des notes supplémentaires requises.</span><span class="sxs-lookup"><span data-stu-id="9e221-125">In the **Notes** field, enter any additional notes that are required.</span></span>
12. <span data-ttu-id="9e221-126">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9e221-126">Select **OK**.</span></span>

![Créer une demande de maintenance](media/03-manage-maintenance-requests.png)

## <a name="subsequent-processing-of-maintenance-requests"></a><span data-ttu-id="9e221-128">Traitement ultérieur des demandes de maintenance</span><span class="sxs-lookup"><span data-stu-id="9e221-128">Subsequent processing of maintenance requests</span></span>

<span data-ttu-id="9e221-129">Une fois une demande de maintenance créée, mais avant qu’elle ne soit convertie en ordre de travail, vous devez mettre à jour diverses informations.</span><span class="sxs-lookup"><span data-stu-id="9e221-129">After a maintenance request is created, but before it's converted to a work order, various information should be updated on it.</span></span> <span data-ttu-id="9e221-130">Généralement, un gestionnaire ou un autre employé administratif effectue cette tâche.</span><span class="sxs-lookup"><span data-stu-id="9e221-130">Typically, a planner or another administrative employee completes this task.</span></span>

- <span data-ttu-id="9e221-131">Dans la page **Toutes les demandes de maintenance** ou **Demandes de maintenance actives**, sélectionnez la demande à utiliser, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="9e221-131">On the **All maintenance requests** or **Active maintenance requests** page, select the request to work with, and then select **Edit**.</span></span>

<span data-ttu-id="9e221-132">Dans la vue Détails, vous pouvez mettre à jour diverses informations.</span><span class="sxs-lookup"><span data-stu-id="9e221-132">In the details view, you can update various information.</span></span> <span data-ttu-id="9e221-133">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="9e221-133">Here are some examples:</span></span>

- <span data-ttu-id="9e221-134">Sélectionnez et vérifiez l'actif.</span><span class="sxs-lookup"><span data-stu-id="9e221-134">Select and verify the asset.</span></span> <span data-ttu-id="9e221-135">Si vous devez sélectionner un autre actif ultérieurement, vous pouvez définir l'option **Actif vérifié** sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="9e221-135">If you must select a different asset later, you can set the **Asset verified** option to **No**.</span></span>
- <span data-ttu-id="9e221-136">Sélectionnez un groupe d'agents de maintenance responsable et/ou un agent de maintenance responsable.</span><span class="sxs-lookup"><span data-stu-id="9e221-136">Select a responsible maintenance worker group and/or a responsible maintenance worker.</span></span> <span data-ttu-id="9e221-137">Pour plus d'informations sur le paramétrage requis, voir [Agents de maintenance responsables](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="9e221-137">For more information about the required setup, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>
- <span data-ttu-id="9e221-138">Sélectionnez un type de tâche de maintenance et, si ces informations sont pertinentes, une variante de la tâche de maintenance associée et un commerce de tâche.</span><span class="sxs-lookup"><span data-stu-id="9e221-138">Select a maintenance job type and, if this information is relevant, a related maintenance job variant and a job trade.</span></span>
- <span data-ttu-id="9e221-139">Dans les champs **Latitude** et **Longitude**, entrez les coordonnées géographiques.</span><span class="sxs-lookup"><span data-stu-id="9e221-139">In the **Latitude** and **Longitude** fields, enter geographic coordinates.</span></span> <span data-ttu-id="9e221-140">Toutes les coordonnées ajoutées à une demande de maintenance sont automatiquement transférées vers un ordre de travail associé.</span><span class="sxs-lookup"><span data-stu-id="9e221-140">Any coordinates that are added to a maintenance request are automatically transferred to a related work order.</span></span> 

![Mettre à jour la demande de maintenance](media/04-manage-maintenance-requests.png)

> [!NOTE]
> <span data-ttu-id="9e221-142">Si vous sélectionnez un actif lorsque vous créez une demande de maintenance, vous pouvez ajouter un défaut à l'actif.</span><span class="sxs-lookup"><span data-stu-id="9e221-142">If you select an asset when you create a maintenance request, you can add one fault to the asset.</span></span> <span data-ttu-id="9e221-143">Une fois la demande de maintenance créée, vous pouvez ajouter des défauts, comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="9e221-143">After the maintenance request has been created, you can add more faults, as you require.</span></span> <span data-ttu-id="9e221-144">Pour ajouter des défauts, sélectionnez **Défaut d'actif** sur la page **Toutes les demandes de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="9e221-144">To add faults, select **Asset fault** on the **All maintenance requests** page.</span></span>
