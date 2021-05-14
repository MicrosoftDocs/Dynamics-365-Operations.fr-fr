---
title: Paramétrer un canal de vente au détail
description: Cette rubrique décrit comment créer un canal de vente au détail dans Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3f1f5dc2c8402d9b6b68a049f804932812eb74c0
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937532"
---
# <a name="set-up-a-retail-channel"></a><span data-ttu-id="9b2f3-103">Configurer un canal de vente au détail</span><span class="sxs-lookup"><span data-stu-id="9b2f3-103">Set up a retail channel</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9b2f3-104">Cette rubrique décrit comment créer un canal de vente au détail dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-104">This topic describes how to create a new retail channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="9b2f3-105">Dynamics 365 Commerce prend en charge plusieurs canaux de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-105">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="9b2f3-106">Ces canaux de vente au détail comprennent les magasins en ligne, les centres d’appels et les magasins de vente au détail (également appelés magasins traditionnels).</span><span class="sxs-lookup"><span data-stu-id="9b2f3-106">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="9b2f3-107">Chaque canal de magasin de vente au détail peut proposer son propre mode de paiement, ses propres groupes de prix, ses propres caisses enregistreuses de PDV, ses propres comptes de revenus et de dépenses et son propre personnel.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-107">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="9b2f3-108">Vous devez paramétrer tous ces éléments avant de pouvoir créer un canal de magasin de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-108">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="9b2f3-109">Avant de créer un canal de vente au détail, assurez-vous de suivre les [Conditions préalables du canal](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="9b2f3-109">Before a retail channel is created, ensure you follow the [channel prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-retail-channel"></a><span data-ttu-id="9b2f3-110">Créer et configurer un canal de vente au détail</span><span class="sxs-lookup"><span data-stu-id="9b2f3-110">Create and configure a new retail channel</span></span>

1. <span data-ttu-id="9b2f3-111">Dans le volet de navigation, accédez à **Modules \> Canaux \> Magasins \> Tous les magasins**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-111">In the navigation pane, go to **Modules \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="9b2f3-112">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-112">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9b2f3-113">Dans le champ **Nom**, fournissez un nom pour le nouveau canal.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-113">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="9b2f3-114">Dans le champ **Numéro de magasin**, fournissez un numéro de magasin unique.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-114">In the **Store number** field, provide a unique store number.</span></span> <span data-ttu-id="9b2f3-115">Ce numéro peut être alphanumérique avec un maximum de 10 caractères.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-115">The number can be alphanumeric with a maximum of 10 characters.</span></span>
1. <span data-ttu-id="9b2f3-116">Dans la liste déroulante **Entité juridique**, entrez l’entité juridique appropriée.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-116">In the **Legal entity** drop-down list, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="9b2f3-117">Dans la liste déroulante **Entrepôt**, entrez l’entrepôt approprié.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-117">In the **Warehouse** drop-down list, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="9b2f3-118">Dans le champ **Fuseau hoaraire du magasin**, sélectionnez le fuseau horaire adéquat.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-118">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="9b2f3-119">Dans la liste déroulante **Groupe de taxe**, sélectionnez un groupe de taxe approprié pour le magasin.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-119">In the **Sales tax group** drop-down list, select an appropriate sales tax group for the store.</span></span>
1. <span data-ttu-id="9b2f3-120">Sélectionnez la devise adéquate dans le champ **Devise**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-120">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="9b2f3-121">Dans le **Carnet d’adresses client**, fournissez un carnet d’adresses valide.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-121">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="9b2f3-122">Dans le champ **Client par défaut**, indiquez un client par défaut valide.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-122">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="9b2f3-123">Dans le champ **Profil de la fonctionnalité**, sélectionnez un profil de fonctionnalité le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-123">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="9b2f3-124">Dans le champ **Profil de notification par e-mail**, fournissez un profil de notification par e-mail valide.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-124">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="9b2f3-125">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-125">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="9b2f3-126">L’image suivante montre la création d’un canal de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-126">The following image shows the creation of a new retail channel.</span></span>

![Nouveau canal de vente au détail](media/channel-setup-retail-1.png)

<span data-ttu-id="9b2f3-128">L’image suivante présente un exemple de canal de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-128">The following image shows an example retail channel.</span></span>

![Exemple de canal de vente au détail](media/channel-setup-retail-2.png)

