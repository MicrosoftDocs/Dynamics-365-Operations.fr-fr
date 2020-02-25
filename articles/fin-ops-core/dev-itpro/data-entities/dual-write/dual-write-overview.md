---
title: Intégration des données en quasi temps réel avec Common Data Service
description: Cette rubrique offre une vue d'ensemble de l'intégration entre Finance and Operations et Common Data Service.
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
ms.openlocfilehash: 1c09b0c0bb695e7695acb7a8821ffb99ae1f6f06
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019782"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a><span data-ttu-id="5ae7f-103">Intégration des données en quasi temps réel avec Common Data Service</span><span class="sxs-lookup"><span data-stu-id="5ae7f-103">Near-real-time data integration with Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="5ae7f-104">Dans le monde numérique actuel, les écosystèmes commerciaux utilisent les applications Microsoft Dynamics 365 dans son ensemble.</span><span class="sxs-lookup"><span data-stu-id="5ae7f-104">In the current digital world, business ecosystems use Microsoft Dynamics 365 applications as a whole.</span></span> <span data-ttu-id="5ae7f-105">Comme les données des personnes, des clients, des opérations et de l'Internet des objets (IoT) arrivent dans une seule source, il existe une possibilité de boucles de rétroaction numérique.</span><span class="sxs-lookup"><span data-stu-id="5ae7f-105">Because data from people, customers, operations, and Internet of Things (IoT) devices flows into one source, there is an opportunity for digital feedback loops.</span></span> <span data-ttu-id="5ae7f-106">Pour obtenir cette expérience, l'intégration entre les applications Finance and Operations et d'autres applications Dynamics 365 est vitale.</span><span class="sxs-lookup"><span data-stu-id="5ae7f-106">To achieve this experience, integration between Finance and Operations apps and other Dynamics 365 applications is essential.</span></span> <span data-ttu-id="5ae7f-107">Certaines applications reposent sur Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5ae7f-107">Some applications are built on top of Common Data Service.</span></span> <span data-ttu-id="5ae7f-108">L'intégration entre les données d'applications Finance and Operations avec Common Data Service permet à d'autres applications de communiquer de manière cohérente et fluide avec Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5ae7f-108">Integration between Finance and Operations apps data with Common Data Service lets other applications communicate coherently and fluently with Finance and Operations.</span></span>

<span data-ttu-id="5ae7f-109">Les applications Finance and Operations et Common Data Service fournissent la synchronisation des données en temps quasi-réel entre les applications Finance and Operations et d'autres applications Dynamics 365 via une infrastructure en double écriture.</span><span class="sxs-lookup"><span data-stu-id="5ae7f-109">Finance and Operations apps and Common Data Service provide near-real-time data synchronization between Finance and Operations apps and other Dynamics 365 applications via a dual-write framework.</span></span> <span data-ttu-id="5ae7f-110">La couverture est large et couvre 28 zones de l'application.</span><span class="sxs-lookup"><span data-stu-id="5ae7f-110">The coverage is broad and spans 28 surface areas of the application.</span></span> <span data-ttu-id="5ae7f-111">L'objectif est de fournir une expérience utilisateur « Dynamics 365 Unique » avec des flux de données transparents qui connectent les processus d'entreprise entre applications.</span><span class="sxs-lookup"><span data-stu-id="5ae7f-111">The goal is to provide a "One Dynamics 365" user experience through seamless data flows that connect business processes across applications.</span></span>

![Diagramme de vue d'ensemble de l'architecture](media/dual-write-overview.jpg)

<span data-ttu-id="5ae7f-113">Les propositions de valeur suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="5ae7f-113">The following value propositions are available:</span></span>

+ [<span data-ttu-id="5ae7f-114">Hiérarchie d'organisation dans Common Data Service</span><span class="sxs-lookup"><span data-stu-id="5ae7f-114">Organization hierarchy in Common Data Service</span></span>](organization-mapping.md)
+ [<span data-ttu-id="5ae7f-115">Concept de société dans Common Data Service</span><span class="sxs-lookup"><span data-stu-id="5ae7f-115">Company concept in Common Data Service</span></span>](company-data.md)
+ [<span data-ttu-id="5ae7f-116">Données principales client intégrées</span><span class="sxs-lookup"><span data-stu-id="5ae7f-116">Integrated customer master</span></span>](customer-mapping.md)
+ [<span data-ttu-id="5ae7f-117">Comptabilité intégrée</span><span class="sxs-lookup"><span data-stu-id="5ae7f-117">Integrated ledger</span></span>](ledger-mapping.md)
+ [<span data-ttu-id="5ae7f-118">Expérience produit uniformisée</span><span class="sxs-lookup"><span data-stu-id="5ae7f-118">Unified product experience</span></span>](product-mapping.md)
+ [<span data-ttu-id="5ae7f-119">Données principales fournisseur intégrées</span><span class="sxs-lookup"><span data-stu-id="5ae7f-119">Integrated vendor master</span></span>](vendor-mapping.md)
+ [<span data-ttu-id="5ae7f-120">Sites et entrepôts intégrés</span><span class="sxs-lookup"><span data-stu-id="5ae7f-120">Integrated sites and warehouses</span></span>](sites-warehouses-mapping.md)
+ [<span data-ttu-id="5ae7f-121">Données principales relatives aux taxes intégrées</span><span class="sxs-lookup"><span data-stu-id="5ae7f-121">Integrated tax master</span></span>](tax-mapping.md)

## <a name="system-requirements"></a><span data-ttu-id="5ae7f-122">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="5ae7f-122">System requirements</span></span>

<span data-ttu-id="5ae7f-123">Les flux de données en temps quasi-réel synchrones nécessitent les versions suivantes :</span><span class="sxs-lookup"><span data-stu-id="5ae7f-123">Synchronous, bidirectional, near-real-time data flows require the following versions:</span></span>

+ <span data-ttu-id="5ae7f-124">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (juiellet 2019) avec Platform update 28, ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="5ae7f-124">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019) with Platform update 28, or later</span></span>
+ <span data-ttu-id="5ae7f-125">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="5ae7f-125">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) or later</span></span>

