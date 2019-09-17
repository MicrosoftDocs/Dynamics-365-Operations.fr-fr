---
title: Configuration de l'intégration de la paie entre Talent et Dayforce
description: Cette rubrique explique comment configurer l'intégration entre Microsoft Dynamics 365 for Talent et Ceridian Dayforce afin de pouvoir traiter un cycle de paie.
author: andreabichsel
manager: AnnBe
ms.date: 06/24/2019
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
ms.openlocfilehash: c26dfed9909b0dbd05fc18c206e5adc947feaef5
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742910"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="502ff-103">Configurer l'intégration de la paie entre Talent et Dayforce</span><span class="sxs-lookup"><span data-stu-id="502ff-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="502ff-104">L'intégration entre Microsoft Dynamics 365 for Talent et Ceridian Dayforce repose sur plusieurs étapes de configuration décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="502ff-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="502ff-105">Vous devez configurer l'intégration dans Talent et Dayforce avant de pouvoir traiter un cycle de paie.</span><span class="sxs-lookup"><span data-stu-id="502ff-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="502ff-106">Lorsque vous utilisez un service comme Dayforce pour compléter des cycles de paie, vous devez activer l'intégration dans Talent.</span><span class="sxs-lookup"><span data-stu-id="502ff-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="502ff-107">L'intégration nécessite des données spécifiques de Talent.</span><span class="sxs-lookup"><span data-stu-id="502ff-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="502ff-108">Par conséquent, vous devez vérifier que les données mises en correspondance avec Dayforce sont configurées dans Talent d'une manière prenant en charge l'intégration.</span><span class="sxs-lookup"><span data-stu-id="502ff-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="502ff-109">L'intégration utilise les larges catégories de données suivantes :</span><span class="sxs-lookup"><span data-stu-id="502ff-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="502ff-110">Données de ressources humaines</span><span class="sxs-lookup"><span data-stu-id="502ff-110">Human resources data</span></span>
- <span data-ttu-id="502ff-111">Données de rémunération</span><span class="sxs-lookup"><span data-stu-id="502ff-111">Compensation data</span></span>
- <span data-ttu-id="502ff-112">Données salariales, telles que des cycles de paie, des périodes de rémunération, et des codes de rémunération</span><span class="sxs-lookup"><span data-stu-id="502ff-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="502ff-113">Données sur les collaborateurs</span><span class="sxs-lookup"><span data-stu-id="502ff-113">Worker data</span></span>

<span data-ttu-id="502ff-114">Cette rubrique décrit la procédure à suivre pour activer l'intégration.</span><span class="sxs-lookup"><span data-stu-id="502ff-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="502ff-115">Elle décrit également les types de données et les détails de configuration que l'intégration nécessite.</span><span class="sxs-lookup"><span data-stu-id="502ff-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="502ff-116">Activer l'intégration</span><span class="sxs-lookup"><span data-stu-id="502ff-116">Enable the integration</span></span>

<span data-ttu-id="502ff-117">Dans Talent, vous devez activer l'intégration et entrer des informations de configuration pour vous connecter Dayforce.</span><span class="sxs-lookup"><span data-stu-id="502ff-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="502ff-118">Si vous souhaitez que l'écriture comptable produite soit importée dans Microsoft Dynamics 365 for Finance and Operations, vous devez également configurer un compte de stockage Microsoft Azure et entrer la chaîne de connexion de stockage Azure dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="502ff-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="502ff-119">Pour l'activer l'intégration dans Talent, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="502ff-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="502ff-120">Sur la page **Administration du système**, sélectionnez **Configuration de l'intégration**.</span><span class="sxs-lookup"><span data-stu-id="502ff-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="502ff-121">Entrez le point de terminaison FTP (File Transfer Protocol) sécurisé et le chemin d'accès de dossier FTP sécurisé.</span><span class="sxs-lookup"><span data-stu-id="502ff-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="502ff-122">Entrez le nom d'utilisateur et le mot de passe de l'utilisateur qui accèdera au point de terminaison FTP et au chemin d'accès du dossier sécurisés.</span><span class="sxs-lookup"><span data-stu-id="502ff-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="502ff-123">Testez la connexion, au besoin, puis définissez l'option **Activation de l'intégration de la paie** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="502ff-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="502ff-124">Lorsque l'intégration est activée, le package et les fichiers d'exportation de données sont créés, et la fréquence est définie.</span><span class="sxs-lookup"><span data-stu-id="502ff-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="502ff-125">Vous pouvez modifier la fréquence selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="502ff-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="502ff-126">Pour plus d'informations sur les comptes de stockage Azure et les chaînes de connexion de stockage Azure, consultez les rubriques Azure suivantes :</span><span class="sxs-lookup"><span data-stu-id="502ff-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="502ff-127">À propos des comptes de stockage Azure</span><span class="sxs-lookup"><span data-stu-id="502ff-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="502ff-128">Configurer les chaînes de connexion de stockage Azure</span><span class="sxs-lookup"><span data-stu-id="502ff-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="502ff-129">Détails techniques lorsque l'intégration de la paie est activée</span><span class="sxs-lookup"><span data-stu-id="502ff-129">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="502ff-130">Activer l'intégration de la paie a deux principaux effets :</span><span class="sxs-lookup"><span data-stu-id="502ff-130">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="502ff-131">Un projet d'exportation de données nommé « Exportation de l'intégration de la paie » est créé.</span><span class="sxs-lookup"><span data-stu-id="502ff-131">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="502ff-132">Ce projet contient les entités et les champs nécessaires pour l'intégration de la paie.</span><span class="sxs-lookup"><span data-stu-id="502ff-132">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="502ff-133">Pour examiner le projet, accédez à **Administration système**, sélectionnez la vignette **Gestion des données**, puis ouvrez le projet à partir de la liste de projets.</span><span class="sxs-lookup"><span data-stu-id="502ff-133">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="502ff-134">Ce traitement par lots exécute le projet d'exportation de données, chiffre le package de données obtenues, et transfère le fichier de package de données au point de terminaison SFTP configuré dans l'écran **Configuration de l'intégration**.</span><span class="sxs-lookup"><span data-stu-id="502ff-134">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="502ff-135">Le package de données transféré au point de terminaison SFTP est chiffré à l'aide d'une clé unique dans le module.</span><span class="sxs-lookup"><span data-stu-id="502ff-135">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="502ff-136">Cette clé est dans un coffre Azure Key Vault qui n'est accessible que par Ceridian.</span><span class="sxs-lookup"><span data-stu-id="502ff-136">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="502ff-137">Il est impossible de déchiffrer et examiner le contenu du package de données.</span><span class="sxs-lookup"><span data-stu-id="502ff-137">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="502ff-138">Si vous devez examiner le contenu du package de données, vous devez exporter le projet de données « Exportation de l'intégration de la paie » manuellement, le télécharger, puis l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="502ff-138">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="502ff-139">L'exportation manuelle n'appliquera pas de chiffrement ou de transfert au package.</span><span class="sxs-lookup"><span data-stu-id="502ff-139">Manual export will not apply encryption or transfer the package.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="502ff-140">Configurer vos données</span><span class="sxs-lookup"><span data-stu-id="502ff-140">Configure your data</span></span> 

<span data-ttu-id="502ff-141">Pour traiter les paies, vous devez configurer les données des ressources humaines dans Talent.</span><span class="sxs-lookup"><span data-stu-id="502ff-141">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="502ff-142">Vous devez configurer les données organisationnelles, telles que les tâches et les postes, ainsi que les avantages et les informations de rémunération.</span><span class="sxs-lookup"><span data-stu-id="502ff-142">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="502ff-143">Ces informations fournissent des informations sur l'emploi, le salaire et les déductions nécessaires pour générer le salaire de l'employé.</span><span class="sxs-lookup"><span data-stu-id="502ff-143">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="502ff-144">Données des ressources humaines</span><span class="sxs-lookup"><span data-stu-id="502ff-144">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="502ff-145">Avantages</span><span class="sxs-lookup"><span data-stu-id="502ff-145">Benefits</span></span> 

<span data-ttu-id="502ff-146">Les ressources humaines proposent des outils de paramétrage et de mise à jour des avantages, des déductions et des plans de compensation des collaborateurs qu'une organisation offre ou gère pour ses collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="502ff-146">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="502ff-147">Lorsque vous créez des avantages, n'oubliez pas les données et les configurations suivantes utilisées dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="502ff-147">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="502ff-148">Plans d'avantages</span><span class="sxs-lookup"><span data-stu-id="502ff-148">Benefit plans</span></span>

