---
title: Approvisionnement avec LinkedIn Recruiter
description: "Cette rubrique fournit des informations sur l'utilisation du Machine Learning pour obtenir des recommandations de poste et de candidat à un poste."
author: josaw
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: 
ms.author: josaw
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: 2fc6bf25d303d7d8de8002a923a080b90dcfbeab
ms.openlocfilehash: 106103e2c3d8f3d89aac5140174e5794da22536f
ms.contentlocale: fr-fr
ms.lasthandoff: 10/24/2018

---

# <a name="sourcing-with-linkedin-recruiter"></a><span data-ttu-id="41b94-103">Approvisionnement avec LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="41b94-103">Sourcing with LinkedIn Recruiter</span></span>
[!include[banner](../includes/banner.md)]

<span data-ttu-id="41b94-104">LinkedIn est la plus grande base de données de talents au monde et souvent le principal système que les recruteurs utilisent pour rechercher, communiquer, et approvisionner en candidats de sources pour les postes que les recruteurs cherchent à pourvoir.</span><span class="sxs-lookup"><span data-stu-id="41b94-104">LinkedIn is the world’s largest talent database and often the primary system that recruiters use to find, communicate with, and source candidates for the jobs that recruiters are looking to fill.</span></span> <span data-ttu-id="41b94-105">L'intégration de LinkedIn Recruiter à Dynamics 365 for Talent - Attract permet aux utilisateurs de facilement embaucher et conserver les données synchronisées entre les deux systèmes.</span><span class="sxs-lookup"><span data-stu-id="41b94-105">LinkedIn Recruiter integration with Dynamics 365 for Talent: Attract makes it easier for users to hire, and to keep the data in sync between the two systems.</span></span>

> [!NOTE]
> <span data-ttu-id="41b94-106">Vous avez besoin du Composant additionnel de recrutement complet et de licences LinkedIn Recruiter pour pouvoir utiliser l'intégration de LinkedIn Recruiter à Attract.</span><span class="sxs-lookup"><span data-stu-id="41b94-106">You need the Comprehensive hiring add-on and LinkedIn Recruiter seats to be able to use LinkedIn Recruiter integration with Attract.</span></span>

## <a name="set-up-linkedin-recruiter-with-attract"></a><span data-ttu-id="41b94-107">Paramétrage de LinkedIn Recruiter avec Attract</span><span class="sxs-lookup"><span data-stu-id="41b94-107">Set up LinkedIn Recruiter with Attract</span></span> 

<span data-ttu-id="41b94-108">Avant de pouvoir utiliser les fonctionnalités de LinkedIn Recruiter, vous devez configurer un accès au niveau du contrat ou de la société avec votre instance Attract.</span><span class="sxs-lookup"><span data-stu-id="41b94-108">Before you can use the LinkedIn Recruiter capabilities, you must configure contract-level or company-level access with your Attract instance.</span></span> <span data-ttu-id="41b94-109">Pour terminer le processus de configuration, vous devez collaborer avec l'utilisateur qui est un administrateur de votre contrat LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="41b94-109">To complete the configuration process, you must work with the user who is an Admin on your LinkedIn Recruiter contract.</span></span> <span data-ttu-id="41b94-110">Procédez comme suit pour configurer LinkedIn Recruiter avec Attract.</span><span class="sxs-lookup"><span data-stu-id="41b94-110">Complete the following steps to configure LinkedIn Recruiter with Attract.</span></span>

1.  <span data-ttu-id="41b94-111">Connectez-vous à Attract en tant qu'administrateur et accédez à **Paramètres d'administration**.</span><span class="sxs-lookup"><span data-stu-id="41b94-111">Sign in to Attract as an Admin and go to **Admin Settings**.</span></span>

2.  <span data-ttu-id="41b94-112">Dans le volet de gauche, cliquez sur l'onglet **Intégration de LinkedIn**.</span><span class="sxs-lookup"><span data-stu-id="41b94-112">On the left pane, click the **LinkedIn Integration** tab.</span></span>

