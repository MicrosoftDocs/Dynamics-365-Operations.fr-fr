---
title: Finaliser le paramétrage de base d’un produit générique lancé
description: Cette rubrique indique comment terminer la configuration minimale requise avant que le produit générique puisse être utilisé dans les versions de nomenclature.
author: ShylaThompson
manager: tfehr
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8c6de9fa9dd49cc32f87a6041a3639198db9f182
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218607"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a><span data-ttu-id="94b4a-103">Finaliser le paramétrage de base d’un produit générique lancé</span><span class="sxs-lookup"><span data-stu-id="94b4a-103">Complete basic setup of a released product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="94b4a-104">Cette rubrique indique comment terminer la configuration minimale requise avant que le produit générique puisse être utilisé dans les versions de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="94b4a-104">This topic shows how to complete the minimum setup that is required before the product master can be used in BOM versions.</span></span>

<span data-ttu-id="94b4a-105">Il s’agit de la troisième procédure (parmi les huit) qui explique comment créer des combinaisons pour la configuration basée sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="94b4a-105">This is the third procedure out of eight which explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="94b4a-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="94b4a-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="94b4a-107">Accédez à **Volet de navigation > Modules > Gestion d’informations sur les produits > Produits > Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="94b4a-107">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="94b4a-108">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="94b4a-108">In the list, find and select the desired record.</span></span> <span data-ttu-id="94b4a-109">Sélectionnez le produit générique que vous avez lancé dans la deuxième procédure.</span><span class="sxs-lookup"><span data-stu-id="94b4a-109">Select the product master that you have released in the second procedure.</span></span> <span data-ttu-id="94b4a-110">Ce produit générique est créé avec la technologie de configuration basée sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="94b4a-110">This product master is created with the dimension-based configuration technology.</span></span>  
3. <span data-ttu-id="94b4a-111">Dans le volet Actions, sélectionnez **Produit**.</span><span class="sxs-lookup"><span data-stu-id="94b4a-111">On the Action Pane, select **Product**.</span></span>
4. <span data-ttu-id="94b4a-112">Sélectionnez **Groupes de dimensions** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="94b4a-112">Select **Dimension groups** to open the drop dialog.</span></span>
5. <span data-ttu-id="94b4a-113">Dans le champ **Groupe de dimensions de stockage**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="94b4a-113">In the **Storage dimension group** field, select the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="94b4a-114">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="94b4a-114">In the list, find and select the desired record.</span></span> <span data-ttu-id="94b4a-115">Le groupe de dimensions de stockage détermine les dimensions de stockage utilisées pour la transaction de produit.</span><span class="sxs-lookup"><span data-stu-id="94b4a-115">The storage dimension group determines which storage dimensions are used for product transaction.</span></span> <span data-ttu-id="94b4a-116">Sélectionnez **Site** pour cette procédure.</span><span class="sxs-lookup"><span data-stu-id="94b4a-116">Select **Site** for this procedure.</span></span>  
7. <span data-ttu-id="94b4a-117">Dans le champ **Groupe de dimensions de suivi**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="94b4a-117">In the **Tracking dimension group** field, select the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="94b4a-118">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="94b4a-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="94b4a-119">Le groupe de dimensions de suivi détermine les dimensions de suivi utilisées pour la transaction de produit.</span><span class="sxs-lookup"><span data-stu-id="94b4a-119">The tracking dimension group determines which tracking dimensions are used for product transaction.</span></span> <span data-ttu-id="94b4a-120">Sélectionnez **Aucun** pour cette procédure.</span><span class="sxs-lookup"><span data-stu-id="94b4a-120">Select **None** for this procedure.</span></span>  
9. <span data-ttu-id="94b4a-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="94b4a-121">Click **OK**.</span></span>
10. <span data-ttu-id="94b4a-122">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="94b4a-122">Click **Edit**.</span></span>
11. <span data-ttu-id="94b4a-123">Dans le champ **Groupe de modèles d’articles**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="94b4a-123">In the **Item model group** field, select the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="94b4a-124">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="94b4a-124">In the list, find and select the desired record.</span></span> <span data-ttu-id="94b4a-125">Les groupes de modèles d’articles contiennent des paramètres qui déterminent la manière dont les articles sont contrôlés et gérés au niveau des réceptions et sorties d’articles.</span><span class="sxs-lookup"><span data-stu-id="94b4a-125">Item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="94b4a-126">Ils déterminent également le mode de calcul de la consommation d’articles.</span><span class="sxs-lookup"><span data-stu-id="94b4a-126">They also determine how item consumption is calculated.</span></span> <span data-ttu-id="94b4a-127">Sélectionnez **FIFO** pour cette procédure.</span><span class="sxs-lookup"><span data-stu-id="94b4a-127">Select **FIFO** for this procedure.</span></span>  
13. <span data-ttu-id="94b4a-128">Développez la section **Gérer les coûts**.</span><span class="sxs-lookup"><span data-stu-id="94b4a-128">Expand the **Manage costs** section.</span></span>
14. <span data-ttu-id="94b4a-129">Dans le champ **Groupe d’articles**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="94b4a-129">In the **Item group** field, select the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="94b4a-130">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="94b4a-130">In the list, find and select the desired record.</span></span> <span data-ttu-id="94b4a-131">Les groupes d’articles sont utilisés pour gérer le stock en divisant les articles en stock en groupes.</span><span class="sxs-lookup"><span data-stu-id="94b4a-131">Item groups are used to manage inventory by dividing inventory items into groups.</span></span> <span data-ttu-id="94b4a-132">Sélectionnez **CarAudio** pour cette procédure.</span><span class="sxs-lookup"><span data-stu-id="94b4a-132">Select **CarAudio** for this procedure.</span></span>  
16. <span data-ttu-id="94b4a-133">Dans le volet Actions, sélectionnez **Planifier**.</span><span class="sxs-lookup"><span data-stu-id="94b4a-133">On the Action Pane, select **Plan**.</span></span>
17. <span data-ttu-id="94b4a-134">Sélectionnez **Paramètres de commande par défaut**.</span><span class="sxs-lookup"><span data-stu-id="94b4a-134">Select **Default order settings**.</span></span>
18. <span data-ttu-id="94b4a-135">Dans le champ **Type de commande par défaut**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="94b4a-135">In the **Default order type field**, select an option.</span></span> <span data-ttu-id="94b4a-136">Sélectionnez **Production** pour spécifier que l’option d’approvisionnement par défaut pour ce produit générique est de le produire.</span><span class="sxs-lookup"><span data-stu-id="94b4a-136">Select **Production** to specify that the default supply option for this product master is to produce it.</span></span>  
19. <span data-ttu-id="94b4a-137">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="94b4a-137">Select **Save**.</span></span>
20. <span data-ttu-id="94b4a-138">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="94b4a-138">Close the page.</span></span>
21. <span data-ttu-id="94b4a-139">Fermez le formulaire **Détails des produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="94b4a-139">Close the **Released product details** form.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]