---
title: Profils de classement
description: Cette rubrique décrit le paramétrage des données de profils de classement.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d359394ee0086edc5c8b9a3a0c48cf5933963ceb
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828440"
---
# <a name="rating-profiles"></a><span data-ttu-id="55ea5-103">Profils de classement</span><span class="sxs-lookup"><span data-stu-id="55ea5-103">Rating profiles</span></span>

<span data-ttu-id="55ea5-104">Un profil de classement ressemble à un contrat logistique (mais pas à un contrat légal).</span><span class="sxs-lookup"><span data-stu-id="55ea5-104">A rating profile resembles a logistics contract (but not a legal contract).</span></span> <span data-ttu-id="55ea5-105">Il sert à déterminer les tarifs de transport des charges.</span><span class="sxs-lookup"><span data-stu-id="55ea5-105">It's used to determine transportation tariffs for loads.</span></span> 

<span data-ttu-id="55ea5-106">Chaque profil de classement est propre à un transporteur.</span><span class="sxs-lookup"><span data-stu-id="55ea5-106">Each rating profile is unique to a shipping carrier.</span></span> <span data-ttu-id="55ea5-107">Dans le profil, vous associer le transporteur à une table maître des taux.</span><span class="sxs-lookup"><span data-stu-id="55ea5-107">In the profile, you associate the shipping carrier with a rate master.</span></span> <span data-ttu-id="55ea5-108">La table maître des taux définit l’affectation de base de taux et la base de taux.</span><span class="sxs-lookup"><span data-stu-id="55ea5-108">The rate master defines the rate base assignment and the rate base.</span></span> <span data-ttu-id="55ea5-109">La base de taux détermine le taux du transporteur.</span><span class="sxs-lookup"><span data-stu-id="55ea5-109">The rate base determines the rate of the carrier.</span></span>

<span data-ttu-id="55ea5-110">Vous pouvez paramétrer un profil de classement à l’aide d’une page générique qui affiche une vue d’ensemble de tous les profils de classement existants.</span><span class="sxs-lookup"><span data-stu-id="55ea5-110">You can set up a rating profile by using a generic page that shows an overview of all existing rating profiles.</span></span> <span data-ttu-id="55ea5-111">Sinon, vous pouvez paramétrer le profil de classement directement à partir du transporteur.</span><span class="sxs-lookup"><span data-stu-id="55ea5-111">Alternatively, you can set up a rating profile directly from the shipping carrier.</span></span> <span data-ttu-id="55ea5-112">Dans les deux cas, les informations que vous définissez pour le profil de classement sont les mêmes.</span><span class="sxs-lookup"><span data-stu-id="55ea5-112">In both cases, the information that you set up for the rating profile is the same.</span></span>

## <a name="create-or-edit-a-rating-profile-on-the-rating-profiles-page"></a><span data-ttu-id="55ea5-113">Créer ou modifier un profil de classement sur la page Profils de classement</span><span class="sxs-lookup"><span data-stu-id="55ea5-113">Create or edit a rating profile on the Rating profiles page</span></span>

<span data-ttu-id="55ea5-114">Sur la page **Profils de classement**, vous pouvez consulter tous les profils de classement disponibles.</span><span class="sxs-lookup"><span data-stu-id="55ea5-114">On the **Rating profiles** page, you can review all available rating profiles.</span></span> <span data-ttu-id="55ea5-115">Vous pouvez également modifier les profils existants et créer des profils.</span><span class="sxs-lookup"><span data-stu-id="55ea5-115">You can also edit existing profiles and create new profiles.</span></span>

