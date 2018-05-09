--- 
title: "Spécifier une adresse de chargement pour une transaction intracommunautaire"
description: "Cette procédure indique comment spécifier une adresse de chargement pour une transaction d'échanges intracommunautaires."
author: v-oloski
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 0feeba19510d3c2790b1a77bca3c8ec6e7078726
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---
# <a name="specify-a-lading-address-for-an-intra-community-transaction"></a><span data-ttu-id="c93a7-103">Spécifier une adresse de chargement pour une transaction intracommunautaire</span><span class="sxs-lookup"><span data-stu-id="c93a7-103">Specify a lading address for an intra-community transaction</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c93a7-104">Cette procédure indique comment spécifier une adresse de chargement pour une transaction d'échanges intracommunautaires.</span><span class="sxs-lookup"><span data-stu-id="c93a7-104">This procedure shows how to specify a lading address for an intra-community trade transaction.</span></span> <span data-ttu-id="c93a7-105">Par exemple, une société allemande commande des articles auprès d'un fournisseur ayant une adresse professionnelle allemande.</span><span class="sxs-lookup"><span data-stu-id="c93a7-105">For example, a Germany company orders items from a vendor with a German business address.</span></span> <span data-ttu-id="c93a7-106">Ce fournisseur a un entrepôt en Italie et expédie les articles depuis cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="c93a7-106">This vendor has a warehouse in Italy and ships the items from there.</span></span> <span data-ttu-id="c93a7-107">Cette livraison doit être portée dans la déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="c93a7-107">This delivery must be reported in the Intrastat.</span></span> <span data-ttu-id="c93a7-108">Le même comportement est valide pour les retours client.</span><span class="sxs-lookup"><span data-stu-id="c93a7-108">The same behavior is valid for customer returns.</span></span>
<span data-ttu-id="c93a7-109">Cette procédure s'applique à tous les pays/régions européens.</span><span class="sxs-lookup"><span data-stu-id="c93a7-109">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="c93a7-110">La tâche a été créée avec les données de démonstration de la société fictive DEMF, avec une adresse principale en Allemagne.</span><span class="sxs-lookup"><span data-stu-id="c93a7-110">The task was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="c93a7-111">Avant d'exécuter cette procédure, vous devez configurer la génération d'états de déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="c93a7-111">Before you can complete this procedure, you must configure Intrastat reporting.</span></span> <span data-ttu-id="c93a7-112">Cette procédure est destinée aux comptables.</span><span class="sxs-lookup"><span data-stu-id="c93a7-112">This procedure is intended for accountants.</span></span> <span data-ttu-id="c93a7-113">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="c93a7-113">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="c93a7-114">Accédez à Comptabilité fournisseur > Commandes fournisseur > Toutes les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="c93a7-114">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="c93a7-115">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c93a7-115">Click New.</span></span>
3. <span data-ttu-id="c93a7-116">Entrer ou sélectionner une valeur</span><span class="sxs-lookup"><span data-stu-id="c93a7-116">Enter or select a value</span></span>
    * <span data-ttu-id="c93a7-117">Par exemple, sélectionnez DE-001.</span><span class="sxs-lookup"><span data-stu-id="c93a7-117">For example, select DE-001.</span></span> <span data-ttu-id="c93a7-118">Ce fournisseur a une adresse professionnelle allemande.</span><span class="sxs-lookup"><span data-stu-id="c93a7-118">This vendor has a German business address.</span></span>  
4. <span data-ttu-id="c93a7-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c93a7-119">Click OK.</span></span>
5. <span data-ttu-id="c93a7-120">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c93a7-120">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="c93a7-121">Dans le champ Numéro d'article, entrez ou sélectionnez une valeur D0001.</span><span class="sxs-lookup"><span data-stu-id="c93a7-121">In the Item number field, enter or select a value D0001.</span></span>
7. <span data-ttu-id="c93a7-122">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="c93a7-122">Click Save.</span></span>
8. <span data-ttu-id="c93a7-123">Cliquez sur Recevoir dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="c93a7-123">On the Action Pane, click Receive.</span></span>
9. <span data-ttu-id="c93a7-124">Cliquez sur Détails du transport.</span><span class="sxs-lookup"><span data-stu-id="c93a7-124">Click Transportation details.</span></span>
10. <span data-ttu-id="c93a7-125">Dans le champ Date et heure du chargement, entrez une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="c93a7-125">In the Loading date and time field, enter a date and time.</span></span>
11. <span data-ttu-id="c93a7-126">Cliquez sur Ajouter une adresse.</span><span class="sxs-lookup"><span data-stu-id="c93a7-126">Click Add address.</span></span>
12. <span data-ttu-id="c93a7-127">Cliquez sur Nouveau et créez une adresse dont l'objet est Chargement.</span><span class="sxs-lookup"><span data-stu-id="c93a7-127">Click New and create new address with purpose Lading.</span></span>
13. <span data-ttu-id="c93a7-128">Dans le champ Nom ou description, tapez « Italien ».</span><span class="sxs-lookup"><span data-stu-id="c93a7-128">In the Name or description field, type 'Italian'.</span></span>
14. <span data-ttu-id="c93a7-129">Sélectionnez Chargement comme valeur.</span><span class="sxs-lookup"><span data-stu-id="c93a7-129">Select Lading as the value.</span></span>
    * <span data-ttu-id="c93a7-130">Notez que l'objet de l'adresse doit être Chargement.</span><span class="sxs-lookup"><span data-stu-id="c93a7-130">Note that that address purpose must be Lading.</span></span>  