- <span data-ttu-id="502ff-149">Plan (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-149">Plan (required)</span></span>
- <span data-ttu-id="502ff-150">Type (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-150">Type (required)</span></span>
- <span data-ttu-id="502ff-151">Impact sur la paie (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-151">Payroll impact (required)</span></span>
- <span data-ttu-id="502ff-152">Recouvrer les arriérés</span><span class="sxs-lookup"><span data-stu-id="502ff-152">Recover arrears</span></span>
- <span data-ttu-id="502ff-153">Méthode de déduction</span><span class="sxs-lookup"><span data-stu-id="502ff-153">Deduction method</span></span>
- <span data-ttu-id="502ff-154">Priorité de la déduction</span><span class="sxs-lookup"><span data-stu-id="502ff-154">Deduction priority</span></span>
- <span data-ttu-id="502ff-155">Période limite</span><span class="sxs-lookup"><span data-stu-id="502ff-155">Limit period</span></span>
- <span data-ttu-id="502ff-156">Montant limite</span><span class="sxs-lookup"><span data-stu-id="502ff-156">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="502ff-157">Avantages</span><span class="sxs-lookup"><span data-stu-id="502ff-157">Benefits</span></span>

- <span data-ttu-id="502ff-158">Plan (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-158">Plan (required)</span></span>
- <span data-ttu-id="502ff-159">Type (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-159">Type (required)</span></span>
- <span data-ttu-id="502ff-160">Option (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-160">Option (required)</span></span>
- <span data-ttu-id="502ff-161">ID avantage (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-161">Benefit ID (required)</span></span>
- <span data-ttu-id="502ff-162">Fréquence</span><span class="sxs-lookup"><span data-stu-id="502ff-162">Frequency</span></span>
- <span data-ttu-id="502ff-163">Base</span><span class="sxs-lookup"><span data-stu-id="502ff-163">Basis</span></span>
- <span data-ttu-id="502ff-164">Montant ou taux</span><span class="sxs-lookup"><span data-stu-id="502ff-164">Amount or rate</span></span>
- <span data-ttu-id="502ff-165">Code de rémunération</span><span class="sxs-lookup"><span data-stu-id="502ff-165">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="502ff-166">Fréquences prises en charge</span><span class="sxs-lookup"><span data-stu-id="502ff-166">Supported frequencies</span></span> 

- <span data-ttu-id="502ff-167">Hebdomadairement</span><span class="sxs-lookup"><span data-stu-id="502ff-167">Weekly</span></span>
- <span data-ttu-id="502ff-168">Bimensuelle</span><span class="sxs-lookup"><span data-stu-id="502ff-168">Bi-weekly</span></span>
- <span data-ttu-id="502ff-169">Bimensuel</span><span class="sxs-lookup"><span data-stu-id="502ff-169">Semi-monthly</span></span>
- <span data-ttu-id="502ff-170">Mensuellement</span><span class="sxs-lookup"><span data-stu-id="502ff-170">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="502ff-171">Bases pris en charge</span><span class="sxs-lookup"><span data-stu-id="502ff-171">Supported bases</span></span> 

- <span data-ttu-id="502ff-172">Montant fixe</span><span class="sxs-lookup"><span data-stu-id="502ff-172">Fixed amount</span></span>
- <span data-ttu-id="502ff-173">Pourcentage des rémunérations</span><span class="sxs-lookup"><span data-stu-id="502ff-173">Percent of earnings</span></span>
- <span data-ttu-id="502ff-174">Heures productives</span><span class="sxs-lookup"><span data-stu-id="502ff-174">Productive hours</span></span>

<span data-ttu-id="502ff-175">Dayforce crée les déductions suivantes, selon l'impact sur la paie défini dans le plan d'avantages.</span><span class="sxs-lookup"><span data-stu-id="502ff-175">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="502ff-176">Sélection dans Talent</span><span class="sxs-lookup"><span data-stu-id="502ff-176">Selection in Talent</span></span>        | <span data-ttu-id="502ff-177">Résultat dans Dayforce</span><span class="sxs-lookup"><span data-stu-id="502ff-177">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="502ff-178">None</span><span class="sxs-lookup"><span data-stu-id="502ff-178">None</span></span>                       | <span data-ttu-id="502ff-179">Aucune retenue n'est créée.</span><span class="sxs-lookup"><span data-stu-id="502ff-179">No deduction is created.</span></span>                      |
| <span data-ttu-id="502ff-180">Déduction uniquement</span><span class="sxs-lookup"><span data-stu-id="502ff-180">Deduction only</span></span>             | <span data-ttu-id="502ff-181">Une retenue employé est créée.</span><span class="sxs-lookup"><span data-stu-id="502ff-181">An employee deduction is created.</span></span>             |
| <span data-ttu-id="502ff-182">Contribution uniquement</span><span class="sxs-lookup"><span data-stu-id="502ff-182">Contribution only</span></span>          | <span data-ttu-id="502ff-183">Une retenue employeur est créée.</span><span class="sxs-lookup"><span data-stu-id="502ff-183">An employer deduction is created.</span></span>             |
| <span data-ttu-id="502ff-184">Déduction et contribution</span><span class="sxs-lookup"><span data-stu-id="502ff-184">Deduction and contribution</span></span> | <span data-ttu-id="502ff-185">Des retenues employé et employeur sont créées.</span><span class="sxs-lookup"><span data-stu-id="502ff-185">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="502ff-186">Pour plus d'informations sur la définition et la gestion des programmes d'avantages, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="502ff-186">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="502ff-187">Communiquer le programme d'avantages à un employé</span><span class="sxs-lookup"><span data-stu-id="502ff-187">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="502ff-188">Créer un avantage</span><span class="sxs-lookup"><span data-stu-id="502ff-188">Create a new benefit</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="502ff-189">Définir les règles d'admissibilité et les stratégies relatives aux avantages</span><span class="sxs-lookup"><span data-stu-id="502ff-189">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="502ff-190">Inscrire et annuler l'inscription des travailleurs à des avantages</span><span class="sxs-lookup"><span data-stu-id="502ff-190">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="502ff-191">Rémunération</span><span class="sxs-lookup"><span data-stu-id="502ff-191">Compensation</span></span> 

<span data-ttu-id="502ff-192">La gestion des rémunérations est utilisée pour contrôler la rémunération de base et les primes.</span><span class="sxs-lookup"><span data-stu-id="502ff-192">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="502ff-193">Le salaire de base fixe et les augmentations pour mérite d'un employé sont contrôlés via les régimes de rémunération fixe.</span><span class="sxs-lookup"><span data-stu-id="502ff-193">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="502ff-194">Le paiement des primes (primes liées aux résultats, options d'achat d'actions et octrois d'actions), ainsi que les primes exceptionnelles, est contrôlé via les régimes de rémunération variable.</span><span class="sxs-lookup"><span data-stu-id="502ff-194">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="502ff-195">Dayforce utilise les informations de rémunération pour calculer le taux horaire ou annuel d'un employé.</span><span class="sxs-lookup"><span data-stu-id="502ff-195">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="502ff-196">Des plans de rémunération fixe et des conversions de taux de salaire sont requis.</span><span class="sxs-lookup"><span data-stu-id="502ff-196">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="502ff-197">Les employés doivent être associés à un plan de rémunération fixe.</span><span class="sxs-lookup"><span data-stu-id="502ff-197">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="502ff-198">Pour plus d'informations sur les plans de rémunération, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="502ff-198">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="502ff-199">Créer des régimes de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="502ff-199">Create fixed compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="502ff-200">Créer des régimes de rémunération variable</span><span class="sxs-lookup"><span data-stu-id="502ff-200">Create variable compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="502ff-201">Développer les plans et la structure du salaire/de la rémunération</span><span class="sxs-lookup"><span data-stu-id="502ff-201">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="502ff-202">Traiter la rémunération</span><span class="sxs-lookup"><span data-stu-id="502ff-202">Process compensation</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="502ff-203">Définir le processus de rémunération et calculer les résultats</span><span class="sxs-lookup"><span data-stu-id="502ff-203">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="502ff-204">Inscrire un employé à un régime de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="502ff-204">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="502ff-205">Inscrire un employé à un régime de rémunération variable</span><span class="sxs-lookup"><span data-stu-id="502ff-205">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="502ff-206">Postes</span><span class="sxs-lookup"><span data-stu-id="502ff-206">Jobs</span></span> 

<span data-ttu-id="502ff-207">Une tâche est un ensemble de tâches et de responsabilités attribuées à la personne affectée à la tâche.</span><span class="sxs-lookup"><span data-stu-id="502ff-207">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="502ff-208">Pour plus d'informations, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="502ff-208">For more information, see the following topics:</span></span>

- [<span data-ttu-id="502ff-209">Paramétrage des composants d'une tâche</span><span class="sxs-lookup"><span data-stu-id="502ff-209">Setting up the components of a job</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="502ff-210">Définir les nouvelles tâches</span><span class="sxs-lookup"><span data-stu-id="502ff-210">Define new jobs</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="502ff-211">Postes</span><span class="sxs-lookup"><span data-stu-id="502ff-211">Positions</span></span>

<span data-ttu-id="502ff-212">Un poste est une instance individuelle d'une tâche.</span><span class="sxs-lookup"><span data-stu-id="502ff-212">A position is an individual instance of a job.</span></span> <span data-ttu-id="502ff-213">Par exemple, le poste « Responsable des ventes (est) » est l'un des postes associés à la tâche « Responsable des ventes ».</span><span class="sxs-lookup"><span data-stu-id="502ff-213">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="502ff-214">Un poste existe dans un département.</span><span class="sxs-lookup"><span data-stu-id="502ff-214">A position exists in a department.</span></span> <span data-ttu-id="502ff-215">Seul un collaborateur peut être associé à chaque poste.</span><span class="sxs-lookup"><span data-stu-id="502ff-215">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="502ff-216">Gardez à l'esprit les données et la configuration suivantes lorsque vous paramétrez des postes :</span><span class="sxs-lookup"><span data-stu-id="502ff-216">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="502ff-217">Poste (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-217">Position (required)</span></span>
- <span data-ttu-id="502ff-218">Description (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-218">Description (required)</span></span>
- <span data-ttu-id="502ff-219">Tâche (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-219">Job (required)</span></span>
- <span data-ttu-id="502ff-220">Département (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-220">Department (required)</span></span>
- <span data-ttu-id="502ff-221">Type de poste (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-221">Position type (required)</span></span>
- <span data-ttu-id="502ff-222">Équivalent temps plein</span><span class="sxs-lookup"><span data-stu-id="502ff-222">Full-time equivalent</span></span>
- <span data-ttu-id="502ff-223">Durée annuelle normale (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-223">Annual regular hours (required)</span></span>
- <span data-ttu-id="502ff-224">Rémunéré par l'entité juridique (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-224">Paid by legal entity (required)</span></span>
- <span data-ttu-id="502ff-225">Cycle de paie (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-225">Pay cycle (required)</span></span>
- <span data-ttu-id="502ff-226">Dimension financière par défaut – Centre de coût (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-226">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="502ff-227">Affectation du collaborateur – Collaborateur, début de l'affectation, fin de l'affectation, code motif</span><span class="sxs-lookup"><span data-stu-id="502ff-227">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="502ff-228">Si plusieurs postes dans un même département sont associés à la même tâche, ils sont consolidés un seul poste dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="502ff-228">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="502ff-229">Pour plus d'informations, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="502ff-229">For more information, see the following topics:</span></span>

- [<span data-ttu-id="502ff-230">Organisation du personnel à l'aide des départements, tâches et postes</span><span class="sxs-lookup"><span data-stu-id="502ff-230">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="502ff-231">Paramétrer les postes</span><span class="sxs-lookup"><span data-stu-id="502ff-231">Set up positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="502ff-232">Départements</span><span class="sxs-lookup"><span data-stu-id="502ff-232">Departments</span></span>

<span data-ttu-id="502ff-233">Un département est une unité opérationnelle qui représente une catégorie ou un domaine fonctionnel d'une organisation.</span><span class="sxs-lookup"><span data-stu-id="502ff-233">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="502ff-234">Un département est responsable d'un domaine spécifique de l'organisation, par exemple les ventes, la comptabilité ou les ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="502ff-234">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="502ff-235">Les départements vous permettent de générer des états sur les domaines fonctionnels.</span><span class="sxs-lookup"><span data-stu-id="502ff-235">You can use departments to report on functional areas.</span></span> <span data-ttu-id="502ff-236">Les départements peuvent avoir la responsabilité des résultats.</span><span class="sxs-lookup"><span data-stu-id="502ff-236">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="502ff-237">Pour plus d'informations, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="502ff-237">For more information, see the following topics:</span></span>

- [<span data-ttu-id="502ff-238">Créer un département et l'associer à la hiérarchie des départements</span><span class="sxs-lookup"><span data-stu-id="502ff-238">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="502ff-239">Définir les nouveaux départements</span><span class="sxs-lookup"><span data-stu-id="502ff-239">Define new departments</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="502ff-240">Cycles de paie et périodes de rémunération</span><span class="sxs-lookup"><span data-stu-id="502ff-240">Pay cycles and pay periods</span></span>

<span data-ttu-id="502ff-241">Un cycle de paie détermine la fréquence d'exécution de la paie et les jours spécifiques où les collaborateurs sont payés.</span><span class="sxs-lookup"><span data-stu-id="502ff-241">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="502ff-242">Par exemple, un cycle de paie peut être mensuel, et les employés peuvent être payés le dernier jour du mois.</span><span class="sxs-lookup"><span data-stu-id="502ff-242">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="502ff-243">Sinon, un cycle de paie peut être hebdomadaire, et les employés peuvent être payés le mardi après la fin de la période de rémunération.</span><span class="sxs-lookup"><span data-stu-id="502ff-243">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="502ff-244">Les cycles de paie sont affectés aux postes afin de contrôler à quel moment les collaborateurs à ces postes sont payés.</span><span class="sxs-lookup"><span data-stu-id="502ff-244">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="502ff-245">Après avoir créé des cycles de paie, vous pouvez générer des périodes de rémunération pour chaque cycle.</span><span class="sxs-lookup"><span data-stu-id="502ff-245">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="502ff-246">Chaque période de rémunération comprend une date de paiement par défaut basée sur les informations que vous fournissez.</span><span class="sxs-lookup"><span data-stu-id="502ff-246">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="502ff-247">Toutefois, vous pouvez modifier la date de paiement par défaut d'une période de rémunération pour permettre des exceptions, par exemple lorsque la date de paiement a lieu un jour férié.</span><span class="sxs-lookup"><span data-stu-id="502ff-247">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="502ff-248">Les informations suivantes sont utilisée dans Dayforce :</span><span class="sxs-lookup"><span data-stu-id="502ff-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="502ff-249">Cycle de paie (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-249">Pay cycle (required)</span></span>
- <span data-ttu-id="502ff-250">Fréquence du cycle de paie (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-250">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="502ff-251">Date de début de la période (première période de rémunération obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-251">Period start date (first pay period required)</span></span>
- <span data-ttu-id="502ff-252">Date de rémunération par défaut (première période de rémunération obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-252">Default payment date (first pay period required)</span></span>

<span data-ttu-id="502ff-253">Ces informations sont intégrées à Dayforce en tant que des groupes de paie, et sont séparées par pays ou par région pour chaque cycle de paie.</span><span class="sxs-lookup"><span data-stu-id="502ff-253">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="502ff-254">Au moins une période de rémunération doit être générée avant l'intégration.</span><span class="sxs-lookup"><span data-stu-id="502ff-254">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="502ff-255">Dayforce génère des calendriers de groupe de paie et des dates de rémunération, selon la date de début de la première période de rémunération et la date de rémunération par défaut paramétrées dans Talent.</span><span class="sxs-lookup"><span data-stu-id="502ff-255">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="502ff-256">Codes de rémunérations</span><span class="sxs-lookup"><span data-stu-id="502ff-256">Earning codes</span></span>

<span data-ttu-id="502ff-257">Les codes de rémunérations identifient de manière unique chaque type de revenus que les collaborateurs reçoivent.</span><span class="sxs-lookup"><span data-stu-id="502ff-257">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="502ff-258">Les codes ont différents paramètres associés aux revenus, tels que des règles comptables, des lois fiscales, des conditions de génération d'états, et la capacité de montant brut.</span><span class="sxs-lookup"><span data-stu-id="502ff-258">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="502ff-259">Les informations suivantes sont utilisée dans Dayforce :</span><span class="sxs-lookup"><span data-stu-id="502ff-259">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="502ff-260">Code de rémunération (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-260">Earning Code (required)</span></span>
- <span data-ttu-id="502ff-261">Description</span><span class="sxs-lookup"><span data-stu-id="502ff-261">Description</span></span>
- <span data-ttu-id="502ff-262">Unité de mesure</span><span class="sxs-lookup"><span data-stu-id="502ff-262">Unit of measure</span></span>
- <span data-ttu-id="502ff-263">Productif</span><span class="sxs-lookup"><span data-stu-id="502ff-263">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="502ff-264">Données sur les collaborateurs</span><span class="sxs-lookup"><span data-stu-id="502ff-264">Worker data</span></span>

<span data-ttu-id="502ff-265">Les enregistrements pour les différents types d'employés dont vous disposez sont importants pour vos systèmes de ressources humaines et de paie.</span><span class="sxs-lookup"><span data-stu-id="502ff-265">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="502ff-266">Les informations que vous entrez peuvent servir à suivre les informations des collaborateurs et les informations personnelles.</span><span class="sxs-lookup"><span data-stu-id="502ff-266">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="502ff-267">Vous pouvez tenir à jour les informations suivantes pour les travailleurs :</span><span class="sxs-lookup"><span data-stu-id="502ff-267">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="502ff-268">**Base** – Permet de tenir à jour les informations de base sur un collaborateur, telles que les informations de contact, les informations démographiques, les informations d'identification, les informations sur la famille, le statut de service militaire, les informations d'expatriation, et les contacts personnels et les personnes à prévenir en cas d'urgence.</span><span class="sxs-lookup"><span data-stu-id="502ff-268">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="502ff-269">**Emploi** – Permet de tenir à jour les informations relatives à l'emploi des collaborateurs, telles que l'affiliation de la société ou de l'organisation, l'affectation de poste, les dates de début et de fin, l'éligibilité à un emploi, les conditions d'emploi, la retraite, les congés, et les informations de mutation.</span><span class="sxs-lookup"><span data-stu-id="502ff-269">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="502ff-270">**Congé et absence** – Permet de tenir à jour les informations sur les absences des collaborateurs, telles que les calendriers de travail, les transactions d'absence et le paramétrage d'absence.</span><span class="sxs-lookup"><span data-stu-id="502ff-270">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="502ff-271">**Rémunération et paie** – Permet de tenir à jour les informations sur les régimes de rémunération des collaborateurs et les informations de paie, telles que l'inscription à un régime, les primes, les performances, la commission, les informations fiscales, la retraite et les déductions de salaire.</span><span class="sxs-lookup"><span data-stu-id="502ff-271">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="502ff-272">Lorsque vous entrez des informations sur le collaborateur, n'oubliez pas les données et les configurations suivantes utilisées dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="502ff-272">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="502ff-273">Informations générales</span><span class="sxs-lookup"><span data-stu-id="502ff-273">General information</span></span>

- <span data-ttu-id="502ff-274">Matricule (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-274">Personnel number (required)</span></span>
- <span data-ttu-id="502ff-275">Prénom (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-275">First name (required)</span></span>
- <span data-ttu-id="502ff-276">Nom (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-276">Last name (required)</span></span>
- <span data-ttu-id="502ff-277">Autres prénoms</span><span class="sxs-lookup"><span data-stu-id="502ff-277">Middle name</span></span>
- <span data-ttu-id="502ff-278">Date d'ancienneté</span><span class="sxs-lookup"><span data-stu-id="502ff-278">Seniority date</span></span>
- <span data-ttu-id="502ff-279">Connu sous</span><span class="sxs-lookup"><span data-stu-id="502ff-279">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="502ff-280">Informations personnelles</span><span class="sxs-lookup"><span data-stu-id="502ff-280">Personal information</span></span>

- <span data-ttu-id="502ff-281">État civil (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-281">Marital status (required)</span></span>
- <span data-ttu-id="502ff-282">Date de naissance (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-282">Birth date (required)</span></span>
- <span data-ttu-id="502ff-283">Sexe (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-283">Gender (required)</span></span>
- <span data-ttu-id="502ff-284">Personne handicapée</span><span class="sxs-lookup"><span data-stu-id="502ff-284">Person with disabilities</span></span>
- <span data-ttu-id="502ff-285">Région/pays de nationalité (uniquement au Mexique)</span><span class="sxs-lookup"><span data-stu-id="502ff-285">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="502ff-286">Informations d'adresse</span><span class="sxs-lookup"><span data-stu-id="502ff-286">Address information</span></span>

- <span data-ttu-id="502ff-287">Adresse principale (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-287">Primary (required)</span></span>
- <span data-ttu-id="502ff-288">Pays/région (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-288">Country/region (required)</span></span>
- <span data-ttu-id="502ff-289">Code postal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-289">Postal code (required)</span></span>
- <span data-ttu-id="502ff-290">Numéro de la rue (obligatoire) (uniquement au Mexique)</span><span class="sxs-lookup"><span data-stu-id="502ff-290">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="502ff-291">Info complémentaire sur le bâtiment (uniquement au Mexique)</span><span class="sxs-lookup"><span data-stu-id="502ff-291">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="502ff-292">Ville (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-292">City (required)</span></span>
- <span data-ttu-id="502ff-293">État (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-293">State (required)</span></span>
- <span data-ttu-id="502ff-294">Pays (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-294">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="502ff-295">Informations de contact</span><span class="sxs-lookup"><span data-stu-id="502ff-295">Contact information</span></span> 

- <span data-ttu-id="502ff-296">Contact principal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-296">Primary (required)</span></span>
- <span data-ttu-id="502ff-297">Numéro du contact (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-297">Contact number (required)</span></span>
- <span data-ttu-id="502ff-298">Poste</span><span class="sxs-lookup"><span data-stu-id="502ff-298">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="502ff-299">Informations sur les salaires et codes de rémunération</span><span class="sxs-lookup"><span data-stu-id="502ff-299">Payroll information and earning codes</span></span>

<span data-ttu-id="502ff-300">Les employés peuvent bénéficier de revenus spécifiques à une fréquence de paiement donnée et avoir un mode de paiement préféré.</span><span class="sxs-lookup"><span data-stu-id="502ff-300">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="502ff-301">Les champs suivants sont utilisés dans Dayforce pour garantir que ces préférences et paramètres soient utilisés.</span><span class="sxs-lookup"><span data-stu-id="502ff-301">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="502ff-302">Codes de rémunérations</span><span class="sxs-lookup"><span data-stu-id="502ff-302">Earning codes</span></span>

- <span data-ttu-id="502ff-303">Poste (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-303">Position (required)</span></span>
- <span data-ttu-id="502ff-304">Code de rémunération (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-304">Earning Code (required)</span></span>
- <span data-ttu-id="502ff-305">Fréquence (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-305">Frequency (required)</span></span>
- <span data-ttu-id="502ff-306">Montant (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-306">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="502ff-307">Informations sur les salaires</span><span class="sxs-lookup"><span data-stu-id="502ff-307">Payroll information</span></span>

- <span data-ttu-id="502ff-308">Mode de paiement</span><span class="sxs-lookup"><span data-stu-id="502ff-308">Payment Method</span></span>
- <span data-ttu-id="502ff-309">Région économique (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-309">Economic Region (required)</span></span>
- <span data-ttu-id="502ff-310">ID avantages employé</span><span class="sxs-lookup"><span data-stu-id="502ff-310">Employee Benefits ID</span></span>
- <span data-ttu-id="502ff-311">Numéro d'ID national (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-311">National ID Number (required)</span></span>
- <span data-ttu-id="502ff-312">Numéro de service militaire</span><span class="sxs-lookup"><span data-stu-id="502ff-312">Military Service Number</span></span>
- <span data-ttu-id="502ff-313">ID d'équipe (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-313">Shift ID (required)</span></span>
- <span data-ttu-id="502ff-314">Numéro de taxe (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-314">Tax Number (required)</span></span>
- <span data-ttu-id="502ff-315">ID syndicat (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-315">Union ID (required)</span></span>
- <span data-ttu-id="502ff-316">ID de la journée de travail (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-316">Work Day ID (required)</span></span>
- <span data-ttu-id="502ff-317">Numéro de permis de travail</span><span class="sxs-lookup"><span data-stu-id="502ff-317">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="502ff-318">Pour le mode de paiement, le Mexique prend en charge les **Espèces**, les **Chèques** (chèque physique de la société) et le **Paiement électronique**.</span><span class="sxs-lookup"><span data-stu-id="502ff-318">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="502ff-319">Si aucun mode de paiement n'est spécifié, le **Chèque** est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="502ff-319">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="502ff-320">Détails de l'emploi</span><span class="sxs-lookup"><span data-stu-id="502ff-320">Employment details</span></span>

<span data-ttu-id="502ff-321">L'historique des détails de l'emploi est utilisé comme information clé pour en dériver le statut d'embauche, de fin du contrat, et de réembauche d'un employé dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="502ff-321">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="502ff-322">Dayforce prend en charge un seul enregistrement d'emploi actif à la fois.</span><span class="sxs-lookup"><span data-stu-id="502ff-322">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="502ff-323">Date de début de l'emploi (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-323">Employment start date (required)</span></span>
- <span data-ttu-id="502ff-324">Date de fin de l'emploi</span><span class="sxs-lookup"><span data-stu-id="502ff-324">Employment end date</span></span>
- <span data-ttu-id="502ff-325">Date de début</span><span class="sxs-lookup"><span data-stu-id="502ff-325">Start date</span></span>
- <span data-ttu-id="502ff-326">Date de début de contrat ajustée</span><span class="sxs-lookup"><span data-stu-id="502ff-326">Adjusted start date</span></span>
- <span data-ttu-id="502ff-327">Date de fin de contrat (obligatoire à la fin du contrat)</span><span class="sxs-lookup"><span data-stu-id="502ff-327">Termination date (required upon termination)</span></span>
- <span data-ttu-id="502ff-328">Motif de la fin du contrat (obligatoire à la fin du contrat)</span><span class="sxs-lookup"><span data-stu-id="502ff-328">Termination reason (required upon termination)</span></span>

<span data-ttu-id="502ff-329">Les dates clés d'un employé sont dérivées à l'aide des informations suivantes.</span><span class="sxs-lookup"><span data-stu-id="502ff-329">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="502ff-330">Talent</span><span class="sxs-lookup"><span data-stu-id="502ff-330">Talent</span></span>                | <span data-ttu-id="502ff-331">Dayforce</span><span class="sxs-lookup"><span data-stu-id="502ff-331">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="502ff-332">Date d'embauche la plus récente</span><span class="sxs-lookup"><span data-stu-id="502ff-332">Most recent hire date</span></span> | <span data-ttu-id="502ff-333">Début de l'emploi de l'enregistrement d'historique d'emploi avec contrat en cours</span><span class="sxs-lookup"><span data-stu-id="502ff-333">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="502ff-334">Date de fin de contrat</span><span class="sxs-lookup"><span data-stu-id="502ff-334">Termination date</span></span>      | <span data-ttu-id="502ff-335">Date de fin de contrat de l'enregistrement d'historique d'emploi avec contrat en cours</span><span class="sxs-lookup"><span data-stu-id="502ff-335">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="502ff-336">Date de début</span><span class="sxs-lookup"><span data-stu-id="502ff-336">Start date</span></span>            | <span data-ttu-id="502ff-337">Date de début ajustée, date de début, ou début de l'emploi de l'enregistrement d'historique d'emploi inactif actuel</span><span class="sxs-lookup"><span data-stu-id="502ff-337">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="502ff-338">Date d'embauche d'origine</span><span class="sxs-lookup"><span data-stu-id="502ff-338">Original hire date</span></span>    | <span data-ttu-id="502ff-339">Début d'emploi de l'enregistrement d'historique d'emploi le plus proche</span><span class="sxs-lookup"><span data-stu-id="502ff-339">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="502ff-340">Rémunération</span><span class="sxs-lookup"><span data-stu-id="502ff-340">Compensation</span></span>

<span data-ttu-id="502ff-341">Un plan de rémunération fixe doit être associé au poste principal de chaque employé tout au long d'une période d'emploi.</span><span class="sxs-lookup"><span data-stu-id="502ff-341">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="502ff-342">Cette période démarre à la date à laquelle l'employé a été embauché (ou à la date de début de l'emploi) et se poursuit jusqu'à la fin de contrat.</span><span class="sxs-lookup"><span data-stu-id="502ff-342">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="502ff-343">Date d'effet (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-343">Effective Date (required)</span></span>
- <span data-ttu-id="502ff-344">Date d'expiration</span><span class="sxs-lookup"><span data-stu-id="502ff-344">Expiration date</span></span>
- <span data-ttu-id="502ff-345">Taux de salaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-345">Pay Rate (required)</span></span>
- <span data-ttu-id="502ff-346">Conversions de taux de salaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-346">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="502ff-347">Équivalent annuel (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-347">Annual equivalent (required)</span></span>
- <span data-ttu-id="502ff-348">Équivalent horaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-348">Hourly equivalent (required)</span></span>

<span data-ttu-id="502ff-349">Si un employé horaire a plusieurs postes, la rémunération fixe du poste principal est importée dans Dayforce comme taux de base/salaire de niveau d'employé.</span><span class="sxs-lookup"><span data-stu-id="502ff-349">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="502ff-350">Pour les postes non principaux, le taux horaire est enregistré au poste correspondant dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="502ff-350">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="502ff-351">Si un employé salarié occupe plusieurs postes, le taux horaire cumulé et le salaire annuel entre tous les postes actifs sont dérivés et utilisés comme taux de base/salaire au niveau de l'employé.</span><span class="sxs-lookup"><span data-stu-id="502ff-351">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="502ff-352">Numéros d'identifications</span><span class="sxs-lookup"><span data-stu-id="502ff-352">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="502ff-353">Numéro de Sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="502ff-353">Social Security identifier</span></span> 

<span data-ttu-id="502ff-354">Chaque employé doit avoir un numéro principal.</span><span class="sxs-lookup"><span data-stu-id="502ff-354">Every employee must have one primary identifier.</span></span> <span data-ttu-id="502ff-355">Cet numéro doit être de type d'identification **N° S.S.**.</span><span class="sxs-lookup"><span data-stu-id="502ff-355">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="502ff-356">Dans Dayforce, il est automatiquement dérivé du numéro de Sécurité sociale de l'employé qui est obligatoire pour l'embaucher.</span><span class="sxs-lookup"><span data-stu-id="502ff-356">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="502ff-357">Numéro principal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-357">Primary (required)</span></span>
- <span data-ttu-id="502ff-358">Type d'identification = « N° S.S. »</span><span class="sxs-lookup"><span data-stu-id="502ff-358">Identification Type = "SSN"</span></span>
- <span data-ttu-id="502ff-359">Date d'émission</span><span class="sxs-lookup"><span data-stu-id="502ff-359">Issued Date</span></span>
- <span data-ttu-id="502ff-360">Date d'expiration</span><span class="sxs-lookup"><span data-stu-id="502ff-360">Expiration Date</span></span>

<span data-ttu-id="502ff-361">Les employés peuvent déclarer plusieurs numéros d'identification de type d'identification **N° S.S.**.</span><span class="sxs-lookup"><span data-stu-id="502ff-361">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="502ff-362">Toutefois, seul l'enregistrement marqué comme **Principal** est intégré à Dayforce, que le numéro soit active ou arrivé à expiration.</span><span class="sxs-lookup"><span data-stu-id="502ff-362">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="502ff-363">Comptes en banque et décaissements</span><span class="sxs-lookup"><span data-stu-id="502ff-363">Bank accounts and disbursements</span></span>

<span data-ttu-id="502ff-364">Des informations de compte bancaire valides doivent être entrées pour tous les employés qui choisissent d'être payés à l'aide de virements bancaires.</span><span class="sxs-lookup"><span data-stu-id="502ff-364">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="502ff-365">Talent</span><span class="sxs-lookup"><span data-stu-id="502ff-365">Talent</span></span>                         | <span data-ttu-id="502ff-366">Dayforce</span><span class="sxs-lookup"><span data-stu-id="502ff-366">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="502ff-367">Numéro de compte bancaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-367">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="502ff-368">Code SWIFT (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-368">SWIFT code (required)</span></span>          | <span data-ttu-id="502ff-369">Le champ**ID banque** utilisé lors du traitement du salaire au Mexique.</span><span class="sxs-lookup"><span data-stu-id="502ff-369">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="502ff-370">Numéro d'agence (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-370">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="502ff-371">Type de compte bancaire (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-371">Bank account type (required)</span></span>   | <span data-ttu-id="502ff-372">Le champ**Type de compte** utilisé lors du traitement du salaire au Mexique.</span><span class="sxs-lookup"><span data-stu-id="502ff-372">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="502ff-373">Les valeurs prises en charge sont **Chèque** et **Paie**.</span><span class="sxs-lookup"><span data-stu-id="502ff-373">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="502ff-374">Les employés qui choisissent d'être payés par des virements bancaires doivent fournir un lien vers un compte de solde qui se trouve sous une entité juridique avec son adresse principale au Mexique, et associée à un compte bancaire valide dans une banque mexicaine.</span><span class="sxs-lookup"><span data-stu-id="502ff-374">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="502ff-375">Tous les autres comptes non-solde sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="502ff-375">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="502ff-376">Informations d'adresse</span><span class="sxs-lookup"><span data-stu-id="502ff-376">Address information</span></span>

<span data-ttu-id="502ff-377">Chaque employé doit avoir un lieu principal.</span><span class="sxs-lookup"><span data-stu-id="502ff-377">Every employee must have one primary location.</span></span> <span data-ttu-id="502ff-378">Dans Dayforce, ce lieu est utilisé pour déterminer la résidence principale de l'employé à des fins fiscales.</span><span class="sxs-lookup"><span data-stu-id="502ff-378">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="502ff-379">Lieu principal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-379">Primary (required)</span></span>
- <span data-ttu-id="502ff-380">Pays/région (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-380">Country/region (required)</span></span>
- <span data-ttu-id="502ff-381">Code postal (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-381">Zip/postal code (required)</span></span>
- <span data-ttu-id="502ff-382">Rue (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-382">Street (required)</span></span>
- <span data-ttu-id="502ff-383">Numéro de rue (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-383">Street Number (required)</span></span>
- <span data-ttu-id="502ff-384">Info complémentaire sur le bâtiment</span><span class="sxs-lookup"><span data-stu-id="502ff-384">Building Complement</span></span>
- <span data-ttu-id="502ff-385">Ville (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-385">City (required)</span></span>
- <span data-ttu-id="502ff-386">État (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-386">State (required)</span></span>
- <span data-ttu-id="502ff-387">Pays (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-387">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="502ff-388">Configurer vos données pour générer un salaire aux États-Unis et au Canada</span><span class="sxs-lookup"><span data-stu-id="502ff-388">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="502ff-389">Si vous générez un salaire pour des employés aux États-Unis et au Canada, les éléments suivants doivent être configurés :</span><span class="sxs-lookup"><span data-stu-id="502ff-389">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="502ff-390">Les départements sont obligatoires sur les postes.</span><span class="sxs-lookup"><span data-stu-id="502ff-390">Departments are required on positions.</span></span>
- <span data-ttu-id="502ff-391">Les centres de coût doivent être définis comme des dimensions financières et doivent être le premier élément de la chaîne de dimension financière par défaut.</span><span class="sxs-lookup"><span data-stu-id="502ff-391">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="502ff-392">Vous pouvez configurer Talent pour demander que les postes spécifient un service.</span><span class="sxs-lookup"><span data-stu-id="502ff-392">You can configure Talent to require that Positions specify a Department.</span></span> <span data-ttu-id="502ff-393">Pour ce faire, accédez à **Postes partagés par les ressources humaines > Postes > Demander le service des postes**.</span><span class="sxs-lookup"><span data-stu-id="502ff-393">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="502ff-394">Nous vous recommandons d'appliquer ce paramètre pour l'intégration.</span><span class="sxs-lookup"><span data-stu-id="502ff-394">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="502ff-395">Types de missions</span><span class="sxs-lookup"><span data-stu-id="502ff-395">Job types</span></span>

<span data-ttu-id="502ff-396">Les types de tâches sont utilisés pour regrouper les tâches similaires en catégories.</span><span class="sxs-lookup"><span data-stu-id="502ff-396">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="502ff-397">Les types de tâches sont nécessaires pour traiter la paie aux États-Unis et au Canada.</span><span class="sxs-lookup"><span data-stu-id="502ff-397">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="502ff-398">Les exemples de types de tâches incluent le temps plein et le temps partiel, ou le salaire et le paiement à l'heure.</span><span class="sxs-lookup"><span data-stu-id="502ff-398">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="502ff-399">Les types de tâches sont mis en correspondance dans Dayforce comme types de paies qui indiquent si un employé est payé à l'heure ou salarié.</span><span class="sxs-lookup"><span data-stu-id="502ff-399">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="502ff-400">Les types de tâches et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="502ff-400">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="502ff-401">Type de mission</span><span class="sxs-lookup"><span data-stu-id="502ff-401">Job type</span></span>   | <span data-ttu-id="502ff-402">Description</span><span class="sxs-lookup"><span data-stu-id="502ff-402">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="502ff-403">Horaire</span><span class="sxs-lookup"><span data-stu-id="502ff-403">Hourly</span></span>     | <span data-ttu-id="502ff-404">Horaire</span><span class="sxs-lookup"><span data-stu-id="502ff-404">Hourly</span></span>      |
| <span data-ttu-id="502ff-405">Salarié</span><span class="sxs-lookup"><span data-stu-id="502ff-405">Salaried</span></span>   | <span data-ttu-id="502ff-406">Salarié</span><span class="sxs-lookup"><span data-stu-id="502ff-406">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="502ff-407">Types de poste</span><span class="sxs-lookup"><span data-stu-id="502ff-407">Position types</span></span> 

<span data-ttu-id="502ff-408">Vous utilisez les types de postes pour indiquer si le poste est à temps plein, à temps partiel, ou autre chose.</span><span class="sxs-lookup"><span data-stu-id="502ff-408">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="502ff-409">Les types de postes sont mis en correspondance dans Dayforce comme classes de paiements qui indiquent si un employé est à temps plein ou à temps partiel.</span><span class="sxs-lookup"><span data-stu-id="502ff-409">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="502ff-410">Les types de postes et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="502ff-410">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="502ff-411">Type de poste</span><span class="sxs-lookup"><span data-stu-id="502ff-411">Position type</span></span>   | <span data-ttu-id="502ff-412">Description</span><span class="sxs-lookup"><span data-stu-id="502ff-412">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="502ff-413">Temps plein</span><span class="sxs-lookup"><span data-stu-id="502ff-413">Full-time</span></span>       | <span data-ttu-id="502ff-414">Employé à temps plein</span><span class="sxs-lookup"><span data-stu-id="502ff-414">Full time employee</span></span> |
| <span data-ttu-id="502ff-415">Temps partiel</span><span class="sxs-lookup"><span data-stu-id="502ff-415">Part-time</span></span>       | <span data-ttu-id="502ff-416">Employé à temps partiel</span><span class="sxs-lookup"><span data-stu-id="502ff-416">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="502ff-417">Codes motif</span><span class="sxs-lookup"><span data-stu-id="502ff-417">Reason codes</span></span>

<span data-ttu-id="502ff-418">Les codes motif fournissent des informations sur le statut d'un employé.</span><span class="sxs-lookup"><span data-stu-id="502ff-418">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="502ff-419">Les codes motif sont mis en correspondance avec Dayforce comme motifs du statut, indiquant le motif des modifications apportées au poste ou au statut d'emploi d'un employé.</span><span class="sxs-lookup"><span data-stu-id="502ff-419">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="502ff-420">Les codes motif et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="502ff-420">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="502ff-421">Code motif</span><span class="sxs-lookup"><span data-stu-id="502ff-421">Reason code</span></span>    | <span data-ttu-id="502ff-422">Description</span><span class="sxs-lookup"><span data-stu-id="502ff-422">Description</span></span>      | <span data-ttu-id="502ff-423">Scénarios applicables</span><span class="sxs-lookup"><span data-stu-id="502ff-423">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="502ff-424">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="502ff-424">RESIGNATION</span></span>    | <span data-ttu-id="502ff-425">Démission</span><span class="sxs-lookup"><span data-stu-id="502ff-425">Resignation</span></span>      | <span data-ttu-id="502ff-426">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="502ff-426">Terminate worker</span></span>     |
| <span data-ttu-id="502ff-427">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="502ff-427">TERMINATION</span></span>    | <span data-ttu-id="502ff-428">Fin du contrat</span><span class="sxs-lookup"><span data-stu-id="502ff-428">Termination</span></span>      | <span data-ttu-id="502ff-429">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="502ff-429">Terminate worker</span></span>     |
| <span data-ttu-id="502ff-430">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="502ff-430">RETIREMENT</span></span>     | <span data-ttu-id="502ff-431">Retraite</span><span class="sxs-lookup"><span data-stu-id="502ff-431">Retirement</span></span>       | <span data-ttu-id="502ff-432">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="502ff-432">Terminate worker</span></span>     |
| <span data-ttu-id="502ff-433">OTHER</span><span class="sxs-lookup"><span data-stu-id="502ff-433">OTHER</span></span>          | <span data-ttu-id="502ff-434">Autres motifs</span><span class="sxs-lookup"><span data-stu-id="502ff-434">Other Reasons</span></span>    | <span data-ttu-id="502ff-435">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="502ff-435">Terminate worker</span></span>     |
| <span data-ttu-id="502ff-436">DEATH</span><span class="sxs-lookup"><span data-stu-id="502ff-436">DEATH</span></span>          | <span data-ttu-id="502ff-437">Décès</span><span class="sxs-lookup"><span data-stu-id="502ff-437">Death</span></span>            | <span data-ttu-id="502ff-438">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="502ff-438">Terminate worker</span></span>     |
| <span data-ttu-id="502ff-439">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="502ff-439">LEAVEOFABSENCE</span></span> | <span data-ttu-id="502ff-440">Congé</span><span class="sxs-lookup"><span data-stu-id="502ff-440">Leave of Absence</span></span> | <span data-ttu-id="502ff-441">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="502ff-441">Terminate worker</span></span>     |
| <span data-ttu-id="502ff-442">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="502ff-442">CONTRACTEND</span></span>    | <span data-ttu-id="502ff-443">Fin du contrat</span><span class="sxs-lookup"><span data-stu-id="502ff-443">End of Contract</span></span>  | <span data-ttu-id="502ff-444">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="502ff-444">Terminate worker</span></span>     |
| <span data-ttu-id="502ff-445">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="502ff-445">SALARYCHANGE</span></span>   | <span data-ttu-id="502ff-446">Modification du salaire</span><span class="sxs-lookup"><span data-stu-id="502ff-446">Change of Salary</span></span> | <span data-ttu-id="502ff-447">Rémunération</span><span class="sxs-lookup"><span data-stu-id="502ff-447">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="502ff-448">Situation de famille</span><span class="sxs-lookup"><span data-stu-id="502ff-448">Marital status</span></span>

<span data-ttu-id="502ff-449">Les valeurs de situation de famille sont mises en correspondance avec Dayforce et traduite, au besoin, dans les valeurs acceptées lors de l'intégration.</span><span class="sxs-lookup"><span data-stu-id="502ff-449">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="502ff-450">Le tableau suivant montre comment les valeurs de situation de famille sont mises en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="502ff-450">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="502ff-451">Talent</span><span class="sxs-lookup"><span data-stu-id="502ff-451">Talent</span></span>                 | <span data-ttu-id="502ff-452">Dayforce</span><span class="sxs-lookup"><span data-stu-id="502ff-452">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="502ff-453">Marié</span><span class="sxs-lookup"><span data-stu-id="502ff-453">Married</span></span>                | <span data-ttu-id="502ff-454">Marié</span><span class="sxs-lookup"><span data-stu-id="502ff-454">Married</span></span>              |
| <span data-ttu-id="502ff-455">Unique</span><span class="sxs-lookup"><span data-stu-id="502ff-455">Single</span></span>                 | <span data-ttu-id="502ff-456">Unique</span><span class="sxs-lookup"><span data-stu-id="502ff-456">Single</span></span>               |
| <span data-ttu-id="502ff-457">Veuf</span><span class="sxs-lookup"><span data-stu-id="502ff-457">Widowed</span></span>                | <span data-ttu-id="502ff-458">Veuf</span><span class="sxs-lookup"><span data-stu-id="502ff-458">Widowed</span></span>              |
| <span data-ttu-id="502ff-459">Divorcé</span><span class="sxs-lookup"><span data-stu-id="502ff-459">Divorced</span></span>               | <span data-ttu-id="502ff-460">Divorcé</span><span class="sxs-lookup"><span data-stu-id="502ff-460">Divorced</span></span>             |
| <span data-ttu-id="502ff-461">Partenariat enregistré</span><span class="sxs-lookup"><span data-stu-id="502ff-461">Registered Partnership</span></span> | <span data-ttu-id="502ff-462">Partenariat local</span><span class="sxs-lookup"><span data-stu-id="502ff-462">Domestic Partnership</span></span> |
| <span data-ttu-id="502ff-463">None</span><span class="sxs-lookup"><span data-stu-id="502ff-463">None</span></span>                   | <span data-ttu-id="502ff-464">None</span><span class="sxs-lookup"><span data-stu-id="502ff-464">None</span></span>                 |
| <span data-ttu-id="502ff-465">Concubinage</span><span class="sxs-lookup"><span data-stu-id="502ff-465">Cohabiting</span></span>             | <span data-ttu-id="502ff-466">Concubinage</span><span class="sxs-lookup"><span data-stu-id="502ff-466">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="502ff-467">Sexe</span><span class="sxs-lookup"><span data-stu-id="502ff-467">Gender</span></span>

<span data-ttu-id="502ff-468">Le sexe est mis en correspondance avec Dayforce et traduit, au besoin, dans les valeurs acceptées lors de l'intégration.</span><span class="sxs-lookup"><span data-stu-id="502ff-468">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="502ff-469">Le tableau suivant montre comment le sexe est mis en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="502ff-469">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="502ff-470">Talent</span><span class="sxs-lookup"><span data-stu-id="502ff-470">Talent</span></span>       | <span data-ttu-id="502ff-471">Dayforce</span><span class="sxs-lookup"><span data-stu-id="502ff-471">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="502ff-472">Masculin</span><span class="sxs-lookup"><span data-stu-id="502ff-472">Male</span></span>         | <span data-ttu-id="502ff-473">Masculin</span><span class="sxs-lookup"><span data-stu-id="502ff-473">Male</span></span>            |
| <span data-ttu-id="502ff-474">Féminin</span><span class="sxs-lookup"><span data-stu-id="502ff-474">Female</span></span>       | <span data-ttu-id="502ff-475">Féminin</span><span class="sxs-lookup"><span data-stu-id="502ff-475">Female</span></span>          |
| <span data-ttu-id="502ff-476">Non spécifique</span><span class="sxs-lookup"><span data-stu-id="502ff-476">Non-specific</span></span> | <span data-ttu-id="502ff-477">*Non pris en charge*</span><span class="sxs-lookup"><span data-stu-id="502ff-477">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="502ff-478">Codes de rémunérations</span><span class="sxs-lookup"><span data-stu-id="502ff-478">Earning codes</span></span>

<span data-ttu-id="502ff-479">Les codes de rémunérations identifient de manière unique chaque type de revenus que les collaborateurs reçoivent.</span><span class="sxs-lookup"><span data-stu-id="502ff-479">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="502ff-480">Les codes couvrent différents paramètres associés aux revenus, tels que des règles comptables, des lois fiscales, des conditions de génération d'états, et la capacité de montant brut.</span><span class="sxs-lookup"><span data-stu-id="502ff-480">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="502ff-481">Si une fréquence non prise en charge est utilisée, la fréquence **Chaque paie** est utilisée par défaut pour le calcul.</span><span class="sxs-lookup"><span data-stu-id="502ff-481">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="502ff-482">Fréquences prises en charge</span><span class="sxs-lookup"><span data-stu-id="502ff-482">Supported frequencies</span></span>

- <span data-ttu-id="502ff-483">Tous</span><span class="sxs-lookup"><span data-stu-id="502ff-483">All</span></span>
- <span data-ttu-id="502ff-484">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="502ff-484">EVERYPAY</span></span>
- <span data-ttu-id="502ff-485">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="502ff-485">EACHPAYPERIOD</span></span>
- <span data-ttu-id="502ff-486">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="502ff-486">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="502ff-487">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="502ff-487">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="502ff-488">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-488">1OFMTH</span></span>
- <span data-ttu-id="502ff-489">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-489">LASTOFMTH</span></span>
- <span data-ttu-id="502ff-490">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-490">2OFMTH</span></span>
- <span data-ttu-id="502ff-491">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-491">3OFMTH</span></span>
- <span data-ttu-id="502ff-492">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-492">4OFMTH</span></span>
- <span data-ttu-id="502ff-493">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-493">5OFMTH</span></span>
- <span data-ttu-id="502ff-494">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-494">1N2OFMTH</span></span>
- <span data-ttu-id="502ff-495">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-495">3N4OFMTH</span></span>
- <span data-ttu-id="502ff-496">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-496">1N3OFMTH</span></span>
- <span data-ttu-id="502ff-497">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-497">1N4OFMTH</span></span>
- <span data-ttu-id="502ff-498">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-498">2N3OFMTH</span></span>
- <span data-ttu-id="502ff-499">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-499">2N4OFMTH</span></span>
- <span data-ttu-id="502ff-500">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-500">1N2N3OFMTH</span></span>
- <span data-ttu-id="502ff-501">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-501">1N2N4OFMTH</span></span>
- <span data-ttu-id="502ff-502">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-502">1N3N4OFMTH</span></span>
- <span data-ttu-id="502ff-503">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-503">2N3N4OFMTH</span></span>
- <span data-ttu-id="502ff-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="502ff-505">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="502ff-505">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="502ff-506">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="502ff-506">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="502ff-507">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="502ff-507">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="502ff-508">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="502ff-508">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="502ff-509">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="502ff-509">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="502ff-510">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="502ff-510">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="502ff-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="502ff-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="502ff-512">Adresses</span><span class="sxs-lookup"><span data-stu-id="502ff-512">Addresses</span></span>

<span data-ttu-id="502ff-513">L'identification d'un pays ou d'une région, d'un état, et des codes département (municipalité) spécifiques nécessite des formats spécifiques que les fournisseurs Dayforce et dans le pays/la région peuvent identifier.</span><span class="sxs-lookup"><span data-stu-id="502ff-513">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="502ff-514">Bien que le format pour les villes soit flexible, chaque ville doit être associée à un état.</span><span class="sxs-lookup"><span data-stu-id="502ff-514">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="502ff-515">Talent</span><span class="sxs-lookup"><span data-stu-id="502ff-515">Talent</span></span>          | <span data-ttu-id="502ff-516">Dayforce</span><span class="sxs-lookup"><span data-stu-id="502ff-516">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="502ff-517">Pays/région</span><span class="sxs-lookup"><span data-stu-id="502ff-517">Country/Region</span></span>  | <span data-ttu-id="502ff-518">Code pays</span><span class="sxs-lookup"><span data-stu-id="502ff-518">Country Code</span></span>          |
| <span data-ttu-id="502ff-519">Code postal</span><span class="sxs-lookup"><span data-stu-id="502ff-519">Zip/Postal Code</span></span> | <span data-ttu-id="502ff-520">Code postal</span><span class="sxs-lookup"><span data-stu-id="502ff-520">Postal Code</span></span>           |
| <span data-ttu-id="502ff-521">État</span><span class="sxs-lookup"><span data-stu-id="502ff-521">State</span></span>           | <span data-ttu-id="502ff-522">Code région</span><span class="sxs-lookup"><span data-stu-id="502ff-522">State Code</span></span>            |
| <span data-ttu-id="502ff-523">Ville</span><span class="sxs-lookup"><span data-stu-id="502ff-523">City</span></span>            | <span data-ttu-id="502ff-524">Ville</span><span class="sxs-lookup"><span data-stu-id="502ff-524">City</span></span>                  |
| <span data-ttu-id="502ff-525">Commune</span><span class="sxs-lookup"><span data-stu-id="502ff-525">County</span></span>          | <span data-ttu-id="502ff-526">Département (municipalité)</span><span class="sxs-lookup"><span data-stu-id="502ff-526">County (Municipality)</span></span> |
| <span data-ttu-id="502ff-527">Rue</span><span class="sxs-lookup"><span data-stu-id="502ff-527">Street</span></span>          | <span data-ttu-id="502ff-528">Ligne d'adresse 1</span><span class="sxs-lookup"><span data-stu-id="502ff-528">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="502ff-529">Zones fiscales</span><span class="sxs-lookup"><span data-stu-id="502ff-529">Tax regions</span></span>

<span data-ttu-id="502ff-530">Les régions fiscales permettent de déterminer la taxe appropriée qui doit être appliquée lors de la génération des salaires.</span><span class="sxs-lookup"><span data-stu-id="502ff-530">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="502ff-531">Les régions fiscales sont mises en correspondance avec Dayforce comme adresses de lieu.</span><span class="sxs-lookup"><span data-stu-id="502ff-531">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="502ff-532">La région fiscale par défaut doit être associée au poste actif du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="502ff-532">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="502ff-533">Région fiscale (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-533">Tax region (required)</span></span>
- <span data-ttu-id="502ff-534">Pays/région (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-534">Country/Region (required)</span></span>
- <span data-ttu-id="502ff-535">État (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-535">State (required)</span></span>
- <span data-ttu-id="502ff-536">Commune</span><span class="sxs-lookup"><span data-stu-id="502ff-536">County</span></span> 
- <span data-ttu-id="502ff-537">Ville (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="502ff-537">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="502ff-538">Configurez vos données pour générer un salaire au Mexique</span><span class="sxs-lookup"><span data-stu-id="502ff-538">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="502ff-539">Si vous générez un salaire pour des employés au Mexique, les éléments suivants doivent être configurés :</span><span class="sxs-lookup"><span data-stu-id="502ff-539">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="502ff-540">Les départements sont obligatoires sur les postes.</span><span class="sxs-lookup"><span data-stu-id="502ff-540">Departments are required on positions.</span></span>
- <span data-ttu-id="502ff-541">Les centres de coût doivent être définis comme des dimensions financières et doivent être le premier élément de la chaîne de dimension financière par défaut.</span><span class="sxs-lookup"><span data-stu-id="502ff-541">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="502ff-542">Types de missions</span><span class="sxs-lookup"><span data-stu-id="502ff-542">Job types</span></span>

<span data-ttu-id="502ff-543">Les types de tâches sont utilisés pour regrouper les tâches similaires en catégories.</span><span class="sxs-lookup"><span data-stu-id="502ff-543">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="502ff-544">Les types de tâches sont nécessaires afin de traiter le salaire au Mexique.</span><span class="sxs-lookup"><span data-stu-id="502ff-544">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="502ff-545">Les exemples de types de tâches incluent le temps plein et le temps partiel, ou le salaire et le paiement à l'heure.</span><span class="sxs-lookup"><span data-stu-id="502ff-545">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="502ff-546">Les types de tâches sont mis en correspondance dans Dayforce comme types de paies qui indiquent si un employé est payé à l'heure ou salarié.</span><span class="sxs-lookup"><span data-stu-id="502ff-546">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="502ff-547">Les types de tâches et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="502ff-547">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="502ff-548">Type de mission</span><span class="sxs-lookup"><span data-stu-id="502ff-548">Job type</span></span>   | <span data-ttu-id="502ff-549">Description</span><span class="sxs-lookup"><span data-stu-id="502ff-549">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="502ff-550">Horaire</span><span class="sxs-lookup"><span data-stu-id="502ff-550">Hourly</span></span>     | <span data-ttu-id="502ff-551">Horaire MX</span><span class="sxs-lookup"><span data-stu-id="502ff-551">MX Hourly</span></span>   |
| <span data-ttu-id="502ff-552">Salarié</span><span class="sxs-lookup"><span data-stu-id="502ff-552">Salaried</span></span>   | <span data-ttu-id="502ff-553">Salarié MX</span><span class="sxs-lookup"><span data-stu-id="502ff-553">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="502ff-554">Types de poste</span><span class="sxs-lookup"><span data-stu-id="502ff-554">Position types</span></span> 

<span data-ttu-id="502ff-555">Vous utilisez les types de postes pour indiquer si le poste est à temps plein, à temps partiel, ou autre chose.</span><span class="sxs-lookup"><span data-stu-id="502ff-555">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="502ff-556">Les types de postes sont mis en correspondance dans Dayforce comme classes de paiements qui indiquent si un employé est à temps plein ou à temps partiel.</span><span class="sxs-lookup"><span data-stu-id="502ff-556">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="502ff-557">Les types de postes et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="502ff-557">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="502ff-558">Type de poste</span><span class="sxs-lookup"><span data-stu-id="502ff-558">Position type</span></span>   | <span data-ttu-id="502ff-559">Description</span><span class="sxs-lookup"><span data-stu-id="502ff-559">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="502ff-560">Temps plein</span><span class="sxs-lookup"><span data-stu-id="502ff-560">Full-time</span></span>       | <span data-ttu-id="502ff-561">Employé à temps plein</span><span class="sxs-lookup"><span data-stu-id="502ff-561">Full time employee</span></span> |
| <span data-ttu-id="502ff-562">Temps partiel</span><span class="sxs-lookup"><span data-stu-id="502ff-562">Part-time</span></span>       | <span data-ttu-id="502ff-563">Employé à temps partiel</span><span class="sxs-lookup"><span data-stu-id="502ff-563">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="502ff-564">Codes motif</span><span class="sxs-lookup"><span data-stu-id="502ff-564">Reason codes</span></span>

<span data-ttu-id="502ff-565">Les codes motif fournissent des informations sur le statut d'un employé.</span><span class="sxs-lookup"><span data-stu-id="502ff-565">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="502ff-566">Les codes motif sont mis en correspondance avec Dayforce comme motifs du statut, indiquant le motif des modifications apportées au poste ou au statut d'emploi d'un employé.</span><span class="sxs-lookup"><span data-stu-id="502ff-566">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="502ff-567">Les codes motif et les descriptions suivants sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="502ff-567">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="502ff-568">Code motif</span><span class="sxs-lookup"><span data-stu-id="502ff-568">Reason code</span></span>            | <span data-ttu-id="502ff-569">Description</span><span class="sxs-lookup"><span data-stu-id="502ff-569">Description</span></span>                    | <span data-ttu-id="502ff-570">Scénarios applicables</span><span class="sxs-lookup"><span data-stu-id="502ff-570">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="502ff-571">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="502ff-571">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="502ff-572">Départ avant le premier salaire</span><span class="sxs-lookup"><span data-stu-id="502ff-572">Departure before first payroll</span></span> | <span data-ttu-id="502ff-573">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="502ff-573">Terminate worker</span></span>     |
| <span data-ttu-id="502ff-574">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="502ff-574">RESIGNATION</span></span>            | <span data-ttu-id="502ff-575">Démission</span><span class="sxs-lookup"><span data-stu-id="502ff-575">Resignation</span></span>                    | <span data-ttu-id="502ff-576">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="502ff-576">Terminate worker</span></span>     |
| <span data-ttu-id="502ff-577">PENSION</span><span class="sxs-lookup"><span data-stu-id="502ff-577">PENSION</span></span>                | <span data-ttu-id="502ff-578">Retraite</span><span class="sxs-lookup"><span data-stu-id="502ff-578">Pension</span></span>                        | <span data-ttu-id="502ff-579">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="502ff-579">Terminate worker</span></span>     |
| <span data-ttu-id="502ff-580">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="502ff-580">TERMINATION</span></span>            | <span data-ttu-id="502ff-581">Fin du contrat</span><span class="sxs-lookup"><span data-stu-id="502ff-581">Termination</span></span>                    | <span data-ttu-id="502ff-582">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="502ff-582">Terminate worker</span></span>     |
| <span data-ttu-id="502ff-583">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="502ff-583">RETIREMENT</span></span>             | <span data-ttu-id="502ff-584">Retraite</span><span class="sxs-lookup"><span data-stu-id="502ff-584">Retirement</span></span>                     | <span data-ttu-id="502ff-585">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="502ff-585">Terminate worker</span></span>     |
| <span data-ttu-id="502ff-586">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="502ff-586">ABSENTEE</span></span>               | <span data-ttu-id="502ff-587">Absent</span><span class="sxs-lookup"><span data-stu-id="502ff-587">Absentee</span></span>                       | <span data-ttu-id="502ff-588">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="502ff-588">Terminate worker</span></span>     |
| <span data-ttu-id="502ff-589">OTHER</span><span class="sxs-lookup"><span data-stu-id="502ff-589">OTHER</span></span>                  | <span data-ttu-id="502ff-590">Autres motifs</span><span class="sxs-lookup"><span data-stu-id="502ff-590">Other Reasons</span></span>                  | <span data-ttu-id="502ff-591">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="502ff-591">Terminate worker</span></span>     |
| <span data-ttu-id="502ff-592">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="502ff-592">CLOSURE</span></span>                | <span data-ttu-id="502ff-593">Fermeture de l'entreprise</span><span class="sxs-lookup"><span data-stu-id="502ff-593">Business Closure</span></span>               | <span data-ttu-id="502ff-594">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="502ff-594">Terminate worker</span></span>     |
| <span data-ttu-id="502ff-595">DEATH</span><span class="sxs-lookup"><span data-stu-id="502ff-595">DEATH</span></span>                  | <span data-ttu-id="502ff-596">Décès</span><span class="sxs-lookup"><span data-stu-id="502ff-596">Death</span></span>                          | <span data-ttu-id="502ff-597">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="502ff-597">Terminate worker</span></span>     |
| <span data-ttu-id="502ff-598">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="502ff-598">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="502ff-599">Congé</span><span class="sxs-lookup"><span data-stu-id="502ff-599">Leave of Absence</span></span>               | <span data-ttu-id="502ff-600">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="502ff-600">Terminate worker</span></span>     |
| <span data-ttu-id="502ff-601">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="502ff-601">CONTRACTEND</span></span>            | <span data-ttu-id="502ff-602">Fin du contrat</span><span class="sxs-lookup"><span data-stu-id="502ff-602">End of Contract</span></span>                | <span data-ttu-id="502ff-603">Mettre un terme au contrat du collaborateur</span><span class="sxs-lookup"><span data-stu-id="502ff-603">Terminate worker</span></span>     |
| <span data-ttu-id="502ff-604">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="502ff-604">SALARYCHANGE</span></span>           | <span data-ttu-id="502ff-605">Modification du salaire</span><span class="sxs-lookup"><span data-stu-id="502ff-605">Change of Salary</span></span>               | <span data-ttu-id="502ff-606">Rémunération</span><span class="sxs-lookup"><span data-stu-id="502ff-606">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="502ff-607">Conditions d'emploi</span><span class="sxs-lookup"><span data-stu-id="502ff-607">Terms of employment</span></span>

<span data-ttu-id="502ff-608">Les conditions d'emploi sont utilisées pour créer des catégories de conditions d'emploi.</span><span class="sxs-lookup"><span data-stu-id="502ff-608">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="502ff-609">Les conditions sont mises en correspondance avec Dayforce en tant que valeurs d'indicateur d'emploi.</span><span class="sxs-lookup"><span data-stu-id="502ff-609">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="502ff-610">Les conditions d'emploi et descriptions suivantes sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="502ff-610">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="502ff-611">Conditions d'emploi</span><span class="sxs-lookup"><span data-stu-id="502ff-611">Terms of employment</span></span>   | <span data-ttu-id="502ff-612">Description</span><span class="sxs-lookup"><span data-stu-id="502ff-612">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="502ff-613">Régulier</span><span class="sxs-lookup"><span data-stu-id="502ff-613">Regular</span></span>               | <span data-ttu-id="502ff-614">Régulier</span><span class="sxs-lookup"><span data-stu-id="502ff-614">Regular</span></span>     |
| <span data-ttu-id="502ff-615">Direct</span><span class="sxs-lookup"><span data-stu-id="502ff-615">Direct</span></span>                | <span data-ttu-id="502ff-616">Direct</span><span class="sxs-lookup"><span data-stu-id="502ff-616">Direct</span></span>      |
| <span data-ttu-id="502ff-617">Stage</span><span class="sxs-lookup"><span data-stu-id="502ff-617">Internship</span></span>            | <span data-ttu-id="502ff-618">Stage</span><span class="sxs-lookup"><span data-stu-id="502ff-618">Internship</span></span>  |
| <span data-ttu-id="502ff-619">Permanent</span><span class="sxs-lookup"><span data-stu-id="502ff-619">Permanent</span></span>             | <span data-ttu-id="502ff-620">Permanent</span><span class="sxs-lookup"><span data-stu-id="502ff-620">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="502ff-621">Situation de famille</span><span class="sxs-lookup"><span data-stu-id="502ff-621">Marital status</span></span>

<span data-ttu-id="502ff-622">Les valeurs de situation de famille sont mises en correspondance avec Dayforce et traduite, au besoin, dans les valeurs acceptées lors de l'intégration.</span><span class="sxs-lookup"><span data-stu-id="502ff-622">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="502ff-623">Le tableau suivant montre comment les valeurs de situation de famille sont mises en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="502ff-623">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="502ff-624">Talent</span><span class="sxs-lookup"><span data-stu-id="502ff-624">Talent</span></span>                 | <span data-ttu-id="502ff-625">Dayforce</span><span class="sxs-lookup"><span data-stu-id="502ff-625">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="502ff-626">Marié</span><span class="sxs-lookup"><span data-stu-id="502ff-626">Married</span></span>                | <span data-ttu-id="502ff-627">Marié</span><span class="sxs-lookup"><span data-stu-id="502ff-627">Married</span></span>                   |
| <span data-ttu-id="502ff-628">Unique</span><span class="sxs-lookup"><span data-stu-id="502ff-628">Single</span></span>                 | <span data-ttu-id="502ff-629">Unique</span><span class="sxs-lookup"><span data-stu-id="502ff-629">Single</span></span>                    |
| <span data-ttu-id="502ff-630">Veuf</span><span class="sxs-lookup"><span data-stu-id="502ff-630">Widowed</span></span>                | <span data-ttu-id="502ff-631">Veuf</span><span class="sxs-lookup"><span data-stu-id="502ff-631">Widowed</span></span>                   |
| <span data-ttu-id="502ff-632">Divorcé</span><span class="sxs-lookup"><span data-stu-id="502ff-632">Divorced</span></span>               | <span data-ttu-id="502ff-633">Divorcé</span><span class="sxs-lookup"><span data-stu-id="502ff-633">Divorced</span></span>                  |
| <span data-ttu-id="502ff-634">Partenariat enregistré</span><span class="sxs-lookup"><span data-stu-id="502ff-634">Registered Partnership</span></span> | <span data-ttu-id="502ff-635">Partenariat local</span><span class="sxs-lookup"><span data-stu-id="502ff-635">Domestic Partnership</span></span>      |
| <span data-ttu-id="502ff-636">None</span><span class="sxs-lookup"><span data-stu-id="502ff-636">None</span></span>                   | <span data-ttu-id="502ff-637">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="502ff-637">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="502ff-638">Concubinage</span><span class="sxs-lookup"><span data-stu-id="502ff-638">Cohabiting</span></span>             | <span data-ttu-id="502ff-639">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="502ff-639">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="502ff-640">Sexe</span><span class="sxs-lookup"><span data-stu-id="502ff-640">Gender</span></span>

<span data-ttu-id="502ff-641">Le sexe est mis en correspondance avec Dayforce et traduit, au besoin, dans les valeurs acceptées lors de l'intégration.</span><span class="sxs-lookup"><span data-stu-id="502ff-641">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="502ff-642">Le tableau suivant montre comment le sexe est mis en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="502ff-642">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="502ff-643">Talent</span><span class="sxs-lookup"><span data-stu-id="502ff-643">Talent</span></span>       | <span data-ttu-id="502ff-644">Dayforce</span><span class="sxs-lookup"><span data-stu-id="502ff-644">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="502ff-645">Masculin</span><span class="sxs-lookup"><span data-stu-id="502ff-645">Male</span></span>         | <span data-ttu-id="502ff-646">Masculin</span><span class="sxs-lookup"><span data-stu-id="502ff-646">Male</span></span>                      |
| <span data-ttu-id="502ff-647">Féminin</span><span class="sxs-lookup"><span data-stu-id="502ff-647">Female</span></span>       | <span data-ttu-id="502ff-648">Féminin</span><span class="sxs-lookup"><span data-stu-id="502ff-648">Female</span></span>                    |
| <span data-ttu-id="502ff-649">Non spécifique</span><span class="sxs-lookup"><span data-stu-id="502ff-649">Non-specific</span></span> | <span data-ttu-id="502ff-650">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="502ff-650">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="502ff-651">Mode de paiement</span><span class="sxs-lookup"><span data-stu-id="502ff-651">Payment method</span></span>

<span data-ttu-id="502ff-652">Les modes de paiement fournissent à l'employé et à la société une manière de décrire la façon dont les employés sont payés.</span><span class="sxs-lookup"><span data-stu-id="502ff-652">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="502ff-653">Les modes de paiement sont mis en correspondance avec Dayforce et traduit, au besoin, dans les valeurs acceptées lors de l'intégration.</span><span class="sxs-lookup"><span data-stu-id="502ff-653">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="502ff-654">Le tableau suivant montre comment les modes de paiement sont mis en correspondance avec Dayforce.</span><span class="sxs-lookup"><span data-stu-id="502ff-654">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="502ff-655">Talent</span><span class="sxs-lookup"><span data-stu-id="502ff-655">Talent</span></span>             | <span data-ttu-id="502ff-656">Dayforce</span><span class="sxs-lookup"><span data-stu-id="502ff-656">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="502ff-657">Espèces</span><span class="sxs-lookup"><span data-stu-id="502ff-657">Cash</span></span>               | <span data-ttu-id="502ff-658">Espèces</span><span class="sxs-lookup"><span data-stu-id="502ff-658">Cash</span></span>                      |
| <span data-ttu-id="502ff-659">Paiement électronique</span><span class="sxs-lookup"><span data-stu-id="502ff-659">Electronic Payment</span></span> | <span data-ttu-id="502ff-660">Virement</span><span class="sxs-lookup"><span data-stu-id="502ff-660">Transfer</span></span>                  |
| <span data-ttu-id="502ff-661">Chèque</span><span class="sxs-lookup"><span data-stu-id="502ff-661">Check</span></span>              | <span data-ttu-id="502ff-662">Chèque</span><span class="sxs-lookup"><span data-stu-id="502ff-662">Cheque</span></span>                    |
| <span data-ttu-id="502ff-663">Traites bancaires</span><span class="sxs-lookup"><span data-stu-id="502ff-663">Bank Draft</span></span>         | <span data-ttu-id="502ff-664">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="502ff-664">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="502ff-665">Autre/s</span><span class="sxs-lookup"><span data-stu-id="502ff-665">Other</span></span>              | <span data-ttu-id="502ff-666">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="502ff-666">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="502ff-667">Type de compte bancaire</span><span class="sxs-lookup"><span data-stu-id="502ff-667">Bank account type</span></span>

<span data-ttu-id="502ff-668">Les types de comptes bancaires sont utilisés pour les paiements électroniques aux employés.</span><span class="sxs-lookup"><span data-stu-id="502ff-668">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="502ff-669">Les types de comptes bancaires sont mis en correspondance avec Dayforce tant qu'informations de compte de transfert.</span><span class="sxs-lookup"><span data-stu-id="502ff-669">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="502ff-670">Les types de comptes bancaires sont traduits, au besoin, dans des valeurs acceptées lors de l'intégration.</span><span class="sxs-lookup"><span data-stu-id="502ff-670">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="502ff-671">Talent</span><span class="sxs-lookup"><span data-stu-id="502ff-671">Talent</span></span>            | <span data-ttu-id="502ff-672">Dayforce</span><span class="sxs-lookup"><span data-stu-id="502ff-672">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="502ff-673">Compte courant</span><span class="sxs-lookup"><span data-stu-id="502ff-673">Checking Account</span></span>  | <span data-ttu-id="502ff-674">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="502ff-674">CheckingAccount</span></span>           |
| <span data-ttu-id="502ff-675">Compte de paie</span><span class="sxs-lookup"><span data-stu-id="502ff-675">Payroll Account</span></span>   | <span data-ttu-id="502ff-676">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="502ff-676">PayrollAccount</span></span>            |
| <span data-ttu-id="502ff-677">Compte d'épargne</span><span class="sxs-lookup"><span data-stu-id="502ff-677">Savings Account</span></span>   | <span data-ttu-id="502ff-678">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="502ff-678">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="502ff-679">Compte BankGirot</span><span class="sxs-lookup"><span data-stu-id="502ff-679">BankGirot account</span></span> | <span data-ttu-id="502ff-680">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="502ff-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="502ff-681">Compte PlusGirot</span><span class="sxs-lookup"><span data-stu-id="502ff-681">PlusGirot account</span></span> | <span data-ttu-id="502ff-682">*Non pris en charge par le Mexique*</span><span class="sxs-lookup"><span data-stu-id="502ff-682">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="502ff-683">Codes de rémunérations</span><span class="sxs-lookup"><span data-stu-id="502ff-683">Earning codes</span></span>

<span data-ttu-id="502ff-684">Les codes de rémunérations identifient de manière unique chaque type de revenus que les collaborateurs reçoivent.</span><span class="sxs-lookup"><span data-stu-id="502ff-684">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="502ff-685">Les codes couvrent différents paramètres associés aux revenus, tels que des règles comptables, des lois fiscales, des conditions de génération d'états, et la capacité de montant brut.</span><span class="sxs-lookup"><span data-stu-id="502ff-685">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="502ff-686">Si une fréquence non prise en charge est utilisée, la fréquence **Chaque paie** est utilisée par défaut pour le calcul.</span><span class="sxs-lookup"><span data-stu-id="502ff-686">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="502ff-687">Fréquences prises en charge</span><span class="sxs-lookup"><span data-stu-id="502ff-687">Supported frequencies</span></span>

- <span data-ttu-id="502ff-688">Tous</span><span class="sxs-lookup"><span data-stu-id="502ff-688">All</span></span>
- <span data-ttu-id="502ff-689">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="502ff-689">EVERYPAY</span></span>
- <span data-ttu-id="502ff-690">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="502ff-690">EACHPAYPERIOD</span></span>
- <span data-ttu-id="502ff-691">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="502ff-691">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="502ff-692">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="502ff-692">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="502ff-693">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-693">1OFMTH</span></span>
- <span data-ttu-id="502ff-694">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-694">LASTOFMTH</span></span>
- <span data-ttu-id="502ff-695">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-695">2OFMTH</span></span>
- <span data-ttu-id="502ff-696">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-696">3OFMTH</span></span>
- <span data-ttu-id="502ff-697">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-697">4OFMTH</span></span>
- <span data-ttu-id="502ff-698">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-698">5OFMTH</span></span>
- <span data-ttu-id="502ff-699">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-699">1N2OFMTH</span></span>
- <span data-ttu-id="502ff-700">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-700">3N4OFMTH</span></span>
- <span data-ttu-id="502ff-701">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-701">1N3OFMTH</span></span>
- <span data-ttu-id="502ff-702">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-702">1N4OFMTH</span></span>
- <span data-ttu-id="502ff-703">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-703">2N3OFMTH</span></span>
- <span data-ttu-id="502ff-704">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-704">2N4OFMTH</span></span>
- <span data-ttu-id="502ff-705">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-705">1N2N3OFMTH</span></span>
- <span data-ttu-id="502ff-706">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-706">1N2N4OFMTH</span></span>
- <span data-ttu-id="502ff-707">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-707">1N3N4OFMTH</span></span>
- <span data-ttu-id="502ff-708">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-708">2N3N4OFMTH</span></span>
- <span data-ttu-id="502ff-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="502ff-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="502ff-710">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="502ff-710">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="502ff-711">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="502ff-711">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="502ff-712">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="502ff-712">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="502ff-713">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="502ff-713">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="502ff-714">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="502ff-714">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="502ff-715">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="502ff-715">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="502ff-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="502ff-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="502ff-717">Adresses</span><span class="sxs-lookup"><span data-stu-id="502ff-717">Addresses</span></span>

<span data-ttu-id="502ff-718">L'identification d'un pays ou d'une région, d'un état, et des codes département (municipalité) spécifiques nécessite des formats spécifiques que les fournisseurs Dayforce et dans le pays/la région peuvent identifier.</span><span class="sxs-lookup"><span data-stu-id="502ff-718">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="502ff-719">Bien que le format pour les villes soit flexible, chaque ville doit être associée à un état.</span><span class="sxs-lookup"><span data-stu-id="502ff-719">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="502ff-720">Talent</span><span class="sxs-lookup"><span data-stu-id="502ff-720">Talent</span></span>              | <span data-ttu-id="502ff-721">Dayforce</span><span class="sxs-lookup"><span data-stu-id="502ff-721">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="502ff-722">Pays/région</span><span class="sxs-lookup"><span data-stu-id="502ff-722">Country/Region</span></span>      | <span data-ttu-id="502ff-723">Code pays</span><span class="sxs-lookup"><span data-stu-id="502ff-723">Country Code</span></span>          |
| <span data-ttu-id="502ff-724">Code postal</span><span class="sxs-lookup"><span data-stu-id="502ff-724">Zip/Postal Code</span></span>     | <span data-ttu-id="502ff-725">Code postal</span><span class="sxs-lookup"><span data-stu-id="502ff-725">Postal Code</span></span>           |
| <span data-ttu-id="502ff-726">État</span><span class="sxs-lookup"><span data-stu-id="502ff-726">State</span></span>               | <span data-ttu-id="502ff-727">Code région</span><span class="sxs-lookup"><span data-stu-id="502ff-727">State Code</span></span>            |
| <span data-ttu-id="502ff-728">Ville</span><span class="sxs-lookup"><span data-stu-id="502ff-728">City</span></span>                | <span data-ttu-id="502ff-729">Ville</span><span class="sxs-lookup"><span data-stu-id="502ff-729">City</span></span>                  |
| <span data-ttu-id="502ff-730">Commune</span><span class="sxs-lookup"><span data-stu-id="502ff-730">County</span></span>              | <span data-ttu-id="502ff-731">Département (municipalité)</span><span class="sxs-lookup"><span data-stu-id="502ff-731">County (Municipality)</span></span> |
| <span data-ttu-id="502ff-732">Rue</span><span class="sxs-lookup"><span data-stu-id="502ff-732">Street</span></span>              | <span data-ttu-id="502ff-733">Ligne d'adresse 1</span><span class="sxs-lookup"><span data-stu-id="502ff-733">Address Line 1</span></span>        |
| <span data-ttu-id="502ff-734">Numéro de la rue</span><span class="sxs-lookup"><span data-stu-id="502ff-734">Street Number</span></span>       | <span data-ttu-id="502ff-735">Ligne d'adresse 2</span><span class="sxs-lookup"><span data-stu-id="502ff-735">Address Line 2</span></span>        |
| <span data-ttu-id="502ff-736">Info complémentaire sur le bâtiment</span><span class="sxs-lookup"><span data-stu-id="502ff-736">Building Complement</span></span> | <span data-ttu-id="502ff-737">Ligne d'adresse 5</span><span class="sxs-lookup"><span data-stu-id="502ff-737">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="502ff-738">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="502ff-738">Passport number</span></span>

<span data-ttu-id="502ff-739">Les employés peuvent déclarer des informations de passeport.</span><span class="sxs-lookup"><span data-stu-id="502ff-739">Employees can declare passport information.</span></span> <span data-ttu-id="502ff-740">Ces informations sont de type d'identification **Passeport** et sont intégrées à Dayforce dans le cadre des informations spécifique au Mexique d'un employé.</span><span class="sxs-lookup"><span data-stu-id="502ff-740">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="502ff-741">Type d'identification = « Passeport »</span><span class="sxs-lookup"><span data-stu-id="502ff-741">Identification Type = "Passport"</span></span>
- <span data-ttu-id="502ff-742">Date d'émission</span><span class="sxs-lookup"><span data-stu-id="502ff-742">Issued Date</span></span>
- <span data-ttu-id="502ff-743">Date d'expiration</span><span class="sxs-lookup"><span data-stu-id="502ff-743">Expiration Date</span></span>

<span data-ttu-id="502ff-744">Les employés peuvent déclarer plusieurs numéros d'identification de type d'identification **Passeport**.</span><span class="sxs-lookup"><span data-stu-id="502ff-744">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="502ff-745">Toutefois, seule la saisie de passeport actif actuel est intégrée à Dayforce.</span><span class="sxs-lookup"><span data-stu-id="502ff-745">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="502ff-746">Si toutes les entrées de passeport sont arrivées à expiration, le passeport émis le plus récemment est intégré dans Dayforce.</span><span class="sxs-lookup"><span data-stu-id="502ff-746">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
