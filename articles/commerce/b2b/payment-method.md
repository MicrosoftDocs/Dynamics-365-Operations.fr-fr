---
title: Configurer le mode de paiement du compte client pour les sites de commerce électronique B2B
description: Cette rubrique décrit comment configurer le mode de paiement du compte client pour les sites de commerce électronique interentreprises (B2B).
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 82dfd6ac7e97d838ef442fd6ded4a4f165fc795b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211199"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a><span data-ttu-id="48cd2-103">Configurer le mode de paiement du compte client pour les sites de commerce électronique B2B</span><span class="sxs-lookup"><span data-stu-id="48cd2-103">Configure the customer account payment method for B2B e-commerce sites</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="48cd2-104">Cette rubrique décrit comment configurer le mode de paiement du compte client pour les sites de commerce électronique interentreprises (B2B).</span><span class="sxs-lookup"><span data-stu-id="48cd2-104">This topic describes how to configure the customer account payment method for business-to-business (B2B) e-commerce sites.</span></span>

<span data-ttu-id="48cd2-105">Les détaillants peuvent accepter différents types de paiement en échange des produits et des services qu’ils vendent dans un canal d'e-commerce.</span><span class="sxs-lookup"><span data-stu-id="48cd2-105">Retailers can accept various types of payment in exchange for the products and services that they sell in an e-commerce channel.</span></span> <span data-ttu-id="48cd2-106">Chaque type de paiement accepté par un détaillant doit être configurée dans Microsoft Dynamics 365 Commerce lors du paramétrage du système.</span><span class="sxs-lookup"><span data-stu-id="48cd2-106">Each payment type that a retailer accepts must be configured in Microsoft Dynamics 365 Commerce when the system is set up.</span></span> <span data-ttu-id="48cd2-107">Le mode de paiement du compte client (ou « en compte ») doit être pris en charge sur les sites de commerce électronique B2B.</span><span class="sxs-lookup"><span data-stu-id="48cd2-107">The customer account (or "on account") payment method must be supported on B2B e-commerce sites.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="48cd2-108">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="48cd2-108">Prerequisites</span></span>

1. <span data-ttu-id="48cd2-109">Ajoutez le mode de paiement du compte client dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="48cd2-109">Add the customer account payment method in Commerce headquarters.</span></span>
2. <span data-ttu-id="48cd2-110">Associez le mode de paiement du compte client au canal e-commerce.</span><span class="sxs-lookup"><span data-stu-id="48cd2-110">Associate the customer account payment method with the e-commerce channel.</span></span>
3. <span data-ttu-id="48cd2-111">Vérifiez que **Autoriser en compte** est activé pour le client dans **Retail et Commerce \> Clients \> Tous les clients \> Valeurs par défaut du paiement** dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="48cd2-111">Make sure that **Allow on account** is enabled for the customer at **Retail and Commerce \> Customers \> All customers \> Payment defaults** in Commerce headquarters.</span></span> <span data-ttu-id="48cd2-112">Assurez-vous également que les paramètres **Limite de crédit** sont définis de manière appropriée pour le client dans **Retail et Commerce \> Clients \> Tous les clients \> Crédit et relances** dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="48cd2-112">Also make sure that **Credit limit** parameters are set appropriately for the customer at **Retail and Commerce \> Customers \> All customers \> Credit and Collections** in Commerce headquarters.</span></span> 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a><span data-ttu-id="48cd2-113">Activer le mode de paiement du compte client dans le générateur de site Commerce</span><span class="sxs-lookup"><span data-stu-id="48cd2-113">Enable the customer account payment method in Commerce site builder</span></span> 

<span data-ttu-id="48cd2-114">Pour activer le mode de paiement du compte client dans le générateur de site Commerce, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="48cd2-114">To enable the customer account payment method in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="48cd2-115">Accédez à **Paramètres du site \> Extensions**.</span><span class="sxs-lookup"><span data-stu-id="48cd2-115">Go to **Site Settings \> Extensions**.</span></span>
1. <span data-ttu-id="48cd2-116">Définissez la propriété **Activer les paiements du compte client** sur **Activé pour les clients B2B**.</span><span class="sxs-lookup"><span data-stu-id="48cd2-116">Set the **Enable customer account payments** property to **Enabled for B2B customers**.</span></span> 
1. <span data-ttu-id="48cd2-117">Sélectionnez **Enregistrer et publier**.</span><span class="sxs-lookup"><span data-stu-id="48cd2-117">Select **Save and Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="48cd2-118">Les nouveaux paramètres de site ne prennent effet qu'après la mise à jour du fichier app.settings.json.</span><span class="sxs-lookup"><span data-stu-id="48cd2-118">The new site settings take effect only after the app.settings.json file is updated.</span></span> <span data-ttu-id="48cd2-119">Pour plus d’informations, voir [Mise à jour des kits de développement logiciel (SDK) et des bibliothèques de modules](../e-commerce-extensibility/sdk-updates.md).</span><span class="sxs-lookup"><span data-stu-id="48cd2-119">For more information, see [SDK and Module library updates](../e-commerce-extensibility/sdk-updates.md).</span></span>

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a><span data-ttu-id="48cd2-120">Activer le mode de paiement du compte client sur la page de paiement du site e-commerce B2B</span><span class="sxs-lookup"><span data-stu-id="48cd2-120">Enable the customer account payment method on the checkout page for the B2B e-commerce site</span></span>

