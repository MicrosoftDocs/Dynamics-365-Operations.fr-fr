---
title: "Créer et traiter une conformité"
description: "Utilisez cette procédure pour effectuer la gestion de non-conformité, en fonction d'un ordre de qualité existant."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e5187c44aac881273900b2fc0ca91045a65cd838
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-and-process-a-conformance"></a><span data-ttu-id="625d5-103">Créer et traiter une conformité</span><span class="sxs-lookup"><span data-stu-id="625d5-103">Create and process a conformance</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="625d5-104">Utilisez cette procédure pour effectuer la gestion de non-conformité, en fonction d'un ordre de qualité existant.</span><span class="sxs-lookup"><span data-stu-id="625d5-104">Use this procedure to perform nonconformance management, based on an existing quality order.</span></span> <span data-ttu-id="625d5-105">Vous pouvez exécuter cet enregistrement de la société de démonstration USMF et utiliser les valeurs suggérées.</span><span class="sxs-lookup"><span data-stu-id="625d5-105">You can run this recording in the USMF demo company and can use the suggested values.</span></span> <span data-ttu-id="625d5-106">Généralement, cette procédure est réalisée par le commis à la qualité.</span><span class="sxs-lookup"><span data-stu-id="625d5-106">Typically, this procedure is performed by a quality clerk.</span></span>  <span data-ttu-id="625d5-107">Comme préalable, exécutez l'enregistrement de la tâche « Inspecter la qualité des marchandises ».</span><span class="sxs-lookup"><span data-stu-id="625d5-107">As a prerequisite, run the “Inspect the quality of goods” task recording.</span></span> <span data-ttu-id="625d5-108">Pour traiter l'approbation d'une non-conformité, l'utilisateur qui exécute l'enregistrement de la tâche doit spécifier une valeur « Nom » affectée sur la page Utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="625d5-108">To process the approval of a nonconformance, the user who runs the task recording must have a “Name” value assigned on the Users page.</span></span> <span data-ttu-id="625d5-109">Pour utiliser les notes de document, l'utilisateur doit également avoir activé la gestion des documents dans les options d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="625d5-109">To use the document notes, the user must also have Document handling activated in the user options.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="625d5-110">Sélectionnez un ordre de qualité.</span><span class="sxs-lookup"><span data-stu-id="625d5-110">Select a quality order</span></span>
1. <span data-ttu-id="625d5-111">Accédez à Ordres de qualité.</span><span class="sxs-lookup"><span data-stu-id="625d5-111">Go to Quality orders.</span></span>
2. <span data-ttu-id="625d5-112">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="625d5-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="625d5-113">Sélectionnez l'ordre de qualité créé à partir de l'enregistrement de la tâche « Inspecter la qualité des marchandises ».</span><span class="sxs-lookup"><span data-stu-id="625d5-113">Select the quality order that was created from the "Inspect the quality of goods" task recording.</span></span>  

## <a name="create-a-nonconformance"></a><span data-ttu-id="625d5-114">Créer une non-conformité</span><span class="sxs-lookup"><span data-stu-id="625d5-114">Create a nonconformance</span></span>
1. <span data-ttu-id="625d5-115">Cliquez sur Recherches.</span><span class="sxs-lookup"><span data-stu-id="625d5-115">Click Inquiries.</span></span>
2. <span data-ttu-id="625d5-116">Cliquez sur Non-conformités.</span><span class="sxs-lookup"><span data-stu-id="625d5-116">Click Non conformances.</span></span>
3. <span data-ttu-id="625d5-117">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="625d5-117">Click New.</span></span>
4. <span data-ttu-id="625d5-118">Dans le champ Type de problème, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="625d5-118">In the Problem type field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="625d5-119">Sélectionnez le problème qui a été indiqué lors du processus d'inspection.</span><span class="sxs-lookup"><span data-stu-id="625d5-119">Select the problem that was found during the inspection process.</span></span>  
5. <span data-ttu-id="625d5-120">Dans le champ Type de problème, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="625d5-120">In the Problem type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="625d5-121">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="625d5-121">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="625d5-122">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="625d5-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="625d5-123">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="625d5-123">Click OK.</span></span>

