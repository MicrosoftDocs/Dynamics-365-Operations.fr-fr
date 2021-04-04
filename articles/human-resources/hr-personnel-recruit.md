---
title: Recruter des candidats à un poste
description: Cette rubrique montre comment recruter des candidats dans Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6aca285133495dfe023dfd18bdeb050aabcafee6
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478282"
---
# <a name="recruit-job-candidates"></a><span data-ttu-id="8db6d-103">Recruter des candidats à un poste</span><span class="sxs-lookup"><span data-stu-id="8db6d-103">Recruit job candidates</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8db6d-104">Dynamics 365 Human Resources vous aide à gérer les demandes de recrutement.</span><span class="sxs-lookup"><span data-stu-id="8db6d-104">Dynamics 365 Human Resources helps you to manage recruiting requests.</span></span> <span data-ttu-id="8db6d-105">Il vous aide également à faire la transition transparente des candidats aux employés.</span><span class="sxs-lookup"><span data-stu-id="8db6d-105">It also helps you seamlessly transition job candidates to employees.</span></span> <span data-ttu-id="8db6d-106">Si votre organisation utilise une application de recrutement distincte, votre processus de recrutement peut inclure les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="8db6d-106">If your organization uses a separate recruiting application, your recruiting process might include the following steps:</span></span>

- <span data-ttu-id="8db6d-107">Saisissez votre demande de recrutement dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8db6d-107">Enter your recruiting request in Human Resources.</span></span>
- <span data-ttu-id="8db6d-108">Recevez des références de candidats dans Human Resources à partir de l’application de recrutement.</span><span class="sxs-lookup"><span data-stu-id="8db6d-108">Receive candidate referrals in Human Resources from the recruiting application.</span></span>
- <span data-ttu-id="8db6d-109">Terminez le processus d’approbation des candidats dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8db6d-109">Complete the candidate approval process in Human Resources.</span></span>

