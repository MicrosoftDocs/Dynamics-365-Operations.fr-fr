---
title: Paramétrer un canal de vente au détail
description: Cette rubrique décrit comment créer un canal de vente au détail dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: a9291dddf7d4dc080b6eb1ec60702de32a761f45
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/10/2020
ms.locfileid: "3113826"
---
# <a name="set-up-a-retail-channel"></a><span data-ttu-id="e88ef-103">Paramétrer un canal de vente au détail</span><span class="sxs-lookup"><span data-stu-id="e88ef-103">Set up a retail channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="e88ef-104">Cette rubrique décrit comment créer un canal de vente au détail dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e88ef-104">This topic describes how to create a new retail channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e88ef-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="e88ef-105">Overview</span></span>

<span data-ttu-id="e88ef-106">Dynamics 365 Commerce prend en charge plusieurs canaux de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="e88ef-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="e88ef-107">Ces canaux de vente au détail comprennent les magasins en ligne, les centres d'appels et les magasins de vente au détail (également appelés magasins traditionnels).</span><span class="sxs-lookup"><span data-stu-id="e88ef-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="e88ef-108">Chaque canal de magasin de vente au détail peut proposer son propre mode de paiement, ses propres groupes de prix, ses propres caisses enregistreuses de PDV, ses propres comptes de revenus et de dépenses et son propre personnel.</span><span class="sxs-lookup"><span data-stu-id="e88ef-108">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="e88ef-109">Vous devez paramétrer tous ces éléments avant de pouvoir créer un canal de magasin de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="e88ef-109">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="e88ef-110">Avant de créer un canal de vente au détail, assurez-vous de suivre les [Conditions préalables du canal](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="e88ef-110">Before a retail channel is created, ensure you follow the [channel prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-retail-channel"></a><span data-ttu-id="e88ef-111">Créer et configurer un canal de vente au détail</span><span class="sxs-lookup"><span data-stu-id="e88ef-111">Create and configure a new retail channel</span></span>

1. <span data-ttu-id="e88ef-112">Dans le volet de navigation, accédez à **Modules \> Canaux \> Magasins \> Tous les magasins**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-112">In the navigation pane, go to **Modules \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="e88ef-113">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="e88ef-114">Dans le champ **Nom**, fournissez un nom pour le nouveau canal.</span><span class="sxs-lookup"><span data-stu-id="e88ef-114">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="e88ef-115">Dans le champ **Numéro de magasin**, fournissez un numéro de magasin unique.</span><span class="sxs-lookup"><span data-stu-id="e88ef-115">In the **Store number** field, provide a unique store number.</span></span> <span data-ttu-id="e88ef-116">Ce numéro peut être alphanumérique avec un maximum de 10 caractères.</span><span class="sxs-lookup"><span data-stu-id="e88ef-116">The number can be alphanumeric with a maximum of 10 characters.</span></span>
1. <span data-ttu-id="e88ef-117">Dans la liste déroulante **Entité juridique**, entrez l'entité juridique appropriée.</span><span class="sxs-lookup"><span data-stu-id="e88ef-117">In the **Legal entity** drop-down list, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="e88ef-118">Dans la liste déroulante **Entrepôt**, entrez l'entrepôt approprié.</span><span class="sxs-lookup"><span data-stu-id="e88ef-118">In the **Warehouse** drop-down list, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="e88ef-119">Dans le champ **Fuseau hoaraire du magasin**, sélectionnez le fuseau horaire adéquat.</span><span class="sxs-lookup"><span data-stu-id="e88ef-119">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="e88ef-120">Dans la liste déroulante **Groupe de taxe**, sélectionnez un groupe de taxe approprié pour le magasin.</span><span class="sxs-lookup"><span data-stu-id="e88ef-120">In the **Sales tax group** drop-down list, select an appropriate sales tax group for the store.</span></span>
1. <span data-ttu-id="e88ef-121">Sélectionnez la devise adéquate dans le champ **Devise**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-121">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="e88ef-122">Dans le **Carnet d'adresses client**, fournissez un carnet d'adresses valide.</span><span class="sxs-lookup"><span data-stu-id="e88ef-122">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="e88ef-123">Dans le champ **Client par défaut**, indiquez un client par défaut valide.</span><span class="sxs-lookup"><span data-stu-id="e88ef-123">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="e88ef-124">Dans le champ **Profil de la fonctionnalité**, sélectionnez un profil de fonctionnalité le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="e88ef-124">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="e88ef-125">Dans le champ **Profil de notification par e-mail**, fournissez un profil de notification par e-mail valide.</span><span class="sxs-lookup"><span data-stu-id="e88ef-125">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="e88ef-126">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-126">On the action pane, select **Save**.</span></span>

<span data-ttu-id="e88ef-127">L'image suivante montre la création d'un canal de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="e88ef-127">The following image shows the creation of a new retail channel.</span></span>

![Nouveau canal de vente au détail](media/channel-setup-retail-1.png)

<span data-ttu-id="e88ef-129">L'image suivante présente un exemple de canal de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="e88ef-129">The following image shows an example retail channel.</span></span>

![Exemple de canal de vente au détail](media/channel-setup-retail-2.png)

## <a name="other-settings"></a><span data-ttu-id="e88ef-131">Autres paramètres</span><span class="sxs-lookup"><span data-stu-id="e88ef-131">Other settings</span></span>

<span data-ttu-id="e88ef-132">De nombreux autres paramètres facultatifs peuvent être configurés dans les sections **Relevé/clôture**et **Divers**, en fonction des besoins du magasin de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="e88ef-132">There are numerous other optional settings that can be set in the **Statement/closing** and **Miscellaneous** sections, based on the needs of the retail store.</span></span>

<span data-ttu-id="e88ef-133">De plus, voir [Mises en page de l'écran pour le point de vente (PDV)](pos-screen-layouts.md) pour plus d'informations sur la configuration de la disposition d'écran par défaut dans la section **Mise en page de l'écran** et [Configuration et installation d'une Retail Hardware Station](retail-hardware-station-configuration-installation.md) pour des informations de configuration sur la section **Stations matérielles**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-133">In addition, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information on setting up the default screen layout in the **Screen layout** section and [Configure and install Retail hardware station](retail-hardware-station-configuration-installation.md) for setup information about the **Hardware stations** section.</span></span>

<span data-ttu-id="e88ef-134">L'image suivante présente un exemple de paramétrage de canal de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="e88ef-134">The following image shows an example retail channel setup configuration.</span></span>

![Exemple de paramétrage de canal de vente au détail](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a><span data-ttu-id="e88ef-136">Paramétrage de canal supplémentaire</span><span class="sxs-lookup"><span data-stu-id="e88ef-136">Additional channel set up</span></span>

<span data-ttu-id="e88ef-137">Des éléments supplémentaires doivent être configurés pour un canal qui peut être trouvé dans le **Volet Actions** dans la section **Paramétrer**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-137">There are additional items that need to be set up for a channel that can be found on the **Action pane** under the **Set up** section.</span></span>

<span data-ttu-id="e88ef-138">Les tâches supplémentaires requises pour le paramétrage du canal en ligne comprennent la configuration des modes de paiement, la déclaration des montants en caisse, les modes de livraison, le compte de revenus/dépenses, les sections, l'affectation du groupe d'exécution et les coffres-forts.</span><span class="sxs-lookup"><span data-stu-id="e88ef-138">Additional tasks required for online channel setup include setting up payment methods, cash declaration, modes of delivery, income/expense account, sections, the fulfillment group assignment, and safes.</span></span>

<span data-ttu-id="e88ef-139">L'image suivante montre diverses autres options de paramétrage de canal de vente au détail dans l'onglet **Paramétrer**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-139">The following image shows various additional retail channel setup options on the **Set up** tab.</span></span>

![Paramétrer un canal](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="e88ef-141">paramétrer les modes de paiement ;</span><span class="sxs-lookup"><span data-stu-id="e88ef-141">Set up payment methods</span></span>

<span data-ttu-id="e88ef-142">Pour configurer des modes de paiement, pour chaque type de paiement pris en charge sur ce canal, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e88ef-142">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="e88ef-143">Dans le volet Actions, sélectionnez l'onglet **Configurer**, puis **Modes de paiement**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-143">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="e88ef-144">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-144">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="e88ef-145">Dans le volet de navigation, sélectionnez un mode de paiement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e88ef-145">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="e88ef-146">Dans la section **Général**, fournissez un **Nom de l'opération** et configurez tous les autres paramètres souhaités.</span><span class="sxs-lookup"><span data-stu-id="e88ef-146">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="e88ef-147">Configurez tous les autres paramètres requis pour le type de paiement.</span><span class="sxs-lookup"><span data-stu-id="e88ef-147">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="e88ef-148">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-148">On the action pane, select **Save**.</span></span>

<span data-ttu-id="e88ef-149">L'image suivante présente un exemple de mode de paiement au comptant.</span><span class="sxs-lookup"><span data-stu-id="e88ef-149">The following image shows an example of a cash payment method.</span></span>

![Exemple de modes de paiement](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a><span data-ttu-id="e88ef-151">Paramétrer une déclaration des montants en caisse</span><span class="sxs-lookup"><span data-stu-id="e88ef-151">Set up cash declaration</span></span>

1. <span data-ttu-id="e88ef-152">Dans le volet Actions, sélectionnez l'onglet **Configurer**, puis **Déclaration des montants en caisse**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-152">On the action pane, select the **Set Up** tab, and then select **Cash declaration**.</span></span>
1. <span data-ttu-id="e88ef-153">Dans le volet Actions, sélectionnez **Nouveau**, puis créez toutes les dénominations **Pièce** et **Billet** applicables.</span><span class="sxs-lookup"><span data-stu-id="e88ef-153">On the action pane, select **New**, and then create all **Coin** and **Note** denominations that are applicable.</span></span>

<span data-ttu-id="e88ef-154">L'image suivante présente un exemple de mode de déclaration des montants en caisse.</span><span class="sxs-lookup"><span data-stu-id="e88ef-154">The following image shows an example of a cash declaration.</span></span>

![Paramétrer des déclaration des montants en caisse](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="e88ef-156">Paramétrer des modes de livraison</span><span class="sxs-lookup"><span data-stu-id="e88ef-156">Set up modes of delivery</span></span>

<span data-ttu-id="e88ef-157">Vous pouvez voir les modes de livraison configurés en sélectionnant **Modes de livraison** dans l'onglet **Paramétrer** du **Volet Actions**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-157">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="e88ef-158">Pour modifier ou ajouter un mode de livraison, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e88ef-158">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="e88ef-159">Dans le volet de navigation, accédez à **Modules \> Gestion des stocks \> Modes de livraison**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-159">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="e88ef-160">Dans le volet Actions, sélectionnez **Nouveau** pour créer un mode de livraison ou sélectionnez un mode existant.</span><span class="sxs-lookup"><span data-stu-id="e88ef-160">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="e88ef-161">Dans la section **Canaux de vente au détail**, sélectionnez **Ajouter une ligne** pour ajouter le canal.</span><span class="sxs-lookup"><span data-stu-id="e88ef-161">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="e88ef-162">L'ajout de canaux à l'aide de nœuds d'organisation au lieu d'ajouter chaque canal individuellement peut rationaliser l'ajout de canaux.</span><span class="sxs-lookup"><span data-stu-id="e88ef-162">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="e88ef-163">L'image suivante présente un exemple de mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="e88ef-163">The following image shows an example of a mode of delivery.</span></span>

![Paramétrer des modes de livraison](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a><span data-ttu-id="e88ef-165">Paramétrer le compte de revenus/dépenses</span><span class="sxs-lookup"><span data-stu-id="e88ef-165">Set up income/expense account</span></span>

<span data-ttu-id="e88ef-166">Pour paramétrer le compte de revenus/dépenses, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e88ef-166">To set up income/expense account, follow these steps.</span></span>

1. <span data-ttu-id="e88ef-167">Dans le volet Actions, sélectionnez l'onglet **Paramétrer**, puis **Compte de revenus/dépenses**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-167">On the action pane, select the **Set Up** tab, and then select **Income/Expense account**.</span></span>
1. <span data-ttu-id="e88ef-168">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-168">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="e88ef-169">Sous **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="e88ef-169">Under **Name**, enter a name.</span></span>
1. <span data-ttu-id="e88ef-170">Sous **Nom de recherche**, entrez un nom de recherche.</span><span class="sxs-lookup"><span data-stu-id="e88ef-170">Under **Search name**, enter a search name.</span></span>
1. <span data-ttu-id="e88ef-171">Sous **Type de compte**, entrez le type de compte.</span><span class="sxs-lookup"><span data-stu-id="e88ef-171">Under **Account type**, enter the account type.</span></span>
1. <span data-ttu-id="e88ef-172">Saisissez du texte pour **Ligne de message 1**, **Ligne de message 2**, **Texte de bon 1** et **Texte de bon 2**, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="e88ef-172">Enter text for **Message line 1**, **Message line 2**, **Slip text 1**, and **Slip text 2** as needed.</span></span>
1. <span data-ttu-id="e88ef-173">Sous **Validation**, saisissez les informations sur la validation.</span><span class="sxs-lookup"><span data-stu-id="e88ef-173">Under **Posting**, enter posting information.</span></span>
1. <span data-ttu-id="e88ef-174">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-174">On the action pane, select **Save**.</span></span>

<span data-ttu-id="e88ef-175">L'image suivante montre un exemple de compte de revenus/dépenses.</span><span class="sxs-lookup"><span data-stu-id="e88ef-175">The following image shows an example of an income/expense account.</span></span>

![Paramétrer des comptes de revenus/dépenses](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a><span data-ttu-id="e88ef-177">Paramétrer des sections</span><span class="sxs-lookup"><span data-stu-id="e88ef-177">Set up sections</span></span>

<span data-ttu-id="e88ef-178">Pour paramétrer des sections, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e88ef-178">To set up sections, follow these steps.</span></span>

1. <span data-ttu-id="e88ef-179">Dans le volet Actions, sélectionnez l'onglet **Paramétrer** puis cliquez sur **Sections**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-179">On the action pane, select the **Set Up** tab and click **Sections**.</span></span>
1. <span data-ttu-id="e88ef-180">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-180">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="e88ef-181">Sous **Numéro de section**, entrez un numéro de section.</span><span class="sxs-lookup"><span data-stu-id="e88ef-181">Under **Section number**, enter a section number.</span></span>
1. <span data-ttu-id="e88ef-182">Sous **Description**, entrez une description.</span><span class="sxs-lookup"><span data-stu-id="e88ef-182">Under **Description**, enter a description.</span></span>
1. <span data-ttu-id="e88ef-183">Sous **Taille de la section**, entrez une taille de section.</span><span class="sxs-lookup"><span data-stu-id="e88ef-183">Under **Section size**, enter a section size.</span></span>
1. <span data-ttu-id="e88ef-184">Configurez des paramètres supplémentaires pour **Général** et **Statistiques vente**, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="e88ef-184">Configure additional settings for **General** and **Sales statistics** as needed.</span></span>
1. <span data-ttu-id="e88ef-185">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-185">On the action pane, select **Save**.</span></span>

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="e88ef-186">Paramétrer une affectation de groupe d'exécution</span><span class="sxs-lookup"><span data-stu-id="e88ef-186">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="e88ef-187">Pour paramétrer une affectation de groupe d'exécution, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e88ef-187">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="e88ef-188">Dans le volet Actions, sélectionnez l'onglet **Paramétrer**, puis **Affectation du groupe d'exécution**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-188">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="e88ef-189">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-189">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="e88ef-190">Dans la liste déroulante **Groupe d'exécution**, sélectionnez un groupe d'exécution.</span><span class="sxs-lookup"><span data-stu-id="e88ef-190">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="e88ef-191">Dans la liste déroulante **Description**, entrez une description.</span><span class="sxs-lookup"><span data-stu-id="e88ef-191">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="e88ef-192">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-192">On the action pane, select **Save**</span></span>

<span data-ttu-id="e88ef-193">L'image suivante montre un exemple de configuration d'affectation de groupe d'exécution.</span><span class="sxs-lookup"><span data-stu-id="e88ef-193">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Paramétrer l'affectation du groupe d'exécution](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a><span data-ttu-id="e88ef-195">Configurer des coffres-forts</span><span class="sxs-lookup"><span data-stu-id="e88ef-195">Set up safes</span></span>

<span data-ttu-id="e88ef-196">Pour configurer des coffres-forts, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e88ef-196">To set up safes, follow these steps.</span></span>

1. <span data-ttu-id="e88ef-197">Dans le volet Actions, sélectionnez l'onglet **Paramétrer** puis cliquez sur **Coffres-forts**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-197">On the action pane, select the **Set Up** tab and click **Safes**.</span></span>
1. <span data-ttu-id="e88ef-198">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-198">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="e88ef-199">Entrez un nom pour le coffre-fort.</span><span class="sxs-lookup"><span data-stu-id="e88ef-199">Enter a name for the safe.</span></span>
1. <span data-ttu-id="e88ef-200">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e88ef-200">On the action pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e88ef-201">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e88ef-201">Additional resources</span></span>

[<span data-ttu-id="e88ef-202">Présentation des canaux</span><span class="sxs-lookup"><span data-stu-id="e88ef-202">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="e88ef-203">Conditions préalables au paramétrage du canal</span><span class="sxs-lookup"><span data-stu-id="e88ef-203">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="e88ef-204">Paramétrer un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="e88ef-204">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="e88ef-205">Paramétrer un canal de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="e88ef-205">Set up a call center channel</span></span>](channel-setup-callcenter.md)

