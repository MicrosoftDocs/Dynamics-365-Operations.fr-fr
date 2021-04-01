---
title: Confirmation de prélèvement de pièces
description: Cette rubrique décrit comment vous paramétrez et appliquez la confirmation de prélèvement des pièces d’un périphérique mobile.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 852bd29ae18b4903906aa7fb97a06389cd7cd3bc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232861"
---
# <a name="piece-picking-confirmation"></a><span data-ttu-id="8fe3e-103">Confirmation de prélèvement de pièces</span><span class="sxs-lookup"><span data-stu-id="8fe3e-103">Piece picking confirmation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8fe3e-104">Le prélèvement de pièces vous permet de confirmer chaque pièce du stock via le travail de prélèvement d’inventaire sur un appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-104">Piece picking allows you to confirm each piece of inventory through picking or counting work on a mobile device.</span></span> <span data-ttu-id="8fe3e-105">Pour les prélèvements, vous pouvez confirmer la quantité de travail à traiter jusqu’à la quantité spécifiée dans le travail à prélever.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-105">For picks, you can confirm the quantity of work to be processed up to the quantity that is specified on work to be picked.</span></span> <span data-ttu-id="8fe3e-106">Pour le travail d’inventaire, vous pouvez analyser le stock que vous comptez et suivre la quantité totale.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-106">For counting work, you can scan the inventory that you are counting and track the total amount.</span></span>

<span data-ttu-id="8fe3e-107">Lorsque vous activez le prélèvement de pièce, la confirmation de produit est automatiquement activée.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-107">When you enable piece picking, product confirmation is automatically selected.</span></span> <span data-ttu-id="8fe3e-108">Pour les prélèvements de type travail, un nombre maximal de pièces est activé.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-108">For work-type picks, a maximum number of pieces is enabled.</span></span> <span data-ttu-id="8fe3e-109">Cela vous permet de définir un maximum dans le nombre de pièces qui doivent être confirmées lors du processus de travail.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-109">This allows you to set a maximum to the number of pieces that must be confirmed during the work process.</span></span> <span data-ttu-id="8fe3e-110">La quantité maximale est basée sur l’unité de travail actuelle qui est traitée.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-110">The maximum quantity is based on the current work unit that is being processed.</span></span> <span data-ttu-id="8fe3e-111">Le type de travail d’inventaire n’autorise pas un nombre maximum.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-111">The counting work type does not allow a maximum.</span></span>

<span data-ttu-id="8fe3e-112">Vous pouvez également utiliser la quantité et l’unité de mesure (UOM) associée à un code-barres scanné.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-112">You can also use the quantity and unit of measure (UOM) that is associated with a scanned bar code.</span></span> <span data-ttu-id="8fe3e-113">Cela fonctionnera pour recevoir des flux entrants, y compris la réception du contenant mixte, l’article de commande fournisseur, l’article d’ordre de transfert et l’élément de chargement.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-113">This will work for receiving on inbound flows including mixed license plate receiving, purchase order item, transfer order item, and load item.</span></span> <span data-ttu-id="8fe3e-114">Ces options fonctionnent également pour le prélèvement de pièces où la lecture du code-barres permet d’ajouter la quantité au nombre total de pièces confirmées avec une conversion entre l’UM sur le code-barres et l’unité de travail.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-114">It also works for piece picking where scanning the bar code will add the quantity to the total number of confirmed pieces converting between the UOM on the bar code and the work unit.</span></span> <span data-ttu-id="8fe3e-115">Si, lors du comptage de l’UM sur le code à barres, il est confirmé que la quantité est autorisée pour compter le groupe de séquences, la quantité sera ajoutée au nombre total.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-115">If, when counting the UOM on the bar code, it is confirmed that the quantity is allowed for counting on the sequence group, the quantity will be added to the total count.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="8fe3e-116">Dans ce cas</span><span class="sxs-lookup"><span data-stu-id="8fe3e-116">Where it applies</span></span>

<span data-ttu-id="8fe3e-117">Les travaux de prélèvement des pièces fonctionnent dans le cadre du travail d’inventaire et du prélèvement d’origine pour les types de travail.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-117">Piece picking works for all counting work and for the initial pick for any type of work.</span></span> <span data-ttu-id="8fe3e-118">Le prélèvement de pièce ne s’applique pas si l’article est contrôlé par des numéros de série ou s’il s’agit d’une production ou d’un prélèvement de kanban à partir d’un emplacement de contenant et que l’article est défini à l’échelonnement.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-118">Piece picking does not apply if the item is controlled by serial numbers or if it is a production or kanban pick from a license plate (LP) location and the item is set to staging.</span></span>

## <a name="set-up-piece-picking"></a><span data-ttu-id="8fe3e-119">Définir le prélèvement de pièces</span><span class="sxs-lookup"><span data-stu-id="8fe3e-119">Set up piece picking</span></span>

1.  <span data-ttu-id="8fe3e-120">Dans une option de menu de l’appareil mobile, ouvrez l’écran de paramétrage pour la confirmation du travail : Gestion des entrepôts > **Gestion des entrepôts** > **Paramétrage** > **Appareil mobile** > **Options de menu d’appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-120">On a mobile device menu item, open the setup form for work confirmation: Warehouse management > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span> 
2. <span data-ttu-id="8fe3e-121">Dans l’option de menu de l’appareil mobile, ouvrez Paramétrage de la confirmation du travail.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-121">From the mobile device menu item, open Work confirmation setup.</span></span>

<span data-ttu-id="8fe3e-122">Les options suivantes sont disponibles pour la sélection lorsque le type de travail est prélèvement ou comptage.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-122">The following options become available for selection when the work type is pick or counting.</span></span>


|           <span data-ttu-id="8fe3e-123">Option</span><span class="sxs-lookup"><span data-stu-id="8fe3e-123">Option</span></span>           |                                                                            <span data-ttu-id="8fe3e-124">Description</span><span class="sxs-lookup"><span data-stu-id="8fe3e-124">Description</span></span>                                                                            |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8fe3e-125">Confirmation de prélèvement de pièces</span><span class="sxs-lookup"><span data-stu-id="8fe3e-125">Piece picking confirmation</span></span> | <span data-ttu-id="8fe3e-126">Disponible pour les types de travail de prélèvement et d’inventaire.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-126">Available for pick and counting work types.</span></span> <span data-ttu-id="8fe3e-127">La confirmation de produit est automatiquement activée.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-127">Product confirmation is automatically selected.</span></span> <span data-ttu-id="8fe3e-128">Permet de confirmer chaque pièce du stock de l’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-128">Allows you to confirm each piece of inventory from the mobile device.</span></span> |
|  <span data-ttu-id="8fe3e-129">Nombre maximal de pièces</span><span class="sxs-lookup"><span data-stu-id="8fe3e-129">Maximum number of pieces</span></span>  |                   <span data-ttu-id="8fe3e-130">Disponible pour le travail de prélèvement si la confirmation de prélèvement de pièce est activée.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-130">Available for pick work if piece picking confirmation is enabled.</span></span> <span data-ttu-id="8fe3e-131">Fixe une limite au nombre de pièces que vous devez confirmer.</span><span class="sxs-lookup"><span data-stu-id="8fe3e-131">Sets a limit to the number of pieces that you must confirm.</span></span>                   |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]