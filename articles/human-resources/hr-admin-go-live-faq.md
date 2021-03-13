---
title: FAQ sur le lancement
description: Cette rubrique répertorie les questions fréquemment posées sur le lancement d'un projet de mise en œuvre de Dynamics 365 Human Resources.
author: rachel-profitt
manager: tfehr
ms.date: 10/13/2020
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
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c5041d515b261bb3e4b14885e0ec0ce788edf729
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112503"
---
# <a name="go-live-faq"></a><span data-ttu-id="b0313-103">FAQ sur le lancement</span><span class="sxs-lookup"><span data-stu-id="b0313-103">Go-live FAQ</span></span> 

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="b0313-104">Cette rubrique répertorie les questions fréquemment posées sur le lancement d'un projet de mise en œuvre de Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b0313-104">This topic lists frequently asked questions about how to go live with a Dynamics 365 Human Resources implementation project.</span></span> 

## <a name="when-can-i-configure-and-request-my-production-environment"></a><span data-ttu-id="b0313-105">Quand puis-je configurer et demander mon environnement de production ?</span><span class="sxs-lookup"><span data-stu-id="b0313-105">When can I configure and request my production environment?</span></span> 

<span data-ttu-id="b0313-106">En règle générale, un environnement de production est déployé après avoir satisfait aux critères suivants :</span><span class="sxs-lookup"><span data-stu-id="b0313-106">Typically, a production environment is deployed after meeting the following criteria:</span></span>

- <span data-ttu-id="b0313-107">Toutes les personnalisations sont entièrement codées.</span><span class="sxs-lookup"><span data-stu-id="b0313-107">All customizations are code-complete.</span></span>
- <span data-ttu-id="b0313-108">Le test d'acceptation par l'utilisateur (UAT) est terminé.</span><span class="sxs-lookup"><span data-stu-id="b0313-108">User acceptance testing (UAT) is complete.</span></span>
- <span data-ttu-id="b0313-109">Le client a approuvé la solution.</span><span class="sxs-lookup"><span data-stu-id="b0313-109">The customer has signed off on the solution.</span></span>
- <span data-ttu-id="b0313-110">Il n'y a pas de problèmes bloquant le lancement.</span><span class="sxs-lookup"><span data-stu-id="b0313-110">There are no blocking issues for go-live.</span></span> 

<span data-ttu-id="b0313-111">Lorsque les clients qualifiés en sont à ce stade, l'équipe Microsoft FastTrack travaillera avec l'équipe de projet pour effectuer une évaluation du lancement.</span><span class="sxs-lookup"><span data-stu-id="b0313-111">When qualified customers are at this stage, the Microsoft FastTrack team will work with the project team to do a go-live assessment.</span></span> 

## <a name="what-are-the-prerequisites-to-deploying-a-production-environment"></a><span data-ttu-id="b0313-112">Quelles sont les conditions préalables au déploiement d'un environnement de production ?</span><span class="sxs-lookup"><span data-stu-id="b0313-112">What are the prerequisites to deploying a production environment?</span></span> 

<span data-ttu-id="b0313-113">Pour obtenir la liste des prérequis, voir [Préparer le lancement](hr-admin-go-live-prepare.md).</span><span class="sxs-lookup"><span data-stu-id="b0313-113">For a list of the prerequisites, see [Prepare for go-live](hr-admin-go-live-prepare.md).</span></span> 

## <a name="what-is-a-go-live-assessment"></a><span data-ttu-id="b0313-114">Qu'est-ce qu'une évaluation du lancement ?</span><span class="sxs-lookup"><span data-stu-id="b0313-114">What is a go-live assessment?</span></span>  

