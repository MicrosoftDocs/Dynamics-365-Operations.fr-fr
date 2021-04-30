---
title: Configuration de l’intégration avec Dayforce
description: L’intégration entre Microsoft Dynamics 365 Human Resources et Ceridian Dayforce repose sur plusieurs étapes de configuration décrites dans cet article. Vous devez configurer l’intégration dans Human Resources et Dayforce avant de pouvoir traiter un cycle de paie.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PersonnelIntegrationConfiguration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1647b7fbf84a78051e745e918954df32a2e7e1dd
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890002"
---
# <a name="configure-integration-with-dayforce"></a><span data-ttu-id="2a644-104">Configuration de l’intégration avec Dayforce</span><span class="sxs-lookup"><span data-stu-id="2a644-104">Configure integration with Dayforce</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="2a644-105">L’intégration entre Microsoft Dynamics 365 Human Resources et Ceridian Dayforce repose sur plusieurs étapes de configuration décrites dans cet article.</span><span class="sxs-lookup"><span data-stu-id="2a644-105">The integration between Microsoft Dynamics 365 Human Resources and Ceridian Dayforce relies on several configuration steps that are described in this article.</span></span> <span data-ttu-id="2a644-106">Vous devez configurer l’intégration dans Human Resources et Dayforce avant de pouvoir traiter un cycle de paie.</span><span class="sxs-lookup"><span data-stu-id="2a644-106">You must configure the integration in both Human Resources and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="2a644-107">Lorsque vous utilisez un service comme Dayforce pour compléter des cycles de paie, vous devez activer l’intégration dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2a644-107">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Human Resources.</span></span> <span data-ttu-id="2a644-108">L’intégration nécessite des données spécifiques de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2a644-108">The integration requires specific data from Human Resources.</span></span> <span data-ttu-id="2a644-109">Par conséquent, vous devez vérifier que les données mises en correspondance avec Dayforce sont configurées dans Human Resources d’une manière prenant en charge l’intégration.</span><span class="sxs-lookup"><span data-stu-id="2a644-109">Therefore, you must verify that data that is mapped to Dayforce is configured in Human Resources in a manner that supports the integration.</span></span> <span data-ttu-id="2a644-110">L’intégration utilise les larges catégories de données suivantes :</span><span class="sxs-lookup"><span data-stu-id="2a644-110">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="2a644-111">Données de ressources humaines</span><span class="sxs-lookup"><span data-stu-id="2a644-111">Human resources data</span></span>
- <span data-ttu-id="2a644-112">Données de rémunération</span><span class="sxs-lookup"><span data-stu-id="2a644-112">Compensation data</span></span>
- <span data-ttu-id="2a644-113">Données salariales, telles que des cycles de paie, des périodes de rémunération, et des codes de rémunération</span><span class="sxs-lookup"><span data-stu-id="2a644-113">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="2a644-114">Données sur les collaborateurs</span><span class="sxs-lookup"><span data-stu-id="2a644-114">Worker data</span></span>

<span data-ttu-id="2a644-115">Cet article décrit la procédure à suivre pour activer l’intégration.</span><span class="sxs-lookup"><span data-stu-id="2a644-115">This article describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="2a644-116">Elle décrit également les types de données et les détails de configuration que l’intégration nécessite.</span><span class="sxs-lookup"><span data-stu-id="2a644-116">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="2a644-117">Activer l’intégration</span><span class="sxs-lookup"><span data-stu-id="2a644-117">Enable the integration</span></span>

<span data-ttu-id="2a644-118">Dans Human Resources, vous devez activer l’intégration et entrer des informations de configuration pour vous connecter Dayforce.</span><span class="sxs-lookup"><span data-stu-id="2a644-118">In Human Resources, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="2a644-119">Si vous souhaitez que l’écriture comptable produite soit importée dans Microsoft Dynamics 365 Finance, vous devez également configurer un compte de stockage Microsoft Azure et entrer la chaîne de connexion de stockage Azure dans Finance.</span><span class="sxs-lookup"><span data-stu-id="2a644-119">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="2a644-120">Pour l’activer l’intégration dans Human Resources, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="2a644-120">To turn on the integration in Human Resources, follow these steps.</span></span>

1. <span data-ttu-id="2a644-121">Sur la page **Administration du système**, sélectionnez **Configuration de l’intégration**.</span><span class="sxs-lookup"><span data-stu-id="2a644-121">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="2a644-122">Entrez le point de terminaison FTP (File Transfer Protocol) sécurisé et le chemin d’accès de dossier FTP sécurisé.</span><span class="sxs-lookup"><span data-stu-id="2a644-122">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="2a644-123">Entrez le nom d’utilisateur et le mot de passe de l’utilisateur qui accèdera au point de terminaison FTP et au chemin d’accès du dossier sécurisés.</span><span class="sxs-lookup"><span data-stu-id="2a644-123">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="2a644-124">Testez la connexion, au besoin, puis définissez l’option **Activation de l’intégration de la paie** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="2a644-124">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="2a644-125">Lorsque l’intégration est activée, le package et les fichiers d’exportation de données sont créés, et la fréquence est définie.</span><span class="sxs-lookup"><span data-stu-id="2a644-125">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="2a644-126">Vous pouvez modifier la fréquence selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="2a644-126">You can change this frequency as you require.</span></span>

<span data-ttu-id="2a644-127">Pour plus d’informations sur les comptes de stockage Azure et les chaînes de connexion de stockage Azure, consultez les articles Azure suivants :</span><span class="sxs-lookup"><span data-stu-id="2a644-127">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure articles:</span></span>

