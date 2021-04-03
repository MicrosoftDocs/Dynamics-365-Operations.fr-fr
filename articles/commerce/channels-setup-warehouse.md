---
title: Paramétrer un entrepôt
description: Cette rubrique décrit comment paramétrer un entrepôt à utiliser avec un nouveau canal dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 772c7584549b30a34e371a7911131edc01214ed8
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477632"
---
# <a name="warehouse-set-up"></a><span data-ttu-id="a7932-103">Paramétrer un entrepôt</span><span class="sxs-lookup"><span data-stu-id="a7932-103">Warehouse set up</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a7932-104">Cette rubrique décrit comment paramétrer un entrepôt à utiliser avec un nouveau canal dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a7932-104">This topic describes how to set up a warehouse to be used with a new channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="a7932-105">Chaque canal Commerce requiert un entrepôt configuré pour lui être associé.</span><span class="sxs-lookup"><span data-stu-id="a7932-105">Each Commerce channel requires a configured warehouse to be associated with it.</span></span> <span data-ttu-id="a7932-106">Les procédures suivantes fournissent la configuration minimale requise pour paramétrer un entrepôt pour un canal Commerce.</span><span class="sxs-lookup"><span data-stu-id="a7932-106">The following procedures provide the minimum configuration required to set up a warehouse for a Commerce channel.</span></span> <span data-ttu-id="a7932-107">Pour plus d'informations sur le paramétrage de l'entrepôt, veuillez consulter la [Vue d'ensemble de gestion des entrepôts](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="a7932-107">For more information regarding warehouse setup, please see the [Warehouse management overview](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="configure-a-warehouse-site"></a><span data-ttu-id="a7932-108">Configurer un site d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="a7932-108">Configure a warehouse site</span></span>

<span data-ttu-id="a7932-109">Avant de paramétrer un entrepôt, vous devez configurer un site d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="a7932-109">Before setting up a warehouse, you need to configure a warehouse site.</span></span>

<span data-ttu-id="a7932-110">Pour configurer un site d'entrepôt, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a7932-110">To configure a warehouse site, follow these steps.</span></span>

1. <span data-ttu-id="a7932-111">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Sites**.</span><span class="sxs-lookup"><span data-stu-id="a7932-111">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Sites**.</span></span>
1. <span data-ttu-id="a7932-112">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a7932-112">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a7932-113">Dans le champ **Site**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a7932-113">In the **Site** field, enter a value.</span></span>
1. <span data-ttu-id="a7932-114">Dans le champ **Nom**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a7932-114">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="a7932-115">Dans la section **Général**, définissez le **Fuseau horaire** adéquat.</span><span class="sxs-lookup"><span data-stu-id="a7932-115">In the **General** section, set the appropriate **Time zone**.</span></span>
1. <span data-ttu-id="a7932-116">Dans la section **Adresses**, entrez une adresse.</span><span class="sxs-lookup"><span data-stu-id="a7932-116">In the **Addresses** section, enter an address.</span></span>
1. <span data-ttu-id="a7932-117">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a7932-117">On the action pane, select **Save**.</span></span>

<span data-ttu-id="a7932-118">L'image suivante présente un exemple de site d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="a7932-118">The following image shows an example warehouse site.</span></span>

