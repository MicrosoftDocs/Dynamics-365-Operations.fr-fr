---
title: "Stratégies de travail d'entrepôt"
description: "Les stratégies de travail d'entrepôt contrôlent si le travail d'entrepôt est créé par les processus d'entrepôt pour la production, selon le type d'ordre de travail, l'emplacement de stockage et le produit."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 196561
ms.assetid: cbf48ec6-1836-48d5-ad66-a9b534af1786
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 0710eac8daba7f51f6b5d1522476b812a130960d
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---

# <a name="warehouse-work-policies"></a><span data-ttu-id="0bc05-103">Stratégies de travail d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="0bc05-103">Warehouse work policies</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0bc05-104">Les stratégies de travail d'entrepôt dans Microsoft Dynamics 365 for Finance and Operations contrôlent si le travail d'entrepôt est créé par les processus d'entrepôt pour la production, selon le type d'ordre de travail, l'emplacement de stockage et le produit.</span><span class="sxs-lookup"><span data-stu-id="0bc05-104">Warehouse work policies in Microsoft Dynamics 365 for Finance and Operations control whether warehouse work is created by warehouse processes in manufacturing, based on work order type, inventory location, and product.</span></span>

<span data-ttu-id="0bc05-105">Cette stratégie de travail contrôle si le travail d'entrepôt est créé pour les processus d'entrepôt pour la production.</span><span class="sxs-lookup"><span data-stu-id="0bc05-105">This work policy controls whether warehouse work is created for warehouse processes in manufacturing.</span></span> <span data-ttu-id="0bc05-106">Vous pouvez paramétrer la stratégie de travail à l'aide d'une combinaison de **types d'ordres d'exécution**, d'**emplacement de stockage**, et de **produit**</span><span class="sxs-lookup"><span data-stu-id="0bc05-106">You can set up the work policy by using a combination of **work order types**, an **inventory location**, and a **product**.</span></span> <span data-ttu-id="0bc05-107">Par exemple, le produit L0101 est déclaré comme terminé à l'emplacement de sortie 001.</span><span class="sxs-lookup"><span data-stu-id="0bc05-107">For example, product L0101 is reported as finished to output location 001.</span></span> <span data-ttu-id="0bc05-108">Le produit fini est consommé ultérieurement dans un autre ordre de fabrication à l'emplacement de sortie 001.</span><span class="sxs-lookup"><span data-stu-id="0bc05-108">The finished good is later consumed in another production order at output location 001.</span></span> <span data-ttu-id="0bc05-109">Dans ce cas, vous pouvez paramétrer une stratégie de travail pour empêcher de créer un travail pour ranger le produit fini lorsque vous déclarez le produit L0101 terminé à l'emplacement de sortie 001.</span><span class="sxs-lookup"><span data-stu-id="0bc05-109">In this case, you can set up a work policy to prevent the work for finished goods put-away from being created when you report product L0101 as finished to output location 001.</span></span> <span data-ttu-id="0bc05-110">La stratégie de travail est une entité individuelle qui peut être décrite à l'aide des informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0bc05-110">The work policy is an individual entity that can be described through the following information:</span></span>

-   <span data-ttu-id="0bc05-111">**Nom de stratégie de travail**(identificateur unique de la stratégie de travail)</span><span class="sxs-lookup"><span data-stu-id="0bc05-111">**Work policy name** (the unique identifier of the work policy)</span></span>
-   <span data-ttu-id="0bc05-112">**Types d'ordres d'exécution** et **Méthode de création de travail**</span><span class="sxs-lookup"><span data-stu-id="0bc05-112">**Work order types** and **Work creation method**</span></span>
-   <span data-ttu-id="0bc05-113">**Emplacement de stockage**</span><span class="sxs-lookup"><span data-stu-id="0bc05-113">**Inventory locations**</span></span>
-   <span data-ttu-id="0bc05-114">**Produits**</span><span class="sxs-lookup"><span data-stu-id="0bc05-114">**Products**</span></span>

