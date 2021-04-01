---
title: Vue d’ensemble des objets de service
description: Les objets de service sont des actifs et des produits d’un client pour lesquels vous pouvez effectuer un service.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dae74ebb59d73e1197426757ec9c050b1905852e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211788"
---
# <a name="service-objects-overview"></a><span data-ttu-id="91395-103">Vue d’ensemble des objets de service</span><span class="sxs-lookup"><span data-stu-id="91395-103">Service objects overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="91395-104">Les objets de service sont des actifs et des produits d’un client pour lesquels vous pouvez effectuer un service.</span><span class="sxs-lookup"><span data-stu-id="91395-104">Service objects are a customer’s assets and products for which you can perform a service.</span></span> <span data-ttu-id="91395-105">Selon le type de service fourni, les objets peuvent être tangibles ou intangibles :</span><span class="sxs-lookup"><span data-stu-id="91395-105">Depending on the type of service you provide, objects can be tangible or intangible:</span></span>

-  <span data-ttu-id="91395-106">Les objets tangibles sont des éléments, tels qu’une machine ou un immeuble, sur lesquels vous réalisez une tâche de service physique.</span><span class="sxs-lookup"><span data-stu-id="91395-106">Tangible objects are things, such as a machine or a building, on which you can perform a physical service task.</span></span>

    <span data-ttu-id="91395-107">Un objet de service tangible peut également être un article en stock que vous créez dans l’écran Détails des produits lancés.</span><span class="sxs-lookup"><span data-stu-id="91395-107">A tangible service object can also be an inventory item that you create in the Released product details form.</span></span> <span data-ttu-id="91395-108">Selon le groupe de dimensions de stock que vous associez à l’article, vous pouvez créer un objet de service à un niveau de détail comprenant le numéro de série de l’article.</span><span class="sxs-lookup"><span data-stu-id="91395-108">Depending on the inventory dimension group that you attach to the item, you can create a service object to a level of detail that includes the item serial number.</span></span> <span data-ttu-id="91395-109">C’est utile lorsque vous devez conserver la trace de l’article exact que l’objet de service représente.</span><span class="sxs-lookup"><span data-stu-id="91395-109">This is useful when you must keep track of the exact item that the service object represents.</span></span>

    <span data-ttu-id="91395-110">Un objet de service tangible peut également être un élément qui n’est pas directement associé à la production directe ou à la chaîne d’approvisionnement de la société.</span><span class="sxs-lookup"><span data-stu-id="91395-110">A tangible service object can also be an item that is not directly related to a company's direct production or supply chain.</span></span> <span data-ttu-id="91395-111">Par exemple, une trousse à outils utilisée pour des réparations dans le cadre d’une commande de service peut être un objet de service qui n’est pas inclus dans le stock.</span><span class="sxs-lookup"><span data-stu-id="91395-111">For example, a tool kit that is used for repairs in a service order can be a service object that is not included in inventory.</span></span> <span data-ttu-id="91395-112">Dans ce cas, vous ne l’enregistrez pas comme un article en stock.</span><span class="sxs-lookup"><span data-stu-id="91395-112">In this case, you don’t register it as an inventory item.</span></span>

-  <span data-ttu-id="91395-113">Les objets intangibles sont des entités non physiques, telles qu’une série de comptes ou un document juridique, sur lesquelles une tâche de service est réalisée.</span><span class="sxs-lookup"><span data-stu-id="91395-113">Intangible objects are nonphysical things, such as a set of accounts or a legal document, on which you can perform a service task.</span></span>

## <a name="example-of-an-intangible-service-object"></a><span data-ttu-id="91395-114">Exemple d’objet de service intangible</span><span class="sxs-lookup"><span data-stu-id="91395-114">Example of an intangible service object</span></span>

<span data-ttu-id="91395-115">La société A gère les états financiers de plusieurs petites entreprises.</span><span class="sxs-lookup"><span data-stu-id="91395-115">Company A maintains the financial records for several small companies.</span></span> <span data-ttu-id="91395-116">L’un des clients de la société A est l’équipe de football locale, pour laquelle la société A gère la comptabilité hebdomadaire et réalise un audit annuel des comptes du club.</span><span class="sxs-lookup"><span data-stu-id="91395-116">One of Company A's clients is the local football team, for which Company A does the weekly bookkeeping and annual audit of the club's accounts.</span></span> <span data-ttu-id="91395-117">Les comptes du club sont paramétrés dans l’écran Objets du service et spécifiés comme objet dans l’accord de service.</span><span class="sxs-lookup"><span data-stu-id="91395-117">The club's accounts are set up in the Service objects form and specified as the object in the service agreement.</span></span> <span data-ttu-id="91395-118">Il existe deux lignes d’accord de service pour l’objet.</span><span class="sxs-lookup"><span data-stu-id="91395-118">There are two service agreement lines for the object.</span></span> <span data-ttu-id="91395-119">La ligne 1 correspond à une comptabilité hebdomadaire et un intervalle hebdomadaire est affecté à la ligne, la ligne 2 correspond à l’audit annuel et un intervalle annuel est affecté à celle-ci.</span><span class="sxs-lookup"><span data-stu-id="91395-119">Line 1 is weekly bookkeeping with a weekly interval assigned to the line, and line 2 is the annual audit with a yearly interval assigned to it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="91395-120">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="91395-120">Related topics</span></span>

[<span data-ttu-id="91395-121">Créer des objets de service</span><span class="sxs-lookup"><span data-stu-id="91395-121">Create service objects</span></span>](create-service-objects.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]