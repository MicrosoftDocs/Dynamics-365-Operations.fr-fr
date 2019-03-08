---
title: Processus de droit aux avantages
description: Cette procédure décrit le fonctionnement du processus d'admissibilité aux avantages.
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 859bf2ef369173ce4b6bc380820ea157ae86e13a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "325547"
---
# <a name="benefit-eligibility-process"></a><span data-ttu-id="81e32-103">Processus de droit aux avantages</span><span class="sxs-lookup"><span data-stu-id="81e32-103">Benefit eligibility process</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="81e32-104">Cette procédure décrit le fonctionnement du processus d'admissibilité aux avantages.</span><span class="sxs-lookup"><span data-stu-id="81e32-104">This procedure shows how the benefit eligibility process works.</span></span> <span data-ttu-id="81e32-105">Lorsque le processus est terminé, vous pouvez afficher les résultats.</span><span class="sxs-lookup"><span data-stu-id="81e32-105">When the process is complete you can view the results.</span></span> <span data-ttu-id="81e32-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="81e32-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="81e32-107">Accédez à Ressources humaines > Avantages > Avantages.</span><span class="sxs-lookup"><span data-stu-id="81e32-107">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="81e32-108">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="81e32-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="81e32-109">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="81e32-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="81e32-110">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="81e32-110">Click Edit.</span></span>
5. <span data-ttu-id="81e32-111">Dans le champ Admissibilité, sélectionnez « Basée sur les règles ».</span><span class="sxs-lookup"><span data-stu-id="81e32-111">In the Eligibility field, select 'Rule based'.</span></span>
6. <span data-ttu-id="81e32-112">Dans le champ Type de règle, sélectionnez la règle de stratégie de droit aux avantages que vous souhaitez appliquer à l'avantage.</span><span class="sxs-lookup"><span data-stu-id="81e32-112">In the Rule type field, select the benefit policy rule you would like applied to the benefit.</span></span>
7. <span data-ttu-id="81e32-113">Cliquez sur Avantage dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="81e32-113">On the Action Pane, click Benefit.</span></span>
8. <span data-ttu-id="81e32-114">Cliquez sur Créer un événement de droit pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="81e32-114">Click Create eligibility event to open the drop dialog.</span></span>
9. <span data-ttu-id="81e32-115">Dans le champ Événement, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="81e32-115">In the Event field, type a value.</span></span>
10. <span data-ttu-id="81e32-116">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="81e32-116">In the Description field, type a value.</span></span>
11. <span data-ttu-id="81e32-117">Dans le champ Type d'événement, sélectionnez Inscription en cours.</span><span class="sxs-lookup"><span data-stu-id="81e32-117">In the Event type field, select 'Open enrollment'.</span></span>
12. <span data-ttu-id="81e32-118">Dans le champ Date de début de la couverture, entrez une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="81e32-118">In the Coverage start date field, enter a date and time.</span></span>
13. <span data-ttu-id="81e32-119">Dans le champ Date de début de la période d'inscription, entrez une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="81e32-119">In the Enrollment period start date field, enter a date and time.</span></span>
14. <span data-ttu-id="81e32-120">Dans le champ Jours avant l'inscription, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="81e32-120">In the Days to enroll field, enter a number.</span></span>
15. <span data-ttu-id="81e32-121">Cliquez sur Créer un événement.</span><span class="sxs-lookup"><span data-stu-id="81e32-121">Click Create event.</span></span>
16. <span data-ttu-id="81e32-122">Dans l'organisateur Collaborateurs, cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="81e32-122">Click Add in the Workers FastTab.</span></span>
17. <span data-ttu-id="81e32-123">Dans le champ Afficher par type, sélectionnez Employés.</span><span class="sxs-lookup"><span data-stu-id="81e32-123">In the Show by type field, select 'Employees'.</span></span>
18. <span data-ttu-id="81e32-124">Dans le champ Afficher par entité juridique, sélectionnez Entité juridique actuelle.</span><span class="sxs-lookup"><span data-stu-id="81e32-124">In the Show by legal entity field, select 'Current legal entity'.</span></span>
19. <span data-ttu-id="81e32-125">Dans la liste, cochez ou décochez toutes les lignes.</span><span class="sxs-lookup"><span data-stu-id="81e32-125">In the list, mark or unmark all rows.</span></span>
20. <span data-ttu-id="81e32-126">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="81e32-126">Click OK.</span></span>
21. <span data-ttu-id="81e32-127">Cliquez sur Traiter.</span><span class="sxs-lookup"><span data-stu-id="81e32-127">Click Process.</span></span>
22. <span data-ttu-id="81e32-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="81e32-128">Click OK.</span></span>
23. <span data-ttu-id="81e32-129">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="81e32-129">Refresh the page.</span></span>
24. <span data-ttu-id="81e32-130">Cliquez sur Afficher les résultats.</span><span class="sxs-lookup"><span data-stu-id="81e32-130">Click Show results.</span></span>
25. <span data-ttu-id="81e32-131">Ouvrez le filtre de colonne État.</span><span class="sxs-lookup"><span data-stu-id="81e32-131">Open Status column filter.</span></span>
26. <span data-ttu-id="81e32-132">Trier de A à Z</span><span class="sxs-lookup"><span data-stu-id="81e32-132">Sort A to Z</span></span>

