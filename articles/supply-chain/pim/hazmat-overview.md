---
title: Vue d’ensemble des matières dangereuses
description: Cette rubrique fournit une vue d’ensemble des fonctionnalités liées à la manipulation et à la documentation sur les matières dangereuses lors de la gestion des informations sur les produits et de la gestion des entrepôts.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 34c0a19308bb5159faa9a4ab06bf65e58da0deb1
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2020
ms.locfileid: "3802747"
---
# <a name="hazardous-materials-overview"></a><span data-ttu-id="344aa-103">Vue d’ensemble des matières dangereuses</span><span class="sxs-lookup"><span data-stu-id="344aa-103">Hazardous materials overview</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="344aa-104">Pour rester conformes aux réglementations sur l’expédition et le transport, les organisations qui expédient des matières classées comme marchandises dangereuses doivent inclure des documents supplémentaires dans leurs expéditions.</span><span class="sxs-lookup"><span data-stu-id="344aa-104">To remain compliant with shipping and transport regulations, organizations that ship materials that are classified as dangerous goods must include additional paperwork with their shipments.</span></span> <span data-ttu-id="344aa-105">La fonction relatives aux matières dangereuses permet aux clients de stocker des informations sur les articles lancés.</span><span class="sxs-lookup"><span data-stu-id="344aa-105">The hazardous materials feature lets customers store information that is related to released items.</span></span> <span data-ttu-id="344aa-106">Ces informations peuvent ensuite être utilisées pour préparer la documentation d’expédition.</span><span class="sxs-lookup"><span data-stu-id="344aa-106">This information can then be used to help prepare shipping documentation.</span></span> <span data-ttu-id="344aa-107">Une organisation qui expédie des marchandises dangereuses doit avoir ses propres processus et procédures pour gérer le processus d’expédition.</span><span class="sxs-lookup"><span data-stu-id="344aa-107">An organization that ships dangerous goods must have its own processes and procedures for managing the shipping process.</span></span> <span data-ttu-id="344aa-108">Microsoft Dynamics 365 Supply Chain Management est simplement un outil qui peut aider à générer les documents requis.</span><span class="sxs-lookup"><span data-stu-id="344aa-108">Microsoft Dynamics 365 Supply Chain Management is just a tool that can help generate the required documents.</span></span>

<span data-ttu-id="344aa-109">Le diagramme suivant illustre les étapes nécessaires pour configurer et utiliser la fonction sur les matières dangereuses.</span><span class="sxs-lookup"><span data-stu-id="344aa-109">The following diagram illustrates the steps needed to set up and use the hazardous materials feature.</span></span>

<span data-ttu-id="344aa-110">![Configuration et utilisation de la fonction sur les matières dangereuses](media/hazmat-overview.png "Configuration et utilisation de la fonction sur les matières dangereuses")</span><span class="sxs-lookup"><span data-stu-id="344aa-110">![Setup and use of the hazardous materials feature](media/hazmat-overview.png "Setup and use of the hazardous materials feature")</span></span>

<span data-ttu-id="344aa-111">La fonctionnalité sur les matières dangereuses est configurée dans la gestion des informations sur les produits et fournit des documents qui peuvent être imprimés via la gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="344aa-111">The hazardous materials feature is set up in Product information management and provides documents that can be printed through Warehouse management.</span></span> <span data-ttu-id="344aa-112">Par conséquent, de manière générale, ces domaines sont les deux principaux domaines dans lesquels vous allez examiner, configurer et utiliser les fonctionnalités de cette fonctionnalité :</span><span class="sxs-lookup"><span data-stu-id="344aa-112">Therefore, broadly speaking, those areas are the two main areas where you will review, set up, and use this feature's functionality:</span></span>

- <span data-ttu-id="344aa-113">**Gestion des informations produits** – configurez les codes qui peuvent être appliqués à un produit lancé.</span><span class="sxs-lookup"><span data-stu-id="344aa-113">**Product information management** – Set up the codes that will be applied to a released product.</span></span>
- <span data-ttu-id="344aa-114">**Gestion des entrepôts** – Utilisez des documents d’expédition supplémentaires qui seront imprimés pour les expéditions.</span><span class="sxs-lookup"><span data-stu-id="344aa-114">**Warehouse management** – Work with additional shipping documents that will be printed for shipments.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="344aa-115">Les fonctionnalités sur les matières dangereuses dans Supply Chain Management fournissent une collection de champs d’informations utiles sur le produit et des fonctionnalités associées qui peuvent vous aider à enregistrer et à référencer les informations relatives à vos produits dangereux.</span><span class="sxs-lookup"><span data-stu-id="344aa-115">The hazardous materials features in Supply Chain Management provide a collection of useful product information fields and related functionality that can help you record and reference information that is related to your hazardous products.</span></span> <span data-ttu-id="344aa-116">Ces fonctionnalités peuvent également vous aider à concevoir et à imprimer des documents d’expédition qui incluent certaines de ces mêmes informations sur les matières dangereuses que vous expédiez.</span><span class="sxs-lookup"><span data-stu-id="344aa-116">These features can also help you design and print shipment documents that include some of the same information about any hazardous materials that you're shipping.</span></span> <span data-ttu-id="344aa-117">Cependant, le système ne vous met pas automatiquement en conformité avec toutes les réglementations applicables dans votre pays ou région.</span><span class="sxs-lookup"><span data-stu-id="344aa-117">However, the system won't automatically make you compliant with all applicable regulations in your country or region.</span></span> <span data-ttu-id="344aa-118">Bien que ces outils soient destinés à vous aider à vous mettre en conformité avec les réglementations en vigueur, ils ne sont ni suffisants en eux-mêmes ni garantis de l’être.</span><span class="sxs-lookup"><span data-stu-id="344aa-118">Although these tools are intended to help you comply with common regulations, they are neither sufficient in themselves nor guaranteed to be so.</span></span> <span data-ttu-id="344aa-119">Votre organisation a la responsabilité de connaître toutes les réglementations applicables et de prendre toutes les mesures nécessaires pour vous y conformer.</span><span class="sxs-lookup"><span data-stu-id="344aa-119">Your organization is responsible for being aware of all applicable regulations and for taking all necessary steps to comply with them.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="344aa-120">Gestion des informations sur les produits</span><span class="sxs-lookup"><span data-stu-id="344aa-120">Product information management</span></span>

