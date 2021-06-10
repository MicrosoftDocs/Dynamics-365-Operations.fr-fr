---
title: Distribuer des questionnaires à l’aide d’une planification
description: La planification de questionnaire vous permet de planifier et répartir les questionnaires entre plusieurs personnes interrogées.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMKnowledgeCollectorPlanningTable, KMKnowledgeCollectorPlanningMulti, SysQueryForm, HcmPersonLookup, KMKnowledgeCollectorPlanning, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 952048ce0a2ac94be70d7bde0dc52610f19151ed
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056298"
---
# <a name="distribute-questionnaires-using-scheduling"></a><span data-ttu-id="0e9da-103">Distribuer des questionnaires à l’aide d’une planification</span><span class="sxs-lookup"><span data-stu-id="0e9da-103">Distribute questionnaires using scheduling</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="0e9da-104">La planification de questionnaire vous permet de planifier et répartir les questionnaires entre plusieurs personnes interrogées.</span><span class="sxs-lookup"><span data-stu-id="0e9da-104">Questionnaire scheduling allows you to plan and distribute questionnaires to multiple respondents.</span></span> <span data-ttu-id="0e9da-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="0e9da-105">The demo data company used to create this procedure is USMF.</span></span>

## <a name="create-a-questionnaire-schedule"></a><span data-ttu-id="0e9da-106">Créer un programme de questionnaire</span><span class="sxs-lookup"><span data-stu-id="0e9da-106">Create a questionnaire schedule</span></span>

1. <span data-ttu-id="0e9da-107">Accédez à Questionnaire > Distribuer > Programmes de questionnaire.</span><span class="sxs-lookup"><span data-stu-id="0e9da-107">Go to Questionnaire > Distribute > Questionnaire schedules.</span></span>

2. <span data-ttu-id="0e9da-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="0e9da-108">Click New.</span></span>

3. <span data-ttu-id="0e9da-109">Dans le champ Planification, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0e9da-109">In the Scheduling field, type a value.</span></span>

4. <span data-ttu-id="0e9da-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0e9da-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="0e9da-111">Définissez le programme sur Anonyme si les réponses doivent être enregistrées sans noms associés à la réponse.</span><span class="sxs-lookup"><span data-stu-id="0e9da-111">Set the schedule to Anonymous if the responses should be recorded without names associated to the response.</span></span>  
    * <span data-ttu-id="0e9da-112">L’option Autoriser les résultats anonymes doit être définie dans les paramètres HR.</span><span class="sxs-lookup"><span data-stu-id="0e9da-112">Allowing anonymous results must be set up in the HR parameters first.</span></span>  

5. <span data-ttu-id="0e9da-113">Dans le champ Type, sélectionnez le type de planification.</span><span class="sxs-lookup"><span data-stu-id="0e9da-113">In the Type field, select the planning type.</span></span>  <span data-ttu-id="0e9da-114">Dans cet exemple, nous utiliserons le type Satisfaction.</span><span class="sxs-lookup"><span data-stu-id="0e9da-114">In this example we will use the Satisfaction type.</span></span>

6. <span data-ttu-id="0e9da-115">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="0e9da-115">In the list, find and select the desired record.</span></span>

7. <span data-ttu-id="0e9da-116">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0e9da-116">In the list, click the link in the selected row.</span></span>

8. <span data-ttu-id="0e9da-117">Entrez une date dans le champ Date.</span><span class="sxs-lookup"><span data-stu-id="0e9da-117">In the Date field, enter a date.</span></span>

9. <span data-ttu-id="0e9da-118">Développez la section E-mail pour le libre-service pour employés.</span><span class="sxs-lookup"><span data-stu-id="0e9da-118">Expand the Email for employee self service section.</span></span>

10. <span data-ttu-id="0e9da-119">Tapez une valeur dans le champ Objet.</span><span class="sxs-lookup"><span data-stu-id="0e9da-119">In the Subject field, type a value.</span></span>

    * <span data-ttu-id="0e9da-120">Exemple : questionnaire disponible</span><span class="sxs-lookup"><span data-stu-id="0e9da-120">Example: Questionnaire available</span></span>  

