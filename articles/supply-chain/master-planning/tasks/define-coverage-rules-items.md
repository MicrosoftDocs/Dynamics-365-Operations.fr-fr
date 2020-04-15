---
title: Définir des règles de couverture pour les articles
description: Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.
author: ShylaThompson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5ecd56c84b232fd7855bf2fb01eaebe3f3bd4440
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3150284"
---
# <a name="define-coverage-rules-for-items"></a><span data-ttu-id="ce42a-103">Définir des règles de couverture pour les articles</span><span class="sxs-lookup"><span data-stu-id="ce42a-103">Define coverage rules for items</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ce42a-104">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="ce42a-104">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="ce42a-105">Cet procédure indique comment créer des règles de couverture et remplacer des paramètres de couverture pour un article spécifique.</span><span class="sxs-lookup"><span data-stu-id="ce42a-105">This procedure shows how to create coverage rules and override coverage settings for a specific item.</span></span> <span data-ttu-id="ce42a-106">Il indique également comment spécifier les paramètres de stock par défaut.</span><span class="sxs-lookup"><span data-stu-id="ce42a-106">It also shows how to specify default inventory settings.</span></span>


## <a name="create-a-coverage-group"></a><span data-ttu-id="ce42a-107">Créer un groupe de couverture</span><span class="sxs-lookup"><span data-stu-id="ce42a-107">Create a coverage group</span></span>
1. <span data-ttu-id="ce42a-108">Accédez au **Volet de navigation> Modules > Planification > Paramétrage > Groupes de couverture**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-108">Go to **Navigation pane > Modules > Master planning > Setup > Coverage groups**.</span></span>
2. <span data-ttu-id="ce42a-109">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-109">Click **New**.</span></span>
3. <span data-ttu-id="ce42a-110">Dans le champ **Groupe de couverture**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ce42a-110">In the **Coverage group** field, type a value.</span></span>
4. <span data-ttu-id="ce42a-111">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="ce42a-112">Dans le champ **Calendrier**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ce42a-112">In the **Calendar** field, type a value.</span></span> <span data-ttu-id="ce42a-113">Choisissez le calendrier que la planification utilise pour créer des suggestions de réapprovisionnement pour les articles de ce groupe.</span><span class="sxs-lookup"><span data-stu-id="ce42a-113">Choose the calendar that master planning uses to create replenishment suggestions for items in this group.</span></span>  
6. <span data-ttu-id="ce42a-114">Dans le champ **Code couverture**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="ce42a-114">In the **Coverage code** field, select an option.</span></span> <span data-ttu-id="ce42a-115">Sélectionnez « Conditions requises » pour cette procédure.</span><span class="sxs-lookup"><span data-stu-id="ce42a-115">Select 'Requirement' for this procedure.</span></span>  
7. <span data-ttu-id="ce42a-116">Entrez « 90 » dans le champ **Plage de gestion de la couverture (jours)**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-116">In the **Coverage time fence (days) field**, enter '90'.</span></span> <span data-ttu-id="ce42a-117">Pour les articles de ce groupe, la planification crée des suggestions de réapprovisionnement jusqu'à 90 jours dans le futur.</span><span class="sxs-lookup"><span data-stu-id="ce42a-117">For items in this group, master planning will create replenishment suggestions for up to 90 days in the future.</span></span>  
8. <span data-ttu-id="ce42a-118">Entrez 1 dans le champ **Jours négatifs**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-118">In the **Negative days** field, enter '1'.</span></span>
9. <span data-ttu-id="ce42a-119">Entrez 1 dans le champ **Jours positifs**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-119">In the **Positive days** field, enter '1'.</span></span>
10. <span data-ttu-id="ce42a-120">Développez ou réduisez la section **Autre**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-120">Expand or collapse the **Other** section.</span></span>
11. <span data-ttu-id="ce42a-121">Sous la section **Marges de sécurité en jours**, dans le champ **Marge de réception ajoutée à la date de besoin**, entrez « 1 ».</span><span class="sxs-lookup"><span data-stu-id="ce42a-121">Under the **Safety margins in days** section, in the **Receipt margin added to requirement date** field, enter '1'.</span></span> <span data-ttu-id="ce42a-122">Par exemple, si la marge de réception est définie sur une journée et si une ligne de commande fournisseur est prévue pour réception le 15 mai, la planification calcule le 16 mai comme date de réception ajustée.</span><span class="sxs-lookup"><span data-stu-id="ce42a-122">For example, if the receipt margin is set to 1 day, and a purchase order line is scheduled for receipt on May 15, master planning calculates the adjusted receipt date as May 16.</span></span>  
12. <span data-ttu-id="ce42a-123">Entrez « 1 » dans le champ **Marge de sortie déduite de la date de besoin**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-123">In the **Issue margin deducted from requirement date** field, enter '1'.</span></span> <span data-ttu-id="ce42a-124">Par exemple, si la marge de sécurité est définie sur une journée et si une ligne de commande client est prévue pour livraison le 15 mai, la planification calcule le 14 mai comme date de livraison ajustée.</span><span class="sxs-lookup"><span data-stu-id="ce42a-124">For example, if the safety margin is set to 1 day, and a sales order line is scheduled for delivery on May 15, master scheduling calculates the adjusted delivery date as May 14.</span></span>  
13. <span data-ttu-id="ce42a-125">Entrez « 1 » dans le champ **Marge de renouvellement ajouté au délai de l'article**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-125">In the **Reorder margin added to item lead time** field, enter '1'.</span></span>
14. <span data-ttu-id="ce42a-126">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-126">Click **Save**.</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="ce42a-127">Créer un nouveau produit</span><span class="sxs-lookup"><span data-stu-id="ce42a-127">Create a new product</span></span>
1. <span data-ttu-id="ce42a-128">Accédez à **Volet de navigation > Modules > Gestion d'informations sur les produits > Produits > Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-128">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="ce42a-129">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-129">Click **New**.</span></span>
3. <span data-ttu-id="ce42a-130">Dans le champ **Numéro du produit**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ce42a-130">In the **Product number** field, type a value.</span></span>
4. <span data-ttu-id="ce42a-131">Dans le champ **Nom du produit**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ce42a-131">In the **Product name** field, type a value.</span></span>
5. <span data-ttu-id="ce42a-132">Dans le champ **Groupe de modèles d'articles**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ce42a-132">In the **Item model group** field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="ce42a-133">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="ce42a-133">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="ce42a-134">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ce42a-134">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="ce42a-135">Dans le champ **Groupe d'articles**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ce42a-135">In the **Item group** field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="ce42a-136">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="ce42a-136">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="ce42a-137">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ce42a-137">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="ce42a-138">Dans le champ **Groupe de dimensions de stockage**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ce42a-138">In the **Storage dimension group** field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="ce42a-139">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="ce42a-139">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="ce42a-140">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ce42a-140">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="ce42a-141">Dans le champ **Groupe de dimensions de suivi**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ce42a-141">In the **Tracking dimension group** field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="ce42a-142">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="ce42a-142">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="ce42a-143">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ce42a-143">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="ce42a-144">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-144">Click **OK**.</span></span>

