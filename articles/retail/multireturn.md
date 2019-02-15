---
title: Retourner des articles pour plusieurs commandes et factures client
description: Cette rubrique décrit la fonctionnalité d'activation des retours pour plusieurs commandes et factures client dans Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 1/08/2019
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
ms.openlocfilehash: d2cf6f92e90ef196827abb599c65c732615ec7bb
ms.sourcegitcommit: e72eae546d48d41d4b07ff78cfc0242c32b793e7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2019
ms.locfileid: "373066"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="3922e-103">Retourner des articles pour plusieurs commandes et factures client</span><span class="sxs-lookup"><span data-stu-id="3922e-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

<span data-ttu-id="3922e-104">Dans Dynamics 365 for Finance and Operations version 10.0, les retours peuvent être effectués pour plusieurs commandes et factures, alors que dans les versions antérieures à la version 10,0, les retours ne pouvaient être traités que pour une seule facture à la fois.</span><span class="sxs-lookup"><span data-stu-id="3922e-104">In Dynamics 365 for Finance and Operations version 10.0, returns can be made across multiple orders and invoices, whereas in releases prior to 10.0, returns could only be processed by a single invoice at a time.</span></span> 

## <a name="configure-retail-to-support-returns-across-multiple-customer-order-and-invoices"></a><span data-ttu-id="3922e-105">Configurer Retail pour prendre en charge les retours pour plusieurs commandes et factures client</span><span class="sxs-lookup"><span data-stu-id="3922e-105">Configure Retail to support returns across multiple customer order and invoices</span></span>

1. <span data-ttu-id="3922e-106">Accédez à **Paramètres Retail \> Commandes client**.</span><span class="sxs-lookup"><span data-stu-id="3922e-106">Go to **Retail parameters \> Customer orders**.</span></span>
1. <span data-ttu-id="3922e-107">Activez le paramètre **Activer les retours pour plusieurs commandes**.</span><span class="sxs-lookup"><span data-stu-id="3922e-107">Turn on the **Enable returns for multiple orders** parameter.</span></span> 

## <a name="process-returns"></a><span data-ttu-id="3922e-108">Traiter les retours</span><span class="sxs-lookup"><span data-stu-id="3922e-108">Process returns</span></span>

<span data-ttu-id="3922e-109">Une fois que le paramètre est activé et que les modifications sont synchronisées avec les magasins, le caissier du magasin peut sélectionner plusieurs commandes d'un client pour les retourner.</span><span class="sxs-lookup"><span data-stu-id="3922e-109">After the parameter is turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="3922e-110">Lorsque les commandes sont sélectionnées, la liste de tous les produits retournables pour toutes les factures des commandes s'affiche.</span><span class="sxs-lookup"><span data-stu-id="3922e-110">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="3922e-111">Le caissier peut ensuite sélectionner les produits à retourner.</span><span class="sxs-lookup"><span data-stu-id="3922e-111">The cashier can then select the products to return.</span></span> <span data-ttu-id="3922e-112">Un ordre de retour unique sera créé pour tous les produits sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="3922e-112">A single return order will be created for all the selected products.</span></span>
