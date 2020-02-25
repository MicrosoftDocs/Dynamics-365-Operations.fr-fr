---
title: Créer une question fermée
description: Les questions fermées permettent à la personne interrogée de choisir des options.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 55a41ae639970eb3324a5760af7f6dd5fb8f2ad5
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009059"
---
# <a name="create-a-closed-ended-question"></a><span data-ttu-id="be80d-103">Créer une question fermée</span><span class="sxs-lookup"><span data-stu-id="be80d-103">Create a closed ended question</span></span>



<span data-ttu-id="be80d-104">Les questions fermées permettent à la personne interrogée de choisir des options.</span><span class="sxs-lookup"><span data-stu-id="be80d-104">Closed-ended questions allow you to provide options for the respondent to choose from.</span></span> <span data-ttu-id="be80d-105">Vous devez tout d'abord créer le groupe de réponses avec des réponses, puis créer la question qui va utiliser le groupe de réponses.</span><span class="sxs-lookup"><span data-stu-id="be80d-105">First, you need to create the Answer group with the answers, then create the question that will use the answer group.</span></span> <span data-ttu-id="be80d-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="be80d-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-an-answer-group"></a><span data-ttu-id="be80d-107">Créer un groupe de réponses</span><span class="sxs-lookup"><span data-stu-id="be80d-107">Create an answer group</span></span>
1. <span data-ttu-id="be80d-108">Allez dans Questionnaire > Conception > Groupes de réponses.</span><span class="sxs-lookup"><span data-stu-id="be80d-108">Go to Questionnaire > Design > Answer groups.</span></span>
2. <span data-ttu-id="be80d-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="be80d-109">Click New.</span></span>
3. <span data-ttu-id="be80d-110">Tapez une valeur dans le champ Groupe de réponses.</span><span class="sxs-lookup"><span data-stu-id="be80d-110">In the Answer group field, type a value.</span></span>
4. <span data-ttu-id="be80d-111">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="be80d-111">In the Description field, type a value.</span></span>
    * <span data-ttu-id="be80d-112">Utilisez la fonctionnalité Aléatoire pour placer de manière aléatoire les réponses dans une commande différente chaque fois que le groupe de réponses est utilisé pour une question.</span><span class="sxs-lookup"><span data-stu-id="be80d-112">Use the Randomize functionality to randomly place the answers in a different order each time the answer group is used for a question.</span></span>  
5. <span data-ttu-id="be80d-113">Cliquez sur Réponse.</span><span class="sxs-lookup"><span data-stu-id="be80d-113">Click Answer.</span></span>
6. <span data-ttu-id="be80d-114">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="be80d-114">Click New.</span></span>
    * <span data-ttu-id="be80d-115">Le numéro de souche contrôle l'ordre dans lequel les réponses sont affichées, sauf si la fonctionnalité Aléatoire est activée pour le groupe de réponses.</span><span class="sxs-lookup"><span data-stu-id="be80d-115">Sequence number controls the order in which the answers are displayed, unless Randomize is selected for the Answer group.</span></span>  
    * <span data-ttu-id="be80d-116">Les points peuvent être affectés aux réponses pour être utilisées pour marquer les points le questionnaire.</span><span class="sxs-lookup"><span data-stu-id="be80d-116">Points can be awarded to answers for use in scoring the questionnaire.</span></span>  
7. <span data-ttu-id="be80d-117">Entrez un nombre dans le champ Points.</span><span class="sxs-lookup"><span data-stu-id="be80d-117">In the Points field, enter a number.</span></span>
    * <span data-ttu-id="be80d-118">La réponse correcte peut être marquée pour indiquer que la réponse sélectionnée est correcte.</span><span class="sxs-lookup"><span data-stu-id="be80d-118">The correct answer can be marked to indicate that the selected answer is the correct one.</span></span> <span data-ttu-id="be80d-119">Cette opération peut être utilisée pour marquer les points du questionnaire.</span><span class="sxs-lookup"><span data-stu-id="be80d-119">This can be used for scoring the questionnaire.</span></span>  
