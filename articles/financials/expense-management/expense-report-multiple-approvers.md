---
title: "États de dépenses et approbateurs multiples"
description: "Cette rubrique fournit des informations sur les états de dépenses qui nécessitent l'approbation de plusieurs personnes."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvExpensesReportList
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: a76acb4912e6f4ace8bedfe45764f8a9594b9801
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="expense-reports-and-multiple-approvers"></a><span data-ttu-id="adb01-103">États de dépenses et approbateurs multiples</span><span class="sxs-lookup"><span data-stu-id="adb01-103">Expense reports and multiple approvers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="adb01-104">En fonction des stratégies d'approbation des dépenses de votre organisation, il se peut que plusieurs personnes doivent approuver un état de dépenses envoyé par un employé.</span><span class="sxs-lookup"><span data-stu-id="adb01-104">Depending on your organization's expense approval policies, more than one person might have to approve an expense report that is submitted by an employee.</span></span> <span data-ttu-id="adb01-105">Lorsque vous paramétrez le processus de workflow pour l'approbation des états de dépenses, vous pouvez ajouter des éléments de workflow qui incluent des tâches ou des étapes pour un ou plusieurs approbateurs des états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="adb01-105">When you set up the workflow process for expense report approval, you can add workflow elements that include tasks or steps for one or more expense report approvers.</span></span> <span data-ttu-id="adb01-106">Par exemple, vous pouvez exiger que tous les états de dépenses soient approuvés d'abord par le responsable de l'employé ayant soumis l'état, puis par le coordinateur des Achats.</span><span class="sxs-lookup"><span data-stu-id="adb01-106">For example, you might require that all expense reports be approved first by the manager of the employee who submitted the report and then by the Accounts payable coordinator.</span></span>

<span data-ttu-id="adb01-107">Si vous décidez d'exiger plusieurs approbateurs des états de dépenses, vous pouvez ajouter des éléments de workflow de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="adb01-107">If you decide to require multiple expense report approvers, you can add the workflow elements in any of the following ways:</span></span>

- <span data-ttu-id="adb01-108">Ajoutez un seul élément d'approbation qui contient une étape unique.</span><span class="sxs-lookup"><span data-stu-id="adb01-108">Add one approval element that has one step.</span></span> <span data-ttu-id="adb01-109">Par exemple, l'étape peut exiger qu'un état de dépenses soit affecté à un groupe d'utilisateurs et qu'il soit approuvé par 50 % des membres du groupe d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="adb01-109">For example, the step might require that an expense report be assigned to a user group, and that it be approved by 50 percent of the user group's members.</span></span>
- <span data-ttu-id="adb01-110">Ajoutez un seul élément d'approbation qui contient plusieurs étapes.</span><span class="sxs-lookup"><span data-stu-id="adb01-110">Add one approval element that has multiple steps.</span></span> <span data-ttu-id="adb01-111">Par exemple, l'élément d'approbation peut comporter les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="adb01-111">For example, the approval element might have the following steps:</span></span>

    1. <span data-ttu-id="adb01-112">Le responsable de l'employé qui a soumis l'état de dépenses l'approuve.</span><span class="sxs-lookup"><span data-stu-id="adb01-112">The manager of the employee who submitted the expense report approves it.</span></span>
    2. <span data-ttu-id="adb01-113">Le commis aux Achats vérifie les réceptions et les éléments de l'état de dépenses.</span><span class="sxs-lookup"><span data-stu-id="adb01-113">The Accounts payable clerk verifies the receipts and the expense report items.</span></span>
    3. <span data-ttu-id="adb01-114">Le propriétaire du budget approuve l'état de dépenses.</span><span class="sxs-lookup"><span data-stu-id="adb01-114">The budget owner approves the expense report.</span></span>

- <span data-ttu-id="adb01-115">Ajoutez plusieurs éléments d'approbation, chacun contenant une étape.</span><span class="sxs-lookup"><span data-stu-id="adb01-115">Add multiple approval elements, each of which has one step.</span></span> <span data-ttu-id="adb01-116">Par exemple, vous pouvez ajouter un élément d'approbation distinct pour chacune des étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="adb01-116">For example, you might add a separate approval element for each of the following steps:</span></span>

    1. <span data-ttu-id="adb01-117">Le responsable de l'employé approuve l'état de dépenses.</span><span class="sxs-lookup"><span data-stu-id="adb01-117">The employee's manager approves the expense report.</span></span>
    2. <span data-ttu-id="adb01-118">Le propriétaire du budget approuve l'état de dépenses.</span><span class="sxs-lookup"><span data-stu-id="adb01-118">The budget owner approves the expense report.</span></span>

