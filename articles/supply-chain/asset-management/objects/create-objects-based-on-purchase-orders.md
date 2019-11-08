---
title: Créer des actifs basés sur les commandes fournisseur
description: Cette rubrique explique comment créer une liste d'éléments d'actifs pouvant servir de base à la création d'actifs pour les travaux de maintenance dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
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
ms.openlocfilehash: 6eba14e285f23338cad0243fca567b30c6d4d3f2
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571574"
---
# <a name="create-assets-based-on-purchase-orders"></a><span data-ttu-id="3639e-103">Créer des actifs basés sur les commandes fournisseur</span><span class="sxs-lookup"><span data-stu-id="3639e-103">Create assets based on purchase orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="3639e-104">Cette rubrique explique comment créer une liste d'éléments d'actifs pouvant servir de base à la création d'actifs pour les travaux de maintenance dans le module Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="3639e-104">This topic explains how you can create a list of asset items that can be used as a basis for creating assets for maintenance jobs in Asset Management.</span></span> <span data-ttu-id="3639e-105">En fonction des actifs, vous pouvez afficher une liste des lignes de commande créées sur ces articles.</span><span class="sxs-lookup"><span data-stu-id="3639e-105">Based on the asset items, you are able to view a list of the purchase order lines that have been created on those items.</span></span> <span data-ttu-id="3639e-106">Le but de cette fonctionnalité est de créer facilement un actif dans le module Gestion des actifs basé sur une commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3639e-106">The purpose of this functionality is to easily create an asset in Asset Management based on a purchase order.</span></span>

<span data-ttu-id="3639e-107">Premièrement, vous définissez les articles à utiliser pour créer les actifs d'une commande fournisseur dans **Articles d'actifs**.</span><span class="sxs-lookup"><span data-stu-id="3639e-107">First, you set up the items to be used for creating assets from a purchase order in **Asset items**.</span></span> <span data-ttu-id="3639e-108">Après avoir créé une ligne de commande fournisseur, créez les actifs dans **Actifs en attente**.</span><span class="sxs-lookup"><span data-stu-id="3639e-108">After creating a purchase order line, you create the assets in **Pending assets**.</span></span> <span data-ttu-id="3639e-109">Il est possible de déterminer à quel stade de la commande fournisseur l'actif doit être créé.</span><span class="sxs-lookup"><span data-stu-id="3639e-109">It is possible to decide at which stage of the purchase order the asset should be created.</span></span>


## <a name="select-asset-items"></a><span data-ttu-id="3639e-110">Sélectionner des éléments d'actifs</span><span class="sxs-lookup"><span data-stu-id="3639e-110">Select asset items</span></span>

1. <span data-ttu-id="3639e-111">Cliquez sur **Gestion des actifs** > **Paramétrage** > **Actifs** > **Articles**.</span><span class="sxs-lookup"><span data-stu-id="3639e-111">Click **Asset management** > **Setup** > **Assets** > **Items**.</span></span>
2. <span data-ttu-id="3639e-112">Cliquez sur **Nouveau** pour créer un élément d'actif.</span><span class="sxs-lookup"><span data-stu-id="3639e-112">Click **New** to create a new asset item.</span></span>
3. <span data-ttu-id="3639e-113">Sélectionnez l'élément dans le champ **Numéro d'article**.</span><span class="sxs-lookup"><span data-stu-id="3639e-113">Select the item in the **Item number** field.</span></span> <span data-ttu-id="3639e-114">Lorsque vous laissez ce champ, le nom d'article est automatiquement inséré dans le champ **Nom du produit**.</span><span class="sxs-lookup"><span data-stu-id="3639e-114">When you leave that field, the item name is automatically inserted in the **Product name** field.</span></span>
4. <span data-ttu-id="3639e-115">Dans l'organisateur **Général**, sélectionnez un type d'actif pour l'article.</span><span class="sxs-lookup"><span data-stu-id="3639e-115">On the **General** FastTab, select an asset type for the item.</span></span>
5. <span data-ttu-id="3639e-116">Sélectionnez le fabricant et le modèle d'actif pour l'article.</span><span class="sxs-lookup"><span data-stu-id="3639e-116">Select asset manufacturer and model for the item.</span></span>
6. <span data-ttu-id="3639e-117">Enregistrez l'élément.</span><span class="sxs-lookup"><span data-stu-id="3639e-117">Save the item.</span></span>


