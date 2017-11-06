--- 
title: " Configurer et exécuter une tâche de validation des relevés"
description: "Cette procédure décrit la configuration et l'exécution d'un traitement par lots récurrent pour valider les relevés pour un magasin ou un groupe de magasins sélectionné."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0e2dae54cc9ccfc0a85046c5478e539585c3744d
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="configure-and-run-a-job-to-post-statements"></a><span data-ttu-id="0416c-103"> Configurer et exécuter une tâche de validation des relevés</span><span class="sxs-lookup"><span data-stu-id="0416c-103">Configure and run a job to post statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="0416c-104">Cette procédure décrit la configuration et l'exécution d'un traitement par lots récurrent pour valider les relevés pour un magasin ou un groupe de magasins sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0416c-104">This procedure walks through configuring and running a recurrent batch job to post statements for a selected store or group of stores.</span></span> <span data-ttu-id="0416c-105">Cette procédure utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="0416c-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="0416c-106">Accédez à Tous les espaces de travail > ..</span><span class="sxs-lookup"><span data-stu-id="0416c-106">Go to All workspaces > ..</span></span> <span data-ttu-id="0416c-107">> Finances du magasin de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="0416c-107">> Retail store financials.</span></span>
2. <span data-ttu-id="0416c-108">Cliquez sur Valider les relevés.</span><span class="sxs-lookup"><span data-stu-id="0416c-108">Click Post statements.</span></span>
    * <span data-ttu-id="0416c-109">Sélectionnez une hiérarchie organisationnelle, puis dans l'arborescence des nœuds d'organisation, sélectionnez un magasin individuel ou un nœud.</span><span class="sxs-lookup"><span data-stu-id="0416c-109">Select an organizational hierarchy and then in the organization nodes tree, select either an individual store or a node.</span></span> <span data-ttu-id="0416c-110">Sélectionnez un nœud si vous souhaitez créer le traitement par lots pour un groupe de magasins.</span><span class="sxs-lookup"><span data-stu-id="0416c-110">Select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="0416c-111">Cliquez sur la flèche pour ajouter votre sélection.</span><span class="sxs-lookup"><span data-stu-id="0416c-111">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="0416c-112">Cliquez sur l'onglet Exécuter à l'arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="0416c-112">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="0416c-113">Activez ou désactivez la case à cocher Traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="0416c-113">Check or uncheck the Batch processing checkbox.</span></span>
5. <span data-ttu-id="0416c-114">Cliquez sur Répétition.</span><span class="sxs-lookup"><span data-stu-id="0416c-114">Click Recurrence.</span></span>
6. <span data-ttu-id="0416c-115">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="0416c-115">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="0416c-116">Dans le champ Heure de début, saisissez une heure.</span><span class="sxs-lookup"><span data-stu-id="0416c-116">In the Start time field, enter a time.</span></span>
    * <span data-ttu-id="0416c-117">Choisissez si vous souhaitez terminer la répétition après un nombre spécifique d'exécutions, à une date spécifique ou jamais.</span><span class="sxs-lookup"><span data-stu-id="0416c-117">Choose whether you want to end the recurrence after a specific number of runs, at a specific date, or never.</span></span> <span data-ttu-id="0416c-118">Sélectionnez ensuite les différentes options pour définir la fréquence d'exécution de la tâche.</span><span class="sxs-lookup"><span data-stu-id="0416c-118">Then choose the various options to define how frequently you want the job to run.</span></span>  
8. <span data-ttu-id="0416c-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0416c-119">Click OK.</span></span>
9. <span data-ttu-id="0416c-120">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0416c-120">Click OK.</span></span>


