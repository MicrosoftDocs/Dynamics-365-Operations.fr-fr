--- 
title: "Configurer et exécuter la tâche de calcul des déclarations"
description: "Cette procédure décrit la configuration et l'exécution de traitements par lots récurrents pour créer et calculer des relevés pour un magasin ou un groupe de magasins sélectionné."
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: f52603672e95d0ae4973844851c4ed260484e5f0
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="configure-and-run-job-to-calculate-statements"></a><span data-ttu-id="512e5-103">Configurer et exécuter la tâche de calcul des déclarations</span><span class="sxs-lookup"><span data-stu-id="512e5-103">Configure and run job to calculate statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="512e5-104">Cette procédure décrit la configuration et l'exécution de traitements par lots récurrents pour créer et calculer des relevés pour un magasin ou un groupe de magasins sélectionné.</span><span class="sxs-lookup"><span data-stu-id="512e5-104">This procedure walks through configuring and running recurrent batch jobs to create and calculate statements for a selected store or group of stores.</span></span> <span data-ttu-id="512e5-105">Cette procédure utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="512e5-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="512e5-106">Accédez à Tous les espaces de travail > Finances du magasin de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="512e5-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="512e5-107">Cliquez sur Calcul des relevés.</span><span class="sxs-lookup"><span data-stu-id="512e5-107">Click Calculate statements.</span></span>
    * <span data-ttu-id="512e5-108">Sélectionnez un magasin spécifique ou un nœud si vous souhaitez créer le traitement par lots pour un groupe de magasins.</span><span class="sxs-lookup"><span data-stu-id="512e5-108">Select either a specific store, or a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="512e5-109">Cliquez sur la flèche pour ajouter votre sélection.</span><span class="sxs-lookup"><span data-stu-id="512e5-109">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="512e5-110">Cliquez sur l'onglet Exécuter à l'arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="512e5-110">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="512e5-111">Sous Traitement par lots, sélectionnez « Oui ».</span><span class="sxs-lookup"><span data-stu-id="512e5-111">Under Batch processing, select 'Yes'.</span></span>
5. <span data-ttu-id="512e5-112">Cliquez sur Répétition.</span><span class="sxs-lookup"><span data-stu-id="512e5-112">Click Recurrence.</span></span>
6. <span data-ttu-id="512e5-113">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="512e5-113">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="512e5-114">Dans le champ Heure de début, saisissez une heure.</span><span class="sxs-lookup"><span data-stu-id="512e5-114">In the Start time field, enter a time.</span></span>
8. <span data-ttu-id="512e5-115">Sélectionnez l'option Pas de date de fin.</span><span class="sxs-lookup"><span data-stu-id="512e5-115">Select the No end date option.</span></span>
9. <span data-ttu-id="512e5-116">Dans le champ PatternUnit, saisissez « Jours ».</span><span class="sxs-lookup"><span data-stu-id="512e5-116">In the PatternUnit field, enter 'Days'.</span></span>
10. <span data-ttu-id="512e5-117">Entrez un numéro dans le champ Par.</span><span class="sxs-lookup"><span data-stu-id="512e5-117">In the Per field, enter a number.</span></span>
11. <span data-ttu-id="512e5-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="512e5-118">Click OK.</span></span>
12. <span data-ttu-id="512e5-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="512e5-119">Click OK.</span></span>


