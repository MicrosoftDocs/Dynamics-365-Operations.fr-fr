---
title: Utiliser des catalogues externes pour PunchOut eProcurement
description: Cette rubrique explique comment utiliser des catalogues externes pour créer et envoyer des demandes.
author: mkirknel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchVendorPortalRequests, CatExternalCatalogBasketWizard, CatExternalCatalogPunchoutDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cccd3517f31a82e502052f100e44322ac4cb344f
ms.sourcegitcommit: e3f4dd2257a3255c2982f4fc7b72a1121275b88a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4018489"
---
# <a name="use-external-catalogs-for-punchout-e-procurement"></a><span data-ttu-id="180ac-103">Utiliser des catalogues externes pour PunchOut eProcurement</span><span class="sxs-lookup"><span data-stu-id="180ac-103">Use external catalogs for PunchOut e-procurement</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="180ac-104">En utilisant des catalogues externes pour PunchOut eProcurement, il n'est pas nécessaire de tenir à jour les informations sur les produits de vos fournisseurs dans vos propres données principales.</span><span class="sxs-lookup"><span data-stu-id="180ac-104">By using external catalogs for PunchOut e-procurement, you don't have to maintain information about your vendors' products in your own master data.</span></span> <span data-ttu-id="180ac-105">À la place, le chariot sur le site Web d'un fournisseur est converti en lignes de demande contenant les informations correctes sur les produits.</span><span class="sxs-lookup"><span data-stu-id="180ac-105">Instead, the shopping cart on a vendor's website is converted to requisition lines that have the correct product information.</span></span> 

<span data-ttu-id="180ac-106">Vous devez éviter de tenir à jour les descriptions et les prix des produits de vos fournisseurs dans vos propres données principales.</span><span class="sxs-lookup"><span data-stu-id="180ac-106">You should avoid maintaining the descriptions and prices of your vendors’ products in your own product master data.</span></span> <span data-ttu-id="180ac-107">Utilisez plutôt des catalogues externes pour PunchOut eProcurement.</span><span class="sxs-lookup"><span data-stu-id="180ac-107">Instead, use external catalogs for PunchOut e-procurement.</span></span> <span data-ttu-id="180ac-108">Lorsque les employés créent des demandes, ils peuvent « pointer » vers le site du catalogue externe d'un fournisseur (autrement dit, ils quittent votre système et se rendent sur le site du fournisseur).</span><span class="sxs-lookup"><span data-stu-id="180ac-108">Then, when employees create requisitions, they can “punch out” to a vendor’s external catalog site (in other words, they leave your system and go to the vendor’s site).</span></span> <span data-ttu-id="180ac-109">Les produits ajoutés au chariot sur le site Web du fournisseur peuvent ensuite être convertis en lignes de demande.</span><span class="sxs-lookup"><span data-stu-id="180ac-109">The products that are added to the shopping cart on the vendor’s website can then be converted to requisition lines.</span></span> <span data-ttu-id="180ac-110">Ainsi, vous obtenez des informations correctes sur les produits : ID de produit, nom, prix, etc.</span><span class="sxs-lookup"><span data-stu-id="180ac-110">Therefore, you get the correct product information: product ID, name, price, and so on.</span></span>

<span data-ttu-id="180ac-111">Pour utiliser des catalogues externes, un employé doit créer une demande sur la page **Mes demandes d'achat**.</span><span class="sxs-lookup"><span data-stu-id="180ac-111">To use external catalogs, an employee must create a requisition on the **My purchase requisitions** page.</span></span>

<span data-ttu-id="180ac-112">L'employé qui crée une demande est appelé préparateur de la demande.</span><span class="sxs-lookup"><span data-stu-id="180ac-112">The employee who creates a requisition is referred to as the preparer of the requisition.</span></span> <span data-ttu-id="180ac-113">En tant que préparateur, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="180ac-113">As a preparer, you can complete the following tasks.</span></span>

<span data-ttu-id="180ac-114">Utilisez la ligne d'action **Catalogues externes** pour ouvrir une page contenant l'ensemble des catalogues externes disponibles pour le demandeur spécifié, l'entité juridique d'achat et l'unité opérationnelle de réception.</span><span class="sxs-lookup"><span data-stu-id="180ac-114">Use the **External catalogs** line action to open a page that includes all external catalogs that are available for the specified requester, buying legal entity, and receiving operating unit.</span></span>

