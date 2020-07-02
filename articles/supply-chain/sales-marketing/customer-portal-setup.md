---
title: Installer, configurer et mettre à jour le portail client
description: Cette rubrique fournit des détails sur les licences et les instructions de configuration du portail client.
author: dasani-madipalli
manager: tfehr
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 0343100362c4d7bc3e09334fb7890919bdb84941
ms.sourcegitcommit: 7d943499f302298c6ff127f56cecc34af6cee289
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/08/2020
ms.locfileid: "3435606"
---
# <a name="install-set-up-and-update-the-customer-portal"></a><span data-ttu-id="ee081-103">Installer, configurer et mettre à jour le portail client</span><span class="sxs-lookup"><span data-stu-id="ee081-103">Install, set up, and update the Customer portal</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="ee081-104">Licences requises préalables</span><span class="sxs-lookup"><span data-stu-id="ee081-104">Licensing requirements</span></span>

<span data-ttu-id="ee081-105">Pour implémenter le portail client, vous devez disposer des licences suivantes :</span><span class="sxs-lookup"><span data-stu-id="ee081-105">To implement the Customer portal, you must have the following licenses:</span></span>

- <span data-ttu-id="ee081-106">**Portails Power Apps** – Cette licence est requise pour héberger le portail client.</span><span class="sxs-lookup"><span data-stu-id="ee081-106">**Power Apps portals** – This license is required to host the Customer portal.</span></span> <span data-ttu-id="ee081-107">Les licences de portail sont délivrées selon l'utilisation.</span><span class="sxs-lookup"><span data-stu-id="ee081-107">Portals are licensed based on usage.</span></span> <span data-ttu-id="ee081-108">Pour plus d'informations, voir [Conditions des licences des portails Power Apps](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals).</span><span class="sxs-lookup"><span data-stu-id="ee081-108">For more information, see the [Power Apps portals licensing requirements](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals).</span></span>
- <span data-ttu-id="ee081-109">**Double écriture** – Vous devez disposer des licences nécessaires pour activer la double écriture pour les entités de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ee081-109">**Dual-write** – You must have the necessary licenses to enable dual-write for Supply Chain Management entities.</span></span> <span data-ttu-id="ee081-110">Pour plus d'informations, voir [Configuration requise pour la double écriture](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span><span class="sxs-lookup"><span data-stu-id="ee081-110">For more information, see the [system requirements for dual-write](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span></span>

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a><span data-ttu-id="ee081-111">Dépendances à la double écriture et aux portails Power Apps</span><span class="sxs-lookup"><span data-stu-id="ee081-111">Dependencies on dual-write and Power Apps portals</span></span>

<span data-ttu-id="ee081-112">Le portail client dépend des portails Power Apps et de la double écriture, comme indiqué dans l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="ee081-112">The Customer portal depends on Power Apps portals and dual-write, as shown in the following illustration.</span></span>

<span data-ttu-id="ee081-113">![Dépendances du portail client](media/customer-portal-elements.png "Dépendances du portail client")</span><span class="sxs-lookup"><span data-stu-id="ee081-113">![Customer portal dependencies](media/customer-portal-elements.png "Customer portal dependencies")</span></span>

<span data-ttu-id="ee081-114">Contrairement aux autres fonctionnalités de Supply Chain Management, le modèle de portail client réside dans les portails Power Apps.</span><span class="sxs-lookup"><span data-stu-id="ee081-114">Unlike other features from Supply Chain Management, the Customer portal template resides in Power Apps portals.</span></span> <span data-ttu-id="ee081-115">Par conséquent, le portail client est limité par les fonctionnalités et capacités assurées par les portails Power Apps et les entités en double écriture.</span><span class="sxs-lookup"><span data-stu-id="ee081-115">Therefore, the Customer portal is limited by the functionality and capabilities that are provided by Power Apps portals and the entities in dual-write.</span></span>

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a><span data-ttu-id="ee081-116">Configuration requise pour activer le portail client</span><span class="sxs-lookup"><span data-stu-id="ee081-116">Required setup to enable the Customer portal</span></span>

