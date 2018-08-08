---
title: "Contrôler le stock de consignation à l'aide de la collaboration fournisseur"
description: "Cette procédure indique comment utiliser la collaboration du fournisseur pour afficher des informations sur le niveau de stock du produit que vous avez placé en consignation auprès d'un client."
author: mkirknel
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 8e4a620fe5f5ab3c0fae8b04d79e9912111b7ece
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a><span data-ttu-id="eb8ce-103">Contrôler le stock de consignation à l'aide de la collaboration fournisseur</span><span class="sxs-lookup"><span data-stu-id="eb8ce-103">Monitor consignment inventory using vendor collaboration</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="eb8ce-104">Cette procédure indique comment utiliser la collaboration du fournisseur pour afficher des informations sur le niveau de stock du produit que vous avez placé en consignation auprès d'un client.</span><span class="sxs-lookup"><span data-stu-id="eb8ce-104">This procedure shows how to use vendor collaboration to see information about the stock level of product that you have placed in consignment with a customer.</span></span> <span data-ttu-id="eb8ce-105">Vous pouvez également contrôler la consommation du stock lorsque le client s'approprie le stock.</span><span class="sxs-lookup"><span data-stu-id="eb8ce-105">You can also monitor the consumption of the stock when the customer takes ownership of the inventory.</span></span> <span data-ttu-id="eb8ce-106">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="eb8ce-106">You can use this procedure in the USMF demo data company.</span></span> <span data-ttu-id="eb8ce-107">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="eb8ce-107">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="view-consumed-inventory"></a><span data-ttu-id="eb8ce-108">Afficher le stock consommé</span><span class="sxs-lookup"><span data-stu-id="eb8ce-108">View consumed inventory</span></span>
1. <span data-ttu-id="eb8ce-109">Allez dans Collaborateur du fournisseur > Stock de consignation > Produits reçus à partir du stock de consignation.</span><span class="sxs-lookup"><span data-stu-id="eb8ce-109">Go to Vendor collaboration > Consignment inventory > Products received from consignment inventory.</span></span>
    * <span data-ttu-id="eb8ce-110">La liste affiche les lignes d'accusé de réception de marchandises qui ont été générées lorsque la propriété du stock de consignation est passée du fournisseur au client.</span><span class="sxs-lookup"><span data-stu-id="eb8ce-110">The list shows the product receipt lines that were generated when ownership of the consignment inventory was changed from the vendor to the customer.</span></span> <span data-ttu-id="eb8ce-111">Vous devrez peut-être faire défiler vers la droite pour afficher les quantités et d'autres informations.</span><span class="sxs-lookup"><span data-stu-id="eb8ce-111">You might have to scroll to the right to see quantities and other information.</span></span> <span data-ttu-id="eb8ce-112">Vous pouvez utiliser les informations de cette liste pour générer des factures pour votre client.</span><span class="sxs-lookup"><span data-stu-id="eb8ce-112">You can use the information in this list to generate invoices for your customer.</span></span> <span data-ttu-id="eb8ce-113">Vous pouvez également exporter les données vers Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="eb8ce-113">You can also export the data to Microsoft Excel.</span></span>   
2. <span data-ttu-id="eb8ce-114">Cliquez sur Afficher la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="eb8ce-114">Click View purchase order.</span></span>
3. <span data-ttu-id="eb8ce-115">Développez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="eb8ce-115">Expand the Line details section.</span></span>
    * <span data-ttu-id="eb8ce-116">La ligne est marquée comme consignation, et la section d'en-tête indique que la commande fournisseur a le statut Reçu.</span><span class="sxs-lookup"><span data-stu-id="eb8ce-116">The line is marked as Consignment, and the header section shows that the purchase order has a status of Received.</span></span>  
4. <span data-ttu-id="eb8ce-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="eb8ce-117">Close the page.</span></span>

## <a name="view-on-hand-inventory"></a><span data-ttu-id="eb8ce-118">Affichage du stock disponible</span><span class="sxs-lookup"><span data-stu-id="eb8ce-118">View on-hand inventory</span></span>
1. <span data-ttu-id="eb8ce-119">Allez dans Collaborateur du fournisseur > Stock de consignation > Stock de consignation disponible.</span><span class="sxs-lookup"><span data-stu-id="eb8ce-119">Go to Vendor collaboration > Consignment inventory > On-hand consignment inventory.</span></span>
    * <span data-ttu-id="eb8ce-120">La page Stock de consignation disponible indique le stock que vous possédez dans l'entrepôt du client.</span><span class="sxs-lookup"><span data-stu-id="eb8ce-120">The On-hand consignment inventory page shows the stock that you own at the customer’s warehouse.</span></span> <span data-ttu-id="eb8ce-121">Vous pouvez afficher des dimensions supplémentaires, telles que le site et l'entrepôt, en cliquant sur l'onglet Afficher les dimensions.</span><span class="sxs-lookup"><span data-stu-id="eb8ce-121">You can show additional dimensions, such as the site and warehouse, by clicking the Display dimensions tab.</span></span>   

