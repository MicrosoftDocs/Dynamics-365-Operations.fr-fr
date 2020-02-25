---
title: Matières dangereuses
description: Cette rubrique fournit des informations sur les documents relatifs aux matières dangereuses et les informations stockées dans votre environnement.
author: lachlancashMS
manager: AnnBe
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76dd6539e39bb77c546e613b290fc5decba9457f
ms.sourcegitcommit: 4c60f5dccdf0b94ed110a657ef331546adc5424a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2020
ms.locfileid: "2982306"
---
# <a name="hazardous-materials"></a><span data-ttu-id="0e592-103">Matières dangereuses</span><span class="sxs-lookup"><span data-stu-id="0e592-103">Hazardous materials</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0e592-104">Les informations sur les matières dangereuses sont définies dans Gestion des informations sur les produits.</span><span class="sxs-lookup"><span data-stu-id="0e592-104">Information about hazardous materials is set up in Product information management.</span></span> <span data-ttu-id="0e592-105">Ce module fournit également des documents qui peuvent être imprimés via la gestion de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="0e592-105">This module also provides documents that can be printed through warehouse management.</span></span>

<span data-ttu-id="0e592-106">Lorsque vous expédiez des matières classées comme marchandises dangereuses, des documents supplémentaires doivent être inclus avec les envois.</span><span class="sxs-lookup"><span data-stu-id="0e592-106">When you ship materials that are classified as dangerous goods, additional paperwork must be included with the shipments.</span></span> <span data-ttu-id="0e592-107">La fonctionnalité des matières dangereuses permet aux clients de stocker les informations de classification et de les relier aux articles de sortie.</span><span class="sxs-lookup"><span data-stu-id="0e592-107">The hazardous materials functionality lets customers store classification information and relate it to release items.</span></span> <span data-ttu-id="0e592-108">Ces informations peuvent ensuite être utilisées pour préparer la documentation d'expédition.</span><span class="sxs-lookup"><span data-stu-id="0e592-108">This information can then be used to help prepare shipping documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e592-109">Pour aider à gérer les expéditions de marchandises dangereuses, Microsoft Dynamics 365 Supply Chain Management vous permet de configurer des informations de référence supplémentaires liées aux produits.</span><span class="sxs-lookup"><span data-stu-id="0e592-109">To help manage shipments of dangerous goods, Microsoft Dynamics 365 Supply Chain Management lets you set up additional reference information that is related to products.</span></span> <span data-ttu-id="0e592-110">Vous pouvez également configurer des documents d'expédition supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="0e592-110">You can also set up additional shipment documents.</span></span> <span data-ttu-id="0e592-111">Cependant, le système n'est pas automatiquement conforme aux réglementations de votre pays ou région.</span><span class="sxs-lookup"><span data-stu-id="0e592-111">However, the system isn't automatically compliant with your country's or region's regulations.</span></span> <span data-ttu-id="0e592-112">C'est plutôt un outil qui peut aider votre programme global.</span><span class="sxs-lookup"><span data-stu-id="0e592-112">Instead, it's a tool that can help your overall program.</span></span>

<span data-ttu-id="0e592-113">Avant de pouvoir utiliser cette fonctionnalité, la configuration suivante est requise :</span><span class="sxs-lookup"><span data-stu-id="0e592-113">Before you can use this functionality, the following setup is required:</span></span>

- <span data-ttu-id="0e592-114">**Gestion des informations produits :** configurez des codes qui peuvent être appliqués aux produits lancés.</span><span class="sxs-lookup"><span data-stu-id="0e592-114">**Product information management:** Set up codes that can be applied to released products.</span></span>
- <span data-ttu-id="0e592-115">**Gestion d'entrepôt :** utilisez des documents d'expédition supplémentaires pour imprimer les informations d'expédition.</span><span class="sxs-lookup"><span data-stu-id="0e592-115">**Warehouse management:** Use additional shipping documents to print shipment information.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="0e592-116">Gestion des informations sur le produit</span><span class="sxs-lookup"><span data-stu-id="0e592-116">Product information management</span></span>

<span data-ttu-id="0e592-117">Dans Gestion des informations sur les produits, il existe une série de tableaux de configuration dans lesquels vous pouvez ajouter les informations de référence fournies dans les listes de marchandises dangereuses pour le fret routier, aérien et maritime.</span><span class="sxs-lookup"><span data-stu-id="0e592-117">In Product information management, there is a range of setup tables where you can add the reference information that is provided in the dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="0e592-118">Voici certaines des réglementations qui sont souvent référencées :</span><span class="sxs-lookup"><span data-stu-id="0e592-118">Here are some of the regulations that are often referenced:</span></span>

- <span data-ttu-id="0e592-119">**ADR** - Règlements liés au transport international de marchandises dangereuses par route</span><span class="sxs-lookup"><span data-stu-id="0e592-119">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="0e592-120">**CFR 49** - Réglementation aux États-Unis pour le transport de marchandises dangereuses</span><span class="sxs-lookup"><span data-stu-id="0e592-120">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="0e592-121">**IMDG** - Le code IMDG (International Marine Dangerous Goods)</span><span class="sxs-lookup"><span data-stu-id="0e592-121">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="0e592-122">**IATA** - Règlement sur les marchandises dangereuses de l'Association internationale du transport aérien (IATA)</span><span class="sxs-lookup"><span data-stu-id="0e592-122">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="0e592-123">Chacun de ces règlements a une liste de marchandises dangereuses qui comprend des codes de référence.</span><span class="sxs-lookup"><span data-stu-id="0e592-123">Each of these regulations has a dangerous goods list that includes reference codes.</span></span> <span data-ttu-id="0e592-124">Les listes pour chaque type de transport sont combinées sur des classifications internationales partagées.</span><span class="sxs-lookup"><span data-stu-id="0e592-124">The lists for each type of transport are combined on shared international classifications.</span></span> <span data-ttu-id="0e592-125">Supply Chain Management fournit un tableau de référence pour les codes partagés dans ces listes.</span><span class="sxs-lookup"><span data-stu-id="0e592-125">Supply Chain Management provides a reference table for the shared codes in those lists.</span></span> <span data-ttu-id="0e592-126">Chaque liste possède également des codes uniques qui peuvent être définis.</span><span class="sxs-lookup"><span data-stu-id="0e592-126">Each list also has some unique codes that can be defined.</span></span>

<span data-ttu-id="0e592-127">Pour commencer à configurer ces informations, créez une réglementation que vous pouvez utiliser pour configurer les paramètres initiaux.</span><span class="sxs-lookup"><span data-stu-id="0e592-127">To start to configure this information, create a regulation that you can use to configure the initial parameters.</span></span>

## <a name="warehouse-management"></a><span data-ttu-id="0e592-128">Gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="0e592-128">Warehouse management</span></span>

<span data-ttu-id="0e592-129">Lorsqu'un envoi est préparé, plusieurs nouveaux rapports peuvent être imprimés.</span><span class="sxs-lookup"><span data-stu-id="0e592-129">When a shipment is prepared, several new reports can be printed.</span></span> <span data-ttu-id="0e592-130">Ces rapports utilisent les informations que vous avez configurées dans la gestion des informations produit.</span><span class="sxs-lookup"><span data-stu-id="0e592-130">These reports use the information that you set up in Product information management.</span></span>
