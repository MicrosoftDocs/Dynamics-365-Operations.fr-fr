---
title: Temps d'arrêt pour maintenance
description: Cette rubrique décrit le temps d'arrêt pour maintenance dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cc79dc1b5911679586fa560142ada5add1a881d2
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918242"
---
# <a name="maintenance-downtime"></a><span data-ttu-id="b7800-103">Temps d'arrêt pour maintenance</span><span class="sxs-lookup"><span data-stu-id="b7800-103">Maintenance downtime</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="b7800-104">Vous pouvez créer des enregistrements de temps d'arrêt pour maintenance sur l'actif sélectionné sur un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="b7800-104">You can create maintenance downtime registrations on the asset selected on a work order.</span></span> <span data-ttu-id="b7800-105">Cela est utile si vous souhaitez enregistrer le temps d'arrêt pour maintenance sur une ou plusieurs machines dans la zone de production.</span><span class="sxs-lookup"><span data-stu-id="b7800-105">This is useful if you want to register maintenance downtime on one or more machines in the production area.</span></span> <span data-ttu-id="b7800-106">Premièrement, vous pouvez créer des codes motif de temps d'arrêt pour maintenance que vous souhaitez utiliser, par exemple, la répartition et l'arrêt planifié.</span><span class="sxs-lookup"><span data-stu-id="b7800-106">First, you create the maintenance downtime reason codes that you want to use, for example, breakdown and planned stop.</span></span> <span data-ttu-id="b7800-107">Cela est effectué dans **Codes motif de temps d'arrêt pour maintenance**.</span><span class="sxs-lookup"><span data-stu-id="b7800-107">This is done in **Maintenance downtime reason codes**.</span></span> <span data-ttu-id="b7800-108">Ensuite, vous pouvez créer des enregistrements de temps d'arrêt pour maintenance dans **Temps d'arrêt pour maintenance** et ajouter des codes motif appropriés.</span><span class="sxs-lookup"><span data-stu-id="b7800-108">Next, you can create maintenance downtime registrations in **Maintenance downtime** and add the relevant reason codes.</span></span>

## <a name="create-maintenance-downtime-reason-codes"></a><span data-ttu-id="b7800-109">Créer des codes motif de temps d'arrêt pour maintenance</span><span class="sxs-lookup"><span data-stu-id="b7800-109">Create maintenance downtime reason codes</span></span>

1. <span data-ttu-id="b7800-110">Cliquez sur **Gestion des actifs** > **Configuration** > **Ordres de travail** > **Codes motif de temps d'arrêt pour maintenance**.</span><span class="sxs-lookup"><span data-stu-id="b7800-110">Click **Asset management** > **Setup** > **Work orders** > **Maintenance downtime reason codes**.</span></span>

2. <span data-ttu-id="b7800-111">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b7800-111">Click **New**.</span></span>

3. <span data-ttu-id="b7800-112">Insérez un ID dans le champ **Code motif de temps d'arrêt pour maintenance**.</span><span class="sxs-lookup"><span data-stu-id="b7800-112">Insert an ID in the **Maintenance downtime reason code** field.</span></span>

4. <span data-ttu-id="b7800-113">Insérez un nom pour le code motif dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="b7800-113">Insert a name for the reason code in the **Name** field.</span></span>

5. <span data-ttu-id="b7800-114">Sélectionnez la case à cocher **Les indicateurs de performance clés incluent** si le code motif doit être inclus dans les calculs des indicateurs de performance clés des actifs.</span><span class="sxs-lookup"><span data-stu-id="b7800-114">Select the **KPI include** check box if the reason code should be included in asset KPI calculations.</span></span> <span data-ttu-id="b7800-115">En général, les arrêts de production planifiés ne doivent pas être inclus dans les calculs des indicateurs de performance clés puisqu'ils n'ont pas d'impact sur les performances prévues.</span><span class="sxs-lookup"><span data-stu-id="b7800-115">Generally, planned production stops should not be included in KPI calculations as they do not impact expected performance.</span></span>

6. <span data-ttu-id="b7800-116">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b7800-116">Click **Save**.</span></span>

![Figure 1](media/15-work-orders.png)


<span data-ttu-id="b7800-118">Lorsque vous avez créé les codes motif de temps d'arrêt pour maintenance que vous souhaitez utiliser, vous pouvez créer les enregistrements des temps d'arrêt pour maintenance pour les ordres de travail et les actifs.</span><span class="sxs-lookup"><span data-stu-id="b7800-118">When you have created the maintenance downtime reason codes you want to use, you can create maintenance downtime registrations for work orders and assets.</span></span>


