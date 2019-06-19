---
title: Étendre Talent à l'aide de PowerApps et de Microsoft Flow - Exemples de scénarios
description: Cette rubrique décrit quelques exemples de scénarios d'extensibilité pour Microsoft Dynamics 365 for Talent utilisant Microsoft PowerApps et Microsoft Flow.
author: negudava
manager: Annbe
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 for Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2019-03-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: a9ebfd1f2621b8ad65d7623c37b6851cc0b5cb54
ms.sourcegitcommit: ffc37f7c2a63bada3055f37856a30424040bc9a3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/16/2019
ms.locfileid: "1577793"
---
# <a name="extend-talent-by-using-powerapps-and-microsoft-flow---example-scenarios"></a><span data-ttu-id="74ecf-103">Étendre Talent à l'aide de PowerApps et de Microsoft Flow - Exemples de scénarios</span><span class="sxs-lookup"><span data-stu-id="74ecf-103">Extend Talent by using PowerApps and Microsoft Flow - Example scenarios</span></span>

<span data-ttu-id="74ecf-104">Cette rubrique décrit quelques exemples de scénarios d'extensibilité pour Microsoft Dynamics 365 for Talent utilisant Microsoft PowerApps et Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="74ecf-104">This topic describes some examples of extensibility scenarios for Microsoft Dynamics 365 for Talent that use Microsoft PowerApps and Microsoft Flow.</span></span> <span data-ttu-id="74ecf-105">Vous pouvez importer le module de solution associé à chaque exemple dans l'environnement de PowerApps.</span><span class="sxs-lookup"><span data-stu-id="74ecf-105">You can import the solution package that is associated with each example into your PowerApps environment.</span></span> <span data-ttu-id="74ecf-106">Vous pouvez ensuite utiliser les modules comme orientation ou comme point de départ pour implémenter les scénarios qui s'appliquent à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="74ecf-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74ecf-107">Pour utiliser les modèles et l'application décrits dans cette rubrique « en l'état », veillez à les tester pour vous assurer qu'ils couvrent tous les scénarios spécifiques à votre implémentation.</span><span class="sxs-lookup"><span data-stu-id="74ecf-107">If you want to use the templates and app that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="74ecf-108">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="74ecf-108">Prerequisites</span></span>

- <span data-ttu-id="74ecf-109">Pour importer des modules, les utilisateurs doivent avoir l'autorisation **Créateur d'environnement**.</span><span class="sxs-lookup"><span data-stu-id="74ecf-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="74ecf-110">Pour exporter ou importer des applications, les utilisateurs doivent disposer d'une licence PowerApps Plan 2 ou une licence d'essai PowerApps Plan 2.</span><span class="sxs-lookup"><span data-stu-id="74ecf-110">To export or import apps, users must have a PowerApps Plan 2 license or a PowerApps Plan 2 trial license.</span></span>

## <a name="flow--form-connect"></a><span data-ttu-id="74ecf-111">Flow – Form Connect</span><span class="sxs-lookup"><span data-stu-id="74ecf-111">Flow – Form Connect</span></span>

<span data-ttu-id="74ecf-112">Le modèle **Flow – Form Connect** peut être utilisé pour lire des données de Microsoft Forms et les enregistrer dans une entité Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="74ecf-112">The **Flow – Form Connect** template can be used to read data from Microsoft Forms and store it in a Common Data Service entity.</span></span>

<span data-ttu-id="74ecf-113">Ce modèle peut être étendu pour être utilisé pour d'autres scénarios.</span><span class="sxs-lookup"><span data-stu-id="74ecf-113">This template can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="74ecf-114">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="74ecf-114">Here are some examples:</span></span>

- <span data-ttu-id="74ecf-115">Captures des évaluations de candidats.</span><span class="sxs-lookup"><span data-stu-id="74ecf-115">Capture candidate assessments.</span></span>
- <span data-ttu-id="74ecf-116">Capture des résultats questionnaire de cours</span><span class="sxs-lookup"><span data-stu-id="74ecf-116">Capture results from course questionnaires.</span></span>
- <span data-ttu-id="74ecf-117">Compilation d'une bibliothèque de questions d'entretien pour les administrateurs des Ressources humaines (RH).</span><span class="sxs-lookup"><span data-stu-id="74ecf-117">Compile a library of interview questions for Human resources (HR) administrators.</span></span>
- <span data-ttu-id="74ecf-118">Capture de l'évaluation du processus d'entretien d'un candidat</span><span class="sxs-lookup"><span data-stu-id="74ecf-118">Capture a candidate's evaluation of the interview process</span></span>

