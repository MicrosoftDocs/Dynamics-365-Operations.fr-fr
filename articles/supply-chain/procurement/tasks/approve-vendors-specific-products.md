--- 
title: "Approuver des fournisseurs pour des produits spécifiques"
description: "Cette procédure décrit comment approuver des fournisseurs pour les produits spécifiques."
author: mkirknel
manager: AnnBe
ms.date: 11/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: a6db8ab41ab393cc92b4fea0435608eff110d58b
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---
# <a name="approve-vendors-for-specific-products"></a><span data-ttu-id="308c8-103">Approuver des fournisseurs pour des produits spécifiques</span><span class="sxs-lookup"><span data-stu-id="308c8-103">Approve vendors for specific products</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="308c8-104">Cette procédure décrit comment approuver des fournisseurs pour les produits spécifiques.</span><span class="sxs-lookup"><span data-stu-id="308c8-104">This procedure shows you how to approve vendors for specific products.</span></span> <span data-ttu-id="308c8-105">Ceci vous permet de contrôler quels fournisseurs peuvent être utilisés lorsque le produit est ajouté à une commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="308c8-105">This allows you to control which vendors can be used when the product is added to a purchase order.</span></span> <span data-ttu-id="308c8-106">Vous pouvez utiliser cette procédure dans la société USMF fictive ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="308c8-106">You can use this procedure in demo data company USMF, or on your own data.</span></span> <span data-ttu-id="308c8-107">Cette tâche est généralement effectuée par un responsable des achats.</span><span class="sxs-lookup"><span data-stu-id="308c8-107">This task would typically be carried out by a Purchasing manager.</span></span>

1. <span data-ttu-id="308c8-108">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="308c8-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="308c8-109">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="308c8-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="308c8-110">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="308c8-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="308c8-111">Développez la section Achats.</span><span class="sxs-lookup"><span data-stu-id="308c8-111">Expand the Purchase section.</span></span>
    * <span data-ttu-id="308c8-112">S'il existe un fournisseur principal indiqué dans le champ Fournisseur, vous devez alors l'ajouter en tant que fournisseur agréé dans les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="308c8-112">If there is a primary vendor shown in the Vendor field, then you need to add this vendor as an approved vendor in the following steps.</span></span> <span data-ttu-id="308c8-113">Notez le numéro du fournisseur, s'il est indiqué.</span><span class="sxs-lookup"><span data-stu-id="308c8-113">Make a note of the vendor number, if one is shown.</span></span>  
5. <span data-ttu-id="308c8-114">Cliquez sur Achats dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="308c8-114">On the Action Pane, click Purchase.</span></span>
6. <span data-ttu-id="308c8-115">Cliquez sur Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="308c8-115">Click Setup.</span></span>
7. <span data-ttu-id="308c8-116">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="308c8-116">Click Add.</span></span>
8. <span data-ttu-id="308c8-117">Saisissez ou sélectionnez une valeur dans le champ Fournisseur.</span><span class="sxs-lookup"><span data-stu-id="308c8-117">In the Vendor field, enter or select a value.</span></span>
    * <span data-ttu-id="308c8-118">Sélectionnez le fournisseur agréé.</span><span class="sxs-lookup"><span data-stu-id="308c8-118">Select the approved vendor.</span></span> <span data-ttu-id="308c8-119">Au moins l'une des lignes doit être le fournisseur principal s'il y avait un dans l'enregistrement de produit.</span><span class="sxs-lookup"><span data-stu-id="308c8-119">At least one of the lines has to be the primary vendor if there was one in the product record.</span></span> <span data-ttu-id="308c8-120">Si vous avez noté le numéro de fournisseur auparavant, sélectionnez-le ici.</span><span class="sxs-lookup"><span data-stu-id="308c8-120">If you made a note of the vendor number earlier, select it here.</span></span>  
