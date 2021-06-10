---
title: Configurer les compétences
description: Vous pouvez suivre les compétences de votre collaborateur dans Dynamics 365 Human Resources. Vous pouvez également spécifier les compétences requises pour une tâche spécifique.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 816822d1f3d365b4c5571c13e9f596e1c5d5e59c
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076557"
---
# <a name="configure-skills"></a><span data-ttu-id="2332a-104">Configurer les compétences</span><span class="sxs-lookup"><span data-stu-id="2332a-104">Configure skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="2332a-105">Vous pouvez suivre les compétences de votre collaborateur dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2332a-105">You can track your worker's skills in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="2332a-106">Vous pouvez également spécifier les compétences requises pour une tâche spécifique.</span><span class="sxs-lookup"><span data-stu-id="2332a-106">You can also specify the skills that are required for a specific job.</span></span>

<span data-ttu-id="2332a-107">Voici des exemples de compétences que vous pouvez suivre :</span><span class="sxs-lookup"><span data-stu-id="2332a-107">Examples of skills you can track include:</span></span>

- <span data-ttu-id="2332a-108">Supervision – Capacité de superviser le travail des autres.</span><span class="sxs-lookup"><span data-stu-id="2332a-108">Supervisory – Ability to supervise the work of others.</span></span>
- <span data-ttu-id="2332a-109">Leadership – Capacité de diriger des employés et des secteurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="2332a-109">Leadership – Ability to lead employees and business domains.</span></span>
- <span data-ttu-id="2332a-110">Planification – Capacité à anticiper les choses, à former des énoncés de vision et à les mener à bien.</span><span class="sxs-lookup"><span data-stu-id="2332a-110">Planning – Ability to look ahead, to form vision statements, and to see them through.</span></span>
- <span data-ttu-id="2332a-111">HTML – Capacité d’écrire du code HTML.</span><span class="sxs-lookup"><span data-stu-id="2332a-111">HTML – Ability to write HTML code.</span></span>

<span data-ttu-id="2332a-112">Si vous n’avez pas déjà configuré des types de compétences et des modèles d’évaluation, vous devrez en ajouter avant de créer des compétences.</span><span class="sxs-lookup"><span data-stu-id="2332a-112">If you haven't already set up skill types and rating models, you'll need to add some before creating skills.</span></span>

<span data-ttu-id="2332a-113">Les personnes suivantes peuvent saisir des compétences pour un collaborateur :</span><span class="sxs-lookup"><span data-stu-id="2332a-113">The following people can enter skills for a worker:</span></span>

- <span data-ttu-id="2332a-114">Les collaborateurs peuvent saisir des compétences pour eux-mêmes dans le libre-service des employés.</span><span class="sxs-lookup"><span data-stu-id="2332a-114">Workers can enter skills for themselves in Employee self-service.</span></span> <span data-ttu-id="2332a-115">Ces compétences nécessitent l’approbation du responsable.</span><span class="sxs-lookup"><span data-stu-id="2332a-115">These skills require manager approval.</span></span>
- <span data-ttu-id="2332a-116">Les responsables peuvent saisir des compétences pour leurs collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="2332a-116">Managers can enter skills for their workers.</span></span> <span data-ttu-id="2332a-117">Vous pouvez créer un flux de travail qui approuve automatiquement ces compétences.</span><span class="sxs-lookup"><span data-stu-id="2332a-117">You can create a workflow that auto-approves these skills.</span></span>

## <a name="create-a-skill-type"></a><span data-ttu-id="2332a-118">Créer un type de compétence</span><span class="sxs-lookup"><span data-stu-id="2332a-118">Create a skill type</span></span>

<span data-ttu-id="2332a-119">Les types de compétences sont des catégories dans lesquelles entrent les compétences individuelles, telles que Administration ou Vente.</span><span class="sxs-lookup"><span data-stu-id="2332a-119">Skill types are categories that individual skills fall under, such as Administration or Sales.</span></span>

1. <span data-ttu-id="2332a-120">Dans l’espace de travail, **Perfectionnement de l’employé**, sélectionnez **Liens**.</span><span class="sxs-lookup"><span data-stu-id="2332a-120">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="2332a-121">Sous **Configuration des compétences**, sélectionnez **Types de compétences**.</span><span class="sxs-lookup"><span data-stu-id="2332a-121">Under **Competency setup**, select **Skill types**.</span></span>