<span data-ttu-id="180ac-115">Selon vos autorisations, vous pouvez modifier le demandeur, l'entité juridique d'achat et l'unité opérationnelle de réception.</span><span class="sxs-lookup"><span data-stu-id="180ac-115">Depending on your permissions, change the requester, buying legal entity, and receiving operating unit.</span></span> <span data-ttu-id="180ac-116">Une modification de ces valeurs peut changer la liste des catalogues externes accessibles à un demandeur.</span><span class="sxs-lookup"><span data-stu-id="180ac-116">A change in those values might change the list of external catalogs that are available to a requester.</span></span> <span data-ttu-id="180ac-117">Les catalogues externes disponibles dépendent des stratégies d'achat actives actuelles pour l'entité juridique d'achat ou l'unité opérationnelle de réception.</span><span class="sxs-lookup"><span data-stu-id="180ac-117">The external catalogs that are available depend on the current active purchasing policies for the buying legal entity or the receiving operating unit.</span></span> <span data-ttu-id="180ac-118">Ces stratégies peuvent autoriser ou empêcher l'accès à des catégories d'approvisionnement spécifiques.</span><span class="sxs-lookup"><span data-stu-id="180ac-118">These policies can allow or prevent access to specific procurement categories.</span></span> <span data-ttu-id="180ac-119">Par conséquent, la liste des catalogues externes qui sont mis en correspondance avec ces catégories d'approvisionnement peut être affectée.</span><span class="sxs-lookup"><span data-stu-id="180ac-119">Therefore, the list of external catalogs that are mapped to these procurement categories can be affected.</span></span>

<span data-ttu-id="180ac-120">Pour plus d'informations sur les stratégies, voir [Vue d'ensemble des stratégies d'achat](../procurement/purchase-policies.md).</span><span class="sxs-lookup"><span data-stu-id="180ac-120">For more information about policies, see [Purchasing policies overview](../procurement/purchase-policies.md).</span></span>

- <span data-ttu-id="180ac-121">Pour rechercher des catalogues externes pour des catégories d'approvisionnement spécifiques, entrez du texte dans le champ de recherche de catalogue.</span><span class="sxs-lookup"><span data-stu-id="180ac-121">To find external catalogs for specific procurement categories, enter text in the catalog search field.</span></span>
- <span data-ttu-id="180ac-122">Pour ajouter des produits du catalogue externe d'un fournisseur sur le site Web du fournisseur, cliquez sur le catalogue externe.</span><span class="sxs-lookup"><span data-stu-id="180ac-122">To add products from a vendor’s external catalog on the vendor’s website, click the external catalog.</span></span> <span data-ttu-id="180ac-123">Ajoutez ensuite les produits au chariot, puis procédez à l'extraction. Les lignes du chariot sont transférées vers Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="180ac-123">Then add products to the shopping cart, and check out. The shopping cart lines will be transferred to Microsoft Dynamics 365.</span></span>

<span data-ttu-id="180ac-124">S'il existe plusieurs options pour les catégories d'approvisionnement, sélectionnez la catégorie d'approvisionnement appropriée avant d'ajouter les lignes à la demande.</span><span class="sxs-lookup"><span data-stu-id="180ac-124">If there are multiple options for procurement categories, select the correct procurement category before you add the lines to the requisition.</span></span>
<span data-ttu-id="180ac-125">Une fois que les lignes ont été ajoutées à une demande, vous pouvez ajouter d'autres lignes sans utiliser des catalogues externes.</span><span class="sxs-lookup"><span data-stu-id="180ac-125">After lines have been added to a requisition, you can add more lines without using external catalogs.</span></span> <span data-ttu-id="180ac-126">Vous pouvez également continuer à utiliser des catalogues externes pour ajouter des lignes.</span><span class="sxs-lookup"><span data-stu-id="180ac-126">Alternatively, you can continue to use external catalogs to add lines.</span></span>

<span data-ttu-id="180ac-127">Lorsque la demande est prête, utilisez l'action **Workflow** > **Envoyer** pour l'envoyer pour approbation.</span><span class="sxs-lookup"><span data-stu-id="180ac-127">When the requisition is ready, use the **Workflow** > **Submit** action to submit it for approval.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="180ac-128">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="180ac-128">Additional resources</span></span>

- [<span data-ttu-id="180ac-129">Paramétrer un catalogue externe pour PunchOut eProcurement</span><span class="sxs-lookup"><span data-stu-id="180ac-129">Set up an external catalog for PunchOut e-procurement</span></span>](set-up-external-catalog-for-punchout.md)
- [<span data-ttu-id="180ac-130">Améliorations des cXML d’achat</span><span class="sxs-lookup"><span data-stu-id="180ac-130">Purchasing cXML enhancements</span></span>](purchasing-cxml-enhancements.md)