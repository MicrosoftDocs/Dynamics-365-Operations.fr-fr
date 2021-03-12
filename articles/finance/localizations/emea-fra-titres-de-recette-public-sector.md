---
title: Titres de recette dans le secteur public en France
description: Le titre de recette est utilisé par le directeur utilise le titre de recette pour aviser et autoriser le comptable à collecter et à déposer un montant déterminé d’une autre entité.
author: rschloma
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: kfend
ms.custom: 19931
ms.search.region: France
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c51f4e7b6c54ca7690ee8cb9cd25dfa7612ede28
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5002929"
---
# <a name="titres-de-recette-in-the-public-sector-in-france"></a><span data-ttu-id="b922e-103">Titres de recette dans le secteur public en France</span><span class="sxs-lookup"><span data-stu-id="b922e-103">Titres de recette in the public sector in France</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b922e-104">Le directeur utilise le titre de recette est utilisé par le directeur utilise le titre de recette pour aviser et autoriser le comptable à collecter et à déposer un montant déterminé d’une autre entité.</span><span class="sxs-lookup"><span data-stu-id="b922e-104">The director uses the titre de recette to notify and authorize the accountant to collect and deposit a specific amount from another entity.</span></span> <span data-ttu-id="b922e-105">Le directeur ou le comptable peut déléguer un représentant pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="b922e-105">The director or the accountant may delegate a representative to perform the task.</span></span> <span data-ttu-id="b922e-106">Cependant, la responsabilité de chaque tâche incombe au directeur ou au comptable.</span><span class="sxs-lookup"><span data-stu-id="b922e-106">However, the responsibility for each task remains with the director or the accountant.</span></span> <span data-ttu-id="b922e-107">Le titre permet de garantir une séparation nette obligatoire entre le rôle opérationnel du directeur et le rôle comptable du comptable.</span><span class="sxs-lookup"><span data-stu-id="b922e-107">The titre maintains the strict separation that is required between the director's operational role and the accountant's accounting role.</span></span>

<span data-ttu-id="b922e-108">Dans Dynamics 365 Finance, une seule ligne de facture financière est affectée à chaque titre.</span><span class="sxs-lookup"><span data-stu-id="b922e-108">In Dynamics 365 Finance, each titre is assigned a single free text invoice line.</span></span> <span data-ttu-id="b922e-109">Cette affectation permet de garantir que chaque titre ne concerne qu’un seul débiteur et n’inclut qu’un seul compte budgétaire.</span><span class="sxs-lookup"><span data-stu-id="b922e-109">This assignment guarantees that each titre concerns only one debtor and includes only one budgetary account.</span></span> <span data-ttu-id="b922e-110">Un groupe de titres liés avec leurs documents associés sont affectés à un bordereau de titre pour être soumis au comptable.</span><span class="sxs-lookup"><span data-stu-id="b922e-110">A group of related titres, together with all supporting documentation, are assigned to a bordereau de titre for submittal to the accountant.</span></span>

## <a name="directors-tasks"></a><span data-ttu-id="b922e-111">Tâches du directeur</span><span class="sxs-lookup"><span data-stu-id="b922e-111">Director’s tasks</span></span>
<span data-ttu-id="b922e-112">Sur la page **Tenir à jour les titres de recette**, le directeur peut effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="b922e-112">From the **Maintain titres de recette** page, the director can complete the following tasks:</span></span>

-   <span data-ttu-id="b922e-113">**Affecter des lignes de facture à un titre de recette.**</span><span class="sxs-lookup"><span data-stu-id="b922e-113">**Assign invoice lines to a titre de recette.**</span></span> <span data-ttu-id="b922e-114">Pour rechercher les lignes de facture qui n’ont pas encore été affectées à un titre, vous pouvez filtrer les lignes récupérées par la colonne **Titre**.</span><span class="sxs-lookup"><span data-stu-id="b922e-114">To find the invoice lines that haven’t yet been assigned to a titre, you can filter the retrieved lines by the **Titre** column.</span></span>
-   <span data-ttu-id="b922e-115">**Autoriser le recouvrement des lignes de facture affectées à des titres.**</span><span class="sxs-lookup"><span data-stu-id="b922e-115">**Authorize collection of invoice lines that are assigned to titres.**</span></span> <span data-ttu-id="b922e-116">L’autorisation peut également être effectuée à partir de l’onglet **Titre de recette** de la page **Facture financière**.</span><span class="sxs-lookup"><span data-stu-id="b922e-116">Authorization can also be completed from the **Titre de recette** tab on the **Free text invoice** page.</span></span>
-   <span data-ttu-id="b922e-117">**Affectation de titres à un bordereau de titre.**</span><span class="sxs-lookup"><span data-stu-id="b922e-117">**Assign titres to a bordereau de titre.**</span></span> <span data-ttu-id="b922e-118">Pour rechercher les lignes de facture qui n’ont pas encore été affectées à un bordereau de titre, utilisez la colonne **Bordereau de titre** pour filtrer les lignes récupérées.</span><span class="sxs-lookup"><span data-stu-id="b922e-118">To find the invoice lines that haven’t yet been assigned to a bordereau de titre, use the **Bordereau de titre** column to filter the retrieved lines.</span></span>

