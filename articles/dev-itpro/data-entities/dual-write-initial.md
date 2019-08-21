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
ms.openlocfilehash: b74bc2d3133af7e87663a4e6bafb8780e0a6a66f
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797296"
---
# <a name="execution-order-for-initial-sychronization-of-finance-and-operations-and-common-data-service"></a><span data-ttu-id="c9e93-103">Ordre d'exécution de la synchronisation initiale de Finance and Operations et Common Data Service</span><span class="sxs-lookup"><span data-stu-id="c9e93-103">Execution order for initial sychronization of Finance and Operations and Common Data Service</span></span>

<span data-ttu-id="c9e93-104">Avant d'utiliser l'intégration des données, vous devez créer les données initiales requises pour les clients, les fournisseurs et les contacts.</span><span class="sxs-lookup"><span data-stu-id="c9e93-104">Before you use data integration, you must create the initial data required for customers, vendors and contacts.</span></span> <span data-ttu-id="c9e93-105">Par exemple, si vous souhaitez créer un élément **Groupe de fournisseurs** et définir ses **Conditions de paiement** comme **Net30**, avant de tenter de créer l'élément **Groupe de fournisseurs**, vous devez vous assurer que **Net30** existe dans Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c9e93-105">For example, if you want to create a new **Vendor group** item and set its **Terms of Payment** as **Net30**, then before you attempt to create the **Vendor group** item you need to make sure that **Net30** exists in both Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="c9e93-106">(À l'avenir, nous lancerons une fonctionnalité de plateforme en double écriture appelée **Synchronisation initiale**. Elle effectuera une synchronisation unique des données entre Finance and Operations et Common Data Service dans le cadre du paramétrage de la double écriture.)</span><span class="sxs-lookup"><span data-stu-id="c9e93-106">(In the future, we will release a  dual-write platform functionality called **Initial Sync**. It will do a one-time data synchronization between Finance and Operations and Common Data Service as part of the dual-write setup.)</span></span>

<span data-ttu-id="c9e93-107">Conseils : Nous lançons une mise en correspondance de la double écriture pour toutes les données de référence notamment les **Conditions de paiement**.</span><span class="sxs-lookup"><span data-stu-id="c9e93-107">Tips: We are releasing a dual-write map for all reference data including **Terms of Payment** (Payment Terms).</span></span> <span data-ttu-id="c9e93-108">Si vous avez déjà les données initiales dans un système, une petite opération de mise à jour sur un enregistrement peut déclencher la double écriture partir de cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="c9e93-108">If you already have the initial data in one system, a small update operation on a record can trigger dual-write on that record.</span></span> 

<span data-ttu-id="c9e93-109">Vous devez suivre l'ordre de priorité suivant et vous assurer que les données initiales sont disponibles sur Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c9e93-109">You must follow the following order of precedence and make sure that the initial data is available on both Finance and Operations and Common Data Service.</span></span>   

## <a name="vendor"></a><span data-ttu-id="c9e93-110">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="c9e93-110">Vendor</span></span>

<span data-ttu-id="c9e93-111">L'ordre d'exécution pour le fournisseur est :</span><span class="sxs-lookup"><span data-stu-id="c9e93-111">The order of execution for Vendor is:</span></span>

```
Vendor Group
    Terms of payment
        Payment day & lines
        Payment schedule
Vendor payment method
```

## <a name="customer-organization"></a><span data-ttu-id="c9e93-112">Client (Organisation)</span><span class="sxs-lookup"><span data-stu-id="c9e93-112">Customer (Organization)</span></span>

<span data-ttu-id="c9e93-113">L'ordre d'exécution pour le client est :</span><span class="sxs-lookup"><span data-stu-id="c9e93-113">The order of execution for Customer is:</span></span>

```
Customer Group
    Terms of payment
        Payment day & lines
        Payment 
Customer payment method
```

## <a name="contact-person"></a><span data-ttu-id="c9e93-114">Contact (Personne)</span><span class="sxs-lookup"><span data-stu-id="c9e93-114">Contact (Person)</span></span>

<span data-ttu-id="c9e93-115">L'ordre d'exécution pour le contact est :</span><span class="sxs-lookup"><span data-stu-id="c9e93-115">The order of execution for Contact is:</span></span>

```
Customer
Vendor               
```
