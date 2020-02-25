---
title: Configurer un canal en ligne
description: Cette rubrique décrit comment créer un canal en ligne dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9b7a2b8fd157df8b39e9e227d188a3802cacb4e3
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002425"
---
# <a name="set-up-an-online-channel"></a><span data-ttu-id="d6629-103">Configurer un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="d6629-103">Set up an online channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="d6629-104">Cette rubrique décrit comment créer un canal en ligne dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d6629-104">This topic describes how to create a new online channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d6629-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="d6629-105">Overview</span></span>

<span data-ttu-id="d6629-106">Dynamics 365 Commerce prend en charge plusieurs canaux de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="d6629-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="d6629-107">Ces canaux de vente au détail comprennent les magasins en ligne, les centres d'appels et les magasins de vente au détail (également appelés magasins traditionnels).</span><span class="sxs-lookup"><span data-stu-id="d6629-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="d6629-108">Les magasins en ligne donnent aux clients la possibilité d'acheter des produits dans le magasin en ligne du détaillant, en plus de ses magasins de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="d6629-108">Online stores give customers the option of purchasing products from the retailer's online store in addition to its retail stores.</span></span>

<span data-ttu-id="d6629-109">Pour créer un magasin en ligne dans Commerce, vous devez d'abord créer un canal en ligne.</span><span class="sxs-lookup"><span data-stu-id="d6629-109">To create an online store in Commerce, you must first create an online channel.</span></span> 

<span data-ttu-id="d6629-110">Avant de créer un nouveau canal en ligne, assurez-vous d'avoir rempli la [Configuration requise de paramétrage de canaux](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="d6629-110">Before you create a new online channel, ensure that you have completed the [Channel set up prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-online-channel"></a><span data-ttu-id="d6629-111">Créer et configurer un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="d6629-111">Create and configure a new online channel</span></span>

<span data-ttu-id="d6629-112">Pour créer et configurer un canal en ligne, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d6629-112">To create and configure a new online channel, follow these steps.</span></span>

1. <span data-ttu-id="d6629-113">Dans le volet de navigation, accédez à **Modules \> Canaux \> Magasins en ligne**.</span><span class="sxs-lookup"><span data-stu-id="d6629-113">In the navigation pane, go to **Modules \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="d6629-114">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d6629-114">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="d6629-115">Dans le champ **Nom**, fournissez un nom pour le nouveau canal.</span><span class="sxs-lookup"><span data-stu-id="d6629-115">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="d6629-116">Dans la liste déroulante **Entité juridique**, entrez l'entité juridique appropriée.</span><span class="sxs-lookup"><span data-stu-id="d6629-116">In the **Legal entity** drop-down, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="d6629-117">Dans la liste déroulante **Entrepôt**, entrez l'entrepôt approprié.</span><span class="sxs-lookup"><span data-stu-id="d6629-117">In the **Warehouse** drop-down, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="d6629-118">Dans le champ **Fuseau hoaraire du magasin**, sélectionnez le fuseau horaire adéquat.</span><span class="sxs-lookup"><span data-stu-id="d6629-118">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="d6629-119">Sélectionnez la devise adéquate dans le champ **Devise**.</span><span class="sxs-lookup"><span data-stu-id="d6629-119">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="d6629-120">Dans le champ **Client par défaut**, indiquez un client par défaut valide.</span><span class="sxs-lookup"><span data-stu-id="d6629-120">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="d6629-121">Dans le **Carnet d'adresses client**, fournissez un carnet d'adresses valide.</span><span class="sxs-lookup"><span data-stu-id="d6629-121">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="d6629-122">Dans le champ **Profil de la fonctionnalité**, sélectionnez un profil de fonctionnalité le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="d6629-122">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="d6629-123">Dans le champ **Profil de notification par e-mail**, fournissez un profil de notification par e-mail valide.</span><span class="sxs-lookup"><span data-stu-id="d6629-123">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="d6629-124">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d6629-124">On the action pane, select **Save**.</span></span>

