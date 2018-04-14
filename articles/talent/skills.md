---
title: Aligner les qualifications du personnel sur les besoins de l'entreprise
description: "Vous pouvez suivre les qualifications que les travailleurs, les candidats ou les personnes à contacter ont ou doivent avoir pour assumer efficacement leurs rôles. Vous pouvez également spécifier les qualifications requises pour une tâche spécifique."
author: kherr75
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 3a5b9f98b371dbad9b6b0538e0d9975dc5ed701c
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="align-workforce-skills-with-business-needs"></a><span data-ttu-id="ab08e-104">Aligner les qualifications du personnel sur les besoins de l'entreprise</span><span class="sxs-lookup"><span data-stu-id="ab08e-104">Align workforce skills with business needs</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="ab08e-105">Vous pouvez suivre les qualifications que les travailleurs, les candidats ou les personnes à contacter ont ou doivent avoir pour assumer efficacement leurs rôles.</span><span class="sxs-lookup"><span data-stu-id="ab08e-105">You can track the skills that workers, applicants, or contact persons have, or should have, to fulfill their roles effectively.</span></span> <span data-ttu-id="ab08e-106">Vous pouvez également spécifier les qualifications requises pour une tâche spécifique.</span><span class="sxs-lookup"><span data-stu-id="ab08e-106">You can also specify the skills that are required for a specific job.</span></span>

<span data-ttu-id="ab08e-107">Les exemples de qualifications que vous pouvez suivre sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="ab08e-107">Examples of skills you can track include the following:</span></span>
-   <span data-ttu-id="ab08e-108">Supervision – Capacité de superviser le travail des autres.</span><span class="sxs-lookup"><span data-stu-id="ab08e-108">Supervisory – Ability to supervise the work of others.</span></span>
-   <span data-ttu-id="ab08e-109">Leadership – Capacité de diriger des employés et des secteurs d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="ab08e-109">Leadership – Ability to lead employees and business domains.</span></span>
-   <span data-ttu-id="ab08e-110">Planification – Capacité de réfléchir à l'avenir, de formuler des visions et de les mener à bien.</span><span class="sxs-lookup"><span data-stu-id="ab08e-110">Planning – Ability to look ahead, to form visions, and to see them through.</span></span>
-   <span data-ttu-id="ab08e-111">HTML – Capacité d'écrire du code HTML.</span><span class="sxs-lookup"><span data-stu-id="ab08e-111">HTML – Ability to write HTML code.</span></span>

<span data-ttu-id="ab08e-112">Avant d'affecter une qualification à une personne ou une tâche, de créer une recherche de mise en correspondance des qualifications ou de créer un profil de qualification, vous devez entrer des informations sur les qualifications dans la page **Qualifications**.</span><span class="sxs-lookup"><span data-stu-id="ab08e-112">Before you can assign a skill to a person or a job, create a skill-mapping search, or create a skill profile, you must enter information about the skills on the **Skills** page.</span></span> <span data-ttu-id="ab08e-113">Pour chaque qualification, vous pouvez sélectionner un type de qualification et un modèle de classement.</span><span class="sxs-lookup"><span data-stu-id="ab08e-113">For each skill, you can select a skill type and a rating model.</span></span>

## <a name="rating-models"></a><span data-ttu-id="ab08e-114">Modèles de classement</span><span class="sxs-lookup"><span data-stu-id="ab08e-114">Rating models</span></span>
<span data-ttu-id="ab08e-115">Le fait de classer les modèles permet d'évaluer le niveau de qualification réel d'une personne, le niveau qu'ils doivent atteindre, ou le niveau de la qualification nécessaire pour une tâche.</span><span class="sxs-lookup"><span data-stu-id="ab08e-115">Rating models help evaluate a person's actual level of skill, the level they should work to achieve, or the level of skill that is required for a job.</span></span> <span data-ttu-id="ab08e-116">Vous pouvez entrer jusqu'à 10 niveaux pour un modèle de classement.</span><span class="sxs-lookup"><span data-stu-id="ab08e-116">You can enter up to 10 levels for a rating model.</span></span>  <span data-ttu-id="ab08e-117">Un facteur est affecté à chaque niveau dans un modèle de classement.</span><span class="sxs-lookup"><span data-stu-id="ab08e-117">Each level in a rating model is assigned a factor.</span></span>  <span data-ttu-id="ab08e-118">La valeur de facteur sera utilisée pour normaliser les scores de compétences qui utilisent différents modèles de classement.</span><span class="sxs-lookup"><span data-stu-id="ab08e-118">The factor value will be used to normalize the scores of skills that use different rating models.</span></span>  <span data-ttu-id="ab08e-119">Le facteur doit être un numéro compris entre 0 et 9 et chaque niveau doit avoir un facteur unique.</span><span class="sxs-lookup"><span data-stu-id="ab08e-119">The factor must be a number between 0-9 and each level must have a unique factor.</span></span>  <span data-ttu-id="ab08e-120">Les niveaux avec des valeurs de facteur plus élevées ont plus de poids dans un modèle de classement.</span><span class="sxs-lookup"><span data-stu-id="ab08e-120">Levels with higher factor values carry more weight in a rating model.</span></span>

