---
title: Configurer la taxe pour les commandes en ligne
description: Cette rubrique fournit une vue d'ensemble de la sélection du groupe de taxes pour différents types de commande en ligne dans Dynamics 365 Commerce.
author: gvrmohanreddy
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: gmohanv
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 40c20bf13779f73289e43df21b763e1b864686a7
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4530195"
---
# <a name="configure-sales-tax-for-online-orders"></a><span data-ttu-id="01a3c-103">Configurer la taxe pour les commandes en ligne</span><span class="sxs-lookup"><span data-stu-id="01a3c-103">Configure sales tax for online orders</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="01a3c-104">Cette rubrique fournit une vue d'ensemble de la sélection du groupe de taxes pour différents types de commande en ligne.</span><span class="sxs-lookup"><span data-stu-id="01a3c-104">This topic provides an overview of sales tax group selection for different online order types.</span></span> 

<span data-ttu-id="01a3c-105">Votre canal d'e-commerce peut souhaiter prendre en charge des options telles que la livraison ou le retrait des commandes en ligne.</span><span class="sxs-lookup"><span data-stu-id="01a3c-105">Your e-commerce channel may want to support options like delivery or pickup for online orders.</span></span> <span data-ttu-id="01a3c-106">L'applicabilité de la taxe est basée sur l'option sélectionnée par vos utilisateurs en ligne.</span><span class="sxs-lookup"><span data-stu-id="01a3c-106">The sales tax applicability is based on the option selected by your online users.</span></span> <span data-ttu-id="01a3c-107">Lorsqu'un client du site choisit d'acheter un article en ligne et le fait expédier à une adresse, la taxe est déterminée en fonction du paramètre de groupe de taxes de l'adresse de livraison du client.</span><span class="sxs-lookup"><span data-stu-id="01a3c-107">When a site customer chooses to buy an item online and gets it shipped to an address, the sales tax is determined based on the customer's shipping address tax group setting.</span></span> <span data-ttu-id="01a3c-108">Lorsqu'un client choisit de récupérer un article acheté dans un magasin, la taxe est déterminée en fonction du paramètre de groupe de taxes du magasin de retrait.</span><span class="sxs-lookup"><span data-stu-id="01a3c-108">When a customer opts to pick up a purchased item at a store, the sales tax is determined based on the pickup store's tax group setting.</span></span> 

## <a name="orders-shipped-to-a-customer-address"></a><span data-ttu-id="01a3c-109">Commandes expédiées à une adresse client</span><span class="sxs-lookup"><span data-stu-id="01a3c-109">Orders shipped to a customer address</span></span> 

<span data-ttu-id="01a3c-110">En général, les taxes pour les commandes en ligne expédiées aux adresses des clients sont définies par la destination.</span><span class="sxs-lookup"><span data-stu-id="01a3c-110">In general, taxes for online orders that ship to customer addresses are defined by the destination.</span></span> <span data-ttu-id="01a3c-111">Chaque groupe de taxes a une configuration de taxe basée sur la destination de vente au détail dans laquelle votre entreprise peut définir des détails de destination tels que le département/la région, l'état, le pays et la ville sous une forme hiérarchique.</span><span class="sxs-lookup"><span data-stu-id="01a3c-111">Every sales tax group has a retail destination-based tax configuration in which your business can define destination details such as county/region, state, county, and city in a hierarchical form.</span></span> <span data-ttu-id="01a3c-112">Lorsqu'une commande en ligne est passée, le moteur de taxe Commerce utilise l'adresse de livraison de chaque élément de ligne de la commande et recherche les groupes de taxes avec les critères de taxe correspondant à la destination.</span><span class="sxs-lookup"><span data-stu-id="01a3c-112">When an online order is placed, the Commerce tax engine uses the delivery address of every line item in the order, and finds sales tax groups with matching destination-based tax criteria.</span></span> <span data-ttu-id="01a3c-113">Par exemple, pour une commande en ligne avec une adresse de livraison d'élément de campagne à San Francisco, Californie, le moteur de taxe trouvera le groupe de taxes et le code de taxe pour la Californie, puis calculera la taxe pour chaque élément de ligne en conséquence.</span><span class="sxs-lookup"><span data-stu-id="01a3c-113">For example, for an online order with a line item delivery address to San Francisco, California, the tax engine will find the sales tax group and sales tax code for California and then calculate tax for each line item accordingly.</span></span>  

