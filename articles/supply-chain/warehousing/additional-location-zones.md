---
title: Zones d'emplacement supplémentaires
description: Cette rubrique fournit une vue d'ensemble des nouvelles zones d'emplacement qui ont été ajoutées à Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: AnnBe
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 9727187ad555f9e3d09beed3f3447a22c29ed22a
ms.sourcegitcommit: a7a7303004620d2e9cef0642b16d89163911dbb4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2020
ms.locfileid: "3530165"
---
# <a name="additional-location-zones"></a><span data-ttu-id="f1067-103">Zones d'emplacement supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f1067-103">Additional location zones</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f1067-104">Trois nouveaux champs de zone sont disponibles dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f1067-104">Three new zone fields are available in Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="f1067-105">Les responsables d'entrepôt peuvent les utiliser pour définir des organisations ou des dispositions d'entrepôt supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="f1067-105">Warehouse managers can use them to define additional warehouse organizations or layouts.</span></span> <span data-ttu-id="f1067-106">Les nouveaux champs de zone peuvent être définis manuellement ou en utilisant l'Assistant **Paramétrage d'emplacement**.</span><span class="sxs-lookup"><span data-stu-id="f1067-106">The new zone fields can be set either manually or by using the **Location setup** wizard.</span></span> <span data-ttu-id="f1067-107">Ils peuvent être utilisés dans toute requête ou tout filtrage qui utilise la table Emplacements.</span><span class="sxs-lookup"><span data-stu-id="f1067-107">They can be used in any query or filtering that uses the Locations table.</span></span>

<span data-ttu-id="f1067-108">Aucune configuration supplémentaire n'est requise pour utiliser les champs de zone.</span><span class="sxs-lookup"><span data-stu-id="f1067-108">No additional setup is required to use the zone fields.</span></span>

## <a name="turn-on-the-additional-location-zone-feature"></a><span data-ttu-id="f1067-109">Activer la fonctionnalité Zone d'emplacement supplémentaire</span><span class="sxs-lookup"><span data-stu-id="f1067-109">Turn on the Additional location zone feature</span></span>

<span data-ttu-id="f1067-110">Avant de pouvoir utiliser la fonctionnalité *Zone d'emplacement supplémentaire*, celle-ci doit être activée dans votre système.</span><span class="sxs-lookup"><span data-stu-id="f1067-110">Before you can use the *Additional location zone* feature, it must be turned on in your system.</span></span> <span data-ttu-id="f1067-111">Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f1067-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="f1067-112">Dans l'espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="f1067-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="f1067-113">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="f1067-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="f1067-114">**Nom de la fonctionnalité :** *Zone d'emplacement supplémentaire*</span><span class="sxs-lookup"><span data-stu-id="f1067-114">**Feature name:** *Additional location zone*</span></span>

## <a name="use-location-zones"></a><span data-ttu-id="f1067-115">Utiliser les zones d'emplacement</span><span class="sxs-lookup"><span data-stu-id="f1067-115">Use location zones</span></span>

1. <span data-ttu-id="f1067-116">Allez dans **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Assistant Paramétrage d'emplacement**.</span><span class="sxs-lookup"><span data-stu-id="f1067-116">Go to **Warehouse management \> Setup \> Warehouse \> Location setup wizard**.</span></span>
2. <span data-ttu-id="f1067-117">Définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="f1067-117">Set the following values:</span></span>

    - <span data-ttu-id="f1067-118">Dans le champ **Entrepôt**, sélectionnez _62_.</span><span class="sxs-lookup"><span data-stu-id="f1067-118">In the **Warehouse** field, select _62_.</span></span>
    - <span data-ttu-id="f1067-119">Dans le champ **ID zone**, sélectionnez _FLOOR_.</span><span class="sxs-lookup"><span data-stu-id="f1067-119">In the **Zone ID** field, select _FLOOR_.</span></span>
    - <span data-ttu-id="f1067-120">Dans le champ **Zone supplémentaire 1**, sélectionnez _PICKZONE1_.</span><span class="sxs-lookup"><span data-stu-id="f1067-120">In the **Additional Zone 1** field, select _PICKZONE1_.</span></span>
    - <span data-ttu-id="f1067-121">Dans le champ **Zone supplémentaire 2**, sélectionnez _WEBSHOP1_.</span><span class="sxs-lookup"><span data-stu-id="f1067-121">In the **Additional Zone 2** field, select _WEBSHOP1_.</span></span>
    - <span data-ttu-id="f1067-122">Dans le champ **ID profil d'emplacement**, sélectionnez _FLOOR_.</span><span class="sxs-lookup"><span data-stu-id="f1067-122">In the **Location profile ID** field, select _FLOOR_.</span></span>

3. <span data-ttu-id="f1067-123">Sélectionnez la ligne **Sol**.</span><span class="sxs-lookup"><span data-stu-id="f1067-123">Select the **Floor** line.</span></span>
4. <span data-ttu-id="f1067-124">Dans le champ **Numéro de départ**, entrez _1_.</span><span class="sxs-lookup"><span data-stu-id="f1067-124">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="f1067-125">Dans le champ **Numéro d'arrivée**, entrez _3_.</span><span class="sxs-lookup"><span data-stu-id="f1067-125">In the **To number** field, enter _3_.</span></span>
5. <span data-ttu-id="f1067-126">Sélectionnez la ligne **Allée**.</span><span class="sxs-lookup"><span data-stu-id="f1067-126">Select the **Aisle** line.</span></span>
6. <span data-ttu-id="f1067-127">Dans le champ **Numéro de départ**, entrez _1_.</span><span class="sxs-lookup"><span data-stu-id="f1067-127">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="f1067-128">Dans le champ **Numéro d'arrivée**, entrez _5_.</span><span class="sxs-lookup"><span data-stu-id="f1067-128">In the **To number** field, enter _5_.</span></span>
7. <span data-ttu-id="f1067-129">Sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="f1067-129">Select **Create**.</span></span>
8. <span data-ttu-id="f1067-130">Vous recevez des messages indiquant que de nouveaux emplacements ont été ajoutés.</span><span class="sxs-lookup"><span data-stu-id="f1067-130">You receive messages that state that new locations have been added.</span></span> <span data-ttu-id="f1067-131">Sélectionnez le bouton **Afficher les messages** pour afficher les messages.</span><span class="sxs-lookup"><span data-stu-id="f1067-131">Select the **Show messages** button to view the messages.</span></span>
9. <span data-ttu-id="f1067-132">Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Emplacements**.</span><span class="sxs-lookup"><span data-stu-id="f1067-132">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span> <span data-ttu-id="f1067-133">Les nouveaux emplacements s'affichent dans la liste et tous les champs de zone sont disponibles (c'est-à-dire le champ de zone existant et les nouveaux champs de zone supplémentaires).</span><span class="sxs-lookup"><span data-stu-id="f1067-133">The new locations appear in the list, and all zone fields are available (that is, the existing zone field and the new additional zone fields).</span></span>