1. <span data-ttu-id="55ea5-116">Accédez à **Gestion du transport \> Configurer \> Taux \> Données principales de taux**.</span><span class="sxs-lookup"><span data-stu-id="55ea5-116">Go to **Transportation management \> Setup \> Rating \> Rating profile**.</span></span>
1. <span data-ttu-id="55ea5-117">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter un nouveau profil de classement à la grille, ou sélectionnez **Modifier** pour modifier un profil existant.</span><span class="sxs-lookup"><span data-stu-id="55ea5-117">On the Action Pane, select **New** to add a new rating profile to the grid, or select **Edit** to edit an existing profile.</span></span>
1. <span data-ttu-id="55ea5-118">Dans la ligne du profil de notation nouveau ou existant, définissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="55ea5-118">In the row for the new or existing rating profile, set the following fields:</span></span>

    - <span data-ttu-id="55ea5-119">**Profils de classement** – Entrez un identificateur (ID) unique pour le profil de classement.</span><span class="sxs-lookup"><span data-stu-id="55ea5-119">**Rating profile** – Enter a unique identifier (ID) for the rating profile.</span></span>
    - <span data-ttu-id="55ea5-120">**Nom** – Entrez un nom descriptif pour le profil de classement.</span><span class="sxs-lookup"><span data-stu-id="55ea5-120">**Name** – Enter a descriptive name for the rating profile.</span></span>
    - <span data-ttu-id="55ea5-121">**Transporteur** – Sélectionnez un transporteur.</span><span class="sxs-lookup"><span data-stu-id="55ea5-121">**Shipping carrier** – Select a shipping carrier.</span></span> <span data-ttu-id="55ea5-122">Le profil de classement que vous configurez sera également affiché sur la page **Transporteurs** pour le transporteur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="55ea5-122">The rating profile that you're setting up will also be shown on the **Shipping carriers** page for the selected carrier.</span></span>
    - <span data-ttu-id="55ea5-123">**Site** et **Entrepôt** – Sélectionnez un site et un entrepôt.</span><span class="sxs-lookup"><span data-stu-id="55ea5-123">**Site** and **Warehouse** – Select a site and warehouse.</span></span>
    - <span data-ttu-id="55ea5-124">**Moteur de taux** – Sélectionnez le moteur de taux pour le profil de classement.</span><span class="sxs-lookup"><span data-stu-id="55ea5-124">**Rate engine** – Select the rate engine for the rating profile.</span></span>
    - <span data-ttu-id="55ea5-125">**Maître de taux** – Sélectionnez le maître de taux pour le profil de classement.</span><span class="sxs-lookup"><span data-stu-id="55ea5-125">**Rate master** – Select the rate master for the rating profile.</span></span> <span data-ttu-id="55ea5-126">Vous pouvez utiliser le maître des taux pour définir un type de base de taux et une base de taux.</span><span class="sxs-lookup"><span data-stu-id="55ea5-126">You can use the rate master to define a rate base type and a rate base.</span></span> <span data-ttu-id="55ea5-127">Pour plus d’informations, voir [Paramétrage des maîtres de taux](set-up-rate-masters.md).</span><span class="sxs-lookup"><span data-stu-id="55ea5-127">For more information, see [Set up rate masters](set-up-rate-masters.md).</span></span>
    - <span data-ttu-id="55ea5-128">**Moteur de temps de transit** – Sélectionnez le moteur de temps de transit pour le profils de classement.</span><span class="sxs-lookup"><span data-stu-id="55ea5-128">**Transit time engine** – Select the transit time engine for the rating profile.</span></span>
    - <span data-ttu-id="55ea5-129">**Indice de carburant du transporteur** – Sélectionnez l’indice de carburant du transporteur pour le profil de classement.</span><span class="sxs-lookup"><span data-stu-id="55ea5-129">**Carrier fuel index** – Select the carrier fuel index for the rating profile.</span></span>
    - <span data-ttu-id="55ea5-130">**Date et heure de début effectives** et **Date et heure de fin effectives** – Définissez la période pendant laquelle le profil de classement doit être actif.</span><span class="sxs-lookup"><span data-stu-id="55ea5-130">**Effect start date and time** and **Effective end date and time** – Define the period when the rating profile should be active.</span></span>

1. <span data-ttu-id="55ea5-131">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="55ea5-131">On the Action Pane, select **Save**.</span></span>

## <a name="create-a-rating-profile-directly-on-the-shipping-carriers-page"></a><span data-ttu-id="55ea5-132">Créer ou modifier un profil de classement directement sur la page Transporteurs</span><span class="sxs-lookup"><span data-stu-id="55ea5-132">Create a rating profile directly on the Shipping carriers page</span></span>

1. <span data-ttu-id="55ea5-133">Allez dans **Gestion du transport \> Configuration \> Transporteurs \> Transporteurs**.</span><span class="sxs-lookup"><span data-stu-id="55ea5-133">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="55ea5-134">Sélectionnez un transporteur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="55ea5-134">Select a shipping carrier in the list.</span></span>
1. <span data-ttu-id="55ea5-135">Dans l’organisateur **profils de classement**, cliquez sur **Nouveau** pour créer un profil de classement.</span><span class="sxs-lookup"><span data-stu-id="55ea5-135">On the **Rating profiles** FastTab, select **New** to create a rating profile.</span></span>
1. <span data-ttu-id="55ea5-136">Définissez les champs du nouveau profils de classement.</span><span class="sxs-lookup"><span data-stu-id="55ea5-136">Set the fields for the new rating profile.</span></span> <span data-ttu-id="55ea5-137">Ces champs correspondent aux champs de la page **profils de classement**, comme décrit dans la section précédente de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="55ea5-137">These fields correspond to the fields on the **Rating profiles** page, as described in previous section of this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="55ea5-138">Les profils créés sur la page **Transporteurs** sont également affichés sur la page **profils de classement**.</span><span class="sxs-lookup"><span data-stu-id="55ea5-138">Profiles that are created on the **Shipping carriers** page are also shown on the **Rating profiles** page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]