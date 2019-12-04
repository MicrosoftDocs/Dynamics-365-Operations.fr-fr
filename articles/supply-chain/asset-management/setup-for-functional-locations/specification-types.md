---
title: Types d'attribut de maintenance
description: Cette rubrique explique comment créer des types d'attribut dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 625e2c6a6b385c69d33ec4325a462310a37f1eed
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812189"
---
# <a name="maintenance-attribute-types"></a><span data-ttu-id="6c6a9-103">Types d'attribut de maintenance</span><span class="sxs-lookup"><span data-stu-id="6c6a9-103">Maintenance attribute types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="6c6a9-104">Cette rubrique explique comment créer des types d'attribut dans le module Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-104">This topic explains how to create attribute types in Asset Management.</span></span> <span data-ttu-id="6c6a9-105">Les attributs permettent de décrire les propriétés de différents éléments.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-105">Attributes are used to describe the properties of various elements.</span></span> <span data-ttu-id="6c6a9-106">Vous pouvez paramétrer des attributs sur les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6c6a9-106">You can set up attributes on the following elements:</span></span>

- [<span data-ttu-id="6c6a9-107">Types d'emplacement fonctionnels</span><span class="sxs-lookup"><span data-stu-id="6c6a9-107">Functional location types</span></span>](../setup-for-functional-locations/functional-location-types.md)
- [<span data-ttu-id="6c6a9-108">Créer des emplacement fonctionnels</span><span class="sxs-lookup"><span data-stu-id="6c6a9-108">Create functional locations</span></span>](../functional-locations/create-functional-locations.md)
- [<span data-ttu-id="6c6a9-109">Types d'actif</span><span class="sxs-lookup"><span data-stu-id="6c6a9-109">Asset types</span></span>](../setup-for-objects/object-types.md)
- <span data-ttu-id="6c6a9-110">Actifs</span><span class="sxs-lookup"><span data-stu-id="6c6a9-110">Assets</span></span>

<span data-ttu-id="6c6a9-111">Les attributs que vous pouvez paramétrer varient selon l'élément.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-111">The attributes that you can set up vary, depending on the element.</span></span> <span data-ttu-id="6c6a9-112">Par exemple, pour un poste technique, vous pouvez paramétrer des attributs pour la configuration et la taille physique de l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-112">For example, for a functional location, you can set up attributes for the configuration and physical size of the location.</span></span> <span data-ttu-id="6c6a9-113">Pour un type d'actif ou un actif, vous pouvez paramétrer des attributs pour le volume du moteur, la consommation électrique et la capacité de charge maximale sous différentes conditions.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-113">For an asset type or an asset, you can set up attributes for engine volume, power consumption, and maximum load capacity under different conditions.</span></span>

## <a name="create-attribute-types"></a><span data-ttu-id="6c6a9-114">Création de types d'attributs</span><span class="sxs-lookup"><span data-stu-id="6c6a9-114">Create attribute types</span></span>

<span data-ttu-id="6c6a9-115">Vous pouvez créer vos propres types d'attribut.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-115">You can create your own attribute types.</span></span> <span data-ttu-id="6c6a9-116">En outre, vous pouvez transférer des dimensions de produit vers la page **Types d'attributs**.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-116">Additionally, you can transfer product dimensions to the **Attribute types** page.</span></span>

1. <span data-ttu-id="6c6a9-117">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Types d'attributs**.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-117">Select **Asset management** \> **Setup** \> **Attribute types**.</span></span>
2. <span data-ttu-id="6c6a9-118">La première fois que vous paramétrez des types d'attribut, sélectionnez **Créer des dimensions de produit** pour transférer automatiquement des dimensions de produit standard.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-118">The first time that you set up attribute types, select **Create product dimensions** to automatically transfer standard product dimensions.</span></span>
3. <span data-ttu-id="6c6a9-119">Sélectionnez **Nouveau** pour créer un type d'attribut.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-119">Select **New** to create a new attribute type.</span></span>
4. <span data-ttu-id="6c6a9-120">Dans le champ **Type d'attribut**, entrez un nom pour le type d'attribut.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-120">In the **Attribute type** field, enter a name for the attribute type.</span></span>
5. <span data-ttu-id="6c6a9-121">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-121">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="6c6a9-122">Dans le champ **Unité**, sélectionnez l'unité appropriée de l'attribut, au besoin.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-122">In the **Unit** field, select the relevant attribute unit, as required.</span></span>
7. <span data-ttu-id="6c6a9-123">Dans le champ **Type de données**, sélectionnez un type de données pour l'unité.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-123">In the **Data type** field, select a data type for the unit.</span></span>
8. <span data-ttu-id="6c6a9-124">Si vous avez sélectionné **Chaîne** comme type de données, procédez comme suit pour créer des valeurs pour le type d'attribut :</span><span class="sxs-lookup"><span data-stu-id="6c6a9-124">If you selected **String** as the data type, follow these steps to create values for the attribute type:</span></span>

    1. <span data-ttu-id="6c6a9-125">Sélectionnez le type d'attribut, puis sélectionnez **Valeurs**.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-125">Select the attribute type, and then select **Values**.</span></span>
    2. <span data-ttu-id="6c6a9-126">Dans le champ **Valeurs d'attribut**, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-126">In the **Attribute values** field, select **New**.</span></span>
    3. <span data-ttu-id="6c6a9-127">Dans le champ **Type d'attribut**, sélectionnez un type d'attribut (dimension).</span><span class="sxs-lookup"><span data-stu-id="6c6a9-127">In the **Attribute type** field, select an attribute type (dimension).</span></span>
    4. <span data-ttu-id="6c6a9-128">Dans le champ **Valeur**, entrez une valeur associée.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-128">In the **Value** field, enter a related value.</span></span>
    5. <span data-ttu-id="6c6a9-129">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-129">In the **Description** field, enter a description.</span></span>
    6. <span data-ttu-id="6c6a9-130">Enregistrez l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-130">Save the record.</span></span>
    7. <span data-ttu-id="6c6a9-131">Revenez à la page **Types d'attributs**.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-131">Return to the **Attribute types** page.</span></span>

9. <span data-ttu-id="6c6a9-132">Enregistrez l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-132">Save the record.</span></span>

    <span data-ttu-id="6c6a9-133">Le champ **Types de poste technique** affiche le nombre de postes techniques qui utilisent le type d'attribut.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-133">The **Functional location types** field shows the number of functional locations that are using the attribute type.</span></span> <span data-ttu-id="6c6a9-134">Le champ **Types d'actif** affiche le nombre de types d'actif qui l'utilisent.</span><span class="sxs-lookup"><span data-stu-id="6c6a9-134">The **Asset types** field shows the number of asset types that are using it.</span></span>