<span data-ttu-id="b0313-115">L'évaluation du lancement fait partie du [Programme Microsoft FastTrack](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview).</span><span class="sxs-lookup"><span data-stu-id="b0313-115">The go-live assessment is part of the [Microsoft FastTrack program](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview).</span></span> <span data-ttu-id="b0313-116">Au cours de cet examen, un architecte de solution évalue si un projet de mise en œuvre est prêt pour une transition et un lancement réussis.</span><span class="sxs-lookup"><span data-stu-id="b0313-116">During this review, a solution architect assesses whether an implementation project is ready for a successful cutover and go-live.</span></span> <span data-ttu-id="b0313-117">Cet examen est obligatoire pour chaque projet d'implémentation avant de pouvoir demander à être lancé dans un environnement de production.</span><span class="sxs-lookup"><span data-stu-id="b0313-117">This review is mandatory for every implementation project before you can request to go live in a production environment.</span></span> 

## <a name="our-sandbox-environments-are-deployed-in-the-central-us-datacenter-we-want-our-production-environments-to-be-deployed-in-the-west-us-datacenter-can-i-select-west-us-as-the-datacenter-in-my-production-configuration"></a><span data-ttu-id="b0313-118">Nos environnements Sandbox sont déployés dans le centre de données USA Centre.</span><span class="sxs-lookup"><span data-stu-id="b0313-118">Our Sandbox environments are deployed in the Central US datacenter.</span></span> <span data-ttu-id="b0313-119">Nous voulons que nos environnements de production soient déployés dans le centre de données USA Ouest.</span><span class="sxs-lookup"><span data-stu-id="b0313-119">We want our Production environments to be deployed in the West US datacenter.</span></span> <span data-ttu-id="b0313-120">Puis-je sélectionner USA Ouest comme centre de données dans ma configuration de production ?</span><span class="sxs-lookup"><span data-stu-id="b0313-120">Can I select West US as the datacenter in my Production configuration?</span></span> 

<span data-ttu-id="b0313-121">LCS ne vous empêche pas de sélectionner un centre de données différent lorsque vous déployez un environnement Human Resources, mais nous vous recommandons vivement de ne pas sélectionner un centre de données différent.</span><span class="sxs-lookup"><span data-stu-id="b0313-121">LCS doesn't restrict you from selecting a different data center when you deploy a Human Resources environment, but we strongly recommend not selecting a different data center.</span></span>  

<span data-ttu-id="b0313-122">Si vous souhaitez que votre environnement de production se trouve dans le centre de données de l'ouest des États-Unis, vous devez d'abord redéployer vos environnements Sandbox dans le centre de données de l'ouest des États-Unis, les tester et vous déconnecter.</span><span class="sxs-lookup"><span data-stu-id="b0313-122">If you want your Production environment to be in the West US datacenter, you should first redeploy your Sandbox environments to the West US datacenter, test them, and sign off.</span></span> 

<span data-ttu-id="b0313-123">Pour plus d'informations sur la sélection du centre de données approprié, voir [Configuration réseau requise](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/system-requirements#network-requirements).</span><span class="sxs-lookup"><span data-stu-id="b0313-123">For information about selecting the correct datacenter, see [Network requirements](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/system-requirements#network-requirements).</span></span> 

## <a name="what-level-of-access-do-i-have-to-the-azure-resources-for-my-human-resources-environments"></a><span data-ttu-id="b0313-124">Quel niveau d'accès ai-je aux ressources Azure pour mes environnements Human Resources ?</span><span class="sxs-lookup"><span data-stu-id="b0313-124">What level of access do I have to the Azure resources for my Human Resources environments?</span></span>  

<span data-ttu-id="b0313-125">L'accès aux environnements Human Resources est limité.</span><span class="sxs-lookup"><span data-stu-id="b0313-125">Access to the Human Resources environments is limited.</span></span> <span data-ttu-id="b0313-126">Vous ne pouvez pas accéder à la machine virtuelle (VM) ou à Microsoft Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="b0313-126">You can't access the virtual machine (VM) or Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="b0313-127">Vous ne pouvez pas non plus accéder à la base de données via Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="b0313-127">You also can't access the database through Microsoft SQL Server Management Studio.</span></span> 

<span data-ttu-id="b0313-128">Bien que vous ne puissiez pas accéder à vos ressources Azure ou à l'environnement Dynamics 365 Human Resources directement, il existe des fonctionnalités supplémentaires que vous pouvez utiliser pour accéder à vos données :</span><span class="sxs-lookup"><span data-stu-id="b0313-128">Although you can't access your Azure resources or Dynamics 365 Human Resources environment directly, there are additional features you can use to access your data:</span></span>