3. <span data-ttu-id="2332a-122">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2332a-122">Select **New**.</span></span>

4. <span data-ttu-id="2332a-123">Complétez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="2332a-123">Complete the following fields:</span></span>

   - <span data-ttu-id="2332a-124">**Type de compétence** : entrez un nom pour le type de compétence.</span><span class="sxs-lookup"><span data-stu-id="2332a-124">**Skill type**: Enter a name for the skill type.</span></span>
   - <span data-ttu-id="2332a-125">**Description** : entrez une description pour le type de compétence.</span><span class="sxs-lookup"><span data-stu-id="2332a-125">**Description**: Enter a description for the skill type.</span></span>

5. <span data-ttu-id="2332a-126">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2332a-126">Select **Save**.</span></span>

## <a name="create-a-rating-model"></a><span data-ttu-id="2332a-127">Créer un modèle d’évaluation</span><span class="sxs-lookup"><span data-stu-id="2332a-127">Create a rating model</span></span>

<span data-ttu-id="2332a-128">Les modèles d’évaluation permettent d’évaluer le niveau de compétence réel d’une personne, le niveau qu’ils doivent atteindre, ou le niveau de compétence nécessaire pour une tâche.</span><span class="sxs-lookup"><span data-stu-id="2332a-128">Rating models help evaluate a person's actual level of skill, the level they should work to achieve, or the level of skill required for a job.</span></span> <span data-ttu-id="2332a-129">Un facteur est affecté à chaque niveau dans un modèle de classement.</span><span class="sxs-lookup"><span data-stu-id="2332a-129">Each level in a rating model is assigned a factor.</span></span>

1. <span data-ttu-id="2332a-130">Dans l’espace de travail, **Perfectionnement de l’employé**, sélectionnez **Liens**.</span><span class="sxs-lookup"><span data-stu-id="2332a-130">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="2332a-131">Sous **Configuration des compétences**, sélectionnez **Modèles d’évaluation**.</span><span class="sxs-lookup"><span data-stu-id="2332a-131">Under **Competency setup**, select **Rating models**.</span></span>

3. <span data-ttu-id="2332a-132">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2332a-132">Select **New**.</span></span>

4. <span data-ttu-id="2332a-133">Complétez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="2332a-133">Complete the following fields:</span></span>

   - <span data-ttu-id="2332a-134">**Évaluation** : entrez un nom pour le modèle d’évaluation, tel que **Compétences**.</span><span class="sxs-lookup"><span data-stu-id="2332a-134">**Rating**: Enter a name for the rating model, such as **Skills**.</span></span>
   - <span data-ttu-id="2332a-135">**Description** : entrez une description pour le modèle d’évaluation, telle que **Évaluations des compétences**.</span><span class="sxs-lookup"><span data-stu-id="2332a-135">**Description**: Enter a description for the rating model, such as **Skill ratings**.</span></span>

5. <span data-ttu-id="2332a-136">Dans la section **Niveaux**, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2332a-136">In the **Levels** section, select **New**.</span></span> <span data-ttu-id="2332a-137">Pour chaque niveau que vous souhaitez ajouter, complétez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="2332a-137">For each level you want to add, complete the following fields:</span></span>

   - <span data-ttu-id="2332a-138">**Niveau** : entrez un nom pour le niveau.</span><span class="sxs-lookup"><span data-stu-id="2332a-138">**Level**: Enter a name for the level.</span></span>
   - <span data-ttu-id="2332a-139">**Description** : entrez une description pour le niveau.</span><span class="sxs-lookup"><span data-stu-id="2332a-139">**Description**: Enter a description for the level.</span></span>
   - <span data-ttu-id="2332a-140">**Facteur** : entrez une valeur de facteur comprise entre 0 et 9.</span><span class="sxs-lookup"><span data-stu-id="2332a-140">**Factor**: Enter a factor value from 0-9.</span></span> <span data-ttu-id="2332a-141">Les facteurs aident à normaliser les scores de compétences qui utilisent différents modèles d’évaluation.</span><span class="sxs-lookup"><span data-stu-id="2332a-141">Factors help normalize the scores of skills that use different rating models.</span></span> <span data-ttu-id="2332a-142">Chaque niveau doit avoir un facteur unique.</span><span class="sxs-lookup"><span data-stu-id="2332a-142">Each level must have a unique factor.</span></span> <span data-ttu-id="2332a-143">Les niveaux avec des valeurs de facteur plus élevées ont plus de poids dans un modèle de classement.</span><span class="sxs-lookup"><span data-stu-id="2332a-143">Levels with higher factor values carry more weight in a rating model.</span></span>

   <span data-ttu-id="2332a-144">Continuez à ajouter des niveaux si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="2332a-144">Continue adding levels as necessary.</span></span> <span data-ttu-id="2332a-145">Vous pouvez entrer jusqu’à 10 niveaux pour chaque modèle d’évaluation.</span><span class="sxs-lookup"><span data-stu-id="2332a-145">You can enter up to 10 levels for each rating model.</span></span>

