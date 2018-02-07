---
title: "Expédier une commande depuis un autre magasin"
description: "Cette rubrique décrit la fonction Facturer l'envoi."
author: ashishmsft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 7612935c42ee7b28e1d1e24b22801e31114dc675
ms.contentlocale: fr-fr
ms.lasthandoff: 02/07/2018

---

# <a name="ship-an-order-from-a-different-store"></a><span data-ttu-id="804c0-103">Expédier une commande depuis un autre magasin</span><span class="sxs-lookup"><span data-stu-id="804c0-103">Ship an order from a different store</span></span>

<span data-ttu-id="804c0-104">Avec la fonction Facturer l'envoi de Dynamics 365 for Retail, les commandes client peuvent être passées dans un magasin et expédiées depuis un autre magasin.</span><span class="sxs-lookup"><span data-stu-id="804c0-104">With the Charge send feature in Dynamics 365 for Retail, customer orders can be placed in one store and shipped from another store.</span></span> <span data-ttu-id="804c0-105">Les commandes client du point de vente (PDV) prennent en charge les plusieurs options d'exécution.</span><span class="sxs-lookup"><span data-stu-id="804c0-105">Customer orders in the point of sale (POS) client support multiple fulfillment options.</span></span> <span data-ttu-id="804c0-106">Parmi les options d'exécution de commande notons :</span><span class="sxs-lookup"><span data-stu-id="804c0-106">Some examples of fulfillment options include:</span></span>
-   <span data-ttu-id="804c0-107">Prélèvement dans le même magasin à une date différente.</span><span class="sxs-lookup"><span data-stu-id="804c0-107">Pick up from the same store on a different date.</span></span>
-   <span data-ttu-id="804c0-108">Prélèvement dans un autre magasin à la même date ou à une date différente.</span><span class="sxs-lookup"><span data-stu-id="804c0-108">Pick up from a different store on the same date or a different date.</span></span>
-   <span data-ttu-id="804c0-109">Expédition depuis l'entrepôt d'expédition affecté par défaut au magasin, et livraison à une date spécifique.</span><span class="sxs-lookup"><span data-stu-id="804c0-109">Ship from the default shipping warehouse that is assigned to the store, and deliver on a specific date.</span></span>

<span data-ttu-id="804c0-110">La fonction Facturer l'envoi utilise les opérations du PDV suivantes : Expédier tous les produits et Expédier les produits sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="804c0-110">The Charge send feature uses the following POS operations: Ship all products and Ship selected products.</span></span> <span data-ttu-id="804c0-111">Cela permet au commis de magasin de sélectionner l'emplacement d'« expédition » à partir duquel la commande ou la ligne de commande peut être honorée.</span><span class="sxs-lookup"><span data-stu-id="804c0-111">This allows the store clerk to select the “ship from” location that the order or order line can be fulfilled from.</span></span> <span data-ttu-id="804c0-112">Par défaut, l'emplacement d'« expédition » est l'entrepôt d'expédition associé au magasin.</span><span class="sxs-lookup"><span data-stu-id="804c0-112">By default, the “ship from” location is the shipping warehouse that is associated with the store.</span></span> <span data-ttu-id="804c0-113">Toutefois, le commis de magasin peut modifier cet emplacement et sélectionner n'importe quel magasin défini dans le groupe de localisateurs de magasin affecté au magasin.</span><span class="sxs-lookup"><span data-stu-id="804c0-113">However, the store clerk can change this location and select any store that is defined in the store locator group that is assigned to the store.</span></span> 

<span data-ttu-id="804c0-114">La capacité de sélectionner des adresses d'« expédition » reste inchangée.</span><span class="sxs-lookup"><span data-stu-id="804c0-114">The ability to select “ship to” addresses remains unchanged.</span></span> 

<span data-ttu-id="804c0-115">Les méthodes d'expédition qui peuvent être utilisées pour honorer la ligne de commande sont basées sur la configuration de modes de livraison valides pour les produits et les adresses.</span><span class="sxs-lookup"><span data-stu-id="804c0-115">The shipping methods that can be used to fulfill the order line are based on the configuration of valid modes of delivery for products and addresses.</span></span> <span data-ttu-id="804c0-116">Du fait que les règles sur les modes de livraison valides sont tenues à jour uniquement dans Retail Siège, un client du PDV effectue un appel en temps réel pour extraire les modes de livraison valides pour une ligne d'expédition.</span><span class="sxs-lookup"><span data-stu-id="804c0-116">Because the rules about valid of modes of delivery are maintained only in the Retail headquarters (HQ), the POS client makes a real-time call to fetch the valid modes of delivery for a ship line.</span></span> 


