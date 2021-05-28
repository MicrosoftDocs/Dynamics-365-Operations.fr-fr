---
title: Regulatory Configuration Service
description: Cette rubrique fournit une vue d'ensemble des fonctionnalités de Regulatory Configuration Service (RCS) et explique comment accéder au service.
author: JaneA07
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 1eeac7217290e0583fcecdf5b4b5b9153d266240
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019392"
---
# <a name="regulatory-configuration-service"></a><span data-ttu-id="09ceb-103">Regulatory Configuration Service</span><span class="sxs-lookup"><span data-stu-id="09ceb-103">Regulatory Configuration Service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="09ceb-104">Regulatory Configuration Service (RCS) est un concepteur autonome et un service de gestion du cycle de vie pour la fonctionnalité de globalisation sans code/à faible code.</span><span class="sxs-lookup"><span data-stu-id="09ceb-104">Regulatory Configuration Service (RCS) is a standalone designer and lifecycle management service for no-code/low-code globalization functionality.</span></span> <span data-ttu-id="09ceb-105">RCS permet aux acteurs de la globalisation d'étendre et de personnaliser les domaines clés de la globalisation que sont la fiscalité, la facturation électronique, la génération d’états réglementaires, les documents commerciaux et bancaires sans devoir faire appel à des développeurs.</span><span class="sxs-lookup"><span data-stu-id="09ceb-105">RCS lets globalization stakeholders extend and customize key globalization areas of tax, e-invoicing, regulatory reporting, banking, and business documents without having to involve developers.</span></span> <span data-ttu-id="09ceb-106">Cette approche de la globalisation sans code/à faible code rend la globalisation plus facile, plus rapide et plus économique à créer ou à étendre.</span><span class="sxs-lookup"><span data-stu-id="09ceb-106">This no-code/low-code globalization approach makes globalization easier, faster, and more cost effective to create or extend.</span></span>

<span data-ttu-id="09ceb-107">RCS fournit les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="09ceb-107">RCS provides the following capabilities:</span></span>

- <span data-ttu-id="09ceb-108">Prise en charge de toutes les fonctionnalités fournies par les la Gestion des états électroniques (ER).</span><span class="sxs-lookup"><span data-stu-id="09ceb-108">Support for all functionality that is provided by Electronic reporting (ER).</span></span>
- <span data-ttu-id="09ceb-109">Une condition préalable pour configurer de nouveaux microservices de globalisation.</span><span class="sxs-lookup"><span data-stu-id="09ceb-109">A prerequisite to configure new globalization microservices.</span></span>
- <span data-ttu-id="09ceb-110">Prise en charge de la facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="09ceb-110">Support for Electronic Invoicing.</span></span> <span data-ttu-id="09ceb-111">Pour plus d’informations, voir [Facturation électronique](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).</span><span class="sxs-lookup"><span data-stu-id="09ceb-111">For more information, see [Electronic Invoicing](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).</span></span>
- <span data-ttu-id="09ceb-112">Prise en charge du calcul des taxes.</span><span class="sxs-lookup"><span data-stu-id="09ceb-112">Supports for Tax Calculation.</span></span> <span data-ttu-id="09ceb-113">Pour plus d’informations, voir [Service de taxe](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).</span><span class="sxs-lookup"><span data-stu-id="09ceb-113">For more information, see [Tax service](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).</span></span>
- <span data-ttu-id="09ceb-114">Prise en charge de la nouvelle fonctionnalité de globalisation qui simplifie la gestion du cycle de vie des fonctionnalités multi-composants et offre une capacité supplémentaire pour configurer les actions et les paramètres de fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="09ceb-114">Support for new globalization feature functionality that simplifies the lifecycle management of multi-component features and provides extra capability to configure actions and set up feature parameters.</span></span> <span data-ttu-id="09ceb-115">Pour plus d'informations, voir [Regulatory Configuration Service - gestion simplifiée des fonctionnalités de globalisation pour les services de globalisation](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).</span><span class="sxs-lookup"><span data-stu-id="09ceb-115">For more information, see [Regulatory Configuration Service – simplified globalization feature management for globalization services](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).</span></span>
- <span data-ttu-id="09ceb-116">Prise en charge de la publication, du stockage et du partage centralisés des configurations personnalisées dans le référentiel global pour simplifier la gestion des configurations sans nécessiter l'utilisation de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="09ceb-116">Support for centralized publication, storage, and sharing of custom configurations in the Global repository to simplify configuration management without requiring the use of Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="access-rcs"></a><span data-ttu-id="09ceb-117">Accès à RCS</span><span class="sxs-lookup"><span data-stu-id="09ceb-117">Access RCS</span></span>

