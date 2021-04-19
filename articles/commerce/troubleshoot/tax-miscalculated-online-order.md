---
title: Les taxes sur les commandes en ligne ne sont pas correctement calculées
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque les taxes sur les commandes en ligne ne sont pas correctement calculées ou lorsque le groupe de taxe sur la ligne de vente n’est pas correctement défini.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7f71add679e1d24f80db8ce3990058b591128ec1
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801409"
---
# <a name="taxes-on-online-orders-are-incorrectly-calculated"></a><span data-ttu-id="8bfec-103">Les taxes sur les commandes en ligne ne sont pas correctement calculées</span><span class="sxs-lookup"><span data-stu-id="8bfec-103">Taxes on online orders are incorrectly calculated</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8bfec-104">Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque les taxes sur les commandes en ligne ne sont pas correctement calculées ou lorsque le groupe de taxe sur la ligne de vente n’est pas correctement défini.</span><span class="sxs-lookup"><span data-stu-id="8bfec-104">This topic provides troubleshooting guidance that can help when taxes on online orders are incorrectly calculated, or when the tax group on the sales line isn't correctly set.</span></span>

## <a name="description"></a><span data-ttu-id="8bfec-105">Description</span><span class="sxs-lookup"><span data-stu-id="8bfec-105">Description</span></span>

<span data-ttu-id="8bfec-106">Lorsqu’une commande e-commerce est passée, les taxes ne sont pas correctement calculées ou le groupe de taxe sur la ligne de vente est défini de manière incorrecte.</span><span class="sxs-lookup"><span data-stu-id="8bfec-106">When an e-commerce order is placed, the taxes are incorrectly calculated, or the tax group on the sales line is incorrectly set.</span></span>

## <a name="resolution"></a><span data-ttu-id="8bfec-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="8bfec-107">Resolution</span></span>

### <a name="configure-the-sales-tax-for-a-retail-store-in-commerce-headquarters"></a><span data-ttu-id="8bfec-108">Configurer la taxe pour un magasin de détail dans Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="8bfec-108">Configure the sales tax for a retail store in Commerce headquarters</span></span>

<span data-ttu-id="8bfec-109">Pour configurer la taxe pour un magasin de détail dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="8bfec-109">To configure the sales tax for a retail store in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="8bfec-110">Accédez à **Retail et Commerce \> Canaux \> Tous les magasins**.</span><span class="sxs-lookup"><span data-stu-id="8bfec-110">Go to **Retail and Commerce \> Channels \> All stores**.</span></span>
1. <span data-ttu-id="8bfec-111">Sélectionnez le magasin pour lequel configurer la taxe.</span><span class="sxs-lookup"><span data-stu-id="8bfec-111">Select the store to configure sales tax for.</span></span>
1. <span data-ttu-id="8bfec-112">Sur le raccourci **Général**, dans la section **Taxe**, configurez les informations de taxe pour le magasin.</span><span class="sxs-lookup"><span data-stu-id="8bfec-112">On the **General** FastTab, in the **Sales tax** section, configure the sales tax information for the store.</span></span>

