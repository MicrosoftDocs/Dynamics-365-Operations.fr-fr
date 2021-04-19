---
title: Configurer le BOPIS dans un environnement d’évaluation Dynamics 365 Commerce
description: Cette rubrique explique comment configurer l’achat en ligne, le retrait en magasin (BOPIS) dans un environnement d’évaluation Microsoft Dynamics 365 Commerce après qu’il a été approvisionné.
author: rubendel
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: rubendel
ms.search.validFrom: 2020-04-20
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 219504da62fd4637ed01f9acbab32f873cef81b0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795953"
---
# <a name="configure-bopis-in-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="ec690-103">Configurer le BOPIS dans un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ec690-103">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ec690-104">Cette rubrique explique comment configurer l’achat en ligne, le retrait en magasin (BOPIS) dans un environnement Microsoft Dynamics 365 Commerce après l’approvisionnement de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="ec690-104">This topic explains how to configure buy online, pickup in store (BOPIS) in a Microsoft Dynamics 365 Commerce evaluation environment after the environment has been provisioned.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="ec690-105">Logiciel requis</span><span class="sxs-lookup"><span data-stu-id="ec690-105">Prerequisite</span></span>

<span data-ttu-id="ec690-106">Effectuez les procédures de cette rubrique uniquement une fois que votre environnement d’évaluation de Commerce a été mis en service et configuré.</span><span class="sxs-lookup"><span data-stu-id="ec690-106">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned and configured.</span></span> <span data-ttu-id="ec690-107">Pour plus d’informations sur l’approvisionnement et la configuration de votre environnement, voir [Mettre en service un environnement d’évaluation Dynamics 365 Commerce](provisioning-guide.md) et [Configurer un environnement d’évaluation Dynamics 365 Commerce](https://docs.microsoft.com/dynamics365/commerce/cpe-post-provisioning).</span><span class="sxs-lookup"><span data-stu-id="ec690-107">For information about how to provision and configure your environment, see [Provision a Dynamics 365 Commerce evaluation environment](provisioning-guide.md) and [Configure a Dynamics 365 Commerce evaluation environment](https://docs.microsoft.com/dynamics365/commerce/cpe-post-provisioning).</span></span>

<span data-ttu-id="ec690-108">Une fois que votre environnement Commerce a été approvisionné et configuré de bout en bout, vous pouvez utiliser cette rubrique pour activer les scénarios BOPIS.</span><span class="sxs-lookup"><span data-stu-id="ec690-108">After your Commerce environment has been provisioned and configured end to end, you can use this topic to enable BOPIS scenarios.</span></span>

## <a name="configure-the-pos"></a><span data-ttu-id="ec690-109">Configuration du PDV</span><span class="sxs-lookup"><span data-stu-id="ec690-109">Configure the POS</span></span>

### <a name="configure-modern-pos"></a><span data-ttu-id="ec690-110">Configuration de Modern POS</span><span class="sxs-lookup"><span data-stu-id="ec690-110">Configure Modern POS</span></span>

<span data-ttu-id="ec690-111">Les scénarios BOPIS impliquant un paiement par carte de crédit nécessitent une station matérielle.</span><span class="sxs-lookup"><span data-stu-id="ec690-111">BOPIS scenarios that involve a credit card payment require a hardware station.</span></span> <span data-ttu-id="ec690-112">La station matérielle est intégrée dans les Modern POS pour les clients Windows et Android.</span><span class="sxs-lookup"><span data-stu-id="ec690-112">The hardware station is built into Modern POS for Windows and Android clients.</span></span> <span data-ttu-id="ec690-113">Si vous utilisez Cloud POS ou Modern POS pour iOS, le client du point de vente (PDV) doit être associé à une station matérielle partagée.</span><span class="sxs-lookup"><span data-stu-id="ec690-113">If you're using Cloud POS or Modern POS for iOS, the point of sale (POS) client must be paired with a shared hardware station.</span></span> <span data-ttu-id="ec690-114">Cette rubrique explique comment configurer BOPIS pour les clients Windows et Android.</span><span class="sxs-lookup"><span data-stu-id="ec690-114">This topic explains how to configure BOPIS for Windows and Android clients.</span></span> <span data-ttu-id="ec690-115">Pour plus d’informations sur la configuration d’une station matérielle partagée, voir [Configurer et installer la station matérielle Retail](https://docs.microsoft.com/dynamics365/commerce/retail-hardware-station-configuration-installation).</span><span class="sxs-lookup"><span data-stu-id="ec690-115">For information about how to set up a shared hardware station, see [Configure and install Retail hardware station](https://docs.microsoft.com/dynamics365/commerce/retail-hardware-station-configuration-installation).</span></span>

1. <span data-ttu-id="ec690-116">Allez dans **Commerce et vente au détail \> Paramétrage du canal \> Paramétrage du PDV \> Caisses enregistreuses**.</span><span class="sxs-lookup"><span data-stu-id="ec690-116">Go to **Retail and Commerce \> Channel setup \> POS setup \> Registers**.</span></span>
2. <span data-ttu-id="ec690-117">Sélectionnez enregistrer **SANFRAN-5**, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="ec690-117">Select register **SANFRAN-5**, and then select **Edit**.</span></span>
3. <span data-ttu-id="ec690-118">Modifiez la valeur du champ **Profil matériel** de **HW002** sur **HW001**, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ec690-118">Change the value of the **Hardware profile** field from **HW002** to **HW001**, and then select **Save**.</span></span>
4. <span data-ttu-id="ec690-119">Pour synchroniser les modifications, accédez à **Retail et Commerce \> Informatique vente au détail et Commerce \> Programme de distribution**.</span><span class="sxs-lookup"><span data-stu-id="ec690-119">To synchronize the changes, go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
5. <span data-ttu-id="ec690-120">Sélectionnez le programme de distribution **1090**, puis sur le volet Action, sélectionnez **Exécuter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="ec690-120">Select distribution schedule **1090**, and then, on the Action Pane, select **Run now**.</span></span>
6. <span data-ttu-id="ec690-121">Sélectionnez **Oui**, puis **OK** pour lancer la synchronisation des données.</span><span class="sxs-lookup"><span data-stu-id="ec690-121">Select **Yes** and then **OK** to initiate data synchronization.</span></span> 

### <a name="install-modern-pos"></a><span data-ttu-id="ec690-122">Installer Modern POS</span><span class="sxs-lookup"><span data-stu-id="ec690-122">Install Modern POS</span></span>

1. <span data-ttu-id="ec690-123">Allez dans **Commerce et vente au détail \> Paramétrage du canal \> Paramétrage du PDV \> Appareils**.</span><span class="sxs-lookup"><span data-stu-id="ec690-123">Go to **Retail and Commerce \> Channel setup \> POS setup \> Devices**.</span></span>
2. <span data-ttu-id="ec690-124">Sélectionnez l’appareil **SANFRANCIS-5**.</span><span class="sxs-lookup"><span data-stu-id="ec690-124">Select device **SANFRANCIS-5**.</span></span>
3. <span data-ttu-id="ec690-125">Dans le volet Actions, sélectionnez **Télécharger**, puis sélectionnez **Fichier de configuration**.</span><span class="sxs-lookup"><span data-stu-id="ec690-125">On the Action Pane, select **Download**, and then select **Configuration file**.</span></span>
4. <span data-ttu-id="ec690-126">Sélectionnez **Télécharger**, puis **Retail Modern POS**.</span><span class="sxs-lookup"><span data-stu-id="ec690-126">Select **Download**, and then select **Retail Modern POS**.</span></span> 
5. <span data-ttu-id="ec690-127">Une fois le téléchargement du fichier **ModernPOSSetup.exe** terminé, sélectionnez **Ouvrir le fichier**.</span><span class="sxs-lookup"><span data-stu-id="ec690-127">When download of the **ModernPOSSetup.exe** file is completed, select **Open file**.</span></span>

    ![Ouvrir le fichier](./dev-itpro/media/PAYMENTS/openfile.png)

6. <span data-ttu-id="ec690-129">Sélectionnez **Suivant** pour passer par le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="ec690-129">Select **Next** to go through the installation process.</span></span> <span data-ttu-id="ec690-130">Une fois l’installation terminée, sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="ec690-130">When installation is completed, select **Close**.</span></span>

### <a name="activate-modern-pos"></a><span data-ttu-id="ec690-131">Activer Modern POS</span><span class="sxs-lookup"><span data-stu-id="ec690-131">Activate Modern POS</span></span>

1. <span data-ttu-id="ec690-132">Sur le Bureau Windows, sélectionnez le bouton **Démarrer** et entrez **Retail Modern POS**.</span><span class="sxs-lookup"><span data-stu-id="ec690-132">On the Windows desktop, select the **Start** button, and enter **Retail Modern POS**.</span></span>
2. <span data-ttu-id="ec690-133">Sélectionnez l’application **Retail Modern POS** pour lancer l’activation.</span><span class="sxs-lookup"><span data-stu-id="ec690-133">Select the **Retail Modern POS** application to initiate activation.</span></span>
3. <span data-ttu-id="ec690-134">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ec690-134">Select **Next**.</span></span> <span data-ttu-id="ec690-135">Les champs **URL du serveur**, **Référence de l’appareil** et **Numéro d’enregistrement** doivent être prédéfinis en utilisant les informations du fichier de configuration que vous avez téléchargé dans la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="ec690-135">The **Server URL**, **Device ID**, and **Register number** fields should be preset by using information from the configuration file that you downloaded in the previous procedure.</span></span>
4. <span data-ttu-id="ec690-136">Sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="ec690-136">Select **Activate**.</span></span>
5. <span data-ttu-id="ec690-137">Une boîte de dialogue d’authentification apparaît.</span><span class="sxs-lookup"><span data-stu-id="ec690-137">An authentication dialog box appears.</span></span> <span data-ttu-id="ec690-138">Sélectionnez le compte qui utilise l’adresse e-mail précédemment associée au collaborateur **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="ec690-138">Select the account that uses the email address that was previously associated with worker **000713 - Andrew Collette**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec690-139">Si vous n’avez pas encore associé de collaborateur à votre identité, l’activation échouera.</span><span class="sxs-lookup"><span data-stu-id="ec690-139">If you haven't yet associated a worker with your identity, activation will be unsuccessful.</span></span> <span data-ttu-id="ec690-140">Dans ce cas, suivez les étapes de la section « Associer un collaborateur à votre identité » dans la rubrique [Configurer un environnement d’évaluation Dynamics 365 Commerce](cpe-post-provisioning.md#associate-a-worker-with-your-identity).</span><span class="sxs-lookup"><span data-stu-id="ec690-140">In this case, follow the steps under the "Associate a worker with your identity" section in the [Configure a Dynamics 365 Commerce evaluation environment](cpe-post-provisioning.md#associate-a-worker-with-your-identity) topic.</span></span>
    
6. <span data-ttu-id="ec690-141">Lorsque vous êtes invité à laisser votre organisation gérer l’appareil, sélectionnez **Cette application uniquement**.</span><span class="sxs-lookup"><span data-stu-id="ec690-141">When you're prompted to let your organization manage the device, select **This app only**.</span></span>
7. <span data-ttu-id="ec690-142">Une fois l’activation terminée, sélectionnez **Mise en route**.</span><span class="sxs-lookup"><span data-stu-id="ec690-142">When activation is completed, select **Get started**.</span></span>

### <a name="enable-bopis-in-modern-pos"></a><span data-ttu-id="ec690-143">Activer BOPIS dans Modern POS</span><span class="sxs-lookup"><span data-stu-id="ec690-143">Enable BOPIS in Modern POS</span></span>

1. <span data-ttu-id="ec690-144">Connectez-vous à Modern POS en utilisant **000713** comme ID opérateur et **123** comme mot de passe.</span><span class="sxs-lookup"><span data-stu-id="ec690-144">Sign in to Modern POS by using **000713** as the operator ID and **123** as the password.</span></span>
2. <span data-ttu-id="ec690-145">Pendant la lecture de la vidéo d’introduction, cochez les deux cases dans le coin inférieur gauche de la boîte de dialogue, puis fermez la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ec690-145">While the introductory walkthrough video is playing, select the two check boxes in the lower-left corner of the dialog box, and then close the dialog box.</span></span>
3. <span data-ttu-id="ec690-146">Si vous n’êtes pas invité à fermer le quart de travail, faites défiler vers la droite la page **Bienvenue**, sélectionnez **Fermer l’équipe**, puis reconnectez-vous au PDV.</span><span class="sxs-lookup"><span data-stu-id="ec690-146">If you aren't prompted to close the shift, scroll to the right on the **Welcome** page, select **Close shift**, and then sign back in to the POS.</span></span>
4. <span data-ttu-id="ec690-147">Une fois connecté, lorsque vous y êtes invité, sélectionnez **Effectuer une opération sans tiroir-caisse**.</span><span class="sxs-lookup"><span data-stu-id="ec690-147">After you're signed in, when you're prompted, select **Perform a non-drawer operation**.</span></span>
5. <span data-ttu-id="ec690-148">Sur la page **Bienvenue**, faites défiler vers la droite et sélectionnez l’opération **Sélectionner la station matérielle**.</span><span class="sxs-lookup"><span data-stu-id="ec690-148">On the **Welcome** page, scroll to the right, and select the **Select hardware station** operation.</span></span>
6. <span data-ttu-id="ec690-149">Sélectionnez **Gérer**, définissez l’option **Utiliser la station matérielle** sur **Activé**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec690-149">Select **Manage**, set the **Use hardware station** option to **On**, and then select **OK**.</span></span>
7. <span data-ttu-id="ec690-150">Déconnectez-vous du PDV et puis reconnectez-vous.</span><span class="sxs-lookup"><span data-stu-id="ec690-150">Sign out of the POS, and then sign back in.</span></span>
8. <span data-ttu-id="ec690-151">Une fois connecté, sélectionnez **Ouvrir un nouveau quart de travail**, puis sélectionnez **Tiroir-caisse**.</span><span class="sxs-lookup"><span data-stu-id="ec690-151">After you're signed in, select **Open a new shift**, and then select **Drawer**.</span></span>

## <a name="complete-a-bopis-scenario"></a><span data-ttu-id="ec690-152">Terminer un scénario BOPIS</span><span class="sxs-lookup"><span data-stu-id="ec690-152">Complete a BOPIS scenario</span></span>

### <a name="create-a-storefront-order-for-in-store-pickup"></a><span data-ttu-id="ec690-153">Créer une commande dans la vitrine pour un retrait en magasin</span><span class="sxs-lookup"><span data-stu-id="ec690-153">Create a storefront order for in-store pickup</span></span>

1. <span data-ttu-id="ec690-154">Accédez à l’URL spécifiée à l’étape [Initialiser e-Commerce](https://docs.microsoft.com/dynamics365/commerce/provisioning-guide#initialize-e-commerce) lors de la configuration de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="ec690-154">Go to the URL that you specified in the [Initialize e-Commerce](https://docs.microsoft.com/dynamics365/commerce/provisioning-guide#initialize-e-commerce) step during environment configuration.</span></span>
2. <span data-ttu-id="ec690-155">Sélectionnez un article, puis **Ajouter au panier**.</span><span class="sxs-lookup"><span data-stu-id="ec690-155">Select an item, and select **Add to cart**.</span></span>
3. <span data-ttu-id="ec690-156">Sur la page du panier, sélectionnez **Retrait** pour la ligne de commande que vous venez d’ajouter.</span><span class="sxs-lookup"><span data-stu-id="ec690-156">On the shopping bag page, select **Pick this up** for the order line that you just added.</span></span>
4. <span data-ttu-id="ec690-157">Dans la boîte de dialogue **Sélectionner un magasin**, entrez **San Francisco**, puis cliquez sur le bouton **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="ec690-157">In the **Select a store** dialog box, enter **San Francisco**, and then select the **Search** button.</span></span>
5. <span data-ttu-id="ec690-158">Dans la liste des résultats, recherchez le magasin de San Francisco et sélectionnez **Retirer ici**.</span><span class="sxs-lookup"><span data-stu-id="ec690-158">In the list of results, find the San Francisco store, and select **Pick up here**.</span></span>
6. <span data-ttu-id="ec690-159">Sur la page du panier, sélectionnez **Passer la commander en tant qu’invité**.</span><span class="sxs-lookup"><span data-stu-id="ec690-159">On the shopping bag page, select **Checkout as Guest**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="ec690-160">Pour continuer avec le paiement, vous devez accepter l’avis relatif aux cookies.</span><span class="sxs-lookup"><span data-stu-id="ec690-160">To continue with checkout, you must accept the cookie notice.</span></span> <span data-ttu-id="ec690-161">Cet avis apparaît sous la forme d’une bannière en haut de la page de paiement.</span><span class="sxs-lookup"><span data-stu-id="ec690-161">This notice appears as a banner at the top of the checkout page.</span></span>

7. <span data-ttu-id="ec690-162">Pour le mode de paiement par carte de crédit, entrez les détails suivants :</span><span class="sxs-lookup"><span data-stu-id="ec690-162">For the credit card payment method, enter the following details:</span></span>

    - <span data-ttu-id="ec690-163">**Nom du titulaire de la carte :** Entrez n’importe quel nom.</span><span class="sxs-lookup"><span data-stu-id="ec690-163">**Cardholder name:** Enter any name.</span></span>
    - <span data-ttu-id="ec690-164">**Numéro de carte :** Entrez **4111-1111-1111-1111**.</span><span class="sxs-lookup"><span data-stu-id="ec690-164">**Card number:** Enter **4111-1111-1111-1111**.</span></span>
    - <span data-ttu-id="ec690-165">**Date d’expiration :** Entrez **10/20**.</span><span class="sxs-lookup"><span data-stu-id="ec690-165">**Expiration date:** Enter **10/20**.</span></span>
    - <span data-ttu-id="ec690-166">**Code de valeur de la vérification de la carte (CVV) :** Entrez **737**.</span><span class="sxs-lookup"><span data-stu-id="ec690-166">**Card verification value (CVV) code:** Enter **737**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ec690-167">En aucun cas vous ne devez tenter d’utiliser des informations de carte de crédit réelle sur le site de test.</span><span class="sxs-lookup"><span data-stu-id="ec690-167">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

8. <span data-ttu-id="ec690-168">Continuez le paiement en entrant les détails de l’adresse de facturation, puis cliquez sur **Enregistrer et continuer**.</span><span class="sxs-lookup"><span data-stu-id="ec690-168">Continue with checkout by entering details of the billing address, and then select **Save and continue**.</span></span>
9. <span data-ttu-id="ec690-169">Lorsque la commande est prête à être passée, sélectionnez **Paiement**.</span><span class="sxs-lookup"><span data-stu-id="ec690-169">When the order is ready to be placed, select **Checkout**.</span></span>

### <a name="synchronize-online-orders-to-the-back-office"></a><span data-ttu-id="ec690-170">Synchronisez les commandes en ligne avec le back office</span><span class="sxs-lookup"><span data-stu-id="ec690-170">Synchronize online orders to the back office</span></span>

<span data-ttu-id="ec690-171">Pour plus d’informations sur la synchronisation des commandes en ligne, voir [Validation des ventes et paiements en ligne](https://docs.microsoft.com/dynamics365/commerce/tasks/posting-online-sales-payments).</span><span class="sxs-lookup"><span data-stu-id="ec690-171">For information about how to synchronize online orders, see [Posting of online sales and payments](https://docs.microsoft.com/dynamics365/commerce/tasks/posting-online-sales-payments).</span></span>

### <a name="pick-up-an-order-in-the-store"></a><span data-ttu-id="ec690-172">Retirer une commande en magasin</span><span class="sxs-lookup"><span data-stu-id="ec690-172">Pick up an order in the store</span></span>

1. <span data-ttu-id="ec690-173">Connectez-vous au PDV.</span><span class="sxs-lookup"><span data-stu-id="ec690-173">Sign in to the POS.</span></span>
2. <span data-ttu-id="ec690-174">Sur l’écran **Bienvenue**, sélectionnez **Exécution de la commande**</span><span class="sxs-lookup"><span data-stu-id="ec690-174">On the **Welcome** screen, select **Order fulfillment**</span></span>
3. <span data-ttu-id="ec690-175">Dans la liste des articles à retirer en magasin, sélectionnez la ligne de la commande passée en ligne.</span><span class="sxs-lookup"><span data-stu-id="ec690-175">In the list of items for pickup, select the line from the order that was placed online.</span></span>
4. <span data-ttu-id="ec690-176">Pendant que la ligne de commande est sélectionnée, sélectionnez **Retrait**.</span><span class="sxs-lookup"><span data-stu-id="ec690-176">While the order line is selected, select **Pick up**.</span></span>

    <span data-ttu-id="ec690-177">L’article de la ligne est ajouté à l’écran de transaction, et **0,00 $** est indiqué comme le solde dû.</span><span class="sxs-lookup"><span data-stu-id="ec690-177">The line item is added to the transaction screen, and **$0.00** is shown as the balance that is due.</span></span>

5. <span data-ttu-id="ec690-178">Sélectionnez le solde dû **0,00 $** ou sélectionnez un mode de paiement pour conclure la transaction.</span><span class="sxs-lookup"><span data-stu-id="ec690-178">Select the balance due of **$0.00**, or select any payment method to conclude the transaction.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ec690-179">Dépannage</span><span class="sxs-lookup"><span data-stu-id="ec690-179">Troubleshooting</span></span>

### <a name="online-orders-that-are-retrieved-in-the-pos-have-a-non-zero-balance-due"></a><span data-ttu-id="ec690-180">Les commandes en ligne récupérées dans le PDV ont un solde dû non nul</span><span class="sxs-lookup"><span data-stu-id="ec690-180">Online orders that are retrieved in the POS have a non-zero balance due</span></span>

<span data-ttu-id="ec690-181">Lorsqu’une commande est récupérée pour un retrait en magasin, si le solde dû n’est pas de 0 (zéro), assurez-vous que Modern POS est en cours d’utilisation et que la station matérielle est active.</span><span class="sxs-lookup"><span data-stu-id="ec690-181">When an order is retrieved for in-store pickup, if the balance due isn't 0 (zero), make sure that Modern POS is being used, and that the hardware station is active.</span></span> <span data-ttu-id="ec690-182">Si Cloud POS ou Modern POS pour iOS est en cours d’utilisation, assurez-vous qu’une station matérielle partagée est active.</span><span class="sxs-lookup"><span data-stu-id="ec690-182">If Cloud POS or Modern POS for iOS is being used, make sure that a shared hardware station is active.</span></span> <span data-ttu-id="ec690-183">Une certaine forme de station matérielle active est requise pour récupérer les paiements effectués en ligne.</span><span class="sxs-lookup"><span data-stu-id="ec690-183">Some form of active hardware station is required to retrieve payments that were made online.</span></span>

### <a name="general-issues-with-payment-capture"></a><span data-ttu-id="ec690-184">Problèmes généraux avec la capture de paiement</span><span class="sxs-lookup"><span data-stu-id="ec690-184">General issues with payment capture</span></span>

<span data-ttu-id="ec690-185">Pour tous les problèmes généraux, vous devez toujours consulter les journaux des événements de la station matérielle Modern POS ou Services Internet (IIS) dans un premier temps.</span><span class="sxs-lookup"><span data-stu-id="ec690-185">For all general issues, you should always consult the Modern POS or Internet Information Services (IIS) Hardware Station event logs as a first step.</span></span> <span data-ttu-id="ec690-186">Vous pouvez trouver ces journaux sous les nœuds suivants dans le journal des événements Windows :</span><span class="sxs-lookup"><span data-stu-id="ec690-186">You can find these logs under the following nodes in the Windows event log:</span></span>

- <span data-ttu-id="ec690-187">Journaux des applications et des services \> Microsoft \> Dynamics \> Commerce-ModernPOS</span><span class="sxs-lookup"><span data-stu-id="ec690-187">Application and Services Logs \> Microsoft \> Dynamics \> Commerce-ModernPOS</span></span>
- <span data-ttu-id="ec690-188">Journaux des applications et des services \> Microsoft \> Dynamics \> Commerce-Station matérielle</span><span class="sxs-lookup"><span data-stu-id="ec690-188">Application and Services Logs \> Microsoft \> Dynamics \> Commerce-Hardware Station</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ec690-189">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ec690-189">Additional resources</span></span>

[<span data-ttu-id="ec690-190">Vue d’ensemble d’un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ec690-190">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="ec690-191">Mettre en service un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ec690-191">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="ec690-192">Configurer des fonctionnalités facultatives pour un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ec690-192">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="ec690-193">FAQ des environnements d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ec690-193">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="ec690-194">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="ec690-194">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="ec690-195">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="ec690-195">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="ec690-196">Portail Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="ec690-196">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="ec690-197">Site web Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ec690-197">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)

[<span data-ttu-id="ec690-198">Connecteur de paiement Adyen</span><span class="sxs-lookup"><span data-stu-id="ec690-198">Adyen payment connector</span></span>](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3)

[<span data-ttu-id="ec690-199">Enregistrement des instruments de paiement en ligne avec le connecteur Adyen</span><span class="sxs-lookup"><span data-stu-id="ec690-199">Saving online payment instruments with the Adyen connector</span></span>](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector-listpi)

[<span data-ttu-id="ec690-200">Vue d’ensemble des paiements omnicanaux</span><span class="sxs-lookup"><span data-stu-id="ec690-200">Omni-channel payments overview</span></span>](https://docs.microsoft.com/dynamics365/commerce/omni-channel-payments)


[!INCLUDE[footer-include](../includes/footer-banner.md)]