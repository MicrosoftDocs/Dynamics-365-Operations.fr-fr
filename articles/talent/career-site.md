---
title: "Fonctionnalité de site de carrière dans Attract"
description: "Cet article fournit une vue d'ensemble de la fonctionnalité de site de carrière côté candidat dans Microsoft Dynamics 365 for Talent - Attract. Il décrit également la procédure de paramétrage de cette fonctionnalité."
author: josaw
manager: AnnBe
ms.date: 10/18/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 452e3e92ea32ab5f1e3720ab81ff2f7ea18b2a06
ms.contentlocale: fr-fr
ms.lasthandoff: 10/22/2018

---
# <a name="career-site-functionality-in-attract"></a><span data-ttu-id="d430c-104">Fonctionnalité de site de carrière dans Attract</span><span class="sxs-lookup"><span data-stu-id="d430c-104">Career site functionality in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d430c-105">Cet article fournit une vue d'ensemble de la fonctionnalité de site de carrière côté candidat dans Microsoft Dynamics 365 for Talent : Attract.</span><span class="sxs-lookup"><span data-stu-id="d430c-105">This article provides an overview of the candidate-facing career site functionality in Microsoft Dynamics 365 for Talent: Attract.</span></span> <span data-ttu-id="d430c-106">Il décrit également la procédure de paramétrage de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="d430c-106">It also explains how to set up this functionality.</span></span>

## <a name="overview"></a><span data-ttu-id="d430c-107">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="d430c-107">Overview</span></span>

<span data-ttu-id="d430c-108">Attract fournit un site de carrière pour chaque environnement dans un locataire.</span><span class="sxs-lookup"><span data-stu-id="d430c-108">Attract provides one career site for each environment in a tenant.</span></span> <span data-ttu-id="d430c-109">Par exemple, si une organisation a un environnement de développement et un environnement de test, un site de carrière est mis en service pour l'environnement de développement, et un autre site de carrière est mis en service pour l'environnement de test.</span><span class="sxs-lookup"><span data-stu-id="d430c-109">For example, if an organization has a development environment and a test environment, one career site is provisioned for the development environment, and another career site is provisioned for the test environment.</span></span> <span data-ttu-id="d430c-110">Chaque site de carrière est **complètement isolé** et possède son propre mécanisme d'authentification.</span><span class="sxs-lookup"><span data-stu-id="d430c-110">Each career site is **completely isolated** and has its own authentication mechanism.</span></span> <span data-ttu-id="d430c-111">Les postes et les profils de candidats ne sont pas partagés entre les sites de carrière.</span><span class="sxs-lookup"><span data-stu-id="d430c-111">Jobs and candidate profiles aren't shared between career sites.</span></span>

<span data-ttu-id="d430c-112">Par défaut, le site de carrière est public.</span><span class="sxs-lookup"><span data-stu-id="d430c-112">By default, the career site is public.</span></span> <span data-ttu-id="d430c-113">Par conséquent, les candidats peuvent afficher tous les postes marqués comme étant externes sans avoir à se connecter.</span><span class="sxs-lookup"><span data-stu-id="d430c-113">Therefore, candidates can view all jobs that are marked as external without having to sign in.</span></span> <span data-ttu-id="d430c-114">Toutefois, toutes les autres actions demandent que les candidats se connectent.</span><span class="sxs-lookup"><span data-stu-id="d430c-114">However, all other actions require that candidates sign in.</span></span>

## <a name="career-site-management"></a><span data-ttu-id="d430c-115">Gestion du site de carrière</span><span class="sxs-lookup"><span data-stu-id="d430c-115">Career site management</span></span>

<span data-ttu-id="d430c-116">Les éléments suivants du site de carrière sont contrôlés par des paramètres :</span><span class="sxs-lookup"><span data-stu-id="d430c-116">The following items on the career site are controlled by settings:</span></span>