11. <span data-ttu-id="0e9da-121">Dans le champ Texte, tapez le corps de votre message électronique.</span><span class="sxs-lookup"><span data-stu-id="0e9da-121">In the Text field, type the body of your email message.</span></span> <span data-ttu-id="0e9da-122">Notez que la variable peut être utilisée pour remplacer les valeurs du système.</span><span class="sxs-lookup"><span data-stu-id="0e9da-122">Note, the variable can be used to substitue values in the system.</span></span>

    * <span data-ttu-id="0e9da-123">Exemple : Cher/chère %P%, connectez-vous au Libre-service employé pour compléter le questionnaire sur la santé du personnel.</span><span class="sxs-lookup"><span data-stu-id="0e9da-123">Example: Dear %P%, Please log in to Employee Self Service to complete the Workforce Health questionnaire.</span></span>  <span data-ttu-id="0e9da-124">Contoso</span><span class="sxs-lookup"><span data-stu-id="0e9da-124">Contoso</span></span>  

12. <span data-ttu-id="0e9da-125">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="0e9da-125">Click Save.</span></span>

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a><span data-ttu-id="0e9da-126">Utilisez les Détails de la configuration pour sélectionner les questionnaires auxquels répondre ainsi que toutes les requêtes à utiliser pour sélectionner les personnes interrogées.</span><span class="sxs-lookup"><span data-stu-id="0e9da-126">Use the Setup details to select the questionnaire(s) to be answered as well as any queries to use to select respondents.</span></span>

1. <span data-ttu-id="0e9da-127">Cliquez sur Détails de la configuration.</span><span class="sxs-lookup"><span data-stu-id="0e9da-127">Click Setup details.</span></span>

2. <span data-ttu-id="0e9da-128">Dans la liste, sélectionnez une requête à utiliser pour rechercher dans le système les personnes interrogées par le questionnaire.</span><span class="sxs-lookup"><span data-stu-id="0e9da-128">In the list, select a query to use to search the system for respondents for the questionnaire.</span></span>

    * <span data-ttu-id="0e9da-129">Exemple : collaborateurs</span><span class="sxs-lookup"><span data-stu-id="0e9da-129">Example: Workers</span></span>  

3. <span data-ttu-id="0e9da-130">Cliquez sur Afficher ou modifier la requête pour sélectionner des personnes spécifiques ou ajuster la requête pour rechercher des personnes qui correspondent à des critères spécifiques.</span><span class="sxs-lookup"><span data-stu-id="0e9da-130">Click View or modify query to select specific people or adjust the query to find people who match specific criteria.</span></span>

    * <span data-ttu-id="0e9da-131">Notez que toutes les personnes interrogées doivent aussi être des utilisateurs du système.</span><span class="sxs-lookup"><span data-stu-id="0e9da-131">Note that all respondents must also be users in the system.</span></span>  

4. <span data-ttu-id="0e9da-132">Dans la liste, marquez la ligne associée à Personne</span><span class="sxs-lookup"><span data-stu-id="0e9da-132">In the list, mark the row for Person</span></span>

5. <span data-ttu-id="0e9da-133">Dans le champ Critères, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0e9da-133">In the Criteria field, enter or select a value.</span></span>

    * <span data-ttu-id="0e9da-134">Sélectionner Julia Funderburk</span><span class="sxs-lookup"><span data-stu-id="0e9da-134">Select Julia Funderburk</span></span>  

6. <span data-ttu-id="0e9da-135">Dans la liste, sélectionnez Julia Funderburk</span><span class="sxs-lookup"><span data-stu-id="0e9da-135">In the list, select Julia Funderburk</span></span>

7. <span data-ttu-id="0e9da-136">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0e9da-136">Click OK.</span></span>

8. <span data-ttu-id="0e9da-137">Cliquez sur l’onglet Questionnaires.</span><span class="sxs-lookup"><span data-stu-id="0e9da-137">Click the Questionnaires tab.</span></span>

9. <span data-ttu-id="0e9da-138">Dans l’arborescence, développez le nœud du type de questionnaire Enquête de satisfaction.</span><span class="sxs-lookup"><span data-stu-id="0e9da-138">In the tree, expand 'the node for the questionnaire type Satisfaction Survey'.</span></span>

10. <span data-ttu-id="0e9da-139">Dans l’arborescence, cochez « Évaluation de la santé du personnel ».</span><span class="sxs-lookup"><span data-stu-id="0e9da-139">In the tree, check 'Workforce Health Assessment'.</span></span>