<span data-ttu-id="ee081-117">Après vous être assuré que vous disposez des licences requises, vous pouvez configurer la double écriture comme décrit dans les [instructions de synchronisation initiale de la double écriture](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md).</span><span class="sxs-lookup"><span data-stu-id="ee081-117">After you've made sure that you have the required licenses, you can set up dual-write as described in the [dual-write initial synchronization instructions](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md).</span></span>

<span data-ttu-id="ee081-118">Veillez à activer les mappages d'entités suivants en double écriture :</span><span class="sxs-lookup"><span data-stu-id="ee081-118">Be sure to enable the following entity mappings in dual-write:</span></span>

- <span data-ttu-id="ee081-119">En-tête de commande client</span><span class="sxs-lookup"><span data-stu-id="ee081-119">Sales Order Header</span></span>
- <span data-ttu-id="ee081-120">Détails de la commande client</span><span class="sxs-lookup"><span data-stu-id="ee081-120">Sales Order Details</span></span>
- <span data-ttu-id="ee081-121">Comptes</span><span class="sxs-lookup"><span data-stu-id="ee081-121">Accounts</span></span>
- <span data-ttu-id="ee081-122">Contacts</span><span class="sxs-lookup"><span data-stu-id="ee081-122">Contacts</span></span>
- <span data-ttu-id="ee081-123">Produits</span><span class="sxs-lookup"><span data-stu-id="ee081-123">Products</span></span>

<span data-ttu-id="ee081-124">Une fois cette configuration terminée, vous pouvez provisionner le modèle de portail client.</span><span class="sxs-lookup"><span data-stu-id="ee081-124">After this setup is completed, you can provision the Customer portal template.</span></span>

## <a name="provision-the-customer-portal"></a><span data-ttu-id="ee081-125">Provisionner le portail client</span><span class="sxs-lookup"><span data-stu-id="ee081-125">Provision the Customer portal</span></span>