<span data-ttu-id="74ecf-119">Dans Microsoft Dynamics 365 : Attract, les écrans peuvent s'afficher dans le portail Candidat, et les candidats peuvent renseigner les informations.</span><span class="sxs-lookup"><span data-stu-id="74ecf-119">In Microsoft Dynamics 365: Attract, forms can appear in Candidate portal, and candidates can fill in details.</span></span> <span data-ttu-id="74ecf-120">Les écrans peuvent également être incorporés comme activités dans un modèle de poste.</span><span class="sxs-lookup"><span data-stu-id="74ecf-120">Forms can also be embedded as activities in a job template.</span></span>

<span data-ttu-id="74ecf-121">Lorsqu'un candidat envoie un formulaire, Microsoft Flow capture l'envoi de l'écran, lit les données et les stocke dans l'entité Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="74ecf-121">When a candidate submits a form, Microsoft Flow captures the form submission, reads the data, and stores it in the Common Data Service entity.</span></span>

<span data-ttu-id="74ecf-122">Pour télécharger le modèle **Flow – Form Connect** et la structure de l'entité personnalisée, accédez à [Flow – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) dans le Centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74ecf-122">To download the **Flow – Form Connect** template and Custom Entity Structure, go to [Flow – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) on the Microsoft Download Center.</span></span>

## <a name="initiate-and-extract-parameters-passed-to-powerapps"></a><span data-ttu-id="74ecf-123">Initier et extraire les paramètres transmis à Powerapps</span><span class="sxs-lookup"><span data-stu-id="74ecf-123">Initiate and Extract Parameters Passed to Powerapps</span></span>

<span data-ttu-id="74ecf-124">Le modèle **Initier et extraire les paramètres transmis à Powerapps** peut être utilisé comme point de départ pour tout scénario PowerApps spécifique à Attract.</span><span class="sxs-lookup"><span data-stu-id="74ecf-124">The **Initiate and Extract Parameters Passed to Powerapps** template can be used as a starting point for any PowerApps scenario that is specific to Attract.</span></span> <span data-ttu-id="74ecf-125">Il inclut tous les paramètres par défaut qui sont passés par Attract, par exemple, **Candidature**, **ID du candidat**et **JobID**.</span><span class="sxs-lookup"><span data-stu-id="74ecf-125">It includes all the default parameters that are passed by Attract, such as **Job Application**, **Candidate ID**, and **JobID**.</span></span>

<span data-ttu-id="74ecf-126">Il peut être utilisé pour récupérer un écran d'évaluation de candidat. Ainsi, un responsable du recrutement peut afficher l'évaluation qu'un candidat a remplie.</span><span class="sxs-lookup"><span data-stu-id="74ecf-126">This template can be used to retrieve a candidate assessment form, so that a hiring manager can view the assessment that a candidate filled in.</span></span>

<span data-ttu-id="74ecf-127">Les applications créées à l'aide de PowerApps peuvent être intégrées dans le modèle de poste dans Attract.</span><span class="sxs-lookup"><span data-stu-id="74ecf-127">Apps that are created by using PowerApps can be embedded into the job template in Attract.</span></span>

<span data-ttu-id="74ecf-128">Pour télécharger le modèle **Initier et extraire les paramètres transmis à Powerapps** et la structure de l'entité personnalisée, accédez à [Initier et extraire les paramètres transmis à Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) dans le Centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74ecf-128">To download the **Initiate and Extract Parameters Passed to Powerapps** template and Custom Entity Structure, go to [Initiate and Extract Parameters Passed to Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) on the Microsoft Download Center.</span></span>

## <a name="integration-with-office-365"></a><span data-ttu-id="74ecf-129">Intégration à Office 365</span><span class="sxs-lookup"><span data-stu-id="74ecf-129">Integration with Office 365</span></span>

