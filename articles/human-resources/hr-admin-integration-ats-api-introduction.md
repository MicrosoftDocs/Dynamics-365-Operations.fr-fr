---
title: Introduction à l’API d’intégration du système de suivi des candidats
description: Cette rubrique décrit l’API d’intégration du système de suivi des candidats Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f70e377d6844b5c4f9201f0a561ad9cfcab2eda1
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890123"
---
# <a name="applicant-tracking-system-integration-api-introduction"></a><span data-ttu-id="47738-103">Introduction à l’API d’intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="47738-103">Applicant Tracking System integration API introduction</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="47738-104">Cette rubrique décrit l’API d’intégration du système de suivi des candidats Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="47738-104">This topic describes the Dynamics 365 Human Resources Applicant Tracking System (ATS) integration API.</span></span> <span data-ttu-id="47738-105">Cette API a pour but de permettre des intégrations rationalisées entre Dynamics 365 Human Resources et les ATS partenaires.</span><span class="sxs-lookup"><span data-stu-id="47738-105">The intent of the API is to enable streamlined integrations between Dynamics 365 Human Resources and partnering ATSs.</span></span>

![Flux d’intégration ATS](media/hr-admin-integration-ats-api-introduction-flow.png)

<span data-ttu-id="47738-107">L’expérience intégrée débute dans Human Resources lorsqu’un responsable du recrutement crée une demande de recrutement.</span><span class="sxs-lookup"><span data-stu-id="47738-107">The integrated experience begins in Human Resources when a hiring manager creates a recruiting request.</span></span> <span data-ttu-id="47738-108">Lorsque la demande est activée, l’ATS extrait le détail de la demande pour créer un projet de recrutement.</span><span class="sxs-lookup"><span data-stu-id="47738-108">When the request is activated, the ATS pulls the detail for the request to create a recruiting project.</span></span> <span data-ttu-id="47738-109">Ensuite, il suit le processus de recrutement pour sélectionner et embaucher un candidat.</span><span class="sxs-lookup"><span data-stu-id="47738-109">Then it follows the recruiting pipeline to select and hire a candidate for the position(s).</span></span> <span data-ttu-id="47738-110">Enfin, l’ATS complète l’intégration complète en envoyant le dossier du candidat sélectionné dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="47738-110">Finally, the ATS completes the round-trip integration by sending the selected candidate’s record into Human Resources.</span></span> <span data-ttu-id="47738-111">Le dossier de candidature peut ensuite passer par d’autres validations d’intégration et flux de travail pour créer la fiche de l’employé.</span><span class="sxs-lookup"><span data-stu-id="47738-111">The candidate record can then go through more onboarding validations and workflows to create the employee record.</span></span>

<span data-ttu-id="47738-112">Pour permettre l’intégration, Human Resources a ajouté les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="47738-112">To enable the integration, Human Resources has added the following components:</span></span>

1.  <span data-ttu-id="47738-113">Fonctionnalité pour créer une demande de recrutement.</span><span class="sxs-lookup"><span data-stu-id="47738-113">Functionality to create a recruiting request.</span></span>
2.  <span data-ttu-id="47738-114">Un profil de candidat étendu et les flux de travail associés.</span><span class="sxs-lookup"><span data-stu-id="47738-114">An expanded candidate profile and related workflows.</span></span>
3.  <span data-ttu-id="47738-115">Une API d’intégration ouvrant la nouvelle fonctionnalité à l’intégration d’applications.</span><span class="sxs-lookup"><span data-stu-id="47738-115">An integration API opening up the new functionality to integrating applications.</span></span>

<span data-ttu-id="47738-116">Pour plus d’informations sur la configuration et l’utilisation de la demande de recrutement et de la fonctionnalité de candidature, voir [Recruter des candidats à un poste](hr-personnel-recruit.md).</span><span class="sxs-lookup"><span data-stu-id="47738-116">For more information about setting up and using the recruiting request and candidate functionality, see [Recruit job candidates](hr-personnel-recruit.md).</span></span>

