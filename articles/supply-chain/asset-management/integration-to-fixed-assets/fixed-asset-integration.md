---
title: Intégration de la gestion des actifs avec des immobilisations
description: Cette rubrique explique comment intégrer les modules Gestion d’actifs et Immobilisations, afin de pouvoir lier des immobilisations à des actifs de maintenance.
author: kamaybac
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: a45bf1f62cdcc8abed2ec157a223e7f3fddec7ce
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809852"
---
# <a name="integrate-asset-management-with-fixed-assets"></a><span data-ttu-id="a0579-103">Intégration de la gestion des actifs avec des immobilisations</span><span class="sxs-lookup"><span data-stu-id="a0579-103">Integrate asset management with fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a0579-104">En intégrant les modules **Gestion d’actifs** et **Immobilisations**, afin de pouvoir lier des immobilisations à des actifs de maintenance.</span><span class="sxs-lookup"><span data-stu-id="a0579-104">By integrating the **Asset management** and **Fixed assets** modules, you can link fixed assets with maintenance assets.</span></span> <span data-ttu-id="a0579-105">Les utilisateurs d’immobilisations peuvent ensuite créer un actif de maintenance à partir d’un actif fixe, nouveau ou existant, et les utilisateurs de la gestion d’actifs peuvent associer un actif de maintenance à un actif fixe existant.</span><span class="sxs-lookup"><span data-stu-id="a0579-105">Fixed assets users can then create a maintenance asset from a new or existing fixed asset, and Asset management users can associate a maintenance asset with an existing fixed asset.</span></span> <span data-ttu-id="a0579-106">Cette fonctionnalité permet également aux utilisateurs des immobilisations de visualiser facilement les coûts qui ont été enregistrés à partir des ordres de travail pour les actifs de maintenance associés.</span><span class="sxs-lookup"><span data-stu-id="a0579-106">This feature also makes it easy for Fixed assets users to view the costs that were posted from work orders for related maintenance assets.</span></span>

> [!NOTE]
> <span data-ttu-id="a0579-107">Dans cette rubrique, *actifs de maintenance* se réfère aux actifs du module **Gestion d’actifs**, et *Immobilisations* se réfère aux actifs du module **Immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="a0579-107">In this topic, *maintenance assets* refer to assets from the **Asset management** module, and *fixed assets* refer to assets from the **Fixed assets** module.</span></span>

## <a name="set-a-default-location-for-new-maintenance-assets-that-are-created-from-fixed-assets-optional"></a><span data-ttu-id="a0579-108">Définir un emplacement par défaut pour les nouveaux actifs de maintenance créés à partir d’immobilisations (facultatif)</span><span class="sxs-lookup"><span data-stu-id="a0579-108">Set a default location for new maintenance assets that are created from fixed assets (optional)</span></span>

<span data-ttu-id="a0579-109">Cette configuration facultative vous permet de définir un poste technique par défaut pour les nouveaux actifs de maintenance créés à partir d’immobilisations.</span><span class="sxs-lookup"><span data-stu-id="a0579-109">This optional configuration lets you set a default functional location for new maintenance assets that are created from fixed assets.</span></span> <span data-ttu-id="a0579-110">Vous terminez généralement cette configuration une seule fois, si vous la terminez.</span><span class="sxs-lookup"><span data-stu-id="a0579-110">You typically complete this configuration this just one time, if you complete it at all.</span></span>

<span data-ttu-id="a0579-111">Procédez comme suit pour effectuer cette configuration :</span><span class="sxs-lookup"><span data-stu-id="a0579-111">To complete the configuration, follow these steps.</span></span>

1. <span data-ttu-id="a0579-112">Accédez à **Gestion d’actifs \> Configuration \> Paramètres de gestion des actifs**.</span><span class="sxs-lookup"><span data-stu-id="a0579-112">Go to **Asset management \> Setup \> Asset management parameters**.</span></span>
1. <span data-ttu-id="a0579-113">Sous l’onglet **Immobilisations**, dans le champ **Poste technique**, sélectionnez l’emplacement par défaut.</span><span class="sxs-lookup"><span data-stu-id="a0579-113">On the **Fixed assets** tab, in the **Functional location** field, select the default location.</span></span>
1. <span data-ttu-id="a0579-114">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a0579-114">On the Action Pane, select **Save**.</span></span>

