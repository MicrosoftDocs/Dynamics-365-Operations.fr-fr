--- 
title: " Configurer et exécuter une tâche de calcul des déclarations"
description: "Cette procédure décrit la configuration et l'exécution de traitements par lots récurrents pour créer et calculer des relevés pour un magasin ou un groupe de magasins sélectionné."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 54dacef8ae0afd1fb706d5c67fa77b315a2cb4de
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---
# <a name="configure-and-run-a-job-to-calculate-statements"></a><span data-ttu-id="92f82-103"> Configurer et exécuter une tâche de calcul des déclarations</span><span class="sxs-lookup"><span data-stu-id="92f82-103">Configure and run a job to calculate statements</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="92f82-104">Cette procédure décrit la configuration et l'exécution de traitements par lots récurrents pour créer et calculer des relevés pour un magasin ou un groupe de magasins sélectionné.</span><span class="sxs-lookup"><span data-stu-id="92f82-104">This procedure walks through configuring and running recurrent batch jobs to create and calculate statements for a selected store or group of stores.</span></span> <span data-ttu-id="92f82-105">Cette procédure utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="92f82-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="92f82-106">Accédez à Tous les espaces de travail > Finances du magasin de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="92f82-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="92f82-107">Cliquez sur Calcul des relevés.</span><span class="sxs-lookup"><span data-stu-id="92f82-107">Click Calculate statements.</span></span>
    * <span data-ttu-id="92f82-108">Sélectionnez un magasin spécifique ou un nœud si vous souhaitez créer le traitement par lots pour un groupe de magasins.</span><span class="sxs-lookup"><span data-stu-id="92f82-108">Select either a specific store, or a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="92f82-109">Cliquez sur la flèche pour ajouter votre sélection.</span><span class="sxs-lookup"><span data-stu-id="92f82-109">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="92f82-110">Cliquez sur l'onglet Exécuter à l'arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="92f82-110">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="92f82-111">Sous Traitement par lots, sélectionnez « Oui ».</span><span class="sxs-lookup"><span data-stu-id="92f82-111">Under Batch processing, select 'Yes'.</span></span>
5. <span data-ttu-id="92f82-112">Cliquez sur Répétition.</span><span class="sxs-lookup"><span data-stu-id="92f82-112">Click Recurrence.</span></span>
6. <span data-ttu-id="92f82-113">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="92f82-113">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="92f82-114">Dans le champ Heure de début, saisissez une heure.</span><span class="sxs-lookup"><span data-stu-id="92f82-114">In the Start time field, enter a time.</span></span>
8. <span data-ttu-id="92f82-115">Sélectionnez l'option Pas de date de fin.</span><span class="sxs-lookup"><span data-stu-id="92f82-115">Select the No end date option.</span></span>
9. <span data-ttu-id="92f82-116">Dans le champ PatternUnit, saisissez « Jours ».</span><span class="sxs-lookup"><span data-stu-id="92f82-116">In the PatternUnit field, enter 'Days'.</span></span>
10. <span data-ttu-id="92f82-117">Entrez un numéro dans le champ Par.</span><span class="sxs-lookup"><span data-stu-id="92f82-117">In the Per field, enter a number.</span></span>
11. <span data-ttu-id="92f82-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="92f82-118">Click OK.</span></span>
12. <span data-ttu-id="92f82-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="92f82-119">Click OK.</span></span>


