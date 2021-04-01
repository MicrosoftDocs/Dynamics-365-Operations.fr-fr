---
title: Déplacer, remplacer et installer des actifs
description: Cette rubrique explique comment déplacer, remplacer et installer des actifs dans Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectReplace, EntAssetObjectInstallLookup, EntAssetObjectMove, EntAssetObjectTableEditSubObjects
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f5eff3cc1bcf85e1541917edf525d83c124edb7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253228"
---
# <a name="move-replace-and-install-assets"></a><span data-ttu-id="ede46-103">Déplacer, remplacer et installer des actifs</span><span class="sxs-lookup"><span data-stu-id="ede46-103">Move, replace, and install assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="ede46-104">Cette rubrique explique comment déplacer, remplacer et installer des actifs dans Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="ede46-104">This topic explains how to move, replace, and install assets in Asset Management.</span></span> <span data-ttu-id="ede46-105">Vous pouvez créer les actifs individuels sans aucun lien avec d’autres actifs, ou créer une structure d’actif incluant un actif parent (actif supérieur) et des actifs enfants associés (sous-actifs).</span><span class="sxs-lookup"><span data-stu-id="ede46-105">You can create individual assets that have no relations to other assets, or you can create an asset structure that includes a parent asset (top-level asset) and related child assets (sub-assets).</span></span> <span data-ttu-id="ede46-106">Dans Gestion des actifs, il existe trois approches pour déplacer et modifier l’emplacement d’un actif :</span><span class="sxs-lookup"><span data-stu-id="ede46-106">In Asset Management, there are three approaches to moving and changing the location of an asset:</span></span>

- <span data-ttu-id="ede46-107">**Déplacer** - Déplacement d’un actif vers une autre structure d’actif, ou vers un autre emplacement dans la même structure d’actif.</span><span class="sxs-lookup"><span data-stu-id="ede46-107">**Move** – Move an asset either to another asset structure or to another location in the same asset structure.</span></span>
- <span data-ttu-id="ede46-108">**Remplacer** - Suppression temporaire d’un actif d’une structure d’actif afin de pouvoir réparer ou rénover un actif, puis rajout de l’actif rénové à la structure d’actif ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="ede46-108">**Replace** – Temporarily remove an asset from an asset structure so that it can be repaired or refurbished, and then add the refurbished asset back to the asset structure later.</span></span> <span data-ttu-id="ede46-109">Sinon, remplacement définitif d’un actif usagé par un nouvel actif.</span><span class="sxs-lookup"><span data-stu-id="ede46-109">Alternatively, permanently replace a used asset with a new asset.</span></span>
- <span data-ttu-id="ede46-110">**Installer** - Installation d’un actif parent et de tous les actifs enfants associés à un poste technique.</span><span class="sxs-lookup"><span data-stu-id="ede46-110">**Install** – Install a parent asset and any related child assets on a functional location.</span></span>

> [!NOTE]
> <span data-ttu-id="ede46-111">L’actif que vous déplacez, remplacez ou installez peut être associé à un autre poste technique.</span><span class="sxs-lookup"><span data-stu-id="ede46-111">The asset that you move, replace, or install might be related to another functional location.</span></span> <span data-ttu-id="ede46-112">Dans ce cas, l’actif peut utiliser des dimensions financières du poste technique.</span><span class="sxs-lookup"><span data-stu-id="ede46-112">In that case, the asset might use financial dimensions of the functional location.</span></span> <span data-ttu-id="ede46-113">Sur la page **Types de postes techniques**, vous paramétrez le traitement des dimensions financières aux postes techniques.</span><span class="sxs-lookup"><span data-stu-id="ede46-113">On the **Functional location types** page, you set up the handling of financial dimensions on functional locations.</span></span>

## <a name="move-asset"></a><span data-ttu-id="ede46-114">Déplacer l’actif</span><span class="sxs-lookup"><span data-stu-id="ede46-114">Move asset</span></span>