## <a name="create-assets-from-pending-assets"></a><span data-ttu-id="3639e-118">Créer des actifs à partir des actifs en attente</span><span class="sxs-lookup"><span data-stu-id="3639e-118">Create assets from pending assets</span></span>

1. <span data-ttu-id="3639e-119">Cliquez sur **Gestion des actifs** > **Commun** > **Actifs** > **Actifs en attente**.</span><span class="sxs-lookup"><span data-stu-id="3639e-119">Click **Asset management** > **Common** > **Assets** > **Pending Assets**.</span></span>
2. <span data-ttu-id="3639e-120">Vous verrez une liste mise à jour des commandes d'achat basée sur les articles sélectionnés dans **Articles d'actifs**.</span><span class="sxs-lookup"><span data-stu-id="3639e-120">You will see an updated list of the purchase orders based on the items selected in **Asset items**.</span></span>
3. <span data-ttu-id="3639e-121">Vous pouvez filtrer le statut des commandes d'achat pour sélectionner le statut de cycle de vie auquel l'actif doit être créé.</span><span class="sxs-lookup"><span data-stu-id="3639e-121">You can filter the status of purchase orders to select at which lifecycle state the asset should be created.</span></span> <span data-ttu-id="3639e-122">Par exemple, vous souhaiterez peut-être créer des actifs uniquement lorsqu'un reçu de produit aura été enregistré lors d'une commande d'achat.</span><span class="sxs-lookup"><span data-stu-id="3639e-122">For example, you may only want to create assets when a product receipt has been posted on a purchase order.</span></span>
4. <span data-ttu-id="3639e-123">Sélectionnez le lien **Numéro de référence** dans une ligne de commande fournisseur pour afficher des informations détaillées sur l'article.</span><span class="sxs-lookup"><span data-stu-id="3639e-123">Select the **Reference number** link on a purchase order line to view detailed information about the item.</span></span>
5. <span data-ttu-id="3639e-124">Si vous souhaitez modifier les dimensions à afficher sous l'organisateur **Dimensions de stock**, cliquez sur le bouton **Affichage des dimensions**, puis effectuez vos sélections.</span><span class="sxs-lookup"><span data-stu-id="3639e-124">If you want to edit which dimensions are displayed on the **Inventory dimensions** FastTab, click the **Display Dimensions** button, and make your selections.</span></span>
6. <span data-ttu-id="3639e-125">Si vous souhaitez créer un actif sur une ligne de commande fournisseur, activez la case à cocher dans la colonne **Marquer** pour cette ligne sur la page de liste, puis cliquez sur **Créer des actifs**.</span><span class="sxs-lookup"><span data-stu-id="3639e-125">If you want to create an asset based on a purchase order line, select the check box in the **Mark** column for that line on the list page, and click **Create assets**.</span></span> <span data-ttu-id="3639e-126">Un message s'affiche vous informant de l'ID d'actif.</span><span class="sxs-lookup"><span data-stu-id="3639e-126">A message will be displayed informing you of the asset ID.</span></span>
7. <span data-ttu-id="3639e-127">Sélectionnez l'actif dans la liste **Tous les actifs**, puis cliquez sur **Modifier** pour ajouter davantage d'informations à l'actif.</span><span class="sxs-lookup"><span data-stu-id="3639e-127">Select the asset in the **All assets** list and click **Edit** to add more information to the asset.</span></span>
8. <span data-ttu-id="3639e-128">Dans **Actifs en attente**, si vous souhaitez supprimer une ligne car vous ne souhaitez pas créer d'actif, activez la case à cocher dans la colonne **Marquer** pour cette ligne, puis cliquez sur **Ignorer les actifs en attente**.</span><span class="sxs-lookup"><span data-stu-id="3639e-128">In **Pending assets**, if you want to delete a line because you don't want to create an asset, select the check box in the **Mark** column for that line, and click **Discard pending assets**.</span></span> <span data-ttu-id="3639e-129">Un message s'affiche vous informant de l'ID d'actif.</span><span class="sxs-lookup"><span data-stu-id="3639e-129">A message will be displayed informing you of the asset ID.</span></span> <span data-ttu-id="3639e-130">Vous ne supprimez pas la commande fournisseur ou la commande client, juste l'enregistrement à partir duquel vous auriez pu créer un actif dans **Gestion des actifs**.</span><span class="sxs-lookup"><span data-stu-id="3639e-130">You are not deleting the purchase order or sales order, just the record from which you could have created an asset in **Asset Management**.</span></span>