<span data-ttu-id="48cd2-121">Pour activer le mode de paiement du compte client sur la page de paiement du site e-commerce B2B, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="48cd2-121">To enable the customer account payment method on the checkout page for the B2B e-commerce site, follow these steps.</span></span>

1. <span data-ttu-id="48cd2-122">Dans le générateur de site Commerce, recherchez et modifiez la page de paiement ou le fragment contenant le module de paiement du site de commerce électronique B2B.</span><span class="sxs-lookup"><span data-stu-id="48cd2-122">In Commerce site builder, find and edit the checkout page or fragment that contains the checkout module for the B2B e-commerce site.</span></span>
1. <span data-ttu-id="48cd2-123">Dans l'emplacement **Conteneur de section de caisse**, sélectionnez **Ajouter un module**, puis ajoutez un module **Paiement du compte client**.</span><span class="sxs-lookup"><span data-stu-id="48cd2-123">In the **Checkout section container** slot, select **Add Module**, and then add a **Customer account payment** module.</span></span>
1. <span data-ttu-id="48cd2-124">Positionnez le module **Paiement du compte client** en sélectionnant les points de suspension (**...**), puis en sélectionnant **Déplacer vers le haut** ou **Déplacer vers le bas** selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="48cd2-124">Position the **Customer account payment** module by selecting the ellipsis (**...**), and then selecting **Move Up** or **Move Down** as required.</span></span>
1. <span data-ttu-id="48cd2-125">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="48cd2-125">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a><span data-ttu-id="48cd2-126">Confirmer que le mode de paiement du compte client a été activé et publié</span><span class="sxs-lookup"><span data-stu-id="48cd2-126">Confirm that the customer account payment method has been enabled and published</span></span>

<span data-ttu-id="48cd2-127">Pour confirmer que le mode de paiement du compte client a été activé et publié, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="48cd2-127">To confirm that the customer account payment method has been enabled, follow these steps.</span></span>

1. <span data-ttu-id="48cd2-128">Connectez-vous au site d’e-commerce.</span><span class="sxs-lookup"><span data-stu-id="48cd2-128">Sign in to the e-commerce site.</span></span>
1. <span data-ttu-id="48cd2-129">Ajoutez un produit dans le panier.</span><span class="sxs-lookup"><span data-stu-id="48cd2-129">Add a product to the cart.</span></span>
1. <span data-ttu-id="48cd2-130">Allez sur la page de caisse.</span><span class="sxs-lookup"><span data-stu-id="48cd2-130">Go to the checkout page.</span></span> <span data-ttu-id="48cd2-131">Vous devriez voir le nouveau mode de paiement **Compte client**.</span><span class="sxs-lookup"><span data-stu-id="48cd2-131">You should see the new **Customer Account** payment method.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="48cd2-132">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="48cd2-132">Additional resources</span></span>

[<span data-ttu-id="48cd2-133">Configurer un site d'e-commerce B2B</span><span class="sxs-lookup"><span data-stu-id="48cd2-133">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="48cd2-134">Créer des hiérarchies de modélisation organisationnelle pour les organisations B2B</span><span class="sxs-lookup"><span data-stu-id="48cd2-134">Create org modeling hierarchies for B2B organizations</span></span>](org-model.md)

[<span data-ttu-id="48cd2-135">Gérer les partenaires commerciaux sur les sites de commerce électronique B2B</span><span class="sxs-lookup"><span data-stu-id="48cd2-135">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="48cd2-136">Définir des limites de quantité de produits pour les sites de commerce électronique B2B</span><span class="sxs-lookup"><span data-stu-id="48cd2-136">Set product quantity limits for B2B e-commerce sites</span></span>](quantity-limits.md)

[<span data-ttu-id="48cd2-137">Mise à jour du kit de développement logiciel et de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="48cd2-137">SDK and Module library updates</span></span>](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]