> [!NOTE]
> <span data-ttu-id="8bfec-113">Pour le retrait de produits dans un magasin, le groupe de taxe provient du magasin sélectionné pour le retrait.</span><span class="sxs-lookup"><span data-stu-id="8bfec-113">For product pickup from a store, the tax group comes from the store that is selected for pickup.</span></span> <span data-ttu-id="8bfec-114">Pour plus d’informations, voir [Paramétrage d’autres options de taxe pour les magasins](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span><span class="sxs-lookup"><span data-stu-id="8bfec-114">For more information, see [Set other tax options for stores](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span></span>

### <a name="configure-the-sales-tax-for-a-customers-address-in-commerce-headquarters"></a><span data-ttu-id="8bfec-115">Configurer la taxe pour l’adresse d’un client dans Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="8bfec-115">Configure the sales tax for a customer's address in Commerce headquarters</span></span>

<span data-ttu-id="8bfec-116">Pour configurer la taxe pour l’adresse d’un client dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="8bfec-116">To configure the sales tax for a customer's address in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="8bfec-117">Allez dans **Comptabilité client \> Clients \> Tous les clients**.</span><span class="sxs-lookup"><span data-stu-id="8bfec-117">Go to **Accounts receivable \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="8bfec-118">Sélectionnez le client pour lequel vous voulez configurer la taxe.</span><span class="sxs-lookup"><span data-stu-id="8bfec-118">Select the customer to configure sales taxes for.</span></span>
1. <span data-ttu-id="8bfec-119">Sur le raccourci **Adresses**, sélectionnez l’adresse pour laquelle configurer les taxes, sélectionnez **Plus d’options**, puis **Avancé**.</span><span class="sxs-lookup"><span data-stu-id="8bfec-119">On the **Addresses** FastTab, select the address to configure sales taxes for, select **More options**, and then select **Advanced**.</span></span>
1. <span data-ttu-id="8bfec-120">Sous le raccourci **Général**, sélectionnez le **Groupe de taxe**.</span><span class="sxs-lookup"><span data-stu-id="8bfec-120">On the **General** FastTab, select the **Tax group**.</span></span>
1. <span data-ttu-id="8bfec-121">Dans le champ **Taxe**, sélectionnez la valeur appropriée.</span><span class="sxs-lookup"><span data-stu-id="8bfec-121">In the **Sales tax** field, select the appropriate value.</span></span>

> [!NOTE]
> <span data-ttu-id="8bfec-122">Pour les expéditions impliquant une taxe sur l’adresse du client, l’adresse de livraison de la ligne détermine le groupe de taxe de la ligne.</span><span class="sxs-lookup"><span data-stu-id="8bfec-122">For shipping that involves sales tax on the customer's address, the delivery address of the line determines the tax group for the line.</span></span> <span data-ttu-id="8bfec-123">Si le client expédie à une adresse existante pour laquelle un groupe de taxe est déjà configuré, le groupe de taxe existant sera utilisé.</span><span class="sxs-lookup"><span data-stu-id="8bfec-123">If the customer is shipping to an existing address that has a tax group that is already configured, the existing tax group will be used.</span></span> <span data-ttu-id="8bfec-124">Par défaut, les adresses n’ont pas de groupe de taxe lorsqu’elles sont créées.</span><span class="sxs-lookup"><span data-stu-id="8bfec-124">By default, addresses don't have a tax group when they are created.</span></span>

### <a name="configure-general-sales-tax-groups-in-commerce-headquarters"></a><span data-ttu-id="8bfec-125">Configurer les groupes de taxe générale dans Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="8bfec-125">Configure general sales tax groups in Commerce headquarters</span></span>

<span data-ttu-id="8bfec-126">Pour configurer les groupes de taxe générale dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="8bfec-126">To configure general sales tax groups in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="8bfec-127">Accédez à **Taxe \> Taxes indirectes \> Taxe \> Groupes de taxe**.</span><span class="sxs-lookup"><span data-stu-id="8bfec-127">Go to **Tax \> Indirect taxes \> Sales tax \> Sales tax group**.</span></span>
1. <span data-ttu-id="8bfec-128">Dans le volet de navigation de gauche, sélectionnez le groupe de taxe à configurer.</span><span class="sxs-lookup"><span data-stu-id="8bfec-128">In the left navigation, select the tax group to configure.</span></span>
1. <span data-ttu-id="8bfec-129">Sur le raccourci **Taxe selon la destination de vente au détail**, configurez les taxes pour le groupe de taxe.</span><span class="sxs-lookup"><span data-stu-id="8bfec-129">On the **Retail destination based tax** FastTab, configure the taxes for the sales tax group.</span></span>

> [!NOTE]
> <span data-ttu-id="8bfec-130">Pour les expéditions qui n’impliquent pas de taxe sur l’adresse du client, l’adresse de livraison de la ligne et les taxes selon la destination qui sont configurées pour le groupe de taxe déterminent le groupe de taxe.</span><span class="sxs-lookup"><span data-stu-id="8bfec-130">For shipping that doesn't involve sales tax on the customer's address, the delivery address of the line and the destination-based taxes that are configured for the tax group determine the tax group.</span></span> <span data-ttu-id="8bfec-131">Pour plus d’informations, voir [Configurer les taxes pour les magasins en ligne en fonction de la destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span><span class="sxs-lookup"><span data-stu-id="8bfec-131">For more information, see [Set up taxes for online stores based on destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8bfec-132">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="8bfec-132">Additional resources</span></span>

[<span data-ttu-id="8bfec-133">Configurer la taxe pour les commandes en ligne</span><span class="sxs-lookup"><span data-stu-id="8bfec-133">Configure sales tax for online orders</span></span>](../sales-tax-config.md)