<span data-ttu-id="8db6d-110">Si vous n’utilisez pas d’application de recrutement distincte, vous pouvez également gérer manuellement les candidats dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8db6d-110">If you aren't using a separate recruiting application, you can also manually manage candidates in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="8db6d-111">Si vous êtes administrateur ou développeur et souhaitez intégrer Human Resources à une application de recrutement tierce, consultez [Configurer l’intégration de Dataverse](hr-admin-integration-common-data-service.md) et [Configurer les tables virtuelles Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)</span><span class="sxs-lookup"><span data-stu-id="8db6d-111">If you're an admin or developer and want to integrate Human Resources with a third-party recruiting application, see [Configure Dataverse integration](hr-admin-integration-common-data-service.md) and [Configure Dataverse virtual tables](hr-admin-integration-common-data-service-virtual-entities.md)</span></span>
>
> <span data-ttu-id="8db6d-112">Vous pouvez également trouver des applications d’intégration de recrutement sur [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).</span><span class="sxs-lookup"><span data-stu-id="8db6d-112">You can also find recruiting integration apps on [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).</span></span>
>
> <span data-ttu-id="8db6d-113">Pour essayer notre fonctionnalité d’évaluation pour l’intégration avec LinkedIn Talent Hub, voir [Intégrer avec LinkedIn Talent Hub](hr-admin-integration-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="8db6d-113">To try out our preview feature for integrating with LinkedIn Talent Hub, see [Integrate with LinkedIn Talent Hub](hr-admin-integration-linkedin.md).</span></span>

## <a name="enable-recruiting-requests"></a><span data-ttu-id="8db6d-114">Activer les demandes de recrutement</span><span class="sxs-lookup"><span data-stu-id="8db6d-114">Enable recruiting requests</span></span>

<span data-ttu-id="8db6d-115">Si vous souhaitez soumettre des demandes de recrutement dans Human Resources, vous devez d’abord activer la fonctionnalité dans **Paramètres partagés de Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-115">If you want to submit recruiting requests in Human Resources, you must first enable the functionality in **Human resources shared parameters**.</span></span>

1. <span data-ttu-id="8db6d-116">Dans l’espace de travail **Gestion du personnel**, sélectionnez **Liens**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-116">In the **Personnel management** workspace, select **Links**.</span></span>

2. <span data-ttu-id="8db6d-117">Sous **Configuration**, sélectionnez **Paramètres partagés des ressources humaines**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-117">Under **Setup**, select **Human resources shared parameters**.</span></span>

3. <span data-ttu-id="8db6d-118">Sur l’onglet **Recrutement**, sous **RECRUTEMENT**, définissez **Activer les demandes de recrutement** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-118">On the **Recruitment** tab, under **RECRUITING**, set **Enable recruiting requests** to **Yes**.</span></span>

## <a name="add-a-recruiting-request-location"></a><span data-ttu-id="8db6d-119">Ajouter un emplacement de demande de recrutement</span><span class="sxs-lookup"><span data-stu-id="8db6d-119">Add a recruiting request location</span></span>

<span data-ttu-id="8db6d-120">Si votre organisation possède plusieurs emplacements, vous pouvez les ajouter afin que les demandeurs puissent sélectionner un emplacement où la nouvelle recrue travaillera.</span><span class="sxs-lookup"><span data-stu-id="8db6d-120">If your organization has multiple locations, you can add them so requestors can select a location where the new recruit will be working.</span></span> <span data-ttu-id="8db6d-121">L’emplacement sera inclus dans l’offre d’emploi.</span><span class="sxs-lookup"><span data-stu-id="8db6d-121">The location will be included in the job posting.</span></span>

1. <span data-ttu-id="8db6d-122">Dans la barre de recherche, saisissez **emplacement de la demande de recrutement**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-122">In the search bar, enter **recruiting request location**.</span></span>

2. <span data-ttu-id="8db6d-123">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-123">Select **New**.</span></span>

3. <span data-ttu-id="8db6d-124">Dans le champ **Emplacement de la demande de recrutement**, entrez le nom de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="8db6d-124">In the **Recruiting request location** field, enter the location name.</span></span>

   ![Ajouter un emplacement de demande de recrutement](./media/hr-recruit-0a-add-location.png)

4. <span data-ttu-id="8db6d-126">Dans **Description**, entrez une description de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="8db6d-126">In the **Description**, enter a description for the location.</span></span>

5. <span data-ttu-id="8db6d-127">Sous **Emplacement**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-127">Under **Location**, select **Add**.</span></span> <span data-ttu-id="8db6d-128">Si la fenêtre contextuelle **Nouvelle adresse** apparaît, entrez l’adresse de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="8db6d-128">If the **New address** popout appears, enter the address for the location.</span></span>

   ![Entrer l’adresse](./media/hr-recruit-0b-address.png)

6. <span data-ttu-id="8db6d-130">Sous **Informations de contact**, entrez les informations du contact du lieu.</span><span class="sxs-lookup"><span data-stu-id="8db6d-130">Under **Contact information**, enter the information for the location's contact.</span></span>

7. <span data-ttu-id="8db6d-131">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-131">Select **Save**.</span></span>

## <a name="add-a-recruiting-request"></a><span data-ttu-id="8db6d-132">Ajouter une demande de recrutement</span><span class="sxs-lookup"><span data-stu-id="8db6d-132">Add a recruiting request</span></span>

<span data-ttu-id="8db6d-133">Les managers peuvent soumettre des demandes de recrutement dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8db6d-133">Managers can submit recruiting requests in Human Resources.</span></span> <span data-ttu-id="8db6d-134">Si vous utilisez une application de recrutement distincte, ces étapes enverront une demande de recrutement et lancera le processus de recrutement dans cette candidature.</span><span class="sxs-lookup"><span data-stu-id="8db6d-134">If you use a separate recruiting application, completing these steps will send a recruiting request and start the recruiting process in that application.</span></span> <span data-ttu-id="8db6d-135">Sinon, suivez cette procédure pour lancer le workflow de votre propre processus de recrutement interne.</span><span class="sxs-lookup"><span data-stu-id="8db6d-135">Otherwise, complete this procedure to begin the workflow for your own internal recruiting process.</span></span>

1. <span data-ttu-id="8db6d-136">Sélectionnez **Libre service employé**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-136">Select **Employee self service**.</span></span>

2. <span data-ttu-id="8db6d-137">Sélectionnez l’onglet **Mon équipe**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-137">Select the **My team** tab.</span></span>

3. <span data-ttu-id="8db6d-138">Sélectionnez **Demande de recrutement**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-138">Select  **Request to recruit**.</span></span>

   ![Démarrer une demande de recrutement](./media/hr-recruit-1-request-to-recruit.png)

4. <span data-ttu-id="8db6d-140">Remplissez les champs **Description**, **Poste** et **Estimation de la date de début**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-140">Complete the **Description**, **Job**, and **Estimated start date** fields.</span></span>

   ![Remplissez la demande de recrutement](./media/hr-recruit-2-request-to-recruit.png)

5. <span data-ttu-id="8db6d-142">Sélectionnez **Continuer**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-142">Select **Continue**.</span></span> <span data-ttu-id="8db6d-143">La demande de recrutement pour votre poste apparaît.</span><span class="sxs-lookup"><span data-stu-id="8db6d-143">The recruiting request for your position appears.</span></span>

6. <span data-ttu-id="8db6d-144">Sous **Général**, sélectionnez un recruteur dans la liste déroulante **Recruteur**, puis sélectionnez un emplacement dans le menu déroulant **Emplacement de la demande de recrutement**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-144">Under **General**, select a recruiter from the **Recruiter** dropdown, and then select a location from the **Recruiting request location** dropdown.</span></span>

7. <span data-ttu-id="8db6d-145">Sous **Emploi**, modifiez les informations selon vos besoins, puis sélectionnez **Créer des détails à partir du poste**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-145">Under **Job**, change any information as needed, and then select **Create details from job**.</span></span>

   ![Créer des détails à partir de la tâche](./media/hr-recruit-3-create-details-from-job.png)

   <span data-ttu-id="8db6d-147">Le reste de la demande de recrutement sera rempli avec les informations par défaut pour l’emploi que vous avez entré.</span><span class="sxs-lookup"><span data-stu-id="8db6d-147">The rest of the recruiting request will populate with the default information for the job you entered.</span></span>

8. <span data-ttu-id="8db6d-148">Sous **Description externe**, saisissez une description de poste externe.</span><span class="sxs-lookup"><span data-stu-id="8db6d-148">Under **External description**, enter an external-facing job description.</span></span>

9. <span data-ttu-id="8db6d-149">Sous **Postes**, sélectionnez **Ajouter**, puis sélectionnez un poste pour cette demande de recrutement.</span><span class="sxs-lookup"><span data-stu-id="8db6d-149">Under **Positions**, select **Add**, and then select a position for this recruiting request.</span></span>

   ![Ajouter un poste](./media/hr-recruit-4-select-position.png)

10. <span data-ttu-id="8db6d-151">Sous **Compétences**, sélectionnez **Ajouter**, puis sélectionnez une compétence.</span><span class="sxs-lookup"><span data-stu-id="8db6d-151">Under **Skills**, select **Add**, and then select a skill.</span></span>

11. <span data-ttu-id="8db6d-152">Sous **Exigences scolaires**, sélectionnez **Ajouter**, puis sélectionnez des valeurs dans les listes déroulantes **Éducation** et **Niveau d’instruction requis**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-152">Under **Educational requirements**, select **Add**, and then select values from the **Education** and **Level of education** dropdowns.</span></span>

   ![Ajouter des exigences scolaires](./media/hr-recruit-5-select-educational-requirements.png)

12. <span data-ttu-id="8db6d-154">Sous **Commentaire**, ajoutez des commentaires si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="8db6d-154">Under **Comment**, add comments as necessary.</span></span>

13. <span data-ttu-id="8db6d-155">Sous **Rémunération**, sélectionnez un niveau dans la liste déroulante **Niveau**, puis ajustez **Plancher**, **Point de contrôle**, et **Plafond** le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="8db6d-155">Under **Compensation**, select a level from the **Level** dropdown, and then adjust **Low threshold**, **Control point**, and **High threshold** as necessary.</span></span>

14. <span data-ttu-id="8db6d-156">Lorsque votre demande de recrutement est terminée et que vous êtes prêt à démarrer le processus de recrutement, sélectionnez **Activer** dans la barre de menus.</span><span class="sxs-lookup"><span data-stu-id="8db6d-156">When your recruiting request is complete and you're ready to start the recruiting process, select **Activate** in the menu bar.</span></span>

   ![Activer la demande de recrutement](./media/hr-recruit-6-activate-recruit-request.png)

15. <span data-ttu-id="8db6d-158">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-158">Select **Save**.</span></span>

## <a name="view-and-edit-your-recruiting-requests"></a><span data-ttu-id="8db6d-159">Consultez et modifiez vos demandes de recrutement</span><span class="sxs-lookup"><span data-stu-id="8db6d-159">View and edit your recruiting requests</span></span>

<span data-ttu-id="8db6d-160">Si vous êtes un responsable et souhaitez consulter vos propres demandes :</span><span class="sxs-lookup"><span data-stu-id="8db6d-160">If you're a manager and want to view your own requests:</span></span>

1. <span data-ttu-id="8db6d-161">Sélectionnez **Libre service employé**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-161">Select **Employee self service**.</span></span>

2. <span data-ttu-id="8db6d-162">Sélectionnez l’onglet **Mon équipe**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-162">Select the **My team** tab.</span></span>

3. <span data-ttu-id="8db6d-163">Sous **Informations sur mon équipe**, sélectionnez l’onglet **Demandes de recrutement**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-163">Under **My team information**, select the **Recruiting requests** tab.</span></span>

   ![Sélectionnez l’onglet Demandes de recrutement](./media/hr-recruit-7-recruiting-requests.png)

4. <span data-ttu-id="8db6d-165">Pour afficher ou modifier une demande de recrutement, sélectionnez-la dans la grille.</span><span class="sxs-lookup"><span data-stu-id="8db6d-165">To view or edit a recruiting request, select it in the grid.</span></span>

<span data-ttu-id="8db6d-166">Si vous êtes un professionnel des RH et que vous souhaitez consulter toutes les demandes de recrutement :</span><span class="sxs-lookup"><span data-stu-id="8db6d-166">If you're an HR pro and want to view all recruiting requests:</span></span>

1. <span data-ttu-id="8db6d-167">Sélectionnez **Gestion du personnel**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-167">Select **Personnel management**.</span></span>

2. <span data-ttu-id="8db6d-168">Sélectionnez **Demandes de recrutement**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-168">Select **Recruiting requests**.</span></span>

   ![Afficher les demandes de recrutement dans Gestion du personnel](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. <span data-ttu-id="8db6d-170">Pour afficher ou modifier une demande de recrutement, sélectionnez-la dans la grille.</span><span class="sxs-lookup"><span data-stu-id="8db6d-170">To view or edit a recruiting request, select it in the grid.</span></span>

## <a name="add-or-edit-a-candidate-profile"></a><span data-ttu-id="8db6d-171">Ajouter ou modifier un profil de candidat</span><span class="sxs-lookup"><span data-stu-id="8db6d-171">Add or edit a candidate profile</span></span>

<span data-ttu-id="8db6d-172">Si votre organisation s’est intégrée à une autre application pour gérer les demandes de recrutement, les demandes de recrutement sont transmises à cette application.</span><span class="sxs-lookup"><span data-stu-id="8db6d-172">If your organization has integrated with another application to manage recruiting requests, recruiting requests are forwarded to that application.</span></span> <span data-ttu-id="8db6d-173">La candidature de recrutement renvoie ensuite les informations du candidat à Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8db6d-173">The recruiting application then sends candidate information back to Human Resources.</span></span> <span data-ttu-id="8db6d-174">Sinon, vous pouvez suivre vos propres processus de recrutement internes et saisir manuellement les informations sur le candidat.</span><span class="sxs-lookup"><span data-stu-id="8db6d-174">Otherwise, you can follow your own internal recruiting processes and enter candidate information manually.</span></span>

1. <span data-ttu-id="8db6d-175">Sélectionnez **Gestion du personnel**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-175">Select **Personnel management**.</span></span>

2. <span data-ttu-id="8db6d-176">Sélectionnez **Liens**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-176">Select **Links**.</span></span>

3. <span data-ttu-id="8db6d-177">Sous **Recrutement**, sélectionnez **Candidats**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-177">Under **Recruiting**, select **Candidates**.</span></span>

   ![Afficher les candidats](./media/hr-recruit-9-candidates.png)

4. <span data-ttu-id="8db6d-179">Pour ajouter un candidat, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-179">To add a candidate, select **New**.</span></span> <span data-ttu-id="8db6d-180">Pour modifier un candidat existant, sélectionnez le candidat dans la liste, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-180">To edit an existing candidate, select the candidate from the list and then select **Edit**.</span></span> <span data-ttu-id="8db6d-181">Le profil du candidat apparaît.</span><span class="sxs-lookup"><span data-stu-id="8db6d-181">The candidate profile appears.</span></span>

5. <span data-ttu-id="8db6d-182">Sous **Résumé du candidat**, entrez ou modifiez les informations sur le candidat si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="8db6d-182">Under **Candidate summary**, enter or edit the candidate information as necessary.</span></span>

6. <span data-ttu-id="8db6d-183">Sous **Demande de recrutement**, sélectionnez une demande de recrutement à laquelle associer le candidat.</span><span class="sxs-lookup"><span data-stu-id="8db6d-183">Under **Recruiting request**, select a recruiting request to link the candidate to.</span></span> <span data-ttu-id="8db6d-184">Puis complétez les champs **Estimation de date de début estimée**, **Responsable du recrutement**, **Poste** et **Description** le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="8db6d-184">Then complete the **Estimated start date**, **Hiring manager**, **Position**, and **Description fields** as appropriate.</span></span>

   ![Lien vers une demande de recrutement](./media/hr-recruit-10-link-to-recruiting-request.png)

7. <span data-ttu-id="8db6d-186">Complétez toutes les informations dans les domaines suivants que vous souhaitez inclure dans le dossier du candidat :</span><span class="sxs-lookup"><span data-stu-id="8db6d-186">Complete all the information in the following areas that you want to include in the candidate's record:</span></span>
   - <span data-ttu-id="8db6d-187">**Commentaires**</span><span class="sxs-lookup"><span data-stu-id="8db6d-187">**Comments**</span></span>
   - <span data-ttu-id="8db6d-188">**Expérience professionnelle**</span><span class="sxs-lookup"><span data-stu-id="8db6d-188">**Professional experience**</span></span>
   - <span data-ttu-id="8db6d-189">**Informations sur le contact**</span><span class="sxs-lookup"><span data-stu-id="8db6d-189">**Contact information**</span></span>
   - <span data-ttu-id="8db6d-190">**Formation**</span><span class="sxs-lookup"><span data-stu-id="8db6d-190">**Education**</span></span>
   - <span data-ttu-id="8db6d-191">**Compétences**</span><span class="sxs-lookup"><span data-stu-id="8db6d-191">**Skills**</span></span>
   - <span data-ttu-id="8db6d-192">**Certificats**</span><span class="sxs-lookup"><span data-stu-id="8db6d-192">**Certificates**</span></span>
   - <span data-ttu-id="8db6d-193">**Présélections**</span><span class="sxs-lookup"><span data-stu-id="8db6d-193">**Screenings**</span></span>

8. <span data-ttu-id="8db6d-194">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-194">Select **Save**.</span></span>

## <a name="hire-a-candidate"></a><span data-ttu-id="8db6d-195">Engager un candidat</span><span class="sxs-lookup"><span data-stu-id="8db6d-195">Hire a candidate</span></span>

<span data-ttu-id="8db6d-196">Lorsque vous êtes prêt à embaucher un candidat, suivez cette procédure pour transformer le candidat en employé.</span><span class="sxs-lookup"><span data-stu-id="8db6d-196">When you're ready to hire a candidate, follow this procedure to transition the candidate to an employee.</span></span>

1. <span data-ttu-id="8db6d-197">Sur le formulaire de candidature, sélectionnez **Embaucher**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-197">On the candidate form, select **Hire**.</span></span>

   ![Engager un candidat](./media/hr-recruit-11-hire.png)

2. <span data-ttu-id="8db6d-199">Sur le formulaire **Embaucher un nouveau collaborateur**, sous **Détails**, remplissez tous les champs.</span><span class="sxs-lookup"><span data-stu-id="8db6d-199">On the **Hire new worker** form, under **Details**, complete all the fields.</span></span>

   ![Entrez les détails de la nouvelle recrue](./media/hr-recruit-12-hire-new-worker.png)

3. <span data-ttu-id="8db6d-201">Sous **Détails du poste**, vérifiez et modifiez les informations si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="8db6d-201">Under **Position details**, verify and change information as necessary.</span></span>

4. <span data-ttu-id="8db6d-202">Sous **Listes de contrôle de l’intégration**, sélectionnez les listes de contrôle d’intégration pertinentes pour cet employé.</span><span class="sxs-lookup"><span data-stu-id="8db6d-202">Under **Onboarding checklists**, select the relevant onboarding checklists for this employee.</span></span>

5. <span data-ttu-id="8db6d-203">Sélectionnez **Continuer** pour créer la fiche de l’employé.</span><span class="sxs-lookup"><span data-stu-id="8db6d-203">Select **Continue** to create the employee record.</span></span>

   >[!NOTE]
   ><span data-ttu-id="8db6d-204">En fonction des workflows de votre organisation, l’enregistrement de candidat peut passer par des étapes d’approbation supplémentaires avant de devenir un enregistrement d’employé.</span><span class="sxs-lookup"><span data-stu-id="8db6d-204">Depending on your organization's workflows, the candidate record may go through additional approval steps before becoming an employee record.</span></span>

## <a name="decide-not-to-hire-a-candidate"></a><span data-ttu-id="8db6d-205">Décider de ne pas embaucher de candidat</span><span class="sxs-lookup"><span data-stu-id="8db6d-205">Decide not to hire a candidate</span></span>

<span data-ttu-id="8db6d-206">Si vous décidez de ne pas embaucher un candidat, suivez cette procédure pour le retirer du processus de vérification.</span><span class="sxs-lookup"><span data-stu-id="8db6d-206">If you decide not to hire a candidate, follow this procedure to remove them from the vetting process.</span></span> 

1. <span data-ttu-id="8db6d-207">Sur le formulaire de candidature, sélectionnez **Ne pas embaucher**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-207">On the candidate form, select **Do not hire**.</span></span>

   ![Ne pas engager un candidat](./media/hr-recruit-13-do-not-hire.png)

2. <span data-ttu-id="8db6d-209">Sélectionnez un **Code motif** et incluez vos commentaires.</span><span class="sxs-lookup"><span data-stu-id="8db6d-209">Select a **Reason code** and include any comments.</span></span>

3. <span data-ttu-id="8db6d-210">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-210">Select **OK**.</span></span>

## <a name="dismiss-a-candidate"></a><span data-ttu-id="8db6d-211">Ignorer un candidat</span><span class="sxs-lookup"><span data-stu-id="8db6d-211">Dismiss a candidate</span></span>

<span data-ttu-id="8db6d-212">Si nécessaire, vous pouvez ignorer un candidat après l’avoir embauché.</span><span class="sxs-lookup"><span data-stu-id="8db6d-212">If needed, you can dismiss a candidate after hiring them.</span></span> <span data-ttu-id="8db6d-213">Par exemple, un candidat peut rejeter votre offre ou ne pas se présenter le premier jour.</span><span class="sxs-lookup"><span data-stu-id="8db6d-213">For example, a candidate might reject your offer or not show up on their first day.</span></span>

- <span data-ttu-id="8db6d-214">Sur le formulaire de candidature, sélectionnez **Ignorer un candidat**.</span><span class="sxs-lookup"><span data-stu-id="8db6d-214">On the candidate form, select **Dismiss candidate**.</span></span>

  ![Ignorer le candidat](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a><span data-ttu-id="8db6d-216">Voir également :</span><span class="sxs-lookup"><span data-stu-id="8db6d-216">See also</span></span>

[<span data-ttu-id="8db6d-217">Configurer des tables virtuelles Dataverse</span><span class="sxs-lookup"><span data-stu-id="8db6d-217">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="8db6d-218">Organisation du personnel</span><span class="sxs-lookup"><span data-stu-id="8db6d-218">Organize your workforce</span></span>](hr-personnel-departments-jobs-positions.md)<br>
[<span data-ttu-id="8db6d-219">Paramétrer les composants d’une tâche</span><span class="sxs-lookup"><span data-stu-id="8db6d-219">Set up the components of a job</span></span>](hr-personnel-jobs.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
