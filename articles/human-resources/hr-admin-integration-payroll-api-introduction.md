---
title: Présentation de l'API d'intégration de la paie
description: Cette rubrique décrit l'API d'intégration de la paie de Dynamics 365 Human Resources.
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
ms.author: jcart
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3a7be5ad42642de48ffdb2731a1300a953c5ede4
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022761"
---
# <a name="payroll-integration-api-introduction"></a><span data-ttu-id="580e9-103">Présentation de l'API d'intégration de la paie</span><span class="sxs-lookup"><span data-stu-id="580e9-103">Payroll integration API introduction</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="580e9-104">Ce document décrit l'API d'intégration de la paie de Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="580e9-104">This document describes the Dynamics 365 Human Resources Payroll integration API.</span></span> <span data-ttu-id="580e9-105">L'API permet de rationnaliser de bout en bout les intégrations entre Human Resources et les systèmes de paie partenaires.</span><span class="sxs-lookup"><span data-stu-id="580e9-105">The API enables streamlined end-to-end integrations between Human Resources and partnering payroll systems.</span></span> <span data-ttu-id="580e9-106">L'expérience intégrée commence dans Human Resources avec le profil du collaborateur, le salaire et les déductions, et les informations sur les cotisations.</span><span class="sxs-lookup"><span data-stu-id="580e9-106">The integrated experience begins in Human Resources with the employee profile, salary and deduction, and contribution information.</span></span> <span data-ttu-id="580e9-107">Lorsque vous embauchez un collaborateur et que vous saisissez le profil et les informations de paie requis dans Human Resources, le système de paie extrait ces informations pour les utiliser lors du traitement de la paie.</span><span class="sxs-lookup"><span data-stu-id="580e9-107">When you hire an employee and enter the required profile and pay information into Human Resources, the payroll system pulls this information to use when processing payroll.</span></span> <span data-ttu-id="580e9-108">Toutes les mises à jour apportées aux informations du collaborateur ou de la paie sont également extraites pour être utilisées dans les cycles de paie ultérieurs.</span><span class="sxs-lookup"><span data-stu-id="580e9-108">Any updates made to the employee or pay information are also pulled for use in later pay runs.</span></span>

![Flux d’intégration de la paie](media/hr-admin-integration-payroll-api-introduction-flow.png)

<span data-ttu-id="580e9-110">Pour permettre l’intégration, Human Resources comprend les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="580e9-110">To enable the integration, Human Resources includes the following components:</span></span>

- <span data-ttu-id="580e9-111">Fonctionnalité pour marquer un collaborateur comme Prêt pour le paiement</span><span class="sxs-lookup"><span data-stu-id="580e9-111">Functionality to mark an employee as ready to pay</span></span>
- <span data-ttu-id="580e9-112">Une API d’intégration ouvrant la nouvelle fonctionnalité à l’intégration d’applications</span><span class="sxs-lookup"><span data-stu-id="580e9-112">An integration API opening up the new functionality to integrating applications</span></span>

## <a name="microsoft-dataverse"></a><span data-ttu-id="580e9-113">Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="580e9-113">Microsoft Dataverse</span></span>

<span data-ttu-id="580e9-114">Cette API repose sur Microsoft Dataverse (auparavant Common Data Service).</span><span class="sxs-lookup"><span data-stu-id="580e9-114">This API is built on Microsoft Dataverse (formerly Common Data Service).</span></span> <span data-ttu-id="580e9-115">Toutes les interactions RESTful avec cette API se font via l’API Web Microsoft Dataverse, qui utilise OData.</span><span class="sxs-lookup"><span data-stu-id="580e9-115">All RESTful interaction with this API is done via the Microsoft Dataverse Web API, which uses OData.</span></span> <span data-ttu-id="580e9-116">Cette API est un sous-ensemble de l’API Web Dataverse.</span><span class="sxs-lookup"><span data-stu-id="580e9-116">This API is a subset of the Dataverse Web API.</span></span> <span data-ttu-id="580e9-117">L’API Web Dataverse définit des caractéristiques telles que l’authentification, les SLA, les lots, le contrôle de la concurrence et la gestion des erreurs.</span><span class="sxs-lookup"><span data-stu-id="580e9-117">The Dataverse Web API defines characteristics such as authentication, SLAs, batch, concurrency control, and error handling.</span></span>

