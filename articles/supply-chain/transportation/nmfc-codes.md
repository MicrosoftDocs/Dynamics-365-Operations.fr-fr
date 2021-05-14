---
title: Codes National Motor Freight Classification (NMFC)
description: Cette rubrique décrit comment utiliser les codes NMFC (National Motor Freight Classification) dans Microsoft Dynamics 365 Supply Chain Management
author: Henrikan
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 0307437d3868f7ac34fa16a0913907a046ac14d4
ms.sourcegitcommit: 636c1bf096a8666a551b67e898da1f48feb9a187
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2021
ms.locfileid: "5941880"
---
# <a name="national-motor-freight-classification-nmfc-codes"></a><span data-ttu-id="9bc77-103">Codes National Motor Freight Classification (NMFC)</span><span class="sxs-lookup"><span data-stu-id="9bc77-103">National Motor Freight Classification (NMFC) codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9bc77-104">Les codes NMFC (National Motor Freight Classification) vous aident à classer les articles qui peuvent être expédiés.</span><span class="sxs-lookup"><span data-stu-id="9bc77-104">National Motor Freight Classification (NMFC) codes help you classify items that can be shipped.</span></span> <span data-ttu-id="9bc77-105">Le code NMFC est une désignation utilisée pour regrouper les produits.</span><span class="sxs-lookup"><span data-stu-id="9bc77-105">The NMFC code is a designation that is used to group commodities.</span></span> <span data-ttu-id="9bc77-106">Il permet aux entreprises de transport d'évaluer les marchandises à expédier en classant les articles en fonction de considérations telles que la capacité du camion, les problèmes de chargement, les problèmes de manutention et la périssabilité.</span><span class="sxs-lookup"><span data-stu-id="9bc77-106">It enables transport companies to evaluate goods for shipment by classifying items based on considerations such as truck fit, loading issues, handling issues, and perishability.</span></span> <span data-ttu-id="9bc77-107">Les produits sont regroupés dans l'une des 18 classes de fret en utilisant une plage de nombres de 50 à 500.</span><span class="sxs-lookup"><span data-stu-id="9bc77-107">Commodities are grouped into one of 18 freight classes by using a range of numbers from 50 to 500.</span></span> <span data-ttu-id="9bc77-108">La classe dans laquelle une marchandise est regroupée est basée sur une évaluation de quatre caractéristiques de transport : densité, capacité de rangement, manutention et responsabilité.</span><span class="sxs-lookup"><span data-stu-id="9bc77-108">The class that a commodity is grouped into is based on an evaluation of four transportation characteristics: density, stowability, handling, and liability.</span></span> <span data-ttu-id="9bc77-109">Ces caractéristiques désignent ensemble la transportabilité de la marchandise.</span><span class="sxs-lookup"><span data-stu-id="9bc77-109">Together, these characteristics establish the commodity's transportability.</span></span>

<span data-ttu-id="9bc77-110">Un code NMFC est associé à chaque article d'expédition à chargement partiel (LTL).</span><span class="sxs-lookup"><span data-stu-id="9bc77-110">An NMFC code is associated with every less than truckload (LTL) shipping item.</span></span> <span data-ttu-id="9bc77-111">Par exemple, un ordinateur portable peut se voir attribuer un NMFC classé à 2,5, tandis que des fils électriques peuvent se voir attribuer un NMFC classé à 65.</span><span class="sxs-lookup"><span data-stu-id="9bc77-111">For example, a laptop might be assigned an NMFC that is classed at 2.5, whereas electrical cords might be assigned an NMFC that is classed at 65.</span></span>

<span data-ttu-id="9bc77-112">Cette fonctionnalité peut aider les collaborateurs à utiliser les codes NMFC pour classer les articles d'expédition LTL.</span><span class="sxs-lookup"><span data-stu-id="9bc77-112">This feature can help workers use NMFC codes to classify LTL shipping items.</span></span> <span data-ttu-id="9bc77-113">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="9bc77-113">Here are some examples:</span></span>

