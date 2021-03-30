---
title: Configurer un canal de centre d'appels
description: Cette rubrique décrit comment créer un canal de centre d’appels dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 03/13/2020
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
ms.openlocfilehash: 878774c8e5485211525e7e7b63973173f6874b26
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218367"
---
# <a name="set-up-a-call-center-channel"></a><span data-ttu-id="487ed-103">Paramétrer un canal de centre d’appels</span><span class="sxs-lookup"><span data-stu-id="487ed-103">Set up a call center channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="487ed-104">Cette rubrique décrit comment créer un canal de centre d’appels dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="487ed-104">This topic describes how to create a new call center channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="487ed-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="487ed-105">Overview</span></span>


<span data-ttu-id="487ed-106">Dans Dynamics 365 Commerce, un centre d'appels est un type de canal Commerce qui peut être défini dans l'application.</span><span class="sxs-lookup"><span data-stu-id="487ed-106">In Dynamics 365 Commerce, a call center is a type of Commerce channel that can be defined in the application.</span></span> <span data-ttu-id="487ed-107">La définition d'un canal pour vos entités de centre d'appels permet au système de lier des données spécifiques et des valeurs par défaut de traitement des commandes aux commandes client.</span><span class="sxs-lookup"><span data-stu-id="487ed-107">Defining a channel for your call center entities allows the system to tie specific data and order processing defaults to sales orders.</span></span> <span data-ttu-id="487ed-108">Bien qu'une entreprise puisse définir plusieurs canaux de centre d'appels dans Commerce, il est important de noter qu'un utilisateur individuel ne peut pas être lié à un seul canal de centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="487ed-108">While a company can define multiple call center channels in Commerce, it is important to note that an individual user may only be linked to one call center channel.</span></span> 

