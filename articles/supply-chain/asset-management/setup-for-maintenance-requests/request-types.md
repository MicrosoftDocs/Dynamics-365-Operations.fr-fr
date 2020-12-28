---
title: Types de demandes de maintenance
description: Cette rubrique explique comment paramétrer des types de demandes de maintenance dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
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
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d353f084e0d3e056f1b5ff5af6437ba211def8ec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428000"
---
# <a name="maintenance-request-types"></a><span data-ttu-id="3b47c-103">Types de demandes de maintenance</span><span class="sxs-lookup"><span data-stu-id="3b47c-103">Maintenance request types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="3b47c-104">Les types de demandes de maintenance permettent de classer par catégorie les demandes de maintenance.</span><span class="sxs-lookup"><span data-stu-id="3b47c-104">Maintenance request types are used to categorize maintenance requests.</span></span> <span data-ttu-id="3b47c-105">Par exemple, des types de demandes de maintenance peuvent être associés à la maintenance préventive et à la maintenance corrective.</span><span class="sxs-lookup"><span data-stu-id="3b47c-105">For example, you might have maintenance request types that are related to preventive maintenance and corrective maintenance.</span></span> <span data-ttu-id="3b47c-106">Un type de demande de maintenance spécial peut être utilisé pour gérer la réparation des actifs (réparation au dépôt).</span><span class="sxs-lookup"><span data-stu-id="3b47c-106">Or you might have a special maintenance request type that is used to manage repair of assets (depot repair).</span></span>

<span data-ttu-id="3b47c-107">Un type de demande de maintenance définit l'affiliation à un groupe d'états du cycle de vie de la demande de maintenance (modèle de cycle de vie de maintenance).</span><span class="sxs-lookup"><span data-stu-id="3b47c-107">A maintenance request type defines the affiliation with a maintenance request lifecycle state group (maintenance lifecycle model).</span></span> <span data-ttu-id="3b47c-108">Les modèles de cycle de vie de la demande de maintenance définissent les états du cycle de vie qui peuvent être définis pour une demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="3b47c-108">Maintenance request lifecycle models define the lifecycle states that can be set for a maintenance request.</span></span> <span data-ttu-id="3b47c-109">(**Créé**, **Actif** et **Terminé** sont des exemples d'états du cycle de vie de la demande de maintenance).</span><span class="sxs-lookup"><span data-stu-id="3b47c-109">(Examples of maintenance request lifecycle states include **Created**, **Active**, and **Ended**.)</span></span>

1. <span data-ttu-id="3b47c-110">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Demandes de maintenance** \> **Types de demandes de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="3b47c-110">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Maintenance request types**.</span></span>
2. <span data-ttu-id="3b47c-111">Sélectionnez **Nouveau** pour créer un type de demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="3b47c-111">Select **New** to create a maintenance request type.</span></span>
3. <span data-ttu-id="3b47c-112">Dans le champ **Type de demande de maintenance**, entrez un ID pour le type de demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="3b47c-112">In the **Maintenance request type** field, enter an ID for the maintenance request type.</span></span>
4. <span data-ttu-id="3b47c-113">Dans le champ **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="3b47c-113">In the **Name** field, enter a name.</span></span>
5. <span data-ttu-id="3b47c-114">Dans le raccourci **Général**, dans le champ **Modèle de cycle de vie des demandes de maintenance**, sélectionnez un modèle de cycle de vie de la demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="3b47c-114">On the **General** FastTab, in the **Maintenance request lifecycle model** field, select a maintenance request lifecycle model.</span></span>
6. <span data-ttu-id="3b47c-115">Dans le champ **Type d'ordre de travail**, sélectionnez un type d'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="3b47c-115">In the **Work order type** field, select a work order type.</span></span> <span data-ttu-id="3b47c-116">Lorsqu'une demande de maintenance est convertie en bon de travail, le type d'ordre de travail associé au type de demande de maintenance est automatiquement attribué à l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="3b47c-116">When a maintenance request is converted to a work order, the work order automatically gets the work order type that is related to the maintenance request type.</span></span>

<span data-ttu-id="3b47c-117">L'illustration suivante présente un exemple de la page **Types de demandes de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="3b47c-117">The following illustration shows an example of the **Maintenance request types** page.</span></span>

![Page Types de demandes de maintenance](media/07-setup-for-requests.png)