## <a name="customer-based-tax-groups"></a><span data-ttu-id="01a3c-114">Groupes de taxes basés sur le client</span><span class="sxs-lookup"><span data-stu-id="01a3c-114">Customer-based tax groups</span></span>

<span data-ttu-id="01a3c-115">Au siège de Commerce, il existe deux emplacements où les groupes de taxes clients sont configurés :</span><span class="sxs-lookup"><span data-stu-id="01a3c-115">In Commerce headquarters, there are two places where customer tax groups are configured:</span></span>

- <span data-ttu-id="01a3c-116">**Profil du client**</span><span class="sxs-lookup"><span data-stu-id="01a3c-116">**Customer's profile**</span></span>
- <span data-ttu-id="01a3c-117">**Adresse d'expédition du client**</span><span class="sxs-lookup"><span data-stu-id="01a3c-117">**Customer's shipping address**</span></span>

### <a name="if-a-customers-profile-has-a-tax-group-configured"></a><span data-ttu-id="01a3c-118">Si le profil d'un client a un groupe de taxes configuré</span><span class="sxs-lookup"><span data-stu-id="01a3c-118">If a customer's profile has a tax group configured</span></span>

<span data-ttu-id="01a3c-119">Un enregistrement de profil d'un client au siège peut avoir un groupe de taxes configuré, mais pour les commandes en ligne, le groupe de taxes configuré dans le profil d'un client ne sera pas utilisé par le moteur de taxe.</span><span class="sxs-lookup"><span data-stu-id="01a3c-119">A customer's profile record in headquarters may have a sales tax group configured, however for online orders the sales tax group configured in a customer's profile will not be used by the tax engine.</span></span> 

### <a name="if-a-customers-shipping-address-has-a-tax-group-configured"></a><span data-ttu-id="01a3c-120">Si l'adresse de livraison d'un client a un groupe de taxes configuré</span><span class="sxs-lookup"><span data-stu-id="01a3c-120">If a customer's shipping address has a tax group configured</span></span>

<span data-ttu-id="01a3c-121">Si l'enregistrement d'adresse de livraison d'un client a un groupe de taxes configuré et qu'une commande en ligne (ou un article) est expédiée à l'adresse de livraison du client, le groupe de taxes configuré dans l'enregistrement d'adresse du client sera utilisé par le moteur de taxes pour les calculs de taxe.</span><span class="sxs-lookup"><span data-stu-id="01a3c-121">If a customer's shipping address record has a tax group configured and an online order (or line item) is shipped to the customer's shipping address, the tax group configured in the customer's address record will be used by the tax engine for tax calculations.</span></span>

#### <a name="configure-a-tax-group-for-a-customers-shipping-address-record"></a><span data-ttu-id="01a3c-122">Configurer un groupe de taxes pour un enregistrement d'adresse de livraison d'un client</span><span class="sxs-lookup"><span data-stu-id="01a3c-122">Configure a tax group for a customer's shipping address record</span></span>

<span data-ttu-id="01a3c-123">Pour configurer un groupe de taxes pour l'enregistrement d'adresse de livraison d'un client au siège de Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="01a3c-123">To configure a tax group for a customer's shipping address record in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="01a3c-124">Aller à **Tous les clients**, puis sélectionnez le client souhaité.</span><span class="sxs-lookup"><span data-stu-id="01a3c-124">Go to **All customers**, and then select the desired customer.</span></span> 
1. <span data-ttu-id="01a3c-125">Sur le raccourci **Adresses**, sélectionnez l'adresse souhaitée, puis sélectionnez **Plus d'options \> Avancée**.</span><span class="sxs-lookup"><span data-stu-id="01a3c-125">On the **Addresses** FastTab, select the desired address, and then select **More options \> Advanced**.</span></span> 
1. <span data-ttu-id="01a3c-126">Sous l'onglet **Général** sur la page **Gérer les adresses**, définissez la valeur de la taxe selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="01a3c-126">Under the **General** tab on the **Manage addresses** page, set the sales tax value as needed.</span></span>

