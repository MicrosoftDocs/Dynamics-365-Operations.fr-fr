---
title: Valider des journaux périodiques
description: Les journaux périodiques sont parfois appelés journaux récurrents car le montant, le texte, ainsi que d'autres informations sont répétés à chaque extraction du journal périodique.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransPeriodic, LedgerJournalTransDaily
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 241023c36723fa2dba5646e997b649741142c0ad
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834948"
---
# <a name="post-periodic-journals"></a><span data-ttu-id="bd5ac-103">Valider des journaux périodiques</span><span class="sxs-lookup"><span data-stu-id="bd5ac-103">Post periodic journals</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bd5ac-104">Les journaux périodiques sont parfois appelés journaux récurrents car le montant, le texte, ainsi que d'autres informations sont répétés à chaque extraction du journal périodique.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-104">Periodic journals are sometimes called recurring journals because the amount, text, and other information are repeated each time that the periodic journal is retrieved.</span></span> <span data-ttu-id="bd5ac-105">Lorsque vous créez le journal périodique vous devez spécifier l'intervalle de périodes de la récurrence (des jours ou des mois, par exemple).</span><span class="sxs-lookup"><span data-stu-id="bd5ac-105">When you create the periodic journal, you specify the period interval for the recurrence, such as days or months.</span></span> <span data-ttu-id="bd5ac-106">Ce guide de tâche crée un journal périodique avec une récurrence mensuelle.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-106">This task guide will create a periodic journal with a monthly recurrence.</span></span>



1. <span data-ttu-id="bd5ac-107">Accédez à Comptabilité > Tâches périodiques > Journaux périodiques.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-107">Go to General ledger > Periodic tasks > Periodic journals.</span></span>
2. <span data-ttu-id="bd5ac-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-108">Click New.</span></span>
3. <span data-ttu-id="bd5ac-109">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-109">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="bd5ac-110">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="bd5ac-111">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-111">In the Description field, type a value.</span></span>
    * <span data-ttu-id="bd5ac-112">La description contiendra par la suite le nom du journal périodique, veillez donc à lui attribuer un nom pertinent.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-112">The description will be the name of the Periodic journal when retrieved later so make sure to give it a relevant name.</span></span>  
6. <span data-ttu-id="bd5ac-113">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-113">Click Lines.</span></span>
    * <span data-ttu-id="bd5ac-114">Un journal périodique inclut généralement plusieurs lignes de journal.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-114">A periodic journal will typically include several journal lines.</span></span> <span data-ttu-id="bd5ac-115">Ce guide de tâche ajoutera toutefois une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-115">this task guide will however only add one line.</span></span>  
7. <span data-ttu-id="bd5ac-116">Entrez une date dans le champ Date.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-116">In the Date field, enter a date.</span></span>
    * <span data-ttu-id="bd5ac-117">Le champ Date contient la date de validation pour le transfert suivant dans le journal d'opérations diverses.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-117">The Date field contains the posting date for the next transfer to the daily journal.</span></span> <span data-ttu-id="bd5ac-118">Pour les journaux qui sont extraits chaque mois, il est recommandé d'utiliser la date du mois de validation, généralement la première ou la dernière date de la période.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-118">For journals that will be retrieved each month it is recommended to use the date in the month when it will be posted, typically the first or last date in the period.</span></span> <span data-ttu-id="bd5ac-119">Il est possible de laisser le champ Date vide et de donner une date lorsque le journal est récupéré, à l'aide du champ Date vide.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-119">It is possible to leave the Date field blank and to give a date when the journal is retrieved, using the Empty date field.</span></span>    <span data-ttu-id="bd5ac-120">Le champ est automatiquement mis à jour avec la date récurrente suivante lorsque des transactions sont extraites.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-120">The field is automatically updated to the next recurring date when transactions are retrieved.</span></span>  
