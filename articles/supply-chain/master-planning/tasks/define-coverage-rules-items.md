--- 
title: "Définir des règles de couverture pour les articles"
description: "Les données fictives utilisées pour créer cette procédure correspondent à la société USMF."
author: YuyuScheller
manager: AnnBe
ms.date: 11/02/2017
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
ms.openlocfilehash: 4d28abe06cb7bfd43fd95af8cd88e022a51f5380
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="define-coverage-rules-for-items"></a><span data-ttu-id="cf00b-103">Définir des règles de couverture pour les articles</span><span class="sxs-lookup"><span data-stu-id="cf00b-103">Define coverage rules for items</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cf00b-104">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="cf00b-104">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="cf00b-105">Cet procédure indique comment créer des règles de couverture et remplacer des paramètres de couverture pour un article spécifique.</span><span class="sxs-lookup"><span data-stu-id="cf00b-105">This procedure shows how to create coverage rules and override coverage settings for a specific item.</span></span> <span data-ttu-id="cf00b-106">Il indique également comment spécifier les paramètres de stock par défaut.</span><span class="sxs-lookup"><span data-stu-id="cf00b-106">It also shows how to specify default inventory settings.</span></span>


## <a name="create-a-coverage-group"></a><span data-ttu-id="cf00b-107">Créer un groupe de couverture</span><span class="sxs-lookup"><span data-stu-id="cf00b-107">Create a coverage group</span></span>
1. <span data-ttu-id="cf00b-108">Allez dans Groupes de couverture.</span><span class="sxs-lookup"><span data-stu-id="cf00b-108">Go to Coverage groups.</span></span>
2. <span data-ttu-id="cf00b-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="cf00b-109">Click New.</span></span>
3. <span data-ttu-id="cf00b-110">Dans le champ Groupe de couverture, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="cf00b-110">In the Coverage group field, type a value.</span></span>
4. <span data-ttu-id="cf00b-111">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="cf00b-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="cf00b-112">Dans le champ Calendrier, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="cf00b-112">In the Calendar field, type a value.</span></span>
    * <span data-ttu-id="cf00b-113">Choisissez le calendrier que la planification utilise pour créer des suggestions de réapprovisionnement pour les articles de ce groupe.</span><span class="sxs-lookup"><span data-stu-id="cf00b-113">Choose the calendar that master planning uses to create replenishment suggestions for items in this group.</span></span>  
6. <span data-ttu-id="cf00b-114">Dans le champ Code couverture, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="cf00b-114">In the Coverage code field, select an option.</span></span>
    * <span data-ttu-id="cf00b-115">Sélectionnez Conditions requises pour cette procédure.</span><span class="sxs-lookup"><span data-stu-id="cf00b-115">Select Requirement for this procedure.</span></span>  
7. <span data-ttu-id="cf00b-116">Entrez 90 dans le champ Plage de gestion de la couverture (jours).</span><span class="sxs-lookup"><span data-stu-id="cf00b-116">In the Coverage time fence (days) field, enter '90'.</span></span>
    * <span data-ttu-id="cf00b-117">Pour les articles de ce groupe, la planification crée des suggestions de réapprovisionnement jusqu'à 90 jours dans le futur.</span><span class="sxs-lookup"><span data-stu-id="cf00b-117">For items in this group, master planning will create replenishment suggestions for up to 90 days in the future.</span></span>  
8. <span data-ttu-id="cf00b-118">Entrez 1 dans le champ Jours négatifs.</span><span class="sxs-lookup"><span data-stu-id="cf00b-118">In the Negative days field, enter '1'.</span></span>
9. <span data-ttu-id="cf00b-119">Entrez 1 dans le champ Jours positifs.</span><span class="sxs-lookup"><span data-stu-id="cf00b-119">In the Positive days field, enter '1'.</span></span>
10. <span data-ttu-id="cf00b-120">Développez ou réduisez la section Autre.</span><span class="sxs-lookup"><span data-stu-id="cf00b-120">Expand or collapse the Other section.</span></span>
11. <span data-ttu-id="cf00b-121">Entrez 1 dans le champ Marge de réception ajoutée à la date de besoin.</span><span class="sxs-lookup"><span data-stu-id="cf00b-121">In the Receipt margin added to requirement date field, enter '1'.</span></span>
    * <span data-ttu-id="cf00b-122">Par exemple, si la marge de réception est définie sur une journée et si une ligne de commande fournisseur est prévue pour réception le 15 mai, la planification calcule le 16 mai comme date de réception ajustée.</span><span class="sxs-lookup"><span data-stu-id="cf00b-122">For example, if the receipt margin is set to 1 day, and a purchase order line is scheduled for receipt on May 15, master planning calculates the adjusted receipt date as May 16.</span></span>  