## <a name="setup-default-order-settings"></a><span data-ttu-id="ce42a-145">Configurer les paramètres de commande par défaut</span><span class="sxs-lookup"><span data-stu-id="ce42a-145">Setup default order settings</span></span>
1. <span data-ttu-id="ce42a-146">Dans le **volet Action**, cliquez sur **Plan**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-146">On the **Action Pane**, click **Plan**.</span></span>
2. <span data-ttu-id="ce42a-147">Sous **Paramètres de la commande**, cliquez sur **Paramètres de commande par défaut**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-147">Under **Order settings**, click **Default order settings**.</span></span>
3. <span data-ttu-id="ce42a-148">Sous **Commande fournisseur**, dans le champ **Site par défaut**, tapez le site utilisé comme valeur par défaut lorsque des commandes fournisseur sont créées.</span><span class="sxs-lookup"><span data-stu-id="ce42a-148">Under **Purchase order**, in the **Default site** field, type the site used as default when purchase orders are created.</span></span>
4. <span data-ttu-id="ce42a-149">Dans le champ **Entrepôt par défaut**, tapez le site de stockage de l'article.</span><span class="sxs-lookup"><span data-stu-id="ce42a-149">In the **Default warehouse** field, type the site where the item is stored.</span></span>
5. <span data-ttu-id="ce42a-150">Développez ou réduisez la section **Stock**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-150">Expand or collapse the **Inventory** section.</span></span>
6. <span data-ttu-id="ce42a-151">Dans le champ **Multiple**, saisissez « 10 ».</span><span class="sxs-lookup"><span data-stu-id="ce42a-151">In the **Multiple** field, type '10'.</span></span>
7. <span data-ttu-id="ce42a-152">Dans le champ **Quantité de commande min.**, saisissez « 10 ».</span><span class="sxs-lookup"><span data-stu-id="ce42a-152">In the **Min. order quantity** field, type '10'.</span></span>
8. <span data-ttu-id="ce42a-153">Dans le champ **Quantité de commande max.**, saisissez « 100 ».</span><span class="sxs-lookup"><span data-stu-id="ce42a-153">In the **Max. order quantity** field, type '100'.</span></span>
9. <span data-ttu-id="ce42a-154">Dans le champ **Quantité de commande standard**, saisissez « 10 ».</span><span class="sxs-lookup"><span data-stu-id="ce42a-154">In the **Standard order quantity**, type '10'.</span></span>
10. <span data-ttu-id="ce42a-155">Entrez un numéro dans le champ **Délai d'achat**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-155">In the **Purchase lead time** field, enter a number.</span></span>
11. <span data-ttu-id="ce42a-156">Activez ou désactivez la case à cocher **Jours ouvrables**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-156">Select or clear the **Working days** check box.</span></span>
12. <span data-ttu-id="ce42a-157">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-157">Click **Save**.</span></span>
13. <span data-ttu-id="ce42a-158">Dans le champ **Type de commande par défaut**, sélectionnez « Commande fournisseur ».</span><span class="sxs-lookup"><span data-stu-id="ce42a-158">In the **Default order type** field select 'Purchase order'.</span></span>
14. <span data-ttu-id="ce42a-159">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-159">Click **Save**.</span></span>
15. <span data-ttu-id="ce42a-160">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ce42a-160">Close the page.</span></span> <span data-ttu-id="ce42a-161">Fermez la page Paramètres de commande par défaut.</span><span class="sxs-lookup"><span data-stu-id="ce42a-161">Close the Default order settings page.</span></span>  

