---
title: Temps d'arrêt pour maintenance
description: Cette rubrique décrit le temps d'arrêt pour maintenance dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ad9f1b2a0e63b4fb0d6daceb451c3a1dc1ec7de7
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626150"
---
# <a name="maintenance-downtime"></a><span data-ttu-id="7085f-103">Temps d'arrêt pour maintenance</span><span class="sxs-lookup"><span data-stu-id="7085f-103">Maintenance downtime</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="7085f-104">Vous pouvez créer des enregistrements de temps d'arrêt pour maintenance sur l'actif sélectionné sur un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="7085f-104">You can create maintenance downtime registrations on the asset that is selected on a work order.</span></span> <span data-ttu-id="7085f-105">Cette capacité est utile si vous souhaitez enregistrer le temps d'arrêt pour maintenance sur une ou plusieurs machines dans la zone de production.</span><span class="sxs-lookup"><span data-stu-id="7085f-105">This capability is useful if you want to register maintenance downtime on one or more machines in the production area.</span></span> <span data-ttu-id="7085f-106">Premièrement, vous pouvez créer des codes motif de temps d'arrêt pour maintenance que vous souhaitez utiliser, par exemple, la **répartition** et **l'arrêt planifié**.</span><span class="sxs-lookup"><span data-stu-id="7085f-106">You first create the maintenance downtime reason codes that you want to use, such as **Breakdown** and **Planned stop**.</span></span> <span data-ttu-id="7085f-107">Cette étape s'effectue sur la page **Codes motif de temps d'arrêt pour maintenance**.</span><span class="sxs-lookup"><span data-stu-id="7085f-107">This step is done on the **Maintenance downtime reason codes** page.</span></span> <span data-ttu-id="7085f-108">Vous pouvez ensuite créer des enregistrements de temps d'arrêt pour maintenance sur la page **Temps d'arrêt pour maintenance** et ajouter des codes motif de temps d'arrêt pour maintenance appropriés.</span><span class="sxs-lookup"><span data-stu-id="7085f-108">You can then create maintenance downtime registrations on the **Maintenance downtime** page and add the relevant maintenance downtime reason codes.</span></span>

## <a name="create-maintenance-downtime-reason-codes"></a><span data-ttu-id="7085f-109">Créer des codes motif de temps d'arrêt pour maintenance</span><span class="sxs-lookup"><span data-stu-id="7085f-109">Create maintenance downtime reason codes</span></span>

1. <span data-ttu-id="7085f-110">Sélectionnez **Gestion des actifs** > **Configuration** > **Ordres de travail** > **Codes motif de temps d'arrêt pour maintenance**.</span><span class="sxs-lookup"><span data-stu-id="7085f-110">Select **Asset management** > **Setup** > **Work orders** > **Maintenance downtime reason codes**.</span></span>

2. <span data-ttu-id="7085f-111">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="7085f-111">Select **New**.</span></span>

3. <span data-ttu-id="7085f-112">Dans le champ **Code motif de temps d'arrêt pour maintenance**, entrez un ID de code motif de temps d'arrêt pour maintenance.</span><span class="sxs-lookup"><span data-stu-id="7085f-112">In the **Maintenance downtime reason code** field, enter an ID for the maintenance downtime reason code.</span></span>

4. <span data-ttu-id="7085f-113">Dans le champ **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="7085f-113">In the **Name** field, enter a name.</span></span>

5. <span data-ttu-id="7085f-114">Activez la case à cocher **Les indicateurs de performance clés incluent** si le code motif doit être inclus dans les calculs des indicateurs de performance clés pour l'actif.</span><span class="sxs-lookup"><span data-stu-id="7085f-114">Select the **KPI include** check box if the reason code should be included in calculations of key performance indicators (KPIs) for the asset.</span></span> <span data-ttu-id="7085f-115">En général, les arrêts de production planifiés ne doivent pas être inclus dans les calculs des indicateurs de performance clés, car ils n'affectent pas les performances prévues.</span><span class="sxs-lookup"><span data-stu-id="7085f-115">In general, planned production stops should not be included in KPI calculations, because they don't affect expected performance.</span></span>

6. <span data-ttu-id="7085f-116">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="7085f-116">Select **Save**.</span></span>

<span data-ttu-id="7085f-117">L'illustration ci-dessous présente un exemple de la page **Codes motif des temps d'arrêt pour maintenance**.</span><span class="sxs-lookup"><span data-stu-id="7085f-117">The illustration below shows an example of the **Maintenance downtime reason codes** page.</span></span>

![Figure 1](media/15-work-orders.png)

<span data-ttu-id="7085f-119">Après avoir créé les codes motif de temps d'arrêt pour maintenance que vous souhaitez utiliser, vous pouvez créer les enregistrements des temps d'arrêt pour maintenance pour les ordres de travail et les actifs.</span><span class="sxs-lookup"><span data-stu-id="7085f-119">After you've created the maintenance downtime reason codes that you want to use, you can create maintenance downtime registrations for work orders and assets.</span></span>


