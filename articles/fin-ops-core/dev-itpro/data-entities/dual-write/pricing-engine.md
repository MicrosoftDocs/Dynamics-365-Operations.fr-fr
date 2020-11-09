---
title: Synchroniser avec le moteur de tarification Dynamics 365 Supply Chain Management à la demande
description: Cette rubrique décrit comment utiliser le moteur de tarification dans Microsoft Dynamics 365 Supply Chain Management depuis Dynamics 365 Sales.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 740ae20704abd9c59f64c2c7622fa96d65dccb1d
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997144"
---
# <a name="sync-with-the-dynamics-365-supply-chain-management-pricing-engine-on-demand"></a><span data-ttu-id="bbc67-103">Synchroniser avec le moteur de tarification Dynamics 365 Supply Chain Management à la demande</span><span class="sxs-lookup"><span data-stu-id="bbc67-103">Sync with the Dynamics 365 Supply Chain Management pricing engine on demand</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="bbc67-104">Microsoft Dynamics 365 Supply Chain Management comprend un moteur de tarification qui gère les accords commerciaux, les listes de prix, les programmes de fidélisation de la clientèle, les promotions et les remises.</span><span class="sxs-lookup"><span data-stu-id="bbc67-104">Microsoft Dynamics 365 Supply Chain Management includes a pricing engine that handles trade agreements, price lists, customer loyalty programs, promotions, and discounts.</span></span> <span data-ttu-id="bbc67-105">Le moteur de tarification utilise des règles complexes pour déterminer le meilleur prix pour une offre ou une commande donnée.</span><span class="sxs-lookup"><span data-stu-id="bbc67-105">The pricing engine uses complex rules to determine the best price for a given quotation or order.</span></span> <span data-ttu-id="bbc67-106">Lorsque vous utilisez la double écriture, vous utilisez la tarification statique ou le moteur de tarification de Dynamics 365 Supply Chain Management sur les pages Devis et Commande dans Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="bbc67-106">When you use dual-write, you use either static pricing or the pricing engine from Dynamics 365 Supply Chain Management on the Quote and Order pages in Dynamics 365 Sales.</span></span>

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a><span data-ttu-id="bbc67-107">Utiliser le moteur de tarification de Supply Chain Management dans Sales</span><span class="sxs-lookup"><span data-stu-id="bbc67-107">Use the pricing engine from Supply Chain Management in Sales</span></span>

1. <span data-ttu-id="bbc67-108">Dans Sales, accédez à **Ventes \> Commandes**.</span><span class="sxs-lookup"><span data-stu-id="bbc67-108">In Sales, go to **Sales \> Orders**.</span></span>
2. <span data-ttu-id="bbc67-109">Sélectionnez **Nouveau** pour créer une commande, ou sélectionnez une commande existante dans la liste **Mes commandes**.</span><span class="sxs-lookup"><span data-stu-id="bbc67-109">Select **New** to create a new order, or select an existing order in the **My Orders** list.</span></span>
3. <span data-ttu-id="bbc67-110">Ajoutez une nouvelle ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="bbc67-110">Add a new order line.</span></span>
4. <span data-ttu-id="bbc67-111">Si vous créez une commande, sélectionnez **Ordre de prix** sur le volet Action.</span><span class="sxs-lookup"><span data-stu-id="bbc67-111">If you're creating a new order, select **Price Order** on the Action Pane.</span></span> <span data-ttu-id="bbc67-112">Si vous mettez à jour une commande existante, sélectionnez **Recalculer** sur le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="bbc67-112">If you're updating an existing order, select **Recalculate** on the Action Pane.</span></span>

    <span data-ttu-id="bbc67-113">Les champs suivants sont complétés automatiquement dans :</span><span class="sxs-lookup"><span data-stu-id="bbc67-113">The following fields are automatically filled in:</span></span>

    + <span data-ttu-id="bbc67-114">Montant détaillé</span><span class="sxs-lookup"><span data-stu-id="bbc67-114">Detail Amount</span></span>
    + <span data-ttu-id="bbc67-115">Remise %</span><span class="sxs-lookup"><span data-stu-id="bbc67-115">Discount %</span></span>
    + <span data-ttu-id="bbc67-116">Remise</span><span class="sxs-lookup"><span data-stu-id="bbc67-116">Discount</span></span>
    + <span data-ttu-id="bbc67-117">Montant avant le transport</span><span class="sxs-lookup"><span data-stu-id="bbc67-117">Pre-Freight Amount</span></span>
    + <span data-ttu-id="bbc67-118">Montant du transport</span><span class="sxs-lookup"><span data-stu-id="bbc67-118">Freight Amount</span></span>
    + <span data-ttu-id="bbc67-119">Total des taxes</span><span class="sxs-lookup"><span data-stu-id="bbc67-119">Total Tax</span></span>
    + <span data-ttu-id="bbc67-120">Montant total</span><span class="sxs-lookup"><span data-stu-id="bbc67-120">Total Amount</span></span>
    