- [<span data-ttu-id="2a644-128">À propos des comptes de stockage Azure</span><span class="sxs-lookup"><span data-stu-id="2a644-128">About Azure storage accounts</span></span>](/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="2a644-129">Configurer les chaînes de connexion de stockage Azure</span><span class="sxs-lookup"><span data-stu-id="2a644-129">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="2a644-130">Détails techniques lorsque l’intégration de la paie est activée</span><span class="sxs-lookup"><span data-stu-id="2a644-130">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="2a644-131">Activer l’intégration de la paie a deux principaux effets :</span><span class="sxs-lookup"><span data-stu-id="2a644-131">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="2a644-132">Un projet d’exportation de données nommé « Exportation de l’intégration de la paie » est créé.</span><span class="sxs-lookup"><span data-stu-id="2a644-132">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="2a644-133">Ce projet contient les entités et les champs nécessaires pour l’intégration de la paie.</span><span class="sxs-lookup"><span data-stu-id="2a644-133">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="2a644-134">Pour examiner le projet, accédez à **Administration système**, sélectionnez la vignette **Gestion des données**, puis ouvrez le projet à partir de la liste de projets.</span><span class="sxs-lookup"><span data-stu-id="2a644-134">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="2a644-135">Ce traitement par lots exécute le projet d’exportation de données, chiffre le package de données obtenues, et transfère le fichier de package de données au point de terminaison SFTP configuré dans l’écran **Configuration de l’intégration**.</span><span class="sxs-lookup"><span data-stu-id="2a644-135">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="2a644-136">Le package de données transféré au point de terminaison SFTP est chiffré à l’aide d’une clé unique dans le module.</span><span class="sxs-lookup"><span data-stu-id="2a644-136">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="2a644-137">Cette clé est dans un coffre Azure Key Vault qui n’est accessible que par Ceridian.</span><span class="sxs-lookup"><span data-stu-id="2a644-137">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="2a644-138">Il est impossible de déchiffrer et examiner le contenu du package de données.</span><span class="sxs-lookup"><span data-stu-id="2a644-138">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="2a644-139">Si vous devez examiner le contenu du package de données, vous devez exporter le projet de données « Exportation de l’intégration de la paie » manuellement, le télécharger, puis l’ouvrir.</span><span class="sxs-lookup"><span data-stu-id="2a644-139">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="2a644-140">L’exportation manuelle n’appliquera pas de chiffrement ou de transfert au package.</span><span class="sxs-lookup"><span data-stu-id="2a644-140">Manual export will not apply encryption or transfer the package.</span></span>
> <span data-ttu-id="2a644-141">Pour les instances où les fichiers d'intégration sont envoyés à partir d'un test d'acceptation utilisateur ou d'un environnement de bac à sable Dynamics 365 Human Resources vers un environnement de test Ceridian Dayforce, vous pouvez utiliser l'URL de coffre de clés suivante : https://payrollintegrationprod.vault.azure.net.</span><span class="sxs-lookup"><span data-stu-id="2a644-141">For instances where the integration files are sent from a Dynamics 365 Human Resources UAT or Sandbox environment to a Ceridian Dayforce Test environment, you can use the following key vault URL: https://payrollintegrationprod.vault.azure.net.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="2a644-142">Configurer vos données</span><span class="sxs-lookup"><span data-stu-id="2a644-142">Configure your data</span></span> 

<span data-ttu-id="2a644-143">Pour traiter les paies, vous devez configurer les données des ressources humaines dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2a644-143">To process payroll, you must configure human resource data in Human Resources.</span></span> <span data-ttu-id="2a644-144">Vous devez configurer les données organisationnelles, telles que les tâches et les postes, ainsi que les avantages et les informations de rémunération.</span><span class="sxs-lookup"><span data-stu-id="2a644-144">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="2a644-145">Ces informations fournissent des informations sur l’emploi, le salaire et les déductions nécessaires pour générer le salaire de l’employé.</span><span class="sxs-lookup"><span data-stu-id="2a644-145">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="2a644-146">Données des ressources humaines</span><span class="sxs-lookup"><span data-stu-id="2a644-146">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="2a644-147">Avantages</span><span class="sxs-lookup"><span data-stu-id="2a644-147">Benefits</span></span> 

<span data-ttu-id="2a644-148">Les ressources humaines proposent des outils de paramétrage et de mise à jour des avantages, des déductions et des plans de compensation des collaborateurs qu’une organisation offre ou gère pour ses collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="2a644-148">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="2a644-149">Lorsque vous créez des avantages, n’oubliez pas les données et les configurations suivantes utilisées dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="2a644-149">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="2a644-150">Plans d’avantages</span><span class="sxs-lookup"><span data-stu-id="2a644-150">Benefit plans</span></span>

- <span data-ttu-id="2a644-151">Plan (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-151">Plan (required)</span></span>
- <span data-ttu-id="2a644-152">Type (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-152">Type (required)</span></span>
- <span data-ttu-id="2a644-153">Impact sur la paie (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-153">Payroll impact (required)</span></span>
- <span data-ttu-id="2a644-154">Recouvrer les arriérés</span><span class="sxs-lookup"><span data-stu-id="2a644-154">Recover arrears</span></span>
- <span data-ttu-id="2a644-155">Méthode de déduction</span><span class="sxs-lookup"><span data-stu-id="2a644-155">Deduction method</span></span>
- <span data-ttu-id="2a644-156">Priorité de la déduction</span><span class="sxs-lookup"><span data-stu-id="2a644-156">Deduction priority</span></span>
- <span data-ttu-id="2a644-157">Période limite</span><span class="sxs-lookup"><span data-stu-id="2a644-157">Limit period</span></span>
- <span data-ttu-id="2a644-158">Montant limite</span><span class="sxs-lookup"><span data-stu-id="2a644-158">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="2a644-159">Avantages</span><span class="sxs-lookup"><span data-stu-id="2a644-159">Benefits</span></span>

- <span data-ttu-id="2a644-160">Plan (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-160">Plan (required)</span></span>
- <span data-ttu-id="2a644-161">Type (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-161">Type (required)</span></span>
- <span data-ttu-id="2a644-162">Option (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-162">Option (required)</span></span>
- <span data-ttu-id="2a644-163">ID avantage (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-163">Benefit ID (required)</span></span>
- <span data-ttu-id="2a644-164">Fréquence</span><span class="sxs-lookup"><span data-stu-id="2a644-164">Frequency</span></span>
- <span data-ttu-id="2a644-165">Base</span><span class="sxs-lookup"><span data-stu-id="2a644-165">Basis</span></span>
- <span data-ttu-id="2a644-166">Montant ou taux</span><span class="sxs-lookup"><span data-stu-id="2a644-166">Amount or rate</span></span>
- <span data-ttu-id="2a644-167">Code de rémunération</span><span class="sxs-lookup"><span data-stu-id="2a644-167">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="2a644-168">Fréquences prises en charge</span><span class="sxs-lookup"><span data-stu-id="2a644-168">Supported frequencies</span></span> 

- <span data-ttu-id="2a644-169">Hebdomadairement</span><span class="sxs-lookup"><span data-stu-id="2a644-169">Weekly</span></span>
- <span data-ttu-id="2a644-170">Bimensuelle</span><span class="sxs-lookup"><span data-stu-id="2a644-170">Bi-weekly</span></span>
- <span data-ttu-id="2a644-171">Bimensuel</span><span class="sxs-lookup"><span data-stu-id="2a644-171">Semi-monthly</span></span>
- <span data-ttu-id="2a644-172">Mensuellement</span><span class="sxs-lookup"><span data-stu-id="2a644-172">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="2a644-173">Bases pris en charge</span><span class="sxs-lookup"><span data-stu-id="2a644-173">Supported bases</span></span> 

- <span data-ttu-id="2a644-174">Montant fixe</span><span class="sxs-lookup"><span data-stu-id="2a644-174">Fixed amount</span></span>
- <span data-ttu-id="2a644-175">Pourcentage des rémunérations</span><span class="sxs-lookup"><span data-stu-id="2a644-175">Percent of earnings</span></span>
- <span data-ttu-id="2a644-176">Heures productives</span><span class="sxs-lookup"><span data-stu-id="2a644-176">Productive hours</span></span>

<span data-ttu-id="2a644-177">Dayforce crée les déductions suivantes, selon l’impact sur la paie défini dans le plan d’avantages.</span><span class="sxs-lookup"><span data-stu-id="2a644-177">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="2a644-178">Sélection dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="2a644-178">Selection in Human Resources</span></span>        | <span data-ttu-id="2a644-179">Résultat dans Dayforce</span><span class="sxs-lookup"><span data-stu-id="2a644-179">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="2a644-180">Aucune</span><span class="sxs-lookup"><span data-stu-id="2a644-180">None</span></span>                       | <span data-ttu-id="2a644-181">Aucune retenue n’est créée.</span><span class="sxs-lookup"><span data-stu-id="2a644-181">No deduction is created.</span></span>                      |
| <span data-ttu-id="2a644-182">Déduction uniquement</span><span class="sxs-lookup"><span data-stu-id="2a644-182">Deduction only</span></span>             | <span data-ttu-id="2a644-183">Une retenue employé est créée.</span><span class="sxs-lookup"><span data-stu-id="2a644-183">An employee deduction is created.</span></span>             |
| <span data-ttu-id="2a644-184">Contribution uniquement</span><span class="sxs-lookup"><span data-stu-id="2a644-184">Contribution only</span></span>          | <span data-ttu-id="2a644-185">Une retenue employeur est créée.</span><span class="sxs-lookup"><span data-stu-id="2a644-185">An employer deduction is created.</span></span>             |
| <span data-ttu-id="2a644-186">Déduction et contribution</span><span class="sxs-lookup"><span data-stu-id="2a644-186">Deduction and contribution</span></span> | <span data-ttu-id="2a644-187">Des retenues employé et employeur sont créées.</span><span class="sxs-lookup"><span data-stu-id="2a644-187">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="2a644-188">Pour plus d’informations sur la définition et la gestion des programmes d’avantages, consultez les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="2a644-188">For more information about how to define and manage a benefits program, see the following articles:</span></span>

- [<span data-ttu-id="2a644-189">Communiquer le programme d’avantages à un employé</span><span class="sxs-lookup"><span data-stu-id="2a644-189">Deliver an employee benefits program</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="2a644-190">Créer un avantage</span><span class="sxs-lookup"><span data-stu-id="2a644-190">Create a new benefit</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="2a644-191">Définir les règles d’admissibilité et les stratégies relatives aux avantages</span><span class="sxs-lookup"><span data-stu-id="2a644-191">Define benefit eligibility rules and policies</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="2a644-192">Inscrire et annuler l’inscription des travailleurs à des avantages</span><span class="sxs-lookup"><span data-stu-id="2a644-192">Enroll and remove benefits from workers</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="2a644-193">Rémunération</span><span class="sxs-lookup"><span data-stu-id="2a644-193">Compensation</span></span> 

<span data-ttu-id="2a644-194">La gestion des rémunérations est utilisée pour contrôler la rémunération de base et les primes.</span><span class="sxs-lookup"><span data-stu-id="2a644-194">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="2a644-195">Le salaire de base fixe et les augmentations pour mérite d’un employé sont contrôlés via les régimes de rémunération fixe.</span><span class="sxs-lookup"><span data-stu-id="2a644-195">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="2a644-196">Le paiement des primes (primes liées aux résultats, options d’achat d’actions et octrois d’actions), ainsi que les primes exceptionnelles, est contrôlé via les régimes de rémunération variable.</span><span class="sxs-lookup"><span data-stu-id="2a644-196">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="2a644-197">Dayforce utilise les informations de rémunération pour calculer le taux horaire ou annuel d’un employé.</span><span class="sxs-lookup"><span data-stu-id="2a644-197">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="2a644-198">Des plans de rémunération fixe et des conversions de taux de salaire sont requis.</span><span class="sxs-lookup"><span data-stu-id="2a644-198">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="2a644-199">Les employés doivent être associés à un plan de rémunération fixe.</span><span class="sxs-lookup"><span data-stu-id="2a644-199">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="2a644-200">Pour plus d’informations sur les plans de rémunération, voir les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="2a644-200">For more information about compensation plans, see the following articles:</span></span>

- [<span data-ttu-id="2a644-201">Créer des régimes de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="2a644-201">Create fixed compensation plans</span></span>](/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="2a644-202">Créer des régimes de rémunération variable</span><span class="sxs-lookup"><span data-stu-id="2a644-202">Create variable compensation plans</span></span>](/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="2a644-203">Développer les plans et la structure du salaire/de la rémunération</span><span class="sxs-lookup"><span data-stu-id="2a644-203">Develop salary/compensation structure and plans</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="2a644-204">Traiter la rémunération</span><span class="sxs-lookup"><span data-stu-id="2a644-204">Process compensation</span></span>](/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="2a644-205">Définir le processus de rémunération et calculer les résultats</span><span class="sxs-lookup"><span data-stu-id="2a644-205">Define compensation process and calculate results</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="2a644-206">Inscrire un employé à un régime de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="2a644-206">Enroll an employee in a fixed compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="2a644-207">Inscrire un employé à un régime de rémunération variable</span><span class="sxs-lookup"><span data-stu-id="2a644-207">Enroll an employee in a variable compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="2a644-208">Postes</span><span class="sxs-lookup"><span data-stu-id="2a644-208">Jobs</span></span> 

<span data-ttu-id="2a644-209">Une tâche est un ensemble de tâches et de responsabilités attribuées à la personne affectée à la tâche.</span><span class="sxs-lookup"><span data-stu-id="2a644-209">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="2a644-210">Pour plus d’informations, voir l’article suivant :</span><span class="sxs-lookup"><span data-stu-id="2a644-210">For more information, see the following articles:</span></span>

- [<span data-ttu-id="2a644-211">Paramétrage des composants d’une tâche</span><span class="sxs-lookup"><span data-stu-id="2a644-211">Setting up the components of a job</span></span>](/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="2a644-212">Définir les nouvelles tâches</span><span class="sxs-lookup"><span data-stu-id="2a644-212">Define new jobs</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="2a644-213">Postes</span><span class="sxs-lookup"><span data-stu-id="2a644-213">Positions</span></span>

<span data-ttu-id="2a644-214">Un poste est une instance individuelle d’une tâche.</span><span class="sxs-lookup"><span data-stu-id="2a644-214">A position is an individual instance of a job.</span></span> <span data-ttu-id="2a644-215">Par exemple, le poste « Responsable des ventes (est) » est l’un des postes associés à la tâche « Responsable des ventes ».</span><span class="sxs-lookup"><span data-stu-id="2a644-215">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="2a644-216">Un poste existe dans un département.</span><span class="sxs-lookup"><span data-stu-id="2a644-216">A position exists in a department.</span></span> <span data-ttu-id="2a644-217">Seul un collaborateur peut être associé à chaque poste.</span><span class="sxs-lookup"><span data-stu-id="2a644-217">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="2a644-218">Gardez à l’esprit les données et la configuration suivantes lorsque vous paramétrez des postes :</span><span class="sxs-lookup"><span data-stu-id="2a644-218">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="2a644-219">Poste (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-219">Position (required)</span></span>
- <span data-ttu-id="2a644-220">Description (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-220">Description (required)</span></span>
- <span data-ttu-id="2a644-221">Tâche (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-221">Job (required)</span></span>
- <span data-ttu-id="2a644-222">Département (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-222">Department (required)</span></span>
- <span data-ttu-id="2a644-223">Type de poste (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-223">Position type (required)</span></span>
- <span data-ttu-id="2a644-224">Équivalent temps plein</span><span class="sxs-lookup"><span data-stu-id="2a644-224">Full-time equivalent</span></span>
- <span data-ttu-id="2a644-225">Durée annuelle normale (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-225">Annual regular hours (required)</span></span>
- <span data-ttu-id="2a644-226">Rémunéré par l’entité juridique (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-226">Paid by legal entity (required)</span></span>
- <span data-ttu-id="2a644-227">Cycle de paie (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-227">Pay cycle (required)</span></span>
- <span data-ttu-id="2a644-228">Dimension financière par défaut – Centre de coût (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-228">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="2a644-229">Affectation du collaborateur – Collaborateur, début de l’affectation, fin de l’affectation, code motif</span><span class="sxs-lookup"><span data-stu-id="2a644-229">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="2a644-230">Si plusieurs postes dans un même département sont associés à la même tâche, ils sont consolidés un seul poste dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="2a644-230">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="2a644-231">Pour plus d’informations, voir l’article suivant :</span><span class="sxs-lookup"><span data-stu-id="2a644-231">For more information, see the following articles:</span></span>

- [<span data-ttu-id="2a644-232">Organisation du personnel à l’aide des départements, tâches et postes</span><span class="sxs-lookup"><span data-stu-id="2a644-232">Organize your workforce using departments, jobs, and positions</span></span>](/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="2a644-233">Paramétrer les postes</span><span class="sxs-lookup"><span data-stu-id="2a644-233">Set up positions</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="2a644-234">Départements</span><span class="sxs-lookup"><span data-stu-id="2a644-234">Departments</span></span>

<span data-ttu-id="2a644-235">Un département est une unité opérationnelle qui représente une catégorie ou un domaine fonctionnel d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="2a644-235">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="2a644-236">Un département est responsable d’un domaine spécifique de l’organisation, par exemple les ventes, la comptabilité ou les ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="2a644-236">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="2a644-237">Les départements vous permettent de générer des états sur les domaines fonctionnels.</span><span class="sxs-lookup"><span data-stu-id="2a644-237">You can use departments to report on functional areas.</span></span> <span data-ttu-id="2a644-238">Les départements peuvent avoir la responsabilité des résultats.</span><span class="sxs-lookup"><span data-stu-id="2a644-238">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="2a644-239">Pour plus d’informations, voir l’article suivant :</span><span class="sxs-lookup"><span data-stu-id="2a644-239">For more information, see the following articles:</span></span>

- [<span data-ttu-id="2a644-240">Créer un département et l’associer à la hiérarchie des départements</span><span class="sxs-lookup"><span data-stu-id="2a644-240">Create a department and associate it with the department hierarchy</span></span>](/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="2a644-241">Définir les nouveaux départements</span><span class="sxs-lookup"><span data-stu-id="2a644-241">Define new departments</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="2a644-242">Cycles de paie et périodes de rémunération</span><span class="sxs-lookup"><span data-stu-id="2a644-242">Pay cycles and pay periods</span></span>

<span data-ttu-id="2a644-243">Un cycle de paie détermine la fréquence d’exécution de la paie et les jours spécifiques où les collaborateurs sont payés.</span><span class="sxs-lookup"><span data-stu-id="2a644-243">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="2a644-244">Par exemple, un cycle de paie peut être mensuel, et les employés peuvent être payés le dernier jour du mois.</span><span class="sxs-lookup"><span data-stu-id="2a644-244">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="2a644-245">Sinon, un cycle de paie peut être hebdomadaire, et les employés peuvent être payés le mardi après la fin de la période de rémunération.</span><span class="sxs-lookup"><span data-stu-id="2a644-245">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="2a644-246">Les cycles de paie sont affectés aux postes afin de contrôler à quel moment les collaborateurs à ces postes sont payés.</span><span class="sxs-lookup"><span data-stu-id="2a644-246">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="2a644-247">Après avoir créé des cycles de paie, vous pouvez générer des périodes de rémunération pour chaque cycle.</span><span class="sxs-lookup"><span data-stu-id="2a644-247">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="2a644-248">Chaque période de rémunération comprend une date de paiement par défaut basée sur les informations que vous fournissez.</span><span class="sxs-lookup"><span data-stu-id="2a644-248">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="2a644-249">Toutefois, vous pouvez modifier la date de paiement par défaut d’une période de rémunération pour permettre des exceptions, par exemple lorsque la date de paiement a lieu un jour férié.</span><span class="sxs-lookup"><span data-stu-id="2a644-249">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="2a644-250">Les informations suivantes sont utilisée dans Dayforce :</span><span class="sxs-lookup"><span data-stu-id="2a644-250">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="2a644-251">Cycle de paie (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-251">Pay cycle (required)</span></span>
- <span data-ttu-id="2a644-252">Fréquence du cycle de paie (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-252">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="2a644-253">Date de début de la période (première période de rémunération obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-253">Period start date (first pay period required)</span></span>
- <span data-ttu-id="2a644-254">Date de rémunération par défaut (première période de rémunération obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-254">Default payment date (first pay period required)</span></span>

<span data-ttu-id="2a644-255">Ces informations sont intégrées à Dayforce en tant que des groupes de paie, et sont séparées par pays ou par région pour chaque cycle de paie.</span><span class="sxs-lookup"><span data-stu-id="2a644-255">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="2a644-256">Au moins une période de rémunération doit être générée avant l’intégration.</span><span class="sxs-lookup"><span data-stu-id="2a644-256">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="2a644-257">Dayforce génère des calendriers de groupe de paie et des dates de rémunération, selon la date de début de la première période de rémunération et la date de rémunération par défaut paramétrées dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2a644-257">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Human Resources.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="2a644-258">Codes de rémunérations</span><span class="sxs-lookup"><span data-stu-id="2a644-258">Earning codes</span></span>

<span data-ttu-id="2a644-259">Les codes de rémunérations identifient de manière unique chaque type de revenus que les collaborateurs reçoivent.</span><span class="sxs-lookup"><span data-stu-id="2a644-259">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="2a644-260">Les codes ont différents paramètres associés aux revenus, tels que des règles comptables, des lois fiscales, des conditions de génération d’états, et la capacité de montant brut.</span><span class="sxs-lookup"><span data-stu-id="2a644-260">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="2a644-261">Les informations suivantes sont utilisée dans Dayforce :</span><span class="sxs-lookup"><span data-stu-id="2a644-261">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="2a644-262">Code de rémunération (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-262">Earning Code (required)</span></span>
- <span data-ttu-id="2a644-263">Description</span><span class="sxs-lookup"><span data-stu-id="2a644-263">Description</span></span>
- <span data-ttu-id="2a644-264">Unité de mesure</span><span class="sxs-lookup"><span data-stu-id="2a644-264">Unit of measure</span></span>
- <span data-ttu-id="2a644-265">Productif</span><span class="sxs-lookup"><span data-stu-id="2a644-265">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="2a644-266">Données sur les collaborateurs</span><span class="sxs-lookup"><span data-stu-id="2a644-266">Worker data</span></span>

<span data-ttu-id="2a644-267">Les enregistrements pour les différents types d’employés dont vous disposez sont importants pour vos systèmes de ressources humaines et de paie.</span><span class="sxs-lookup"><span data-stu-id="2a644-267">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="2a644-268">Les informations que vous entrez peuvent servir à suivre les informations des collaborateurs et les informations personnelles.</span><span class="sxs-lookup"><span data-stu-id="2a644-268">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="2a644-269">Vous pouvez tenir à jour les informations suivantes pour les travailleurs :</span><span class="sxs-lookup"><span data-stu-id="2a644-269">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="2a644-270">**Base** – Permet de tenir à jour les informations de base sur un collaborateur, telles que les informations de contact, les informations démographiques, les informations d’identification, les informations sur la famille, le statut de service militaire, les informations d’expatriation, et les contacts personnels et les personnes à prévenir en cas d’urgence.</span><span class="sxs-lookup"><span data-stu-id="2a644-270">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="2a644-271">**Emploi** – Permet de tenir à jour les informations relatives à l’emploi des collaborateurs, telles que l’affiliation de la société ou de l’organisation, l’affectation de poste, les dates de début et de fin, l’éligibilité à un emploi, les conditions d’emploi, la retraite, les congés, et les informations de mutation.</span><span class="sxs-lookup"><span data-stu-id="2a644-271">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="2a644-272">**Congé et absence** – Permet de tenir à jour les informations sur les absences des collaborateurs, telles que les calendriers de travail, les transactions d’absence et le paramétrage d’absence.</span><span class="sxs-lookup"><span data-stu-id="2a644-272">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="2a644-273">**Rémunération et paie** – Permet de tenir à jour les informations sur les régimes de rémunération des collaborateurs et les informations de paie, telles que l’inscription à un régime, les primes, les performances, la commission, les informations fiscales, la retraite et les déductions de salaire.</span><span class="sxs-lookup"><span data-stu-id="2a644-273">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="2a644-274">Lorsque vous entrez des informations sur le collaborateur, n’oubliez pas les données et les configurations suivantes utilisées dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="2a644-274">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="2a644-275">Informations générales</span><span class="sxs-lookup"><span data-stu-id="2a644-275">General information</span></span>

- <span data-ttu-id="2a644-276">Matricule (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-276">Personnel number (required)</span></span>
- <span data-ttu-id="2a644-277">Prénom (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-277">First name (required)</span></span>
- <span data-ttu-id="2a644-278">Nom (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-278">Last name (required)</span></span>
- <span data-ttu-id="2a644-279">Autres prénoms</span><span class="sxs-lookup"><span data-stu-id="2a644-279">Middle name</span></span>
- <span data-ttu-id="2a644-280">Date d’ancienneté</span><span class="sxs-lookup"><span data-stu-id="2a644-280">Seniority date</span></span>
- <span data-ttu-id="2a644-281">Connu sous</span><span class="sxs-lookup"><span data-stu-id="2a644-281">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="2a644-282">Informations personnelles</span><span class="sxs-lookup"><span data-stu-id="2a644-282">Personal information</span></span>

- <span data-ttu-id="2a644-283">État civil (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-283">Marital status (required)</span></span>
- <span data-ttu-id="2a644-284">Date de naissance (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-284">Birth date (required)</span></span>
- <span data-ttu-id="2a644-285">Sexe (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-285">Gender (required)</span></span>
- <span data-ttu-id="2a644-286">Personne handicapée</span><span class="sxs-lookup"><span data-stu-id="2a644-286">Person with disabilities</span></span>
- <span data-ttu-id="2a644-287">Région/pays de nationalité (uniquement au Mexique)</span><span class="sxs-lookup"><span data-stu-id="2a644-287">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="2a644-288">Informations d’adresse</span><span class="sxs-lookup"><span data-stu-id="2a644-288">Address information</span></span>

- <span data-ttu-id="2a644-289">Adresse principale (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-289">Primary (required)</span></span>
- <span data-ttu-id="2a644-290">Pays/région (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-290">Country/region (required)</span></span>
- <span data-ttu-id="2a644-291">Code postal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-291">Postal code (required)</span></span>
- <span data-ttu-id="2a644-292">Numéro de la rue (obligatoire) (uniquement au Mexique)</span><span class="sxs-lookup"><span data-stu-id="2a644-292">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="2a644-293">Info complémentaire sur le bâtiment (uniquement au Mexique)</span><span class="sxs-lookup"><span data-stu-id="2a644-293">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="2a644-294">Ville (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-294">City (required)</span></span>
- <span data-ttu-id="2a644-295">État (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-295">State (required)</span></span>
- <span data-ttu-id="2a644-296">Pays (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-296">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="2a644-297">Informations de contact</span><span class="sxs-lookup"><span data-stu-id="2a644-297">Contact information</span></span> 

- <span data-ttu-id="2a644-298">Contact principal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-298">Primary (required)</span></span>
- <span data-ttu-id="2a644-299">Numéro du contact (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-299">Contact number (required)</span></span>
- <span data-ttu-id="2a644-300">Poste</span><span class="sxs-lookup"><span data-stu-id="2a644-300">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="2a644-301">Informations sur les salaires et codes de rémunération</span><span class="sxs-lookup"><span data-stu-id="2a644-301">Payroll information and earning codes</span></span>

<span data-ttu-id="2a644-302">Les employés peuvent bénéficier de revenus spécifiques à une fréquence de paiement donnée et avoir un mode de paiement préféré.</span><span class="sxs-lookup"><span data-stu-id="2a644-302">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="2a644-303">Les champs suivants sont utilisés dans Dayforce pour garantir que ces préférences et paramètres soient utilisés.</span><span class="sxs-lookup"><span data-stu-id="2a644-303">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="2a644-304">Codes de rémunérations</span><span class="sxs-lookup"><span data-stu-id="2a644-304">Earning codes</span></span>

- <span data-ttu-id="2a644-305">Poste (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-305">Position (required)</span></span>
- <span data-ttu-id="2a644-306">Code de rémunération (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-306">Earning Code (required)</span></span>
- <span data-ttu-id="2a644-307">Fréquence (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-307">Frequency (required)</span></span>
- <span data-ttu-id="2a644-308">Montant (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-308">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="2a644-309">Informations sur les salaires</span><span class="sxs-lookup"><span data-stu-id="2a644-309">Payroll information</span></span>

- <span data-ttu-id="2a644-310">Mode de paiement</span><span class="sxs-lookup"><span data-stu-id="2a644-310">Payment Method</span></span>
- <span data-ttu-id="2a644-311">Région économique (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-311">Economic Region (required)</span></span>
- <span data-ttu-id="2a644-312">ID avantages employé</span><span class="sxs-lookup"><span data-stu-id="2a644-312">Employee Benefits ID</span></span>
- <span data-ttu-id="2a644-313">Numéro d’ID national (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-313">National ID Number (required)</span></span>
- <span data-ttu-id="2a644-314">Numéro de service militaire</span><span class="sxs-lookup"><span data-stu-id="2a644-314">Military Service Number</span></span>
- <span data-ttu-id="2a644-315">ID d’équipe (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-315">Shift ID (required)</span></span>
- <span data-ttu-id="2a644-316">Numéro de taxe (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-316">Tax Number (required)</span></span>
- <span data-ttu-id="2a644-317">ID syndicat (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-317">Union ID (required)</span></span>
- <span data-ttu-id="2a644-318">ID de la journée de travail (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-318">Work Day ID (required)</span></span>
- <span data-ttu-id="2a644-319">Numéro de permis de travail</span><span class="sxs-lookup"><span data-stu-id="2a644-319">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="2a644-320">Pour le mode de paiement, le Mexique prend en charge les **Espèces**, les **Chèques** (chèque physique de la société) et le **Paiement électronique**.</span><span class="sxs-lookup"><span data-stu-id="2a644-320">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="2a644-321">Si aucun mode de paiement n’est spécifié, le **Chèque** est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="2a644-321">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="2a644-322">Détails de l’emploi</span><span class="sxs-lookup"><span data-stu-id="2a644-322">Employment details</span></span>

<span data-ttu-id="2a644-323">L’historique des détails de l’emploi est utilisé comme information clé pour en dériver le statut d’embauche, de fin du contrat, et de réembauche d’un employé dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="2a644-323">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="2a644-324">Dayforce prend en charge un seul enregistrement d’emploi actif à la fois.</span><span class="sxs-lookup"><span data-stu-id="2a644-324">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="2a644-325">Date de début de l’emploi (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-325">Employment start date (required)</span></span>
- <span data-ttu-id="2a644-326">Date de fin de l’emploi</span><span class="sxs-lookup"><span data-stu-id="2a644-326">Employment end date</span></span>
- <span data-ttu-id="2a644-327">Date de début</span><span class="sxs-lookup"><span data-stu-id="2a644-327">Start date</span></span>
- <span data-ttu-id="2a644-328">Date de début de contrat ajustée</span><span class="sxs-lookup"><span data-stu-id="2a644-328">Adjusted start date</span></span>
- <span data-ttu-id="2a644-329">Date de fin de contrat (obligatoire à la fin du contrat)</span><span class="sxs-lookup"><span data-stu-id="2a644-329">Termination date (required upon termination)</span></span>
- <span data-ttu-id="2a644-330">Motif de la fin du contrat (obligatoire à la fin du contrat)</span><span class="sxs-lookup"><span data-stu-id="2a644-330">Termination reason (required upon termination)</span></span>

<span data-ttu-id="2a644-331">Les dates clés d’un employé sont dérivées à l’aide des informations suivantes.</span><span class="sxs-lookup"><span data-stu-id="2a644-331">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="2a644-332">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="2a644-332">Human Resources</span></span>                | <span data-ttu-id="2a644-333">Dayforce</span><span class="sxs-lookup"><span data-stu-id="2a644-333">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="2a644-334">Date d’embauche la plus récente</span><span class="sxs-lookup"><span data-stu-id="2a644-334">Most recent hire date</span></span> | <span data-ttu-id="2a644-335">Début de l’emploi de l’enregistrement d’historique d’emploi avec contrat en cours</span><span class="sxs-lookup"><span data-stu-id="2a644-335">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="2a644-336">Date de fin de contrat</span><span class="sxs-lookup"><span data-stu-id="2a644-336">Termination date</span></span>      | <span data-ttu-id="2a644-337">Date de fin de contrat de l’enregistrement d’historique d’emploi avec contrat en cours</span><span class="sxs-lookup"><span data-stu-id="2a644-337">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="2a644-338">Date de début</span><span class="sxs-lookup"><span data-stu-id="2a644-338">Start date</span></span>            | <span data-ttu-id="2a644-339">Date de début ajustée, date de début, ou début de l’emploi de l’enregistrement d’historique d’emploi inactif actuel</span><span class="sxs-lookup"><span data-stu-id="2a644-339">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="2a644-340">Date d’embauche d’origine</span><span class="sxs-lookup"><span data-stu-id="2a644-340">Original hire date</span></span>    | <span data-ttu-id="2a644-341">Début d’emploi de l’enregistrement d’historique d’emploi le plus proche</span><span class="sxs-lookup"><span data-stu-id="2a644-341">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="2a644-342">Rémunération</span><span class="sxs-lookup"><span data-stu-id="2a644-342">Compensation</span></span>

<span data-ttu-id="2a644-343">Un plan de rémunération fixe doit être associé au poste principal de chaque employé tout au long d’une période d’emploi.</span><span class="sxs-lookup"><span data-stu-id="2a644-343">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="2a644-344">Cette période démarre à la date à laquelle l’employé a été embauché (ou à la date de début de l’emploi) et se poursuit jusqu’à la fin de contrat.</span><span class="sxs-lookup"><span data-stu-id="2a644-344">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="2a644-345">Date d’effet (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-345">Effective Date (required)</span></span>
- <span data-ttu-id="2a644-346">Date d’expiration</span><span class="sxs-lookup"><span data-stu-id="2a644-346">Expiration date</span></span>
- <span data-ttu-id="2a644-347">Taux de salaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-347">Pay Rate (required)</span></span>
- <span data-ttu-id="2a644-348">Conversions de taux de salaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-348">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="2a644-349">Équivalent annuel (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-349">Annual equivalent (required)</span></span>
- <span data-ttu-id="2a644-350">Équivalent horaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-350">Hourly equivalent (required)</span></span>

<span data-ttu-id="2a644-351">Si un employé horaire a plusieurs postes, la rémunération fixe du poste principal est importée dans Dayforce comme taux de base/salaire de niveau d’employé.</span><span class="sxs-lookup"><span data-stu-id="2a644-351">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="2a644-352">Pour les postes non principaux, le taux horaire est enregistré au poste correspondant dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="2a644-352">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="2a644-353">Si un employé salarié occupe plusieurs postes, le taux horaire cumulé et le salaire annuel entre tous les postes actifs sont dérivés et utilisés comme taux de base/salaire au niveau de l’employé.</span><span class="sxs-lookup"><span data-stu-id="2a644-353">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="2a644-354">Numéros d’identifications</span><span class="sxs-lookup"><span data-stu-id="2a644-354">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="2a644-355">Numéro de Sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="2a644-355">Social Security identifier</span></span> 

<span data-ttu-id="2a644-356">Chaque employé doit avoir un numéro principal.</span><span class="sxs-lookup"><span data-stu-id="2a644-356">Every employee must have one primary identifier.</span></span> <span data-ttu-id="2a644-357">Cet numéro doit être de type d’identification **N° S.S.**.</span><span class="sxs-lookup"><span data-stu-id="2a644-357">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="2a644-358">Dans Dayforce, il est automatiquement dérivé du numéro de Sécurité sociale de l’employé qui est obligatoire pour l’embaucher.</span><span class="sxs-lookup"><span data-stu-id="2a644-358">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="2a644-359">Numéro principal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-359">Primary (required)</span></span>
- <span data-ttu-id="2a644-360">Type d’identification = « N° S.S. »</span><span class="sxs-lookup"><span data-stu-id="2a644-360">Identification Type = "SSN"</span></span>
- <span data-ttu-id="2a644-361">Date d’émission</span><span class="sxs-lookup"><span data-stu-id="2a644-361">Issued Date</span></span>
- <span data-ttu-id="2a644-362">Date d’expiration</span><span class="sxs-lookup"><span data-stu-id="2a644-362">Expiration Date</span></span>

<span data-ttu-id="2a644-363">Les employés peuvent déclarer plusieurs numéros d’identification de type d’identification **N° S.S.**.</span><span class="sxs-lookup"><span data-stu-id="2a644-363">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="2a644-364">Toutefois, seul l’enregistrement marqué comme **Principal** est intégré à Dayforce, que le numéro soit active ou arrivé à expiration.</span><span class="sxs-lookup"><span data-stu-id="2a644-364">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="2a644-365">Comptes en banque et décaissements</span><span class="sxs-lookup"><span data-stu-id="2a644-365">Bank accounts and disbursements</span></span>

<span data-ttu-id="2a644-366">Des informations de compte bancaire valides doivent être entrées pour tous les employés qui choisissent d’être payés à l’aide de virements bancaires.</span><span class="sxs-lookup"><span data-stu-id="2a644-366">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="2a644-367">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="2a644-367">Human Resources</span></span>                         | <span data-ttu-id="2a644-368">Dayforce</span><span class="sxs-lookup"><span data-stu-id="2a644-368">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="2a644-369">Numéro de compte bancaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-369">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="2a644-370">Code SWIFT (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-370">SWIFT code (required)</span></span>          | <span data-ttu-id="2a644-371">Le champ **ID banque** utilisé lors du traitement du salaire au Mexique.</span><span class="sxs-lookup"><span data-stu-id="2a644-371">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="2a644-372">Numéro d’agence (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-372">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="2a644-373">Type de compte bancaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-373">Bank account type (required)</span></span>   | <span data-ttu-id="2a644-374">Le champ **Type de compte** utilisé lors du traitement du salaire au Mexique.</span><span class="sxs-lookup"><span data-stu-id="2a644-374">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="2a644-375">Les valeurs prises en charge sont **Chèque** et **Paie**.</span><span class="sxs-lookup"><span data-stu-id="2a644-375">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="2a644-376">Les employés qui choisissent d’être payés par des virements bancaires doivent fournir un lien vers un compte de solde qui se trouve sous une entité juridique avec son adresse principale au Mexique, et associée à un compte bancaire valide dans une banque mexicaine.</span><span class="sxs-lookup"><span data-stu-id="2a644-376">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="2a644-377">Tous les autres comptes non-solde sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="2a644-377">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="2a644-378">Informations d’adresse</span><span class="sxs-lookup"><span data-stu-id="2a644-378">Address information</span></span>

<span data-ttu-id="2a644-379">Chaque employé doit avoir un lieu principal.</span><span class="sxs-lookup"><span data-stu-id="2a644-379">Every employee must have one primary location.</span></span> <span data-ttu-id="2a644-380">Dans Dayforce, ce lieu est utilisé pour déterminer la résidence principale de l’employé à des fins fiscales.</span><span class="sxs-lookup"><span data-stu-id="2a644-380">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="2a644-381">Lieu principal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-381">Primary (required)</span></span>
- <span data-ttu-id="2a644-382">Pays/région (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-382">Country/region (required)</span></span>
- <span data-ttu-id="2a644-383">Code postal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-383">Zip/postal code (required)</span></span>
- <span data-ttu-id="2a644-384">Rue (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-384">Street (required)</span></span>
- <span data-ttu-id="2a644-385">Numéro de rue (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-385">Street Number (required)</span></span>
- <span data-ttu-id="2a644-386">Info complémentaire sur le bâtiment</span><span class="sxs-lookup"><span data-stu-id="2a644-386">Building Complement</span></span>
- <span data-ttu-id="2a644-387">Ville (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-387">City (required)</span></span>
- <span data-ttu-id="2a644-388">État (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-388">State (required)</span></span>
- <span data-ttu-id="2a644-389">Pays (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-389">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="2a644-390">Configurer vos données pour générer un salaire aux États-Unis et au Canada</span><span class="sxs-lookup"><span data-stu-id="2a644-390">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="2a644-391">Si vous générez un salaire pour des employés aux États-Unis et au Canada, les éléments suivants doivent être configurés :</span><span class="sxs-lookup"><span data-stu-id="2a644-391">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="2a644-392">Les départements sont obligatoires sur les postes.</span><span class="sxs-lookup"><span data-stu-id="2a644-392">Departments are required on positions.</span></span>
- <span data-ttu-id="2a644-393">Les centres de coût doivent être définis comme des dimensions financières et doivent être le premier élément de la chaîne de dimension financière par défaut.</span><span class="sxs-lookup"><span data-stu-id="2a644-393">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="2a644-394">Vous pouvez configurer Human Resources pour demander que les postes spécifient un service.</span><span class="sxs-lookup"><span data-stu-id="2a644-394">You can configure Human Resources to require that Positions specify a Department.</span></span> <span data-ttu-id="2a644-395">Pour ce faire, accédez à **Postes partagés par les ressources humaines > Postes > Demander le service des postes**.</span><span class="sxs-lookup"><span data-stu-id="2a644-395">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="2a644-396">Nous vous recommandons d’appliquer ce paramètre pour l’intégration.</span><span class="sxs-lookup"><span data-stu-id="2a644-396">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="2a644-397">Types de missions</span><span class="sxs-lookup"><span data-stu-id="2a644-397">Job types</span></span>

<span data-ttu-id="2a644-398">Les types de tâches sont utilisés pour regrouper les tâches similaires en catégories.</span><span class="sxs-lookup"><span data-stu-id="2a644-398">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="2a644-399">Les types de tâches sont nécessaires pour traiter la paie aux États-Unis et au Canada.</span><span class="sxs-lookup"><span data-stu-id="2a644-399">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="2a644-400">Les exemples de types de tâches incluent le temps plein et le temps partiel, ou le salaire et le paiement à l’heure.</span><span class="sxs-lookup"><span data-stu-id="2a644-400">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="2a644-401">Les types de tâches sont mis en correspondance dans Dayforce comme types de paies qui indiquent si un employé est payé à l’heure ou salarié.</span><span class="sxs-lookup"><span data-stu-id="2a644-401">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="2a644-402">Les types de tâches et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="2a644-402">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="2a644-403">Type de mission</span><span class="sxs-lookup"><span data-stu-id="2a644-403">Job type</span></span>   | <span data-ttu-id="2a644-404">Description</span><span class="sxs-lookup"><span data-stu-id="2a644-404">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="2a644-405">Horaire</span><span class="sxs-lookup"><span data-stu-id="2a644-405">Hourly</span></span>     | <span data-ttu-id="2a644-406">Horaire</span><span class="sxs-lookup"><span data-stu-id="2a644-406">Hourly</span></span>      |
| <span data-ttu-id="2a644-407">Salarié</span><span class="sxs-lookup"><span data-stu-id="2a644-407">Salaried</span></span>   | <span data-ttu-id="2a644-408">Salarié</span><span class="sxs-lookup"><span data-stu-id="2a644-408">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="2a644-409">Types de poste</span><span class="sxs-lookup"><span data-stu-id="2a644-409">Position types</span></span> 

<span data-ttu-id="2a644-410">Vous utilisez les types de postes pour indiquer si le poste est à temps plein, à temps partiel, ou autre chose.</span><span class="sxs-lookup"><span data-stu-id="2a644-410">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="2a644-411">Les types de postes sont mis en correspondance dans Dayforce comme classes de paiements qui indiquent si un employé est à temps plein ou à temps partiel.</span><span class="sxs-lookup"><span data-stu-id="2a644-411">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="2a644-412">Les types de postes et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="2a644-412">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="2a644-413">Type de poste</span><span class="sxs-lookup"><span data-stu-id="2a644-413">Position type</span></span>   | <span data-ttu-id="2a644-414">Description</span><span class="sxs-lookup"><span data-stu-id="2a644-414">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="2a644-415">Temps plein</span><span class="sxs-lookup"><span data-stu-id="2a644-415">Full-time</span></span>       | <span data-ttu-id="2a644-416">Employé à temps plein</span><span class="sxs-lookup"><span data-stu-id="2a644-416">Full time employee</span></span> |
| <span data-ttu-id="2a644-417">Temps partiel</span><span class="sxs-lookup"><span data-stu-id="2a644-417">Part-time</span></span>       | <span data-ttu-id="2a644-418">Employé à temps partiel</span><span class="sxs-lookup"><span data-stu-id="2a644-418">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="2a644-419">Codes motif</span><span class="sxs-lookup"><span data-stu-id="2a644-419">Reason codes</span></span>

<span data-ttu-id="2a644-420">Les codes motif fournissent des informations sur le statut d’un employé.</span><span class="sxs-lookup"><span data-stu-id="2a644-420">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="2a644-421">Les codes motif sont mis en correspondance avec Dayforce comme motifs du statut, indiquant le motif des modifications apportées au poste ou au statut d’emploi d’un employé.</span><span class="sxs-lookup"><span data-stu-id="2a644-421">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="2a644-422">Les codes motif et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="2a644-422">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="2a644-423">Code motif</span><span class="sxs-lookup"><span data-stu-id="2a644-423">Reason code</span></span>    | <span data-ttu-id="2a644-424">Description</span><span class="sxs-lookup"><span data-stu-id="2a644-424">Description</span></span>      | <span data-ttu-id="2a644-425">Scénarios applicables</span><span class="sxs-lookup"><span data-stu-id="2a644-425">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="2a644-426">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="2a644-426">RESIGNATION</span></span>    | <span data-ttu-id="2a644-427">Démission</span><span class="sxs-lookup"><span data-stu-id="2a644-427">Resignation</span></span>      | <span data-ttu-id="2a644-428">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="2a644-428">Terminate worker</span></span>     |
| <span data-ttu-id="2a644-429">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="2a644-429">TERMINATION</span></span>    | <span data-ttu-id="2a644-430">Fin du contrat</span><span class="sxs-lookup"><span data-stu-id="2a644-430">Termination</span></span>      | <span data-ttu-id="2a644-431">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="2a644-431">Terminate worker</span></span>     |
| <span data-ttu-id="2a644-432">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="2a644-432">RETIREMENT</span></span>     | <span data-ttu-id="2a644-433">Retraite</span><span class="sxs-lookup"><span data-stu-id="2a644-433">Retirement</span></span>       | <span data-ttu-id="2a644-434">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="2a644-434">Terminate worker</span></span>     |
| <span data-ttu-id="2a644-435">OTHER</span><span class="sxs-lookup"><span data-stu-id="2a644-435">OTHER</span></span>          | <span data-ttu-id="2a644-436">Autres motifs</span><span class="sxs-lookup"><span data-stu-id="2a644-436">Other Reasons</span></span>    | <span data-ttu-id="2a644-437">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="2a644-437">Terminate worker</span></span>     |
| <span data-ttu-id="2a644-438">DEATH</span><span class="sxs-lookup"><span data-stu-id="2a644-438">DEATH</span></span>          | <span data-ttu-id="2a644-439">Décès</span><span class="sxs-lookup"><span data-stu-id="2a644-439">Death</span></span>            | <span data-ttu-id="2a644-440">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="2a644-440">Terminate worker</span></span>     |
| <span data-ttu-id="2a644-441">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="2a644-441">LEAVEOFABSENCE</span></span> | <span data-ttu-id="2a644-442">Congé</span><span class="sxs-lookup"><span data-stu-id="2a644-442">Leave of Absence</span></span> | <span data-ttu-id="2a644-443">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="2a644-443">Terminate worker</span></span>     |
| <span data-ttu-id="2a644-444">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="2a644-444">CONTRACTEND</span></span>    | <span data-ttu-id="2a644-445">Fin du contrat</span><span class="sxs-lookup"><span data-stu-id="2a644-445">End of Contract</span></span>  | <span data-ttu-id="2a644-446">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="2a644-446">Terminate worker</span></span>     |
| <span data-ttu-id="2a644-447">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="2a644-447">SALARYCHANGE</span></span>   | <span data-ttu-id="2a644-448">Modification du salaire</span><span class="sxs-lookup"><span data-stu-id="2a644-448">Change of Salary</span></span> | <span data-ttu-id="2a644-449">Rémunération</span><span class="sxs-lookup"><span data-stu-id="2a644-449">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="2a644-450">Situation de famille</span><span class="sxs-lookup"><span data-stu-id="2a644-450">Marital status</span></span>

<span data-ttu-id="2a644-451">Les valeurs de situation de famille sont mises en correspondance avec Dayforce et traduite, au besoin, dans les valeurs acceptées lors de l’intégration.</span><span class="sxs-lookup"><span data-stu-id="2a644-451">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="2a644-452">Le tableau suivant montre comment les valeurs de situation de famille sont mises en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="2a644-452">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="2a644-453">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="2a644-453">Human Resources</span></span>                 | <span data-ttu-id="2a644-454">Dayforce</span><span class="sxs-lookup"><span data-stu-id="2a644-454">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="2a644-455">Marié</span><span class="sxs-lookup"><span data-stu-id="2a644-455">Married</span></span>                | <span data-ttu-id="2a644-456">Marié</span><span class="sxs-lookup"><span data-stu-id="2a644-456">Married</span></span>              |
| <span data-ttu-id="2a644-457">Unique</span><span class="sxs-lookup"><span data-stu-id="2a644-457">Single</span></span>                 | <span data-ttu-id="2a644-458">Unique</span><span class="sxs-lookup"><span data-stu-id="2a644-458">Single</span></span>               |
| <span data-ttu-id="2a644-459">Veuf</span><span class="sxs-lookup"><span data-stu-id="2a644-459">Widowed</span></span>                | <span data-ttu-id="2a644-460">Veuf</span><span class="sxs-lookup"><span data-stu-id="2a644-460">Widowed</span></span>              |
| <span data-ttu-id="2a644-461">Divorcé</span><span class="sxs-lookup"><span data-stu-id="2a644-461">Divorced</span></span>               | <span data-ttu-id="2a644-462">Divorcé</span><span class="sxs-lookup"><span data-stu-id="2a644-462">Divorced</span></span>             |
| <span data-ttu-id="2a644-463">Partenariat enregistré</span><span class="sxs-lookup"><span data-stu-id="2a644-463">Registered Partnership</span></span> | <span data-ttu-id="2a644-464">Partenariat local</span><span class="sxs-lookup"><span data-stu-id="2a644-464">Domestic Partnership</span></span> |
| <span data-ttu-id="2a644-465">None</span><span class="sxs-lookup"><span data-stu-id="2a644-465">None</span></span>                   | <span data-ttu-id="2a644-466">None</span><span class="sxs-lookup"><span data-stu-id="2a644-466">None</span></span>                 |
| <span data-ttu-id="2a644-467">Concubinage</span><span class="sxs-lookup"><span data-stu-id="2a644-467">Cohabiting</span></span>             | <span data-ttu-id="2a644-468">Concubinage</span><span class="sxs-lookup"><span data-stu-id="2a644-468">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="2a644-469">Sexe</span><span class="sxs-lookup"><span data-stu-id="2a644-469">Gender</span></span>

<span data-ttu-id="2a644-470">Le sexe est mis en correspondance avec Dayforce et traduit, au besoin, dans les valeurs acceptées lors de l’intégration.</span><span class="sxs-lookup"><span data-stu-id="2a644-470">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="2a644-471">Le tableau suivant montre comment le sexe est mis en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="2a644-471">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="2a644-472">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="2a644-472">Human Resources</span></span>       | <span data-ttu-id="2a644-473">Dayforce</span><span class="sxs-lookup"><span data-stu-id="2a644-473">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="2a644-474">Masculin</span><span class="sxs-lookup"><span data-stu-id="2a644-474">Male</span></span>         | <span data-ttu-id="2a644-475">Masculin</span><span class="sxs-lookup"><span data-stu-id="2a644-475">Male</span></span>            |
| <span data-ttu-id="2a644-476">Féminin</span><span class="sxs-lookup"><span data-stu-id="2a644-476">Female</span></span>       | <span data-ttu-id="2a644-477">Féminin</span><span class="sxs-lookup"><span data-stu-id="2a644-477">Female</span></span>          |
| <span data-ttu-id="2a644-478">Non spécifique</span><span class="sxs-lookup"><span data-stu-id="2a644-478">Non-specific</span></span> | <span data-ttu-id="2a644-479">*Non pris en charge*</span><span class="sxs-lookup"><span data-stu-id="2a644-479">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="2a644-480">Codes de rémunérations</span><span class="sxs-lookup"><span data-stu-id="2a644-480">Earning codes</span></span>

<span data-ttu-id="2a644-481">Les codes de rémunérations identifient de manière unique chaque type de revenus que les collaborateurs reçoivent.</span><span class="sxs-lookup"><span data-stu-id="2a644-481">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="2a644-482">Les codes couvrent différents paramètres associés aux revenus, tels que des règles comptables, des lois fiscales, des conditions de génération d’états, et la capacité de montant brut.</span><span class="sxs-lookup"><span data-stu-id="2a644-482">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="2a644-483">Si une fréquence non prise en charge est utilisée, la fréquence **Chaque paie** est utilisée par défaut pour le calcul.</span><span class="sxs-lookup"><span data-stu-id="2a644-483">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="2a644-484">Fréquences prises en charge</span><span class="sxs-lookup"><span data-stu-id="2a644-484">Supported frequencies</span></span>

- <span data-ttu-id="2a644-485">Tous</span><span class="sxs-lookup"><span data-stu-id="2a644-485">All</span></span>
- <span data-ttu-id="2a644-486">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="2a644-486">EVERYPAY</span></span>
- <span data-ttu-id="2a644-487">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="2a644-487">EACHPAYPERIOD</span></span>
- <span data-ttu-id="2a644-488">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="2a644-488">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="2a644-489">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="2a644-489">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="2a644-490">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-490">1OFMTH</span></span>
- <span data-ttu-id="2a644-491">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-491">LASTOFMTH</span></span>
- <span data-ttu-id="2a644-492">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-492">2OFMTH</span></span>
- <span data-ttu-id="2a644-493">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-493">3OFMTH</span></span>
- <span data-ttu-id="2a644-494">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-494">4OFMTH</span></span>
- <span data-ttu-id="2a644-495">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-495">5OFMTH</span></span>
- <span data-ttu-id="2a644-496">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-496">1N2OFMTH</span></span>
- <span data-ttu-id="2a644-497">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-497">3N4OFMTH</span></span>
- <span data-ttu-id="2a644-498">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-498">1N3OFMTH</span></span>
- <span data-ttu-id="2a644-499">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-499">1N4OFMTH</span></span>
- <span data-ttu-id="2a644-500">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-500">2N3OFMTH</span></span>
- <span data-ttu-id="2a644-501">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-501">2N4OFMTH</span></span>
- <span data-ttu-id="2a644-502">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-502">1N2N3OFMTH</span></span>
- <span data-ttu-id="2a644-503">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-503">1N2N4OFMTH</span></span>
- <span data-ttu-id="2a644-504">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-504">1N3N4OFMTH</span></span>
- <span data-ttu-id="2a644-505">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-505">2N3N4OFMTH</span></span>
- <span data-ttu-id="2a644-506">1N2N3N4OFMTH – 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-506">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="2a644-507">2N3N4N5OFMth – 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="2a644-507">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="2a644-508">1OFQTR – 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="2a644-508">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="2a644-509">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="2a644-509">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="2a644-510">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="2a644-510">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="2a644-511">1OFYEAR – 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="2a644-511">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="2a644-512">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="2a644-512">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="2a644-513">NOVNDECOFYEAR – NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="2a644-513">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="2a644-514">Adresses</span><span class="sxs-lookup"><span data-stu-id="2a644-514">Addresses</span></span>

<span data-ttu-id="2a644-515">L’identification d’un pays ou d’une région, d’un état, et des codes département (municipalité) spécifiques nécessite des formats spécifiques que les fournisseurs Dayforce et dans le pays/la région peuvent identifier.</span><span class="sxs-lookup"><span data-stu-id="2a644-515">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="2a644-516">Bien que le format pour les villes soit flexible, chaque ville doit être associée à un état.</span><span class="sxs-lookup"><span data-stu-id="2a644-516">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="2a644-517">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="2a644-517">Human Resources</span></span>          | <span data-ttu-id="2a644-518">Dayforce</span><span class="sxs-lookup"><span data-stu-id="2a644-518">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="2a644-519">Pays/région</span><span class="sxs-lookup"><span data-stu-id="2a644-519">Country/Region</span></span>  | <span data-ttu-id="2a644-520">Code pays</span><span class="sxs-lookup"><span data-stu-id="2a644-520">Country Code</span></span>          |
| <span data-ttu-id="2a644-521">Code postal</span><span class="sxs-lookup"><span data-stu-id="2a644-521">Zip/Postal Code</span></span> | <span data-ttu-id="2a644-522">Code postal</span><span class="sxs-lookup"><span data-stu-id="2a644-522">Postal Code</span></span>           |
| <span data-ttu-id="2a644-523">État</span><span class="sxs-lookup"><span data-stu-id="2a644-523">State</span></span>           | <span data-ttu-id="2a644-524">Code région</span><span class="sxs-lookup"><span data-stu-id="2a644-524">State Code</span></span>            |
| <span data-ttu-id="2a644-525">Ville</span><span class="sxs-lookup"><span data-stu-id="2a644-525">City</span></span>            | <span data-ttu-id="2a644-526">Ville</span><span class="sxs-lookup"><span data-stu-id="2a644-526">City</span></span>                  |
| <span data-ttu-id="2a644-527">Commune</span><span class="sxs-lookup"><span data-stu-id="2a644-527">County</span></span>          | <span data-ttu-id="2a644-528">Département (municipalité)</span><span class="sxs-lookup"><span data-stu-id="2a644-528">County (Municipality)</span></span> |
| <span data-ttu-id="2a644-529">Rue</span><span class="sxs-lookup"><span data-stu-id="2a644-529">Street</span></span>          | <span data-ttu-id="2a644-530">Ligne d’adresse 1</span><span class="sxs-lookup"><span data-stu-id="2a644-530">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="2a644-531">Zones fiscales</span><span class="sxs-lookup"><span data-stu-id="2a644-531">Tax regions</span></span>

<span data-ttu-id="2a644-532">Les régions fiscales permettent de déterminer la taxe appropriée qui doit être appliquée lors de la génération des salaires.</span><span class="sxs-lookup"><span data-stu-id="2a644-532">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="2a644-533">Les régions fiscales sont mises en correspondance avec Dayforce comme adresses de lieu.</span><span class="sxs-lookup"><span data-stu-id="2a644-533">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="2a644-534">La région fiscale par défaut doit être associée au poste actif du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="2a644-534">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="2a644-535">Région fiscale (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-535">Tax region (required)</span></span>
- <span data-ttu-id="2a644-536">Pays/région (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-536">Country/Region (required)</span></span>
- <span data-ttu-id="2a644-537">État (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-537">State (required)</span></span>
- <span data-ttu-id="2a644-538">Commune</span><span class="sxs-lookup"><span data-stu-id="2a644-538">County</span></span> 
- <span data-ttu-id="2a644-539">Ville (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="2a644-539">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="2a644-540">Configurez vos données pour générer un salaire au Mexique</span><span class="sxs-lookup"><span data-stu-id="2a644-540">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="2a644-541">Si vous générez un salaire pour des employés au Mexique, les éléments suivants doivent être configurés :</span><span class="sxs-lookup"><span data-stu-id="2a644-541">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="2a644-542">Les départements sont obligatoires sur les postes.</span><span class="sxs-lookup"><span data-stu-id="2a644-542">Departments are required on positions.</span></span>
- <span data-ttu-id="2a644-543">Les centres de coût doivent être définis comme des dimensions financières et doivent être le premier élément de la chaîne de dimension financière par défaut.</span><span class="sxs-lookup"><span data-stu-id="2a644-543">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="2a644-544">Types de missions</span><span class="sxs-lookup"><span data-stu-id="2a644-544">Job types</span></span>

<span data-ttu-id="2a644-545">Les types de tâches sont utilisés pour regrouper les tâches similaires en catégories.</span><span class="sxs-lookup"><span data-stu-id="2a644-545">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="2a644-546">Les types de tâches sont nécessaires afin de traiter le salaire au Mexique.</span><span class="sxs-lookup"><span data-stu-id="2a644-546">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="2a644-547">Les exemples de types de tâches incluent le temps plein et le temps partiel, ou le salaire et le paiement à l’heure.</span><span class="sxs-lookup"><span data-stu-id="2a644-547">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="2a644-548">Les types de tâches sont mis en correspondance dans Dayforce comme types de paies qui indiquent si un employé est payé à l’heure ou salarié.</span><span class="sxs-lookup"><span data-stu-id="2a644-548">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="2a644-549">Les types de tâches et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="2a644-549">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="2a644-550">Type de mission</span><span class="sxs-lookup"><span data-stu-id="2a644-550">Job type</span></span>   | <span data-ttu-id="2a644-551">Description</span><span class="sxs-lookup"><span data-stu-id="2a644-551">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="2a644-552">Horaire</span><span class="sxs-lookup"><span data-stu-id="2a644-552">Hourly</span></span>     | <span data-ttu-id="2a644-553">Horaire MX</span><span class="sxs-lookup"><span data-stu-id="2a644-553">MX Hourly</span></span>   |
| <span data-ttu-id="2a644-554">Salarié</span><span class="sxs-lookup"><span data-stu-id="2a644-554">Salaried</span></span>   | <span data-ttu-id="2a644-555">Salarié MX</span><span class="sxs-lookup"><span data-stu-id="2a644-555">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="2a644-556">Types de poste</span><span class="sxs-lookup"><span data-stu-id="2a644-556">Position types</span></span> 

<span data-ttu-id="2a644-557">Vous utilisez les types de postes pour indiquer si le poste est à temps plein, à temps partiel, ou autre chose.</span><span class="sxs-lookup"><span data-stu-id="2a644-557">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="2a644-558">Les types de postes sont mis en correspondance dans Dayforce comme classes de paiements qui indiquent si un employé est à temps plein ou à temps partiel.</span><span class="sxs-lookup"><span data-stu-id="2a644-558">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="2a644-559">Les types de postes et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="2a644-559">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="2a644-560">Type de poste</span><span class="sxs-lookup"><span data-stu-id="2a644-560">Position type</span></span>   | <span data-ttu-id="2a644-561">Description</span><span class="sxs-lookup"><span data-stu-id="2a644-561">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="2a644-562">Temps plein</span><span class="sxs-lookup"><span data-stu-id="2a644-562">Full-time</span></span>       | <span data-ttu-id="2a644-563">Employé à temps plein</span><span class="sxs-lookup"><span data-stu-id="2a644-563">Full time employee</span></span> |
| <span data-ttu-id="2a644-564">Temps partiel</span><span class="sxs-lookup"><span data-stu-id="2a644-564">Part-time</span></span>       | <span data-ttu-id="2a644-565">Employé à temps partiel</span><span class="sxs-lookup"><span data-stu-id="2a644-565">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="2a644-566">Codes motif</span><span class="sxs-lookup"><span data-stu-id="2a644-566">Reason codes</span></span>

<span data-ttu-id="2a644-567">Les codes motif fournissent des informations sur le statut d’un employé.</span><span class="sxs-lookup"><span data-stu-id="2a644-567">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="2a644-568">Les codes motif sont mis en correspondance avec Dayforce comme motifs du statut, indiquant le motif des modifications apportées au poste ou au statut d’emploi d’un employé.</span><span class="sxs-lookup"><span data-stu-id="2a644-568">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="2a644-569">Les codes motif et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="2a644-569">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="2a644-570">Code motif</span><span class="sxs-lookup"><span data-stu-id="2a644-570">Reason code</span></span>            | <span data-ttu-id="2a644-571">Description</span><span class="sxs-lookup"><span data-stu-id="2a644-571">Description</span></span>                    | <span data-ttu-id="2a644-572">Scénarios applicables</span><span class="sxs-lookup"><span data-stu-id="2a644-572">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="2a644-573">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="2a644-573">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="2a644-574">Départ avant le premier salaire</span><span class="sxs-lookup"><span data-stu-id="2a644-574">Departure before first payroll</span></span> | <span data-ttu-id="2a644-575">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="2a644-575">Terminate worker</span></span>     |
| <span data-ttu-id="2a644-576">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="2a644-576">RESIGNATION</span></span>            | <span data-ttu-id="2a644-577">Démission</span><span class="sxs-lookup"><span data-stu-id="2a644-577">Resignation</span></span>                    | <span data-ttu-id="2a644-578">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="2a644-578">Terminate worker</span></span>     |
| <span data-ttu-id="2a644-579">PENSION</span><span class="sxs-lookup"><span data-stu-id="2a644-579">PENSION</span></span>                | <span data-ttu-id="2a644-580">Retraite</span><span class="sxs-lookup"><span data-stu-id="2a644-580">Pension</span></span>                        | <span data-ttu-id="2a644-581">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="2a644-581">Terminate worker</span></span>     |
| <span data-ttu-id="2a644-582">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="2a644-582">TERMINATION</span></span>            | <span data-ttu-id="2a644-583">Fin du contrat</span><span class="sxs-lookup"><span data-stu-id="2a644-583">Termination</span></span>                    | <span data-ttu-id="2a644-584">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="2a644-584">Terminate worker</span></span>     |
| <span data-ttu-id="2a644-585">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="2a644-585">RETIREMENT</span></span>             | <span data-ttu-id="2a644-586">Retraite</span><span class="sxs-lookup"><span data-stu-id="2a644-586">Retirement</span></span>                     | <span data-ttu-id="2a644-587">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="2a644-587">Terminate worker</span></span>     |
| <span data-ttu-id="2a644-588">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="2a644-588">ABSENTEE</span></span>               | <span data-ttu-id="2a644-589">Absent</span><span class="sxs-lookup"><span data-stu-id="2a644-589">Absentee</span></span>                       | <span data-ttu-id="2a644-590">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="2a644-590">Terminate worker</span></span>     |
| <span data-ttu-id="2a644-591">OTHER</span><span class="sxs-lookup"><span data-stu-id="2a644-591">OTHER</span></span>                  | <span data-ttu-id="2a644-592">Autres motifs</span><span class="sxs-lookup"><span data-stu-id="2a644-592">Other Reasons</span></span>                  | <span data-ttu-id="2a644-593">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="2a644-593">Terminate worker</span></span>     |
| <span data-ttu-id="2a644-594">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="2a644-594">CLOSURE</span></span>                | <span data-ttu-id="2a644-595">Fermeture de l’entreprise</span><span class="sxs-lookup"><span data-stu-id="2a644-595">Business Closure</span></span>               | <span data-ttu-id="2a644-596">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="2a644-596">Terminate worker</span></span>     |
| <span data-ttu-id="2a644-597">DEATH</span><span class="sxs-lookup"><span data-stu-id="2a644-597">DEATH</span></span>                  | <span data-ttu-id="2a644-598">Décès</span><span class="sxs-lookup"><span data-stu-id="2a644-598">Death</span></span>                          | <span data-ttu-id="2a644-599">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="2a644-599">Terminate worker</span></span>     |
| <span data-ttu-id="2a644-600">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="2a644-600">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="2a644-601">Congé</span><span class="sxs-lookup"><span data-stu-id="2a644-601">Leave of Absence</span></span>               | <span data-ttu-id="2a644-602">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="2a644-602">Terminate worker</span></span>     |
| <span data-ttu-id="2a644-603">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="2a644-603">CONTRACTEND</span></span>            | <span data-ttu-id="2a644-604">Fin du contrat</span><span class="sxs-lookup"><span data-stu-id="2a644-604">End of Contract</span></span>                | <span data-ttu-id="2a644-605">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="2a644-605">Terminate worker</span></span>     |
| <span data-ttu-id="2a644-606">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="2a644-606">SALARYCHANGE</span></span>           | <span data-ttu-id="2a644-607">Modification du salaire</span><span class="sxs-lookup"><span data-stu-id="2a644-607">Change of Salary</span></span>               | <span data-ttu-id="2a644-608">Rémunération</span><span class="sxs-lookup"><span data-stu-id="2a644-608">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="2a644-609">Conditions d’emploi</span><span class="sxs-lookup"><span data-stu-id="2a644-609">Terms of employment</span></span>

<span data-ttu-id="2a644-610">Les conditions d’emploi sont utilisées pour créer des catégories de conditions d’emploi.</span><span class="sxs-lookup"><span data-stu-id="2a644-610">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="2a644-611">Les conditions sont mises en correspondance avec Dayforce en tant que valeurs d’indicateur d’emploi.</span><span class="sxs-lookup"><span data-stu-id="2a644-611">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="2a644-612">Les conditions d’emploi et descriptions suivantes sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="2a644-612">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="2a644-613">Conditions d’emploi</span><span class="sxs-lookup"><span data-stu-id="2a644-613">Terms of employment</span></span>   | <span data-ttu-id="2a644-614">Description</span><span class="sxs-lookup"><span data-stu-id="2a644-614">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="2a644-615">Régulier</span><span class="sxs-lookup"><span data-stu-id="2a644-615">Regular</span></span>               | <span data-ttu-id="2a644-616">Régulier</span><span class="sxs-lookup"><span data-stu-id="2a644-616">Regular</span></span>     |
| <span data-ttu-id="2a644-617">Direct</span><span class="sxs-lookup"><span data-stu-id="2a644-617">Direct</span></span>                | <span data-ttu-id="2a644-618">Direct</span><span class="sxs-lookup"><span data-stu-id="2a644-618">Direct</span></span>      |
| <span data-ttu-id="2a644-619">Stage</span><span class="sxs-lookup"><span data-stu-id="2a644-619">Internship</span></span>            | <span data-ttu-id="2a644-620">Stage</span><span class="sxs-lookup"><span data-stu-id="2a644-620">Internship</span></span>  |
| <span data-ttu-id="2a644-621">Permanent</span><span class="sxs-lookup"><span data-stu-id="2a644-621">Permanent</span></span>             | <span data-ttu-id="2a644-622">Permanent</span><span class="sxs-lookup"><span data-stu-id="2a644-622">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="2a644-623">Situation de famille</span><span class="sxs-lookup"><span data-stu-id="2a644-623">Marital status</span></span>

<span data-ttu-id="2a644-624">Les valeurs de situation de famille sont mises en correspondance avec Dayforce et traduite, au besoin, dans les valeurs acceptées lors de l’intégration.</span><span class="sxs-lookup"><span data-stu-id="2a644-624">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="2a644-625">Le tableau suivant montre comment les valeurs de situation de famille sont mises en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="2a644-625">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="2a644-626">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="2a644-626">Human Resources</span></span>                 | <span data-ttu-id="2a644-627">Dayforce</span><span class="sxs-lookup"><span data-stu-id="2a644-627">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="2a644-628">Marié</span><span class="sxs-lookup"><span data-stu-id="2a644-628">Married</span></span>                | <span data-ttu-id="2a644-629">Marié</span><span class="sxs-lookup"><span data-stu-id="2a644-629">Married</span></span>                   |
| <span data-ttu-id="2a644-630">Unique</span><span class="sxs-lookup"><span data-stu-id="2a644-630">Single</span></span>                 | <span data-ttu-id="2a644-631">Unique</span><span class="sxs-lookup"><span data-stu-id="2a644-631">Single</span></span>                    |
| <span data-ttu-id="2a644-632">Veuf</span><span class="sxs-lookup"><span data-stu-id="2a644-632">Widowed</span></span>                | <span data-ttu-id="2a644-633">Veuf</span><span class="sxs-lookup"><span data-stu-id="2a644-633">Widowed</span></span>                   |
| <span data-ttu-id="2a644-634">Divorcé</span><span class="sxs-lookup"><span data-stu-id="2a644-634">Divorced</span></span>               | <span data-ttu-id="2a644-635">Divorcé</span><span class="sxs-lookup"><span data-stu-id="2a644-635">Divorced</span></span>                  |
| <span data-ttu-id="2a644-636">Partenariat enregistré</span><span class="sxs-lookup"><span data-stu-id="2a644-636">Registered Partnership</span></span> | <span data-ttu-id="2a644-637">Partenariat local</span><span class="sxs-lookup"><span data-stu-id="2a644-637">Domestic Partnership</span></span>      |
| <span data-ttu-id="2a644-638">None</span><span class="sxs-lookup"><span data-stu-id="2a644-638">None</span></span>                   | <span data-ttu-id="2a644-639">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="2a644-639">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="2a644-640">Concubinage</span><span class="sxs-lookup"><span data-stu-id="2a644-640">Cohabiting</span></span>             | <span data-ttu-id="2a644-641">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="2a644-641">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="2a644-642">Sexe</span><span class="sxs-lookup"><span data-stu-id="2a644-642">Gender</span></span>

<span data-ttu-id="2a644-643">Le sexe est mis en correspondance avec Dayforce et traduit, au besoin, dans les valeurs acceptées lors de l’intégration.</span><span class="sxs-lookup"><span data-stu-id="2a644-643">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="2a644-644">Le tableau suivant montre comment le sexe est mis en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="2a644-644">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="2a644-645">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="2a644-645">Human Resources</span></span>       | <span data-ttu-id="2a644-646">Dayforce</span><span class="sxs-lookup"><span data-stu-id="2a644-646">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="2a644-647">Masculin</span><span class="sxs-lookup"><span data-stu-id="2a644-647">Male</span></span>         | <span data-ttu-id="2a644-648">Masculin</span><span class="sxs-lookup"><span data-stu-id="2a644-648">Male</span></span>                      |
| <span data-ttu-id="2a644-649">Féminin</span><span class="sxs-lookup"><span data-stu-id="2a644-649">Female</span></span>       | <span data-ttu-id="2a644-650">Féminin</span><span class="sxs-lookup"><span data-stu-id="2a644-650">Female</span></span>                    |
| <span data-ttu-id="2a644-651">Non spécifique</span><span class="sxs-lookup"><span data-stu-id="2a644-651">Non-specific</span></span> | <span data-ttu-id="2a644-652">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="2a644-652">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="2a644-653">Mode de paiement</span><span class="sxs-lookup"><span data-stu-id="2a644-653">Payment method</span></span>

<span data-ttu-id="2a644-654">Les modes de paiement fournissent à l’employé et à la société une manière de décrire la façon dont les employés sont payés.</span><span class="sxs-lookup"><span data-stu-id="2a644-654">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="2a644-655">Les modes de paiement sont mis en correspondance avec Dayforce et traduit, au besoin, dans les valeurs acceptées lors de l’intégration.</span><span class="sxs-lookup"><span data-stu-id="2a644-655">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="2a644-656">Le tableau suivant montre comment les modes de paiement sont mis en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="2a644-656">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="2a644-657">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="2a644-657">Human Resources</span></span>             | <span data-ttu-id="2a644-658">Dayforce</span><span class="sxs-lookup"><span data-stu-id="2a644-658">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="2a644-659">Argent comptant</span><span class="sxs-lookup"><span data-stu-id="2a644-659">Cash</span></span>               | <span data-ttu-id="2a644-660">Argent comptant</span><span class="sxs-lookup"><span data-stu-id="2a644-660">Cash</span></span>                      |
| <span data-ttu-id="2a644-661">Paiement électronique</span><span class="sxs-lookup"><span data-stu-id="2a644-661">Electronic Payment</span></span> | <span data-ttu-id="2a644-662">Transférer</span><span class="sxs-lookup"><span data-stu-id="2a644-662">Transfer</span></span>                  |
| <span data-ttu-id="2a644-663">Vérification</span><span class="sxs-lookup"><span data-stu-id="2a644-663">Check</span></span>              | <span data-ttu-id="2a644-664">Chèque</span><span class="sxs-lookup"><span data-stu-id="2a644-664">Cheque</span></span>                    |
| <span data-ttu-id="2a644-665">Traites bancaires</span><span class="sxs-lookup"><span data-stu-id="2a644-665">Bank Draft</span></span>         | <span data-ttu-id="2a644-666">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="2a644-666">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="2a644-667">Autre/s</span><span class="sxs-lookup"><span data-stu-id="2a644-667">Other</span></span>              | <span data-ttu-id="2a644-668">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="2a644-668">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="2a644-669">Type de compte bancaire</span><span class="sxs-lookup"><span data-stu-id="2a644-669">Bank account type</span></span>

<span data-ttu-id="2a644-670">Les types de comptes bancaires sont utilisés pour les paiements électroniques aux employés.</span><span class="sxs-lookup"><span data-stu-id="2a644-670">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="2a644-671">Les types de comptes bancaires sont mis en correspondance avec Dayforce tant qu’informations de compte de transfert.</span><span class="sxs-lookup"><span data-stu-id="2a644-671">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="2a644-672">Les types de comptes bancaires sont traduits, au besoin, dans des valeurs acceptées lors de l’intégration.</span><span class="sxs-lookup"><span data-stu-id="2a644-672">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="2a644-673">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="2a644-673">Human Resources</span></span>            | <span data-ttu-id="2a644-674">Dayforce</span><span class="sxs-lookup"><span data-stu-id="2a644-674">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="2a644-675">Compte courant</span><span class="sxs-lookup"><span data-stu-id="2a644-675">Checking Account</span></span>  | <span data-ttu-id="2a644-676">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="2a644-676">CheckingAccount</span></span>           |
| <span data-ttu-id="2a644-677">Compte de paie</span><span class="sxs-lookup"><span data-stu-id="2a644-677">Payroll Account</span></span>   | <span data-ttu-id="2a644-678">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="2a644-678">PayrollAccount</span></span>            |
| <span data-ttu-id="2a644-679">Compte d’épargne</span><span class="sxs-lookup"><span data-stu-id="2a644-679">Savings Account</span></span>   | <span data-ttu-id="2a644-680">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="2a644-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="2a644-681">Compte BankGirot</span><span class="sxs-lookup"><span data-stu-id="2a644-681">BankGirot account</span></span> | <span data-ttu-id="2a644-682">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="2a644-682">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="2a644-683">Compte PlusGirot</span><span class="sxs-lookup"><span data-stu-id="2a644-683">PlusGirot account</span></span> | <span data-ttu-id="2a644-684">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="2a644-684">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="2a644-685">Codes de rémunérations</span><span class="sxs-lookup"><span data-stu-id="2a644-685">Earning codes</span></span>

<span data-ttu-id="2a644-686">Les codes de rémunérations identifient de manière unique chaque type de revenus que les collaborateurs reçoivent.</span><span class="sxs-lookup"><span data-stu-id="2a644-686">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="2a644-687">Les codes couvrent différents paramètres associés aux revenus, tels que des règles comptables, des lois fiscales, des conditions de génération d’états, et la capacité de montant brut.</span><span class="sxs-lookup"><span data-stu-id="2a644-687">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="2a644-688">Si une fréquence non prise en charge est utilisée, la fréquence **Chaque paie** est utilisée par défaut pour le calcul.</span><span class="sxs-lookup"><span data-stu-id="2a644-688">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="2a644-689">Fréquences prises en charge</span><span class="sxs-lookup"><span data-stu-id="2a644-689">Supported frequencies</span></span>

- <span data-ttu-id="2a644-690">Tous</span><span class="sxs-lookup"><span data-stu-id="2a644-690">All</span></span>
- <span data-ttu-id="2a644-691">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="2a644-691">EVERYPAY</span></span>
- <span data-ttu-id="2a644-692">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="2a644-692">EACHPAYPERIOD</span></span>
- <span data-ttu-id="2a644-693">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="2a644-693">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="2a644-694">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="2a644-694">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="2a644-695">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-695">1OFMTH</span></span>
- <span data-ttu-id="2a644-696">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-696">LASTOFMTH</span></span>
- <span data-ttu-id="2a644-697">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-697">2OFMTH</span></span>
- <span data-ttu-id="2a644-698">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-698">3OFMTH</span></span>
- <span data-ttu-id="2a644-699">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-699">4OFMTH</span></span>
- <span data-ttu-id="2a644-700">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-700">5OFMTH</span></span>
- <span data-ttu-id="2a644-701">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-701">1N2OFMTH</span></span>
- <span data-ttu-id="2a644-702">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-702">3N4OFMTH</span></span>
- <span data-ttu-id="2a644-703">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-703">1N3OFMTH</span></span>
- <span data-ttu-id="2a644-704">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-704">1N4OFMTH</span></span>
- <span data-ttu-id="2a644-705">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-705">2N3OFMTH</span></span>
- <span data-ttu-id="2a644-706">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-706">2N4OFMTH</span></span>
- <span data-ttu-id="2a644-707">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-707">1N2N3OFMTH</span></span>
- <span data-ttu-id="2a644-708">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-708">1N2N4OFMTH</span></span>
- <span data-ttu-id="2a644-709">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-709">1N3N4OFMTH</span></span>
- <span data-ttu-id="2a644-710">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-710">2N3N4OFMTH</span></span>
- <span data-ttu-id="2a644-711">1N2N3N4OFMTH – 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="2a644-711">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="2a644-712">2N3N4N5OFMth – 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="2a644-712">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="2a644-713">1OFQTR – 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="2a644-713">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="2a644-714">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="2a644-714">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="2a644-715">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="2a644-715">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="2a644-716">1OFYEAR – 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="2a644-716">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="2a644-717">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="2a644-717">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="2a644-718">NOVNDECOFYEAR – NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="2a644-718">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="2a644-719">Adresses</span><span class="sxs-lookup"><span data-stu-id="2a644-719">Addresses</span></span>

<span data-ttu-id="2a644-720">L’identification d’un pays ou d’une région, d’un état, et des codes département (municipalité) spécifiques nécessite des formats spécifiques que les fournisseurs Dayforce et dans le pays/la région peuvent identifier.</span><span class="sxs-lookup"><span data-stu-id="2a644-720">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="2a644-721">Bien que le format pour les villes soit flexible, chaque ville doit être associée à un état.</span><span class="sxs-lookup"><span data-stu-id="2a644-721">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="2a644-722">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="2a644-722">Human Resources</span></span>              | <span data-ttu-id="2a644-723">Dayforce</span><span class="sxs-lookup"><span data-stu-id="2a644-723">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="2a644-724">Pays/région</span><span class="sxs-lookup"><span data-stu-id="2a644-724">Country/Region</span></span>      | <span data-ttu-id="2a644-725">Code pays</span><span class="sxs-lookup"><span data-stu-id="2a644-725">Country Code</span></span>          |
| <span data-ttu-id="2a644-726">Code postal</span><span class="sxs-lookup"><span data-stu-id="2a644-726">Zip/Postal Code</span></span>     | <span data-ttu-id="2a644-727">Code postal</span><span class="sxs-lookup"><span data-stu-id="2a644-727">Postal Code</span></span>           |
| <span data-ttu-id="2a644-728">État</span><span class="sxs-lookup"><span data-stu-id="2a644-728">State</span></span>               | <span data-ttu-id="2a644-729">Code région</span><span class="sxs-lookup"><span data-stu-id="2a644-729">State Code</span></span>            |
| <span data-ttu-id="2a644-730">Ville</span><span class="sxs-lookup"><span data-stu-id="2a644-730">City</span></span>                | <span data-ttu-id="2a644-731">Ville</span><span class="sxs-lookup"><span data-stu-id="2a644-731">City</span></span>                  |
| <span data-ttu-id="2a644-732">Commune</span><span class="sxs-lookup"><span data-stu-id="2a644-732">County</span></span>              | <span data-ttu-id="2a644-733">Département (municipalité)</span><span class="sxs-lookup"><span data-stu-id="2a644-733">County (Municipality)</span></span> |
| <span data-ttu-id="2a644-734">Rue</span><span class="sxs-lookup"><span data-stu-id="2a644-734">Street</span></span>              | <span data-ttu-id="2a644-735">Ligne d’adresse 1</span><span class="sxs-lookup"><span data-stu-id="2a644-735">Address Line 1</span></span>        |
| <span data-ttu-id="2a644-736">Numéro de la rue</span><span class="sxs-lookup"><span data-stu-id="2a644-736">Street Number</span></span>       | <span data-ttu-id="2a644-737">Ligne d’adresse 2</span><span class="sxs-lookup"><span data-stu-id="2a644-737">Address Line 2</span></span>        |
| <span data-ttu-id="2a644-738">Info complémentaire sur le bâtiment</span><span class="sxs-lookup"><span data-stu-id="2a644-738">Building Complement</span></span> | <span data-ttu-id="2a644-739">Ligne d’adresse 5</span><span class="sxs-lookup"><span data-stu-id="2a644-739">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="2a644-740">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="2a644-740">Passport number</span></span>

<span data-ttu-id="2a644-741">Les employés peuvent déclarer des informations de passeport.</span><span class="sxs-lookup"><span data-stu-id="2a644-741">Employees can declare passport information.</span></span> <span data-ttu-id="2a644-742">Ces informations sont de type d’identification **Passeport** et sont intégrées à Dayforce dans le cadre des informations spécifique au Mexique d’un employé.</span><span class="sxs-lookup"><span data-stu-id="2a644-742">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="2a644-743">Type d’identification = « Passeport »</span><span class="sxs-lookup"><span data-stu-id="2a644-743">Identification Type = "Passport"</span></span>
- <span data-ttu-id="2a644-744">Date d’émission</span><span class="sxs-lookup"><span data-stu-id="2a644-744">Issued Date</span></span>
- <span data-ttu-id="2a644-745">Date d’expiration</span><span class="sxs-lookup"><span data-stu-id="2a644-745">Expiration Date</span></span>

<span data-ttu-id="2a644-746">Les employés peuvent déclarer plusieurs numéros d’identification de type d’identification **Passeport**.</span><span class="sxs-lookup"><span data-stu-id="2a644-746">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="2a644-747">Toutefois, seule la saisie de passeport actif actuel est intégrée à Dayforce.</span><span class="sxs-lookup"><span data-stu-id="2a644-747">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="2a644-748">Si toutes les entrées de passeport sont arrivées à expiration, le passeport émis le plus récemment est intégré dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="2a644-748">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]