<span data-ttu-id="ede46-115">Utilisez la fonctionnalité **Déplacer l’actif** pour déplacer l’actif vers une autre structure d’actif, ou vers un autre emplacement dans la même structure d’actif.</span><span class="sxs-lookup"><span data-stu-id="ede46-115">Use the **Move asset** function to move an asset either to another asset structure or to another location in the same asset structure.</span></span> <span data-ttu-id="ede46-116">Vous pouvez également déplacer un actif en dehors d’une structure d’actif afin qu’il devienne autonome sans aucune relation de structure.</span><span class="sxs-lookup"><span data-stu-id="ede46-116">You can also move an asset out of an asset structure so that it becomes a standalone asset that has no structure relations.</span></span>

> [!NOTE]
> <span data-ttu-id="ede46-117">N’utilisez pas cette fonctionnalité si des actifs sont en cours de réparation ou remplacés temporairement.</span><span class="sxs-lookup"><span data-stu-id="ede46-117">Don't use this function if assets are being repaired or temporarily replaced.</span></span> <span data-ttu-id="ede46-118">Au lieu de cela, utilisez la fonctionnalité **Remplacer l’actif** décrite plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="ede46-118">Instead, use the **Replace asset** functionality that is described later in this topic.</span></span>

1. <span data-ttu-id="ede46-119">Sélectionnez **Gestion des actifs** \> **Commun** \> **Actifs** \> **Tous les Actifs** ou **Actifs actifs**.</span><span class="sxs-lookup"><span data-stu-id="ede46-119">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="ede46-120">Dans la liste, sélectionnez l’actif à déplacer.</span><span class="sxs-lookup"><span data-stu-id="ede46-120">In the list, select the asset to move.</span></span> <span data-ttu-id="ede46-121">Si l’actif comporte des actifs enfants, vous déplacez également ces actifs.</span><span class="sxs-lookup"><span data-stu-id="ede46-121">If the asset has child assets, you also move those assets.</span></span>
3. <span data-ttu-id="ede46-122">Sélectionnez **Déplacer l’actif**.</span><span class="sxs-lookup"><span data-stu-id="ede46-122">Select **Move asset**.</span></span>
4. <span data-ttu-id="ede46-123">Pour déplacer l’actif afin qu’il puisse faire une partie d’une structure d’actif, sélectionnez le nouvel actif parent dans le champ **Actif parent**.</span><span class="sxs-lookup"><span data-stu-id="ede46-123">To move the asset so that it becomes part of an asset structure, select the new parent asset in the **Parent asset** field.</span></span> <span data-ttu-id="ede46-124">Si vous déplacez un actif enfant, et que vous souhaitez en faire un actif autonome qui n’a aucune relation de structure, laissez le champ **Actif parent** vide.</span><span class="sxs-lookup"><span data-stu-id="ede46-124">If you're moving a child asset, and you want to make it a standalone asset that has no structure relations, leave the **Parent asset** field blank.</span></span>
5. <span data-ttu-id="ede46-125">Par défaut, le champ **Date d’effet** est défini sur la date et l’heure actuelles.</span><span class="sxs-lookup"><span data-stu-id="ede46-125">By default, the **Effective** field is set to the current date and time.</span></span> <span data-ttu-id="ede46-126">Toutefois, vous pouvez sélectionner d’autres date et heure à partir desquelles le déplacement de l’actif sera valide.</span><span class="sxs-lookup"><span data-stu-id="ede46-126">However, you can select a different date and time that the asset move is valid from.</span></span>
6. <span data-ttu-id="ede46-127">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ede46-127">Select **OK**.</span></span>

## <a name="replace-asset"></a><span data-ttu-id="ede46-128">Remplacer l’actif</span><span class="sxs-lookup"><span data-stu-id="ede46-128">Replace asset</span></span>

