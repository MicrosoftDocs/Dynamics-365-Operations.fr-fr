---
title: "Définir des workflows pour les dépenses"
description: "Vous pouvez paramétrer un processus de workflow utilisé pour réviser et approuver les documents de déplacement et de dépenses."
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi2
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 19d725f15f00afce1a2ae4b336226f1dafa94b41
ms.contentlocale: fr-fr
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-workflows-for-expense"></a><span data-ttu-id="1ec61-103">Définir des workflows pour les dépenses</span><span class="sxs-lookup"><span data-stu-id="1ec61-103">Set up workflows for expense</span></span>

[!include[banner](../includes/banner.md)]<span data-ttu-id="1ec61-104"> Vous pouvez paramétrer un processus de workflow utilisé pour réviser et approuver les documents de déplacement et de dépenses.</span><span class="sxs-lookup"><span data-stu-id="1ec61-104"> You can set up a workflow process that is used to review and approve travel and expense documents.</span></span> <span data-ttu-id="1ec61-105">Les documents pour lesquels des workflows peuvent être définis incluent les états de dépenses, les demandes de voyage et les demandes d'avance de disponibilités.</span><span class="sxs-lookup"><span data-stu-id="1ec61-105">The documents for which workflows can be defined include expense reports, travel requisitions, and cash advance requests.</span></span>

<span data-ttu-id="1ec61-106">Un workflow représente un processus entreprise.</span><span class="sxs-lookup"><span data-stu-id="1ec61-106">A workflow represents a business process.</span></span> <span data-ttu-id="1ec61-107">Il définit le transfert d'un document dans le système et indique qui doit traiter une tâche ou approuver un document.</span><span class="sxs-lookup"><span data-stu-id="1ec61-107">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="1ec61-108">L'utilisation du système de workflow dans votre organisation présente plusieurs avantages :</span><span class="sxs-lookup"><span data-stu-id="1ec61-108">There are several benefits of using the workflow system in your organization:</span></span>

-   <span data-ttu-id="1ec61-109">**Processus cohérents** — Vous pouvez définir le processus d'approbation pour des documents spécifiques, tels que des demandes d'achat ou des états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="1ec61-109">**Consistent processes** — You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="1ec61-110">Le système de workflow permet de s'assurer que les documents sont traités et approuvés de manière cohérente et efficace.</span><span class="sxs-lookup"><span data-stu-id="1ec61-110">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>

-   <span data-ttu-id="1ec61-111">Visibilité de processus — Vous pouvez suivre le statut, l'historique et les mesures de performance d'une instance de workflow spécifique.</span><span class="sxs-lookup"><span data-stu-id="1ec61-111">Process visibility — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="1ec61-112">Vous pouvez ainsi déterminer si des modifications doivent être apportées au workflow afin d'en optimiser l'efficacité.</span><span class="sxs-lookup"><span data-stu-id="1ec61-112">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>

-   <span data-ttu-id="1ec61-113">Liste de travail centralisée — Les utilisateurs peuvent afficher une liste de travail centralisée pour consulter les tâches et les approbations de workflow qui leur sont affectées.</span><span class="sxs-lookup"><span data-stu-id="1ec61-113">Centralized work list — Users can view a centralized work list to view the workflow tasks and approvals assigned to them.</span></span> 

<span data-ttu-id="1ec61-114">**Types de workflows qu'il est possible de créer**</span><span class="sxs-lookup"><span data-stu-id="1ec61-114">**The types of workflows you can create**</span></span>

<span data-ttu-id="1ec61-115">Le tableau suivant répertorie les types de workflows que vous pouvez créer dans le module **Budgétisation**.</span><span class="sxs-lookup"><span data-stu-id="1ec61-115">The following table lists the types of workflows that you can create in **Expense**.</span></span>

| <span data-ttu-id="1ec61-116">**Type**</span><span class="sxs-lookup"><span data-stu-id="1ec61-116">**Type**</span></span>                           | <span data-ttu-id="1ec61-117">**Utilisation**</span><span class="sxs-lookup"><span data-stu-id="1ec61-117">**Use this type to**</span></span>                                                 |     
|------------------------------------|----------------------------------------------------------------------|
| <span data-ttu-id="1ec61-118">**État de dépenses**</span><span class="sxs-lookup"><span data-stu-id="1ec61-118">**Expense report**</span></span>                 | <span data-ttu-id="1ec61-119">Créer des workflows d'approbation pour les états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="1ec61-119">Create approval workflows for expense reports.</span></span>                       |      
| <span data-ttu-id="1ec61-120">**Validation automatique de l'état de dépenses**</span><span class="sxs-lookup"><span data-stu-id="1ec61-120">**Expense report auto posting**</span></span>    | <span data-ttu-id="1ec61-121">Créer des workflows de validation automatique pour les états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="1ec61-121">Create automatic posting workflows for expense reports.</span></span>              |     
| <span data-ttu-id="1ec61-122">**Article de ligne de dépense**</span><span class="sxs-lookup"><span data-stu-id="1ec61-122">**Expense line item**</span></span>              | <span data-ttu-id="1ec61-123">Créer des workflows d'approbation pour les lignes des états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="1ec61-123">Create approval workflows for line items on expense reports.</span></span>         |     
| <span data-ttu-id="1ec61-124">**Validation automatique des lignes de dépense**</span><span class="sxs-lookup"><span data-stu-id="1ec61-124">**Expense line item auto posting**</span></span> | <span data-ttu-id="1ec61-125">Créer des workflows de validation automatique pour les lignes des états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="1ec61-125">Create automatic posting workflows for line items on expense reports.</span></span>|
| <span data-ttu-id="1ec61-126">**Demande d'achat de déplacement**</span><span class="sxs-lookup"><span data-stu-id="1ec61-126">**Travel requisition**</span></span>             | <span data-ttu-id="1ec61-127">Créer des workflows d'approbation pour les demandes de voyage.</span><span class="sxs-lookup"><span data-stu-id="1ec61-127">Create approval workflows for travel requisitions.</span></span>                   |    
| <span data-ttu-id="1ec61-128">**Demande d'avance de disponibilités**</span><span class="sxs-lookup"><span data-stu-id="1ec61-128">**Cash advance request**</span></span>           | <span data-ttu-id="1ec61-129">Créer des workflows d'approbation pour les demandes d'avance de disponibilités.</span><span class="sxs-lookup"><span data-stu-id="1ec61-129">Create approval workflows for cash advance requests.</span></span>                 |     
| <span data-ttu-id="1ec61-130">**Recouvrement fiscal de la TVA**</span><span class="sxs-lookup"><span data-stu-id="1ec61-130">**VAT tax recovery**</span></span>               | <span data-ttu-id="1ec61-131">Créer des workflows d'approbation pour la récupération de la taxe sur la valeur ajoutée (VAT).</span><span class="sxs-lookup"><span data-stu-id="1ec61-131">Create approval workflows for the recovery of value-added tax (VAT).</span></span> |       

