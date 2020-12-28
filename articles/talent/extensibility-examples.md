---
title: Étendre Talent avec Power Apps et Power Automate
description: Cet article décrit quelques exemples de scénarios d'extensibilité pour Microsoft Dynamics 365 Talent - Attract utilisant Microsoft Power Apps et Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: cfdf36e9486aa4853d3bf674afa73ec3a4d1c161
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529632"
---
# <a name="extend-talent-with-power-apps-and-power-automate"></a><span data-ttu-id="2bf04-103">Étendre Talent avec Power Apps et Power Automate</span><span class="sxs-lookup"><span data-stu-id="2bf04-103">Extend Talent with Power Apps and Power Automate</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="2bf04-104">Cet article décrit quelques exemples de scénarios d'extensibilité pour Microsoft Dynamics 365 Talent: Attract utilisant Microsoft Power Apps et Microsoft Power Automate.</span><span class="sxs-lookup"><span data-stu-id="2bf04-104">This article describes some examples of extensibility scenarios for Microsoft Dynamics 365 Talent: Attract that use Microsoft Power Apps and Microsoft Power Automate.</span></span> <span data-ttu-id="2bf04-105">Vous pouvez importer le module de solution associé à chaque exemple dans l’environnement de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="2bf04-105">You can import the solution package that is associated with each example into your Power Apps environment.</span></span> <span data-ttu-id="2bf04-106">Vous pouvez ensuite utiliser les modules comme orientation ou comme point de départ pour implémenter les scénarios qui s'appliquent à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2bf04-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2bf04-107">Pour utiliser les modèles et l'application décrits dans cet article « en l'état », veillez à les tester pour vous assurer qu'ils couvrent tous les scénarios spécifiques à votre implémentation.</span><span class="sxs-lookup"><span data-stu-id="2bf04-107">If you want to use the templates and app that are described in this article "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="2bf04-108">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="2bf04-108">Prerequisites</span></span>

- <span data-ttu-id="2bf04-109">Pour importer des modules, les utilisateurs doivent avoir l’autorisation **Créateur d’environnement**.</span><span class="sxs-lookup"><span data-stu-id="2bf04-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="2bf04-110">Pour exporter ou importer des applications, les utilisateurs doivent disposer d'une licence Power Apps Plan 2 ou une licence d'essai Power Apps Plan 2.</span><span class="sxs-lookup"><span data-stu-id="2bf04-110">To export or import apps, users must have a Power Apps Plan 2 license or a Power Apps Plan 2 trial license.</span></span>

## <a name="power-automate--form-connect"></a><span data-ttu-id="2bf04-111">Power Automate – Form Connect</span><span class="sxs-lookup"><span data-stu-id="2bf04-111">Power Automate – Form Connect</span></span>

<span data-ttu-id="2bf04-112">Le modèle **Power Automate – Form Connect** peut être utilisé pour lire des données de Microsoft Forms et les enregistrer dans une entité Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2bf04-112">The **Power Automate – Form Connect** template can be used to read data from Microsoft Forms and store it in a Common Data Service entity.</span></span>

<span data-ttu-id="2bf04-113">Ce modèle peut être étendu pour être utilisé pour d'autres scénarios.</span><span class="sxs-lookup"><span data-stu-id="2bf04-113">This template can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="2bf04-114">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="2bf04-114">Here are some examples:</span></span>

- <span data-ttu-id="2bf04-115">Captures des évaluations de candidats.</span><span class="sxs-lookup"><span data-stu-id="2bf04-115">Capture candidate assessments.</span></span>
- <span data-ttu-id="2bf04-116">Capture des résultats questionnaire de cours</span><span class="sxs-lookup"><span data-stu-id="2bf04-116">Capture results from course questionnaires.</span></span>
- <span data-ttu-id="2bf04-117">Compilation d'une bibliothèque de questions d'entretien pour les administrateurs des Ressources humaines (RH).</span><span class="sxs-lookup"><span data-stu-id="2bf04-117">Compile a library of interview questions for Human resources (HR) administrators.</span></span>
- <span data-ttu-id="2bf04-118">Capture de l'évaluation du processus d'entretien d'un candidat</span><span class="sxs-lookup"><span data-stu-id="2bf04-118">Capture a candidate's evaluation of the interview process</span></span>

<span data-ttu-id="2bf04-119">Dans Microsoft Dynamics 365 : Attract, vous pouvez utiliser les écrans dans le portail Candidat, et les candidats peuvent renseigner des informations.</span><span class="sxs-lookup"><span data-stu-id="2bf04-119">In Microsoft Dynamics 365: Attract, you can use forms in the candidate portal, where candidates fill in details.</span></span> <span data-ttu-id="2bf04-120">Les écrans peuvent également être incorporés comme activités dans un modèle de poste.</span><span class="sxs-lookup"><span data-stu-id="2bf04-120">You can also embed forms as activities in a job template.</span></span>

<span data-ttu-id="2bf04-121">Lorsqu'un candidat envoie un formulaire, Microsoft Power Automate capture l'envoi de l'écran, lit les données et les stocke dans l'entité Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2bf04-121">When a candidate submits a form, Microsoft Power Automate captures the form submission, reads the data, and stores it in the Common Data Service entity.</span></span>

<span data-ttu-id="2bf04-122">Pour télécharger le modèle **Power Automate – Form Connect** et la structure de l'entité personnalisée, accédez à [Power Automate – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) dans le Centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2bf04-122">To download the **Power Automate – Form Connect** template and Custom Entity Structure, go to [Power Automate – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) on the Microsoft Download Center.</span></span>

