---
title: Création d'un traitement par lots
description: Un traitement par lots est un groupe de tâches soumis à une instance Serveur d'objets d'application (AOS) pour un traitement automatique.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4903724adc9deaa40b6cd04c215273dd4b0522d4
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982524"
---
# <a name="create-a-batch-job"></a><span data-ttu-id="d36b3-103">Création d'un traitement par lots</span><span class="sxs-lookup"><span data-stu-id="d36b3-103">Create a batch job</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d36b3-104">Un traitement par lots est un groupe de tâches soumis à une instance Serveur d'objets d'application (AOS) pour un traitement automatique.</span><span class="sxs-lookup"><span data-stu-id="d36b3-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="d36b3-105">L'exécution de traitements par lots utilise les informations d'authentification de sécurité de l'utilisateur qui a créé la tâche.</span><span class="sxs-lookup"><span data-stu-id="d36b3-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="d36b3-106">Procédez comme suit pour créer un traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="d36b3-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="d36b3-107">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="d36b3-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="d36b3-108">Créer le traitement par lots</span><span class="sxs-lookup"><span data-stu-id="d36b3-108">Create the batch job</span></span>
1. <span data-ttu-id="d36b3-109">Accédez à **Volet de navigation pane > Modules > Administration système> Recherches > Traitements par lots**.</span><span class="sxs-lookup"><span data-stu-id="d36b3-109">Go to **Navigation pane > Modules > System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="d36b3-110">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d36b3-110">Click **New**.</span></span>
3. <span data-ttu-id="d36b3-111">Tapez une valeur dans le champ **Description de la tâche**.</span><span class="sxs-lookup"><span data-stu-id="d36b3-111">In the **Job description** field, type a value.</span></span>
4. <span data-ttu-id="d36b3-112">Dans le champ **Date/heure de début réel**, entrez une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="d36b3-112">In the **Scheduled start date/time** field, enter a date and time.</span></span>
5. <span data-ttu-id="d36b3-113">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d36b3-113">Click **Save**.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="d36b3-114">Créer une répétition</span><span class="sxs-lookup"><span data-stu-id="d36b3-114">Create a recurrence</span></span>
1. <span data-ttu-id="d36b3-115">Dans le volet Actions, cliquez sur **Traitement par lots**.</span><span class="sxs-lookup"><span data-stu-id="d36b3-115">On the Action Pane, click **Batch job**.</span></span>
2. <span data-ttu-id="d36b3-116">Cliquez sur **Répétition**.</span><span class="sxs-lookup"><span data-stu-id="d36b3-116">Click **Recurrence**.</span></span> <span data-ttu-id="d36b3-117">Utilisez ces options pour entrer une gamme et un modèle pour la répétition.</span><span class="sxs-lookup"><span data-stu-id="d36b3-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="d36b3-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d36b3-118">Click **OK**.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="d36b3-119">Ajouter des alertes</span><span class="sxs-lookup"><span data-stu-id="d36b3-119">Add alerts</span></span>
1. <span data-ttu-id="d36b3-120">Dans le volet Actions, cliquez sur **Traitement par lots**.</span><span class="sxs-lookup"><span data-stu-id="d36b3-120">On the Action Pane, click **Batch job**.</span></span>
2. <span data-ttu-id="d36b3-121">Cliquez sur **Alertes**.</span><span class="sxs-lookup"><span data-stu-id="d36b3-121">Click **Alerts**.</span></span> <span data-ttu-id="d36b3-122">Indiquez si vous voulez que des messages d'alerte soient envoyés à la fin du traitement par lots ou lorsque celui-ci rencontre une erreur ou est annulé.</span><span class="sxs-lookup"><span data-stu-id="d36b3-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="d36b3-123">Spécifiez ensuite si vous souhaitez que les alertes soient affichées sous la forme de messages contextuels.</span><span class="sxs-lookup"><span data-stu-id="d36b3-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="d36b3-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d36b3-124">Click **OK**.</span></span>

## <a name="adjust-batch-job-status"></a><span data-ttu-id="d36b3-125">Ajuster le statut du traitement par lots</span><span class="sxs-lookup"><span data-stu-id="d36b3-125">Adjust batch job status</span></span>
1. <span data-ttu-id="d36b3-126">Accédez à **Administration du système > Recherches > Traitements par lots**.</span><span class="sxs-lookup"><span data-stu-id="d36b3-126">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="d36b3-127">Sélectionnez le traitement par lots approprié.</span><span class="sxs-lookup"><span data-stu-id="d36b3-127">Select the appropriate batch job.</span></span>
3. <span data-ttu-id="d36b3-128">Dans le volet Actions, cliquez sur **Traitement par lots > Fonctions > Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="d36b3-128">On the Action Pane, click **Batch job > Functions > Change status**.</span></span>
4. <span data-ttu-id="d36b3-129">Sélectionnez le statut approprié :</span><span class="sxs-lookup"><span data-stu-id="d36b3-129">Select the appropriate status:</span></span>
    - <span data-ttu-id="d36b3-130">**Retenir** : Définissez le traitement par lots comme **retenu** de sorte qu'il soit différé dans le planificateur de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="d36b3-130">**Withhold**: Set the batch job as **withhold** so it is withheld from the batch job scheduler.</span></span> <span data-ttu-id="d36b3-131">Équivalent à *arrêter*.</span><span class="sxs-lookup"><span data-stu-id="d36b3-131">Equivalent to *stop*.</span></span>
    - <span data-ttu-id="d36b3-132">**En attente** : Définissez le traitement par lots comme **en attente** pour qu'il attende d'être prélevé par le planificateur de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="d36b3-132">**Waiting**: Set the batch job as **waiting** so it is waiting to be picked up by the batch job scheduler.</span></span> <span data-ttu-id="d36b3-133">Équivalent à *lancer*.</span><span class="sxs-lookup"><span data-stu-id="d36b3-133">Equivalent to *go*.</span></span>
5. <span data-ttu-id="d36b3-134">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d36b3-134">Click **OK**.</span></span>