## <a name="other-settings"></a><span data-ttu-id="9b2f3-130">Autres paramètres</span><span class="sxs-lookup"><span data-stu-id="9b2f3-130">Other settings</span></span>

<span data-ttu-id="9b2f3-131">De nombreux autres paramètres facultatifs peuvent être configurés dans les sections **Relevé/clôture** et **Divers**, en fonction des besoins du magasin de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-131">There are numerous other optional settings that can be set in the **Statement/closing** and **Miscellaneous** sections, based on the needs of the retail store.</span></span>

<span data-ttu-id="9b2f3-132">De plus, voir [Mises en page de l’écran pour le point de vente (PDV)](pos-screen-layouts.md) pour plus d’informations sur la configuration de la disposition d’écran par défaut dans la section **Mise en page de l’écran** et [Configuration et installation d’une Retail Hardware Station](retail-hardware-station-configuration-installation.md) pour des informations de configuration sur la section **Stations matérielles**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-132">In addition, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information on setting up the default screen layout in the **Screen layout** section and [Configure and install Retail hardware station](retail-hardware-station-configuration-installation.md) for setup information about the **Hardware stations** section.</span></span>

<span data-ttu-id="9b2f3-133">L’image suivante présente un exemple de paramétrage de canal de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-133">The following image shows an example retail channel setup configuration.</span></span>

