---
title: Sous-traitance
description: "Cette rubrique vous aide à créer une procédure de sous-traitance de la fabrication dans Microsoft Dynamics 365 for Finance and Operations."
author: christophernread
manager: AnnBe
ms.date: 09/28/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: 
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: ade3f4ad9878c9e885afc5034334e41897512871
ms.openlocfilehash: 55b516f928eadea9b7ddbb1192db79f3ab7fa204
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2018

---

# <a name="subcontracting"></a><span data-ttu-id="5f4b6-103">Sous-traitance</span><span class="sxs-lookup"><span data-stu-id="5f4b6-103">Subcontracting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5f4b6-104">Cette rubrique vous aide à créer une procédure de sous-traitance de la fabrication dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-104">This topic will help you build a walkthrough of subcontracting in manufacturing in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="5f4b6-105">La première partie de cette rubrique décrit le paramétrage des données.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-105">The first part of this topic describes the setup of the data.</span></span> <span data-ttu-id="5f4b6-106">La deuxième partie vous explique les étapes de la procédure.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-106">The second part takes you through the steps in the walkthrough.</span></span>

## <a name="target-audience"></a><span data-ttu-id="5f4b6-107">Public cible</span><span class="sxs-lookup"><span data-stu-id="5f4b6-107">Target audience</span></span>

<span data-ttu-id="5f4b6-108">Dans cette rubrique, vous apprendrez comment paramétrer la sous-traitance de la fabrication.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-108">In this topic, you will learn how to set up subcontracting in manufacturing.</span></span> <span data-ttu-id="5f4b6-109">Vous utiliserez les données existantes dans l'entité juridique HQUS pour effectuer le paramétrage de base d'un flux d'activités de sous-traitance.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-109">You will use existing data in the HQUS legal entity to do the basic setup of a subcontracting activity flow.</span></span> <span data-ttu-id="5f4b6-110">Les données de démonstration de l'entité juridique HQUS comprennent des paramètres de configuration qui ont été prédéfinis pour prendre en charge les étapes de la procédure.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-110">The demo data in the HQUS legal entity includes setup parameters that have been preset to support the steps in the walkthrough.</span></span> <span data-ttu-id="5f4b6-111">Même si la procédure traite des principaux points sensibles et défis pour divers rôles, elle peut être effectuée par l'administrateur du système.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-111">Even though the walkthrough addresses key pain points and challenges for various roles, it can be completed by the system admin.</span></span>

## <a name="demo-scenario"></a><span data-ttu-id="5f4b6-112">Scénario de démonstration</span><span class="sxs-lookup"><span data-stu-id="5f4b6-112">Demo scenario</span></span>

<span data-ttu-id="5f4b6-113">Dans l'entité juridique HQUS, des haut-parleurs haut de gamme sont fabriqués.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-113">In the HQUS legal entity, high-end speakers are manufactured.</span></span> <span data-ttu-id="5f4b6-114">Au cours du processus de fabrication, les haut-parleurs passent par les trois opérations suivantes.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-114">During the manufacturing process, speakers go through the following three operations.</span></span>

- <span data-ttu-id="5f4b6-115">**Préassemblage** – L'enceinte est assemblée.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-115">**Pre-assembly** – The speaker cabinet is assembled.</span></span> <span data-ttu-id="5f4b6-116">Le matériel pour l'enceinte est prélevé dans l'entrepôt de matières premières avant le démarrage de l'opération.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-116">The material for the cabinet is picked in the material warehouse before the operation is started.</span></span>
- <span data-ttu-id="5f4b6-117">**Revêtement** – Une fois que l'enceinte a été assemblée, elle doit être recouverte.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-117">**Coating** – After the speaker cabinet has been assembled, it must be coated.</span></span> <span data-ttu-id="5f4b6-118">Cette opération est effectuée par un fournisseur (sous-traitant).</span><span class="sxs-lookup"><span data-stu-id="5f4b6-118">This operation is completed by a vendor (subcontractor).</span></span> <span data-ttu-id="5f4b6-119">L'enceinte préassemblée est expédiée au sous-traitant en revêtement avec deux matières.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-119">The pre-assembled speaker cabinet is shipped to the coating subcontractor together with two materials.</span></span>
- <span data-ttu-id="5f4b6-120">**Finition** – Une fois que l'enceinte préassemblée a été recouverte par le sous-traitant, elle est renvoyée à l'entité juridique HQUS afin que l'assemblage final du haut-parleur puisse être terminé.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-120">**Finish** – After the pre-assembled speaker cabinet has been coated by the subcontractor, it's returned to the HQUS legal entity so that final assembly of the speaker can be completed.</span></span>

<span data-ttu-id="5f4b6-121">L'illustration suivante présente les trois opérations et les matières utilisées.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-121">The following illustration shows the three operations and the materials that they consume.</span></span>

![Opérations de préassemblage, de revêtement et de finition et matières utilisées](./media/subcontract01_operations-materials.png)

## <a name="setup"></a><span data-ttu-id="5f4b6-123">Configuration</span><span class="sxs-lookup"><span data-stu-id="5f4b6-123">Setup</span></span>