## <a name="setup-instructions"></a><span data-ttu-id="5ae7f-126">Définir des instructions</span><span class="sxs-lookup"><span data-stu-id="5ae7f-126">Setup instructions</span></span>

<span data-ttu-id="5ae7f-127">Pour définir l'intégration entre les applications Finance and Operations et Common Data Service, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5ae7f-127">Follow these steps to set up integration between Finance and Operations apps and Common Data Service.</span></span>
    
1. <span data-ttu-id="5ae7f-128">Pour le paramétrage du système en double écriture, voir le [guide pas à pas](https://aka.ms/dualwrite-docs) dans l'annonce de la version préliminaire de la double écriture.</span><span class="sxs-lookup"><span data-stu-id="5ae7f-128">For the setup of the dual-write system, see the [step-by-step guide](https://aka.ms/dualwrite-docs) on Announcing Dual Write Preview.</span></span>
2. <span data-ttu-id="5ae7f-129">Téléchargez et installez la solution à partir du groupe Yammer [Fin Ops et de l'intégration de CDS/CE en double-écriture](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096).</span><span class="sxs-lookup"><span data-stu-id="5ae7f-129">Download and install the solution from the [Fin Ops and CDS/CE Integration via Dual-Write](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer group.</span></span> <span data-ttu-id="5ae7f-130">Le module contient cinq solutions :</span><span class="sxs-lookup"><span data-stu-id="5ae7f-130">The package contains five solutions:</span></span>

    + <span data-ttu-id="5ae7f-131">Dynamics365Company</span><span class="sxs-lookup"><span data-stu-id="5ae7f-131">Dynamics365Company</span></span>
    + <span data-ttu-id="5ae7f-132">CurrencyExchangeRates</span><span class="sxs-lookup"><span data-stu-id="5ae7f-132">CurrencyExchangeRates</span></span>
    + <span data-ttu-id="5ae7f-133">Dynamics365FinanceAndOperationsCommon</span><span class="sxs-lookup"><span data-stu-id="5ae7f-133">Dynamics365FinanceAndOperationsCommon</span></span>
    + <span data-ttu-id="5ae7f-134">Dynamics365FinanceCommon</span><span class="sxs-lookup"><span data-stu-id="5ae7f-134">Dynamics365FinanceCommon</span></span>
    + <span data-ttu-id="5ae7f-135">Dynamics365SupplyChainCommon</span><span class="sxs-lookup"><span data-stu-id="5ae7f-135">Dynamics365SupplyChainCommon</span></span>

3. <span data-ttu-id="5ae7f-136">Suivez l'ordre d'exécution de la [synchronisation des données de référence initiales](initial-sync.md).</span><span class="sxs-lookup"><span data-stu-id="5ae7f-136">Follow the execution order for [synchronizing initial reference data](initial-sync.md).</span></span>
4. <span data-ttu-id="5ae7f-137">Si vous rencontrez des problèmes de synchronisation en double écriture, voir [Guide de résolution des problèmes d'intégration des données](dual-write-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="5ae7f-137">If you encounter dual-write synchronization issues, see the [Troubleshooting guide for data integration](dual-write-troubleshooting.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ae7f-138">Vous ne pouvez pas exécuter la double écriture et [Prospect en disponibilités](../../../../supply-chain/sales-marketing/prospect-to-cash.md) côte à côte.</span><span class="sxs-lookup"><span data-stu-id="5ae7f-138">You can’t run dual-write and [Prospect to cash](../../../../supply-chain/sales-marketing/prospect-to-cash.md) side-by-side.</span></span> <span data-ttu-id="5ae7f-139">Si vous exécutez la solution Prospect en disponibilités, vous devez la désinstaller.</span><span class="sxs-lookup"><span data-stu-id="5ae7f-139">If you're running the Prospect to cash solution, you must uninstall it.</span></span> <span data-ttu-id="5ae7f-140">Vous devez également désactiver les modèles de double écriture client et fournisseur qui font partie de la solution Prospect en disponibilités.</span><span class="sxs-lookup"><span data-stu-id="5ae7f-140">You must also disable the customer and vendor dual-write templates that are part of the Prospect to cash solution.</span></span>
