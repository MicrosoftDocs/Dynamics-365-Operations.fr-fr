---
title: Configurer et exécuter la tâche de validation des déclarations
description: Cette procédure décrit la configuration et l'exécution d'un traitement par lots récurrent pour valider les relevés pour un magasin ou un groupe de magasins sélectionné.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 676216d90c50c0d3fa1a839cab7a734e624708ba
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550114"
---
# <a name="configure-and-run-job-to-post-statements"></a><span data-ttu-id="f67ee-103">Configurer et exécuter la tâche de validation des déclarations</span><span class="sxs-lookup"><span data-stu-id="f67ee-103">Configure and run job to post statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="f67ee-104">Cette procédure décrit la configuration et l'exécution d'un traitement par lots récurrent pour valider les relevés pour un magasin ou un groupe de magasins sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f67ee-104">This procedure walks through configuring and running a recurrent batch job to post statements for a selected store or group of stores.</span></span> <span data-ttu-id="f67ee-105">Cette procédure utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="f67ee-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="f67ee-106">Accédez à Tous les espaces de travail > ..</span><span class="sxs-lookup"><span data-stu-id="f67ee-106">Go to All workspaces > ..</span></span> <span data-ttu-id="f67ee-107">> Finances du magasin de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="f67ee-107">> Retail store financials.</span></span>
2. <span data-ttu-id="f67ee-108">Cliquez sur Valider les relevés.</span><span class="sxs-lookup"><span data-stu-id="f67ee-108">Click Post statements.</span></span>
    * <span data-ttu-id="f67ee-109">Sélectionnez une hiérarchie organisationnelle, puis dans l'arborescence des nœuds d'organisation, sélectionnez un magasin individuel ou un nœud.</span><span class="sxs-lookup"><span data-stu-id="f67ee-109">Select an organizational hierarchy and then in the organization nodes tree, select either an individual store or a node.</span></span> <span data-ttu-id="f67ee-110">Sélectionnez un nœud si vous souhaitez créer le traitement par lots pour un groupe de magasins.</span><span class="sxs-lookup"><span data-stu-id="f67ee-110">Select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="f67ee-111">Cliquez sur la flèche pour ajouter votre sélection.</span><span class="sxs-lookup"><span data-stu-id="f67ee-111">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="f67ee-112">Cliquez sur l'onglet Exécuter à l'arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="f67ee-112">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="f67ee-113">Activez ou désactivez la case à cocher Traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="f67ee-113">Check or uncheck the Batch processing checkbox.</span></span>
5. <span data-ttu-id="f67ee-114">Cliquez sur Répétition.</span><span class="sxs-lookup"><span data-stu-id="f67ee-114">Click Recurrence.</span></span>
6. <span data-ttu-id="f67ee-115">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="f67ee-115">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="f67ee-116">Dans le champ Heure de début, saisissez une heure.</span><span class="sxs-lookup"><span data-stu-id="f67ee-116">In the Start time field, enter a time.</span></span>
    * <span data-ttu-id="f67ee-117">Choisissez si vous souhaitez terminer la répétition après un nombre spécifique d'exécutions, à une date spécifique ou jamais.</span><span class="sxs-lookup"><span data-stu-id="f67ee-117">Choose whether you want to end the recurrence after a specific number of runs, at a specific date, or never.</span></span> <span data-ttu-id="f67ee-118">Sélectionnez ensuite les différentes options pour définir la fréquence d'exécution de la tâche.</span><span class="sxs-lookup"><span data-stu-id="f67ee-118">Then choose the various options to define how frequently you want the job to run.</span></span>  
8. <span data-ttu-id="f67ee-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f67ee-119">Click OK.</span></span>
9. <span data-ttu-id="f67ee-120">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f67ee-120">Click OK.</span></span>