- <span data-ttu-id="9bc77-114">Si votre entreprise inclut une description du fret sur la feuille de chargement (BOL), le transporteur aura une idée de sa composition.</span><span class="sxs-lookup"><span data-stu-id="9bc77-114">If your company includes a freight description on the bill of lading (BOL), the carrier will have some idea what the freight is.</span></span> <span data-ttu-id="9bc77-115">Le fret est une classification importante, car de nombreuses entreprises de transport fondent leur modèle commercial global sur les types de fret qu'elles expédient.</span><span class="sxs-lookup"><span data-stu-id="9bc77-115">Freight is an important classification because many transportation companies base their whole business model on the types of freight that they ship.</span></span>
- <span data-ttu-id="9bc77-116">Cette classification peut être essentielle pour votre entreprise car elle sert à déterminer le coût d'une charge donnée.</span><span class="sxs-lookup"><span data-stu-id="9bc77-116">This classification might be essential to your company because it's used to determine the cost of a given load.</span></span>
- <span data-ttu-id="9bc77-117">Votre entreprise peut identifier la rentabilité d'une entreprise de logistique et de transport LTL.</span><span class="sxs-lookup"><span data-stu-id="9bc77-117">Your company can identify the profitability of an LTL logistics and transportation company.</span></span>

<span data-ttu-id="9bc77-118">Cette rubrique décrit comment utiliser des codes NMFC dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9bc77-118">This topic describes how to work with NMFC codes in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9bc77-119">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="9bc77-119">Prerequisites</span></span>

<span data-ttu-id="9bc77-120">Avant de pouvoir créer des codes NMFC, vous devez configurer toutes les classes de fret LTL qui doivent y être mappées.</span><span class="sxs-lookup"><span data-stu-id="9bc77-120">Before you can create NMFC codes, you must set up all the LTL freight classes that must be mapped to them.</span></span> <span data-ttu-id="9bc77-121">Les classes de fret LTL représentent des catégories d'articles, tandis que les codes NMFC sont liés à des produits spécifiques dans chacune des 18 classes de fret.</span><span class="sxs-lookup"><span data-stu-id="9bc77-121">LTL freight classes represent categories of items, whereas NMFC codes are related to specific commodities in each of the 18 freight classes.</span></span> <span data-ttu-id="9bc77-122">Pour plus d'informations sur l'utilisation des classes LTL, consultez [Classes de chargement partiel d'un camion (Less than truckload, LTL)](ltl-class.md).</span><span class="sxs-lookup"><span data-stu-id="9bc77-122">For more information about how to work with LTL classes, see [Less than truckload (LTL) classes](ltl-class.md).</span></span>

## <a name="create-an-nmfc-code"></a><span data-ttu-id="9bc77-123">Créer un code NMFC</span><span class="sxs-lookup"><span data-stu-id="9bc77-123">Create an NMFC code</span></span>

<span data-ttu-id="9bc77-124">Pour créer un code NMFC, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="9bc77-124">To create an NMFC code, follow these steps.</span></span>

1. <span data-ttu-id="9bc77-125">Utilisez l’une des procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="9bc77-125">Follow one of these steps:</span></span>

    - <span data-ttu-id="9bc77-126">Accédez à **Gestion des entrepôts \> Paramétrage \> Stock \> Codes NMFC**.</span><span class="sxs-lookup"><span data-stu-id="9bc77-126">Go to **Warehouse management \> Setup \> Inventory \> NMFC codes**.</span></span>
    - <span data-ttu-id="9bc77-127">Accédez à **Gestion du transport \> Paramétrage \> Normes de transport \> Codes NMFC**.</span><span class="sxs-lookup"><span data-stu-id="9bc77-127">Go to **Transportation management \> Setup \> Transportation standards \> NMFC codes**.</span></span>