12. <span data-ttu-id="cf00b-123">Entrez 1 dans le champ Marge de sortie déduite de la date de besoin.</span><span class="sxs-lookup"><span data-stu-id="cf00b-123">In the Issue margin deducted from requirement date field, enter '1'.</span></span>
    * <span data-ttu-id="cf00b-124">Par exemple, si la marge de sécurité est définie sur une journée et si une ligne de commande client est prévue pour livraison le 15 mai, la planification calcule le 14 mai comme date de livraison ajustée.</span><span class="sxs-lookup"><span data-stu-id="cf00b-124">For example, if the safety margin is set to 1 day, and a sales order line is scheduled for delivery on May 15, master scheduling calculates the adjusted delivery date as May 14.</span></span>  
13. <span data-ttu-id="cf00b-125">Entrez 1 dans le champ Marge de renouvellement ajouté au délai de l'article.</span><span class="sxs-lookup"><span data-stu-id="cf00b-125">In the Reorder margin added to item lead time field, enter '1'.</span></span>
14. <span data-ttu-id="cf00b-126">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="cf00b-126">Click Save.</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="cf00b-127">Créer un nouveau produit</span><span class="sxs-lookup"><span data-stu-id="cf00b-127">Create a new product</span></span>
1. <span data-ttu-id="cf00b-128">Allez dans Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="cf00b-128">Go to Released products.</span></span>
2. <span data-ttu-id="cf00b-129">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="cf00b-129">Click New.</span></span>
3. <span data-ttu-id="cf00b-130">Dans le champ Numéro du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="cf00b-130">In the Product number field, type a value.</span></span>
4. <span data-ttu-id="cf00b-131">Dans le champ Nom du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="cf00b-131">In the Product name field, type a value.</span></span>
5. <span data-ttu-id="cf00b-132">Dans le champ groupe de modèles d'articles, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="cf00b-132">In the Item model group field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="cf00b-133">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="cf00b-133">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="cf00b-134">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cf00b-134">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="cf00b-135">Dans le champ Groupe d'articles, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="cf00b-135">In the Item group field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="cf00b-136">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="cf00b-136">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="cf00b-137">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cf00b-137">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="cf00b-138">Dans le champ Groupe de dimensions de stockage, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="cf00b-138">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="cf00b-139">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="cf00b-139">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="cf00b-140">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cf00b-140">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="cf00b-141">Dans le champ Groupe de dimensions de suivi, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="cf00b-141">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="cf00b-142">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="cf00b-142">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="cf00b-143">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cf00b-143">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="cf00b-144">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cf00b-144">Click OK.</span></span>

## <a name="setup-default-order-settings"></a><span data-ttu-id="cf00b-145">Configurer les paramètres de commande par défaut</span><span class="sxs-lookup"><span data-stu-id="cf00b-145">Setup default order settings</span></span>
1. <span data-ttu-id="cf00b-146">Cliquez sur Planifier dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="cf00b-146">On the Action Pane, click Plan.</span></span>
2. <span data-ttu-id="cf00b-147">Cliquez sur Paramètres de commande par défaut.</span><span class="sxs-lookup"><span data-stu-id="cf00b-147">Click Default order settings.</span></span>
3. <span data-ttu-id="cf00b-148">Dans le champ Site d'achat, tapez le site utilisé comme valeur par défaut lorsque des commandes fournisseur sont créées.</span><span class="sxs-lookup"><span data-stu-id="cf00b-148">In the Purchase site field, type the site used as default when purchase orders are created.</span></span>
4. <span data-ttu-id="cf00b-149">Dans le champ Site de stock, tapez le site de stockage de l'article.</span><span class="sxs-lookup"><span data-stu-id="cf00b-149">In the Inventory site field, type the site where the item is stored.</span></span>
5. <span data-ttu-id="cf00b-150">Développez ou réduisez la section Stock.</span><span class="sxs-lookup"><span data-stu-id="cf00b-150">Expand or collapse the Inventory section.</span></span>
6. <span data-ttu-id="cf00b-151">Définissez Multiple sur 10.</span><span class="sxs-lookup"><span data-stu-id="cf00b-151">Set Multiple to '10'.</span></span>
7. <span data-ttu-id="cf00b-152">Définissez Quantité de commande min.</span><span class="sxs-lookup"><span data-stu-id="cf00b-152">Set Min.</span></span> <span data-ttu-id="cf00b-153">sur 10.</span><span class="sxs-lookup"><span data-stu-id="cf00b-153">order quantity to '10'.</span></span>
8. <span data-ttu-id="cf00b-154">Définissez Quantité de commande max.</span><span class="sxs-lookup"><span data-stu-id="cf00b-154">Set Max.</span></span> <span data-ttu-id="cf00b-155">sur 100.</span><span class="sxs-lookup"><span data-stu-id="cf00b-155">order quantity to '100'.</span></span>
9. <span data-ttu-id="cf00b-156">Définissez Quantité de commande standard sur 10.</span><span class="sxs-lookup"><span data-stu-id="cf00b-156">Set Standard order quantity to '10'.</span></span>
10. <span data-ttu-id="cf00b-157">Entrez un numéro dans le champ Délai d'achat.</span><span class="sxs-lookup"><span data-stu-id="cf00b-157">In the Purchase lead time field, enter a number.</span></span>
11. <span data-ttu-id="cf00b-158">Activez ou désactivez la case à cocher Jours ouvrables.</span><span class="sxs-lookup"><span data-stu-id="cf00b-158">Select or clear the Working days check box.</span></span>
12. <span data-ttu-id="cf00b-159">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="cf00b-159">Click Save.</span></span>
13. <span data-ttu-id="cf00b-160">Sélectionnez « Commande fournisseur » dans le champ Type de commande par défaut.</span><span class="sxs-lookup"><span data-stu-id="cf00b-160">In the Default order type field select 'Purchase order'.</span></span>
14. <span data-ttu-id="cf00b-161">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="cf00b-161">Click Save.</span></span>
15. <span data-ttu-id="cf00b-162">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="cf00b-162">Close the page.</span></span>
    * <span data-ttu-id="cf00b-163">Fermez la page Paramètres de commande par défaut.</span><span class="sxs-lookup"><span data-stu-id="cf00b-163">Close the Default order settings page.</span></span>  