<span data-ttu-id="09ceb-118">Vous pouvez vous inscrire ou vous connecter à RCS à partir de la [page Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="09ceb-118">You can sign up for or sign in to RCS from the [Regulatory Configuration Service page](https://marketing.configure.global.dynamics.com/).</span></span>

![Inscription/connexion à RCS](media/202103_RCS%20Marketing%20page_updated_1.jpg)

<span data-ttu-id="09ceb-120">Sur la page **Regulatory Configuration Service**, lisez et acceptez les conditions générales supplémentaires d'utilisation du service, puis sélectionnez l'un des boutons suivants :</span><span class="sxs-lookup"><span data-stu-id="09ceb-120">On the **Regulatory Configuration Service** page, review and accept the supplemental terms and conditions for use of the service, and then select one of the following buttons:</span></span>

- <span data-ttu-id="09ceb-121">**S'inscrire** si vous utilisez le service pour la première fois et que vous utilisez une adresse e-mail professionnelle pour fournir à votre organisation un environnement de service</span><span class="sxs-lookup"><span data-stu-id="09ceb-121">**Sign up** if you're a first-time user of the service, and you're using a business email address to provision your organization a service environment</span></span>
- <span data-ttu-id="09ceb-122">**Se connecter** si vous vous êtes déjà inscrit au service et que vous souhaitez accéder à l'environnement de votre organisation</span><span class="sxs-lookup"><span data-stu-id="09ceb-122">**Sign in** if you've previously signed up for the service, and you want to access your organization environment</span></span>

## <a name="regional-availability"></a><span data-ttu-id="09ceb-123">Disponibilité régionale</span><span class="sxs-lookup"><span data-stu-id="09ceb-123">Regional availability</span></span>

<span data-ttu-id="09ceb-124">RCS est en disponibilité générale dans les régions suivantes :</span><span class="sxs-lookup"><span data-stu-id="09ceb-124">RCS is generally available in the following regions:</span></span>

- <span data-ttu-id="09ceb-125">Etats-Unis</span><span class="sxs-lookup"><span data-stu-id="09ceb-125">United States</span></span>
- <span data-ttu-id="09ceb-126">Inde</span><span class="sxs-lookup"><span data-stu-id="09ceb-126">India</span></span>
- <span data-ttu-id="09ceb-127">France</span><span class="sxs-lookup"><span data-stu-id="09ceb-127">France</span></span>
- <span data-ttu-id="09ceb-128">Europe</span><span class="sxs-lookup"><span data-stu-id="09ceb-128">Europe</span></span>

<span data-ttu-id="09ceb-129">Pour une liste complète des régions, voir [Dynamics 365 et Power Platform : disponibilité, emplacement des données, langue et localisation](https://aka.ms/dynamics_365_international_availability_deck).</span><span class="sxs-lookup"><span data-stu-id="09ceb-129">For a complete list of regions, see [Dynamics 365 and Power Platform: Availability, data location, language, and localization](https://aka.ms/dynamics_365_international_availability_deck).</span></span>

## <a name="related-rcs-documentation"></a><span data-ttu-id="09ceb-130">Documentation RCS connexe</span><span class="sxs-lookup"><span data-stu-id="09ceb-130">Related RCS documentation</span></span>

<span data-ttu-id="09ceb-131">Pour plus d’informations sur les composants associés, consultez la documentation suivante :</span><span class="sxs-lookup"><span data-stu-id="09ceb-131">For more information about related components, see the following documentation:</span></span>

- <span data-ttu-id="09ceb-132">**Référentiel global :**</span><span class="sxs-lookup"><span data-stu-id="09ceb-132">**Global repository:**</span></span>

    - [<span data-ttu-id="09ceb-133">Créer une configuration ER et charger dans le référentiel global</span><span class="sxs-lookup"><span data-stu-id="09ceb-133">Create ER configuration & upload to Global repo</span></span>](rcs-global-repo-upload.md)
    - [<span data-ttu-id="09ceb-134">Partager une configuration dans le référentiel global</span><span class="sxs-lookup"><span data-stu-id="09ceb-134">Share configuration in Global repo</span></span>](rcs-global-repo-share-configuration.md)
    - [<span data-ttu-id="09ceb-135">Filtrage amélioré dans le référentiel global</span><span class="sxs-lookup"><span data-stu-id="09ceb-135">Enhanced filtering in Global repo</span></span>](enhanced-filtering-global-repo.md)
    - [<span data-ttu-id="09ceb-136">Télécharger les configurations ER depuis le référentiel global</span><span class="sxs-lookup"><span data-stu-id="09ceb-136">Download ER configurations from the Global repository</span></span>](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [<span data-ttu-id="09ceb-137">Interrompre les configurations dans le référentiel global</span><span class="sxs-lookup"><span data-stu-id="09ceb-137">Discontinuing configurations in Global repo</span></span>](discontinuing-configurations-rcs-global-repo.md)

- <span data-ttu-id="09ceb-138">**Fonctionnalités de globalisation :**</span><span class="sxs-lookup"><span data-stu-id="09ceb-138">**Globalization feature:**</span></span>

    - [<span data-ttu-id="09ceb-139">Regulatory Configuration Service (RCS) - Fonction de globalisation</span><span class="sxs-lookup"><span data-stu-id="09ceb-139">Regulatory Configuration Service (RCS) - Globalization feature</span></span>](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)