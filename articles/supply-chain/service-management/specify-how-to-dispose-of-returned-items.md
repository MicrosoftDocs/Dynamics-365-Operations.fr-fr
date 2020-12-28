---
title: Spécification de la procédure de cession des articles retournés
description: Spécification de la procédure de cession des articles retournés.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b2b1468328433a67253bafc21ac9c9b3a2398872
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427557"
---
# <a name="specify-how-to-dispose-of-returned-items"></a><span data-ttu-id="8ad60-103">Spécification de la procédure de cession des articles retournés</span><span class="sxs-lookup"><span data-stu-id="8ad60-103">Specify how to dispose of returned items</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="8ad60-104">Lorsque vous traitez un ordre de retour, vous devez spécifier un code motif de retour pour identifier la raison pour laquelle le produit est retourné.</span><span class="sxs-lookup"><span data-stu-id="8ad60-104">When you handle a return order, you must specify a reason return code to identify why the product is being returned.</span></span> <span data-ttu-id="8ad60-105">Vous devez également spécifier un code disposition et une action de disposition pour déterminer les tâches à effectuer avec le produit retourné.</span><span class="sxs-lookup"><span data-stu-id="8ad60-105">You must also specify a disposition code and a disposition action to determine what should be done with the returned product itself.</span></span>

<span data-ttu-id="8ad60-106">Vous pouvez appliquer un code disposition lorsque vous créez un ordre de retour, enregistrez l'arrivée des articles, mettez à jour le bon de livraison d'une arrivée d'articles ou terminez un ordre de contrôle.</span><span class="sxs-lookup"><span data-stu-id="8ad60-106">A disposition code can be applied when you create the return order, register item arrival or packing-slip update an item arrival, and end a quarantine order.</span></span>