<span data-ttu-id="74ecf-130">L'application **Intégration à Office 365** peut être utilisée pour extraire les informations d'équipe pour les utilisateurs connectés à partir de Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="74ecf-130">The **Integration with Office 365** app can be used to extract team information for signed-in users from Microsoft Office 365.</span></span> <span data-ttu-id="74ecf-131">Elle référence les collaborateurs dans Talent pour extraire les informations de pointage d'arrivée et de départ et les enregistrements d'exception.</span><span class="sxs-lookup"><span data-stu-id="74ecf-131">It references workers in Talent to extract clock-in and clock-out details and exception recordings.</span></span> <span data-ttu-id="74ecf-132">Les informations de pointage d'arrivée et de départ sont stockées dans les entités personnalisées Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="74ecf-132">Clock-in and Clock-out details are stored in custom Common Data Service entities.</span></span> <span data-ttu-id="74ecf-133">On suppose que ces informations sont renseignées par des systèmes tiers par l'intermédiaire de l'intégration.</span><span class="sxs-lookup"><span data-stu-id="74ecf-133">The assumption is that these details are filled in from third-party systems via integration.</span></span>

<span data-ttu-id="74ecf-134">Cette application peut être étendue pour être utilisée pour d'autres scénarios.</span><span class="sxs-lookup"><span data-stu-id="74ecf-134">This app can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="74ecf-135">Par exemple, elle peut servir à afficher les informations de congés d'équipe, les événements de calendrier, et tout événement spécifique à une équipe.</span><span class="sxs-lookup"><span data-stu-id="74ecf-135">For example, it can be used to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="74ecf-136">Pour télécharger l'application **Intégration à Office 365** et la structure d'entité personnalisée, accédez à [Intégration à Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) dans le Centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74ecf-136">To download the **Integration with Office 365** app and Custome Entity Structure, go to [Integration with Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="flow--email-notification"></a><span data-ttu-id="74ecf-137">Flow – Notification par e-mail</span><span class="sxs-lookup"><span data-stu-id="74ecf-137">Flow – Email Notification</span></span>

<span data-ttu-id="74ecf-138">Le modèle **Flow – Notification par e-mail** peut être utilisé pour les scénarios de notification par e-mail.</span><span class="sxs-lookup"><span data-stu-id="74ecf-138">The **Flow – Email Notification** template can be used for email notification scenarios.</span></span> <span data-ttu-id="74ecf-139">Il peut être utilisé pour déclencher des notifications par e-mail aux candidats rejetés par l'équipe de recrutement à une étape quelconque du processus.</span><span class="sxs-lookup"><span data-stu-id="74ecf-139">It can be used to trigger notification emails to candidates that the hiring team rejects during any stage of the recruiting process.</span></span>

<span data-ttu-id="74ecf-140">Ce modèle peut être étendu pour suivre les modifications du statut du candidat tout au long du processus de recrutement, et pour envoyer des notifications à l'équipe de recrutement et au candidat.</span><span class="sxs-lookup"><span data-stu-id="74ecf-140">This template can be extended to track changes to the candidate stage throughout the recruiting process, and to send notifications to the hiring team and candidate.</span></span>

<span data-ttu-id="74ecf-141">En général, pour les entités enregistrées dans Common Data Service, les flux peuvent être paramétrés de manière à envoyer des notifications pour les événements qui se produisent dans Core HR, Attract ou Dynamics 365 Talent : Onboard.</span><span class="sxs-lookup"><span data-stu-id="74ecf-141">In general, for entities that are stored in Common Data Service, flows can be set up to send notifications for events that occur in Core HR, Attract, or Dynamics 365 Talent: Onboard.</span></span>

<span data-ttu-id="74ecf-142">Pour télécharger le modèle **Flow – Notification par e-mail** et la structure de l'entité personnalisée, accédez à [Flow – Notification par e-mail](https://go.microsoft.com/fwlink/?linkid=2082103) dans le Centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74ecf-142">To download the **Flow – Email Notification** template, go to [Flow – Email Notification](https://go.microsoft.com/fwlink/?linkid=2082103) on the Microsoft Download Center.</span></span>

