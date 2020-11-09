---
title: Configurer un canal en ligne
description: Cette rubrique décrit comment créer un canal en ligne dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 07/02/2020
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
ms.openlocfilehash: 07225d97af76ea665fa28362cc205c6e8dc4fdf4
ms.sourcegitcommit: 776758a0ff95c3c7398986095104d1d2b9814514
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2020
ms.locfileid: "4107228"
---
# <a name="set-up-an-online-channel"></a><span data-ttu-id="14a5a-103">Configurer un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="14a5a-103">Set up an online channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="14a5a-104">Cette rubrique décrit comment créer un canal en ligne dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="14a5a-104">This topic describes how to create a new online channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="14a5a-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="14a5a-105">Overview</span></span>

<span data-ttu-id="14a5a-106">Dynamics 365 Commerce prend en charge plusieurs canaux de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="14a5a-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="14a5a-107">Ces canaux de vente au détail comprennent les magasins en ligne, les centres d'appels et les magasins de vente au détail (également appelés magasins traditionnels).</span><span class="sxs-lookup"><span data-stu-id="14a5a-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="14a5a-108">Les magasins en ligne donnent aux clients la possibilité d'acheter des produits dans le magasin en ligne du détaillant, en plus de ses magasins de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="14a5a-108">Online stores give customers the option of purchasing products from the retailer's online store in addition to its retail stores.</span></span>