- <span data-ttu-id="b0313-129">Vous pouvez déployer une base de données Azure SQL dans votre propre client Azure et utiliser la fonctionnalité Bring Your Own Database (BYOD) pour synchroniser les données.</span><span class="sxs-lookup"><span data-stu-id="b0313-129">You can deploy an Azure SQL database in your own Azure tenant and use the Bring Your Own Database (BYOD) feature to synchronize data.</span></span> <span data-ttu-id="b0313-130">Pour plus d’informations, consultez [Apporter votre propre base de données (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span><span class="sxs-lookup"><span data-stu-id="b0313-130">For more information, see [Bring your own database (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span></span>

- <span data-ttu-id="b0313-131">Vous pouvez utiliser l'intégration de Dataverse pour synchroniser les entités sélectionnées dans la base de données Dataverse.</span><span class="sxs-lookup"><span data-stu-id="b0313-131">You can use Dataverse integration to synchronize select entities into the Dataverse database.</span></span> <span data-ttu-id="b0313-132">Pour plus d’informations, consultez les [tables Dataverse](hr-developer-entities.md).</span><span class="sxs-lookup"><span data-stu-id="b0313-132">For more information, see [Dataverse tables](hr-developer-entities.md).</span></span> 

## <a name="how-often-is-my-production-database-backed-up"></a><span data-ttu-id="b0313-133">À quelle fréquence ma base de données de production est-elle sauvegardée ?</span><span class="sxs-lookup"><span data-stu-id="b0313-133">How often is my production database backed up?</span></span> 

<span data-ttu-id="b0313-134">Les bases de données sont protégées par des sauvegardes automatiques aux fréquences suivantes :</span><span class="sxs-lookup"><span data-stu-id="b0313-134">Databases are protected by automatic backups at the following frequencies:</span></span>

| <span data-ttu-id="b0313-135">Type de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="b0313-135">Type of backup</span></span> | <span data-ttu-id="b0313-136">Fréquence</span><span class="sxs-lookup"><span data-stu-id="b0313-136">Frequency</span></span> |
| --- | --- |
| <span data-ttu-id="b0313-137">Sauvegarde complète de base de données</span><span class="sxs-lookup"><span data-stu-id="b0313-137">Full database backup</span></span> | <span data-ttu-id="b0313-138">Toutes les semaines</span><span class="sxs-lookup"><span data-stu-id="b0313-138">Weekly</span></span> |
| <span data-ttu-id="b0313-139">Sauvegarde différentielle de base de données</span><span class="sxs-lookup"><span data-stu-id="b0313-139">Differential database backup</span></span> | <span data-ttu-id="b0313-140">Toutes les 12 à 24 heures</span><span class="sxs-lookup"><span data-stu-id="b0313-140">Every 12-24 hours</span></span> |
| <span data-ttu-id="b0313-141">Sauvegarde du journal des transactions</span><span class="sxs-lookup"><span data-stu-id="b0313-141">Transaction log backup</span></span> | <span data-ttu-id="b0313-142">Toutes les 5 à 10 minutes</span><span class="sxs-lookup"><span data-stu-id="b0313-142">Every 5 to 10 minutes</span></span> |

<span data-ttu-id="b0313-143">Microsoft conserve suffisamment de sauvegardes pour permettre la restauration à un moment donné (PITR) au cours des 14 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="b0313-143">Microsoft retains sufficient backups to allow for Point in Time Restore (PITR) within the last 14 days.</span></span> 

<span data-ttu-id="b0313-144">Pour plus d'informations, voir [En savoir plus sur les sauvegardes de base de données SQL](https://docs.microsoft.com/azure/azure-sql/database/automated-backups-overview?tabs=single-database).</span><span class="sxs-lookup"><span data-stu-id="b0313-144">For more information, see [Learn about automatic SQL Database backups](https://docs.microsoft.com/azure/azure-sql/database/automated-backups-overview?tabs=single-database).</span></span> 

## <a name="can-i-request-a-copy-of-the-backup-of-my-production-database"></a><span data-ttu-id="b0313-145">Puis-je demander une copie de la sauvegarde de ma base de données de production ?</span><span class="sxs-lookup"><span data-stu-id="b0313-145">Can I request a copy of the backup of my production database?</span></span> 

<span data-ttu-id="b0313-146">Non.</span><span class="sxs-lookup"><span data-stu-id="b0313-146">No.</span></span> <span data-ttu-id="b0313-147">Cependant, vous pouvez soumettre une demande de service d'actualisation de la base de données pour copier votre environnement de production dans votre environnement Sandbox.</span><span class="sxs-lookup"><span data-stu-id="b0313-147">You can submit a database refresh service request to copy your Production environment to your Sandbox environment, however.</span></span> <span data-ttu-id="b0313-148">Vous pouvez déployer une base de données Azure SQL dans votre propre client Azure et utiliser la fonctionnalité BYOD pour synchroniser les données de votre environnement de production.</span><span class="sxs-lookup"><span data-stu-id="b0313-148">You can deploy an Azure SQL database in your own Azure tenant and use the BYOD feature to synchronize data from your Production environment.</span></span> <span data-ttu-id="b0313-149">Pour plus d’informations, consultez [Apporter votre propre base de données (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span><span class="sxs-lookup"><span data-stu-id="b0313-149">For more information, see [Bring your own database (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span></span> 

## <a name="how-do-i-move-my-sandbox-environment-to-production-for-go-live"></a><span data-ttu-id="b0313-150">Comment déplacer mon environnement Sandbox vers un environnement de production pour le lancement ?</span><span class="sxs-lookup"><span data-stu-id="b0313-150">How do I move my Sandbox environment to Production for go-live?</span></span> 

<span data-ttu-id="b0313-151">Étant donné qu'aucune fonction de copie n'est disponible pour déplacer votre environnement d'un environnement Sandbox vers un environnement de production, vous devez utiliser des packages de données pour déplacer des données dans votre environnement de production.</span><span class="sxs-lookup"><span data-stu-id="b0313-151">Because a copy feature isn't available to move your environment from a Sandbox to a Production environment, you must use data packages to move data into your Production environment.</span></span>  

<span data-ttu-id="b0313-152">Nous vous recommandons de conserver une liste claire des entités configurées dans votre bac à sable tout au long du projet.</span><span class="sxs-lookup"><span data-stu-id="b0313-152">We recommend maintaining a clear list of entities configured in your Sandbox throughout the project.</span></span> <span data-ttu-id="b0313-153">Testez ensuite le processus de basculement et de migration de tous les packages de données nécessaires à votre lancement.</span><span class="sxs-lookup"><span data-stu-id="b0313-153">Then test the process of cutover and migration of any data packages needed for your go-live.</span></span> <span data-ttu-id="b0313-154">Vous devez déplacer manuellement tous les packages de données dans l'environnement de production lorsque vous êtes prêt pour le lancement.</span><span class="sxs-lookup"><span data-stu-id="b0313-154">You must manually move any data packages into the Production environment when you are ready to go live.</span></span> 

## <a name="what-should-i-do-if-my-production-environment-is-down"></a><span data-ttu-id="b0313-155">Que dois-je faire si mon environnement de production est en panne ?</span><span class="sxs-lookup"><span data-stu-id="b0313-155">What should I do if my Production environment is down?</span></span> 

<span data-ttu-id="b0313-156">Pour signaler une interruption de l'environnement de production, suivez le processus décrit dans [Signaler une panne de production](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/report-production-outage).</span><span class="sxs-lookup"><span data-stu-id="b0313-156">To report a Production outage, follow the process described in [Report a production outage](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/report-production-outage).</span></span> 

 ## <a name="see-also"></a><span data-ttu-id="b0313-157">Voir également :</span><span class="sxs-lookup"><span data-stu-id="b0313-157">See also</span></span>

 [<span data-ttu-id="b0313-158">Préparation au lancement</span><span class="sxs-lookup"><span data-stu-id="b0313-158">Prepare for go-live</span></span>](hr-admin-go-live-prepare.md)
