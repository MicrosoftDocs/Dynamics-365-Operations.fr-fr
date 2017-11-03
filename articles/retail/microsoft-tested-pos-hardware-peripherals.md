---
title: "Périphériques matériels de PDV"
description: "Retail Modern point of sale (PDV) et PDV Cloud peuvent utiliser un large éventail des périphériques matériels de PDV, avec des interfaces et des options de déploiement multiples pour exécuter différents scénarios métier d'un détaillant."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 215234
ms.assetid: 1893d4b3-e1b7-4b66-be58-0102addd5b36
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4fbfb176f2504be8aaf67992d094da1daeefeb76
ms.contentlocale: fr-fr
ms.lasthandoff: 11/03/2017

---

# <a name="pos-hardware-peripherals"></a><span data-ttu-id="e6031-103">Périphériques matériels de PDV</span><span class="sxs-lookup"><span data-stu-id="e6031-103">POS hardware peripherals</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="e6031-104">Retail Modern point of sale (PDV) et PDV Cloud peuvent utiliser un large éventail des périphériques matériels de PDV, avec des interfaces et des options de déploiement multiples pour exécuter différents scénarios métier d'un détaillant.</span><span class="sxs-lookup"><span data-stu-id="e6031-104">Retail Modern point of sale (POS) and Cloud POS can utilize a wide range of POS hardware peripherals, with multiple interfaces and deployment options to achieve a retailer’s various business scenarios.</span></span> 

<span data-ttu-id="e6031-105">Pour prendre en charge la sélection la plus étendue de périphériques entres fabricants et modèles, PDV utilise des interfaces standard telles qu'OLE for Retail POS (OPOS), des pilotes de périphériques Windows et des API (interface de programmation d'applications) Windows de point de service.</span><span class="sxs-lookup"><span data-stu-id="e6031-105">To support the widest selection of devices across manufactures and models, POS utilizes standard interfaces such as OLE for Retail POS (OPOS), Windows device drivers, and Windows point of service application program interfaces (APIs).</span></span> <span data-ttu-id="e6031-106">En général, PDV fonctionnera sur ces périphériques à condition que le pilote approprié soit fourni.</span><span class="sxs-lookup"><span data-stu-id="e6031-106">Generally, POS will work on these devices provided that the appropriate driver is supplied.</span></span> <span data-ttu-id="e6031-107">Toutefois, parce que l'implémentation de ces normes par les fabricants et développeurs de logiciels peut varier, il existe souvent des différences entre les capacités ou comportements pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e6031-107">However, because each manufacturer and software developer’s implementation of these standards can vary, there are often differences in supported capabilities or behaviors.</span></span>

<span data-ttu-id="e6031-108">La liste suivante récapitule les modèles de périphériques, dans chaque classe, qui ont été testés en interne par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e6031-108">The following list includes device models, in each class, that have been tested internally by Microsoft.</span></span>

<span data-ttu-id="e6031-109">**périphériques OPOS**</span><span class="sxs-lookup"><span data-stu-id="e6031-109">**OPOS devices**</span></span>

-   <span data-ttu-id="e6031-110">Code-barres – Motorola DS9208</span><span class="sxs-lookup"><span data-stu-id="e6031-110">Barcode – Motorola DS9208</span></span>
-   <span data-ttu-id="e6031-111">MSR – HP IDRA-334133, Magtek PN - 21073062</span><span class="sxs-lookup"><span data-stu-id="e6031-111">MSR – HP IDRA-334133, Magtek PN - 21073062</span></span>
-   <span data-ttu-id="e6031-112">LineDisplay – Epson M58DC</span><span class="sxs-lookup"><span data-stu-id="e6031-112">LineDisplay – Epson M58DC</span></span>
-   <span data-ttu-id="e6031-113">Pinpad – Verifone 1000SE</span><span class="sxs-lookup"><span data-stu-id="e6031-113">Pinpad – Verifone 1000SE</span></span>
-   <span data-ttu-id="e6031-114">Bloc de signature – Scriptel ST1550</span><span class="sxs-lookup"><span data-stu-id="e6031-114">Signature pad – Scriptel ST1550</span></span>
-   <span data-ttu-id="e6031-115">Imprimante – EPSON TM-T88IV, TMT88V</span><span class="sxs-lookup"><span data-stu-id="e6031-115">Printer – EPSON TM-T88IV, TMT88V</span></span>
-   <span data-ttu-id="e6031-116">Tiroir-caisse – Star SMD2-1317BK44</span><span class="sxs-lookup"><span data-stu-id="e6031-116">Cash drawer – Star SMD2-1317BK44</span></span>
-   <span data-ttu-id="e6031-117">Balance – Datalogic Magellan 8400</span><span class="sxs-lookup"><span data-stu-id="e6031-117">Scale – Datalogic Magellan 8400</span></span>

<span data-ttu-id="e6031-118">**Wedge de clavier LBM**</span><span class="sxs-lookup"><span data-stu-id="e6031-118">**Keyboard wedge MSR**</span></span>

-   <span data-ttu-id="e6031-119">USB Magtek</span><span class="sxs-lookup"><span data-stu-id="e6031-119">Magtek USB</span></span>

<span data-ttu-id="e6031-120">**Terminal de paiement**</span><span class="sxs-lookup"><span data-stu-id="e6031-120">**Payment terminal**</span></span>

-   <span data-ttu-id="e6031-121">Equinox L3500</span><span class="sxs-lookup"><span data-stu-id="e6031-121">Equinox L3500</span></span>
-   <span data-ttu-id="e6031-122">Verifone MX925</span><span class="sxs-lookup"><span data-stu-id="e6031-122">Verifone MX925</span></span>

<span data-ttu-id="e6031-123">**Périphériques réseau**</span><span class="sxs-lookup"><span data-stu-id="e6031-123">**Network devices**</span></span>

-   <span data-ttu-id="e6031-124">Imprimante – Star TSP650II</span><span class="sxs-lookup"><span data-stu-id="e6031-124">Printer – Star TSP650II</span></span>
-   <span data-ttu-id="e6031-125">Tiroir-caisse – APG Atwood</span><span class="sxs-lookup"><span data-stu-id="e6031-125">Cash drawer – APG Atwood</span></span>
-   <span data-ttu-id="e6031-126">Terminal de paiement – MX915, MX925</span><span class="sxs-lookup"><span data-stu-id="e6031-126">Payment terminal – MX915, MX925</span></span>

<span data-ttu-id="e6031-127">**Coûts de production indirects directs MPOS uniquement**</span><span class="sxs-lookup"><span data-stu-id="e6031-127">**MPOS direct IPC only**</span></span>

-   <span data-ttu-id="e6031-128">Code-barres – Honeywell 1900, HP LS2208</span><span class="sxs-lookup"><span data-stu-id="e6031-128">Barcode – Honeywell 1900, HP LS2208</span></span>
-   <span data-ttu-id="e6031-129">LBM – Magtek PN - 21073075</span><span class="sxs-lookup"><span data-stu-id="e6031-129">MSR – Magtek PN - 21073075</span></span>





