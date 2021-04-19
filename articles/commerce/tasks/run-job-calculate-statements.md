---
title: Configurer et exécuter la tâche de calcul des déclarations
description: Cette procédure décrit la configuration et l’exécution de traitements par lots récurrents pour créer et calculer des relevés pour un magasin ou un groupe de magasins sélectionné.
author: josaw1
ms.date: 08/29/2018
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
ms.openlocfilehash: 11acedb719286cc6c9c79e22e8d0ceca2368baee
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802597"
---
# <a name="configure-and-run-job-to-calculate-statements"></a><span data-ttu-id="b33d6-103">Configurer et exécuter la tâche de calcul des déclarations</span><span class="sxs-lookup"><span data-stu-id="b33d6-103">Configure and run job to calculate statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b33d6-104">Cette procédure décrit la configuration et l’exécution de traitements par lots récurrents pour créer et calculer des relevés pour un magasin ou un groupe de magasins sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b33d6-104">This procedure walks through configuring and running recurrent batch jobs to create and calculate statements for a selected store or group of stores.</span></span> <span data-ttu-id="b33d6-105">Cette procédure utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="b33d6-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="b33d6-106">Accédez à Tous les espaces de travail > Finances du magasin.</span><span class="sxs-lookup"><span data-stu-id="b33d6-106">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="b33d6-107">Cliquez sur Calcul des relevés.</span><span class="sxs-lookup"><span data-stu-id="b33d6-107">Click Calculate statements.</span></span>
    * <span data-ttu-id="b33d6-108">Sélectionnez un magasin spécifique ou un nœud si vous souhaitez créer le traitement par lots pour un groupe de magasins.</span><span class="sxs-lookup"><span data-stu-id="b33d6-108">Select either a specific store, or a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="b33d6-109">Cliquez sur la flèche pour ajouter votre sélection.</span><span class="sxs-lookup"><span data-stu-id="b33d6-109">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="b33d6-110">Cliquez sur l’onglet Exécuter à l’arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="b33d6-110">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="b33d6-111">Sous Traitement par lots, sélectionnez « Oui ».</span><span class="sxs-lookup"><span data-stu-id="b33d6-111">Under Batch processing, select 'Yes'.</span></span>
5. <span data-ttu-id="b33d6-112">Cliquez sur Répétition.</span><span class="sxs-lookup"><span data-stu-id="b33d6-112">Click Recurrence.</span></span>
6. <span data-ttu-id="b33d6-113">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="b33d6-113">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="b33d6-114">Dans le champ Heure de début, saisissez une heure.</span><span class="sxs-lookup"><span data-stu-id="b33d6-114">In the Start time field, enter a time.</span></span>
8. <span data-ttu-id="b33d6-115">Sélectionnez l’option Pas de date de fin.</span><span class="sxs-lookup"><span data-stu-id="b33d6-115">Select the No end date option.</span></span>
9. <span data-ttu-id="b33d6-116">Dans le champ PatternUnit, saisissez « Jours ».</span><span class="sxs-lookup"><span data-stu-id="b33d6-116">In the PatternUnit field, enter 'Days'.</span></span>
10. <span data-ttu-id="b33d6-117">Entrez un numéro dans le champ Par.</span><span class="sxs-lookup"><span data-stu-id="b33d6-117">In the Per field, enter a number.</span></span>
11. <span data-ttu-id="b33d6-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b33d6-118">Click OK.</span></span>
12. <span data-ttu-id="b33d6-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b33d6-119">Click OK.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]