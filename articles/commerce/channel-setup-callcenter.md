---
title: Configurer un canal de centre d'appels
description: Cette rubrique décrit comment créer un canal de centre d'appels dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 6ec42ab920868f541eeac54556f4f24cb1efaa3a
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002448"
---
# <a name="set-up-a-call-center-channel"></a><span data-ttu-id="10461-103">Configurer un canal de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="10461-103">Set up a call center channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="10461-104">Cette rubrique décrit comment créer un canal de centre d'appels dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="10461-104">This topic describes how to create a new call center channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="10461-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="10461-105">Overview</span></span>

<span data-ttu-id="10461-106">Dans Dynamics 365 Commerce, un centre d'appels est un type de canal de vente au détail qui peut être défini dans l'application.</span><span class="sxs-lookup"><span data-stu-id="10461-106">In Dynamics 365 Commerce, a call center is a type of retail channel that can be defined in the application.</span></span> <span data-ttu-id="10461-107">La définition d'un canal pour vos entités de centre d'appels permet au système de lier des données spécifiques et des valeurs par défaut de traitement des commandes aux commandes client.</span><span class="sxs-lookup"><span data-stu-id="10461-107">Defining a channel for your call center entities allows the system to tie specific data and order processing defaults to sales orders.</span></span> <span data-ttu-id="10461-108">Une société peut définir plusieurs canaux pour les centres d'appels dans Commerce.</span><span class="sxs-lookup"><span data-stu-id="10461-108">A company can define multiple call center channels in Commerce.</span></span> 