## <a name="microsoft-dataverse"></a><span data-ttu-id="47738-117">Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="47738-117">Microsoft Dataverse</span></span>

<span data-ttu-id="47738-118">Cette API repose sur Microsoft Dataverse (auparavant Common Data Service).</span><span class="sxs-lookup"><span data-stu-id="47738-118">This API is built on Microsoft Dataverse (formerly Common Data Service).</span></span> <span data-ttu-id="47738-119">Toutes les interactions RESTful avec cette API se font via l’API Web Microsoft Dataverse, qui utilise OData.</span><span class="sxs-lookup"><span data-stu-id="47738-119">All RESTful interaction with this API is done via the Microsoft Dataverse Web API, which uses OData.</span></span> <span data-ttu-id="47738-120">Cette API est un sous-ensemble de l’API Web Dataverse.</span><span class="sxs-lookup"><span data-stu-id="47738-120">This API is a subset of the Dataverse Web API.</span></span> <span data-ttu-id="47738-121">L’API Web Dataverse définit des caractéristiques telles que l’authentification, les SLA, les lots, le contrôle de la concurrence et la gestion des erreurs.</span><span class="sxs-lookup"><span data-stu-id="47738-121">The Dataverse Web API defines characteristics such as authentication, SLAs, batch, concurrency control, and error handling.</span></span>

<span data-ttu-id="47738-122">Pour plus d’informations générales sur l’API Web Microsoft Dataverse :</span><span class="sxs-lookup"><span data-stu-id="47738-122">For more general information about the Microsoft Dataverse Web API, see:</span></span>

- [<span data-ttu-id="47738-123">Qu’est-ce que Microsoft Dataverse ?</span><span class="sxs-lookup"><span data-stu-id="47738-123">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)
- [<span data-ttu-id="47738-124">Utiliser l’API Web Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="47738-124">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)
- [<span data-ttu-id="47738-125">Guide du développeur Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="47738-125">Microsoft Dataverse developer guide</span></span>](/powerapps/developer/data-platform)

<span data-ttu-id="47738-126">La documentation ci-dessus comprend des détails et des conseils pour les développeurs sur l’utilisation de l’API Web Dataverse, comme [gérer l’authentification](/powerapps/developer/data-platform/webapi/authenticate-web-api), [effectuer des opérations](/powerapps/developer/data-platform/webapi/perform-operations-web-api), [ utiliser Postman avec l’API](/powerapps/developer/data-platform/webapi/use-postman-web-api), et [utiliser le suivi des modifications ou des jetons delta](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) avec l’API.</span><span class="sxs-lookup"><span data-stu-id="47738-126">The above documentation includes detail and developer guidance on using the Dataverse Web API, such as [managing authentication](/powerapps/developer/data-platform/webapi/authenticate-web-api), [performing operations](/powerapps/developer/data-platform/webapi/perform-operations-web-api), [using Postman with the API](/powerapps/developer/data-platform/webapi/use-postman-web-api), and [using change tracking or delta tokens](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) with the API.</span></span>

### <a name="option-sets"></a><span data-ttu-id="47738-127">Jeux d’options</span><span class="sxs-lookup"><span data-stu-id="47738-127">Option sets</span></span>

<span data-ttu-id="47738-128">Le modèle de données pour l’API d’intégration ATS décrit dans ce document comprend des ensembles d’options qui fournissent des valeurs énumérées associées aux propriétés d’entité.</span><span class="sxs-lookup"><span data-stu-id="47738-128">The data model for the ATS integration API described in this document includes option sets that provide enumerated values associated with entity properties.</span></span> <span data-ttu-id="47738-129">Pour plus de détails sur l’utilisation des jeux d’options dans l’API Web Dataverse, voir [Créer et mettre à jour des ensembles d’options à l’aide de l’API Web](/powerapps/developer/data-platform/webapi/create-update-optionsets).</span><span class="sxs-lookup"><span data-stu-id="47738-129">For detail on working with option sets in the Dataverse Web API, see [Create and update option sets using the Web API](/powerapps/developer/data-platform/webapi/create-update-optionsets).</span></span> <span data-ttu-id="47738-130">Des ensembles d’options sont définis pour chaque environnement Dataverse.</span><span class="sxs-lookup"><span data-stu-id="47738-130">Option sets are defined for each Dataverse environment.</span></span>

