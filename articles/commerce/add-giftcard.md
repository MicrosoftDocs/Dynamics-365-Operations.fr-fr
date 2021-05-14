---
title: Module de carte cadeau
description: Cette rubrique couvre les modules de carte cadeau et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8db7e597241f1fd552f6b960c2b57b0ba83da949
ms.sourcegitcommit: efde05c758b2e02960760d875569d780d77d5550
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/29/2021
ms.locfileid: "5962761"
---
# <a name="gift-card-module"></a><span data-ttu-id="a6787-103">Module Carte cadeau</span><span class="sxs-lookup"><span data-stu-id="a6787-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a6787-104">Cette rubrique couvre les modules de carte cadeau et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a6787-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="a6787-105">Les modules de cartes cadeaux peuvent être utilisé dans les modules de paiement pour accepter des cartes cadeaux, moyen de paiement courant utilisé dans les transactions d’e-commerce.</span><span class="sxs-lookup"><span data-stu-id="a6787-105">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="a6787-106">Le module de carte cadeau prend en charge les cartes cadeaux Dynamics 365, SVS et Givex.</span><span class="sxs-lookup"><span data-stu-id="a6787-106">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="a6787-107">Les cartes cadeaux SVS et Givex sont échangées via le fournisseur de paiement Adyen.</span><span class="sxs-lookup"><span data-stu-id="a6787-107">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="a6787-108">Pour plus d’informations sur la prise en charge des cartes cadeaux externes telles que SVS et Givex, voir [Prise en charge des cartes cadeaux externes](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="a6787-108">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a6787-109">La prise en charge du remboursement des cartes cadeaux SVS et Givex pendant le processus de paiement est disponible dans la version 10.0.11 de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a6787-109">Support for redeeming SVS and Givex gift cards during checkout flow is available in the Dynamics 365 Commerce 10.0.11 release.</span></span> 

<span data-ttu-id="a6787-110">Deux modules de cartes-cadeaux sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="a6787-110">There are two gift card modules available:</span></span>

- <span data-ttu-id="a6787-111">**Carte cadeau** – Ce module peut être utilisé sur une page de paiement pour utiliser une carte-cadeau comme offre.</span><span class="sxs-lookup"><span data-stu-id="a6787-111">**Gift card** – This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="a6787-112">**Vérification du solde de la carte-cadeau** – Ce module peut être utilisé sur n’importe quelle page pour vérifier le solde d’une carte cadeau.</span><span class="sxs-lookup"><span data-stu-id="a6787-112">**Gift card balance check** – This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="a6787-113">Ce module est disponible dans Commerce version 10.0.14 et ultérieure.</span><span class="sxs-lookup"><span data-stu-id="a6787-113">This module is available in Commerce release 10.0.14 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="a6787-114">La prise en charge du module de vérification du solde de la carte cadeau est disponible dans la version 10.0.14 de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a6787-114">Support for the gift card balance check module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="a6787-115">L’image suivante montre un exemple de module de carte cadeau dans une page de caisse.</span><span class="sxs-lookup"><span data-stu-id="a6787-115">The following image shows an example of a gift card module on a checkout page.</span></span>