## <a name="flow--sql-connect-and-execute"></a><span data-ttu-id="74ecf-143">Flow – Connexion et exécution SQL</span><span class="sxs-lookup"><span data-stu-id="74ecf-143">Flow – SQL Connect and execute</span></span>

<span data-ttu-id="74ecf-144">Le modèle **Flow – Connexion et exécution SQL** se connecte à Microsoft SQL Server et active les requêtes SQL à exécuter.</span><span class="sxs-lookup"><span data-stu-id="74ecf-144">The **Flow – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="74ecf-145">Bien que ce modèle soit conçu pour lire et mettre à jour les tables SQL, il peut être étendu de manière à être utilisé pour d'autres scénarios.</span><span class="sxs-lookup"><span data-stu-id="74ecf-145">Although this template is designed to read and update SQL tables, it can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="74ecf-146">Par exemple, il peut être utilisé pour remplir une table intermédiaire dans Common Data Service avec des enregistrements de SQL Server, et pour synchroniser périodiquement la table intermédiaire à l'aide d'un envoi incrémentiel de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="74ecf-146">For example, it can be used to fill a staging table in Common Data Service with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="74ecf-147">Pour télécharger le modèle **Flow – Connexion et exécution SQL**, accédez à [Flow – Connexion et exécution SQL](https://go.microsoft.com/fwlink/?linkid=2081789) dans le Centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74ecf-147">To download the **Flow – SQL Connect and execute** template, go to [Flow – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="flow--sharepoint-integration"></a><span data-ttu-id="74ecf-148">Intégration Flow – SharePoint</span><span class="sxs-lookup"><span data-stu-id="74ecf-148">Flow – SharePoint Integration</span></span>

<span data-ttu-id="74ecf-149">Le modèle **Intégration Flow – SharePoint** peut être utilisé pour lire les données d'une liste Microsoft SharePoint, comparer cette liste avec les valeurs de champ d'une entité Common Data Service, et envoyer les résultats de la comparaison dans un e-mail de notification.</span><span class="sxs-lookup"><span data-stu-id="74ecf-149">The **Flow – SharePoint Integration** template can be used to read data from a Microsoft SharePoint list, compare the list with field values for any Common Data Service entity, and send the results of the comparison as a notification email.</span></span> 

<span data-ttu-id="74ecf-150">Une organisation peut avoir un besoin urgent d'un certain ensemble de qualifications.</span><span class="sxs-lookup"><span data-stu-id="74ecf-150">An organization might have a set of skills that it urgently requires.</span></span> <span data-ttu-id="74ecf-151">Ces qualifications peuvent être enregistrées dans SharePoint sous forme de liste SharePoint.</span><span class="sxs-lookup"><span data-stu-id="74ecf-151">These skills can be stored in SharePoint as a SharePoint list.</span></span> <span data-ttu-id="74ecf-152">Lorsqu'un candidat postule à un poste associé à un ensemble de qualifications répertorié, s'il existe une bonne correspondance entre les qualifications du candidat et les qualifications enregistrées dans SharePoint, un e-mail de notification est envoyé.</span><span class="sxs-lookup"><span data-stu-id="74ecf-152">When a candidate applies for any job that a set of required skills is listed for, if there is a significant match between the candidate's skill and the skills that are stored in SharePoint, a notification email is sent.</span></span> <span data-ttu-id="74ecf-153">De cette manière, les postes à pourvoir en urgence sont plus vite pourvus car les notifications aident les recruteurs à atteindre des candidats dans toute l'organisation.</span><span class="sxs-lookup"><span data-stu-id="74ecf-153">In this way, positions that are urgently required are filled faster, because the notifications help recruiters reach out and cross-hire candidates throughout the organization.</span></span>

<span data-ttu-id="74ecf-154">Ce modèle peut être étendu pour être utilisé dans tout scénario utilisant l'intégration de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="74ecf-154">This template can be extended so that it can be used for any scenario that involves SharePoint integration.</span></span>

<span data-ttu-id="74ecf-155">Pour télécharger le modèle **Intégration Flow – SharePoint**, accédez à [Intégration Flow – SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) dans le Centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74ecf-155">To download the **Flow – SharePoint Integration** template, go to [Flow – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) on the Microsoft Download Center.</span></span>