6. <span data-ttu-id="2332a-146">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2332a-146">Select **Save**.</span></span>

## <a name="create-a-skill"></a><span data-ttu-id="2332a-147">Créer une compétence</span><span class="sxs-lookup"><span data-stu-id="2332a-147">Create a skill</span></span>

<span data-ttu-id="2332a-148">Avant d’affecter une compétence, de créer une recherche par mise en correspondance des compétences ou de créer un profil de compétence, vous devez entrer des informations sur les compétences dans la page **Compétences**.</span><span class="sxs-lookup"><span data-stu-id="2332a-148">Before you can assign a skill, or create a skill-mapping search or skill profile, you must enter information about the skills on the **Skills** page.</span></span> <span data-ttu-id="2332a-149">Pour chaque compétence, vous pouvez sélectionner un type de compétence et un modèle de classement.</span><span class="sxs-lookup"><span data-stu-id="2332a-149">For each skill, you can select a skill type and a rating model.</span></span>

1. <span data-ttu-id="2332a-150">Dans l’espace de travail, **Perfectionnement de l’employé**, sélectionnez **Liens**.</span><span class="sxs-lookup"><span data-stu-id="2332a-150">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="2332a-151">Sous **Configuration des compétences**, sélectionnez **Compétences**.</span><span class="sxs-lookup"><span data-stu-id="2332a-151">Under **Competency setup**, select **Skills**.</span></span>

3. <span data-ttu-id="2332a-152">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2332a-152">Select **New**.</span></span>

4. <span data-ttu-id="2332a-153">Complétez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="2332a-153">Complete the following fields:</span></span>

   - <span data-ttu-id="2332a-154">**Compétence** : entrez un nom pour la compétence.</span><span class="sxs-lookup"><span data-stu-id="2332a-154">**Skill**: Enter a name for the skill.</span></span>
   - <span data-ttu-id="2332a-155">**Description** : entrez une description pour la compétence.</span><span class="sxs-lookup"><span data-stu-id="2332a-155">**Description**: Enter a description for the skill.</span></span>
   - <span data-ttu-id="2332a-156">**Évaluation** : sélectionnez le modèle d’évaluation que vous souhaitez utiliser pour cette compétence.</span><span class="sxs-lookup"><span data-stu-id="2332a-156">**Rating**: Select the rating model you want to use for this skill.</span></span>
   - <span data-ttu-id="2332a-157">**Type de compétence** : sélectionnez une option dans la liste des types de compétences.</span><span class="sxs-lookup"><span data-stu-id="2332a-157">**Skill type**: Select from the list of skill types.</span></span>

5. <span data-ttu-id="2332a-158">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2332a-158">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="2332a-159">Voir également :</span><span class="sxs-lookup"><span data-stu-id="2332a-159">See also</span></span>

[<span data-ttu-id="2332a-160">Saisir les compétences</span><span class="sxs-lookup"><span data-stu-id="2332a-160">Enter skills</span></span>](hr-develop-enter-skills.md)<br>
[<span data-ttu-id="2332a-161">Mettre en correspondance les compétences</span><span class="sxs-lookup"><span data-stu-id="2332a-161">Map skills</span></span>](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]