<span data-ttu-id="5f4b6-124">Avant de commencer la procédure, vous devez paramétrer les données.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-124">Before you start the walkthrough, you must set up the data.</span></span>

### <a name="set-up-the-finished-product"></a><span data-ttu-id="5f4b6-125">Paramétrer le produit fini</span><span class="sxs-lookup"><span data-stu-id="5f4b6-125">Set up the finished product</span></span>

<span data-ttu-id="5f4b6-126">Cette procédure vous guide dans le paramétrage du produit lancé D8100, « Enceinte avec revêtement ».</span><span class="sxs-lookup"><span data-stu-id="5f4b6-126">This procedure takes you through the setup of released product D8100, "Coated Cabinet."</span></span>

1. <span data-ttu-id="5f4b6-127">Sélectionnez **Gestion des informations sur les produits \> Produits \> Produits lancés** pour ouvrir la page **Détails des produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-127">Select **Product information management \> Products \> Released products** to open the **Released product details** page.</span></span>
2. <span data-ttu-id="5f4b6-128">Dans le champ de filtre rapide, entrez **D8100** pour rechercher le produit lancé existant.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-128">In the quick filter field, enter **D8100** to find the existing released product.</span></span>

    ![Filtrage du produit lancé D8100 dans la page Détails des produits lancés](./media/subcontract02_filtering-released-products.png)

3. <span data-ttu-id="5f4b6-130">Dans le volet Actions, sous l'onglet **Ingérieur**, sélectionnez **Gamme** pour ouvrir la page **Gamme**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-130">On the Action Pane, on the **Engineer** tab, select **Route** to open the **Route** page.</span></span>

    <span data-ttu-id="5f4b6-131">La page **Gamme** affiche les huit versions de gamme pour le produit lancé D8100.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-131">The **Route** page shows the eight route versions for released product D8100.</span></span> <span data-ttu-id="5f4b6-132">Les huit versions de gamme sont réparties sur quatre gammes dans le site 1 et le site 5.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-132">The eight route versions are divided among four routes on site 1 and site 5.</span></span> <span data-ttu-id="5f4b6-133">La gamme 000400 est utilisée pour l'évaluation des coûts, la gamme 00041 est utilisée lorsque l'opération de revêtement est une opération interne et la gamme 00042 est utilisée lorsque l'opération de revêtement est une opération externe.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-133">Route 000400 is used for costing, route 00041 is used when the Coating operation is an internal operation, and route 00042 is used when the Coating operation is an external operation.</span></span>

    ![Huit versions de gamme dans la page Gamme](./media/subcontract03_route-page.png)

4. <span data-ttu-id="5f4b6-135">Dans le volet supérieur, dans la grille **Versions**, sélectionnez la version de gamme **00042** pour le site **5**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-135">In the upper pane, in the **Versions** grid, select route version **00042** for site **5**.</span></span>
5. <span data-ttu-id="5f4b6-136">Dans le volet inférieur, sous l'onglet **Vue d'ensemble**, sélectionnez l'opération **20** (**Cbnt CtSc**) dans la grille.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-136">In the lower pane, on the **Overview** tab, select operation **20** (**Cbnt CtSc**) in the grid.</span></span>

    ![Opération 20 pour la version de gamme 00042 pour le site 5 sélectionné](./media/subcontract04_route-version-operation.png)

