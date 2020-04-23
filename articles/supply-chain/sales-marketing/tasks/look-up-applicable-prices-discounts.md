---
title: Rechercher les prix et remises applicables
description: Cette procédure décrit comment rechercher le prix ou la remise pour un produit qui est actuellement valide pour un client spécifique, sans créer de commande client.
author: omulvad
manager: tfehr
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4ea4c7db203d0b47c59b241c9d89c69c71cf6cb1
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211926"
---
# <a name="look-up-applicable-prices-and-discounts"></a><span data-ttu-id="e44fc-103">Rechercher les prix et remises applicables</span><span class="sxs-lookup"><span data-stu-id="e44fc-103">Look up applicable prices and discounts</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e44fc-104">Cette procédure décrit comment rechercher le prix ou la remise pour un produit qui est actuellement valide pour un client spécifique, sans créer de commande client.</span><span class="sxs-lookup"><span data-stu-id="e44fc-104">This procedure shows how to find the price and/or discount for a product which is currently valid for a specific customer, without creating a sales order.</span></span> <span data-ttu-id="e44fc-105">La procédure décrit un exemple spécifique et vous devez suivre l'exemple à l'aide de la société de démonstration USMF afin de sélectionner les valeurs nécessaires.</span><span class="sxs-lookup"><span data-stu-id="e44fc-105">The procedure walks through a specific example, and you need follow the example using the USMF demo company in order to select the necessary values.</span></span>


## <a name="find-the-applicable-price"></a><span data-ttu-id="e44fc-106">Rechercher le prix applicable</span><span class="sxs-lookup"><span data-stu-id="e44fc-106">Find the applicable price</span></span>
1. <span data-ttu-id="e44fc-107">Accédez à Ventes et marketing > Prix et remises > Rechercher des prix.</span><span class="sxs-lookup"><span data-stu-id="e44fc-107">Go to Sales and marketing > Prices and discounts > Find prices.</span></span>
2. <span data-ttu-id="e44fc-108">Dans le champ Compte client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e44fc-108">In the Customer account field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="e44fc-109">Dans la liste, recherchez et sélectionnez le client US-001.</span><span class="sxs-lookup"><span data-stu-id="e44fc-109">In the list, find and select customer US-001.</span></span>
4. <span data-ttu-id="e44fc-110">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e44fc-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="e44fc-111">Entrez « T0004 » dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="e44fc-111">In the Item number field, type 'T0004'.</span></span>
    * <span data-ttu-id="e44fc-112">Par défaut, le champ Quantité est défini sur 1.</span><span class="sxs-lookup"><span data-stu-id="e44fc-112">By default, the Quantity field is set to 1.</span></span> <span data-ttu-id="e44fc-113">Toutefois, si vous connaissez la taille de la commande que le client a l'intention de passer pour le produit en question, entrez cette valeur à la place.</span><span class="sxs-lookup"><span data-stu-id="e44fc-113">However, if you know the size of the order that the customer intends to place for the product in question, then enter this value instead.</span></span> <span data-ttu-id="e44fc-114">Ces informations sont pertinentes si les accords commerciaux avec le client sont soumis à la quantité (en d'autres termes, que le prix du produit dépend de la quantité minimale achetée).</span><span class="sxs-lookup"><span data-stu-id="e44fc-114">This information is relevant if the trade agreements with the customer have quantity breaks, that is, the product's price depends on the minimum quantity purchased.</span></span>  
6. <span data-ttu-id="e44fc-115">Dans le champ Date, entrez la date à laquelle le client compte passer une commande.</span><span class="sxs-lookup"><span data-stu-id="e44fc-115">In the Date field, enter a date for when the customer expects to place an order.</span></span> 
    * <span data-ttu-id="e44fc-116">La date peut être celle d'aujourd'hui ou n'importe quelle date ultérieure.</span><span class="sxs-lookup"><span data-stu-id="e44fc-116">The date can be today's date or any date in the future.</span></span>  
    * <span data-ttu-id="e44fc-117">Le système renvoie désormais le prix qui est valide pour le produit sélectionné une fois acheté par le client sélectionné à la date sélectionnée avec une quantité spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e44fc-117">The system now returns the price that is valid for the selected product when bought by the selected customer on the selected date with a specified quantity.</span></span> <span data-ttu-id="e44fc-118">Dans cet exemple, si le client US-001 achetait 1 unités du produit T0004 aujourd'hui, il paierait 350 CAD l'unité.</span><span class="sxs-lookup"><span data-stu-id="e44fc-118">In this example, if the customer US-001 bought 1 unit of product T0004 today, they would be charged 350 CAD a unit.</span></span> <span data-ttu-id="e44fc-119">Ce prix provient d'un accord commercial existant et actif passé avec le client.</span><span class="sxs-lookup"><span data-stu-id="e44fc-119">This price comes from an existing and active trade agreement with the customer.</span></span>      <span data-ttu-id="e44fc-120">D'autres champs de la page fournissent plus de détails sur le prix et le coût du produit (si le paramétrage a été effectué sur le produit générique), ainsi que sur la rentabilité calculée.</span><span class="sxs-lookup"><span data-stu-id="e44fc-120">Other fields on the page provide more details about the product price and product cost (if set up on the product master), and calculated profitability.</span></span>  
    * <span data-ttu-id="e44fc-121">Si l'option Afficher les variantes de produits associées est activée, cela signifie qu'il existe des accords commerciaux supplémentaires pour les variantes du produit.</span><span class="sxs-lookup"><span data-stu-id="e44fc-121">If the Show related product variants option is selected, it means that there are additional trade agreements for product's variants.</span></span>  