<span data-ttu-id="41b94-113">[![Vue de l'administrateur Attract pour démarrer l'intégration de LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)</span><span class="sxs-lookup"><span data-stu-id="41b94-113">[![Attract Admin view to start LinkedIn Recruiter integration](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)</span></span>

3.  <span data-ttu-id="41b94-114">Cliquez sur **Connexion** pour activer la configuration et être guidé dans le processus de connexion à LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="41b94-114">Click **Connect** to start the setup and be guided through the LinkedIn sign-in process.</span></span>

4.  <span data-ttu-id="41b94-115">Si vous avez des licences dans plusieurs contrats LinkedIn, sélectionnez le contrat que vous voulez connecter au système Attract.</span><span class="sxs-lookup"><span data-stu-id="41b94-115">If you have seats on multiple LinkedIn contracts, select the contract that you would like to connect to the Attract system.</span></span> <span data-ttu-id="41b94-116">Si vous avez une licence sur un seul contrat LinkedIn, cette étape n'est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="41b94-116">If you have a seat on only one LinkedIn contract, this step will not be needed.</span></span>

5.  <span data-ttu-id="41b94-117">Le widget LinkedIn va se charger dans vos paramètres d'administration avec la liste des intégrations affichées.</span><span class="sxs-lookup"><span data-stu-id="41b94-117">The LinkedIn widget will now load in your Admin settings with the list of integrations shown.</span></span> <span data-ttu-id="41b94-118">Sous **Recruiter System connect**, cliquez sur **Demander**.</span><span class="sxs-lookup"><span data-stu-id="41b94-118">Under **Recruiter System connect**, click **Request**.</span></span>

<span data-ttu-id="41b94-119">[![Vue de l'administrateur Attract pour demander l'intégration de LinkedIn Recruiter](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)</span><span class="sxs-lookup"><span data-stu-id="41b94-119">[![Attract Admin view to Request LinkedIn Recruiter integration](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)</span></span>

6.  <span data-ttu-id="41b94-120">Une fois l'intégration demandée à partir d'Attract, elle s'affiche comme **Partenaire prêt** et est prête à être activée dans **Paramètres d'administration Recruiter**.</span><span class="sxs-lookup"><span data-stu-id="41b94-120">After the integration is requested from Attract, it will show as **Partner ready** and is ready to be turned on from **Recruiter Admin settings**.</span></span> <span data-ttu-id="41b94-121">Si vous voyez **Notifier le partenaire** sur cette page, attendez quelques secondes, cliquez sur **Notifier le partenaire**, puis actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="41b94-121">If you see **Notify partner** on this page, wait a few seconds, click **Notify partner**, and then refresh the page.</span></span> <span data-ttu-id="41b94-122">Elle doit désormais s'afficher comme **Partenaire prêt**.</span><span class="sxs-lookup"><span data-stu-id="41b94-122">It should now show as **Partner ready**.</span></span>

<span data-ttu-id="41b94-123">[![Vue de l'administrateur Attract pour indiquer que des demandes ont été terminées du côté d'Attract](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)</span><span class="sxs-lookup"><span data-stu-id="41b94-123">[![Attract Admin view to indicate Attract side of requests have been completed](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)</span></span>

<span data-ttu-id="41b94-124">Pour terminer l'étape suivante, vous devez disposer d'un privilège d'administrateur sur votre contrat LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="41b94-124">To complete the next step, you need to have an Admin privilege on your LinkedIn Recruiter Contract.</span></span>

7.  <span data-ttu-id="41b94-125">Connectez-vous à LinkedIn à l'aide du compte d'administrateur et accédez à LinkedIn Recruiter dans le coin supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="41b94-125">Sign in to LinkedIn using the Admin account and go to LinkedIn Recruiter on the top right.</span></span> 

8. <span data-ttu-id="41b94-126">Sur le menu **Plus** en haut de l'écran, cliquez sur **Paramètres d'administration**, puis cliquez sur l'onglet **ATS**.</span><span class="sxs-lookup"><span data-stu-id="41b94-126">On the **More** menu at the top of the screen, click **Admin Settings**, and then click the **ATS** Tab.</span></span>

<span data-ttu-id="41b94-127">Le système Attract sera répertorié avec certaines options qui peuvent être activées.</span><span class="sxs-lookup"><span data-stu-id="41b94-127">The Attract system will be listed with a couple of options that can be turned on.</span></span>

9. <span data-ttu-id="41b94-128">Si vous souhaitez activer uniquement l'exportation en 1 clic pour l'**Indicateur In-ATS** et le **Widget Profil In-ATS**, sélectionnez **Accès au niveau de la société**.</span><span class="sxs-lookup"><span data-stu-id="41b94-128">If you want to enable only 1-Click export for the **In-ATS indicator** and the **In-ATS Profile Widget**, select **Company-level access**.</span></span> <span data-ttu-id="41b94-129">Si vous souhaitez activer l'accès à toutes les fonctionnalités au niveau de la société, ainsi que l'accès à l'historique InMail, l'historique Notes, et au profil de bordereau InMail, sélectionnez **Accès au niveau du contrat**.</span><span class="sxs-lookup"><span data-stu-id="41b94-129">If you want to enable all of Company-level access features plus InMail history, Notes history, and the InMail stub profile access, select **Contract-level access**.</span></span>

10. <span data-ttu-id="41b94-130">Activez le niveau d'accès souhaité dans vos paramètres **Admin-ATS** LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="41b94-130">Turn on the desired access level from your LinkedIn Recruiter **Admin-ATS** settings.</span></span>

<span data-ttu-id="41b94-131">[![Activer l'intégration d'Attract depuis la vue de l'administrateur LinkedIn Recruiter](./media/EnableRSC.png)](./media/EnableRSC.png)</span><span class="sxs-lookup"><span data-stu-id="41b94-131">[![Turn on Attract integration from LinkedIn Recruiter Admin view](./media/EnableRSC.png)](./media/EnableRSC.png)</span></span>

12. <span data-ttu-id="41b94-132">Revenez aux paramètres d'administration Attract en tant qu'AttractAdmin et sélectionnez l'onglet **Intégration de LinkedIn**. Vous devez maintenant voir le chargement du widget LinkedIn affichant **Activé** avec le niveau d'accès sélectionné activé.</span><span class="sxs-lookup"><span data-stu-id="41b94-132">Go back to Attract Admin Settings as an AttractAdmin and select the **LinkedIn integration** tab. You should now see the LinkedIn widget load showing **Enabled** with the selected access level turned on.</span></span>

<span data-ttu-id="41b94-133">[![Intégration de LinkedIn Recruiter terminée](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)</span><span class="sxs-lookup"><span data-stu-id="41b94-133">[![LinkedIn Recruiter integration complete](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)</span></span>

## <a name="using-linkedin-recruiter-capabilities"></a><span data-ttu-id="41b94-134">Utilisation des fonctionnalités de LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="41b94-134">Using LinkedIn Recruiter capabilities</span></span>

<span data-ttu-id="41b94-135">Une fois les fonctionnalités de LinkedIn Recruiter activées par l'administrateur Attract, elles sont accessibles aux responsables de l'embauche et aux recruteurs.</span><span class="sxs-lookup"><span data-stu-id="41b94-135">After LinkedIn Recruiter capabilities has been enabled by the Attract Admin it is available for hiring managers and recruiters to access.</span></span> <span data-ttu-id="41b94-136">Pour utiliser ces fonctionnalités, connectez-vous à votre compte LinkedIn sous **Paramètres utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="41b94-136">To use these capabilities, connect your LinkedIn account under **User Settings**.</span></span> <span data-ttu-id="41b94-137">Plusieurs fonctionnalités seront disponibles une fois que les paramètres d'administration et utilisateur auront été connectés.</span><span class="sxs-lookup"><span data-stu-id="41b94-137">Several capabilities will be available after both the Admin and User settings have been connected.</span></span>

### <a name="in-ats-profile-widget"></a><span data-ttu-id="41b94-138">Widget Profil In-ATS</span><span class="sxs-lookup"><span data-stu-id="41b94-138">In-ATS profile widget</span></span>

<span data-ttu-id="41b94-139">Vous pouvez afficher le profil LinkedIn du candidat dans Attract.</span><span class="sxs-lookup"><span data-stu-id="41b94-139">You can view the candidate’s LinkedIn profile in Attract.</span></span> <span data-ttu-id="41b94-140">Le widget LinkedIn affiche le profil du candidat lorsque les informations d'ATS correspondent aux informations de LinkedIn de ses utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="41b94-140">The LinkedIn widget will display the candidate profile when the ATS information matches the LinkedIn information of its users.</span></span>

<span data-ttu-id="41b94-141">Pour afficher un profil, accédez au profil du candidat depuis un poste ou un vivier de talents.</span><span class="sxs-lookup"><span data-stu-id="41b94-141">To view a profile, go the candidate profile either from a job or talent pool.</span></span> <span data-ttu-id="41b94-142">Dans le profil du candidat, sélectionnez l'onglet **LinkedIn** et le widget du profil se chargera.</span><span class="sxs-lookup"><span data-stu-id="41b94-142">In the candidate profile, select the **LinkedIn** tab and the profile widget will load.</span></span> <span data-ttu-id="41b94-143">À l'aide du widget du profil, indiquez si la correspondance est exacte.</span><span class="sxs-lookup"><span data-stu-id="41b94-143">Using the profile widget, indicate if this is the correct match.</span></span> <span data-ttu-id="41b94-144">Si ne n'est pas le cas, recherchez la bonne personne.</span><span class="sxs-lookup"><span data-stu-id="41b94-144">If it is not, find the correct person.</span></span> <span data-ttu-id="41b94-145">Vous pouvez également enregistrer le candidat dans vos projets LinkedIn Recruiter depuis cette page.</span><span class="sxs-lookup"><span data-stu-id="41b94-145">You can also save the candidate to your LinkedIn Recruiter projects from this page.</span></span>

### <a name="1-click-export"></a><span data-ttu-id="41b94-146">Exportation en 1 clic</span><span class="sxs-lookup"><span data-stu-id="41b94-146">1-click export</span></span> 

<span data-ttu-id="41b94-147">Lors de l'approvisionnement en candidats dans LinkedIn, vous pouvez exporter en 1 clic le candidat vers les missions qui sont actuellement en cours.</span><span class="sxs-lookup"><span data-stu-id="41b94-147">While sourcing candidates in LinkedIn, you can 1-click export the candidate to the jobs that you currently have open.</span></span> <span data-ttu-id="41b94-148">Procédez comme suit pour une exportation en 1 clic.</span><span class="sxs-lookup"><span data-stu-id="41b94-148">Complete the following steps for a 1-click export.</span></span> <span data-ttu-id="41b94-149">Avant de terminer ces étapes, vérifiez que vous êtes disposez du rôle de responsable de l'embauche ou de recruteur pour la mission et que celle-ci est à la phase **Prospect**.</span><span class="sxs-lookup"><span data-stu-id="41b94-149">Before you complete these steps, verify that you are a assigned the role of Hiring manager or Recruiter for the job and that the job has a **Prospect** stage.</span></span>

1.  <span data-ttu-id="41b94-150">Créer la mission, affectez les rôles appropriés, puis activez la mission.</span><span class="sxs-lookup"><span data-stu-id="41b94-150">Create the job, assign the appropriate roles, and activate the job.</span></span>

2.  <span data-ttu-id="41b94-151">Lorsque la mission est activée, accédez à LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="41b94-151">When the job is activated, navigate to LinkedIn Recruiter.</span></span>

3.  <span data-ttu-id="41b94-152">Recherchez le candidat de votre choix et accédez à son profil.</span><span class="sxs-lookup"><span data-stu-id="41b94-152">Find the candidate that you are looking for and go to their profile.</span></span>

4.  <span data-ttu-id="41b94-153">À l'aide de la zone de recherche de la fiche contact, recherchez la mission à l'aide du titre ou de l'ID de la mission activé dans Attract.</span><span class="sxs-lookup"><span data-stu-id="41b94-153">Using the job search box in the contact card, find the job using the title or the Job ID that was activated in Attract.</span></span> <span data-ttu-id="41b94-154">Si vous ne trouvez pas la mission, cliquez sur **Modifier ATS** pour rechercher l'instance Attract correcte.</span><span class="sxs-lookup"><span data-stu-id="41b94-154">If you don’t find the job, click **Change ATS** to find the correct Attract instance.</span></span>

5. <span data-ttu-id="41b94-155">Une fois la mission sélectionnée, cliquez sur **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="41b94-155">After the job is selected, click **Export**.</span></span> <span data-ttu-id="41b94-156">Le candidat est à présent extrait par Attract.</span><span class="sxs-lookup"><span data-stu-id="41b94-156">The candidate is now fetched by Attract.</span></span>

6.  <span data-ttu-id="41b94-157">Accédez à Attract et ouvrez la mission concernée.</span><span class="sxs-lookup"><span data-stu-id="41b94-157">Go to Attract and open the respective job.</span></span> <span data-ttu-id="41b94-158">Vous trouverez le candidat que vous venez d'exporter à la phase **Prospect** de la mission.</span><span class="sxs-lookup"><span data-stu-id="41b94-158">You will find the candidate that you just exported in the **Prospect** stage of the job.</span></span>

### <a name="in-ats-indicator"></a><span data-ttu-id="41b94-159">Indicateur In-ATS</span><span class="sxs-lookup"><span data-stu-id="41b94-159">In-ATS indicator</span></span> 

<span data-ttu-id="41b94-160">À l'aide de LinkedIn Recruiter, vous pouvez suivre si un candidat a postulé à d'autres postes de votre organisation, examiner à quelles phases distinctes des candidatures à un poste ils se trouvent, et afficher des commentaires et des rétroactions d'Attract dans LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="41b94-160">Using LinkedIn recruiter, you can track whether a candidate has applied to other jobs in your organization, look at where they are in different stages of job applications, and view the feedback and comments from Attract in LinkedIn Recruiter.</span></span>

1.  <span data-ttu-id="41b94-161">Ouvrez LinkedIn Recruiter et localisez le profil du candidat que vous recherchez.</span><span class="sxs-lookup"><span data-stu-id="41b94-161">Open LinkedIn Recruiter and locate the candidate profile that you are looking for.</span></span>

2.  <span data-ttu-id="41b94-162">Faites défiler l'écran pour afficher la section **In-ATS** dans le profil du candidat.</span><span class="sxs-lookup"><span data-stu-id="41b94-162">Scroll down to view the **In-ATS** section on the candidate’s profile.</span></span>

3.  <span data-ttu-id="41b94-163">Vous pouvez utiliser ce widget pour afficher toutes les informations sur le candidat présentes dans Attract dans la vue de LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="41b94-163">You can use this widget to view all of the information about the candidate that’s present in Attract from within the LinkedIn Recruiter view.</span></span>

4.  <span data-ttu-id="41b94-164">Sélectionnez l'onglet **Postes et statuts** pour afficher les missions dont ils font partie, le dernier statut, et savoir comment ils se positionnent sur chaque mission.</span><span class="sxs-lookup"><span data-stu-id="41b94-164">Select the **Jobs & Statuses** tab to see jobs they are part of, the latest status, and how they have been moving against each job.</span></span>

5.  <span data-ttu-id="41b94-165">Sélectionnez l'onglet **Commentaire sur l'entretien** pour voir les commentaires des interviewers dans Attract.</span><span class="sxs-lookup"><span data-stu-id="41b94-165">Select the **Interview Feedback** tab to see feedback that the interviewers have submitted in Attract.</span></span>

6.  <span data-ttu-id="41b94-166">Sélectionnez l'onglet **Notes** pour afficher les notes qui ont été capturées pour ce candidat dans Attract.</span><span class="sxs-lookup"><span data-stu-id="41b94-166">Select the **Notes** tab to see notes that have been captured for this applicant in Attract.</span></span>

### <a name="inmail-history"></a><span data-ttu-id="41b94-167">Historique InMail</span><span class="sxs-lookup"><span data-stu-id="41b94-167">InMail history</span></span>

<span data-ttu-id="41b94-168">L'historique LinkedIn InMail est disponible avec l'accès au niveau du contrat avec LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="41b94-168">The LinkedIn InMail history is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="41b94-169">Lorsqu'il est activé, vous pouvez afficher l'historique InMail complet avec le candidat.</span><span class="sxs-lookup"><span data-stu-id="41b94-169">When it is enabled, you can view your entire InMail history with the candidate.</span></span> <span data-ttu-id="41b94-170">Vous pouvez également voir qui d'autre dans votre organisation a échangé sur InMail avec le candidat, mais vous ne pouvez pas afficher les messages entre eux.</span><span class="sxs-lookup"><span data-stu-id="41b94-170">You can also see who else from your organization has exchanged InMail with the candidate, however you can't view the messages between them.</span></span>

<span data-ttu-id="41b94-171">Pour afficher l'historique InMail, accédez au profil d'un candidat, accédez à l'onglet **LinkedIn** et faites défiler vers le bas de page pour afficher l'historique.</span><span class="sxs-lookup"><span data-stu-id="41b94-171">To view InMail history, go to a candidate’s profile, go to the **LinkedIn** tab and scroll to the bottom of the page to view the history.</span></span> <span data-ttu-id="41b94-172">Vous pouvez afficher l'historique InMail uniquement si le candidat a répondu à votre demande et choisi de partager son profil avec vous dans LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="41b94-172">You can view the InMail history only if the candidate has responded to your request and chosen to share their profile with you in LinkedIn.</span></span> <span data-ttu-id="41b94-173">Les messages InMail se synchronisent avec Attract toutes les deux heures.</span><span class="sxs-lookup"><span data-stu-id="41b94-173">The messages from InMail sync with Attract every couple of hours.</span></span>

### <a name="notes-history"></a><span data-ttu-id="41b94-174">Historique Notes</span><span class="sxs-lookup"><span data-stu-id="41b94-174">Notes history</span></span> 

<span data-ttu-id="41b94-175">L'historique des notes LinkedIn est disponible avec l'accès au niveau du contrat avec LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="41b94-175">The LinkedIn notes history is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="41b94-176">Lorsqu'il est activé, vous pouvez afficher les notes qui ont été capturées sur le candidat par les différents recruteurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="41b94-176">When it is enabled, you can view the notes that have been captured about the candidate by different recruiters from your organization.</span></span>

<span data-ttu-id="41b94-177">Pour afficher l'historique Notes, accédez au profil d'un candidat, accédez à l'onglet **LinkedIn** et faites défiler vers le bas de page pour afficher l'historique.</span><span class="sxs-lookup"><span data-stu-id="41b94-177">To view Notes history, go to a candidate’s profile, go to the **LinkedIn** tab and scroll to the bottom of the page to view the history.</span></span> <span data-ttu-id="41b94-178">Vous pouvez afficher toutes les notes sur le candidat dans LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="41b94-178">You can view all the notes about the candidate from LinkedIn Recruiter.</span></span>

### <a name="inmail-stub-profile"></a><span data-ttu-id="41b94-179">Profil de bordereau InMail</span><span class="sxs-lookup"><span data-stu-id="41b94-179">InMail stub profile</span></span>

<span data-ttu-id="41b94-180">Le profil de bordereau InMail est disponible avec l'accès au niveau du contrat avec LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="41b94-180">The InMail stub profile is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="41b94-181">Si les candidats acceptent de partager leurs profils LinkedIn avec tout utilisateur de votre organisation, vous pouvez suivre les candidats dans Attract et un nouvel enregistrement de candidat sera créé pour chaque candidat.</span><span class="sxs-lookup"><span data-stu-id="41b94-181">If candidates agree to share their LinkedIn profiles with any user in your organization, you can track the candidates in Attract and a new candidate record will be created for each candidate.</span></span>

<span data-ttu-id="41b94-182">Pour afficher la liste des candidats, accédez à **Viviers de talents** pour afficher un vivier de talents LinkedIn créé par le système.</span><span class="sxs-lookup"><span data-stu-id="41b94-182">To view the list of candidates, go to **Talent pools** to see a system-created LinkedIn talent pool.</span></span> <span data-ttu-id="41b94-183">Ce vivier de talents contient les candidats de liste et leurs profils de bordereau reçus de LinkedIn, affichant le prénom et le nom du candidat.</span><span class="sxs-lookup"><span data-stu-id="41b94-183">This talent pool contains the list candidates and their stub profiles as received from LinkedIn, showing the candidate's first name and last name.</span></span> <span data-ttu-id="41b94-184">L'ID e-mail du candidat sera affiché si le candidat a choisi de partager son adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="41b94-184">The candidate’s email ID will be displayed if the candidate had chosen to share their email address.</span></span>

