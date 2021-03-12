---
title: Réapprovisionnement sur la capacité de l’emplacement
description: Cette rubrique fournit des informations sur la fonctionnalité Réapprovisionnement sur la capacité de l’emplacement. Cette fonctionnalité permet de créer tout le travail de réapprovisionnement qui sera nécessaire pour la journée et gère la disponibilité de ce travail de réapprovisionnement pour garantir que le site de prélèvement ne soit pas à court de stock ni ne dépasse la capacité.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 3f94053920b475ef9190b5ac65a5f9ca01dcd4a1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996121"
---
# <a name="replenishment-over-location-capacity"></a><span data-ttu-id="12852-104">Réapprovisionnement sur la capacité de l’emplacement</span><span class="sxs-lookup"><span data-stu-id="12852-104">Replenishment over location capacity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="12852-105">Certains entrepôts à volume élevé ou à espace restreint doivent expédier plus de quantité d’un article en une journée que celle du lieu de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="12852-105">Some high-volume or space-constrained warehouses must ship more quantity of an item in a day than will fit in the picking location.</span></span> <span data-ttu-id="12852-106">La fonctionnalité *Réapprovisionnement sur la capacité de l’emplacement* permet de créer tout le travail de réapprovisionnement qui sera nécessaire pour la journée et gère la disponibilité de ce travail de réapprovisionnement pour garantir que le site de prélèvement ne soit pas à court de stock ni ne dépasse la capacité.</span><span class="sxs-lookup"><span data-stu-id="12852-106">The *Replenishment over location capacity* feature enables all replenishment work that will be required for the day to be created and manages availability of that replenishment work to ensure that the picking location neither runs out of inventory nor goes above capacity.</span></span>

<span data-ttu-id="12852-107">La fonctionnalité permet de créer plus de travaux de réapprovisionnement que ce qui peut en tenir à un emplacement, et elle empêche le travail de réapprovisionnement de se terminer lorsque l’emplacement est plein.</span><span class="sxs-lookup"><span data-stu-id="12852-107">The feature enables more replenishment work to be created than will fit in a location, and it blocks replenishment work from being completed when the location is full.</span></span> <span data-ttu-id="12852-108">À mesure que le stock de l’emplacement de prélèvement tombe en dessous d’un seuil configurable, plus de travail de réapprovisionnement est rendu disponible.</span><span class="sxs-lookup"><span data-stu-id="12852-108">As inventory in the picking location drops below a configurable threshold, more replenishment work is made available.</span></span>

## <a name="turn-on-the-replenishment-over-location-capacity-feature"></a><span data-ttu-id="12852-109">Activer la fonctionnalité Réapprovisionnement sur la capacité de l’emplacement</span><span class="sxs-lookup"><span data-stu-id="12852-109">Turn on the Replenishment over location capacity feature</span></span>

