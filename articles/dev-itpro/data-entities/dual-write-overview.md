---
title: Intégration de données en temps réel entre Finance and Operations et Common Data Service
description: Cette rubrique offre une vue d'ensemble de l'intégration entre Microsoft Dynamics 365 for Finance and Operations et Common Data Service.
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
ms.openlocfilehash: aa614c8e6a79a3f7a4f8f2f99f1f1bd1a67ac921
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797226"
---
# <a name="near-real-time-data-integration-between-finance-and-operations-and-common-data-service"></a><span data-ttu-id="ebd08-103">Intégration de données en temps réel entre Finance and Operations et Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ebd08-103">Near-real-time data integration between Finance and Operations and Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="ebd08-104">Dans le monde numérique actuel, les écosystèmes commerciaux utilisent la suite Microsoft Dynamics 365 dans son ensemble.</span><span class="sxs-lookup"><span data-stu-id="ebd08-104">In the current digital world, business ecosystems use the Microsoft Dynamics 365 suite as a whole.</span></span> <span data-ttu-id="ebd08-105">Comme les données des personnes, des clients, des opérations et de l'Internet des objets (IoT) arrivent dans une seule source, il existe une possibilité de boucles de rétroaction numérique.</span><span class="sxs-lookup"><span data-stu-id="ebd08-105">Because data from people, customers, operations, and Internet of Things (IoT) devices flows into one source, there is an opportunity for digital feedback loops.</span></span> <span data-ttu-id="ebd08-106">Pour obtenir cette expérience, l'intégration entre Dynamics 365 for Finance and Operations et les applications Dynamics 365 for Customer Engagement est vital.</span><span class="sxs-lookup"><span data-stu-id="ebd08-106">To achieve this experience, integration between Dynamics 365 for Finance and Operations and Dynamics 365 for Customer Engagement applications is essential.</span></span> <span data-ttu-id="ebd08-107">Les applications Customer Engagement reposent sur Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ebd08-107">Customer Engagement applications are built on top of Common Data Service.</span></span> <span data-ttu-id="ebd08-108">L'intégration entre les données de Finance and Operations avec Common Data Service permet aux applications Customer Engagement de communiquer avec cohérence et de manière fluide avec Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ebd08-108">Integration between Finance and Operations data with Common Data Service lets Customer Engagement applications communicate coherently and fluently with Finance and Operations.</span></span>

<span data-ttu-id="ebd08-109">Finance and Operations et Common Data Service fournissent la synchronisation des données en temps quasi-réel entre Finance and Operations et les applications Customer Engagement via une infrastructure en double écriture.</span><span class="sxs-lookup"><span data-stu-id="ebd08-109">Finance and Operations and Common Data Service provide near-real-time data synchronization between Finance and Operations and Customer Engagement applications via a dual-write framework.</span></span> <span data-ttu-id="ebd08-110">La couverture est large et couvre 28 zones de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ebd08-110">The coverage is broad and spans 28 surface areas of Finance and Operations.</span></span> <span data-ttu-id="ebd08-111">L'objectif est de fournir une expérience utilisateur « Dynamics 365 Unique » avec des flux de données transparents qui connectent les processus d'entreprise entre applications.</span><span class="sxs-lookup"><span data-stu-id="ebd08-111">The goal is to provide a "One Dynamics 365" user experience through seamless data flows that connect business processes across applications.</span></span>

![Diagramme de vue d'ensemble de l'architecture](media/dual-write-overview.jpg)

<span data-ttu-id="ebd08-113">Les propositions de valeur suivantes sont disponibles pour les clients :</span><span class="sxs-lookup"><span data-stu-id="ebd08-113">The following value propositions are available for customers:</span></span>

+ [<span data-ttu-id="ebd08-114">Hiérarchie d'organisation dans Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ebd08-114">Organization hierarchy in Common Data Service</span></span>](dual-write-organization.md)
+ [<span data-ttu-id="ebd08-115">Concept de société dans Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ebd08-115">Company concept in Common Data Service</span></span>](dual-write-company.md)
+ [<span data-ttu-id="ebd08-116">Données principales client intégrées</span><span class="sxs-lookup"><span data-stu-id="ebd08-116">Integrated customer master</span></span>](dual-write-customer.md)
+ [<span data-ttu-id="ebd08-117">Données principales fournisseur intégrées</span><span class="sxs-lookup"><span data-stu-id="ebd08-117">Integrated vendor master</span></span>](dual-write-vendor.md)
+ <span data-ttu-id="ebd08-118">Produit générique unifié</span><span class="sxs-lookup"><span data-stu-id="ebd08-118">Unified product master</span></span>

## <a name="system-requirements"></a><span data-ttu-id="ebd08-119">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="ebd08-119">System requirements</span></span>

<span data-ttu-id="ebd08-120">Les flux de données en temps quasi-réel synchrones nécessitent les versions suivantes :</span><span class="sxs-lookup"><span data-stu-id="ebd08-120">Synchronous, bidirectional, near-real-time data flows require the following versions:</span></span>

+ <span data-ttu-id="ebd08-121">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (juiellet 2019) avec Platform update 28, ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="ebd08-121">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019) with Platform update 28, or later</span></span>
+ <span data-ttu-id="ebd08-122">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="ebd08-122">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) or later</span></span>

