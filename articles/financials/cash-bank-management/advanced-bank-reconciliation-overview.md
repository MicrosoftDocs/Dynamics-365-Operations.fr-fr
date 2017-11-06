---
title: "Vue d'ensemble du rapprochement bancaire avancé"
description: "Cet article décrit le flux du processus de rapprochement bancaire avancé. La fonctionnalité avancée de rapprochement bancaire permet d'importer des relevés bancaires qui peuvent être automatiquement rapprochés dans les transactions bancaires."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e069bf65e7dcab7f3b049aa786f3daff07383f4c
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="advanced-bank-reconciliation-overview"></a><span data-ttu-id="070d3-104">Vue d'ensemble du rapprochement bancaire avancé</span><span class="sxs-lookup"><span data-stu-id="070d3-104">Advanced bank reconciliation overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="070d3-105">Cet article décrit le flux du processus de rapprochement bancaire avancé.</span><span class="sxs-lookup"><span data-stu-id="070d3-105">This article describes the flow for the advanced bank reconciliation process.</span></span> <span data-ttu-id="070d3-106">La fonctionnalité avancée de rapprochement bancaire permet d'importer des relevés bancaires qui peuvent être automatiquement rapprochés dans les transactions bancaires.</span><span class="sxs-lookup"><span data-stu-id="070d3-106">The advanced bank reconciliation feature lets you import bank statements that can be automatically reconciled from within bank transactions.</span></span>

<span data-ttu-id="070d3-107">La fonctionnalité de rapprochement bancaire avancé vous permet d'importer des relevés bancaires.</span><span class="sxs-lookup"><span data-stu-id="070d3-107">The advanced bank reconciliation feature lets you import bank statements.</span></span> <span data-ttu-id="070d3-108">Le relevé bancaire importé peut ensuite être automatiquement rapproché depuis les transactions bancaires.</span><span class="sxs-lookup"><span data-stu-id="070d3-108">The imported bank statement can then be automatically reconciled from within bank transactions.</span></span> <span data-ttu-id="070d3-109">Voici les étapes du flux de rapprochement bancaire avancé.</span><span class="sxs-lookup"><span data-stu-id="070d3-109">Here are the steps in the advanced bank reconciliation flow.</span></span>

1.  <span data-ttu-id="070d3-110">Configurer une importation de relevé bancaire.</span><span class="sxs-lookup"><span data-stu-id="070d3-110">Set up a bank statement import.</span></span>
    -   <span data-ttu-id="070d3-111">Importer les relevés bancaires via l'infrastructure d'entité de données.</span><span class="sxs-lookup"><span data-stu-id="070d3-111">Import bank statements through the data entity framework.</span></span>
    -   <span data-ttu-id="070d3-112">Trois formats de relevé bancaire standard sont incorporés : ISO20022, BAI2 et MT940.</span><span class="sxs-lookup"><span data-stu-id="070d3-112">Three typical bank statement formats are built in: ISO20022, BAI2, and MT940.</span></span>
    -   <span data-ttu-id="070d3-113">La fonctionnalité peut être étendue à n'importe quel format.</span><span class="sxs-lookup"><span data-stu-id="070d3-113">The functionality can be extended to any format.</span></span>

2.  <span data-ttu-id="070d3-114">Paramétrer une souche de numéros à utiliser pour le rapprochement bancaire avancé, puis définissez les règles de correspondance du rapprochement bancaire.</span><span class="sxs-lookup"><span data-stu-id="070d3-114">Set up a number sequence to use for advanced bank reconciliation, and define the bank reconciliation matching rules.</span></span>
    -   <span data-ttu-id="070d3-115">Une règle de correspondance de rapprochement est un ensemble de critères utilisés pour filtrer les lignes de relevé bancaire et les lignes de transactions bancaires Microsoft Dynamics 365 for Finance and Operations, Enterprise edition lors du processus de rapprochement.</span><span class="sxs-lookup"><span data-stu-id="070d3-115">A reconciliation matching rule is a set of criteria that are used to filter bank statement lines and Microsoft Dynamics 365 for Finance and Operations, Enterprise edition bank transaction lines during the reconciliation process.</span></span> <span data-ttu-id="070d3-116">En fonction des procédures de votre entreprise, vous pouvez paramétrer plusieurs règles de correspondance pour automatiser et optimiser votre processus de rapprochement.</span><span class="sxs-lookup"><span data-stu-id="070d3-116">Depending on your business practice, you can set up more than one matching rule to automate and optimize your reconciliation process.</span></span>

3.  <span data-ttu-id="070d3-117">Rapprocher les relevés bancaires avec des transactions bancaires Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="070d3-117">Reconcile bank statements with Finance and Operations bank transactions.</span></span>
    -   <span data-ttu-id="070d3-118">Exécuter la correspondance et la création des journaux de rapprochement automatiques.</span><span class="sxs-lookup"><span data-stu-id="070d3-118">Perform automatic matching and creation of reconciliation journals.</span></span>
    -   <span data-ttu-id="070d3-119">Afficher les relevés bancaires et les transactions bancaires Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="070d3-119">View bank statements and Finance and Operations bank transactions side by side.</span></span>
    -   <span data-ttu-id="070d3-120">Valider automatiquement des transactions bancaires Finance and Operations si elles figurent sur un relevé bancaire mais n'apparaissent pas dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="070d3-120">Automatically post Finance and Operations bank transactions if they appear on a bank statement but don't appear in Finance and Operations.</span></span>
    -   <span data-ttu-id="070d3-121">Générer un relevé de rapprochement.</span><span class="sxs-lookup"><span data-stu-id="070d3-121">Generate a reconciliation statement.</span></span>