5. <span data-ttu-id="bbc67-121">Pour garantir que le système prend en compte les accords commerciaux et les contrats de vente pour calculer le prix :</span><span class="sxs-lookup"><span data-stu-id="bbc67-121">To ensure that the system considers trade and sales agreements to calculate the price:</span></span>
    1. <span data-ttu-id="bbc67-122">Accédez à votre environnement Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bbc67-122">Navigate to your Supply Chain Management environment.</span></span>
    2. <span data-ttu-id="bbc67-123">Accédez à **Comptabilité client \> Configuration \> Paramètres de la comptabilité client**.</span><span class="sxs-lookup"><span data-stu-id="bbc67-123">Navigate to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
    3. <span data-ttu-id="bbc67-124">Sélectionnez l'onglet **Prix** dans la barre de navigation latérale.</span><span class="sxs-lookup"><span data-stu-id="bbc67-124">Select the **Prices** tab in the side navigation bar.</span></span>
    4. <span data-ttu-id="bbc67-125">Sous l'organisateur **Évaluation des accords commerciaux** , décochez l'option **Saisie manuelle**.</span><span class="sxs-lookup"><span data-stu-id="bbc67-125">Under the **Trade agreement evaluation** fastab, uncheck the **Manual entry** option.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="bbc67-126">Comment ça fonctionne</span><span class="sxs-lookup"><span data-stu-id="bbc67-126">How it works</span></span>

<span data-ttu-id="bbc67-127">Lorsque vous sélectionnez **Ordre de prix** dans Sales, la fonction **Totaux** sur l'onglet **Commande client \> Vue** dans Supply Chain Management est appelé pour la commande client associée.</span><span class="sxs-lookup"><span data-stu-id="bbc67-127">When you select **Price Order** in Sales, the **Totals** function on the **Sales Order \> View** tab in Supply Chain Management is called for the associated sales order.</span></span> <span data-ttu-id="bbc67-128">Les valeurs du total de la commande dans Sales sont utilisées pour remplir les champs correspondants dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bbc67-128">The values in the order total in Sales are used to fill in the corresponding fields in Supply Chain Management.</span></span>

<span data-ttu-id="bbc67-129">Lorsque le total de la commande client est calculé dans Supply Chain Management, le calcul évalue les accords commerciaux et les accords de vente existants pour le client et les produits répertoriés dans la commande client.</span><span class="sxs-lookup"><span data-stu-id="bbc67-129">When the sales order total is calculated in Supply Chain Management, the calculation evaluates the existing trade agreements and sales agreements for the customer and the products that are listed in the sales order.</span></span> <span data-ttu-id="bbc67-130">Ces informations sont utilisées pour calculer les totaux.</span><span class="sxs-lookup"><span data-stu-id="bbc67-130">This information is used to calculate the totals.</span></span> <span data-ttu-id="bbc67-131">Quand **Ordre de prix** est sélectionné, Sales reflète automatiquement toute la configuration effectuée dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bbc67-131">When **Price Order** is selected, Sales automatically reflects all the setup that has been done in Supply Chain Management.</span></span>

## <a name="limitations"></a><span data-ttu-id="bbc67-132">Limitations</span><span class="sxs-lookup"><span data-stu-id="bbc67-132">Limitations</span></span>

<span data-ttu-id="bbc67-133">Lorsque les champs de Sales sont remplis, les limitations suivantes s'appliquent :</span><span class="sxs-lookup"><span data-stu-id="bbc67-133">When the fields in Sales are filled in, the following limitations apply:</span></span>

+ <span data-ttu-id="bbc67-134">La configuration des frais et des allocations de frais dans Supply Chain Management n'est pas répliquée dans Sales.</span><span class="sxs-lookup"><span data-stu-id="bbc67-134">The setup of charges and charge allocations in Supply Chain Management isn't replicated in Sales.</span></span>
+ <span data-ttu-id="bbc67-135">Les prix ne tiennent pas compte des prix de détail spéciaux spécifiés dans le **Canal de vente au détail** sur la page de ligne de commande client dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bbc67-135">Pricing doesn't consider special retail pricing that is specified in the **Retail Channel** field on the sales order line page in Supply Chain Management.</span></span>
+ <span data-ttu-id="bbc67-136">Les remises définies dans la section **Gestion des reprises** de Supply Chain Management ne sont pas prises en compte.</span><span class="sxs-lookup"><span data-stu-id="bbc67-136">Discounts that are defined in the **Trade Allowance Management** section of Supply Chain Management aren't considered.</span></span>