- <span data-ttu-id="d430c-117">**Nom de l'organisation :** Le nom de l'organisation s'affiche dans la barre de navigation en haut du site de carrière.</span><span class="sxs-lookup"><span data-stu-id="d430c-117">**Organization name:** The organization name appears on the navigation bar at the top of the career site.</span></span> <span data-ttu-id="d430c-118">Si vous sélectionnez le nom de l'organisation, les candidats accèdent à une page qui répertorie tous les postes en cours.</span><span class="sxs-lookup"><span data-stu-id="d430c-118">By selecting the organization name, candidates go to a page that lists all open jobs.</span></span>
- <span data-ttu-id="d430c-119">**Logo de l'organisation :** Une image du logo de l'organisation s'affiche dans la partie supérieure gauche du site de carrière.</span><span class="sxs-lookup"><span data-stu-id="d430c-119">**Organization logo:** An image of the organization's logo appears in the upper left of the career site.</span></span> <span data-ttu-id="d430c-120">Si vous sélectionnez le logo de l'organisation, les candidats accèdent à une page qui répertorie tous les postes en cours.</span><span class="sxs-lookup"><span data-stu-id="d430c-120">By selecting the logo image, candidates go to a page that lists all open jobs.</span></span>

<span data-ttu-id="d430c-121">Pour définir des valeurs pour le nom et le logo de l'organisation, connectez-vous à Attract en tant qu'administrateur, sélectionnez **Centre d'administration** dans le menu **Paramètres** (symbole d'engrenages), puis sélectionnez l'onglet **Informations sur la société**.</span><span class="sxs-lookup"><span data-stu-id="d430c-121">To set the values for the organization name and logo, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu (the gear symbol), and then select the **Company information** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="d430c-122">L'image du logo qui s'affiche sur le site de carrière a une hauteur fixe de 20 pixels (px).</span><span class="sxs-lookup"><span data-stu-id="d430c-122">The logo image that appears on the career site has a fixed height of 20 pixels (px).</span></span> <span data-ttu-id="d430c-123">L'image ajoutée au centre d'administration est mise à l'échelle.</span><span class="sxs-lookup"><span data-stu-id="d430c-123">The image that you add in the Admin center is scaled to fit.</span></span> <span data-ttu-id="d430c-124">Par conséquent, en fonction de l'image, la largeur peut varier.</span><span class="sxs-lookup"><span data-stu-id="d430c-124">Therefore, depending on the image, the width might change.</span></span>

## <a name="career-site-url"></a><span data-ttu-id="d430c-125">URL du site de carrière</span><span class="sxs-lookup"><span data-stu-id="d430c-125">Career site URL</span></span>