## <a name="work-order-types"></a><span data-ttu-id="0bc05-115">Types d'ordre d'exécution</span><span class="sxs-lookup"><span data-stu-id="0bc05-115">Work order types</span></span>
<span data-ttu-id="0bc05-116">Vous pouvez sélectionner un des types d'ordres d'exécution suivants :</span><span class="sxs-lookup"><span data-stu-id="0bc05-116">You can select the following work order types:</span></span>

-   <span data-ttu-id="0bc05-117">Rangement des produits finis</span><span class="sxs-lookup"><span data-stu-id="0bc05-117">Finished goods put away</span></span>
-   <span data-ttu-id="0bc05-118">Rangement des coproduits et des sous-produits</span><span class="sxs-lookup"><span data-stu-id="0bc05-118">Co-product and by-product put away</span></span>
-   <span data-ttu-id="0bc05-119">Prélèvement de matières premières</span><span class="sxs-lookup"><span data-stu-id="0bc05-119">Raw material picking</span></span>

<span data-ttu-id="0bc05-120">Le champ **Méthode de création de travail** a la valeur **Jamais**.</span><span class="sxs-lookup"><span data-stu-id="0bc05-120">The **Work creation method** field has the value **Never**.</span></span> <span data-ttu-id="0bc05-121">Cette valeur indique que la stratégie de travail empêchera tout travail d'entrepôt d'être créé pour le type d'ordre d'exécution sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0bc05-121">This value indicates that the work policy will prevent warehouse work from being created for the selected work order type.</span></span>

## <a name="inventory-locations"></a><span data-ttu-id="0bc05-122">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="0bc05-122">Inventory locations</span></span>
<span data-ttu-id="0bc05-123">Vous pouvez sélectionner un emplacement auquel la stratégie de travail s'applique.</span><span class="sxs-lookup"><span data-stu-id="0bc05-123">You can select a location that the work policy applies to.</span></span> <span data-ttu-id="0bc05-124">Si aucun emplacement n'est associé à une stratégie de travail, la stratégie de travail ne s'applique à aucun processus.</span><span class="sxs-lookup"><span data-stu-id="0bc05-124">If no location is associated with a work policy, the work policy doesn’t apply to any processes.</span></span> <span data-ttu-id="0bc05-125">Sur la page **Emplacements**, vous pouvez également sélectionner ou annuler la sélection de la stratégie de travail pour un emplacement spécifique.</span><span class="sxs-lookup"><span data-stu-id="0bc05-125">On the **Locations** page, you can also select or cancel the selection of the work policy for a specific location.</span></span>

## <a name="products"></a><span data-ttu-id="0bc05-126">Produits</span><span class="sxs-lookup"><span data-stu-id="0bc05-126">Products</span></span>
<span data-ttu-id="0bc05-127">Vous pouvez sélectionner un produit auquel la stratégie de travail s'applique.</span><span class="sxs-lookup"><span data-stu-id="0bc05-127">You can select a product that the work policy applies to.</span></span> <span data-ttu-id="0bc05-128">Vous pouvez appliquer la stratégie de travail à tous les produits ou à des produits sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="0bc05-128">You can apply the work policy to either all products or selected products.</span></span>

## <a name="example"></a><span data-ttu-id="0bc05-129">Exemple</span><span class="sxs-lookup"><span data-stu-id="0bc05-129">Example</span></span>
<span data-ttu-id="0bc05-130">Dans l'exemple suivant, il existe deux ordres de fabrication, PRD-001 et PRD-00*2*.</span><span class="sxs-lookup"><span data-stu-id="0bc05-130">In the following example, there are two production orders, PRD-001 and PRD-00*2*.</span></span> <span data-ttu-id="0bc05-131">L'ordre de fabrication PRD-001 a une opération qui est appelée **Assemblage**, où le produit SC1 est déclaré terminé à l'emplacement O1.</span><span class="sxs-lookup"><span data-stu-id="0bc05-131">Production order PRD-001 has an operation that is named **Assembly**, where product SC1 is being reported as finished to location O1.</span></span> <span data-ttu-id="0bc05-132">L'ordre de fabrication PRD-002 a une opération qui est appelée **Peinture** et consomme le produit SC1 de l'emplacement O1.</span><span class="sxs-lookup"><span data-stu-id="0bc05-132">Production order PRD-002 has an operation that is named **Painting** and consumes product SC1 from location O1.</span></span> <span data-ttu-id="0bc05-133">L'ordre de fabrication PRD-002 consomme également la matière première RM1 de l'emplacement O1.</span><span class="sxs-lookup"><span data-stu-id="0bc05-133">Production order PRD-002 also consumes raw material RM1 from location O1.</span></span> <span data-ttu-id="0bc05-134">RM1 est stocké à l'emplacement d'entrepôt BULK-001 et sera prélevé à l'emplacement O1 par le travail d'entrepôt pour le prélèvement de matières premières.</span><span class="sxs-lookup"><span data-stu-id="0bc05-134">RM1 is stored in warehouse location BULK-001 and will be picked to location O1 by warehouse work for raw material picking.</span></span> <span data-ttu-id="0bc05-135">Le travail de prélèvement est généré lorsque la production de PRD-002 est lancée.</span><span class="sxs-lookup"><span data-stu-id="0bc05-135">The picking work is generated when production PRD-002 is released.</span></span> 