## <a name="add-an-item-to-a-coverage-group"></a><span data-ttu-id="cf00b-164">Ajouter un article à un groupe de couverture</span><span class="sxs-lookup"><span data-stu-id="cf00b-164">Add an item to a coverage group</span></span>
1. <span data-ttu-id="cf00b-165">Développez ou réduisez la section Plan.</span><span class="sxs-lookup"><span data-stu-id="cf00b-165">Expand or collapse the Plan section.</span></span>
2. <span data-ttu-id="cf00b-166">Dans le champ Groupe de couverture, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="cf00b-166">In the Coverage group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="cf00b-167">Dans la liste, recherchez le groupe de couverture créé.</span><span class="sxs-lookup"><span data-stu-id="cf00b-167">In the list, find the Coverage group you have created.</span></span>
4. <span data-ttu-id="cf00b-168">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cf00b-168">In the list, click the link in the selected row.</span></span>

## <a name="create-item-coverage-rules"></a><span data-ttu-id="cf00b-169">Créer des règles de couverture d'article</span><span class="sxs-lookup"><span data-stu-id="cf00b-169">Create item coverage rules</span></span>
1. <span data-ttu-id="cf00b-170">Cliquez sur Planifier dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="cf00b-170">On the Action Pane, click Plan.</span></span>
2. <span data-ttu-id="cf00b-171">Cliquez sur Couverture de l'article.</span><span class="sxs-lookup"><span data-stu-id="cf00b-171">Click Item coverage.</span></span>
3. <span data-ttu-id="cf00b-172">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="cf00b-172">Click New.</span></span>
4. <span data-ttu-id="cf00b-173">Cliquez sur l'onglet Général.</span><span class="sxs-lookup"><span data-stu-id="cf00b-173">Click the General tab.</span></span>
5. <span data-ttu-id="cf00b-174">Activez la case à cocher sous l'en-tête Remplacer les paramètres du groupe de couverture.</span><span class="sxs-lookup"><span data-stu-id="cf00b-174">Check the box on the header of Override coverage group settings.</span></span>
6. <span data-ttu-id="cf00b-175">Entrez 60 dans le champ Plage de gestion de la couverture (jours).</span><span class="sxs-lookup"><span data-stu-id="cf00b-175">In the Coverage time fence (days) field, enter '60'.</span></span>
    * <span data-ttu-id="cf00b-176">Même si des articles du groupe de couverture Besoin sont planifiés à 90 jours dans le futur, cet article sera planifié à 60 jours dans le futur.</span><span class="sxs-lookup"><span data-stu-id="cf00b-176">Although items in coverage group Requirement are planned 90 days ahead, this item will be planned 60 days ahead.</span></span>  
7. <span data-ttu-id="cf00b-177">Entrez 2 dans le champ Jours négatifs.</span><span class="sxs-lookup"><span data-stu-id="cf00b-177">In the Negative days field, enter '2'.</span></span>
8. <span data-ttu-id="cf00b-178">Entrez 2 dans le champ Jours positifs.</span><span class="sxs-lookup"><span data-stu-id="cf00b-178">In the Positive days field, enter '2'.</span></span>
9. <span data-ttu-id="cf00b-179">Cliquez sur l'onglet Délai.</span><span class="sxs-lookup"><span data-stu-id="cf00b-179">Click the Lead time tab.</span></span>
10. <span data-ttu-id="cf00b-180">Activez la case à cocher dans l'en-tête Achat.</span><span class="sxs-lookup"><span data-stu-id="cf00b-180">Check the box on the header of Purchase.</span></span>
11. <span data-ttu-id="cf00b-181">Entrez 5 dans le champ Délai d'achat.</span><span class="sxs-lookup"><span data-stu-id="cf00b-181">In the Purchase time field, enter '5'.</span></span>
12. <span data-ttu-id="cf00b-182">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="cf00b-182">Click Save.</span></span>


