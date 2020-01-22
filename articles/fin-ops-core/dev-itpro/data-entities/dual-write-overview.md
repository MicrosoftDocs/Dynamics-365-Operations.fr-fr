---
title: Intégration des données en quasi temps réel avec Common Data Service
description: Cette rubrique offre une vue d'ensemble de l'intégration des données de produit entre Finance and Operations et Common Data Service.
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
ms.openlocfilehash: 072564446b74318ffc8e8e6ad4fd16f4421e7854
ms.sourcegitcommit: d0322d1ed6c798301058e44dae76227a0e1f49ac
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2019
ms.locfileid: "2853904"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a><span data-ttu-id="11df2-103">Intégration des données en quasi temps réel avec Common Data Service</span><span class="sxs-lookup"><span data-stu-id="11df2-103">Near-real-time data integration with Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="11df2-104">Dans le monde numérique actuel, les écosystèmes commerciaux utilisent les applications Microsoft Dynamics 365 dans son ensemble.</span><span class="sxs-lookup"><span data-stu-id="11df2-104">In the current digital world, business ecosystems use Microsoft Dynamics 365 applications as a whole.</span></span> <span data-ttu-id="11df2-105">Comme les données des personnes, des clients, des opérations et de l'Internet des objets (IoT) arrivent dans une seule source, il existe une possibilité de boucles de rétroaction numérique.</span><span class="sxs-lookup"><span data-stu-id="11df2-105">Because data from people, customers, operations, and Internet of Things (IoT) devices flows into one source, there is an opportunity for digital feedback loops.</span></span> <span data-ttu-id="11df2-106">Pour obtenir cette expérience, l'intégration entre les applications Finance and Operations et d'autres applications Dynamics 365 est vital.</span><span class="sxs-lookup"><span data-stu-id="11df2-106">To achieve this experience, integration between Finance and Operations apps and other Dynamics 365 applications is essential.</span></span> <span data-ttu-id="11df2-107">Certaines applications reposent sur Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="11df2-107">Some applications are built on top of Common Data Service.</span></span> <span data-ttu-id="11df2-108">L'intégration entre les données des applications Finance and Operations avec Common Data Service permet aux autres applications de communiquer avec cohérence et de manière fluide avec Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="11df2-108">Integration between Finance and Operations apps data with Common Data Service lets other applications communicate coherently and fluently with Finance and Operations.</span></span>

<span data-ttu-id="11df2-109">Les applications Finance and Operations et Common Data Service fournissent la synchronisation des données en temps quasi-réel entre les applications Finance and Operations et d'autres applications Dynamics 365 via une infrastructure en double écriture.</span><span class="sxs-lookup"><span data-stu-id="11df2-109">Finance and Operations apps and Common Data Service provide near-real-time data synchronization between Finance and Operations apps and other Dynamics 365 applications via a dual-write framework.</span></span> <span data-ttu-id="11df2-110">La couverture est large et couvre 28 zones de l'application.</span><span class="sxs-lookup"><span data-stu-id="11df2-110">The coverage is broad and spans 28 surface areas of the application.</span></span> <span data-ttu-id="11df2-111">L'objectif est de fournir une expérience utilisateur « Dynamics 365 Unique » avec des flux de données transparents qui connectent les processus d'entreprise entre applications.</span><span class="sxs-lookup"><span data-stu-id="11df2-111">The goal is to provide a "One Dynamics 365" user experience through seamless data flows that connect business processes across applications.</span></span>

![Diagramme de vue d'ensemble de l'architecture](media/dual-write-overview.jpg)

<span data-ttu-id="11df2-113">Les propositions de valeur suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="11df2-113">The following value propositions are available:</span></span>

+ [<span data-ttu-id="11df2-114">Hiérarchie d'organisation dans Common Data Service</span><span class="sxs-lookup"><span data-stu-id="11df2-114">Organization hierarchy in Common Data Service</span></span>](dual-write-organization.md)
+ [<span data-ttu-id="11df2-115">Concept de société dans Common Data Service</span><span class="sxs-lookup"><span data-stu-id="11df2-115">Company concept in Common Data Service</span></span>](dual-write-company.md)
+ [<span data-ttu-id="11df2-116">Données principales client intégrées</span><span class="sxs-lookup"><span data-stu-id="11df2-116">Integrated customer master</span></span>](dual-write-customer.md)
+ [<span data-ttu-id="11df2-117">Comptabilité intégrée</span><span class="sxs-lookup"><span data-stu-id="11df2-117">Integrated ledger</span></span>](dual-write-ledger.md)
+ [<span data-ttu-id="11df2-118">Expérience produit uniformisée</span><span class="sxs-lookup"><span data-stu-id="11df2-118">Unified product experience</span></span>](dual-write-product.md)
+ [<span data-ttu-id="11df2-119">Données principales fournisseur intégrées</span><span class="sxs-lookup"><span data-stu-id="11df2-119">Integrated vendor master</span></span>](dual-write-vendor.md)
+ [<span data-ttu-id="11df2-120">Sites et entrepôts intégrés</span><span class="sxs-lookup"><span data-stu-id="11df2-120">Integrated sites and warehouses</span></span>](dual-write-sites-and-warehouses.md)
+ [<span data-ttu-id="11df2-121">Données principales relatives aux taxes intégrées</span><span class="sxs-lookup"><span data-stu-id="11df2-121">Integrated tax master</span></span>](dual-write-tax.md)

## <a name="system-requirements"></a><span data-ttu-id="11df2-122">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="11df2-122">System requirements</span></span>

<span data-ttu-id="11df2-123">Les flux de données en temps quasi-réel synchrones nécessitent les versions suivantes :</span><span class="sxs-lookup"><span data-stu-id="11df2-123">Synchronous, bidirectional, near-real-time data flows require the following versions:</span></span>

+ <span data-ttu-id="11df2-124">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (juiellet 2019) avec Platform update 28, ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="11df2-124">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019) with Platform update 28, or later</span></span>
+ <span data-ttu-id="11df2-125">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="11df2-125">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) or later</span></span>

