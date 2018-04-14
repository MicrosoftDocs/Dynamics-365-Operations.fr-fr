--- 
title: "Finaliser le paramétrage de base d'un produit générique lancé"
description: "Cette procédure indique comment terminer la configuration minimale requise avant que le produit générique puisse être utilisé dans les versions de nomenclature."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d52b337d9062fa8051e02144df5d064e54a6784d
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="complete-basic-setup-of-a-released-product-master"></a><span data-ttu-id="32fc8-103">Finaliser le paramétrage de base d'un produit générique lancé</span><span class="sxs-lookup"><span data-stu-id="32fc8-103">Complete basic setup of a released product master</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="32fc8-104">Cette procédure indique comment terminer la configuration minimale requise avant que le produit générique puisse être utilisé dans les versions de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="32fc8-104">This procedure shows how to complete the minimum setup that is required before the product master can be used in BOM versions.</span></span>

<span data-ttu-id="32fc8-105">Il s'agit de la troisième procédure (parmi les huit) qui explique comment créer des combinaisons pour la configuration basée sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="32fc8-105">This is the third procedure out of eight which explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="32fc8-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="32fc8-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="32fc8-107">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="32fc8-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="32fc8-108">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="32fc8-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="32fc8-109">Sélectionnez le produit générique que vous avez lancé dans la deuxième procédure.</span><span class="sxs-lookup"><span data-stu-id="32fc8-109">Select the product master that you have released in the second procedure.</span></span> <span data-ttu-id="32fc8-110">Ce produit générique est créé avec la technologie de configuration basée sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="32fc8-110">This product master is created with the dimension-based configuration technology.</span></span>  
3. <span data-ttu-id="32fc8-111">Dans le volet Actions, cliquez sur Produit.</span><span class="sxs-lookup"><span data-stu-id="32fc8-111">On the Action Pane, click Product.</span></span>
4. <span data-ttu-id="32fc8-112">Cliquez sur Groupes de dimensions pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="32fc8-112">Click Dimension groups to open the drop dialog.</span></span>
5. <span data-ttu-id="32fc8-113">Dans le champ Groupe de dimensions de stockage, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="32fc8-113">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="32fc8-114">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="32fc8-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="32fc8-115">Le groupe de dimensions de stockage détermine les dimensions de stockage utilisées pour la transaction de produit.</span><span class="sxs-lookup"><span data-stu-id="32fc8-115">The storage dimension group determines which storage dimensions are used for product transaction.</span></span> <span data-ttu-id="32fc8-116">Sélectionnez Site pour cette procédure.</span><span class="sxs-lookup"><span data-stu-id="32fc8-116">Select Site for this procedure.</span></span>  
7. <span data-ttu-id="32fc8-117">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="32fc8-117">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="32fc8-118">Dans le champ Groupe de dimensions de suivi, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="32fc8-118">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="32fc8-119">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="32fc8-119">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="32fc8-120">Le groupe de dimensions de suivi détermine les dimensions de suivi utilisées pour la transaction de produit.</span><span class="sxs-lookup"><span data-stu-id="32fc8-120">The tracking dimension group determines which tracking dimensions are used for product transaction.</span></span> <span data-ttu-id="32fc8-121">Sélectionnez Aucun pour cette procédure.</span><span class="sxs-lookup"><span data-stu-id="32fc8-121">Select None for this procedure.</span></span>  
10. <span data-ttu-id="32fc8-122">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="32fc8-122">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="32fc8-123">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="32fc8-123">Click OK.</span></span>
12. <span data-ttu-id="32fc8-124">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="32fc8-124">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="32fc8-125">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="32fc8-125">Click Edit.</span></span>
    * <span data-ttu-id="32fc8-126">Ouvrez le formulaire Détails des produits lancés pour poursuivre la tâche de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="32fc8-126">Open the Released product details form to continue the setup task.</span></span>  
14. <span data-ttu-id="32fc8-127">Dans le champ groupe de modèles d'articles, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="32fc8-127">In the Item model group field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="32fc8-128">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="32fc8-128">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="32fc8-129">Les groupes de modèles d'articles contiennent des paramètres qui déterminent la manière dont les articles sont contrôlés et gérés au niveau des réceptions et sorties d'articles.</span><span class="sxs-lookup"><span data-stu-id="32fc8-129">Item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="32fc8-130">Ils déterminent également le mode de calcul de la consommation d'articles.</span><span class="sxs-lookup"><span data-stu-id="32fc8-130">They also determine how item consumption is calculated.</span></span> <span data-ttu-id="32fc8-131">Sélectionnez FIFO pour cette procédure.</span><span class="sxs-lookup"><span data-stu-id="32fc8-131">Select   FIFO for this procedure.</span></span>  
16. <span data-ttu-id="32fc8-132">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="32fc8-132">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="32fc8-133">Développez ou réduisez la section Gérer les coûts.</span><span class="sxs-lookup"><span data-stu-id="32fc8-133">Expand or collapse the Manage costs section.</span></span>
18. <span data-ttu-id="32fc8-134">Dans le champ Groupe d'articles, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="32fc8-134">In the Item group field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="32fc8-135">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="32fc8-135">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="32fc8-136">Les groupes d'articles sont utilisés pour gérer le stock en divisant les articles en stock en groupes.</span><span class="sxs-lookup"><span data-stu-id="32fc8-136">Item groups are used to manage inventory by dividing inventory items into groups.</span></span> <span data-ttu-id="32fc8-137">Sélectionnez CarAudio pour cette procédure.</span><span class="sxs-lookup"><span data-stu-id="32fc8-137">Select   CarAudio for this procedure.</span></span>  
20. <span data-ttu-id="32fc8-138">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="32fc8-138">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="32fc8-139">Cliquez sur Planifier dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="32fc8-139">On the Action Pane, click Plan.</span></span>
22. <span data-ttu-id="32fc8-140">Cliquez sur Paramètres de commande par défaut.</span><span class="sxs-lookup"><span data-stu-id="32fc8-140">Click Default order settings.</span></span>
23. <span data-ttu-id="32fc8-141">Dans le champ Type de commande par défaut, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="32fc8-141">In the Default order type field, select an option.</span></span>
    * <span data-ttu-id="32fc8-142">Sélectionnez Production pour spécifier que l'option d'approvisionnement par défaut pour ce produit générique est de le produire.</span><span class="sxs-lookup"><span data-stu-id="32fc8-142">Select Production to specify that the default supply option for this product master is to produce it.</span></span>  
24. <span data-ttu-id="32fc8-143">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="32fc8-143">Close the page.</span></span>
25. <span data-ttu-id="32fc8-144">Fermez le formulaire Détails des produits lancés.</span><span class="sxs-lookup"><span data-stu-id="32fc8-144">Close the Released product details form.</span></span>


