---
title: Ordre d'exécution de la synchronisation initiale de Finance and Operations et Common Data Service
description: Cette rubrique spécifie l'ordre de synchronisation à suivre pour créer les données initiales.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
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
ms.openlocfilehash: 1473c3bad55734d5f83ee3e4c1654921b872f3bb
ms.sourcegitcommit: 3f05ede8b8acdf0550240a83a013e093b4ad043d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2019
ms.locfileid: "1873126"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-and-common-data-service"></a><span data-ttu-id="24a4d-103">Ordre d'exécution de la synchronisation initiale de Finance and Operations et Common Data Service</span><span class="sxs-lookup"><span data-stu-id="24a4d-103">Execution order for initial synchronization of Finance and Operations and Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="24a4d-104">Avant d'utiliser l'intégration des données, vous devez créer les données initiales requises pour les clients, les fournisseurs et les contacts.</span><span class="sxs-lookup"><span data-stu-id="24a4d-104">Before you use data integration, you must create the initial data that is required for customers, vendors, and contacts.</span></span> <span data-ttu-id="24a4d-105">Par exemple, vous souhaitez créer un nouvel élément **Groupe de fournisseurs** et définir la valeur de ses **Conditions de paiement** sur **Net30**.</span><span class="sxs-lookup"><span data-stu-id="24a4d-105">For example, you want to create a new **Vendor group** item and set its **Terms of Payment** value to **Net30**.</span></span> <span data-ttu-id="24a4d-106">Dans ce cas, avant d'essayer de créer l'élément **Groupe de fournisseurs**, vous devez vous assurer que **Net30** existe bien dans Microsoft Dynamics 365 for Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="24a4d-106">In this case, before you try to create the **Vendor group** item, you must make sure that **Net30** exists in both Microsoft Dynamics 365 for Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="24a4d-107">(À l'avenir, Microsoft lancera une fonctionnalité de plateforme en double écriture appelée Synchronisation initiale. Elle effectuera une synchronisation unique des données entre Finance and Operations et Common Data Service dans le cadre du paramétrage de la double écriture.)</span><span class="sxs-lookup"><span data-stu-id="24a4d-107">(In the future, Microsoft will release dual-write platform functionality that is named Initial Sync. This functionality will do a one-time data synchronization between Finance and Operations and Common Data Service as part of the dual-write setup.)</span></span>

> [!TIP]
> <span data-ttu-id="24a4d-108">Microsoft lance une mise en correspondance de la double écriture pour toutes les données de référence notamment les **Conditions de paiement**.</span><span class="sxs-lookup"><span data-stu-id="24a4d-108">Microsoft is releasing a dual-write map for all reference data, including **Terms of Payment** (payment terms).</span></span> <span data-ttu-id="24a4d-109">Si vous avez déjà les données initiales dans un système, une petite opération de mise à jour sur un enregistrement peut déclencher la double écriture partir de cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="24a4d-109">If you already have the initial data in one system, a small update operation on a record can trigger dual-write on that record.</span></span>

<span data-ttu-id="24a4d-110">Vous devez suivre l'ordre de priorité suivant et vous assurer que les données initiales sont disponibles sur Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="24a4d-110">You must follow the following order of precedence and make sure that the initial data is available in both Finance and Operations and Common Data Service.</span></span>

## <a name="vendor"></a><span data-ttu-id="24a4d-111">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="24a4d-111">Vendor</span></span>

<span data-ttu-id="24a4d-112">Voici l'ordre d'exécution de l'entité **Fournisseur** :</span><span class="sxs-lookup"><span data-stu-id="24a4d-112">Here is the order of execution for the **Vendor** entity:</span></span>

1. <span data-ttu-id="24a4d-113">Groupe de fournisseurs</span><span class="sxs-lookup"><span data-stu-id="24a4d-113">Vendor group</span></span>

    1. <span data-ttu-id="24a4d-114">Conditions de paiement</span><span class="sxs-lookup"><span data-stu-id="24a4d-114">Terms of payment</span></span>

        1. <span data-ttu-id="24a4d-115">Lignes de jour de paiement</span><span class="sxs-lookup"><span data-stu-id="24a4d-115">Payment day and lines</span></span>
        2. <span data-ttu-id="24a4d-116">Echéancier de paiement</span><span class="sxs-lookup"><span data-stu-id="24a4d-116">Payment schedule</span></span>

2. <span data-ttu-id="24a4d-117">Mode de paiement fournisseur</span><span class="sxs-lookup"><span data-stu-id="24a4d-117">Vendor payment method</span></span>

## <a name="customer-organization"></a><span data-ttu-id="24a4d-118">Client (Organisation)</span><span class="sxs-lookup"><span data-stu-id="24a4d-118">Customer (Organization)</span></span>

<span data-ttu-id="24a4d-119">Voici l'ordre d'exécution de l'entité **Client** :</span><span class="sxs-lookup"><span data-stu-id="24a4d-119">Here is the order of execution for the **Customer** entity:</span></span>

1. <span data-ttu-id="24a4d-120">Groupe de clients</span><span class="sxs-lookup"><span data-stu-id="24a4d-120">Customer group</span></span>

    1. <span data-ttu-id="24a4d-121">Conditions de paiement</span><span class="sxs-lookup"><span data-stu-id="24a4d-121">Terms of payment</span></span>

        1. <span data-ttu-id="24a4d-122">Lignes de jour de paiement</span><span class="sxs-lookup"><span data-stu-id="24a4d-122">Payment day and lines</span></span>
        2. <span data-ttu-id="24a4d-123">Paiement</span><span class="sxs-lookup"><span data-stu-id="24a4d-123">Payment</span></span> 

2. <span data-ttu-id="24a4d-124">Modes de paiement des clients</span><span class="sxs-lookup"><span data-stu-id="24a4d-124">Customer payment method</span></span>

## <a name="contact-person"></a><span data-ttu-id="24a4d-125">Contact (Personne)</span><span class="sxs-lookup"><span data-stu-id="24a4d-125">Contact (Person)</span></span>

<span data-ttu-id="24a4d-126">Voici l'ordre d'exécution de l'entité **Contact** :</span><span class="sxs-lookup"><span data-stu-id="24a4d-126">Here is the order of execution for the **Contact** entity:</span></span>

1. <span data-ttu-id="24a4d-127">Client </span><span class="sxs-lookup"><span data-stu-id="24a4d-127">Customer</span></span>
2. <span data-ttu-id="24a4d-128">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="24a4d-128">Vendor</span></span>