## <a name="specify-job-skills"></a><span data-ttu-id="ab08e-121">Spécification des qualifications requises pour une tâche</span><span class="sxs-lookup"><span data-stu-id="ab08e-121">Specify job skills</span></span>
<span data-ttu-id="ab08e-122">Lorsque vous entrez des informations sur une tâche, vous pouvez spécifier les qualifications qu'une personne doit avoir pour exécuter le travail requis par la tâche.</span><span class="sxs-lookup"><span data-stu-id="ab08e-122">When you enter information about a job, you can specify the skills that a person should have to perform the work required for the job.</span></span>  <span data-ttu-id="ab08e-123">En outre, vous pouvez spécifier le niveau désiré pour chaque qualification, ainsi que le niveau d'importance de la qualification.</span><span class="sxs-lookup"><span data-stu-id="ab08e-123">In addition you can specify the desired level for each skill as well the level of importance of the skill.</span></span> <span data-ttu-id="ab08e-124">Différents postes peuvent nécessiter différents niveaux d'importance d'une même qualification.</span><span class="sxs-lookup"><span data-stu-id="ab08e-124">Different jobs can require different levels of importance for the same skill.</span></span>

## <a name="enter-skills-for-workers-applicants-or-contacts"></a><span data-ttu-id="ab08e-125">Saisie de qualifications pour les travailleurs, les candidats, ou les contacts</span><span class="sxs-lookup"><span data-stu-id="ab08e-125">Enter skills for workers, applicants, or contacts</span></span>
<span data-ttu-id="ab08e-126">Vous pouvez entrer des qualifications cibles ou des qualifications réelles pour les travailleurs, les candidats, ou les contacts.</span><span class="sxs-lookup"><span data-stu-id="ab08e-126">You can enter target skills or actual skills for workers, applicants, or contacts.</span></span> <span data-ttu-id="ab08e-127">Une qualification cible est une qualification que la personne envisage d'acquérir.</span><span class="sxs-lookup"><span data-stu-id="ab08e-127">A target skill is a skill that a person plans to achieve.</span></span> <span data-ttu-id="ab08e-128">Une qualification réelle est une qualification qu'une personne possède actuellement.</span><span class="sxs-lookup"><span data-stu-id="ab08e-128">An actual skill is a skill that a person currently has.</span></span>

## <a name="skill-mapping-and-skill-mapping-profiles"></a><span data-ttu-id="ab08e-129"> Mise en correspondance des qualifications et profils de mise en correspondance des qualifications</span><span class="sxs-lookup"><span data-stu-id="ab08e-129">Skill mapping and Skill mapping profiles</span></span>
<span data-ttu-id="ab08e-130">Vous pouvez créer une recherche de mise en correspondance des qualifications pour rechercher un collaborateur, un candidat, ou une personne à contacter qui est qualifiée pour effectuer un type de tâche spécifique de tâche.</span><span class="sxs-lookup"><span data-stu-id="ab08e-130">You can create a skill-mapping search to find a worker, applicant, or contact person who is qualified to perform a specific type of task.</span></span> <span data-ttu-id="ab08e-131">Le recherche de mise en correspondance des qualifications étudie les compétences, la formation, les certificats, les postes de confiance et l'expérience sur le projet et renvoie des résultats qui correspondent aux critères entrés.</span><span class="sxs-lookup"><span data-stu-id="ab08e-131">Skill-mapping searches look across skills, education, certificates, positions of trust and project experience and return results that match the criteria entered.</span></span>  <span data-ttu-id="ab08e-132">Par exemple, il peut être utile de savoir quels collaborateurs de votre organisation ont un diplôme de comptabilité.</span><span class="sxs-lookup"><span data-stu-id="ab08e-132">For example, it might be useful to know which workers in your organization earned their CPA.</span></span>