<span data-ttu-id="12852-110">Pour rendre cette fonctionnalité disponible, activez les fonctionnalités suivantes dans la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (dans l’ordre suivant) :</span><span class="sxs-lookup"><span data-stu-id="12852-110">To make this feature available, turn on the following features in [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (in this order):</span></span>

1. <span data-ttu-id="12852-111">Blocage des tâches à l’échelle de l’organisation</span><span class="sxs-lookup"><span data-stu-id="12852-111">Organization-wide work blocking</span></span>
1. <span data-ttu-id="12852-112">Réapprovisionnement sur la capacité de l’emplacement</span><span class="sxs-lookup"><span data-stu-id="12852-112">Replenishment over location capacity</span></span>

## <a name="set-up-the-feature-for-the-example-scenario"></a><span data-ttu-id="12852-113">Configurer la fonctionnalité pour l’exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="12852-113">Set up the feature for the example scenario</span></span>

<span data-ttu-id="12852-114">Cette section fournit des instructions et un exemple de la configuration de cette fonctionnalité et prépare des exemples de données pour l’exemple de scénario fourni plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="12852-114">This section provides guidelines and an example that shows how to set up this feature and prepare sample data for the example scenario that is provided later in this topic.</span></span>

### <a name="enable-sample-data"></a><span data-ttu-id="12852-115">Activer les exemples de données</span><span class="sxs-lookup"><span data-stu-id="12852-115">Enable sample data</span></span>

<span data-ttu-id="12852-116">Pour utiliser [l’exemple de scénario](#example-scenario) à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées.</span><span class="sxs-lookup"><span data-stu-id="12852-116">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="12852-117">En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="12852-117">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="location-profile"></a><span data-ttu-id="12852-118">Profil d’emplacement</span><span class="sxs-lookup"><span data-stu-id="12852-118">Location profile</span></span>

<span data-ttu-id="12852-119">Activez la fonctionnalité Réapprovisionnement sur la capacité de l’emplacement sur le profil d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="12852-119">Enable the replenish over capacity functionality on the location profile.</span></span>

1. <span data-ttu-id="12852-120">Allez dans **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Profils d’emplacements**.</span><span class="sxs-lookup"><span data-stu-id="12852-120">Go to **Warehouse management \> Setup \> Warehouse \> Locations profiles**.</span></span>
1. <span data-ttu-id="12852-121">Dans le volet gauche, sélectionnez **PICK-06**.</span><span class="sxs-lookup"><span data-stu-id="12852-121">In the left pane, select **PICK-06**.</span></span>
1. <span data-ttu-id="12852-122">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="12852-122">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="12852-123">Dans l’organisateur **Réapprovisionnement**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="12852-123">On the **Replenishment** FastTab, set the following values:</span></span>

    - <span data-ttu-id="12852-124">**Dépasser la capacité de l’emplacement :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="12852-124">**Exceed Location Capacity:** *Yes*</span></span>

        <span data-ttu-id="12852-125">Lorsque ce champ est activé, la capacité maximale de l’emplacement pourra être dépassée par le travail de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="12852-125">When enabled, the maximum capacity of the location will be allowed to be exceeded by replenishment work.</span></span> <span data-ttu-id="12852-126">Cela active également d’autres champs sur l’organisateur **Réapprovisionnement**.</span><span class="sxs-lookup"><span data-stu-id="12852-126">This also enables other fields on the **Replenishment** FastTab.</span></span>

    - <span data-ttu-id="12852-127">**Type de seuil de disponibilité de travail :** *Quantité*</span><span class="sxs-lookup"><span data-stu-id="12852-127">**Work availability threshold type:** *Quantity*</span></span>

        <span data-ttu-id="12852-128">Ce champ définit la méthode utilisée pour déterminer quand plus de travail doit être libéré.</span><span class="sxs-lookup"><span data-stu-id="12852-128">This field defines the method that is used to determine when more work should be released.</span></span> <span data-ttu-id="12852-129">Vous pouvez procéder à une libération par quantité ou par pourcentage :</span><span class="sxs-lookup"><span data-stu-id="12852-129">You can release by either quantity or a percentage:</span></span>

        - <span data-ttu-id="12852-130">*Pourcentage* – Sélectionnez cette option pour utiliser un pourcentage de capacité basé sur des limites de stockage ou des volumes.</span><span class="sxs-lookup"><span data-stu-id="12852-130">*Percent* – Select this option to use percentage capacity that is based on stocking limits or volumetrics.</span></span> <span data-ttu-id="12852-131">La sélection de cette option active le champ **Pourcentage de débordement** et désactive les deux champs liés à la quantité, **Quantité de débordement** et **Unité de débordement**.</span><span class="sxs-lookup"><span data-stu-id="12852-131">Selecting this option enables the **Overflow percentage** field, and disables the two quantity related fields,  **Overflow quantity** and **Overflow unit**.</span></span>

            <span data-ttu-id="12852-132">Vous pouvez utiliser cette option si les emplacements de prélèvement utilisent la volumétrie.</span><span class="sxs-lookup"><span data-stu-id="12852-132">You can use this option if the picking locations use volumetrics.</span></span>

            <span data-ttu-id="12852-133">Si cette option est sélectionnée, définissez le champ **Pourcentage de débordement** sur le pourcentage auquel des travaux de réapprovisionnement supplémentaires seront disponibles.</span><span class="sxs-lookup"><span data-stu-id="12852-133">If this option is selected, set the **Overflow percentage** field to the percentage at which more replenishment work will be made available.</span></span>

        - <span data-ttu-id="12852-134">*Quantité* – Sélectionnez cette option pour utiliser une valeur de quantité spécifique.</span><span class="sxs-lookup"><span data-stu-id="12852-134">*Quantity* – Select this option to use a specific quantity value.</span></span> <span data-ttu-id="12852-135">La sélection de cette option désactive le champ **Pourcentage de débordement** et les champs **Quantité de débordement** et **Unité de débordement**.</span><span class="sxs-lookup"><span data-stu-id="12852-135">Selecting this option disables the **Overflow percentage** field and enables **Overflow quantity** and **Overflow unit** fields.</span></span>

            <span data-ttu-id="12852-136">Utilisez cette option lorsque vous n’utilisez pas de volumétrie pour les emplacements qui sont en cours de réapprovisionnement, ou lorsque vous avez des quantités cohérentes pour lesquelles vous souhaitez que plus de stock soit amené à l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="12852-136">Use this option when you aren't using volumetrics for the locations that are being replenished, or when you have consistent quantities at which you want more inventory to be brought to the location.</span></span>

           <span data-ttu-id="12852-137">Si cette option est sélectionnée, définissez les champs **Quantité de débordement** et **Unité de débordement** sur la quantité et l’unité auxquelles plus de travail de réapprovisionnement sera disponible.</span><span class="sxs-lookup"><span data-stu-id="12852-137">If this option is selected, set the **Overflow quantity** and **Overflow unit** fields to the quantity and unit at which more replenishment work will be made available.</span></span>

    - <span data-ttu-id="12852-138">**Quantité de dépassement :** *0,65*</span><span class="sxs-lookup"><span data-stu-id="12852-138">**Overflow quantity:** *0.65*</span></span>

        <span data-ttu-id="12852-139">Ce champ définit la quantité de débordement de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="12852-139">This field defines the quantity at which the location overflows.</span></span>

        <span data-ttu-id="12852-140">Le travail sera disponible lorsque la somme de la quantité disponible à l’emplacement et la quantité de travail sont inférieures à cette valeur.</span><span class="sxs-lookup"><span data-stu-id="12852-140">Work will be available whenever the sum of the on-hand quantity in the location and the work quantity is below this value.</span></span> <span data-ttu-id="12852-141">Tout travail de réapprovisionnement supérieur à cette valeur sera bloqué et doit être débloqué manuellement.</span><span class="sxs-lookup"><span data-stu-id="12852-141">Any replenishment work above this value will be blocked and must be manually unblocked.</span></span>

        <span data-ttu-id="12852-142">Les limites de stockage sur site sont prises en compte lors du calcul de la quantité de travail.</span><span class="sxs-lookup"><span data-stu-id="12852-142">Location stocking limits are considered when the work quantity is calculated.</span></span>

    - <span data-ttu-id="12852-143">**Unité de débordement :** *PL*</span><span class="sxs-lookup"><span data-stu-id="12852-143">**Overflow unit:** *PL*</span></span>

        <span data-ttu-id="12852-144">Ce champ définit l’unité associée à la quantité de débordement.</span><span class="sxs-lookup"><span data-stu-id="12852-144">This field defines the unit that is associated with the overflow quantity.</span></span>

        <span data-ttu-id="12852-145">Dans ce cas, des travaux de réapprovisionnement supplémentaires seront disponibles lorsque l’emplacement sera réduit à 0,65 palette (PL).</span><span class="sxs-lookup"><span data-stu-id="12852-145">In this case, more replenishment work will be made available when the location gets down to 0.65 pallet (PL).</span></span>

    - <span data-ttu-id="12852-146">**Pourcentage de dépassement**</span><span class="sxs-lookup"><span data-stu-id="12852-146">**Overflow percentage**</span></span>

        <span data-ttu-id="12852-147">Ce champ définit le pourcentage de débordement de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="12852-147">This field defines the percentage at which the location overflows.</span></span>

        <span data-ttu-id="12852-148">Le travail sera disponible lorsque la somme de la quantité disponible à l’emplacement et la quantité de travail sont inférieures à ce pourcentage.</span><span class="sxs-lookup"><span data-stu-id="12852-148">Work will be available whenever the sum of the on-hand quantity in the location and the work quantity is below this percentage.</span></span> <span data-ttu-id="12852-149">Tout pourcentage de quantité de travail de réapprovisionnement supérieur à cette valeur sera bloqué et doit être débloqué manuellement.</span><span class="sxs-lookup"><span data-stu-id="12852-149">Any replenishment work quantity percentage above this value will be blocked and must be manually unblocked.</span></span>

        <span data-ttu-id="12852-150">Les limites de stockage sur site sont prises en compte lors du calcul du pourcentage de travail.</span><span class="sxs-lookup"><span data-stu-id="12852-150">Location stocking limits are considered when the work quantity percentage is calculated.</span></span> <span data-ttu-id="12852-151">Si aucune limite de stockage d’emplacement n’est définie, le pourcentage de quantité de travail est calculé par volume si les contraintes de volume sont définies pour le profil d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="12852-151">If no location stocking limits are defined, the work quantity percentage is calculated by volume if volume constraints are defined for the location profile.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="12852-152">Si vous utilisez les données de démonstration pour l’entité juridique **USMF** et que vous avez précédemment activé la fonctionnalité *Positionnement des contenants d’emplacement*, vous devez désactiver la fonction **Activer le positionnement des contenants** pour le profil d’emplacement **BULK-06** pour terminer les étapes mobiles dans l’exemple de scénario.</span><span class="sxs-lookup"><span data-stu-id="12852-152">If you're using the demo data for the **USMF** legal entity and previously turned on the *Location license plate positioning* feature, you must turn off the **Enable license plate positioning** setting for the **BULK-06** location profile to complete the mobile steps in the example scenario.</span></span>

### <a name="wave-step-code"></a><span data-ttu-id="12852-153">Code étape de vague</span><span class="sxs-lookup"><span data-stu-id="12852-153">Wave step code</span></span>

> [!NOTE]
> <span data-ttu-id="12852-154">Pour configurer un code d’étape de vague comme décrit ici, vous devrez peut-être d’abord utiliser la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer la fonctionnalité nommée *Code d’étape de vague à l’échelle de l’organisation*.</span><span class="sxs-lookup"><span data-stu-id="12852-154">To set up a wave step code as described here, you might first have to use [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn on the feature that is named *Organization wide wave step code*.</span></span>

1. <span data-ttu-id="12852-155">Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Codes étape de vague**.</span><span class="sxs-lookup"><span data-stu-id="12852-155">Go to **Warehouse Management \> Setup \> Waves \> Wave step codes**.</span></span>
1. <span data-ttu-id="12852-156">Sélectionnez **Nouveau** et définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="12852-156">Select **New**, and set the following values:</span></span>

    - <span data-ttu-id="12852-157">**Code étape de vague :** *Réappro.*</span><span class="sxs-lookup"><span data-stu-id="12852-157">**Wave step code:** *Replen*</span></span>
    - <span data-ttu-id="12852-158">**Description étape de vague :** *Réapprovisionnement*</span><span class="sxs-lookup"><span data-stu-id="12852-158">**Wave step description:** *Replenishment*</span></span>
    - <span data-ttu-id="12852-159">**Type étape de vague :** *Réapprovisionnement*</span><span class="sxs-lookup"><span data-stu-id="12852-159">**Wave step type:** *Replenishment*</span></span>

1. <span data-ttu-id="12852-160">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="12852-160">Select **Save**.</span></span>

### <a name="replenishment-template"></a><span data-ttu-id="12852-161">Modèle de réapprovisionnement</span><span class="sxs-lookup"><span data-stu-id="12852-161">Replenishment template</span></span>

<span data-ttu-id="12852-162">Les modèles de réapprovisionnement constituent un ensemble de règles contrôlant quand et comment un emplacement est réapprovisionné.</span><span class="sxs-lookup"><span data-stu-id="12852-162">Replenishment templates are a set of rules that control when and how a location is replenished.</span></span>

1. <span data-ttu-id="12852-163">Allez dans **Gestion des entrepôts \> Paramétrage \> Réapprovisionnement \> Modèles de réapprovisionnement**.</span><span class="sxs-lookup"><span data-stu-id="12852-163">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>
1. <span data-ttu-id="12852-164">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="12852-164">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="12852-165">Dans la section **Aperçu**, sélectionnez la ligne où le champ **Modèle de réapprovisionnement** est défini sur *Réapprovisionnement de la demande*.</span><span class="sxs-lookup"><span data-stu-id="12852-165">In the **Overview** section, select the line where the **Replenish template** field is set to *Demand replenish*.</span></span>
1. <span data-ttu-id="12852-166">Définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="12852-166">Set the following values:</span></span>

    - <span data-ttu-id="12852-167">**Code étape de vague :** *Réappro.*</span><span class="sxs-lookup"><span data-stu-id="12852-167">**Wave step code:** *Replen*</span></span>
    - <span data-ttu-id="12852-168">**Autoriser la demande de vague à utiliser des quantités non réservées :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="12852-168">**Allow wave demand to use unreserved quantities:** *Yes*</span></span>

1. <span data-ttu-id="12852-169">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="12852-169">Select **Save**.</span></span>

### <a name="wave-template"></a><span data-ttu-id="12852-170">Modèle de vague</span><span class="sxs-lookup"><span data-stu-id="12852-170">Wave template</span></span>

1. <span data-ttu-id="12852-171">Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.</span><span class="sxs-lookup"><span data-stu-id="12852-171">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="12852-172">Dans le volet gauche, définissez le champ **Type de modèle de vague** sur *Expédition*.</span><span class="sxs-lookup"><span data-stu-id="12852-172">In the left pane, set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="12852-173">Sélectionnez le modèle **61 Shipping** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="12852-173">Select template **61 Shipping** in the list.</span></span>
1. <span data-ttu-id="12852-174">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="12852-174">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="12852-175">Dans le raccourci **Général**, définissez l’option **Automatiser la libération du travail de réapprovisionnement** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="12852-175">On the **General** FastTab, set the **Automate replenishment work release** option to *Yes*.</span></span>

    <span data-ttu-id="12852-176">Définissez cette option sur *Oui* pour créer un travail de réapprovisionnement basé sur la demande et le libérer automatiquement.</span><span class="sxs-lookup"><span data-stu-id="12852-176">Set this option to *Yes* to create demand-based replenishment work and release it automatically.</span></span> <span data-ttu-id="12852-177">Vous devez ajouter la méthode de vague de réapprovisionnement au modèle de vague, puis créer un modèle de réapprovisionnement du type **Demande de vague**.</span><span class="sxs-lookup"><span data-stu-id="12852-177">You must add the replenishment wave method to the wave template and create a replenishment template of the **Wave demand** type.</span></span> <span data-ttu-id="12852-178">Paramétrez un modèle de réapprovisionnement sur la page **Modèles de réapprovisionnement**.</span><span class="sxs-lookup"><span data-stu-id="12852-178">Set up a replenishment template on the **Replenishment templates** page.</span></span> <span data-ttu-id="12852-179">Pour configurer un modèle de réapprovisionnement, vous devez ajouter la méthode de réapprovisionnement au modèle de vague.</span><span class="sxs-lookup"><span data-stu-id="12852-179">To set up a replenishment template, you must add the replenish method to the wave template.</span></span>

1. <span data-ttu-id="12852-180">Sur l’organisateur **Méthodes**, dans la colonne **Méthodes sélectionnées**, recherchez la ligne suivante :</span><span class="sxs-lookup"><span data-stu-id="12852-180">On the **Methods** FastTab, in the **Selected methods** column, find the following line:</span></span>

    - <span data-ttu-id="12852-181">**Nom de la méthode :** *réapprovisionner*</span><span class="sxs-lookup"><span data-stu-id="12852-181">**Method name:** *replenish*</span></span>
    - <span data-ttu-id="12852-182">**Nom :** *Réapprovisionnement*</span><span class="sxs-lookup"><span data-stu-id="12852-182">**Name:** *Replenishment*</span></span>

1. <span data-ttu-id="12852-183">Définissez le champ **Code d’étape de vague** pour cette ligne sur *Réappro.*.</span><span class="sxs-lookup"><span data-stu-id="12852-183">Set the **Wave step code** field for this line to *Replen*.</span></span>
1. <span data-ttu-id="12852-184">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="12852-184">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="12852-185">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="12852-185">Example scenario</span></span>

<span data-ttu-id="12852-186">Après avoir mis à disposition tous les exemples de données décrits précédemment et les avoir configurés, vous pouvez suivre ce scénario pour essayer la fonctionnalité *Réapprovisionnement sur la capacité de l’emplacement*.</span><span class="sxs-lookup"><span data-stu-id="12852-186">After you've made all the previously described sample data available and set it up, you can work through this scenario to try out the *Replenishment over location capacity* feature.</span></span> <span data-ttu-id="12852-187">Les valeurs affichées dans ce scénario supposent que vous travaillez avec les données de démonstration standard, que vous avez sélectionné l’entité juridique **USMF** et que vous avez préparé les exemples d’enregistrements décrits plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="12852-187">The values that are shown in this scenario assume that you're working with the standard demo data, that you selected the **USMF** legal entity, and that you prepared the sample records that are described earlier in this topic.</span></span> <span data-ttu-id="12852-188">Ce scénario sert également d’exemple pour indiquer comment la fonctionnalité peut être utilisée dans un cadre de production.</span><span class="sxs-lookup"><span data-stu-id="12852-188">This scenario also serves as an example that shows how the feature can be used in a production setting.</span></span>

### <a name="create-replenishment-work"></a><span data-ttu-id="12852-189">Créer un travail de réapprovisionnement</span><span class="sxs-lookup"><span data-stu-id="12852-189">Create replenishment work</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="12852-190">Créer une commande client 1</span><span class="sxs-lookup"><span data-stu-id="12852-190">Create sales order 1</span></span>

1. <span data-ttu-id="12852-191">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="12852-191">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="12852-192">Dans le volet Actions, sélectionnez **Nouveau** pour ouvrir une boîte de dialogue de création de commande client.</span><span class="sxs-lookup"><span data-stu-id="12852-192">On the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="12852-193">Dans la boîte de dialogue, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="12852-193">In the dialog box, set the following values:</span></span>

    - <span data-ttu-id="12852-194">**Compte client :** *US-007*</span><span class="sxs-lookup"><span data-stu-id="12852-194">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="12852-195">**Entrepôt :** *61*</span><span class="sxs-lookup"><span data-stu-id="12852-195">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="12852-196">Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="12852-196">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="12852-197">La nouvelle commande client est ouverte.</span><span class="sxs-lookup"><span data-stu-id="12852-197">The new sales order is opened.</span></span> <span data-ttu-id="12852-198">Elle comprend une nouvelle ligne vide sur l’organisateur **Lignes de commande client**.</span><span class="sxs-lookup"><span data-stu-id="12852-198">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="12852-199">Sur cette ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="12852-199">On this line, set the following values:</span></span>

    - <span data-ttu-id="12852-200">**Numéro d’article :** *T0100*</span><span class="sxs-lookup"><span data-stu-id="12852-200">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="12852-201">**Quantité :** *40*</span><span class="sxs-lookup"><span data-stu-id="12852-201">**Quantity:** *40*</span></span>

1. <span data-ttu-id="12852-202">Sur l’organisateur **Lignes de commande client**, sélectionnez **Stock \> Réservation**.</span><span class="sxs-lookup"><span data-stu-id="12852-202">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="12852-203">Sur la page **Réservation**, sélectionnez **Réserver un lot**.</span><span class="sxs-lookup"><span data-stu-id="12852-203">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="12852-204">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="12852-204">Close the page.</span></span>
1. <span data-ttu-id="12852-205">Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="12852-205">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="12852-206">Vous recevez des messages d’informations indiquant que l’ID de vague et l’ID d’expédition ont été créés.</span><span class="sxs-lookup"><span data-stu-id="12852-206">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="12852-207">Une vague de réapprovisionnement est également créée.</span><span class="sxs-lookup"><span data-stu-id="12852-207">A replenishment wave is also created.</span></span>

    <span data-ttu-id="12852-208">Vous recevez également un message d’avertissement indiquant : « L’ID de travail XXXX ne peut pas être débloqué, car le travail de réapprovisionnement n’est pas terminé. »</span><span class="sxs-lookup"><span data-stu-id="12852-208">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="create-sales-order-2"></a><span data-ttu-id="12852-209">Créer une commande client 2</span><span class="sxs-lookup"><span data-stu-id="12852-209">Create sales order 2</span></span>

1. <span data-ttu-id="12852-210">Sur la page **Toutes les commandes client**, dans le volet Actions, sélectionnez **Nouveau** pour ouvrir une boîte de dialogue de création de commande client.</span><span class="sxs-lookup"><span data-stu-id="12852-210">On the **All sales orders**, page, on the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="12852-211">Dans la boîte de dialogue, définissez la valeur suivante :</span><span class="sxs-lookup"><span data-stu-id="12852-211">In the dialog box, set the following value:</span></span>

    - <span data-ttu-id="12852-212">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="12852-212">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="12852-213">**Entrepôt :** *61*</span><span class="sxs-lookup"><span data-stu-id="12852-213">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="12852-214">Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="12852-214">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="12852-215">La nouvelle commande client est ouverte.</span><span class="sxs-lookup"><span data-stu-id="12852-215">The new sales order is opened.</span></span> <span data-ttu-id="12852-216">Elle comprend une nouvelle ligne vide sur l’organisateur **Lignes de commande client**.</span><span class="sxs-lookup"><span data-stu-id="12852-216">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="12852-217">Sur cette ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="12852-217">On this line, set the following values:</span></span>

    - <span data-ttu-id="12852-218">**Numéro d’article :** *T0100*</span><span class="sxs-lookup"><span data-stu-id="12852-218">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="12852-219">**Quantité :** *60*</span><span class="sxs-lookup"><span data-stu-id="12852-219">**Quantity:** *60*</span></span>

1. <span data-ttu-id="12852-220">Sur l’organisateur **Lignes de commande client**, sélectionnez **Stock \> Réservation**.</span><span class="sxs-lookup"><span data-stu-id="12852-220">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="12852-221">Sur la page **Réservation**, sélectionnez **Réserver un lot**.</span><span class="sxs-lookup"><span data-stu-id="12852-221">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="12852-222">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="12852-222">Close the page.</span></span>
1. <span data-ttu-id="12852-223">Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="12852-223">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="12852-224">Vous recevez des messages d’informations indiquant que l’ID de vague et l’ID d’expédition ont été créés.</span><span class="sxs-lookup"><span data-stu-id="12852-224">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="12852-225">Une vague de réapprovisionnement est également créée.</span><span class="sxs-lookup"><span data-stu-id="12852-225">A replenishment wave is also created.</span></span>

    <span data-ttu-id="12852-226">Vous recevez également un message d’avertissement indiquant : « L’ID de travail XXXX ne peut pas être débloqué, car le travail de réapprovisionnement n’est pas terminé. »</span><span class="sxs-lookup"><span data-stu-id="12852-226">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="create-sales-order-3"></a><span data-ttu-id="12852-227">Créer une commande client 3</span><span class="sxs-lookup"><span data-stu-id="12852-227">Create sales order 3</span></span>

1. <span data-ttu-id="12852-228">Sur la page **Toutes les commandes client**, dans le volet Actions, sélectionnez **Nouveau** pour ouvrir une boîte de dialogue de création de commande client.</span><span class="sxs-lookup"><span data-stu-id="12852-228">On the **All sales orders** page, on the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="12852-229">Dans la boîte de dialogue, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="12852-229">In the dialog box, set the following values:</span></span>

    - <span data-ttu-id="12852-230">**Compte client :** *US-004*</span><span class="sxs-lookup"><span data-stu-id="12852-230">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="12852-231">**Entrepôt :** *61*</span><span class="sxs-lookup"><span data-stu-id="12852-231">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="12852-232">Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="12852-232">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="12852-233">La nouvelle commande client est ouverte.</span><span class="sxs-lookup"><span data-stu-id="12852-233">The new sales order is opened.</span></span> <span data-ttu-id="12852-234">Elle comprend une nouvelle ligne vide sur l’organisateur **Lignes de commande client**.</span><span class="sxs-lookup"><span data-stu-id="12852-234">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="12852-235">Sur cette ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="12852-235">On this line, set the following values:</span></span>

    - <span data-ttu-id="12852-236">**Numéro d’article :** *T0100*</span><span class="sxs-lookup"><span data-stu-id="12852-236">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="12852-237">**Quantité :** *30*</span><span class="sxs-lookup"><span data-stu-id="12852-237">**Quantity:** *30*</span></span>

1. <span data-ttu-id="12852-238">Sur l’organisateur **Lignes de commande client**, sélectionnez **Stock \> Réservation**.</span><span class="sxs-lookup"><span data-stu-id="12852-238">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="12852-239">Sur la page **Réservation**, sélectionnez **Réserver un lot**.</span><span class="sxs-lookup"><span data-stu-id="12852-239">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="12852-240">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="12852-240">Close the page.</span></span>
1. <span data-ttu-id="12852-241">Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="12852-241">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="12852-242">Vous recevez des messages d’informations indiquant que l’ID de vague et l’ID d’expédition ont été créés.</span><span class="sxs-lookup"><span data-stu-id="12852-242">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="12852-243">Une vague de réapprovisionnement est également créée.</span><span class="sxs-lookup"><span data-stu-id="12852-243">A replenishment wave is also created.</span></span>

    <span data-ttu-id="12852-244">Vous recevez également un message d’avertissement indiquant : « L’ID de travail XXXX ne peut pas être débloqué, car le travail de réapprovisionnement n’est pas terminé. »</span><span class="sxs-lookup"><span data-stu-id="12852-244">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="view-work-details"></a><span data-ttu-id="12852-245">Afficher les détails du travail</span><span class="sxs-lookup"><span data-stu-id="12852-245">View work details</span></span>

1. <span data-ttu-id="12852-246">Accédez à **Gestion des entrepôts \> Travail \> Détails du travail**.</span><span class="sxs-lookup"><span data-stu-id="12852-246">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="12852-247">Dans la section **Aperçu**, filtrez la colonne **Entrepôt** pour l’entrepôt *61*.</span><span class="sxs-lookup"><span data-stu-id="12852-247">In the **Overview** section, filter the **Warehouse** column for warehouse *61*.</span></span>
1. <span data-ttu-id="12852-248">Vous devriez voir que sept ID de travail ont été créés pour les trois commandes client à la demande.</span><span class="sxs-lookup"><span data-stu-id="12852-248">You should see that seven work IDs were created for the three demand sales orders.</span></span>

    - <span data-ttu-id="12852-249">Trois des sept ID de travail ont une valeur de **Type d’ordre de travail** de *Réapprovisionnement* et quatre ont une valeur de **Type d’ordre de travail** de *Commandes client*.</span><span class="sxs-lookup"><span data-stu-id="12852-249">Three of the seven work IDs have a **Work order type** value of *Replenishment*, and four have a **Work order type** value of *Sales orders*.</span></span>
    - <span data-ttu-id="12852-250">Les trois ID de travail qui ont une valeur de **Type d’ordre de travail** de *Réapprovisionnement* ont les mêmes emplacements de *Prélèvement* et *Rangement* dans la section **Lignes** :</span><span class="sxs-lookup"><span data-stu-id="12852-250">All three work IDs that have a **Work order type** value of *Replenishment* have the same *Pick* and *Put* locations in the **Lines** section:</span></span>

        - <span data-ttu-id="12852-251">**Prélèvement :** *02A01R5S1B*</span><span class="sxs-lookup"><span data-stu-id="12852-251">**Pick:** *02A01R5S1B*</span></span>
        - <span data-ttu-id="12852-252">**Rangement :** *06A01R2S1B*</span><span class="sxs-lookup"><span data-stu-id="12852-252">**Put:** *06A01R2S1B*</span></span>

    - <span data-ttu-id="12852-253">Deux ID de travail ont été créés pour la commande client 1.</span><span class="sxs-lookup"><span data-stu-id="12852-253">Two work IDs were created for sales order 1.</span></span>

1. <span data-ttu-id="12852-254">Notez les ID de travail des commandes client.</span><span class="sxs-lookup"><span data-stu-id="12852-254">Make a note of the work IDs for the sales orders.</span></span>

<span data-ttu-id="12852-255">En fonction de vos quantités disponibles, les quantités de travail créées peuvent varier légèrement.</span><span class="sxs-lookup"><span data-stu-id="12852-255">Depending on your on-hand quantities, the work quantities that are created might vary slightly.</span></span> <span data-ttu-id="12852-256">Toutefois, dans l’ensemble, les en-têtes de travail créés doivent correspondre à cet exemple de scénario.</span><span class="sxs-lookup"><span data-stu-id="12852-256">However, overall, the work headers that are created should match this scenario example.</span></span>

#### <a name="on-hand-inventory-license-plate-id"></a><span data-ttu-id="12852-257">ID contenant du stock disponible</span><span class="sxs-lookup"><span data-stu-id="12852-257">On-hand inventory license plate ID</span></span>

<span data-ttu-id="12852-258">Plus tard dans ce scénario, vous utiliserez l’application d’entrepôt (ou un émulateur), où vous devez identifier le contenant pour terminer les scénarios de prélèvement et de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="12852-258">Later in this scenario, you will use the warehouse app (or an emulator), where you must identify the license plate to complete the picking and replenishment scenarios.</span></span>

<span data-ttu-id="12852-259">Pour trouver les ID de contenant dont vous aurez besoin ultérieurement, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="12852-259">To find the license plate IDs that you will need later, follow these steps.</span></span>

1. <span data-ttu-id="12852-260">Accédez à **Gestion des stocks \> Recherches et états \> Stock disponible**.</span><span class="sxs-lookup"><span data-stu-id="12852-260">Go to **Inventory management \> Inquiries and reports \> On-hand list**.</span></span>
1. <span data-ttu-id="12852-261">Sélectionnez le bouton **Afficher les filtres** pour ouvrir le volet des filtres.</span><span class="sxs-lookup"><span data-stu-id="12852-261">Select the **Show filters** button to open the filter pane.</span></span>
1. <span data-ttu-id="12852-262">Entrez les critères de filtrage suivants pour obtenir les contenants du scénario.</span><span class="sxs-lookup"><span data-stu-id="12852-262">Enter the following filtering criteria to get the license plates for the scenario.</span></span> <span data-ttu-id="12852-263">Utilisez le filtre *commence par*.</span><span class="sxs-lookup"><span data-stu-id="12852-263">Use the *begins with* filter.</span></span>

    - <span data-ttu-id="12852-264">**Numéro d’article :** *T0100*</span><span class="sxs-lookup"><span data-stu-id="12852-264">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="12852-265">**Entrepôt :** *61*</span><span class="sxs-lookup"><span data-stu-id="12852-265">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="12852-266">Sélectionnez **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="12852-266">Select **Apply**.</span></span>
1. <span data-ttu-id="12852-267">Dans le volet Actions, sélectionnez **Dimensions**.</span><span class="sxs-lookup"><span data-stu-id="12852-267">On the Action Pane, select **Dimensions**.</span></span>
1. <span data-ttu-id="12852-268">Dans la boîte de dialogue **Affichage des dimensions**, dans la section **Dimensions de stockage**, sélectionnez toutes les valeurs.</span><span class="sxs-lookup"><span data-stu-id="12852-268">In the **Dimensions display** dialog box, in the **Storage Dimensions** section, select all the values.</span></span>
1. <span data-ttu-id="12852-269">Dans la section **Transactions**, sélectionnez **Numéro d’article** et **Quantité \<\> 0**.</span><span class="sxs-lookup"><span data-stu-id="12852-269">In the **Transactions** section, select **Item number** and **Quantity \<\> 0**.</span></span>
1. <span data-ttu-id="12852-270">Lorsque vous avez terminé, sélectionnez **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="12852-270">When you've finished, select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="12852-271">La grille **Disponible** montre les numéros de contenants pour l’article *T0100* à chaque emplacement.</span><span class="sxs-lookup"><span data-stu-id="12852-271">The **On-hand** grid shows the license plate numbers for item *T0100* in each location.</span></span> <span data-ttu-id="12852-272">Notez le contenant qui se trouve à chaque emplacement, car vous aurez besoin de ces informations plus tard.</span><span class="sxs-lookup"><span data-stu-id="12852-272">Make a note of the license plate that is in each location, because you will need this information later.</span></span>
1. <span data-ttu-id="12852-273">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="12852-273">Close the page.</span></span>

### <a name="process-steps"></a><span data-ttu-id="12852-274">Étapes du processus</span><span class="sxs-lookup"><span data-stu-id="12852-274">Process steps</span></span>

<span data-ttu-id="12852-275">Vous effectuerez le réapprovisionnement de l’emplacement d’entrepôt pour les deux premiers ID de travail.</span><span class="sxs-lookup"><span data-stu-id="12852-275">You will perform the warehouse location replenishment for the first two work IDs.</span></span> <span data-ttu-id="12852-276">Les travaux du troisième réapprovisionnement seront bloqués jusqu’à ce que le niveau de stock dans le lieu de prélèvement tombe en dessous du seuil.</span><span class="sxs-lookup"><span data-stu-id="12852-276">Work on the third replenishment work will be blocked until the inventory level in the picking location falls below the threshold.</span></span>

#### <a name="replenishment"></a><span data-ttu-id="12852-277">Réapprovisionnement</span><span class="sxs-lookup"><span data-stu-id="12852-277">Replenishment</span></span>

1. <span data-ttu-id="12852-278">Connectez-vous à l’application d’entrepôt en tant qu’utilisateur de l’entrepôt *61*.</span><span class="sxs-lookup"><span data-stu-id="12852-278">Sign in to the warehouse app as a user in warehouse *61*.</span></span> <span data-ttu-id="12852-279">(Entrez *61* comme ID utilisateur et *1* comme mot de passe.)</span><span class="sxs-lookup"><span data-stu-id="12852-279">(Enter *61* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="12852-280">Allez dans **Stock \> Réapprovisionnement**.</span><span class="sxs-lookup"><span data-stu-id="12852-280">Go to **Inventory \> Replenishment**.</span></span>

    <span data-ttu-id="12852-281">Vous êtes invité à terminer le premier travail de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="12852-281">You're prompted to complete the first replenishment work.</span></span> <span data-ttu-id="12852-282">Le numéro d’article, la quantité et l’emplacement du prélèvement sont affichés.</span><span class="sxs-lookup"><span data-stu-id="12852-282">The item number, quantity, and location to pick from are shown.</span></span>

1. <span data-ttu-id="12852-283">Dans le champ **LP**, entrez le numéro de contenant de l’article à l’emplacement indiqué.</span><span class="sxs-lookup"><span data-stu-id="12852-283">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="12852-284">Sélectionnez le bouton **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="12852-284">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="12852-285">Le système génère un numéro de contenant cible pour le nouveau contenant de l’article prélevé.</span><span class="sxs-lookup"><span data-stu-id="12852-285">The system generates a target license plate number for the new license plate for the picked item.</span></span>

1. <span data-ttu-id="12852-286">Sélectionnez **OK** pour confirmer la valeur.</span><span class="sxs-lookup"><span data-stu-id="12852-286">Select **OK** to confirm the value.</span></span>

    <span data-ttu-id="12852-287">Un travail de mise en place est affiché qui demande à l’utilisateur de placer le contenant cible à l’emplacement de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="12852-287">Put work is shown that instructs the user to put the target license plate into the replenishment location.</span></span> <span data-ttu-id="12852-288">L’emplacement de *Rangement* devrait être **06A01R2S1B**.</span><span class="sxs-lookup"><span data-stu-id="12852-288">The *Put* location should be **06A01R2S1B**.</span></span>

1. <span data-ttu-id="12852-289">Confirmez les détails du rangement et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="12852-289">Confirm the put details, and select **OK**.</span></span>

    <span data-ttu-id="12852-290">Vous recevez un message « Travail terminé » et les détails de la prochaine tâche de prélèvement de réapprovisionnement sont affichés : le numéro d’article, la quantité et l’emplacement de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="12852-290">You receive a "Work Completed" message, and the details of the next replenishment pick task are shown: the item number, quantity, and location to pick from.</span></span> <span data-ttu-id="12852-291">L’emplacement de prélèvement sera le même que le premier emplacement de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="12852-291">The picking location will be the same as the first replenishment location.</span></span> <span data-ttu-id="12852-292">Par conséquent, le contenant aura le même ID de contenant que celui utilisé pour la première tâche de travail de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="12852-292">Therefore, the license plate will have the same license plate ID that was used for the first replenishment work task.</span></span>

1. <span data-ttu-id="12852-293">Répétez les étapes précédentes pour terminer le travail de réapprovisionnement pour la deuxième tâche de travail.</span><span class="sxs-lookup"><span data-stu-id="12852-293">Repeat the preceding steps to complete the replenishment work for the second work task.</span></span> <span data-ttu-id="12852-294">La quantité et le contenant cible seront différentes de la quantité et du contenant cible pour la première tâche de travail.</span><span class="sxs-lookup"><span data-stu-id="12852-294">The quantity and target license plate will differ from the quantity and target license plate for the first work task.</span></span>

<span data-ttu-id="12852-295">Une fois le second travail de réapprovisionnement terminé, vous recevez un message « Travail terminé ».</span><span class="sxs-lookup"><span data-stu-id="12852-295">After the second replenishment work is completed, you receive a "Work Completed" message.</span></span> <span data-ttu-id="12852-296">L’appareil mobile vous informe également qu’il n’y a pas de travail disponible, même s’il reste du travail de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="12852-296">The mobile device also informs you that there is no work available, even though some replenishment work remains.</span></span> <span data-ttu-id="12852-297">Ce problème se produit, car le travail de réapprovisionnement a un état de disponibilité de *Suspendu* et est donc marqué comme **Bloqué**.</span><span class="sxs-lookup"><span data-stu-id="12852-297">This behavior occurs because the replenishment work has an availability status of *Held* and is therefore marked as **Blocked**.</span></span>

<span data-ttu-id="12852-298">Le statut *Suspendu* a été déclenché, car le profil d’emplacement du lieu de prélèvement auquel le travail est affecté a une valeur de **Quantité de débordement** de *0,65 PL*.</span><span class="sxs-lookup"><span data-stu-id="12852-298">The *Held* status was triggered because the location profile for the picking location that the work is being assigned to has an **Overflow quantity** value of *0.65 PL*.</span></span> <span data-ttu-id="12852-299">Les deux tâches de réapprovisionnement précédentes ont rempli l’emplacement presque à sa limite de dépassement de capacité pour l’article *T0100*.</span><span class="sxs-lookup"><span data-stu-id="12852-299">The two previous replenishment work tasks filled the location almost to its overflow limit for item *T0100*.</span></span> <span data-ttu-id="12852-300">(La conversion d’unité pour l’article est de *1 PL = 100 unités*.) Par conséquent, les travaux de réapprovisionnement restants entraîneraient un dépassement de la limite de dépassement de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="12852-300">(The unit conversion for the item is *1 PL = 100 ea*.) Therefore, the remaining replenishment work would cause the location to exceed its overflow limit.</span></span>

<span data-ttu-id="12852-301">Jusqu’à ce qu’un stock suffisant soit sélectionné à partir de l’emplacement pour le ramener en dessous du seuil de validation du travail sur l’élément de menu de l’appareil mobile, ce travail de réapprovisionnement restera bloqué.</span><span class="sxs-lookup"><span data-stu-id="12852-301">Until enough inventory is picked from the location to bring it below the work release threshold on the mobile device menu item, this replenishment work will remain blocked.</span></span>

#### <a name="sales-order-pick"></a><span data-ttu-id="12852-302">Prélèvement de commande client</span><span class="sxs-lookup"><span data-stu-id="12852-302">Sales order pick</span></span>

<span data-ttu-id="12852-303">Avant que la tâche de travail de réapprovisionnement restante ne puisse être terminée, l’emplacement de prélèvement doit être épuisé à un niveau où le travail de réapprovisionnement restant peut être débloqué.</span><span class="sxs-lookup"><span data-stu-id="12852-303">Before the remaining replenishment work task can be completed, the picking location must be depleted of inventory to a level where the remaining replenishment work can be unblocked.</span></span> <span data-ttu-id="12852-304">En d’autres termes, la somme de la quantité de stock disponible dans l’emplacement et la quantité de réapprovisionnement ne peut pas dépasser la valeur de la **Quantité de débordement**.</span><span class="sxs-lookup"><span data-stu-id="12852-304">In other words, the sum of the quantity of on-hand inventory in the location and the replenishment quantity can't exceed the **Overflow quantity** value.</span></span> <span data-ttu-id="12852-305">Lorsque cette somme est inférieure à la quantité de débordement, le travail de réapprovisionnement restant sera débloqué.</span><span class="sxs-lookup"><span data-stu-id="12852-305">When this sum is less than the overflow quantity, the remaining replenishment work will be unblocked.</span></span>

1. <span data-ttu-id="12852-306">Connectez-vous à l’application d’entrepôt en tant qu’utilisateur de l’entrepôt *61*.</span><span class="sxs-lookup"><span data-stu-id="12852-306">Sign in to the warehouse app as a user in warehouse *61*.</span></span> <span data-ttu-id="12852-307">(Entrez *61* comme ID utilisateur et *1* comme mot de passe.)</span><span class="sxs-lookup"><span data-stu-id="12852-307">(Enter *61* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="12852-308">Allez à **Sortant \> Prélèvement des ventes**.</span><span class="sxs-lookup"><span data-stu-id="12852-308">Go to **Outbound \> Sales Picking**.</span></span>
1. <span data-ttu-id="12852-309">Saisissez le premier ID de travail pour la commande client 1.</span><span class="sxs-lookup"><span data-stu-id="12852-309">Enter the first work ID for sales order 1.</span></span>

    <span data-ttu-id="12852-310">Reportez-vous aux ID de travail des commandes client dont vous avez pris note précédemment, sur la page **Détails du travail**.</span><span class="sxs-lookup"><span data-stu-id="12852-310">Refer to the work IDs for sales orders that you made a note of earlier, on the **Work details** page.</span></span> <span data-ttu-id="12852-311">L’ID de travail que vous entrez ici générera un travail de prélèvement pour une quantité de 10 pièces à partir de deux emplacements distincts.</span><span class="sxs-lookup"><span data-stu-id="12852-311">The work ID that you enter here will generate pick work for a quantity of 10 ea from two separate locations.</span></span>

1. <span data-ttu-id="12852-312">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="12852-312">Select **OK**.</span></span>

    <span data-ttu-id="12852-313">La page des tâches **Commandes client : Prélèvement** affiche le numéro d’article, la quantité et l’emplacement de sélection pour le premier emplacement.</span><span class="sxs-lookup"><span data-stu-id="12852-313">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from for the first location.</span></span>

1. <span data-ttu-id="12852-314">Dans le champ **LP**, entrez le numéro de contenant de l’article à l’emplacement indiqué.</span><span class="sxs-lookup"><span data-stu-id="12852-314">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="12852-315">Sélectionnez le bouton **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="12852-315">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="12852-316">La page des tâches **Commandes client : Prélèvement** affiche le numéro d’article, la quantité et l’emplacement de prélèvement pour l’emplacement suivant.</span><span class="sxs-lookup"><span data-stu-id="12852-316">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from for the next location.</span></span>

1. <span data-ttu-id="12852-317">Dans le champ **LP**, entrez le numéro de contenant de l’article à l’emplacement indiqué.</span><span class="sxs-lookup"><span data-stu-id="12852-317">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="12852-318">Sélectionnez le bouton **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="12852-318">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="12852-319">La page **Commandes client : Rangement** vous demande de ranger les deux travaux de prélèvement terminés à l’emplacement de transfert sortant.</span><span class="sxs-lookup"><span data-stu-id="12852-319">The **Sales orders: Put** page instructs you to put away both the completed picking works to the outbound staging location.</span></span>

1. <span data-ttu-id="12852-320">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="12852-320">Select **OK**.</span></span>

    <span data-ttu-id="12852-321">Vous recevez un message « Travail terminé ».</span><span class="sxs-lookup"><span data-stu-id="12852-321">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="12852-322">Saisissez le second ID de travail pour la commande client 1.</span><span class="sxs-lookup"><span data-stu-id="12852-322">Enter the second work ID for sales order 1.</span></span>

    <span data-ttu-id="12852-323">Il n’y a qu’une seule tâche de prélèvement pour cet ID de travail.</span><span class="sxs-lookup"><span data-stu-id="12852-323">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="12852-324">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="12852-324">Select **OK**.</span></span>

    <span data-ttu-id="12852-325">La page des tâches **Commandes client : Prélèvement** affiche le numéro d’article, la quantité et l’emplacement de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="12852-325">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="12852-326">Dans le champ **LP**, entrez le numéro de contenant de l’article à l’emplacement indiqué.</span><span class="sxs-lookup"><span data-stu-id="12852-326">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="12852-327">Le contenant que vous spécifiez sera l’un des contenants générés par le système à partir des tâches de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="12852-327">The license plate that you specify will be one of the system-generated license plates from the replenishment work tasks.</span></span> <span data-ttu-id="12852-328">Pour vous assurer que vous saisissez le bon ID de contenant, vérifiez le stock sur la page **Stock disponible** pour l’article, l’emplacement et la quantité.</span><span class="sxs-lookup"><span data-stu-id="12852-328">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="12852-329">Sélectionnez le bouton **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="12852-329">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="12852-330">Confirmez les instructions de la tâche de rangement vers l’emplacement intermédiaire sortant.</span><span class="sxs-lookup"><span data-stu-id="12852-330">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="12852-331">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="12852-331">Select **OK**.</span></span>

    <span data-ttu-id="12852-332">Vous recevez un message « Travail terminé ».</span><span class="sxs-lookup"><span data-stu-id="12852-332">You receive a "Work Completed" message.</span></span>

<span data-ttu-id="12852-333">Le prélèvement de la commande client 2 est bloqué, car la tâche de réapprovisionnement à laquelle elle est liée n’est pas terminée.</span><span class="sxs-lookup"><span data-stu-id="12852-333">Sales order 2 is blocked from picking because the replenishment task that it's linked to isn't completed.</span></span> <span data-ttu-id="12852-334">Actuellement, il y a encore une quantité de 30 unités à l’emplacement de prélèvement et la quantité de réapprovisionnement pour la commande client 2 est de 60 unités.</span><span class="sxs-lookup"><span data-stu-id="12852-334">Currently, there is still a quantity of 30 ea in the picking location, and the replenishment quantity for sales order 2 is 60 ea.</span></span> <span data-ttu-id="12852-335">La somme du stock disponible et du stock de réapprovisionnement (90 unités) dépasse la quantité de débordement de 0,65 PL (ou 65 unités).</span><span class="sxs-lookup"><span data-stu-id="12852-335">The sum of the on-hand inventory and the replenishment inventory (90 ea) exceeds the overflow quantity of 0.65 PL (or 65 ea).</span></span> <span data-ttu-id="12852-336">Avant que le travail de réapprovisionnement puisse être terminé, la commande client 3 doit être prélevée.</span><span class="sxs-lookup"><span data-stu-id="12852-336">Before the replenishment work can be completed, sales order 3 must be picked.</span></span>

1. <span data-ttu-id="12852-337">Saisissez l’ID de travail pour la commande client 3.</span><span class="sxs-lookup"><span data-stu-id="12852-337">Enter the work ID for sales order 3.</span></span>

    <span data-ttu-id="12852-338">Il n’y a qu’une seule tâche de prélèvement pour cet ID de travail.</span><span class="sxs-lookup"><span data-stu-id="12852-338">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="12852-339">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="12852-339">Select **OK**.</span></span>

    <span data-ttu-id="12852-340">La page des tâches **Commandes client : Prélèvement** affiche le numéro d’article, la quantité et l’emplacement de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="12852-340">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="12852-341">Dans le champ **LP**, entrez le numéro de contenant de l’article à l’emplacement indiqué.</span><span class="sxs-lookup"><span data-stu-id="12852-341">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="12852-342">Le contenant que vous spécifiez sera l’un des contenants générés par le système à partir des tâches de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="12852-342">The license plate that you specify will be one of the system-generated license plates from the replenishment work tasks.</span></span> <span data-ttu-id="12852-343">Pour vous assurer que vous saisissez le bon ID de contenant, vérifiez le stock sur la page **Stock disponible** pour l’article, l’emplacement et la quantité.</span><span class="sxs-lookup"><span data-stu-id="12852-343">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="12852-344">Sélectionnez le bouton **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="12852-344">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="12852-345">Confirmez les instructions de la tâche de rangement vers l’emplacement intermédiaire sortant.</span><span class="sxs-lookup"><span data-stu-id="12852-345">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="12852-346">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="12852-346">Select **OK**.</span></span>

    <span data-ttu-id="12852-347">Vous recevez un message « Travail terminé ».</span><span class="sxs-lookup"><span data-stu-id="12852-347">You receive a "Work Completed" message.</span></span>

<span data-ttu-id="12852-348">Dès que la somme de la quantité disponible sur l’emplacement de prélèvement et de la quantité de réapprovisionnement est inférieure au seuil, vous pourrez traiter le travail de réapprovisionnement restant.</span><span class="sxs-lookup"><span data-stu-id="12852-348">As soon as the sum of the on-hand quantity in the picking location and the replenishment quantity is below the threshold, you will be able to process the remaining replenishment work.</span></span>

<span data-ttu-id="12852-349">Revenez à la page **Détails du travail** et notez que la disponibilité du travail de réapprovisionnement pour la partie finale du réapprovisionnement (pour la commande client 2) est *Ouverte*, car il y a maintenant suffisamment d’espace à l’emplacement pour accepter le réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="12852-349">Return to the **Work details** page, and notice that the replenishment work availability for the final piece of replenishment (for sales order 2) is *Open*, because there is now enough space in the location to accept the replenishment.</span></span>

<span data-ttu-id="12852-350">Vous pouvez désormais traiter ce travail de réapprovisionnement via l’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="12852-350">You can now process this replenishment work via the mobile device.</span></span>

1. <span data-ttu-id="12852-351">Allez dans **Stock \> Réapprovisionnement**.</span><span class="sxs-lookup"><span data-stu-id="12852-351">Go to **Inventory \> Replenishment**.</span></span>

    <span data-ttu-id="12852-352">Vous êtes invité à terminer le travail de réapprovisionnement restant.</span><span class="sxs-lookup"><span data-stu-id="12852-352">You're prompted to complete the remaining replenishment work.</span></span> <span data-ttu-id="12852-353">Le numéro d’article, la quantité et l’emplacement du prélèvement sont affichés.</span><span class="sxs-lookup"><span data-stu-id="12852-353">The item number, quantity, and location to pick from are shown.</span></span>

1. <span data-ttu-id="12852-354">Dans le champ **LP**, entrez le numéro de contenant de l’article à l’emplacement indiqué.</span><span class="sxs-lookup"><span data-stu-id="12852-354">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="12852-355">Sélectionnez le bouton **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="12852-355">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="12852-356">Le système génère un numéro de contenant cible pour le nouveau contenant de l’article prélevé.</span><span class="sxs-lookup"><span data-stu-id="12852-356">The system generates a target license plate number for the new license plate for the picked item.</span></span>

1. <span data-ttu-id="12852-357">Sélectionnez **OK** pour confirmer la valeur.</span><span class="sxs-lookup"><span data-stu-id="12852-357">Select **OK** to confirm the value.</span></span>

    <span data-ttu-id="12852-358">Un travail de mise en place est affiché qui demande à l’utilisateur de placer le contenant cible à l’emplacement de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="12852-358">Put work is shown that instructs the user to put the target license plate into the replenishment location.</span></span> <span data-ttu-id="12852-359">L’emplacement de *Rangement* devrait être **06A01R2S1B**.</span><span class="sxs-lookup"><span data-stu-id="12852-359">The *Put* location should be **06A01R2S1B**.</span></span>

1. <span data-ttu-id="12852-360">Confirmez les détails du rangement et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="12852-360">Confirm the put details, and select **OK**.</span></span>

    <span data-ttu-id="12852-361">Vous recevez les messages « Travail terminé » et « Aucun travail disponible ».</span><span class="sxs-lookup"><span data-stu-id="12852-361">You receive "Work Completed" and "No Work Available" messages.</span></span>

<span data-ttu-id="12852-362">Vous pouvez maintenant prélever la commande client 2.</span><span class="sxs-lookup"><span data-stu-id="12852-362">You can now pick sales order 2.</span></span> <span data-ttu-id="12852-363">Elle a été débloquée lorsque le travail de réapprovisionnement lié à la commande client a été terminé.</span><span class="sxs-lookup"><span data-stu-id="12852-363">It became unblocked when the replenishment work that is linked to the sales order was completed.</span></span>

1. <span data-ttu-id="12852-364">Saisissez l’ID de travail pour la commande client 2.</span><span class="sxs-lookup"><span data-stu-id="12852-364">Enter the work ID for sales order 2.</span></span>

    <span data-ttu-id="12852-365">Il n’y a qu’une seule tâche de prélèvement pour cet ID de travail.</span><span class="sxs-lookup"><span data-stu-id="12852-365">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="12852-366">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="12852-366">Select **OK**.</span></span>

    <span data-ttu-id="12852-367">La page des tâches **Commandes client : Prélèvement** affiche le numéro d’article, la quantité et l’emplacement de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="12852-367">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="12852-368">Dans le champ **LP**, entrez le numéro de contenant de l’article à l’emplacement indiqué.</span><span class="sxs-lookup"><span data-stu-id="12852-368">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="12852-369">Le contenant que vous spécifiez sera le contenant généré par le système à partir de la tâche de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="12852-369">The license plate that you specify will be the system-generated license plate from the replenishment work task.</span></span> <span data-ttu-id="12852-370">Pour vous assurer que vous saisissez le bon ID de contenant, vérifiez le stock sur la page **Stock disponible** pour l’article, l’emplacement et la quantité.</span><span class="sxs-lookup"><span data-stu-id="12852-370">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="12852-371">Sélectionnez le bouton **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="12852-371">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="12852-372">Confirmez les instructions de la tâche de rangement vers l’emplacement intermédiaire sortant.</span><span class="sxs-lookup"><span data-stu-id="12852-372">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="12852-373">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="12852-373">Select **OK**.</span></span>

    <span data-ttu-id="12852-374">Vous recevez un message « Travail terminé ».</span><span class="sxs-lookup"><span data-stu-id="12852-374">You receive a "Work Completed" message.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="12852-375">Remarques et conseils</span><span class="sxs-lookup"><span data-stu-id="12852-375">Notes and tips</span></span>

- <span data-ttu-id="12852-376">Cette fonctionnalité fonctionne avec tous les types de réapprovisionnement : demande de vague, min/max, demande de chargement et créneaux.</span><span class="sxs-lookup"><span data-stu-id="12852-376">This functionality works with all types of replenishment: wave demand, min/max, load demand, and slotting.</span></span>
- <span data-ttu-id="12852-377">Vous pouvez remplacer manuellement la disponibilité du travail de réapprovisionnement pour chaque en-tête de travail à partir de la page **Détails du travail** si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="12852-377">You can manually override the replenishment work availability for each work header from the **Work details** page if you want.</span></span>
- <span data-ttu-id="12852-378">Lorsque le système définit la disponibilité du travail de réapprovisionnement, il prend en compte tout stock qui se trouve déjà à l’emplacement avant la fin des travaux</span><span class="sxs-lookup"><span data-stu-id="12852-378">When the system sets the replenishment work availability, it considers any inventory that is already in the location before any work is completed</span></span>
- <span data-ttu-id="12852-379">Chaque travail de commande client est lié à un travail de réapprovisionnement spécifique.</span><span class="sxs-lookup"><span data-stu-id="12852-379">Each piece of sales order work is linked to a specific replenishment work.</span></span> <span data-ttu-id="12852-380">Il n’existe pas de fonctionnalité de disponibilité du travail de vente correspondante.</span><span class="sxs-lookup"><span data-stu-id="12852-380">There is no corresponding sales work availability functionality.</span></span>
