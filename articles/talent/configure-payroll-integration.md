---
title: Configuration de l'intégration de la paie entre Talent et Dayforce
description: Cette rubrique explique comment configurer l'intégration entre Microsoft Dynamics 365 for Talent et Ceridian Dayforce afin de pouvoir traiter un cycle de paie.
author: andreabichsel
manager: AnnBe
ms.date: 03/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9a88bf61dbb12520b555ceb7363b1c646d95386e
ms.sourcegitcommit: 204e4554e409c39fbbf7b273ad138ce2809931a8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/26/2019
ms.locfileid: "898442"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="b96a8-103">Configurer l'intégration de la paie entre Talent et Dayforce</span><span class="sxs-lookup"><span data-stu-id="b96a8-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b96a8-104">L'intégration entre Microsoft Dynamics 365 for Talent et Ceridian Dayforce repose sur plusieurs étapes de configuration décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="b96a8-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="b96a8-105">Vous devez configurer l'intégration dans Talent et Dayforce avant de pouvoir traiter un cycle de paie.</span><span class="sxs-lookup"><span data-stu-id="b96a8-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="b96a8-106">Lorsque vous utilisez un service comme Dayforce pour compléter des cycles de paie, vous devez activer l'intégration dans Talent.</span><span class="sxs-lookup"><span data-stu-id="b96a8-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="b96a8-107">L'intégration nécessite des données spécifiques de Talent.</span><span class="sxs-lookup"><span data-stu-id="b96a8-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="b96a8-108">Par conséquent, vous devez vérifier que les données mises en correspondance avec Dayforce sont configurées dans Talent d'une manière prenant en charge l'intégration.</span><span class="sxs-lookup"><span data-stu-id="b96a8-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="b96a8-109">L'intégration utilise les larges catégories de données suivantes :</span><span class="sxs-lookup"><span data-stu-id="b96a8-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="b96a8-110">Données de ressources humaines</span><span class="sxs-lookup"><span data-stu-id="b96a8-110">Human resources data</span></span>
- <span data-ttu-id="b96a8-111">Données de rémunération</span><span class="sxs-lookup"><span data-stu-id="b96a8-111">Compensation data</span></span>
- <span data-ttu-id="b96a8-112">Données salariales, telles que des cycles de paie, des périodes de rémunération, et des codes de rémunération</span><span class="sxs-lookup"><span data-stu-id="b96a8-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="b96a8-113">Données sur les collaborateurs</span><span class="sxs-lookup"><span data-stu-id="b96a8-113">Worker data</span></span>

<span data-ttu-id="b96a8-114">Cette rubrique décrit la procédure à suivre pour activer l'intégration.</span><span class="sxs-lookup"><span data-stu-id="b96a8-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="b96a8-115">Elle décrit également les types de données et les détails de configuration que l'intégration nécessite.</span><span class="sxs-lookup"><span data-stu-id="b96a8-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="b96a8-116">Activer l'intégration</span><span class="sxs-lookup"><span data-stu-id="b96a8-116">Enable the integration</span></span>

<span data-ttu-id="b96a8-117">Dans Talent, vous devez activer l'intégration et entrer des informations de configuration pour vous connecter Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b96a8-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="b96a8-118">Si vous souhaitez que l'écriture comptable produite soit importée dans Microsoft Dynamics 365 for Finance and Operations, vous devez également configurer un compte de stockage Microsoft Azure et entrer la chaîne de connexion de stockage Azure dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b96a8-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="b96a8-119">Pour l'activer l'intégration dans Talent, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b96a8-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="b96a8-120">Sur la page **Administration du système**, sélectionnez **Configuration de l'intégration**.</span><span class="sxs-lookup"><span data-stu-id="b96a8-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="b96a8-121">Entrez le point de terminaison FTP (File Transfer Protocol) sécurisé et le chemin d'accès de dossier FTP sécurisé.</span><span class="sxs-lookup"><span data-stu-id="b96a8-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="b96a8-122">Entrez le nom d'utilisateur et le mot de passe de l'utilisateur qui accèdera au point de terminaison FTP et au chemin d'accès du dossier sécurisés.</span><span class="sxs-lookup"><span data-stu-id="b96a8-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="b96a8-123">Testez la connexion, au besoin, puis définissez l'option **Activation de l'intégration de la paie** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b96a8-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="b96a8-124">Lorsque l'intégration est activée, le package et les fichiers d'exportation de données sont créés, et la fréquence est définie.</span><span class="sxs-lookup"><span data-stu-id="b96a8-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="b96a8-125">Vous pouvez modifier la fréquence selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="b96a8-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="b96a8-126">Pour plus d'informations sur les comptes de stockage Azure et les chaînes de connexion de stockage Azure, consultez les rubriques Azure suivantes :</span><span class="sxs-lookup"><span data-stu-id="b96a8-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="b96a8-127">À propos des comptes de stockage Azure</span><span class="sxs-lookup"><span data-stu-id="b96a8-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="b96a8-128">Configurer les chaînes de connexion de stockage Azure</span><span class="sxs-lookup"><span data-stu-id="b96a8-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

## <a name="configure-your-data"></a><span data-ttu-id="b96a8-129">Configurer vos données</span><span class="sxs-lookup"><span data-stu-id="b96a8-129">Configure your data</span></span> 

<span data-ttu-id="b96a8-130">Pour traiter les paies, vous devez configurer les données des ressources humaines dans Talent.</span><span class="sxs-lookup"><span data-stu-id="b96a8-130">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="b96a8-131">Vous devez configurer les données organisationnelles, telles que les tâches et les postes, ainsi que les avantages et les informations de rémunération.</span><span class="sxs-lookup"><span data-stu-id="b96a8-131">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="b96a8-132">Ces informations fournissent des informations sur l'emploi, le salaire et les déductions nécessaires pour générer le salaire de l'employé.</span><span class="sxs-lookup"><span data-stu-id="b96a8-132">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="b96a8-133">Données des ressources humaines</span><span class="sxs-lookup"><span data-stu-id="b96a8-133">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="b96a8-134">Avantages</span><span class="sxs-lookup"><span data-stu-id="b96a8-134">Benefits</span></span> 

<span data-ttu-id="b96a8-135">Les ressources humaines proposent des outils de paramétrage et de mise à jour des avantages, des déductions et des plans de compensation des collaborateurs qu'une organisation offre ou gère pour ses collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="b96a8-135">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="b96a8-136">Lorsque vous créez des avantages, n'oubliez pas les données et les configurations suivantes utilisées dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b96a8-136">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="b96a8-137">Plans d'avantages</span><span class="sxs-lookup"><span data-stu-id="b96a8-137">Benefit plans</span></span>

