---
title: "Planifier la capacité de charge de travail"
description: "Cette rubrique explique comment paramétrer et planifier la capacité de charge de travail pour les collaborateurs d'un entrepôt ou pour un entrepôt entier."
author: MarkusFogelberg
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSWorkloadCapacity
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 69b9c5590e6f9311696bbbed2e63a6eeba2a90bf
ms.openlocfilehash: 1b93cfaf098b4cff3e72ee9bb599eadfdac2a9b9
ms.contentlocale: fr-fr
ms.lasthandoff: 05/03/2018

---

# <a name="schedule-workload-capacity"></a><span data-ttu-id="78aa2-103">Planifier la capacité de charge de travail</span><span class="sxs-lookup"><span data-stu-id="78aa2-103">Schedule workload capacity</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="78aa2-104">Vous pouvez programmer la capacité de la charge de travail pour les entrepôts, et vous pouvez également prévoir les charges de travail actuelles et futures pour les collaborateurs des entrepôts individuels.</span><span class="sxs-lookup"><span data-stu-id="78aa2-104">You can schedule workload capacity for warehouses, and you can also project the current and future workloads for the workers in individual warehouses.</span></span> <span data-ttu-id="78aa2-105">Vous pouvez prévoir la charge de travail pour l'ensemble de l'entrepôt, ou vous pouvez prévoir la charge de travail séparément pour les charges de travail entrantes et sortantes.</span><span class="sxs-lookup"><span data-stu-id="78aa2-105">You can project the workload for the whole warehouse, or you can project the workload separately for incoming and outgoing workloads.</span></span>

<span data-ttu-id="78aa2-106">Pour prévoir la charge de travail sortante pour les entrepôts sélectionnés, les données du calcul PDP/MRP doivent être disponibles pour ces entrepôts.</span><span class="sxs-lookup"><span data-stu-id="78aa2-106">To project workload output for selected warehouses, master scheduling data must be available for those warehouses.</span></span> <span data-ttu-id="78aa2-107">Pour plus d'informations, voir [Plans généraux](../master-planning/master-plans.md).</span><span class="sxs-lookup"><span data-stu-id="78aa2-107">For more information, see [Master plans](../master-planning/master-plans.md).</span></span>

## <a name="schedule-and-view-workloads-for-a-warehouse"></a><span data-ttu-id="78aa2-108">Planification et affichage des charges de travail pour un entrepôt</span><span class="sxs-lookup"><span data-stu-id="78aa2-108">Schedule and view workloads for a warehouse</span></span>

<span data-ttu-id="78aa2-109">Pour planifier la capacité de la charge de travail d'un entrepôt, vous devez créer un paramétrage de charge de travail pour un ou plusieurs entrepôts, puis associer ce paramétrage à un plan général.</span><span class="sxs-lookup"><span data-stu-id="78aa2-109">To schedule workload capacity for a warehouse, you create a workload setup for one or more warehouses, and then associate the workload setup with a master plan.</span></span> <span data-ttu-id="78aa2-110">Dans le paramétrage de la capacité de la charge de travail, vous pouvez définir des limites pour le poids ou le volume des transactions entrantes et sortantes.</span><span class="sxs-lookup"><span data-stu-id="78aa2-110">In the workload capacity setup, you can define limits for the weight or volume for incoming and outgoing transactions.</span></span> <span data-ttu-id="78aa2-111">Vous pouvez également créer plusieurs paramétrages pour chaque entrepôt, puis associer le paramétrage à des plans généraux individuels.</span><span class="sxs-lookup"><span data-stu-id="78aa2-111">You can also create more than one setup for each warehouse and then associate the setup with individual master plans.</span></span> <span data-ttu-id="78aa2-112">Vous pouvez par exemple utiliser cette approche pour répondre aux modifications saisonnières du personnel.</span><span class="sxs-lookup"><span data-stu-id="78aa2-112">For example, you might use this approach to accommodate seasonal changes in the workforce.</span></span>

<span data-ttu-id="78aa2-113">Si les collaborateurs d'un entrepôt utilisent des transactions à la fois pour les charges de travail entrantes et sortantes, vous pouvez configurer le paramétrage de la capacité de l'entrepôt de façon à ce que la charge de travail soit projetée dans une vue combinée.</span><span class="sxs-lookup"><span data-stu-id="78aa2-113">If the workers for a warehouse work with transactions for both incoming and outgoing workloads, you can configure the warehouse capacity setup so that the workload is projected in a combined view.</span></span>

<span data-ttu-id="78aa2-114">Pour planifier et afficher les charges de travail pour les entrepôts, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="78aa2-114">To schedule and view workloads for warehouses, you must complete the following tasks:</span></span>