<span data-ttu-id="ab08e-133">Les profils de mise en correspondance des qualifications vous permettent de rechercher les employés actuels ou les candidats dont les qualifications correspondent directement aux besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="ab08e-133">Skill-mapping profiles allow you to find current employees or candidates with qualifications that directly correspond to business needs.</span></span>  <span data-ttu-id="ab08e-134">Par exemple, vous pouvez créer un profil de mise en correspondance des qualifications pour un poste vacant de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ab08e-134">For example, you could create a skill-mapping profile for an open position in your organization.</span></span> <span data-ttu-id="ab08e-135">En créant un profil pour une tâche spécifique et en copiant les qualifications, les formations et les certificats de cette tâche dans le profil, vous pouvez rechercher rapidement des travailleurs, des candidats et des personnes à contacter qui correspondent à un ou plusieurs des critères entrés dans le profil et afficher la liste des candidats dont les qualifications correspondent le mieux aux qualifications requises pour la tâche.</span><span class="sxs-lookup"><span data-stu-id="ab08e-135">By creating a profile for a particular job and copying the skills, education and certificates from that job to the profile, you can quickly search workers, applicants and contact persons who match one or more of the criteria entered on the profile and view a list of the candidates whose skills most closely match the skills required for the job.</span></span>

> <span data-ttu-id="ab08e-136">**Remarque** Seuls les travailleurs, les candidats, les personnes à contacter sélectionnés pour être inclus dans les recherches de mise en correspondance des qualifications peuvent être affichés dans la liste des résultats de la mise en correspondance des qualifications ou être inclus dans un profil de qualification.</span><span class="sxs-lookup"><span data-stu-id="ab08e-136">**Note** Only workers, applicants, and contact persons who are selected to be included in skill mapping searches can be displayed in a skill-mapping results list, or included in a skill profile.</span></span> <span data-ttu-id="ab08e-137">Pour inclure un travailleur, un candidat ou une personne à contacter dans les recherches de mise en correspondance des qualifications, définissez l'option **Inclure dans la mise en correspondance des qualifications** sur Oui dans les pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="ab08e-137">To include a worker, applicant, or contact person in skill mapping searches, set the **Include in skill mapping** selection to Yes in the following pages:</span></span>
> 
> + <span data-ttu-id="ab08e-138">Collaborateur</span><span class="sxs-lookup"><span data-stu-id="ab08e-138">Worker</span></span>
> + <span data-ttu-id="ab08e-139">Employé</span><span class="sxs-lookup"><span data-stu-id="ab08e-139">Employee</span></span>
> + <span data-ttu-id="ab08e-140">Candidat</span><span class="sxs-lookup"><span data-stu-id="ab08e-140">Applicant</span></span>
> + <span data-ttu-id="ab08e-141">contacts ;</span><span class="sxs-lookup"><span data-stu-id="ab08e-141">Contacts</span></span>

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a><span data-ttu-id="ab08e-142">Analyse des écarts de qualification et analyse des profils de qualification</span><span class="sxs-lookup"><span data-stu-id="ab08e-142">Skill gap analysis and skill profile analysis</span></span>
<span data-ttu-id="ab08e-143">Vous pouvez créer une analyse des profils de qualification pour afficher la liste des compétences d'un travailleur, d'un candidat ou d'une personne à contacter à une date spécifique.</span><span class="sxs-lookup"><span data-stu-id="ab08e-143">You can create a skill profile analysis to view a list of the competencies of a worker, applicant, or contact person as of a specific date.</span></span> <span data-ttu-id="ab08e-144">Vous pouvez créer une analyse des écarts de qualification pour comparer les qualifications d'une personne aux qualifications requises pour une tâche donnée.</span><span class="sxs-lookup"><span data-stu-id="ab08e-144">You can create a skill gap analysis to compare a person’s skills and the skills that are required for a specific job.</span></span>  



<a name="see-also"></a><span data-ttu-id="ab08e-145">Voir également :</span><span class="sxs-lookup"><span data-stu-id="ab08e-145">See also</span></span>
--------

[<span data-ttu-id="ab08e-146">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="ab08e-146">Human resources</span></span>](index.md)




