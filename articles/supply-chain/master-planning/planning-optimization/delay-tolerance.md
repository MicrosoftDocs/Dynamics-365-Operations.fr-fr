---
title: Tolérance de retard (jours négatifs)
description: Cette rubrique fournit des informations sur le calcul de la tolérance de retard et son impact sur la création d’ordres planifiés dans l’optimisation de la planification.
author: crytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 748e047e89747f2eabccc04a40c79bcb1e6f3dea
ms.sourcegitcommit: f21659f1c23bc2cd65bbe7fb7210910d5a8e1cb9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306461"
---
# <a name="delay-tolerance-negative-days"></a><span data-ttu-id="50374-103">Tolérance de retard (jours négatifs)</span><span class="sxs-lookup"><span data-stu-id="50374-103">Delay tolerance (negative days)</span></span>

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="50374-104">La fonctionnalité de tolérance de retard permet à l’optimisation de la planification de prendre en compte la valeur **Jours négatifs** définie pour les groupes de couverture.</span><span class="sxs-lookup"><span data-stu-id="50374-104">The delay tolerance functionality enables Planning Optimization to consider the **Negative days** value that is set for coverage groups.</span></span> <span data-ttu-id="50374-105">Elle sert à prolonger la période de tolérance de retard qui est appliquée lors de la planification générale.</span><span class="sxs-lookup"><span data-stu-id="50374-105">It's used to extend the delay tolerance period that is applied during master planning.</span></span> <span data-ttu-id="50374-106">De cette façon, vous pouvez éviter de créer de nouvelles commandes d’approvisionnement si l’approvisionnement existant peut couvrir la demande après un court délai.</span><span class="sxs-lookup"><span data-stu-id="50374-106">In this way, you can avoid creating new supply orders if existing supply will be able to cover the demand after a short delay.</span></span> <span data-ttu-id="50374-107">Le but de cette fonctionnalité est de déterminer s’il est judicieux de créer un nouvel ordre d’approvisionnement pour une demande donnée.</span><span class="sxs-lookup"><span data-stu-id="50374-107">The purpose of the functionality is to determine whether it makes sense to create a new supply order for a given demand.</span></span>

## <a name="turn-on-the-feature-in-your-system"></a><span data-ttu-id="50374-108">Activez la fonctionnalité dans votre système</span><span class="sxs-lookup"><span data-stu-id="50374-108">Turn on the feature in your system</span></span>

