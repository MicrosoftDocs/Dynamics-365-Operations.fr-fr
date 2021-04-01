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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e4f622cda62cad13a8146cbc26bc2e5f1a45222
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5261187"
---
# <a name="maintenance-request-types"></a><span data-ttu-id="33ebe-103">Types de demandes de maintenance</span><span class="sxs-lookup"><span data-stu-id="33ebe-103">Maintenance request types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="33ebe-104">Les types de demandes de maintenance permettent de classer par catégorie les demandes de maintenance.</span><span class="sxs-lookup"><span data-stu-id="33ebe-104">Maintenance request types are used to categorize maintenance requests.</span></span> <span data-ttu-id="33ebe-105">Par exemple, des types de demandes de maintenance peuvent être associés à la maintenance préventive et à la maintenance corrective.</span><span class="sxs-lookup"><span data-stu-id="33ebe-105">For example, you might have maintenance request types that are related to preventive maintenance and corrective maintenance.</span></span> <span data-ttu-id="33ebe-106">Un type de demande de maintenance spécial peut être utilisé pour gérer la réparation des actifs (réparation au dépôt).</span><span class="sxs-lookup"><span data-stu-id="33ebe-106">Or you might have a special maintenance request type that is used to manage repair of assets (depot repair).</span></span>

<span data-ttu-id="33ebe-107">Un type de demande de maintenance définit l’affiliation à un groupe d’états du cycle de vie de la demande de maintenance (modèle de cycle de vie de maintenance).</span><span class="sxs-lookup"><span data-stu-id="33ebe-107">A maintenance request type defines the affiliation with a maintenance request lifecycle state group (maintenance lifecycle model).</span></span> <span data-ttu-id="33ebe-108">Les modèles de cycle de vie de la demande de maintenance définissent les états du cycle de vie qui peuvent être définis pour une demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="33ebe-108">Maintenance request lifecycle models define the lifecycle states that can be set for a maintenance request.</span></span> <span data-ttu-id="33ebe-109">(**Créé**, **Actif** et **Terminé** sont des exemples d’états du cycle de vie de la demande de maintenance).</span><span class="sxs-lookup"><span data-stu-id="33ebe-109">(Examples of maintenance request lifecycle states include **Created**, **Active**, and **Ended**.)</span></span>

1. <span data-ttu-id="33ebe-110">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Demandes de maintenance** \> **Types de demandes de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="33ebe-110">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Maintenance request types**.</span></span>
2. <span data-ttu-id="33ebe-111">Sélectionnez **Nouveau** pour créer un type de demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="33ebe-111">Select **New** to create a maintenance request type.</span></span>
3. <span data-ttu-id="33ebe-112">Dans le champ **Type de demande de maintenance**, entrez un ID pour le type de demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="33ebe-112">In the **Maintenance request type** field, enter an ID for the maintenance request type.</span></span>
4. <span data-ttu-id="33ebe-113">Dans le champ **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="33ebe-113">In the **Name** field, enter a name.</span></span>
5. <span data-ttu-id="33ebe-114">Dans le raccourci **Général**, dans le champ **Modèle de cycle de vie des demandes de maintenance**, sélectionnez un modèle de cycle de vie de la demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="33ebe-114">On the **General** FastTab, in the **Maintenance request lifecycle model** field, select a maintenance request lifecycle model.</span></span>
6. <span data-ttu-id="33ebe-115">Dans le champ **Type d’ordre de travail**, sélectionnez un type d’ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="33ebe-115">In the **Work order type** field, select a work order type.</span></span> <span data-ttu-id="33ebe-116">Lorsqu’une demande de maintenance est convertie en bon de travail, le type d’ordre de travail associé au type de demande de maintenance est automatiquement attribué à l’ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="33ebe-116">When a maintenance request is converted to a work order, the work order automatically gets the work order type that is related to the maintenance request type.</span></span>

<span data-ttu-id="33ebe-117">L’illustration suivante présente un exemple de la page **Types de demandes de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="33ebe-117">The following illustration shows an example of the **Maintenance request types** page.</span></span>

![Page Types de demandes de maintenance](media/07-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]