### <a name="virtual-tables-for-human-resources-in-dataverse"></a><span data-ttu-id="47738-131">Tables virtuelles pour Human Resources dans Dataverse</span><span class="sxs-lookup"><span data-stu-id="47738-131">Virtual tables for Human Resources in Dataverse</span></span>

<span data-ttu-id="47738-132">Les points de terminaison de l’API d’intégration ATS utilisent les capacités de la plateforme de table virtuelle de Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="47738-132">The endpoints for the ATS integration API use the virtual table platform capabilities of Microsoft Dataverse.</span></span> <span data-ttu-id="47738-133">Par défaut, les tables virtuelles et leurs points de terminaison d’API associés ne sont pas déployés pour les environnements Human Resources, ce qui permet aux organisations de déterminer quels points de terminaison OData seront exposés pour l’environnement.</span><span class="sxs-lookup"><span data-stu-id="47738-133">By default, the virtual tables and their associated API endpoints are not deployed for Human Resources environments, enabling organizations to determine which OData endpoints will be exposed for the environment.</span></span> <span data-ttu-id="47738-134">Pour utiliser l’API, les tables virtuelles des entités Ressources humaines doivent être générées pour l’environnement.</span><span class="sxs-lookup"><span data-stu-id="47738-134">To use the API, the virtual tables for the Human Resources entities must be generated for the environment.</span></span> 

<span data-ttu-id="47738-135">Pour plus d’informations sur la génération des tables virtuelles pour l’API, consultez [Configurer les tables virtuelles Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).</span><span class="sxs-lookup"><span data-stu-id="47738-135">For information on generating the virtual tables for the API, see [Configure Dataverse virtual tables](./hr-admin-integration-common-data-service-virtual-entities.md).</span></span>

## <a name="data-model"></a><span data-ttu-id="47738-136">Modèle de données</span><span class="sxs-lookup"><span data-stu-id="47738-136">Data model</span></span>

<span data-ttu-id="47738-137">Le modèle de données est centré autour de deux entités principales :</span><span class="sxs-lookup"><span data-stu-id="47738-137">The data model is centered around two main entities:</span></span>

- <span data-ttu-id="47738-138">**RecruitingRequest** représente une demande adressée à un ATS pour recruter un ou plusieurs candidats. Pour obtenir un exemple de requête, voir [Exemple de requête pour une demande de recrutement](hr-admin-integration-ats-api-recruiting-request-example-query.md).</span><span class="sxs-lookup"><span data-stu-id="47738-138">**RecruitingRequest** represents a request to an ATS to recruit for one or more open positions.For an example query, see [Example query for Recruiting request](hr-admin-integration-ats-api-recruiting-request-example-query.md).</span></span>
- <span data-ttu-id="47738-139">**CandidateToHire** représente les détails d’un candidat qui a accepté une offre de poste.</span><span class="sxs-lookup"><span data-stu-id="47738-139">**CandidateToHire** represents details of a candidate who has accepted an offer for a position.</span></span> <span data-ttu-id="47738-140">**Personne** représente l’individu qui est le candidat.</span><span class="sxs-lookup"><span data-stu-id="47738-140">**Person** represents the individual who is the candidate.</span></span> <span data-ttu-id="47738-141">Une personne peut avoir plusieurs rôles dans l’entreprise, tels que candidat, travailleur, employé ou sous-traitant.</span><span class="sxs-lookup"><span data-stu-id="47738-141">A person can have multiple roles in the company, such as candidate, worker, employee, or contractor.</span></span> <span data-ttu-id="47738-142">Pour un exemple de requête, voir [Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).</span><span class="sxs-lookup"><span data-stu-id="47738-142">For an example query, see [Example query for Candidate to hire](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).</span></span>

