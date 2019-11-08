---
title: Actifs entrants et sortants
description: Cette rubrique explique comment enregistrer des actifs entrants et sortants dans Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bb318c24424c291f08ba7527b2258c0da4cba9a8
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571666"
---
# <a name="inbound-and-outbound-assets"></a><span data-ttu-id="b12e1-103">Actifs entrants et sortants</span><span class="sxs-lookup"><span data-stu-id="b12e1-103">Inbound and outbound assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="b12e1-104">Si votre société effectue des tâches de réparation ou de maintenance sur les actifs reçus d'autres emplacements ou clients, Gestion des actifs peut suivre les actifs entrants vers votre société et les actifs sortants qui sont retournées.</span><span class="sxs-lookup"><span data-stu-id="b12e1-104">If your company does repair jobs or maintenance jobs on assets that are received from other locations or customers, Asset Management can track both inbound assets that are on their way to your company and outbound assets that are being returned.</span></span>

> [!NOTE]
> <span data-ttu-id="b12e1-105">Si vous souhaitez utiliser des états du cycle de vie entrant et sortant pour gérer les actifs entrants et étant retournés, vous devez paramétrer des états de cycle de vie de demande de maintenance et des modèles de cycle de vie pour prendre en charge ces actions.</span><span class="sxs-lookup"><span data-stu-id="b12e1-105">If you want to use inbound and outbound lifecycle states to manage assets that are coming in and being returned, you must set up maintenance request lifecycle states and lifecycle models to support these actions.</span></span> <span data-ttu-id="b12e1-106">Pour plus d'informations, voir [Paramétrage des demandes de maintenance](../setup-for-maintenance-requests/requests.md).</span><span class="sxs-lookup"><span data-stu-id="b12e1-106">For more information, see [Setup for maintenance requests](../setup-for-maintenance-requests/requests.md).</span></span>

<span data-ttu-id="b12e1-107">Le paramétrage de Gestion des actifs détermine si vous pouvez utiliser les actifs entrants et sortants.</span><span class="sxs-lookup"><span data-stu-id="b12e1-107">The setup of Asset Management determines whether you can work with inbound and outbound assets.</span></span>

## <a name="register-assets-as-inbound"></a><span data-ttu-id="b12e1-108">Enregistrer les actifs comme entrants</span><span class="sxs-lookup"><span data-stu-id="b12e1-108">Register assets as inbound</span></span>

1. <span data-ttu-id="b12e1-109">Sélectionnez **Gestion des actifs** \> **Commun** \> **Demandes de maintenance** \> **Demandes de maintenance actives**.</span><span class="sxs-lookup"><span data-stu-id="b12e1-109">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="b12e1-110">Sélectionnez la demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="b12e1-110">Select the maintenance request.</span></span>
3. <span data-ttu-id="b12e1-111">Sélectionnez **Mettre à jour l'état de la demande de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="b12e1-111">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="b12e1-112">Sélectionnez **Entrant** (ou un autre état du cycle de vie créé pour les actifs entrants), puis **OK**.</span><span class="sxs-lookup"><span data-stu-id="b12e1-112">Select **Inbound** (or another lifecycle state that you've created for inbound assets), and then select **OK**.</span></span>

![Enregistrer les actifs comme entrants](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a><span data-ttu-id="b12e1-114">Enregistrer les actifs entrants comme reçus</span><span class="sxs-lookup"><span data-stu-id="b12e1-114">Register inbound assets as received</span></span>

1. <span data-ttu-id="b12e1-115">Sélectionnez **Gestion des actifs** \> **Commun** \> **Entrant/sortant** \> **Actifs entrants**.</span><span class="sxs-lookup"><span data-stu-id="b12e1-115">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Inbound assets**.</span></span>
2. <span data-ttu-id="b12e1-116">Sélectionnez l'actif ou la demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="b12e1-116">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="b12e1-117">Sélectionnez **Recevoir des actifs**.</span><span class="sxs-lookup"><span data-stu-id="b12e1-117">Select **Receive assets**.</span></span>
4. <span data-ttu-id="b12e1-118">Dans le champ **Reçu**, entrez de date et l'heure.</span><span class="sxs-lookup"><span data-stu-id="b12e1-118">In the **Received** field, enter the date and time.</span></span> <span data-ttu-id="b12e1-119">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b12e1-119">Then select **OK**.</span></span> <span data-ttu-id="b12e1-120">L'enregistrement est supprimé de la page de liste **Actifs entrants**.</span><span class="sxs-lookup"><span data-stu-id="b12e1-120">The record is removed from the **Inbound assets** list page.</span></span>

![Enregistrer les actifs entrants comme reçus](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a><span data-ttu-id="b12e1-122">Enregistrer les actifs comme sortants</span><span class="sxs-lookup"><span data-stu-id="b12e1-122">Register assets as outbound</span></span>

<span data-ttu-id="b12e1-123">Lorsque vous avez terminé la tâche de maintenance ou de réparation, vous pouvez enregistrer l'actif comme retourné.</span><span class="sxs-lookup"><span data-stu-id="b12e1-123">When you've completed the maintenance or repair job, you can register the asset as returned.</span></span>

1. <span data-ttu-id="b12e1-124">Sélectionnez **Gestion des actifs** \> **Commun** \> **Demandes de maintenance** \> **Demandes de maintenance actives**.</span><span class="sxs-lookup"><span data-stu-id="b12e1-124">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="b12e1-125">Sélectionnez la demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="b12e1-125">Select the maintenance request.</span></span>
3. <span data-ttu-id="b12e1-126">Sélectionnez **Mettre à jour l'état de la demande de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="b12e1-126">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="b12e1-127">Sélectionnez **Sortant** (ou un autre état du cycle de vie créé pour les actifs sortants), puis **OK**.</span><span class="sxs-lookup"><span data-stu-id="b12e1-127">Select **Outbound** (or another lifecycle state that you've created for outbound assets), and then select **OK**.</span></span>

## <a name="register-outbound-assets-as-delivered"></a><span data-ttu-id="b12e1-128">Enregistrer les actifs sortants comme livrés</span><span class="sxs-lookup"><span data-stu-id="b12e1-128">Register outbound assets as delivered</span></span>

1. <span data-ttu-id="b12e1-129">Sélectionnez **Gestion des actifs** \> **Commun** \> **Entrant/sortant** \> **Actifs sortants**.</span><span class="sxs-lookup"><span data-stu-id="b12e1-129">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Outbound assets**.</span></span>
2. <span data-ttu-id="b12e1-130">Sélectionnez l'actif ou la demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="b12e1-130">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="b12e1-131">Sélectionnez **Livrer les actifs**.</span><span class="sxs-lookup"><span data-stu-id="b12e1-131">Select **Deliver assets**.</span></span>
4. <span data-ttu-id="b12e1-132">Dans le champ **Livré**, entrez de date et l'heure.</span><span class="sxs-lookup"><span data-stu-id="b12e1-132">In the **Delivered** field, enter the date and time.</span></span> <span data-ttu-id="b12e1-133">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b12e1-133">Then select **OK**.</span></span> <span data-ttu-id="b12e1-134">L'enregistrement est supprimé de la page de liste **Actifs sortants**.</span><span class="sxs-lookup"><span data-stu-id="b12e1-134">The record is removed from the **Outbound assets** list page.</span></span>
