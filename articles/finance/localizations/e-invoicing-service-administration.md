---
title: Composants d’administration de la Facturation électronique
description: Cette rubrique fournit des informations sur les composants liés à l’administration de la Facturation électronique.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 2e859875e124796e49000cd5ea94cfb75ecd768a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840026"
---
# <a name="electronic-invoicing-administration-components"></a><span data-ttu-id="9691a-103">Composants d’administration de la Facturation électronique</span><span class="sxs-lookup"><span data-stu-id="9691a-103">Electronic invoicing administration components</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="9691a-104">Cette rubrique fournit des informations sur les composants liés à l’administration de la Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="9691a-104">This topic provides information about the components that are related to administration of Electronic invoicing.</span></span> <span data-ttu-id="9691a-105">Elle fournit également des informations sur la configuration du service de Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="9691a-105">It also provides information about how to configure the Electronic invoicing service.</span></span>

## <a name="azure"></a><span data-ttu-id="9691a-106">Azure</span><span class="sxs-lookup"><span data-stu-id="9691a-106">Azure</span></span>

<span data-ttu-id="9691a-107">Utilisez Microsoft Azure pour créer les secrets du coffre de clés et du compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="9691a-107">Use Microsoft Azure to create the secrets for the key vault and storage account.</span></span> <span data-ttu-id="9691a-108">Utilisez ensuite les secrets dans la configuration de la Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="9691a-108">Then use the secrets in the configuration of Electronic invoicing.</span></span>

## <a name="lifecycle-services"></a><span data-ttu-id="9691a-109">Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="9691a-109">Lifecycle Services</span></span>

<span data-ttu-id="9691a-110">Utilisez Microsoft Dynamics Lifecycle Services (LCS) pour activer les microservices de votre projet de déploiement LCS.</span><span class="sxs-lookup"><span data-stu-id="9691a-110">Use Microsoft Dynamics Lifecycle Services (LCS) to enable the microservices for your LCS deployment project.</span></span>

