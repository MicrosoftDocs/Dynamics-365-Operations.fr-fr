---
title: États de demande de maintenance
description: Cette rubrique explique comment créer des états de demande de maintenance dans Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5abb62e7f92f62d4635309625d765e1c081052eb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427946"
---
# <a name="maintenance-request-reports"></a><span data-ttu-id="9e8e0-103">États de demande de maintenance</span><span class="sxs-lookup"><span data-stu-id="9e8e0-103">Maintenance request reports</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="9e8e0-104">Dans Gestion des actifs, vous pouvez générer deux états associés aux demandes de maintenance.</span><span class="sxs-lookup"><span data-stu-id="9e8e0-104">In Asset Management, you can generate two reports that are related to maintenance requests.</span></span> <span data-ttu-id="9e8e0-105">Un état affiche des détails et l'autre état fournit une liste qui peut être utilisée pour la planification et le suivi.</span><span class="sxs-lookup"><span data-stu-id="9e8e0-105">One report shows details, and the other report provides a list that can be used for planning and follow-up.</span></span>

## <a name="create-a-maintenance-request-details-report"></a><span data-ttu-id="9e8e0-106">Créer un état des détails de la demande de maintenance</span><span class="sxs-lookup"><span data-stu-id="9e8e0-106">Create a Maintenance request details report</span></span>

<span data-ttu-id="9e8e0-107">L'état **Détails de la demande de maintenance** affiche différentes informations liées à la demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="9e8e0-107">The **Maintenance request details** report shows various information that is related to maintenance requests.</span></span>

1. <span data-ttu-id="9e8e0-108">Sélectionnez **Gestion des actifs** \> **États** \> **Demandes de maintenance** \> **Détails de la demande de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="9e8e0-108">Select **Asset management** \> **Reports** \> **Maintenance requests** \> **Maintenance request details**.</span></span>
2. <span data-ttu-id="9e8e0-109">Dans l'organisateur **Enregistrements à inclure**, vous pouvez sélectionner des demandes de maintenance spécifiques à inclure dans l'état.</span><span class="sxs-lookup"><span data-stu-id="9e8e0-109">On the **Records to include** FastTab, you can select specific maintenance requests to include on the report.</span></span>
3. <span data-ttu-id="9e8e0-110">Dans l'organisateur **Exécuter en arrière-plan**, vous pouvez paramétrer la génération d'état comme un traitement par lots, comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="9e8e0-110">On the **Run in the background** FastTab, you can set up report generation as a batch job, as you require.</span></span>
4. <span data-ttu-id="9e8e0-111">Sélectionnez **OK** pour générer l'état.</span><span class="sxs-lookup"><span data-stu-id="9e8e0-111">Select **OK** to generate the report.</span></span>

<span data-ttu-id="9e8e0-112">L'illustration suivante présente un exemple de l'état **Détails de la demande de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="9e8e0-112">The following illustration shows an example of the **Maintenance request details** report.</span></span>

![État Détails de la demande de maintenance](media/09-manage-maintenance-requests.png)

## <a name="create-a-maintenance-request-list-report"></a><span data-ttu-id="9e8e0-114">Créer un état de la liste des demandes de maintenance</span><span class="sxs-lookup"><span data-stu-id="9e8e0-114">Create a Maintenance request list report</span></span>

<span data-ttu-id="9e8e0-115">L'état **Liste des demandes de maintenance** affiche une liste de toutes les demandes de maintenance du même type.</span><span class="sxs-lookup"><span data-stu-id="9e8e0-115">The **Maintenance request list** report shows a list of all maintenance requests of the same request type.</span></span>

1. <span data-ttu-id="9e8e0-116">Sélectionnez **Gestion des actifs** \> **États** \> **Demandes de maintenance** \> **Liste des demandes de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="9e8e0-116">Select **Asset management** \> **Reports** \> **Maintenance requests** \> **Maintenance request list**.</span></span>
2. <span data-ttu-id="9e8e0-117">Dans l'organisateur **Enregistrements à inclure**, vous pouvez effectuer des sélections pour définir les demandes de maintenance à inclure dans l'état.</span><span class="sxs-lookup"><span data-stu-id="9e8e0-117">On the **Records to include** FastTab, you can make selections to define which maintenance requests are included on the report.</span></span>
3. <span data-ttu-id="9e8e0-118">Dans l'organisateur **Exécuter en arrière-plan**, vous pouvez paramétrer la génération d'état comme un traitement par lots, comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="9e8e0-118">On the **Run in the background** FastTab, you can set up report generation as a batch job, as you require.</span></span>
4. <span data-ttu-id="9e8e0-119">Sélectionnez **OK** pour générer l'état.</span><span class="sxs-lookup"><span data-stu-id="9e8e0-119">Select **OK** to generate the report.</span></span>

<span data-ttu-id="9e8e0-120">L'illustration suivante présente un exemple de l'état **Liste des demandes de maintenance** pour toutes les demandes de maintenance actives.</span><span class="sxs-lookup"><span data-stu-id="9e8e0-120">The following illustration shows an example of the **Maintenance request list** report for all active maintenance requests.</span></span>

![États Liste des demandes de maintenance](media/10-manage-maintenance-requests.png)