11. <span data-ttu-id="0e9da-140">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0e9da-140">Click OK.</span></span>

12. <span data-ttu-id="0e9da-141">Cliquez sur Session de réponse prévue.</span><span class="sxs-lookup"><span data-stu-id="0e9da-141">Click Planned answer session.</span></span>

    * <span data-ttu-id="0e9da-142">Notez que des sessions de réponse prévues ont été créées pour chaque utilisateur sélectionné/cherché.</span><span class="sxs-lookup"><span data-stu-id="0e9da-142">Note that Planned answer sessions have been created for each selected/queried user.</span></span>  

13. <span data-ttu-id="0e9da-143">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0e9da-143">Close the page.</span></span>

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a><span data-ttu-id="0e9da-144">Démarrez le programme de questionnaire afin de rendre le questionnaire disponible pour que les personnes interrogées le remplissent.</span><span class="sxs-lookup"><span data-stu-id="0e9da-144">Start the questionnaire schedule in order to make the questionnaire available for respondents to complete.</span></span>

1. <span data-ttu-id="0e9da-145">Cliquez sur Fonctions.</span><span class="sxs-lookup"><span data-stu-id="0e9da-145">Click Functions.</span></span>

2. <span data-ttu-id="0e9da-146">Cliquez sur Démarrer.</span><span class="sxs-lookup"><span data-stu-id="0e9da-146">Click Start.</span></span>

3. <span data-ttu-id="0e9da-147">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0e9da-147">Click OK.</span></span>

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a><span data-ttu-id="0e9da-148">Envoyez un e-mail pour informer les personnes interrogées que le questionnaire est disponible.</span><span class="sxs-lookup"><span data-stu-id="0e9da-148">Send the email to inform respondents of the available questionnaire.</span></span>

1. <span data-ttu-id="0e9da-149">Cliquez sur Fonctions.</span><span class="sxs-lookup"><span data-stu-id="0e9da-149">Click Functions.</span></span>

2. <span data-ttu-id="0e9da-150">Cliquez sur Envoyer un e-mail.</span><span class="sxs-lookup"><span data-stu-id="0e9da-150">Click Send email.</span></span>

3. <span data-ttu-id="0e9da-151">Cliquez sur Annuler.</span><span class="sxs-lookup"><span data-stu-id="0e9da-151">Click Cancel.</span></span>

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a><span data-ttu-id="0e9da-152">Utilisez les sessions de réponse prévues pour surveiller qui doit compléter le questionnaire.</span><span class="sxs-lookup"><span data-stu-id="0e9da-152">Use Planned answer sessions to monitor who needs to complete the questionnaire.</span></span>

1. <span data-ttu-id="0e9da-153">Cliquez sur Session de réponse prévue.</span><span class="sxs-lookup"><span data-stu-id="0e9da-153">Click Planned answer session.</span></span>

    * <span data-ttu-id="0e9da-154">Supprimez toutes les sessions de réponse prévue restantes lorsque vous êtes prêt à terminer la session planifiée.</span><span class="sxs-lookup"><span data-stu-id="0e9da-154">Delete any remaining planned answer session when you're ready to end the scheduled session.</span></span>  

2. <span data-ttu-id="0e9da-155">Cliquez sur Supprimer.</span><span class="sxs-lookup"><span data-stu-id="0e9da-155">Click Delete.</span></span>

3. <span data-ttu-id="0e9da-156">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="0e9da-156">Click Yes.</span></span>

4. <span data-ttu-id="0e9da-157">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0e9da-157">Close the page.</span></span>

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a><span data-ttu-id="0e9da-158">Terminez le programme lorsque toutes les personnes interrogées ont répondu au questionnaire et/ou toutes les sessions de réponse prévues restantes ont été supprimées.</span><span class="sxs-lookup"><span data-stu-id="0e9da-158">End the schedule when all respondents have completed the questionnaire and/or all remaining Planned answer sessions have been deleted.</span></span>

1. <span data-ttu-id="0e9da-159">Cliquez sur Fonctions.</span><span class="sxs-lookup"><span data-stu-id="0e9da-159">Click Functions.</span></span>
2. <span data-ttu-id="0e9da-160">Cliquez sur Fin.</span><span class="sxs-lookup"><span data-stu-id="0e9da-160">Click End.</span></span>
3. <span data-ttu-id="0e9da-161">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0e9da-161">Click OK.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]