## <a name="admin-console-to-manage-talent-pools"></a><span data-ttu-id="74ecf-156">Console d'administration pour gérer les viviers de talents</span><span class="sxs-lookup"><span data-stu-id="74ecf-156">Admin console to manage talent pools</span></span>

<span data-ttu-id="74ecf-157">Lorsque vous activez l'intégration avec LinkedIn, Attract crée automatiquement un vivier de talents LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="74ecf-157">When you enable integration with LinkedIn, Attract automatically createas a LinkedIn talent pool.</span></span> <span data-ttu-id="74ecf-158">Lorsqu'un recruteur échange un InMail avec une recrue via LinkedIn, Attract crée un profil pour la recrue, et celle-ci devient un membre du viviers de talents LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="74ecf-158">When a recruiter exchanges InMail with a recruit through LinkedIn, Attract creates a profile for the recruit, and the recruit becomes a member of the LinkedIn talent pool.</span></span> <span data-ttu-id="74ecf-159">Cette application PowerApps est utile pour réorganiser les candidats dans le vivier de talents en fonction des compétences.</span><span class="sxs-lookup"><span data-stu-id="74ecf-159">This PowerApps app is useful for reorganizing candidates in talent pools based on skill.</span></span>

<span data-ttu-id="74ecf-160">Exécutez cette application PowerApps comme console d'administration pour effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="74ecf-160">Run this PowerApps app as an admin console to perform the following tasks:</span></span>

- <span data-ttu-id="74ecf-161">Répertorier des candidat dans un vivier de talents</span><span class="sxs-lookup"><span data-stu-id="74ecf-161">List candidates in a talent pool</span></span>
- <span data-ttu-id="74ecf-162">Ajouter et supprimer des candidats d'un vivier de talents</span><span class="sxs-lookup"><span data-stu-id="74ecf-162">Add and remove candidates from a talent pool</span></span>
- <span data-ttu-id="74ecf-163">Déplacer des candidats vivier de talents à un autre</span><span class="sxs-lookup"><span data-stu-id="74ecf-163">Move candidates from one talent pool to another</span></span>
- <span data-ttu-id="74ecf-164">Déterminer si les candidats font déjà partie d'un vivier de talents avant de les déplacer</span><span class="sxs-lookup"><span data-stu-id="74ecf-164">Determine whether candidates are already part of a talent pool before moving them</span></span>
- <span data-ttu-id="74ecf-165">Vérifier les qualifications d'un candidat avant de le déplacer vers d'autres viviers de talents</span><span class="sxs-lookup"><span data-stu-id="74ecf-165">Check the skills of candidates before moving them to other talent pools</span></span>

<span data-ttu-id="74ecf-166">Cette application PowerApps utilise des relations plusieurs à plusieurs, afin que vous puissiez l'utiliser comme modèle pour d'autres cas où vous devez extraire des enregistrements avec des relations plusieurs à plusieurs.</span><span class="sxs-lookup"><span data-stu-id="74ecf-166">This PowerApps app uses many-to-many relationships, so you can use it as a template for other scenarios where you need to extract records that have many-to-many relationships.</span></span>

<span data-ttu-id="74ecf-167">Pour télécharger le modèle **Console d'administration pour gérer des viviers de talents**, accédez à la [console d'administration pour gérer les viviers de talents](https://www.microsoft.com/downloads/details.aspx?FamilyID=780a5eee-0e2a-4159-9a83-009f9ccdc469) dans le Centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74ecf-167">To download the **Admin console to manage talent pools** template,  go to [Admin console to manage talent pools](https://www.microsoft.com/downloads/details.aspx?FamilyID=780a5eee-0e2a-4159-9a83-009f9ccdc469) on the Microsoft Download Center.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="74ecf-168">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="74ecf-168">Additional resources</span></span>

[<span data-ttu-id="74ecf-169">Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="74ecf-169">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[<span data-ttu-id="74ecf-170">Migration d'application entre clients et environnements</span><span class="sxs-lookup"><span data-stu-id="74ecf-170">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/en-us/power-platform/admin/environment-and-tenant-migration)