9. <span data-ttu-id="308c8-121">Dans le champ Expiration, entrer une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="308c8-121">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="308c8-122">Sélectionnez une date dans les mois à venir.</span><span class="sxs-lookup"><span data-stu-id="308c8-122">Choose a date a that is a few months ahead.</span></span>  
10. <span data-ttu-id="308c8-123">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="308c8-123">Click Add.</span></span>
11. <span data-ttu-id="308c8-124">Saisissez ou sélectionnez une valeur dans le champ Fournisseur.</span><span class="sxs-lookup"><span data-stu-id="308c8-124">In the Vendor field, enter or select a value.</span></span>
12. <span data-ttu-id="308c8-125">Dans le champ Expiration, entrer une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="308c8-125">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="308c8-126">Sélectionnez une date différente de la date d'expiration précédente.</span><span class="sxs-lookup"><span data-stu-id="308c8-126">Choose a date that is different than the previous expiration date.</span></span>  
13. <span data-ttu-id="308c8-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="308c8-127">Close the page.</span></span>
14. <span data-ttu-id="308c8-128">Cliquez sur Fournisseurs approuvés.</span><span class="sxs-lookup"><span data-stu-id="308c8-128">Click Approved vendors.</span></span>
15. <span data-ttu-id="308c8-129">Dans le champ Expiration, entrer une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="308c8-129">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="308c8-130">Cette date agit en tant qu'un filtre, donc vous pouvez voir qui sont les fournisseurs agréés jusqu'à une date donnée.</span><span class="sxs-lookup"><span data-stu-id="308c8-130">This date acts as a filter so you can see who the approved vendors are, up to a certain date.</span></span>  
16. <span data-ttu-id="308c8-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="308c8-131">Close the page.</span></span>
17. <span data-ttu-id="308c8-132">Cliquez sur Période d'effet.</span><span class="sxs-lookup"><span data-stu-id="308c8-132">Click Effective period.</span></span>
18. <span data-ttu-id="308c8-133">Entrez une date dans le champ Afficher les fournisseurs expirant le.</span><span class="sxs-lookup"><span data-stu-id="308c8-133">In the Show vendors expired by field, enter a date.</span></span>
    * <span data-ttu-id="308c8-134">Vous pouvez utiliser cette page pour identifier les fournisseurs dont le statut d'approbation expirera après une certaine date.</span><span class="sxs-lookup"><span data-stu-id="308c8-134">You can use this page to identify vendors where the approval status will expire after a certain date.</span></span>  
19. <span data-ttu-id="308c8-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="308c8-135">Close the page.</span></span>
20. <span data-ttu-id="308c8-136">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="308c8-136">Click Edit.</span></span>
21. <span data-ttu-id="308c8-137">Sélectionnez une option dans le champ Méthode de vérification fournisseur approuvée.</span><span class="sxs-lookup"><span data-stu-id="308c8-137">In the Approved vendor check method field, select an option.</span></span>
    * <span data-ttu-id="308c8-138">Ce champ vous permet de spécifier ce qu'il convient de faire si le produit est ajouté à une ligne de commande fournisseur dont le fournisseur n'est pas un fournisseur agréé.</span><span class="sxs-lookup"><span data-stu-id="308c8-138">This field allows you to select the policy for what should happen if the product is added to a purchase order line where the vendor is not an approved vendor.</span></span>  
22. <span data-ttu-id="308c8-139">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="308c8-139">Click Save.</span></span>
23. <span data-ttu-id="308c8-140">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="308c8-140">Close the page.</span></span>
24. <span data-ttu-id="308c8-141">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="308c8-141">Close the page.</span></span>
25. <span data-ttu-id="308c8-142">Accédez à Approvisionnements > Fournisseurs > Relations fournisseur/article > Liste de fournisseurs approuvés par article.</span><span class="sxs-lookup"><span data-stu-id="308c8-142">Go to Procurement and sourcing > Vendors > Vendor/item relations > Approved vendor list by item.</span></span>
    * <span data-ttu-id="308c8-143">Cette page vous donne une vue d'ensemble de tous les produits et des fournisseurs agréés.</span><span class="sxs-lookup"><span data-stu-id="308c8-143">This page gives you an overview of all products and the approved vendors.</span></span>  
26. <span data-ttu-id="308c8-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="308c8-144">Close the page.</span></span>
27. <span data-ttu-id="308c8-145">Accédez à Approvisionnements > Fournisseurs > Tous les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="308c8-145">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
    * <span data-ttu-id="308c8-146">Vous pouvez également commencer à partir d'un fournisseur, puis accéder à la liste de produits approuvés pour ce compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="308c8-146">You can also start from a vendor and then go to the list of approved products for that vendor account.</span></span>  
28. <span data-ttu-id="308c8-147">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="308c8-147">In the list, find and select the desired record.</span></span>
29. <span data-ttu-id="308c8-148">Cliquez sur Approvisionnement dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="308c8-148">On the Action Pane, click Procurement.</span></span>
30. <span data-ttu-id="308c8-149">Cliquez sur Liste de fournisseurs approuvés par fournisseur.</span><span class="sxs-lookup"><span data-stu-id="308c8-149">Click Approved vendor list by vendor.</span></span>
31. <span data-ttu-id="308c8-150">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="308c8-150">Close the page.</span></span>
32. <span data-ttu-id="308c8-151">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="308c8-151">Close the page.</span></span>


