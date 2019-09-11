---
title: Mise à jour manuelle des compteurs d'actifs
description: Cette rubrique décrit les mises à jour manuelles des compteurs d'actifs dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1e7c5ec288404c18b00f9dcd0e66f50744d0aa2f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875653"
---
# <a name="manual-update-of-asset-counters"></a><span data-ttu-id="1960c-103">Mise à jour manuelle des compteurs d'actifs</span><span class="sxs-lookup"><span data-stu-id="1960c-103">Manual update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="1960c-104">Les compteurs permettent de créer des enregistrements sur un actif concernant, par exemple, le nombre d'heures d'exploitation, ou les quantités produites.</span><span class="sxs-lookup"><span data-stu-id="1960c-104">Counters are used to create registrations on an asset regarding, for example, number of hours in operation, or the number of quantities produced.</span></span>

<span data-ttu-id="1960c-105">Si le type de compteur sélectionné pour un compteur est défini pour hériter des contre-valeurs (**Gestion des actifs** > **Paramétrage** > **Types d'actif** > **Compteurs** > **Général** organisateur > bouton à bascule **Hériter des contre-valeurs d'actifs** défini sur « Oui »), alors, lorsque vous créez une ligne de compteur de ce type, chaque actif enfant qui utilise le même type de compteur est automatiquement mis à jour.</span><span class="sxs-lookup"><span data-stu-id="1960c-105">If the counter type selected for a counter is set to inherit counter values (**Asset management** > **Setup** > **Asset types** > **Counters** > **General** FastTab > **Inherit asset counter values** toggle button set to "Yes"), then, when you create a new counter line of that type, every child asset that uses the same counter type is automatically updated.</span></span>

<span data-ttu-id="1960c-106">Dans **Tous les actifs**, vous créez enregistrements de compteur de type heures ou quantité sur un actif, selon vos lectures de l'actif.</span><span class="sxs-lookup"><span data-stu-id="1960c-106">In **All assets**, you create hours or quantity counter registrations on an asset, based on your readings on the asset.</span></span>

1. <span data-ttu-id="1960c-107">Cliquez sur **Gestion des actifs** > **Commun** > **Actifs** > **Tous les actifs**.</span><span class="sxs-lookup"><span data-stu-id="1960c-107">Click **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="1960c-108">Sélectionnez l'actif dans la liste et cliquez sur **Compteurs**.</span><span class="sxs-lookup"><span data-stu-id="1960c-108">Select the asset in the list, and click **Counters**.</span></span> <span data-ttu-id="1960c-109">Sur l'écran **Compteurs d'actifs**, vous découvrez une liste de tous les enregistrements de compteur précédents sur l'actif sélectionné.</span><span class="sxs-lookup"><span data-stu-id="1960c-109">In the **Asset counters** form, you see a list of all previous counter registrations on the selected asset.</span></span>

3. <span data-ttu-id="1960c-110">Cliquez sur **Nouveau** pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="1960c-110">Click **New** to create a new registration.</span></span> <span data-ttu-id="1960c-111">L'ID d'immobilisation est automatiquement inséré.</span><span class="sxs-lookup"><span data-stu-id="1960c-111">The asset ID is automatically inserted.</span></span>

4. <span data-ttu-id="1960c-112">Dans le champ **Compteur**, sélectionnez le compteur pertinent.</span><span class="sxs-lookup"><span data-stu-id="1960c-112">In the **Counter** field, select the relevant counter.</span></span> <span data-ttu-id="1960c-113">Seuls les compteurs associés au type d'actif sélectionné sur l'actif sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="1960c-113">Only counters related to the asset type selected on the asset are available.</span></span> <span data-ttu-id="1960c-114">L'unité associée est automatiquement insérée dans le champ **Unité**.</span><span class="sxs-lookup"><span data-stu-id="1960c-114">The related unit is automatically inserted in the **Unit** field.</span></span>