<span data-ttu-id="47738-143">Le diagramme suivant illustre les relations au sein de l’API.</span><span class="sxs-lookup"><span data-stu-id="47738-143">The following diagram illustrates relationships within the API.</span></span> <span data-ttu-id="47738-144">Plusieurs types ont des clés étrangères vers d’autres entités préexistantes dans Human Resources qui ne sont pas illustrées ici.</span><span class="sxs-lookup"><span data-stu-id="47738-144">Several types have foreign keys to other, pre-existing entities in Human Resources that aren't illustrated here.</span></span> <span data-ttu-id="47738-145">Ce document fournit des informations sur les entités spécifiques aux scénarios d’intégration de recrutement.</span><span class="sxs-lookup"><span data-stu-id="47738-145">This document provides information on entities that are specific to recruiting integration scenarios.</span></span> <span data-ttu-id="47738-146">Cependant, il existe de nombreuses autres entités dans l’API Web Dataverse pour Dynamics 365 Human Resources qui peuvent également être pertinentes pour votre intégration.</span><span class="sxs-lookup"><span data-stu-id="47738-146">However, there are many other entities in the Dataverse Web API for Dynamics 365 Human Resources that may also be relevant to your integration.</span></span> <span data-ttu-id="47738-147">Par exemple, vous pouvez également avoir besoin de détails sur les travailleurs, les emplois, les postes ou d’autres entités non définies ici.</span><span class="sxs-lookup"><span data-stu-id="47738-147">For example, you may also need detail for workers, jobs, positions, or other entities not defined here.</span></span> <span data-ttu-id="47738-148">Beaucoup de ces entités sont référencées dans des relations de clé étrangère ou des propriétés de navigation.</span><span class="sxs-lookup"><span data-stu-id="47738-148">Many of these entities are referenced in foreign key relationships or navigation properties.</span></span>

![Modèle de données de l’API d’intégration ATS](media/hr-admin-integration-ats-api-data-model.png)

## <a name="recruiting-request-and-related-entities-and-option-sets"></a><span data-ttu-id="47738-150">Demande de recrutement et entités et ensembles d’options associés</span><span class="sxs-lookup"><span data-stu-id="47738-150">Recruiting request and related entities and option sets</span></span>

<span data-ttu-id="47738-151">Exemple de requête :</span><span class="sxs-lookup"><span data-stu-id="47738-151">Example query:</span></span> 

- [<span data-ttu-id="47738-152">Exemple de requête pour une demande de recrutement</span><span class="sxs-lookup"><span data-stu-id="47738-152">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)

<span data-ttu-id="47738-153">Entités :</span><span class="sxs-lookup"><span data-stu-id="47738-153">Entities:</span></span>

- [<span data-ttu-id="47738-154">Demande de recrutement</span><span class="sxs-lookup"><span data-stu-id="47738-154">Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request.md)
- [<span data-ttu-id="47738-155">Poste de la demande de recrutement</span><span class="sxs-lookup"><span data-stu-id="47738-155">Recruiting request position</span></span>](hr-admin-integration-ats-api-recruiting-request-position.md)
- [<span data-ttu-id="47738-156">Compétence de la demande de recrutement</span><span class="sxs-lookup"><span data-stu-id="47738-156">Recruiting request skill</span></span>](hr-admin-integration-ats-api-recruiting-request-skill.md)
- [<span data-ttu-id="47738-157">Formation de la demande de recrutement</span><span class="sxs-lookup"><span data-stu-id="47738-157">Recruiting request education</span></span>](hr-admin-integration-ats-api-recruiting-request-education.md)
- [<span data-ttu-id="47738-158">Emplacement de la demande de recrutement</span><span class="sxs-lookup"><span data-stu-id="47738-158">Recruiting request location</span></span>](hr-admin-integration-ats-api-recruiting-request-location.md)

<span data-ttu-id="47738-159">Jeux d’options :</span><span class="sxs-lookup"><span data-stu-id="47738-159">Option sets:</span></span>