## <a name="work-with-integrated-maintenance-assets-and-fixed-assets"></a><span data-ttu-id="a0579-115">Utiliser des actifs de maintenance et des immobilisations intégrés</span><span class="sxs-lookup"><span data-stu-id="a0579-115">Work with integrated maintenance assets and fixed assets</span></span>

<span data-ttu-id="a0579-116">Cette section fournit un ensemble de procédures qui montrent différentes manières d’utiliser les fonctionnalités intégrées de gestion des actifs et des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="a0579-116">This section provides a collection of procedures that show various ways that you can work with the integrated Asset management and Fixed assets features.</span></span>

### <a name="associate-an-existing-maintenance-asset-with-a-fixed-asset"></a><span data-ttu-id="a0579-117">Associer un actif de maintenance existant à une immobilisation</span><span class="sxs-lookup"><span data-stu-id="a0579-117">Associate an existing maintenance asset with a fixed asset</span></span>

<span data-ttu-id="a0579-118">Pour associer un actif de maintenance existant à une immobilisation, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a0579-118">To associate an existing maintenance asset with a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="a0579-119">Accédez à **Gestion des actifs \> Actifs \> Tous les Actifs** (ou **Actifs actifs**).</span><span class="sxs-lookup"><span data-stu-id="a0579-119">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="a0579-120">Sélectionnez un actif.</span><span class="sxs-lookup"><span data-stu-id="a0579-120">Select an asset.</span></span>
1. <span data-ttu-id="a0579-121">Sur l’organisateur **Immobilisation**, dans le champ **Numéro d’immobilisation**, sélectionnez une immobilisation existante.</span><span class="sxs-lookup"><span data-stu-id="a0579-121">On the **Fixed asset** FastTab, in the **Fixed asset number** field, select an existing fixed asset.</span></span>
1. <span data-ttu-id="a0579-122">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a0579-122">On the Action Pane, select **Save**.</span></span>

### <a name="view-the-fixed-asset-that-is-associated-with-a-selected-maintenance-asset"></a><span data-ttu-id="a0579-123">Afficher l’immobilisation associée à un actif de maintenance sélectionné</span><span class="sxs-lookup"><span data-stu-id="a0579-123">View the fixed asset that is associated with a selected maintenance asset</span></span>

<span data-ttu-id="a0579-124">Pour afficher l’immobilisation associée à un actif de maintenance sélectionné, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a0579-124">To view the fixed asset that is associated with a selected maintenance asset, follow these steps.</span></span>

1. <span data-ttu-id="a0579-125">Accédez à **Gestion des actifs \> Actifs \> Tous les Actifs** (ou **Actifs actifs**).</span><span class="sxs-lookup"><span data-stu-id="a0579-125">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="a0579-126">Sélectionnez un actif.</span><span class="sxs-lookup"><span data-stu-id="a0579-126">Select an asset.</span></span>
1. <span data-ttu-id="a0579-127">Sur l’organisateur **Immobilisation**, dans le champ **Numéro d’immobilisation**, sélectionnez le lien.</span><span class="sxs-lookup"><span data-stu-id="a0579-127">On the **Fixed asset** FastTab, in the **Fixed asset number** field, select the link.</span></span>

    <span data-ttu-id="a0579-128">La page **Immobilisations** de l’actif sélectionné s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="a0579-128">The **Fixed assets** page for the selected asset is opened.</span></span> <span data-ttu-id="a0579-129">(En règle générale, cette page se trouve à l’adresse **Immobilisations \> Immobilisations \> Immobilisations**.)</span><span class="sxs-lookup"><span data-stu-id="a0579-129">(Typically, this page is found at **Fixed assets \> Fixed assets \> Fixed assets**.)</span></span>

### <a name="view-the-maintenance-asset-that-is-associated-with-a-selected-fixed-asset"></a><span data-ttu-id="a0579-130">Afficher la ressource en cours de maintenance associée à une immobilisation sélectionné</span><span class="sxs-lookup"><span data-stu-id="a0579-130">View the maintenance asset that is associated with a selected fixed asset</span></span>

