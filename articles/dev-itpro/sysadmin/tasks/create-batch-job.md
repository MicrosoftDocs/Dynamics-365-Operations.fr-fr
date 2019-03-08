---
title: Création d'un traitement par lots
description: Un traitement par lots est un groupe de tâches soumis à une instance Serveur d'objets d'application (AOS) pour un traitement automatique.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fbb844ebcf8d4b47b127132a5bf0ea45fa40f747
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "313357"
---
# <a name="create-a-batch-job"></a><span data-ttu-id="20ecf-103">Création d'un traitement par lots</span><span class="sxs-lookup"><span data-stu-id="20ecf-103">Create a batch job</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="20ecf-104">Un traitement par lots est un groupe de tâches soumis à une instance Serveur d'objets d'application (AOS) pour un traitement automatique.</span><span class="sxs-lookup"><span data-stu-id="20ecf-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="20ecf-105">L'exécution de traitements par lots utilise les informations d'authentification de sécurité de l'utilisateur qui a créé la tâche.</span><span class="sxs-lookup"><span data-stu-id="20ecf-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="20ecf-106">Procédez comme suit pour créer un traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="20ecf-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="20ecf-107">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="20ecf-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="20ecf-108">Créer le traitement par lots</span><span class="sxs-lookup"><span data-stu-id="20ecf-108">Create the batch job</span></span>
1. <span data-ttu-id="20ecf-109">Allez dans Administration du système > Recherches > Traitements par lots.</span><span class="sxs-lookup"><span data-stu-id="20ecf-109">Go to System administration > Inquiries > Batch jobs.</span></span>
2. <span data-ttu-id="20ecf-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="20ecf-110">Click New.</span></span>
3. <span data-ttu-id="20ecf-111">Tapez une valeur dans le champ Description de la tâche.</span><span class="sxs-lookup"><span data-stu-id="20ecf-111">In the Job description field, type a value.</span></span>
4. <span data-ttu-id="20ecf-112">Dans le champ Date/heure de début réel, entrez une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="20ecf-112">In the Scheduled start date/time field, enter a date and time.</span></span>
5. <span data-ttu-id="20ecf-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="20ecf-113">Click Save.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="20ecf-114">Créer une répétition</span><span class="sxs-lookup"><span data-stu-id="20ecf-114">Create a recurrence</span></span>
1. <span data-ttu-id="20ecf-115">Dans le volet Actions, cliquez sur Traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="20ecf-115">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="20ecf-116">Cliquez sur Répétition.</span><span class="sxs-lookup"><span data-stu-id="20ecf-116">Click Recurrence.</span></span>
    * <span data-ttu-id="20ecf-117">Utilisez ces options pour entrer une gamme et un modèle pour la répétition.</span><span class="sxs-lookup"><span data-stu-id="20ecf-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="20ecf-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="20ecf-118">Click OK.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="20ecf-119">Ajouter des alertes</span><span class="sxs-lookup"><span data-stu-id="20ecf-119">Add alerts</span></span>
1. <span data-ttu-id="20ecf-120">Dans le volet Actions, cliquez sur Traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="20ecf-120">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="20ecf-121">Cliquez sur Alertes.</span><span class="sxs-lookup"><span data-stu-id="20ecf-121">Click Alerts.</span></span>
    * <span data-ttu-id="20ecf-122">Indiquez si vous voulez que des messages d'alerte soient envoyés à la fin du traitement par lots ou lorsque celui-ci rencontre une erreur ou est annulé.</span><span class="sxs-lookup"><span data-stu-id="20ecf-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="20ecf-123">Spécifiez ensuite si vous souhaitez que les alertes soient affichées sous la forme de messages contextuels.</span><span class="sxs-lookup"><span data-stu-id="20ecf-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="20ecf-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="20ecf-124">Click OK.</span></span>

