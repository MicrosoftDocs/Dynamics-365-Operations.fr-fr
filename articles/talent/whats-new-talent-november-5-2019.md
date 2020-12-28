---
title: Nouveautés ou modifications dans Dynamics 365 Talent (5 novembre 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-11-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c4068cf81782d2f9559179b91da31e049c006059
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527118"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-5-2019"></a><span data-ttu-id="15e79-103">Nouveautés ou modifications dans Dynamics 365 Talent (5 novembre 2019)</span><span class="sxs-lookup"><span data-stu-id="15e79-103">What's new or changed in Dynamics 365 Talent (November 5, 2019)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="15e79-104">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="15e79-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="15e79-105">Modifications apportées dans Attract</span><span class="sxs-lookup"><span data-stu-id="15e79-105">Changes in Attract</span></span>

<span data-ttu-id="15e79-106">Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="15e79-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="15e79-107">Modifications apportées à Onboard</span><span class="sxs-lookup"><span data-stu-id="15e79-107">Changes in Onboard</span></span>

<span data-ttu-id="15e79-108">Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="15e79-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="15e79-109">Modifications apportées à Core HR</span><span class="sxs-lookup"><span data-stu-id="15e79-109">Changes in Core HR</span></span>

<span data-ttu-id="15e79-110">Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2598.</span><span class="sxs-lookup"><span data-stu-id="15e79-110">Changes described in this section apply to build number 8.1.2598.</span></span> <span data-ttu-id="15e79-111">Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="15e79-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="copy-a-core-hr-instance"></a><span data-ttu-id="15e79-112">Copier une instance Core HR</span><span class="sxs-lookup"><span data-stu-id="15e79-112">Copy a Core HR instance</span></span>

<span data-ttu-id="15e79-113">Dans la version de cette semaine, vous pouvez utiliser Microsoft Dynamics Lifecycle Services (LCS) pour copier une base de données Microsoft Dynamics 365 Talent: Core HR dans un environnement de bac à sable.</span><span class="sxs-lookup"><span data-stu-id="15e79-113">In this week's release, you can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Talent: Core HR database to a sandbox environment.</span></span> <span data-ttu-id="15e79-114">Si vous avez un autre environnement de bac à sable, vous pouvez également copier la base de données de cet environnement vers un environnement cible de bac à sable.</span><span class="sxs-lookup"><span data-stu-id="15e79-114">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span> <span data-ttu-id="15e79-115">Pour plus d'informations, voir :</span><span class="sxs-lookup"><span data-stu-id="15e79-115">For more information, see:</span></span>

- <span data-ttu-id="15e79-116">[Gestion de l'environnement plus étendue](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) dans Dynamics 365 : 2e partie du lancement 2019.</span><span class="sxs-lookup"><span data-stu-id="15e79-116">[Broader environment management](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) in the Dynamics 365: 2019 release wave 2 plan</span></span>

- <span data-ttu-id="15e79-117">[Copier une instance Core HR](hr-copy-instance.md) dans la documentation Talent</span><span class="sxs-lookup"><span data-stu-id="15e79-117">[Copy a Core HR instance](hr-copy-instance.md) in Talent documentation</span></span>

### <a name="common-data-service-integration-batch-jobs-arent-created-when-common-data-service-integration-is-enabled-388030"></a><span data-ttu-id="15e79-118">Les traitements par lots d'intégration Common Data Service ne sont pas créés lorsque l'intégration Common Data Service est activée (388030)</span><span class="sxs-lookup"><span data-stu-id="15e79-118">Common Data Service integration batch jobs aren't created when Common Data Service integration is enabled (388030)</span></span>

<span data-ttu-id="15e79-119">Cette modification créera des traitements par lots pour l'intégration de Common Data Service lorsqu'elle s'est activée.</span><span class="sxs-lookup"><span data-stu-id="15e79-119">This change will create batch jobs for Common Data Service integration when it's enabled.</span></span>

### <a name="the-hcmpersonimageentity-doesnt-resize-the-person-image-when-uploaded-369469"></a><span data-ttu-id="15e79-120">HcmPersonImageEntity ne redimensionne pas l'image de la personne une fois téléchargée (369469)</span><span class="sxs-lookup"><span data-stu-id="15e79-120">The HcmPersonImageEntity doesn't resize the person image when uploaded (369469)</span></span>

<span data-ttu-id="15e79-121">La publication de cette semaine modifie comment les images sont redimensionnées pour de meilleures performances lors de l'importation via la gestion des données.</span><span class="sxs-lookup"><span data-stu-id="15e79-121">This week's release changes how images are resized for better performance when imported through data management.</span></span>

### <a name="a-positions-available-for-assignment-date-can-be-earlier-than-the-activation-date-340103"></a><span data-ttu-id="15e79-122">Une Date disponible pour affectation du poste peut être antérieure à la Date d'activation (340103)</span><span class="sxs-lookup"><span data-stu-id="15e79-122">A position's Available for assignment date can be earlier than the Activation date (340103)</span></span>

<span data-ttu-id="15e79-123">Avec cette modification, un avertissement s'affichera si vous sélectionnez une **Date disponible pour affectation** antérieure à la **Date d'activation** du poste.</span><span class="sxs-lookup"><span data-stu-id="15e79-123">With this change, a warning will appear if you select an **Available for assignment date** that's earlier than the position's **Activation date**.</span></span>

### <a name="cant-create-a-compensation-change-request-in-employee-self-service-for-step-based-plans-376872"></a><span data-ttu-id="15e79-124">Impossible de créer une demande de modification de rémunération dans le libre-service pour les employés pour les plans basés sur des étapes (376872)</span><span class="sxs-lookup"><span data-stu-id="15e79-124">Can't create a compensation change request in employee self-service for step-based plans (376872)</span></span>

<span data-ttu-id="15e79-125">Cette version corrige un problème lors de la demande des modifications de rémunération via le libre-service des employés pour les plans basés sur des étapes.</span><span class="sxs-lookup"><span data-stu-id="15e79-125">This release corrects an issue when requesting compensation changes through employee self-service for step-based plans.</span></span> 

### <a name="reason-code-doesnt-sync-to-common-data-service-if-the-description-is-longer-than-30-characters-core-hr-allows-60-352682"></a><span data-ttu-id="15e79-126">Le code de motif ne se synchronise pas à Common Data Service si la description est supérieure à 30 caractères, Core HR en autorise 60 (352682)</span><span class="sxs-lookup"><span data-stu-id="15e79-126">Reason code doesn't sync to Common Data Service if the description is longer than 30 characters, Core HR allows 60 (352682)</span></span>

<span data-ttu-id="15e79-127">à cette modification, les codes de motif avec plus de 30 caractères sont mis à jour dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="15e79-127">with this change, reason codes with more than 30 characters will be updated in Common Data Service.</span></span> <span data-ttu-id="15e79-128">Les modifications effectuées dans Common Data Service seront également répercutées dans Talent.</span><span class="sxs-lookup"><span data-stu-id="15e79-128">Changes made in Common Data Service will also be reflected back in Talent.</span></span>

### <a name="address-integration-from-talent-to-finance-and-operations-351961"></a><span data-ttu-id="15e79-129">Abordez l'intégration de Talent à Finance and Operations (351961)</span><span class="sxs-lookup"><span data-stu-id="15e79-129">Address integration from Talent to Finance and Operations (351961)</span></span>

<span data-ttu-id="15e79-130">Cette version fixe un problème où les adresses mises à jour dans Talent n'étaient pas mises à jour dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="15e79-130">This release fixes an issue where addresses updated in Talent weren't updating in Finance and Operations.</span></span> <span data-ttu-id="15e79-131">Les modifications apportées aux blocs d'adresse seront désormais à jour.</span><span class="sxs-lookup"><span data-stu-id="15e79-131">Changes to address blocks will now update.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="15e79-132">Prochainement</span><span class="sxs-lookup"><span data-stu-id="15e79-132">Coming soon</span></span>

### <a name="print-performance-reviews"></a><span data-ttu-id="15e79-133">Imprimer les évaluations des performances</span><span class="sxs-lookup"><span data-stu-id="15e79-133">Print performance reviews</span></span>

<span data-ttu-id="15e79-134">Voir [Imprimer les examens des performances](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) dans Dynamics 365 : 2e partie du lancement 2019.</span><span class="sxs-lookup"><span data-stu-id="15e79-134">See [Print performance reviews](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) in the Dynamics 365: 2019 release wave 2 plan.</span></span>

### <a name="feature-management-workspace"></a><span data-ttu-id="15e79-135">Espace de travail Gestion des fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="15e79-135">Feature management workspace</span></span>

<span data-ttu-id="15e79-136">Les fonctionnalités sont ajoutées et mises à jour dans chaque version.</span><span class="sxs-lookup"><span data-stu-id="15e79-136">Features are added and updated in every release.</span></span> <span data-ttu-id="15e79-137">L'expérience de gestion de la fonctionnalité fournit un espace de travail dans lequel vous pouvez afficher une liste des fonctionnalités fournies dans chaque version.</span><span class="sxs-lookup"><span data-stu-id="15e79-137">The feature management experience provides a workspace where you can view a list of features that have been delivered in each release.</span></span> <span data-ttu-id="15e79-138">Par défaut, les nouvelles fonctionnalités sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="15e79-138">By default, new features are turned off.</span></span> <span data-ttu-id="15e79-139">Vous pouvez utiliser l'espace de travail pour les activer et consulter la documentation les concernant.</span><span class="sxs-lookup"><span data-stu-id="15e79-139">You can use the workspace to turn them on and view the documentation for them.</span></span>

<span data-ttu-id="15e79-140">Pour en savoir plus sur les modifications venant avec la gestion des fonctionnalités, voir [Vue d'ensemble de la gestion des fonctionnalités](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="15e79-140">To learn more about the changes coming with feature management, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>