<span data-ttu-id="10461-109">Avant de créer un centre d'appel, assurez-vous d'avoir rempli la [Configuration requise de paramétrage de canaux](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="10461-109">Before you create a new call center channel, ensure that you have completed the [Channel set up prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-call-center-channel"></a><span data-ttu-id="10461-110">Créer et configurer un centre d'appels</span><span class="sxs-lookup"><span data-stu-id="10461-110">Create and configure a new call center channel</span></span>

<span data-ttu-id="10461-111">Pour créer et configurer un centre d'appels, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="10461-111">To create and configure a new call center channel, follow these steps.</span></span>

1. <span data-ttu-id="10461-112">Dans le volet de navigation, accédez à **Modules \> Canaux \> Centre d'appels \> Tous les centres d'appels**.</span><span class="sxs-lookup"><span data-stu-id="10461-112">In the navigation pane, go to **Modules \> Channels \> Call centers \> All call centers**.</span></span>
1. <span data-ttu-id="10461-113">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="10461-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="10461-114">Dans le champ **Nom**, fournissez un nom pour le nouveau canal.</span><span class="sxs-lookup"><span data-stu-id="10461-114">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="10461-115">Sélectionnez l'**Entité juridique** adéquate dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="10461-115">Select the appropriate **Legal entity** from the drop down.</span></span>
1. <span data-ttu-id="10461-116">Sélectionnez l'emplacement **Entrepôt** adéquat dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="10461-116">Select the appropriate **Warehouse** location from the drop down.</span></span>
1. <span data-ttu-id="10461-117">Dans le champ **Client par défaut**, indiquez un client par défaut valide.</span><span class="sxs-lookup"><span data-stu-id="10461-117">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="10461-118">Dans le champ **Profil de notification par e-mail**, fournissez un profil de notification par e-mail valide.</span><span class="sxs-lookup"><span data-stu-id="10461-118">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="10461-119">Fournissez un code info **Prix manuel**.</span><span class="sxs-lookup"><span data-stu-id="10461-119">Provide a **Price override** info code.</span></span> <span data-ttu-id="10461-120">Notez que vous devrez peut-être d'abord créer un code info.</span><span class="sxs-lookup"><span data-stu-id="10461-120">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="10461-121">Fournissez un code info **Code de blocage**.</span><span class="sxs-lookup"><span data-stu-id="10461-121">Provide a **Hold code** info code.</span></span> <span data-ttu-id="10461-122">Notez que vous devrez peut-être d'abord créer un code info.</span><span class="sxs-lookup"><span data-stu-id="10461-122">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="10461-123">Fournissez un code info **Crédit**.</span><span class="sxs-lookup"><span data-stu-id="10461-123">Provide a **Credit** info code.</span></span> <span data-ttu-id="10461-124">Notez que vous devrez peut-être d'abord créer un code info.</span><span class="sxs-lookup"><span data-stu-id="10461-124">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="10461-125">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="10461-125">Select **Save**.</span></span>

<span data-ttu-id="10461-126">L'image suivante montre la création d'un canal de centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="10461-126">The following image shows the creation of a new call center channel.</span></span>

![Nouveau canal de centre d'appels](media/channel-setup-callcenter-1.png)

<span data-ttu-id="10461-128">L'image suivante présente un exemple de canal de centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="10461-128">The following image shows an example call center channel.</span></span>

![Exemple de canal de centre d'appels](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a><span data-ttu-id="10461-130">Configuration de canal supplémentaire</span><span class="sxs-lookup"><span data-stu-id="10461-130">Additional channel setup</span></span>

<span data-ttu-id="10461-131">Les tâches supplémentaires requises pour la configuration du canal de centre d'appels comprennent la configuration des modes de paiement et des modes de livraison.</span><span class="sxs-lookup"><span data-stu-id="10461-131">Additional tasks required for call center channel setup include setting up payment methods and modes of delivery.</span></span>

<span data-ttu-id="10461-132">L'image suivante montre les options de configuration **Modes de livraison** et **Modes de paiement** de l'onglet **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="10461-132">The following image shows **Modes of delivery** and **Payment methods** set up options on the **Set up** tab.</span></span>

![Actions supplémentaires de configuration de canal de centre d'appels](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="10461-134">paramétrer les modes de paiement ;</span><span class="sxs-lookup"><span data-stu-id="10461-134">Set up payment methods</span></span>

<span data-ttu-id="10461-135">Pour configurer des modes de paiement, pour chaque type de paiement pris en charge sur ce canal, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="10461-135">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="10461-136">Dans le volet Actions, sélectionnez l'onglet **Configurer**, puis **Modes de paiement**.</span><span class="sxs-lookup"><span data-stu-id="10461-136">On the action pane, select the **Set up** tab, and then select **Payment methods**.</span></span>
1. <span data-ttu-id="10461-137">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="10461-137">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="10461-138">Dans le volet de navigation, sélectionnez un mode de paiement souhaité.</span><span class="sxs-lookup"><span data-stu-id="10461-138">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="10461-139">Dans la section **Général**, fournissez un **Nom de l'opération** et configurez tous les autres paramètres souhaités.</span><span class="sxs-lookup"><span data-stu-id="10461-139">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="10461-140">Configurez tous les autres paramètres requis pour le type de paiement.</span><span class="sxs-lookup"><span data-stu-id="10461-140">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="10461-141">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="10461-141">On the action pane, select **Save**.</span></span>

<span data-ttu-id="10461-142">L'image suivante présente un exemple de mode de paiement au comptant.</span><span class="sxs-lookup"><span data-stu-id="10461-142">The following image shows an example of a cash payment method.</span></span>

![Exemple de modes de paiement](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="10461-144">Paramétrer des modes de livraison</span><span class="sxs-lookup"><span data-stu-id="10461-144">Set up modes of delivery</span></span>

<span data-ttu-id="10461-145">Vous pouvez voir les modes de livraison configurés en sélectionnant **Modes de livraison** dans l'onglet **Paramétrer** du **Volet Actions**.</span><span class="sxs-lookup"><span data-stu-id="10461-145">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="10461-146">Pour modifier ou ajouter un mode de livraison, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="10461-146">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="10461-147">Dans le volet de navigation, accédez à **Modules \> Gestion des stocks \> Modes de livraison**.</span><span class="sxs-lookup"><span data-stu-id="10461-147">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="10461-148">Dans le volet Actions, sélectionnez **Nouveau** pour créer un mode de livraison ou sélectionnez un mode existant.</span><span class="sxs-lookup"><span data-stu-id="10461-148">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="10461-149">Dans la section **Canaux de vente au détail**, sélectionnez **Ajouter une ligne** pour ajouter le canal.</span><span class="sxs-lookup"><span data-stu-id="10461-149">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="10461-150">L'ajout de canaux à l'aide de nœuds d'organisation au lieu d'ajouter chaque canal individuellement peut rationaliser l'ajout de canaux.</span><span class="sxs-lookup"><span data-stu-id="10461-150">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="10461-151">L'image suivante présente un exemple de mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="10461-151">The following image shows an example of a mode of delivery.</span></span>

![Paramétrer des modes de livraison](media/channel-setup-retail-7.png)

## <a name="additional-resources"></a><span data-ttu-id="10461-153">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="10461-153">Additional resources</span></span>

[<span data-ttu-id="10461-154">Configuration requise pour le paramétrage de canaux</span><span class="sxs-lookup"><span data-stu-id="10461-154">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="10461-155">Fonctionnalité de vente du centre d'appels</span><span class="sxs-lookup"><span data-stu-id="10461-155">Call center sales functionality</span></span>](call-center-functionality.md)

[<span data-ttu-id="10461-156">Configurer des options de traitement de commandes de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="10461-156">Set up call center order processing options</span></span>](set-up-order-processing-options.md)

[<span data-ttu-id="10461-157">Catalogues de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="10461-157">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="10461-158">Paramétrer et utiliser les alertes pour fraude</span><span class="sxs-lookup"><span data-stu-id="10461-158">Set up and work with fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="10461-159">Paramétrer des programmes périodiques pour les centres d'appels</span><span class="sxs-lookup"><span data-stu-id="10461-159">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)
