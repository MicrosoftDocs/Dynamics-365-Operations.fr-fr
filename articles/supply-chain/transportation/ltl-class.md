---
title: Classes de chargement partiel d'un camion (Less than truckload, LTL)
description: Cette rubrique explique ce que sont les classes de chargement partiel d'un camion (Less than truckload, LTL) et explique comment les configurer dans Microsoft Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 04/05/2021
ms.topic: article
ms.search.form: WHSLTLClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 295006cac0a67cd577809a1b62566de043ea55fb
ms.sourcegitcommit: 636c1bf096a8666a551b67e898da1f48feb9a187
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2021
ms.locfileid: "5941808"
---
# <a name="less-than-truckload-ltl-classes"></a><span data-ttu-id="d9208-103">Classes de chargement partiel d'un camion (Less than truckload, LTL)</span><span class="sxs-lookup"><span data-stu-id="d9208-103">Less than truckload (LTL) classes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d9208-104">Une classe de chargement partiel d'un camion (Less than truckload, LTL) est une classe d'expédition de fret utilisée pour classer les articles pouvant être expédiés.</span><span class="sxs-lookup"><span data-stu-id="d9208-104">A less than truckload (LTL) class is a freight shipping class that is used to classify items that can be shipped.</span></span> <span data-ttu-id="d9208-105">En règle générale, chaque type de produit ou de marchandise a un code NMFC (National Motor Freight Classification) qui correspond à un numéro de classe de fret spécifique pour les envois LTL.</span><span class="sxs-lookup"><span data-stu-id="d9208-105">Generally, every type of product or commodity has a National Motor Freight Classification (NMFC) code that corresponds to a specific freight class number for LTL shipments.</span></span> <span data-ttu-id="d9208-106">Les classes de fret LTL représentent des catégories d'articles, tandis que les codes NMFC sont liés à des produits spécifiques dans chacune des 18 classes de fret.</span><span class="sxs-lookup"><span data-stu-id="d9208-106">LTL freight classes represent categories of items, whereas NMFC codes are related to specific commodities in each of the 18 freight classes.</span></span>

<span data-ttu-id="d9208-107">Cette fonctionnalité vous permet d’utiliser votre système pour effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="d9208-107">This feature lets you use your system to perform the following tasks:</span></span>

- <span data-ttu-id="d9208-108">Définir les classes de fret LTL utilisées dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="d9208-108">Define the LTL freight classes that are used at your company.</span></span>
- <span data-ttu-id="d9208-109">Attribuer chaque classe LTL à un code NMFC sur la page **Codes NMFC**.</span><span class="sxs-lookup"><span data-stu-id="d9208-109">Assign each LTL class to an NMFC code on the **NMFC Codes** page.</span></span> <span data-ttu-id="d9208-110">Pour plus d'informations, consultez les codes [National Motor Freight Classification (NMFC)](nmfc-codes.md).</span><span class="sxs-lookup"><span data-stu-id="d9208-110">For more information, see [National Motor Freight Classification (NMFC) codes](nmfc-codes.md).</span></span>
- <span data-ttu-id="d9208-111">Attribuer un code NMFC (et donc son code LTL associé) à chaque produit sur la page **Produits**.</span><span class="sxs-lookup"><span data-stu-id="d9208-111">Assign an NMFC code (and therefore its associated LTL code) to each product on the **Products** page.</span></span>
- <span data-ttu-id="d9208-112">Évaluer avec précision la classe LTL de chaque produit auquel un code NMFC est attribué.</span><span class="sxs-lookup"><span data-stu-id="d9208-112">Accurately assess the LTL class of each product that an NMFC code is assigned to.</span></span>
- <span data-ttu-id="d9208-113">Déterminer les exigences d'emballage pour chaque classe LTL en vérifiant les normes internationales LTL.</span><span class="sxs-lookup"><span data-stu-id="d9208-113">Determine packing requirements for each LTL class by checking the international LTL standards.</span></span> <span data-ttu-id="d9208-114">De cette façon, vous avez la certitude que vos produits seront bien protégés et expédiés en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="d9208-114">In this way, you ensure that your products will be well protected and safely shipped.</span></span>
- <span data-ttu-id="d9208-115">Obtenir des estimations d'expédition précises, basées sur la classe de fret LTL pour chaque produit.</span><span class="sxs-lookup"><span data-stu-id="d9208-115">Get accurate shipping estimates, based on the LTL freight class for each product.</span></span>

<span data-ttu-id="d9208-116">Cette rubrique explique comment créer des classes LTL dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d9208-116">This topic describes how to create LTL classes in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="create-an-ltl-class"></a><span data-ttu-id="d9208-117">Créer une classe LTL</span><span class="sxs-lookup"><span data-stu-id="d9208-117">Create an LTL class</span></span>

<span data-ttu-id="d9208-118">Pour créer une classe LTL, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d9208-118">To create an LTL class, follow these steps.</span></span>

1. <span data-ttu-id="d9208-119">Utilisez l’une des procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="d9208-119">Follow one of these steps:</span></span>

    - <span data-ttu-id="d9208-120">Accédez à **Gestion des entrepôts \> Paramétrage \> Stock \> Classes LTL**.</span><span class="sxs-lookup"><span data-stu-id="d9208-120">Go to **Warehouse management \> Setup \> Inventory \> LTL classes**.</span></span>
    - <span data-ttu-id="d9208-121">Accédez à **Gestion du transport \> Paramétrage \> Normes de transport \> Classes LTL**.</span><span class="sxs-lookup"><span data-stu-id="d9208-121">Go to **Transportation management \> Setup \> Transportation standards \> LTL classes**.</span></span>