<span data-ttu-id="8ad60-107">Vous pouvez définir tout code disposition nécessaire à la prise en charge des processus entreprise.</span><span class="sxs-lookup"><span data-stu-id="8ad60-107">You can define any disposition codes that you need in order to support the business processes.</span></span> <span data-ttu-id="8ad60-108">Le tableau suivant présente un ensemble de codes généralement utilisés pour affecter une disposition à l'article retourné.</span><span class="sxs-lookup"><span data-stu-id="8ad60-108">The following table provides a set of typically used codes to assign return-item disposition.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8ad60-109">Type de disposition</span><span class="sxs-lookup"><span data-stu-id="8ad60-109">Disposition type</span></span></p></th>
<th><p><span data-ttu-id="8ad60-110">Code courant</span><span class="sxs-lookup"><span data-stu-id="8ad60-110">Common code</span></span></p></th>
<th><p><span data-ttu-id="8ad60-111">description ;</span><span class="sxs-lookup"><span data-stu-id="8ad60-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ad60-112">Cession</span><span class="sxs-lookup"><span data-stu-id="8ad60-112">Disposal</span></span></p></td>
<td><p><span data-ttu-id="8ad60-113">SC</span><span class="sxs-lookup"><span data-stu-id="8ad60-113">SC</span></span></p></td>
<td><p><span data-ttu-id="8ad60-114">Mise au rebut/destruction</span><span class="sxs-lookup"><span data-stu-id="8ad60-114">Scrap/Destroy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad60-115">Cession</span><span class="sxs-lookup"><span data-stu-id="8ad60-115">Disposal</span></span></p></td>
<td><p><span data-ttu-id="8ad60-116">DC</span><span class="sxs-lookup"><span data-stu-id="8ad60-116">DC</span></span></p></td>
<td><p><span data-ttu-id="8ad60-117">Don aux œuvres caritatives</span><span class="sxs-lookup"><span data-stu-id="8ad60-117">Donate to Charity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad60-118">Cession</span><span class="sxs-lookup"><span data-stu-id="8ad60-118">Disposal</span></span></p></td>
<td><p><span data-ttu-id="8ad60-119">TD</span><span class="sxs-lookup"><span data-stu-id="8ad60-119">TD</span></span></p></td>
<td><p><span data-ttu-id="8ad60-120">Cession à un tiers</span><span class="sxs-lookup"><span data-stu-id="8ad60-120">Third-Party Disposal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad60-121">Cession</span><span class="sxs-lookup"><span data-stu-id="8ad60-121">Disposal</span></span></p></td>
<td><p><span data-ttu-id="8ad60-122">SL</span><span class="sxs-lookup"><span data-stu-id="8ad60-122">SL</span></span></p></td>
<td><p><span data-ttu-id="8ad60-123">Valeur résiduelle</span><span class="sxs-lookup"><span data-stu-id="8ad60-123">Salvage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad60-124">Cession</span><span class="sxs-lookup"><span data-stu-id="8ad60-124">Disposal</span></span></p></td>
<td><p><span data-ttu-id="8ad60-125">TS</span><span class="sxs-lookup"><span data-stu-id="8ad60-125">TS</span></span></p></td>
<td><p><span data-ttu-id="8ad60-126">Vente à des tiers (marchés secondaires)</span><span class="sxs-lookup"><span data-stu-id="8ad60-126">Third-Party Sale (Secondary Markets)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad60-127">Réparation/modification</span><span class="sxs-lookup"><span data-stu-id="8ad60-127">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="8ad60-128">RW</span><span class="sxs-lookup"><span data-stu-id="8ad60-128">RW</span></span></p></td>
<td><p><span data-ttu-id="8ad60-129">Remise en fabrication</span><span class="sxs-lookup"><span data-stu-id="8ad60-129">Rework</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad60-130">Réparation/modification</span><span class="sxs-lookup"><span data-stu-id="8ad60-130">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="8ad60-131">RF</span><span class="sxs-lookup"><span data-stu-id="8ad60-131">RF</span></span></p></td>
<td><p><span data-ttu-id="8ad60-132">Réusinage/rénovation</span><span class="sxs-lookup"><span data-stu-id="8ad60-132">Remanufacture/Refurbish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad60-133">Réparation/modification</span><span class="sxs-lookup"><span data-stu-id="8ad60-133">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="8ad60-134">MD</span><span class="sxs-lookup"><span data-stu-id="8ad60-134">MD</span></span></p></td>
<td><p><span data-ttu-id="8ad60-135">Modification</span><span class="sxs-lookup"><span data-stu-id="8ad60-135">Modify</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad60-136">Réparation/modification</span><span class="sxs-lookup"><span data-stu-id="8ad60-136">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="8ad60-137">RP</span><span class="sxs-lookup"><span data-stu-id="8ad60-137">RP</span></span></p></td>
<td><p><span data-ttu-id="8ad60-138">Réparation</span><span class="sxs-lookup"><span data-stu-id="8ad60-138">Repair</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad60-139">Réparation/modification</span><span class="sxs-lookup"><span data-stu-id="8ad60-139">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="8ad60-140">RV</span><span class="sxs-lookup"><span data-stu-id="8ad60-140">RV</span></span></p></td>
<td><p><span data-ttu-id="8ad60-141">Retour au fournisseur</span><span class="sxs-lookup"><span data-stu-id="8ad60-141">Return to Vendor</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad60-142">Divers</span><span class="sxs-lookup"><span data-stu-id="8ad60-142">Other</span></span></p></td>
<td><p><span data-ttu-id="8ad60-143">AI</span><span class="sxs-lookup"><span data-stu-id="8ad60-143">AI</span></span></p></td>
<td><p><span data-ttu-id="8ad60-144">Utilisation par dérogation</span><span class="sxs-lookup"><span data-stu-id="8ad60-144">Use as is</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad60-145">Divers</span><span class="sxs-lookup"><span data-stu-id="8ad60-145">Other</span></span></p></td>
<td><p><span data-ttu-id="8ad60-146">RS</span><span class="sxs-lookup"><span data-stu-id="8ad60-146">RS</span></span></p></td>
<td><p><span data-ttu-id="8ad60-147">Revente</span><span class="sxs-lookup"><span data-stu-id="8ad60-147">Resale</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad60-148">Divers</span><span class="sxs-lookup"><span data-stu-id="8ad60-148">Other</span></span></p></td>
<td><p><span data-ttu-id="8ad60-149">EX</span><span class="sxs-lookup"><span data-stu-id="8ad60-149">EX</span></span></p></td>
<td><p><span data-ttu-id="8ad60-150">Échanger</span><span class="sxs-lookup"><span data-stu-id="8ad60-150">Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad60-151">Divers</span><span class="sxs-lookup"><span data-stu-id="8ad60-151">Other</span></span></p></td>
<td><p><span data-ttu-id="8ad60-152">MS</span><span class="sxs-lookup"><span data-stu-id="8ad60-152">MS</span></span></p></td>
<td><p><span data-ttu-id="8ad60-153">Autre(s)</span><span class="sxs-lookup"><span data-stu-id="8ad60-153">Miscellaneous</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8ad60-154">Pour chaque code disposition défini, vous devez sélectionner une action de disposition.</span><span class="sxs-lookup"><span data-stu-id="8ad60-154">For each disposition code that you define, you must select a disposition action.</span></span> <span data-ttu-id="8ad60-155">L'action de disposition détermine les conséquences physiques et financières des codes disposition.</span><span class="sxs-lookup"><span data-stu-id="8ad60-155">The disposition action determines the physical and financial implications of the disposition codes.</span></span> <span data-ttu-id="8ad60-156">Par exemple, l'action de disposition détermine la gestion physique de l'article retourné, l'impact financier de l'article retourné et si un article de remplacement doit être envoyé au client.</span><span class="sxs-lookup"><span data-stu-id="8ad60-156">For example, the disposition action determines the physical handling of the returned item, the financial effect of the returned item, and if a replacement item must be sent to the customer.</span></span> <span data-ttu-id="8ad60-157">Vous pouvez définir un nombre illimité de codes disposition en fonction de vos besoins, mais vous avez le choix uniquement entre six actions de destination prédéfinies.</span><span class="sxs-lookup"><span data-stu-id="8ad60-157">You can define an unlimited number of disposition codes according to your business needs, but there are only six predefined disposition actions that you can select from.</span></span> <span data-ttu-id="8ad60-158">Le tableau suivant décrit les actions de disposition et leurs définitions.</span><span class="sxs-lookup"><span data-stu-id="8ad60-158">The following table provides the disposition actions and their definitions.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8ad60-159">Action de disposition</span><span class="sxs-lookup"><span data-stu-id="8ad60-159">Disposition action</span></span></p></th>
<th><p><span data-ttu-id="8ad60-160">Description</span><span class="sxs-lookup"><span data-stu-id="8ad60-160">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ad60-161"><strong>Crédit</strong></span><span class="sxs-lookup"><span data-stu-id="8ad60-161"><strong>Credit</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad60-162">Permet de remettre l'article en stock et de créditer le compte client.</span><span class="sxs-lookup"><span data-stu-id="8ad60-162">Return the item to inventory and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad60-163"><strong>Créditer uniquement</strong></span><span class="sxs-lookup"><span data-stu-id="8ad60-163"><strong>Credit only</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad60-164">Permet de créditer le client sans demander ni attendre que l'article soit retourné.</span><span class="sxs-lookup"><span data-stu-id="8ad60-164">Credit the customer without requiring or expecting the item to be returned.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad60-165"><strong>Rebut</strong></span><span class="sxs-lookup"><span data-stu-id="8ad60-165"><strong>Scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad60-166">Permet de mettre l'article au rebut et de créditer le client.</span><span class="sxs-lookup"><span data-stu-id="8ad60-166">Scrap the item and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad60-167"><strong>Remplacer et créditer</strong></span><span class="sxs-lookup"><span data-stu-id="8ad60-167"><strong>Replace and credit</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad60-168">Permet de remettre l'article en stock, de créer un ordre de remplacement et de créditer le client.</span><span class="sxs-lookup"><span data-stu-id="8ad60-168">Return the item to inventory, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad60-169"><strong>Remplacer et mettre au rebut</strong></span><span class="sxs-lookup"><span data-stu-id="8ad60-169"><strong>Replace and scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad60-170">Permet de mettre l'article au rebut, de créer un ordre de remplacement et de créditer le client.</span><span class="sxs-lookup"><span data-stu-id="8ad60-170">Scrap the item, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad60-171"><strong>Retourner au client</strong></span><span class="sxs-lookup"><span data-stu-id="8ad60-171"><strong>Return to customer</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad60-172">Permet de rejeter l'article retourné et de le renvoyer au client.</span><span class="sxs-lookup"><span data-stu-id="8ad60-172">Reject the returned item and return it to the customer.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="select-a-disposition-code-for-a-quarantine-order"></a><span data-ttu-id="8ad60-173">Sélection d'un code disposition pour un ordre de contrôle</span><span class="sxs-lookup"><span data-stu-id="8ad60-173">Select a disposition code for a quarantine order</span></span>

