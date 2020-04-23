---
title: Actifs et ordres de travail
description: Cette rubrique décrit les actifs et les ordres de travail dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c2500a695fcffe0d60ac13b1b74cda4322b0e14
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206885"
---
# <a name="assets-and-work-orders"></a><span data-ttu-id="ca5b4-103">Actifs et ordres de travail</span><span class="sxs-lookup"><span data-stu-id="ca5b4-103">Assets and work orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="ca5b4-104">Cette rubrique décrit les actifs et les ordres de travail dans le module Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-104">This topic describes assets and work orders in Asset Management.</span></span> <span data-ttu-id="ca5b4-105">Les actifs et les ordres de travail sont les parties centrales du module Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-105">Assets and work orders are the central parts of Asset Management.</span></span> <span data-ttu-id="ca5b4-106">Un *actif* est une machine ou une pièce de machine qui nécessite une maintenance et un service continus.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-106">An *asset* is a machine or machine part that requires continuous maintenance and service.</span></span> <span data-ttu-id="ca5b4-107">Les actifs peuvent être créés dans une structure hiérarchique, et ils peuvent être associés à des postes techniques.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-107">Assets can be created in a hierarchical structure, and they can be related to functional locations.</span></span> <span data-ttu-id="ca5b4-108">Les tâches de maintenance peuvent être planifiées à tous les niveaux de la structure de l'actif.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-108">Maintenance jobs can be planned at all levels in the asset structure.</span></span>

<span data-ttu-id="ca5b4-109">Diverses données, telles que les informations sur le produit et la spécification de l'actif, ainsi que les plans de maintenance requis sont paramétrés sur chaque actif.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-109">Various data, such as product information and asset specification, and required maintenance plans are set up on each asset.</span></span> <span data-ttu-id="ca5b4-110">L'illustration suivante donne une vue d'ensemble des données d'actif et de l'affiliation des actifs aux types de tâche.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-110">The following illustration shows an overview of asset data and the affiliation of assets to job types.</span></span> <span data-ttu-id="ca5b4-111">Le texte en rouge est utilisé pour les exemples illustrant l'héritage et les dépendances.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-111">Red text is used for examples that show inheritance and dependencies.</span></span>

![Diagramme affichant des données d'actifs liées aux types de tâches](media/05-overview-image.png)

<span data-ttu-id="ca5b4-113">Chaque ordre de travail a un type d'ordre de travail, comme la maintenance préventive, la maintenance corrective ou l'inspection.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-113">Every work order has a work order type, such preventive maintenance, corrective maintenance, or inspection.</span></span> <span data-ttu-id="ca5b4-114">L'ordre de travail contient une ou plusieurs tâches d'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-114">The work order contains one or more work order jobs.</span></span> <span data-ttu-id="ca5b4-115">Chaque tâche d'ordre de travail définit une tâche qui doit être réalisée sur un actif et un type de tâche associé.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-115">Every work order job defines a job that must be performed on an asset and a related job type.</span></span> <span data-ttu-id="ca5b4-116">La révision à 10 000 km, 50 000 km et 1 an et l'inspection de sécurité sont des exemples de types de tâche associés.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-116">Examples of related job types include 10,000 km, 50,000 km, 1-year overhaul, and safety inspection.</span></span> <span data-ttu-id="ca5b4-117">Un ordre de travail peut être associé à plusieurs actifs.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-117">One work order can be related to multiple assets.</span></span>

<span data-ttu-id="ca5b4-118">L'illustration suivante donne une vue d'ensemble des principales données d'un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-118">The following illustration shows an overview of the key data in a work order.</span></span>

![Diagramme affichant des données clés dans un ordre de travail](media/06-overview-image.png)

<span data-ttu-id="ca5b4-120">Un ordre de travail peut être associé à un autre ordre de travail, et les types de tâche peuvent contenir les tâches suivantes qui créent un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-120">A work order can be related to another work order, and job types can contain succeeding jobs that create a work order.</span></span> <span data-ttu-id="ca5b4-121">En général, il n'existe aucune dépendance entre les ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-121">In general, there are no dependencies between work orders.</span></span> <span data-ttu-id="ca5b4-122">Par conséquent, ils peuvent modifier leur état du cycle de vie et peuvent être planifiés indépendamment les uns des autres.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-122">Therefore, they can change their work order lifecycle state and can be scheduled independently of each other.</span></span>

<span data-ttu-id="ca5b4-123">Il est possible de créer des ordres de travail de différentes manières qui sont associés à la maintenance corrective, préventive ou réactive.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-123">Work orders can be created in various ways that are related to corrective, preventive, or reactive maintenance.</span></span> <span data-ttu-id="ca5b4-124">Vous pouvez également créer des ordres de travail manuellement.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-124">You can also create work orders manually.</span></span> <span data-ttu-id="ca5b4-125">L'illustration suivante donne une vue d'ensemble du processus de création automatique ou manuelle des ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-125">The following illustration shows an overview of the process for automatic or manual creation of work orders.</span></span>

![Diagramme affichant la création automatique ou manuelle des ordres de travail](media/07-overview-image.png)

<span data-ttu-id="ca5b4-127">Plusieurs étapes doivent être effectuées lorsque vous souhaitez planifier et exécuter une tâche de maintenance sur un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-127">Several steps must be completed when you want to schedule and run a maintenance job on a work order.</span></span> <span data-ttu-id="ca5b4-128">L'illustration suivante donne une vue d'ensemble du traitement d'un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-128">The following illustration shows an overview of the processing for a work order.</span></span>

![Diagramme affichant une vue d'ensemble d'un ordre de travail](media/08-overview-image.png)

> [!NOTE]
> <span data-ttu-id="ca5b4-130">En général, lorsque vous travaillez dans Dynamics 365 Supply Chain Management et le module **Gestion des actifs**, vous sélectionnez **Nouveau** pour créer un enregistrement, vous sélectionnez **Modifier** pour mettre à jour un enregistrement existant et vous sélectionnez **Enregistrer** pour enregistrer des données nouvelles ou modifiées.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-130">In general, when you work in Dynamics 365 Supply Chain Management and the **Asset Management** module, you select **New** to create a new record, you select **Edit** to update an existing record, and you select **Save** to save new or edited data.</span></span>
