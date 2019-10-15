---
title: Retourner des articles pour plusieurs commandes et factures client
description: Cette rubrique décrit la fonctionnalité d'activation des retours pour plusieurs commandes et factures client dans Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 03/05/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 25a1081e5f903076e23089c41dda7437f8a70124
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2017987"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="1b420-103">Retourner des articles pour plusieurs commandes et factures client</span><span class="sxs-lookup"><span data-stu-id="1b420-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="1b420-104">Il est possible d'effectuer des retours pour plusieurs commandes et factures client.</span><span class="sxs-lookup"><span data-stu-id="1b420-104">Returns can be made across multiple orders and invoices.</span></span> 

## <a name="configure-retail-to-support-returns-across-multiple-customer-order-and-invoices"></a><span data-ttu-id="1b420-105">Configurer Retail pour prendre en charge les retours pour plusieurs commandes et factures client</span><span class="sxs-lookup"><span data-stu-id="1b420-105">Configure Retail to support returns across multiple customer order and invoices</span></span>

1. <span data-ttu-id="1b420-106">Accédez à **Paramètres des ventes au détail \> Commandes client**.</span><span class="sxs-lookup"><span data-stu-id="1b420-106">Go to **Retail parameters \> Customer orders**.</span></span>
1. <span data-ttu-id="1b420-107">Activez le paramètre **Activer les retours pour plusieurs commandes**.</span><span class="sxs-lookup"><span data-stu-id="1b420-107">Turn on the **Enable returns for multiple orders** parameter.</span></span> 

## <a name="process-returns"></a><span data-ttu-id="1b420-108">Traiter les retours</span><span class="sxs-lookup"><span data-stu-id="1b420-108">Process returns</span></span>

<span data-ttu-id="1b420-109">Une fois que le paramètre est activé et que les modifications sont synchronisées avec les magasins, le caissier du magasin peut sélectionner plusieurs commandes d'un client pour les retourner.</span><span class="sxs-lookup"><span data-stu-id="1b420-109">After the parameter is turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="1b420-110">Lorsque les commandes sont sélectionnées, la liste de tous les produits retournables pour toutes les factures des commandes s'affiche.</span><span class="sxs-lookup"><span data-stu-id="1b420-110">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="1b420-111">Le caissier peut ensuite sélectionner les produits à retourner.</span><span class="sxs-lookup"><span data-stu-id="1b420-111">The cashier can then select the products to return.</span></span> <span data-ttu-id="1b420-112">Un ordre de retour unique sera créé pour tous les produits sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="1b420-112">A single return order will be created for all the selected products.</span></span>