## <a name="create-maintenance-downtime-registrations"></a><span data-ttu-id="7085f-120">Créer des enregistrements de temps d'arrêt pour maintenance</span><span class="sxs-lookup"><span data-stu-id="7085f-120">Create maintenance downtime registrations</span></span>

1. <span data-ttu-id="7085f-121">Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="7085f-121">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="7085f-122">Sélectionnez l'ordre de travail puis, sous l'onglet **Ordre de travail**, dans le groupe **Actif**, sélectionnez **Temps d'arrêt pour maintenance**.</span><span class="sxs-lookup"><span data-stu-id="7085f-122">Select the work order, and then, on the **Work order** tab, in the **Asset** group, select **Maintenance downtime**.</span></span>

3. <span data-ttu-id="7085f-123">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="7085f-123">Select **New**.</span></span>

4. <span data-ttu-id="7085f-124">Dans les champs **De** et **À**, définissez l'intervalle de date et d'heure pour l'enregistrement du temps d'arrêt pour maintenance.</span><span class="sxs-lookup"><span data-stu-id="7085f-124">In the **From** and **To** fields, define the date and time interval for the maintenance downtime registration.</span></span>

>[!NOTE]
><span data-ttu-id="7085f-125">Lorsque vous quittez le champ **À**, la durée en heures est automatiquement insérée dans le champ **Durée**.</span><span class="sxs-lookup"><span data-stu-id="7085f-125">When you leave the **To** field, the duration in hours is automatically inserted in the **Duration** field.</span></span>

5. <span data-ttu-id="7085f-126">Dans le champ **Code motif de temps d'arrêt pour maintenance**, sélectionnez un code motif.</span><span class="sxs-lookup"><span data-stu-id="7085f-126">In the **maintenance downtime reason code** field, select a reason code.</span></span>

6. <span data-ttu-id="7085f-127">Répétez les étapes 3 à 5 pour ajouter d'autres inscriptions.</span><span class="sxs-lookup"><span data-stu-id="7085f-127">Repeat steps 3 through 5 to add more registrations.</span></span>

7. <span data-ttu-id="7085f-128">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="7085f-128">Select **Save**.</span></span>

<span data-ttu-id="7085f-129">L'illustration ci-dessous présente un exemple d'inscription de temps d'arrêt pour maintenance.</span><span class="sxs-lookup"><span data-stu-id="7085f-129">The illustration below shows an example of maintenance downtime registration.</span></span>

![Figure 2](media/16-work-orders.png)

<span data-ttu-id="7085f-131">Le calendrier qui est utilisé pour calculer un enregistrement de temps d'arrêt pour maintenance dépend de votre sélection dans la configuration des actifs et des paramètres.</span><span class="sxs-lookup"><span data-stu-id="7085f-131">The calendar that is used to calculate a maintenance downtime registration depends on your selection in the setup of assets and parameters.</span></span> <span data-ttu-id="7085f-132">Si une ressource est sélectionnée sur un actif dans le champ **Ressource** de l'organisateur **Immobilisation** de la page **Tous les actifs**, la configuration du calendrier pour le groupe de ressources associé est utilisé, comme indiqué sur l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="7085f-132">If a resource is selected on an asset in the **Resource** field on the **Fixed asset** FastTab of the **All assets** page, the calendar that is set up for the associated resource group is used, as shown in the following illustration.</span></span>

![Figure 3](media/17-work-orders.png)

<span data-ttu-id="7085f-134">Si aucune ressource n'est sélectionnée sur l'actif, le calendrier standard sélectionné sur la page **Paramètres de gestion des actifs** est utilisé, comme indiqué sur l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="7085f-134">If no resource is selected on the asset, the standard calendar that is selected on the **Asset management parameters** page is used, as shown in the following illustration.</span></span>

![Figure 4](media/18-work-orders.png)

<span data-ttu-id="7085f-136">Pour afficher une vue d'ensemble de tous les enregistrements de temps d'arrêt pour maintenance, cliquez sur **Gestion des actifs** > **Recherches** > **Temps d'arrêt pour maintenance**.</span><span class="sxs-lookup"><span data-stu-id="7085f-136">To see an overview of all maintenance downtime registrations, click **Asset management** > **Inquiries** > **Maintenance downtime**.</span></span>

>[!NOTE]
><span data-ttu-id="7085f-137">Tous les calendriers qui sont utilisés dans le module **Gestion des actifs** sont configurés dans **Administration d'organisation** > **Configuration** > **Calendriers** > **Calendriers**.</span><span class="sxs-lookup"><span data-stu-id="7085f-137">All calendars that are used in the **Asset Management** module are set up in **Organization administration** > **Setup** > **Calendars** > **Calendars**.</span></span>