![Exemple de paramétrage de canal de vente au détail](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a><span data-ttu-id="9b2f3-135">Paramétrage de canal supplémentaire</span><span class="sxs-lookup"><span data-stu-id="9b2f3-135">Additional channel set up</span></span>

<span data-ttu-id="9b2f3-136">Des éléments supplémentaires doivent être configurés pour un canal disponible dans le volet Actions dans la section **Paramétrer**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-136">There are additional items that need to be set up for a channel that can be found on the Action Pane under the **Set up** section.</span></span>

<span data-ttu-id="9b2f3-137">Les tâches supplémentaires requises pour le paramétrage du canal en ligne comprennent la configuration des modes de paiement, la déclaration des montants en caisse, les modes de livraison, le compte de revenus/dépenses, les sections, l’affectation du groupe d’exécution et les coffres-forts.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-137">Additional tasks required for online channel setup include setting up payment methods, cash declaration, modes of delivery, income/expense account, sections, the fulfillment group assignment, and safes.</span></span>

<span data-ttu-id="9b2f3-138">L’image suivante montre diverses autres options de paramétrage de canal de vente au détail dans l’onglet **Paramétrer**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-138">The following image shows various additional retail channel setup options on the **Set up** tab.</span></span>

![Paramétrer un canal](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="9b2f3-140">paramétrer les modes de paiement ;</span><span class="sxs-lookup"><span data-stu-id="9b2f3-140">Set up payment methods</span></span>

<span data-ttu-id="9b2f3-141">Pour configurer des modes de paiement, pour chaque type de paiement pris en charge sur ce canal, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-141">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="9b2f3-142">Dans le volet Actions, sélectionnez l’onglet **Configurer**, puis **Modes de paiement**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-142">On the Action Pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="9b2f3-143">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-143">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9b2f3-144">Dans le volet de navigation, sélectionnez un mode de paiement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-144">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="9b2f3-145">Dans la section **Général**, fournissez un **Nom de l’opération** et configurez tous les autres paramètres souhaités.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-145">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="9b2f3-146">Configurez tous les autres paramètres requis pour le type de paiement.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-146">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="9b2f3-147">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-147">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="9b2f3-148">L’image suivante présente un exemple de mode de paiement au comptant.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-148">The following image shows an example of a cash payment method.</span></span>

![Exemple de modes de paiement](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a><span data-ttu-id="9b2f3-150">Paramétrer une déclaration des montants en caisse</span><span class="sxs-lookup"><span data-stu-id="9b2f3-150">Set up cash declaration</span></span>

1. <span data-ttu-id="9b2f3-151">Dans le volet Actions, sélectionnez l’onglet **Configurer**, puis **Déclaration des montants en caisse**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-151">On the Action Pane, select the **Set Up** tab, and then select **Cash declaration**.</span></span>
1. <span data-ttu-id="9b2f3-152">Dans le volet Actions, sélectionnez **Nouveau**, puis créez toutes les dénominations **Pièce** et **Billet** applicables.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-152">On the Action Pane, select **New**, and then create all **Coin** and **Note** denominations that are applicable.</span></span>

<span data-ttu-id="9b2f3-153">L’image suivante présente un exemple de mode de déclaration des montants en caisse.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-153">The following image shows an example of a cash declaration.</span></span>

![Paramétrer des déclaration des montants en caisse](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="9b2f3-155">Paramétrer des modes de livraison</span><span class="sxs-lookup"><span data-stu-id="9b2f3-155">Set up modes of delivery</span></span>

<span data-ttu-id="9b2f3-156">Vous pouvez voir les modes de livraison configurés en sélectionnant **Modes de livraison** dans l’onglet **Paramétrer** du volet Actions.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-156">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the Action Pane.</span></span>  

<span data-ttu-id="9b2f3-157">Pour modifier ou ajouter un mode de livraison, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-157">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="9b2f3-158">Dans le volet de navigation, accédez à **Modules \> Gestion des stocks \> Modes de livraison**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-158">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="9b2f3-159">Dans le volet Actions, sélectionnez **Nouveau** pour créer un mode de livraison ou sélectionnez un mode existant.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-159">On the Action Pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="9b2f3-160">Dans la section **Canaux de vente au détail**, sélectionnez **Ajouter une ligne** pour ajouter le canal.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-160">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="9b2f3-161">L’ajout de canaux à l’aide de nœuds d’organisation au lieu d’ajouter chaque canal individuellement peut rationaliser l’ajout de canaux.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-161">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="9b2f3-162">L’image suivante présente un exemple de mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-162">The following image shows an example of a mode of delivery.</span></span>

![Paramétrer des modes de livraison](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a><span data-ttu-id="9b2f3-164">Paramétrer le compte de revenus/dépenses</span><span class="sxs-lookup"><span data-stu-id="9b2f3-164">Set up income/expense account</span></span>

<span data-ttu-id="9b2f3-165">Pour paramétrer le compte de revenus/dépenses, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-165">To set up income/expense account, follow these steps.</span></span>

1. <span data-ttu-id="9b2f3-166">Dans le volet Actions, sélectionnez l’onglet **Paramétrer**, puis **Compte de revenus/dépenses**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-166">On the Action Pane, select the **Set Up** tab, and then select **Income/Expense account**.</span></span>
1. <span data-ttu-id="9b2f3-167">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-167">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9b2f3-168">Sous **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-168">Under **Name**, enter a name.</span></span>
1. <span data-ttu-id="9b2f3-169">Sous **Nom de recherche**, entrez un nom de recherche.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-169">Under **Search name**, enter a search name.</span></span>
1. <span data-ttu-id="9b2f3-170">Sous **Type de compte**, entrez le type de compte.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-170">Under **Account type**, enter the account type.</span></span>
1. <span data-ttu-id="9b2f3-171">Saisissez du texte pour **Ligne de message 1**, **Ligne de message 2**, **Texte de bon 1** et **Texte de bon 2**, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-171">Enter text for **Message line 1**, **Message line 2**, **Slip text 1**, and **Slip text 2** as needed.</span></span>
1. <span data-ttu-id="9b2f3-172">Sous **Validation**, saisissez les informations sur la validation.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-172">Under **Posting**, enter posting information.</span></span>
1. <span data-ttu-id="9b2f3-173">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-173">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="9b2f3-174">L’image suivante montre un exemple de compte de revenus/dépenses.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-174">The following image shows an example of an income/expense account.</span></span>

![Paramétrer des comptes de revenus/dépenses](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a><span data-ttu-id="9b2f3-176">Paramétrer des sections</span><span class="sxs-lookup"><span data-stu-id="9b2f3-176">Set up sections</span></span>

<span data-ttu-id="9b2f3-177">Pour paramétrer des sections, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-177">To set up sections, follow these steps.</span></span>

1. <span data-ttu-id="9b2f3-178">Dans le volet Actions, sélectionnez l’onglet **Paramétrer** puis cliquez sur **Sections**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-178">On the Action Pane, select the **Set Up** tab and click **Sections**.</span></span>
1. <span data-ttu-id="9b2f3-179">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-179">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9b2f3-180">Sous **Numéro de section**, entrez un numéro de section.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-180">Under **Section number**, enter a section number.</span></span>
1. <span data-ttu-id="9b2f3-181">Sous **Description**, entrez une description.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-181">Under **Description**, enter a description.</span></span>
1. <span data-ttu-id="9b2f3-182">Sous **Taille de la section**, entrez une taille de section.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-182">Under **Section size**, enter a section size.</span></span>
1. <span data-ttu-id="9b2f3-183">Configurez des paramètres supplémentaires pour **Général** et **Statistiques vente**, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-183">Configure additional settings for **General** and **Sales statistics** as needed.</span></span>
1. <span data-ttu-id="9b2f3-184">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-184">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="9b2f3-185">Paramétrer une affectation de groupe d’exécution</span><span class="sxs-lookup"><span data-stu-id="9b2f3-185">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="9b2f3-186">Pour paramétrer une affectation de groupe d’exécution, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-186">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="9b2f3-187">Dans le volet Actions, sélectionnez l’onglet **Paramétrer**, puis **Affectation du groupe d’exécution**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-187">On the Action Pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="9b2f3-188">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-188">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9b2f3-189">Dans la liste déroulante **Groupe d’exécution**, sélectionnez un groupe d’exécution.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-189">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="9b2f3-190">Dans la liste déroulante **Description**, entrez une description.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-190">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="9b2f3-191">Dans le volet Actions, sélectionnez **Enregistrer**</span><span class="sxs-lookup"><span data-stu-id="9b2f3-191">On the Action Pane, select **Save**</span></span>

<span data-ttu-id="9b2f3-192">L’image suivante montre un exemple de configuration d’affectation de groupe d’exécution.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-192">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Paramétrer l’affectation du groupe d’exécution](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a><span data-ttu-id="9b2f3-194">Configurer des coffres-forts</span><span class="sxs-lookup"><span data-stu-id="9b2f3-194">Set up safes</span></span>

<span data-ttu-id="9b2f3-195">Pour configurer des coffres-forts, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-195">To set up safes, follow these steps.</span></span>

1. <span data-ttu-id="9b2f3-196">Dans le volet Actions, sélectionnez l’onglet **Paramétrer** puis cliquez sur **Coffres-forts**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-196">On the Action Pane, select the **Set Up** tab and click **Safes**.</span></span>
1. <span data-ttu-id="9b2f3-197">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-197">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9b2f3-198">Entrez un nom pour le coffre-fort.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-198">Enter a name for the safe.</span></span>
1. <span data-ttu-id="9b2f3-199">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-199">On the Action Pane, select **Save**.</span></span>

### <a name="ensure-unique-transaction-ids"></a><span data-ttu-id="9b2f3-200">Garantir des identifiants de transaction uniques</span><span class="sxs-lookup"><span data-stu-id="9b2f3-200">Ensure unique transaction IDs</span></span>

<span data-ttu-id="9b2f3-201">À partir de la version 10.0.18 de Commerce, les ID de transaction générés pour le point de vente (PDV) sont séquentiels et comprennent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="9b2f3-201">As of the Commerce version 10.0.18 , transaction IDs generated for the point of sale (POS) are sequential and include the following parts:</span></span>

- <span data-ttu-id="9b2f3-202">Une partie fixe, qui est une concaténation de l'ID de magasin et de l'ID de terminal.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-202">A fixed part, which is a concatenation of store ID and terminal ID.</span></span> 
- <span data-ttu-id="9b2f3-203">Une partie séquentielle, qui est une séquence de nombres.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-203">A sequential part, which is a number sequence.</span></span> 

<span data-ttu-id="9b2f3-204">Plus précisément, le format est *{store}-{terminal} -{numbersequence}*.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-204">Specifically, the format is *{store}-{terminal}-{numbersequence}*.</span></span> 

<span data-ttu-id="9b2f3-205">Étant donné que les ID de transaction peuvent être générés en mode hors ligne et en ligne, des instances d'ID de transaction en double ont été générées.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-205">Because transaction IDs can be generated in offline and online modes, there have been instances of duplicate transaction IDs being generated.</span></span> <span data-ttu-id="9b2f3-206">L'élimination des ID de transaction en double nécessite de nombreuses corrections manuelles.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-206">Eliminating duplicate transaction IDs requires a lot of manual data fixing.</span></span> 

<span data-ttu-id="9b2f3-207">Avec Commerce version 10.0.19, le format de l'ID de transaction a été mis à jour pour supprimer la partie séquentielle et utilise à la place un nombre à 13 chiffres généré en calculant le temps en millisecondes depuis 1970.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-207">With Commerce version 10.0.19, the transaction ID format has been updated to remove the sequential part and instead uses a 13-digit number generated by calculating the time in milliseconds since 1970.</span></span> <span data-ttu-id="9b2f3-208">Avec ce changement, le nouveau format d'ID de transaction est *{store}-{terminal}-{millisecondsSince1970}*.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-208">With this change, the new transaction ID format is *{store}-{terminal}-{millisecondsSince1970}*.</span></span> <span data-ttu-id="9b2f3-209">Cette mise à jour rend l'ID de transaction non séquentiel et garantit que les ID de transaction sont toujours uniques.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-209">This update makes the transaction ID non-sequential and ensures that transaction IDs are always unique.</span></span> 

> [!NOTE]
> <span data-ttu-id="9b2f3-210">Les ID de transaction sont uniquement destinés à un usage interne au système, ils ne doivent donc pas être séquentiels.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-210">Transaction IDs are meant for internal system use only, so they are not required to be sequential.</span></span> <span data-ttu-id="9b2f3-211">Cependant, de nombreux pays exigent que les ID de reçu soient séquentiels.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-211">However, many countries require receipt IDs to be sequential.</span></span>

<span data-ttu-id="9b2f3-212">La nouvelle fonctionnalité de format d'ID de transaction peut être activée à partir de l'espace e travail **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-212">The new transaction ID format feature can be enabled from the **Feature management** workspace.</span></span> 

<span data-ttu-id="9b2f3-213">Pour activer l'utilisation de nouveaux ID de transaction, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="9b2f3-213">To enable the use of new transaction IDs, follow these steps:</span></span>

1. <span data-ttu-id="9b2f3-214">Dans Commerce Headquarters, accédez à **Administration système \> Espaces de travail \> Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-214">In Commerce headquarters, go to **System administration \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="9b2f3-215">Filtrez pour trouver le module « Retail et Commerce ».</span><span class="sxs-lookup"><span data-stu-id="9b2f3-215">Filter for the "retail and commerce" module.</span></span>
1. <span data-ttu-id="9b2f3-216">Recherchez le nom de la fonction **Activer le nouvel identifiant de transaction pour éviter les identifiants de transaction en double**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-216">Search for the **Enable new transaction id to avoid duplicate transaction ids** feature name.</span></span>
1. <span data-ttu-id="9b2f3-217">Sélectionnez la fonctionnalité, puis sélectionnez **Activer maintenant** dans le volet de droite.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-217">Select the feature, and then select **Enable Now** in the right pane.</span></span>  
1. <span data-ttu-id="9b2f3-218">Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-218">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="9b2f3-219">Exécutez les tâches **Configuration des canaux 1070** et **Enregistreur de tâches 1170 POS** pour synchroniser la fonction activée avec les magasins.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-219">Run the **1070 Channel configuration** and **1170 POS task recorder** jobs to synchronize the enabled feature to the stores.</span></span>
1. <span data-ttu-id="9b2f3-220">Une fois les modifications envoyées aux magasins, les terminaux PDV doivent être fermés et rouverts pour utiliser le nouveau format d'ID de transaction.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-220">After the changes have been sent to the stores, POS terminals must be closed and reopened to use the new transaction ID format.</span></span> 

> [!NOTE]
> <span data-ttu-id="9b2f3-221">Une fois la nouvelle fonctionnalité de format d'ID de transaction activée, vous ne pourrez pas la désactiver.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-221">After the new transaction ID format feature is enabled, you will not be able to disable this feature.</span></span> <span data-ttu-id="9b2f3-222">Si elle doit être désactivée, veuillez contacter le support commercial.</span><span class="sxs-lookup"><span data-stu-id="9b2f3-222">If it must be disabled, please contact Commerce Support.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9b2f3-223">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="9b2f3-223">Additional resources</span></span>

[<span data-ttu-id="9b2f3-224">Vue d’ensemble des canaux</span><span class="sxs-lookup"><span data-stu-id="9b2f3-224">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="9b2f3-225">Conditions préalables à la configuration de canal</span><span class="sxs-lookup"><span data-stu-id="9b2f3-225">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="9b2f3-226">Paramétrer un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="9b2f3-226">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="9b2f3-227">Paramétrer un canal de centre d’appels</span><span class="sxs-lookup"><span data-stu-id="9b2f3-227">Set up a call center channel</span></span>](channel-setup-callcenter.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
