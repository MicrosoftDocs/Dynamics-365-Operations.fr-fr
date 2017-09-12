---
title: Catalogues de centre d'appels
description: "Cet article décrit la fonctionnalité spécifique au centre d'appel des catalogues dans Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 7be87496ceaea2d1d5f97a5cc17e50dcddbaf33d
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---

# <a name="call-center-catalogs"></a><span data-ttu-id="64783-103">Catalogues de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="64783-103">Call center catalogs</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="64783-104">Cet article décrit la fonctionnalité spécifique au centre d'appel des catalogues dans Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="64783-104">This article describes the call center–specific functionality for catalogs in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="64783-105">Dans un centre d'appels, vous pouvez utiliser les catalogues de produits vendus au détail pour identifier les produits que vous souhaitez proposer à vos clients.</span><span class="sxs-lookup"><span data-stu-id="64783-105">In a call center, you can use product catalogs to identify the products that you want to offer to customers.</span></span> <span data-ttu-id="64783-106">Les centres d'appels utilisent généralement des catalogues imprimés.</span><span class="sxs-lookup"><span data-stu-id="64783-106">Call centers typically use printed catalogs.</span></span> <span data-ttu-id="64783-107">La conception et la production d'un catalogue imprimé sont gérées en dehors de Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="64783-107">The design and production of a printed catalog is handled outside Dynamics 365 for Retail.</span></span> <span data-ttu-id="64783-108">Toutefois, vous pouvez créer et stocker un format numérique d'un catalogue à l'aide des mêmes pages que celles que vous utilisez pour paramétrer les catalogues de vente au détail en ligne.</span><span class="sxs-lookup"><span data-stu-id="64783-108">However, you can create and store a digital form of a catalog by using the same pages that you use to set up online retail catalogs.</span></span> <span data-ttu-id="64783-109">Avant de créer un catalogue, vous devez paramétrer des assortiments de produits et affecter les assortiments à un centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="64783-109">Before you can create a catalog, you must set up product assortments and assign the assortments to a call center.</span></span> <span data-ttu-id="64783-110">Vous ajoutez ensuite les produits au catalogue en sélectionnant des produits de ces assortiments.</span><span class="sxs-lookup"><span data-stu-id="64783-110">You then add products to the catalog by selecting products from these assortments.</span></span> <span data-ttu-id="64783-111">Une fois les produits ajoutés au catalogue, et le catalogue terminé, vous devez valider le catalogue pour vérifier les données.</span><span class="sxs-lookup"><span data-stu-id="64783-111">After products have been added to the catalog, and the catalog is complete, you must validate the catalog to verify the data.</span></span> <span data-ttu-id="64783-112">Vous devez ensuite envoyer le catalogue pour révision et approbation.</span><span class="sxs-lookup"><span data-stu-id="64783-112">You must then submit the catalog for review and approval.</span></span> <span data-ttu-id="64783-113">Une fois le catalogue approuvé, il peut être publié.</span><span class="sxs-lookup"><span data-stu-id="64783-113">After the catalog is approved, it can be published.</span></span> <span data-ttu-id="64783-114">Lorsqu'un catalogue de centre d'appel est créé, vous pouvez prendre un instantané des données du catalogue au moment de la publication du catalogue.</span><span class="sxs-lookup"><span data-stu-id="64783-114">When a call center catalog is created, you can take a snapshot of the catalog data at the time that the catalog is published.</span></span> <span data-ttu-id="64783-115">Cette fonctionnalité d'instantané permet d'accéder à une version spécifique du catalogue, même si le catalogue est modifié et mis à jour ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="64783-115">This snapshot functionality lets you access a particular version of the catalog even if the catalog is later changed and updated.</span></span> <span data-ttu-id="64783-116">Les catalogues de centre d'appels peuvent également être paramétrés pour inclure les fonctionnalités optionnelles suivantes :</span><span class="sxs-lookup"><span data-stu-id="64783-116">Call center catalogs can also be set up to include the following optional features:</span></span>

-   <span data-ttu-id="64783-117">**Codes source** - Les codes source permettent de suivre la réponse du client à des envois de catalogues spécifiques.</span><span class="sxs-lookup"><span data-stu-id="64783-117">**Source codes** – Source codes are used to track the customer response to specific catalog mailings.</span></span>
-   <span data-ttu-id="64783-118">**Produits gratuits** – Ces produits peuvent être inclus dans la commande d'un client sans frais supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="64783-118">**Free products** – Products can be included in a customer's order at no additional charge.</span></span> <span data-ttu-id="64783-119">Ces produits sont automatiquement ajoutés à une commande lorsque le code source du catalogue est entré dans la commande.</span><span class="sxs-lookup"><span data-stu-id="64783-119">These products are automatically added to an order when the source code for the catalog is entered into the order.</span></span>
-   <span data-ttu-id="64783-120">**Scripts** – Les scripts sont des textes qu'un collaborateur du centre d'appels lit à un client lorsqu'une commande client est créée.</span><span class="sxs-lookup"><span data-stu-id="64783-120">**Scripts** – Scripts are texts that a call center worker reads to a customer when a sales order is being created.</span></span> <span data-ttu-id="64783-121">Les scripts peuvent inclure des salutations ou des suggestions d'achat.</span><span class="sxs-lookup"><span data-stu-id="64783-121">Scripts can include greetings or purchase suggestions.</span></span>
-   <span data-ttu-id="64783-122">**Mise en page** – Une mise en page capture la position de page des produits dans le catalogue imprimé.</span><span class="sxs-lookup"><span data-stu-id="64783-122">**Page layout** – A page layout captures the page position of products in the printed catalog.</span></span> <span data-ttu-id="64783-123">Ces informations sont utilisées pour l'état d'analyse d'une zone de catalogue.</span><span class="sxs-lookup"><span data-stu-id="64783-123">This information is used for the catalog area analysis report.</span></span>