1. <span data-ttu-id="78aa2-115">Créez un paramétrage de la capacité de la charge de travail et définissez des limites de capacité de la charge de travail pour un ou plusieurs entrepôts.</span><span class="sxs-lookup"><span data-stu-id="78aa2-115">Create a workload capacity setup and define workload capacity limits for one or more warehouses.</span></span>
2. <span data-ttu-id="78aa2-116">Associez le paramétrage de la capacité de la charge de travail à un plan général pour créer des projections de charge de travail et spécifier la durée pendant laquelle celles-ci s'appliquent.</span><span class="sxs-lookup"><span data-stu-id="78aa2-116">Associate the workload capacity setup with a master plan to create workload projections and specify how long those projections will apply.</span></span>

### <a name="create-a-workload-capacity-setup-for-a-warehouse"></a><span data-ttu-id="78aa2-117">Création d'un paramétrage de la capacité de la charge de travail pour un entrepôt</span><span class="sxs-lookup"><span data-stu-id="78aa2-117">Create a workload capacity setup for a warehouse</span></span>

1. <span data-ttu-id="78aa2-118">Sélectionnez **Gestion des stocks** \> **Paramétrage** \> **Surveillance de l'entrepôt** \> **Capacité de la charge de travail**.</span><span class="sxs-lookup"><span data-stu-id="78aa2-118">Select **Inventory management** \> **Setup** \> **Warehouse monitoring** \> **Workload capacity**.</span></span>
2. <span data-ttu-id="78aa2-119">Dans le volet Actions, sélectionnez **Nouveau** pour créer un paramétrage de la capacité de charge de travail.</span><span class="sxs-lookup"><span data-stu-id="78aa2-119">On the Action Pane, select **New** to create a workload capacity setup.</span></span>
3. <span data-ttu-id="78aa2-120">Dans l'organisateur **Entrepôts**, sélectionnez **Nouveau** puis entrez les valeurs sur la ligne pour associer un entrepôt au paramétrage de la capacité de la charge de travail.</span><span class="sxs-lookup"><span data-stu-id="78aa2-120">On the **Warehouses** FastTab, select **New**, and then enter values on the line to associate a warehouse with the workload capacity setup.</span></span>
4. <span data-ttu-id="78aa2-121">Activez la case à cocher **Combinaison des charges de travail entrante et sortante** si l'état **Capacité de la charge de travail** doit afficher la charge de travail totale pour les transactions entrantes et sortantes sur une seule vue.</span><span class="sxs-lookup"><span data-stu-id="78aa2-121">Select the **Combined inbound and outbound workload** check box if the **Workload capacity** report should show the total workload for incoming and outgoing transactions in one view.</span></span>
5. <span data-ttu-id="78aa2-122">Dans l'organisateur **Types de transactions**, sélectionnez les types de transactions entrantes et sortantes auxquels les limites de charge de travail s'appliquent.</span><span class="sxs-lookup"><span data-stu-id="78aa2-122">On the **Transaction types** FastTab, select the types of incoming and outgoing transactions that the workload limits will apply to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="78aa2-123">Vous devez sélectionner au moins un type de transaction pour la charge de travail entrante et la charge de travail sortante.</span><span class="sxs-lookup"><span data-stu-id="78aa2-123">You must select at least one transaction type for both the incoming workload and the outgoing workload.</span></span>

#### <a name="define-limits-for-volume-or-weight"></a><span data-ttu-id="78aa2-124">Définir des limites pour le volume ou le poids</span><span class="sxs-lookup"><span data-stu-id="78aa2-124">Define limits for volume or weight</span></span>

<span data-ttu-id="78aa2-125">Vous pouvez paramétrer des limites pour le volume ou le poids selon la limitation appropriée pour le personnel de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="78aa2-125">You can set up limits for volume or weight, depending on the limitation that is relevant for the warehouse workforce.</span></span> <span data-ttu-id="78aa2-126">Les limites que vous spécifiez sont incluses dans la projection de la capacité de la charge de travail que vous pouvez afficher dans l'état **Capacité de la charge de travail**.</span><span class="sxs-lookup"><span data-stu-id="78aa2-126">The limits that you specify are included in the workload capacity projection that you can view on the **Workload capacity** report.</span></span>

<span data-ttu-id="78aa2-127">Le volume standard d'un article en stock et le poids d'un article en stock doivent être spécifiés pour tous les produits pour pouvoir projeter des informations sur le volume et le poids des articles.</span><span class="sxs-lookup"><span data-stu-id="78aa2-127">To project information about volume and weight for items, the standard volume of one inventory item and the weight of one inventory item must be specified for all products.</span></span> <span data-ttu-id="78aa2-128">Les champs requis sont disponibles dans les groupes de champs suivants de l'organisateur **Gérer le stock** de la page **Détails des produits lancés** :</span><span class="sxs-lookup"><span data-stu-id="78aa2-128">The fields that are required are available in the following field groups on the **Manage inventory** FastTab of the **Released product details** page:</span></span>