## <a name="approvereject-a-nonconformance"></a><span data-ttu-id="625d5-124">Approuver/rejeter une non-conformité</span><span class="sxs-lookup"><span data-stu-id="625d5-124">Approve/reject a nonconformance</span></span>
1. <span data-ttu-id="625d5-125">Cliquez sur Fonctions.</span><span class="sxs-lookup"><span data-stu-id="625d5-125">Click Functions.</span></span>
2. <span data-ttu-id="625d5-126">Cliquez sur Approuver la non-conformité.</span><span class="sxs-lookup"><span data-stu-id="625d5-126">Click Approve non conformance.</span></span>
    * <span data-ttu-id="625d5-127">Pour cet exemple, approuvez la non-conformité.</span><span class="sxs-lookup"><span data-stu-id="625d5-127">For this example, approve the nonconformance.</span></span> <span data-ttu-id="625d5-128">Les non-conformités approuvées peuvent être associées à des opérations associées au travail d'enregistrement qui est exécuté dans le cadre de la gestion de la non-conformité et, comme dans cet enregistrement de tâche, le traitement de la gestion des corrections.</span><span class="sxs-lookup"><span data-stu-id="625d5-128">Approved nonconformances can be associated with related operations to record work that is done as part of the nonconformance handling and, as in this task recording, the processing of correction handling.</span></span>  
3. <span data-ttu-id="625d5-129">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="625d5-129">Click Yes.</span></span>

## <a name="create-a-correction-action"></a><span data-ttu-id="625d5-130">Créer une action de correction</span><span class="sxs-lookup"><span data-stu-id="625d5-130">Create a correction action</span></span>
1. <span data-ttu-id="625d5-131">Cliquez sur Corrections.</span><span class="sxs-lookup"><span data-stu-id="625d5-131">Click Corrections.</span></span>
2. <span data-ttu-id="625d5-132">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="625d5-132">Click New.</span></span>
3. <span data-ttu-id="625d5-133">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="625d5-133">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="625d5-134">Dans le champ Numéro personnel, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="625d5-134">In the Personnel number field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="625d5-135">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="625d5-135">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="625d5-136">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="625d5-136">Click Select.</span></span>
7. <span data-ttu-id="625d5-137">Cliquez Joindre.</span><span class="sxs-lookup"><span data-stu-id="625d5-137">Click Attach.</span></span>
    * <span data-ttu-id="625d5-138">Créez une remarque sur la correction.</span><span class="sxs-lookup"><span data-stu-id="625d5-138">Create a note about the correction.</span></span> <span data-ttu-id="625d5-139">Pour cet exemple, l'action consiste à contacter le fournisseur pour présenter l'incident de non-conformité.</span><span class="sxs-lookup"><span data-stu-id="625d5-139">For this example, the action is to contact the vendor to discuss the nonconformance case.</span></span>  
8. <span data-ttu-id="625d5-140">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="625d5-140">Click New.</span></span>
9. <span data-ttu-id="625d5-141">Cliquez sur Remarque.</span><span class="sxs-lookup"><span data-stu-id="625d5-141">Click Note.</span></span>
    * <span data-ttu-id="625d5-142">Notez que selon le paramétrage d'état, différents types de documents peuvent être imprimés sur les états associés à la gestion de non-conformité.</span><span class="sxs-lookup"><span data-stu-id="625d5-142">Note that, depending on the report setup, different document types can be printed on the reports that are related to nonconformance management.</span></span>  
10. <span data-ttu-id="625d5-143">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="625d5-143">In the Description field, type a value.</span></span>
11. <span data-ttu-id="625d5-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="625d5-144">Close the page.</span></span>

## <a name="maintain-a-correction"></a><span data-ttu-id="625d5-145">Maintenir une correction</span><span class="sxs-lookup"><span data-stu-id="625d5-145">Maintain a correction</span></span>
1. <span data-ttu-id="625d5-146">Cliquez sur Marquer comme terminé.</span><span class="sxs-lookup"><span data-stu-id="625d5-146">Click Mark complete.</span></span>
2. <span data-ttu-id="625d5-147">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="625d5-147">Click OK.</span></span>
3. <span data-ttu-id="625d5-148">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="625d5-148">Close the page.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="625d5-149">Clôturer une non-conformité</span><span class="sxs-lookup"><span data-stu-id="625d5-149">Close a nonconformance</span></span>
1. <span data-ttu-id="625d5-150">Cliquez sur Fonctions.</span><span class="sxs-lookup"><span data-stu-id="625d5-150">Click Functions.</span></span>
2. <span data-ttu-id="625d5-151">Cliquez sur Clôturer la non-conformité.</span><span class="sxs-lookup"><span data-stu-id="625d5-151">Click Close non conformance.</span></span>
3. <span data-ttu-id="625d5-152">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="625d5-152">Click Yes.</span></span>
4. <span data-ttu-id="625d5-153">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="625d5-153">Close the page.</span></span>
5. <span data-ttu-id="625d5-154">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="625d5-154">Close the page.</span></span>

