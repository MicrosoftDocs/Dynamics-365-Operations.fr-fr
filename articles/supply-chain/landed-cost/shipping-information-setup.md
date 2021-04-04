---
title: Paramétrage des informations d’expédition
description: Cette rubrique décrit comment configurer les informations d’expédition pour le module de coût au débarquement.
author: sherry-zheng
manager: tfehr
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMGoodsDescriptionTable, ITMVesselTable, ITMExporterTable, ITMCommodityCodeTable, ITMCustomsDescription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 90794a154eb2a63f33277383cda80323dafd77b0
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500932"
---
# <a name="shipping-information-setup"></a><span data-ttu-id="039d5-103">Paramétrage des informations d’expédition</span><span class="sxs-lookup"><span data-stu-id="039d5-103">Shipping information setup</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="039d5-104">Cette rubrique décrit comment configurer les informations d’expédition pour le module de **coût au débarquement**.</span><span class="sxs-lookup"><span data-stu-id="039d5-104">This topic describes how to set up shipping information for the **Landed cost** module.</span></span>

## <a name="description-of-goods"></a><a name="description-of-goods"></a><span data-ttu-id="039d5-105">Description des marchandises</span><span class="sxs-lookup"><span data-stu-id="039d5-105">Description of goods</span></span>

<span data-ttu-id="039d5-106">Les descriptions de marchandises aident à identifier un voyage, un conteneur d’expédition ou un folio de marchandises et les marchandises qu’il contient.</span><span class="sxs-lookup"><span data-stu-id="039d5-106">Descriptions of goods help identify a voyage, shipping container, or folio of goods, and the goods in it.</span></span> <span data-ttu-id="039d5-107">Sélectionnez une description des marchandises sur l’en-tête du conteneur d’expédition ou l’en-tête du folio.</span><span class="sxs-lookup"><span data-stu-id="039d5-107">You can select a description of goods on the shipping container header or the folio header.</span></span>

<span data-ttu-id="039d5-108">Pour travailler avec des descriptions de marchandises, accédez à **Prix au débarquement \> Configuration des informations d’expédition \> Description des biens**.</span><span class="sxs-lookup"><span data-stu-id="039d5-108">To work with descriptions of goods, go to **Landed cost \> Shipping information setup \> Description of goods**.</span></span> <span data-ttu-id="039d5-109">Là, vous pouvez afficher, ouvrir, créer et supprimer des enregistrements pour les descriptions des marchandises.</span><span class="sxs-lookup"><span data-stu-id="039d5-109">There, you can view, open, create, and delete records for descriptions of goods.</span></span> <span data-ttu-id="039d5-110">Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.</span><span class="sxs-lookup"><span data-stu-id="039d5-110">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="039d5-111">Champ</span><span class="sxs-lookup"><span data-stu-id="039d5-111">Field</span></span> | <span data-ttu-id="039d5-112">Description</span><span class="sxs-lookup"><span data-stu-id="039d5-112">Description</span></span> |
|---|---|
| <span data-ttu-id="039d5-113">Description des marchandises</span><span class="sxs-lookup"><span data-stu-id="039d5-113">Description of goods</span></span> | <span data-ttu-id="039d5-114">Entrez un nom / numéro d’identification unique pour le type de marchandises qui utilisera cette description.</span><span class="sxs-lookup"><span data-stu-id="039d5-114">Enter a unique identification name/number for the type of goods that will use this description.</span></span> |
| <span data-ttu-id="039d5-115">Description</span><span class="sxs-lookup"><span data-stu-id="039d5-115">Description</span></span> | <span data-ttu-id="039d5-116">Saisissez une description du type de marchandises dans cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="039d5-116">Enter a description of the type of goods in this category.</span></span> |

## <a name="vessels"></a><a name="vessels"></a><span data-ttu-id="039d5-117">Bateaux</span><span class="sxs-lookup"><span data-stu-id="039d5-117">Vessels</span></span>