5. <span data-ttu-id="1960c-115">Sélectionnez la date et l'heure pour le compteur d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="1960c-115">Select date and time for the counter registration.</span></span>

6. <span data-ttu-id="1960c-116">Dans le champ **Valeur**, insérez le nombre depuis le dernier enregistrement de compteur, ou, dans le champ **Valeur associée**, insérez le nombre total.</span><span class="sxs-lookup"><span data-stu-id="1960c-116">In the **Value** field, insert the number since the last counter registration, or, in the **Aggregated value** field, insert the total count number.</span></span>

- <span data-ttu-id="1960c-117">Si vous installez physiquement un nouveau compteur sur un actif, vous devez enregistrer la modification sur l'actif dans **Compteurs d'actifs**.</span><span class="sxs-lookup"><span data-stu-id="1960c-117">If you physically install a new counter on an asset, you need to register the change on the asset in **Asset counters**.</span></span> <span data-ttu-id="1960c-118">Ensuite, vous devez créer deux lignes d'enregistrement avec des groupes date/d'heure identiques, puis sur la ligne concernant le nouveau compteur, activez la case à cocher **Réinitialiser le compteur**.</span><span class="sxs-lookup"><span data-stu-id="1960c-118">Next, you must create two registration lines with identical timestamps, and on the line regarding the new counter, you select the **Counter reset** check box.</span></span> <span data-ttu-id="1960c-119">Lorsque vous créez les deux lignes d'enregistrement, la première ligne doit être pour le compteur que vous remplacez.</span><span class="sxs-lookup"><span data-stu-id="1960c-119">When you create the two registration lines, the first line must be for the counter that you are replacing.</span></span> <span data-ttu-id="1960c-120">Dans le champ **Totaux**, le total correspond à la somme du total du compteur de toutes les valeurs enregistrées dans ce compteur type.</span><span class="sxs-lookup"><span data-stu-id="1960c-120">In the **Totals** field, the total count number is the sum of the counter total of all registered values on that counter type.</span></span>  
- <span data-ttu-id="1960c-121">Si la case **Réinitialiser le compteur** est cochée sur un actif à l'aide d'un plan de maintenance avec un intervalle de type « Une fois à partir de… » ou « Une fois atteint… », le compteur est toujours actif sur la nouvelle ligne du compteur, car vous créez une ligne de compteur à part et commencez un nouveau compteur.</span><span class="sxs-lookup"><span data-stu-id="1960c-121">If the **Counter reset** check box is selected on an asset using a maintenance plan with a "Once from..." or "Once reached..." interval type, the counter is still active on the new counter line because you create a separate counter line and start over with a new counter.</span></span>

![Figure 1](media/11-work-orders.png)


<span data-ttu-id="1960c-123">Si vous devez effectuer des enregistrements de compteur sur plusieurs actifs, cela peut s'effectuer dans **Gestion des actifs** > **Recherches** > **Actifs** > **Compteurs d'actifs**.</span><span class="sxs-lookup"><span data-stu-id="1960c-123">If you need to make counter registrations on several assets, that can be done in **Asset management** > **Inquiries** > **Assets** > **Asset counters**.</span></span>

>[!NOTE]
><span data-ttu-id="1960c-124">Vous pouvez paramétrer une plage pour définir des écarts dans les enregistrements de compteur manuels, et le type de message qui doit être affiché si les enregistrements se font en dehors de la plage définie.</span><span class="sxs-lookup"><span data-stu-id="1960c-124">You can set up a range to define deviations in manual counter registrations, and the type of message that should be displayed if registrations are outside the defined range.</span></span> <span data-ttu-id="1960c-125">Reportez-vous à la section [Compteurs](../setup-for-objects/counters.md) pour plus d'informations sur le paramétrage des compteurs.</span><span class="sxs-lookup"><span data-stu-id="1960c-125">Refer to the [Counters](../setup-for-objects/counters.md) topic regarding setup of counters.</span></span>
