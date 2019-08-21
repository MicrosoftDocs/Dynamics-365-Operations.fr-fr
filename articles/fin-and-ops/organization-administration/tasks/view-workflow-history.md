---
title: Afficher l'historique du flux de travail
description: Cette rubrique décrit les étapes pour afficher le statut d'un document qui a été envoyé au système de workflow pour traitement et approbation.
author: jasongre
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowStatus
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 16c6594161f1fecd36183a6b8f2c798f52d70a9c
ms.sourcegitcommit: 81e6eaa2178fda7f7d086ad978f4c891bc4ec10a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/10/2019
ms.locfileid: "1738786"
---
# <a name="view-workflow-history"></a><span data-ttu-id="098dc-103">Afficher l'historique du flux de travail</span><span class="sxs-lookup"><span data-stu-id="098dc-103">View workflow history</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="098dc-104">Cette rubrique décrit les étapes pour afficher le statut d'un document qui a été envoyé au système de workflow pour traitement et approbation.</span><span class="sxs-lookup"><span data-stu-id="098dc-104">This topic describes the steps to view the status of a document that was submitted to the workflow system for processing and approval.</span></span> <span data-ttu-id="098dc-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="098dc-105">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="098dc-106">Allez dans **Volet de navigation > Modules > Commun > Recherches > Workflow > Historique du workflow**.</span><span class="sxs-lookup"><span data-stu-id="098dc-106">Go to **Navigation pane > Modules > Common > Inquiries > Workflow > Workflow history**.</span></span>
    - <span data-ttu-id="098dc-107">Cet écran permet d'afficher le statut d'un document envoyé au système de workflow pour traitement et approbation.</span><span class="sxs-lookup"><span data-stu-id="098dc-107">Use this form to view the status of a document that was submitted to the workflow system for processing and approval.</span></span>  
    - <span data-ttu-id="098dc-108">**ID d'instance** est le code d'identification de l'instance de workflow qui traite ou qui a traité le document.</span><span class="sxs-lookup"><span data-stu-id="098dc-108">The **Instance ID** is the identification code of the workflow instance that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="098dc-109">**Statut** est le statut de workflow du document.</span><span class="sxs-lookup"><span data-stu-id="098dc-109">The **Status** is the workflow status of the document.</span></span>  
    - <span data-ttu-id="098dc-110">**ID du workflow** est le code d'identification du workflow qui traite ou qui a traité le document.</span><span class="sxs-lookup"><span data-stu-id="098dc-110">The **Workflow ID** is the identification code of the workflow that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="098dc-111">**Document** est le code d'identification du document.</span><span class="sxs-lookup"><span data-stu-id="098dc-111">The **Document** is the identification code of the document.</span></span>  
    - <span data-ttu-id="098dc-112">**Type de document** est le type de document envoyé pour traitement.</span><span class="sxs-lookup"><span data-stu-id="098dc-112">The **Document type** is the type of document that was submitted for processing.</span></span>  
    - <span data-ttu-id="098dc-113">**Workflow** est le nom du workflow qui traite ou qui a traité le document.</span><span class="sxs-lookup"><span data-stu-id="098dc-113">The **Workflow** is the name of the workflow that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="098dc-114">**Version** est le numéro de version du workflow qui traite ou qui a traité le document.</span><span class="sxs-lookup"><span data-stu-id="098dc-114">The **Version** is the version number of the workflow that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="098dc-115">**Date et heure de création** est la date et l'heure de l'envoi du document.</span><span class="sxs-lookup"><span data-stu-id="098dc-115">The **Created date and time** is the date and time that the document was submitted.</span></span>  
    - <span data-ttu-id="098dc-116">**Temps écoulé** est le temps qui s'est écoulé depuis l'envoi du document.</span><span class="sxs-lookup"><span data-stu-id="098dc-116">The **Elapsed time** is the time that has passed since the document was submitted.</span></span>  
    - <span data-ttu-id="098dc-117">Le bouton **Reprendre** vous permet de reprendre le processus du workflow du document sélectionné.</span><span class="sxs-lookup"><span data-stu-id="098dc-117">The **Resume** button allows you to resume the workflow process for the selected document.</span></span>  
    - <span data-ttu-id="098dc-118">Le bouton **Rappeler** vous permet de rappeler le document sélectionné afin qu'il ne soit pas traité.</span><span class="sxs-lookup"><span data-stu-id="098dc-118">The **Recall** button allows you to recall the selected document so that it is not processed.</span></span>   
2. <span data-ttu-id="098dc-119">Dans la liste, sélectionnez le lien dans la ligne souhaitée.</span><span class="sxs-lookup"><span data-stu-id="098dc-119">In the list, select the link in the desired row.</span></span>
    - <span data-ttu-id="098dc-120">Assurez-vous que la section **Éléments de travail** est développée.</span><span class="sxs-lookup"><span data-stu-id="098dc-120">Make sure the **Work items** section is expanded.</span></span> <span data-ttu-id="098dc-121">Dans cette section, vous pouvez afficher les éléments de travail associés au document sélectionné.</span><span class="sxs-lookup"><span data-stu-id="098dc-121">In this section you can view the work items that are associated with the selected document.</span></span> <span data-ttu-id="098dc-122">Par exemple, il se peut qu'il faille terminer une tâche ou approuver un document.</span><span class="sxs-lookup"><span data-stu-id="098dc-122">For example, a task may have to be completed, or the document may have to be approved.</span></span>  
    - <span data-ttu-id="098dc-123">Le bouton **Réaffecter** ouvre une boîte de dialogue dans laquelle vous pouvez réaffecter un élément de travail à un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="098dc-123">The **Reassign** button will open a dialog box where you can reassign a work item to another user.</span></span>  
    - <span data-ttu-id="098dc-124">Assurez-vous que la section **Détails du suivi** est développée.</span><span class="sxs-lookup"><span data-stu-id="098dc-124">Make sure the **Tracking details** section is expanded.</span></span> <span data-ttu-id="098dc-125">Dans cette section, vous pouvez afficher l'historique du workflow du document sélectionné.</span><span class="sxs-lookup"><span data-stu-id="098dc-125">In this section you can view the workflow history of the selected document.</span></span>  