<span data-ttu-id="039d5-118">Un navire est le nom unique d’un navire ou d’un navire utilisé par une compagnie maritime ou une agence.</span><span class="sxs-lookup"><span data-stu-id="039d5-118">A vessel is the unique name of a ship or vessel that a shipping company or agency uses.</span></span> <span data-ttu-id="039d5-119">Lorsque vous créez un voyage, vous devez toujours sélectionner ou saisir un navire pour celui-ci.</span><span class="sxs-lookup"><span data-stu-id="039d5-119">When you create a voyage, you must always either select or enter a vessel for it.</span></span> <span data-ttu-id="039d5-120">Si vous utilisez souvent les mêmes navires, vous pouvez alors rendre plus rapide et plus facile la création d’un voyage en créant un enregistrement de navire pour chacun d’eux, permettant ainsi aux utilisateurs de sélectionner le navire dans une liste plutôt que d’entrer le nom ou le numéro manuellement chaque fois.</span><span class="sxs-lookup"><span data-stu-id="039d5-120">If you often use the same vessels, then you can make it faster and easier to create a new voyage by creating a vessel record for each of them, thereby allowing users to select the vessel from a list rather then enter the name or number manually each time.</span></span>

<span data-ttu-id="039d5-121">Pour travailler avec les navires, accédez à **Coût au débarquement \> Configuration des informations d’expédition \> Navires**.</span><span class="sxs-lookup"><span data-stu-id="039d5-121">To work with vessels, go to **Landed cost \> Shipping information setup \> Vessels**.</span></span> <span data-ttu-id="039d5-122">Là, vous pouvez afficher, ouvrir, créer et supprimer des enregistrements pour les navires.</span><span class="sxs-lookup"><span data-stu-id="039d5-122">There, you can view, open, create, and delete records for vessels.</span></span> <span data-ttu-id="039d5-123">Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.</span><span class="sxs-lookup"><span data-stu-id="039d5-123">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="039d5-124">Champ</span><span class="sxs-lookup"><span data-stu-id="039d5-124">Field</span></span> | <span data-ttu-id="039d5-125">Description</span><span class="sxs-lookup"><span data-stu-id="039d5-125">Description</span></span> |
|---|---|
| <span data-ttu-id="039d5-126">Bateau</span><span class="sxs-lookup"><span data-stu-id="039d5-126">Vessel</span></span> | <span data-ttu-id="039d5-127">Entrez un nom / numéro d’identification unique pour le navire qui sera utilisé pour transporter des marchandises lors d’un voyage.</span><span class="sxs-lookup"><span data-stu-id="039d5-127">Enter a unique identification name/number for the ship that will be used to transport goods on a voyage.</span></span> |
| <span data-ttu-id="039d5-128">Description</span><span class="sxs-lookup"><span data-stu-id="039d5-128">Description</span></span> | <span data-ttu-id="039d5-129">Permet d’entrer une description du navire.</span><span class="sxs-lookup"><span data-stu-id="039d5-129">Enter a description of the vessel.</span></span> <span data-ttu-id="039d5-130">En règle générale, cette description identifie le nom du navire et la compagnie maritime / l’agent.</span><span class="sxs-lookup"><span data-stu-id="039d5-130">Typically, this description identifies the name of the ship and the shipping company/agent.</span></span> |
| <span data-ttu-id="039d5-131">Mode de livraison</span><span class="sxs-lookup"><span data-stu-id="039d5-131">Mode of delivery</span></span> | <span data-ttu-id="039d5-132">Sélectionnez le mode de livraison utilisé par le navire (tel que _Air_, _océan_, ou _Train_).</span><span class="sxs-lookup"><span data-stu-id="039d5-132">Select the mode of delivery that the vessel uses (such as _Air_, _Ocean_, or _Train_).</span></span> |

## <a name="exporters"></a><span data-ttu-id="039d5-133">Exportateurs</span><span class="sxs-lookup"><span data-stu-id="039d5-133">Exporters</span></span>

