---
title: Mise à jour manuelle des compteurs d’actifs
description: Cette rubrique décrit les mises à jour manuelles des compteurs d’actifs dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCounter
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4618ff2d6880f478683fbed0ed716af5ab8d4d9c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842247"
---
# <a name="manual-update-of-asset-counters"></a><span data-ttu-id="bc555-103">Mise à jour manuelle des compteurs d’actifs</span><span class="sxs-lookup"><span data-stu-id="bc555-103">Manual update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="bc555-104">Les compteurs permettent de créer des enregistrements sur un actif, comme des enregistrements du nombre d’heures fonctionnelles de l’actif ou la quantité produite.</span><span class="sxs-lookup"><span data-stu-id="bc555-104">Counters are used to create registrations on an asset, such as registrations about the number of hours that the asset has been in operation or the quantity that has been produced.</span></span>

<span data-ttu-id="bc555-105">Le type de compteur sélectionné pour un compteur peut être défini pour hériter des valeurs du compteur.</span><span class="sxs-lookup"><span data-stu-id="bc555-105">The counter type that is selected for a counter might be set to inherit counter values.</span></span> <span data-ttu-id="bc555-106">En d’autres termes, l’option **Hériter des contre-valeurs d’actifs** est définie sur **Oui** dans l’organisateur **Général** de la page **Compteurs** (**Gestion des actifs** > **Paramétrage** > **Types d’actifs** > **Compteurs**).</span><span class="sxs-lookup"><span data-stu-id="bc555-106">In other words, the **Inherit asset counter values** option is set to **Yes** on the **General** FastTab of the **Counters** page (**Asset management** > **Setup** > **Asset types** > **Counters**).</span></span> <span data-ttu-id="bc555-107">Dans ce cas, lorsque vous créez une ligne de compteur de ce type, chaque actif enfant qui utilise le même type de compteur est automatiquement mis à jour.</span><span class="sxs-lookup"><span data-stu-id="bc555-107">In this case, when you create a new counter line of that type, every child asset that uses the same counter type is automatically updated.</span></span>

<span data-ttu-id="bc555-108">Sur la page **Tous les actifs**, vous créez enregistrements de compteur de type heures ou quantité sur un actif, selon vos lectures de l’actif.</span><span class="sxs-lookup"><span data-stu-id="bc555-108">On the **All assets** page, you create hours or quantity counter registrations on an asset, based on your readings on the asset.</span></span>

1. <span data-ttu-id="bc555-109">Sélectionnez **Gestion des actifs** > **Commun** > **Actifs** > **Tous les actifs**.</span><span class="sxs-lookup"><span data-stu-id="bc555-109">Select **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="bc555-110">Sélectionnez l’actif, puis dans le volet Actions, sous l’onglet **Actif**, dans le groupe **Préventif**, sélectionnez **Compteurs**.</span><span class="sxs-lookup"><span data-stu-id="bc555-110">Select the asset, and then, on the Action Pane, on the **Asset** tab, in the **Preventive** group, select **Counters**.</span></span> <span data-ttu-id="bc555-111">La page **Compteurs d’actifs** affiche une liste de tous les enregistrements de compteur précédents effectués sur l’actif sélectionné.</span><span class="sxs-lookup"><span data-stu-id="bc555-111">The **Asset counters** page shows a list of all previous counter registrations that have been made on the selected asset.</span></span>

3. <span data-ttu-id="bc555-112">Sélectionnez **Nouveau** pour créer une inscription.</span><span class="sxs-lookup"><span data-stu-id="bc555-112">Select **New** to create a registration.</span></span> <span data-ttu-id="bc555-113">L’ID actif est automatiquement entré dans le champ **Actif**.</span><span class="sxs-lookup"><span data-stu-id="bc555-113">The asset ID is automatically entered in the **Asset** field.</span></span>

4. <span data-ttu-id="bc555-114">Dans le champ **Compteur**, sélectionnez le compteur pertinent.</span><span class="sxs-lookup"><span data-stu-id="bc555-114">In the **Counter** field, select the relevant counter.</span></span> <span data-ttu-id="bc555-115">Seuls les compteurs associés au type d’actif sélectionné sur l’actif sont disponibles pour sélection.</span><span class="sxs-lookup"><span data-stu-id="bc555-115">Only counters that are related to the asset type selected on the asset are available for selection.</span></span> <span data-ttu-id="bc555-116">L’unité associée est automatiquement entrée dans le champ **Unité**.</span><span class="sxs-lookup"><span data-stu-id="bc555-116">The related unit is automatically entered in the **Unit** field.</span></span>