## <a name="create-maintenance-downtime-registrations"></a><span data-ttu-id="b7800-119">Créer des enregistrements de temps d'arrêt pour maintenance</span><span class="sxs-lookup"><span data-stu-id="b7800-119">Create maintenance downtime registrations</span></span>

1. <span data-ttu-id="b7800-120">Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="b7800-120">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="b7800-121">Sélectionnez l'ordre de travail et cliquez sur **Temps d'arrêt pour maintenance**.</span><span class="sxs-lookup"><span data-stu-id="b7800-121">Select the work order and click **Maintenance downtime**.</span></span>

3. <span data-ttu-id="b7800-122">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b7800-122">Click **New**.</span></span>

4. <span data-ttu-id="b7800-123">Insérez l'intervalle de date pour l'enregistrement du temps d'arrêt pour maintenance dans les champs **De** et **À**.</span><span class="sxs-lookup"><span data-stu-id="b7800-123">Insert date and time interval for the maintenance downtime registration in the **From** and **To** fields.</span></span>

5. <span data-ttu-id="b7800-124">Lorsque vous quittez le champ **À**, la durée en heures est automatiquement insérée dans le champ **Durée**.</span><span class="sxs-lookup"><span data-stu-id="b7800-124">When you leave the **To** field, the duration in hours is automatically inserted in the **Duration** field.</span></span>

6. <span data-ttu-id="b7800-125">Sélectionnez un code motif dans le champ **Code motif de temps d'arrêt pour maintenance**.</span><span class="sxs-lookup"><span data-stu-id="b7800-125">Select a reason code in the **maintenance downtime reason code** field.</span></span>

7. <span data-ttu-id="b7800-126">Répétez les étapes 3-6 si vous souhaitez ajouter plus d'enregistrements.</span><span class="sxs-lookup"><span data-stu-id="b7800-126">Repeat steps 3-6 if you want to add more registrations.</span></span>

8. <span data-ttu-id="b7800-127">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b7800-127">Click **Save**.</span></span>


![Figure 2](media/16-work-orders.png)


<span data-ttu-id="b7800-129">Le calendrier utilisé pour calculer un enregistrement de temps d'arrêt pour maintenance dépend de votre sélection dans la configuration des actifs et des paramètres.</span><span class="sxs-lookup"><span data-stu-id="b7800-129">The calendar used to calculate a maintenance downtime registration depends on your selection in the setup of assets and parameters.</span></span> <span data-ttu-id="b7800-130">Si une ressource est sélectionnée sur un actif dans le champ **Tous les actifs** >  organisateur **Immobilisation** > **Ressource**, la configuration du calendrier pour le groupe de ressources associé est utilisé, comme indiqué sur la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="b7800-130">If a resource is selected on an asset in **All assets** > **Fixed asset** FastTab > **Resource** field, the calendar set up for the associated resource group is used, as shown in the following figure.</span></span>

![Figure 3](media/17-work-orders.png)


<span data-ttu-id="b7800-132">Si aucune ressource n'est sélectionnée sur l'actif, le calendrier standard sélectionné dans **Paramètres de gestion des actifs** est utilisé, comme indiqué sur la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="b7800-132">If no resource is selected on the asset, the standard calendar selected in **Asset management parameters** is used, as shown in the following figure.</span></span>

![Figure 4](media/18-work-orders.png)


<span data-ttu-id="b7800-134">Cliquez sur **Gestion des actifs d'entreprise** > **Recherches** > **Temps d'arrêt pour maintenance** pour afficher une vue d'ensemble de tous les enregistrements de temps d'arrêt pour maintenance.</span><span class="sxs-lookup"><span data-stu-id="b7800-134">Click **Enterprise asset management** > **Inquiries** > **Maintenance downtime** to see an overview of all maintenance downtime registrations.</span></span>

>[!NOTE]
><span data-ttu-id="b7800-135">Tous les calendriers utilisés dans le module **Gestion des actifs** sont configurés dans **Administration d'organisation** > **Configuration** > **Calendriers** > **Calendriers**.</span><span class="sxs-lookup"><span data-stu-id="b7800-135">All calendars used in the **Asset Management** module are set up in **Organization administration** > **Setup** > **Calendars** > **Calendars**.</span></span>