1. <span data-ttu-id="9bc77-128">Sélectionnez **Nouveau** pour créer un code NMFC.</span><span class="sxs-lookup"><span data-stu-id="9bc77-128">Select **New** to create an NMFC code.</span></span> <span data-ttu-id="9bc77-129">Définissez ensuite les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="9bc77-129">Then set the following fields:</span></span>

    - <span data-ttu-id="9bc77-130">**Code NMFC** – Entrez le code NMFC du type de marchandise.</span><span class="sxs-lookup"><span data-stu-id="9bc77-130">**NMFC code** – Enter the NMFC code for the commodity type.</span></span>
    - <span data-ttu-id="9bc77-131">**Nom** – Entrez un nom pour le code NMFC.</span><span class="sxs-lookup"><span data-stu-id="9bc77-131">**Name** – Enter a name for the NMFC code.</span></span>
    - <span data-ttu-id="9bc77-132">**Classe LTL** - Sélectionnez la classe LTL associée au code NMFC.</span><span class="sxs-lookup"><span data-stu-id="9bc77-132">**LTL class** – Select the LTL class that is associated with the NMFC code.</span></span>
    - <span data-ttu-id="9bc77-133">**Unité de manutention BOL** - Définissez le type de manutention par défaut pour l'expédition.</span><span class="sxs-lookup"><span data-stu-id="9bc77-133">**BOL handling unit** – Define the default handling type for the shipment.</span></span>

## <a name="example-set-up-nmfc-codes"></a><span data-ttu-id="9bc77-134">Exemple : Paramétrer les codes NMFC</span><span class="sxs-lookup"><span data-stu-id="9bc77-134">Example: Set up NMFC codes</span></span>

<span data-ttu-id="9bc77-135">L'exemple suivant montre comment configurer deux codes NMFC différents que vous pouvez utiliser avec différents types de produits.</span><span class="sxs-lookup"><span data-stu-id="9bc77-135">The following example shows how to set up two different NMFC codes that can be used with different products.</span></span>

1. <span data-ttu-id="9bc77-136">Accédez à **Gestion des entrepôts \> Paramétrage \> Stock \> Codes NMFC**.</span><span class="sxs-lookup"><span data-stu-id="9bc77-136">Go to **Warehouse management \> Setup \> Inventory \> NMFC codes**.</span></span>
1. <span data-ttu-id="9bc77-137">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9bc77-137">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9bc77-138">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="9bc77-138">On the new line, set the following values:</span></span>

    - <span data-ttu-id="9bc77-139">**Code NMFC :** *92,5*</span><span class="sxs-lookup"><span data-stu-id="9bc77-139">**NMFC code:** *92.5*</span></span>
    - <span data-ttu-id="9bc77-140">**Nom :** *Ordinateurs*</span><span class="sxs-lookup"><span data-stu-id="9bc77-140">**Name:** *Computers*</span></span>
    - <span data-ttu-id="9bc77-141">**Classe LTL :** *92,5*</span><span class="sxs-lookup"><span data-stu-id="9bc77-141">**LTL class:** *92.5*</span></span>
    - <span data-ttu-id="9bc77-142">**Unité de manutention BOL :** *Unité*</span><span class="sxs-lookup"><span data-stu-id="9bc77-142">**BOL handling unit:** *Unit*</span></span>

1. <span data-ttu-id="9bc77-143">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9bc77-143">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="9bc77-144">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9bc77-144">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9bc77-145">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="9bc77-145">On the new line, set the following values:</span></span>

    - <span data-ttu-id="9bc77-146">**Code NMFC :** *125*</span><span class="sxs-lookup"><span data-stu-id="9bc77-146">**NMFC code:** *125*</span></span>
    - <span data-ttu-id="9bc77-147">**Nom :** *Téléphones*</span><span class="sxs-lookup"><span data-stu-id="9bc77-147">**Name:** *Phones*</span></span>
    - <span data-ttu-id="9bc77-148">**Classe LTL :** *125*</span><span class="sxs-lookup"><span data-stu-id="9bc77-148">**LTL class:** *125*</span></span>
    - <span data-ttu-id="9bc77-149">**Unité de manutention BOL :** *Unité*</span><span class="sxs-lookup"><span data-stu-id="9bc77-149">**BOL handling unit:** *Unit*</span></span>

1. <span data-ttu-id="9bc77-150">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9bc77-150">On the Action Pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9bc77-151">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="9bc77-151">Additional resources</span></span>

- [<span data-ttu-id="9bc77-152">Classes de chargement partiel d'un camion (Less than truckload, LTL)</span><span class="sxs-lookup"><span data-stu-id="9bc77-152">Less than truckload (LTL) classes</span></span>](ltl-class.md)
- [<span data-ttu-id="9bc77-153">Créer une feuille de chargement</span><span class="sxs-lookup"><span data-stu-id="9bc77-153">Create a bill of landing</span></span>](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