> [!NOTE]
> <span data-ttu-id="01a3c-127">Le groupe de taxes est défini à l'aide de l'adresse de livraison de la ligne de commande et les taxes basées sur la destination sont configurées au niveau du groupe de taxes lui-même.</span><span class="sxs-lookup"><span data-stu-id="01a3c-127">The tax group is defined using the delivery address of the order line and the destination-based taxes are configured at the tax group itself.</span></span> <span data-ttu-id="01a3c-128">Pour plus d'informations, voir [Configurer les taxes pour les magasins en ligne en fonction de la destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span><span class="sxs-lookup"><span data-stu-id="01a3c-128">For more information, see [Set up taxes for online stores based on destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span></span>

## <a name="order-pickup-in-store"></a><span data-ttu-id="01a3c-129">Retrait de commande en magasin</span><span class="sxs-lookup"><span data-stu-id="01a3c-129">Order pickup in store</span></span>

<span data-ttu-id="01a3c-130">Pour les lignes de commande avec retrait en magasin ou retrait à un point-relais spécifié, le groupe de taxes du magasin de retrait sélectionné sera appliqué.</span><span class="sxs-lookup"><span data-stu-id="01a3c-130">For order lines with pickup in store or curbside pickup specified, the tax group from the selected pickup store will be applied.</span></span> <span data-ttu-id="01a3c-131">Pour plus d'informations sur la configuration du groupe de taxes pour un magasin donné, voir [Définir d'autres options fiscales pour les magasins](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span><span class="sxs-lookup"><span data-stu-id="01a3c-131">For details about how to configure the tax group for a given store, see [Set other tax options for stores](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span></span>

> [!NOTE]
> <span data-ttu-id="01a3c-132">Lorsqu'une ligne de commande est retirée dans un magasin, les paramètres de taxe d'adresse d'un client (s'ils sont configurés) seront ignorés par le moteur de taxe et la configuration de taxe du magasin de retrait sera appliquée.</span><span class="sxs-lookup"><span data-stu-id="01a3c-132">When an order line is picked up at a store, a customer's address tax settings (if set up) will be ignored by the tax engine and the pickup store's tax configuration will be applied.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="01a3c-133">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="01a3c-133">Additional resources</span></span>

[<span data-ttu-id="01a3c-134">Vue d’ensemble des taxes</span><span class="sxs-lookup"><span data-stu-id="01a3c-134">Sales tax overview</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="01a3c-135">Modes de calcul des taxes dans le champ Origine</span><span class="sxs-lookup"><span data-stu-id="01a3c-135">Sales tax calculation methods in the Origin field</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/sales-tax-calculation-methods-origin-field?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="01a3c-136">Affectation et remplacement des taxes</span><span class="sxs-lookup"><span data-stu-id="01a3c-136">Sales tax assignment and overrides</span></span>](https://docs.microsoft.com/dynamics365/supply-chain/procurement/tasks/sales-tax-assignment-overrides?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="01a3c-137">Options de calcul montant entier et intervalle pour les codes taxe</span><span class="sxs-lookup"><span data-stu-id="01a3c-137">Whole amount and Interval calculation options for sales tax codes</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/whole-amount-interval-options-sales-tax-codes?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="01a3c-138">Calcul de l’exonération fiscale</span><span class="sxs-lookup"><span data-stu-id="01a3c-138">Calculation of tax exemption</span></span>](tax-exempt-price-inclusive.md) 