<span data-ttu-id="039d5-134">Chaque enregistrement d’exportateur identifie un vendeur ou un exportateur qui peut être défini comme le vendeur pour un voyage.</span><span class="sxs-lookup"><span data-stu-id="039d5-134">Each exporter record identifies a vendor or exporter that can be defined as the vendor for a voyage.</span></span> <span data-ttu-id="039d5-135">L’exportateur peut être associé à un voyage et utilisé pour la déclaration.</span><span class="sxs-lookup"><span data-stu-id="039d5-135">The exporter can be associated with a voyage and used for reporting.</span></span>

<span data-ttu-id="039d5-136">Pour travailler avec les exportateurs, accédez à **Coût au débarquement \> Configuration des informations d’expédition \> exportateurs**.</span><span class="sxs-lookup"><span data-stu-id="039d5-136">To work with exporters, go to **Landed cost \> Shipping information setup \> Exporters**.</span></span> <span data-ttu-id="039d5-137">Là, vous pouvez afficher, ouvrir, créer et supprimer des enregistrements pour les exportateurs.</span><span class="sxs-lookup"><span data-stu-id="039d5-137">There, you can view, open, create, and delete records for exporters.</span></span> <span data-ttu-id="039d5-138">Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.</span><span class="sxs-lookup"><span data-stu-id="039d5-138">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="039d5-139">Champ</span><span class="sxs-lookup"><span data-stu-id="039d5-139">Field</span></span> | <span data-ttu-id="039d5-140">Description</span><span class="sxs-lookup"><span data-stu-id="039d5-140">Description</span></span> |
|---|---|
| <span data-ttu-id="039d5-141">Exportateur</span><span class="sxs-lookup"><span data-stu-id="039d5-141">Exporter</span></span> | <span data-ttu-id="039d5-142">Entrez un nom / numéro d’identification unique pour l’exportateur de marchandises qui seront transportées lors d’un voyage.</span><span class="sxs-lookup"><span data-stu-id="039d5-142">Enter a unique identification name/number for the exporter of goods that are transported on a voyage.</span></span> |
| <span data-ttu-id="039d5-143">Description</span><span class="sxs-lookup"><span data-stu-id="039d5-143">Description</span></span> | <span data-ttu-id="039d5-144">Permet d’entrer une description de l’exportateur.</span><span class="sxs-lookup"><span data-stu-id="039d5-144">Enter a description of the exporter.</span></span> <span data-ttu-id="039d5-145">En règle générale, cette description identifie le nom complet de la compagnie maritime / l’agent.</span><span class="sxs-lookup"><span data-stu-id="039d5-145">Typically, this description identifies the full name of the shipping company/agent.</span></span> |

## <a name="commodity-codes"></a><span data-ttu-id="039d5-146">Codes marchandise</span><span class="sxs-lookup"><span data-stu-id="039d5-146">Commodity codes</span></span>

<span data-ttu-id="039d5-147">Vous utilisez les codes marchandises pour faciliter l’identification douanière et le calcul des taux de droits pour les marchandises en voyage.</span><span class="sxs-lookup"><span data-stu-id="039d5-147">You use commodity codes to help with customs identification and the calculation of duty rates for goods on a voyage.</span></span> <span data-ttu-id="039d5-148">Vous pouvez sélectionner des codes marchandises sur la page **Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="039d5-148">You can select commodity codes on the **Released products** page.</span></span>

