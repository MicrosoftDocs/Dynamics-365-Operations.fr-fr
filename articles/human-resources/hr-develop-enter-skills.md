---
title: Saisir les compétences
description: Les collaborateurs et les responsables peuvent saisir des compétences dans Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: b24d37292a2e9749fb2fde06b9f03fcd13db0bbe
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076592"
---
# <a name="enter-skills"></a><span data-ttu-id="b36b4-103">Saisir les compétences</span><span class="sxs-lookup"><span data-stu-id="b36b4-103">Enter skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b36b4-104">Vous pouvez saisir des compétences cibles ou des compétences réelles pour les collaborateurs, les candidats ou les contacts dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b36b4-104">You can enter target skills or actual skills for workers, applicants, or contacts in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="b36b4-105">Une compétence cible est une compétence que la personne envisage d’acquérir.</span><span class="sxs-lookup"><span data-stu-id="b36b4-105">A target skill is a skill that a person plans to achieve.</span></span> <span data-ttu-id="b36b4-106">Une compétence réelle est une compétence qu’une personne possède actuellement.</span><span class="sxs-lookup"><span data-stu-id="b36b4-106">An actual skill is a skill that a person currently has.</span></span>

## <a name="create-a-workflow-to-auto-approve-skills"></a><span data-ttu-id="b36b4-107">Créer un flux de travail pour approuver automatiquement les compétences</span><span class="sxs-lookup"><span data-stu-id="b36b4-107">Create a workflow to auto-approve skills</span></span>

<span data-ttu-id="b36b4-108">Pour saisir des compétences sans nécessiter d’approbation, vous devez créer un flux de travail pour approuver automatiquement les compétences.</span><span class="sxs-lookup"><span data-stu-id="b36b4-108">To enter skills without requiring approval, you must create a workflow to auto-approve skills.</span></span>

> [!NOTE]
> <span data-ttu-id="b36b4-109">Les compétences saisies par les collaborateurs nécessitent toujours l’approbation du responsable.</span><span class="sxs-lookup"><span data-stu-id="b36b4-109">Skills entered by workers always require manager approval.</span></span> <span data-ttu-id="b36b4-110">Ce flux de travail n’approuve automatiquement que les compétences saisies par les responsables au nom de leurs collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="b36b4-110">This workflow only auto-approves skills entered by managers on behalf of their workers.</span></span>

1. <span data-ttu-id="b36b4-111">Dans l’espace de travail **Gestion du personnel**, sélectionnez **Liens**.</span><span class="sxs-lookup"><span data-stu-id="b36b4-111">In the **Personnel management** workspace, select **Links**.</span></span>

2. <span data-ttu-id="b36b4-112">Sous **Configuration**, sélectionnez **Flux de travail des ressources humaines**.</span><span class="sxs-lookup"><span data-stu-id="b36b4-112">Under **Setup**, select **Human resources workflows**.</span></span>

3. <span data-ttu-id="b36b4-113">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b36b4-113">Select **New**.</span></span>