<span data-ttu-id="487ed-109">Avant de créer un centre d'appel, assurez-vous d'avoir rempli la [Configuration requise de paramétrage de canaux](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="487ed-109">Before you create a new call center channel, ensure that you have completed the [Channel setup prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-call-center-channel"></a><span data-ttu-id="487ed-110">Créer et configurer un centre d'appels</span><span class="sxs-lookup"><span data-stu-id="487ed-110">Create and configure a new call center channel</span></span>

<span data-ttu-id="487ed-111">Pour créer et configurer un centre d'appels, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="487ed-111">To create and configure a new call center channel, follow these steps.</span></span>

1. <span data-ttu-id="487ed-112">Dans le volet de navigation, accédez à **Retail et Commerce \> Canaux \> Centres d'appels \> Tous les centres d'appels**.</span><span class="sxs-lookup"><span data-stu-id="487ed-112">In the navigation pane, go to **Retail and Commerce \> Channels \> Call centers \> All call centers**.</span></span>
1. <span data-ttu-id="487ed-113">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="487ed-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="487ed-114">Dans le champ **Nom**, fournissez un nom pour le nouveau canal.</span><span class="sxs-lookup"><span data-stu-id="487ed-114">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="487ed-115">Sélectionnez l'**Entité juridique** adéquate dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="487ed-115">Select the appropriate **Legal entity** from the drop-down.</span></span>
1. <span data-ttu-id="487ed-116">Sélectionnez l'emplacement **Entrepôt** adéquat dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="487ed-116">Select the appropriate **Warehouse** location from the drop-down.</span></span> <span data-ttu-id="487ed-117">Cet emplacement sera utilisé par défaut sur les commandes client créées pour ce canal de centre d'appels, sauf si d'autres valeurs par défaut ont été définies au niveau du client ou de l'article.</span><span class="sxs-lookup"><span data-stu-id="487ed-117">This location will be used as the default on sales orders created for this call center channel, unless other defaults have been defined at the customer or item level.</span></span>
1. <span data-ttu-id="487ed-118">Dans le champ **Client par défaut**, indiquez un client par défaut valide.</span><span class="sxs-lookup"><span data-stu-id="487ed-118">In the **Default customer** field, provide a valid default customer.</span></span> <span data-ttu-id="487ed-119">Ces données sont utilisées pour faciliter le remplissage automatique des valeurs par défaut lors de la création de nouveaux enregistrements client.</span><span class="sxs-lookup"><span data-stu-id="487ed-119">This data is used to assist in autopopulating defaults when new customer records are created.</span></span> <span data-ttu-id="487ed-120">Lors de la création de commandes de centre d'appels, il n'est pas conseillé de créer des commandes pour le client par défaut.</span><span class="sxs-lookup"><span data-stu-id="487ed-120">When creating call center orders, it is not advisable to create orders for the default customer.</span></span>
1. <span data-ttu-id="487ed-121">Dans le champ **Profil de notification par e-mail**, fournissez un profil de notification par e-mail valide.</span><span class="sxs-lookup"><span data-stu-id="487ed-121">In the **Email notification profile** field, provide a valid email notification profile.</span></span> <span data-ttu-id="487ed-122">Au fur et à mesure que les commandes du centre d'appels sont créées et traitées, le profil de notification par e-mail est utilisé pour déclencher des alertes par e-mail automatiques aux clients avec des informations sur l'état de leur commande.</span><span class="sxs-lookup"><span data-stu-id="487ed-122">As call center orders are created and processed, the email notification profile is used to trigger automated email alerts to customers with information about their order status.</span></span>
1. <span data-ttu-id="487ed-123">Fournissez un code info **Prix manuel**.</span><span class="sxs-lookup"><span data-stu-id="487ed-123">Provide a **Price override** info code.</span></span> <span data-ttu-id="487ed-124">Vous devrez peut-être d'abord créer un code info.</span><span class="sxs-lookup"><span data-stu-id="487ed-124">You may need to create an info code for this first.</span></span> <span data-ttu-id="487ed-125">Ce code info fournit l'ensemble des codes motif que l'utilisateur sera invité à choisir lors de l'utilisation de la fonctionnalité de substitution de prix sur une commande de centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="487ed-125">This info code provides the set of reason codes that the user will be prompted to choose from when using the price override functionality on a call center order.</span></span>
1. <span data-ttu-id="487ed-126">Fournissez un code info **Code de blocage**.</span><span class="sxs-lookup"><span data-stu-id="487ed-126">Provide a **Hold code** info code.</span></span> <span data-ttu-id="487ed-127">Vous devrez peut-être d'abord créer un code info.</span><span class="sxs-lookup"><span data-stu-id="487ed-127">You may need to create an info code for this first.</span></span> <span data-ttu-id="487ed-128">Ce code info fournit l'ensemble des codes motif en option que l'utilisateur sera invité à choisir lors du passage d'une commande en attente.</span><span class="sxs-lookup"><span data-stu-id="487ed-128">This info code provides the set of optional reason codes that the user will be prompted to choose from when placing an order on hold.</span></span>
1. <span data-ttu-id="487ed-129">Fournissez un code info **Crédit**.</span><span class="sxs-lookup"><span data-stu-id="487ed-129">Provide a **Credit** info code.</span></span> <span data-ttu-id="487ed-130">Vous devrez peut-être d'abord créer un code info.</span><span class="sxs-lookup"><span data-stu-id="487ed-130">You may need to create an info code for this first.</span></span> <span data-ttu-id="487ed-131">Ce code d'information fournit l'ensemble des codes de motif que l'utilisateur peut choisir lors de l'utilisation de la fonctionnalité de crédit de commande du centre d'appels pour donner des remboursements divers au client pour des raisons de service client.</span><span class="sxs-lookup"><span data-stu-id="487ed-131">This info code provides the set of reason codes that the user can choose from when using the order credit functionality of call center to give misc refunds to the customer for customer service reasons.</span></span>
1. <span data-ttu-id="487ed-132">En option : configurez les dimensions financières sur le raccourci **Dimensions financières**.</span><span class="sxs-lookup"><span data-stu-id="487ed-132">Optional: set up financial dimensions on the **Financial dimensions** FastTab.</span></span> <span data-ttu-id="487ed-133">Les dimensions saisies ici figureront par défaut sur n'importe quelle commande client créée dans ce canal de centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="487ed-133">The dimensions entered here will default on any sales order created in this call center channel.</span></span>
1. <span data-ttu-id="487ed-134">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="487ed-134">Click **Save**.</span></span>

<span data-ttu-id="487ed-135">L'image suivante montre la création d'un canal de centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="487ed-135">The following image shows the creation of a new call center channel.</span></span>

![Nouveau canal de centre d'appels](media/channel-setup-callcenter-1.png)

<span data-ttu-id="487ed-137">L'image suivante présente un exemple de canal de centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="487ed-137">The following image shows an example call center channel.</span></span>

![Exemple de canal de centre d'appels](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a><span data-ttu-id="487ed-139">Configuration de canal supplémentaire</span><span class="sxs-lookup"><span data-stu-id="487ed-139">Additional channel setup</span></span>

<span data-ttu-id="487ed-140">Les tâches supplémentaires requises pour la configuration du canal de centre d'appels comprennent la configuration des modes de paiement et des modes de livraison.</span><span class="sxs-lookup"><span data-stu-id="487ed-140">Additional tasks required for call center channel setup include setting up payment methods and modes of delivery.</span></span>

<span data-ttu-id="487ed-141">L'image suivante montre les options de configuration **Modes de livraison** et **Modes de paiement** de l'onglet **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="487ed-141">The following image shows **Modes of delivery** and **Payment methods** setup options on the **Set up** tab.</span></span>

![Actions supplémentaires de configuration de canal de centre d'appels](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="487ed-143">paramétrer les modes de paiement ;</span><span class="sxs-lookup"><span data-stu-id="487ed-143">Set up payment methods</span></span>

<span data-ttu-id="487ed-144">Pour configurer des modes de paiement, pour chaque type de paiement pris en charge sur ce canal, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="487ed-144">To set up payment methods, follow these steps for each payment type supported on this channel.</span></span> <span data-ttu-id="487ed-145">Les utilisateurs devront sélectionner des modes de paiement prédéfinis pour les lier au canal du centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="487ed-145">Users will be required to select from pre-defined payment methods to link them to the call center channel.</span></span> <span data-ttu-id="487ed-146">Avant de configurer vos modes de paiement de centre d'appels, configurez d'abord vos modes de paiement principaux dans **Retail et Commerce \>Configuration des canaux \> Modes de payement \> Modes de payement**.</span><span class="sxs-lookup"><span data-stu-id="487ed-146">Before setting up your call center payment methods, first set up your master methods of payment in **Retail and Commerce \> Channel setup \> Payment methods \> Payment methods**.</span></span>

1. <span data-ttu-id="487ed-147">Dans le volet Actions, sélectionnez l'onglet **Configurer**, puis **Modes de paiement**.</span><span class="sxs-lookup"><span data-stu-id="487ed-147">On the action pane, select the **Set up** tab, and then select **Payment methods**.</span></span>
1. <span data-ttu-id="487ed-148">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="487ed-148">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="487ed-149">Dans le volet de navigation, sélectionnez un mode de paiement parmi les paiements prédéfinis disponibles.</span><span class="sxs-lookup"><span data-stu-id="487ed-149">In the navigation pane, select a payment method from the pre-defined payments available.</span></span>
1. <span data-ttu-id="487ed-150">Configurez tous les autres paramètres requis pour le type de paiement.</span><span class="sxs-lookup"><span data-stu-id="487ed-150">Configure any additional settings as required for the payment type.</span></span> <span data-ttu-id="487ed-151">Pour les cartes de crédit, les cartes-cadeaux ou les cartes de fidélité, une configuration supplémentaire est requise en sélectionnant la fonction **Configuration de la carte**.</span><span class="sxs-lookup"><span data-stu-id="487ed-151">For credit cards, gift cards, or loyalty cards, additional setup is required by selecting the **Card setup** function.</span></span> 
1. <span data-ttu-id="487ed-152">Configurez les comptes de validation appropriés pour le type de paiement dans la section **Affectation**.</span><span class="sxs-lookup"><span data-stu-id="487ed-152">Configure proper posting accounts for the payment type in the **Posting** section.</span></span>
1. <span data-ttu-id="487ed-153">Dans le volet Actions, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="487ed-153">On the action pane, click **Save**.</span></span>

<span data-ttu-id="487ed-154">L'image suivante présente un exemple de mode de paiement au comptant.</span><span class="sxs-lookup"><span data-stu-id="487ed-154">The following image shows an example of a cash payment method.</span></span>

![Exemple de modes de paiement](media/channel-setup-callcenter-payments.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="487ed-156">Paramétrer des modes de livraison</span><span class="sxs-lookup"><span data-stu-id="487ed-156">Set up modes of delivery</span></span>

<span data-ttu-id="487ed-157">Vous pouvez voir les modes de livraison configurés en sélectionnant **Modes de livraison** dans l'onglet **Paramétrer** du **Volet Actions**.</span><span class="sxs-lookup"><span data-stu-id="487ed-157">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="487ed-158">Pour modifier ou ajouter un mode de livraison à associer au canal du centre d'appels, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="487ed-158">To change or add a mode of delivery to be associated to the call center channel, follow these steps.</span></span>

1. <span data-ttu-id="487ed-159">Dans le formulaire Modes de livraison du centre d'appels, sélectionnez **Gérer les modes de livraison**</span><span class="sxs-lookup"><span data-stu-id="487ed-159">From the Call center modes of delivery form, select **Manage modes of delivery**</span></span>
1. <span data-ttu-id="487ed-160">Dans le volet Actions, sélectionnez **Nouveau** pour créer un mode de livraison ou sélectionnez un mode existant.</span><span class="sxs-lookup"><span data-stu-id="487ed-160">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="487ed-161">Dans la section **Canaux de vente au détail**, cliquez sur **Ajouter une ligne** pour ajouter le canal du centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="487ed-161">In the **Retail channels** section, click **Add line** to add the call center channel.</span></span> <span data-ttu-id="487ed-162">L'ajout de canaux à l'aide de nœuds d'organisation au lieu d'ajouter chaque canal individuellement peut rationaliser l'ajout de canaux.</span><span class="sxs-lookup"><span data-stu-id="487ed-162">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>
1. <span data-ttu-id="487ed-163">Assurez-vous que le mode de livraison a été configuré avec des données sur le raccourci **Produits** et le raccourci **Adresses**.</span><span class="sxs-lookup"><span data-stu-id="487ed-163">Ensure the mode of delivery has been configured with data on the **Products** FastTab and the **Addresses** FastTab.</span></span> <span data-ttu-id="487ed-164">Si aucun produit ou aucune adresse de livraison n'est valide pour le mode de livraison, le choisir lors de la saisie de la commande entraînera des erreurs.</span><span class="sxs-lookup"><span data-stu-id="487ed-164">If no products or delivery addresses are valid for the mode of delivery, choosing it during order entry will result in errors.</span></span>
1. <span data-ttu-id="487ed-165">Une fois que les modifications ont été apportées aux configurations du mode de livraison du centre d'appels, la tâche **Traiter les modes de livraison** doit être exécutée pour faire exploser la matrice de changement.</span><span class="sxs-lookup"><span data-stu-id="487ed-165">After any changes have been made to the call center mode of delivery configurations, the **Process delivery modes** job must be run to explode the change matrix.</span></span> <span data-ttu-id="487ed-166">Ce travail peut être trouvé en accédant à **Retail et Commerce \> Retail et Commerce IT \> Traiter les modes de livraison**.</span><span class="sxs-lookup"><span data-stu-id="487ed-166">This job can be found by navigating to **Retail and Commerce \> Retail and Commerce IT \> Process delivery modes**.</span></span>

<span data-ttu-id="487ed-167">L'image suivante présente un exemple de mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="487ed-167">The following image shows an example of a mode of delivery.</span></span>

![Paramétrer des modes de livraison](media/channel-setup-retail-7.png)

### <a name="set-up-channel-users"></a><span data-ttu-id="487ed-169">Configurer des utilisateurs de canal</span><span class="sxs-lookup"><span data-stu-id="487ed-169">Set up channel users</span></span>

<span data-ttu-id="487ed-170">Pour créer une commande client associée au canal du centre d'appels à partir du Commerce Headquarters, l'utilisateur qui crée la commande client doit être lié au canal du centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="487ed-170">To create a sales order that is linked to the call center channel from Commerce Headquarters, the user creating the sales order must be linked to the call center channel.</span></span> <span data-ttu-id="487ed-171">L'utilisateur ne peut pas lier manuellement une commande client créée dans Commerce Headquarters au canal du centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="487ed-171">The user cannot manually link a sales order created in Commerce Headquarters to the call center channel.</span></span> <span data-ttu-id="487ed-172">Le lien est systématique et est basé sur l'utilisateur et la relation de l'utilisateur avec le canal du centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="487ed-172">The link is systematic, and is based on the user and the user's relationship to the call center channel.</span></span> <span data-ttu-id="487ed-173">Un utilisateur ne peut être lié qu'à un seul canal du centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="487ed-173">A user may only be linked to one call center channel.</span></span>

1. <span data-ttu-id="487ed-174">Dans le volet Actions, sélectionnez l'onglet **Canal**, puis **Utilisateurs du canal**.</span><span class="sxs-lookup"><span data-stu-id="487ed-174">On the action pane, select the **Channel** tab, and then select **Channel users**.</span></span>
1. <span data-ttu-id="487ed-175">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="487ed-175">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="487ed-176">Choisissez un **Identifiant d'utilisateur** existant dans la liste déroulante de sélection pour lier cet utilisateur au canal du centre d'appels</span><span class="sxs-lookup"><span data-stu-id="487ed-176">Choose an existing **User ID** from the dropdown selection list to link this user to the call center channel</span></span>

<span data-ttu-id="487ed-177">Une fois la configuration de l'utilisateur du canal effectuée, et lorsque l'utilisateur crée une commande client dans Commerce Headquarters, la commande client sera associée à leur canal du centre d'appels associé.</span><span class="sxs-lookup"><span data-stu-id="487ed-177">After the channel user setup is done and the user creates a new sales order in Commerce Headquarters, the sales order will be linked to their associated call center channel.</span></span> <span data-ttu-id="487ed-178">Toutes les configurations de ce canal seront appliquées systématiquement à la commande client.</span><span class="sxs-lookup"><span data-stu-id="487ed-178">Any configurations for this channel will be applied systematically to the sales order.</span></span> <span data-ttu-id="487ed-179">Un utilisateur peut confirmer le canal du centre d'appels auquel la commande client est liée en affichant la référence du nom du canal dans l'en-tête de la commande client.</span><span class="sxs-lookup"><span data-stu-id="487ed-179">A user can confirm which call center channel the sales order is linked to by viewing the channel name reference on the sales order header.</span></span>


### <a name="set-up-price-groups"></a><span data-ttu-id="487ed-180">Paramétrer des groupes de prix</span><span class="sxs-lookup"><span data-stu-id="487ed-180">Set up price groups</span></span>

<span data-ttu-id="487ed-181">Les groupes de prix sont facultatifs, mais s'ils sont utilisés, ils peuvent contrôler les prix de vente qui seront proposés aux clients passant des commandes dans le canal du centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="487ed-181">Price groups are optional, but if used, can control which sales prices will be offered to customers placing orders in the call center channel.</span></span> <span data-ttu-id="487ed-182">Si aucun groupe de prix n'a été configuré pour le client, ou si des groupes de prix de catalogue ne sont pas appliqués à la commande client (à l'aide du champ **ID du code source** dans l'en-tête de commande du centre d'appels), le groupe de prix du canal est utilisé pour localiser les prix des articles.</span><span class="sxs-lookup"><span data-stu-id="487ed-182">If a price group has not been configured for the customer, or if catalog price groups are not being applied to the sales order (using the **Source code ID** field on the call center order header), then the channel price group is used to locate item prices.</span></span> <span data-ttu-id="487ed-183">Si aucun groupe de prix n'est trouvé sur le canal du centre d'appels, les prix principaux par défaut des articles sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="487ed-183">If a price group is not found on the call center channel, the default item master prices are used.</span></span> 

<span data-ttu-id="487ed-184">Pour configurer un groupe de prix, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="487ed-184">To set up a price group, do the following.</span></span>

1. <span data-ttu-id="487ed-185">Dans le volet Actions, cliquez sur l'onglet **Canal**, puis sélectionnez **Groupes de prix**.</span><span class="sxs-lookup"><span data-stu-id="487ed-185">On the action pane, click the **Channel** tab, and then select **Price groups**.</span></span>
1. <span data-ttu-id="487ed-186">Dans le volet Actions, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="487ed-186">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="487ed-187">Sélectionnez un **Groupe de prix de détail** dans la liste déroulante de sélection.</span><span class="sxs-lookup"><span data-stu-id="487ed-187">Select a **Retail price group** from the dropdown selection list.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="487ed-188">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="487ed-188">Additional resources</span></span>

[<span data-ttu-id="487ed-189">Conditions préalables à la configuration de canal</span><span class="sxs-lookup"><span data-stu-id="487ed-189">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="487ed-190">Fonctionnalité de vente du centre d'appels</span><span class="sxs-lookup"><span data-stu-id="487ed-190">Call center sales functionality</span></span>](call-center-functionality.md)

[<span data-ttu-id="487ed-191">Configurer des options de traitement de commandes de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="487ed-191">Set up call center order processing options</span></span>](set-up-order-processing-options.md)

[<span data-ttu-id="487ed-192">Catalogues de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="487ed-192">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="487ed-193">Paramétrer et utiliser les alertes pour fraude</span><span class="sxs-lookup"><span data-stu-id="487ed-193">Set up and work with fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="487ed-194">Paramétrer des programmes périodiques pour les centres d'appels</span><span class="sxs-lookup"><span data-stu-id="487ed-194">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]