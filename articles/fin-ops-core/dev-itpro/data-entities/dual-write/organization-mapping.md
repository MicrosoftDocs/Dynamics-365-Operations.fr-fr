---
title: Hiérarchie d’organisation dans Dataverse
description: Cette rubrique décrit l’intégration des données organisationnelles entre les applications Finance and Operations et Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: f265d49a87383e2abf129b8d1d67567fc4b9e0de
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559577"
---
# <a name="organization-hierarchy-in-dataverse"></a><span data-ttu-id="96fa9-103">Hiérarchie d’organisation dans Dataverse</span><span class="sxs-lookup"><span data-stu-id="96fa9-103">Organization hierarchy in Dataverse</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="96fa9-104">Comme Dynamics 365 Finance est un système financier, l’*organisation* est un concept de base, et le système commence par la configuration d’une hiérarchie d’organisation.</span><span class="sxs-lookup"><span data-stu-id="96fa9-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="96fa9-105">Les opérations financières et commerciales peuvent ensuite être suivies au niveau de l’organisation et également à tous les niveaux de la hiérarchie d’organisation.</span><span class="sxs-lookup"><span data-stu-id="96fa9-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="96fa9-106">Bien que Dataverse ne dispose pas du concept de hiérarchie d’organisation, il dispose de certains concepts flous, tels que le total du produit des ventes.</span><span class="sxs-lookup"><span data-stu-id="96fa9-106">Although Dataverse doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="96fa9-107">Dans le cadre de l’intégration de Dataverse, la structure de données de la hiérarchie d’organisation est ajoutée à Dataverse.</span><span class="sxs-lookup"><span data-stu-id="96fa9-107">As part of Dataverse integration, the organization hierarchy data structure is added to Dataverse.</span></span>

## <a name="data-flow"></a><span data-ttu-id="96fa9-108">Flux de données</span><span class="sxs-lookup"><span data-stu-id="96fa9-108">Data flow</span></span>

<span data-ttu-id="96fa9-109">Un écosystème commercial composé des applications Finance and Operations et de Dataverse continue d’avoir une hiérarchie d’organisation.</span><span class="sxs-lookup"><span data-stu-id="96fa9-109">A business ecosystem that consists of Finance and Operations apps and Dataverse will continue to have an organization hierarchy.</span></span> <span data-ttu-id="96fa9-110">Cette hiérarchie d’organisation repose sur les applications Finance and Operations, mais elle est exposée dans Dataverse à des fins d’informations et d’extensibilité.</span><span class="sxs-lookup"><span data-stu-id="96fa9-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Dataverse for informational and extensibility purposes.</span></span> <span data-ttu-id="96fa9-111">L’illustration suivante présente les informations de la hiérarchie d’organisation exposées dans Dataverse comme un flux unidirectionnel entre les applications Finance and Operations et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="96fa9-111">The following illustration shows the organization hierarchy information that is exposed in Dataverse as a one-way data flow from Finance and Operations apps to Dataverse.</span></span>

![Image de l’architecture](media/dual-write-data-flow.png)

<span data-ttu-id="96fa9-113">Des mises en correspondance de la table Hiérarchie d’organisation sont disponibles pour la synchronisation unidirectionnelle des données entre les applications Finance and Operations et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="96fa9-113">Organization hierarchy table maps are available for one-way synchronization of data from Finance and Operations apps to Dataverse.</span></span>

## <a name="templates"></a><span data-ttu-id="96fa9-114">Modèles</span><span class="sxs-lookup"><span data-stu-id="96fa9-114">Templates</span></span>

<span data-ttu-id="96fa9-115">Les informations de produit contiennent toutes les informations associées au produit et à sa définition, comme les dimensions du produit ou les dimensions de suivi et de stockage.</span><span class="sxs-lookup"><span data-stu-id="96fa9-115">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="96fa9-116">Lorsque le tableau suivant s’affiche, un ensemble de cartes de tables est créé pour synchroniser les produits et les informations associées.</span><span class="sxs-lookup"><span data-stu-id="96fa9-116">As the following table shows, a collection of table maps is created to sync products and related information.</span></span>

<span data-ttu-id="96fa9-117">Applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="96fa9-117">Finance and Operations apps</span></span> | <span data-ttu-id="96fa9-118">Autres applications Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="96fa9-118">Other Dynamics 365 apps</span></span> | <span data-ttu-id="96fa9-119">Description</span><span class="sxs-lookup"><span data-stu-id="96fa9-119">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="96fa9-120">Objectifs de la hiérarchie d’organisation</span><span class="sxs-lookup"><span data-stu-id="96fa9-120">Organization hierarchy purposes</span></span> | <span data-ttu-id="96fa9-121">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="96fa9-121">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="96fa9-122">Ce modèle fournit une synchronisation unidirectionnelle de la table Objectif de la hiérarchie d’organisation.</span><span class="sxs-lookup"><span data-stu-id="96fa9-122">This template provides one-way synchronization of the Organization Hierarchy Purpose table.</span></span>
<span data-ttu-id="96fa9-123">Type de la hiérarchie d'organisation</span><span class="sxs-lookup"><span data-stu-id="96fa9-123">Organization hierarchy type</span></span> | <span data-ttu-id="96fa9-124">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="96fa9-124">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="96fa9-125">Ce modèle fournit une synchronisation unidirectionnelle de la table Type de hiérarchie d’organisation.</span><span class="sxs-lookup"><span data-stu-id="96fa9-125">This template provides one-way synchronization of the Organization Hierarchy Type table.</span></span>
<span data-ttu-id="96fa9-126">Hiérarchie d'organisation - publiée</span><span class="sxs-lookup"><span data-stu-id="96fa9-126">Organization hierarchy - published</span></span> | <span data-ttu-id="96fa9-127">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="96fa9-127">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="96fa9-128">Ce modèle fournit une synchronisation unidirectionnelle de la table Hiérarchie d’organisation publiée.</span><span class="sxs-lookup"><span data-stu-id="96fa9-128">This template provides one-way synchronization of the Organization Hierarchy Published table.</span></span>
<span data-ttu-id="96fa9-129">Unité opérationnelle</span><span class="sxs-lookup"><span data-stu-id="96fa9-129">Operating unit</span></span> | <span data-ttu-id="96fa9-130">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="96fa9-130">msdyn_internalorganizations</span></span> |
<span data-ttu-id="96fa9-131">Entités juridiques</span><span class="sxs-lookup"><span data-stu-id="96fa9-131">Legal entities</span></span> | <span data-ttu-id="96fa9-132">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="96fa9-132">msdyn_internalorganizations</span></span> |
<span data-ttu-id="96fa9-133">Entités juridiques</span><span class="sxs-lookup"><span data-stu-id="96fa9-133">Legal entities</span></span> | <span data-ttu-id="96fa9-134">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="96fa9-134">cdm_companies</span></span> | <span data-ttu-id="96fa9-135">Fournit la synchronisation bidirectionnelle d’informations sur l’entité juridique (société).</span><span class="sxs-lookup"><span data-stu-id="96fa9-135">Provides bidirectional synchronization of legal entity (company) information.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="96fa9-136">Organisation interne</span><span class="sxs-lookup"><span data-stu-id="96fa9-136">Internal Organization</span></span>

<span data-ttu-id="96fa9-137">Les informations d’organisation internes dans Dataverse proviennent de deux tables, **unité opérationnelle** et **entités juridiques**.</span><span class="sxs-lookup"><span data-stu-id="96fa9-137">Internal organization information in Dataverse comes from two tables, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]