4. <span data-ttu-id="b36b4-114">Dans le volet **Créer un flux de travail**, sélectionnez **Compétences du collaborateur**.</span><span class="sxs-lookup"><span data-stu-id="b36b4-114">In the **Create workflow** pane, select **Worker skills**.</span></span>

   <span data-ttu-id="b36b4-115">[![Sélectionner le flux de travail des compétences du collaborateur](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)</span><span class="sxs-lookup"><span data-stu-id="b36b4-115">[![Select Worker skills workflow](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)</span></span>

5. <span data-ttu-id="b36b4-116">Dans la boîte de dialogue **Ouvrir ce fichier ?**, sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="b36b4-116">In the **Open this file?** dialogue, select **Open**.</span></span> <span data-ttu-id="b36b4-117">Lorsque vous y êtes invité, entrez vos informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="b36b4-117">When prompted, enter your credentials.</span></span>

6. <span data-ttu-id="b36b4-118">Dans l’éditeur de flux de travail, sélectionnez l’élément de flux de travail **Approuver les compétences** et faites-le glisser sur le canevas.</span><span class="sxs-lookup"><span data-stu-id="b36b4-118">In the workflow editor, select the **Approve skills** workflow element and drag it onto the canvas.</span></span>

   <span data-ttu-id="b36b4-119">[![Sélectionner l’élément de flux de travail Approuver les compétences](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)</span><span class="sxs-lookup"><span data-stu-id="b36b4-119">[![Select Approve skills workflow element](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)</span></span>

7. <span data-ttu-id="b36b4-120">Connectez l’élément **Début** à l’élément **Approuver les compétences 1**, puis connectez l’élément **Approuver les compétences 1** à l’élément **Fin**.</span><span class="sxs-lookup"><span data-stu-id="b36b4-120">Connect the **Start** element to the **Approve skills 1** element, and then connect the **Approve skills 1** element to the **End** element.</span></span> <span data-ttu-id="b36b4-121">Vous devrez peut-être faire défiler vers le bas pour voir l’élément **Fin**.</span><span class="sxs-lookup"><span data-stu-id="b36b4-121">You might need to scroll down to see the **End** element.</span></span> <span data-ttu-id="b36b4-122">Vous pouvez le faire glisser plus près des autres éléments.</span><span class="sxs-lookup"><span data-stu-id="b36b4-122">You can drag it closer to the other elements.</span></span>

   <span data-ttu-id="b36b4-123">[![Connecter les éléments du flux de travail](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)</span><span class="sxs-lookup"><span data-stu-id="b36b4-123">[![Connect workflow elements](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)</span></span>

8. <span data-ttu-id="b36b4-124">Double-cliquez sur l’élément de flux de travail **Approuver les compétences 1**, puis cliquez avec le bouton droit sur l’élément **Étape 1**.</span><span class="sxs-lookup"><span data-stu-id="b36b4-124">Double-click the **Approve skills 1** workflow element, and then right-click the **Step 1** element.</span></span> <span data-ttu-id="b36b4-125">Cliquez avec le bouton droit sur l’élément **Étape 1**, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b36b4-125">Right-click the **Step 1** element, and then select **Properties**.</span></span>

9. <span data-ttu-id="b36b4-126">Dans la fenêtre **Propriétés**, sélectionnez **Condition** dans la barre de navigation de gauche.</span><span class="sxs-lookup"><span data-stu-id="b36b4-126">In the **Properties** window, select **Condition** on the left-hand nav bar.</span></span>

10. <span data-ttu-id="b36b4-127">Sélectionnez **Exécuter cette étape uniquement si la condition suivante est remplie**.</span><span class="sxs-lookup"><span data-stu-id="b36b4-127">Select **Run this step only when the following condition is met**.</span></span>

11. <span data-ttu-id="b36b4-128">Sélectionnez **Ajouter une condition**.</span><span class="sxs-lookup"><span data-stu-id="b36b4-128">Select **Add condition**.</span></span> <span data-ttu-id="b36b4-129">Après **Où**, sélectionnez **Compétences du libre-service des employés**, puis sélectionnez **Compétences du libre-service des employés**.</span><span class="sxs-lookup"><span data-stu-id="b36b4-129">After **Where**, select **Employee self service skills**, and then select **Employee self service skills.Person**.</span></span> <span data-ttu-id="b36b4-130">Après **est**, sélectionnez **champ**, puis sélectionnez **Relation utilisateur/personne**.</span><span class="sxs-lookup"><span data-stu-id="b36b4-130">After **is**, select **field**, and then select **User to person relationship.Person**.</span></span>

    <span data-ttu-id="b36b4-131">[![Spécifier la condition](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)</span><span class="sxs-lookup"><span data-stu-id="b36b4-131">[![Specify condition](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)</span></span>

12. <span data-ttu-id="b36b4-132">Sélectionnez **Affectation** dans la barre de navigation de gauche.</span><span class="sxs-lookup"><span data-stu-id="b36b4-132">Select **Assignment** on the left-hand nav bar.</span></span>

13. <span data-ttu-id="b36b4-133">Dans l’onglet **Type d’affectation**, sélectionnez **Hiérarchie**.</span><span class="sxs-lookup"><span data-stu-id="b36b4-133">On the **Assignment type** tab, select **Hierarchy**.</span></span>

14. <span data-ttu-id="b36b4-134">Dans l’onglet **Sélection de la hiérarchie**, dans le champ **Type de hiérarchie :**, sélectionnez **Hiérarchie managériale**.</span><span class="sxs-lookup"><span data-stu-id="b36b4-134">On the **Hierarchy selection** tab, in the **Hierarchy type:** field, select **Managerial hierarchy**.</span></span>

    <span data-ttu-id="b36b4-135">[![Spécifier la hiérarchie managériale](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)</span><span class="sxs-lookup"><span data-stu-id="b36b4-135">[![Specify managerial hierarchy](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)</span></span>

15. <span data-ttu-id="b36b4-136">Sélectionnez **Fermer**, sélectionnez **Flux de travail** dans la barre de navigation du canevas, puis sélectionnez **Enregistrer et fermer**.</span><span class="sxs-lookup"><span data-stu-id="b36b4-136">Select **Close**, select **Workflow** in the canvas breadcrumb, and then select **Save and close**.</span></span>

<span data-ttu-id="b36b4-137">Pour plus d’informations sur la création de flux de travail, consultez [Vue d’ensemble du système de flux de travail](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system?toc=/dynamics365/human-resources/toc.json).</span><span class="sxs-lookup"><span data-stu-id="b36b4-137">For more information about creating workflows, see [Workflow system overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system?toc=/dynamics365/human-resources/toc.json).</span></span>

## <a name="enter-skills-for-a-worker"></a><span data-ttu-id="b36b4-138">Saisir les compétences d’un collaborateur</span><span class="sxs-lookup"><span data-stu-id="b36b4-138">Enter skills for a worker</span></span>

1. <span data-ttu-id="b36b4-139">Sélectionnez un collaborateur.</span><span class="sxs-lookup"><span data-stu-id="b36b4-139">Select a worker.</span></span>

2. <span data-ttu-id="b36b4-140">Dans la barre d’actions de la page **Collaborateur**, sélectionnez **Personne**, puis sélectionnez **Compétences**.</span><span class="sxs-lookup"><span data-stu-id="b36b4-140">In the action bar of the **Worker** page, select **Person**, and then select **Skills**.</span></span>

3. <span data-ttu-id="b36b4-141">Dans la page **Compétences**, complétez les champs suivants pour chaque compétence :</span><span class="sxs-lookup"><span data-stu-id="b36b4-141">On the **Skills** page, complete the following fields for each skill:</span></span>

   - <span data-ttu-id="b36b4-142">**Compétence** : sélectionnez une compétence.</span><span class="sxs-lookup"><span data-stu-id="b36b4-142">**Skill**: Select a skill.</span></span>
   - <span data-ttu-id="b36b4-143">**Type de niveau** : sélectionnez **Réel** pour une compétence que le collaborateur possède déjà, ou sélectionnez **Cible** pour une compétence que le collaborateur souhaite acquérir.</span><span class="sxs-lookup"><span data-stu-id="b36b4-143">**Level type**: Select **Actual** for a skill the worker already has, or select **Target** for a skill the worker is working toward.</span></span>
   - <span data-ttu-id="b36b4-144">**Niveau** : sélectionnez un niveau pour la compétence du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="b36b4-144">**Level**: Select a level for the worker's skill.</span></span>
   - <span data-ttu-id="b36b4-145">**Date du niveau** : sélectionnez une date dans l’outil de calendrier.</span><span class="sxs-lookup"><span data-stu-id="b36b4-145">**Level date**: Select a date in the calendar tool.</span></span>
   - <span data-ttu-id="b36b4-146">**Examinateur** : le cas échéant, sélectionnez un examinateur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="b36b4-146">**Examiner**: If appropriate, select an examiner from the list.</span></span> <span data-ttu-id="b36b4-147">Vous pouvez filtrer votre recherche.</span><span class="sxs-lookup"><span data-stu-id="b36b4-147">You can filter your search.</span></span>
   - <span data-ttu-id="b36b4-148">**Années d’expérience** : entrez les années d’expérience.</span><span class="sxs-lookup"><span data-stu-id="b36b4-148">**Years of experience**: Enter years of experience.</span></span>
   - <span data-ttu-id="b36b4-149">**Vérifiée** : si la compétence est vérifiée, cochez la case.</span><span class="sxs-lookup"><span data-stu-id="b36b4-149">**Verified**: If the skill is verified, check the box.</span></span>
   - <span data-ttu-id="b36b4-150">**Vérifiée par** : entrez le nom du vérificateur.</span><span class="sxs-lookup"><span data-stu-id="b36b4-150">**Verified by**: Enter the name of the verifier.</span></span>

4. <span data-ttu-id="b36b4-151">Lorsque vous avez terminé de saisir les compétences, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b36b4-151">When you're done entering skills, select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b36b4-152">Voir également :</span><span class="sxs-lookup"><span data-stu-id="b36b4-152">See also</span></span>

[<span data-ttu-id="b36b4-153">Configurer les compétences</span><span class="sxs-lookup"><span data-stu-id="b36b4-153">Configure skills</span></span>](hr-develop-skills.md)<br>
[<span data-ttu-id="b36b4-154">Mettre en correspondance les compétences</span><span class="sxs-lookup"><span data-stu-id="b36b4-154">Map skills</span></span>](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]