> [!NOTE]
> <span data-ttu-id="9691a-111">L’installation du microservice dans LCS nécessite au moins une machine virtuelle de niveau 2.</span><span class="sxs-lookup"><span data-stu-id="9691a-111">The installation of the microservice in LCS requires at least a Tier 2 virtual machine.</span></span> <span data-ttu-id="9691a-112">Pour plus d’informations sur la planification de l’environnement, voir [Planification de l’environnement](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="9691a-112">For more information about environment planning, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
 

## <a name="regulatory-configuration-services"></a><span data-ttu-id="9691a-113">Regulatory Configuration Services</span><span class="sxs-lookup"><span data-stu-id="9691a-113">Regulatory Configuration Services</span></span>

<span data-ttu-id="9691a-114">Dynamics 365 Regulatory Configuration Services (RCS) est l’interface utilisée pour configurer la Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="9691a-114">Dynamics 365 Regulatory Configuration Services (RCS) is the interface that is used to configure Electronic invoicing.</span></span> <span data-ttu-id="9691a-115">Des ressources telles que des environnements et des fonctionnalités de facturation électronique sont créées, gérées et hébergées dans RCS.</span><span class="sxs-lookup"><span data-stu-id="9691a-115">Resources such as environments and electronic invoicing features are created, maintained, and hosted in RCS.</span></span> <span data-ttu-id="9691a-116">Lorsque les ressources sont prêtes, elles sont publiées dans le service de Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="9691a-116">When the resources are ready, they are published to Electronic invoicing service.</span></span>

<span data-ttu-id="9691a-117">Pour l’inscription au RCS, voir [Regulatory services](https://marketing.configure.global.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="9691a-117">For RCS sign-up, see [Regulatory services](https://marketing.configure.global.dynamics.com/).</span></span>

<span data-ttu-id="9691a-118">Pour plus d’informations sur RCS, voir [Regulatory Configuration Services (RCS) – Fonctionnalités de globalisation](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="9691a-118">For more information about RCS, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md)</span></span>

### <a name="integration-with-electronic-invoicing"></a><span data-ttu-id="9691a-119">Intégration avec la Facturation électronique</span><span class="sxs-lookup"><span data-stu-id="9691a-119">Integration with Electronic invoicing</span></span> 

<span data-ttu-id="9691a-120">Avant de pouvoir utiliser RCS pour configurer des factures électroniques, vous devez le configurer pour permettre la communication avec la Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="9691a-120">Before you can use RCS to configure electronic invoices, you must configure RCS to allow for communication with Electronic invoicing.</span></span> <span data-ttu-id="9691a-121">Vous devez effectuer cette configuration sur l’onglet **Facturation électronique** de la page **Paramètres de la gestion des états électroniques**.</span><span class="sxs-lookup"><span data-stu-id="9691a-121">You complete this configuration on the **Electronic invoicing** tab of the **Electronic reporting parameters** page.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="9691a-122">Point de terminaison de service</span><span class="sxs-lookup"><span data-stu-id="9691a-122">Service endpoint</span></span>

<span data-ttu-id="9691a-123">La Facturation électronique est disponible dans plusieurs emplacements géographiques du centre de données Azure.</span><span class="sxs-lookup"><span data-stu-id="9691a-123">Electronic invoicing is available in several Azure datacenter geographies.</span></span> <span data-ttu-id="9691a-124">Le tableau suivant répertorie la disponibilité par région.</span><span class="sxs-lookup"><span data-stu-id="9691a-124">The following table lists the availability per region.</span></span>

| <span data-ttu-id="9691a-125">Emplacement géographique du centre de données Azure</span><span class="sxs-lookup"><span data-stu-id="9691a-125">Azure datacenter geography</span></span> |
|----------------------------|
| <span data-ttu-id="9691a-126">Est des États-Unis</span><span class="sxs-lookup"><span data-stu-id="9691a-126">East US</span></span>                    |
| <span data-ttu-id="9691a-127">Ouest des États-Unis</span><span class="sxs-lookup"><span data-stu-id="9691a-127">West US</span></span>                    |
| <span data-ttu-id="9691a-128">Nord de l’UE</span><span class="sxs-lookup"><span data-stu-id="9691a-128">North EU</span></span>                   |
| <span data-ttu-id="9691a-129">Ouest de l’UE</span><span class="sxs-lookup"><span data-stu-id="9691a-129">West EU</span></span>                    |

### <a name="service-environments"></a><span data-ttu-id="9691a-130">Environnements de service</span><span class="sxs-lookup"><span data-stu-id="9691a-130">Service environments</span></span>

<span data-ttu-id="9691a-131">Les environnements de service sont des partitions logiques créées pour prendre en charge l’exécution des fonctionnalités de facturation électronique dans la Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="9691a-131">Service environments are logical partitions that are created to support execution of the electronic invoicing features in Electronic invoicing.</span></span> <span data-ttu-id="9691a-132">Les secrets de sécurité et les certificats numériques, ainsi que la gouvernance (c’est-à-dire les autorisations d’accès), doivent être configurés au niveau de l’environnement de service.</span><span class="sxs-lookup"><span data-stu-id="9691a-132">The security secrets and digital certificates, and the governance (that is, access permissions), must be configured at the service environment level.</span></span>

<span data-ttu-id="9691a-133">Les clients peuvent créer autant d’environnements de service qu’ils le souhaitent.</span><span class="sxs-lookup"><span data-stu-id="9691a-133">Customers can create as many service environments as they want.</span></span> <span data-ttu-id="9691a-134">Tous les environnements de service créés par un client sont indépendants les uns des autres.</span><span class="sxs-lookup"><span data-stu-id="9691a-134">All the service environments that a customer creates are independent of each other.</span></span>

<span data-ttu-id="9691a-135">Les environnements de service doivent être créés et gérés dans RCS.</span><span class="sxs-lookup"><span data-stu-id="9691a-135">Service environments must be created and maintained in RCS.</span></span> <span data-ttu-id="9691a-136">Lorsque les environnements de service sont prêts, ils doivent être publiés dans la Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="9691a-136">When the service environments are ready, they must be published to Electronic invoicing.</span></span>

#### <a name="service-environment-status"></a><span data-ttu-id="9691a-137">Statut de l’environnement de service</span><span class="sxs-lookup"><span data-stu-id="9691a-137">Service environment status</span></span>

<span data-ttu-id="9691a-138">Les environnements de service peuvent être gérés via leur statut.</span><span class="sxs-lookup"><span data-stu-id="9691a-138">Service environments can be managed through status.</span></span> <span data-ttu-id="9691a-139">Les options possibles sont :</span><span class="sxs-lookup"><span data-stu-id="9691a-139">The possible options are:</span></span>

- <span data-ttu-id="9691a-140">**Non publié** – L’environnement a été créé, mais il n’a pas encore été publié.</span><span class="sxs-lookup"><span data-stu-id="9691a-140">**Not published** – The environment has been created, but it hasn't yet been published.</span></span>
- <span data-ttu-id="9691a-141">**Publié** – L’environnement a été publié dans la Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="9691a-141">**Published** – The environment has been published to Electronic invoicing .</span></span>
- <span data-ttu-id="9691a-142">**Modifié** – Les attributs d’un environnement publié ont été modifiés, mais les modifications n’ont pas encore été publiées.</span><span class="sxs-lookup"><span data-stu-id="9691a-142">**Changed** – The attributes of a published environment have been changed, but the changes haven't yet been published.</span></span>

#### <a name="customer-secrets"></a><span data-ttu-id="9691a-143">Secrets clients</span><span class="sxs-lookup"><span data-stu-id="9691a-143">Customer secrets</span></span>

<span data-ttu-id="9691a-144">Le service de Facturation électronique a la responsabilité de stocker toutes vos données métier dans les ressources Azure appartenant à votre société.</span><span class="sxs-lookup"><span data-stu-id="9691a-144">The Electronic invoicing service is responsible for storing all your business data in the Azure resources that your company owns.</span></span> <span data-ttu-id="9691a-145">Pour vous assurer que le service fonctionne correctement et que toutes les données métier requises et générées par la Facturation électronique ne sont accessibles que de manière appropriée, vous devez créer deux ressources Azure principales :</span><span class="sxs-lookup"><span data-stu-id="9691a-145">To ensure that the service works correctly, and that all the business data that is required for and generated by Electronic invoicing is accessed appropriately, you must create two main Azure resources:</span></span>

- <span data-ttu-id="9691a-146">Un compte de stockage Azure (stockage Blob) qui va stocker les factures électroniques</span><span class="sxs-lookup"><span data-stu-id="9691a-146">An Azure storage account (Blob storage) that will store electronic invoices</span></span>
- <span data-ttu-id="9691a-147">Un coffre de clés Azure qui va stocker les certificats et l’Uniform Resource Identifier (URI) du compte de stockage</span><span class="sxs-lookup"><span data-stu-id="9691a-147">An Azure key vault that will store certificates and the uniform resource identifier (URI) of the storage account</span></span>

> [!NOTE]
> <span data-ttu-id="9691a-148">Une ressource de coffre de clés dédiée et un compte de stockage client doivent être alloués spécifiquement pour une utilisation avec la Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="9691a-148">A dedicated key vault and customer storage account must be allocated specifically for use with the Electronic invoicing .</span></span>

<span data-ttu-id="9691a-149">Pour plus d’informations, voir [Créer un compte de stockage Azure et un coffre de clés](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="9691a-149">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

#### <a name="users"></a><span data-ttu-id="9691a-150">Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9691a-150">Users</span></span>

<span data-ttu-id="9691a-151">Chaque environnement de service doit répertorier les utilisateurs qui peuvent se connecter à partir de Dynamics 365 Finance et Dynamics 365 Supply Chain Management à la Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="9691a-151">Each service environment must list the users who can connect from Dynamics 365 Finance and Dynamics 365 Supply Chain Management in Electronic invoicing.</span></span>

#### <a name="publication"></a><span data-ttu-id="9691a-152">Publication</span><span class="sxs-lookup"><span data-stu-id="9691a-152">Publication</span></span>

<span data-ttu-id="9691a-153">Les environnements de service doivent être publiés dans la Facturation électronique avant de pouvoir être utilisés.</span><span class="sxs-lookup"><span data-stu-id="9691a-153">Service environments must be published to Electronic invoicing before they can be used.</span></span> <span data-ttu-id="9691a-154">Seuls les environnements publiés sont accessibles par Finance et Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9691a-154">Only published environments can be accessed by Finance and Supply Chain Management.</span></span> <span data-ttu-id="9691a-155">De plus, un environnement de service doit être publié avant que toute mise à jour de ses attributs ne prenne effet sur le service de facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="9691a-155">Additionally, a service environment must be published before any updates to its attributes will take effect on the electronic invoicing service.</span></span>

### <a name="connected-applications"></a><span data-ttu-id="9691a-156">Applications connectées</span><span class="sxs-lookup"><span data-stu-id="9691a-156">Connected applications</span></span>

<span data-ttu-id="9691a-157">Les applications connectées sont les instances de Finance et Supply Chain Management que vous souhaitez peut-être atteindre via RCS.</span><span class="sxs-lookup"><span data-stu-id="9691a-157">Connected applications are the instances of Finance and Supply Chain Management that you might want to reach through RCS.</span></span> <span data-ttu-id="9691a-158">Outre l’URL de l’application et son client, une application connectée contient les informations d’identification qui permettent à RCS de se connecter à l’environnement.</span><span class="sxs-lookup"><span data-stu-id="9691a-158">Besides the application URL and its tenant, a connected application contains the credentials that enable RCS to connect to the environment.</span></span>

<span data-ttu-id="9691a-159">Grâce aux applications connectées, vous pouvez configurer une partie de la fonction de facturation électronique dans Finance et Supply Chain Management pour faire fonctionner l’ensemble de la fonction de facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="9691a-159">Through the connected applications, you can configure part of the electronic invoicing feature in Finance and Supply Chain Management to make the whole electronic invoicing feature work.</span></span>

## <a name="finance-and-supply-chain-management"></a><span data-ttu-id="9691a-160">Finance et Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="9691a-160">Finance and Supply Chain Management</span></span>

### <a name="integration-with-electronic-invoicing"></a><span data-ttu-id="9691a-161">Intégration avec la Facturation électronique</span><span class="sxs-lookup"><span data-stu-id="9691a-161">Integration with Electronic invoicing</span></span>

<span data-ttu-id="9691a-162">Avant de pouvoir utiliser Finance et Supply Chain Management pour émettre des factures électroniques via la Facturation électronique, ils doivent être configurés pour permettre la communication avec le service.</span><span class="sxs-lookup"><span data-stu-id="9691a-162">Before you can use Finance and Supply Chain Management to issue electronic invoices through Electronic invoicing, it must be configured to allow for communication with the service.</span></span>

#### <a name="electronic-invoicing-integration-feature"></a><span data-ttu-id="9691a-163">Fonctionnalité d’intégration de la Facturation électronique</span><span class="sxs-lookup"><span data-stu-id="9691a-163">Electronic invoicing integration feature</span></span>

<span data-ttu-id="9691a-164">Pour activer la communication entre Finance et Supply Chain Management et la Facturation électronique, vous devez activer la fonctionnalité **Intégration de la Facturation électronique** dans l’espace de travail **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="9691a-164">To enable communication between Finance and Supply Chain Management and Electronic invoicing, you must turn on the **Electronic Invoicing integration** feature in the **Feature management** workspace.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="9691a-165">Point de terminaison de service</span><span class="sxs-lookup"><span data-stu-id="9691a-165">Service endpoint</span></span>

<span data-ttu-id="9691a-166">Le point de terminaison du service est l’URL où se trouve la Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="9691a-166">The service endpoint is the URL where Electronic invoicing is located.</span></span> <span data-ttu-id="9691a-167">Pour pouvoir émettre des factures électroniques, le point de terminaison de service doit être configuré dans Finance et Supply Chain Management pour permettre la communication avec le service.</span><span class="sxs-lookup"><span data-stu-id="9691a-167">Before electronic invoices can be issued, the service endpoint must be configured in Finance and Supply Chain Management to allow for communication with the service.</span></span>

<span data-ttu-id="9691a-168">Pour configurer le point de terminaison du service, accédez à **Administration d’organisation \> Paramétrage \> Paramètres des documents électroniques**, puis, sur l’onglet **Services de soumission**, dans le champ **URL de la Facturation électronique**, entrez l’URL comme décrit dans le tableau de la section **Point de terminaison du service**.</span><span class="sxs-lookup"><span data-stu-id="9691a-168">To configure the service endpoint, go to **Organization administration \> Setup \> Electronic document parameter**, and then, on the **Submission services** tab, in the **Electronic invoicing URL** field, enter the URL as described in the table described in section **Service endpoint**.</span></span>

#### <a name="environments"></a><span data-ttu-id="9691a-169">Environnements</span><span class="sxs-lookup"><span data-stu-id="9691a-169">Environments</span></span>

<span data-ttu-id="9691a-170">Le nom de l’environnement entré dans Finance et Supply Chain Management fait référence au nom de l’environnement créé dans RCS et publié dans la Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="9691a-170">The environment name that is entered in Finance and Supply Chain Management refers to the name of the environment that is created in RCS and published to Electronic invoicing.</span></span>

<span data-ttu-id="9691a-171">L’environnement doit être configuré sur l’onglet **Services de soumission** de la page **Paramètres des documents électroniques**, de sorte que chaque demande d’émission de factures électroniques contienne l’environnement dans lequel la Facturation électronique peut déterminer quelle fonction de facturation électronique doit traiter la demande.</span><span class="sxs-lookup"><span data-stu-id="9691a-171">The environment must be configured on the **Submission services** tab of the **Electronic document parameter** page, so that every request to issue electronic invoices contains the environment where Electronic invoicing can determine which electronic invoicing feature must process the request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9691a-172">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="9691a-172">Additional resources</span></span>

- [<span data-ttu-id="9691a-173">Configurer des factures électroniques dans RCS</span><span class="sxs-lookup"><span data-stu-id="9691a-173">Configure electronic invoices in RCS</span></span>](e-invoicing-configuration-rcs.md)
- [<span data-ttu-id="9691a-174">Émettre des factures électroniques dans Finance et Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="9691a-174">Issue electronic invoices in Finance and Supply Chain Management</span></span>](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