## <a name="add-an-item-to-a-coverage-group"></a><span data-ttu-id="ce42a-162">Ajouter un article à un groupe de couverture</span><span class="sxs-lookup"><span data-stu-id="ce42a-162">Add an item to a coverage group</span></span>
1. <span data-ttu-id="ce42a-163">Développez ou réduisez la section **Plan**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-163">Expand or collapse the **Plan** section.</span></span>
2. <span data-ttu-id="ce42a-164">Dans le champ **Groupe de couverture**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ce42a-164">In the **Coverage group** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="ce42a-165">Dans la liste, recherchez le **groupe de couverture** créé.</span><span class="sxs-lookup"><span data-stu-id="ce42a-165">In the list, find the **Coverage group** you have created.</span></span>
4. <span data-ttu-id="ce42a-166">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ce42a-166">In the list, click the link in the selected row.</span></span>

## <a name="create-item-coverage-rules"></a><span data-ttu-id="ce42a-167">Créer des règles de couverture d'article</span><span class="sxs-lookup"><span data-stu-id="ce42a-167">Create item coverage rules</span></span>
1. <span data-ttu-id="ce42a-168">Dans le **volet Action**, cliquez sur **Plan**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-168">On the **Action Pane**, click **Plan**.</span></span>
2. <span data-ttu-id="ce42a-169">Sous **Couverture**, cliquez sur **Couverture de l'article**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-169">Under **Coverage**, click **Item coverage**.</span></span>
3. <span data-ttu-id="ce42a-170">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-170">Click **New**.</span></span>
4. <span data-ttu-id="ce42a-171">Cliquez sur l'onglet **Général**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-171">Click the **General** tab.</span></span>
5. <span data-ttu-id="ce42a-172">Activez la case à cocher sous l'en-tête **Remplacer les paramètres du groupe de couverture**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-172">Check the box on the header of **Override coverage group** settings.</span></span>
6. <span data-ttu-id="ce42a-173">Entrez « 60 » dans le champ **Plage de gestion de la couverture (jours)**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-173">In the **Coverage time fence (days)** field, enter '60'.</span></span> <span data-ttu-id="ce42a-174">Même si des articles du groupe de couverture Besoin sont planifiés à 90 jours dans le futur, cet article sera planifié à 60 jours dans le futur.</span><span class="sxs-lookup"><span data-stu-id="ce42a-174">Although items in coverage group Requiremen are planned 90 days ahead, this item will be planned 60 days ahead.</span></span>  
7. <span data-ttu-id="ce42a-175">Entrez 2 dans le champ **Jours négatifs**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-175">In the **Negative days** field, enter '2'.</span></span>
8. <span data-ttu-id="ce42a-176">Entrez 2 dans le champ **Jours positifs**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-176">In the **Positive days** field, enter '2'.</span></span>
9. <span data-ttu-id="ce42a-177">Cliquez sur l'onglet **Délai**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-177">Click the **Lead time** tab.</span></span>
10. <span data-ttu-id="ce42a-178">Activez la case à cocher dans l'en-tête **Achat**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-178">Check the box on the header of **Purchase**.</span></span>
11. <span data-ttu-id="ce42a-179">Entrez « 5 » dans le champ **Délai d'achat**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-179">In the **Purchase time** field, enter '5'.</span></span>
12. <span data-ttu-id="ce42a-180">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ce42a-180">Click **Save**.</span></span>

