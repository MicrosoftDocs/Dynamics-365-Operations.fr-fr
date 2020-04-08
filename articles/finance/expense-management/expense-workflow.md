---
title: Workflow de gestion des dépenses
description: Cette rubrique explique comment utiliser le système de flux de travail dans Microsoft Dynamics 365 Finance pour configurer un processus de révision des notes de frais dans la Gestion des dépenses.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5207be92cb58d8ab2658096b3e0f3fc81d73d91e
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3153969"
---
# <a name="expense-management-workflow"></a><span data-ttu-id="112f2-103">Workflow de gestion des dépenses</span><span class="sxs-lookup"><span data-stu-id="112f2-103">Expense management workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="112f2-104">Vous pouvez utiliser le système de workflow pour paramétrer un processus de révision pour les états de dépenses dans Gestion des dépenses.</span><span class="sxs-lookup"><span data-stu-id="112f2-104">You can use the workflow system to set up a review process for expense reports in Expense management.</span></span> <span data-ttu-id="112f2-105">Vous pouvez paramétrer un workflow qui utilise les critères suivants pour déterminer qui approuve les états de dépenses :</span><span class="sxs-lookup"><span data-stu-id="112f2-105">You can set up a workflow that uses the following criteria to determine who approves expense reports:</span></span>

- <span data-ttu-id="112f2-106">La hiérarchie de génération d'états des employés et le plafond autorisé prédéfinis</span><span class="sxs-lookup"><span data-stu-id="112f2-106">The employee reporting hierarchy and predefined approval limits</span></span>
- <span data-ttu-id="112f2-107">Approbation à plusieurs niveaux qui prend en charge les approbateurs intermédiaires et un approbateur final</span><span class="sxs-lookup"><span data-stu-id="112f2-107">Multi-level approval that supports interim approvers and a final approver</span></span>
- <span data-ttu-id="112f2-108">Les dimensions financières et la responsabilité du projet</span><span class="sxs-lookup"><span data-stu-id="112f2-108">Financial dimensions and project responsibility</span></span>
- <span data-ttu-id="112f2-109">L'affectation à des utilisateurs ou groupes d'utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="112f2-109">Assignment to specific users or user groups</span></span>

<span data-ttu-id="112f2-110">Les approbations de workflow peuvent être créées pour les états de dépenses, les demandes de voyage, les avances de disponibilités et la récupération de la taxe sur la valeur ajoutée (TVA).</span><span class="sxs-lookup"><span data-stu-id="112f2-110">Workflow approvals can be created for expense reports, travel requisitions, cash advances, and value-added tax (VAT) recovery.</span></span>

<span data-ttu-id="112f2-111">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="112f2-111">**Example**</span></span>

<span data-ttu-id="112f2-112">Le processus suivant est un exemple de workflow de gestion des dépenses pour un état de dépenses.</span><span class="sxs-lookup"><span data-stu-id="112f2-112">The following process is an example of the expense management workflow for an expense report.</span></span>

1. <span data-ttu-id="112f2-113">Un employé crée et enregistre un état de dépenses.</span><span class="sxs-lookup"><span data-stu-id="112f2-113">An employee creates and saves an expense report.</span></span>
2. <span data-ttu-id="112f2-114">L'employé soumet l'état de dépenses pour approbation.</span><span class="sxs-lookup"><span data-stu-id="112f2-114">The employee submits the expense report for approval.</span></span> <span data-ttu-id="112f2-115">L'approbateur est identifié en fonction des règles qui ont été définies lors du paramétrage du workflow.</span><span class="sxs-lookup"><span data-stu-id="112f2-115">The approver is identified based on the rules that were defined when the workflow was set up.</span></span>
3. <span data-ttu-id="112f2-116">L'approbateur reçoit une notification lui signalant qu'un état de dépenses est prêt pour approbation.</span><span class="sxs-lookup"><span data-stu-id="112f2-116">The approver receives a notification that an expense report is ready for approval.</span></span> <span data-ttu-id="112f2-117">L'approbateur révise l'état de dépenses et vérifie que les conditions suivantes sont remplies :</span><span class="sxs-lookup"><span data-stu-id="112f2-117">The approver reviews the expense report and verifies that the following conditions are met:</span></span>

    - <span data-ttu-id="112f2-118">Les dépenses ne violent aucune stratégie des dépenses.</span><span class="sxs-lookup"><span data-stu-id="112f2-118">The expenses don't violate any expense policies.</span></span> <span data-ttu-id="112f2-119">Si une dépense viole une stratégie, l'approbateur vérifie que l'état de dépenses comprend une justification commerciale valide.</span><span class="sxs-lookup"><span data-stu-id="112f2-119">If an expense violates a policy, the approver verifies that the expense report includes a valid business justification.</span></span>
    - <span data-ttu-id="112f2-120">Des reçus électroniques sont joints à l'état de dépenses.</span><span class="sxs-lookup"><span data-stu-id="112f2-120">Electronic receipts are attached to the expense report.</span></span>

4. <span data-ttu-id="112f2-121">L'approbateur approuve l'état de dépenses.</span><span class="sxs-lookup"><span data-stu-id="112f2-121">The approver approves the expense report.</span></span>
5. <span data-ttu-id="112f2-122">L'état de dépenses est affecté au coordinateur de la Comptabilité fournisseur pour validation.</span><span class="sxs-lookup"><span data-stu-id="112f2-122">The expense report is assigned to the Accounts payable coordinator for posting.</span></span>
6. <span data-ttu-id="112f2-123">L'une des étapes suivantes se produit, selon que la validation automatique est configurée :</span><span class="sxs-lookup"><span data-stu-id="112f2-123">One of the following steps occurs, depending on whether automatic posting is configured:</span></span>

    - <span data-ttu-id="112f2-124">Si la validation automatique est configurée, l'état de dépenses est traité pour le paiement et le statut de l'état de dépenses est mis à jour.</span><span class="sxs-lookup"><span data-stu-id="112f2-124">If automatic posting is configured, the expense report is processed for payment, and the status of the expense report is updated.</span></span>
    - <span data-ttu-id="112f2-125">Si la validation automatique n'est pas configurée, le coordinateur de la Comptabilité fournisseur vérifie que toutes les réceptions originales ont été envoyées, et que les réceptions correspondent aux dépenses indiquées dans l'état de dépenses.</span><span class="sxs-lookup"><span data-stu-id="112f2-125">If automatic posting isn't configured, the Accounts payable coordinator verifies that all original receipts have been submitted, and that the receipts are aligned with the expenses on the expense report.</span></span> <span data-ttu-id="112f2-126">L'exactitude de tous les codes taxe qui sont entrés dans l'état de dépenses doit également être vérifiée.</span><span class="sxs-lookup"><span data-stu-id="112f2-126">All tax codes that are entered on the expense report must also be verified as correct.</span></span>

<span data-ttu-id="112f2-127">Une fois ces conditions vérifiées, l'état de dépenses est validé.</span><span class="sxs-lookup"><span data-stu-id="112f2-127">After these requirements are verified, the expense report is posted.</span></span>

<span data-ttu-id="112f2-128">Une fois l'état de dépenses validé, le paiement est autorisé pour l'état de dépenses et l'employé est remboursé.</span><span class="sxs-lookup"><span data-stu-id="112f2-128">After the expense report is posted, payment is authorized for the expense report, and the employee is reimbursed.</span></span>