8. <span data-ttu-id="bd5ac-121">Dans le champ Compte, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-121">In the Account field, specify the desired values.</span></span>
9. <span data-ttu-id="bd5ac-122">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="bd5ac-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-123">Close the page.</span></span>
11. <span data-ttu-id="bd5ac-124">Entrez un nombre dans le champ Débit.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-124">In the Debit field, enter a number.</span></span>
12. <span data-ttu-id="bd5ac-125">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-125">In the Offset account field, specify the desired values.</span></span>
13. <span data-ttu-id="bd5ac-126">Sélectionnez « Mois » dans le champ Unité.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-126">In the Unit field, select 'Months'.</span></span>
14. <span data-ttu-id="bd5ac-127">Entrez 1 dans le champ Nombre d'unités.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-127">In the Number of units field, enter '1'.</span></span>
15. <span data-ttu-id="bd5ac-128">Entrez une date dans le champ Dernière date.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-128">In the Last date field, enter a date.</span></span>
    * <span data-ttu-id="bd5ac-129">Le fait d'entrer le dernier jour dans la période précédente empêche de créer le journal récurrent par erreur dans la période de début incorrecte.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-129">Entering last date in the preceding period will prevent that the recurring journal by mistake is created in the wrong starting period.</span></span> <span data-ttu-id="bd5ac-130">La dernière date sera mise à jour ultérieurement à chaque extraction du journal périodique.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-130">Last date will later on be updated each time the periodic journal is retrieved.</span></span>  
16. <span data-ttu-id="bd5ac-131">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-131">Click Save.</span></span>
17. <span data-ttu-id="bd5ac-132">Allez dans le Tableau de bord par défaut.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-132">Go to Default dashboard.</span></span>
18. <span data-ttu-id="bd5ac-133">Accédez à Comptabilité > Entrées de journal > Journaux des opérations diverses.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-133">Go to General ledger > Journal entries > General journals.</span></span>
19. <span data-ttu-id="bd5ac-134">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-134">Click New.</span></span>
20. <span data-ttu-id="bd5ac-135">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-135">In the Name field, enter or select a value.</span></span>
21. <span data-ttu-id="bd5ac-136">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-136">In the list, find and select the desired record.</span></span>
22. <span data-ttu-id="bd5ac-137">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-137">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="bd5ac-138">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-138">In the Description field, type a value.</span></span>
24. <span data-ttu-id="bd5ac-139">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-139">Click Lines.</span></span>
25. <span data-ttu-id="bd5ac-140">Cliquez sur Journal périodique.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-140">Click Period journal.</span></span>
26. <span data-ttu-id="bd5ac-141">Cliquez sur Extraire le journal.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-141">Click Retrieve journal.</span></span>
27. <span data-ttu-id="bd5ac-142">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-142">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="bd5ac-143">La date de fin sert de date limite aux lignes de document périodiques.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-143">The To date serves as the cutoff date for the periodic voucher lines.</span></span> <span data-ttu-id="bd5ac-144">Selon le paramètre de récurrence, il est possible d'inclure la dernière date et la date de fin sur la même ligne plusieurs fois dans le journal obtenu.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-144">Based on the recurrence setting, the Last date and To date the same line might be included more than once in the resulting journal.</span></span> <span data-ttu-id="bd5ac-145">La date de fin est automatiquement mise à jour en fonction de la date de session du dernier transfert de la ligne périodique dans un journal.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-145">To date is automatically updated based on  session date of the last time the periodic line was transferred to a journal.</span></span>  
28. <span data-ttu-id="bd5ac-146">Saisissez ou sélectionnez une valeur dans le champ Numéro de journal périodique.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-146">In the Periodic journal number field, enter or select a value.</span></span>
29. <span data-ttu-id="bd5ac-147">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-147">In the list, click the link in the selected row.</span></span>
30. <span data-ttu-id="bd5ac-148">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-148">Click OK.</span></span>
    * <span data-ttu-id="bd5ac-149">Le journal périodique peut désormais être révisé, approuvé ou validé selon les besoins et le paramétrage.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-149">The period journal can now be reviewed, approved or posted depending on requirement and setup.</span></span>  

