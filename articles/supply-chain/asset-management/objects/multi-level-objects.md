---
title: Actifs à plusieurs niveaux
description: Cette rubrique explique comment créer et supprimer des actifs à plusieurs niveaux.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c656ee9422bbcbb095305fad835fc18eceaeb89
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839677"
---
# <a name="multi-level-assets"></a><span data-ttu-id="7e8d7-103">Actifs à plusieurs niveaux</span><span class="sxs-lookup"><span data-stu-id="7e8d7-103">Multi-level assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="7e8d7-104">Cette rubrique explique comment créer et supprimer des actifs à plusieurs niveaux.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-104">This topic explains how to create and delete multi-level assets.</span></span> <span data-ttu-id="7e8d7-105">Vous pouvez créer des actifs et des sous-actifs associés dans une structure arborescente hiérarchique.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-105">You can create assets and related sub-assets in a hierarchical tree structure.</span></span> <span data-ttu-id="7e8d7-106">De cette manière, vous pouvez afficher les relations et les dépendances entre les actifs.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-106">In this way, you can show relations and dependencies among assets.</span></span> <span data-ttu-id="7e8d7-107">Les tâches de maintenance peuvent être associées à tous les niveaux de la structure arborescente.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-107">Maintenance jobs can be related to all levels of the tree structure.</span></span> <span data-ttu-id="7e8d7-108">Des statistiques peuvent également être créées à un niveau particulier ou en tant que somme de tous les sous-niveaux.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-108">Statistics can also be created for an individual level or as a sum of all sub-asset levels.</span></span>

<span data-ttu-id="7e8d7-109">Sur la page de liste **Tous les actifs** (**Gestion des actifs** \> **Commun** \> **Actifs** \> **Tous les actifs**), la colonne **Actif** répertorie les actifs dans l’ordre hiérarchique.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-109">On the **All Assets** list page (**Asset management** \> **Common** \> **Assets** \> **All assets**), the **Asset** column lists assets in hierarchical order.</span></span> <span data-ttu-id="7e8d7-110">La colonne **Parent** affiche le parent associé.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-110">The **Parent** column shows the related parent.</span></span> <span data-ttu-id="7e8d7-111">En outre, si les actifs et les sous-actifs ont déjà été créés, la section **Arborescence d’actifs** du volet **Informations associées** affiche les actifs sous forme de structure arborescente.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-111">Additionally, if assets and sub-assets have already been created, the **Asset tree** section in the **Related information** pane shows the assets in a tree structure.</span></span>