<span data-ttu-id="d6629-125">L'image suivante montre la création d'un canal en ligne.</span><span class="sxs-lookup"><span data-stu-id="d6629-125">The following image shows the creation of a new online channel.</span></span>

![Nouveau canal en ligne](media/channel-setup-online-1.png)

<span data-ttu-id="d6629-127">L'image suivante présente un exemple de canal en ligne.</span><span class="sxs-lookup"><span data-stu-id="d6629-127">The following image shows an example online channel.</span></span>

![Exemple de canal en ligne](media/channel-setup-online-2.png)

## <a name="set-up-languages"></a><span data-ttu-id="d6629-129">Configurer les langues</span><span class="sxs-lookup"><span data-stu-id="d6629-129">Set up languages</span></span>

<span data-ttu-id="d6629-130">Si votre site de commerce électronique prend en charge plusieurs langues, développez la section **Langues** et ajoutez des langues, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="d6629-130">If your e-Commerce site will support multiple languages, expand the **Languages** section and add additional languages as needed.</span></span>

## <a name="set-up-payment-account"></a><span data-ttu-id="d6629-131">Configurer un compte de paiement</span><span class="sxs-lookup"><span data-stu-id="d6629-131">Set up payment account</span></span>

<span data-ttu-id="d6629-132">Depuis la section **Compte de paiement**, vous pouvez ajouter un fournisseur de paiement tiers.</span><span class="sxs-lookup"><span data-stu-id="d6629-132">From within the **Payment account** section, you can add a third-party payment provider.</span></span> <span data-ttu-id="d6629-133">Pour plus d'informations sur la configuration d'un connecteur de paiement Adyen, consultez [Connecteur de paiement Dynamics 365 pour Adyen](../retail/dev-itpro/adyen-connector.md).</span><span class="sxs-lookup"><span data-stu-id="d6629-133">For information on settting up an Adyen payment connector, see [Dynamics 365 Payment Connector for Adyen](../retail/dev-itpro/adyen-connector.md).</span></span>

## <a name="additional-channel-set-up"></a><span data-ttu-id="d6629-134">Paramétrage de canal supplémentaire</span><span class="sxs-lookup"><span data-stu-id="d6629-134">Additional channel set up</span></span>

<span data-ttu-id="d6629-135">Les tâches supplémentaires requises pour la configuration du canal en ligne comprennent la configuration des modes de paiement, des modes de livraison et l'affectation du groupe d'exécution.</span><span class="sxs-lookup"><span data-stu-id="d6629-135">Additional tasks required for online channel setup include setting up payment methods, modes of delivery, and the fulfillment group assignment.</span></span>

<span data-ttu-id="d6629-136">L'image suivante montre les options de configuration **Modes de livraison**, **Modes de paiement** et **Affectation du groupe d'exécution** de l'onglet **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="d6629-136">The following image shows **Modes of delivery**, **Payment methods**, and **Fulfillment group assignment** setup options on the **Set up** tab.</span></span>