<span data-ttu-id="580e9-118">Pour plus d’informations générales sur l’API Web Microsoft Dataverse :</span><span class="sxs-lookup"><span data-stu-id="580e9-118">For more general information about the Microsoft Dataverse Web API, see:</span></span>

- [<span data-ttu-id="580e9-119">Qu’est-ce que Microsoft Dataverse ?</span><span class="sxs-lookup"><span data-stu-id="580e9-119">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)
- [<span data-ttu-id="580e9-120">Utiliser l’API Web Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="580e9-120">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)
- [<span data-ttu-id="580e9-121">Guide du développeur Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="580e9-121">Microsoft Dataverse developer guide</span></span>](/powerapps/developer/data-platform)

<span data-ttu-id="580e9-122">Cette documentation comprend des détails et des conseils pour les développeurs sur l'utilisation de l'API Web Dataverse, y compris les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="580e9-122">This documentation includes details and developer guidance for using the Dataverse Web API, including the following topics:</span></span>

- [<span data-ttu-id="580e9-123">S'authentifier auprès de Microsoft Dataverse avec l'API Web</span><span class="sxs-lookup"><span data-stu-id="580e9-123">Authenticate to Microsoft Dataverse with the Web API</span></span>](/powerapps/developer/data-platform/webapi/authenticate-web-api)
- [<span data-ttu-id="580e9-124">Effectuer des opérations à l'aide de l'API Web</span><span class="sxs-lookup"><span data-stu-id="580e9-124">Perform operations using the Web API</span></span>](/powerapps/developer/data-platform/webapi/perform-operations-web-api)
- [<span data-ttu-id="580e9-125">Utiliser Postman avec l'API Web</span><span class="sxs-lookup"><span data-stu-id="580e9-125">Use Postman with the Web API</span></span>](/powerapps/developer/data-platform/webapi/use-postman-web-api)
- [<span data-ttu-id="580e9-126">Utiliser le suivi des modifications pour synchroniser les données avec des systèmes externes</span><span class="sxs-lookup"><span data-stu-id="580e9-126">Use change tracking to synchronize data with external systems</span></span>](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems)

### <a name="virtual-tables-for-human-resources-in-dataverse"></a><span data-ttu-id="580e9-127">Tables virtuelles pour Human Resources dans Dataverse</span><span class="sxs-lookup"><span data-stu-id="580e9-127">Virtual tables for Human Resources in Dataverse</span></span>

<span data-ttu-id="580e9-128">Les points de terminaison de l’API d’intégration de la paie utilisent les capacités de la plateforme de table virtuelle de Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="580e9-128">The endpoints for the Payroll integration API use the virtual table platform capabilities of Microsoft Dataverse.</span></span> <span data-ttu-id="580e9-129">Par défaut, les tables virtuelles et leurs points de terminaison d’API associés ne sont pas déployés pour les environnements Human Resources, ce qui permet aux organisations de déterminer quels points de terminaison OData seront exposés pour l’environnement.</span><span class="sxs-lookup"><span data-stu-id="580e9-129">By default, the virtual tables and their associated API endpoints aren't deployed for Human Resources environments, enabling organizations to determine which OData endpoints will be exposed for the environment.</span></span> <span data-ttu-id="580e9-130">Pour utiliser l’API, les tables virtuelles des entités Ressources humaines doivent être générées pour l’environnement.</span><span class="sxs-lookup"><span data-stu-id="580e9-130">To use the API, the virtual tables for the Human Resources entities must be generated for the environment.</span></span>

<span data-ttu-id="580e9-131">Pour plus d’informations sur la génération des tables virtuelles pour l’API, consultez [Configurer les tables virtuelles Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).</span><span class="sxs-lookup"><span data-stu-id="580e9-131">For information on generating the virtual tables for the API, see [Configure Dataverse virtual tables](./hr-admin-integration-common-data-service-virtual-entities.md).</span></span>

## <a name="data-model"></a><span data-ttu-id="580e9-132">Modèle de données</span><span class="sxs-lookup"><span data-stu-id="580e9-132">Data model</span></span>

<span data-ttu-id="580e9-133">Le diagramme suivant illustre les relations au sein de l’API.</span><span class="sxs-lookup"><span data-stu-id="580e9-133">The following diagram illustrates relationships within the API.</span></span> <span data-ttu-id="580e9-134">Plusieurs types ont des clés étrangères vers d’autres entités préexistantes dans Human Resources qui ne sont pas illustrées ici.</span><span class="sxs-lookup"><span data-stu-id="580e9-134">Several types have foreign keys to other, pre-existing entities in Human Resources that aren't illustrated here.</span></span> <span data-ttu-id="580e9-135">Ce document fournit des informations sur les entités spécifiques aux scénarios d’intégration de la paie.</span><span class="sxs-lookup"><span data-stu-id="580e9-135">This document provides information on entities that are specific to payroll integration scenarios.</span></span> <span data-ttu-id="580e9-136">Cependant, il existe de nombreuses autres entités dans l’API Web Dataverse pour Human Resources qui peuvent également être pertinentes pour votre intégration.</span><span class="sxs-lookup"><span data-stu-id="580e9-136">However, there are many other entities in the Dataverse Web API for Human Resources that may also be relevant to your integration.</span></span> <span data-ttu-id="580e9-137">Certaines de ces entités sont référencées dans des relations de clé étrangère ou des propriétés de navigation.</span><span class="sxs-lookup"><span data-stu-id="580e9-137">Some of these entities are referenced in foreign key relationships or navigation properties.</span></span>

![Modèle de données de l’API d’intégration de la paie](media/hr-admin-payroll-api-data-model.png)

## <a name="payroll-employee-and-related-entities"></a><span data-ttu-id="580e9-139">Collaborateur avec paie et entités associées</span><span class="sxs-lookup"><span data-stu-id="580e9-139">Payroll employee and related entities</span></span>

<span data-ttu-id="580e9-140">Entités :</span><span class="sxs-lookup"><span data-stu-id="580e9-140">Entities:</span></span>

- [<span data-ttu-id="580e9-141">Employé avec paie</span><span class="sxs-lookup"><span data-stu-id="580e9-141">Payroll employee</span></span>](hr-admin-integration-payroll-api-payroll-employee.md)
- [<span data-ttu-id="580e9-142">Adresse du collaborateur avec paie</span><span class="sxs-lookup"><span data-stu-id="580e9-142">Payroll worker address</span></span>](hr-admin-integration-payroll-api-payroll-worker-address.md)
- [<span data-ttu-id="580e9-143">Régime de rémunération fixe avec paie</span><span class="sxs-lookup"><span data-stu-id="580e9-143">Payroll fixed compensation plan</span></span>](hr-admin-integration-ats-api-recruiting-request-education.md)
- [<span data-ttu-id="580e9-144">Tâche du poste de paie</span><span class="sxs-lookup"><span data-stu-id="580e9-144">Payroll position job</span></span>](hr-admin-integration-payroll-api-payroll-position-job.md)
- [<span data-ttu-id="580e9-145">Poste de paie</span><span class="sxs-lookup"><span data-stu-id="580e9-145">Payroll position</span></span>](hr-admin-integration-payroll-api-payroll-position.md)

## <a name="see-also"></a><span data-ttu-id="580e9-146">Voir également :</span><span class="sxs-lookup"><span data-stu-id="580e9-146">See also</span></span>

[<span data-ttu-id="580e9-147">Générer et réviser les entités de paie</span><span class="sxs-lookup"><span data-stu-id="580e9-147">Generate and review payroll entities</span></span>](hr-admin-integration-payroll-api-generate-review-entities.md)<br>
[<span data-ttu-id="580e9-148">Configurer les paramètres de Human Resources</span><span class="sxs-lookup"><span data-stu-id="580e9-148">Configure Human Resources parameters</span></span>](hr-setup-parameters.md)<br>
[<span data-ttu-id="580e9-149">Configurer les paramètres partagés de Human Resources</span><span class="sxs-lookup"><span data-stu-id="580e9-149">Configure Human Resources shared parameters</span></span>](hr-setup-shared-parameters.md)<br>
[<span data-ttu-id="580e9-150">Qu’est-ce que Microsoft Dataverse ?</span><span class="sxs-lookup"><span data-stu-id="580e9-150">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="580e9-151">Utiliser l’API Web Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="580e9-151">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]