---
title: Configurer et exécuter la tâche de validation des déclarations
description: Cette procédure décrit la configuration et l’exécution d’un traitement par lots récurrent pour valider les relevés pour un magasin ou un groupe de magasins sélectionné.
author: josaw1
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 52baa707c36f3468263782dc8ec735e44af88e38
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804231"
---
# <a name="configure-and-run-job-to-post-statements"></a><span data-ttu-id="f922c-103">Configurer et exécuter la tâche de validation des déclarations</span><span class="sxs-lookup"><span data-stu-id="f922c-103">Configure and run job to post statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f922c-104">Cette procédure décrit la configuration et l’exécution d’un traitement par lots récurrent pour valider les relevés pour un magasin ou un groupe de magasins sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f922c-104">This procedure walks through configuring and running a recurrent batch job to post statements for a selected store or group of stores.</span></span> <span data-ttu-id="f922c-105">Cette procédure utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="f922c-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="f922c-106">Accédez à Tous les espaces de travail > ..</span><span class="sxs-lookup"><span data-stu-id="f922c-106">Go to All workspaces > ..</span></span> <span data-ttu-id="f922c-107">> Finances du magasin.</span><span class="sxs-lookup"><span data-stu-id="f922c-107">> Store financials.</span></span>
2. <span data-ttu-id="f922c-108">Cliquez sur Valider les relevés en mode de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="f922c-108">Click Post statements in batch.</span></span>
    * <span data-ttu-id="f922c-109">Sélectionnez une hiérarchie organisationnelle, puis dans l’arborescence des nœuds d’organisation, sélectionnez un magasin individuel ou un nœud.</span><span class="sxs-lookup"><span data-stu-id="f922c-109">Select an organizational hierarchy and then in the organization nodes tree, select either an individual store or a node.</span></span> <span data-ttu-id="f922c-110">Sélectionnez un nœud si vous souhaitez créer le traitement par lots pour un groupe de magasins.</span><span class="sxs-lookup"><span data-stu-id="f922c-110">Select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="f922c-111">Cliquez sur la flèche pour ajouter votre sélection.</span><span class="sxs-lookup"><span data-stu-id="f922c-111">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="f922c-112">Cliquez sur Exécuter dans l’onglet d’arrière-plan. ![Exécuter à l’arrière-plan](../dev-itpro/media/runbackground.png "Exécuter à l’arrière-plan")</span><span class="sxs-lookup"><span data-stu-id="f922c-112">Click the Run in the background tab. ![Run in the background](../dev-itpro/media/runbackground.png "Run in the background")</span></span> 
4. <span data-ttu-id="f922c-113">Activez ou désactivez la case à cocher Traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="f922c-113">Check or uncheck the Batch processing checkbox.</span></span>
<span data-ttu-id="f922c-114">![Traitement par lots](../dev-itpro/media/batchprocessing.png "Traitement par lots et répétition")</span><span class="sxs-lookup"><span data-stu-id="f922c-114">![Batch Processing](../dev-itpro/media/batchprocessing.png "Batch Processing & Recurrance")</span></span> 
5. <span data-ttu-id="f922c-115">Cliquez sur Répétition.</span><span class="sxs-lookup"><span data-stu-id="f922c-115">Click Recurrence.</span></span>
6. <span data-ttu-id="f922c-116">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="f922c-116">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="f922c-117">Dans le champ Heure de début, saisissez une heure.</span><span class="sxs-lookup"><span data-stu-id="f922c-117">In the Start time field, enter a time.</span></span>
    * <span data-ttu-id="f922c-118">Choisissez si vous souhaitez terminer la répétition après un nombre spécifique d’exécutions, à une date spécifique ou jamais.</span><span class="sxs-lookup"><span data-stu-id="f922c-118">Choose whether you want to end the recurrence after a specific number of runs, at a specific date, or never.</span></span> <span data-ttu-id="f922c-119">Sélectionnez ensuite les différentes options pour définir la fréquence d’exécution de la tâche.</span><span class="sxs-lookup"><span data-stu-id="f922c-119">Then choose the various options to define how frequently you want the job to run.</span></span>  
8. <span data-ttu-id="f922c-120">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f922c-120">Click OK.</span></span>
9. <span data-ttu-id="f922c-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f922c-121">Click OK.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]