2. <span data-ttu-id="d9208-122">Dans le volet Actions, sélectionnez **Nouveau** pour créer une classe LTL.</span><span class="sxs-lookup"><span data-stu-id="d9208-122">On the Action Pane, select **New** to create an LTL class.</span></span> <span data-ttu-id="d9208-123">Définissez ensuite les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="d9208-123">Then set the following fields:</span></span>

    - <span data-ttu-id="d9208-124">**Classe LTL** - Entrez l'identifiant de classe LTL (ID) interne de votre entreprise pour le type de produit.</span><span class="sxs-lookup"><span data-stu-id="d9208-124">**LTL class** – Enter your company's internal LTL class identifier (ID) for the commodity type.</span></span> <span data-ttu-id="d9208-125">La plupart des entreprises utilisent la norme internationale.</span><span class="sxs-lookup"><span data-stu-id="d9208-125">Most companies use the international standard.</span></span> <span data-ttu-id="d9208-126">Dans ce cas, la valeur de ce champ correspondra à la valeur du champ **Classe**.</span><span class="sxs-lookup"><span data-stu-id="d9208-126">In that case, the value of this field will match the value of the **Class** field.</span></span> <span data-ttu-id="d9208-127">Cependant, si votre entreprise utilise sa propre norme, entrez un code conforme à cette norme.</span><span class="sxs-lookup"><span data-stu-id="d9208-127">However, if your company uses its own standard, enter a code that conforms to that standard.</span></span>
    - <span data-ttu-id="d9208-128">**Nom** - Entrez un nom descriptif qui vous aidera, ainsi que les autres utilisateurs, à sélectionner la classe LTL correcte pour chaque code NMFC.</span><span class="sxs-lookup"><span data-stu-id="d9208-128">**Name** – Enter a descriptive name that will help you and other users select the correct LTL class for each NMFC code.</span></span>
    - <span data-ttu-id="d9208-129">**Classer** - Entrez l'ID de classe LTL standard international pour le type de produit.</span><span class="sxs-lookup"><span data-stu-id="d9208-129">**Class** – Enter the international standard LTL class ID for the commodity type.</span></span> <span data-ttu-id="d9208-130">Le code que vous entrez ici doit être conforme à la norme officielle.</span><span class="sxs-lookup"><span data-stu-id="d9208-130">The code that you enter here must conform to the official standard.</span></span>

## <a name="example-set-up-ltl-classes"></a><span data-ttu-id="d9208-131">Exemple : Configurer des classes LTL</span><span class="sxs-lookup"><span data-stu-id="d9208-131">Example: Set up LTL classes</span></span>

<span data-ttu-id="d9208-132">L'exemple suivant montre comment configurer deux classes LTL différentes que vous pouvez utiliser avec différents types de produits.</span><span class="sxs-lookup"><span data-stu-id="d9208-132">The following example shows how to set up two different LTL classes that you can use with different types of products.</span></span>

1. <span data-ttu-id="d9208-133">Accédez à **Gestion des entrepôts \> Paramétrage \> Stock \> Classes LTL**.</span><span class="sxs-lookup"><span data-stu-id="d9208-133">Go to **Warehouse management \> Setup \> Inventory \> LTL classes**.</span></span>
1. <span data-ttu-id="d9208-134">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d9208-134">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="d9208-135">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="d9208-135">On the new line, set the following values:</span></span>

    - <span data-ttu-id="d9208-136">**Classe LTL :** *92,5*</span><span class="sxs-lookup"><span data-stu-id="d9208-136">**LTL class:** *92.5*</span></span>
    - <span data-ttu-id="d9208-137">**Nom :** *Ordinateurs, moniteurs, réfrigérateurs*</span><span class="sxs-lookup"><span data-stu-id="d9208-137">**Name:** *Computers, monitors, refrigerators*</span></span>
    - <span data-ttu-id="d9208-138">**Classe :** *92,5*</span><span class="sxs-lookup"><span data-stu-id="d9208-138">**Class:** *92.5*</span></span>

1. <span data-ttu-id="d9208-139">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d9208-139">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="d9208-140">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d9208-140">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="d9208-141">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="d9208-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="d9208-142">**Classe LTL :** *125*</span><span class="sxs-lookup"><span data-stu-id="d9208-142">**LTL class:** *125*</span></span>
    - <span data-ttu-id="d9208-143">**Nom :** *Petits appareils électroménagers*</span><span class="sxs-lookup"><span data-stu-id="d9208-143">**Name:** *Small household appliances*</span></span>
    - <span data-ttu-id="d9208-144">**Classe :** *125*</span><span class="sxs-lookup"><span data-stu-id="d9208-144">**Class:** *125*</span></span>

1. <span data-ttu-id="d9208-145">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d9208-145">On the Action Pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d9208-146">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d9208-146">Additional resources</span></span>

- [<span data-ttu-id="d9208-147">Codes National Motor Freight Classification (NMFC)</span><span class="sxs-lookup"><span data-stu-id="d9208-147">National Motor Freight Classification (NMFC) codes</span></span>](nmfc-codes.md)
- [<span data-ttu-id="d9208-148">Créer une feuille de chargement</span><span class="sxs-lookup"><span data-stu-id="d9208-148">Create a bill of lading</span></span>](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
