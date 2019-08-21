---
title: Hiérarchie d'organisation dans Common Data Service
description: Cette rubrique décrit l'intégration des données organisationnelles entre Finance and Operations et Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: ca2ac0f9dbb8544b12f23a271423a43b0e601272
ms.sourcegitcommit: 02c223b44ac7196df675afac61c6783f467d1983
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2019
ms.locfileid: "1789188"
---
## <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="a1620-103">Hiérarchie d'organisation dans Common Data Service</span><span class="sxs-lookup"><span data-stu-id="a1620-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="a1620-104">Comme Microsoft Dynamics 365 for Finance and Operations est un système financier, l'*organisation* est un concept de base, et le système commence par la configuration d'une hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="a1620-104">Because Microsoft Dynamics 365 for Finance and Operations is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="a1620-105">Les opérations financières et commerciales peuvent ensuite être suivies au niveau de l'organisation et également à tous les niveaux de la hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="a1620-105">Business financials and operations can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="a1620-106">Bien que Common Data Service ne dispose pas du concept de hiérarchie d'organisation, il dispose de certains concepts flous, tels que le total du produit des ventes.</span><span class="sxs-lookup"><span data-stu-id="a1620-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="a1620-107">Dans le cadre de l'intégration de Common Data Service, la structure de données de la hiérarchie d'organisation est ajoutée à Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a1620-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="a1620-108">Flux de données</span><span class="sxs-lookup"><span data-stu-id="a1620-108">Data flow</span></span>

<span data-ttu-id="a1620-109">Écosystème commercial composé de Finance and Operations et Common Data Service continue d'avoir une hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="a1620-109">A business ecosystem that consists of Finance and Operations and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="a1620-110">Cette hiérarchie d'organisation repose sur Finance and Operations, mais elle est exposé dans Common Data Service à des fins d'informations et d'extensibilité.</span><span class="sxs-lookup"><span data-stu-id="a1620-110">This organization hierarchy is built on Finance and Operations, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="a1620-111">L'illustration suivante présente les informations de la hiérarchie d'organisation exposées dans Common Data Service comme un flux unidirectionnel entre Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a1620-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations to Common Data Service.</span></span>

