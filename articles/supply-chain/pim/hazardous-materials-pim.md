---
title: Matières dangereuses
description: Cette rubrique fournit des informations sur les documents relatifs aux matières dangereuses et les informations stockées dans votre environnement.
author: lachlancashMS
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: kamaybac
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: bda81f72d5dea24c7ba678b9a86258a02f7b8cd5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829424"
---
# <a name="hazardous-materials"></a><span data-ttu-id="73417-103">Matières dangereuses</span><span class="sxs-lookup"><span data-stu-id="73417-103">Hazardous materials</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="73417-104">Les informations sur les matières dangereuses sont définies dans Gestion des informations sur les produits.</span><span class="sxs-lookup"><span data-stu-id="73417-104">Information about hazardous materials is set up in Product information management.</span></span> <span data-ttu-id="73417-105">Ce module fournit également des documents qui peuvent être imprimés via la gestion de l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="73417-105">This module also provides documents that can be printed through warehouse management.</span></span>

<span data-ttu-id="73417-106">Lorsque vous expédiez des matières classées comme marchandises dangereuses, des documents supplémentaires doivent être inclus avec les envois.</span><span class="sxs-lookup"><span data-stu-id="73417-106">When you ship materials that are classified as dangerous goods, additional paperwork must be included with the shipments.</span></span> <span data-ttu-id="73417-107">La fonctionnalité des matières dangereuses permet aux clients de stocker les informations de classification et de les relier aux articles de sortie.</span><span class="sxs-lookup"><span data-stu-id="73417-107">The hazardous materials functionality lets customers store classification information and relate it to release items.</span></span> <span data-ttu-id="73417-108">Ces informations peuvent ensuite être utilisées pour préparer la documentation d’expédition.</span><span class="sxs-lookup"><span data-stu-id="73417-108">This information can then be used to help prepare shipping documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73417-109">Les fonctionnalités sur les matières dangereuses dans Microsoft Dynamics 365 Supply Chain Management fournissent une collection de champs d’informations utiles sur le produit et des fonctionnalités associées qui peuvent vous aider à enregistrer et à référencer les informations relatives à vos produits dangereux.</span><span class="sxs-lookup"><span data-stu-id="73417-109">The hazardous materials features in Microsoft Dynamics 365 Supply Chain Management provide a collection of useful product information fields and related functionality that can help you record and reference information that is related to your hazardous products.</span></span> <span data-ttu-id="73417-110">Ces fonctionnalités peuvent également vous aider à concevoir et à imprimer des documents d’expédition qui incluent certaines de ces mêmes informations sur les matières dangereuses que vous expédiez.</span><span class="sxs-lookup"><span data-stu-id="73417-110">These features can also help you design and print shipment documents that include some of the same information about any hazardous materials that you're shipping.</span></span> <span data-ttu-id="73417-111">Cependant, le système ne vous met pas automatiquement en conformité avec toutes les réglementations applicables dans votre pays ou région.</span><span class="sxs-lookup"><span data-stu-id="73417-111">However, the system won't automatically make you compliant with all applicable regulations in your country or region.</span></span> <span data-ttu-id="73417-112">Bien que ces outils soient destinés à vous aider à vous mettre en conformité avec les réglementations en vigueur, ils ne sont ni suffisants en eux-mêmes ni garantis de l’être.</span><span class="sxs-lookup"><span data-stu-id="73417-112">Although these tools are intended to help you comply with common regulations, they are neither sufficient in themselves nor guaranteed to be so.</span></span> <span data-ttu-id="73417-113">Votre organisation a la responsabilité de connaître toutes les réglementations applicables et de prendre toutes les mesures nécessaires pour vous y conformer.</span><span class="sxs-lookup"><span data-stu-id="73417-113">Your organization is responsible for being aware of all applicable regulations and for taking all necessary steps to comply with them.</span></span>

<span data-ttu-id="73417-114">Avant de pouvoir utiliser cette fonctionnalité, la configuration suivante est requise :</span><span class="sxs-lookup"><span data-stu-id="73417-114">Before you can use this functionality, the following setup is required:</span></span>