1.  <span data-ttu-id="8ad60-174">Cliquez sur **Gestion des stocks** \> **Périodique** \> **Gestion de la qualité** \> **Ordres de contrôle**.</span><span class="sxs-lookup"><span data-stu-id="8ad60-174">Click **Inventory management** \> **Periodic** \> **Quality management** \> **Quarantine orders**.</span></span>

2.  <span data-ttu-id="8ad60-175">Pour un ordre de contrôle existant, sélectionnez une action dans le champ **Code disposition** de l'onglet **Vue d'ensemble**.</span><span class="sxs-lookup"><span data-stu-id="8ad60-175">For an existing quarantine order, select an action from the **Disposition code** field on the **Overview** tab.</span></span>



## <a name="see-also"></a><span data-ttu-id="8ad60-176">Voir également :</span><span class="sxs-lookup"><span data-stu-id="8ad60-176">See also</span></span>

<span data-ttu-id="8ad60-177">[Ordre de contrôle (écran)](https://technet.microsoft.com/library/aa554073(v=ax.60))</span><span class="sxs-lookup"><span data-stu-id="8ad60-177">[Quarantine order (form)](https://technet.microsoft.com/library/aa554073(v=ax.60))</span></span>

<span data-ttu-id="8ad60-178">[Codes disposition (écran)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="8ad60-178">[Disposition codes (form)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))</span></span>

  


