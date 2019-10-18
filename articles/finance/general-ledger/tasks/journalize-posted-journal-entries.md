---
title: Journaliser les entrées de journal validées
description: Cette procédure indique comment journaliser les entrées de journal validées.
author: aprilolson
manager: AnnBe
ms.date: 08/09/2019
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
ms.openlocfilehash: e20229ca910aa0d7d820434c22edf5a27030bba5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175421"
---
# <a name="journalize-posted-journal-entries"></a><span data-ttu-id="17805-103">Journaliser les entrées de journal validées</span><span class="sxs-lookup"><span data-stu-id="17805-103">Journalize posted journal entries</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="17805-104">Cette procédure indique comment journaliser les entrées de journal validées.</span><span class="sxs-lookup"><span data-stu-id="17805-104">This procedure shows how to journalize posted journal entries.</span></span> <span data-ttu-id="17805-105">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="17805-105">This procedure uses the USMF demo data company.</span></span>

1. <span data-ttu-id="17805-106">Dans le **Volet de navigation**, accédez à **Modules > Comptabilité > Paramétrage de la comptabilité > Paramètres de comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="17805-106">In the **Navigation pane**, go to **Modules > General ledger > Ledger setup > General ledger parameters**.</span></span>
2. <span data-ttu-id="17805-107">Le champ **Journal comptable étendu** peut être défini sur Oui ou Non.</span><span class="sxs-lookup"><span data-stu-id="17805-107">The **Extended ledger journal** field can be set to Yes or No.</span></span> <span data-ttu-id="17805-108">S'il est défini sur Oui, la sortie d'état est différente.</span><span class="sxs-lookup"><span data-stu-id="17805-108">If Yes, the report output will be different.</span></span>
3. <span data-ttu-id="17805-109">Indiquez si la période peut être clôturée si le processus de journalisation n'a pas été exécuté.</span><span class="sxs-lookup"><span data-stu-id="17805-109">Select whether the period can be closed if the journalizing process hasn't been run.</span></span> <span data-ttu-id="17805-110">Si cette option est définie Oui, la période ne peut pas être clôturée tant que le processus de journalisation n'a pas été terminé pour cette période.</span><span class="sxs-lookup"><span data-stu-id="17805-110">If this option is set to Yes, the period cannot be closed until the journalizing process has been completed for that period.</span></span>  
4. <span data-ttu-id="17805-111">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="17805-111">Close the page.</span></span>
5. <span data-ttu-id="17805-112">Dans le **Volet de navigation**, accédez à **Modules > Comptabilité > Tâches périodiques > Journalisation**.</span><span class="sxs-lookup"><span data-stu-id="17805-112">In the **Navigation pane**, go to **Modules > General ledger > Periodic tasks > Journalizing**.</span></span>
6. <span data-ttu-id="17805-113">Cliquez sur **Filtre**.</span><span class="sxs-lookup"><span data-stu-id="17805-113">Click **Filter**.</span></span>
7. <span data-ttu-id="17805-114">Mettez en surbrillance la ligne avec les critères de filtre que vous souhaitez définir.</span><span class="sxs-lookup"><span data-stu-id="17805-114">Highlight the row with the filter criteria that you want to define.</span></span>
8. <span data-ttu-id="17805-115">Dans le champ **Critères**, entrez ou sélectionnez les critères de filtre.</span><span class="sxs-lookup"><span data-stu-id="17805-115">In the **Criteria** field, enter or select the filter criteria..</span></span>
9. <span data-ttu-id="17805-116">Cliquez sur **OK** pour fermer la page de filtre.</span><span class="sxs-lookup"><span data-stu-id="17805-116">Click **OK** to close the filter page.</span></span>
10. <span data-ttu-id="17805-117">Cliquez sur **OK** pour démarrer le processus de journalisation.</span><span class="sxs-lookup"><span data-stu-id="17805-117">Click **OK** to start the journalizing process.</span></span> <span data-ttu-id="17805-118">Un état est généré à la fin du processus.</span><span class="sxs-lookup"><span data-stu-id="17805-118">A report will be generated after the process is complete.</span></span>  