<span data-ttu-id="b922e-119">Pour soumettre les titres au comptable pour dépôt, le directeur recueille les titres imprimés et leurs documents associés sous un bordereau de titre.</span><span class="sxs-lookup"><span data-stu-id="b922e-119">To submit titres to the accountant for deposit, the director collects the printed titres and their related documentation under a borderau de titre.</span></span>

-   <span data-ttu-id="b922e-120">Imprimez les titres affectés à un bordereau à partir de l’organisateur **Enregistrements à inclure** de la page **État de titre de recette**.</span><span class="sxs-lookup"><span data-stu-id="b922e-120">Print the titres assigned to a bordereau from the **Records to include** FastTab on the **Titre de recette report** page.</span></span>
-   <span data-ttu-id="b922e-121">Imprimez le bordereau à partir de l’organisateur **Enregistrements à inclure** de la page **État de bordereau de titre**.</span><span class="sxs-lookup"><span data-stu-id="b922e-121">Print the bordereau from the **Records to include** FastTab on the **Bordereau de titre report** page.</span></span>

## <a name="accountants-tasks"></a><span data-ttu-id="b922e-122">Tâches du comptable</span><span class="sxs-lookup"><span data-stu-id="b922e-122">Accountant’s tasks</span></span>
<span data-ttu-id="b922e-123">À partir de la page **Tenir à jour les titres de recette** ou de l’onglet **Titre de recette** de la page de facture financière, le comptable peut accepter, rejeter ou mettre en attente les titres.</span><span class="sxs-lookup"><span data-stu-id="b922e-123">From the **Maintain titres de recette** page or from the **Titre de recette** tab on the free text invoice page, the accountant can accept, reject, or hold titres.</span></span> <span data-ttu-id="b922e-124">Lorsqu’un titre est rejeté, le statut d’administrateur passe à Non révisé(e).</span><span class="sxs-lookup"><span data-stu-id="b922e-124">When a titre is rejected, the director status changes to Not reviewed.</span></span> <span data-ttu-id="b922e-125">Les numéros de titre et bordereau de titre sont effacés.</span><span class="sxs-lookup"><span data-stu-id="b922e-125">The titre and bordereau de titre numbers are cleared.</span></span>

## <a name="using-the-database-inquiry-page"></a><span data-ttu-id="b922e-126">Utilisation de la page Recherche dans la base de données</span><span class="sxs-lookup"><span data-stu-id="b922e-126">Using the Database inquiry page</span></span>
<span data-ttu-id="b922e-127">Pour ouvrir la page **Recherche dans la base de données** à partir de la page **Tenir à jour les titres de recette**, spécifiez la plage de dates dans laquelle vous souhaitez sélectionner des factures.</span><span class="sxs-lookup"><span data-stu-id="b922e-127">To open the **Database inquiry** page from the **Maintain titres de recette** page, specify the range of dates you want to select invoices from.</span></span> <span data-ttu-id="b922e-128">Cliquez ensuite sur **Récupérer les lignes**.</span><span class="sxs-lookup"><span data-stu-id="b922e-128">Then click **Retrieve lines**.</span></span> <span data-ttu-id="b922e-129">La page **Recherche dans la base de données** s’ouvre et vous pouvez spécifier les critères pour les lignes de facture que vous souhaitez récupérer.</span><span class="sxs-lookup"><span data-stu-id="b922e-129">Thhe **Database inquiry** page opens and you can specify the criteria for the invoice lines you want to retrieve.</span></span> <span data-ttu-id="b922e-130">Lorsque vous fermez la page, toutes les lignes de facture qui correspondent aux critères sélectionnés s’affichent dans la grille.</span><span class="sxs-lookup"><span data-stu-id="b922e-130">When you close the page, all the invoice lines that meet the selected criteria are retrieved into the grid.</span></span> <span data-ttu-id="b922e-131">Les lignes des factures qui sont en cours de modification ne sont pas récupérées.</span><span class="sxs-lookup"><span data-stu-id="b922e-131">Lines from the invoices that are being edited will not be retrieved.</span></span> 

<span data-ttu-id="b922e-132">Utilisez les critères suivants dans la page de recherche dans la base de données pour récupérer des lignes.</span><span class="sxs-lookup"><span data-stu-id="b922e-132">Use the following criteria in the database inquiry page to retrieve lines.</span></span>