>[!NOTE]
><span data-ttu-id="3639e-131">Toutes les dimensions de produit (taille, couleur, configuration, etc.) sont transférées automatiquement dans les attributs d'actifs.</span><span class="sxs-lookup"><span data-stu-id="3639e-131">All product dimensions (size, color, configuration etc.) are automatically transferred to the asset attributes.</span></span> <span data-ttu-id="3639e-132">Les dimensions de suivi (numéro de série) sont enregistrés directement sur l'actif lors de sa création.</span><span class="sxs-lookup"><span data-stu-id="3639e-132">Tracking dimensions (serial number) are stored directly on the asset when the asset is created.</span></span>


## <a name="find-pending-assets"></a><span data-ttu-id="3639e-133">Rechercher des actifs en attente</span><span class="sxs-lookup"><span data-stu-id="3639e-133">Find pending assets</span></span>

<span data-ttu-id="3639e-134">Vous pouvez exécuter un **nombre d'actifs en attente** pour vérifier les actifs en attente.</span><span class="sxs-lookup"><span data-stu-id="3639e-134">You can run a **Pending asset count** to check for pending assets.</span></span> <span data-ttu-id="3639e-135">Par exemple, cette fonction peut être utilisée pour recevoir une notification chaque fois qu'un actif en attente est prêt à être créé en tant qu'actif.</span><span class="sxs-lookup"><span data-stu-id="3639e-135">For example, this function can be used for receiving a notification each time a pending asset is ready to be created as an asset.</span></span>

1. <span data-ttu-id="3639e-136">Cliquez sur **Gestion des actifs** > **Périodique** > **Actifs** > **Nombre d'actifs en attente**.</span><span class="sxs-lookup"><span data-stu-id="3639e-136">Click **Asset management** > **Periodic** > **Assets** > **Pending asset count**.</span></span>
2. <span data-ttu-id="3639e-137">Cliquez sur **Ajouter** pour exécuter la tâche et mettre à jour la liste dans **Actifs en attente**.</span><span class="sxs-lookup"><span data-stu-id="3639e-137">Click **OK** to run the job and update the list in **Pending assets**.</span></span>
3. <span data-ttu-id="3639e-138">Vous pouvez configurer l'exécution de ce travail en tant que traitement par lots, par exemple une fois par jour.</span><span class="sxs-lookup"><span data-stu-id="3639e-138">You can set up this job to run as a batch job, for example, once each day.</span></span>

<span data-ttu-id="3639e-139">**Attention :** Si les données sont modifiées dans une commande fournisseur *une fois que* vous avez créé un actif en fonction de l'élément concerné, ces modifications ne sont pas répercutées sur l'actif.</span><span class="sxs-lookup"><span data-stu-id="3639e-139">**Caution:** If data is changed on a purchase order *after* you have created an asset based on the appertaining item, those changes will not be reflected on the asset.</span></span>