- [<span data-ttu-id="47738-160">Statut d’exonération d’un travail</span><span class="sxs-lookup"><span data-stu-id="47738-160">Job exempt status</span></span>](hr-admin-integration-ats-api-job-exempt-status.md)
- [<span data-ttu-id="47738-161">Statut du poste de demande de recrutement</span><span class="sxs-lookup"><span data-stu-id="47738-161">Recruiting request position status</span></span>](hr-admin-integration-ats-api-recruiting-request-position-status.md)
- [<span data-ttu-id="47738-162">Statut de la demande de recrutement</span><span class="sxs-lookup"><span data-stu-id="47738-162">Recruiting request status</span></span>](hr-admin-integration-ats-api-recruiting-request-status.md)
- [<span data-ttu-id="47738-163">Catégorie d’emploi réglementaire</span><span class="sxs-lookup"><span data-stu-id="47738-163">Regulatory job category</span></span>](hr-admin-integration-ats-api-regulatory-job-category.md)

## <a name="candidate-to-hire-and-related-entities-and-option-sets"></a><span data-ttu-id="47738-164">Candidat à l’embauche et entités connexes et ensembles d’options</span><span class="sxs-lookup"><span data-stu-id="47738-164">Candidate to hire and related entities and option sets</span></span>

<span data-ttu-id="47738-165">Exemple de requête :</span><span class="sxs-lookup"><span data-stu-id="47738-165">Example query:</span></span>