![Actions supplémentaires de configuration de canal en ligne](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="d6629-138">paramétrer les modes de paiement ;</span><span class="sxs-lookup"><span data-stu-id="d6629-138">Set up payment methods</span></span>

<span data-ttu-id="d6629-139">Pour configurer des modes de paiement, pour chaque type de paiement pris en charge sur ce canal, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d6629-139">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="d6629-140">Dans le volet Actions, sélectionnez l'onglet **Configurer**, puis **Modes de paiement**.</span><span class="sxs-lookup"><span data-stu-id="d6629-140">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="d6629-141">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d6629-141">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="d6629-142">Dans le volet de navigation, sélectionnez un mode de paiement souhaité.</span><span class="sxs-lookup"><span data-stu-id="d6629-142">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="d6629-143">Dans la section **Général**, fournissez un **Nom de l'opération** et configurez tous les autres paramètres souhaités.</span><span class="sxs-lookup"><span data-stu-id="d6629-143">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="d6629-144">Configurez tous les autres paramètres requis pour le type de paiement.</span><span class="sxs-lookup"><span data-stu-id="d6629-144">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="d6629-145">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d6629-145">On the action pane, select **Save**.</span></span>

<span data-ttu-id="d6629-146">L'image suivante présente un exemple de mode de paiement au comptant.</span><span class="sxs-lookup"><span data-stu-id="d6629-146">The following image shows an example of a cash payment method.</span></span>

![Exemple de modes de paiement](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="d6629-148">Paramétrer des modes de livraison</span><span class="sxs-lookup"><span data-stu-id="d6629-148">Set up modes of delivery</span></span>

<span data-ttu-id="d6629-149">Vous pouvez voir les modes de livraison configurés en sélectionnant **Modes de livraison** dans l'onglet **Paramétrer** du **Volet Actions**.</span><span class="sxs-lookup"><span data-stu-id="d6629-149">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="d6629-150">Pour modifier ou ajouter un mode de livraison, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d6629-150">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="d6629-151">Dans le volet de navigation, accédez à **Modules \> Gestion des stocks \> Modes de livraison**.</span><span class="sxs-lookup"><span data-stu-id="d6629-151">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="d6629-152">Dans le volet Actions, sélectionnez **Nouveau** pour créer un mode de livraison ou sélectionnez un mode existant.</span><span class="sxs-lookup"><span data-stu-id="d6629-152">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="d6629-153">Dans la section **Canaux de vente au détail**, sélectionnez **Ajouter une ligne** pour ajouter le canal.</span><span class="sxs-lookup"><span data-stu-id="d6629-153">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="d6629-154">L'ajout de canaux à l'aide de nœuds d'organisation au lieu d'ajouter chaque canal individuellement peut rationaliser l'ajout de canaux.</span><span class="sxs-lookup"><span data-stu-id="d6629-154">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="d6629-155">L'image suivante présente un exemple de mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="d6629-155">The following image shows an example of a mode of delivery.</span></span>

![Paramétrer des modes de livraison](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="d6629-157">Paramétrer une affectation de groupe d'exécution</span><span class="sxs-lookup"><span data-stu-id="d6629-157">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="d6629-158">Pour paramétrer une affectation de groupe d'exécution, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d6629-158">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="d6629-159">Dans le volet Actions, sélectionnez l'onglet **Paramétrer**, puis **Affectation du groupe d'exécution**.</span><span class="sxs-lookup"><span data-stu-id="d6629-159">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="d6629-160">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d6629-160">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="d6629-161">Dans la liste déroulante **Groupe d'exécution**, sélectionnez un groupe d'exécution.</span><span class="sxs-lookup"><span data-stu-id="d6629-161">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="d6629-162">Dans la liste déroulante **Description**, entrez une description.</span><span class="sxs-lookup"><span data-stu-id="d6629-162">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="d6629-163">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d6629-163">On the action pane, select **Save**.</span></span>

<span data-ttu-id="d6629-164">L'image suivante montre un exemple de configuration d'affectation de groupe d'exécution.</span><span class="sxs-lookup"><span data-stu-id="d6629-164">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Configurer l'affectation du groupe d'exécution](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a><span data-ttu-id="d6629-166">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d6629-166">Additional resources</span></span>

[<span data-ttu-id="d6629-167">Présentation des canaux</span><span class="sxs-lookup"><span data-stu-id="d6629-167">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="d6629-168">Configuration requise pour le paramétrage de canaux</span><span class="sxs-lookup"><span data-stu-id="d6629-168">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="d6629-169">Paramétrer un canal de vente au détail</span><span class="sxs-lookup"><span data-stu-id="d6629-169">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="d6629-170">Paramétrer un canal de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="d6629-170">Set up a call center channel</span></span>](channel-setup-callcenter.md)

[<span data-ttu-id="d6629-171">Connecteur de paiement Dynamics 365 pour Adyen</span><span class="sxs-lookup"><span data-stu-id="d6629-171">Dynamics 365 Payment Connector for Adyen</span></span>](../retail/dev-itpro/adyen-connector.md)
