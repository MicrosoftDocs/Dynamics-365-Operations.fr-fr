---
title: Utiliser des catalogues externes pour PunchOut eProcurement
description: "Cette rubrique explique comment utiliser des catalogues externes pour créer et envoyer des demandes."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 035c5d15e5508c78dd66a349defd534bfecc96bb
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="use-external-catalogs-for-punchout-eprocurement"></a><span data-ttu-id="86e08-103">Utiliser des catalogues externes pour PunchOut eProcurement</span><span class="sxs-lookup"><span data-stu-id="86e08-103">Use external catalogs for PunchOut eProcurement</span></span>
<span data-ttu-id="86e08-104">En utilisant des catalogues externes pour PunchOut eProcurement, il n'est pas nécessaire de tenir à jour les informations sur les produits de vos fournisseurs dans vos propres données principales.</span><span class="sxs-lookup"><span data-stu-id="86e08-104">By using external catalogs for PunchOut e-procurement, you don't have to maintain information about your vendors' products in your own master data.</span></span> <span data-ttu-id="86e08-105">À la place, le chariot sur le site Web d'un fournisseur est converti en lignes de demande contenant les informations correctes sur les produits.</span><span class="sxs-lookup"><span data-stu-id="86e08-105">Instead, the shopping cart on a vendor's website is converted to requisition lines that have the correct product information.</span></span> 

<span data-ttu-id="86e08-106">Vous devez éviter de tenir à jour les descriptions et les prix des produits de vos fournisseurs dans vos propres données principales.</span><span class="sxs-lookup"><span data-stu-id="86e08-106">You should avoid maintaining the descriptions and prices of your vendors’ products in your own product master data.</span></span> <span data-ttu-id="86e08-107">Utilisez plutôt des catalogues externes pour PunchOut eProcurement.</span><span class="sxs-lookup"><span data-stu-id="86e08-107">Instead, use external catalogs for PunchOut e-procurement.</span></span> <span data-ttu-id="86e08-108">Lorsque les employés créent des demandes, ils peuvent « pointer » vers le site du catalogue externe d'un fournisseur (autrement dit, ils quittent votre système et se rendent sur le site du fournisseur).</span><span class="sxs-lookup"><span data-stu-id="86e08-108">Then, when employees create requisitions, they can “punch out” to a vendor’s external catalog site (in other words, they leave your system and go to the vendor’s site).</span></span> <span data-ttu-id="86e08-109">Les produits ajoutés au chariot sur le site Web du fournisseur peuvent ensuite être convertis en lignes de demande.</span><span class="sxs-lookup"><span data-stu-id="86e08-109">The products that are added to the shopping cart on the vendor’s website can then be converted to requisition lines.</span></span> <span data-ttu-id="86e08-110">Ainsi, vous obtenez des informations correctes sur les produits : ID de produit, nom, prix, etc.</span><span class="sxs-lookup"><span data-stu-id="86e08-110">Therefore, you get the correct product information: product ID, name, price, and so on.</span></span>

<span data-ttu-id="86e08-111">Pour utiliser des catalogues externes, un employé doit créer une demande sur la page **Mes demandes d'achat**.</span><span class="sxs-lookup"><span data-stu-id="86e08-111">To use external catalogs, an employee must create a requisition on the **My purchase requisitions** page.</span></span>

<span data-ttu-id="86e08-112">L'employé qui crée une demande est appelé préparateur de la demande.</span><span class="sxs-lookup"><span data-stu-id="86e08-112">The employee who creates a requisition is referred to as the preparer of the requisition.</span></span> <span data-ttu-id="86e08-113">En tant que préparateur, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="86e08-113">As a preparer, you can complete the following tasks.</span></span>

<span data-ttu-id="86e08-114">Utilisez la ligne d'action **Catalogues externes** pour ouvrir une page contenant l'ensemble des catalogues externes disponibles pour le demandeur spécifié, l'entité juridique d'achat et l'unité opérationnelle de réception.</span><span class="sxs-lookup"><span data-stu-id="86e08-114">Use the **External catalogs** line action to open a page that includes all external catalogs that are available for the specified requester, buying legal entity, and receiving operating unit.</span></span>