## <a name="setup-instructions"></a><span data-ttu-id="ebd08-123">Définir des instructions</span><span class="sxs-lookup"><span data-stu-id="ebd08-123">Setup instructions</span></span>

<span data-ttu-id="ebd08-124">Procédez comme suit pour paramétrer l'intégration entre Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ebd08-124">Follow these steps to set up integration between Finance and Operations and Common Data Service.</span></span>
    
1. <span data-ttu-id="ebd08-125">Pour le paramétrage du système en double écriture, voir le [guide pas à pas](https://aka.ms/dualwrite-docs) dans l'annonce de la version préliminaire de la double écriture.</span><span class="sxs-lookup"><span data-stu-id="ebd08-125">For the setup of the dual-write system, see the [step-by-step guide](https://aka.ms/dualwrite-docs) on Announcing Dual Write Preview.</span></span>
2. <span data-ttu-id="ebd08-126">Téléchargez et installez la solution à partir de [Finance and Operations, Common Data Service et intégration Customer Engagement](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) du groupe Yammer.</span><span class="sxs-lookup"><span data-stu-id="ebd08-126">Download and install the solution from the [Finance and Operations, Common Data Service, and Customer Engagement Integration](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer group.</span></span> <span data-ttu-id="ebd08-127">Le module contient cinq solutions :</span><span class="sxs-lookup"><span data-stu-id="ebd08-127">The package contains five solutions:</span></span>

    + <span data-ttu-id="ebd08-128">Dynamics365Company</span><span class="sxs-lookup"><span data-stu-id="ebd08-128">Dynamics365Company</span></span>
    + <span data-ttu-id="ebd08-129">CurrencyExchangeRates</span><span class="sxs-lookup"><span data-stu-id="ebd08-129">CurrencyExchangeRates</span></span>
    + <span data-ttu-id="ebd08-130">Dynamics365FinanceAndOperationsCommon</span><span class="sxs-lookup"><span data-stu-id="ebd08-130">Dynamics365FinanceAndOperationsCommon</span></span>
    + <span data-ttu-id="ebd08-131">Dynamics365FinanceCommon</span><span class="sxs-lookup"><span data-stu-id="ebd08-131">Dynamics365FinanceCommon</span></span>
    + <span data-ttu-id="ebd08-132">Dynamics365SupplyChainCommon</span><span class="sxs-lookup"><span data-stu-id="ebd08-132">Dynamics365SupplyChainCommon</span></span>

3. <span data-ttu-id="ebd08-133">Suivez l'ordre d'exécution de la [synchronisation des données de référence initiales](dual-write-initial.md).</span><span class="sxs-lookup"><span data-stu-id="ebd08-133">Follow the execution order for [synchronizing initial reference data](dual-write-initial.md).</span></span>
4. <span data-ttu-id="ebd08-134">Si vous rencontrez des problèmes de synchronisation en double écriture, voir [Guide de résolution des problèmes d'intégration des données](dual-write-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="ebd08-134">If you encounter dual-write synchronization issues, see the [Troubleshooting guide for data integration](dual-write-troubleshooting.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebd08-135">Vous ne pouvez pas exécuter la double écriture et [Prospect en disponibilités](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) côte à côte.</span><span class="sxs-lookup"><span data-stu-id="ebd08-135">You can’t run dual-write and [Prospect to cash](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) side-by-side.</span></span> <span data-ttu-id="ebd08-136">Si vous exécutez la solution Prospect en disponibilités, vous devez la désinstaller.</span><span class="sxs-lookup"><span data-stu-id="ebd08-136">If you're running the Prospect to cash solution, you must uninstall it.</span></span> <span data-ttu-id="ebd08-137">Vous devez également désactiver les modèles de double écriture client et fournisseur qui font partie de la solution Prospect en disponibilités.</span><span class="sxs-lookup"><span data-stu-id="ebd08-137">You must also disable the customer and vendor dual-write templates that are part of the Prospect to cash solution.</span></span>
