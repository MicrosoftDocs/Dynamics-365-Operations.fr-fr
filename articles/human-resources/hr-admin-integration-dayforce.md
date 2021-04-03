---
title: Configuration de l’intégration avec Dayforce
description: L’intégration entre Microsoft Dynamics 365 Human Resources et Ceridian Dayforce repose sur plusieurs étapes de configuration décrites dans cet article. Vous devez configurer l’intégration dans Human Resources et Dayforce avant de pouvoir traiter un cycle de paie.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 2d5f65672960716bee3f58c98ccce249fdbf8697
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467143"
---
# <a name="configure-integration-with-dayforce"></a><span data-ttu-id="8d322-104">Configuration de l’intégration avec Dayforce</span><span class="sxs-lookup"><span data-stu-id="8d322-104">Configure integration with Dayforce</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8d322-105">L’intégration entre Microsoft Dynamics 365 Human Resources et Ceridian Dayforce repose sur plusieurs étapes de configuration décrites dans cet article.</span><span class="sxs-lookup"><span data-stu-id="8d322-105">The integration between Microsoft Dynamics 365 Human Resources and Ceridian Dayforce relies on several configuration steps that are described in this article.</span></span> <span data-ttu-id="8d322-106">Vous devez configurer l’intégration dans Human Resources et Dayforce avant de pouvoir traiter un cycle de paie.</span><span class="sxs-lookup"><span data-stu-id="8d322-106">You must configure the integration in both Human Resources and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="8d322-107">Lorsque vous utilisez un service comme Dayforce pour compléter des cycles de paie, vous devez activer l’intégration dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8d322-107">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Human Resources.</span></span> <span data-ttu-id="8d322-108">L’intégration nécessite des données spécifiques de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8d322-108">The integration requires specific data from Human Resources.</span></span> <span data-ttu-id="8d322-109">Par conséquent, vous devez vérifier que les données mises en correspondance avec Dayforce sont configurées dans Human Resources d’une manière prenant en charge l’intégration.</span><span class="sxs-lookup"><span data-stu-id="8d322-109">Therefore, you must verify that data that is mapped to Dayforce is configured in Human Resources in a manner that supports the integration.</span></span> <span data-ttu-id="8d322-110">L’intégration utilise les larges catégories de données suivantes :</span><span class="sxs-lookup"><span data-stu-id="8d322-110">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="8d322-111">Données de ressources humaines</span><span class="sxs-lookup"><span data-stu-id="8d322-111">Human resources data</span></span>
- <span data-ttu-id="8d322-112">Données de rémunération</span><span class="sxs-lookup"><span data-stu-id="8d322-112">Compensation data</span></span>
- <span data-ttu-id="8d322-113">Données salariales, telles que des cycles de paie, des périodes de rémunération, et des codes de rémunération</span><span class="sxs-lookup"><span data-stu-id="8d322-113">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="8d322-114">Données sur les collaborateurs</span><span class="sxs-lookup"><span data-stu-id="8d322-114">Worker data</span></span>

<span data-ttu-id="8d322-115">Cet article décrit la procédure à suivre pour activer l’intégration.</span><span class="sxs-lookup"><span data-stu-id="8d322-115">This article describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="8d322-116">Elle décrit également les types de données et les détails de configuration que l’intégration nécessite.</span><span class="sxs-lookup"><span data-stu-id="8d322-116">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="8d322-117">Activer l’intégration</span><span class="sxs-lookup"><span data-stu-id="8d322-117">Enable the integration</span></span>

<span data-ttu-id="8d322-118">Dans Human Resources, vous devez activer l’intégration et entrer des informations de configuration pour vous connecter Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8d322-118">In Human Resources, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="8d322-119">Si vous souhaitez que l’écriture comptable produite soit importée dans Microsoft Dynamics 365 Finance, vous devez également configurer un compte de stockage Microsoft Azure et entrer la chaîne de connexion de stockage Azure dans Finance.</span><span class="sxs-lookup"><span data-stu-id="8d322-119">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="8d322-120">Pour l’activer l’intégration dans Human Resources, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="8d322-120">To turn on the integration in Human Resources, follow these steps.</span></span>

1. <span data-ttu-id="8d322-121">Sur la page **Administration du système**, sélectionnez **Configuration de l’intégration**.</span><span class="sxs-lookup"><span data-stu-id="8d322-121">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="8d322-122">Entrez le point de terminaison FTP (File Transfer Protocol) sécurisé et le chemin d’accès de dossier FTP sécurisé.</span><span class="sxs-lookup"><span data-stu-id="8d322-122">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="8d322-123">Entrez le nom d’utilisateur et le mot de passe de l’utilisateur qui accèdera au point de terminaison FTP et au chemin d’accès du dossier sécurisés.</span><span class="sxs-lookup"><span data-stu-id="8d322-123">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="8d322-124">Testez la connexion, au besoin, puis définissez l’option **Activation de l’intégration de la paie** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="8d322-124">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="8d322-125">Lorsque l’intégration est activée, le package et les fichiers d’exportation de données sont créés, et la fréquence est définie.</span><span class="sxs-lookup"><span data-stu-id="8d322-125">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="8d322-126">Vous pouvez modifier la fréquence selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="8d322-126">You can change this frequency as you require.</span></span>

<span data-ttu-id="8d322-127">Pour plus d’informations sur les comptes de stockage Azure et les chaînes de connexion de stockage Azure, consultez les articles Azure suivants :</span><span class="sxs-lookup"><span data-stu-id="8d322-127">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure articles:</span></span>