<span data-ttu-id="50374-109">Pour rendre la fonctionnalité de tolérance de retard disponible dans votre système, accédez à [Gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), et activez la fonctionnalité *Jours négatifs dans l’optimisation de la planification*.</span><span class="sxs-lookup"><span data-stu-id="50374-109">To make the delay tolerance functionality available in your system, go to [Feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the *Negative days for Planning Optimization* feature.</span></span>

## <a name="delay-tolerance-in-planning-optimization"></a><span data-ttu-id="50374-110">Tolérance de retard dans l’optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="50374-110">Delay tolerance in Planning Optimization</span></span>

<span data-ttu-id="50374-111">La tolérance de retard représente le nombre de jours au-delà du délai que vous êtes prêt à attendre avant de commander un nouveau réapprovisionnement lorsqu’un approvisionnement existant est déjà planifié.</span><span class="sxs-lookup"><span data-stu-id="50374-111">Delay tolerance represents the number of days beyond the lead time that you're willing to wait before you order new replenishment when existing supply is already planned.</span></span> <span data-ttu-id="50374-112">La tolérance de retard est définie en fonction des jours calendaires et non des jours ouvrables.</span><span class="sxs-lookup"><span data-stu-id="50374-112">Delay tolerance is defined by using calendar days, not business days.</span></span>

<span data-ttu-id="50374-113">Au moment de la planification générale, lorsque le système calcule la tolérance de retard, il prend en compte le paramètre **Jours négatifs**.</span><span class="sxs-lookup"><span data-stu-id="50374-113">At the time of master planning, when the system calculates the delay tolerance, it considers the **Negative days** setting.</span></span> <span data-ttu-id="50374-114">Vous pouvez définir la valeur **Jours négatifs** sur la page **Groupes de couverture** ou sur la page **Couverture de l’article**.</span><span class="sxs-lookup"><span data-stu-id="50374-114">You can set the **Negative days** value on either the **Coverage groups** page or the **Item coverage** page.</span></span>

<span data-ttu-id="50374-115">Le système lie le calcul de la tolérance de retard à la *date de réapprovisionnement la plus proche*, qui est égale à la date du jour plus le délai.</span><span class="sxs-lookup"><span data-stu-id="50374-115">The system links the delay tolerance calculation to the *earliest replenishment date*, which equals today's date plus the lead time.</span></span> <span data-ttu-id="50374-116">La tolérance de retard est calculée en utilisant la formule suivante, où *max()* trouve la plus grande des deux valeurs :</span><span class="sxs-lookup"><span data-stu-id="50374-116">The delay tolerance is calculated by using following formula, where *max()* finds the larger of two values:</span></span>

<span data-ttu-id="50374-117">*max(Date de réapprovisionnement la plus proche, Date d’échéance de la demande)*  – *Date d’échéance de la demande* + *Jours négatifs*</span><span class="sxs-lookup"><span data-stu-id="50374-117">*max(Earliest replenishment date, Demand due date)* – *Demand due date* + *Negative days*</span></span>

<span data-ttu-id="50374-118">Cette formule garantit que la planification générale ne crée pas de nouvelles commandes d’approvisionnement lorsqu’il existe suffisamment d’approvisionnement pendant le délai d’approvisionnement du produit.</span><span class="sxs-lookup"><span data-stu-id="50374-118">This formula ensures that master planning doesn't create new supply orders when enough supply exists during the product lead time.</span></span>

> [!NOTE]
> <span data-ttu-id="50374-119">Le calcul de la tolérance de retard dans l’optimisation de la planification utilise toujours le calcul dynamique des jours négatifs provenant de la planification générale intégrée.</span><span class="sxs-lookup"><span data-stu-id="50374-119">The delay tolerance calculation in Planning Optimization always uses the dynamic negative days calculation from built-in master planning.</span></span> <span data-ttu-id="50374-120">Le paramètre **Utiliser des jours négatifs dynamiques** de la page **Paramètres de la planification générale** n’a aucun effet sur ce comportement.</span><span class="sxs-lookup"><span data-stu-id="50374-120">The **Use dynamic negative days** setting on the **Master planning parameters** page has no effect on this behavior.</span></span>

<span data-ttu-id="50374-121">Si l’approvisionnement existant implique un retard de demande inférieur ou égal à la tolérance de retard calculée, l’optimisation de la planification rattache l’approvisionnement existant à la demande.</span><span class="sxs-lookup"><span data-stu-id="50374-121">If the existing supply implies a demand delay that is less than or equal to the calculated delay tolerance, Planning Optimization pegs existing supply with the demand.</span></span> <span data-ttu-id="50374-122">Dans certains cas, il vaut mieux retarder la demande que de se retrouver avec une offre excédentaire.</span><span class="sxs-lookup"><span data-stu-id="50374-122">In some cases, it's better to delay the demand than to end up with oversupply.</span></span>

<span data-ttu-id="50374-123">Les sous-sections suivantes illustrent qui montrent comment la tolérance de retard affecte la création d’ordres planifiés dans l’optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="50374-123">The following subsections provide examples that show how delay tolerance affects the creation of planned orders in Planning Optimization.</span></span>

### <a name="example-1"></a><span data-ttu-id="50374-124">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="50374-124">Example 1</span></span>

<span data-ttu-id="50374-125">Un produit a la configuration suivante :</span><span class="sxs-lookup"><span data-stu-id="50374-125">A product has the following configuration:</span></span>

- <span data-ttu-id="50374-126">**Délai :** *10*</span><span class="sxs-lookup"><span data-stu-id="50374-126">**Lead time:** *10*</span></span>
- <span data-ttu-id="50374-127">**Jours négatifs :** *2*</span><span class="sxs-lookup"><span data-stu-id="50374-127">**Negative days:** *2*</span></span>

<span data-ttu-id="50374-128">L’offre et la demande suivantes existent pour le produit :</span><span class="sxs-lookup"><span data-stu-id="50374-128">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="50374-129">**Demande pour aujourd’hui :** une commande client pour une quantité de 10</span><span class="sxs-lookup"><span data-stu-id="50374-129">**Demand for today:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="50374-130">**Approvisionnement dans 12 jours :** une commande fournisseur pour une quantité de 10</span><span class="sxs-lookup"><span data-stu-id="50374-130">**Supply in 12 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="50374-131">L’approvisionnement existant peut couvrir la demande dans les 12 jours, et cette période est égale à la tolérance de retard.</span><span class="sxs-lookup"><span data-stu-id="50374-131">Existing supply can cover the demand within 12 days, and that period equals the delay tolerance.</span></span> <span data-ttu-id="50374-132">Par conséquent, lors de l’exécution de la planification générale, aucune commande planifiée n’est créé.</span><span class="sxs-lookup"><span data-stu-id="50374-132">Therefore, when master planning runs, no planned orders are created.</span></span>

### <a name="example-2"></a><span data-ttu-id="50374-133">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="50374-133">Example 2</span></span>

<span data-ttu-id="50374-134">Un produit a la configuration suivante :</span><span class="sxs-lookup"><span data-stu-id="50374-134">A product has the following configuration:</span></span>

- <span data-ttu-id="50374-135">**Délai :** *10*</span><span class="sxs-lookup"><span data-stu-id="50374-135">**Lead time:** *10*</span></span>
- <span data-ttu-id="50374-136">**Jours négatifs :** *0*</span><span class="sxs-lookup"><span data-stu-id="50374-136">**Negative days:** *0*</span></span>

<span data-ttu-id="50374-137">L’offre et la demande suivantes existent pour le produit :</span><span class="sxs-lookup"><span data-stu-id="50374-137">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="50374-138">**Demande pour aujourd’hui :** une commande client pour une quantité de 10</span><span class="sxs-lookup"><span data-stu-id="50374-138">**Demand for today:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="50374-139">**Approvisionnement dans 12 jours :** une commande fournisseur pour une quantité de 10</span><span class="sxs-lookup"><span data-stu-id="50374-139">**Supply in 12 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="50374-140">L’approvisionnement existant ne peut couvrir la demande qu’après 12 jours.</span><span class="sxs-lookup"><span data-stu-id="50374-140">Existing supply can cover the demand only after 12 days.</span></span> <span data-ttu-id="50374-141">Cependant, la tolérance de retard est de 10 jours.</span><span class="sxs-lookup"><span data-stu-id="50374-141">However, the delay tolerance is 10 days.</span></span> <span data-ttu-id="50374-142">Par conséquent, lors de l’exécution de la planification générale, une commande planifiée pour une quantité de 10 est créé.</span><span class="sxs-lookup"><span data-stu-id="50374-142">Therefore, when master planning runs, a planned order for a quantity of 10 is created.</span></span>

### <a name="example-3"></a><span data-ttu-id="50374-143">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="50374-143">Example 3</span></span>

<span data-ttu-id="50374-144">Un produit a la configuration suivante :</span><span class="sxs-lookup"><span data-stu-id="50374-144">A product has the following configuration:</span></span>

- <span data-ttu-id="50374-145">**Délai :** *10*</span><span class="sxs-lookup"><span data-stu-id="50374-145">**Lead time:** *10*</span></span>
- <span data-ttu-id="50374-146">**Jours négatifs :** *2*</span><span class="sxs-lookup"><span data-stu-id="50374-146">**Negative days:** *2*</span></span>

<span data-ttu-id="50374-147">L’offre et la demande suivantes existent pour le produit :</span><span class="sxs-lookup"><span data-stu-id="50374-147">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="50374-148">**Demande dans 11 jours :** une commande client pour une quantité de 10</span><span class="sxs-lookup"><span data-stu-id="50374-148">**Demand in 11 days:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="50374-149">**Approvisionnement dans 14 jours :** une commande fournisseur pour une quantité de 10</span><span class="sxs-lookup"><span data-stu-id="50374-149">**Supply in 14 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="50374-150">L’approvisionnement existant ne peut couvrir la demande qu’après trois jours.</span><span class="sxs-lookup"><span data-stu-id="50374-150">Existing supply can cover the demand only after three days.</span></span> <span data-ttu-id="50374-151">Cependant, la tolérance de retard est de deux jours.</span><span class="sxs-lookup"><span data-stu-id="50374-151">However, the delay tolerance is two days.</span></span> <span data-ttu-id="50374-152">(Dans ce cas, la tolérance de retard ne comprend que les deux jours négatifs.</span><span class="sxs-lookup"><span data-stu-id="50374-152">(In this case, the delay tolerance includes only the two negative days.</span></span> <span data-ttu-id="50374-153">La date de demande n’est pas incluse car elle est postérieure au délai de livraison du produit.) Par conséquent, lors de l’exécution de la planification générale, une commande planifiée pour une quantité de 10 est créé.</span><span class="sxs-lookup"><span data-stu-id="50374-153">The demand date isn't included because it's after the product lead time.) Therefore, when master planning runs, a planned order for a quantity of 10 is created.</span></span>
