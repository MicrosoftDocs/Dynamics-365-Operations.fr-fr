---
title: Paramétrer un entrepôt
description: Cette rubrique décrit comment paramétrer un entrepôt à utiliser avec un nouveau canal dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 67c0bb169bee8a7ea90edb4db7233111a8ee6e34
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993651"
---
# <a name="warehouse-set-up"></a><span data-ttu-id="d39d9-103">Paramétrer un entrepôt</span><span class="sxs-lookup"><span data-stu-id="d39d9-103">Warehouse set up</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="d39d9-104">Cette rubrique décrit comment paramétrer un entrepôt à utiliser avec un nouveau canal dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d39d9-104">This topic describes how to set up a warehouse to be used with a new channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d39d9-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="d39d9-105">Overview</span></span>

<span data-ttu-id="d39d9-106">Chaque canal Commerce requiert un entrepôt configuré pour lui être associé.</span><span class="sxs-lookup"><span data-stu-id="d39d9-106">Each Commerce channel requires a configured warehouse to be associated with it.</span></span> <span data-ttu-id="d39d9-107">Les procédures suivantes fournissent la configuration minimale requise pour paramétrer un entrepôt pour un canal Commerce.</span><span class="sxs-lookup"><span data-stu-id="d39d9-107">The following procedures provide the minimum configuration required to set up a warehouse for a Commerce channel.</span></span> <span data-ttu-id="d39d9-108">Pour plus d'informations sur le paramétrage de l'entrepôt, veuillez consulter la [Vue d'ensemble de gestion des entrepôts](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="d39d9-108">For more information regarding warehouse setup, please see the [Warehouse management overview](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="configure-a-warehouse-site"></a><span data-ttu-id="d39d9-109">Configurer un site d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="d39d9-109">Configure a warehouse site</span></span>

<span data-ttu-id="d39d9-110">Avant de paramétrer un entrepôt, vous devez configurer un site d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="d39d9-110">Before setting up a warehouse, you need to configure a warehouse site.</span></span>

<span data-ttu-id="d39d9-111">Pour configurer un site d'entrepôt, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d39d9-111">To configure a warehouse site, follow these steps.</span></span>

1. <span data-ttu-id="d39d9-112">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Sites**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-112">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Sites**.</span></span>
1. <span data-ttu-id="d39d9-113">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="d39d9-114">Dans le champ **Site**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d39d9-114">In the **Site** field, enter a value.</span></span>
1. <span data-ttu-id="d39d9-115">Dans le champ **Nom**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d39d9-115">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="d39d9-116">Dans la section **Général**, définissez le **Fuseau horaire** adéquat.</span><span class="sxs-lookup"><span data-stu-id="d39d9-116">In the **General** section, set the appropriate **Time zone**.</span></span>
1. <span data-ttu-id="d39d9-117">Dans la section **Adresses**, entrez une adresse.</span><span class="sxs-lookup"><span data-stu-id="d39d9-117">In the **Addresses** section, enter an address.</span></span>
1. <span data-ttu-id="d39d9-118">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-118">On the action pane, select **Save**.</span></span>

<span data-ttu-id="d39d9-119">L'image suivante présente un exemple de site d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="d39d9-119">The following image shows an example warehouse site.</span></span>

![Exemple de site d'entrepôt](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a><span data-ttu-id="d39d9-121">Paramétrer un entrepôt</span><span class="sxs-lookup"><span data-stu-id="d39d9-121">Set up a warehouse</span></span>

<span data-ttu-id="d39d9-122">Pour paramétrer un entrepôt, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d39d9-122">To set up a warehouse, follow these steps.</span></span>

1. <span data-ttu-id="d39d9-123">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-123">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="d39d9-124">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-124">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="d39d9-125">Dans le champ **Entrepôt**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d39d9-125">In the **Warehouse** field, enter a value.</span></span>  <span data-ttu-id="d39d9-126">S'il s'agit d'un mappage 1:1 avec un magasin, envisagez d'utiliser le nom du magasin ou le nom d'un centre de distribution régional.</span><span class="sxs-lookup"><span data-stu-id="d39d9-126">If this is a 1:1 mapping to a store, consider using the store name or the name of a regional distribution center.</span></span>
1. <span data-ttu-id="d39d9-127">Dans le champ **Nom**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d39d9-127">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="d39d9-128">Dans la liste déroulante **Site**, sélectionnez un site d'entrepôt créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="d39d9-128">In the **Site** drop-down list, select the warehouse site created previously.</span></span>
1. <span data-ttu-id="d39d9-129">Dans le champ **Type**, sélectionnez **Par défaut**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-129">In the **Type** field, select **Default**.</span></span>
    - <span data-ttu-id="d39d9-130">Si vous souhaitez définir un **Entrepôt de contrôle**, vous devez d'abord suivre ces étapes pour créer un entrepôt supplémentaire dans lequel **Type** est réglé sur **Contrôle**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-130">If you want to set a **Quarantine warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Quarantine**.</span></span>
    - <span data-ttu-id="d39d9-131">Si vous souhaitez définir un **Entrepôt de transit**, vous devez d'abord suivre ces étapes pour créer un entrepôt supplémentaire dans lequel **Type** est réglé sur **Transit**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-131">If you want to set a **Transit warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Transit**.</span></span>
1. <span data-ttu-id="d39d9-132">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-132">On the action pane, select **Save**.</span></span>

## <a name="set-up-inventory-aisles"></a><span data-ttu-id="d39d9-133">Paramétrer les allées de stock</span><span class="sxs-lookup"><span data-stu-id="d39d9-133">Set up inventory aisles</span></span>

<span data-ttu-id="d39d9-134">Pour paramétrer des allées de stockage, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d39d9-134">To set up inventory aisles, follow these steps.</span></span>

1. <span data-ttu-id="d39d9-135">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Paramétrage d'emplacement \> Allées de stockage**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-135">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Location setup \> Inventory aisles**.</span></span>
1. <span data-ttu-id="d39d9-136">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-136">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="d39d9-137">Dans la liste déroulante **Entrepôt**, sélectionnez l'entrepôt créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="d39d9-137">In the **Warehouse** drop-down list, select the warehouse created previously.</span></span>
1. <span data-ttu-id="d39d9-138">Entrez un nom dans le champ **Allée** (par exemple « Déf »).</span><span class="sxs-lookup"><span data-stu-id="d39d9-138">In the **Aisle** field, enter a name (for example, "Def").</span></span>
1. <span data-ttu-id="d39d9-139">Entrez un nom dans le champ **Nom** (par exemple « Allée par défaut »).</span><span class="sxs-lookup"><span data-stu-id="d39d9-139">In the **Name** field, enter a name (for example, "Default aisle").</span></span>
1. <span data-ttu-id="d39d9-140">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-140">On the action pane, select **Save**.</span></span>

## <a name="set-up-warehouse-inventory-locations"></a><span data-ttu-id="d39d9-141">Paramétrer des emplacements de stockage d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="d39d9-141">Set up warehouse inventory locations</span></span>

<span data-ttu-id="d39d9-142">Pour paramétrer des emplacements de stockage d'entrepôt pour le stock standard, endommagé et retourné, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d39d9-142">To set up warehouse inventory locations for standard, damaged, and returned inventory, follow these steps.</span></span>

1. <span data-ttu-id="d39d9-143">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-143">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="d39d9-144">Sélectionnez l'entrepôt que vous avez précédemment créé.</span><span class="sxs-lookup"><span data-stu-id="d39d9-144">Select the warehouse you created previously.</span></span>
1. <span data-ttu-id="d39d9-145">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-145">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="d39d9-146">Dans le volet Actions, sélectionnez **Entrepôt**, puis sélectionnez **Emplacement de stockage**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-146">On the action pane, select **Warehouse**, and then select **Inventory location**.</span></span>
1. <span data-ttu-id="d39d9-147">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-147">On the action pane, select **New**.</span></span> <span data-ttu-id="d39d9-148">La liste déroulante **Entrepôt** devrait par défaut être celle de votre nouvel entrepôt.</span><span class="sxs-lookup"><span data-stu-id="d39d9-148">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="d39d9-149">Dans la zone **Allée**, entrez le nom de l'allée que vous avez spécifiée précédemment.</span><span class="sxs-lookup"><span data-stu-id="d39d9-149">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="d39d9-150">Paramétrez **Mise à jour manuelle** sur **Oui**</span><span class="sxs-lookup"><span data-stu-id="d39d9-150">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="d39d9-151">Dans la zone **Emplacement**, entrez le nom de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="d39d9-151">In the **Location** box, enter the name of the warehouse.</span></span>
    1. <span data-ttu-id="d39d9-152">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-152">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="d39d9-153">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-153">On the action pane, select **New**.</span></span>  <span data-ttu-id="d39d9-154">La liste déroulante **Entrepôt** devrait par défaut être celle de votre nouvel entrepôt.</span><span class="sxs-lookup"><span data-stu-id="d39d9-154">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="d39d9-155">Dans la zone **Allée**, entrez le nom de l'allée que vous avez spécifiée précédemment.</span><span class="sxs-lookup"><span data-stu-id="d39d9-155">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span>  
    1. <span data-ttu-id="d39d9-156">Paramétrez **Mise à jour manuelle** sur **Oui**</span><span class="sxs-lookup"><span data-stu-id="d39d9-156">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="d39d9-157">Dans la zone **Emplacement**, entrez « Endommagé ».</span><span class="sxs-lookup"><span data-stu-id="d39d9-157">In the **Location** box, enter "Damaged".</span></span>
    1. <span data-ttu-id="d39d9-158">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-158">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="d39d9-159">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-159">On the action pane, select **New**.</span></span>  <span data-ttu-id="d39d9-160">La liste déroulante **Entrepôt** devrait par défaut être celle de votre nouvel entrepôt.</span><span class="sxs-lookup"><span data-stu-id="d39d9-160">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="d39d9-161">Dans la zone **Allée**, entrez le nom de l'allée que vous avez spécifiée précédemment.</span><span class="sxs-lookup"><span data-stu-id="d39d9-161">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="d39d9-162">Paramétrez **Mise à jour manuelle** sur **Oui**</span><span class="sxs-lookup"><span data-stu-id="d39d9-162">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="d39d9-163">Dans la zone **Emplacement**, entrez « Retours ».</span><span class="sxs-lookup"><span data-stu-id="d39d9-163">In the **Location** box, enter "Returns".</span></span>
    1. <span data-ttu-id="d39d9-164">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-164">On the action pane, select **Save**.</span></span>
    
<span data-ttu-id="d39d9-165">L'image suivante montre une configuration de l'emplacement de stockage de l'entrepôt de San Francisco.</span><span class="sxs-lookup"><span data-stu-id="d39d9-165">The following image shows a San Francisco warehouse inventory location setup.</span></span>

![Exemple de configuration d'emplacement de stockage](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a><span data-ttu-id="d39d9-167">Paramétrage d'entrepôt complet</span><span class="sxs-lookup"><span data-stu-id="d39d9-167">Complete warehouse setup</span></span>

<span data-ttu-id="d39d9-168">Pour terminer le paramétrage de l'entrepôt, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d39d9-168">To complete warehouse setup, follow these steps.</span></span>

1. <span data-ttu-id="d39d9-169">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-169">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="d39d9-170">Sélectionnez l'entrepôt que vous avez précédemment créé.</span><span class="sxs-lookup"><span data-stu-id="d39d9-170">Select the warehouse you previously created.</span></span>
1. <span data-ttu-id="d39d9-171">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-171">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="d39d9-172">Sous **Gestion des entrepôts et des stocks** :</span><span class="sxs-lookup"><span data-stu-id="d39d9-172">Under **Inventory and warehouse management**:</span></span>
    1. <span data-ttu-id="d39d9-173">Paramétrez **Emplacement de réception par défaut** sur l'emplacement par défaut créé ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="d39d9-173">Set **Default receipt location** to the default location created above.</span></span>
    1. <span data-ttu-id="d39d9-174">Sélectionnez **Emplacement de sortie par défaut** sur l'emplacement par défaut créé ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="d39d9-174">Select **Default issue location** to the default location created above.</span></span>
1. <span data-ttu-id="d39d9-175">Sous la section **Adresses**, entrez une adresse d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="d39d9-175">Under the **Addresses** section, enter a warehouse address.</span></span>
1. <span data-ttu-id="d39d9-176">Sous la section **Vente au détail** :</span><span class="sxs-lookup"><span data-stu-id="d39d9-176">Under the **Retail** section:</span></span> 
    1. <span data-ttu-id="d39d9-177">Dans la zone **Emplacement de retour par défaut**, entrez l'emplacement de retour créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="d39d9-177">In the **Default return location** box, enter the returns location created previously.</span></span>
    1. <span data-ttu-id="d39d9-178">Paramétrez **Magasin** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-178">Set **Store** to **Yes**.</span></span>
    1. <span data-ttu-id="d39d9-179">Paramétrez **Poids** sur **1,00**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-179">Set **Weight** to **1.00**.</span></span> 
    1. <span data-ttu-id="d39d9-180">Dans la zone **Dimensions de stockage**, entrez l'emplacement par défaut créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="d39d9-180">In the **Storage Dimensions** box, enter the default location created previously.</span></span>
1. <span data-ttu-id="d39d9-181">Sous la section **Entrepôt**, paramétrez **Stock physique négatif** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-181">Under the **Warehouse** section, set **Physical negative inventory** to **Yes**.</span></span>
1. <span data-ttu-id="d39d9-182">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d39d9-182">On the action pane, select **Save**.</span></span>

<span data-ttu-id="d39d9-183">L'image suivante montre les détails d'un entrepôt configuré.</span><span class="sxs-lookup"><span data-stu-id="d39d9-183">The following image shows details for a configured warehouse.</span></span>

![Exemple d'entrepôt configuré](media/warehouse-sample.png)

## <a name="additional-resources"></a><span data-ttu-id="d39d9-185">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d39d9-185">Additional resources</span></span>

[<span data-ttu-id="d39d9-186">Vue d'ensemble de gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="d39d9-186">Warehouse management overview</span></span>](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="d39d9-187">Présentation des canaux</span><span class="sxs-lookup"><span data-stu-id="d39d9-187">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="d39d9-188">Conditions préalables au paramétrage du canal</span><span class="sxs-lookup"><span data-stu-id="d39d9-188">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="d39d9-189">Paramétrer un canal de vente au détail</span><span class="sxs-lookup"><span data-stu-id="d39d9-189">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="d39d9-190">Paramétrer un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="d39d9-190">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="d39d9-191">Paramétrer un canal de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="d39d9-191">Set up a call center channel</span></span>](channel-setup-callcenter.md)