<span data-ttu-id="a0579-131">Pour afficher la ressource en cours de maintenance associée à une immobilisation sélectionné, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a0579-131">To view the maintenance asset that is associated with a selected fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="a0579-132">Allez dans **Immobilisations \> Immobilisations \> Immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="a0579-132">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="a0579-133">Sélectionnez un actif.</span><span class="sxs-lookup"><span data-stu-id="a0579-133">Select an asset.</span></span>
1. <span data-ttu-id="a0579-134">Dans le volet Actions, sous l’onglet **Gestion des actifs**, dans le groupe **Nouveau**, sélectionnez **Ressource en cours de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="a0579-134">On the Action Pane, on the **Asset management** tab, in the **View** group, select **Maintenance asset**.</span></span>

    <span data-ttu-id="a0579-135">La page **Ressource en cours de maintenance** de l’actif associé à l’immobilisation sélectionnée est ouverte.</span><span class="sxs-lookup"><span data-stu-id="a0579-135">The **Maintenance asset** page for the asset that is associated with the selected fixed asset is opened.</span></span> <span data-ttu-id="a0579-136">(En règle générale, cette page se trouve à l’adresse **Gestion d’actifs \> Actifs \> Tous les actifs**.)</span><span class="sxs-lookup"><span data-stu-id="a0579-136">(Typically, this page is found at **Asset management \> Assets \> All assets**.)</span></span>

### <a name="view-maintenance-costs-that-are-associated-with-a-fixed-asset"></a><span data-ttu-id="a0579-137">Afficher les coûts de maintenance associés à une immobilisation</span><span class="sxs-lookup"><span data-stu-id="a0579-137">View maintenance costs that are associated with a fixed asset</span></span>

<span data-ttu-id="a0579-138">Les ordres de travail de gestion des actifs peuvent être enregistrés pour les ressources en cours de maintenance, et chacun de ces ordres de travail a généralement un coût.</span><span class="sxs-lookup"><span data-stu-id="a0579-138">Asset management work orders can be posted for maintenance assets, and each of those work orders typically has a cost.</span></span> <span data-ttu-id="a0579-139">Lorsqu’une immobilisation est associée à une ressource en cours de maintenance, vous pouvez aller directement de l’immobilisation pour afficher les coûts associés.</span><span class="sxs-lookup"><span data-stu-id="a0579-139">When a fixed asset is associated with a maintenance asset, you can go directly from the fixed asset to view the related costs.</span></span>

<span data-ttu-id="a0579-140">Pour afficher les coûts de maintenance associés à une immobilisation, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a0579-140">To view the maintenance costs that are associated with a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="a0579-141">Allez dans **Immobilisations \> Immobilisations \> Immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="a0579-141">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="a0579-142">Sélectionnez un actif.</span><span class="sxs-lookup"><span data-stu-id="a0579-142">Select an asset.</span></span>
1. <span data-ttu-id="a0579-143">Dans le volet Actions, sous l’onglet **Gestion des actifs**, dans le groupe **Nouveau**, sélectionnez **Coût de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="a0579-143">On the Action Pane, on the **Asset management** tab, in the **View** group, select **Maintenance cost**.</span></span>

    <span data-ttu-id="a0579-144">La page **Coût de maintenance** est ouverte et affiche les coûts associés.</span><span class="sxs-lookup"><span data-stu-id="a0579-144">The **Maintenance cost** page is opened and shows the related costs.</span></span>

### <a name="create-a-new-maintenance-asset-for-an-existing-fixed-asset"></a><a name="new-maintenance-from-fixed"></a><span data-ttu-id="a0579-145">Créer une ressource en cours de maintenance pour une immobilisation existante</span><span class="sxs-lookup"><span data-stu-id="a0579-145">Create a new maintenance asset for an existing fixed asset</span></span>

