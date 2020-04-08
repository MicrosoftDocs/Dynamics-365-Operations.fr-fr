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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: ef4465144155130087b078f9f96911df38b62c41
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173175"
---
# <a name="sync-with-the-dynamics-365-supply-chain-management-pricing-engine-on-demand"></a><span data-ttu-id="21003-103">Synchroniser avec le moteur de tarification Dynamics 365 Supply Chain Management à la demande</span><span class="sxs-lookup"><span data-stu-id="21003-103">Sync with the Dynamics 365 Supply Chain Management pricing engine on demand</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="21003-104">Microsoft Dynamics 365 Supply Chain Management comprend un moteur de tarification qui gère les accords commerciaux, les listes de prix, les programmes de fidélisation de la clientèle, les promotions et les remises.</span><span class="sxs-lookup"><span data-stu-id="21003-104">Microsoft Dynamics 365 Supply Chain Management includes a pricing engine that handles trade agreements, price lists, customer loyalty programs, promotions, and discounts.</span></span> <span data-ttu-id="21003-105">Le moteur de tarification utilise des règles complexes pour déterminer le meilleur prix pour une offre ou une commande donnée.</span><span class="sxs-lookup"><span data-stu-id="21003-105">The pricing engine uses complex rules to determine the best price for a given quotation or order.</span></span> <span data-ttu-id="21003-106">Lorsque vous utilisez la double écriture, vous utilisez la tarification statique ou le moteur de tarification de Dynamics 365 Supply Chain Management sur les pages Devis et Commande dans Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="21003-106">When you use dual-write, you use either static pricing or the pricing engine from Dynamics 365 Supply Chain Management on the Quote and Order pages in Dynamics 365 Sales.</span></span>

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a><span data-ttu-id="21003-107">Utiliser le moteur de tarification de Supply Chain Management dans Sales</span><span class="sxs-lookup"><span data-stu-id="21003-107">Use the pricing engine from Supply Chain Management in Sales</span></span>

1. <span data-ttu-id="21003-108">Dans Sales, accédez à **Ventes \> Commandes**.</span><span class="sxs-lookup"><span data-stu-id="21003-108">In Sales, go to **Sales \> Orders**.</span></span>
2. <span data-ttu-id="21003-109">Sélectionnez **Nouveau** pour créer une commande, ou sélectionnez une commande existante dans la liste **Mes commandes**.</span><span class="sxs-lookup"><span data-stu-id="21003-109">Select **New** to create a new order, or select an existing order in the **My Orders** list.</span></span>
3. <span data-ttu-id="21003-110">Ajoutez une nouvelle ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="21003-110">Add a new order line.</span></span>
4. <span data-ttu-id="21003-111">Si vous créez une commande, sélectionnez **Ordre de prix** sur le volet Action.</span><span class="sxs-lookup"><span data-stu-id="21003-111">If you're creating a new order, select **Price Order** on the Action Pane.</span></span> <span data-ttu-id="21003-112">Si vous mettez à jour une commande existante, sélectionnez **Recalculer** sur le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="21003-112">If you're updating an existing order, select **Recalculate** on the Action Pane.</span></span>

    <span data-ttu-id="21003-113">Les champs suivants sont complétés automatiquement dans :</span><span class="sxs-lookup"><span data-stu-id="21003-113">The following fields are automatically filled in:</span></span>

    + <span data-ttu-id="21003-114">Montant détaillé</span><span class="sxs-lookup"><span data-stu-id="21003-114">Detail Amount</span></span>
    + <span data-ttu-id="21003-115">Remise %</span><span class="sxs-lookup"><span data-stu-id="21003-115">Discount %</span></span>
    + <span data-ttu-id="21003-116">Remise</span><span class="sxs-lookup"><span data-stu-id="21003-116">Discount</span></span>
    + <span data-ttu-id="21003-117">Montant avant le transport</span><span class="sxs-lookup"><span data-stu-id="21003-117">Pre-Freight Amount</span></span>
    + <span data-ttu-id="21003-118">Montant du transport</span><span class="sxs-lookup"><span data-stu-id="21003-118">Freight Amount</span></span>
    + <span data-ttu-id="21003-119">Total des taxes</span><span class="sxs-lookup"><span data-stu-id="21003-119">Total Tax</span></span>
    + <span data-ttu-id="21003-120">Montant total</span><span class="sxs-lookup"><span data-stu-id="21003-120">Total Amount</span></span>

## <a name="how-it-works"></a><span data-ttu-id="21003-121">Comment ça fonctionne</span><span class="sxs-lookup"><span data-stu-id="21003-121">How it works</span></span>

<span data-ttu-id="21003-122">Lorsque vous sélectionnez **Ordre de prix** dans Sales, la fonction **Totaux** sur l'onglet **Commande client \> Vue** dans Supply Chain Management est appelé pour la commande client associée.</span><span class="sxs-lookup"><span data-stu-id="21003-122">When you select **Price Order** in Sales, the **Totals** function on the **Sales Order \> View** tab in Supply Chain Management is called for the associated sales order.</span></span> <span data-ttu-id="21003-123">Les valeurs du total de la commande dans Sales sont utilisées pour remplir les champs correspondants dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="21003-123">The values in the order total in Sales are used to fill in the corresponding fields in Supply Chain Management.</span></span>

<span data-ttu-id="21003-124">Lorsque le total de la commande client est calculé dans Supply Chain Management, le calcul évalue les accords commerciaux et les accords de vente existants pour le client et les produits répertoriés dans la commande client.</span><span class="sxs-lookup"><span data-stu-id="21003-124">When the sales order total is calculated in Supply Chain Management, the calculation evaluates the existing trade agreements and sales agreements for the customer and the products that are listed in the sales order.</span></span> <span data-ttu-id="21003-125">Ces informations sont utilisées pour calculer les totaux.</span><span class="sxs-lookup"><span data-stu-id="21003-125">This information is used to calculate the totals.</span></span> <span data-ttu-id="21003-126">Quand **Ordre de prix** est sélectionné, Sales reflète automatiquement toute la configuration effectuée dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="21003-126">When **Price Order** is selected, Sales automatically reflects all the setup that has been done in Supply Chain Management.</span></span>

## <a name="limitations"></a><span data-ttu-id="21003-127">Limitations</span><span class="sxs-lookup"><span data-stu-id="21003-127">Limitations</span></span>

<span data-ttu-id="21003-128">Lorsque les champs de Sales sont remplis, les limitations suivantes s'appliquent :</span><span class="sxs-lookup"><span data-stu-id="21003-128">When the fields in Sales are filled in, the following limitations apply:</span></span>

+ <span data-ttu-id="21003-129">La configuration des frais et des allocations de frais dans Supply Chain Management n'est pas répliquée dans Sales.</span><span class="sxs-lookup"><span data-stu-id="21003-129">The setup of charges and charge allocations in Supply Chain Management isn't replicated in Sales.</span></span>
+ <span data-ttu-id="21003-130">Les prix ne tiennent pas compte des prix de détail spéciaux spécifiés dans le **Canal de vente au détail** sur la page de ligne de commande client dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="21003-130">Pricing doesn't consider special retail pricing that is specified in the **Retail Channel** field on the sales order line page in Supply Chain Management.</span></span>
+ <span data-ttu-id="21003-131">Les remises définies dans la section **Gestion des reprises** de Supply Chain Management ne sont pas prises en compte.</span><span class="sxs-lookup"><span data-stu-id="21003-131">Discounts that are defined in the **Trade Allowance Management** section of Supply Chain Management aren't considered.</span></span>
