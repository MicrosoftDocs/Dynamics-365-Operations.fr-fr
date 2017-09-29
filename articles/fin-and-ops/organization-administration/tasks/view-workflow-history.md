--- 
title: Afficher l'historique du workflow
description: "Utilisez ces étapes pour afficher le statut d'un document envoyé au système de workflow pour traitement et approbation."
author: jasongre
manager: AnnBe
ms.date: 02/21/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 212f9fe8bc7807b9209523564ead716959875241
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="view-workflow-history"></a><span data-ttu-id="2795c-103">Afficher l'historique du workflow</span><span class="sxs-lookup"><span data-stu-id="2795c-103">View workflow history</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2795c-104">Utilisez ces étapes pour afficher le statut d'un document envoyé au système de workflow pour traitement et approbation.</span><span class="sxs-lookup"><span data-stu-id="2795c-104">Use these steps to view the status of a document that was submitted to the workflow system for processing and approval.</span></span> <span data-ttu-id="2795c-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="2795c-105">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="2795c-106">Accédez à Commun > Recherches > Workflow > Historique du workflow.</span><span class="sxs-lookup"><span data-stu-id="2795c-106">Go to Common > Inquiries > Workflow > Workflow history.</span></span>
    * <span data-ttu-id="2795c-107">Cet écran permet d'afficher le statut d'un document envoyé au système de workflow pour traitement et approbation.</span><span class="sxs-lookup"><span data-stu-id="2795c-107">Use this form to view the status of a document that was submitted to the workflow system for processing and approval.</span></span>  
    * <span data-ttu-id="2795c-108">L'ID d'instance est le code d'identification de l'instance de workflow qui traite ou qui a traité le document.</span><span class="sxs-lookup"><span data-stu-id="2795c-108">The Instance ID is      the identification code of the workflow instance that is processing, or has processed the document.</span></span>  
    * <span data-ttu-id="2795c-109">Statut est le statut de workflow du document.</span><span class="sxs-lookup"><span data-stu-id="2795c-109">The Status is the workflow status of the document.</span></span>  
    * <span data-ttu-id="2795c-110">ID du workflow est le code d'identification du workflow qui traite ou qui a traité le document.</span><span class="sxs-lookup"><span data-stu-id="2795c-110">The Workflow ID is the identification code of the workflow that is processing, or has processed the document.</span></span>  
    * <span data-ttu-id="2795c-111">Document est le code d'identification du document.</span><span class="sxs-lookup"><span data-stu-id="2795c-111">The Document is the identification code of the document.</span></span>  
    * <span data-ttu-id="2795c-112">Type de document est le type de document envoyé pour traitement.</span><span class="sxs-lookup"><span data-stu-id="2795c-112">The Document type is the type of document that was submitted for processing.</span></span>  
    * <span data-ttu-id="2795c-113">Workflow est le nom du workflow qui traite ou qui a traité le document.</span><span class="sxs-lookup"><span data-stu-id="2795c-113">The Workflow is the name of the workflow that is processing, or has processed the document.</span></span>  
    * <span data-ttu-id="2795c-114">Version est le numéro de version du workflow qui traite ou qui a traité le document.</span><span class="sxs-lookup"><span data-stu-id="2795c-114">The Version is the version number of the workflow that is processing, or has processed the document.</span></span>  
    * <span data-ttu-id="2795c-115">Date et heure de création est la date et l'heure de l'envoi du document.</span><span class="sxs-lookup"><span data-stu-id="2795c-115">The Created date and time is the date and time that the document was submitted.</span></span>  
    * <span data-ttu-id="2795c-116">Temps écoulé est le temps qui s'est écoulé depuis l'envoi du document.</span><span class="sxs-lookup"><span data-stu-id="2795c-116">The Elapsed time is the time that has passed since the document was submitted.</span></span>  
    * <span data-ttu-id="2795c-117">Le bouton Reprendre vous permet de reprendre le processus du workflow du document sélectionné.</span><span class="sxs-lookup"><span data-stu-id="2795c-117">The Resume button allows you to resume the workflow process for the selected document.</span></span>  
    * <span data-ttu-id="2795c-118">Le bouton Rappeler vous permet de rappeler le document sélectionné afin qu'il ne soit pas traité.</span><span class="sxs-lookup"><span data-stu-id="2795c-118">The Recall button allows you to recall the selected document so that it is not processed.</span></span>   
2. <span data-ttu-id="2795c-119">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2795c-119">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2795c-120">Assurez-vous que la section Éléments de travail est développée.</span><span class="sxs-lookup"><span data-stu-id="2795c-120">Make sure the Work items section is expanded.</span></span>    <span data-ttu-id="2795c-121">Dans cette section, vous pouvez afficher les éléments de travail associés au document sélectionné.</span><span class="sxs-lookup"><span data-stu-id="2795c-121">In this section you can view the work items that are associated with the selected document.</span></span> <span data-ttu-id="2795c-122">Par exemple, il se peut qu'il faille terminer une tâche ou approuver un document.</span><span class="sxs-lookup"><span data-stu-id="2795c-122">For example, a task may have to be completed, or the document may have to be approved.</span></span>  
    * <span data-ttu-id="2795c-123">Le bouton Réaffecter ouvre une boîte de dialogue dans laquelle vous pouvez réaffecter un élément de travail à un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2795c-123">The Reassign button will open a dialog box where you can reassign a work item to another user.</span></span>  
    * <span data-ttu-id="2795c-124">Assurez-vous que la section Détails du suivi est développée.</span><span class="sxs-lookup"><span data-stu-id="2795c-124">Make sure the Tracking details section is expanded.</span></span>    <span data-ttu-id="2795c-125">Dans cette section, vous pouvez afficher l'historique du workflow du document sélectionné.</span><span class="sxs-lookup"><span data-stu-id="2795c-125">In this section you can view the workflow history of the selected document.</span></span>  