## <a name="setup-instructions"></a><span data-ttu-id="11df2-126">Définir des instructions</span><span class="sxs-lookup"><span data-stu-id="11df2-126">Setup instructions</span></span>

<span data-ttu-id="11df2-127">Procédez comme suit pour paramétrer l'intégration entre les applications Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="11df2-127">Follow these steps to set up integration between Finance and Operations apps and Common Data Service.</span></span>
    
1. <span data-ttu-id="11df2-128">Pour le paramétrage du système en double écriture, voir le [guide pas à pas](https://aka.ms/dualwrite-docs) dans l'annonce de la version préliminaire de la double écriture.</span><span class="sxs-lookup"><span data-stu-id="11df2-128">For the setup of the dual-write system, see the [step-by-step guide](https://aka.ms/dualwrite-docs) on Announcing Dual Write Preview.</span></span>
2. <span data-ttu-id="11df2-129">Téléchargez et installez la solution à partir du groupe Yammer [Fin Ops et de l'intégration de CDS/CE en double-écriture](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096).</span><span class="sxs-lookup"><span data-stu-id="11df2-129">Download and install the solution from the [Fin Ops and CDS/CE Integration via Dual-Write](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer group.</span></span> <span data-ttu-id="11df2-130">Le module contient cinq solutions :</span><span class="sxs-lookup"><span data-stu-id="11df2-130">The package contains five solutions:</span></span>

    + <span data-ttu-id="11df2-131">Dynamics365Company</span><span class="sxs-lookup"><span data-stu-id="11df2-131">Dynamics365Company</span></span>
    + <span data-ttu-id="11df2-132">CurrencyExchangeRates</span><span class="sxs-lookup"><span data-stu-id="11df2-132">CurrencyExchangeRates</span></span>
    + <span data-ttu-id="11df2-133">Dynamics365FinanceAndOperationsCommon</span><span class="sxs-lookup"><span data-stu-id="11df2-133">Dynamics365FinanceAndOperationsCommon</span></span>
    + <span data-ttu-id="11df2-134">Dynamics365FinanceCommon</span><span class="sxs-lookup"><span data-stu-id="11df2-134">Dynamics365FinanceCommon</span></span>
    + <span data-ttu-id="11df2-135">Dynamics365SupplyChainCommon</span><span class="sxs-lookup"><span data-stu-id="11df2-135">Dynamics365SupplyChainCommon</span></span>

3. <span data-ttu-id="11df2-136">Suivez l'ordre d'exécution de la [synchronisation des données de référence initiales](dual-write-initial.md).</span><span class="sxs-lookup"><span data-stu-id="11df2-136">Follow the execution order for [synchronizing initial reference data](dual-write-initial.md).</span></span>
4. <span data-ttu-id="11df2-137">Si vous rencontrez des problèmes de synchronisation en double écriture, voir [Guide de résolution des problèmes d'intégration des données](dual-write-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="11df2-137">If you encounter dual-write synchronization issues, see the [Troubleshooting guide for data integration](dual-write-troubleshooting.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="11df2-138">Vous ne pouvez pas exécuter la double écriture et [Prospect en disponibilités](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) côte à côte.</span><span class="sxs-lookup"><span data-stu-id="11df2-138">You can’t run dual-write and [Prospect to cash](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) side-by-side.</span></span> <span data-ttu-id="11df2-139">Si vous exécutez la solution Prospect en disponibilités, vous devez la désinstaller.</span><span class="sxs-lookup"><span data-stu-id="11df2-139">If you're running the Prospect to cash solution, you must uninstall it.</span></span> <span data-ttu-id="11df2-140">Vous devez également désactiver les modèles de double écriture client et fournisseur qui font partie de la solution Prospect en disponibilités.</span><span class="sxs-lookup"><span data-stu-id="11df2-140">You must also disable the customer and vendor dual-write templates that are part of the Prospect to cash solution.</span></span>