- [<span data-ttu-id="47738-166">Exemple de requête pour l’entité Candidat à l’embauche</span><span class="sxs-lookup"><span data-stu-id="47738-166">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

<span data-ttu-id="47738-167">Entités :</span><span class="sxs-lookup"><span data-stu-id="47738-167">Entities:</span></span>

- [<span data-ttu-id="47738-168">Candidat à l’embauche</span><span class="sxs-lookup"><span data-stu-id="47738-168">Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire.md)
- [<span data-ttu-id="47738-169">Personne</span><span class="sxs-lookup"><span data-stu-id="47738-169">Person</span></span>](hr-admin-integration-ats-api-person.md)
- [<span data-ttu-id="47738-170">Formation de la personne</span><span class="sxs-lookup"><span data-stu-id="47738-170">Person education</span></span>](hr-admin-integration-ats-api-person-education.md)
- [<span data-ttu-id="47738-171">Expérience professionnelle de la personne</span><span class="sxs-lookup"><span data-stu-id="47738-171">Person professional experience</span></span>](hr-admin-integration-ats-api-person-professional-experience.md)
- [<span data-ttu-id="47738-172">Adresse de la personne</span><span class="sxs-lookup"><span data-stu-id="47738-172">Person address</span></span>](hr-admin-integration-ats-api-person-address.md)
- [<span data-ttu-id="47738-173">Contact du tiers</span><span class="sxs-lookup"><span data-stu-id="47738-173">Party contact</span></span>](hr-admin-integration-ats-api-party-contact.md)
- [<span data-ttu-id="47738-174">Compétence de la personne</span><span class="sxs-lookup"><span data-stu-id="47738-174">Person skill</span></span>](hr-admin-integration-ats-api-person-skill.md)
- [<span data-ttu-id="47738-175">Niveau de classement</span><span class="sxs-lookup"><span data-stu-id="47738-175">Rating level</span></span>](hr-admin-integration-ats-api-rating-level.md)
- [<span data-ttu-id="47738-176">Certificat de la personne</span><span class="sxs-lookup"><span data-stu-id="47738-176">Person certificate</span></span>](hr-admin-integration-ats-api-person-certificate.md)
- [<span data-ttu-id="47738-177">Type de certificat</span><span class="sxs-lookup"><span data-stu-id="47738-177">Certificate type</span></span>](hr-admin-integration-ats-api-certificate-type.md)
- [<span data-ttu-id="47738-178">Présélection</span><span class="sxs-lookup"><span data-stu-id="47738-178">Person screening</span></span>](hr-admin-integration-ats-api-person-screening.md)
- [<span data-ttu-id="47738-179">Types de présélection</span><span class="sxs-lookup"><span data-stu-id="47738-179">Screening types</span></span>](hr-admin-integration-ats-api-screening-types.md)
- [<span data-ttu-id="47738-180">Numéro d’identification de la personne</span><span class="sxs-lookup"><span data-stu-id="47738-180">Person identification number</span></span>](hr-admin-integration-ats-api-person-identification-number.md)

<span data-ttu-id="47738-181">Jeux d’options :</span><span class="sxs-lookup"><span data-stu-id="47738-181">Option sets:</span></span>

- [<span data-ttu-id="47738-182">Résultat de l’intégration du candidat</span><span class="sxs-lookup"><span data-stu-id="47738-182">Applicant integration result</span></span>](hr-admin-integration-ats-api-applicant-integration-result.md)
- [<span data-ttu-id="47738-183">Vide Oui Non</span><span class="sxs-lookup"><span data-stu-id="47738-183">Blank Yes No</span></span>](hr-admin-integration-ats-api-blank-yes-no.md)
- [<span data-ttu-id="47738-184">État d’achèvement</span><span class="sxs-lookup"><span data-stu-id="47738-184">Completion status</span></span>](hr-admin-integration-ats-api-completion-status.md)
- [<span data-ttu-id="47738-185">Type de contact</span><span class="sxs-lookup"><span data-stu-id="47738-185">Contact type</span></span>](hr-admin-integration-ats-api-contact-type.md)
- [<span data-ttu-id="47738-186">Base des crédits de formation</span><span class="sxs-lookup"><span data-stu-id="47738-186">Education credit basis</span></span>](hr-admin-integration-ats-api-education-credit-basis.md)
- [<span data-ttu-id="47738-187">Sexe</span><span class="sxs-lookup"><span data-stu-id="47738-187">Gender</span></span>](hr-admin-integration-ats-api-gender.md)
- [<span data-ttu-id="47738-188">Situation de famille</span><span class="sxs-lookup"><span data-stu-id="47738-188">Marital status</span></span>](hr-admin-integration-ats-api-marital-status.md)
- [<span data-ttu-id="47738-189">Mois de l’année</span><span class="sxs-lookup"><span data-stu-id="47738-189">Months of year</span></span>](hr-admin-integration-ats-api-months-of-year.md)
- [<span data-ttu-id="47738-190">Non Oui</span><span class="sxs-lookup"><span data-stu-id="47738-190">No Yes</span></span>](hr-admin-integration-ats-api-no-yes.md)
- [<span data-ttu-id="47738-191">Unité de période</span><span class="sxs-lookup"><span data-stu-id="47738-191">Period unit</span></span>](hr-admin-integration-ats-api-period-unit.md)
- [<span data-ttu-id="47738-192">Fréquence de présélection</span><span class="sxs-lookup"><span data-stu-id="47738-192">Screening frequency</span></span>](hr-admin-integration-ats-api-screening-frequency.md)
- [<span data-ttu-id="47738-193">Date de début pour le calcul de la fréquence de présélection</span><span class="sxs-lookup"><span data-stu-id="47738-193">Screening frequency generate from</span></span>](hr-admin-integration-ats-api-screening-frequency-generate-from.md)
- [<span data-ttu-id="47738-194">Type de niveau de compétence</span><span class="sxs-lookup"><span data-stu-id="47738-194">Skill level type</span></span>](hr-admin-integration-ats-api-skill-level-type.md)

## <a name="see-also"></a><span data-ttu-id="47738-195">Voir également :</span><span class="sxs-lookup"><span data-stu-id="47738-195">See also</span></span>

[<span data-ttu-id="47738-196">Recruter des candidats à un poste</span><span class="sxs-lookup"><span data-stu-id="47738-196">Recruit job candidates</span></span>](hr-personnel-recruit.md)<br>
[<span data-ttu-id="47738-197">Qu’est-ce que Microsoft Dataverse ?</span><span class="sxs-lookup"><span data-stu-id="47738-197">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="47738-198">Utiliser l’API Web Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="47738-198">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)<br>
[<span data-ttu-id="47738-199">Créer et mettre à jour des ensembles d’options à l’aide de l’API Web</span><span class="sxs-lookup"><span data-stu-id="47738-199">Create and update option sets using the Web API</span></span>](/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]