<span data-ttu-id="344aa-121">La Gestion des informations sur les produits fournit une série de tableaux de configuration dans lesquels vous pouvez saisir des informations de référence concernant les différentes listes de marchandises dangereuses pour le fret routier, aérien et maritime.</span><span class="sxs-lookup"><span data-stu-id="344aa-121">Product information management provides a range of setup tables where you can enter reference information for the various dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="344aa-122">Les réglementations communes suivantes ont été référencées lors du développement de cette fonctionnalité :</span><span class="sxs-lookup"><span data-stu-id="344aa-122">The following common regulations were referenced when this functionality was developed:</span></span>

- <span data-ttu-id="344aa-123">**ADR** - Règlements liés au transport international de marchandises dangereuses par route</span><span class="sxs-lookup"><span data-stu-id="344aa-123">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="344aa-124">**CFR 49** - Réglementation aux États-Unis pour le transport de marchandises dangereuses</span><span class="sxs-lookup"><span data-stu-id="344aa-124">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="344aa-125">**IMDG** - Le code IMDG (International Marine Dangerous Goods)</span><span class="sxs-lookup"><span data-stu-id="344aa-125">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="344aa-126">**IATA** - Règlement sur les marchandises dangereuses de l’Association internationale du transport aérien (IATA)</span><span class="sxs-lookup"><span data-stu-id="344aa-126">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="344aa-127">Chaque ensemble de réglementations fournit des listes normalisées de marchandises dangereuses et des codes de référence.</span><span class="sxs-lookup"><span data-stu-id="344aa-127">Each set of regulations provides standardized lists of dangerous goods and reference codes.</span></span> <span data-ttu-id="344aa-128">Par conséquent, Supply Chain Management fournit un tableau de référence pour les codes communs sur ces listes.</span><span class="sxs-lookup"><span data-stu-id="344aa-128">Therefore, Supply Chain Management provides a reference table for the common codes on those lists.</span></span> <span data-ttu-id="344aa-129">Chaque liste possède également des codes uniques que vous pouvez définir.</span><span class="sxs-lookup"><span data-stu-id="344aa-129">Each list also has some unique codes that you can define.</span></span>

<span data-ttu-id="344aa-130">Pour plus d’informations sur la configuration des réglementations et des valeurs pour les matières dangereuses et sur l’attribution des valeurs aux produits concernés, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="344aa-130">For more information about how to set up regulations and values for hazardous materials, and how to assign the values to relevant products, see the following topics:</span></span>

- [<span data-ttu-id="344aa-131">Paramétrer des matières dangereuses</span><span class="sxs-lookup"><span data-stu-id="344aa-131">Set up hazardous materials</span></span>](hazmat-setup.md)
- [<span data-ttu-id="344aa-132">Matières dangereuses dans les produits, les commandes, les expéditions et les chargements</span><span class="sxs-lookup"><span data-stu-id="344aa-132">Hazardous materials in products, orders, shipments, and loads</span></span>](hazmat-items.md)

## <a name="warehouse-management"></a><span data-ttu-id="344aa-133">Gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="344aa-133">Warehouse management</span></span>

<span data-ttu-id="344aa-134">Lorsque vous préparez une expédition dans la Gestion des entrepôts, vous pourrez imprimer plusieurs nouveaux états qui utilisent les informations que vous avez configurées dans la Gestion des informations sur les produits.</span><span class="sxs-lookup"><span data-stu-id="344aa-134">When you prepare a shipment in Warehouse management, you will be able to print several new reports that use the information that you set up in Product information management.</span></span> <span data-ttu-id="344aa-135">Pour plus d’informations sur les états disponibles et comment les utiliser, consultez [Demandes de renseignements et déclarations sur les matières dangereuses](hazmat-reports.md).</span><span class="sxs-lookup"><span data-stu-id="344aa-135">For more information about the available reports and how to use them, see [Hazardous materials inquiries and reports](hazmat-reports.md).</span></span>