<span data-ttu-id="ee081-126">Avant de commencer, assurez-vous que vous avez déjà terminé la [configuration requise](#required-setup).</span><span class="sxs-lookup"><span data-stu-id="ee081-126">Before you begin, make sure that you've already completed the [required setup](#required-setup).</span></span> <span data-ttu-id="ee081-127">Suivez ensuite ces étapes pour provisionner le portail client.</span><span class="sxs-lookup"><span data-stu-id="ee081-127">Then follow these steps to provision the Customer portal.</span></span>

1. <span data-ttu-id="ee081-128">Accédez à [make.powerapps.com](https://make.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="ee081-128">Go to [make.powerapps.com](https://make.powerapps.com/).</span></span>
2. <span data-ttu-id="ee081-129">Assurez-vous que vous utilisez l'environnement dans lequel vous avez activé la double écriture.</span><span class="sxs-lookup"><span data-stu-id="ee081-129">Make sure that you're using the environment where you enabled dual-write.</span></span>
3. <span data-ttu-id="ee081-130">Dans l'onglet **Créer**, défilez jusqu'à la section **Commencer à partir du modèle** et sélectionnez le modèle nommé **Portail client**.</span><span class="sxs-lookup"><span data-stu-id="ee081-130">On the **Create** tab, scroll down to the **Start from template** section, and select the template that is named **Customer Portal**.</span></span>
4. <span data-ttu-id="ee081-131">Suivez les instructions à l'écran.</span><span class="sxs-lookup"><span data-stu-id="ee081-131">Follow the on-screen instructions.</span></span>

<span data-ttu-id="ee081-132">Une fois le provisionnement terminé, vous pouvez accéder au portail client dans la section **Vos applis** de la page **Accueil**.</span><span class="sxs-lookup"><span data-stu-id="ee081-132">After provisioning is completed, you can access the Customer portal in the **Your apps** section of the **Home** page.</span></span>

> [!NOTE]
> <span data-ttu-id="ee081-133">Si la solution de double écriture n'est pas installée dans l'environnement dans lequel vous travaillez, vous recevrez un message d'erreur et le portail client ne sera pas provisionné.</span><span class="sxs-lookup"><span data-stu-id="ee081-133">If the dual-write solution isn't installed in the environment that you're working in, you will receive an error message, and the Customer portal won't be provisioned.</span></span>

## <a name="update-the-customer-portal"></a><span data-ttu-id="ee081-134">Mettre à jour le portail client</span><span class="sxs-lookup"><span data-stu-id="ee081-134">Update the Customer portal</span></span>

<span data-ttu-id="ee081-135">D'autres fonctionnalités pourront être ajoutées au portail client ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="ee081-135">More functionality might be added to the Customer portal later.</span></span> <span data-ttu-id="ee081-136">Toute modification apportée par Microsoft aux composants de la solution sous-jacente apparaîtra automatiquement dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="ee081-136">Any changes that Microsoft makes to the underlying solution components will automatically appear in your environment.</span></span> <span data-ttu-id="ee081-137">Cependant, le site web provisionné dans votre environnement ne reflétera pas automatiquement les modifications apportées aux données de configuration.</span><span class="sxs-lookup"><span data-stu-id="ee081-137">However, the website that is provisioned in your environment won't automatically reflect changes that are made to the configuration data.</span></span> <span data-ttu-id="ee081-138">Vous devrez appliquer manuellement ces modifications en récupérant le code du nouveau modèle et en le fusionnant avec le site web provisionné.</span><span class="sxs-lookup"><span data-stu-id="ee081-138">You will have to manually apply those changes by getting the code from the new template and merging it with the provisioned website.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ee081-139">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ee081-139">Additional resources</span></span>

<span data-ttu-id="ee081-140">Pour savoir comment configurer et personnaliser le portail client, vous devez commencer par consulter la documentation suivante concernant les technologies sous-jacentes :</span><span class="sxs-lookup"><span data-stu-id="ee081-140">To learn how you can set up and customize the Customer portal, you should start by reviewing the following documentation for the underlying technologies:</span></span>

- [<span data-ttu-id="ee081-141">Documentation des portails Power Apps</span><span class="sxs-lookup"><span data-stu-id="ee081-141">Power Apps portals documentation</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)
- [<span data-ttu-id="ee081-142">Documentation de la double écriture</span><span class="sxs-lookup"><span data-stu-id="ee081-142">Dual-write documentation</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

<span data-ttu-id="ee081-143">Pour gérer efficacement vos portails, vous devez comprendre les portails Power Apps et le cycle de vie de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ee081-143">To effectively manage your portals, you must understand the Power Apps portals and Common Data Service lifecycle.</span></span> <span data-ttu-id="ee081-144">Pour plus d’informations, voir les ressources suivantes (éventuellement en anglais) :</span><span class="sxs-lookup"><span data-stu-id="ee081-144">For more information, see the following resources:</span></span>

- [<span data-ttu-id="ee081-145">À propos du cycle de vie des portails</span><span class="sxs-lookup"><span data-stu-id="ee081-145">About portal lifecycle</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/portal-lifecycle)
- [<span data-ttu-id="ee081-146">Mettre à niveau un portail</span><span class="sxs-lookup"><span data-stu-id="ee081-146">Upgrade a portal</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/upgrade-portal)
- [<span data-ttu-id="ee081-147">Migrer la configuration d'un portail</span><span class="sxs-lookup"><span data-stu-id="ee081-147">Migrate portal configuration</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/migrate-portal-configuration)
- [<span data-ttu-id="ee081-148">Gestion du cycle de vie des solutions : applications Dynamics 365 for Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="ee081-148">Solution Lifecycle Management: Dynamics 365 for Customer Engagement apps</span></span>](https://www.microsoft.com/download/details.aspx?id=57777)