7. <span data-ttu-id="e44fc-122">Cliquez sur la case à cocher Afficher les variantes de produits associées.</span><span class="sxs-lookup"><span data-stu-id="e44fc-122">Click the Show related product variants checkbox.</span></span>
    * <span data-ttu-id="e44fc-123">La liste des variantes de produit s'affiche, avec des informations sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="e44fc-123">A list of the product variants is shown, with information about their dimensions.</span></span>  
8. <span data-ttu-id="e44fc-124">Dans la liste, marquez la ligne représentant la couleur Blanc.</span><span class="sxs-lookup"><span data-stu-id="e44fc-124">In the list, mark the line representing color White.</span></span>
    * <span data-ttu-id="e44fc-125">Notez que le prix du produit est désormais différent de celui précédemment affiché lorsqu'il n'était pas spécifié par dimension.</span><span class="sxs-lookup"><span data-stu-id="e44fc-125">Notice, that the product price is now different from the one displayed previously when it was not specified per dimension.</span></span>  
9. <span data-ttu-id="e44fc-126">Cliquez sur Afficher les prix de vente.</span><span class="sxs-lookup"><span data-stu-id="e44fc-126">Click View sales prices.</span></span>
    * <span data-ttu-id="e44fc-127">La page Prix (ventes) affiche tous les accords commerciaux applicables au produit, y compris ses variantes.</span><span class="sxs-lookup"><span data-stu-id="e44fc-127">The Price (sales) page displays all the trade agreements applicable to the product, including its variants.</span></span>  
10. <span data-ttu-id="e44fc-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e44fc-128">Close the page.</span></span>

## <a name="find-the-applicable-discount"></a><span data-ttu-id="e44fc-129">Rechercher la remise applicable</span><span class="sxs-lookup"><span data-stu-id="e44fc-129">Find the applicable discount</span></span>
<span data-ttu-id="e44fc-130">Vérifiez que le champ Compte client contient le numéro de client US-001 </span><span class="sxs-lookup"><span data-stu-id="e44fc-130">Make sure the Customer account field contains customer number US-001</span></span>   
1. <span data-ttu-id="e44fc-131">Entrez « T0012 » dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="e44fc-131">In the Item number field, type 'T0012'.</span></span>
    * <span data-ttu-id="e44fc-132">Veillez à ce que le champ Quantité soit défini sur 1.</span><span class="sxs-lookup"><span data-stu-id="e44fc-132">Make sure the Quantity field is set to 1.</span></span>  
    * <span data-ttu-id="e44fc-133">Les informations suivantes de tarification indiqués pour le produit T0012 proviennent d'un ou plusieurs accords commerciaux : le prix unitaire est de 1 000 CAD et le pourcentage de remise est de 5.</span><span class="sxs-lookup"><span data-stu-id="e44fc-133">The following pricing details shown for product T0012 come from one or more trade agreements: The unit price is 1,000 CAD and the discount percentage is 5.</span></span>  
2. <span data-ttu-id="e44fc-134">Définir la Quantité sur « 20 ».</span><span class="sxs-lookup"><span data-stu-id="e44fc-134">Set Quantity to '20'.</span></span>
    * <span data-ttu-id="e44fc-135">La quantité de commande augmentée entraîne le passage de la remises ligne offerte au client de 5 à 7 %.</span><span class="sxs-lookup"><span data-stu-id="e44fc-135">The increased order quantity causes the line discount that will be offered to the customer to change from 5 to 7 percent.</span></span>  
    * <span data-ttu-id="e44fc-136">Le Montant net est calculé sur le prix unitaire, la remise et la quantité totale.</span><span class="sxs-lookup"><span data-stu-id="e44fc-136">The Net amount is calculated based on the unit price, discount and the total quantity.</span></span>  
3. <span data-ttu-id="e44fc-137">Cliquez sur Afficher la remise ligne.</span><span class="sxs-lookup"><span data-stu-id="e44fc-137">Click View line discount.</span></span>
    * <span data-ttu-id="e44fc-138">Il existe deux accords de remise de ligne pour le produit T0012, spécifiant une remise de 5 % pour une quantité de ligne de commande de 1 à 10 et de 7 % pour les quantités de commande au-dessus de 10.</span><span class="sxs-lookup"><span data-stu-id="e44fc-138">There are two line discount agreements for product T0012, specifying a 5 percent discount for an order line quantity from 1 to 10, and 7 percent discount for order quantities above 10.</span></span> <span data-ttu-id="e44fc-139">Notez que les remises sont appliquées à un groupe de produits, dans cet exemple, le code du groupe 01 auquel le produit T0012 appartient.</span><span class="sxs-lookup"><span data-stu-id="e44fc-139">Note that the discounts are applied to a group of products, in this example, Group code 01, of which product T0012 is a member.</span></span>  
4. <span data-ttu-id="e44fc-140">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e44fc-140">Close the page.</span></span>