8. <span data-ttu-id="be80d-120">Tapez une valeur dans le champ Réponse.</span><span class="sxs-lookup"><span data-stu-id="be80d-120">In the Answer field, type a value.</span></span>
    * <span data-ttu-id="be80d-121">Continuez à créer des options de sélection de réponse pour le groupe de réponses.</span><span class="sxs-lookup"><span data-stu-id="be80d-121">Continue to create answer selection options for the answer group.</span></span>  
9. <span data-ttu-id="be80d-122">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="be80d-122">Click New.</span></span>
10. <span data-ttu-id="be80d-123">Entrez un nombre dans le champ Points.</span><span class="sxs-lookup"><span data-stu-id="be80d-123">In the Points field, enter a number.</span></span>
11. <span data-ttu-id="be80d-124">Tapez une valeur dans le champ Réponse.</span><span class="sxs-lookup"><span data-stu-id="be80d-124">In the Answer field, type a value.</span></span>
12. <span data-ttu-id="be80d-125">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="be80d-125">Click New.</span></span>
13. <span data-ttu-id="be80d-126">Entrez un nombre dans le champ Points.</span><span class="sxs-lookup"><span data-stu-id="be80d-126">In the Points field, enter a number.</span></span>
14. <span data-ttu-id="be80d-127">Tapez une valeur dans le champ Réponse.</span><span class="sxs-lookup"><span data-stu-id="be80d-127">In the Answer field, type a value.</span></span>
15. <span data-ttu-id="be80d-128">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="be80d-128">Click New.</span></span>
16. <span data-ttu-id="be80d-129">Entrez un nombre dans le champ Points.</span><span class="sxs-lookup"><span data-stu-id="be80d-129">In the Points field, enter a number.</span></span>
17. <span data-ttu-id="be80d-130">Tapez une valeur dans le champ Réponse.</span><span class="sxs-lookup"><span data-stu-id="be80d-130">In the Answer field, type a value.</span></span>
18. <span data-ttu-id="be80d-131">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="be80d-131">Click New.</span></span>
19. <span data-ttu-id="be80d-132">Entrez un nombre dans le champ Points.</span><span class="sxs-lookup"><span data-stu-id="be80d-132">In the Points field, enter a number.</span></span>
20. <span data-ttu-id="be80d-133">Tapez une valeur dans le champ Réponse.</span><span class="sxs-lookup"><span data-stu-id="be80d-133">In the Answer field, type a value.</span></span>
21. <span data-ttu-id="be80d-134">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="be80d-134">Close the page.</span></span>
22. <span data-ttu-id="be80d-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="be80d-135">Close the page.</span></span>

## <a name="create-the-question"></a><span data-ttu-id="be80d-136">Créer la question</span><span class="sxs-lookup"><span data-stu-id="be80d-136">Create the question</span></span>
1. <span data-ttu-id="be80d-137">Accédez à Questionnaire > Conception > Questions.</span><span class="sxs-lookup"><span data-stu-id="be80d-137">Go to Questionnaire > Design > Questions.</span></span>
2. <span data-ttu-id="be80d-138">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="be80d-138">Click New.</span></span>
3. <span data-ttu-id="be80d-139">Utilisez le champ Type pour regrouper les questions associées.</span><span class="sxs-lookup"><span data-stu-id="be80d-139">Use the Type field to group related questions together.</span></span>
    * <span data-ttu-id="be80d-140">Vous pouvez utiliser les types d'entrée Case à cocher, bouton Autre ou Zone de liste modifiable pour des questions fermées.</span><span class="sxs-lookup"><span data-stu-id="be80d-140">You can use input types of Check box, Alternative button, or Combo box for closed-ended questions.</span></span>  
4. <span data-ttu-id="be80d-141">Sélectionnez une option dans le champ Type de saisie.</span><span class="sxs-lookup"><span data-stu-id="be80d-141">In the Input type field, select an option.</span></span>
5. <span data-ttu-id="be80d-142">Saisissez ou sélectionnez une valeur dans le champ Groupe de réponses.</span><span class="sxs-lookup"><span data-stu-id="be80d-142">In the Answer group field, enter or select a value.</span></span>
6. <span data-ttu-id="be80d-143">Tapez une valeur dans le champ Texte.</span><span class="sxs-lookup"><span data-stu-id="be80d-143">In the Text field, type a value.</span></span>