6. <span data-ttu-id="5f4b6-138">Sélectionnez l'onglet **Général**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-138">Select the **General** tab.</span></span>

    <span data-ttu-id="5f4b6-139">Notez que le champ **Type de gamme** est défini sur **Fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-139">Notice that the field **Route type** field is set to **Vendor**.</span></span> <span data-ttu-id="5f4b6-140">Cette valeur indique que l'opération 20 (Cbnt CtSc) est une opération sous-traitée.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-140">This value indicates that operation 20 (Cbnt CtSc) is a subcontracted operation.</span></span>

    ![Champ Type de gamme défini sur Fournisseur dans l'onglet Général](./media/subcontract05_general-tab.png)

7. <span data-ttu-id="5f4b6-142">Sélectionnez l'onglet **Demandes de ressources**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-142">Select the **Resource requirements** tab.</span></span>

    <span data-ttu-id="5f4b6-143">Les fonctionnalités seront utilisées pour trouver une ressource applicable lors de la planification de la production.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-143">Capabilities will be used to find an applicable resource during production scheduling.</span></span> <span data-ttu-id="5f4b6-144">Pour l'opération 20 (Cbnt CtSc), notez qu'une ressource avec deux fonctionnalités, **Revêtement** et **Enceintes avec revêtement**, est requise.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-144">For operation 20 (Cbnt CtSc), notice that a resource that has two capabilities, **Coating** and **Coated cabinets**, is required.</span></span>

    ![Fonctionnalités Revêtement et Enceintes avec revêtement dans l'onglet Demandes de ressources](./media/subcontract06_resource-requirements-tab.png)

8. <span data-ttu-id="5f4b6-146">Sélectionnez **Ressources applicables** pour ouvrir la boîte de dialogue **Ressources applicables**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-146">Select **Applicable resources** to open the **Applicable resources** dialog box.</span></span>

    <span data-ttu-id="5f4b6-147">Trois ressources correspondent aux demandes de ressources pour l'opération.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-147">Three resources are found that match the resource requirements for the operation.</span></span> <span data-ttu-id="5f4b6-148">Notez que les ressources 8851 et 8852 sont de type **Fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-148">Notice that resources 8851 and 8852 are of the **Vendor** type.</span></span>

    ![Trois ressources appropriées dans la boîte de dialogue Ressources applicables](./media/subcontract07_applicable-resources-dialog.png)

9. <span data-ttu-id="5f4b6-150">Cliquez sur **OK** pour fermer la boîte de dialogue **Ressources applicables** et revenir à la page **Gamme**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-150">Select **OK** to close the **Applicable resources** dialog box and return to the **Route** page.</span></span>
10. <span data-ttu-id="5f4b6-151">Fermez la page **Gamme** pour revenir à la page **Détails des produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-151">Close the **Route** page to return to the **Released product details** page.</span></span>

    ![Page Détails des produits lancés](./media/subcontract08_released-product-details-page.png)

11. <span data-ttu-id="5f4b6-153">Dans le volet Actions, sous l'onglet **Ingérieur**, sélectionnez **Versions de nomenclature** pour ouvrir la page **Versions de nomenclature**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-153">On the Action Pane, on the **Engineer** tab, select **BOM versions** to open the **BOM versions** page.</span></span>

    <span data-ttu-id="5f4b6-154">La page **Versions de nomenclature** affiche les quatre versions de nomenclature pour le produit lancé D8100.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-154">The **BOM versions** page shows the four bill of materials (BOM) versions for released product D8100.</span></span> <span data-ttu-id="5f4b6-155">La nomenclature 000040 est utilisée pour l'évaluation des coûts et la planification, la nomenclature 000041 est utilisée si l'opération de revêtement est effectuée en interne et les nomenclatures 000042 et 000043 sont utilisées si l'opération de revêtement est sous-traitée.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-155">BOM 000040 is used for costing and planning, BOM 000041 is used if the Coating operation is done in-house, and BOMs 000042 and 000043 are used if the Coating operation is subcontracted.</span></span>

    <span data-ttu-id="5f4b6-156">Notez que l'article S8050 est un produit du type d'article **Service**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-156">Notice that item S8050 is a product of the **Service** item type.</span></span> <span data-ttu-id="5f4b6-157">Cet article représente le travail sous-traité.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-157">This item represents the subcontracted work.</span></span>

    ![Quatre versions de nomenclature dans la page Versions de nomenclature](./media/subcontract09_bom-versions-page.png)

12. <span data-ttu-id="5f4b6-159">Dans l'organisateur **Lignes de nomenclature**, sélectionnez **Modifier** pour ouvrir la boîte de dialogue **Modifier une ligne de nomenclature**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-159">On the **Bill of materials lines** FastTab, select **Edit** to open the **Edit BOM line** dialog box.</span></span>

    <span data-ttu-id="5f4b6-160">Lorsqu'un ordre de fabrication est créé et estimé pour le produit lancé D8100, une commande fournisseur est automatiquement générée pour l'article S8050.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-160">When a production order is created and estimated for released product D8100, a purchase order will be automatically generated for item S8050.</span></span> <span data-ttu-id="5f4b6-161">Cette commande fournisseur sera associée à l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-161">This purchase order will be linked to the production order.</span></span> <span data-ttu-id="5f4b6-162">Pour que les commandes fournisseur soient automatiquement générées, le champ **Type de ligne** doit être défini sur **Fournisseur**, et le compte fournisseur du sous-traitant doit être sélectionné.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-162">For purchase orders to be automatically generated, the **Line type** field must be set to **Vendor**, and the vendor account for the subcontractor must be selected.</span></span> <span data-ttu-id="5f4b6-163">Dans ce cas, le compte fournisseur est US-801.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-163">In this case, the vendor account is US-801.</span></span>

    <span data-ttu-id="5f4b6-164">Notez que la ligne de nomenclature est associée à l'opération de revêtement par le biais du numéro d'opération (dans ce cas, 20).</span><span class="sxs-lookup"><span data-stu-id="5f4b6-164">Notice that the BOM line is connected to the Coating operation through the operation number (in this case, 20).</span></span>

    ![Boîte de dialogue Modifier une ligne de nomenclature](./media/subcontract10_edit-bom-line-dialog.png)

### <a name="create-a-password-for-warehouse-workers"></a><span data-ttu-id="5f4b6-166">Créer un mot de passe pour les magasiniers</span><span class="sxs-lookup"><span data-stu-id="5f4b6-166">Create a password for warehouse workers</span></span>

<span data-ttu-id="5f4b6-167">Vous devez définir un mot de passe pour les magasiniers qui utilisent l'appareil portable.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-167">You must define a password for the warehouse workers who use the hand-held device.</span></span>

1. <span data-ttu-id="5f4b6-168">Sélectionnez **Gestion des entrepôts \> Paramétrage \> Collaborateur** pour ouvrir la page **Utilisateurs du travail**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-168">Select **Warehouse management \> Setup \> Worker** to open the **Work users** page.</span></span>
2. <span data-ttu-id="5f4b6-169">Dans l'organisateur **Utilisateurs**, sélectionnez la ligne de l'utilisateur **51**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-169">On the **Users** FastTab, select the row for user **51**.</span></span>

    ![Page Utilisateurs du travail](./media/subcontract11_work-users-page.png)

3. <span data-ttu-id="5f4b6-171">Sélectionnez **Réinitialiser le mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-171">Select **Reset password**.</span></span>
4. <span data-ttu-id="5f4b6-172">Dans les champs **Mot de passe** et **Confirmer le mot de passe**, entrez **1**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-172">In the **Password** and **Confirm password** fields, enter **1**.</span></span>
5. <span data-ttu-id="5f4b6-173">Sélectionnez **Définir le mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-173">Select **Set password**.</span></span>

## <a name="step-by-step-walkthrough"></a><span data-ttu-id="5f4b6-174">Procédure pas-à-pas</span><span class="sxs-lookup"><span data-stu-id="5f4b6-174">Step-by-step walkthrough</span></span>

<span data-ttu-id="5f4b6-175">**Scénario et arrière-plan**</span><span class="sxs-lookup"><span data-stu-id="5f4b6-175">**Scenario and background**</span></span>

<span data-ttu-id="5f4b6-176">Un ordre de fabrication de 10 pièces est créé pour le produit D8100, « Enceinte avec revêtement ».</span><span class="sxs-lookup"><span data-stu-id="5f4b6-176">A production order of 10 pieces is created for product D8100, "Coated Cabinet."</span></span> <span data-ttu-id="5f4b6-177">Le revêtement des enceintes est une opération sous-traitée qui est réalisée par le fournisseur US-801, Perfect Coating Solutions.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-177">The coating of the cabinets is a sub-contracted operation that is done at vendor US-801, Perfect Coating Solutions.</span></span> <span data-ttu-id="5f4b6-178">L'ordre de fabrication est composée de trois opérations.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-178">The production order consists of three operations.</span></span> <span data-ttu-id="5f4b6-179">Dans la première opération, l'enceinte est préassemblée comme une opération interne.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-179">In the first operation, the cabinet is pre-assembled as an in-house operation.</span></span> <span data-ttu-id="5f4b6-180">Le matériel de préassemblage est lancé pour prélèvement dans l'entrepôt de matières premières.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-180">The material for the pre-assembly is released for picking in the raw material warehouse.</span></span> <span data-ttu-id="5f4b6-181">Une fois le préassemblage terminé, l'enceinte préassemblée est envoyée à Perfect Coating Solutions avec deux matières requises pour l'opération de revêtement.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-181">After the pre-assembly is completed, the pre-assembled cabinet is sent to Perfect Coating Solutions together with two materials that are required for the Coating operation.</span></span> <span data-ttu-id="5f4b6-182">Lorsque l'enceinte avec revêtement est renvoyée par le fournisseur, elle passe par une opération d'assemblage interne finale avant d'être déclarée comme terminée.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-182">When the coated cabinet is received back from the vendor, it goes through a final in-house assembly operation before it's reported as finished.</span></span>

1. <span data-ttu-id="5f4b6-183">Sélectionnez **Contrôle de la production \> Ordres de fabrication \> Tous les ordres de fabrication** pour ouvrir la page **Tous les ordres de fabrication**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-183">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
2. <span data-ttu-id="5f4b6-184">Dans le volet Actions, sélectionnez **Nouvel ordre de fabrication** pour ouvrir la boîte de dialogue **Créer un ordre de fabrication**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-184">On the Action Pane, select **New production order** to open the **Create production order** dialog box.</span></span>

    ![Boîte de dialogue Crée un ordre de fabrication](./media/subcontract12_create-production-order-dialog.png)

3. <span data-ttu-id="5f4b6-186">Dans le champ **Numéro d'article**, sélectionnez **D8100**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-186">In the **Item number** field, select **D8100**.</span></span>
4. <span data-ttu-id="5f4b6-187">Une fois le numéro d'article sélectionné, les champs de la dimension de stock s'affichent.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-187">After you select the item number, fields for the inventory dimensions appear.</span></span> <span data-ttu-id="5f4b6-188">Dans le champ **Couleur**, sélectionnez **Chrome**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-188">In the **Color** field, select **Chrome**.</span></span>

    <span data-ttu-id="5f4b6-189">Une zone de message apparaît pour vous demander si les versions actives de la nomenclature et de la gamme doivent être insérées.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-189">A message box appears that asks whether the active versions for the BOM and route should be inserted.</span></span>

    ![Zone de message](./media/subcontract13_message-box.png)

5. <span data-ttu-id="5f4b6-191">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-191">Select **Yes**.</span></span> 

    <span data-ttu-id="5f4b6-192">Dans la boîte de dialogue **Créer un ordre de fabrication**, les versions actives de la nomenclature et de la gamme du produit D8100 sont automatiquement sélectionnées dans les champs **Numéro de nomenclature** et **Numéro de gamme**, respectivement.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-192">In the **Create production order** dialog box, the active versions of the BOM and route for product D8100 are automatically selected in the **BOM number** and **Route number** fields, respectively.</span></span> <span data-ttu-id="5f4b6-193">Dans ce cas, la nomenclature **000040** et la gamme **000040** sont sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-193">In this case, BOM **000040** and route **000040** are selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5f4b6-194">Pour la nomenclature et la gamme, la version 000040 est utilisée pour l'évaluation des coûts et la planification.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-194">For both the BOM and the route, version 000040 is used for costing and planning.</span></span>

6. <span data-ttu-id="5f4b6-195">Dans le champ **Site**, sélectionnez **5**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-195">In the **Site** field, select **5**.</span></span>
7. <span data-ttu-id="5f4b6-196">Dans le champ **Entrepôt**, sélectionnez **51**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-196">In the **Warehouse** field, select **51**.</span></span>
8. <span data-ttu-id="5f4b6-197">Dans les champs **Numéro de nomenclature** et **Numéro de gamme**, remplacez la valeur qui a été automatiquement sélectionnée par **000042**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-197">In the **BOM number** and **Route number** fields, change the value that was automatically selected to **000042**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5f4b6-198">Pour la nomenclature et la gamme, la version 000042 est utilisée pour sous-traiter le revêtement de l'enceinte au fournisseur US-801.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-198">For both the BOM and the route, version 000042 is used to subcontract the coating of the cabinet to vendor US-801.</span></span>

    ![Valeurs définies dans la boîte de dialogue Créer un ordre de fabrication](./media/subcontract14_create-production-order-dialog-set.png)

9. <span data-ttu-id="5f4b6-200">Sélectionnez **Créer** pour créer l'ordre de fabrication et revenir à la page **Tous les ordres de fabrication**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-200">Select **Create** to create the production order and return to the **All production orders** page.</span></span>

    ![Nouvel ordre de fabrication dans la page Tous les ordres de fabrication](./media/subcontract15_new-production-order.png)

10. <span data-ttu-id="5f4b6-202">Dans le volet Actions, sous l'onglet **Ordre de fabrication**, sélectionnez **Estimation** pour ouvrir la boîte de dialogue **Estimation**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-202">On the Action Pane, on the **Production order** tab, select **Estimate** to open the **Estimate** dialog box.</span></span>

    ![Boîte de dialogue Estimation](./media/subcontract16_estimate-dialog.png)

11. <span data-ttu-id="5f4b6-204">Cliquez sur **OK** pour confirmer l'estimation et revenir à la page **Tous les ordres de fabrication**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-204">Select **OK** to confirm the estimate and return to the **All production orders** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5f4b6-205">Une fois l'ordre de fabrication estimé, la commande fournisseur pour l'article de service S8050 est générée pour le fournisseur US-801.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-205">When the production order is estimated, the purchase order for service item S8050 is generated for vendor US-801.</span></span>

12. <span data-ttu-id="5f4b6-206">Dans le volet Actions, sous l'onglet **Ordre de fabrication**, sélectionnez **Nomenclature** pour ouvrir la page **Nomenclature**, dans laquelle vous pouvez afficher les lignes de nomenclature pour l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-206">On the Action Pane, on the **Production order** tab, select **BOM** to open the **BOM** page, where you can view the BOM lines for the production order.</span></span>

    <span data-ttu-id="5f4b6-207">Pour l'article de service S8050, notez qu'il existe une référence à la commande fournisseur générée lorsque l'ordre de fabrication a été estimé.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-207">For service item S8050, notice that there is a reference to the purchase order that was generated when the production order was estimated.</span></span>

    ![Lignes de nomenclature de l'ordre de fabrication dans la page Nomenclature](./media/subcontract17_production-order-bom-lines.png)

13. <span data-ttu-id="5f4b6-209">Fermez la page **Nomenclature** pour revenir à la page **Tous les ordres de fabrication**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-209">Close the **BOM** page to return to the **All production orders** page.</span></span>
14. <span data-ttu-id="5f4b6-210">Dans le volet Actions, sous l'onglet **Planification**, sélectionnez **Planifier les tâches** pour ouvrir la boîte de dialogue **Planification de tâche**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-210">On the Action Pane, on the **Schedule** tab, select **Schedule jobs** to open the **Job scheduling** dialog box.</span></span>
15. <span data-ttu-id="5f4b6-211">Spécifiez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="5f4b6-211">Specify the following values:</span></span>

    - <span data-ttu-id="5f4b6-212">Dans le champ **Direction de la planification**, sélectionnez **En avant à partir d'aujourd'hui**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-212">In the **Scheduling direction** field, select **Forward from tomorrow**.</span></span>
    - <span data-ttu-id="5f4b6-213">Définissez l'option **Capacité finie** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-213">Set the **Finite capacity** option to **Yes**.</span></span>

    ![Boîte de dialogue Planification de tâche](./media/subcontract18_job-scheduling-dialog.png)

16. <span data-ttu-id="5f4b6-215">Cliquez sur **OK** pour fermer la boîte de dialogue **Planification de tâche** et revenir à la page **Tous les ordres de fabrication**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-215">Select **OK** to close the **Job scheduling** dialog box and return to the **All production orders** page.</span></span>
17. <span data-ttu-id="5f4b6-216">Dans le volet Actions, sous l'onglet **Planification**, sélectionnez **Gantt** pour ouvrir la page **Diagramme de Gantt - Vue Ressource**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-216">On the Action Pane, on the **Schedule** tab, select **Gantt** to open the **Gantt chart - Resource view** page.</span></span>

    <span data-ttu-id="5f4b6-217">Le diagramme de Gantt donne une vue d'ensemble visuelle de la manière dont les tâches de production sont planifiées sur les ressources.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-217">The Gantt chart provides a visual overview of how the production jobs are scheduled on the resources.</span></span> <span data-ttu-id="5f4b6-218">Notez que l'opération de revêtement externe comporte trois tâches : une tâche de traitement, une tâche de transport et une tâche de temps d'attente.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-218">Notice that the external Coating operation consists of three jobs: a process job, a transport job, and a queue time job.</span></span>

    ![Page Diagramme de Gantt - Vue Ressource](./media/subcontract19_gantt-chart.png)

18. <span data-ttu-id="5f4b6-220">Fermez la page **Diagramme de Gantt - Vue Ressource** pour revenir à la page **Tous les ordres de fabrication**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-220">Close the **Gantt chart - Resource view** page to return to the **All production orders** page.</span></span>
19. <span data-ttu-id="5f4b6-221">Dans le volet Actions, sous l'onglet **Ordre de fabrication**, sélectionnez **Lancement** pour ouvrir la boîte de dialogue **Lancement**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-221">On the Action Pane, on the **Production order** tab, select **Release** to open the **Release** dialog box.</span></span>

    ![Boîte de dialogue Lancement](./media/subcontract20_release-dialog.png)

20. <span data-ttu-id="5f4b6-223">Cliquez sur **OK** pour fermer la boîte de dialogue **Lancement**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-223">Select **OK** to close the **Release** dialog box.</span></span>
21. <span data-ttu-id="5f4b6-224">Sélectionnez **Contrôle de la production \> Tâches périodiques \> Lancer dans l'entrepôt \> Lancement automatique des lignes de nomenclature et de formule** pour ouvrir la boîte de dialogue **Lancement automatique des lignes de nomenclature et de formule**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-224">Select **Production control \> Periodic tasks \> Release to warehouse \> Automatic release of BOM and formula lines** to open the **Automatic release of BOM and formula lines** dialog box.</span></span>

    ![Boîte de dialogue Lancement automatique des lignes de nomenclature et de formule](./media/subcontract21_auto-release-bom-formula-lines-dialog.png)

22. <span data-ttu-id="5f4b6-226">Cliquez sur **OK** pour exécuter la tâche Lancement automatique des lignes de nomenclature et de formule.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-226">Select **OK** to run the Automatic release of BOM and formula lines job.</span></span>

    <span data-ttu-id="5f4b6-227">Cette tâche lance le travail de prélèvement des matières premières dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-227">This job releases pick work for raw materials to the warehouse.</span></span>

23. <span data-ttu-id="5f4b6-228">Sélectionnez **Contrôle de la production \> Ordres de fabrication \> Tous les ordres de fabrication** pour ouvrir la page **Tous les ordres de fabrication**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-228">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
24. <span data-ttu-id="5f4b6-229">Utilisez le champ de filtre rapide pour sélectionner l'ordre de fabrication sur lequel vous travaillez.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-229">Use the quick filter field to select the production order that you've been working on.</span></span>
25. <span data-ttu-id="5f4b6-230">Dans le volet Actions, sous l'onglet **Entrepôt**, sélectionnez **Détails du travail** pour ouvrir la page **Travail**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-230">On the Action Pane, on the **Warehouse** tab, select **Work details** to open the **Work** page.</span></span>

    <span data-ttu-id="5f4b6-231">Notez que les page affiche deux ensembles de travail pour le prélèvement des matières premières.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-231">Notice that the page shows two sets of work for raw material picking.</span></span> <span data-ttu-id="5f4b6-232">Le premier travail s'applique aux matières premières M8100 et M8101.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-232">The first work is for materials M8100 and M8101.</span></span> <span data-ttu-id="5f4b6-233">Ces matières sont consommées par l'opération 10.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-233">These materials are consumed by operation 10.</span></span> <span data-ttu-id="5f4b6-234">Le deuxième travail s'applique aux matières M8202 et M8250.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-234">The second work is for materials M8202 and M8250.</span></span> <span data-ttu-id="5f4b6-235">Ces matières sont consommées par l'opération 20, qui correspond à l'opération sous-traitée.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-235">These materials are consumed by operation 20, which is the subcontracted operation.</span></span>

    ![Deux ensembles de travail pour le prélèvement des matières premières dans la page Travail](./media/subcontract22_work-page.png)

26. <span data-ttu-id="5f4b6-237">Démarrez l'application d'entrepôt pour traiter le travail d'entrepôt pour l'opération 10.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-237">Start the warehouse app to process the warehouse work for operation 10.</span></span>

    <!-- TBD – screen shots for processing pick work for the materials. -->

27. <span data-ttu-id="5f4b6-238">Sélectionnez **Contrôle de la production \> Ordres de fabrication \> Tous les ordres de fabrication** pour ouvrir la page **Tous les ordres de fabrication**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-238">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
28. <span data-ttu-id="5f4b6-239">Utilisez le champ de filtre rapide pour sélectionner l'ordre de fabrication sur lequel vous travaillez.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-239">Use the quick filter field to select the production order that you've been working on.</span></span>
29. <span data-ttu-id="5f4b6-240">Dans le volet Actions, sous l'onglet **Ordre de fabrication**, sélectionnez **Démarrer** pour ouvrir la boîte de dialogue **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-240">On the Action Pane, on the **Production order** tab, select **Start** to open the **Start** dialog box.</span></span>
30. <span data-ttu-id="5f4b6-241">Sous l'onglet **Général**, spécifiez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="5f4b6-241">On the **General** tab, specify the following values:</span></span>

    - <span data-ttu-id="5f4b6-242">Dans le champ **Du n° opér.**,</span><span class="sxs-lookup"><span data-stu-id="5f4b6-242">In the **From Oper. No.**</span></span> <span data-ttu-id="5f4b6-243">sélectionnez **10**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-243">field, select **10**.</span></span>
    - <span data-ttu-id="5f4b6-244">Dans le champ **Au n° opér.**,</span><span class="sxs-lookup"><span data-stu-id="5f4b6-244">In the **To Oper. No.**</span></span> <span data-ttu-id="5f4b6-245">sélectionnez **10**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-245">field, select **10**.</span></span>

    ![Valeurs définies dans l'onglet Général](./media/subcontract23_start-dialog.png)

31. <span data-ttu-id="5f4b6-247">Cliquez sur **OK** pour fermer la boîte de dialogue **Démarrer** et revenir à la page **Tous les ordres de fabrication**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-247">Select **OK** to close the **Start** dialog box and return to the **All production orders** page.</span></span>

    <span data-ttu-id="5f4b6-248">Notez que l'ordre de fabrication a maintenant le statut **Commencé**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-248">Notice that the status of the production order is now **Started**.</span></span> <span data-ttu-id="5f4b6-249">Les matières pour l'opération 10 sont consommées par une validation automatique du journal des prélèvements.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-249">The materials for operation 10 are consumed by an automatic posting of the picking list journal.</span></span> <span data-ttu-id="5f4b6-250">La consommation de temps pour l'opération 10 est comptabilisée par une validation automatique du journal des fiches productions.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-250">Time consumption for operation 10 is accounted for by an automatic posting of a route card journal.</span></span>

32. <span data-ttu-id="5f4b6-251">Démarrez l'application d'entrepôt pour traiter le travail d'entrepôt pour l'opération 20.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-251">Start the warehouse app to process the warehouse work for operation 20.</span></span>

    <!-- TBD – screen shots for processing pick work for the materials. -->

33. <span data-ttu-id="5f4b6-252">Dans le volet Actions, sous l'onglet **Ordre de fabrication**, sélectionnez **Démarrer** pour ouvrir la boîte de dialogue **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-252">On the Action Pane, on the **Production order** tab, select **Start** to open the **Start** dialog box.</span></span>
34. <span data-ttu-id="5f4b6-253">Sous l'onglet **Général**, spécifiez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="5f4b6-253">On the **General** tab, specify the following values:</span></span>

    - <span data-ttu-id="5f4b6-254">Dans le champ **Du n° opér.**,</span><span class="sxs-lookup"><span data-stu-id="5f4b6-254">In the **From Oper. No.**</span></span> <span data-ttu-id="5f4b6-255">sélectionnez **20**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-255">field, select **20**.</span></span>
    - <span data-ttu-id="5f4b6-256">Dans le champ **Au n° opér.**,</span><span class="sxs-lookup"><span data-stu-id="5f4b6-256">In the **To Oper. No.**</span></span> <span data-ttu-id="5f4b6-257">sélectionnez **20**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-257">field, select **20**.</span></span>
    - <span data-ttu-id="5f4b6-258">Dans le champ **Quantité**, entrez **10**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-258">In the **Quantity** field, enter **10**.</span></span>
    - <span data-ttu-id="5f4b6-259">Définissez l'option **Valider immédiatement les prélèvements** sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-259">Set the **Post picking list now** option to **No**.</span></span>

    ![Valeurs définies dans l'onglet Général](./media/subcontract24_general-tab.png)

35. <span data-ttu-id="5f4b6-261">Cliquez sur **OK** pour fermer la boîte de dialogue **Démarrer** et revenir à la page **Tous les ordres de fabrication**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-261">Select **OK** to close the **Start** dialog box and return to the **All production orders** page.</span></span>

    <span data-ttu-id="5f4b6-262">Des prélèvements sont créés pour les matières utilisées pour l'opération de revêtement, et pour l'article de service.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-262">A picking list is created for the materials that are used for the Coating operation, and for the service item.</span></span> <span data-ttu-id="5f4b6-263">L'article de service représente le coût de l'opération sous-traitée.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-263">The service item represents the cost of the subcontracted operation.</span></span>

36. <span data-ttu-id="5f4b6-264">Dans le volet Actions, sous l'onglet **Afficher**, sélectionnez **Prélèvements** pour ouvrir la page **Prélèvements**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-264">On the Action Pane, on the **View** tab, select **Picking list** to open the **Picking list** page.</span></span>
37. <span data-ttu-id="5f4b6-265">Sélectionnez les prélèvements qui ne sont pas validés, puis sélectionnez le numéro de journal pour afficher les lignes de journal.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-265">Select the picking list that isn't posted, and then select the journal number to view the journal lines.</span></span>

    ![Lignes du journal dans la page Prélèvements](./media/subcontract25_picking-list.png)

38. <span data-ttu-id="5f4b6-267">Dans le volet Actions, sélectionnez **Imprimer** \> **État Liste de prélèvement** pour ouvrir la boîte de dialogue **État Liste de prélèvement**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-267">On the Action Pane, select **Print** \> **Picking list report** to open the **Picking list report** dialog box.</span></span>
39. <span data-ttu-id="5f4b6-268">Définissez l'option **Utiliser la mise en page de note de livraison** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-268">Set the **Use delivery note layout** option to **Yes**.</span></span>

    ![Boîte de dialogue État Liste de prélèvement](./media/subcontract26_picking-list-report-dialog.png)

40. <span data-ttu-id="5f4b6-270">Cliquez sur **OK** pour générer un état **Liste de prélèvement**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-270">Select **OK** to generate a **Picking list** report.</span></span>

    <span data-ttu-id="5f4b6-271">Dans ce cas, une note de livraison du fournisseur est imprimée à partir du journal des prélèvements en production.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-271">In this case, a vendor delivery note is printed from the production picking list journal.</span></span> <span data-ttu-id="5f4b6-272">La note de livraison spécifie les matières qui sont expédiées au fournisseur qui effectue l'opération de revêtement.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-272">The delivery note specifies the materials that are shipped to the vendor who will do the Coating operation.</span></span>

    ![État sur la liste des prélèvements](./media/subcontract27_picking-list-report.png)

41. <span data-ttu-id="5f4b6-274">Fermez l'état **Liste de prélèvement** pour revenir à la page **Liste de prélèvement**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-274">Close the **Picking list** report to return to the **Picking list** page.</span></span>
42. <span data-ttu-id="5f4b6-275">Dans le volet Actions, sélectionnez **Valider** pour ouvrir la boîte de dialogue **Valider le journal**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-275">On the Action Pane, select **Post** to open the **Post journal** dialog box.</span></span>

    ![Boîte de dialogue Valider le journal](./media/subcontract28_post-journal-dialog.png)

43. <span data-ttu-id="5f4b6-277">Cliquez sur **OK** pour fermer la boîte de dialogue **Valider le journal**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-277">Select **OK** to close the **Post journal** dialog box.</span></span>
44. <span data-ttu-id="5f4b6-278">Ouvrez la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-278">Open the purchase order.</span></span>

    ![Page Commande fournisseur](./media/subcontract29_purchase-order-page.png)

45. <span data-ttu-id="5f4b6-280">Dans le volet Actions, sous l'onglet **Achats**, sélectionnez **Confirmer**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-280">On the Action Pane, on the **Purchase** tab, select **Confirm**.</span></span>
46. <span data-ttu-id="5f4b6-281">Sélectionnez **Valider** pour ouvrir la boîte de dialogue **Valider le journal**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-281">Select **Post** to open the **Post journal** dialog box.</span></span>
47. <span data-ttu-id="5f4b6-282">Cliquez sur **OK** pour fermer la boîte de dialogue **Valider le journal** et revenir à la page **Commande fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-282">Select **OK** to close the **Post journal** dialog box and return to the **Purchase order** page.</span></span>
48. <span data-ttu-id="5f4b6-283">Modifiez le prix unitaire de **33** en **40**.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-283">Change the unit price from **33** to **40**.</span></span>

    ![Prix unitaire modifié dans la page Commande fournisseur](./media/subcontract30_unit-price.png)

49. <span data-ttu-id="5f4b6-285">Confirmez à nouveau la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-285">Confirm the purchase order again.</span></span>
50. <span data-ttu-id="5f4b6-286">Accusé de réception de produits.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-286">Product receipt.</span></span>

    ![Boîte de dialogue Validation de l'accusé de réception de produits](./media/subcontract31_posting-product-receipt-dialog.png)

51. <span data-ttu-id="5f4b6-288">Facture d'achat.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-288">Purchase invoice.</span></span>
52. <span data-ttu-id="5f4b6-289">Mettre à jour le statut de rapprochement.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-289">Update the match status.</span></span>

    ![Page Facture fournisseur](./media/subcontract32_vendor-invoice-page.png)

53. <span data-ttu-id="5f4b6-291">Déclaration de fin.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-291">Report as finished.</span></span>

    ![Boîte de dialogue Déclaration de fin](./media/subcontract33_report-as-finished-dialog.png)

54. <span data-ttu-id="5f4b6-293">Terminer.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-293">End.</span></span>

    ![Boîte de dialogue Terminer](./media/subcontract34_end-dialog.png)

55. <span data-ttu-id="5f4b6-295">Comparaison du coût.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-295">Cost comparison.</span></span>

    ![Graphiques de comparaison du coût](./media/subcontract35_cost-comparison-charts.png)

<span data-ttu-id="5f4b6-297">Paramétrage manquant des données.</span><span class="sxs-lookup"><span data-stu-id="5f4b6-297">Missing setup in data.</span></span>

