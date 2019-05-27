---
title: Journaux équilibrés pour la comptabilité interunités
description: Cet article décrit la manière dont un journal est automatiquement équilibré lorsqu'une dimension financière d'équilibrage est activée dans la page de comptabilité.
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b596a2332a9ada01df7b4e718a79eb624ee52fc
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549102"
---
# <a name="balanced-journals-for-interunit-accounting"></a><span data-ttu-id="78c0e-103">Journaux équilibrés pour la comptabilité interunités</span><span class="sxs-lookup"><span data-stu-id="78c0e-103">Balanced journals for interunit accounting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78c0e-104">Cet article décrit la manière dont un journal est automatiquement équilibré lorsqu'une dimension financière d'équilibrage est activée dans la page de comptabilité.</span><span class="sxs-lookup"><span data-stu-id="78c0e-104">This article shows how a journal is automatically balanced when a balancing financial dimension is selected on the Ledger page.</span></span> 

<span data-ttu-id="78c0e-105">Si les écritures de compte ne sont pas équilibrées au niveau des valeurs de dimension financière, des écritures de compte supplémentaires sont créées automatiquement pour équilibrer le journal.</span><span class="sxs-lookup"><span data-stu-id="78c0e-105">If account entries don't balance at the level of the financial dimension values, additional account entries are created automatically to balance the journal.</span></span> <span data-ttu-id="78c0e-106">Ces écritures de compte utilisent les types de validation **Interunités - débit** et **Interunités - crédit** dans la page **Comptes pour transactions automatiques** pour déterminer le compte principal.</span><span class="sxs-lookup"><span data-stu-id="78c0e-106">These account entries use the **Interunit - debit** and **Interunit - credit** posting types on the **Accounts for automatic transactions** page to determine the main account.</span></span> <span data-ttu-id="78c0e-107">Par exemple, Unité commerciale, qui est le deuxième segment du compte général, est sélectionné comme dimension financière d'équilibrage, et les écritures comptables suivantes sont sur le point d'être créées.</span><span class="sxs-lookup"><span data-stu-id="78c0e-107">For example, Business Unit, which is the second segment of the ledger account, is selected as the balancing financial dimension, and the following accounting entries are about to be created.</span></span>

|                      |           |
|----------------------|-----------|
| <span data-ttu-id="78c0e-108">6100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="78c0e-108">6100 – MSP – OU\_256</span></span> | <span data-ttu-id="78c0e-109">100.00 DR</span><span class="sxs-lookup"><span data-stu-id="78c0e-109">100.00 DR</span></span> |
| <span data-ttu-id="78c0e-110">6100 – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="78c0e-110">6100 – NY – OU\_249</span></span>  | <span data-ttu-id="78c0e-111">100.00 DR</span><span class="sxs-lookup"><span data-stu-id="78c0e-111">100.00 DR</span></span> |
| <span data-ttu-id="78c0e-112">2100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="78c0e-112">2100 – MSP – OU\_256</span></span> | <span data-ttu-id="78c0e-113">200.00 CR</span><span class="sxs-lookup"><span data-stu-id="78c0e-113">200.00 CR</span></span> |

<span data-ttu-id="78c0e-114">Dans ce cas, les soldes suivants sont déterminés :</span><span class="sxs-lookup"><span data-stu-id="78c0e-114">In this case, the following balances are determined:</span></span>

-   <span data-ttu-id="78c0e-115">Pour l'unité commerciale MSP = 100,00 CR</span><span class="sxs-lookup"><span data-stu-id="78c0e-115">For Business Unit MSP = 100.00 CR</span></span>
-   <span data-ttu-id="78c0e-116">Pour l'unité commerciale NY = 100,00 DR</span><span class="sxs-lookup"><span data-stu-id="78c0e-116">For Business Unit NY = 100.00 DR</span></span>

<span data-ttu-id="78c0e-117">Par conséquent, les écritures comptables suivantes sont créées automatiquement pour équilibrer le journal au niveau des valeurs de dimension financière.</span><span class="sxs-lookup"><span data-stu-id="78c0e-117">Therefore, the following accounting entries are created automatically to balance the  journal at the level of the financial dimension values.</span></span>

|                                   |           |
|-----------------------------------|-----------|
| <span data-ttu-id="78c0e-118">(Débit interunités) – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="78c0e-118">(Interunit Debit) – MSP – OU\_256</span></span> | <span data-ttu-id="78c0e-119">100.00 DR</span><span class="sxs-lookup"><span data-stu-id="78c0e-119">100.00 DR</span></span> |
| <span data-ttu-id="78c0e-120">(Crédit interunités) – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="78c0e-120">(Interunit Credit) – NY – OU\_249</span></span> | <span data-ttu-id="78c0e-121">100.00 CR</span><span class="sxs-lookup"><span data-stu-id="78c0e-121">100.00 CR</span></span> |