<span data-ttu-id="d430c-126">Lorsque vous [publiez un poste externe](./Creating-jobs-Attract.md#postings) pour la première fois, vous pouvez copier le lien **Postuler** dans l'application Attract.</span><span class="sxs-lookup"><span data-stu-id="d430c-126">When you [post an external job](./Creating-jobs-Attract.md#postings) for the first time, you can copy the **Apply** link from the Attract application.</span></span> <span data-ttu-id="d430c-127">L'URL de ce lien est au format suivant : `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`</span><span class="sxs-lookup"><span data-stu-id="d430c-127">The URL for this link will be in the following format: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`</span></span>

<span data-ttu-id="d430c-128">L'URL du site de carrière est une sous-chaîne de l'URL **Postuler**.</span><span class="sxs-lookup"><span data-stu-id="d430c-128">The URL of the career site is a substring of the **Apply** URL.</span></span> <span data-ttu-id="d430c-129">Elle est composée de tout jusqu'au nom de la société.</span><span class="sxs-lookup"><span data-stu-id="d430c-129">It consists of everything up through the company name.</span></span> <span data-ttu-id="d430c-130">Par conséquent, pour l'URL **Postuler** précédente, l'URL du site de carrière est `https://jobs.talent.dynamics.com/jobs/<company_name>/`.</span><span class="sxs-lookup"><span data-stu-id="d430c-130">Therefore, for the preceding **Apply** URL, the career site URL is `https://jobs.talent.dynamics.com/jobs/<company_name>/`.</span></span>

## <a name="authentication-options"></a><span data-ttu-id="d430c-131">Options d'authentification</span><span class="sxs-lookup"><span data-stu-id="d430c-131">Authentication options</span></span>

<span data-ttu-id="d430c-132">Les candidats disposent des options de connexion suivantes pour un site de carrière Attract :</span><span class="sxs-lookup"><span data-stu-id="d430c-132">Candidates have the following sign-in options for an Attract career site:</span></span>

- <span data-ttu-id="d430c-133">Compte personnel :</span><span class="sxs-lookup"><span data-stu-id="d430c-133">Personal account:</span></span>

    - <span data-ttu-id="d430c-134">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="d430c-134">LinkedIn</span></span>
    - <span data-ttu-id="d430c-135">Microsoft</span><span class="sxs-lookup"><span data-stu-id="d430c-135">Microsoft</span></span>
    - <span data-ttu-id="d430c-136">Google</span><span class="sxs-lookup"><span data-stu-id="d430c-136">Google</span></span>
    - <span data-ttu-id="d430c-137">Facebook</span><span class="sxs-lookup"><span data-stu-id="d430c-137">Facebook</span></span>

- <span data-ttu-id="d430c-138">Compte professionnel ou scolaire :</span><span class="sxs-lookup"><span data-stu-id="d430c-138">Work or school account:</span></span>

    - <span data-ttu-id="d430c-139">Microsoft Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="d430c-139">Microsoft Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="d430c-140">La connexion Azure AD est prévue uniquement pour les candidats internes.</span><span class="sxs-lookup"><span data-stu-id="d430c-140">Azure AD sign-in is intended only for internal candidates.</span></span> <span data-ttu-id="d430c-141">Par conséquent, elle fonctionne uniquement pour les candidats internes qui utilisent leurs informations d'identification Azure AD de société.</span><span class="sxs-lookup"><span data-stu-id="d430c-141">Therefore, it works only for internal candidates who use their company Azure AD credentials.</span></span> <span data-ttu-id="d430c-142">Par exemple, un candidat actuellement employé par Contoso Ltd souhaite postuler à un poste dans une société indépendante, Alpine Ski House.</span><span class="sxs-lookup"><span data-stu-id="d430c-142">For example, a candidate who is currently an employee of Contoso Ltd wants to apply for a job in an unrelated company, Alpine Ski House.</span></span> <span data-ttu-id="d430c-143">Dans ce cas, la connexion sera infructueuse si l'employé essaie d'utiliser ses informations d'identification Azure AD de Contoso Ltd.</span><span class="sxs-lookup"><span data-stu-id="d430c-143">In this case, the sign-in will be unsuccessful if the employee tries to use his or her Azure AD credentials from Contoso Ltd.</span></span>

## <a name="create-and-maintain-a-profile"></a><span data-ttu-id="d430c-144">Création et tenue à jour d'un profil</span><span class="sxs-lookup"><span data-stu-id="d430c-144">Create and maintain a profile</span></span>

<span data-ttu-id="d430c-145">Une fois que les candidats se connectent au site de carrière, ils peuvent sélectionner **Mon profil** dans la barre de navigation en haut de la page pour créer et tenir à jour leur profil.</span><span class="sxs-lookup"><span data-stu-id="d430c-145">After candidates sign in to the career site, they can select **My profile** on the navigation bar at the top of the page to create and maintain their profile.</span></span> <span data-ttu-id="d430c-146">Le profil inclut des informations personnelles, des informations sur l'expérience professionnelle, des détails sur leur formation, des documents, des liens, ainsi que des informations sur des ensembles de qualifications.</span><span class="sxs-lookup"><span data-stu-id="d430c-146">The profile includes personal information, information about work experience, education details, documents, links, and information about skill sets.</span></span> <span data-ttu-id="d430c-147">Une fois un profil créé, il peut être utilisé pour postuler à des postes qui intéressent le candidat.</span><span class="sxs-lookup"><span data-stu-id="d430c-147">After a profile is created, it can be used to apply for jobs that the candidate is interested in.</span></span> <span data-ttu-id="d430c-148">Les profils permettent également à Attract de recommander des postes adéquats aux candidats.</span><span class="sxs-lookup"><span data-stu-id="d430c-148">Profiles also help Attract recommend the right jobs to candidates.</span></span>

## <a name="find-the-right-job"></a><span data-ttu-id="d430c-149">Rechercher le poste adéquat</span><span class="sxs-lookup"><span data-stu-id="d430c-149">Find the right job</span></span>

<span data-ttu-id="d430c-150">Sur la page de la liste des postes, les candidats peuvent rechercher un poste spécifique en entrant des conditions de recherche.</span><span class="sxs-lookup"><span data-stu-id="d430c-150">On the job list page, candidates can search for a specific job by entering search terms.</span></span> <span data-ttu-id="d430c-151">La fonctionnalité de recherche recherche des conditions de recherche dans les titres et les descriptions de postes, affiche les postes appropriés comme résultats.</span><span class="sxs-lookup"><span data-stu-id="d430c-151">The search functionality looks for the search terms in job titles and job descriptions, and shows relevant jobs as results.</span></span> <span data-ttu-id="d430c-152">Les candidats peuvent filtrer les résultats à tout moment, selon l'emplacement du poste ou la fonction.</span><span class="sxs-lookup"><span data-stu-id="d430c-152">Candidates can filter the results at any time, based on the job location or job function.</span></span>

<span data-ttu-id="d430c-153">Les candidats peuvent également afficher un ensemble de postes recommandés sur le site de carrière.</span><span class="sxs-lookup"><span data-stu-id="d430c-153">Candidates can also view a set of recommended jobs on the career site.</span></span> <span data-ttu-id="d430c-154">Les postes recommandés à un candidat sont basés sur les candidatures précédentes, le profil, et les CV du candidat.</span><span class="sxs-lookup"><span data-stu-id="d430c-154">The jobs that are recommended to a candidate are based on the candidate's past applications, profile, and resumes.</span></span>

> [!NOTE]
> <span data-ttu-id="d430c-155">Les recommandations de postes sont affichées uniquement si au moins 10 postes sont validés sur le site de carrière, et si le candidat a terminé son profil.</span><span class="sxs-lookup"><span data-stu-id="d430c-155">Job recommendations are shown only if at least 10 jobs are posted on the career site, and if the candidate has completed his or her profile.</span></span>

## <a name="apply-for-jobs"></a><span data-ttu-id="d430c-156">Soumission d'une candidature à des emplois</span><span class="sxs-lookup"><span data-stu-id="d430c-156">Apply for jobs</span></span>

<span data-ttu-id="d430c-157">Une fois que les candidats trouvent le poste adéquat, ils peuvent postuler à l'aide du bouton **Postuler** sur la page des détails du poste.</span><span class="sxs-lookup"><span data-stu-id="d430c-157">After candidates find the right job, they can apply by using the **Apply** button on the job details page.</span></span> <span data-ttu-id="d430c-158">À ce stade, les candidats peuvent créer un profil tout nouveau ou réviser les informations de leur profil existant.</span><span class="sxs-lookup"><span data-stu-id="d430c-158">At this point, candidates can either create a brand-new profile or review the information in their existing profile.</span></span> <span data-ttu-id="d430c-159">Les candidats peuvent également charger un CV, au besoin, puis soumettre la candidature au poste.</span><span class="sxs-lookup"><span data-stu-id="d430c-159">Candidates can also upload a resume, as required, and then submit the job application.</span></span>

## <a name="check-application-status"></a><span data-ttu-id="d430c-160">Consulter le statut de la candidature</span><span class="sxs-lookup"><span data-stu-id="d430c-160">Check application status</span></span>

<span data-ttu-id="d430c-161">Une fois que les candidats postulent à un ou plusieurs postes, ils peuvent sélectionner **Candidatures** dans la barre de navigation en haut de la page pour afficher leur candidatures en cours et clôturées.</span><span class="sxs-lookup"><span data-stu-id="d430c-161">After candidates apply for one or more jobs, they can select **Applications** on the navigation bar at the top of the page to view their open and closed applications.</span></span> <span data-ttu-id="d430c-162">Lorsque les candidats ouvrent l'une de leurs candidatures, ils voient le stade actuel et toutes les actions en cours qu'ils doivent compléter.</span><span class="sxs-lookup"><span data-stu-id="d430c-162">When candidates open one of their applications, they see the current stage and any pending action items that they must complete.</span></span> <span data-ttu-id="d430c-163">Par exemple, si un candidat doit fournir des dates potentielles pour un entretien en personne, la page lui présente ses options.</span><span class="sxs-lookup"><span data-stu-id="d430c-163">For example, if a candidate must provide potential dates for an in-person interview, the page shows his or her options.</span></span>

## <a name="internal-jobs"></a><span data-ttu-id="d430c-164">Postes internes</span><span class="sxs-lookup"><span data-stu-id="d430c-164">Internal jobs</span></span>

<span data-ttu-id="d430c-165">Actuellement, les postes marqués comme internes et publiés sur le site de carrière Attract n'apparaissent pas sur le site de carrière.</span><span class="sxs-lookup"><span data-stu-id="d430c-165">Currently, jobs that are marked as internal and posted to the Attract career site don't appear on the career site.</span></span> <span data-ttu-id="d430c-166">Ils sont accessibles uniquement via l'URL **Postuler** directe qui peut être copiée sur l'application Attract.</span><span class="sxs-lookup"><span data-stu-id="d430c-166">They are accessible only via the direct **Apply** URL that can be copied from the Attract application.</span></span>

