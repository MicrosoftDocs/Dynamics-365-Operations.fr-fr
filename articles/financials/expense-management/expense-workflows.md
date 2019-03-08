---
title: Définir des workflows pour les dépenses
description: Vous pouvez paramétrer un processus de workflow utilisé pour réviser et approuver les documents de déplacement et de dépenses.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8294aaa344e3cb6b79fa4f33f368258ca19c8205
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "355723"
---
# <a name="set-up-workflows-for-expense"></a><span data-ttu-id="76f0f-103">Définir des workflows pour les dépenses</span><span class="sxs-lookup"><span data-stu-id="76f0f-103">Set up workflows for expense</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="76f0f-104"> Vous pouvez paramétrer un processus de workflow utilisé pour réviser et approuver les documents de déplacement et de dépenses.</span><span class="sxs-lookup"><span data-stu-id="76f0f-104">You can set up a workflow process that is used to review and approve travel and expense documents.</span></span> <span data-ttu-id="76f0f-105">Les documents pour lesquels des workflows peuvent être définis incluent les états de dépenses, les demandes de voyage et les demandes d'avance de disponibilités.</span><span class="sxs-lookup"><span data-stu-id="76f0f-105">The documents for which workflows can be defined include expense reports, travel requisitions, and cash advance requests.</span></span>

<span data-ttu-id="76f0f-106">Un workflow représente un processus entreprise.</span><span class="sxs-lookup"><span data-stu-id="76f0f-106">A workflow represents a business process.</span></span> <span data-ttu-id="76f0f-107">Il définit le transfert d'un document dans le système et indique qui doit traiter une tâche ou approuver un document.</span><span class="sxs-lookup"><span data-stu-id="76f0f-107">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="76f0f-108">L'utilisation du système de workflow dans votre organisation présente plusieurs avantages :</span><span class="sxs-lookup"><span data-stu-id="76f0f-108">There are several benefits of using the workflow system in your organization:</span></span>

-   <span data-ttu-id="76f0f-109">**Processus cohérents** — Vous pouvez définir le processus d'approbation pour des documents spécifiques, tels que des demandes d'achat ou des états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="76f0f-109">**Consistent processes** — You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="76f0f-110">Le système de workflow permet de s'assurer que les documents sont traités et approuvés de manière cohérente et efficace.</span><span class="sxs-lookup"><span data-stu-id="76f0f-110">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>

-   <span data-ttu-id="76f0f-111">Visibilité de processus — Vous pouvez suivre le statut, l'historique et les mesures de performance d'une instance de workflow spécifique.</span><span class="sxs-lookup"><span data-stu-id="76f0f-111">Process visibility — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="76f0f-112">Vous pouvez ainsi déterminer si des modifications doivent être apportées au workflow afin d'en optimiser l'efficacité.</span><span class="sxs-lookup"><span data-stu-id="76f0f-112">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>

-   <span data-ttu-id="76f0f-113">Liste de travail centralisée — Les utilisateurs peuvent afficher une liste de travail centralisée pour consulter les tâches et les approbations de workflow qui leur sont affectées.</span><span class="sxs-lookup"><span data-stu-id="76f0f-113">Centralized work list — Users can view a centralized work list to view the workflow tasks and approvals assigned to them.</span></span> 

<span data-ttu-id="76f0f-114">**Types de workflows qu'il est possible de créer**</span><span class="sxs-lookup"><span data-stu-id="76f0f-114">**The types of workflows you can create**</span></span>

<span data-ttu-id="76f0f-115">Le tableau suivant répertorie les types de workflows que vous pouvez créer dans le module **Budgétisation**.</span><span class="sxs-lookup"><span data-stu-id="76f0f-115">The following table lists the types of workflows that you can create in **Expense**.</span></span>


|              <span data-ttu-id="76f0f-116"><strong>Type</strong></span><span class="sxs-lookup"><span data-stu-id="76f0f-116"><strong>Type</strong></span></span>              |                   <span data-ttu-id="76f0f-117"><strong>Utilisation</strong></span><span class="sxs-lookup"><span data-stu-id="76f0f-117"><strong>Use this type to</strong></span></span>                   |
|-------------------------------------------------|-----------------------------------------------------------------------|
|         <span data-ttu-id="76f0f-118"><strong>État de dépenses</strong></span><span class="sxs-lookup"><span data-stu-id="76f0f-118"><strong>Expense report</strong></span></span>         |            <span data-ttu-id="76f0f-119">Créer des workflows d'approbation pour les états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="76f0f-119">Create approval workflows for expense reports.</span></span>             |
|  <span data-ttu-id="76f0f-120"><strong>Validation automatique de l'état de dépenses</strong></span><span class="sxs-lookup"><span data-stu-id="76f0f-120"><strong>Expense report auto posting</strong></span></span>   |        <span data-ttu-id="76f0f-121">Créer des workflows de validation automatique pour les états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="76f0f-121">Create automatic posting workflows for expense reports.</span></span>        |
|       <span data-ttu-id="76f0f-122"><strong>Article de ligne de dépense</strong></span><span class="sxs-lookup"><span data-stu-id="76f0f-122"><strong>Expense line item</strong></span></span>        |     <span data-ttu-id="76f0f-123">Créer des workflows d'approbation pour les lignes des états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="76f0f-123">Create approval workflows for line items on expense reports.</span></span>      |
| <span data-ttu-id="76f0f-124"><strong>Validation automatique des lignes de dépense</strong></span><span class="sxs-lookup"><span data-stu-id="76f0f-124"><strong>Expense line item auto posting</strong></span></span> | <span data-ttu-id="76f0f-125">Créer des workflows de validation automatique pour les lignes des états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="76f0f-125">Create automatic posting workflows for line items on expense reports.</span></span> |
|       <span data-ttu-id="76f0f-126"><strong>Demande d'achat de déplacement</strong></span><span class="sxs-lookup"><span data-stu-id="76f0f-126"><strong>Travel requisition</strong></span></span>       |          <span data-ttu-id="76f0f-127">Créer des workflows d'approbation pour les demandes de voyage.</span><span class="sxs-lookup"><span data-stu-id="76f0f-127">Create approval workflows for travel requisitions.</span></span>           |
|      <span data-ttu-id="76f0f-128"><strong>Demande d'avance de disponibilités</strong></span><span class="sxs-lookup"><span data-stu-id="76f0f-128"><strong>Cash advance request</strong></span></span>      |         <span data-ttu-id="76f0f-129">Créer des workflows d'approbation pour les demandes d'avance de disponibilités.</span><span class="sxs-lookup"><span data-stu-id="76f0f-129">Create approval workflows for cash advance requests.</span></span>          |
|        <span data-ttu-id="76f0f-130"><strong>Recouvrement fiscal de la TVA</strong></span><span class="sxs-lookup"><span data-stu-id="76f0f-130"><strong>VAT tax recovery</strong></span></span>        | <span data-ttu-id="76f0f-131">Créer des workflows d'approbation pour la récupération de la taxe sur la valeur ajoutée (VAT).</span><span class="sxs-lookup"><span data-stu-id="76f0f-131">Create approval workflows for the recovery of value-added tax (VAT).</span></span>  |