- <span data-ttu-id="73417-115">**Gestion des informations produits :** configurez des codes qui peuvent être appliqués aux produits lancés.</span><span class="sxs-lookup"><span data-stu-id="73417-115">**Product information management:** Set up codes that can be applied to released products.</span></span>
- <span data-ttu-id="73417-116">**Gestion d’entrepôt :** utilisez des documents d’expédition supplémentaires pour imprimer les informations d’expédition.</span><span class="sxs-lookup"><span data-stu-id="73417-116">**Warehouse management:** Use additional shipping documents to print shipment information.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="73417-117">Gestion des informations sur le produit</span><span class="sxs-lookup"><span data-stu-id="73417-117">Product information management</span></span>

<span data-ttu-id="73417-118">Dans Gestion des informations sur les produits, il existe une série de tableaux de configuration dans lesquels vous pouvez ajouter les informations de référence fournies dans les listes de marchandises dangereuses pour le fret routier, aérien et maritime.</span><span class="sxs-lookup"><span data-stu-id="73417-118">In Product information management, there is a range of setup tables where you can add the reference information that is provided in the dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="73417-119">Voici certaines des réglementations qui sont souvent référencées :</span><span class="sxs-lookup"><span data-stu-id="73417-119">Here are some of the regulations that are often referenced:</span></span>

- <span data-ttu-id="73417-120">**ADR** - Règlements liés au transport international de marchandises dangereuses par route</span><span class="sxs-lookup"><span data-stu-id="73417-120">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="73417-121">**CFR 49** - Réglementation aux États-Unis pour le transport de marchandises dangereuses</span><span class="sxs-lookup"><span data-stu-id="73417-121">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="73417-122">**IMDG** - Le code IMDG (International Marine Dangerous Goods)</span><span class="sxs-lookup"><span data-stu-id="73417-122">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="73417-123">**IATA** - Règlement sur les marchandises dangereuses de l’Association internationale du transport aérien (IATA)</span><span class="sxs-lookup"><span data-stu-id="73417-123">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="73417-124">Chacun de ces règlements a une liste de marchandises dangereuses qui comprend des codes de référence.</span><span class="sxs-lookup"><span data-stu-id="73417-124">Each of these regulations has a dangerous goods list that includes reference codes.</span></span> <span data-ttu-id="73417-125">Les listes pour chaque type de transport sont combinées sur des classifications internationales partagées.</span><span class="sxs-lookup"><span data-stu-id="73417-125">The lists for each type of transport are combined on shared international classifications.</span></span> <span data-ttu-id="73417-126">Supply Chain Management fournit un tableau de référence pour les codes partagés dans ces listes.</span><span class="sxs-lookup"><span data-stu-id="73417-126">Supply Chain Management provides a reference table for the shared codes in those lists.</span></span> <span data-ttu-id="73417-127">Chaque liste possède également des codes uniques qui peuvent être définis.</span><span class="sxs-lookup"><span data-stu-id="73417-127">Each list also has some unique codes that can be defined.</span></span>

<span data-ttu-id="73417-128">Pour commencer à configurer ces informations, créez une réglementation que vous pouvez utiliser pour configurer les paramètres initiaux.</span><span class="sxs-lookup"><span data-stu-id="73417-128">To start to configure this information, create a regulation that you can use to configure the initial parameters.</span></span>

## <a name="warehouse-management"></a><span data-ttu-id="73417-129">Gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="73417-129">Warehouse management</span></span>

<span data-ttu-id="73417-130">Lorsqu’un envoi est préparé, plusieurs nouveaux rapports peuvent être imprimés.</span><span class="sxs-lookup"><span data-stu-id="73417-130">When a shipment is prepared, several new reports can be printed.</span></span> <span data-ttu-id="73417-131">Ces rapports utilisent les informations que vous avez configurées dans la gestion des informations produit.</span><span class="sxs-lookup"><span data-stu-id="73417-131">These reports use the information that you set up in Product information management.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]