- <span data-ttu-id="b922e-133">Lignes de facture qui n’ont pas été révisées par le directeur.</span><span class="sxs-lookup"><span data-stu-id="b922e-133">Invoice lines that have not been reviewed by the director.</span></span>

  | <span data-ttu-id="b922e-134">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="b922e-134">Table</span></span> | <span data-ttu-id="b922e-135">Table dérivée</span><span class="sxs-lookup"><span data-stu-id="b922e-135">Derived table</span></span> |             <span data-ttu-id="b922e-136">Champ</span><span class="sxs-lookup"><span data-stu-id="b922e-136">Field</span></span>             |    <span data-ttu-id="b922e-137">Critères</span><span class="sxs-lookup"><span data-stu-id="b922e-137">Criteria</span></span>    |
  |-------|---------------|-------------------------------|----------------|
  | <span data-ttu-id="b922e-138">Titre</span><span class="sxs-lookup"><span data-stu-id="b922e-138">Titre</span></span> |     <span data-ttu-id="b922e-139">Titre</span><span class="sxs-lookup"><span data-stu-id="b922e-139">Titre</span></span>     | <span data-ttu-id="b922e-140">Statut d’autorisation du directeur</span><span class="sxs-lookup"><span data-stu-id="b922e-140">Director authorization status</span></span> | <span data-ttu-id="b922e-141">« Non révisé(e) »</span><span class="sxs-lookup"><span data-stu-id="b922e-141">"Not reviewed"</span></span> |


- <span data-ttu-id="b922e-142">Lignes de facture des titres qui ont été autorisés au recouvrement par le directeur, mais pas encore approuvées par le comptable.</span><span class="sxs-lookup"><span data-stu-id="b922e-142">Invoice lines from titres that have been authorized for collection by the director, but not yet approved by the accountant.</span></span>

  | <span data-ttu-id="b922e-143">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="b922e-143">Table</span></span> | <span data-ttu-id="b922e-144">Table dérivée</span><span class="sxs-lookup"><span data-stu-id="b922e-144">Derived table</span></span> |             <span data-ttu-id="b922e-145">Champ</span><span class="sxs-lookup"><span data-stu-id="b922e-145">Field</span></span>             |    <span data-ttu-id="b922e-146">Critères</span><span class="sxs-lookup"><span data-stu-id="b922e-146">Criteria</span></span>    |
  |-------|---------------|-------------------------------|----------------|
  | <span data-ttu-id="b922e-147">Titre</span><span class="sxs-lookup"><span data-stu-id="b922e-147">Titre</span></span> |     <span data-ttu-id="b922e-148">Titre</span><span class="sxs-lookup"><span data-stu-id="b922e-148">Titre</span></span>     | <span data-ttu-id="b922e-149">Statut d’autorisation du directeur</span><span class="sxs-lookup"><span data-stu-id="b922e-149">Director authorization status</span></span> |  <span data-ttu-id="b922e-150">« Autorisé(e) »</span><span class="sxs-lookup"><span data-stu-id="b922e-150">"Authorized"</span></span>  |
  | <span data-ttu-id="b922e-151">Titre</span><span class="sxs-lookup"><span data-stu-id="b922e-151">Titre</span></span> |     <span data-ttu-id="b922e-152">Titre</span><span class="sxs-lookup"><span data-stu-id="b922e-152">Titre</span></span>     | <span data-ttu-id="b922e-153">Statut d’acceptation du comptable</span><span class="sxs-lookup"><span data-stu-id="b922e-153">Accountant acceptance status</span></span>  | <span data-ttu-id="b922e-154">« Non révisé(e) »</span><span class="sxs-lookup"><span data-stu-id="b922e-154">"Not reviewed"</span></span> |


- <span data-ttu-id="b922e-155">Lignes de facture des titres qui ont été rejetés par le comptable.</span><span class="sxs-lookup"><span data-stu-id="b922e-155">Invoice lines from titres that were rejected by the accountant.</span></span>

  | <span data-ttu-id="b922e-156">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="b922e-156">Table</span></span> | <span data-ttu-id="b922e-157">Table dérivée</span><span class="sxs-lookup"><span data-stu-id="b922e-157">Derived table</span></span> | <span data-ttu-id="b922e-158">Champ</span><span class="sxs-lookup"><span data-stu-id="b922e-158">Field</span></span>                        | <span data-ttu-id="b922e-159">Critères</span><span class="sxs-lookup"><span data-stu-id="b922e-159">Criteria</span></span>   |
  |-------|---------------|------------------------------|------------|
  | <span data-ttu-id="b922e-160">Titre</span><span class="sxs-lookup"><span data-stu-id="b922e-160">Titre</span></span> | <span data-ttu-id="b922e-161">Titre</span><span class="sxs-lookup"><span data-stu-id="b922e-161">Titre</span></span>         | <span data-ttu-id="b922e-162">Statut d’acceptation du comptable</span><span class="sxs-lookup"><span data-stu-id="b922e-162">Accountant acceptance status</span></span> | <span data-ttu-id="b922e-163">« Rejeté(e) »</span><span class="sxs-lookup"><span data-stu-id="b922e-163">"Rejected"</span></span> |