![Exemple de site d'entrepôt](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a><span data-ttu-id="a7932-120">Paramétrer un entrepôt</span><span class="sxs-lookup"><span data-stu-id="a7932-120">Set up a warehouse</span></span>

<span data-ttu-id="a7932-121">Pour paramétrer un entrepôt, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a7932-121">To set up a warehouse, follow these steps.</span></span>

1. <span data-ttu-id="a7932-122">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="a7932-122">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="a7932-123">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a7932-123">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a7932-124">Dans le champ **Entrepôt**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a7932-124">In the **Warehouse** field, enter a value.</span></span>  <span data-ttu-id="a7932-125">S'il s'agit d'un mappage 1:1 avec un magasin, envisagez d'utiliser le nom du magasin ou le nom d'un centre de distribution régional.</span><span class="sxs-lookup"><span data-stu-id="a7932-125">If this is a 1:1 mapping to a store, consider using the store name or the name of a regional distribution center.</span></span>
1. <span data-ttu-id="a7932-126">Dans le champ **Nom**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a7932-126">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="a7932-127">Dans la liste déroulante **Site**, sélectionnez un site d'entrepôt créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="a7932-127">In the **Site** drop-down list, select the warehouse site created previously.</span></span>
1. <span data-ttu-id="a7932-128">Dans le champ **Type**, sélectionnez **Par défaut**.</span><span class="sxs-lookup"><span data-stu-id="a7932-128">In the **Type** field, select **Default**.</span></span>
    - <span data-ttu-id="a7932-129">Si vous souhaitez définir un **Entrepôt de contrôle**, vous devez d'abord suivre ces étapes pour créer un entrepôt supplémentaire dans lequel **Type** est réglé sur **Contrôle**.</span><span class="sxs-lookup"><span data-stu-id="a7932-129">If you want to set a **Quarantine warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Quarantine**.</span></span>
    - <span data-ttu-id="a7932-130">Si vous souhaitez définir un **Entrepôt de transit**, vous devez d'abord suivre ces étapes pour créer un entrepôt supplémentaire dans lequel **Type** est réglé sur **Transit**.</span><span class="sxs-lookup"><span data-stu-id="a7932-130">If you want to set a **Transit warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Transit**.</span></span>
1. <span data-ttu-id="a7932-131">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a7932-131">On the action pane, select **Save**.</span></span>

## <a name="set-up-inventory-aisles"></a><span data-ttu-id="a7932-132">Paramétrer les allées de stock</span><span class="sxs-lookup"><span data-stu-id="a7932-132">Set up inventory aisles</span></span>

<span data-ttu-id="a7932-133">Pour paramétrer des allées de stockage, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a7932-133">To set up inventory aisles, follow these steps.</span></span>

1. <span data-ttu-id="a7932-134">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Paramétrage d'emplacement \> Allées de stockage**.</span><span class="sxs-lookup"><span data-stu-id="a7932-134">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Location setup \> Inventory aisles**.</span></span>
1. <span data-ttu-id="a7932-135">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a7932-135">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a7932-136">Dans la liste déroulante **Entrepôt**, sélectionnez l'entrepôt créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="a7932-136">In the **Warehouse** drop-down list, select the warehouse created previously.</span></span>
1. <span data-ttu-id="a7932-137">Entrez un nom dans le champ **Allée** (par exemple « Déf »).</span><span class="sxs-lookup"><span data-stu-id="a7932-137">In the **Aisle** field, enter a name (for example, "Def").</span></span>
1. <span data-ttu-id="a7932-138">Entrez un nom dans le champ **Nom** (par exemple « Allée par défaut »).</span><span class="sxs-lookup"><span data-stu-id="a7932-138">In the **Name** field, enter a name (for example, "Default aisle").</span></span>
1. <span data-ttu-id="a7932-139">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a7932-139">On the action pane, select **Save**.</span></span>

## <a name="set-up-warehouse-inventory-locations"></a><span data-ttu-id="a7932-140">Paramétrer des emplacements de stockage d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="a7932-140">Set up warehouse inventory locations</span></span>

<span data-ttu-id="a7932-141">Pour paramétrer des emplacements de stockage d'entrepôt pour le stock standard, endommagé et retourné, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a7932-141">To set up warehouse inventory locations for standard, damaged, and returned inventory, follow these steps.</span></span>

1. <span data-ttu-id="a7932-142">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="a7932-142">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="a7932-143">Sélectionnez l'entrepôt que vous avez précédemment créé.</span><span class="sxs-lookup"><span data-stu-id="a7932-143">Select the warehouse you created previously.</span></span>
1. <span data-ttu-id="a7932-144">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="a7932-144">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="a7932-145">Dans le volet Actions, sélectionnez **Entrepôt**, puis sélectionnez **Emplacement de stockage**.</span><span class="sxs-lookup"><span data-stu-id="a7932-145">On the action pane, select **Warehouse**, and then select **Inventory location**.</span></span>
1. <span data-ttu-id="a7932-146">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a7932-146">On the action pane, select **New**.</span></span> <span data-ttu-id="a7932-147">La liste déroulante **Entrepôt** devrait par défaut être celle de votre nouvel entrepôt.</span><span class="sxs-lookup"><span data-stu-id="a7932-147">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="a7932-148">Dans la zone **Allée**, entrez le nom de l'allée que vous avez spécifiée précédemment.</span><span class="sxs-lookup"><span data-stu-id="a7932-148">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="a7932-149">Paramétrez **Mise à jour manuelle** sur **Oui**</span><span class="sxs-lookup"><span data-stu-id="a7932-149">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="a7932-150">Dans la zone **Emplacement**, entrez le nom de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="a7932-150">In the **Location** box, enter the name of the warehouse.</span></span>
    1. <span data-ttu-id="a7932-151">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a7932-151">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="a7932-152">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a7932-152">On the action pane, select **New**.</span></span>  <span data-ttu-id="a7932-153">La liste déroulante **Entrepôt** devrait par défaut être celle de votre nouvel entrepôt.</span><span class="sxs-lookup"><span data-stu-id="a7932-153">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="a7932-154">Dans la zone **Allée**, entrez le nom de l'allée que vous avez spécifiée précédemment.</span><span class="sxs-lookup"><span data-stu-id="a7932-154">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span>  
    1. <span data-ttu-id="a7932-155">Paramétrez **Mise à jour manuelle** sur **Oui**</span><span class="sxs-lookup"><span data-stu-id="a7932-155">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="a7932-156">Dans la zone **Emplacement**, entrez « Endommagé ».</span><span class="sxs-lookup"><span data-stu-id="a7932-156">In the **Location** box, enter "Damaged".</span></span>
    1. <span data-ttu-id="a7932-157">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a7932-157">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="a7932-158">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a7932-158">On the action pane, select **New**.</span></span>  <span data-ttu-id="a7932-159">La liste déroulante **Entrepôt** devrait par défaut être celle de votre nouvel entrepôt.</span><span class="sxs-lookup"><span data-stu-id="a7932-159">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="a7932-160">Dans la zone **Allée**, entrez le nom de l'allée que vous avez spécifiée précédemment.</span><span class="sxs-lookup"><span data-stu-id="a7932-160">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="a7932-161">Paramétrez **Mise à jour manuelle** sur **Oui**</span><span class="sxs-lookup"><span data-stu-id="a7932-161">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="a7932-162">Dans la zone **Emplacement**, entrez « Retours ».</span><span class="sxs-lookup"><span data-stu-id="a7932-162">In the **Location** box, enter "Returns".</span></span>
    1. <span data-ttu-id="a7932-163">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a7932-163">On the action pane, select **Save**.</span></span>
    
<span data-ttu-id="a7932-164">L'image suivante montre une configuration de l'emplacement de stockage de l'entrepôt de San Francisco.</span><span class="sxs-lookup"><span data-stu-id="a7932-164">The following image shows a San Francisco warehouse inventory location setup.</span></span>

![Exemple de configuration d'emplacement de stockage](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a><span data-ttu-id="a7932-166">Paramétrage d'entrepôt complet</span><span class="sxs-lookup"><span data-stu-id="a7932-166">Complete warehouse setup</span></span>

<span data-ttu-id="a7932-167">Pour terminer le paramétrage de l'entrepôt, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a7932-167">To complete warehouse setup, follow these steps.</span></span>

1. <span data-ttu-id="a7932-168">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="a7932-168">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="a7932-169">Sélectionnez l'entrepôt que vous avez précédemment créé.</span><span class="sxs-lookup"><span data-stu-id="a7932-169">Select the warehouse you previously created.</span></span>
1. <span data-ttu-id="a7932-170">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="a7932-170">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="a7932-171">Sous **Gestion des entrepôts et des stocks** :</span><span class="sxs-lookup"><span data-stu-id="a7932-171">Under **Inventory and warehouse management**:</span></span>
    1. <span data-ttu-id="a7932-172">Paramétrez **Emplacement de réception par défaut** sur l'emplacement par défaut créé ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="a7932-172">Set **Default receipt location** to the default location created above.</span></span>
    1. <span data-ttu-id="a7932-173">Sélectionnez **Emplacement de sortie par défaut** sur l'emplacement par défaut créé ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="a7932-173">Select **Default issue location** to the default location created above.</span></span>
1. <span data-ttu-id="a7932-174">Sous la section **Adresses**, entrez une adresse d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="a7932-174">Under the **Addresses** section, enter a warehouse address.</span></span>
1. <span data-ttu-id="a7932-175">Sous la section **Vente au détail** :</span><span class="sxs-lookup"><span data-stu-id="a7932-175">Under the **Retail** section:</span></span> 
    1. <span data-ttu-id="a7932-176">Dans la zone **Emplacement de retour par défaut**, entrez l'emplacement de retour créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="a7932-176">In the **Default return location** box, enter the returns location created previously.</span></span>
    1. <span data-ttu-id="a7932-177">Paramétrez **Magasin** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="a7932-177">Set **Store** to **Yes**.</span></span>
    1. <span data-ttu-id="a7932-178">Paramétrez **Poids** sur **1,00**.</span><span class="sxs-lookup"><span data-stu-id="a7932-178">Set **Weight** to **1.00**.</span></span> 
    1. <span data-ttu-id="a7932-179">Dans la zone **Dimensions de stockage**, entrez l'emplacement par défaut créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="a7932-179">In the **Storage Dimensions** box, enter the default location created previously.</span></span>
1. <span data-ttu-id="a7932-180">Sous la section **Entrepôt**, paramétrez **Stock physique négatif** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="a7932-180">Under the **Warehouse** section, set **Physical negative inventory** to **Yes**.</span></span>
1. <span data-ttu-id="a7932-181">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a7932-181">On the action pane, select **Save**.</span></span>

<span data-ttu-id="a7932-182">L'image suivante montre les détails d'un entrepôt configuré.</span><span class="sxs-lookup"><span data-stu-id="a7932-182">The following image shows details for a configured warehouse.</span></span>

![Exemple d'entrepôt configuré](media/warehouse-sample.png)

## <a name="additional-resources"></a><span data-ttu-id="a7932-184">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="a7932-184">Additional resources</span></span>

[<span data-ttu-id="a7932-185">Vue d'ensemble de gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="a7932-185">Warehouse management overview</span></span>](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="a7932-186">Présentation des canaux</span><span class="sxs-lookup"><span data-stu-id="a7932-186">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="a7932-187">Conditions préalables au paramétrage du canal</span><span class="sxs-lookup"><span data-stu-id="a7932-187">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="a7932-188">Paramétrer un canal de vente au détail</span><span class="sxs-lookup"><span data-stu-id="a7932-188">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="a7932-189">Paramétrer un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="a7932-189">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="a7932-190">Paramétrer un canal de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="a7932-190">Set up a call center channel</span></span>](channel-setup-callcenter.md)







[!INCLUDE[footer-include](../includes/footer-banner.md)]
