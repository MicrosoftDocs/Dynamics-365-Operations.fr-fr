---
title: Journaliser les entrées de journal validées
description: Cette procédure indique comment journaliser les entrées de journal validées.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cbf7ee8063487303cd4c8d2b76a8b44bacc86193
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846389"
---
# <a name="journalize-posted-journal-entries"></a><span data-ttu-id="93169-103">Journaliser les entrées de journal validées</span><span class="sxs-lookup"><span data-stu-id="93169-103">Journalize posted journal entries</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="93169-104">Cette procédure indique comment journaliser les entrées de journal validées.</span><span class="sxs-lookup"><span data-stu-id="93169-104">This procedure shows how to journalize posted journal entries.</span></span> <span data-ttu-id="93169-105">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="93169-105">This procedure uses the USMF demo data company.</span></span>

1. <span data-ttu-id="93169-106">Validez les paramètres de journalisation sous Comptabilité > Paramétrage de la comptabilité > Paramètres de comptabilité.</span><span class="sxs-lookup"><span data-stu-id="93169-106">Validate the settings for journalizing under General ledger > Ledger setup > General ledger parameters.</span></span>
2. <span data-ttu-id="93169-107">Le champ Journal comptable étendu peut être défini sur Oui ou Non.</span><span class="sxs-lookup"><span data-stu-id="93169-107">The Extended ledger journal field can be set to Yes or No.</span></span> <span data-ttu-id="93169-108">S'il est défini sur Oui, la sortie d'état est différente.</span><span class="sxs-lookup"><span data-stu-id="93169-108">If Yes, the report output will be different.</span></span>
3. <span data-ttu-id="93169-109">Indiquez si la période peut être clôturée si le processus de journalisation n'a pas été exécuté.</span><span class="sxs-lookup"><span data-stu-id="93169-109">Select whether the period can be closed if the journalizing process hasn't been run.</span></span>
    * <span data-ttu-id="93169-110">Si cette option est définie Oui, la période ne peut pas être clôturée tant que le processus de journalisation n'a pas été terminé pour cette période.</span><span class="sxs-lookup"><span data-stu-id="93169-110">If this option is set to Yes, the period cannot be closed until the journalizing process has been completed for that period.</span></span>  
4. <span data-ttu-id="93169-111">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="93169-111">Close the page.</span></span>
5. <span data-ttu-id="93169-112">Accédez à Comptabilité > Tâches périodiques > Journalisation.</span><span class="sxs-lookup"><span data-stu-id="93169-112">Go to General ledger > Periodic tasks > Journalizing.</span></span>
6. <span data-ttu-id="93169-113">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="93169-113">Click Filter.</span></span>
7. <span data-ttu-id="93169-114">Mettez en surbrillance la ligne avec les critères de filtre que vous souhaitez définir.</span><span class="sxs-lookup"><span data-stu-id="93169-114">Highlight the row with the filter criteria that you want to define.</span></span>
8. <span data-ttu-id="93169-115">Dans le champ Critères, entrez ou sélectionnez les critères de filtre.</span><span class="sxs-lookup"><span data-stu-id="93169-115">In the Criteria field, enter or select the filter criteria..</span></span>
9. <span data-ttu-id="93169-116">Cliquez sur OK pour fermer la page de filtre.</span><span class="sxs-lookup"><span data-stu-id="93169-116">Click OK to close the filter page.</span></span>
10. <span data-ttu-id="93169-117">Cliquez sur OK pour démarrer le processus de journalisation.</span><span class="sxs-lookup"><span data-stu-id="93169-117">Click OK to start the journalizing process.</span></span>
    * <span data-ttu-id="93169-118">Un état est généré à la fin du processus.</span><span class="sxs-lookup"><span data-stu-id="93169-118">A report will be generated after the process is complete.</span></span>  