- <span data-ttu-id="b96a8-138">Plan (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-138">Plan (required)</span></span>
- <span data-ttu-id="b96a8-139">Type (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-139">Type (required)</span></span>
- <span data-ttu-id="b96a8-140">Impact sur la paie (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-140">Payroll impact (required)</span></span>
- <span data-ttu-id="b96a8-141">Recouvrer les arriérés</span><span class="sxs-lookup"><span data-stu-id="b96a8-141">Recover arrears</span></span>
- <span data-ttu-id="b96a8-142">Méthode de déduction</span><span class="sxs-lookup"><span data-stu-id="b96a8-142">Deduction method</span></span>
- <span data-ttu-id="b96a8-143">Priorité de la déduction</span><span class="sxs-lookup"><span data-stu-id="b96a8-143">Deduction priority</span></span>
- <span data-ttu-id="b96a8-144">Période limite</span><span class="sxs-lookup"><span data-stu-id="b96a8-144">Limit period</span></span>
- <span data-ttu-id="b96a8-145">Montant limite</span><span class="sxs-lookup"><span data-stu-id="b96a8-145">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="b96a8-146">Avantages</span><span class="sxs-lookup"><span data-stu-id="b96a8-146">Benefits</span></span>

- <span data-ttu-id="b96a8-147">Plan (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-147">Plan (required)</span></span>
- <span data-ttu-id="b96a8-148">Type (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-148">Type (required)</span></span>
- <span data-ttu-id="b96a8-149">Option (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-149">Option (required)</span></span>
- <span data-ttu-id="b96a8-150">ID avantage (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-150">Benefit ID (required)</span></span>
- <span data-ttu-id="b96a8-151">Fréquence</span><span class="sxs-lookup"><span data-stu-id="b96a8-151">Frequency</span></span>
- <span data-ttu-id="b96a8-152">Base</span><span class="sxs-lookup"><span data-stu-id="b96a8-152">Basis</span></span>
- <span data-ttu-id="b96a8-153">Montant ou taux</span><span class="sxs-lookup"><span data-stu-id="b96a8-153">Amount or rate</span></span>
- <span data-ttu-id="b96a8-154">Code de rémunération</span><span class="sxs-lookup"><span data-stu-id="b96a8-154">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="b96a8-155">Fréquences prises en charge</span><span class="sxs-lookup"><span data-stu-id="b96a8-155">Supported frequencies</span></span> 

- <span data-ttu-id="b96a8-156">Hebdomadairement</span><span class="sxs-lookup"><span data-stu-id="b96a8-156">Weekly</span></span>
- <span data-ttu-id="b96a8-157">Bimensuelle</span><span class="sxs-lookup"><span data-stu-id="b96a8-157">Bi-weekly</span></span>
- <span data-ttu-id="b96a8-158">Bimensuel</span><span class="sxs-lookup"><span data-stu-id="b96a8-158">Semi-monthly</span></span>
- <span data-ttu-id="b96a8-159">Mensuellement</span><span class="sxs-lookup"><span data-stu-id="b96a8-159">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="b96a8-160">Bases pris en charge</span><span class="sxs-lookup"><span data-stu-id="b96a8-160">Supported bases</span></span> 

- <span data-ttu-id="b96a8-161">Montant fixe</span><span class="sxs-lookup"><span data-stu-id="b96a8-161">Fixed amount</span></span>
- <span data-ttu-id="b96a8-162">Pourcentage des rémunérations</span><span class="sxs-lookup"><span data-stu-id="b96a8-162">Percent of earnings</span></span>
- <span data-ttu-id="b96a8-163">Heures productives</span><span class="sxs-lookup"><span data-stu-id="b96a8-163">Productive hours</span></span>

<span data-ttu-id="b96a8-164">Dayforce crée les déductions suivantes, selon l'impact sur la paie défini dans le plan d'avantages.</span><span class="sxs-lookup"><span data-stu-id="b96a8-164">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="b96a8-165">Sélection dans Talent</span><span class="sxs-lookup"><span data-stu-id="b96a8-165">Selection in Talent</span></span>        | <span data-ttu-id="b96a8-166">Résultat dans Dayforce</span><span class="sxs-lookup"><span data-stu-id="b96a8-166">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="b96a8-167">None</span><span class="sxs-lookup"><span data-stu-id="b96a8-167">None</span></span>                       | <span data-ttu-id="b96a8-168">Aucune retenue n'est créée.</span><span class="sxs-lookup"><span data-stu-id="b96a8-168">No deduction is created.</span></span>                      |
| <span data-ttu-id="b96a8-169">Déduction uniquement</span><span class="sxs-lookup"><span data-stu-id="b96a8-169">Deduction only</span></span>             | <span data-ttu-id="b96a8-170">Une retenue employé est créée.</span><span class="sxs-lookup"><span data-stu-id="b96a8-170">An employee deduction is created.</span></span>             |
| <span data-ttu-id="b96a8-171">Contribution uniquement</span><span class="sxs-lookup"><span data-stu-id="b96a8-171">Contribution only</span></span>          | <span data-ttu-id="b96a8-172">Une retenue employeur est créée.</span><span class="sxs-lookup"><span data-stu-id="b96a8-172">An employer deduction is created.</span></span>             |
| <span data-ttu-id="b96a8-173">Déduction et contribution</span><span class="sxs-lookup"><span data-stu-id="b96a8-173">Deduction and contribution</span></span> | <span data-ttu-id="b96a8-174">Des retenues employé et employeur sont créées.</span><span class="sxs-lookup"><span data-stu-id="b96a8-174">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="b96a8-175">Pour plus d'informations sur la définition et la gestion des programmes d'avantages, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b96a8-175">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="b96a8-176">Communiquer le programme d'avantages à un employé</span><span class="sxs-lookup"><span data-stu-id="b96a8-176">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="b96a8-177">Créer un avantage</span><span class="sxs-lookup"><span data-stu-id="b96a8-177">Create a new benefit</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="b96a8-178">Définir les règles d'admissibilité et les stratégies relatives aux avantages</span><span class="sxs-lookup"><span data-stu-id="b96a8-178">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="b96a8-179">Inscrire et annuler l'inscription des travailleurs à des avantages</span><span class="sxs-lookup"><span data-stu-id="b96a8-179">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="b96a8-180">Rémunération</span><span class="sxs-lookup"><span data-stu-id="b96a8-180">Compensation</span></span> 

<span data-ttu-id="b96a8-181">La gestion des rémunérations est utilisée pour contrôler la rémunération de base et les primes.</span><span class="sxs-lookup"><span data-stu-id="b96a8-181">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="b96a8-182">Le salaire de base fixe et les augmentations pour mérite d'un employé sont contrôlés via les régimes de rémunération fixe.</span><span class="sxs-lookup"><span data-stu-id="b96a8-182">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="b96a8-183">Le paiement des primes (primes liées aux résultats, options d'achat d'actions et octrois d'actions), ainsi que les primes exceptionnelles, est contrôlé via les régimes de rémunération variable.</span><span class="sxs-lookup"><span data-stu-id="b96a8-183">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="b96a8-184">Dayforce utilise les informations de rémunération pour calculer le taux horaire ou annuel d'un employé.</span><span class="sxs-lookup"><span data-stu-id="b96a8-184">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="b96a8-185">Des plans de rémunération fixe et des conversions de taux de salaire sont requis.</span><span class="sxs-lookup"><span data-stu-id="b96a8-185">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="b96a8-186">Les employés doivent être associés à un plan de rémunération fixe.</span><span class="sxs-lookup"><span data-stu-id="b96a8-186">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="b96a8-187">Pour plus d'informations sur les plans de rémunération, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b96a8-187">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="b96a8-188">Créer des régimes de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="b96a8-188">Create fixed compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="b96a8-189">Créer des régimes de rémunération variable</span><span class="sxs-lookup"><span data-stu-id="b96a8-189">Create variable compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="b96a8-190">Développer les plans et la structure du salaire/de la rémunération</span><span class="sxs-lookup"><span data-stu-id="b96a8-190">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="b96a8-191">Traiter la rémunération</span><span class="sxs-lookup"><span data-stu-id="b96a8-191">Process compensation</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="b96a8-192">Définir le processus de rémunération et calculer les résultats</span><span class="sxs-lookup"><span data-stu-id="b96a8-192">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="b96a8-193">Inscrire un employé à un régime de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="b96a8-193">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="b96a8-194">Inscrire un employé à un régime de rémunération variable</span><span class="sxs-lookup"><span data-stu-id="b96a8-194">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="b96a8-195">Postes</span><span class="sxs-lookup"><span data-stu-id="b96a8-195">Jobs</span></span> 

<span data-ttu-id="b96a8-196">Une tâche est un ensemble de tâches et de responsabilités attribuées à la personne affectée à la tâche.</span><span class="sxs-lookup"><span data-stu-id="b96a8-196">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="b96a8-197">Pour plus d'informations, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b96a8-197">For more information, see the following topics:</span></span>

- [<span data-ttu-id="b96a8-198">Paramétrage des composants d'une tâche</span><span class="sxs-lookup"><span data-stu-id="b96a8-198">Setting up the components of a job</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="b96a8-199">Définir les nouvelles tâches</span><span class="sxs-lookup"><span data-stu-id="b96a8-199">Define new jobs</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="b96a8-200">Postes</span><span class="sxs-lookup"><span data-stu-id="b96a8-200">Positions</span></span>

<span data-ttu-id="b96a8-201">Un poste est une instance individuelle d'une tâche.</span><span class="sxs-lookup"><span data-stu-id="b96a8-201">A position is an individual instance of a job.</span></span> <span data-ttu-id="b96a8-202">Par exemple, le poste « Responsable des ventes (est) » est l'un des postes associés à la tâche « Responsable des ventes ».</span><span class="sxs-lookup"><span data-stu-id="b96a8-202">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="b96a8-203">Un poste existe dans un département.</span><span class="sxs-lookup"><span data-stu-id="b96a8-203">A position exists in a department.</span></span> <span data-ttu-id="b96a8-204">Seul un collaborateur peut être associé à chaque poste.</span><span class="sxs-lookup"><span data-stu-id="b96a8-204">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="b96a8-205">Gardez à l'esprit les données et la configuration suivantes lorsque vous paramétrez des postes :</span><span class="sxs-lookup"><span data-stu-id="b96a8-205">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="b96a8-206">Poste (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-206">Position (required)</span></span>
- <span data-ttu-id="b96a8-207">Description (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-207">Description (required)</span></span>
- <span data-ttu-id="b96a8-208">Tâche (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-208">Job (required)</span></span>
- <span data-ttu-id="b96a8-209">Département (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-209">Department (required)</span></span>
- <span data-ttu-id="b96a8-210">Type de poste (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-210">Position type (required)</span></span>
- <span data-ttu-id="b96a8-211">Équivalent temps plein</span><span class="sxs-lookup"><span data-stu-id="b96a8-211">Full-time equivalent</span></span>
- <span data-ttu-id="b96a8-212">Durée annuelle normale (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-212">Annual regular hours (required)</span></span>
- <span data-ttu-id="b96a8-213">Rémunéré par l'entité juridique (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-213">Paid by legal entity (required)</span></span>
- <span data-ttu-id="b96a8-214">Cycle de paie (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-214">Pay cycle (required)</span></span>
- <span data-ttu-id="b96a8-215">Dimension financière par défaut – Centre de coût (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-215">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="b96a8-216">Affectation du collaborateur – Collaborateur, début de l'affectation, fin de l'affectation, code motif</span><span class="sxs-lookup"><span data-stu-id="b96a8-216">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="b96a8-217">Si plusieurs postes dans un même département sont associés à la même tâche, ils sont consolidés un seul poste dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b96a8-217">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="b96a8-218">Pour plus d'informations, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b96a8-218">For more information, see the following topics:</span></span>

- [<span data-ttu-id="b96a8-219">Organisation du personnel à l'aide des départements, tâches et postes</span><span class="sxs-lookup"><span data-stu-id="b96a8-219">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="b96a8-220">Paramétrer les postes</span><span class="sxs-lookup"><span data-stu-id="b96a8-220">Set up positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="b96a8-221">Départements</span><span class="sxs-lookup"><span data-stu-id="b96a8-221">Departments</span></span>

<span data-ttu-id="b96a8-222">Un département est une unité opérationnelle qui représente une catégorie ou un domaine fonctionnel d'une organisation.</span><span class="sxs-lookup"><span data-stu-id="b96a8-222">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="b96a8-223">Un département est responsable d'un domaine spécifique de l'organisation, par exemple les ventes, la comptabilité ou les ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="b96a8-223">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="b96a8-224">Les départements vous permettent de générer des états sur les domaines fonctionnels.</span><span class="sxs-lookup"><span data-stu-id="b96a8-224">You can use departments to report on functional areas.</span></span> <span data-ttu-id="b96a8-225">Les départements peuvent avoir la responsabilité des résultats.</span><span class="sxs-lookup"><span data-stu-id="b96a8-225">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="b96a8-226">Pour plus d'informations, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b96a8-226">For more information, see the following topics:</span></span>

- [<span data-ttu-id="b96a8-227">Créer un département et l'associer à la hiérarchie des départements</span><span class="sxs-lookup"><span data-stu-id="b96a8-227">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="b96a8-228">Définir les nouveaux départements</span><span class="sxs-lookup"><span data-stu-id="b96a8-228">Define new departments</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="b96a8-229">Cycles de paie et périodes de rémunération</span><span class="sxs-lookup"><span data-stu-id="b96a8-229">Pay cycles and pay periods</span></span>

<span data-ttu-id="b96a8-230">Un cycle de paie détermine la fréquence d'exécution de la paie et les jours spécifiques où les collaborateurs sont payés.</span><span class="sxs-lookup"><span data-stu-id="b96a8-230">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="b96a8-231">Par exemple, un cycle de paie peut être mensuel, et les employés peuvent être payés le dernier jour du mois.</span><span class="sxs-lookup"><span data-stu-id="b96a8-231">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="b96a8-232">Sinon, un cycle de paie peut être hebdomadaire, et les employés peuvent être payés le mardi après la fin de la période de rémunération.</span><span class="sxs-lookup"><span data-stu-id="b96a8-232">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="b96a8-233">Les cycles de paie sont affectés aux postes afin de contrôler à quel moment les collaborateurs à ces postes sont payés.</span><span class="sxs-lookup"><span data-stu-id="b96a8-233">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="b96a8-234">Après avoir créé des cycles de paie, vous pouvez générer des périodes de rémunération pour chaque cycle.</span><span class="sxs-lookup"><span data-stu-id="b96a8-234">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="b96a8-235">Chaque période de rémunération comprend une date de paiement par défaut basée sur les informations que vous fournissez.</span><span class="sxs-lookup"><span data-stu-id="b96a8-235">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="b96a8-236">Toutefois, vous pouvez modifier la date de paiement par défaut d'une période de rémunération pour permettre des exceptions, par exemple lorsque la date de paiement a lieu un jour férié.</span><span class="sxs-lookup"><span data-stu-id="b96a8-236">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="b96a8-237">Les informations suivantes sont utilisée dans Dayforce :</span><span class="sxs-lookup"><span data-stu-id="b96a8-237">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="b96a8-238">Cycle de paie (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-238">Pay cycle (required)</span></span>
- <span data-ttu-id="b96a8-239">Fréquence du cycle de paie (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-239">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="b96a8-240">Date de début de la période (première période de rémunération obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-240">Period start date (first pay period required)</span></span>
- <span data-ttu-id="b96a8-241">Date de rémunération par défaut (première période de rémunération obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-241">Default payment date (first pay period required)</span></span>

<span data-ttu-id="b96a8-242">Ces informations sont intégrées à Dayforce en tant que des groupes de paie, et sont séparées par pays ou par région pour chaque cycle de paie.</span><span class="sxs-lookup"><span data-stu-id="b96a8-242">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="b96a8-243">Au moins une période de rémunération doit être générée avant l'intégration.</span><span class="sxs-lookup"><span data-stu-id="b96a8-243">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="b96a8-244">Dayforce génère des calendriers de groupe de paie et des dates de rémunération, selon la date de début de la première période de rémunération et la date de rémunération par défaut paramétrées dans Talent.</span><span class="sxs-lookup"><span data-stu-id="b96a8-244">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="b96a8-245">Codes de rémunérations</span><span class="sxs-lookup"><span data-stu-id="b96a8-245">Earning codes</span></span>

<span data-ttu-id="b96a8-246">Les codes de rémunérations identifient de manière unique chaque type de revenus que les collaborateurs reçoivent.</span><span class="sxs-lookup"><span data-stu-id="b96a8-246">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="b96a8-247">Les codes ont différents paramètres associés aux revenus, tels que des règles comptables, des lois fiscales, des conditions de génération d'états, et la capacité de montant brut.</span><span class="sxs-lookup"><span data-stu-id="b96a8-247">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="b96a8-248">Les informations suivantes sont utilisée dans Dayforce :</span><span class="sxs-lookup"><span data-stu-id="b96a8-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="b96a8-249">Code de rémunération (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-249">Earning Code (required)</span></span>
- <span data-ttu-id="b96a8-250">Description</span><span class="sxs-lookup"><span data-stu-id="b96a8-250">Description</span></span>
- <span data-ttu-id="b96a8-251">Unité de mesure</span><span class="sxs-lookup"><span data-stu-id="b96a8-251">Unit of measure</span></span>
- <span data-ttu-id="b96a8-252">Productif</span><span class="sxs-lookup"><span data-stu-id="b96a8-252">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="b96a8-253">Données sur les collaborateurs</span><span class="sxs-lookup"><span data-stu-id="b96a8-253">Worker data</span></span>

<span data-ttu-id="b96a8-254">Les enregistrements pour les différents types d'employés dont vous disposez sont importants pour vos systèmes de ressources humaines et de paie.</span><span class="sxs-lookup"><span data-stu-id="b96a8-254">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="b96a8-255">Les informations que vous entrez peuvent servir à suivre les informations des collaborateurs et les informations personnelles.</span><span class="sxs-lookup"><span data-stu-id="b96a8-255">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="b96a8-256">Vous pouvez tenir à jour les informations suivantes pour les travailleurs :</span><span class="sxs-lookup"><span data-stu-id="b96a8-256">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="b96a8-257">**Base** – Permet de tenir à jour les informations de base sur un collaborateur, telles que les informations de contact, les informations démographiques, les informations d'identification, les informations sur la famille, le statut de service militaire, les informations d'expatriation, et les contacts personnels et les personnes à prévenir en cas d'urgence.</span><span class="sxs-lookup"><span data-stu-id="b96a8-257">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="b96a8-258">**Emploi** – Permet de tenir à jour les informations relatives à l'emploi des collaborateurs, telles que l'affiliation de la société ou de l'organisation, l'affectation de poste, les dates de début et de fin, l'éligibilité à un emploi, les conditions d'emploi, la retraite, les congés, et les informations de mutation.</span><span class="sxs-lookup"><span data-stu-id="b96a8-258">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="b96a8-259">**Congé et absence** – Permet de tenir à jour les informations sur les absences des collaborateurs, telles que les calendriers de travail, les transactions d'absence et le paramétrage d'absence.</span><span class="sxs-lookup"><span data-stu-id="b96a8-259">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="b96a8-260">**Rémunération et paie** – Permet de tenir à jour les informations sur les régimes de rémunération des collaborateurs et les informations de paie, telles que l'inscription à un régime, les primes, les performances, la commission, les informations fiscales, la retraite et les déductions de salaire.</span><span class="sxs-lookup"><span data-stu-id="b96a8-260">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="b96a8-261">Lorsque vous entrez des informations sur le collaborateur, n'oubliez pas les données et les configurations suivantes utilisées dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b96a8-261">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="b96a8-262">Informations générales</span><span class="sxs-lookup"><span data-stu-id="b96a8-262">General information</span></span>

- <span data-ttu-id="b96a8-263">Matricule (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-263">Personnel number (required)</span></span>
- <span data-ttu-id="b96a8-264">Prénom (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-264">First name (required)</span></span>
- <span data-ttu-id="b96a8-265">Nom (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-265">Last name (required)</span></span>
- <span data-ttu-id="b96a8-266">Autres prénoms</span><span class="sxs-lookup"><span data-stu-id="b96a8-266">Middle name</span></span>
- <span data-ttu-id="b96a8-267">Date d'ancienneté</span><span class="sxs-lookup"><span data-stu-id="b96a8-267">Seniority date</span></span>
- <span data-ttu-id="b96a8-268">Connu sous</span><span class="sxs-lookup"><span data-stu-id="b96a8-268">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="b96a8-269">Informations personnelles</span><span class="sxs-lookup"><span data-stu-id="b96a8-269">Personal information</span></span>

- <span data-ttu-id="b96a8-270">État civil (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-270">Marital status (required)</span></span>
- <span data-ttu-id="b96a8-271">Date de naissance (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-271">Birth date (required)</span></span>
- <span data-ttu-id="b96a8-272">Sexe (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-272">Gender (required)</span></span>
- <span data-ttu-id="b96a8-273">Personne handicapée</span><span class="sxs-lookup"><span data-stu-id="b96a8-273">Person with disabilities</span></span>
- <span data-ttu-id="b96a8-274">Région/pays de nationalité (uniquement au Mexique)</span><span class="sxs-lookup"><span data-stu-id="b96a8-274">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="b96a8-275">Informations d'adresse</span><span class="sxs-lookup"><span data-stu-id="b96a8-275">Address information</span></span>

- <span data-ttu-id="b96a8-276">Adresse principale (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-276">Primary (required)</span></span>
- <span data-ttu-id="b96a8-277">Pays/région (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-277">Country/region (required)</span></span>
- <span data-ttu-id="b96a8-278">Code postal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-278">Postal code (required)</span></span>
- <span data-ttu-id="b96a8-279">Numéro de la rue (obligatoire) (uniquement au Mexique)</span><span class="sxs-lookup"><span data-stu-id="b96a8-279">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="b96a8-280">Info complémentaire sur le bâtiment (uniquement au Mexique)</span><span class="sxs-lookup"><span data-stu-id="b96a8-280">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="b96a8-281">Ville (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-281">City (required)</span></span>
- <span data-ttu-id="b96a8-282">État (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-282">State (required)</span></span>
- <span data-ttu-id="b96a8-283">Pays (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-283">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="b96a8-284">Informations de contact</span><span class="sxs-lookup"><span data-stu-id="b96a8-284">Contact information</span></span> 

- <span data-ttu-id="b96a8-285">Contact principal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-285">Primary (required)</span></span>
- <span data-ttu-id="b96a8-286">Numéro du contact (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-286">Contact number (required)</span></span>
- <span data-ttu-id="b96a8-287">Poste</span><span class="sxs-lookup"><span data-stu-id="b96a8-287">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="b96a8-288">Informations sur les salaires et codes de rémunération</span><span class="sxs-lookup"><span data-stu-id="b96a8-288">Payroll information and earning codes</span></span>

<span data-ttu-id="b96a8-289">Les employés peuvent bénéficier de revenus spécifiques à une fréquence de paiement donnée et avoir un mode de paiement préféré.</span><span class="sxs-lookup"><span data-stu-id="b96a8-289">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="b96a8-290">Les champs suivants sont utilisés dans Dayforce pour garantir que ces préférences et paramètres soient utilisés.</span><span class="sxs-lookup"><span data-stu-id="b96a8-290">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="b96a8-291">Codes de rémunérations</span><span class="sxs-lookup"><span data-stu-id="b96a8-291">Earning codes</span></span>

- <span data-ttu-id="b96a8-292">Poste (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-292">Position (required)</span></span>
- <span data-ttu-id="b96a8-293">Code de rémunération (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-293">Earning Code (required)</span></span>
- <span data-ttu-id="b96a8-294">Fréquence (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-294">Frequency (required)</span></span>
- <span data-ttu-id="b96a8-295">Montant (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-295">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="b96a8-296">Informations sur les salaires</span><span class="sxs-lookup"><span data-stu-id="b96a8-296">Payroll information</span></span>

- <span data-ttu-id="b96a8-297">Mode de paiement</span><span class="sxs-lookup"><span data-stu-id="b96a8-297">Payment Method</span></span>
- <span data-ttu-id="b96a8-298">Région économique (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-298">Economic Region (required)</span></span>
- <span data-ttu-id="b96a8-299">ID avantages employé</span><span class="sxs-lookup"><span data-stu-id="b96a8-299">Employee Benefits ID</span></span>
- <span data-ttu-id="b96a8-300">Numéro d'ID national (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-300">National ID Number (required)</span></span>
- <span data-ttu-id="b96a8-301">Numéro de service militaire</span><span class="sxs-lookup"><span data-stu-id="b96a8-301">Military Service Number</span></span>
- <span data-ttu-id="b96a8-302">ID d'équipe (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-302">Shift ID (required)</span></span>
- <span data-ttu-id="b96a8-303">Numéro de taxe (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-303">Tax Number (required)</span></span>
- <span data-ttu-id="b96a8-304">ID syndicat (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-304">Union ID (required)</span></span>
- <span data-ttu-id="b96a8-305">ID de la journée de travail (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-305">Work Day ID (required)</span></span>
- <span data-ttu-id="b96a8-306">Numéro de permis de travail</span><span class="sxs-lookup"><span data-stu-id="b96a8-306">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="b96a8-307">Pour le mode de paiement, le Mexique prend en charge les **Espèces**, les **Chèques** (chèque physique de la société) et le **Paiement électronique**.</span><span class="sxs-lookup"><span data-stu-id="b96a8-307">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="b96a8-308">Si aucun mode de paiement n'est spécifié, le **Chèque** est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="b96a8-308">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="b96a8-309">Détails de l'emploi</span><span class="sxs-lookup"><span data-stu-id="b96a8-309">Employment details</span></span>

<span data-ttu-id="b96a8-310">L'historique des détails de l'emploi est utilisé comme information clé pour en dériver le statut d'embauche, de fin du contrat, et de réembauche d'un employé dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b96a8-310">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="b96a8-311">Dayforce prend en charge un seul enregistrement d'emploi actif à la fois.</span><span class="sxs-lookup"><span data-stu-id="b96a8-311">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="b96a8-312">Date de début de l'emploi (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-312">Employment start date (required)</span></span>
- <span data-ttu-id="b96a8-313">Date de fin de l'emploi</span><span class="sxs-lookup"><span data-stu-id="b96a8-313">Employment end date</span></span>
- <span data-ttu-id="b96a8-314">Date de début</span><span class="sxs-lookup"><span data-stu-id="b96a8-314">Start date</span></span>
- <span data-ttu-id="b96a8-315">Date de début de contrat ajustée</span><span class="sxs-lookup"><span data-stu-id="b96a8-315">Adjusted start date</span></span>
- <span data-ttu-id="b96a8-316">Date de fin de contrat (obligatoire à la fin du contrat)</span><span class="sxs-lookup"><span data-stu-id="b96a8-316">Termination date (required upon termination)</span></span>
- <span data-ttu-id="b96a8-317">Motif de la fin du contrat (obligatoire à la fin du contrat)</span><span class="sxs-lookup"><span data-stu-id="b96a8-317">Termination reason (required upon termination)</span></span>

<span data-ttu-id="b96a8-318">Les dates clés d'un employé sont dérivées à l'aide des informations suivantes.</span><span class="sxs-lookup"><span data-stu-id="b96a8-318">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="b96a8-319">Talent</span><span class="sxs-lookup"><span data-stu-id="b96a8-319">Talent</span></span>                | <span data-ttu-id="b96a8-320">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b96a8-320">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b96a8-321">Date d'embauche la plus récente</span><span class="sxs-lookup"><span data-stu-id="b96a8-321">Most recent hire date</span></span> | <span data-ttu-id="b96a8-322">Début de l'emploi de l'enregistrement d'historique d'emploi avec contrat en cours</span><span class="sxs-lookup"><span data-stu-id="b96a8-322">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="b96a8-323">Date de fin de contrat</span><span class="sxs-lookup"><span data-stu-id="b96a8-323">Termination date</span></span>      | <span data-ttu-id="b96a8-324">Date de fin de contrat de l'enregistrement d'historique d'emploi avec contrat en cours</span><span class="sxs-lookup"><span data-stu-id="b96a8-324">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="b96a8-325">Date de début</span><span class="sxs-lookup"><span data-stu-id="b96a8-325">Start date</span></span>            | <span data-ttu-id="b96a8-326">Date de début ajustée, date de début, ou début de l'emploi de l'enregistrement d'historique d'emploi inactif actuel</span><span class="sxs-lookup"><span data-stu-id="b96a8-326">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="b96a8-327">Date d'embauche d'origine</span><span class="sxs-lookup"><span data-stu-id="b96a8-327">Original hire date</span></span>    | <span data-ttu-id="b96a8-328">Début d'emploi de l'enregistrement d'historique d'emploi le plus proche</span><span class="sxs-lookup"><span data-stu-id="b96a8-328">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="b96a8-329">Rémunération</span><span class="sxs-lookup"><span data-stu-id="b96a8-329">Compensation</span></span>

<span data-ttu-id="b96a8-330">Un plan de rémunération fixe doit être associé au poste principal de chaque employé tout au long d'une période d'emploi.</span><span class="sxs-lookup"><span data-stu-id="b96a8-330">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="b96a8-331">Cette période démarre à la date à laquelle l'employé a été embauché (ou à la date de début de l'emploi) et se poursuit jusqu'à la fin de contrat.</span><span class="sxs-lookup"><span data-stu-id="b96a8-331">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="b96a8-332">Date d'effet (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-332">Effective Date (required)</span></span>
- <span data-ttu-id="b96a8-333">Date d'expiration</span><span class="sxs-lookup"><span data-stu-id="b96a8-333">Expiration date</span></span>
- <span data-ttu-id="b96a8-334">Taux de salaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-334">Pay Rate (required)</span></span>
- <span data-ttu-id="b96a8-335">Conversions de taux de salaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-335">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="b96a8-336">Équivalent annuel (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-336">Annual equivalent (required)</span></span>
- <span data-ttu-id="b96a8-337">Équivalent horaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-337">Hourly equivalent (required)</span></span>

<span data-ttu-id="b96a8-338">Si un employé horaire a plusieurs postes, la rémunération fixe du poste principal est importée dans Dayforce comme taux de base/salaire de niveau d'employé.</span><span class="sxs-lookup"><span data-stu-id="b96a8-338">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="b96a8-339">Pour les postes non principaux, le taux horaire est enregistré au poste correspondant dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b96a8-339">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="b96a8-340">Si un employé salarié occupe plusieurs postes, le taux horaire cumulé et le salaire annuel entre tous les postes actifs sont dérivés et utilisés comme taux de base/salaire au niveau de l'employé.</span><span class="sxs-lookup"><span data-stu-id="b96a8-340">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="b96a8-341">Numéros d'identifications</span><span class="sxs-lookup"><span data-stu-id="b96a8-341">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="b96a8-342">Numéro de Sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="b96a8-342">Social Security identifier</span></span> 

<span data-ttu-id="b96a8-343">Chaque employé doit avoir un numéro principal.</span><span class="sxs-lookup"><span data-stu-id="b96a8-343">Every employee must have one primary identifier.</span></span> <span data-ttu-id="b96a8-344">Cet numéro doit être de type d'identification **N° S.S.**.</span><span class="sxs-lookup"><span data-stu-id="b96a8-344">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="b96a8-345">Dans Dayforce, il est automatiquement dérivé du numéro de Sécurité sociale de l'employé qui est obligatoire pour l'embaucher.</span><span class="sxs-lookup"><span data-stu-id="b96a8-345">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="b96a8-346">Numéro principal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-346">Primary (required)</span></span>
- <span data-ttu-id="b96a8-347">Type d'identification = « N° S.S. »</span><span class="sxs-lookup"><span data-stu-id="b96a8-347">Identification Type = "SSN"</span></span>
- <span data-ttu-id="b96a8-348">Date d'émission</span><span class="sxs-lookup"><span data-stu-id="b96a8-348">Issued Date</span></span>
- <span data-ttu-id="b96a8-349">Date d'expiration</span><span class="sxs-lookup"><span data-stu-id="b96a8-349">Expiration Date</span></span>

<span data-ttu-id="b96a8-350">Les employés peuvent déclarer plusieurs numéros d'identification de type d'identification **N° S.S.**.</span><span class="sxs-lookup"><span data-stu-id="b96a8-350">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="b96a8-351">Toutefois, seul l'enregistrement marqué comme **Principal** est intégré à Dayforce, que le numéro soit active ou arrivé à expiration.</span><span class="sxs-lookup"><span data-stu-id="b96a8-351">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="b96a8-352">Comptes en banque et décaissements</span><span class="sxs-lookup"><span data-stu-id="b96a8-352">Bank accounts and disbursements</span></span>

<span data-ttu-id="b96a8-353">Des informations de compte bancaire valides doivent être entrées pour tous les employés qui choisissent d'être payés à l'aide de virements bancaires.</span><span class="sxs-lookup"><span data-stu-id="b96a8-353">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="b96a8-354">Talent</span><span class="sxs-lookup"><span data-stu-id="b96a8-354">Talent</span></span>                         | <span data-ttu-id="b96a8-355">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b96a8-355">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b96a8-356">Numéro de compte bancaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-356">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="b96a8-357">Code SWIFT (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-357">SWIFT code (required)</span></span>          | <span data-ttu-id="b96a8-358">Le champ**ID banque** utilisé lors du traitement du salaire au Mexique.</span><span class="sxs-lookup"><span data-stu-id="b96a8-358">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="b96a8-359">Numéro d'agence (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-359">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="b96a8-360">Type de compte bancaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-360">Bank account type (required)</span></span>   | <span data-ttu-id="b96a8-361">Le champ**Type de compte** utilisé lors du traitement du salaire au Mexique.</span><span class="sxs-lookup"><span data-stu-id="b96a8-361">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="b96a8-362">Les valeurs prises en charge sont **Chèque** et **Paie**.</span><span class="sxs-lookup"><span data-stu-id="b96a8-362">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="b96a8-363">Les employés qui choisissent d'être payés par des virements bancaires doivent fournir un lien vers un compte de solde qui se trouve sous une entité juridique avec son adresse principale au Mexique, et associée à un compte bancaire valide dans une banque mexicaine.</span><span class="sxs-lookup"><span data-stu-id="b96a8-363">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="b96a8-364">Tous les autres comptes non-solde sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="b96a8-364">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="b96a8-365">Informations d'adresse</span><span class="sxs-lookup"><span data-stu-id="b96a8-365">Address information</span></span>

<span data-ttu-id="b96a8-366">Chaque employé doit avoir un lieu principal.</span><span class="sxs-lookup"><span data-stu-id="b96a8-366">Every employee must have one primary location.</span></span> <span data-ttu-id="b96a8-367">Dans Dayforce, ce lieu est utilisé pour déterminer la résidence principale de l'employé à des fins fiscales.</span><span class="sxs-lookup"><span data-stu-id="b96a8-367">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="b96a8-368">Lieu principal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-368">Primary (required)</span></span>
- <span data-ttu-id="b96a8-369">Pays/région (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-369">Country/region (required)</span></span>
- <span data-ttu-id="b96a8-370">Code postal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-370">Zip/postal code (required)</span></span>
- <span data-ttu-id="b96a8-371">Rue (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-371">Street (required)</span></span>
- <span data-ttu-id="b96a8-372">Numéro de rue (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-372">Street Number (required)</span></span>
- <span data-ttu-id="b96a8-373">Info complémentaire sur le bâtiment</span><span class="sxs-lookup"><span data-stu-id="b96a8-373">Building Complement</span></span>
- <span data-ttu-id="b96a8-374">Ville (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-374">City (required)</span></span>
- <span data-ttu-id="b96a8-375">État (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-375">State (required)</span></span>
- <span data-ttu-id="b96a8-376">Pays (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-376">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="b96a8-377">Configurer vos données pour générer un salaire aux États-Unis et au Canada</span><span class="sxs-lookup"><span data-stu-id="b96a8-377">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="b96a8-378">Si vous générez un salaire pour des employés aux États-Unis et au Canada, les éléments suivants doivent être configurés :</span><span class="sxs-lookup"><span data-stu-id="b96a8-378">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="b96a8-379">Les départements sont obligatoires sur les postes.</span><span class="sxs-lookup"><span data-stu-id="b96a8-379">Departments are required on positions.</span></span>
- <span data-ttu-id="b96a8-380">Les centres de coût doivent être définis comme des dimensions financières et doivent être le premier élément de la chaîne de dimension financière par défaut.</span><span class="sxs-lookup"><span data-stu-id="b96a8-380">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="b96a8-381">Vous pouvez configurer Talent pour demander que les postes spécifient un service.</span><span class="sxs-lookup"><span data-stu-id="b96a8-381">You can configure Talent to require that Positions specify a Department.</span></span> <span data-ttu-id="b96a8-382">Pour ce faire, accédez à **Postes partagés par les ressources humaines > Postes > Demander le service des postes**.</span><span class="sxs-lookup"><span data-stu-id="b96a8-382">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="b96a8-383">Nous vous recommandons d'appliquer ce paramètre pour l'intégration.</span><span class="sxs-lookup"><span data-stu-id="b96a8-383">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="b96a8-384">Types de missions</span><span class="sxs-lookup"><span data-stu-id="b96a8-384">Job types</span></span>

<span data-ttu-id="b96a8-385">Les types de tâches sont utilisés pour regrouper les tâches similaires en catégories.</span><span class="sxs-lookup"><span data-stu-id="b96a8-385">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="b96a8-386">Les types de tâches sont nécessaires pour traiter la paie aux États-Unis et au Canada.</span><span class="sxs-lookup"><span data-stu-id="b96a8-386">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="b96a8-387">Les exemples de types de tâches incluent le temps plein et le temps partiel, ou le salaire et le paiement à l'heure.</span><span class="sxs-lookup"><span data-stu-id="b96a8-387">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="b96a8-388">Les types de tâches sont mis en correspondance dans Dayforce comme types de paies qui indiquent si un employé est payé à l'heure ou salarié.</span><span class="sxs-lookup"><span data-stu-id="b96a8-388">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="b96a8-389">Les types de tâches et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="b96a8-389">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="b96a8-390">Type de mission</span><span class="sxs-lookup"><span data-stu-id="b96a8-390">Job type</span></span>   | <span data-ttu-id="b96a8-391">Description</span><span class="sxs-lookup"><span data-stu-id="b96a8-391">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="b96a8-392">Horaire</span><span class="sxs-lookup"><span data-stu-id="b96a8-392">Hourly</span></span>     | <span data-ttu-id="b96a8-393">Horaire</span><span class="sxs-lookup"><span data-stu-id="b96a8-393">Hourly</span></span>      |
| <span data-ttu-id="b96a8-394">Salarié</span><span class="sxs-lookup"><span data-stu-id="b96a8-394">Salaried</span></span>   | <span data-ttu-id="b96a8-395">Salarié</span><span class="sxs-lookup"><span data-stu-id="b96a8-395">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="b96a8-396">Types de poste</span><span class="sxs-lookup"><span data-stu-id="b96a8-396">Position types</span></span> 

<span data-ttu-id="b96a8-397">Vous utilisez les types de postes pour indiquer si le poste est à temps plein, à temps partiel, ou autre chose.</span><span class="sxs-lookup"><span data-stu-id="b96a8-397">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="b96a8-398">Les types de postes sont mis en correspondance dans Dayforce comme classes de paiements qui indiquent si un employé est à temps plein ou à temps partiel.</span><span class="sxs-lookup"><span data-stu-id="b96a8-398">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="b96a8-399">Les types de postes et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="b96a8-399">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="b96a8-400">Type de poste</span><span class="sxs-lookup"><span data-stu-id="b96a8-400">Position type</span></span>   | <span data-ttu-id="b96a8-401">Description</span><span class="sxs-lookup"><span data-stu-id="b96a8-401">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="b96a8-402">Temps plein</span><span class="sxs-lookup"><span data-stu-id="b96a8-402">Full-time</span></span>       | <span data-ttu-id="b96a8-403">Employé à temps plein</span><span class="sxs-lookup"><span data-stu-id="b96a8-403">Full time employee</span></span> |
| <span data-ttu-id="b96a8-404">Temps partiel</span><span class="sxs-lookup"><span data-stu-id="b96a8-404">Part-time</span></span>       | <span data-ttu-id="b96a8-405">Employé à temps partiel</span><span class="sxs-lookup"><span data-stu-id="b96a8-405">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="b96a8-406">Codes motif</span><span class="sxs-lookup"><span data-stu-id="b96a8-406">Reason codes</span></span>

<span data-ttu-id="b96a8-407">Les codes motif fournissent des informations sur le statut d'un employé.</span><span class="sxs-lookup"><span data-stu-id="b96a8-407">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="b96a8-408">Les codes motif sont mis en correspondance avec Dayforce comme motifs du statut, indiquant le motif des modifications apportées au poste ou au statut d'emploi d'un employé.</span><span class="sxs-lookup"><span data-stu-id="b96a8-408">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="b96a8-409">Les codes motif et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="b96a8-409">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="b96a8-410">Code motif</span><span class="sxs-lookup"><span data-stu-id="b96a8-410">Reason code</span></span>    | <span data-ttu-id="b96a8-411">Description</span><span class="sxs-lookup"><span data-stu-id="b96a8-411">Description</span></span>      | <span data-ttu-id="b96a8-412">Scénarios applicables</span><span class="sxs-lookup"><span data-stu-id="b96a8-412">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="b96a8-413">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="b96a8-413">RESIGNATION</span></span>    | <span data-ttu-id="b96a8-414">Démission</span><span class="sxs-lookup"><span data-stu-id="b96a8-414">Resignation</span></span>      | <span data-ttu-id="b96a8-415">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b96a8-415">Terminate worker</span></span>     |
| <span data-ttu-id="b96a8-416">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="b96a8-416">TERMINATION</span></span>    | <span data-ttu-id="b96a8-417">Fin du contrat</span><span class="sxs-lookup"><span data-stu-id="b96a8-417">Termination</span></span>      | <span data-ttu-id="b96a8-418">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b96a8-418">Terminate worker</span></span>     |
| <span data-ttu-id="b96a8-419">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="b96a8-419">RETIREMENT</span></span>     | <span data-ttu-id="b96a8-420">Retraite</span><span class="sxs-lookup"><span data-stu-id="b96a8-420">Retirement</span></span>       | <span data-ttu-id="b96a8-421">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b96a8-421">Terminate worker</span></span>     |
| <span data-ttu-id="b96a8-422">OTHER</span><span class="sxs-lookup"><span data-stu-id="b96a8-422">OTHER</span></span>          | <span data-ttu-id="b96a8-423">Autres motifs</span><span class="sxs-lookup"><span data-stu-id="b96a8-423">Other Reasons</span></span>    | <span data-ttu-id="b96a8-424">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b96a8-424">Terminate worker</span></span>     |
| <span data-ttu-id="b96a8-425">DEATH</span><span class="sxs-lookup"><span data-stu-id="b96a8-425">DEATH</span></span>          | <span data-ttu-id="b96a8-426">Décès</span><span class="sxs-lookup"><span data-stu-id="b96a8-426">Death</span></span>            | <span data-ttu-id="b96a8-427">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b96a8-427">Terminate worker</span></span>     |
| <span data-ttu-id="b96a8-428">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="b96a8-428">LEAVEOFABSENCE</span></span> | <span data-ttu-id="b96a8-429">Congé</span><span class="sxs-lookup"><span data-stu-id="b96a8-429">Leave of Absence</span></span> | <span data-ttu-id="b96a8-430">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b96a8-430">Terminate worker</span></span>     |
| <span data-ttu-id="b96a8-431">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="b96a8-431">CONTRACTEND</span></span>    | <span data-ttu-id="b96a8-432">Fin du contrat</span><span class="sxs-lookup"><span data-stu-id="b96a8-432">End of Contract</span></span>  | <span data-ttu-id="b96a8-433">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b96a8-433">Terminate worker</span></span>     |
| <span data-ttu-id="b96a8-434">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="b96a8-434">SALARYCHANGE</span></span>   | <span data-ttu-id="b96a8-435">Modification du salaire</span><span class="sxs-lookup"><span data-stu-id="b96a8-435">Change of Salary</span></span> | <span data-ttu-id="b96a8-436">Rémunération</span><span class="sxs-lookup"><span data-stu-id="b96a8-436">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="b96a8-437">Situation de famille</span><span class="sxs-lookup"><span data-stu-id="b96a8-437">Marital status</span></span>

<span data-ttu-id="b96a8-438">Les valeurs de situation de famille sont mises en correspondance avec Dayforce et traduite, au besoin, dans les valeurs acceptées lors de l'intégration.</span><span class="sxs-lookup"><span data-stu-id="b96a8-438">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="b96a8-439">Le tableau suivant montre comment les valeurs de situation de famille sont mises en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b96a8-439">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="b96a8-440">Talent</span><span class="sxs-lookup"><span data-stu-id="b96a8-440">Talent</span></span>                 | <span data-ttu-id="b96a8-441">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b96a8-441">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="b96a8-442">Marié</span><span class="sxs-lookup"><span data-stu-id="b96a8-442">Married</span></span>                | <span data-ttu-id="b96a8-443">Marié</span><span class="sxs-lookup"><span data-stu-id="b96a8-443">Married</span></span>              |
| <span data-ttu-id="b96a8-444">Unique</span><span class="sxs-lookup"><span data-stu-id="b96a8-444">Single</span></span>                 | <span data-ttu-id="b96a8-445">Unique</span><span class="sxs-lookup"><span data-stu-id="b96a8-445">Single</span></span>               |
| <span data-ttu-id="b96a8-446">Veuf</span><span class="sxs-lookup"><span data-stu-id="b96a8-446">Widowed</span></span>                | <span data-ttu-id="b96a8-447">Veuf</span><span class="sxs-lookup"><span data-stu-id="b96a8-447">Widowed</span></span>              |
| <span data-ttu-id="b96a8-448">Divorcé</span><span class="sxs-lookup"><span data-stu-id="b96a8-448">Divorced</span></span>               | <span data-ttu-id="b96a8-449">Divorcé</span><span class="sxs-lookup"><span data-stu-id="b96a8-449">Divorced</span></span>             |
| <span data-ttu-id="b96a8-450">Partenariat enregistré</span><span class="sxs-lookup"><span data-stu-id="b96a8-450">Registered Partnership</span></span> | <span data-ttu-id="b96a8-451">Partenariat local</span><span class="sxs-lookup"><span data-stu-id="b96a8-451">Domestic Partnership</span></span> |
| <span data-ttu-id="b96a8-452">None</span><span class="sxs-lookup"><span data-stu-id="b96a8-452">None</span></span>                   | <span data-ttu-id="b96a8-453">None</span><span class="sxs-lookup"><span data-stu-id="b96a8-453">None</span></span>                 |
| <span data-ttu-id="b96a8-454">Concubinage</span><span class="sxs-lookup"><span data-stu-id="b96a8-454">Cohabiting</span></span>             | <span data-ttu-id="b96a8-455">Concubinage</span><span class="sxs-lookup"><span data-stu-id="b96a8-455">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="b96a8-456">Sexe</span><span class="sxs-lookup"><span data-stu-id="b96a8-456">Gender</span></span>

<span data-ttu-id="b96a8-457">Le sexe est mis en correspondance avec Dayforce et traduit, au besoin, dans les valeurs acceptées lors de l'intégration.</span><span class="sxs-lookup"><span data-stu-id="b96a8-457">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="b96a8-458">Le tableau suivant montre comment le sexe est mis en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b96a8-458">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="b96a8-459">Talent</span><span class="sxs-lookup"><span data-stu-id="b96a8-459">Talent</span></span>       | <span data-ttu-id="b96a8-460">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b96a8-460">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="b96a8-461">Masculin</span><span class="sxs-lookup"><span data-stu-id="b96a8-461">Male</span></span>         | <span data-ttu-id="b96a8-462">Masculin</span><span class="sxs-lookup"><span data-stu-id="b96a8-462">Male</span></span>            |
| <span data-ttu-id="b96a8-463">Féminin</span><span class="sxs-lookup"><span data-stu-id="b96a8-463">Female</span></span>       | <span data-ttu-id="b96a8-464">Féminin</span><span class="sxs-lookup"><span data-stu-id="b96a8-464">Female</span></span>          |
| <span data-ttu-id="b96a8-465">Non spécifique</span><span class="sxs-lookup"><span data-stu-id="b96a8-465">Non-specific</span></span> | <span data-ttu-id="b96a8-466">*Non pris en charge*</span><span class="sxs-lookup"><span data-stu-id="b96a8-466">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="b96a8-467">Codes de rémunérations</span><span class="sxs-lookup"><span data-stu-id="b96a8-467">Earning codes</span></span>

<span data-ttu-id="b96a8-468">Les codes de rémunérations identifient de manière unique chaque type de revenus que les collaborateurs reçoivent.</span><span class="sxs-lookup"><span data-stu-id="b96a8-468">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="b96a8-469">Les codes couvrent différents paramètres associés aux revenus, tels que des règles comptables, des lois fiscales, des conditions de génération d'états, et la capacité de montant brut.</span><span class="sxs-lookup"><span data-stu-id="b96a8-469">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="b96a8-470">Si une fréquence non prise en charge est utilisée, la fréquence **Chaque paie** est utilisée par défaut pour le calcul.</span><span class="sxs-lookup"><span data-stu-id="b96a8-470">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="b96a8-471">Fréquences prises en charge</span><span class="sxs-lookup"><span data-stu-id="b96a8-471">Supported frequencies</span></span>

- <span data-ttu-id="b96a8-472">Tous</span><span class="sxs-lookup"><span data-stu-id="b96a8-472">All</span></span>
- <span data-ttu-id="b96a8-473">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="b96a8-473">EVERYPAY</span></span>
- <span data-ttu-id="b96a8-474">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="b96a8-474">EACHPAYPERIOD</span></span>
- <span data-ttu-id="b96a8-475">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="b96a8-475">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="b96a8-476">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="b96a8-476">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="b96a8-477">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-477">1OFMTH</span></span>
- <span data-ttu-id="b96a8-478">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-478">LASTOFMTH</span></span>
- <span data-ttu-id="b96a8-479">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-479">2OFMTH</span></span>
- <span data-ttu-id="b96a8-480">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-480">3OFMTH</span></span>
- <span data-ttu-id="b96a8-481">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-481">4OFMTH</span></span>
- <span data-ttu-id="b96a8-482">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-482">5OFMTH</span></span>
- <span data-ttu-id="b96a8-483">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-483">1N2OFMTH</span></span>
- <span data-ttu-id="b96a8-484">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-484">3N4OFMTH</span></span>
- <span data-ttu-id="b96a8-485">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-485">1N3OFMTH</span></span>
- <span data-ttu-id="b96a8-486">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-486">1N4OFMTH</span></span>
- <span data-ttu-id="b96a8-487">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-487">2N3OFMTH</span></span>
- <span data-ttu-id="b96a8-488">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-488">2N4OFMTH</span></span>
- <span data-ttu-id="b96a8-489">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-489">1N2N3OFMTH</span></span>
- <span data-ttu-id="b96a8-490">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-490">1N2N4OFMTH</span></span>
- <span data-ttu-id="b96a8-491">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-491">1N3N4OFMTH</span></span>
- <span data-ttu-id="b96a8-492">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-492">2N3N4OFMTH</span></span>
- <span data-ttu-id="b96a8-493">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-493">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="b96a8-494">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="b96a8-494">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="b96a8-495">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="b96a8-495">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="b96a8-496">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="b96a8-496">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="b96a8-497">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="b96a8-497">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="b96a8-498">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="b96a8-498">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="b96a8-499">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="b96a8-499">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="b96a8-500">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="b96a8-500">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="b96a8-501">Adresses</span><span class="sxs-lookup"><span data-stu-id="b96a8-501">Addresses</span></span>

<span data-ttu-id="b96a8-502">L'identification d'un pays ou d'une région, d'un état, et des codes département (municipalité) spécifiques nécessite des formats spécifiques que les fournisseurs Dayforce et dans le pays/la région peuvent identifier.</span><span class="sxs-lookup"><span data-stu-id="b96a8-502">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="b96a8-503">Bien que le format pour les villes soit flexible, chaque ville doit être associée à un état.</span><span class="sxs-lookup"><span data-stu-id="b96a8-503">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="b96a8-504">Talent</span><span class="sxs-lookup"><span data-stu-id="b96a8-504">Talent</span></span>          | <span data-ttu-id="b96a8-505">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b96a8-505">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="b96a8-506">Pays/région</span><span class="sxs-lookup"><span data-stu-id="b96a8-506">Country/Region</span></span>  | <span data-ttu-id="b96a8-507">Code pays</span><span class="sxs-lookup"><span data-stu-id="b96a8-507">Country Code</span></span>          |
| <span data-ttu-id="b96a8-508">Code postal</span><span class="sxs-lookup"><span data-stu-id="b96a8-508">Zip/Postal Code</span></span> | <span data-ttu-id="b96a8-509">Code postal</span><span class="sxs-lookup"><span data-stu-id="b96a8-509">Postal Code</span></span>           |
| <span data-ttu-id="b96a8-510">État</span><span class="sxs-lookup"><span data-stu-id="b96a8-510">State</span></span>           | <span data-ttu-id="b96a8-511">Code région</span><span class="sxs-lookup"><span data-stu-id="b96a8-511">State Code</span></span>            |
| <span data-ttu-id="b96a8-512">Ville</span><span class="sxs-lookup"><span data-stu-id="b96a8-512">City</span></span>            | <span data-ttu-id="b96a8-513">Ville</span><span class="sxs-lookup"><span data-stu-id="b96a8-513">City</span></span>                  |
| <span data-ttu-id="b96a8-514">Commune</span><span class="sxs-lookup"><span data-stu-id="b96a8-514">County</span></span>          | <span data-ttu-id="b96a8-515">Département (municipalité)</span><span class="sxs-lookup"><span data-stu-id="b96a8-515">County (Municipality)</span></span> |
| <span data-ttu-id="b96a8-516">Rue</span><span class="sxs-lookup"><span data-stu-id="b96a8-516">Street</span></span>          | <span data-ttu-id="b96a8-517">Ligne d'adresse 1</span><span class="sxs-lookup"><span data-stu-id="b96a8-517">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="b96a8-518">Zones fiscales</span><span class="sxs-lookup"><span data-stu-id="b96a8-518">Tax regions</span></span>

<span data-ttu-id="b96a8-519">Les régions fiscales permettent de déterminer la taxe appropriée qui doit être appliquée lors de la génération des salaires.</span><span class="sxs-lookup"><span data-stu-id="b96a8-519">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="b96a8-520">Les régions fiscales sont mises en correspondance avec Dayforce comme adresses de lieu.</span><span class="sxs-lookup"><span data-stu-id="b96a8-520">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="b96a8-521">La région fiscale par défaut doit être associée au poste actif du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="b96a8-521">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="b96a8-522">Région fiscale (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-522">Tax region (required)</span></span>
- <span data-ttu-id="b96a8-523">Pays/région (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-523">Country/Region (required)</span></span>
- <span data-ttu-id="b96a8-524">État (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-524">State (required)</span></span>
- <span data-ttu-id="b96a8-525">Commune</span><span class="sxs-lookup"><span data-stu-id="b96a8-525">County</span></span> 
- <span data-ttu-id="b96a8-526">Ville (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="b96a8-526">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="b96a8-527">Configurez vos données pour générer un salaire au Mexique</span><span class="sxs-lookup"><span data-stu-id="b96a8-527">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="b96a8-528">Si vous générez un salaire pour des employés au Mexique, les éléments suivants doivent être configurés :</span><span class="sxs-lookup"><span data-stu-id="b96a8-528">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="b96a8-529">Les départements sont obligatoires sur les postes.</span><span class="sxs-lookup"><span data-stu-id="b96a8-529">Departments are required on positions.</span></span>
- <span data-ttu-id="b96a8-530">Les centres de coût doivent être définis comme des dimensions financières et doivent être le premier élément de la chaîne de dimension financière par défaut.</span><span class="sxs-lookup"><span data-stu-id="b96a8-530">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="b96a8-531">Types de missions</span><span class="sxs-lookup"><span data-stu-id="b96a8-531">Job types</span></span>

<span data-ttu-id="b96a8-532">Les types de tâches sont utilisés pour regrouper les tâches similaires en catégories.</span><span class="sxs-lookup"><span data-stu-id="b96a8-532">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="b96a8-533">Les types de tâches sont nécessaires afin de traiter le salaire au Mexique.</span><span class="sxs-lookup"><span data-stu-id="b96a8-533">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="b96a8-534">Les exemples de types de tâches incluent le temps plein et le temps partiel, ou le salaire et le paiement à l'heure.</span><span class="sxs-lookup"><span data-stu-id="b96a8-534">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="b96a8-535">Les types de tâches sont mis en correspondance dans Dayforce comme types de paies qui indiquent si un employé est payé à l'heure ou salarié.</span><span class="sxs-lookup"><span data-stu-id="b96a8-535">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="b96a8-536">Les types de tâches et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="b96a8-536">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="b96a8-537">Type de mission</span><span class="sxs-lookup"><span data-stu-id="b96a8-537">Job type</span></span>   | <span data-ttu-id="b96a8-538">Description</span><span class="sxs-lookup"><span data-stu-id="b96a8-538">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="b96a8-539">Horaire</span><span class="sxs-lookup"><span data-stu-id="b96a8-539">Hourly</span></span>     | <span data-ttu-id="b96a8-540">Horaire MX</span><span class="sxs-lookup"><span data-stu-id="b96a8-540">MX Hourly</span></span>   |
| <span data-ttu-id="b96a8-541">Salarié</span><span class="sxs-lookup"><span data-stu-id="b96a8-541">Salaried</span></span>   | <span data-ttu-id="b96a8-542">Salarié MX</span><span class="sxs-lookup"><span data-stu-id="b96a8-542">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="b96a8-543">Types de poste</span><span class="sxs-lookup"><span data-stu-id="b96a8-543">Position types</span></span> 

<span data-ttu-id="b96a8-544">Vous utilisez les types de postes pour indiquer si le poste est à temps plein, à temps partiel, ou autre chose.</span><span class="sxs-lookup"><span data-stu-id="b96a8-544">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="b96a8-545">Les types de postes sont mis en correspondance dans Dayforce comme classes de paiements qui indiquent si un employé est à temps plein ou à temps partiel.</span><span class="sxs-lookup"><span data-stu-id="b96a8-545">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="b96a8-546">Les types de postes et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="b96a8-546">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="b96a8-547">Type de poste</span><span class="sxs-lookup"><span data-stu-id="b96a8-547">Position type</span></span>   | <span data-ttu-id="b96a8-548">Description</span><span class="sxs-lookup"><span data-stu-id="b96a8-548">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="b96a8-549">Temps plein</span><span class="sxs-lookup"><span data-stu-id="b96a8-549">Full-time</span></span>       | <span data-ttu-id="b96a8-550">Employé à temps plein</span><span class="sxs-lookup"><span data-stu-id="b96a8-550">Full time employee</span></span> |
| <span data-ttu-id="b96a8-551">Temps partiel</span><span class="sxs-lookup"><span data-stu-id="b96a8-551">Part-time</span></span>       | <span data-ttu-id="b96a8-552">Employé à temps partiel</span><span class="sxs-lookup"><span data-stu-id="b96a8-552">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="b96a8-553">Codes motif</span><span class="sxs-lookup"><span data-stu-id="b96a8-553">Reason codes</span></span>

<span data-ttu-id="b96a8-554">Les codes motif fournissent des informations sur le statut d'un employé.</span><span class="sxs-lookup"><span data-stu-id="b96a8-554">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="b96a8-555">Les codes motif sont mis en correspondance avec Dayforce comme motifs du statut, indiquant le motif des modifications apportées au poste ou au statut d'emploi d'un employé.</span><span class="sxs-lookup"><span data-stu-id="b96a8-555">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="b96a8-556">Les codes motif et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="b96a8-556">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="b96a8-557">Code motif</span><span class="sxs-lookup"><span data-stu-id="b96a8-557">Reason code</span></span>            | <span data-ttu-id="b96a8-558">Description</span><span class="sxs-lookup"><span data-stu-id="b96a8-558">Description</span></span>                    | <span data-ttu-id="b96a8-559">Scénarios applicables</span><span class="sxs-lookup"><span data-stu-id="b96a8-559">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="b96a8-560">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="b96a8-560">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="b96a8-561">Départ avant le premier salaire</span><span class="sxs-lookup"><span data-stu-id="b96a8-561">Departure before first payroll</span></span> | <span data-ttu-id="b96a8-562">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b96a8-562">Terminate worker</span></span>     |
| <span data-ttu-id="b96a8-563">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="b96a8-563">RESIGNATION</span></span>            | <span data-ttu-id="b96a8-564">Démission</span><span class="sxs-lookup"><span data-stu-id="b96a8-564">Resignation</span></span>                    | <span data-ttu-id="b96a8-565">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b96a8-565">Terminate worker</span></span>     |
| <span data-ttu-id="b96a8-566">PENSION</span><span class="sxs-lookup"><span data-stu-id="b96a8-566">PENSION</span></span>                | <span data-ttu-id="b96a8-567">Retraite</span><span class="sxs-lookup"><span data-stu-id="b96a8-567">Pension</span></span>                        | <span data-ttu-id="b96a8-568">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b96a8-568">Terminate worker</span></span>     |
| <span data-ttu-id="b96a8-569">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="b96a8-569">TERMINATION</span></span>            | <span data-ttu-id="b96a8-570">Fin du contrat</span><span class="sxs-lookup"><span data-stu-id="b96a8-570">Termination</span></span>                    | <span data-ttu-id="b96a8-571">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b96a8-571">Terminate worker</span></span>     |
| <span data-ttu-id="b96a8-572">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="b96a8-572">RETIREMENT</span></span>             | <span data-ttu-id="b96a8-573">Retraite</span><span class="sxs-lookup"><span data-stu-id="b96a8-573">Retirement</span></span>                     | <span data-ttu-id="b96a8-574">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b96a8-574">Terminate worker</span></span>     |
| <span data-ttu-id="b96a8-575">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="b96a8-575">ABSENTEE</span></span>               | <span data-ttu-id="b96a8-576">Absent</span><span class="sxs-lookup"><span data-stu-id="b96a8-576">Absentee</span></span>                       | <span data-ttu-id="b96a8-577">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b96a8-577">Terminate worker</span></span>     |
| <span data-ttu-id="b96a8-578">OTHER</span><span class="sxs-lookup"><span data-stu-id="b96a8-578">OTHER</span></span>                  | <span data-ttu-id="b96a8-579">Autres motifs</span><span class="sxs-lookup"><span data-stu-id="b96a8-579">Other Reasons</span></span>                  | <span data-ttu-id="b96a8-580">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b96a8-580">Terminate worker</span></span>     |
| <span data-ttu-id="b96a8-581">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="b96a8-581">CLOSURE</span></span>                | <span data-ttu-id="b96a8-582">Fermeture de l'entreprise</span><span class="sxs-lookup"><span data-stu-id="b96a8-582">Business Closure</span></span>               | <span data-ttu-id="b96a8-583">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b96a8-583">Terminate worker</span></span>     |
| <span data-ttu-id="b96a8-584">DEATH</span><span class="sxs-lookup"><span data-stu-id="b96a8-584">DEATH</span></span>                  | <span data-ttu-id="b96a8-585">Décès</span><span class="sxs-lookup"><span data-stu-id="b96a8-585">Death</span></span>                          | <span data-ttu-id="b96a8-586">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b96a8-586">Terminate worker</span></span>     |
| <span data-ttu-id="b96a8-587">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="b96a8-587">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="b96a8-588">Congé</span><span class="sxs-lookup"><span data-stu-id="b96a8-588">Leave of Absence</span></span>               | <span data-ttu-id="b96a8-589">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b96a8-589">Terminate worker</span></span>     |
| <span data-ttu-id="b96a8-590">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="b96a8-590">CONTRACTEND</span></span>            | <span data-ttu-id="b96a8-591">Fin du contrat</span><span class="sxs-lookup"><span data-stu-id="b96a8-591">End of Contract</span></span>                | <span data-ttu-id="b96a8-592">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b96a8-592">Terminate worker</span></span>     |
| <span data-ttu-id="b96a8-593">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="b96a8-593">SALARYCHANGE</span></span>           | <span data-ttu-id="b96a8-594">Modification du salaire</span><span class="sxs-lookup"><span data-stu-id="b96a8-594">Change of Salary</span></span>               | <span data-ttu-id="b96a8-595">Rémunération</span><span class="sxs-lookup"><span data-stu-id="b96a8-595">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="b96a8-596">Conditions d'emploi</span><span class="sxs-lookup"><span data-stu-id="b96a8-596">Terms of employment</span></span>

<span data-ttu-id="b96a8-597">Les conditions d'emploi sont utilisées pour créer des catégories de conditions d'emploi.</span><span class="sxs-lookup"><span data-stu-id="b96a8-597">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="b96a8-598">Les conditions sont mises en correspondance avec Dayforce en tant que valeurs d'indicateur d'emploi.</span><span class="sxs-lookup"><span data-stu-id="b96a8-598">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="b96a8-599">Les conditions d'emploi et descriptions suivantes sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="b96a8-599">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="b96a8-600">Conditions d'emploi</span><span class="sxs-lookup"><span data-stu-id="b96a8-600">Terms of employment</span></span>   | <span data-ttu-id="b96a8-601">Description</span><span class="sxs-lookup"><span data-stu-id="b96a8-601">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="b96a8-602">Régulier</span><span class="sxs-lookup"><span data-stu-id="b96a8-602">Regular</span></span>               | <span data-ttu-id="b96a8-603">Régulier</span><span class="sxs-lookup"><span data-stu-id="b96a8-603">Regular</span></span>     |
| <span data-ttu-id="b96a8-604">Direct</span><span class="sxs-lookup"><span data-stu-id="b96a8-604">Direct</span></span>                | <span data-ttu-id="b96a8-605">Direct</span><span class="sxs-lookup"><span data-stu-id="b96a8-605">Direct</span></span>      |
| <span data-ttu-id="b96a8-606">Stage</span><span class="sxs-lookup"><span data-stu-id="b96a8-606">Internship</span></span>            | <span data-ttu-id="b96a8-607">Stage</span><span class="sxs-lookup"><span data-stu-id="b96a8-607">Internship</span></span>  |
| <span data-ttu-id="b96a8-608">Permanent</span><span class="sxs-lookup"><span data-stu-id="b96a8-608">Permanent</span></span>             | <span data-ttu-id="b96a8-609">Permanent</span><span class="sxs-lookup"><span data-stu-id="b96a8-609">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="b96a8-610">Situation de famille</span><span class="sxs-lookup"><span data-stu-id="b96a8-610">Marital status</span></span>

<span data-ttu-id="b96a8-611">Les valeurs de situation de famille sont mises en correspondance avec Dayforce et traduite, au besoin, dans les valeurs acceptées lors de l'intégration.</span><span class="sxs-lookup"><span data-stu-id="b96a8-611">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="b96a8-612">Le tableau suivant montre comment les valeurs de situation de famille sont mises en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b96a8-612">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="b96a8-613">Talent</span><span class="sxs-lookup"><span data-stu-id="b96a8-613">Talent</span></span>                 | <span data-ttu-id="b96a8-614">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b96a8-614">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="b96a8-615">Marié</span><span class="sxs-lookup"><span data-stu-id="b96a8-615">Married</span></span>                | <span data-ttu-id="b96a8-616">Marié</span><span class="sxs-lookup"><span data-stu-id="b96a8-616">Married</span></span>                   |
| <span data-ttu-id="b96a8-617">Unique</span><span class="sxs-lookup"><span data-stu-id="b96a8-617">Single</span></span>                 | <span data-ttu-id="b96a8-618">Unique</span><span class="sxs-lookup"><span data-stu-id="b96a8-618">Single</span></span>                    |
| <span data-ttu-id="b96a8-619">Veuf</span><span class="sxs-lookup"><span data-stu-id="b96a8-619">Widowed</span></span>                | <span data-ttu-id="b96a8-620">Veuf</span><span class="sxs-lookup"><span data-stu-id="b96a8-620">Widowed</span></span>                   |
| <span data-ttu-id="b96a8-621">Divorcé</span><span class="sxs-lookup"><span data-stu-id="b96a8-621">Divorced</span></span>               | <span data-ttu-id="b96a8-622">Divorcé</span><span class="sxs-lookup"><span data-stu-id="b96a8-622">Divorced</span></span>                  |
| <span data-ttu-id="b96a8-623">Partenariat enregistré</span><span class="sxs-lookup"><span data-stu-id="b96a8-623">Registered Partnership</span></span> | <span data-ttu-id="b96a8-624">Partenariat local</span><span class="sxs-lookup"><span data-stu-id="b96a8-624">Domestic Partnership</span></span>      |
| <span data-ttu-id="b96a8-625">None</span><span class="sxs-lookup"><span data-stu-id="b96a8-625">None</span></span>                   | <span data-ttu-id="b96a8-626">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="b96a8-626">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="b96a8-627">Concubinage</span><span class="sxs-lookup"><span data-stu-id="b96a8-627">Cohabiting</span></span>             | <span data-ttu-id="b96a8-628">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="b96a8-628">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="b96a8-629">Sexe</span><span class="sxs-lookup"><span data-stu-id="b96a8-629">Gender</span></span>

<span data-ttu-id="b96a8-630">Le sexe est mis en correspondance avec Dayforce et traduit, au besoin, dans les valeurs acceptées lors de l'intégration.</span><span class="sxs-lookup"><span data-stu-id="b96a8-630">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="b96a8-631">Le tableau suivant montre comment le sexe est mis en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b96a8-631">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="b96a8-632">Talent</span><span class="sxs-lookup"><span data-stu-id="b96a8-632">Talent</span></span>       | <span data-ttu-id="b96a8-633">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b96a8-633">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="b96a8-634">Masculin</span><span class="sxs-lookup"><span data-stu-id="b96a8-634">Male</span></span>         | <span data-ttu-id="b96a8-635">Masculin</span><span class="sxs-lookup"><span data-stu-id="b96a8-635">Male</span></span>                      |
| <span data-ttu-id="b96a8-636">Féminin</span><span class="sxs-lookup"><span data-stu-id="b96a8-636">Female</span></span>       | <span data-ttu-id="b96a8-637">Féminin</span><span class="sxs-lookup"><span data-stu-id="b96a8-637">Female</span></span>                    |
| <span data-ttu-id="b96a8-638">Non spécifique</span><span class="sxs-lookup"><span data-stu-id="b96a8-638">Non-specific</span></span> | <span data-ttu-id="b96a8-639">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="b96a8-639">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="b96a8-640">Mode de paiement</span><span class="sxs-lookup"><span data-stu-id="b96a8-640">Payment method</span></span>

<span data-ttu-id="b96a8-641">Les modes de paiement fournissent à l'employé et à la société une manière de décrire la façon dont les employés sont payés.</span><span class="sxs-lookup"><span data-stu-id="b96a8-641">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="b96a8-642">Les modes de paiement sont mis en correspondance avec Dayforce et traduit, au besoin, dans les valeurs acceptées lors de l'intégration.</span><span class="sxs-lookup"><span data-stu-id="b96a8-642">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="b96a8-643">Le tableau suivant montre comment les modes de paiement sont mis en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b96a8-643">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="b96a8-644">Talent</span><span class="sxs-lookup"><span data-stu-id="b96a8-644">Talent</span></span>             | <span data-ttu-id="b96a8-645">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b96a8-645">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="b96a8-646">Espèces</span><span class="sxs-lookup"><span data-stu-id="b96a8-646">Cash</span></span>               | <span data-ttu-id="b96a8-647">Espèces</span><span class="sxs-lookup"><span data-stu-id="b96a8-647">Cash</span></span>                      |
| <span data-ttu-id="b96a8-648">Paiement électronique</span><span class="sxs-lookup"><span data-stu-id="b96a8-648">Electronic Payment</span></span> | <span data-ttu-id="b96a8-649">Virement</span><span class="sxs-lookup"><span data-stu-id="b96a8-649">Transfer</span></span>                  |
| <span data-ttu-id="b96a8-650">Chèque</span><span class="sxs-lookup"><span data-stu-id="b96a8-650">Check</span></span>              | <span data-ttu-id="b96a8-651">Chèque</span><span class="sxs-lookup"><span data-stu-id="b96a8-651">Cheque</span></span>                    |
| <span data-ttu-id="b96a8-652">Traites bancaires</span><span class="sxs-lookup"><span data-stu-id="b96a8-652">Bank Draft</span></span>         | <span data-ttu-id="b96a8-653">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="b96a8-653">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="b96a8-654">Autre/s</span><span class="sxs-lookup"><span data-stu-id="b96a8-654">Other</span></span>              | <span data-ttu-id="b96a8-655">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="b96a8-655">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="b96a8-656">Type de compte bancaire</span><span class="sxs-lookup"><span data-stu-id="b96a8-656">Bank account type</span></span>

<span data-ttu-id="b96a8-657">Les types de comptes bancaires sont utilisés pour les paiements électroniques aux employés.</span><span class="sxs-lookup"><span data-stu-id="b96a8-657">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="b96a8-658">Les types de comptes bancaires sont mis en correspondance avec Dayforce tant qu'informations de compte de transfert.</span><span class="sxs-lookup"><span data-stu-id="b96a8-658">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="b96a8-659">Les types de comptes bancaires sont traduits, au besoin, dans des valeurs acceptées lors de l'intégration.</span><span class="sxs-lookup"><span data-stu-id="b96a8-659">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="b96a8-660">Talent</span><span class="sxs-lookup"><span data-stu-id="b96a8-660">Talent</span></span>            | <span data-ttu-id="b96a8-661">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b96a8-661">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="b96a8-662">Compte courant</span><span class="sxs-lookup"><span data-stu-id="b96a8-662">Checking Account</span></span>  | <span data-ttu-id="b96a8-663">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="b96a8-663">CheckingAccount</span></span>           |
| <span data-ttu-id="b96a8-664">Compte de paie</span><span class="sxs-lookup"><span data-stu-id="b96a8-664">Payroll Account</span></span>   | <span data-ttu-id="b96a8-665">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="b96a8-665">PayrollAccount</span></span>            |
| <span data-ttu-id="b96a8-666">Compte d'épargne</span><span class="sxs-lookup"><span data-stu-id="b96a8-666">Savings Account</span></span>   | <span data-ttu-id="b96a8-667">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="b96a8-667">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="b96a8-668">Compte BankGirot</span><span class="sxs-lookup"><span data-stu-id="b96a8-668">BankGirot account</span></span> | <span data-ttu-id="b96a8-669">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="b96a8-669">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="b96a8-670">Compte PlusGirot</span><span class="sxs-lookup"><span data-stu-id="b96a8-670">PlusGirot account</span></span> | <span data-ttu-id="b96a8-671">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="b96a8-671">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="b96a8-672">Codes de rémunérations</span><span class="sxs-lookup"><span data-stu-id="b96a8-672">Earning codes</span></span>

<span data-ttu-id="b96a8-673">Les codes de rémunérations identifient de manière unique chaque type de revenus que les collaborateurs reçoivent.</span><span class="sxs-lookup"><span data-stu-id="b96a8-673">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="b96a8-674">Les codes couvrent différents paramètres associés aux revenus, tels que des règles comptables, des lois fiscales, des conditions de génération d'états, et la capacité de montant brut.</span><span class="sxs-lookup"><span data-stu-id="b96a8-674">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="b96a8-675">Si une fréquence non prise en charge est utilisée, la fréquence **Chaque paie** est utilisée par défaut pour le calcul.</span><span class="sxs-lookup"><span data-stu-id="b96a8-675">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="b96a8-676">Fréquences prises en charge</span><span class="sxs-lookup"><span data-stu-id="b96a8-676">Supported frequencies</span></span>

- <span data-ttu-id="b96a8-677">Tous</span><span class="sxs-lookup"><span data-stu-id="b96a8-677">All</span></span>
- <span data-ttu-id="b96a8-678">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="b96a8-678">EVERYPAY</span></span>
- <span data-ttu-id="b96a8-679">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="b96a8-679">EACHPAYPERIOD</span></span>
- <span data-ttu-id="b96a8-680">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="b96a8-680">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="b96a8-681">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="b96a8-681">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="b96a8-682">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-682">1OFMTH</span></span>
- <span data-ttu-id="b96a8-683">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-683">LASTOFMTH</span></span>
- <span data-ttu-id="b96a8-684">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-684">2OFMTH</span></span>
- <span data-ttu-id="b96a8-685">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-685">3OFMTH</span></span>
- <span data-ttu-id="b96a8-686">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-686">4OFMTH</span></span>
- <span data-ttu-id="b96a8-687">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-687">5OFMTH</span></span>
- <span data-ttu-id="b96a8-688">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-688">1N2OFMTH</span></span>
- <span data-ttu-id="b96a8-689">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-689">3N4OFMTH</span></span>
- <span data-ttu-id="b96a8-690">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-690">1N3OFMTH</span></span>
- <span data-ttu-id="b96a8-691">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-691">1N4OFMTH</span></span>
- <span data-ttu-id="b96a8-692">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-692">2N3OFMTH</span></span>
- <span data-ttu-id="b96a8-693">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-693">2N4OFMTH</span></span>
- <span data-ttu-id="b96a8-694">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-694">1N2N3OFMTH</span></span>
- <span data-ttu-id="b96a8-695">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-695">1N2N4OFMTH</span></span>
- <span data-ttu-id="b96a8-696">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-696">1N3N4OFMTH</span></span>
- <span data-ttu-id="b96a8-697">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-697">2N3N4OFMTH</span></span>
- <span data-ttu-id="b96a8-698">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b96a8-698">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="b96a8-699">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="b96a8-699">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="b96a8-700">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="b96a8-700">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="b96a8-701">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="b96a8-701">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="b96a8-702">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="b96a8-702">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="b96a8-703">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="b96a8-703">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="b96a8-704">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="b96a8-704">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="b96a8-705">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="b96a8-705">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="b96a8-706">Adresses</span><span class="sxs-lookup"><span data-stu-id="b96a8-706">Addresses</span></span>

<span data-ttu-id="b96a8-707">L'identification d'un pays ou d'une région, d'un état, et des codes département (municipalité) spécifiques nécessite des formats spécifiques que les fournisseurs Dayforce et dans le pays/la région peuvent identifier.</span><span class="sxs-lookup"><span data-stu-id="b96a8-707">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="b96a8-708">Bien que le format pour les villes soit flexible, chaque ville doit être associée à un état.</span><span class="sxs-lookup"><span data-stu-id="b96a8-708">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="b96a8-709">Talent</span><span class="sxs-lookup"><span data-stu-id="b96a8-709">Talent</span></span>              | <span data-ttu-id="b96a8-710">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b96a8-710">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="b96a8-711">Pays/région</span><span class="sxs-lookup"><span data-stu-id="b96a8-711">Country/Region</span></span>      | <span data-ttu-id="b96a8-712">Code pays</span><span class="sxs-lookup"><span data-stu-id="b96a8-712">Country Code</span></span>          |
| <span data-ttu-id="b96a8-713">Code postal</span><span class="sxs-lookup"><span data-stu-id="b96a8-713">Zip/Postal Code</span></span>     | <span data-ttu-id="b96a8-714">Code postal</span><span class="sxs-lookup"><span data-stu-id="b96a8-714">Postal Code</span></span>           |
| <span data-ttu-id="b96a8-715">État</span><span class="sxs-lookup"><span data-stu-id="b96a8-715">State</span></span>               | <span data-ttu-id="b96a8-716">Code région</span><span class="sxs-lookup"><span data-stu-id="b96a8-716">State Code</span></span>            |
| <span data-ttu-id="b96a8-717">Ville</span><span class="sxs-lookup"><span data-stu-id="b96a8-717">City</span></span>                | <span data-ttu-id="b96a8-718">Ville</span><span class="sxs-lookup"><span data-stu-id="b96a8-718">City</span></span>                  |
| <span data-ttu-id="b96a8-719">Commune</span><span class="sxs-lookup"><span data-stu-id="b96a8-719">County</span></span>              | <span data-ttu-id="b96a8-720">Département (municipalité)</span><span class="sxs-lookup"><span data-stu-id="b96a8-720">County (Municipality)</span></span> |
| <span data-ttu-id="b96a8-721">Rue</span><span class="sxs-lookup"><span data-stu-id="b96a8-721">Street</span></span>              | <span data-ttu-id="b96a8-722">Ligne d'adresse 1</span><span class="sxs-lookup"><span data-stu-id="b96a8-722">Address Line 1</span></span>        |
| <span data-ttu-id="b96a8-723">Numéro de la rue</span><span class="sxs-lookup"><span data-stu-id="b96a8-723">Street Number</span></span>       | <span data-ttu-id="b96a8-724">Ligne d'adresse 2</span><span class="sxs-lookup"><span data-stu-id="b96a8-724">Address Line 2</span></span>        |
| <span data-ttu-id="b96a8-725">Info complémentaire sur le bâtiment</span><span class="sxs-lookup"><span data-stu-id="b96a8-725">Building Complement</span></span> | <span data-ttu-id="b96a8-726">Ligne d'adresse 5</span><span class="sxs-lookup"><span data-stu-id="b96a8-726">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="b96a8-727">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="b96a8-727">Passport number</span></span>

<span data-ttu-id="b96a8-728">Les employés peuvent déclarer des informations de passeport.</span><span class="sxs-lookup"><span data-stu-id="b96a8-728">Employees can declare passport information.</span></span> <span data-ttu-id="b96a8-729">Ces informations sont de type d'identification **Passeport** et sont intégrées à Dayforce dans le cadre des informations spécifique au Mexique d'un employé.</span><span class="sxs-lookup"><span data-stu-id="b96a8-729">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="b96a8-730">Type d'identification = « Passeport »</span><span class="sxs-lookup"><span data-stu-id="b96a8-730">Identification Type = "Passport"</span></span>
- <span data-ttu-id="b96a8-731">Date d'émission</span><span class="sxs-lookup"><span data-stu-id="b96a8-731">Issued Date</span></span>
- <span data-ttu-id="b96a8-732">Date d'expiration</span><span class="sxs-lookup"><span data-stu-id="b96a8-732">Expiration Date</span></span>

<span data-ttu-id="b96a8-733">Les employés peuvent déclarer plusieurs numéros d'identification de type d'identification **Passeport**.</span><span class="sxs-lookup"><span data-stu-id="b96a8-733">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="b96a8-734">Toutefois, seule la saisie de passeport actif actuel est intégrée à Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b96a8-734">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="b96a8-735">Si toutes les entrées de passeport sont arrivées à expiration, le passeport émis le plus récemment est intégré dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b96a8-735">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