<span data-ttu-id="7e8d7-112">Pour plus d’informations sur la création d’un actif, voir [Créer un actif](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="7e8d7-112">For information about how to create an asset, see [Create an asset](../objects/create-an-object.md).</span></span> <span data-ttu-id="7e8d7-113">Pour créer un sous-actif, sélectionnez l’actif parent dans le champ **Parent** sur l’organisateur **Général**.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-113">To create a sub-asset, select the parent asset in the **Parent** field on the **General** FastTab.</span></span>

## <a name="copy-an-asset-or-asset-structure"></a><span data-ttu-id="7e8d7-114">Copier un actif ou une structure d’actif</span><span class="sxs-lookup"><span data-stu-id="7e8d7-114">Copy an asset or asset structure</span></span>

<span data-ttu-id="7e8d7-115">Si votre société a plusieurs structures d’actifs similaires, vous pouvez utiliser la fonction Copier dans Gestion des actifs pour en créer rapidement.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-115">If your company has several similar asset structures, you can use the Copy function in Asset Management to quickly create them.</span></span>

1. <span data-ttu-id="7e8d7-116">Sélectionnez **Gestion des actifs** \> **Commun** \> **Actifs** \> **Tous les actifs**.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-116">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="7e8d7-117">Sur la page de liste **Tous les actifs**, sélectionnez l’actif à copier.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-117">On the **All assets** list page, select the asset to copy.</span></span> <span data-ttu-id="7e8d7-118">Par exemple, si vous souhaitez copier la structure d’actif complète, y compris les sous-actifs, sélectionnez un actif parent.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-118">For example, if you want to copy the whole asset structure, including sub-assets, select a parent asset.</span></span>
3. <span data-ttu-id="7e8d7-119">Sélectionnez **Copier l’actif**.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-119">Select **Copy asset**.</span></span> <span data-ttu-id="7e8d7-120">Dans la section **Copier depuis**, le champ **Actif** est défini sur l’actif sélectionné dans la page de liste.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-120">In the **Copy from** section, the **Asset** field is set to the asset that you selected on the list page.</span></span>
4. <span data-ttu-id="7e8d7-121">Dans la section **Copier vers**, dans le champ **Actif**, entrez le nom du nouvel actif.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-121">In the **Copy to** section, in the **Asset** field, enter the name of the new asset.</span></span>
5. <span data-ttu-id="7e8d7-122">Si l’actif créé doit faire partie d’une structure d’actif existante, dans la section **Actif parent**, dans le champ **Actif**, sélectionnez un ID parent.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-122">If the asset that you're creating should be part of an existing asset structure, in the **Parent asset** section, in the **Asset** field, select a parent ID.</span></span>
6. <span data-ttu-id="7e8d7-123">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-123">Select **OK**.</span></span> <span data-ttu-id="7e8d7-124">La nouvelle structure d’actif est affichée sur la page de liste **Tous les actifs**.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-124">The new asset structure is shown on the **All assets** list page.</span></span> <span data-ttu-id="7e8d7-125">Tous les attributs d’actif, plans de maintenance et visites de maintenance associés à l’actif copié sont transférés vers le nouvel actif ou la nouvelle structure d’actif.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-125">All asset attributes, maintenance plans, and maintenance rounds that are related to the asset that you copied are transferred to the new asset or asset structure.</span></span>

<span data-ttu-id="7e8d7-126">Lorsque vous copiez une structure d’actif, les sous-actifs de la nouvelle structure ont le même nom que les sous-actifs que vous avez copiés.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-126">When you copy an asset structure, the sub-assets in the new structure have the same name as the sub-assets that you copied.</span></span> <span data-ttu-id="7e8d7-127">Une fois la procédure de copie terminée, vous pouvez aisément modifier le nom et d’autres paramètres d’un actif.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-127">After the copy procedure is completed, you can easily change the name and other settings for an asset.</span></span> <span data-ttu-id="7e8d7-128">Sélectionnez l’actif sur la page de liste **Tous les actifs**, puis sélectionnez le bouton **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-128">Select the asset on the **All assets** list page, and then select the **Edit** button.</span></span>

> [!NOTE]
> <span data-ttu-id="7e8d7-129">Lorsque vous copiez un actif ou une structure d’actif, l’état du cycle de vie du nouvel actif est réinitialisé à l’état que vous avez défini comme l’état de cycle de vie initial pour les actifs.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-129">When you copy an asset or asset structure, the lifecycle state of the new assets is reset to whatever state you defined as the initial lifecycle state for assets.</span></span> <span data-ttu-id="7e8d7-130">Le poste technique est redéfini sur le poste technique par défaut.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-130">The functional location is reset to the default functional location.</span></span>

## <a name="delete-an-asset-or-asset-structure"></a><span data-ttu-id="7e8d7-131">Supprimer un actif ou une structure d’actif</span><span class="sxs-lookup"><span data-stu-id="7e8d7-131">Delete an asset or asset structure</span></span>

<span data-ttu-id="7e8d7-132">Si un actif a des sous-actifs associés, vous pouvez le supprimer uniquement si aucune demande de maintenant, tâche d’ordre de travail, enregistrement de défaillance ou évaluation des conditions ne sont enregistrés sur l’un des actifs.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-132">If an asset has related sub-assets, you can delete it only if no maintenance requests, work order jobs, fault registrations, or condition assessments are registered on any of the assets.</span></span>

1. <span data-ttu-id="7e8d7-133">Sur la page de liste **Tous les actifs**, sélectionnez l’actif à supprimer.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-133">On the **All assets** list page, select the asset to delete.</span></span>
2. <span data-ttu-id="7e8d7-134">Sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-134">Select **Delete**.</span></span>

> [!NOTE]
> <span data-ttu-id="7e8d7-135">Si vous ne pouvez pas supprimer un actif à l’aide de cette procédure, vous pouvez également paramétrer un état du cycle de vie de l’actif à cet effet.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-135">If you can't delete an asset by using this procedure, another way to handle deletion is to set up an asset lifecycle state for this purpose.</span></span> <span data-ttu-id="7e8d7-136">Par exemple, vous pouvez paramétrer un état du cycle de vie **Mis au rebut** ou **Supprimé** sur la page **États du cycle de vie de l’actif**.</span><span class="sxs-lookup"><span data-stu-id="7e8d7-136">For example, you can set up a **Scrapped** or **Deleted** lifecycle state on the **Asset lifecycle states** page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]