![Exemple d’un module de carte cadeau](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="a6787-117">Propriétés du module</span><span class="sxs-lookup"><span data-stu-id="a6787-117">Module properties</span></span>

- <span data-ttu-id="a6787-118">**Afficher des champs supplémentaires** – Cette propriété définit quels champs doivent être affichés pour les cartes cadeaux en plus du numéro de carte-cadeau, qui est toujours affiché par défaut.</span><span class="sxs-lookup"><span data-stu-id="a6787-118">**Show additional fields** – This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="a6787-119">Par exemple, certaines cartes cadeaux prennent en charge l’affichage d’un numéro d’identification personnel (PIN) et d’autres prennent en charge l’affichage d’un code PIN et d’une date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="a6787-119">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="a6787-120">Alternativement, cette propriété peut être définie sur « Aucune », ce qui n’affichera que le numéro de la carte cadeau et aucun champ supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="a6787-120">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="a6787-121">Valeurs prises en charge :</span><span class="sxs-lookup"><span data-stu-id="a6787-121">Supported values:</span></span>
-   <span data-ttu-id="a6787-122">PIN</span><span class="sxs-lookup"><span data-stu-id="a6787-122">PIN</span></span>
-   <span data-ttu-id="a6787-123">Date d’expiration</span><span class="sxs-lookup"><span data-stu-id="a6787-123">Expiration date</span></span>
-   <span data-ttu-id="a6787-124">Code PIN et date d’expiration</span><span class="sxs-lookup"><span data-stu-id="a6787-124">PIN and expiration date</span></span> 
-   <span data-ttu-id="a6787-125">None</span><span class="sxs-lookup"><span data-stu-id="a6787-125">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="a6787-126">Paramètres du site pour les modules de cartes cadeaux</span><span class="sxs-lookup"><span data-stu-id="a6787-126">Site settings for gift card modules</span></span>

<span data-ttu-id="a6787-127">Dans le générateur de site Commerce, sous **Paramètres du site \> Extensions**, il y a un paramètre de module de carte cadeau appelé **Type de carte cadeau pris en charge**.</span><span class="sxs-lookup"><span data-stu-id="a6787-127">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="a6787-128">Ce paramètre prend en charge trois valeurs :</span><span class="sxs-lookup"><span data-stu-id="a6787-128">This setting supports three values:</span></span>
- <span data-ttu-id="a6787-129">**Carte cadeau Dynamics 365** – Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a6787-129">**Dynamics 365 gift card** – When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="a6787-130">Ce paramètre n’est pris en charge que pour les utilisateurs connectés sur le site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="a6787-130">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="a6787-131">**Cartes cadeaux SVS et Givex** – Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Givex et SVS.</span><span class="sxs-lookup"><span data-stu-id="a6787-131">**SVS and Givex gift cards** – When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="a6787-132">Ce paramètre est pris en charge pour les utilisateurs connectés et anonymes sur le site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="a6787-132">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="a6787-133">**Cartes cadeaux Dynamics 365, SVS et Givex** – Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Dynamics 365, Givex et SVS.</span><span class="sxs-lookup"><span data-stu-id="a6787-133">**Dynamics 365, SVS, and Givex gift cards** – When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="a6787-134">Ce paramètre n’est pris en charge que pour les utilisateurs connectés sur le site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="a6787-134">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6787-135">Ces paramètres sont disponibles dans la version 10.0.11 de Dynamics 365 Commerce et ne sont requis que si vous avez besoin d’assistance pour les cartes cadeaux SVS ou Givex.</span><span class="sxs-lookup"><span data-stu-id="a6787-135">These settings are available in the Dynamics 365 Commerce 10.0.11 release and are required only if you need support for SVS or Givex gift cards.</span></span> <span data-ttu-id="a6787-136">Si vous effectuez une mise à jour à partir d’une ancienne version de Dynamics 365 Commerce, vous devez mettre à jour manuellement le fichier appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="a6787-136">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="a6787-137">Pour obtenir des instructions de mise à jour du fichier appsettings.json, consultez [Mise à jour du kit de développement logiciel et de la bibliothèque de modules](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="a6787-137">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span> 

## <a name="extend-internal-gift-cards-for-use-in-e-commerce-storefronts"></a><span data-ttu-id="a6787-138">Étendre les cartes-cadeaux internes aux vitrines de commerce électronique</span><span class="sxs-lookup"><span data-stu-id="a6787-138">Extend internal gift cards for use in e-commerce storefronts</span></span>

<span data-ttu-id="a6787-139">Par défaut, les cartes-cadeaux internes ne sont pas optimisées pour les vitrines de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="a6787-139">By default, internal gift cards aren't optimized for use in e-commerce storefronts.</span></span> <span data-ttu-id="a6787-140">Par conséquent, avant d'autoriser l'utilisation de cartes-cadeaux internes pour le paiement, vous devez les configurer avec des extensions qui les rendent plus sécurisées.</span><span class="sxs-lookup"><span data-stu-id="a6787-140">Therefore, before you allow internal gift cards to be used for payment, you should configure them with extensions that help make them more secure.</span></span> <span data-ttu-id="a6787-141">Voici les zones de cartes-cadeaux que vous devez étendre avant d'autoriser l'utilisation de cartes-cadeaux internes en production :</span><span class="sxs-lookup"><span data-stu-id="a6787-141">Here are the gift card areas that you should extend before you allow internal gift cards to be used in production:</span></span>

- <span data-ttu-id="a6787-142">**Numéro de la carte-cadeau** – Les séquences de numéros sont utilisées pour générer des numéros de carte-cadeau pour les cartes-cadeaux internes.</span><span class="sxs-lookup"><span data-stu-id="a6787-142">**Gift card number** – Number sequences are used to generate gift card numbers for internal gift cards.</span></span> <span data-ttu-id="a6787-143">Étant donné que les séquences de numéros peuvent être facilement prédites, vous devez étendre la génération des numéros de carte-cadeau afin que des chaînes aléatoires sécurisées par cryptographie soient utilisées pour les numéros émis.</span><span class="sxs-lookup"><span data-stu-id="a6787-143">Because number sequences can easily be predicted, you should extend the generation of gift card numbers so that random, cryptographically secure strings are used for the gift card numbers that are issued.</span></span>
- <span data-ttu-id="a6787-144">**GetBalance** – L'API **GetBalance** est utilisé pour rechercher les soldes des cartes-cadeaux.</span><span class="sxs-lookup"><span data-stu-id="a6787-144">**GetBalance** – The **GetBalance** API is used to look up gift card balances.</span></span> <span data-ttu-id="a6787-145">Par défaut, il s'agit d'une API publique.</span><span class="sxs-lookup"><span data-stu-id="a6787-145">By default, this API public.</span></span> <span data-ttu-id="a6787-146">Si un code PIN n'est pas requis pour rechercher les soldes des cartes-cadeaux, il existe un risque que des attaques par force brute utilisent l'API **GetBalance** pour pirater les numéros de cartes-cadeaux qui ont des soldes.</span><span class="sxs-lookup"><span data-stu-id="a6787-146">If a PIN isn't required to look up gift card balances, there is a risk that brute force attacks could use the **GetBalance** API to try to look up gift card numbers that have balances.</span></span> <span data-ttu-id="a6787-147">En mettant en œuvre à la fois un code PIN pour les cartes-cadeaux internes et la limitation de l'API, vous pouvez atténuer ce risque.</span><span class="sxs-lookup"><span data-stu-id="a6787-147">By implementing both PIN requirements for internal gift cards and API throttling, you can help mitigate the risk.</span></span>
- <span data-ttu-id="a6787-148">**PIN** – Par défaut, les cartes-cadeaux internes ne prennent pas en charge les codes PIN.</span><span class="sxs-lookup"><span data-stu-id="a6787-148">**PIN** – By default, internal gift cards don't support PINs.</span></span> <span data-ttu-id="a6787-149">Vous devez étendre les cartes-cadeaux internes afin qu'un code PIN soit nécessaire pour rechercher les soldes.</span><span class="sxs-lookup"><span data-stu-id="a6787-149">You should extend internal gift cards so that a PIN is required to look up balances.</span></span> <span data-ttu-id="a6787-150">Cette fonctionnalité peut également être utilisée pour verrouiller les cartes-cadeaux après plusieurs tentatives incorrectes de saisie du code PIN.</span><span class="sxs-lookup"><span data-stu-id="a6787-150">This functionality can also be used to lock gift cards after consecutive incorrect attempts to enter the PIN.</span></span>

## <a name="enable-gift-card-payments-for-guest-checkout"></a><span data-ttu-id="a6787-151">Activer les paiements par carte-cadeau pour la caisse d’invité</span><span class="sxs-lookup"><span data-stu-id="a6787-151">Enable gift card payments for guest checkout</span></span>

<span data-ttu-id="a6787-152">Par défaut, les paiements par carte-cadeau ne sont pas activés pour la caisse d’invité (anonyme).</span><span class="sxs-lookup"><span data-stu-id="a6787-152">By default, gift card payments aren't enabled for guest (anonymous) checkout.</span></span> <span data-ttu-id="a6787-153">Pour les activer, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a6787-153">To enable them, follow these steps.</span></span>

1. <span data-ttu-id="a6787-154">Dans Commerce Headquarters, accédez à **Retail et Commerce \> Configuration de canal \>  Configuration de PDV \> PDV \> Opérations PDV**.</span><span class="sxs-lookup"><span data-stu-id="a6787-154">In Commerce headquarters, go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS Operations**.</span></span>
1. <span data-ttu-id="a6787-155">Sélectionnez et maintenez sélectionné (ou cliquez avec le bouton droit) l'en-tête de la grille, puis sélectionnez **Insérer des colonnes**.</span><span class="sxs-lookup"><span data-stu-id="a6787-155">Select and hold (or right-click) the header of the grid, and then select **Insert columns**.</span></span>
1. <span data-ttu-id="a6787-156">Dans la boîte de dialogue **Insérer des colonnes**, sélectionnez la case à cocher **AllowAnonymousAccess**.</span><span class="sxs-lookup"><span data-stu-id="a6787-156">In the **Insert columns** dialog box, select the **AllowAnonymousAccess** check box.</span></span>
1. <span data-ttu-id="a6787-157">Sélectionnez **Mettre à jour**.</span><span class="sxs-lookup"><span data-stu-id="a6787-157">Select **Update**.</span></span>
1. <span data-ttu-id="a6787-158">Pour les opérations **520** (Solde de carte-cadeau) et **214**, définissez la valeur **AllowAnonymousAccess** sur **1**.</span><span class="sxs-lookup"><span data-stu-id="a6787-158">For operations **520** (Gift card balance) and **214**, set the **AllowAnonymousAccess** value to **1**.</span></span>
1. <span data-ttu-id="a6787-159">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a6787-159">Select **Save**.</span></span>
1. <span data-ttu-id="a6787-160">Exécutez la la tâche du planificateur **1090** pour synchroniser les modifications avec la base de données des canaux.</span><span class="sxs-lookup"><span data-stu-id="a6787-160">Run the **1090** scheduler job to sync changes to the channel database.</span></span> 

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="a6787-161">Ajouter un module de carte cadeau à une page</span><span class="sxs-lookup"><span data-stu-id="a6787-161">Add a gift card module to a page</span></span>

<span data-ttu-id="a6787-162">Pour obtenir des instructions sur la façon d’ajouter un module de carte cadeau à une page de paiement et de définir les propriétés requises, voir [Module de paiement ](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="a6787-162">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a6787-163">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="a6787-163">Additional resources</span></span>

[<span data-ttu-id="a6787-164">Module Panier</span><span class="sxs-lookup"><span data-stu-id="a6787-164">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="a6787-165">Module Icône de panier</span><span class="sxs-lookup"><span data-stu-id="a6787-165">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="a6787-166">Module Validation</span><span class="sxs-lookup"><span data-stu-id="a6787-166">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="a6787-167">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="a6787-167">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="a6787-168">Module Adresse d’expédition</span><span class="sxs-lookup"><span data-stu-id="a6787-168">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="a6787-169">Module Options de livraison</span><span class="sxs-lookup"><span data-stu-id="a6787-169">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="a6787-170">Module d’information sur le retrait</span><span class="sxs-lookup"><span data-stu-id="a6787-170">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="a6787-171">Module Détails de la commande</span><span class="sxs-lookup"><span data-stu-id="a6787-171">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="a6787-172">Prendre en charge des cartes cadeaux externes</span><span class="sxs-lookup"><span data-stu-id="a6787-172">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)

[<span data-ttu-id="a6787-173">Mise à jour du kit de développement logiciel et de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="a6787-173">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