<span data-ttu-id="ede46-129">Utilisez la fonctionnalité **Remplacer l’actif** en relation avec des réparations, une rénovation ou un remplacement permanent d’un actif usagé par un nouvel actif.</span><span class="sxs-lookup"><span data-stu-id="ede46-129">Use the **Replace asset** function in connection with repairs, refurbishment, or permanent replacement of a worn-out asset by a new asset.</span></span> <span data-ttu-id="ede46-130">Cette fonctionnalité permet de remplacer les actifs enfants dans une structure d’actif.</span><span class="sxs-lookup"><span data-stu-id="ede46-130">This function is used to replace child assets in an asset structure.</span></span> <span data-ttu-id="ede46-131">Pour les actifs parents (c’est-à-dire les actifs qui n’ont pas d’actif parent actuellement), ce remplacement est effectué à un poste technique.</span><span class="sxs-lookup"><span data-stu-id="ede46-131">For parent assets (that is, assets that don't currently have a parent asset), this replacement is done on a functional location.</span></span> <span data-ttu-id="ede46-132">Pour plus d’informations sur le remplacement des actifs parents à un poste technique, voir [Installer des actifs et des postes techniques](../functional-locations/install-objects-on-functional-locations.md).</span><span class="sxs-lookup"><span data-stu-id="ede46-132">For more information about how to replace parent assets on a functional location, see [Install assets on functional locations](../functional-locations/install-objects-on-functional-locations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ede46-133">Si un atelier de réparation est lié à votre service de production, vous pouvez créer des postes techniques, tels que **Réparation**, **Rebut** et **Stockage** pour gérer la réparation et le remplacement des actifs.</span><span class="sxs-lookup"><span data-stu-id="ede46-133">If a repair shop is related to your production department, you can create functional locations such as **Repair**, **Scrap**, and **Storage** to handle the repair and replacement of assets.</span></span>

1. <span data-ttu-id="ede46-134">Sélectionnez **Gestion des actifs** \> **Commun** \> **Actifs** \> **Tous les Actifs** ou **Actifs actifs**.</span><span class="sxs-lookup"><span data-stu-id="ede46-134">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="ede46-135">Dans la liste, sélectionnez l’actif enfant à remplacer.</span><span class="sxs-lookup"><span data-stu-id="ede46-135">In the list, select the child asset to replace.</span></span> <span data-ttu-id="ede46-136">Si l’actif comporte des actifs enfants, vous remplacez également ces actifs.</span><span class="sxs-lookup"><span data-stu-id="ede46-136">If the asset has child assets, you also replace those assets.</span></span>
3. <span data-ttu-id="ede46-137">Sélectionnez **Remplacer l’actif**.</span><span class="sxs-lookup"><span data-stu-id="ede46-137">Select **Replace asset**.</span></span>

    <span data-ttu-id="ede46-138">Le champ **Modification de la structure** affiche les dernières date et heure auxquelles l’actif et les actifs enfants associés sélectionnés ont été déplacés dans la structure de l’actif.</span><span class="sxs-lookup"><span data-stu-id="ede46-138">The **Structure change** field shows the last date and time that the selected asset and related child assets were moved in the asset structure.</span></span>

4. <span data-ttu-id="ede46-139">Dans la section **Actif sélectionné**, dans le champ **Poste technique cible**, sélectionnez le poste technique vers lequel déplacer l’actif.</span><span class="sxs-lookup"><span data-stu-id="ede46-139">In the **Selected asset** section, in the **Target functional location** field, select the functional location to move the asset to.</span></span> <span data-ttu-id="ede46-140">Par exemple, sélectionnez l’emplacement **Réparation** ou **Rebut**.</span><span class="sxs-lookup"><span data-stu-id="ede46-140">For example, select the **Repair** or **Scrap** location.</span></span>

    <span data-ttu-id="ede46-141">Dans la section **Actif parent**, le champ **Date d’effet** affiche les dernières date et heure auxquelles l’actif parent et les actifs enfants associés ont été installés ou déplacés au poste technique actuel.</span><span class="sxs-lookup"><span data-stu-id="ede46-141">In the **Parent asset** section, the **Effective** field shows the last date and time that the parent asset and related child assets were installed or moved on the current functional location.</span></span>

5. <span data-ttu-id="ede46-142">Dans la section **Nouvel actif**, dans le champ **Actif**, sélectionnez l’actif à insérer comme remplacement temporaire ou permanent pour l’actif sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ede46-142">In the **New asset** section, in the **Asset** field, select the asset to insert as a temporary or permanent replacement for the selected asset.</span></span> <span data-ttu-id="ede46-143">Cet actif peut se trouver actuellement à un autre poste technique, tel que **Stockage**.</span><span class="sxs-lookup"><span data-stu-id="ede46-143">This asset might currently be located on another functional location, such as **Storage**.</span></span>
7. <span data-ttu-id="ede46-144">Dans la section **Début d’effet**, le champ **Date d’effet** est défini sur la date et l’heure actuelles par défaut.</span><span class="sxs-lookup"><span data-stu-id="ede46-144">In the **Effective from** section, the **Effective** field is set to the current date and time by default.</span></span> <span data-ttu-id="ede46-145">Toutefois, vous pouvez sélectionner d’autres date et heure à partir desquelles le remplacement de l’actif sera valide.</span><span class="sxs-lookup"><span data-stu-id="ede46-145">However, you can select a different date and time that the asset replacement is valid from.</span></span>
8. <span data-ttu-id="ede46-146">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ede46-146">Select **OK**.</span></span>

## <a name="install-asset"></a><span data-ttu-id="ede46-147">Installer l’actif</span><span class="sxs-lookup"><span data-stu-id="ede46-147">Install asset</span></span>

<span data-ttu-id="ede46-148">Utilisez la fonctionnalité **Installer l’actif** pour installer une structure d’actif à un poste technique.</span><span class="sxs-lookup"><span data-stu-id="ede46-148">Use the **Install asset** function to install an asset structure on a functional location.</span></span>

> [!NOTE]
> <span data-ttu-id="ede46-149">Sélectionnez toujours un actif parent.</span><span class="sxs-lookup"><span data-stu-id="ede46-149">Always select a parent asset.</span></span> <span data-ttu-id="ede46-150">L’actif parent et les actifs enfants associés sont déplacés vers le poste technique sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ede46-150">The parent asset and related child assets will be moved to the selected functional location.</span></span>

1. <span data-ttu-id="ede46-151">Sélectionnez **Gestion des actifs** \> **Commun** \> **Actifs** \> **Tous les Actifs** ou **Actifs actifs**.</span><span class="sxs-lookup"><span data-stu-id="ede46-151">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="ede46-152">Dans la liste, sélectionnez l’actif parent à installer à un autre poste technique.</span><span class="sxs-lookup"><span data-stu-id="ede46-152">In the list, select the parent asset to install on another functional location.</span></span>
3. <span data-ttu-id="ede46-153">Sélectionnez **Installer l’actif**.</span><span class="sxs-lookup"><span data-stu-id="ede46-153">Select **Install asset**.</span></span>

    <span data-ttu-id="ede46-154">La section **Attributs** affiche les attributs de l’actif qui sont paramétrés sur l’actif parent.</span><span class="sxs-lookup"><span data-stu-id="ede46-154">The **Attributes** section shows the asset attributes that are set up on the parent asset.</span></span>

4. <span data-ttu-id="ede46-155">Dans le champ **Poste technique**, sélectionner le nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="ede46-155">In the **Functional location** field, select the new location.</span></span>
5. <span data-ttu-id="ede46-156">Par défaut, le champ **Date d’effet** est défini sur la date et l’heure actuelles.</span><span class="sxs-lookup"><span data-stu-id="ede46-156">By default, the **Effective** field is set to the current date and time.</span></span> <span data-ttu-id="ede46-157">Toutefois, vous pouvez sélectionner d’autres date et heure à partir desquelles l’installation sur la structure d’actif sera valide.</span><span class="sxs-lookup"><span data-stu-id="ede46-157">However, you can select a different date and time that the installation on the asset structure is valid from.</span></span>
6. <span data-ttu-id="ede46-158">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ede46-158">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]