<span data-ttu-id="14a5a-109">Pour créer un magasin en ligne dans Commerce, vous devez d'abord créer un canal en ligne.</span><span class="sxs-lookup"><span data-stu-id="14a5a-109">To create an online store in Commerce, you must first create an online channel.</span></span> <span data-ttu-id="14a5a-110">Avant de créer un nouveau canal en ligne, assurez-vous d'avoir rempli la [Configuration requise de paramétrage de canaux](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="14a5a-110">Before you create a new online channel, ensure that you have completed the [Channel set up prerequisites](channels-prerequisites.md).</span></span>

<span data-ttu-id="14a5a-111">Avant de pouvoir créer un site, au moins un magasin en ligne doit être créé dans Commerce.</span><span class="sxs-lookup"><span data-stu-id="14a5a-111">Before you can create a new site, at least one online store must be created in Commerce.</span></span> <span data-ttu-id="14a5a-112">Pour plus d'informations, voir [Créer un site de commerce électronique](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="14a5a-112">For more information, see [Create an e-Commerce site](create-ecommerce-site.md).</span></span>

## <a name="create-and-configure-a-new-online-channel"></a><span data-ttu-id="14a5a-113">Créer et configurer un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="14a5a-113">Create and configure a new online channel</span></span>

<span data-ttu-id="14a5a-114">Pour créer et configurer un canal en ligne, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="14a5a-114">To create and configure a new online channel, follow these steps.</span></span>

1. <span data-ttu-id="14a5a-115">Dans le volet de navigation, accédez à **Modules \> Canaux \> Magasins en ligne**.</span><span class="sxs-lookup"><span data-stu-id="14a5a-115">In the navigation pane, go to **Modules \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="14a5a-116">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="14a5a-116">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="14a5a-117">Dans le champ **Nom** , fournissez un nom pour le nouveau canal.</span><span class="sxs-lookup"><span data-stu-id="14a5a-117">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="14a5a-118">Dans la liste déroulante  **Entité juridique** , entrez l'entité juridique appropriée.</span><span class="sxs-lookup"><span data-stu-id="14a5a-118">In the **Legal entity** drop-down, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="14a5a-119">Dans la liste déroulante  **Entrepôt** , entrez l'entrepôt approprié.</span><span class="sxs-lookup"><span data-stu-id="14a5a-119">In the **Warehouse** drop-down, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="14a5a-120">Dans le champ **Fuseau hoaraire du magasin** , sélectionnez le fuseau horaire adéquat.</span><span class="sxs-lookup"><span data-stu-id="14a5a-120">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="14a5a-121">Sélectionnez la devise adéquate dans le champ **Devise**.</span><span class="sxs-lookup"><span data-stu-id="14a5a-121">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="14a5a-122">Dans le champ  **Client par défaut** , indiquez un client par défaut valide.</span><span class="sxs-lookup"><span data-stu-id="14a5a-122">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="14a5a-123">Dans le **Carnet d'adresses client** , fournissez un carnet d'adresses valide.</span><span class="sxs-lookup"><span data-stu-id="14a5a-123">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="14a5a-124">Dans le champ  **Profil de la fonctionnalité** , sélectionnez un profil de fonctionnalité le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="14a5a-124">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="14a5a-125">Dans le champ  **Profil de notification par e-mail** , fournissez un profil de notification par e-mail valide.</span><span class="sxs-lookup"><span data-stu-id="14a5a-125">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="14a5a-126">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="14a5a-126">On the action pane, select **Save**.</span></span>

<span data-ttu-id="14a5a-127">L'image suivante montre la création d'un canal en ligne.</span><span class="sxs-lookup"><span data-stu-id="14a5a-127">The following image shows the creation of a new online channel.</span></span>

![Nouveau canal en ligne](media/channel-setup-online-1.png)

<span data-ttu-id="14a5a-129">L'image suivante présente un exemple de canal en ligne.</span><span class="sxs-lookup"><span data-stu-id="14a5a-129">The following image shows an example online channel.</span></span>

![Exemple de canal en ligne](media/channel-setup-online-2.png)

## <a name="set-up-languages"></a><span data-ttu-id="14a5a-131">Configurer les langues</span><span class="sxs-lookup"><span data-stu-id="14a5a-131">Set up languages</span></span>

<span data-ttu-id="14a5a-132">Si votre site de commerce électronique prend en charge plusieurs langues, développez la section  **Langues** et ajoutez des langues, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="14a5a-132">If your e-Commerce site will support multiple languages, expand the **Languages** section and add additional languages as needed.</span></span>

## <a name="set-up-payment-account"></a><span data-ttu-id="14a5a-133">Configurer un compte de paiement</span><span class="sxs-lookup"><span data-stu-id="14a5a-133">Set up payment account</span></span>

<span data-ttu-id="14a5a-134">Depuis la section  **Compte de paiement** , vous pouvez ajouter un fournisseur de paiement tiers.</span><span class="sxs-lookup"><span data-stu-id="14a5a-134">From within the **Payment account** section, you can add a third-party payment provider.</span></span> <span data-ttu-id="14a5a-135">Pour plus d'informations sur la configuration d'un connecteur de paiement Adyen, consultez [Connecteur de paiement Dynamics 365 pour Adyen](../retail/dev-itpro/adyen-connector.md).</span><span class="sxs-lookup"><span data-stu-id="14a5a-135">For information on setting up an Adyen payment connector, see [Dynamics 365 Payment Connector for Adyen](../retail/dev-itpro/adyen-connector.md).</span></span>

## <a name="additional-channel-setup"></a><span data-ttu-id="14a5a-136">Configuration de canal supplémentaire</span><span class="sxs-lookup"><span data-stu-id="14a5a-136">Additional channel setup</span></span>

<span data-ttu-id="14a5a-137">Les tâches supplémentaires qui sont requises pour la configuration du canal en ligne comprennent la configuration des modes de paiement, des modes de livraison et l'affectation du groupe d'exécution.</span><span class="sxs-lookup"><span data-stu-id="14a5a-137">Additional tasks that are required for online channel setup include setting up payment methods, modes of delivery, and the fulfillment group assignment.</span></span>

<span data-ttu-id="14a5a-138">L'image suivante montre les options de configuration **Modes de livraison** , **Modes de paiement** et **Affectation du groupe d'exécution** de l'onglet  **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="14a5a-138">The following image shows **Modes of delivery** , **Payment methods** , and **Fulfillment group assignment** setup options on the **Set up** tab.</span></span>

![Actions supplémentaires de configuration de canal en ligne](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="14a5a-140">paramétrer les modes de paiement ;</span><span class="sxs-lookup"><span data-stu-id="14a5a-140">Set up payment methods</span></span>

<span data-ttu-id="14a5a-141">Pour configurer des modes de paiement, pour chaque type de paiement pris en charge sur ce canal, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="14a5a-141">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="14a5a-142">Dans le volet Actions, sélectionnez l'onglet  **Configurer** , puis **Modes de paiement**.</span><span class="sxs-lookup"><span data-stu-id="14a5a-142">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="14a5a-143">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="14a5a-143">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="14a5a-144">Dans le volet de navigation, sélectionnez un mode de paiement souhaité.</span><span class="sxs-lookup"><span data-stu-id="14a5a-144">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="14a5a-145">Dans la section  **Général** , fournissez un **Nom de l'opération** et configurez tous les autres paramètres souhaités.</span><span class="sxs-lookup"><span data-stu-id="14a5a-145">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="14a5a-146">Configurez tous les autres paramètres requis pour le type de paiement.</span><span class="sxs-lookup"><span data-stu-id="14a5a-146">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="14a5a-147">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="14a5a-147">On the action pane, select **Save**.</span></span>

<span data-ttu-id="14a5a-148">L'image suivante présente un exemple de mode de paiement au comptant.</span><span class="sxs-lookup"><span data-stu-id="14a5a-148">The following image shows an example of a cash payment method.</span></span>

![Exemple de modes de paiement](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="14a5a-150">Paramétrer des modes de livraison</span><span class="sxs-lookup"><span data-stu-id="14a5a-150">Set up modes of delivery</span></span>

<span data-ttu-id="14a5a-151">Vous pouvez voir les modes de livraison configurés en sélectionnant **Modes de livraison** dans l'onglet  **Paramétrer** du **Volet Actions**.</span><span class="sxs-lookup"><span data-stu-id="14a5a-151">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="14a5a-152">Pour modifier ou ajouter un mode de livraison, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="14a5a-152">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="14a5a-153">Dans le volet de navigation, accédez à **Modules \> Gestion des stocks \> Modes de livraison**.</span><span class="sxs-lookup"><span data-stu-id="14a5a-153">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="14a5a-154">Dans le volet Actions, sélectionnez **Nouveau** pour créer un mode de livraison ou sélectionnez un mode existant.</span><span class="sxs-lookup"><span data-stu-id="14a5a-154">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="14a5a-155">Dans la section  **Canaux de vente au détail** , sélectionnez **Ajouter une ligne** pour ajouter le canal.</span><span class="sxs-lookup"><span data-stu-id="14a5a-155">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="14a5a-156">L'ajout de canaux à l'aide de nœuds d'organisation au lieu d'ajouter chaque canal individuellement peut rationaliser l'ajout de canaux.</span><span class="sxs-lookup"><span data-stu-id="14a5a-156">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="14a5a-157">L'image suivante présente un exemple de mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="14a5a-157">The following image shows an example of a mode of delivery.</span></span>

![Paramétrer des modes de livraison](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="14a5a-159">Paramétrer une affectation de groupe d'exécution</span><span class="sxs-lookup"><span data-stu-id="14a5a-159">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="14a5a-160">Pour paramétrer une affectation de groupe d'exécution, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="14a5a-160">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="14a5a-161">Dans le volet Actions, sélectionnez l'onglet  **Paramétrer** , puis **Affectation du groupe d'exécution**.</span><span class="sxs-lookup"><span data-stu-id="14a5a-161">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="14a5a-162">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="14a5a-162">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="14a5a-163">Dans la liste déroulante **Groupe d'exécution** , sélectionnez un groupe d'exécution.</span><span class="sxs-lookup"><span data-stu-id="14a5a-163">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="14a5a-164">Dans la liste déroulante  **Description** , entrez une description.</span><span class="sxs-lookup"><span data-stu-id="14a5a-164">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="14a5a-165">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="14a5a-165">On the action pane, select **Save**.</span></span>

<span data-ttu-id="14a5a-166">L'image suivante montre un exemple de configuration d'affectation de groupe d'exécution.</span><span class="sxs-lookup"><span data-stu-id="14a5a-166">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Configurer l'affectation du groupe d'exécution](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a><span data-ttu-id="14a5a-168">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="14a5a-168">Additional resources</span></span>

[<span data-ttu-id="14a5a-169">Présentation des canaux</span><span class="sxs-lookup"><span data-stu-id="14a5a-169">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="14a5a-170">Configuration requise pour le paramétrage de canaux</span><span class="sxs-lookup"><span data-stu-id="14a5a-170">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="14a5a-171">Paramétrer un canal de vente au détail</span><span class="sxs-lookup"><span data-stu-id="14a5a-171">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="14a5a-172">Paramétrer un canal de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="14a5a-172">Set up a call center channel</span></span>](channel-setup-callcenter.md)

[<span data-ttu-id="14a5a-173">Connecteur de paiement Dynamics 365 pour Adyen</span><span class="sxs-lookup"><span data-stu-id="14a5a-173">Dynamics 365 Payment Connector for Adyen</span></span>](../retail/dev-itpro/adyen-connector.md)
