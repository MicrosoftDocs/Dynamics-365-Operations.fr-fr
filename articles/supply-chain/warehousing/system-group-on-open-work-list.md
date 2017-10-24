---
title: "Regroupement système sur une liste des travaux en cours"
description: "Cette rubrique décrit comment filtrer la liste des travaux en cours sur un appareil mobile."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0c68d544fec985f325e6472203533f23948cc9b4
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="system-grouping-on-an-open-work-list"></a><span data-ttu-id="507eb-103">Regroupement système sur une liste des travaux en cours</span><span class="sxs-lookup"><span data-stu-id="507eb-103">System grouping on an open work list</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="507eb-104">En utilisant un champ de regroupement système, vous pouvez filtrer la liste des travaux en cours sans avoir à modifier l'option de menu de l'appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="507eb-104">By using a system grouping field, you can filter an open work list without having to edit the mobile device menu item.</span></span>
<span data-ttu-id="507eb-105">Dans ce cas, le regroupement système permet de filtrer la liste des travaux dans un champ d'en-tête de travail unique.</span><span class="sxs-lookup"><span data-stu-id="507eb-105">Where it applies, system grouping works for filtering a work list on a single work header field.</span></span> <span data-ttu-id="507eb-106">Vous ne pouvez pas utiliser le regroupement système pour filtrer les champs au niveau de la ligne.</span><span class="sxs-lookup"><span data-stu-id="507eb-106">You cannot use system grouping to filter on line level fields.</span></span>

## <a name="set-up-system-grouping-on-an-open-work-list"></a><span data-ttu-id="507eb-107">Paramétrer le regroupement système sur une liste des travaux en cours</span><span class="sxs-lookup"><span data-stu-id="507eb-107">Set up system grouping on an open work list</span></span>
<span data-ttu-id="507eb-108">Procédez comme suit pour paramétrer le regroupement système sur une liste des travaux en cours.</span><span class="sxs-lookup"><span data-stu-id="507eb-108">Use these steps to set up system grouping on an open work list.</span></span>

-   <span data-ttu-id="507eb-109">À partir d'une option de menu de l'appareil mobile, sélectionnez **Mode : Indirect** et **Code d'activité : Afficher la liste des travaux en cours**.</span><span class="sxs-lookup"><span data-stu-id="507eb-109">From a mobile device menu item, select **Mode: Indirect** and **Activity Code: Display open work list**.</span></span> <span data-ttu-id="507eb-110">Les options suivantes deviennent disponibles.</span><span class="sxs-lookup"><span data-stu-id="507eb-110">The following options become available.</span></span> <span data-ttu-id="507eb-111">Ces options sont requises pour le regroupement système sur une liste des travaux en cours.</span><span class="sxs-lookup"><span data-stu-id="507eb-111">These options are required for system grouping on an open work list.</span></span> 

| <span data-ttu-id="507eb-112">Option</span><span class="sxs-lookup"><span data-stu-id="507eb-112">Option</span></span>        | <span data-ttu-id="507eb-113">Description</span><span class="sxs-lookup"><span data-stu-id="507eb-113">Description</span></span>   | 
| ------------- | ------------- |
| <span data-ttu-id="507eb-114">Autoriser le regroupement système</span><span class="sxs-lookup"><span data-stu-id="507eb-114">Allow system grouping</span></span>   | <span data-ttu-id="507eb-115">Active le regroupement système pour une option de menu de la liste des travaux en cours.</span><span class="sxs-lookup"><span data-stu-id="507eb-115">Enables system groping for a selected work list menu item.</span></span>| 
| <span data-ttu-id="507eb-116">Champ de regroupement système</span><span class="sxs-lookup"><span data-stu-id="507eb-116">System grouping field</span></span>   | <span data-ttu-id="507eb-117">Disponible uniquement si **Autoriser le travail système** est défini sur **Activé**.</span><span class="sxs-lookup"><span data-stu-id="507eb-117">Available only if **Allow system work** is set to **Yes**.</span></span> <span data-ttu-id="507eb-118">Sélectionnez le champ qui détermine comment le travail de prélèvement sera regroupé pour les collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="507eb-118">Select the field that determines how picking work will be grouped for workers.</span></span> <span data-ttu-id="507eb-119">Par exemple, si vous sélectionnez le champ **ShipmentId**, le collaborateur numérisera l'ID d'expédition pour regrouper les travaux de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="507eb-119">For example, if you select the **ShipmentId** field, the worker will scan the shipment ID to group the picking work.</span></span> <span data-ttu-id="507eb-120">Tout le travail d'expédition est alors affecté au collaborateur.</span><span class="sxs-lookup"><span data-stu-id="507eb-120">All work for the shipment is then assigned to the worker.</span></span> <span data-ttu-id="507eb-121">Ce champ nécessite la création d'une option de menu pour utiliser le travail existant qui est groupé par le système.</span><span class="sxs-lookup"><span data-stu-id="507eb-121">This field requires that you create a menu item to use existing work that is grouped by the system.</span></span> <span data-ttu-id="507eb-122">Utilisez le champ **Étiquette de regroupement système** pour indiquer au collaborateur quoi numériser.</span><span class="sxs-lookup"><span data-stu-id="507eb-122">Use the **System grouping label** field to inform the worker what to scan.</span></span> |
| <span data-ttu-id="507eb-123">Étiquette de regroupement système</span><span class="sxs-lookup"><span data-stu-id="507eb-123">System grouping label</span></span>   | <span data-ttu-id="507eb-124">Disponible uniquement si **Autoriser le travail système** est défini sur **Activé**.</span><span class="sxs-lookup"><span data-stu-id="507eb-124">Available only if **Allow system work** is set to **Yes**.</span></span> <span data-ttu-id="507eb-125">Entrez les informations qui indiqueront au collaborateur quoi numériser lorsque le travail de prélèvement est regroupé.</span><span class="sxs-lookup"><span data-stu-id="507eb-125">Enter information for the worker about what to scan when picking work is grouped.</span></span> <span data-ttu-id="507eb-126">Par exemple, si vous utilisez le champ **ShipmentId** pour grouper le travail de prélèvement par expédition, vous pouvez entrer l'ID d'expédition dans le champ.</span><span class="sxs-lookup"><span data-stu-id="507eb-126">For example, if you use the **ShipmentId** field to group picking work by shipment, you might enter Shipment ID in the field.</span></span> <span data-ttu-id="507eb-127">Ce champ nécessite la création d'une option de menu pour utiliser le travail existant qui est groupé par le système.</span><span class="sxs-lookup"><span data-stu-id="507eb-127">This field requires that you create a menu item to use existing work that is grouped by the system.</span></span> <span data-ttu-id="507eb-128">Vous devez également sélectionner le champ de regroupement dans le champ **Regroupement système**.</span><span class="sxs-lookup"><span data-stu-id="507eb-128">You must also select the field to group by in the **System grouping** field.</span></span>|