- <span data-ttu-id="78aa2-129">Traitement</span><span class="sxs-lookup"><span data-stu-id="78aa2-129">Handling</span></span>
- <span data-ttu-id="78aa2-130">Dimensions physiques</span><span class="sxs-lookup"><span data-stu-id="78aa2-130">Physical dimensions</span></span>
- <span data-ttu-id="78aa2-131">Mesures pondérales</span><span class="sxs-lookup"><span data-stu-id="78aa2-131">Weight measurements</span></span>

<span data-ttu-id="78aa2-132">Si ces informations ne sont pas spécifiées correctement, vous recevez un message lors de la génération de l'état **Capacité de la charge de travail**.</span><span class="sxs-lookup"><span data-stu-id="78aa2-132">If this information isn't specified correctly, you receive a message when you generate the **Workload capacity** report.</span></span> <span data-ttu-id="78aa2-133">Depuis l'état, vous pouvez ensuite effectuer un zoom avant afin d'identifier les informations manquantes requises pour la projection de la future charge de travail.</span><span class="sxs-lookup"><span data-stu-id="78aa2-133">From the report, you can then drill down to identify the missing information that is required in order to project the future workload.</span></span>

### <a name="associate-a-workload-capacity-setup-with-a-master-plan"></a><span data-ttu-id="78aa2-134">Association d'un paramétrage de la capacité de la charge de travail à un plan général</span><span class="sxs-lookup"><span data-stu-id="78aa2-134">Associate a workload capacity setup with a master plan</span></span>

1. <span data-ttu-id="78aa2-135">Sélectionnez **Gestion des stocks** \> **Périodique** \> **Programmer la charge de travail**.</span><span class="sxs-lookup"><span data-stu-id="78aa2-135">Select **Inventory management** \> **Periodic** \> **Schedule workload**.</span></span>
2. <span data-ttu-id="78aa2-136">Dans le champ **Plans généraux**, sélectionnez le plan général à utiliser pour les projections de charge de travail.</span><span class="sxs-lookup"><span data-stu-id="78aa2-136">In the **Master plan** field, select the master plan to use for workload projections.</span></span>
3. <span data-ttu-id="78aa2-137">Dans le champ **Nombre de jours**, spécifiez le nombre de jours couvert par la projection de charge de travail.</span><span class="sxs-lookup"><span data-stu-id="78aa2-137">In the **Number of days** field, specify the number of days that the workload projection covers.</span></span>
4. <span data-ttu-id="78aa2-138">Dans le champ **Charge de travail**, sélectionnez le paramétrage de charge de travail à associer au plan général.</span><span class="sxs-lookup"><span data-stu-id="78aa2-138">In the **Workload** field, select the workload setup to associate with the master plan.</span></span>

### <a name="view-workload-capacity"></a><span data-ttu-id="78aa2-139">Affichage de la capacité de la charge de travail</span><span class="sxs-lookup"><span data-stu-id="78aa2-139">View workload capacity</span></span>

1. <span data-ttu-id="78aa2-140">Sélectionnez **Gestion des stocks** \> **Recherches et états** \> **États sur le stock physique** \> **Capacité de la charge de travail**.</span><span class="sxs-lookup"><span data-stu-id="78aa2-140">Select **Inventory management** \> **Inquiries and reports** \> **Physical inventory reports** \> **Workload capacity**.</span></span>
2. <span data-ttu-id="78aa2-141">Dans le champ **Nombre de colonnes**, spécifiez le nombre de colonnes à afficher dans l'état.</span><span class="sxs-lookup"><span data-stu-id="78aa2-141">In the **Number of columns** field, specify the number of columns to show on the report.</span></span>
3. <span data-ttu-id="78aa2-142">Dans le champ **Type de commande**, sélectionnez **Prévu et confirmé**, **Prévu** ou **Confirmé** pour indiquer le type de commandes à projeter dans l'état.</span><span class="sxs-lookup"><span data-stu-id="78aa2-142">In the **Order type** field, select **Planned and confirmed**, **Planned**, or **Confirmed** to indicate the type of orders to project on the report.</span></span>
4. <span data-ttu-id="78aa2-143">Dans le champ **Type de charge**, sélectionnez un type de charge pour spécifier si la capacité de la charge de travail est projetée pour le volume ou le poids.</span><span class="sxs-lookup"><span data-stu-id="78aa2-143">In the **Load type** field, select a load type to specify whether the workload capacity should be projected for volume or weight.</span></span>
5. <span data-ttu-id="78aa2-144">Dans le champ **Capacité de la charge de travail**, sélectionnez un paramétrage pour la capacité de la charge de travail.</span><span class="sxs-lookup"><span data-stu-id="78aa2-144">In the **Workload capacity** field, select a workload capacity setup.</span></span>

