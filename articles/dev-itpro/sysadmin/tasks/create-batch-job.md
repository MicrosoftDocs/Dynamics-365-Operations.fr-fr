--- 
title: "Création d'un traitement par lots"
description: "Un traitement par lots est un groupe de tâches soumis à une instance Serveur d'objets d'application (AOS) pour un traitement automatique."
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 31c8e2ba87ef8c17a3147e1159104585258d4164
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-a-batch-job"></a><span data-ttu-id="2bc6f-103">Création d'un traitement par lots</span><span class="sxs-lookup"><span data-stu-id="2bc6f-103">Create a batch job</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2bc6f-104">Un traitement par lots est un groupe de tâches soumis à une instance Serveur d'objets d'application (AOS) pour un traitement automatique.</span><span class="sxs-lookup"><span data-stu-id="2bc6f-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="2bc6f-105">L'exécution de traitements par lots utilise les informations d'authentification de sécurité de l'utilisateur qui a créé la tâche.</span><span class="sxs-lookup"><span data-stu-id="2bc6f-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="2bc6f-106">Procédez comme suit pour créer un traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="2bc6f-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="2bc6f-107">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="2bc6f-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="2bc6f-108">Créer le traitement par lots</span><span class="sxs-lookup"><span data-stu-id="2bc6f-108">Create the batch job</span></span>
1. <span data-ttu-id="2bc6f-109">Allez dans Administration du système > Recherches > Traitements par lots.</span><span class="sxs-lookup"><span data-stu-id="2bc6f-109">Go to System administration > Inquiries > Batch jobs.</span></span>
2. <span data-ttu-id="2bc6f-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="2bc6f-110">Click New.</span></span>
3. <span data-ttu-id="2bc6f-111">Tapez une valeur dans le champ Description de la tâche.</span><span class="sxs-lookup"><span data-stu-id="2bc6f-111">In the Job description field, type a value.</span></span>
4. <span data-ttu-id="2bc6f-112">Dans le champ Date/heure de début réel, entrez une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="2bc6f-112">In the Scheduled start date/time field, enter a date and time.</span></span>
5. <span data-ttu-id="2bc6f-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="2bc6f-113">Click Save.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="2bc6f-114">Créer une répétition</span><span class="sxs-lookup"><span data-stu-id="2bc6f-114">Create a recurrence</span></span>
1. <span data-ttu-id="2bc6f-115">Dans le volet Actions, cliquez sur Traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="2bc6f-115">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="2bc6f-116">Cliquez sur Répétition.</span><span class="sxs-lookup"><span data-stu-id="2bc6f-116">Click Recurrence.</span></span>
    * <span data-ttu-id="2bc6f-117">Utilisez ces options pour entrer une gamme et un modèle pour la répétition.</span><span class="sxs-lookup"><span data-stu-id="2bc6f-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="2bc6f-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2bc6f-118">Click OK.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="2bc6f-119">Ajouter des alertes</span><span class="sxs-lookup"><span data-stu-id="2bc6f-119">Add alerts</span></span>
1. <span data-ttu-id="2bc6f-120">Dans le volet Actions, cliquez sur Traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="2bc6f-120">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="2bc6f-121">Cliquez sur Alertes.</span><span class="sxs-lookup"><span data-stu-id="2bc6f-121">Click Alerts.</span></span>
    * <span data-ttu-id="2bc6f-122">Indiquez si vous voulez que des messages d'alerte soient envoyés à la fin du traitement par lots ou lorsque celui-ci rencontre une erreur ou est annulé.</span><span class="sxs-lookup"><span data-stu-id="2bc6f-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="2bc6f-123">Spécifiez ensuite si vous souhaitez que les alertes soient affichées sous la forme de messages contextuels.</span><span class="sxs-lookup"><span data-stu-id="2bc6f-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="2bc6f-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2bc6f-124">Click OK.</span></span>


