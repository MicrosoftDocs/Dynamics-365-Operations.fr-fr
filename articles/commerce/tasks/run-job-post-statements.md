---
title: Configurer et exécuter la tâche de validation des déclarations
description: Cette procédure décrit la configuration et l'exécution d'un traitement par lots récurrent pour valider les relevés pour un magasin ou un groupe de magasins sélectionné.
author: josaw1
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bed4cfb4875231d11ad76e4403c7995519d56e73
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003676"
---
# <a name="configure-and-run-job-to-post-statements"></a><span data-ttu-id="ebbc9-103">Configurer et exécuter la tâche de validation des déclarations</span><span class="sxs-lookup"><span data-stu-id="ebbc9-103">Configure and run job to post statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ebbc9-104">Cette procédure décrit la configuration et l'exécution d'un traitement par lots récurrent pour valider les relevés pour un magasin ou un groupe de magasins sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ebbc9-104">This procedure walks through configuring and running a recurrent batch job to post statements for a selected store or group of stores.</span></span> <span data-ttu-id="ebbc9-105">Cette procédure utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="ebbc9-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="ebbc9-106">Accédez à Tous les espaces de travail > ..</span><span class="sxs-lookup"><span data-stu-id="ebbc9-106">Go to All workspaces > ..</span></span> <span data-ttu-id="ebbc9-107">> Finances du magasin.</span><span class="sxs-lookup"><span data-stu-id="ebbc9-107">> Store financials.</span></span>
2. <span data-ttu-id="ebbc9-108">Cliquez sur Valider les relevés en mode de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="ebbc9-108">Click Post statements in batch.</span></span>
    * <span data-ttu-id="ebbc9-109">Sélectionnez une hiérarchie organisationnelle, puis dans l'arborescence des nœuds d'organisation, sélectionnez un magasin individuel ou un nœud.</span><span class="sxs-lookup"><span data-stu-id="ebbc9-109">Select an organizational hierarchy and then in the organization nodes tree, select either an individual store or a node.</span></span> <span data-ttu-id="ebbc9-110">Sélectionnez un nœud si vous souhaitez créer le traitement par lots pour un groupe de magasins.</span><span class="sxs-lookup"><span data-stu-id="ebbc9-110">Select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="ebbc9-111">Cliquez sur la flèche pour ajouter votre sélection.</span><span class="sxs-lookup"><span data-stu-id="ebbc9-111">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="ebbc9-112">Cliquez sur Exécuter dans l'onglet d'arrière-plan. ![Exécuter à l'arrière-plan](../dev-itpro/media/runbackground.png "Exécuter à l'arrière-plan")</span><span class="sxs-lookup"><span data-stu-id="ebbc9-112">Click the Run in the background tab. ![Run in the background](../dev-itpro/media/runbackground.png "Run in the background")</span></span> 
4. <span data-ttu-id="ebbc9-113">Activez ou désactivez la case à cocher Traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="ebbc9-113">Check or uncheck the Batch processing checkbox.</span></span>
<span data-ttu-id="ebbc9-114">![Traitement par lots](../dev-itpro/media/batchprocessing.png "Traitement par lots et répétition")</span><span class="sxs-lookup"><span data-stu-id="ebbc9-114">![Batch Processing](../dev-itpro/media/batchprocessing.png "Batch Processing & Recurrance")</span></span> 
5. <span data-ttu-id="ebbc9-115">Cliquez sur Répétition.</span><span class="sxs-lookup"><span data-stu-id="ebbc9-115">Click Recurrence.</span></span>
6. <span data-ttu-id="ebbc9-116">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="ebbc9-116">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="ebbc9-117">Dans le champ Heure de début, saisissez une heure.</span><span class="sxs-lookup"><span data-stu-id="ebbc9-117">In the Start time field, enter a time.</span></span>
    * <span data-ttu-id="ebbc9-118">Choisissez si vous souhaitez terminer la répétition après un nombre spécifique d'exécutions, à une date spécifique ou jamais.</span><span class="sxs-lookup"><span data-stu-id="ebbc9-118">Choose whether you want to end the recurrence after a specific number of runs, at a specific date, or never.</span></span> <span data-ttu-id="ebbc9-119">Sélectionnez ensuite les différentes options pour définir la fréquence d'exécution de la tâche.</span><span class="sxs-lookup"><span data-stu-id="ebbc9-119">Then choose the various options to define how frequently you want the job to run.</span></span>  
8. <span data-ttu-id="ebbc9-120">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ebbc9-120">Click OK.</span></span>
9. <span data-ttu-id="ebbc9-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ebbc9-121">Click OK.</span></span>