- [<span data-ttu-id="8d322-128">À propos des comptes de stockage Azure</span><span class="sxs-lookup"><span data-stu-id="8d322-128">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="8d322-129">Configurer les chaînes de connexion de stockage Azure</span><span class="sxs-lookup"><span data-stu-id="8d322-129">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="8d322-130">Détails techniques lorsque l’intégration de la paie est activée</span><span class="sxs-lookup"><span data-stu-id="8d322-130">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="8d322-131">Activer l’intégration de la paie a deux principaux effets :</span><span class="sxs-lookup"><span data-stu-id="8d322-131">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="8d322-132">Un projet d’exportation de données nommé « Exportation de l’intégration de la paie » est créé.</span><span class="sxs-lookup"><span data-stu-id="8d322-132">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="8d322-133">Ce projet contient les entités et les champs nécessaires pour l’intégration de la paie.</span><span class="sxs-lookup"><span data-stu-id="8d322-133">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="8d322-134">Pour examiner le projet, accédez à **Administration système**, sélectionnez la vignette **Gestion des données**, puis ouvrez le projet à partir de la liste de projets.</span><span class="sxs-lookup"><span data-stu-id="8d322-134">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="8d322-135">Ce traitement par lots exécute le projet d’exportation de données, chiffre le package de données obtenues, et transfère le fichier de package de données au point de terminaison SFTP configuré dans l’écran **Configuration de l’intégration**.</span><span class="sxs-lookup"><span data-stu-id="8d322-135">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="8d322-136">Le package de données transféré au point de terminaison SFTP est chiffré à l’aide d’une clé unique dans le module.</span><span class="sxs-lookup"><span data-stu-id="8d322-136">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="8d322-137">Cette clé est dans un coffre Azure Key Vault qui n’est accessible que par Ceridian.</span><span class="sxs-lookup"><span data-stu-id="8d322-137">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="8d322-138">Il est impossible de déchiffrer et examiner le contenu du package de données.</span><span class="sxs-lookup"><span data-stu-id="8d322-138">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="8d322-139">Si vous devez examiner le contenu du package de données, vous devez exporter le projet de données « Exportation de l’intégration de la paie » manuellement, le télécharger, puis l’ouvrir.</span><span class="sxs-lookup"><span data-stu-id="8d322-139">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="8d322-140">L’exportation manuelle n’appliquera pas de chiffrement ou de transfert au package.</span><span class="sxs-lookup"><span data-stu-id="8d322-140">Manual export will not apply encryption or transfer the package.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="8d322-141">Configurer vos données</span><span class="sxs-lookup"><span data-stu-id="8d322-141">Configure your data</span></span> 

<span data-ttu-id="8d322-142">Pour traiter les paies, vous devez configurer les données des ressources humaines dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8d322-142">To process payroll, you must configure human resource data in Human Resources.</span></span> <span data-ttu-id="8d322-143">Vous devez configurer les données organisationnelles, telles que les tâches et les postes, ainsi que les avantages et les informations de rémunération.</span><span class="sxs-lookup"><span data-stu-id="8d322-143">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="8d322-144">Ces informations fournissent des informations sur l’emploi, le salaire et les déductions nécessaires pour générer le salaire de l’employé.</span><span class="sxs-lookup"><span data-stu-id="8d322-144">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="8d322-145">Données des ressources humaines</span><span class="sxs-lookup"><span data-stu-id="8d322-145">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="8d322-146">Avantages</span><span class="sxs-lookup"><span data-stu-id="8d322-146">Benefits</span></span> 

<span data-ttu-id="8d322-147">Les ressources humaines proposent des outils de paramétrage et de mise à jour des avantages, des déductions et des plans de compensation des collaborateurs qu’une organisation offre ou gère pour ses collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="8d322-147">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="8d322-148">Lorsque vous créez des avantages, n’oubliez pas les données et les configurations suivantes utilisées dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8d322-148">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="8d322-149">Plans d’avantages</span><span class="sxs-lookup"><span data-stu-id="8d322-149">Benefit plans</span></span>

- <span data-ttu-id="8d322-150">Plan (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-150">Plan (required)</span></span>
- <span data-ttu-id="8d322-151">Type (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-151">Type (required)</span></span>
- <span data-ttu-id="8d322-152">Impact sur la paie (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-152">Payroll impact (required)</span></span>
- <span data-ttu-id="8d322-153">Recouvrer les arriérés</span><span class="sxs-lookup"><span data-stu-id="8d322-153">Recover arrears</span></span>
- <span data-ttu-id="8d322-154">Méthode de déduction</span><span class="sxs-lookup"><span data-stu-id="8d322-154">Deduction method</span></span>
- <span data-ttu-id="8d322-155">Priorité de la déduction</span><span class="sxs-lookup"><span data-stu-id="8d322-155">Deduction priority</span></span>
- <span data-ttu-id="8d322-156">Période limite</span><span class="sxs-lookup"><span data-stu-id="8d322-156">Limit period</span></span>
- <span data-ttu-id="8d322-157">Montant limite</span><span class="sxs-lookup"><span data-stu-id="8d322-157">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="8d322-158">Avantages</span><span class="sxs-lookup"><span data-stu-id="8d322-158">Benefits</span></span>

- <span data-ttu-id="8d322-159">Plan (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-159">Plan (required)</span></span>
- <span data-ttu-id="8d322-160">Type (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-160">Type (required)</span></span>
- <span data-ttu-id="8d322-161">Option (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-161">Option (required)</span></span>
- <span data-ttu-id="8d322-162">ID avantage (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-162">Benefit ID (required)</span></span>
- <span data-ttu-id="8d322-163">Fréquence</span><span class="sxs-lookup"><span data-stu-id="8d322-163">Frequency</span></span>
- <span data-ttu-id="8d322-164">Base</span><span class="sxs-lookup"><span data-stu-id="8d322-164">Basis</span></span>
- <span data-ttu-id="8d322-165">Montant ou taux</span><span class="sxs-lookup"><span data-stu-id="8d322-165">Amount or rate</span></span>
- <span data-ttu-id="8d322-166">Code de rémunération</span><span class="sxs-lookup"><span data-stu-id="8d322-166">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="8d322-167">Fréquences prises en charge</span><span class="sxs-lookup"><span data-stu-id="8d322-167">Supported frequencies</span></span> 

- <span data-ttu-id="8d322-168">Hebdomadairement</span><span class="sxs-lookup"><span data-stu-id="8d322-168">Weekly</span></span>
- <span data-ttu-id="8d322-169">Bimensuelle</span><span class="sxs-lookup"><span data-stu-id="8d322-169">Bi-weekly</span></span>
- <span data-ttu-id="8d322-170">Bimensuel</span><span class="sxs-lookup"><span data-stu-id="8d322-170">Semi-monthly</span></span>
- <span data-ttu-id="8d322-171">Mensuellement</span><span class="sxs-lookup"><span data-stu-id="8d322-171">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="8d322-172">Bases pris en charge</span><span class="sxs-lookup"><span data-stu-id="8d322-172">Supported bases</span></span> 

- <span data-ttu-id="8d322-173">Montant fixe</span><span class="sxs-lookup"><span data-stu-id="8d322-173">Fixed amount</span></span>
- <span data-ttu-id="8d322-174">Pourcentage des rémunérations</span><span class="sxs-lookup"><span data-stu-id="8d322-174">Percent of earnings</span></span>
- <span data-ttu-id="8d322-175">Heures productives</span><span class="sxs-lookup"><span data-stu-id="8d322-175">Productive hours</span></span>

<span data-ttu-id="8d322-176">Dayforce crée les déductions suivantes, selon l’impact sur la paie défini dans le plan d’avantages.</span><span class="sxs-lookup"><span data-stu-id="8d322-176">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="8d322-177">Sélection dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="8d322-177">Selection in Human Resources</span></span>        | <span data-ttu-id="8d322-178">Résultat dans Dayforce</span><span class="sxs-lookup"><span data-stu-id="8d322-178">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="8d322-179">Aucune</span><span class="sxs-lookup"><span data-stu-id="8d322-179">None</span></span>                       | <span data-ttu-id="8d322-180">Aucune retenue n’est créée.</span><span class="sxs-lookup"><span data-stu-id="8d322-180">No deduction is created.</span></span>                      |
| <span data-ttu-id="8d322-181">Déduction uniquement</span><span class="sxs-lookup"><span data-stu-id="8d322-181">Deduction only</span></span>             | <span data-ttu-id="8d322-182">Une retenue employé est créée.</span><span class="sxs-lookup"><span data-stu-id="8d322-182">An employee deduction is created.</span></span>             |
| <span data-ttu-id="8d322-183">Contribution uniquement</span><span class="sxs-lookup"><span data-stu-id="8d322-183">Contribution only</span></span>          | <span data-ttu-id="8d322-184">Une retenue employeur est créée.</span><span class="sxs-lookup"><span data-stu-id="8d322-184">An employer deduction is created.</span></span>             |
| <span data-ttu-id="8d322-185">Déduction et contribution</span><span class="sxs-lookup"><span data-stu-id="8d322-185">Deduction and contribution</span></span> | <span data-ttu-id="8d322-186">Des retenues employé et employeur sont créées.</span><span class="sxs-lookup"><span data-stu-id="8d322-186">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="8d322-187">Pour plus d’informations sur la définition et la gestion des programmes d’avantages, consultez les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="8d322-187">For more information about how to define and manage a benefits program, see the following articles:</span></span>

- [<span data-ttu-id="8d322-188">Communiquer le programme d’avantages à un employé</span><span class="sxs-lookup"><span data-stu-id="8d322-188">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="8d322-189">Créer un avantage</span><span class="sxs-lookup"><span data-stu-id="8d322-189">Create a new benefit</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="8d322-190">Définir les règles d’admissibilité et les stratégies relatives aux avantages</span><span class="sxs-lookup"><span data-stu-id="8d322-190">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="8d322-191">Inscrire et annuler l’inscription des travailleurs à des avantages</span><span class="sxs-lookup"><span data-stu-id="8d322-191">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="8d322-192">Rémunération</span><span class="sxs-lookup"><span data-stu-id="8d322-192">Compensation</span></span> 

<span data-ttu-id="8d322-193">La gestion des rémunérations est utilisée pour contrôler la rémunération de base et les primes.</span><span class="sxs-lookup"><span data-stu-id="8d322-193">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="8d322-194">Le salaire de base fixe et les augmentations pour mérite d’un employé sont contrôlés via les régimes de rémunération fixe.</span><span class="sxs-lookup"><span data-stu-id="8d322-194">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="8d322-195">Le paiement des primes (primes liées aux résultats, options d’achat d’actions et octrois d’actions), ainsi que les primes exceptionnelles, est contrôlé via les régimes de rémunération variable.</span><span class="sxs-lookup"><span data-stu-id="8d322-195">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="8d322-196">Dayforce utilise les informations de rémunération pour calculer le taux horaire ou annuel d’un employé.</span><span class="sxs-lookup"><span data-stu-id="8d322-196">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="8d322-197">Des plans de rémunération fixe et des conversions de taux de salaire sont requis.</span><span class="sxs-lookup"><span data-stu-id="8d322-197">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="8d322-198">Les employés doivent être associés à un plan de rémunération fixe.</span><span class="sxs-lookup"><span data-stu-id="8d322-198">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="8d322-199">Pour plus d’informations sur les plans de rémunération, voir les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="8d322-199">For more information about compensation plans, see the following articles:</span></span>

- [<span data-ttu-id="8d322-200">Créer des régimes de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="8d322-200">Create fixed compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="8d322-201">Créer des régimes de rémunération variable</span><span class="sxs-lookup"><span data-stu-id="8d322-201">Create variable compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="8d322-202">Développer les plans et la structure du salaire/de la rémunération</span><span class="sxs-lookup"><span data-stu-id="8d322-202">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="8d322-203">Traiter la rémunération</span><span class="sxs-lookup"><span data-stu-id="8d322-203">Process compensation</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="8d322-204">Définir le processus de rémunération et calculer les résultats</span><span class="sxs-lookup"><span data-stu-id="8d322-204">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="8d322-205">Inscrire un employé à un régime de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="8d322-205">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="8d322-206">Inscrire un employé à un régime de rémunération variable</span><span class="sxs-lookup"><span data-stu-id="8d322-206">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="8d322-207">Postes</span><span class="sxs-lookup"><span data-stu-id="8d322-207">Jobs</span></span> 

<span data-ttu-id="8d322-208">Une tâche est un ensemble de tâches et de responsabilités attribuées à la personne affectée à la tâche.</span><span class="sxs-lookup"><span data-stu-id="8d322-208">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="8d322-209">Pour plus d’informations, voir l’article suivant :</span><span class="sxs-lookup"><span data-stu-id="8d322-209">For more information, see the following articles:</span></span>

- [<span data-ttu-id="8d322-210">Paramétrage des composants d’une tâche</span><span class="sxs-lookup"><span data-stu-id="8d322-210">Setting up the components of a job</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="8d322-211">Définir les nouvelles tâches</span><span class="sxs-lookup"><span data-stu-id="8d322-211">Define new jobs</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="8d322-212">Postes</span><span class="sxs-lookup"><span data-stu-id="8d322-212">Positions</span></span>

<span data-ttu-id="8d322-213">Un poste est une instance individuelle d’une tâche.</span><span class="sxs-lookup"><span data-stu-id="8d322-213">A position is an individual instance of a job.</span></span> <span data-ttu-id="8d322-214">Par exemple, le poste « Responsable des ventes (est) » est l’un des postes associés à la tâche « Responsable des ventes ».</span><span class="sxs-lookup"><span data-stu-id="8d322-214">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="8d322-215">Un poste existe dans un département.</span><span class="sxs-lookup"><span data-stu-id="8d322-215">A position exists in a department.</span></span> <span data-ttu-id="8d322-216">Seul un collaborateur peut être associé à chaque poste.</span><span class="sxs-lookup"><span data-stu-id="8d322-216">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="8d322-217">Gardez à l’esprit les données et la configuration suivantes lorsque vous paramétrez des postes :</span><span class="sxs-lookup"><span data-stu-id="8d322-217">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="8d322-218">Poste (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-218">Position (required)</span></span>
- <span data-ttu-id="8d322-219">Description (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-219">Description (required)</span></span>
- <span data-ttu-id="8d322-220">Tâche (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-220">Job (required)</span></span>
- <span data-ttu-id="8d322-221">Département (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-221">Department (required)</span></span>
- <span data-ttu-id="8d322-222">Type de poste (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-222">Position type (required)</span></span>
- <span data-ttu-id="8d322-223">Équivalent temps plein</span><span class="sxs-lookup"><span data-stu-id="8d322-223">Full-time equivalent</span></span>
- <span data-ttu-id="8d322-224">Durée annuelle normale (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-224">Annual regular hours (required)</span></span>
- <span data-ttu-id="8d322-225">Rémunéré par l’entité juridique (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-225">Paid by legal entity (required)</span></span>
- <span data-ttu-id="8d322-226">Cycle de paie (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-226">Pay cycle (required)</span></span>
- <span data-ttu-id="8d322-227">Dimension financière par défaut – Centre de coût (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-227">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="8d322-228">Affectation du collaborateur – Collaborateur, début de l’affectation, fin de l’affectation, code motif</span><span class="sxs-lookup"><span data-stu-id="8d322-228">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="8d322-229">Si plusieurs postes dans un même département sont associés à la même tâche, ils sont consolidés un seul poste dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8d322-229">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="8d322-230">Pour plus d’informations, voir l’article suivant :</span><span class="sxs-lookup"><span data-stu-id="8d322-230">For more information, see the following articles:</span></span>

- [<span data-ttu-id="8d322-231">Organisation du personnel à l’aide des départements, tâches et postes</span><span class="sxs-lookup"><span data-stu-id="8d322-231">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="8d322-232">Paramétrer les postes</span><span class="sxs-lookup"><span data-stu-id="8d322-232">Set up positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="8d322-233">Départements</span><span class="sxs-lookup"><span data-stu-id="8d322-233">Departments</span></span>

<span data-ttu-id="8d322-234">Un département est une unité opérationnelle qui représente une catégorie ou un domaine fonctionnel d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="8d322-234">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="8d322-235">Un département est responsable d’un domaine spécifique de l’organisation, par exemple les ventes, la comptabilité ou les ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="8d322-235">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="8d322-236">Les départements vous permettent de générer des états sur les domaines fonctionnels.</span><span class="sxs-lookup"><span data-stu-id="8d322-236">You can use departments to report on functional areas.</span></span> <span data-ttu-id="8d322-237">Les départements peuvent avoir la responsabilité des résultats.</span><span class="sxs-lookup"><span data-stu-id="8d322-237">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="8d322-238">Pour plus d’informations, voir l’article suivant :</span><span class="sxs-lookup"><span data-stu-id="8d322-238">For more information, see the following articles:</span></span>

- [<span data-ttu-id="8d322-239">Créer un département et l’associer à la hiérarchie des départements</span><span class="sxs-lookup"><span data-stu-id="8d322-239">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="8d322-240">Définir les nouveaux départements</span><span class="sxs-lookup"><span data-stu-id="8d322-240">Define new departments</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="8d322-241">Cycles de paie et périodes de rémunération</span><span class="sxs-lookup"><span data-stu-id="8d322-241">Pay cycles and pay periods</span></span>

<span data-ttu-id="8d322-242">Un cycle de paie détermine la fréquence d’exécution de la paie et les jours spécifiques où les collaborateurs sont payés.</span><span class="sxs-lookup"><span data-stu-id="8d322-242">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="8d322-243">Par exemple, un cycle de paie peut être mensuel, et les employés peuvent être payés le dernier jour du mois.</span><span class="sxs-lookup"><span data-stu-id="8d322-243">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="8d322-244">Sinon, un cycle de paie peut être hebdomadaire, et les employés peuvent être payés le mardi après la fin de la période de rémunération.</span><span class="sxs-lookup"><span data-stu-id="8d322-244">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="8d322-245">Les cycles de paie sont affectés aux postes afin de contrôler à quel moment les collaborateurs à ces postes sont payés.</span><span class="sxs-lookup"><span data-stu-id="8d322-245">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="8d322-246">Après avoir créé des cycles de paie, vous pouvez générer des périodes de rémunération pour chaque cycle.</span><span class="sxs-lookup"><span data-stu-id="8d322-246">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="8d322-247">Chaque période de rémunération comprend une date de paiement par défaut basée sur les informations que vous fournissez.</span><span class="sxs-lookup"><span data-stu-id="8d322-247">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="8d322-248">Toutefois, vous pouvez modifier la date de paiement par défaut d’une période de rémunération pour permettre des exceptions, par exemple lorsque la date de paiement a lieu un jour férié.</span><span class="sxs-lookup"><span data-stu-id="8d322-248">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="8d322-249">Les informations suivantes sont utilisée dans Dayforce :</span><span class="sxs-lookup"><span data-stu-id="8d322-249">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="8d322-250">Cycle de paie (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-250">Pay cycle (required)</span></span>
- <span data-ttu-id="8d322-251">Fréquence du cycle de paie (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-251">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="8d322-252">Date de début de la période (première période de rémunération obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-252">Period start date (first pay period required)</span></span>
- <span data-ttu-id="8d322-253">Date de rémunération par défaut (première période de rémunération obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-253">Default payment date (first pay period required)</span></span>

<span data-ttu-id="8d322-254">Ces informations sont intégrées à Dayforce en tant que des groupes de paie, et sont séparées par pays ou par région pour chaque cycle de paie.</span><span class="sxs-lookup"><span data-stu-id="8d322-254">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="8d322-255">Au moins une période de rémunération doit être générée avant l’intégration.</span><span class="sxs-lookup"><span data-stu-id="8d322-255">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="8d322-256">Dayforce génère des calendriers de groupe de paie et des dates de rémunération, selon la date de début de la première période de rémunération et la date de rémunération par défaut paramétrées dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8d322-256">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Human Resources.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="8d322-257">Codes de rémunérations</span><span class="sxs-lookup"><span data-stu-id="8d322-257">Earning codes</span></span>

<span data-ttu-id="8d322-258">Les codes de rémunérations identifient de manière unique chaque type de revenus que les collaborateurs reçoivent.</span><span class="sxs-lookup"><span data-stu-id="8d322-258">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="8d322-259">Les codes ont différents paramètres associés aux revenus, tels que des règles comptables, des lois fiscales, des conditions de génération d’états, et la capacité de montant brut.</span><span class="sxs-lookup"><span data-stu-id="8d322-259">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="8d322-260">Les informations suivantes sont utilisée dans Dayforce :</span><span class="sxs-lookup"><span data-stu-id="8d322-260">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="8d322-261">Code de rémunération (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-261">Earning Code (required)</span></span>
- <span data-ttu-id="8d322-262">Description</span><span class="sxs-lookup"><span data-stu-id="8d322-262">Description</span></span>
- <span data-ttu-id="8d322-263">Unité de mesure</span><span class="sxs-lookup"><span data-stu-id="8d322-263">Unit of measure</span></span>
- <span data-ttu-id="8d322-264">Productif</span><span class="sxs-lookup"><span data-stu-id="8d322-264">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="8d322-265">Données sur les collaborateurs</span><span class="sxs-lookup"><span data-stu-id="8d322-265">Worker data</span></span>

<span data-ttu-id="8d322-266">Les enregistrements pour les différents types d’employés dont vous disposez sont importants pour vos systèmes de ressources humaines et de paie.</span><span class="sxs-lookup"><span data-stu-id="8d322-266">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="8d322-267">Les informations que vous entrez peuvent servir à suivre les informations des collaborateurs et les informations personnelles.</span><span class="sxs-lookup"><span data-stu-id="8d322-267">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="8d322-268">Vous pouvez tenir à jour les informations suivantes pour les travailleurs :</span><span class="sxs-lookup"><span data-stu-id="8d322-268">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="8d322-269">**Base** – Permet de tenir à jour les informations de base sur un collaborateur, telles que les informations de contact, les informations démographiques, les informations d’identification, les informations sur la famille, le statut de service militaire, les informations d’expatriation, et les contacts personnels et les personnes à prévenir en cas d’urgence.</span><span class="sxs-lookup"><span data-stu-id="8d322-269">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="8d322-270">**Emploi** – Permet de tenir à jour les informations relatives à l’emploi des collaborateurs, telles que l’affiliation de la société ou de l’organisation, l’affectation de poste, les dates de début et de fin, l’éligibilité à un emploi, les conditions d’emploi, la retraite, les congés, et les informations de mutation.</span><span class="sxs-lookup"><span data-stu-id="8d322-270">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="8d322-271">**Congé et absence** – Permet de tenir à jour les informations sur les absences des collaborateurs, telles que les calendriers de travail, les transactions d’absence et le paramétrage d’absence.</span><span class="sxs-lookup"><span data-stu-id="8d322-271">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="8d322-272">**Rémunération et paie** – Permet de tenir à jour les informations sur les régimes de rémunération des collaborateurs et les informations de paie, telles que l’inscription à un régime, les primes, les performances, la commission, les informations fiscales, la retraite et les déductions de salaire.</span><span class="sxs-lookup"><span data-stu-id="8d322-272">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="8d322-273">Lorsque vous entrez des informations sur le collaborateur, n’oubliez pas les données et les configurations suivantes utilisées dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8d322-273">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="8d322-274">Informations générales</span><span class="sxs-lookup"><span data-stu-id="8d322-274">General information</span></span>

- <span data-ttu-id="8d322-275">Matricule (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-275">Personnel number (required)</span></span>
- <span data-ttu-id="8d322-276">Prénom (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-276">First name (required)</span></span>
- <span data-ttu-id="8d322-277">Nom (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-277">Last name (required)</span></span>
- <span data-ttu-id="8d322-278">Autres prénoms</span><span class="sxs-lookup"><span data-stu-id="8d322-278">Middle name</span></span>
- <span data-ttu-id="8d322-279">Date d’ancienneté</span><span class="sxs-lookup"><span data-stu-id="8d322-279">Seniority date</span></span>
- <span data-ttu-id="8d322-280">Connu sous</span><span class="sxs-lookup"><span data-stu-id="8d322-280">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="8d322-281">Informations personnelles</span><span class="sxs-lookup"><span data-stu-id="8d322-281">Personal information</span></span>

- <span data-ttu-id="8d322-282">État civil (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-282">Marital status (required)</span></span>
- <span data-ttu-id="8d322-283">Date de naissance (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-283">Birth date (required)</span></span>
- <span data-ttu-id="8d322-284">Sexe (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-284">Gender (required)</span></span>
- <span data-ttu-id="8d322-285">Personne handicapée</span><span class="sxs-lookup"><span data-stu-id="8d322-285">Person with disabilities</span></span>
- <span data-ttu-id="8d322-286">Région/pays de nationalité (uniquement au Mexique)</span><span class="sxs-lookup"><span data-stu-id="8d322-286">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="8d322-287">Informations d’adresse</span><span class="sxs-lookup"><span data-stu-id="8d322-287">Address information</span></span>

- <span data-ttu-id="8d322-288">Adresse principale (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-288">Primary (required)</span></span>
- <span data-ttu-id="8d322-289">Pays/région (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-289">Country/region (required)</span></span>
- <span data-ttu-id="8d322-290">Code postal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-290">Postal code (required)</span></span>
- <span data-ttu-id="8d322-291">Numéro de la rue (obligatoire) (uniquement au Mexique)</span><span class="sxs-lookup"><span data-stu-id="8d322-291">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="8d322-292">Info complémentaire sur le bâtiment (uniquement au Mexique)</span><span class="sxs-lookup"><span data-stu-id="8d322-292">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="8d322-293">Ville (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-293">City (required)</span></span>
- <span data-ttu-id="8d322-294">État (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-294">State (required)</span></span>
- <span data-ttu-id="8d322-295">Pays (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-295">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="8d322-296">Informations de contact</span><span class="sxs-lookup"><span data-stu-id="8d322-296">Contact information</span></span> 

- <span data-ttu-id="8d322-297">Contact principal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-297">Primary (required)</span></span>
- <span data-ttu-id="8d322-298">Numéro du contact (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-298">Contact number (required)</span></span>
- <span data-ttu-id="8d322-299">Poste</span><span class="sxs-lookup"><span data-stu-id="8d322-299">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="8d322-300">Informations sur les salaires et codes de rémunération</span><span class="sxs-lookup"><span data-stu-id="8d322-300">Payroll information and earning codes</span></span>

<span data-ttu-id="8d322-301">Les employés peuvent bénéficier de revenus spécifiques à une fréquence de paiement donnée et avoir un mode de paiement préféré.</span><span class="sxs-lookup"><span data-stu-id="8d322-301">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="8d322-302">Les champs suivants sont utilisés dans Dayforce pour garantir que ces préférences et paramètres soient utilisés.</span><span class="sxs-lookup"><span data-stu-id="8d322-302">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="8d322-303">Codes de rémunérations</span><span class="sxs-lookup"><span data-stu-id="8d322-303">Earning codes</span></span>

- <span data-ttu-id="8d322-304">Poste (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-304">Position (required)</span></span>
- <span data-ttu-id="8d322-305">Code de rémunération (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-305">Earning Code (required)</span></span>
- <span data-ttu-id="8d322-306">Fréquence (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-306">Frequency (required)</span></span>
- <span data-ttu-id="8d322-307">Montant (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-307">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="8d322-308">Informations sur les salaires</span><span class="sxs-lookup"><span data-stu-id="8d322-308">Payroll information</span></span>

- <span data-ttu-id="8d322-309">Mode de paiement</span><span class="sxs-lookup"><span data-stu-id="8d322-309">Payment Method</span></span>
- <span data-ttu-id="8d322-310">Région économique (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-310">Economic Region (required)</span></span>
- <span data-ttu-id="8d322-311">ID avantages employé</span><span class="sxs-lookup"><span data-stu-id="8d322-311">Employee Benefits ID</span></span>
- <span data-ttu-id="8d322-312">Numéro d’ID national (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-312">National ID Number (required)</span></span>
- <span data-ttu-id="8d322-313">Numéro de service militaire</span><span class="sxs-lookup"><span data-stu-id="8d322-313">Military Service Number</span></span>
- <span data-ttu-id="8d322-314">ID d’équipe (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-314">Shift ID (required)</span></span>
- <span data-ttu-id="8d322-315">Numéro de taxe (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-315">Tax Number (required)</span></span>
- <span data-ttu-id="8d322-316">ID syndicat (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-316">Union ID (required)</span></span>
- <span data-ttu-id="8d322-317">ID de la journée de travail (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-317">Work Day ID (required)</span></span>
- <span data-ttu-id="8d322-318">Numéro de permis de travail</span><span class="sxs-lookup"><span data-stu-id="8d322-318">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="8d322-319">Pour le mode de paiement, le Mexique prend en charge les **Espèces**, les **Chèques** (chèque physique de la société) et le **Paiement électronique**.</span><span class="sxs-lookup"><span data-stu-id="8d322-319">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="8d322-320">Si aucun mode de paiement n’est spécifié, le **Chèque** est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="8d322-320">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="8d322-321">Détails de l’emploi</span><span class="sxs-lookup"><span data-stu-id="8d322-321">Employment details</span></span>

<span data-ttu-id="8d322-322">L’historique des détails de l’emploi est utilisé comme information clé pour en dériver le statut d’embauche, de fin du contrat, et de réembauche d’un employé dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8d322-322">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="8d322-323">Dayforce prend en charge un seul enregistrement d’emploi actif à la fois.</span><span class="sxs-lookup"><span data-stu-id="8d322-323">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="8d322-324">Date de début de l’emploi (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-324">Employment start date (required)</span></span>
- <span data-ttu-id="8d322-325">Date de fin de l’emploi</span><span class="sxs-lookup"><span data-stu-id="8d322-325">Employment end date</span></span>
- <span data-ttu-id="8d322-326">Date de début</span><span class="sxs-lookup"><span data-stu-id="8d322-326">Start date</span></span>
- <span data-ttu-id="8d322-327">Date de début de contrat ajustée</span><span class="sxs-lookup"><span data-stu-id="8d322-327">Adjusted start date</span></span>
- <span data-ttu-id="8d322-328">Date de fin de contrat (obligatoire à la fin du contrat)</span><span class="sxs-lookup"><span data-stu-id="8d322-328">Termination date (required upon termination)</span></span>
- <span data-ttu-id="8d322-329">Motif de la fin du contrat (obligatoire à la fin du contrat)</span><span class="sxs-lookup"><span data-stu-id="8d322-329">Termination reason (required upon termination)</span></span>

<span data-ttu-id="8d322-330">Les dates clés d’un employé sont dérivées à l’aide des informations suivantes.</span><span class="sxs-lookup"><span data-stu-id="8d322-330">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="8d322-331">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="8d322-331">Human Resources</span></span>                | <span data-ttu-id="8d322-332">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8d322-332">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8d322-333">Date d’embauche la plus récente</span><span class="sxs-lookup"><span data-stu-id="8d322-333">Most recent hire date</span></span> | <span data-ttu-id="8d322-334">Début de l’emploi de l’enregistrement d’historique d’emploi avec contrat en cours</span><span class="sxs-lookup"><span data-stu-id="8d322-334">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="8d322-335">Date de fin de contrat</span><span class="sxs-lookup"><span data-stu-id="8d322-335">Termination date</span></span>      | <span data-ttu-id="8d322-336">Date de fin de contrat de l’enregistrement d’historique d’emploi avec contrat en cours</span><span class="sxs-lookup"><span data-stu-id="8d322-336">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="8d322-337">Date de début</span><span class="sxs-lookup"><span data-stu-id="8d322-337">Start date</span></span>            | <span data-ttu-id="8d322-338">Date de début ajustée, date de début, ou début de l’emploi de l’enregistrement d’historique d’emploi inactif actuel</span><span class="sxs-lookup"><span data-stu-id="8d322-338">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="8d322-339">Date d’embauche d’origine</span><span class="sxs-lookup"><span data-stu-id="8d322-339">Original hire date</span></span>    | <span data-ttu-id="8d322-340">Début d’emploi de l’enregistrement d’historique d’emploi le plus proche</span><span class="sxs-lookup"><span data-stu-id="8d322-340">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="8d322-341">Rémunération</span><span class="sxs-lookup"><span data-stu-id="8d322-341">Compensation</span></span>

<span data-ttu-id="8d322-342">Un plan de rémunération fixe doit être associé au poste principal de chaque employé tout au long d’une période d’emploi.</span><span class="sxs-lookup"><span data-stu-id="8d322-342">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="8d322-343">Cette période démarre à la date à laquelle l’employé a été embauché (ou à la date de début de l’emploi) et se poursuit jusqu’à la fin de contrat.</span><span class="sxs-lookup"><span data-stu-id="8d322-343">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="8d322-344">Date d’effet (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-344">Effective Date (required)</span></span>
- <span data-ttu-id="8d322-345">Date d’expiration</span><span class="sxs-lookup"><span data-stu-id="8d322-345">Expiration date</span></span>
- <span data-ttu-id="8d322-346">Taux de salaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-346">Pay Rate (required)</span></span>
- <span data-ttu-id="8d322-347">Conversions de taux de salaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-347">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="8d322-348">Équivalent annuel (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-348">Annual equivalent (required)</span></span>
- <span data-ttu-id="8d322-349">Équivalent horaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-349">Hourly equivalent (required)</span></span>

<span data-ttu-id="8d322-350">Si un employé horaire a plusieurs postes, la rémunération fixe du poste principal est importée dans Dayforce comme taux de base/salaire de niveau d’employé.</span><span class="sxs-lookup"><span data-stu-id="8d322-350">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="8d322-351">Pour les postes non principaux, le taux horaire est enregistré au poste correspondant dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8d322-351">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="8d322-352">Si un employé salarié occupe plusieurs postes, le taux horaire cumulé et le salaire annuel entre tous les postes actifs sont dérivés et utilisés comme taux de base/salaire au niveau de l’employé.</span><span class="sxs-lookup"><span data-stu-id="8d322-352">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="8d322-353">Numéros d’identifications</span><span class="sxs-lookup"><span data-stu-id="8d322-353">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="8d322-354">Numéro de Sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="8d322-354">Social Security identifier</span></span> 

<span data-ttu-id="8d322-355">Chaque employé doit avoir un numéro principal.</span><span class="sxs-lookup"><span data-stu-id="8d322-355">Every employee must have one primary identifier.</span></span> <span data-ttu-id="8d322-356">Cet numéro doit être de type d’identification **N° S.S.**.</span><span class="sxs-lookup"><span data-stu-id="8d322-356">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="8d322-357">Dans Dayforce, il est automatiquement dérivé du numéro de Sécurité sociale de l’employé qui est obligatoire pour l’embaucher.</span><span class="sxs-lookup"><span data-stu-id="8d322-357">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="8d322-358">Numéro principal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-358">Primary (required)</span></span>
- <span data-ttu-id="8d322-359">Type d’identification = « N° S.S. »</span><span class="sxs-lookup"><span data-stu-id="8d322-359">Identification Type = "SSN"</span></span>
- <span data-ttu-id="8d322-360">Date d’émission</span><span class="sxs-lookup"><span data-stu-id="8d322-360">Issued Date</span></span>
- <span data-ttu-id="8d322-361">Date d’expiration</span><span class="sxs-lookup"><span data-stu-id="8d322-361">Expiration Date</span></span>

<span data-ttu-id="8d322-362">Les employés peuvent déclarer plusieurs numéros d’identification de type d’identification **N° S.S.**.</span><span class="sxs-lookup"><span data-stu-id="8d322-362">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="8d322-363">Toutefois, seul l’enregistrement marqué comme **Principal** est intégré à Dayforce, que le numéro soit active ou arrivé à expiration.</span><span class="sxs-lookup"><span data-stu-id="8d322-363">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="8d322-364">Comptes en banque et décaissements</span><span class="sxs-lookup"><span data-stu-id="8d322-364">Bank accounts and disbursements</span></span>

<span data-ttu-id="8d322-365">Des informations de compte bancaire valides doivent être entrées pour tous les employés qui choisissent d’être payés à l’aide de virements bancaires.</span><span class="sxs-lookup"><span data-stu-id="8d322-365">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="8d322-366">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="8d322-366">Human Resources</span></span>                         | <span data-ttu-id="8d322-367">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8d322-367">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8d322-368">Numéro de compte bancaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-368">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="8d322-369">Code SWIFT (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-369">SWIFT code (required)</span></span>          | <span data-ttu-id="8d322-370">Le champ **ID banque** utilisé lors du traitement du salaire au Mexique.</span><span class="sxs-lookup"><span data-stu-id="8d322-370">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="8d322-371">Numéro d’agence (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-371">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="8d322-372">Type de compte bancaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-372">Bank account type (required)</span></span>   | <span data-ttu-id="8d322-373">Le champ **Type de compte** utilisé lors du traitement du salaire au Mexique.</span><span class="sxs-lookup"><span data-stu-id="8d322-373">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="8d322-374">Les valeurs prises en charge sont **Chèque** et **Paie**.</span><span class="sxs-lookup"><span data-stu-id="8d322-374">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="8d322-375">Les employés qui choisissent d’être payés par des virements bancaires doivent fournir un lien vers un compte de solde qui se trouve sous une entité juridique avec son adresse principale au Mexique, et associée à un compte bancaire valide dans une banque mexicaine.</span><span class="sxs-lookup"><span data-stu-id="8d322-375">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="8d322-376">Tous les autres comptes non-solde sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="8d322-376">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="8d322-377">Informations d’adresse</span><span class="sxs-lookup"><span data-stu-id="8d322-377">Address information</span></span>

<span data-ttu-id="8d322-378">Chaque employé doit avoir un lieu principal.</span><span class="sxs-lookup"><span data-stu-id="8d322-378">Every employee must have one primary location.</span></span> <span data-ttu-id="8d322-379">Dans Dayforce, ce lieu est utilisé pour déterminer la résidence principale de l’employé à des fins fiscales.</span><span class="sxs-lookup"><span data-stu-id="8d322-379">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="8d322-380">Lieu principal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-380">Primary (required)</span></span>
- <span data-ttu-id="8d322-381">Pays/région (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-381">Country/region (required)</span></span>
- <span data-ttu-id="8d322-382">Code postal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-382">Zip/postal code (required)</span></span>
- <span data-ttu-id="8d322-383">Rue (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-383">Street (required)</span></span>
- <span data-ttu-id="8d322-384">Numéro de rue (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-384">Street Number (required)</span></span>
- <span data-ttu-id="8d322-385">Info complémentaire sur le bâtiment</span><span class="sxs-lookup"><span data-stu-id="8d322-385">Building Complement</span></span>
- <span data-ttu-id="8d322-386">Ville (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-386">City (required)</span></span>
- <span data-ttu-id="8d322-387">État (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-387">State (required)</span></span>
- <span data-ttu-id="8d322-388">Pays (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-388">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="8d322-389">Configurer vos données pour générer un salaire aux États-Unis et au Canada</span><span class="sxs-lookup"><span data-stu-id="8d322-389">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="8d322-390">Si vous générez un salaire pour des employés aux États-Unis et au Canada, les éléments suivants doivent être configurés :</span><span class="sxs-lookup"><span data-stu-id="8d322-390">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="8d322-391">Les départements sont obligatoires sur les postes.</span><span class="sxs-lookup"><span data-stu-id="8d322-391">Departments are required on positions.</span></span>
- <span data-ttu-id="8d322-392">Les centres de coût doivent être définis comme des dimensions financières et doivent être le premier élément de la chaîne de dimension financière par défaut.</span><span class="sxs-lookup"><span data-stu-id="8d322-392">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="8d322-393">Vous pouvez configurer Human Resources pour demander que les postes spécifient un service.</span><span class="sxs-lookup"><span data-stu-id="8d322-393">You can configure Human Resources to require that Positions specify a Department.</span></span> <span data-ttu-id="8d322-394">Pour ce faire, accédez à **Postes partagés par les ressources humaines > Postes > Demander le service des postes**.</span><span class="sxs-lookup"><span data-stu-id="8d322-394">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="8d322-395">Nous vous recommandons d’appliquer ce paramètre pour l’intégration.</span><span class="sxs-lookup"><span data-stu-id="8d322-395">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="8d322-396">Types de missions</span><span class="sxs-lookup"><span data-stu-id="8d322-396">Job types</span></span>

<span data-ttu-id="8d322-397">Les types de tâches sont utilisés pour regrouper les tâches similaires en catégories.</span><span class="sxs-lookup"><span data-stu-id="8d322-397">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="8d322-398">Les types de tâches sont nécessaires pour traiter la paie aux États-Unis et au Canada.</span><span class="sxs-lookup"><span data-stu-id="8d322-398">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="8d322-399">Les exemples de types de tâches incluent le temps plein et le temps partiel, ou le salaire et le paiement à l’heure.</span><span class="sxs-lookup"><span data-stu-id="8d322-399">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="8d322-400">Les types de tâches sont mis en correspondance dans Dayforce comme types de paies qui indiquent si un employé est payé à l’heure ou salarié.</span><span class="sxs-lookup"><span data-stu-id="8d322-400">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="8d322-401">Les types de tâches et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="8d322-401">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="8d322-402">Type de mission</span><span class="sxs-lookup"><span data-stu-id="8d322-402">Job type</span></span>   | <span data-ttu-id="8d322-403">Description</span><span class="sxs-lookup"><span data-stu-id="8d322-403">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="8d322-404">Horaire</span><span class="sxs-lookup"><span data-stu-id="8d322-404">Hourly</span></span>     | <span data-ttu-id="8d322-405">Horaire</span><span class="sxs-lookup"><span data-stu-id="8d322-405">Hourly</span></span>      |
| <span data-ttu-id="8d322-406">Salarié</span><span class="sxs-lookup"><span data-stu-id="8d322-406">Salaried</span></span>   | <span data-ttu-id="8d322-407">Salarié</span><span class="sxs-lookup"><span data-stu-id="8d322-407">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="8d322-408">Types de poste</span><span class="sxs-lookup"><span data-stu-id="8d322-408">Position types</span></span> 

<span data-ttu-id="8d322-409">Vous utilisez les types de postes pour indiquer si le poste est à temps plein, à temps partiel, ou autre chose.</span><span class="sxs-lookup"><span data-stu-id="8d322-409">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="8d322-410">Les types de postes sont mis en correspondance dans Dayforce comme classes de paiements qui indiquent si un employé est à temps plein ou à temps partiel.</span><span class="sxs-lookup"><span data-stu-id="8d322-410">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="8d322-411">Les types de postes et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="8d322-411">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="8d322-412">Type de poste</span><span class="sxs-lookup"><span data-stu-id="8d322-412">Position type</span></span>   | <span data-ttu-id="8d322-413">Description</span><span class="sxs-lookup"><span data-stu-id="8d322-413">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="8d322-414">Temps plein</span><span class="sxs-lookup"><span data-stu-id="8d322-414">Full-time</span></span>       | <span data-ttu-id="8d322-415">Employé à temps plein</span><span class="sxs-lookup"><span data-stu-id="8d322-415">Full time employee</span></span> |
| <span data-ttu-id="8d322-416">Temps partiel</span><span class="sxs-lookup"><span data-stu-id="8d322-416">Part-time</span></span>       | <span data-ttu-id="8d322-417">Employé à temps partiel</span><span class="sxs-lookup"><span data-stu-id="8d322-417">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="8d322-418">Codes motif</span><span class="sxs-lookup"><span data-stu-id="8d322-418">Reason codes</span></span>

<span data-ttu-id="8d322-419">Les codes motif fournissent des informations sur le statut d’un employé.</span><span class="sxs-lookup"><span data-stu-id="8d322-419">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="8d322-420">Les codes motif sont mis en correspondance avec Dayforce comme motifs du statut, indiquant le motif des modifications apportées au poste ou au statut d’emploi d’un employé.</span><span class="sxs-lookup"><span data-stu-id="8d322-420">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="8d322-421">Les codes motif et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="8d322-421">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="8d322-422">Code motif</span><span class="sxs-lookup"><span data-stu-id="8d322-422">Reason code</span></span>    | <span data-ttu-id="8d322-423">Description</span><span class="sxs-lookup"><span data-stu-id="8d322-423">Description</span></span>      | <span data-ttu-id="8d322-424">Scénarios applicables</span><span class="sxs-lookup"><span data-stu-id="8d322-424">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="8d322-425">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="8d322-425">RESIGNATION</span></span>    | <span data-ttu-id="8d322-426">Démission</span><span class="sxs-lookup"><span data-stu-id="8d322-426">Resignation</span></span>      | <span data-ttu-id="8d322-427">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="8d322-427">Terminate worker</span></span>     |
| <span data-ttu-id="8d322-428">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="8d322-428">TERMINATION</span></span>    | <span data-ttu-id="8d322-429">Fin du contrat</span><span class="sxs-lookup"><span data-stu-id="8d322-429">Termination</span></span>      | <span data-ttu-id="8d322-430">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="8d322-430">Terminate worker</span></span>     |
| <span data-ttu-id="8d322-431">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="8d322-431">RETIREMENT</span></span>     | <span data-ttu-id="8d322-432">Retraite</span><span class="sxs-lookup"><span data-stu-id="8d322-432">Retirement</span></span>       | <span data-ttu-id="8d322-433">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="8d322-433">Terminate worker</span></span>     |
| <span data-ttu-id="8d322-434">OTHER</span><span class="sxs-lookup"><span data-stu-id="8d322-434">OTHER</span></span>          | <span data-ttu-id="8d322-435">Autres motifs</span><span class="sxs-lookup"><span data-stu-id="8d322-435">Other Reasons</span></span>    | <span data-ttu-id="8d322-436">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="8d322-436">Terminate worker</span></span>     |
| <span data-ttu-id="8d322-437">DEATH</span><span class="sxs-lookup"><span data-stu-id="8d322-437">DEATH</span></span>          | <span data-ttu-id="8d322-438">Décès</span><span class="sxs-lookup"><span data-stu-id="8d322-438">Death</span></span>            | <span data-ttu-id="8d322-439">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="8d322-439">Terminate worker</span></span>     |
| <span data-ttu-id="8d322-440">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="8d322-440">LEAVEOFABSENCE</span></span> | <span data-ttu-id="8d322-441">Congé</span><span class="sxs-lookup"><span data-stu-id="8d322-441">Leave of Absence</span></span> | <span data-ttu-id="8d322-442">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="8d322-442">Terminate worker</span></span>     |
| <span data-ttu-id="8d322-443">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="8d322-443">CONTRACTEND</span></span>    | <span data-ttu-id="8d322-444">Fin du contrat</span><span class="sxs-lookup"><span data-stu-id="8d322-444">End of Contract</span></span>  | <span data-ttu-id="8d322-445">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="8d322-445">Terminate worker</span></span>     |
| <span data-ttu-id="8d322-446">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="8d322-446">SALARYCHANGE</span></span>   | <span data-ttu-id="8d322-447">Modification du salaire</span><span class="sxs-lookup"><span data-stu-id="8d322-447">Change of Salary</span></span> | <span data-ttu-id="8d322-448">Rémunération</span><span class="sxs-lookup"><span data-stu-id="8d322-448">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="8d322-449">Situation de famille</span><span class="sxs-lookup"><span data-stu-id="8d322-449">Marital status</span></span>

<span data-ttu-id="8d322-450">Les valeurs de situation de famille sont mises en correspondance avec Dayforce et traduite, au besoin, dans les valeurs acceptées lors de l’intégration.</span><span class="sxs-lookup"><span data-stu-id="8d322-450">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="8d322-451">Le tableau suivant montre comment les valeurs de situation de famille sont mises en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8d322-451">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="8d322-452">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="8d322-452">Human Resources</span></span>                 | <span data-ttu-id="8d322-453">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8d322-453">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="8d322-454">Marié</span><span class="sxs-lookup"><span data-stu-id="8d322-454">Married</span></span>                | <span data-ttu-id="8d322-455">Marié</span><span class="sxs-lookup"><span data-stu-id="8d322-455">Married</span></span>              |
| <span data-ttu-id="8d322-456">Unique</span><span class="sxs-lookup"><span data-stu-id="8d322-456">Single</span></span>                 | <span data-ttu-id="8d322-457">Unique</span><span class="sxs-lookup"><span data-stu-id="8d322-457">Single</span></span>               |
| <span data-ttu-id="8d322-458">Veuf</span><span class="sxs-lookup"><span data-stu-id="8d322-458">Widowed</span></span>                | <span data-ttu-id="8d322-459">Veuf</span><span class="sxs-lookup"><span data-stu-id="8d322-459">Widowed</span></span>              |
| <span data-ttu-id="8d322-460">Divorcé</span><span class="sxs-lookup"><span data-stu-id="8d322-460">Divorced</span></span>               | <span data-ttu-id="8d322-461">Divorcé</span><span class="sxs-lookup"><span data-stu-id="8d322-461">Divorced</span></span>             |
| <span data-ttu-id="8d322-462">Partenariat enregistré</span><span class="sxs-lookup"><span data-stu-id="8d322-462">Registered Partnership</span></span> | <span data-ttu-id="8d322-463">Partenariat local</span><span class="sxs-lookup"><span data-stu-id="8d322-463">Domestic Partnership</span></span> |
| <span data-ttu-id="8d322-464">None</span><span class="sxs-lookup"><span data-stu-id="8d322-464">None</span></span>                   | <span data-ttu-id="8d322-465">None</span><span class="sxs-lookup"><span data-stu-id="8d322-465">None</span></span>                 |
| <span data-ttu-id="8d322-466">Concubinage</span><span class="sxs-lookup"><span data-stu-id="8d322-466">Cohabiting</span></span>             | <span data-ttu-id="8d322-467">Concubinage</span><span class="sxs-lookup"><span data-stu-id="8d322-467">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="8d322-468">Sexe</span><span class="sxs-lookup"><span data-stu-id="8d322-468">Gender</span></span>

<span data-ttu-id="8d322-469">Le sexe est mis en correspondance avec Dayforce et traduit, au besoin, dans les valeurs acceptées lors de l’intégration.</span><span class="sxs-lookup"><span data-stu-id="8d322-469">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="8d322-470">Le tableau suivant montre comment le sexe est mis en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8d322-470">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="8d322-471">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="8d322-471">Human Resources</span></span>       | <span data-ttu-id="8d322-472">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8d322-472">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="8d322-473">Masculin</span><span class="sxs-lookup"><span data-stu-id="8d322-473">Male</span></span>         | <span data-ttu-id="8d322-474">Masculin</span><span class="sxs-lookup"><span data-stu-id="8d322-474">Male</span></span>            |
| <span data-ttu-id="8d322-475">Féminin</span><span class="sxs-lookup"><span data-stu-id="8d322-475">Female</span></span>       | <span data-ttu-id="8d322-476">Féminin</span><span class="sxs-lookup"><span data-stu-id="8d322-476">Female</span></span>          |
| <span data-ttu-id="8d322-477">Non spécifique</span><span class="sxs-lookup"><span data-stu-id="8d322-477">Non-specific</span></span> | <span data-ttu-id="8d322-478">*Non pris en charge*</span><span class="sxs-lookup"><span data-stu-id="8d322-478">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="8d322-479">Codes de rémunérations</span><span class="sxs-lookup"><span data-stu-id="8d322-479">Earning codes</span></span>

<span data-ttu-id="8d322-480">Les codes de rémunérations identifient de manière unique chaque type de revenus que les collaborateurs reçoivent.</span><span class="sxs-lookup"><span data-stu-id="8d322-480">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="8d322-481">Les codes couvrent différents paramètres associés aux revenus, tels que des règles comptables, des lois fiscales, des conditions de génération d’états, et la capacité de montant brut.</span><span class="sxs-lookup"><span data-stu-id="8d322-481">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="8d322-482">Si une fréquence non prise en charge est utilisée, la fréquence **Chaque paie** est utilisée par défaut pour le calcul.</span><span class="sxs-lookup"><span data-stu-id="8d322-482">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="8d322-483">Fréquences prises en charge</span><span class="sxs-lookup"><span data-stu-id="8d322-483">Supported frequencies</span></span>

- <span data-ttu-id="8d322-484">Tous</span><span class="sxs-lookup"><span data-stu-id="8d322-484">All</span></span>
- <span data-ttu-id="8d322-485">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="8d322-485">EVERYPAY</span></span>
- <span data-ttu-id="8d322-486">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="8d322-486">EACHPAYPERIOD</span></span>
- <span data-ttu-id="8d322-487">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="8d322-487">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="8d322-488">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="8d322-488">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="8d322-489">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-489">1OFMTH</span></span>
- <span data-ttu-id="8d322-490">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-490">LASTOFMTH</span></span>
- <span data-ttu-id="8d322-491">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-491">2OFMTH</span></span>
- <span data-ttu-id="8d322-492">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-492">3OFMTH</span></span>
- <span data-ttu-id="8d322-493">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-493">4OFMTH</span></span>
- <span data-ttu-id="8d322-494">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-494">5OFMTH</span></span>
- <span data-ttu-id="8d322-495">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-495">1N2OFMTH</span></span>
- <span data-ttu-id="8d322-496">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-496">3N4OFMTH</span></span>
- <span data-ttu-id="8d322-497">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-497">1N3OFMTH</span></span>
- <span data-ttu-id="8d322-498">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-498">1N4OFMTH</span></span>
- <span data-ttu-id="8d322-499">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-499">2N3OFMTH</span></span>
- <span data-ttu-id="8d322-500">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-500">2N4OFMTH</span></span>
- <span data-ttu-id="8d322-501">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-501">1N2N3OFMTH</span></span>
- <span data-ttu-id="8d322-502">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-502">1N2N4OFMTH</span></span>
- <span data-ttu-id="8d322-503">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-503">1N3N4OFMTH</span></span>
- <span data-ttu-id="8d322-504">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-504">2N3N4OFMTH</span></span>
- <span data-ttu-id="8d322-505">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-505">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="8d322-506">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="8d322-506">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="8d322-507">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="8d322-507">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="8d322-508">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="8d322-508">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="8d322-509">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="8d322-509">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="8d322-510">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="8d322-510">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="8d322-511">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="8d322-511">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="8d322-512">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="8d322-512">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="8d322-513">Adresses</span><span class="sxs-lookup"><span data-stu-id="8d322-513">Addresses</span></span>

<span data-ttu-id="8d322-514">L’identification d’un pays ou d’une région, d’un état, et des codes département (municipalité) spécifiques nécessite des formats spécifiques que les fournisseurs Dayforce et dans le pays/la région peuvent identifier.</span><span class="sxs-lookup"><span data-stu-id="8d322-514">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="8d322-515">Bien que le format pour les villes soit flexible, chaque ville doit être associée à un état.</span><span class="sxs-lookup"><span data-stu-id="8d322-515">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="8d322-516">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="8d322-516">Human Resources</span></span>          | <span data-ttu-id="8d322-517">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8d322-517">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="8d322-518">Pays/région</span><span class="sxs-lookup"><span data-stu-id="8d322-518">Country/Region</span></span>  | <span data-ttu-id="8d322-519">Code pays</span><span class="sxs-lookup"><span data-stu-id="8d322-519">Country Code</span></span>          |
| <span data-ttu-id="8d322-520">Code postal</span><span class="sxs-lookup"><span data-stu-id="8d322-520">Zip/Postal Code</span></span> | <span data-ttu-id="8d322-521">Code postal</span><span class="sxs-lookup"><span data-stu-id="8d322-521">Postal Code</span></span>           |
| <span data-ttu-id="8d322-522">État</span><span class="sxs-lookup"><span data-stu-id="8d322-522">State</span></span>           | <span data-ttu-id="8d322-523">Code région</span><span class="sxs-lookup"><span data-stu-id="8d322-523">State Code</span></span>            |
| <span data-ttu-id="8d322-524">Ville</span><span class="sxs-lookup"><span data-stu-id="8d322-524">City</span></span>            | <span data-ttu-id="8d322-525">Ville</span><span class="sxs-lookup"><span data-stu-id="8d322-525">City</span></span>                  |
| <span data-ttu-id="8d322-526">Commune</span><span class="sxs-lookup"><span data-stu-id="8d322-526">County</span></span>          | <span data-ttu-id="8d322-527">Département (municipalité)</span><span class="sxs-lookup"><span data-stu-id="8d322-527">County (Municipality)</span></span> |
| <span data-ttu-id="8d322-528">Rue</span><span class="sxs-lookup"><span data-stu-id="8d322-528">Street</span></span>          | <span data-ttu-id="8d322-529">Ligne d’adresse 1</span><span class="sxs-lookup"><span data-stu-id="8d322-529">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="8d322-530">Zones fiscales</span><span class="sxs-lookup"><span data-stu-id="8d322-530">Tax regions</span></span>

<span data-ttu-id="8d322-531">Les régions fiscales permettent de déterminer la taxe appropriée qui doit être appliquée lors de la génération des salaires.</span><span class="sxs-lookup"><span data-stu-id="8d322-531">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="8d322-532">Les régions fiscales sont mises en correspondance avec Dayforce comme adresses de lieu.</span><span class="sxs-lookup"><span data-stu-id="8d322-532">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="8d322-533">La région fiscale par défaut doit être associée au poste actif du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="8d322-533">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="8d322-534">Région fiscale (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-534">Tax region (required)</span></span>
- <span data-ttu-id="8d322-535">Pays/région (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-535">Country/Region (required)</span></span>
- <span data-ttu-id="8d322-536">État (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-536">State (required)</span></span>
- <span data-ttu-id="8d322-537">Commune</span><span class="sxs-lookup"><span data-stu-id="8d322-537">County</span></span> 
- <span data-ttu-id="8d322-538">Ville (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="8d322-538">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="8d322-539">Configurez vos données pour générer un salaire au Mexique</span><span class="sxs-lookup"><span data-stu-id="8d322-539">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="8d322-540">Si vous générez un salaire pour des employés au Mexique, les éléments suivants doivent être configurés :</span><span class="sxs-lookup"><span data-stu-id="8d322-540">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="8d322-541">Les départements sont obligatoires sur les postes.</span><span class="sxs-lookup"><span data-stu-id="8d322-541">Departments are required on positions.</span></span>
- <span data-ttu-id="8d322-542">Les centres de coût doivent être définis comme des dimensions financières et doivent être le premier élément de la chaîne de dimension financière par défaut.</span><span class="sxs-lookup"><span data-stu-id="8d322-542">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="8d322-543">Types de missions</span><span class="sxs-lookup"><span data-stu-id="8d322-543">Job types</span></span>

<span data-ttu-id="8d322-544">Les types de tâches sont utilisés pour regrouper les tâches similaires en catégories.</span><span class="sxs-lookup"><span data-stu-id="8d322-544">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="8d322-545">Les types de tâches sont nécessaires afin de traiter le salaire au Mexique.</span><span class="sxs-lookup"><span data-stu-id="8d322-545">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="8d322-546">Les exemples de types de tâches incluent le temps plein et le temps partiel, ou le salaire et le paiement à l’heure.</span><span class="sxs-lookup"><span data-stu-id="8d322-546">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="8d322-547">Les types de tâches sont mis en correspondance dans Dayforce comme types de paies qui indiquent si un employé est payé à l’heure ou salarié.</span><span class="sxs-lookup"><span data-stu-id="8d322-547">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="8d322-548">Les types de tâches et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="8d322-548">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="8d322-549">Type de mission</span><span class="sxs-lookup"><span data-stu-id="8d322-549">Job type</span></span>   | <span data-ttu-id="8d322-550">Description</span><span class="sxs-lookup"><span data-stu-id="8d322-550">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="8d322-551">Horaire</span><span class="sxs-lookup"><span data-stu-id="8d322-551">Hourly</span></span>     | <span data-ttu-id="8d322-552">Horaire MX</span><span class="sxs-lookup"><span data-stu-id="8d322-552">MX Hourly</span></span>   |
| <span data-ttu-id="8d322-553">Salarié</span><span class="sxs-lookup"><span data-stu-id="8d322-553">Salaried</span></span>   | <span data-ttu-id="8d322-554">Salarié MX</span><span class="sxs-lookup"><span data-stu-id="8d322-554">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="8d322-555">Types de poste</span><span class="sxs-lookup"><span data-stu-id="8d322-555">Position types</span></span> 

<span data-ttu-id="8d322-556">Vous utilisez les types de postes pour indiquer si le poste est à temps plein, à temps partiel, ou autre chose.</span><span class="sxs-lookup"><span data-stu-id="8d322-556">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="8d322-557">Les types de postes sont mis en correspondance dans Dayforce comme classes de paiements qui indiquent si un employé est à temps plein ou à temps partiel.</span><span class="sxs-lookup"><span data-stu-id="8d322-557">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="8d322-558">Les types de postes et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="8d322-558">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="8d322-559">Type de poste</span><span class="sxs-lookup"><span data-stu-id="8d322-559">Position type</span></span>   | <span data-ttu-id="8d322-560">Description</span><span class="sxs-lookup"><span data-stu-id="8d322-560">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="8d322-561">Temps plein</span><span class="sxs-lookup"><span data-stu-id="8d322-561">Full-time</span></span>       | <span data-ttu-id="8d322-562">Employé à temps plein</span><span class="sxs-lookup"><span data-stu-id="8d322-562">Full time employee</span></span> |
| <span data-ttu-id="8d322-563">Temps partiel</span><span class="sxs-lookup"><span data-stu-id="8d322-563">Part-time</span></span>       | <span data-ttu-id="8d322-564">Employé à temps partiel</span><span class="sxs-lookup"><span data-stu-id="8d322-564">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="8d322-565">Codes motif</span><span class="sxs-lookup"><span data-stu-id="8d322-565">Reason codes</span></span>

<span data-ttu-id="8d322-566">Les codes motif fournissent des informations sur le statut d’un employé.</span><span class="sxs-lookup"><span data-stu-id="8d322-566">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="8d322-567">Les codes motif sont mis en correspondance avec Dayforce comme motifs du statut, indiquant le motif des modifications apportées au poste ou au statut d’emploi d’un employé.</span><span class="sxs-lookup"><span data-stu-id="8d322-567">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="8d322-568">Les codes motif et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="8d322-568">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="8d322-569">Code motif</span><span class="sxs-lookup"><span data-stu-id="8d322-569">Reason code</span></span>            | <span data-ttu-id="8d322-570">Description</span><span class="sxs-lookup"><span data-stu-id="8d322-570">Description</span></span>                    | <span data-ttu-id="8d322-571">Scénarios applicables</span><span class="sxs-lookup"><span data-stu-id="8d322-571">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="8d322-572">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="8d322-572">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="8d322-573">Départ avant le premier salaire</span><span class="sxs-lookup"><span data-stu-id="8d322-573">Departure before first payroll</span></span> | <span data-ttu-id="8d322-574">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="8d322-574">Terminate worker</span></span>     |
| <span data-ttu-id="8d322-575">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="8d322-575">RESIGNATION</span></span>            | <span data-ttu-id="8d322-576">Démission</span><span class="sxs-lookup"><span data-stu-id="8d322-576">Resignation</span></span>                    | <span data-ttu-id="8d322-577">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="8d322-577">Terminate worker</span></span>     |
| <span data-ttu-id="8d322-578">PENSION</span><span class="sxs-lookup"><span data-stu-id="8d322-578">PENSION</span></span>                | <span data-ttu-id="8d322-579">Retraite</span><span class="sxs-lookup"><span data-stu-id="8d322-579">Pension</span></span>                        | <span data-ttu-id="8d322-580">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="8d322-580">Terminate worker</span></span>     |
| <span data-ttu-id="8d322-581">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="8d322-581">TERMINATION</span></span>            | <span data-ttu-id="8d322-582">Fin du contrat</span><span class="sxs-lookup"><span data-stu-id="8d322-582">Termination</span></span>                    | <span data-ttu-id="8d322-583">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="8d322-583">Terminate worker</span></span>     |
| <span data-ttu-id="8d322-584">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="8d322-584">RETIREMENT</span></span>             | <span data-ttu-id="8d322-585">Retraite</span><span class="sxs-lookup"><span data-stu-id="8d322-585">Retirement</span></span>                     | <span data-ttu-id="8d322-586">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="8d322-586">Terminate worker</span></span>     |
| <span data-ttu-id="8d322-587">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="8d322-587">ABSENTEE</span></span>               | <span data-ttu-id="8d322-588">Absent</span><span class="sxs-lookup"><span data-stu-id="8d322-588">Absentee</span></span>                       | <span data-ttu-id="8d322-589">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="8d322-589">Terminate worker</span></span>     |
| <span data-ttu-id="8d322-590">OTHER</span><span class="sxs-lookup"><span data-stu-id="8d322-590">OTHER</span></span>                  | <span data-ttu-id="8d322-591">Autres motifs</span><span class="sxs-lookup"><span data-stu-id="8d322-591">Other Reasons</span></span>                  | <span data-ttu-id="8d322-592">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="8d322-592">Terminate worker</span></span>     |
| <span data-ttu-id="8d322-593">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="8d322-593">CLOSURE</span></span>                | <span data-ttu-id="8d322-594">Fermeture de l’entreprise</span><span class="sxs-lookup"><span data-stu-id="8d322-594">Business Closure</span></span>               | <span data-ttu-id="8d322-595">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="8d322-595">Terminate worker</span></span>     |
| <span data-ttu-id="8d322-596">DEATH</span><span class="sxs-lookup"><span data-stu-id="8d322-596">DEATH</span></span>                  | <span data-ttu-id="8d322-597">Décès</span><span class="sxs-lookup"><span data-stu-id="8d322-597">Death</span></span>                          | <span data-ttu-id="8d322-598">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="8d322-598">Terminate worker</span></span>     |
| <span data-ttu-id="8d322-599">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="8d322-599">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="8d322-600">Congé</span><span class="sxs-lookup"><span data-stu-id="8d322-600">Leave of Absence</span></span>               | <span data-ttu-id="8d322-601">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="8d322-601">Terminate worker</span></span>     |
| <span data-ttu-id="8d322-602">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="8d322-602">CONTRACTEND</span></span>            | <span data-ttu-id="8d322-603">Fin du contrat</span><span class="sxs-lookup"><span data-stu-id="8d322-603">End of Contract</span></span>                | <span data-ttu-id="8d322-604">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="8d322-604">Terminate worker</span></span>     |
| <span data-ttu-id="8d322-605">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="8d322-605">SALARYCHANGE</span></span>           | <span data-ttu-id="8d322-606">Modification du salaire</span><span class="sxs-lookup"><span data-stu-id="8d322-606">Change of Salary</span></span>               | <span data-ttu-id="8d322-607">Rémunération</span><span class="sxs-lookup"><span data-stu-id="8d322-607">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="8d322-608">Conditions d’emploi</span><span class="sxs-lookup"><span data-stu-id="8d322-608">Terms of employment</span></span>

<span data-ttu-id="8d322-609">Les conditions d’emploi sont utilisées pour créer des catégories de conditions d’emploi.</span><span class="sxs-lookup"><span data-stu-id="8d322-609">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="8d322-610">Les conditions sont mises en correspondance avec Dayforce en tant que valeurs d’indicateur d’emploi.</span><span class="sxs-lookup"><span data-stu-id="8d322-610">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="8d322-611">Les conditions d’emploi et descriptions suivantes sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="8d322-611">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="8d322-612">Conditions d’emploi</span><span class="sxs-lookup"><span data-stu-id="8d322-612">Terms of employment</span></span>   | <span data-ttu-id="8d322-613">Description</span><span class="sxs-lookup"><span data-stu-id="8d322-613">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="8d322-614">Régulier</span><span class="sxs-lookup"><span data-stu-id="8d322-614">Regular</span></span>               | <span data-ttu-id="8d322-615">Régulier</span><span class="sxs-lookup"><span data-stu-id="8d322-615">Regular</span></span>     |
| <span data-ttu-id="8d322-616">Direct</span><span class="sxs-lookup"><span data-stu-id="8d322-616">Direct</span></span>                | <span data-ttu-id="8d322-617">Direct</span><span class="sxs-lookup"><span data-stu-id="8d322-617">Direct</span></span>      |
| <span data-ttu-id="8d322-618">Stage</span><span class="sxs-lookup"><span data-stu-id="8d322-618">Internship</span></span>            | <span data-ttu-id="8d322-619">Stage</span><span class="sxs-lookup"><span data-stu-id="8d322-619">Internship</span></span>  |
| <span data-ttu-id="8d322-620">Permanent</span><span class="sxs-lookup"><span data-stu-id="8d322-620">Permanent</span></span>             | <span data-ttu-id="8d322-621">Permanent</span><span class="sxs-lookup"><span data-stu-id="8d322-621">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="8d322-622">Situation de famille</span><span class="sxs-lookup"><span data-stu-id="8d322-622">Marital status</span></span>

<span data-ttu-id="8d322-623">Les valeurs de situation de famille sont mises en correspondance avec Dayforce et traduite, au besoin, dans les valeurs acceptées lors de l’intégration.</span><span class="sxs-lookup"><span data-stu-id="8d322-623">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="8d322-624">Le tableau suivant montre comment les valeurs de situation de famille sont mises en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8d322-624">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="8d322-625">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="8d322-625">Human Resources</span></span>                 | <span data-ttu-id="8d322-626">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8d322-626">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="8d322-627">Marié</span><span class="sxs-lookup"><span data-stu-id="8d322-627">Married</span></span>                | <span data-ttu-id="8d322-628">Marié</span><span class="sxs-lookup"><span data-stu-id="8d322-628">Married</span></span>                   |
| <span data-ttu-id="8d322-629">Unique</span><span class="sxs-lookup"><span data-stu-id="8d322-629">Single</span></span>                 | <span data-ttu-id="8d322-630">Unique</span><span class="sxs-lookup"><span data-stu-id="8d322-630">Single</span></span>                    |
| <span data-ttu-id="8d322-631">Veuf</span><span class="sxs-lookup"><span data-stu-id="8d322-631">Widowed</span></span>                | <span data-ttu-id="8d322-632">Veuf</span><span class="sxs-lookup"><span data-stu-id="8d322-632">Widowed</span></span>                   |
| <span data-ttu-id="8d322-633">Divorcé</span><span class="sxs-lookup"><span data-stu-id="8d322-633">Divorced</span></span>               | <span data-ttu-id="8d322-634">Divorcé</span><span class="sxs-lookup"><span data-stu-id="8d322-634">Divorced</span></span>                  |
| <span data-ttu-id="8d322-635">Partenariat enregistré</span><span class="sxs-lookup"><span data-stu-id="8d322-635">Registered Partnership</span></span> | <span data-ttu-id="8d322-636">Partenariat local</span><span class="sxs-lookup"><span data-stu-id="8d322-636">Domestic Partnership</span></span>      |
| <span data-ttu-id="8d322-637">None</span><span class="sxs-lookup"><span data-stu-id="8d322-637">None</span></span>                   | <span data-ttu-id="8d322-638">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="8d322-638">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="8d322-639">Concubinage</span><span class="sxs-lookup"><span data-stu-id="8d322-639">Cohabiting</span></span>             | <span data-ttu-id="8d322-640">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="8d322-640">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="8d322-641">Sexe</span><span class="sxs-lookup"><span data-stu-id="8d322-641">Gender</span></span>

<span data-ttu-id="8d322-642">Le sexe est mis en correspondance avec Dayforce et traduit, au besoin, dans les valeurs acceptées lors de l’intégration.</span><span class="sxs-lookup"><span data-stu-id="8d322-642">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="8d322-643">Le tableau suivant montre comment le sexe est mis en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8d322-643">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="8d322-644">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="8d322-644">Human Resources</span></span>       | <span data-ttu-id="8d322-645">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8d322-645">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="8d322-646">Masculin</span><span class="sxs-lookup"><span data-stu-id="8d322-646">Male</span></span>         | <span data-ttu-id="8d322-647">Masculin</span><span class="sxs-lookup"><span data-stu-id="8d322-647">Male</span></span>                      |
| <span data-ttu-id="8d322-648">Féminin</span><span class="sxs-lookup"><span data-stu-id="8d322-648">Female</span></span>       | <span data-ttu-id="8d322-649">Féminin</span><span class="sxs-lookup"><span data-stu-id="8d322-649">Female</span></span>                    |
| <span data-ttu-id="8d322-650">Non spécifique</span><span class="sxs-lookup"><span data-stu-id="8d322-650">Non-specific</span></span> | <span data-ttu-id="8d322-651">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="8d322-651">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="8d322-652">Mode de paiement</span><span class="sxs-lookup"><span data-stu-id="8d322-652">Payment method</span></span>

<span data-ttu-id="8d322-653">Les modes de paiement fournissent à l’employé et à la société une manière de décrire la façon dont les employés sont payés.</span><span class="sxs-lookup"><span data-stu-id="8d322-653">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="8d322-654">Les modes de paiement sont mis en correspondance avec Dayforce et traduit, au besoin, dans les valeurs acceptées lors de l’intégration.</span><span class="sxs-lookup"><span data-stu-id="8d322-654">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="8d322-655">Le tableau suivant montre comment les modes de paiement sont mis en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8d322-655">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="8d322-656">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="8d322-656">Human Resources</span></span>             | <span data-ttu-id="8d322-657">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8d322-657">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="8d322-658">Argent comptant</span><span class="sxs-lookup"><span data-stu-id="8d322-658">Cash</span></span>               | <span data-ttu-id="8d322-659">Argent comptant</span><span class="sxs-lookup"><span data-stu-id="8d322-659">Cash</span></span>                      |
| <span data-ttu-id="8d322-660">Paiement électronique</span><span class="sxs-lookup"><span data-stu-id="8d322-660">Electronic Payment</span></span> | <span data-ttu-id="8d322-661">Transférer</span><span class="sxs-lookup"><span data-stu-id="8d322-661">Transfer</span></span>                  |
| <span data-ttu-id="8d322-662">Vérification</span><span class="sxs-lookup"><span data-stu-id="8d322-662">Check</span></span>              | <span data-ttu-id="8d322-663">Chèque</span><span class="sxs-lookup"><span data-stu-id="8d322-663">Cheque</span></span>                    |
| <span data-ttu-id="8d322-664">Traites bancaires</span><span class="sxs-lookup"><span data-stu-id="8d322-664">Bank Draft</span></span>         | <span data-ttu-id="8d322-665">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="8d322-665">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="8d322-666">Autre/s</span><span class="sxs-lookup"><span data-stu-id="8d322-666">Other</span></span>              | <span data-ttu-id="8d322-667">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="8d322-667">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="8d322-668">Type de compte bancaire</span><span class="sxs-lookup"><span data-stu-id="8d322-668">Bank account type</span></span>

<span data-ttu-id="8d322-669">Les types de comptes bancaires sont utilisés pour les paiements électroniques aux employés.</span><span class="sxs-lookup"><span data-stu-id="8d322-669">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="8d322-670">Les types de comptes bancaires sont mis en correspondance avec Dayforce tant qu’informations de compte de transfert.</span><span class="sxs-lookup"><span data-stu-id="8d322-670">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="8d322-671">Les types de comptes bancaires sont traduits, au besoin, dans des valeurs acceptées lors de l’intégration.</span><span class="sxs-lookup"><span data-stu-id="8d322-671">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="8d322-672">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="8d322-672">Human Resources</span></span>            | <span data-ttu-id="8d322-673">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8d322-673">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="8d322-674">Compte courant</span><span class="sxs-lookup"><span data-stu-id="8d322-674">Checking Account</span></span>  | <span data-ttu-id="8d322-675">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="8d322-675">CheckingAccount</span></span>           |
| <span data-ttu-id="8d322-676">Compte de paie</span><span class="sxs-lookup"><span data-stu-id="8d322-676">Payroll Account</span></span>   | <span data-ttu-id="8d322-677">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="8d322-677">PayrollAccount</span></span>            |
| <span data-ttu-id="8d322-678">Compte d’épargne</span><span class="sxs-lookup"><span data-stu-id="8d322-678">Savings Account</span></span>   | <span data-ttu-id="8d322-679">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="8d322-679">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="8d322-680">Compte BankGirot</span><span class="sxs-lookup"><span data-stu-id="8d322-680">BankGirot account</span></span> | <span data-ttu-id="8d322-681">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="8d322-681">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="8d322-682">Compte PlusGirot</span><span class="sxs-lookup"><span data-stu-id="8d322-682">PlusGirot account</span></span> | <span data-ttu-id="8d322-683">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="8d322-683">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="8d322-684">Codes de rémunérations</span><span class="sxs-lookup"><span data-stu-id="8d322-684">Earning codes</span></span>

<span data-ttu-id="8d322-685">Les codes de rémunérations identifient de manière unique chaque type de revenus que les collaborateurs reçoivent.</span><span class="sxs-lookup"><span data-stu-id="8d322-685">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="8d322-686">Les codes couvrent différents paramètres associés aux revenus, tels que des règles comptables, des lois fiscales, des conditions de génération d’états, et la capacité de montant brut.</span><span class="sxs-lookup"><span data-stu-id="8d322-686">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="8d322-687">Si une fréquence non prise en charge est utilisée, la fréquence **Chaque paie** est utilisée par défaut pour le calcul.</span><span class="sxs-lookup"><span data-stu-id="8d322-687">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="8d322-688">Fréquences prises en charge</span><span class="sxs-lookup"><span data-stu-id="8d322-688">Supported frequencies</span></span>

- <span data-ttu-id="8d322-689">Tous</span><span class="sxs-lookup"><span data-stu-id="8d322-689">All</span></span>
- <span data-ttu-id="8d322-690">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="8d322-690">EVERYPAY</span></span>
- <span data-ttu-id="8d322-691">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="8d322-691">EACHPAYPERIOD</span></span>
- <span data-ttu-id="8d322-692">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="8d322-692">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="8d322-693">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="8d322-693">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="8d322-694">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-694">1OFMTH</span></span>
- <span data-ttu-id="8d322-695">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-695">LASTOFMTH</span></span>
- <span data-ttu-id="8d322-696">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-696">2OFMTH</span></span>
- <span data-ttu-id="8d322-697">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-697">3OFMTH</span></span>
- <span data-ttu-id="8d322-698">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-698">4OFMTH</span></span>
- <span data-ttu-id="8d322-699">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-699">5OFMTH</span></span>
- <span data-ttu-id="8d322-700">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-700">1N2OFMTH</span></span>
- <span data-ttu-id="8d322-701">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-701">3N4OFMTH</span></span>
- <span data-ttu-id="8d322-702">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-702">1N3OFMTH</span></span>
- <span data-ttu-id="8d322-703">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-703">1N4OFMTH</span></span>
- <span data-ttu-id="8d322-704">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-704">2N3OFMTH</span></span>
- <span data-ttu-id="8d322-705">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-705">2N4OFMTH</span></span>
- <span data-ttu-id="8d322-706">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-706">1N2N3OFMTH</span></span>
- <span data-ttu-id="8d322-707">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-707">1N2N4OFMTH</span></span>
- <span data-ttu-id="8d322-708">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-708">1N3N4OFMTH</span></span>
- <span data-ttu-id="8d322-709">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-709">2N3N4OFMTH</span></span>
- <span data-ttu-id="8d322-710">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8d322-710">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="8d322-711">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="8d322-711">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="8d322-712">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="8d322-712">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="8d322-713">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="8d322-713">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="8d322-714">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="8d322-714">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="8d322-715">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="8d322-715">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="8d322-716">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="8d322-716">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="8d322-717">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="8d322-717">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="8d322-718">Adresses</span><span class="sxs-lookup"><span data-stu-id="8d322-718">Addresses</span></span>

<span data-ttu-id="8d322-719">L’identification d’un pays ou d’une région, d’un état, et des codes département (municipalité) spécifiques nécessite des formats spécifiques que les fournisseurs Dayforce et dans le pays/la région peuvent identifier.</span><span class="sxs-lookup"><span data-stu-id="8d322-719">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="8d322-720">Bien que le format pour les villes soit flexible, chaque ville doit être associée à un état.</span><span class="sxs-lookup"><span data-stu-id="8d322-720">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="8d322-721">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="8d322-721">Human Resources</span></span>              | <span data-ttu-id="8d322-722">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8d322-722">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="8d322-723">Pays/région</span><span class="sxs-lookup"><span data-stu-id="8d322-723">Country/Region</span></span>      | <span data-ttu-id="8d322-724">Code pays</span><span class="sxs-lookup"><span data-stu-id="8d322-724">Country Code</span></span>          |
| <span data-ttu-id="8d322-725">Code postal</span><span class="sxs-lookup"><span data-stu-id="8d322-725">Zip/Postal Code</span></span>     | <span data-ttu-id="8d322-726">Code postal</span><span class="sxs-lookup"><span data-stu-id="8d322-726">Postal Code</span></span>           |
| <span data-ttu-id="8d322-727">État</span><span class="sxs-lookup"><span data-stu-id="8d322-727">State</span></span>               | <span data-ttu-id="8d322-728">Code région</span><span class="sxs-lookup"><span data-stu-id="8d322-728">State Code</span></span>            |
| <span data-ttu-id="8d322-729">Ville</span><span class="sxs-lookup"><span data-stu-id="8d322-729">City</span></span>                | <span data-ttu-id="8d322-730">Ville</span><span class="sxs-lookup"><span data-stu-id="8d322-730">City</span></span>                  |
| <span data-ttu-id="8d322-731">Commune</span><span class="sxs-lookup"><span data-stu-id="8d322-731">County</span></span>              | <span data-ttu-id="8d322-732">Département (municipalité)</span><span class="sxs-lookup"><span data-stu-id="8d322-732">County (Municipality)</span></span> |
| <span data-ttu-id="8d322-733">Rue</span><span class="sxs-lookup"><span data-stu-id="8d322-733">Street</span></span>              | <span data-ttu-id="8d322-734">Ligne d’adresse 1</span><span class="sxs-lookup"><span data-stu-id="8d322-734">Address Line 1</span></span>        |
| <span data-ttu-id="8d322-735">Numéro de la rue</span><span class="sxs-lookup"><span data-stu-id="8d322-735">Street Number</span></span>       | <span data-ttu-id="8d322-736">Ligne d’adresse 2</span><span class="sxs-lookup"><span data-stu-id="8d322-736">Address Line 2</span></span>        |
| <span data-ttu-id="8d322-737">Info complémentaire sur le bâtiment</span><span class="sxs-lookup"><span data-stu-id="8d322-737">Building Complement</span></span> | <span data-ttu-id="8d322-738">Ligne d’adresse 5</span><span class="sxs-lookup"><span data-stu-id="8d322-738">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="8d322-739">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="8d322-739">Passport number</span></span>

<span data-ttu-id="8d322-740">Les employés peuvent déclarer des informations de passeport.</span><span class="sxs-lookup"><span data-stu-id="8d322-740">Employees can declare passport information.</span></span> <span data-ttu-id="8d322-741">Ces informations sont de type d’identification **Passeport** et sont intégrées à Dayforce dans le cadre des informations spécifique au Mexique d’un employé.</span><span class="sxs-lookup"><span data-stu-id="8d322-741">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="8d322-742">Type d’identification = « Passeport »</span><span class="sxs-lookup"><span data-stu-id="8d322-742">Identification Type = "Passport"</span></span>
- <span data-ttu-id="8d322-743">Date d’émission</span><span class="sxs-lookup"><span data-stu-id="8d322-743">Issued Date</span></span>
- <span data-ttu-id="8d322-744">Date d’expiration</span><span class="sxs-lookup"><span data-stu-id="8d322-744">Expiration Date</span></span>

<span data-ttu-id="8d322-745">Les employés peuvent déclarer plusieurs numéros d’identification de type d’identification **Passeport**.</span><span class="sxs-lookup"><span data-stu-id="8d322-745">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="8d322-746">Toutefois, seule la saisie de passeport actif actuel est intégrée à Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8d322-746">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="8d322-747">Si toutes les entrées de passeport sont arrivées à expiration, le passeport émis le plus récemment est intégré dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8d322-747">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]