<span data-ttu-id="a0579-146">Pour créer une ressource en cours de maintenance pour une immobilisation associée, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a0579-146">To create a new maintenance asset for an existing fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="a0579-147">Allez dans **Immobilisations \> Immobilisations \> Immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="a0579-147">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="a0579-148">Sélectionnez un actif.</span><span class="sxs-lookup"><span data-stu-id="a0579-148">Select an asset.</span></span>
1. <span data-ttu-id="a0579-149">Dans le volet Actions, sous l’onglet **Gestion des actifs**, dans le groupe **Nouveau**, sélectionnez **Créer une ressource en cours de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="a0579-149">On the Action Pane, on the **Asset management** tab, in the **New** group, select **Create maintenance asset**.</span></span> <span data-ttu-id="a0579-150">(Si cette option n’est pas disponible, une ressource en cours de maintenance peut déjà être associée à l’immobilisation sélectionnée.)</span><span class="sxs-lookup"><span data-stu-id="a0579-150">(If this option is unavailable, a maintenance asset might already be associated with the selected fixed asset.)</span></span>
1. <span data-ttu-id="a0579-151">Terminez la création de l’actif comme décrit dans [Créer un actif](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="a0579-151">Finish creating the asset as described in [Create an asset](../objects/create-an-object.md).</span></span>

### <a name="create-a-new-fixed-asset-and-add-a-new-maintenance-asset-for-it"></a><span data-ttu-id="a0579-152">Créer une immobilisation et ajoutez-lui une nouvelle ressource en cours de maintenance</span><span class="sxs-lookup"><span data-stu-id="a0579-152">Create a new fixed asset and add a new maintenance asset for it</span></span>

<span data-ttu-id="a0579-153">Pour créer une immobilisation et lui ajouter une nouvelle ressource en cours de maintenance, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a0579-153">To create a new fixed asset and add a new maintenance asset for it, follow these steps.</span></span>

1. <span data-ttu-id="a0579-154">Allez dans **Immobilisations \> Immobilisations \> Immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="a0579-154">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="a0579-155">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a0579-155">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a0579-156">Terminez la création de l’immobilisation comme décrit dans [Créer une immobilisation](../../../finance/fixed-assets/tasks/create-fixed-asset.md).</span><span class="sxs-lookup"><span data-stu-id="a0579-156">Finish creating the fixed asset as described in [Create a fixed asset](../../../finance/fixed-assets/tasks/create-fixed-asset.md).</span></span>
1. <span data-ttu-id="a0579-157">Dans le volet Actions, sous l’onglet **Gestion des actifs**, dans le groupe **Nouveau**, sélectionnez **Créer une ressource en cours de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="a0579-157">On the Action Pane, on the **Asset management** tab, in the **New** group, select **Create maintenance asset**.</span></span>
1. <span data-ttu-id="a0579-158">Terminez la création de l’actif comme décrit dans [Créer un actif](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="a0579-158">Finish creating the asset as described in [Create an asset](../objects/create-an-object.md).</span></span>

### <a name="remove-the-association-between-two-assets"></a><span data-ttu-id="a0579-159">Supprimer l’association entre deux actifs</span><span class="sxs-lookup"><span data-stu-id="a0579-159">Remove the association between two assets</span></span>

<span data-ttu-id="a0579-160">Dans certains cas, vous devrez peut-être dissocier une ressource en cours de maintenance de son immobilisation.</span><span class="sxs-lookup"><span data-stu-id="a0579-160">In some cases, you might have to disassociate a maintenance asset from its fixed asset.</span></span> <span data-ttu-id="a0579-161">Par exemple, si vous souhaitez [créer une ressource en cours de maintenance](#new-maintenance-from-fixed) à partir d’une immobilisation, vous devez d’abord supprimer toute association existante.</span><span class="sxs-lookup"><span data-stu-id="a0579-161">For example, if you want to [create a new maintenance asset](#new-maintenance-from-fixed) from a fixed asset, you must first remove any existing association.</span></span>

<span data-ttu-id="a0579-162">Pour supprimer une association existante entre une ressource en cours de maintenance et une immobilisation, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a0579-162">To remove an existing association between a maintenance asset and a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="a0579-163">Accédez à **Gestion des actifs \> Actifs \> Tous les Actifs** (ou **Actifs actifs**).</span><span class="sxs-lookup"><span data-stu-id="a0579-163">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="a0579-164">Recherchez et ouvrez l’immobilisation.</span><span class="sxs-lookup"><span data-stu-id="a0579-164">Find and open the fixed asset.</span></span>
1. <span data-ttu-id="a0579-165">Sur l’organisateur **Immobilisation**, effacez la valeur du champ **Poste technique**.</span><span class="sxs-lookup"><span data-stu-id="a0579-165">On the **Fixed asset** FastTab, clear the value from the **Functional location** field.</span></span>
1. <span data-ttu-id="a0579-166">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a0579-166">On the Action Pane, select **Save**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]