<span data-ttu-id="86e08-115">Selon vos autorisations, vous pouvez modifier le demandeur, l'entité juridique d'achat et l'unité opérationnelle de réception.</span><span class="sxs-lookup"><span data-stu-id="86e08-115">Depending on your permissions, change the requester, buying legal entity, and receiving operating unit.</span></span> <span data-ttu-id="86e08-116">Une modification de ces valeurs peut changer la liste des catalogues externes accessibles à un demandeur.</span><span class="sxs-lookup"><span data-stu-id="86e08-116">A change in those values might change the list of external catalogs that are available to a requester.</span></span> <span data-ttu-id="86e08-117">Les catalogues externes disponibles dépendent des stratégies d'achat actives actuelles pour l'entité juridique d'achat ou l'unité opérationnelle de réception.</span><span class="sxs-lookup"><span data-stu-id="86e08-117">The external catalogs that are available depend on the current active purchasing policies for the buying legal entity or the receiving operating unit.</span></span> <span data-ttu-id="86e08-118">Ces stratégies peuvent autoriser ou empêcher l'accès à des catégories d'approvisionnement spécifiques.</span><span class="sxs-lookup"><span data-stu-id="86e08-118">These policies can allow or prevent access to specific procurement categories.</span></span> <span data-ttu-id="86e08-119">Par conséquent, la liste des catalogues externes qui sont mis en correspondance avec ces catégories d'approvisionnement peut être affectée.</span><span class="sxs-lookup"><span data-stu-id="86e08-119">Therefore, the list of external catalogs that are mapped to these procurement categories can be affected.</span></span>

<span data-ttu-id="86e08-120">Pour plus d'informations sur les stratégies, voir [Stratégies d'achat](../procurement/purchase-policies.md).</span><span class="sxs-lookup"><span data-stu-id="86e08-120">For more information about policies, see [Purchasing policies](../procurement/purchase-policies.md).</span></span>

- <span data-ttu-id="86e08-121">Pour rechercher des catalogues externes pour des catégories d'approvisionnement spécifiques, entrez du texte dans le champ de recherche de catalogue.</span><span class="sxs-lookup"><span data-stu-id="86e08-121">To find external catalogs for specific procurement categories, enter text in the catalog search field.</span></span>
- <span data-ttu-id="86e08-122">Pour ajouter des produits du catalogue externe d'un fournisseur sur le site Web du fournisseur, cliquez sur le catalogue externe.</span><span class="sxs-lookup"><span data-stu-id="86e08-122">To add products from a vendor’s external catalog on the vendor’s website, click the external catalog.</span></span> <span data-ttu-id="86e08-123">Ajoutez ensuite les produits au chariot, puis procédez à l'extraction. Les lignes du chariot sont transférées vers Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="86e08-123">Then add products to the shopping cart, and check out. The shopping cart lines will be transferred to Microsoft Dynamics 365.</span></span>

<span data-ttu-id="86e08-124">S'il existe plusieurs options pour les catégories d'approvisionnement, sélectionnez la catégorie d'approvisionnement appropriée avant d'ajouter les lignes à la demande.</span><span class="sxs-lookup"><span data-stu-id="86e08-124">If there are multiple options for procurement categories, select the correct procurement category before you add the lines to the requisition.</span></span>
<span data-ttu-id="86e08-125">Une fois que les lignes ont été ajoutées à une demande, vous pouvez ajouter d'autres lignes sans utiliser des catalogues externes.</span><span class="sxs-lookup"><span data-stu-id="86e08-125">After lines have been added to a requisition, you can add more lines without using external catalogs.</span></span> <span data-ttu-id="86e08-126">Vous pouvez également continuer à utiliser des catalogues externes pour ajouter des lignes.</span><span class="sxs-lookup"><span data-stu-id="86e08-126">Alternatively, you can continue to use external catalogs to add lines.</span></span>

<span data-ttu-id="86e08-127">Lorsque la demande est prête, utilisez l'action **Workflow** > **Envoyer** pour l'envoyer pour approbation.</span><span class="sxs-lookup"><span data-stu-id="86e08-127">When the requisition is ready, use the **Workflow** > **Submit** action to submit it for approval.</span></span>