## <a name="power-automate--sharepoint-integration"></a><span data-ttu-id="2bf04-123">Intégration de Power Automate – SharePoint</span><span class="sxs-lookup"><span data-stu-id="2bf04-123">Power Automate – SharePoint Integration</span></span>

<span data-ttu-id="2bf04-124">Le modèle Intégration **Power Automate – SharePoint** peut être utilisé pour lire les données d'une liste Microsoft SharePoint, comparer cette liste avec les valeurs de champ d'une entité Common Data Service, et envoyer les résultats de la comparaison dans un e-mail de notification.</span><span class="sxs-lookup"><span data-stu-id="2bf04-124">The **Power Automate – SharePoint Integration** template can be used to read data from a Microsoft SharePoint list, compare the list with field values for any Common Data Service entity, and send the results of the comparison as a notification email.</span></span> 

<span data-ttu-id="2bf04-125">Une organisation peut avoir un besoin urgent d'un certain ensemble de qualifications.</span><span class="sxs-lookup"><span data-stu-id="2bf04-125">An organization might have a set of skills that it urgently requires.</span></span> <span data-ttu-id="2bf04-126">Ces qualifications peuvent être enregistrées dans SharePoint sous forme de liste SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2bf04-126">These skills can be stored in SharePoint as a SharePoint list.</span></span> <span data-ttu-id="2bf04-127">Lorsqu'un candidat postule à un poste associé à un ensemble de qualifications répertorié, s'il existe une bonne correspondance entre les qualifications du candidat et les qualifications enregistrées dans SharePoint, un e-mail de notification est envoyé.</span><span class="sxs-lookup"><span data-stu-id="2bf04-127">When a candidate applies for any job that a set of required skills is listed for, if there is a significant match between the candidate's skill and the skills that are stored in SharePoint, a notification email is sent.</span></span> <span data-ttu-id="2bf04-128">De cette manière, les postes à pourvoir en urgence sont plus vite pourvus car les notifications aident les recruteurs à atteindre des candidats dans toute l'organisation.</span><span class="sxs-lookup"><span data-stu-id="2bf04-128">This helps fill positions that are urgently required faster, because the notifications help recruiters cross-hire candidates throughout the organization.</span></span>

<span data-ttu-id="2bf04-129">Ce modèle peut être étendu pour être utilisé dans tout scénario utilisant l'intégration de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2bf04-129">This template can be extended so that it can be used for any scenario that involves SharePoint integration.</span></span>

<span data-ttu-id="2bf04-130">Pour télécharger le modèle **Power Automate – Intégration SharePoint**, accédez à [Power Automate – Intégration SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) dans le Centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2bf04-130">To download the **Power Automate – SharePoint Integration** template, go to [Power Automate – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) on the Microsoft Download Center.</span></span>

## <a name="referral-app"></a><span data-ttu-id="2bf04-131">Application de référence</span><span class="sxs-lookup"><span data-stu-id="2bf04-131">Referral App</span></span>

<span data-ttu-id="2bf04-132">Vous pouvez utiliser l'application de référence pour ajouter des candidats à un vivier de candidats partagé.</span><span class="sxs-lookup"><span data-stu-id="2bf04-132">You can use the Referral App to add candidates to a shared talent pool.</span></span> <span data-ttu-id="2bf04-133">Il est possible d'entrer le **Prénom**, le **Nom**, l'**E-mail** et l'**URL LinkedIn** en référence lors de la soumission d'un candidat.</span><span class="sxs-lookup"><span data-stu-id="2bf04-133">The referrer can enter **Firstname**, **Lastname**, **Email**, and **LinkedIn URL** when submitting a candidate.</span></span> <span data-ttu-id="2bf04-134">Les métadonnées de la source de la candidature sont ensuite renseignées par les informations de référence.</span><span class="sxs-lookup"><span data-stu-id="2bf04-134">The candidate source metadata is then populated with the referrer’s information.</span></span>

<span data-ttu-id="2bf04-135">Vous pouvez intégrer cette application dans l'espace de travail Libre-service employé pour soumettre des références, ou vous pouvez l'utiliser en tant que lien hypertexte dans le portail de l'entreprise et l'exécuter comme application autonome.</span><span class="sxs-lookup"><span data-stu-id="2bf04-135">You can embed this app in Employee self service for submitting referrals, or you can use it as a hyperlink in the corporate portal and run it as a stand-alone app.</span></span>

<span data-ttu-id="2bf04-136">Pour télécharger l'**Application de référence**, allez dans [Solution d'extensibilité Dynamics 365 Talent : Application de référence](https://www.microsoft.com/download/details.aspx?id=58497) dans le Centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2bf04-136">To download **Referral App**, go to [Dynamics 365 Talent extensibility solution: Referral App](https://www.microsoft.com/download/details.aspx?id=58497) on the Microsoft Download Center.</span></span> <span data-ttu-id="2bf04-137">Vous pouvez importer cette application et la personnaliser pour ajouter des fonctionnalités supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="2bf04-137">You can import this app and customize it to add additional functionality.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2bf04-138">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="2bf04-138">Additional resources</span></span>

[<span data-ttu-id="2bf04-139">Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="2bf04-139">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[<span data-ttu-id="2bf04-140">Migration d'application entre clients et environnements</span><span class="sxs-lookup"><span data-stu-id="2bf04-140">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