<span data-ttu-id="039d5-149">Pour travailler avec les codes de marchandise, accédez à **Coût au débarquement \> Configuration des informations d’expédition \> Codes marchandises**.</span><span class="sxs-lookup"><span data-stu-id="039d5-149">To work with commodity codes, go to **Landed cost \> Shipping information setup \> Commodity codes**.</span></span> <span data-ttu-id="039d5-150">Là, vous pouvez afficher, ouvrir, créer et supprimer des enregistrements pour les codes marchandises.</span><span class="sxs-lookup"><span data-stu-id="039d5-150">There, you can view, open, create, and delete records for commodity codes.</span></span> <span data-ttu-id="039d5-151">Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.</span><span class="sxs-lookup"><span data-stu-id="039d5-151">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="039d5-152">Champ</span><span class="sxs-lookup"><span data-stu-id="039d5-152">Field</span></span> | <span data-ttu-id="039d5-153">Description</span><span class="sxs-lookup"><span data-stu-id="039d5-153">Description</span></span> |
|---|---|
| <span data-ttu-id="039d5-154">Code marchandise</span><span class="sxs-lookup"><span data-stu-id="039d5-154">Commodity code</span></span> | <span data-ttu-id="039d5-155">Saisissez un code unique pour ce type de produit.</span><span class="sxs-lookup"><span data-stu-id="039d5-155">Enter a unique code for this type of commodity.</span></span> |
| <span data-ttu-id="039d5-156">Description</span><span class="sxs-lookup"><span data-stu-id="039d5-156">Description</span></span> | <span data-ttu-id="039d5-157">Permet d’entrer la description du type de marchandise.</span><span class="sxs-lookup"><span data-stu-id="039d5-157">Enter a description of the commodity type.</span></span> |

## <a name="customs-description"></a><span data-ttu-id="039d5-158">Description de la douane</span><span class="sxs-lookup"><span data-stu-id="039d5-158">Customs description</span></span>

<span data-ttu-id="039d5-159">Les descriptions douanières aident à identifier les marchandises à des fins douanières.</span><span class="sxs-lookup"><span data-stu-id="039d5-159">Customs descriptions help identify goods for customs purposes.</span></span> <span data-ttu-id="039d5-160">Vous pouvez sélectionner une description douanière sur la page **Produits lancés** ou sur les lignes de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="039d5-160">You can select a customs description on the **Released products** page or on purchase order lines.</span></span>

<span data-ttu-id="039d5-161">Pour travailler avec des descriptions de douanes, accédez à **Prix au débarquement \> Configuration des informations d’expédition \> Description des douanes**.</span><span class="sxs-lookup"><span data-stu-id="039d5-161">To work with customs descriptions, go to **Landed cost \> Shipping information setup \> Customs description**.</span></span> <span data-ttu-id="039d5-162">Là, vous pouvez afficher, ouvrir, créer et supprimer des enregistrements pour les descriptions des douanes.</span><span class="sxs-lookup"><span data-stu-id="039d5-162">There, you can view, open, create, and delete records for custom descriptions.</span></span> <span data-ttu-id="039d5-163">Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.</span><span class="sxs-lookup"><span data-stu-id="039d5-163">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="039d5-164">Champ</span><span class="sxs-lookup"><span data-stu-id="039d5-164">Field</span></span> | <span data-ttu-id="039d5-165">Description</span><span class="sxs-lookup"><span data-stu-id="039d5-165">Description</span></span> |
|---|---|
| <span data-ttu-id="039d5-166">Description de la douane</span><span class="sxs-lookup"><span data-stu-id="039d5-166">Customs description</span></span> | <span data-ttu-id="039d5-167">Saisissez un code unique pour ce type de classification douanière.</span><span class="sxs-lookup"><span data-stu-id="039d5-167">Enter a unique code for this type of customs classification.</span></span> <span data-ttu-id="039d5-168">Souvent, ce code sera la description officielle fournie par une autorité douanière pour la description et la valeur qualitative des marchandises.</span><span class="sxs-lookup"><span data-stu-id="039d5-168">Often, this code will be the official description that is provided by a customs authority for the description and qualitative value of the goods.</span></span> |
| <span data-ttu-id="039d5-169">Description</span><span class="sxs-lookup"><span data-stu-id="039d5-169">Description</span></span> | <span data-ttu-id="039d5-170">Permet d’entrer la description de la classification douanière.</span><span class="sxs-lookup"><span data-stu-id="039d5-170">Enter a description of the customs classification.</span></span> |
