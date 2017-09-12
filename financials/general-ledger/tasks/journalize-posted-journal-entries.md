--- 
title: "Journaliser les entrées de journal validées"
description: "Cette procédure indique comment journaliser les entrées de journal validées."
author: aprilolson
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 490e9a4beda43f6e32b87792b11153c3e8e322d6
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="journalize-posted-journal-entries"></a><span data-ttu-id="e0933-103">Journaliser les entrées de journal validées</span><span class="sxs-lookup"><span data-stu-id="e0933-103">Journalize posted journal entries</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e0933-104">Cette procédure indique comment journaliser les entrées de journal validées.</span><span class="sxs-lookup"><span data-stu-id="e0933-104">This procedure shows how to journalize posted journal entries.</span></span> <span data-ttu-id="e0933-105">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="e0933-105">This procedure uses the USMF demo data company.</span></span>

1. <span data-ttu-id="e0933-106">Validez les paramètres de journalisation sous Comptabilité > Paramétrage de la comptabilité > Paramètres de comptabilité.</span><span class="sxs-lookup"><span data-stu-id="e0933-106">Validate the settings for journalizing under General ledger > Ledger setup > General ledger parameters.</span></span>
2. <span data-ttu-id="e0933-107">Le champ Journal comptable étendu peut être défini sur Oui ou Non.</span><span class="sxs-lookup"><span data-stu-id="e0933-107">The Extended ledger journal field can be set to Yes or No.</span></span> <span data-ttu-id="e0933-108">S'il est défini sur Oui, la sortie d'état est différente.</span><span class="sxs-lookup"><span data-stu-id="e0933-108">If Yes, the report output will be different.</span></span>
3. <span data-ttu-id="e0933-109">Indiquez si la période peut être clôturée si le processus de journalisation n'a pas été exécuté.</span><span class="sxs-lookup"><span data-stu-id="e0933-109">Select whether the period can be closed if the journalizing process hasn't been run.</span></span>
    * <span data-ttu-id="e0933-110">Si cette option est définie Oui, la période ne peut pas être clôturée tant que le processus de journalisation n'a pas été terminé pour cette période.</span><span class="sxs-lookup"><span data-stu-id="e0933-110">If this option is set to Yes, the period cannot be closed until the journalizing process has been completed for that period.</span></span>  
4. <span data-ttu-id="e0933-111">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e0933-111">Close the page.</span></span>
5. <span data-ttu-id="e0933-112">Accédez à Comptabilité > Tâches périodiques > Journalisation.</span><span class="sxs-lookup"><span data-stu-id="e0933-112">Go to General ledger > Periodic tasks > Journalizing.</span></span>
6. <span data-ttu-id="e0933-113">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="e0933-113">Click Filter.</span></span>
7. <span data-ttu-id="e0933-114">Mettez en surbrillance la ligne avec les critères de filtre que vous souhaitez définir.</span><span class="sxs-lookup"><span data-stu-id="e0933-114">Highlight the row with the filter criteria that you want to define.</span></span>
8. <span data-ttu-id="e0933-115">Dans le champ Critères, entrez ou sélectionnez les critères de filtre.</span><span class="sxs-lookup"><span data-stu-id="e0933-115">In the Criteria field, enter or select the filter criteria..</span></span>
9. <span data-ttu-id="e0933-116">Cliquez sur OK pour fermer la page de filtre.</span><span class="sxs-lookup"><span data-stu-id="e0933-116">Click OK to close the filter page.</span></span>
10. <span data-ttu-id="e0933-117">Cliquez sur OK pour démarrer le processus de journalisation.</span><span class="sxs-lookup"><span data-stu-id="e0933-117">Click OK to start the journalizing process.</span></span>
    * <span data-ttu-id="e0933-118">Un état est généré à la fin du processus.</span><span class="sxs-lookup"><span data-stu-id="e0933-118">A report will be generated after the process is complete.</span></span>  