15. <span data-ttu-id="c93a7-131">Dans le champ Pays/Région, entrez ou sélectionnez une valeur ITA.</span><span class="sxs-lookup"><span data-stu-id="c93a7-131">In the Country/region field, enter or select a value ITA.</span></span>
16. <span data-ttu-id="c93a7-132">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="c93a7-132">Click Save.</span></span>
17. <span data-ttu-id="c93a7-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c93a7-133">Close the page.</span></span>
18. <span data-ttu-id="c93a7-134">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="c93a7-134">Click Save.</span></span>
    * <span data-ttu-id="c93a7-135">Vérifiez si l'adresse de chargement est correcte.</span><span class="sxs-lookup"><span data-stu-id="c93a7-135">Verify that the lading address is correct.</span></span>  
19. <span data-ttu-id="c93a7-136">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c93a7-136">Close the page.</span></span>
20. <span data-ttu-id="c93a7-137">Cliquez sur Achats dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="c93a7-137">On the Action Pane, click Purchase.</span></span>
21. <span data-ttu-id="c93a7-138">Cliquez sur Confirmer.</span><span class="sxs-lookup"><span data-stu-id="c93a7-138">Click Confirm.</span></span>
22. <span data-ttu-id="c93a7-139">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="c93a7-139">On the Action Pane, click Invoice.</span></span>
23. <span data-ttu-id="c93a7-140">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="c93a7-140">Click Invoice.</span></span>
24. <span data-ttu-id="c93a7-141">Tapez une valeur dans le champ Nombre.</span><span class="sxs-lookup"><span data-stu-id="c93a7-141">In the Number field, type a value.</span></span>
25. <span data-ttu-id="c93a7-142">Entrez une date dans le champ Date de facture.</span><span class="sxs-lookup"><span data-stu-id="c93a7-142">In the Invoice date field, enter a date.</span></span>
26. <span data-ttu-id="c93a7-143">Cliquez sur Valeur par défaut de : Quantité de l'accusé de réception de marchandises pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="c93a7-143">Click Default from: Product receipt quantity to open the drop dialog.</span></span>
27. <span data-ttu-id="c93a7-144">Dans le champ Quantité par défaut pour les lignes, sélectionnez « Quantité commandée ».</span><span class="sxs-lookup"><span data-stu-id="c93a7-144">In the Default quantity for lines field, select 'Ordered quantity'.</span></span>
28. <span data-ttu-id="c93a7-145">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c93a7-145">Click OK.</span></span>
29. <span data-ttu-id="c93a7-146">Cliquez sur Détails du transport.</span><span class="sxs-lookup"><span data-stu-id="c93a7-146">Click Transportation details.</span></span>
    * <span data-ttu-id="c93a7-147">Vérifiez si les marchandises ont été expédiées depuis l'Italie.</span><span class="sxs-lookup"><span data-stu-id="c93a7-147">Verify that goods were shipped from Italy.</span></span> <span data-ttu-id="c93a7-148">Si nécessaire, vous pouvez modifier les détails de chargement.</span><span class="sxs-lookup"><span data-stu-id="c93a7-148">If necessary, you can edit the lading details.</span></span>  
30. <span data-ttu-id="c93a7-149">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c93a7-149">Close the page.</span></span>
31. <span data-ttu-id="c93a7-150">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="c93a7-150">Click Post.</span></span>
32. <span data-ttu-id="c93a7-151">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c93a7-151">Close the page.</span></span>
33. <span data-ttu-id="c93a7-152">Accédez à Taxe > Déclarations > Commerce extérieur > Déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="c93a7-152">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
34. <span data-ttu-id="c93a7-153">Cliquez sur Transférer.</span><span class="sxs-lookup"><span data-stu-id="c93a7-153">Click Transfer.</span></span>
35. <span data-ttu-id="c93a7-154">Sélectionnez Oui dans le champ Facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="c93a7-154">Select Yes in the Vendor invoice field.</span></span>
36. <span data-ttu-id="c93a7-155">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c93a7-155">Click OK.</span></span>
37. <span data-ttu-id="c93a7-156">Cliquez sur l'onglet Général.</span><span class="sxs-lookup"><span data-stu-id="c93a7-156">Click the General tab.</span></span>
    * <span data-ttu-id="c93a7-157">Recherchez une ligne nouvellement créée et vérifiez si l'expéditeur a expédié les marchandises depuis l'Italie.</span><span class="sxs-lookup"><span data-stu-id="c93a7-157">Find a newly created line and verify that the sender shipped the goods from Italy.</span></span>  