5. <span data-ttu-id="bc555-117">Dans le champ **Enregistré**, sélectionnez la date et l’heure d’enregistrement du compteur.</span><span class="sxs-lookup"><span data-stu-id="bc555-117">In the **Registered** field, select the date and time for the counter registration.</span></span>

6. <span data-ttu-id="bc555-118">Dans le champ **Valeur**, entrez le numéro depuis le dernier enregistrement du compteur.</span><span class="sxs-lookup"><span data-stu-id="bc555-118">In the **Value** field, enter the number since the last counter registration.</span></span> <span data-ttu-id="bc555-119">Sinon, dans le champ **Valeur associée**, entrez le total.</span><span class="sxs-lookup"><span data-stu-id="bc555-119">Alternatively, in the **Aggregated value** field, enter the total count number.</span></span>

<span data-ttu-id="bc555-120">Notez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="bc555-120">Note the following points:</span></span>

- <span data-ttu-id="bc555-121">Si vous installez physiquement un nouveau compteur sur un actif, vous devez enregistrer la modification sur l’actif sur la page **Compteurs d’actifs**.</span><span class="sxs-lookup"><span data-stu-id="bc555-121">If you physically install a new counter on an asset, you must register the change on the asset on the **Asset counters** page.</span></span> <span data-ttu-id="bc555-122">Ensuite, vous devez créer deux lignes d’enregistrement avec des horodatages identiques.</span><span class="sxs-lookup"><span data-stu-id="bc555-122">Next, you must create two registration lines that have identical timestamps.</span></span> <span data-ttu-id="bc555-123">La première ligne doit être pour le compteur que vous remplacez.</span><span class="sxs-lookup"><span data-stu-id="bc555-123">The first line must be for the counter that you're replacing.</span></span> <span data-ttu-id="bc555-124">Sur la ligne associée au nouveau compteur, activez la case à cocher **Réinitialiser le compteur**.</span><span class="sxs-lookup"><span data-stu-id="bc555-124">On the line that is related to the new counter, select the **Counter reset** check box.</span></span> <span data-ttu-id="bc555-125">Dans le champ **Totaux**, le total correspond à la somme des totaux du compteur de toutes les valeurs enregistrées dans ce compteur type.</span><span class="sxs-lookup"><span data-stu-id="bc555-125">In the **Totals** field, the total count number is the sum of the counter totals of all registered values on that counter type.</span></span>

- <span data-ttu-id="bc555-126">Si la case **Réinitialiser le compteur** est cochée sur un actif à l’aide d’un plan de maintenance avec un intervalle de type « Une fois à partir de… » ou « Une fois atteint… », le compteur est toujours actif sur la nouvelle ligne du compteur, car vous créez une ligne de compteur à part et commencez un nouveau compteur.</span><span class="sxs-lookup"><span data-stu-id="bc555-126">If the **Counter reset** check box is selected on an asset using a maintenance plan that has a "Once from..." or "Once reached..." interval type, the counter is still active on the new counter line, because you create a separate counter line and start over with a new counter.</span></span>

<span data-ttu-id="bc555-127">L’illustration suivante présente un exemple de la boîte de dialogue **Compteurs d’actif**.</span><span class="sxs-lookup"><span data-stu-id="bc555-127">The illustration below shows an example of the **Asset counters** page.</span></span>

![Figure 1](media/11-work-orders.png)

<span data-ttu-id="bc555-129">Sur la page **Compteurs d’actif** (**Gestion des actifs** > **Recherches** > **Actifs** > **Compteurs d’actif**), vous pouvez effectuer des enregistrements de compteur sur plusieurs actifs en même temps, comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="bc555-129">On the **Asset counters** page (**Asset management** > **Inquiries** > **Assets** > **Asset counters**), you can make counter registrations on several assets at the same time, as you require.</span></span>

>[!NOTE]
><span data-ttu-id="bc555-130">Vous pouvez paramétrer une plage pour définir des écarts entre les enregistrements de compteur manuels.</span><span class="sxs-lookup"><span data-stu-id="bc555-130">You can set up a range to define deviations in manual counter registrations.</span></span> <span data-ttu-id="bc555-131">Vous pouvez également spécifier le type de message qui s’affiche si les enregistrements se situent en dehors de la plage définie.</span><span class="sxs-lookup"><span data-stu-id="bc555-131">You can also specify the type of message that is shown if registrations are outside the defined range.</span></span> <span data-ttu-id="bc555-132">Pour plus d’informations sur la configuration des compteurs, voir [Compteurs](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="bc555-132">For more information about how to set up counters, see [Counters](../setup-for-objects/counters.md).</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]