![Image de l'architecture](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="a1620-113">Modèles</span><span class="sxs-lookup"><span data-stu-id="a1620-113">Templates</span></span>

<span data-ttu-id="a1620-114">Des mises en correspondance de l'entité Hiérarchie d'organisation sont disponibles pour la synchronisation unidirectionnelle des données entre Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a1620-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations to Common Data Service.</span></span>

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a><span data-ttu-id="a1620-115">Objectif de la hiérarchie d'organisation interne</span><span class="sxs-lookup"><span data-stu-id="a1620-115">Internal Organization Hierarchy Purpose</span></span>

<span data-ttu-id="a1620-116">Ce modèle fournit une synchronisation unidirectionnelle de l'entité Objet de la hiérarchie d'organisation entre Finance and Operations et Dynamics 365 for Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="a1620-116">This template provides one-way synchronization of the Organization Hierarchy Purpose entity from Finance and Operations to Dynamics 365 for Customer Engagement.</span></span>

<!-- ![architecture image](media/dual-write-purpose.png) -->

<span data-ttu-id="a1620-117">Champ source</span><span class="sxs-lookup"><span data-stu-id="a1620-117">Source field</span></span> | <span data-ttu-id="a1620-118">Type de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="a1620-118">Map type</span></span> | <span data-ttu-id="a1620-119">Champ de destination</span><span class="sxs-lookup"><span data-stu-id="a1620-119">Destination field</span></span>
---|---|---
<span data-ttu-id="a1620-120">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="a1620-120">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="a1620-121">msdyn\_hierarchypurposetypename</span><span class="sxs-lookup"><span data-stu-id="a1620-121">msdyn\_hierarchypurposetypename</span></span>
<span data-ttu-id="a1620-122">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="a1620-122">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="a1620-123">msdyn\_hierarchytype.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="a1620-123">msdyn\_hierarchytype.msdyn\_name</span></span>
<span data-ttu-id="a1620-124">HIERARCHYPURPOSE</span><span class="sxs-lookup"><span data-stu-id="a1620-124">HIERARCHYPURPOSE</span></span> | \>\> | <span data-ttu-id="a1620-125">msdyn\_hierarchypurpose</span><span class="sxs-lookup"><span data-stu-id="a1620-125">msdyn\_hierarchypurpose</span></span>
<span data-ttu-id="a1620-126">IMMUTABLE</span><span class="sxs-lookup"><span data-stu-id="a1620-126">IMMUTABLE</span></span> | \>\> | <span data-ttu-id="a1620-127">msdyn\_immutable</span><span class="sxs-lookup"><span data-stu-id="a1620-127">msdyn\_immutable</span></span>
<span data-ttu-id="a1620-128">SETASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="a1620-128">SETASDEFAULT</span></span> | \>\> | <span data-ttu-id="a1620-129">msdyn\_setasdefault</span><span class="sxs-lookup"><span data-stu-id="a1620-129">msdyn\_setasdefault</span></span>

## <a name="internal-organization-hierarchy-type"></a><span data-ttu-id="a1620-130">Type de hiérarchie d'organisation interne</span><span class="sxs-lookup"><span data-stu-id="a1620-130">Internal Organization Hierarchy Type</span></span>

<span data-ttu-id="a1620-131">Ce modèle fournit une synchronisation unidirectionnelle de l'entité Type de la hiérarchie d'organisation entre Finance and Operations et Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="a1620-131">Tihs template provides one-way synchronization of the Organization Hierarchy Type entity from Finance and Operations to Customer Engagement.</span></span>

<!-- ![architecture image](media/dual-write-type.png) -->

<span data-ttu-id="a1620-132">Champ source</span><span class="sxs-lookup"><span data-stu-id="a1620-132">Source field</span></span> | <span data-ttu-id="a1620-133">Type de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="a1620-133">Map type</span></span> | <span data-ttu-id="a1620-134">Champ de destination</span><span class="sxs-lookup"><span data-stu-id="a1620-134">Destination field</span></span>
---|---|---
<span data-ttu-id="a1620-135">NOM</span><span class="sxs-lookup"><span data-stu-id="a1620-135">NAME</span></span> | \> | <span data-ttu-id="a1620-136">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="a1620-136">msdyn\_name</span></span>

## <a name="internal-organization-hierarchy"></a><span data-ttu-id="a1620-137">Hiérarchie d'organisation interne</span><span class="sxs-lookup"><span data-stu-id="a1620-137">Internal Organization Hierarchy</span></span>

<span data-ttu-id="a1620-138">Ce modèle fournit une synchronisation unidirectionnelle de l'entité Hiérarchie d'organisation publiée entre Finance and Operations et Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="a1620-138">This template provides one-way synchronization of the Organization Hierarchy Published entity from Finance and Operations to Customer Engagement.</span></span>

<!-- ![architecture image](media/dual-write-organization.png) -->

<span data-ttu-id="a1620-139">Champ source</span><span class="sxs-lookup"><span data-stu-id="a1620-139">Source field</span></span> | <span data-ttu-id="a1620-140">Type de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="a1620-140">Map type</span></span> | <span data-ttu-id="a1620-141">Champ de destination</span><span class="sxs-lookup"><span data-stu-id="a1620-141">Destination field</span></span>
---|---|---
<span data-ttu-id="a1620-142">VALIDTO</span><span class="sxs-lookup"><span data-stu-id="a1620-142">VALIDTO</span></span> | \> | <span data-ttu-id="a1620-143">msdyn\_validto</span><span class="sxs-lookup"><span data-stu-id="a1620-143">msdyn\_validto</span></span>
<span data-ttu-id="a1620-144">VALIDFROM</span><span class="sxs-lookup"><span data-stu-id="a1620-144">VALIDFROM</span></span> | \> | <span data-ttu-id="a1620-145">msdyn\_validfrom</span><span class="sxs-lookup"><span data-stu-id="a1620-145">msdyn\_validfrom</span></span>
<span data-ttu-id="a1620-146">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="a1620-146">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="a1620-147">msdyn\_hierarchytypename</span><span class="sxs-lookup"><span data-stu-id="a1620-147">msdyn\_hierarchytypename</span></span>
<span data-ttu-id="a1620-148">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="a1620-148">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="a1620-149">msdyn\_parentpartyid</span><span class="sxs-lookup"><span data-stu-id="a1620-149">msdyn\_parentpartyid</span></span>
<span data-ttu-id="a1620-150">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="a1620-150">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="a1620-151">msdyn\_childpartyid</span><span class="sxs-lookup"><span data-stu-id="a1620-151">msdyn\_childpartyid</span></span>
<span data-ttu-id="a1620-152">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="a1620-152">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="a1620-153">msdyn\_hierarchytypeid.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="a1620-153">msdyn\_hierarchytypeid.msdyn\_name</span></span>
<span data-ttu-id="a1620-154">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="a1620-154">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="a1620-155">msdyn\_childid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="a1620-155">msdyn\_childid.msdyn\_partynumber</span></span>
<span data-ttu-id="a1620-156">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="a1620-156">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="a1620-157">msdyn\_parentid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="a1620-157">msdyn\_parentid.msdyn\_partynumber</span></span>

## <a name="internal-organization"></a><span data-ttu-id="a1620-158">Organisation interne</span><span class="sxs-lookup"><span data-stu-id="a1620-158">Internal Organization</span></span>

<span data-ttu-id="a1620-159">Les informations d'organisation interne dans Common Data Service proviennent de deux entités Finance and Operations, l'**unité opérationnelle** et les **entités juridiques**.</span><span class="sxs-lookup"><span data-stu-id="a1620-159">Internal organization information in Common Data Service comes from two Finance and Operations entities, **operating unit** and **legal entities**.</span></span>

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a><span data-ttu-id="a1620-160">Unité opérationnelle</span><span class="sxs-lookup"><span data-stu-id="a1620-160">Operating unit</span></span>

<span data-ttu-id="a1620-161">Champ source</span><span class="sxs-lookup"><span data-stu-id="a1620-161">Source field</span></span> | <span data-ttu-id="a1620-162">Type de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="a1620-162">Map type</span></span> | <span data-ttu-id="a1620-163">Champ de destination</span><span class="sxs-lookup"><span data-stu-id="a1620-163">Destination field</span></span>
---|---|---
<span data-ttu-id="a1620-164">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="a1620-164">LANGUAGEID</span></span> | \> | <span data-ttu-id="a1620-165">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="a1620-165">msdyn\_languageid</span></span>
<span data-ttu-id="a1620-166">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="a1620-166">NAMEALIAS</span></span> | \> | <span data-ttu-id="a1620-167">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="a1620-167">msdyn\_namealias</span></span>
<span data-ttu-id="a1620-168">NOM</span><span class="sxs-lookup"><span data-stu-id="a1620-168">NAME</span></span> | \> | <span data-ttu-id="a1620-169">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="a1620-169">msdyn\_name</span></span>
<span data-ttu-id="a1620-170">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="a1620-170">PARTYNUMBER</span></span> | \> | <span data-ttu-id="a1620-171">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="a1620-171">msdyn\_partynumber</span></span>
<span data-ttu-id="a1620-172">OPERATINGUNITTYPE</span><span class="sxs-lookup"><span data-stu-id="a1620-172">OPERATINGUNITTYPE</span></span> | \>\> | <span data-ttu-id="a1620-173">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="a1620-173">msdyn\_type</span></span>

### <a name="legal-entity"></a><span data-ttu-id="a1620-174">Entité juridique</span><span class="sxs-lookup"><span data-stu-id="a1620-174">Legal entity</span></span>

<span data-ttu-id="a1620-175">Champ source</span><span class="sxs-lookup"><span data-stu-id="a1620-175">Source field</span></span> | <span data-ttu-id="a1620-176">Type de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="a1620-176">Map type</span></span> | <span data-ttu-id="a1620-177">Champ de destination</span><span class="sxs-lookup"><span data-stu-id="a1620-177">Destination field</span></span>
---|---|---
<span data-ttu-id="a1620-178">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="a1620-178">NAMEALIAS</span></span> | \> | <span data-ttu-id="a1620-179">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="a1620-179">msdyn\_namealias</span></span>
<span data-ttu-id="a1620-180">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="a1620-180">LANGUAGEID</span></span> | \> | <span data-ttu-id="a1620-181">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="a1620-181">msdyn\_languageid</span></span>
<span data-ttu-id="a1620-182">NOM</span><span class="sxs-lookup"><span data-stu-id="a1620-182">NAME</span></span> | \> | <span data-ttu-id="a1620-183">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="a1620-183">msdyn\_name</span></span>
<span data-ttu-id="a1620-184">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="a1620-184">PARTYNUMBER</span></span> | \> | <span data-ttu-id="a1620-185">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="a1620-185">msdyn\_partynumber</span></span>
<span data-ttu-id="a1620-186">aucun</span><span class="sxs-lookup"><span data-stu-id="a1620-186">none</span></span> | \>\> | <span data-ttu-id="a1620-187">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="a1620-187">msdyn\_type</span></span>
<span data-ttu-id="a1620-188">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="a1620-188">LEGALENTITYID</span></span> | \> | <span data-ttu-id="a1620-189">msdyn\_companycode</span><span class="sxs-lookup"><span data-stu-id="a1620-189">msdyn\_companycode</span></span>

## <a name="company"></a><span data-ttu-id="a1620-190">Société</span><span class="sxs-lookup"><span data-stu-id="a1620-190">Company</span></span>

<span data-ttu-id="a1620-191">Fournit la synchronisation bidirectionnelle d'informations sur l'entité juridique (société) entre Finance and Operations et Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="a1620-191">Provides bidirectional synchronization of legal entity (company) information between Finance and Operations and Customer Engagement.</span></span>

<!-- ![architecture image](media/dual-write-company.png) -->

<span data-ttu-id="a1620-192">Champ source</span><span class="sxs-lookup"><span data-stu-id="a1620-192">Source field</span></span> | <span data-ttu-id="a1620-193">Type de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="a1620-193">Map type</span></span> | <span data-ttu-id="a1620-194">Champ de destination</span><span class="sxs-lookup"><span data-stu-id="a1620-194">Destination field</span></span>
---|---|---
<span data-ttu-id="a1620-195">NOM</span><span class="sxs-lookup"><span data-stu-id="a1620-195">NAME</span></span> | = | <span data-ttu-id="a1620-196">cdm\_name</span><span class="sxs-lookup"><span data-stu-id="a1620-196">cdm\_name</span></span>
<span data-ttu-id="a1620-197">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="a1620-197">LEGALENTITYID</span></span> | = | <span data-ttu-id="a1620-198">cdm\_companycode</span><span class="sxs-lookup"><span data-stu-id="a1620-198">cdm\_companycode</span></span>