<span data-ttu-id="0bc05-136">[![Stratégies de travail d'entrepôt](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)</span><span class="sxs-lookup"><span data-stu-id="0bc05-136">[![Warehouse work policies](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)</span></span> 

<span data-ttu-id="0bc05-137">Lorsque vous planifiez de configurer une stratégie de travail d'entrepôt pour ce scénario, vous devez prendre en compte les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0bc05-137">When you plan to configure a warehouse work policy for this scenario, you should consider the following information:</span></span>

-   <span data-ttu-id="0bc05-138">Le travail d'entrepôt pour le rangement de produits finis n'est pas obligatoire lorsque vous déclarez le produit SC1 terminé dans l'ordre de fabrication PRD-001 à l'emplacement O1.</span><span class="sxs-lookup"><span data-stu-id="0bc05-138">Warehouse work for finished goods put-away isn’t required when you report product SC1 as finished from production order PRD-001 to location O1.</span></span> <span data-ttu-id="0bc05-139">Cela s'explique par le fait que l'opération de **Peinture** pour l'ordre de fabrication PRD-002 consomme SC1 au même emplacement.</span><span class="sxs-lookup"><span data-stu-id="0bc05-139">This is because the **Painting** operation for production order PRD-002 consumes SC1 at the same location.</span></span>
-   <span data-ttu-id="0bc05-140">Le travail d'entrepôt pour le prélèvement de matières premières est requis pour déplacer la matière première RM1 de l'emplacement d'entrepôt BULK-001 vers l'emplacement O1.</span><span class="sxs-lookup"><span data-stu-id="0bc05-140">Warehouse work for raw material picking is required in order to move raw material RM1 from warehouse location BULK-001 to location O1.</span></span>

<span data-ttu-id="0bc05-141">Voici un exemple de stratégie de travail que vous pouvez paramétrer, selon ces aspects.</span><span class="sxs-lookup"><span data-stu-id="0bc05-141">Here is an example of the work policy that you can set up, based on these considerations.</span></span>


|                                       |                                       |
|---------------------------------------|---------------------------------------|
| <span data-ttu-id="0bc05-142"><strong>Nom de la stratégie de travail</strong></span><span class="sxs-lookup"><span data-stu-id="0bc05-142"><strong>Work policy name</strong></span></span><br> | <span data-ttu-id="0bc05-143"><strong>Types d'ordre d'exécution</strong></span><span class="sxs-lookup"><span data-stu-id="0bc05-143"><strong>Work order types</strong></span></span><br> |
|         <span data-ttu-id="0bc05-144">Pas de rangement de 01     \`</span><span class="sxs-lookup"><span data-stu-id="0bc05-144">No put away 01     \`</span></span>          |     <span data-ttu-id="0bc05-145">- Rangement du produit fini</span><span class="sxs-lookup"><span data-stu-id="0bc05-145">- Finished good put away</span></span><br>      |
|                                       |    <span data-ttu-id="0bc05-146"><strong>Emplacements</strong></span><span class="sxs-lookup"><span data-stu-id="0bc05-146"><strong>Locations</strong></span></span><br>     |
|                                       |                 <span data-ttu-id="0bc05-147">- O1</span><span class="sxs-lookup"><span data-stu-id="0bc05-147">- O1</span></span>                  |
|                                       |    <span data-ttu-id="0bc05-148"><strong>Produits</strong></span><span class="sxs-lookup"><span data-stu-id="0bc05-148"><strong>Products</strong></span></span> <br>     |
|                                       |                 <span data-ttu-id="0bc05-149">- SC1</span><span class="sxs-lookup"><span data-stu-id="0bc05-149">- SC1</span></span>                 |

<span data-ttu-id="0bc05-150">Les procédures suivantes fournissent des instructions pas-à-pas sur le paramétrage de la stratégie de travail d'entrepôt pour ce scénario.</span><span class="sxs-lookup"><span data-stu-id="0bc05-150">The following procedures provide step-by-step instructions about how to set up the warehouse work policy for this scenario.</span></span> <span data-ttu-id="0bc05-151">Un exemple de paramétrage expliquant comment déclarer un ordre de fabrication comme terminé à un emplacement qui n'est pas contrôlé par contenant est également décrit.</span><span class="sxs-lookup"><span data-stu-id="0bc05-151">A sample setup showing how to report a production order as finished to a location that isn’t license plate–controlled is also described.</span></span>

## <a name="set-up-a-warehouse-work-policy"></a><span data-ttu-id="0bc05-152">Paramétrer une stratégie de travail d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="0bc05-152">Set up a warehouse work policy</span></span>
<span data-ttu-id="0bc05-153">Les processus d'entrepôt n'incluent pas systématiquement les tâches d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="0bc05-153">Warehouse processes don’t always include warehouse work.</span></span> <span data-ttu-id="0bc05-154">En définissant une stratégie de travail, vous pouvez empêcher la création de tâche pour le prélèvement de matières premières et le rangement de produits finis pour un ensemble de produits à des emplacements spécifiques.</span><span class="sxs-lookup"><span data-stu-id="0bc05-154">By defining a work policy, you can prevent the creation of work for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span> <span data-ttu-id="0bc05-155">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="0bc05-155">The USMF demo data company was used to create this procedure.</span></span> 

<span data-ttu-id="0bc05-156">ÉTAPES (21)</span><span class="sxs-lookup"><span data-stu-id="0bc05-156">STEPS (21)</span></span>

|     |                                                                            |
|-----|----------------------------------------------------------------------------|
| <span data-ttu-id="0bc05-157">1.</span><span class="sxs-lookup"><span data-stu-id="0bc05-157">1.</span></span>  | <span data-ttu-id="0bc05-158">Allez dans Gestion des entrepôts &gt; Paramétrage &gt; Travail &gt; Stratégies de travail.</span><span class="sxs-lookup"><span data-stu-id="0bc05-158">Go to Warehouse management &gt; Setup &gt; Work &gt; Work policies.</span></span>        |
| <span data-ttu-id="0bc05-159">2.</span><span class="sxs-lookup"><span data-stu-id="0bc05-159">2.</span></span>  | <span data-ttu-id="0bc05-160">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="0bc05-160">Click New.</span></span>                                                                 |
| <span data-ttu-id="0bc05-161">3.</span><span class="sxs-lookup"><span data-stu-id="0bc05-161">3.</span></span>  | <span data-ttu-id="0bc05-162">Entrez Aucun travail de rangement dans le champ Nom de la stratégie de travail.</span><span class="sxs-lookup"><span data-stu-id="0bc05-162">In the Work policy name field, type 'No put-away work'.</span></span>                    |
| <span data-ttu-id="0bc05-163">4.</span><span class="sxs-lookup"><span data-stu-id="0bc05-163">4.</span></span>  | <span data-ttu-id="0bc05-164">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="0bc05-164">Click Save.</span></span>                                                                |
| <span data-ttu-id="0bc05-165">5.</span><span class="sxs-lookup"><span data-stu-id="0bc05-165">5.</span></span>  | <span data-ttu-id="0bc05-166">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0bc05-166">Click Add.</span></span>                                                                 |
| <span data-ttu-id="0bc05-167">6.</span><span class="sxs-lookup"><span data-stu-id="0bc05-167">6.</span></span>  | <span data-ttu-id="0bc05-168">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0bc05-168">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="0bc05-169">7.</span><span class="sxs-lookup"><span data-stu-id="0bc05-169">7.</span></span>  | <span data-ttu-id="0bc05-170">Sélectionnez Rangement des produits finis dans le champ Type d'ordre d'exécution.</span><span class="sxs-lookup"><span data-stu-id="0bc05-170">In the Work order type field, select 'Finished goods put away'.</span></span>            |
| <span data-ttu-id="0bc05-171">8.</span><span class="sxs-lookup"><span data-stu-id="0bc05-171">8.</span></span>  | <span data-ttu-id="0bc05-172">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0bc05-172">Click Add.</span></span>                                                                 |
| <span data-ttu-id="0bc05-173">9.</span><span class="sxs-lookup"><span data-stu-id="0bc05-173">9.</span></span>  | <span data-ttu-id="0bc05-174">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0bc05-174">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="0bc05-175">10.</span><span class="sxs-lookup"><span data-stu-id="0bc05-175">10.</span></span> | <span data-ttu-id="0bc05-176">Sélectionnez Rangement des coproduits et des sous-produits dans le champ Type d'ordre d'exécution.</span><span class="sxs-lookup"><span data-stu-id="0bc05-176">In the Work order type field, select 'Co-product and by-product put away'.</span></span> |
| <span data-ttu-id="0bc05-177">11.</span><span class="sxs-lookup"><span data-stu-id="0bc05-177">11.</span></span> | <span data-ttu-id="0bc05-178">Développez la section Emplacement de stockage.</span><span class="sxs-lookup"><span data-stu-id="0bc05-178">Expand the Inventory locations section.</span></span>                                    |
| <span data-ttu-id="0bc05-179">12.</span><span class="sxs-lookup"><span data-stu-id="0bc05-179">12.</span></span> | <span data-ttu-id="0bc05-180">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0bc05-180">Click Add.</span></span>                                                                 |
| <span data-ttu-id="0bc05-181">13</span><span class="sxs-lookup"><span data-stu-id="0bc05-181">13.</span></span> | <span data-ttu-id="0bc05-182">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0bc05-182">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="0bc05-183">14.</span><span class="sxs-lookup"><span data-stu-id="0bc05-183">14.</span></span> | <span data-ttu-id="0bc05-184">Entrez 51 dans la liste Entrepôt.</span><span class="sxs-lookup"><span data-stu-id="0bc05-184">In the Warehouse list, enter '51'.</span></span>                                         |
| <span data-ttu-id="0bc05-185">15.</span><span class="sxs-lookup"><span data-stu-id="0bc05-185">15.</span></span> | <span data-ttu-id="0bc05-186">Saisissez ou sélectionnez 001 dans le champ Emplacement.</span><span class="sxs-lookup"><span data-stu-id="0bc05-186">In the Location field, enter or select '001'.</span></span>                              |
| <span data-ttu-id="0bc05-187">16.</span><span class="sxs-lookup"><span data-stu-id="0bc05-187">16.</span></span> | <span data-ttu-id="0bc05-188">Développez la section Produits.</span><span class="sxs-lookup"><span data-stu-id="0bc05-188">Expand the Products section.</span></span>                                               |
| <span data-ttu-id="0bc05-189">17.</span><span class="sxs-lookup"><span data-stu-id="0bc05-189">17.</span></span> | <span data-ttu-id="0bc05-190">Sélectionnez Sélectionné dans le champ Sélection de produits.</span><span class="sxs-lookup"><span data-stu-id="0bc05-190">In the Product selection field, select 'Selected'.</span></span>                         |
| <span data-ttu-id="0bc05-191">18.</span><span class="sxs-lookup"><span data-stu-id="0bc05-191">18.</span></span> | <span data-ttu-id="0bc05-192">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0bc05-192">Click Add.</span></span>                                                                 |
| <span data-ttu-id="0bc05-193">19.</span><span class="sxs-lookup"><span data-stu-id="0bc05-193">19.</span></span> | <span data-ttu-id="0bc05-194">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0bc05-194">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="0bc05-195">20.</span><span class="sxs-lookup"><span data-stu-id="0bc05-195">20.</span></span> | <span data-ttu-id="0bc05-196">Entrez ou sélectionnez L0101 dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="0bc05-196">In the Item number field, enter or select 'L0101'.</span></span>                         |
| <span data-ttu-id="0bc05-197">21.</span><span class="sxs-lookup"><span data-stu-id="0bc05-197">21.</span></span> | <span data-ttu-id="0bc05-198">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="0bc05-198">Click Save.</span></span>                                                                |

## <a name="report-a-production-order-as-finished-to-a-location-that-isnt-license-platecontrolled"></a><span data-ttu-id="0bc05-199">Déclarer un ordre de fabrication terminé à un emplacement qui n'est pas contrôlé par contenant</span><span class="sxs-lookup"><span data-stu-id="0bc05-199">Report a production order as finished to a location that isn’t license plate–controlled</span></span>
<span data-ttu-id="0bc05-200">Cette procédure présente un exemple de déclaration de fin à un emplacement qui ne fait pas l'objet d'un contrôle de contenant.</span><span class="sxs-lookup"><span data-stu-id="0bc05-200">This procedure shows an example of reporting as finished to a location that isn't license plate–controlled.</span></span> <span data-ttu-id="0bc05-201">Une stratégie de travail applicable correspond est une condition préalable pour cette tâche.</span><span class="sxs-lookup"><span data-stu-id="0bc05-201">An applicable work policy is the prerequisite for this task.</span></span> <span data-ttu-id="0bc05-202">La procédure précédente indiquait le paramétrage de la stratégie de travail.</span><span class="sxs-lookup"><span data-stu-id="0bc05-202">The previous procedure shows the setup of the work policy.</span></span> 

<span data-ttu-id="0bc05-203">ÉTAPES (25)</span><span class="sxs-lookup"><span data-stu-id="0bc05-203">STEPS (25)</span></span>

<table>
<tbody>
<tr>
<td colspan="3"><span data-ttu-id="0bc05-204"><strong>Sous-tâche : définir un emplacement de sortie.</strong></span><span class="sxs-lookup"><span data-stu-id="0bc05-204"><strong>Sub-task: Set up an output location.</strong></span></span></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td><span data-ttu-id="0bc05-205">Allez dans Administration d'organisation &gt; Ressources &gt; Groupes de ressources.</span><span class="sxs-lookup"><span data-stu-id="0bc05-205">Go to Organization administration &gt; Resources &gt; Resource groups.</span></span></td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td><span data-ttu-id="0bc05-206">Sélectionnez le groupe de ressources 5102 dans la liste.</span><span class="sxs-lookup"><span data-stu-id="0bc05-206">In the list, select resource group &#39;5102&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td><span data-ttu-id="0bc05-207">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="0bc05-207">Click Edit.</span></span></td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td><span data-ttu-id="0bc05-208">Entrez 51 dans le champ Entrepôt de sortie.</span><span class="sxs-lookup"><span data-stu-id="0bc05-208">In the Output warehouse field, enter &#39;51&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td><span data-ttu-id="0bc05-209">Entrez 001 dans le champ Emplacement de sortie.</span><span class="sxs-lookup"><span data-stu-id="0bc05-209">In the Output location field, enter &#39;001&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td><span data-ttu-id="0bc05-210">L'emplacement 001 n'est un emplacement qui fait l'objet d'un contrôle de contenant.</span><span class="sxs-lookup"><span data-stu-id="0bc05-210">Location 001 isn&#39;t a license plate–controlled location.</span></span> <span data-ttu-id="0bc05-211">Vous pouvez uniquement paramétrer un emplacement de sortie faisant l'objet d'un contrôle de contenant si une stratégie de travail applicable existe pour l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="0bc05-211">You can set up a non–license plate output location only if an applicable work policy exists for the location.</span></span></td>
</tr>
<tr>
<td colspan="3"><span data-ttu-id="0bc05-212"><strong>Sous-tâche : créer un ordre de fabrication et le déclarer comme terminé.</strong></span><span class="sxs-lookup"><span data-stu-id="0bc05-212"><strong>Sub-task: Create a production order and report it as finished.</strong></span></span></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td><span data-ttu-id="0bc05-213">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0bc05-213">Close the page.</span></span></td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td><span data-ttu-id="0bc05-214">Allez dans Contrôle de la production &gt; Ordres de fabrication &gt; Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="0bc05-214">Go to Production control &gt; Production orders &gt; All production orders.</span></span></td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td><span data-ttu-id="0bc05-215">Cliquez sur Nouvel ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="0bc05-215">Click New production order.</span></span></td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td><span data-ttu-id="0bc05-216">Entrez L0101 dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="0bc05-216">In the Item number field, enter &#39;L0101&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td><span data-ttu-id="0bc05-217">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="0bc05-217">Click Create.</span></span></td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td><span data-ttu-id="0bc05-218">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="0bc05-218">On the Action Pane, click Production order.</span></span></td>
</tr>
<tr>
<td></td>
<td>7.</td>
<td><span data-ttu-id="0bc05-219">Cliquez sur Estimer.</span><span class="sxs-lookup"><span data-stu-id="0bc05-219">Click Estimate.</span></span></td>
</tr>
<tr>
<td></td>
<td>8.</td>
<td><span data-ttu-id="0bc05-220">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0bc05-220">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>9.</td>
<td><span data-ttu-id="0bc05-221">Cliquez sur Démarrer.</span><span class="sxs-lookup"><span data-stu-id="0bc05-221">Click Start.</span></span></td>
</tr>
<tr>
<td></td>
<td>10.</td>
<td><span data-ttu-id="0bc05-222">Cliquez sur l'onglet Général.</span><span class="sxs-lookup"><span data-stu-id="0bc05-222">Click the General tab.</span></span></td>
</tr>
<tr>
<td></td>
<td>11.</td>
<td><span data-ttu-id="0bc05-223">Dans le champ Consommation de nomenclature automatique, sélectionnez Jamais.</span><span class="sxs-lookup"><span data-stu-id="0bc05-223">In the Automatic BOM consumption field, select &#39;Never&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>12.</td>
<td><span data-ttu-id="0bc05-224">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0bc05-224">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>13.</td>
<td><span data-ttu-id="0bc05-225">Cliquez sur Déclaration de fin.</span><span class="sxs-lookup"><span data-stu-id="0bc05-225">Click Report as finished.</span></span></td>
</tr>
<tr>
<td></td>
<td>14.</td>
<td><span data-ttu-id="0bc05-226">Cliquez sur l'onglet Général.</span><span class="sxs-lookup"><span data-stu-id="0bc05-226">Click the General tab.</span></span></td>
</tr>
<tr>
<td></td>
<td>15.</td>
<td><span data-ttu-id="0bc05-227">Dans le champ Accepter les erreurs, sélectionnez Oui.</span><span class="sxs-lookup"><span data-stu-id="0bc05-227">Select Yes in the Accept error field.</span></span></td>
</tr>
<tr>
<td></td>
<td>16.</td>
<td><span data-ttu-id="0bc05-228">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0bc05-228">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>17.</td>
<td><span data-ttu-id="0bc05-229">Cliquez sur Entrepôt dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="0bc05-229">On the Action Pane, click Warehouse.</span></span></td>
</tr>
<tr>
<td></td>
<td>18.</td>
<td><span data-ttu-id="0bc05-230">Cliquez sur Détails du travail.</span><span class="sxs-lookup"><span data-stu-id="0bc05-230">Click Work details.</span></span></td>
</tr>
<tr>
<td></td>
<td>19.</td>
<td><span data-ttu-id="0bc05-231">Lorsque l'ordre de fabrication a été déclaré comme terminé, aucune tâche de rangement n'a été générée.</span><span class="sxs-lookup"><span data-stu-id="0bc05-231">When the production order was reported as finished, no work was generated for put-away.</span></span> <span data-ttu-id="0bc05-232">Cela se produit car une stratégie de travail est définie et empêche la tâche d'être générée lorsque le produit L0101 est déclaré comme terminé à l'emplacement 001.</span><span class="sxs-lookup"><span data-stu-id="0bc05-232">This occurs because a work policy is defined that prevents work from being generated when product L0101 is reported as finished to location 001.</span></span></td>
</tr>
</tbody>
</table>




